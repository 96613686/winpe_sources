# Microsoft.VisualStudio.Setup.Extensions::.cctor

- ea: `0x66d0`
- end: `0x6736`
- name: `Microsoft.VisualStudio.Setup.Extensions::.cctor`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## string_xrefs

- `0x66df`: `manifest.json`

## pseudocode

```c

```

## disassembly

```asm
0x66d0  ldstr    aEnUs// "en-US"
0x66d5  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(string)
0x66da  stsfld   class [mscorlib]System.Globalization.CultureInfo Microsoft.VisualStudio.Setup.Extensions::NeutralCulture
0x66df  ldstr    aManifestJson// "manifest.json"
0x66e4  stsfld   string Microsoft.VisualStudio.Setup.Extensions::VsixManifestName
0x66e9  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype Microsoft.VisualStudio.Setup.PackageType>::.ctor()
0x66ee  dup
0x66ef  ldc.i4.1
0x66f0  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype Microsoft.VisualStudio.Setup.PackageType>::Add(var<u1>)
0x66f5  pop
0x66f6  dup
0x66f7  ldc.i4.8
0x66f8  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype Microsoft.VisualStudio.Setup.PackageType>::Add(var<u1>)
0x66fd  pop
0x66fe  dup
0x66ff  ldc.i4.s 9
0x6701  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype Microsoft.VisualStudio.Setup.PackageType>::Add(var<u1>)
0x6706  pop
0x6707  dup
0x6708  ldc.i4.7
0x6709  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype Microsoft.VisualStudio.Setup.PackageType>::Add(var<u1>)
0x670e  pop
0x670f  dup
0x6710  ldc.i4.6
0x6711  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype Microsoft.VisualStudio.Setup.PackageType>::Add(var<u1>)
0x6716  pop
0x6717  dup
0x6718  ldc.i4.2
0x6719  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype Microsoft.VisualStudio.Setup.PackageType>::Add(var<u1>)
0x671e  pop
0x671f  dup
0x6720  ldc.i4.4
0x6721  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype Microsoft.VisualStudio.Setup.PackageType>::Add(var<u1>)
0x6726  pop
0x6727  dup
0x6728  ldc.i4.s 0xA
0x672a  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype Microsoft.VisualStudio.Setup.PackageType>::Add(var<u1>)
0x672f  pop
0x6730  stsfld   class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype Microsoft.VisualStudio.Setup.PackageType> Microsoft.VisualStudio.Setup.Extensions::InstanceDowngradablePackageTypes
0x6735  ret
```
