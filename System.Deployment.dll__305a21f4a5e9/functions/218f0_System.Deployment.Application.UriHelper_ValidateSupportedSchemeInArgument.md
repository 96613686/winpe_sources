# System.Deployment.Application.UriHelper::ValidateSupportedSchemeInArgument

- ea: `0x218f0`
- end: `0x2190a`
- name: `System.Deployment.Application.UriHelper::ValidateSupportedSchemeInArgument`
- size: `26`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xa8c0`
- `0x10a30`
- `0x159b0`

## callees

- `0x218f0`
- `0x21910`
- `0x23020`

## string_xrefs

- `0x218f8`: `Ex_NotSupportedUriScheme`

## pseudocode

```c

```

## disassembly

```asm
0x218f0  ldarg.0
0x218f1  call     bool System.Deployment.Application.UriHelper::IsSupportedScheme(class [System]System.Uri uri)
0x218f6  brtrue.s loc_21909
0x218f8  ldstr    aExNotsupported// "Ex_NotSupportedUriScheme"
0x218fd  call     string System.Deployment.Application.Resources::GetString(string s)
0x21902  ldarg.1
0x21903  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x21908  throw
0x21909  ret
```
