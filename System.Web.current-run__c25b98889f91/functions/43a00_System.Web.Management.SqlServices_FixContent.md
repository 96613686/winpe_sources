# System.Web.Management.SqlServices::FixContent

- ea: `0x43a00`
- end: `0x43c03`
- name: `System.Web.Management.SqlServices::FixContent`
- size: `515`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x43900`
- `0x43c30`
- `0x43e70`

## callees

- `0x34fa0`
- `0x43a00`
- `0x43ef0`

## string_xrefs

- `0x43a1e`: `'sstype_temp'`
- `0x43a6d`: `'sstype_temp'`
- `0x43a3f`: `[tempdb]`
- `0x43a8e`: `[tempdb]`

## pseudocode

```c

```

## disassembly

```asm
0x43a00  ldarg.1
0x43a01  brfalse.s loc_43A0B
0x43a03  ldarg.1
0x43a04  call     string System.Web.Management.SqlServices::RemoveSquareBrackets(string database)
0x43a09  starg.s  1
0x43a0b  ldarg.3
0x43a0c  brfalse  loc_43AE6
0x43a11  ldarg.s  4
0x43a13  brfalse  loc_43B2F
0x43a18  ldarg.s  4
0x43a1a  ldc.i4.1
0x43a1b  bne.un.s loc_43A64
0x43a1d  ldarg.0
0x43a1e  ldstr    aSstypeTemp// "'sstype_temp'"
0x43a23  ldstr    asc_1BD99E// "'"
0x43a28  ldsfld   string System.Web.Management.SqlServices::SSTYPE_PERSISTED
0x43a2d  ldstr    asc_1BD99E// "'"
0x43a32  call     string [mscorlib]System.String::Concat(string, string, string)
0x43a37  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x43a3c  starg.s  0
0x43a3e  ldarg.0
0x43a3f  ldstr    aTempdb// "[tempdb]"
0x43a44  ldstr    asc_1B2EBC// "["
0x43a49  ldsfld   string System.Web.Management.SqlServices::ASPSTATE_DB
0x43a4e  ldstr    asc_1B633C// "]"
0x43a53  call     string [mscorlib]System.String::Concat(string, string, string)
0x43a58  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x43a5d  starg.s  0
0x43a5f  br       loc_43B2F
0x43a64  ldarg.s  4
0x43a66  ldc.i4.2
0x43a67  bne.un   loc_43B2F
0x43a6c  ldarg.0
0x43a6d  ldstr    aSstypeTemp// "'sstype_temp'"
0x43a72  ldstr    asc_1BD99E// "'"
0x43a77  ldsfld   string System.Web.Management.SqlServices::SSTYPE_CUSTOM
0x43a7c  ldstr    asc_1BD99E// "'"
0x43a81  call     string [mscorlib]System.String::Concat(string, string, string)
0x43a86  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x43a8b  starg.s  0
0x43a8d  ldarg.0
0x43a8e  ldstr    aTempdb// "[tempdb]"
0x43a93  ldstr    asc_1B2EBC// "["
0x43a98  ldarg.1
0x43a99  ldstr    asc_1B633C// "]"
0x43a9e  call     string [mscorlib]System.String::Concat(string, string, string)
0x43aa3  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x43aa8  starg.s  0
0x43aaa  ldarg.0
0x43aab  ldstr    aAspstate// "'ASPState'"
0x43ab0  ldstr    asc_1BD99E// "'"
0x43ab5  ldarg.1
0x43ab6  ldstr    asc_1BD99E// "'"
0x43abb  call     string [mscorlib]System.String::Concat(string, string, string)
0x43ac0  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x43ac5  starg.s  0
0x43ac7  ldarg.0
0x43ac8  ldstr    aAspstate_0// "[ASPState]"
0x43acd  ldstr    asc_1B2EBC// "["
0x43ad2  ldarg.1
0x43ad3  ldstr    asc_1B633C// "]"
0x43ad8  call     string [mscorlib]System.String::Concat(string, string, string)
0x43add  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x43ae2  starg.s  0
0x43ae4  br.s     loc_43B2F
0x43ae6  ldarg.0
0x43ae7  ldstr    aAspnetdb// "'aspnetdb'"
0x43aec  ldstr    asc_1BD99E// "'"
0x43af1  ldarg.1
0x43af2  ldstr    asc_1BD99E// "'"
0x43af7  ldstr    asc_1BD9F6// "''"
0x43afc  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x43b01  ldstr    asc_1BD99E// "'"
0x43b06  call     string [mscorlib]System.String::Concat(string, string, string)
0x43b0b  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x43b10  starg.s  0
0x43b12  ldarg.0
0x43b13  ldstr    aAspnetdb_0// "[aspnetdb]"
0x43b18  ldstr    asc_1B2EBC// "["
0x43b1d  ldarg.1
0x43b1e  ldstr    asc_1B633C// "]"
0x43b23  call     string [mscorlib]System.String::Concat(string, string, string)
0x43b28  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x43b2d  starg.s  0
0x43b2f  ldarg.2
0x43b30  brfalse  loc_43C01
0x43b35  ldarg.2
0x43b36  ldstr    asc_1B2EBC// "["
0x43b3b  callvirt instance bool [mscorlib]System.String::Contains(string)
0x43b40  brtrue.s loc_43B5C
0x43b42  ldarg.2
0x43b43  ldstr    asc_1B633C// "]"
0x43b48  callvirt instance bool [mscorlib]System.String::Contains(string)
0x43b4d  brtrue.s loc_43B5C
0x43b4f  ldarg.2
0x43b50  ldstr    asc_1BD99E// "'"
0x43b55  callvirt instance bool [mscorlib]System.String::Contains(string)
0x43b5a  brfalse.s loc_43B6C
0x43b5c  ldstr    aDbfilenameCanN// "DbFileName_can_not_contain_invalid_char"...
0x43b61  call     string System.Web.SR::GetString(string name)
0x43b66  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x43b6b  throw
0x43b6c  ldarg.1
0x43b6d  ldc.i4.1
0x43b6e  newarr   [mscorlib]System.Char
0x43b73  dup
0x43b74  ldc.i4.0
0x43b75  ldc.i4.s 0x5B
0x43b77  stelem.i2
0x43b78  callvirt instance string [mscorlib]System.String::TrimStart(char[])
0x43b7d  starg.s  1
0x43b7f  ldarg.1
0x43b80  ldc.i4.1
0x43b81  newarr   [mscorlib]System.Char
0x43b86  dup
0x43b87  ldc.i4.0
0x43b88  ldc.i4.s 0x5D
0x43b8a  stelem.i2
0x43b8b  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x43b90  starg.s  1
0x43b92  ldarg.1
0x43b93  ldstr    aDat// "_DAT"
0x43b98  call     string [mscorlib]System.String::Concat(string, string)
0x43b9d  stloc.0
0x43b9e  ldloc.0
0x43b9f  ldc.i4.0
0x43ba0  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x43ba5  call     bool [mscorlib]System.Char::IsLetter(char)
0x43baa  brtrue.s loc_43BB8
0x43bac  ldstr    aA// "A"
0x43bb1  ldloc.0
0x43bb2  call     string [mscorlib]System.String::Concat(string, string)
0x43bb7  stloc.0
0x43bb8  ldc.i4.5
0x43bb9  newarr   [mscorlib]System.String
0x43bbe  dup
0x43bbf  ldc.i4.0
0x43bc0  ldstr    aOnName// "ON ( NAME = "
0x43bc5  stelem.ref
0x43bc6  dup
0x43bc7  ldc.i4.1
0x43bc8  ldloc.0
0x43bc9  stelem.ref
0x43bca  dup
0x43bcb  ldc.i4.2
0x43bcc  ldstr    aFilename_1// ", FILENAME = ''"
0x43bd1  stelem.ref
0x43bd2  dup
0x43bd3  ldc.i4.3
0x43bd4  ldarg.2
0x43bd5  stelem.ref
0x43bd6  dup
0x43bd7  ldc.i4.4
0x43bd8  ldstr    aSize10mbFilegr// "'', SIZE = 10MB, FILEGROWTH = 5MB )"
0x43bdd  stelem.ref
0x43bde  call     string [mscorlib]System.String::Concat(string[])
0x43be3  stloc.1
0x43be4  ldarg.0
0x43be5  ldstr    aSetDboptionsN// "SET @dboptions = N'/**/'"
0x43bea  ldstr    aSetDboptionsN_0// "SET @dboptions = N'"
0x43bef  ldloc.1
0x43bf0  ldstr    asc_1BD99E// "'"
0x43bf5  call     string [mscorlib]System.String::Concat(string, string, string)
0x43bfa  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x43bff  starg.s  0
0x43c01  ldarg.0
0x43c02  ret
```
