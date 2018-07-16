# Frames - scheduling API

An managing and scheduling API for small buisnesses.

[---Only supports one manager/admin per company---]

***
***

## API Documentation

### Admin endpoints

#### `/admins`

Endpoint representing all admins using Frames (manager for a business/company).

***

```
GET /admins
```

Get an `[array]` of all admins of Frames.

*URL parameters*:

None

*Data parameters*:

None

*Query string parameters*:

None

*Returns*:

An `[array]` of all admins.

*Example*:

```
> GET /admin

< Status: 200 OK
<
<
<
```

***

```
POST /admins
```

Add an admin to Frames

*URL Parameters*:

None

*Data parameters*:

* The admin to add

*Query string parameters*:

None

*Returns*:

An empty object.

*Example*:

```
> POST /admins
> {
>
> }

< Status: 201 Created
< Location: /admin/:adminId
< {
<
<
< }
```

***
***

__`/admins/:adminId`__

Endpoint representing one admin

***

```
GET /admins/:adminId
```

Get a single user of Frames.

*URL parameters*:

* `adminId` - The id of the admin.

*Data parameters*:

None

*Query string parameters*:

None

*Returns*:

A JSON object of the user.

*Example*:

```
> GET /admins/:adminId

< Status: 200 OK
< {
<     "id": adminId,
<     ...
< }
```

***

```
PUT /admins/:adminId
```

Add or edit a Frames admin.

*URL parameters*:

* `adminId` - The id of the admin to add or edit.

*Data parameters*:

* The admin to add or edit

*Query string parameters*:

None

*Returns*:

An empty object.

*Example*:

```
> PUT /admins/:adminId
> {
>
> }

< Status: 200 OK
< {
< }
```

***

```
DELETE /admins/:adminId
```

Delete a Frames admin.

*URL parameters*:

* `adminId` - The id of the admin to delete.

*Data parameters*:

None

*Query string parameters*:

None

*Returns*:

An empty object.

*Example*:

```
> DELETE /admin/adminId

< Status: 200 OK
< {
<
<
< }
```

***
***
***

### Employee Endpoint (Protected)

#### `/employees`

Endpoint representing all employees using Frames
***
***

__`/employees/:adminId`__

Endpoint representing all employee under a particular admin

***

```
GET /employees/:adminId
```

get all employees for a single business.

*URL parameters*:

* `adminId` - id of the admin the employee works for

*Data parameters*:

None

*Query string parameters*:

None

*Returns*:

A JSON array of the entire week of all employee frames for a admin.

***

```
POST /employees/:adminId
```

create a single/many employee(s) for a admin.

*URL parameters*:

* `adminId` - id of the admin the employee works for

*Data parameters*:

* The array of employee(s) to create

***
***

__`/employees/:adminId/:employeeId`__

Endpoint representing an employee under a particular admin

```
GET /employees/:adminId/:employeeId
```

get a single employee for under an admin.

*URL parameters*:

* `adminId` - id of the admin the employee works for

* `employeeId` - id of the employee

*Data parameters*:

None

*Query string parameters*:

None

*Returns*:

A JSON object of one the employees for an admin.

***

```
PUT /employees/:adminId/:employeeId
```

update a single employee under an admin.

*URL parameters*:

* `adminId` - id of the admin the employee works for

* `employeeId` - id of the employee

*Data parameters*:

* The employee data to update

***
***
***

### Frames endpoint (Protected)

#### `/frames`

Endpoint representing the concept of the 'frame' or chunk of time used for scheduling

***
***

__`/frames/:adminId`__

Endpoint representing all 'frames' for a particular admin.

***

```
GET /frames/:adminId
```

get the 'frames' of an admin (The schedule for a day).

*URL parameters*:

* `adminId` - id of the admin the employee works for

*Query string parameters*:

_**note** only a query range up to a 'frame' of 24 hours.*_

* startDate=[ISO-Date]

* endDate=[ISO-Date]

***
***

__`/frames/:employeeId`__

Endpoint representing all 'frames' for a particular employee.

***

```
GET /frames/:employeeId
```

get the 'frame' of a single employee (schedule for one employee).

*URL parameters*:

* `employeeId` - id of the employee

***
***

__`/frames/:frameId`__

Endpoint representing a 'frame'.

```
GET /frames/:frameId
```

get a single 'frame' of a single employee.

*URL parameters*:

* `frameId` - id of the frame

***
