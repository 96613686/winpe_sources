# Microsoft.BIServer.HostingEnvironment.ImpersonationContext::Finalize

- ea: `0xb90`
- end: `0xbb1`
- name: `Microsoft.BIServer.HostingEnvironment.ImpersonationContext::Finalize`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0xb90`
- `0x15d0`

## string_xrefs

- `0xb98`: `Impersonation Context Not Disposed - (use all instances of Impersonation context in a using() block)`

## pseudocode

```c

```

## disassembly

```asm
0xb90  ldarg.0
0xb91  ldfld    bool Microsoft.BIServer.HostingEnvironment.ImpersonationContext::_disposed
0xb96  brtrue.s loc_BA7
0xb98  ldstr    aImpersonationC// "Impersonation Context Not Disposed - (u"...
0xb9d  call     T0x2B00000A
0xba2  call     void Microsoft.BIServer.HostingEnvironment.Logger::Error(string formatString, object[] formatParams)
0xba7  leave.s  loc_BB0
0xba9  ldarg.0
0xbaa  call     instance void [mscorlib]System.Object::Finalize()
0xbaf  endfinally
0xbb0  ret
```
