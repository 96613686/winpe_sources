# Microsoft.BIServer.Configuration.URL::GetEffectiveUrl

- ea: `0x49a0`
- end: `0x49c3`
- name: `Microsoft.BIServer.Configuration.URL::GetEffectiveUrl`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4860`

## callees

- `0x49a0`
- `0x49d0`
- `0x7860`

## pseudocode

```c

```

## disassembly

```asm
0x49a0  ldarg.0
0x49a1  call     string Microsoft.BIServer.Configuration.URL::ReplaceWildcard(string urlString)
0x49a6  ldc.i4.1
0x49a7  ldloca.s 0
0x49a9  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0x49ae  brtrue.s loc_49C1
0x49b0  ldstr    aTheFormatOfUrl// "The format of UrlString is invalid: {0}"
0x49b5  ldarg.0
0x49b6  call     string [mscorlib]System.String::Format(string, object)
0x49bb  newobj   instance void InvalidUrlReservation::.ctor(string message)
0x49c0  throw
0x49c1  ldloc.0
0x49c2  ret
```
