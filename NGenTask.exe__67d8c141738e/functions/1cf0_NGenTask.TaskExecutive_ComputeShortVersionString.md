# NGenTask.TaskExecutive::ComputeShortVersionString

- ea: `0x1cf0`
- end: `0x1d2a`
- name: `NGenTask.TaskExecutive::ComputeShortVersionString`
- size: `58`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x220`
- `0x310`
- `0x2b10`

## callees

- `0x1cf0`

## pseudocode

```c

```

## disassembly

```asm
0x1cf0  ldstr    aAVersionmajorm// "\\A(?<versionMajorMinor>v\\d+\\.\\d+)\\"...
0x1cf5  ldc.i4   0x201
0x1cfa  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x1cff  stloc.0
0x1d00  ldloc.0
0x1d01  ldarg.0
0x1d02  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string)
0x1d07  stloc.1
0x1d08  ldloc.1
0x1d09  callvirt instance bool [System]System.Text.RegularExpressions.Group::get_Success()
0x1d0e  brfalse.s loc_1D28
0x1d10  ldloc.1
0x1d11  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x1d16  ldstr    aVersionmajormi// "versionMajorMinor"
0x1d1b  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x1d20  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x1d25  stloc.2
0x1d26  ldloc.2
0x1d27  ret
0x1d28  ldnull
0x1d29  ret
```
