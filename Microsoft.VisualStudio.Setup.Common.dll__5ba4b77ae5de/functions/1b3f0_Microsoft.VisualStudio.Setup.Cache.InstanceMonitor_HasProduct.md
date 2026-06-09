# Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::HasProduct

- ea: `0x1b3f0`
- end: `0x1b45d`
- name: `Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::HasProduct`
- size: `109`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1b2c0`
- `0x1b3a0`

## callees

- `0x26a0`
- `0x1a950`
- `0x1a980`
- `0x1b3f0`

## pseudocode

```c

```

## disassembly

```asm
0x1b3f0  ldarg.0
0x1b3f1  ldfld    class Microsoft.VisualStudio.Setup.Cache.Instance Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::instance
0x1b3f6  callvirt instance class Microsoft.VisualStudio.Setup.Cache.ProductReference Microsoft.VisualStudio.Setup.Cache.Instance::get_Product()
0x1b3fb  stloc.0
0x1b3fc  ldloc.0
0x1b3fd  brfalse.s loc_1B41E
0x1b3ff  ldloc.0
0x1b400  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.VisualStudio.Setup.IProductReference::get_IsInstalled()
0x1b405  stloc.1
0x1b406  ldloca.s 1
0x1b408  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1b40d  brfalse.s loc_1B41E
0x1b40f  ldloc.0
0x1b410  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> Microsoft.VisualStudio.Setup.IProductReference::get_IsInstalled()
0x1b415  stloc.1
0x1b416  ldloca.s 1
0x1b418  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1b41d  ret
0x1b41e  ldarg.0
0x1b41f  ldfld    class Microsoft.VisualStudio.Setup.Cache.Instance Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::instance
0x1b424  callvirt instance class Microsoft.VisualStudio.Setup.Cache.ProductReference Microsoft.VisualStudio.Setup.Cache.Instance::get_Product()
0x1b429  brtrue.s loc_1B45B
0x1b42b  ldarg.0
0x1b42c  ldfld    class Microsoft.VisualStudio.Setup.Cache.Instance Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::instance
0x1b431  callvirt instance class Microsoft.VisualStudio.Setup.Cache.PackageReferenceCollection Microsoft.VisualStudio.Setup.Cache.Instance::get_Packages()
0x1b436  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Cache.PackageReference, bool> <>c::<>9__9_0
0x1b43b  dup
0x1b43c  brtrue.s loc_1B455
0x1b43e  pop
0x1b43f  ldsfld   class <>c <>c::<>9
0x1b444  ldftn    instance bool <>c::<HasProduct>b__9_0(class Microsoft.VisualStudio.Setup.Cache.PackageReference p)
0x1b44a  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Cache.PackageReference, bool>::.ctor(object, native int)
0x1b44f  dup
0x1b450  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Cache.PackageReference, bool> <>c::<>9__9_0
0x1b455  call     T0x2B0000D2
0x1b45a  ret
0x1b45b  ldc.i4.1
0x1b45c  ret
```
