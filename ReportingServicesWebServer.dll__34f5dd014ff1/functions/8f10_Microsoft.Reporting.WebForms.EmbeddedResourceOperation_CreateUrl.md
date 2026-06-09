# Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl

- ea: `0x8f10`
- end: `0x8f21`
- name: `Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl`
- size: `17`
- prototype: ``
- caller_count: `26`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6030`
- `0x6260`
- `0x6cd0`
- `0x8f30`
- `0xe330`
- `0x14110`
- `0x14240`
- `0x14580`
- `0x197f0`
- `0x19c90`
- `0x1aa00`
- `0x1b100`
- `0x1b3d0`
- `0x1b450`
- `0x1bcf0`
- `0x2e310`
- `0x2e760`
- `0x2e8e0`
- `0x33c60`
- `0x37510`
- `0x37540`
- `0x37c80`
- `0x37cb0`
- `0x38070`
- `0x38350`
- `0x38380`

## callees

- `0x8f40`

## pseudocode

```c

```

## disassembly

```asm
0x8f10  ldarg.0
0x8f11  ldstr    aResource// "Resource"
0x8f16  call     T0x2B00000E
0x8f1b  call     string Microsoft.Reporting.WebForms.EmbeddedResourceOperation::CreateUrl(string resourceName, string operationType, string[] additionalParams)
0x8f20  ret
```
