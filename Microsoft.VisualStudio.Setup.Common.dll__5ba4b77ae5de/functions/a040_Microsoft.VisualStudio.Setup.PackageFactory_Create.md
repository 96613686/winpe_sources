# Microsoft.VisualStudio.Setup.PackageFactory::Create

- ea: `0xa040`
- end: `0xa0be`
- name: `Microsoft.VisualStudio.Setup.PackageFactory::Create`
- size: `126`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callees

- `0x3e20`
- `0x4d80`
- `0x6a60`
- `0x8fb0`
- `0x9000`
- `0x9400`
- `0xa040`
- `0xb1b0`
- `0xccf0`
- `0xcd80`
- `0xcdf0`
- `0xce60`

## pseudocode

```c

```

## disassembly

```asm
0xa040  ldarg.1
0xa041  ldc.i4.1
0xa042  sub
0xa043  switch   loc_A08E, loc_A094, loc_A09A, loc_A0A0, loc_A0A6, loc_A076, loc_A07C, loc_A082, loc_A088, loc_A0AC, loc_A0B2
0xa074  br.s     loc_A0B8
0xa076  newobj   instance void Microsoft.VisualStudio.Setup.Product::.ctor()
0xa07b  ret
0xa07c  newobj   instance void Microsoft.VisualStudio.Setup.Workload::.ctor()
0xa081  ret
0xa082  newobj   instance void Microsoft.VisualStudio.Setup.Component::.ctor()
0xa087  ret
0xa088  newobj   instance void Microsoft.VisualStudio.Setup.Group::.ctor()
0xa08d  ret
0xa08e  newobj   instance void Microsoft.VisualStudio.Setup.VsixPackage::.ctor()
0xa093  ret
0xa094  newobj   instance void Microsoft.VisualStudio.Setup.MsiPackage::.ctor()
0xa099  ret
0xa09a  newobj   instance void Microsoft.VisualStudio.Setup.MsuPackage::.ctor()
0xa09f  ret
0xa0a0  newobj   instance void Microsoft.VisualStudio.Setup.ExePackage::.ctor()
0xa0a5  ret
0xa0a6  newobj   instance void Microsoft.VisualStudio.Setup.WindowsFeature::.ctor()
0xa0ab  ret
0xa0ac  newobj   instance void Microsoft.VisualStudio.Setup.ZipPackage::.ctor()
0xa0b1  ret
0xa0b2  newobj   instance void Microsoft.VisualStudio.Setup.NuGetPackage::.ctor()
0xa0b7  ret
0xa0b8  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0xa0bd  throw
```
