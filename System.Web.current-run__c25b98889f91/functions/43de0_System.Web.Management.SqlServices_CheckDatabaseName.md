# System.Web.Management.SqlServices::CheckDatabaseName

- ea: `0x43de0`
- end: `0x43e6f`
- name: `System.Web.Management.SqlServices::CheckDatabaseName`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x43db0`
- `0x44100`

## callees

- `0x34fa0`
- `0x43de0`
- `0x43ef0`

## string_xrefs

- `0x43dfc`: `SQL_Services_Database_Empty_Or_Space_Only_Arg`
- `0x43e3f`: `SQL_Services_Database_contains_invalid_chars`

## pseudocode

```c

```

## disassembly

```asm
0x43de0  ldarg.0
0x43de1  ldind.ref
0x43de2  brfalse.s loc_43E4F
0x43de4  ldarg.0
0x43de5  ldarg.0
0x43de6  ldind.ref
0x43de7  ldc.i4.0
0x43de8  newarr   [mscorlib]System.Char
0x43ded  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x43df2  stind.ref
0x43df3  ldarg.0
0x43df4  ldind.ref
0x43df5  callvirt instance int32 [mscorlib]System.String::get_Length()
0x43dfa  brtrue.s loc_43E0C
0x43dfc  ldstr    aSqlServicesDat// "SQL_Services_Database_Empty_Or_Space_On"...
0x43e01  call     string System.Web.SR::GetString(string name)
0x43e06  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x43e0b  throw
0x43e0c  ldarg.0
0x43e0d  ldarg.0
0x43e0e  ldind.ref
0x43e0f  call     string System.Web.Management.SqlServices::RemoveSquareBrackets(string database)
0x43e14  stind.ref
0x43e15  ldarg.0
0x43e16  ldind.ref
0x43e17  ldstr    asc_1BD99E// "'"
0x43e1c  callvirt instance bool [mscorlib]System.String::Contains(string)
0x43e21  brtrue.s loc_43E3F
0x43e23  ldarg.0
0x43e24  ldind.ref
0x43e25  ldstr    asc_1B2EBC// "["
0x43e2a  callvirt instance bool [mscorlib]System.String::Contains(string)
0x43e2f  brtrue.s loc_43E3F
0x43e31  ldarg.0
0x43e32  ldind.ref
0x43e33  ldstr    asc_1B633C// "]"
0x43e38  callvirt instance bool [mscorlib]System.String::Contains(string)
0x43e3d  brfalse.s loc_43E4F
0x43e3f  ldstr    aSqlServicesDat_0// "SQL_Services_Database_contains_invalid_"...
0x43e44  call     string System.Web.SR::GetString(string name)
0x43e49  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x43e4e  throw
0x43e4f  ldarg.0
0x43e50  ldind.ref
0x43e51  brtrue.s loc_43E5B
0x43e53  ldarg.0
0x43e54  ldsfld   string System.Web.Management.SqlServices::DEFAULT_DB
0x43e59  stind.ref
0x43e5a  ret
0x43e5b  ldarg.0
0x43e5c  ldstr    asc_1B2EBC// "["
0x43e61  ldarg.0
0x43e62  ldind.ref
0x43e63  ldstr    asc_1B633C// "]"
0x43e68  call     string [mscorlib]System.String::Concat(string, string, string)
0x43e6d  stind.ref
0x43e6e  ret
```
