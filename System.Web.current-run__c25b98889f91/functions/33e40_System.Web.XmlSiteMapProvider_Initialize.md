# System.Web.XmlSiteMapProvider::Initialize

- ea: `0x33e40`
- end: `0x33ec3`
- name: `System.Web.XmlSiteMapProvider::Initialize`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x2d3e0`
- `0x315f0`
- `0x33e40`
- `0x34fa0`
- `0x57720`
- `0x57a20`

## string_xrefs

- `0x33e48`: `XmlSiteMapProvider_Cannot_Be_Inited_Twice`
- `0x33e7e`: `XmlSiteMapProvider_Description`

## pseudocode

```c

```

## disassembly

```asm
0x33e40  ldarg.0
0x33e41  ldfld    bool System.Web.XmlSiteMapProvider::_initialized
0x33e46  brfalse.s loc_33E58
0x33e48  ldstr    aXmlsitemapprov_16// "XmlSiteMapProvider_Cannot_Be_Inited_Twi"...
0x33e4d  call     string System.Web.SR::GetString(string name)
0x33e52  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x33e57  throw
0x33e58  ldarg.2
0x33e59  brfalse.s loc_33EA9
0x33e5b  ldarg.2
0x33e5c  ldstr    aDescription// "description"
0x33e61  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x33e66  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x33e6b  brfalse.s loc_33E8D
0x33e6d  ldarg.2
0x33e6e  ldstr    aDescription// "description"
0x33e73  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Remove(string)
0x33e78  ldarg.2
0x33e79  ldstr    aDescription// "description"
0x33e7e  ldstr    aXmlsitemapprov_17// "XmlSiteMapProvider_Description"
0x33e83  call     string System.Web.SR::GetString(string name)
0x33e88  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x33e8d  ldnull
0x33e8e  stloc.0
0x33e8f  ldarg.2
0x33e90  ldstr    aSitemapfile// "siteMapFile"
0x33e95  ldarg.1
0x33e96  ldloca.s 0
0x33e98  call     void System.Web.Util.ProviderUtil::GetAndRemoveStringAttribute(class [System]System.Collections.Specialized.NameValueCollection config, string attrib, string providerName, string& val)
0x33e9d  ldarg.0
0x33e9e  ldloc.0
0x33e9f  call     class System.Web.VirtualPath System.Web.VirtualPath::CreateAllowNull(string virtualPath)
0x33ea4  stfld    class System.Web.VirtualPath System.Web.XmlSiteMapProvider::_virtualPath
0x33ea9  ldarg.0
0x33eaa  ldarg.1
0x33eab  ldarg.2
0x33eac  call     instance void System.Web.SiteMapProvider::Initialize(string name, class [System]System.Collections.Specialized.NameValueCollection attributes)
0x33eb1  ldarg.2
0x33eb2  brfalse.s loc_33EBB
0x33eb4  ldarg.2
0x33eb5  ldarg.1
0x33eb6  call     void System.Web.Util.ProviderUtil::CheckUnrecognizedAttributes(class [System]System.Collections.Specialized.NameValueCollection config, string providerName)
0x33ebb  ldarg.0
0x33ebc  ldc.i4.1
0x33ebd  stfld    bool System.Web.XmlSiteMapProvider::_initialized
0x33ec2  ret
```
