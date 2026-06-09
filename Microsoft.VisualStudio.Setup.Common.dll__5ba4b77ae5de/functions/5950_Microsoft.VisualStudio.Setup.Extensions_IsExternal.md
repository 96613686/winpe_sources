# Microsoft.VisualStudio.Setup.Extensions::IsExternal

- ea: `0x5950`
- end: `0x599e`
- name: `Microsoft.VisualStudio.Setup.Extensions::IsExternal`
- size: `78`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x142e0`
- `0x16c00`
- `0x16e40`
- `0x17660`
- `0x17970`

## callees

- `0x5950`
- `0x80d0`
- `0x98f0`
- `0xc1a0`

## pseudocode

```c

```

## disassembly

```asm
0x5950  ldarg.0
0x5951  ldstr    aPackage// "package"
0x5956  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x595b  ldarg.0
0x595c  callvirt instance class Microsoft.VisualStudio.Setup.OriginInfo Microsoft.VisualStudio.Setup.IPackage::get_Origin()
0x5961  dup
0x5962  brtrue.s loc_5970
0x5964  pop
0x5965  ldloca.s 1
0x5967  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.PartialManifestType>
0x596d  ldloc.1
0x596e  br.s     loc_597A
0x5970  call     instance valuetype Microsoft.VisualStudio.Setup.PartialManifestType Microsoft.VisualStudio.Setup.OriginInfo::get_ManifestType()
0x5975  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.PartialManifestType>::.ctor(var<u1>)
0x597a  stloc.0
0x597b  ldloca.s 0
0x597d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.PartialManifestType>::GetValueOrDefault()
0x5982  ldc.i4.1
0x5983  beq.s    loc_599C
0x5985  ldloc.0
0x5986  stloc.1
0x5987  ldc.i4.0
0x5988  stloc.2
0x5989  ldloca.s 1
0x598b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.PartialManifestType>::GetValueOrDefault()
0x5990  ldloc.2
0x5991  ceq
0x5993  ldloca.s 1
0x5995  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.PartialManifestType>::get_HasValue()
0x599a  and
0x599b  ret
0x599c  ldc.i4.1
0x599d  ret
```
