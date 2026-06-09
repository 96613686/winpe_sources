# Microsoft.VisualStudio.Setup.Services.Extensions::OpenKeys

- ea: `0x11350`
- end: `0x11395`
- name: `Microsoft.VisualStudio.Setup.Services.Extensions::OpenKeys`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0xc1a0`
- `0xc1d0`
- `0x112f0`
- `0x11350`

## string_xrefs

- `0x11351`: `registry`
- `0x1135c`: `registryKey`

## pseudocode

```c

```

## disassembly

```asm
0x11350  ldarg.0
0x11351  ldstr    aRegistry// "registry"
0x11356  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x1135b  ldarg.1
0x1135c  ldstr    aRegistrykey_0// "registryKey"
0x11361  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string s, string paramName)
0x11366  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Services.IRegistryKey>::.ctor()
0x1136b  stloc.0
0x1136c  ldsfld   valuetype Microsoft.VisualStudio.Setup.Services.RegistryView[] Microsoft.VisualStudio.Setup.Services.Extensions::RegistryViews
0x11371  stloc.1
0x11372  ldc.i4.0
0x11373  stloc.2
0x11374  br.s     loc_1138D
0x11376  ldloc.1
0x11377  ldloc.2
0x11378  ldelem.i4
0x11379  stloc.3
0x1137a  ldloc.0
0x1137b  ldarg.0
0x1137c  ldarg.1
0x1137d  ldloc.3
0x1137e  ldarg.2
0x1137f  call     class Microsoft.VisualStudio.Setup.Services.IRegistryKey Microsoft.VisualStudio.Setup.Services.Extensions::OpenKey(class Microsoft.VisualStudio.Setup.Services.IRegistry registry, string registryKey, valuetype Microsoft.VisualStudio.Setup.Services.RegistryView view, [opt] bool writable)
0x11384  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Services.IRegistryKey>::Add(var<u1>)
0x11389  ldloc.2
0x1138a  ldc.i4.1
0x1138b  add
0x1138c  stloc.2
0x1138d  ldloc.2
0x1138e  ldloc.1
0x1138f  ldlen
0x11390  conv.i4
0x11391  blt.s    loc_11376
0x11393  ldloc.0
0x11394  ret
```
