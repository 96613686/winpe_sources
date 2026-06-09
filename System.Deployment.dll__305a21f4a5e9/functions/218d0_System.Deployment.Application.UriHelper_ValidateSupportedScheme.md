# System.Deployment.Application.UriHelper::ValidateSupportedScheme

- ea: `0x218d0`
- end: `0x218eb`
- name: `System.Deployment.Application.UriHelper::ValidateSupportedScheme`
- size: `27`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x15090`
- `0x1f1c0`
- `0x203a0`
- `0x21950`

## callees

- `0x147a0`
- `0x218d0`
- `0x21910`
- `0x23020`

## string_xrefs

- `0x218da`: `Ex_NotSupportedUriScheme`

## pseudocode

```c

```

## disassembly

```asm
0x218d0  ldarg.0
0x218d1  call     bool System.Deployment.Application.UriHelper::IsSupportedScheme(class [System]System.Uri uri)
0x218d6  brtrue.s loc_218EA
0x218d8  ldc.i4.s 0x14
0x218da  ldstr    aExNotsupported// "Ex_NotSupportedUriScheme"
0x218df  call     string System.Deployment.Application.Resources::GetString(string s)
0x218e4  newobj   instance void System.Deployment.Application.InvalidDeploymentException::.ctor(valuetype System.Deployment.Application.ExceptionTypes exceptionType, string message)
0x218e9  throw
0x218ea  ret
```
