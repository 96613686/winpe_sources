# System.Windows.Xps.Packaging.XpsOMPackagingPolicy::GenerateIOpcPartUri_0

- ea: `0x1fa50`
- end: `0x1fa75`
- name: `System.Windows.Xps.Packaging.XpsOMPackagingPolicy::GenerateIOpcPartUri_0`
- size: `37`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1f1a0`
- `0x1f570`
- `0x1f6b0`
- `0x1f720`
- `0x1f840`
- `0x1fa30`
- `0x1fac0`
- `0x1fb70`

## callees

- `0x1bc20`
- `0x1fa20`
- `0x1fa50`
- `0x3d5f0`

## pseudocode

```c

```

## disassembly

```asm
0x1fa50  ldarg.0
0x1fa51  ldfld    class System.Windows.Xps.Serialization.RCW.IXpsOMObjectFactory System.Windows.Xps.Packaging.XpsOMPackagingPolicy::_xpsOMFactory
0x1fa56  ldarg.1
0x1fa57  callvirt instance string [mscorlib]System.Object::ToString()
0x1fa5c  callvirt instance class System.Windows.Xps.Serialization.RCW.IOpcPartUri System.Windows.Xps.Serialization.RCW.IXpsOMObjectFactory::CreatePartUri([hasfieldmarshal] string)
0x1fa61  stloc.0
0x1fa62  ldloc.0
0x1fa63  stloc.1
0x1fa64  leave.s  loc_1FA73
0x1fa66  pop
0x1fa67  ldarg.0
0x1fa68  call     instance void System.Windows.Xps.Packaging.XpsOMPackagingPolicy::Invalidate()
0x1fa6d  newobj   instance void System.Printing.PrintingCanceledException::.ctor()
0x1fa72  throw
0x1fa73  ldloc.1
0x1fa74  ret
```
