# System.Net.Http.HttpContentMultipartExtensions::CheckIsFinalPart

- ea: `0x1e90`
- end: `0x1eb8`
- name: `System.Net.Http.HttpContentMultipartExtensions::CheckIsFinalPart`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0xcb10`

## callees

- `0x1e90`
- `0x2830`
- `0x2880`
- `0x28a0`
- `0x29f0`

## pseudocode

```c

```

## disassembly

```asm
0x1e90  ldarg.0
0x1e91  callvirt instance bool System.Net.Http.MimeBodyPart::get_IsComplete()
0x1e96  brfalse.s loc_1EB6
0x1e98  ldarg.0
0x1e99  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent System.Net.Http.MimeBodyPart::GetCompletedHttpContent()
0x1e9e  stloc.0
0x1e9f  ldloc.0
0x1ea0  brfalse.s loc_1EA9
0x1ea2  ldarg.1
0x1ea3  ldloc.0
0x1ea4  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [System.Net.Http]System.Net.Http.HttpContent>::Add(var<u1>)
0x1ea9  ldarg.0
0x1eaa  callvirt instance bool System.Net.Http.MimeBodyPart::get_IsFinal()
0x1eaf  ldarg.0
0x1eb0  callvirt instance void System.Net.Http.MimeBodyPart::Dispose()
0x1eb5  ret
0x1eb6  ldc.i4.0
0x1eb7  ret
```
