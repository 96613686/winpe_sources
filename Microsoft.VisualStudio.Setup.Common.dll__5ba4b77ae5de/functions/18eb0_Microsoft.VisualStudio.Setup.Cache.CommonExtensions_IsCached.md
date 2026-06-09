# Microsoft.VisualStudio.Setup.Cache.CommonExtensions::IsCached

- ea: `0x18eb0`
- end: `0x18f35`
- name: `Microsoft.VisualStudio.Setup.Cache.CommonExtensions::IsCached`
- size: `133`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x6bf0`
- `0x6c00`
- `0xc1a0`
- `0x18eb0`
- `0x19780`

## pseudocode

```c

```

## disassembly

```asm
0x18eb0  ldarg.0
0x18eb1  ldstr    aManager// "manager"
0x18eb6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x18ebb  ldarg.1
0x18ebc  ldstr    aIdentity// "identity"
0x18ec1  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x18ec6  ldarg.1
0x18ec7  isinst   Microsoft.VisualStudio.Setup.IInstallablePackage
0x18ecc  stloc.1
0x18ecd  ldloc.1
0x18ece  brfalse.s loc_18EF1
0x18ed0  ldloc.1
0x18ed1  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Cache.CacheState> Microsoft.VisualStudio.Setup.IInstallablePackage::get_CacheState()
0x18ed6  stloc.2
0x18ed7  ldloca.s 2
0x18ed9  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Cache.CacheState>::get_HasValue()
0x18ede  brfalse.s loc_18EF1
0x18ee0  ldloc.1
0x18ee1  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Cache.CacheState> Microsoft.VisualStudio.Setup.IInstallablePackage::get_CacheState()
0x18ee6  stloc.2
0x18ee7  ldloca.s 2
0x18ee9  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Cache.CacheState>::get_Value()
0x18eee  stloc.0
0x18eef  br.s     loc_18F09
0x18ef1  ldarg.0
0x18ef2  ldarg.1
0x18ef3  ldarg.3
0x18ef4  callvirt instance valuetype Microsoft.VisualStudio.Setup.Cache.CacheState Microsoft.VisualStudio.Setup.Cache.ICacheManager::GetCacheState(class Microsoft.VisualStudio.Setup.IPackageIdentity identity, [opt] bool layout)
0x18ef9  stloc.0
0x18efa  ldloc.1
0x18efb  brfalse.s loc_18F09
0x18efd  ldloc.1
0x18efe  ldloc.0
0x18eff  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Cache.CacheState>::.ctor(var<u1>)
0x18f04  callvirt instance void Microsoft.VisualStudio.Setup.IInstallablePackage::set_CacheState(valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.Cache.CacheState> value)
0x18f09  ldarg.3
0x18f0a  brfalse.s loc_18F1C
0x18f0c  ldarg.0
0x18f0d  ldarg.1
0x18f0e  ldarg.3
0x18f0f  callvirt instance valuetype Microsoft.VisualStudio.Setup.Cache.CacheState Microsoft.VisualStudio.Setup.Cache.ICacheManager::GetCacheState(class Microsoft.VisualStudio.Setup.IPackageIdentity identity, [opt] bool layout)
0x18f14  stloc.0
0x18f15  ldloc.0
0x18f16  ldc.i4.2
0x18f17  and
0x18f18  ldc.i4.2
0x18f19  ceq
0x18f1b  ret
0x18f1c  ldarg.2
0x18f1d  brfalse.s loc_18F2E
0x18f1f  ldarg.1
0x18f20  isinst   Microsoft.VisualStudio.Setup.IInstallablePackage
0x18f25  brfalse.s loc_18F2E
0x18f27  ldloc.0
0x18f28  ldc.i4.3
0x18f29  and
0x18f2a  ldc.i4.3
0x18f2b  ceq
0x18f2d  ret
0x18f2e  ldloc.0
0x18f2f  ldc.i4.1
0x18f30  and
0x18f31  ldc.i4.1
0x18f32  ceq
0x18f34  ret
```
