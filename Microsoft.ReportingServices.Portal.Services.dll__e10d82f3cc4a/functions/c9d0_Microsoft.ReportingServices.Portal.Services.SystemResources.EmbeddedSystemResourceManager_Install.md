# Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::Install

- ea: `0xc9d0`
- end: `0xcb1e`
- name: `Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::Install`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xcbb0`

## callees

- `0xc920`
- `0xc930`
- `0xc9a0`
- `0xc9d0`
- `0xcdd0`
- `0xcdf0`

## pseudocode

```c

```

## disassembly

```asm
0xc9d0  ldarg.1
0xc9d1  call     class [System.Xml.Linq]System.Xml.Linq.XDocument [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceManager::DeserializeMetadata(class [mscorlib]System.Func`1<class [mscorlib]System.IO.Stream>)
0xc9d6  ldloca.s 0
0xc9d8  ldloca.s 1
0xc9da  ldloca.s 2
0xc9dc  ldloca.s 3
0xc9de  call     void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceManager::ParseMetadata(class [System.Xml.Linq]System.Xml.Linq.XDocument, string&, string&, string&, class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceContentItem>&)
0xc9e3  newobj   instance void Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResource::.ctor()
0xc9e8  dup
0xc9e9  ldloc.2
0xc9ea  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource::set_Name(string)
0xc9ef  dup
0xc9f0  ldloc.1
0xc9f1  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource::set_Version(string)
0xc9f6  dup
0xc9f7  ldloc.0
0xc9f8  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResource::set_TypeName(string)
0xc9fd  dup
0xc9fe  ldarg.s  4
0xca00  callvirt instance void Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResource::set_PackageName(string value)
0xca05  stloc.s  4
0xca07  ldloc.3
0xca08  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceContentItem>>::GetEnumerator()
0xca0d  stloc.s  5
0xca0f  br       loc_CACC
0xca14  ldloc.s  5
0xca16  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceContentItem>>::get_Current()
0xca1b  stloc.s  6
0xca1d  ldloca.s 6
0xca1f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceContentItem>::get_Value()
0xca24  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceContentItem::get_ContentType()
0xca29  stloc.s  7
0xca2b  ldstr    a0123// "{0}.{1}.{2}.{3}"
0xca30  ldc.i4.4
0xca31  newarr   [mscorlib]System.Object
0xca36  dup
0xca37  ldc.i4.0
0xca38  ldsfld   string Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::ResourceRoot
0xca3d  stelem.ref
0xca3e  dup
0xca3f  ldc.i4.1
0xca40  ldloc.0
0xca41  stelem.ref
0xca42  dup
0xca43  ldc.i4.2
0xca44  ldstr    a1c648e99E3a246// "_1c648e99_e3a2_4639_90ee_71fff9f08ee3"
0xca49  stelem.ref
0xca4a  dup
0xca4b  ldc.i4.3
0xca4c  ldloca.s 6
0xca4e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceContentItem>::get_Value()
0xca53  callvirt instance string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceContentItem::get_Path()
0xca58  ldc.i4.s 0x5C
0xca5a  ldc.i4.s 0x2E
0xca5c  callvirt instance string [mscorlib]System.String::Replace(char, char)
0xca61  stelem.ref
0xca62  call     string [mscorlib]System.String::Format(string, object[])
0xca67  stloc.s  8
0xca69  ldloc.s  4
0xca6b  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceContentItem> Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResource::get_Contents()
0xca70  ldloca.s 6
0xca72  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceContentItem>::get_Key()
0xca77  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceContentItem::.ctor()
0xca7c  dup
0xca7d  ldloca.s 6
0xca7f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceContentItem>::get_Key()
0xca84  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceContentItem::set_Key(string)
0xca89  dup
0xca8a  ldloc.s  7
0xca8c  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceContentItem::set_ContentType(string)
0xca91  dup
0xca92  ldloc.s  8
0xca94  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceContentItem::set_Path(string)
0xca99  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceContentItem>::Add(var<u1>, !!T0)
0xca9e  ldloc.s  8
0xcaa0  call     unsigned int8[] Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::GetBytes(string location)
0xcaa5  stloc.s  9
0xcaa7  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, unsigned int8[]> Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::_contentCache
0xcaac  ldc.i4.2
0xcaad  newarr   [mscorlib]System.String
0xcab2  dup
0xcab3  ldc.i4.0
0xcab4  ldloc.0
0xcab5  stelem.ref
0xcab6  dup
0xcab7  ldc.i4.1
0xcab8  ldloca.s 6
0xcaba  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourceContentItem>::get_Key()
0xcabf  stelem.ref
0xcac0  call     string Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::CreateCacheKey(string[] names)
0xcac5  ldloc.s  9
0xcac7  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, unsigned int8[]>::Add(var<u1>, !!T0)
0xcacc  ldloc.s  5
0xcace  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xcad3  brtrue   loc_CA14
0xcad8  leave.s  loc_CAE6
0xcada  ldloc.s  5
0xcadc  brfalse.s loc_CAE5
0xcade  ldloc.s  5
0xcae0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcae5  endfinally
0xcae6  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, unsigned int8[]> Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::_contentCache
0xcaeb  ldc.i4.2
0xcaec  newarr   [mscorlib]System.String
0xcaf1  dup
0xcaf2  ldc.i4.0
0xcaf3  ldloc.0
0xcaf4  stelem.ref
0xcaf5  call     string Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::CreateCacheKey(string[] names)
0xcafa  ldarg.3
0xcafb  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, unsigned int8[]>::Add(var<u1>, !!T0)
0xcb00  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResource> Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::_resourceCache
0xcb05  ldc.i4.1
0xcb06  newarr   [mscorlib]System.String
0xcb0b  dup
0xcb0c  ldc.i4.0
0xcb0d  ldloc.0
0xcb0e  stelem.ref
0xcb0f  call     string Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResourceManager::CreateCacheKey(string[] names)
0xcb14  ldloc.s  4
0xcb16  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.ReportingServices.Portal.Services.SystemResources.EmbeddedSystemResource>::Add(var<u1>, !!T0)
0xcb1b  ldloc.s  4
0xcb1d  ret
```
