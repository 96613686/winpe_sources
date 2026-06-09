# Microsoft.Internal.GDIExporter.CGDIRenderTarget::CreateUnstyledFont

- ea: `0x20a80`
- end: `0x20ab6`
- name: `Microsoft.Internal.GDIExporter.CGDIRenderTarget::CreateUnstyledFont`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x208c0`

## callees

- `0x207b0`

## pseudocode

```c

```

## disassembly

```asm
0x20a80  ldloca.s 0
0x20a82  ldarg.1
0x20a83  ldc.i4   0x1A4
0x20a88  unaligned. 4
0x20a8b  cpblk
0x20a8d  ldloca.s 0
0x20a8f  ldc.i4.s 0x10
0x20a91  add
0x20a92  ldc.i4   0x190
0x20a97  stind.i4
0x20a98  ldloca.s 0
0x20a9a  ldc.i4.s 0x14
0x20a9c  add
0x20a9d  ldc.i4.0
0x20a9e  stind.i1
0x20a9f  ldloca.s 0
0x20aa1  ldc.i4.s 0x15
0x20aa3  add
0x20aa4  ldc.i4.0
0x20aa5  stind.i1
0x20aa6  ldloca.s 0
0x20aa8  ldc.i4.s 0x16
0x20aaa  add
0x20aab  ldc.i4.0
0x20aac  stind.i1
0x20aad  ldarg.0
0x20aae  ldloca.s 0
0x20ab0  call     instance class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CGDIRenderTarget::CreateFontCached(modopt([mscorlib]System.Runtime.CompilerServices.IsExplicitlyDereferenced) valuetype tagENUMLOGFONTEXDVW& logfontdv)
0x20ab5  ret
```
