# Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::AddMemberToDynamicPath

- ea: `0x6450`
- end: `0x6485`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.MemberState::AddMemberToDynamicPath`
- size: `53`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x62f0`
- `0x64e0`
- `0x6920`
- `0x6b50`

## callees

- `0x6450`

## pseudocode

```c

```

## disassembly

```asm
0x6450  ldarg.1
0x6451  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6456  brtrue.s loc_6483
0x6458  ldarg.0
0x6459  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x645e  brfalse.s loc_646D
0x6460  ldarg.0
0x6461  ldstr    aX_0// "x"
0x6466  call     string [mscorlib]System.String::Concat(string, string)
0x646b  starg.s  0
0x646d  ldarg.0
0x646e  ldarg.1
0x646f  call     string [mscorlib]System.String::Concat(string, string)
0x6474  starg.s  0
0x6476  ldarg.0
0x6477  ldstr    aX_0// "x"
0x647c  call     string [mscorlib]System.String::Concat(string, string)
0x6481  starg.s  0
0x6483  ldarg.0
0x6484  ret
```
