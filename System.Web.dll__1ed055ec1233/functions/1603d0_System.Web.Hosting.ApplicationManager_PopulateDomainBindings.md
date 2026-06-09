# System.Web.Hosting.ApplicationManager::PopulateDomainBindings

- ea: `0x1603d0`
- end: `0x160458`
- name: `System.Web.Hosting.ApplicationManager::PopulateDomainBindings`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x15f4b0`

## callees

- `0x30f70`

## string_xrefs

- `0x16042c`: `.appPath`
- `0x160439`: `.appVPath`
- `0x1603fa`: `web.config`

## pseudocode

```c

```

## disassembly

```asm
0x1603d0  ldarg.s  5
0x1603d2  ldstr    asc_1B483C// "*"
0x1603d7  callvirt instance void [mscorlib]System.AppDomainSetup::set_PrivateBinPathProbe(string)
0x1603dc  ldarg.s  5
0x1603de  ldstr    aTrue// "true"
0x1603e3  callvirt instance void [mscorlib]System.AppDomainSetup::set_ShadowCopyFiles(string)
0x1603e8  ldarg.s  5
0x1603ea  ldarg.3
0x1603eb  callvirt instance void [mscorlib]System.AppDomainSetup::set_ApplicationBase(string)
0x1603f0  ldarg.s  5
0x1603f2  ldarg.2
0x1603f3  callvirt instance void [mscorlib]System.AppDomainSetup::set_ApplicationName(string)
0x1603f8  ldarg.s  5
0x1603fa  ldstr    aWebConfig// "web.config"
0x1603ff  callvirt instance void [mscorlib]System.AppDomainSetup::set_ConfigurationFile(string)
0x160404  ldarg.s  5
0x160406  ldc.i4.1
0x160407  callvirt instance void [mscorlib]System.AppDomainSetup::set_DisallowCodeDownload(bool)
0x16040c  ldarg.s  6
0x16040e  ldstr    aAppdomain// ".appDomain"
0x160413  ldstr    asc_1B483C// "*"
0x160418  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x16041d  ldarg.s  6
0x16041f  ldstr    aAppid// ".appId"
0x160424  ldarg.1
0x160425  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x16042a  ldarg.s  6
0x16042c  ldstr    aApppath// ".appPath"
0x160431  ldarg.3
0x160432  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x160437  ldarg.s  6
0x160439  ldstr    aAppvpath// ".appVPath"
0x16043e  ldarg.s  4
0x160440  callvirt instance string System.Web.VirtualPath::get_VirtualPathString()
0x160445  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x16044a  ldarg.s  6
0x16044c  ldstr    aDomainid// ".domainId"
0x160451  ldarg.0
0x160452  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x160457  ret
```
