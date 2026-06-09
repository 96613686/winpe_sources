# Microsoft.VisualStudio.Setup.Extensions::GetRootPackages

- ea: `0x5ef0`
- end: `0x5f3b`
- name: `Microsoft.VisualStudio.Setup.Extensions::GetRootPackages`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x5ef0`
- `0xc1a0`

## string_xrefs

- `0x5ef1`: `manifest`

## pseudocode

```c

```

## disassembly

```asm
0x5ef0  ldarg.0
0x5ef1  ldstr    aManifest// "manifest"
0x5ef6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x5efb  ldarg.0
0x5efc  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<var<u1>> class Microsoft.VisualStudio.Setup.IManifest`1<mvar<u1>>::get_Items()
0x5f01  dup
0x5f02  brtrue.s loc_5F08
0x5f04  pop
0x5f05  ldnull
0x5f06  br.s     loc_5F31
0x5f08  call     T0x2B000026
0x5f0d  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.IRootPackage, bool> class <>c__44`1<mvar<u1>>::<>9__44_0
0x5f12  dup
0x5f13  brtrue.s loc_5F2C
0x5f15  pop
0x5f16  ldsfld   class <>c__44`1<var<u1>> class <>c__44`1<mvar<u1>>::<>9
0x5f1b  ldftn    instance bool class <>c__44`1<mvar<u1>>::<GetRootPackages>b__44_0(class Microsoft.VisualStudio.Setup.IRootPackage)
0x5f21  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.IRootPackage, bool>::.ctor(object, native int)
0x5f26  dup
0x5f27  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.IRootPackage, bool> class <>c__44`1<mvar<u1>>::<>9__44_0
0x5f2c  call     T0x2B000027
0x5f31  dup
0x5f32  brtrue.s loc_5F3A
0x5f34  pop
0x5f35  call     T0x2B000028
0x5f3a  ret
```
