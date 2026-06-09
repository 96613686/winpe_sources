# Microsoft.VisualStudio.Setup.Cache.PackageReference::Equals

- ea: `0x1bb40`
- end: `0x1bc03`
- name: `Microsoft.VisualStudio.Setup.Cache.PackageReference::Equals`
- size: `195`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1bc20`
- `0x1bf50`

## callees

- `0xa7a0`
- `0x1b560`
- `0x1b570`
- `0x1bb40`

## pseudocode

```c

```

## disassembly

```asm
0x1bb40  ldsfld   class Microsoft.VisualStudio.Setup.PackageIdentityComparer Microsoft.VisualStudio.Setup.PackageIdentityComparer::Default
0x1bb45  ldarg.0
0x1bb46  ldarg.1
0x1bb47  callvirt instance bool Microsoft.VisualStudio.Setup.PackageIdentityComparer::Equals(class Microsoft.VisualStudio.Setup.IPackageIdentity x, class Microsoft.VisualStudio.Setup.IPackageIdentity y)
0x1bb4c  brfalse  loc_1BC01
0x1bb51  ldarg.0
0x1bb52  brtrue.s loc_1BB5F
0x1bb54  ldloca.s 2
0x1bb56  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.PackageType>
0x1bb5c  ldloc.2
0x1bb5d  br.s     loc_1BB6A
0x1bb5f  ldarg.0
0x1bb60  callvirt instance valuetype Microsoft.VisualStudio.Setup.PackageType Microsoft.VisualStudio.Setup.Cache.IPackageReference::get_Type()
0x1bb65  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.PackageType>::.ctor(var<u1>)
0x1bb6a  stloc.0
0x1bb6b  ldarg.1
0x1bb6c  brtrue.s loc_1BB79
0x1bb6e  ldloca.s 2
0x1bb70  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.PackageType>
0x1bb76  ldloc.2
0x1bb77  br.s     loc_1BB84
0x1bb79  ldarg.1
0x1bb7a  callvirt instance valuetype Microsoft.VisualStudio.Setup.PackageType Microsoft.VisualStudio.Setup.Cache.IPackageReference::get_Type()
0x1bb7f  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.PackageType>::.ctor(var<u1>)
0x1bb84  stloc.1
0x1bb85  ldloca.s 0
0x1bb87  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.PackageType>::GetValueOrDefault()
0x1bb8c  ldloca.s 1
0x1bb8e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.PackageType>::GetValueOrDefault()
0x1bb93  ceq
0x1bb95  ldloca.s 0
0x1bb97  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.PackageType>::get_HasValue()
0x1bb9c  ldloca.s 1
0x1bb9e  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.VisualStudio.Setup.PackageType>::get_HasValue()
0x1bba3  ceq
0x1bba5  and
0x1bba6  brfalse.s loc_1BC01
0x1bba8  ldarg.0
0x1bba9  brtrue.s loc_1BBB7
0x1bbab  ldloca.s 5
0x1bbad  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x1bbb3  ldloc.s  5
0x1bbb5  br.s     loc_1BBC2
0x1bbb7  ldarg.0
0x1bbb8  callvirt instance bool Microsoft.VisualStudio.Setup.Cache.IPackageReference::get_IsExtension()
0x1bbbd  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1bbc2  stloc.3
0x1bbc3  ldarg.1
0x1bbc4  brtrue.s loc_1BBD2
0x1bbc6  ldloca.s 5
0x1bbc8  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x1bbce  ldloc.s  5
0x1bbd0  br.s     loc_1BBDD
0x1bbd2  ldarg.1
0x1bbd3  callvirt instance bool Microsoft.VisualStudio.Setup.Cache.IPackageReference::get_IsExtension()
0x1bbd8  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x1bbdd  stloc.s  4
0x1bbdf  ldloca.s 3
0x1bbe1  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1bbe6  ldloca.s 4
0x1bbe8  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x1bbed  ceq
0x1bbef  ldloca.s 3
0x1bbf1  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1bbf6  ldloca.s 4
0x1bbf8  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1bbfd  ceq
0x1bbff  and
0x1bc00  ret
0x1bc01  ldc.i4.0
0x1bc02  ret
```
