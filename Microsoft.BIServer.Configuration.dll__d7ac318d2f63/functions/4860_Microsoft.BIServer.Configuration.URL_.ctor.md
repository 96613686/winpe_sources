# Microsoft.BIServer.Configuration.URL::.ctor

- ea: `0x4860`
- end: `0x489e`
- name: `Microsoft.BIServer.Configuration.URL::.ctor`
- size: `62`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x48b0`
- `0x48c0`
- `0x48f0`

## callees

- `0x4860`
- `0x4910`
- `0x4930`
- `0x4950`
- `0x4970`
- `0x4990`
- `0x49a0`
- `0x7860`

## pseudocode

```c

```

## disassembly

```asm
0x4860  ldarg.0
0x4861  call     instance void [mscorlib]System.Object::.ctor()
0x4866  ldarg.1
0x4867  brtrue.s loc_4874
0x4869  ldstr    aUrlstringIsNul// "UrlString is null."
0x486e  newobj   instance void InvalidUrlReservation::.ctor(string message)
0x4873  throw
0x4874  ldarg.0
0x4875  ldarg.1
0x4876  call     class [System]System.Uri Microsoft.BIServer.Configuration.URL::GetEffectiveUrl(string urlString)
0x487b  call     instance void Microsoft.BIServer.Configuration.URL::set_EffectiveUrl(class [System]System.Uri value)
0x4880  ldarg.0
0x4881  ldarg.1
0x4882  call     instance void Microsoft.BIServer.Configuration.URL::set_UrlString(string value)
0x4887  ldarg.0
0x4888  ldarg.2
0x4889  call     instance void Microsoft.BIServer.Configuration.URL::set_AccountName(string value)
0x488e  ldarg.0
0x488f  ldarg.3
0x4890  call     instance void Microsoft.BIServer.Configuration.URL::set_AccountSid(string value)
0x4895  ldarg.0
0x4896  ldarg.s  4
0x4898  call     instance void Microsoft.BIServer.Configuration.URL::set_AccountSecurityDescriptor(string value)
0x489d  ret
```
