# System.Web.XmlSiteMapProvider::EnsureChildSiteMapProviderUpToDate

- ea: `0x333f0`
- end: `0x335ec`
- name: `System.Web.XmlSiteMapProvider::EnsureChildSiteMapProviderUpToDate`
- size: `508`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x333f0`
- `0x335f0`
- `0x33650`

## callees

- `0x2c3c0`
- `0x2c670`
- `0x2cc80`
- `0x2cd60`
- `0x2cd70`
- `0x2cdf0`
- `0x2d010`
- `0x2d370`
- `0x2e010`
- `0x2e050`
- `0x2e090`
- `0x2e0d0`
- `0x32cf0`
- `0x333f0`
- `0x34f20`

## string_xrefs

- `0x3340c`: `XmlSiteMapProvider_invalid_sitemapnode_returned`
- `0x33470`: `XmlSiteMapProvider_invalid_sitemapnode_returned`

## pseudocode

```c

```

## disassembly

```asm
0x333f0  ldarg.0
0x333f1  call     instance class [mscorlib]System.Collections.Hashtable System.Web.XmlSiteMapProvider::get_ChildProviderTable()
0x333f6  ldarg.1
0x333f7  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x333fc  castclass System.Web.SiteMapNode
0x33401  stloc.0
0x33402  ldarg.1
0x33403  callvirt instance class System.Web.SiteMapNode System.Web.SiteMapProvider::GetRootNodeCore()
0x33408  stloc.1
0x33409  ldloc.1
0x3340a  brtrue.s loc_3342B
0x3340c  ldstr    aXmlsitemapprov_7// "XmlSiteMapProvider_invalid_sitemapnode_"...
0x33411  ldc.i4.1
0x33412  newarr   [mscorlib]System.Object
0x33417  dup
0x33418  ldc.i4.0
0x33419  ldarg.1
0x3341a  callvirt instance string [System.Configuration]System.Configuration.Provider.ProviderBase::get_Name()
0x3341f  stelem.ref
0x33420  call     string System.Web.SR::GetString(string name, object[] args)
0x33425  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x3342a  throw
0x3342b  ldloc.0
0x3342c  ldloc.1
0x3342d  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x33432  brtrue   loc_335EB
0x33437  ldloc.0
0x33438  brtrue.s loc_3343B
0x3343a  ret
0x3343b  ldarg.0
0x3343c  ldfld    object System.Web.SiteMapProvider::_lock
0x33441  stloc.2
0x33442  ldc.i4.0
0x33443  stloc.3
0x33444  ldloc.2
0x33445  ldloca.s 3
0x33447  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x3344c  ldarg.0
0x3344d  call     instance class [mscorlib]System.Collections.Hashtable System.Web.XmlSiteMapProvider::get_ChildProviderTable()
0x33452  ldarg.1
0x33453  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x33458  castclass System.Web.SiteMapNode
0x3345d  stloc.0
0x3345e  ldloc.0
0x3345f  brtrue.s loc_33466
0x33461  leave    loc_335EB
0x33466  ldarg.1
0x33467  callvirt instance class System.Web.SiteMapNode System.Web.SiteMapProvider::GetRootNodeCore()
0x3346c  stloc.1
0x3346d  ldloc.1
0x3346e  brtrue.s loc_3348F
0x33470  ldstr    aXmlsitemapprov_7// "XmlSiteMapProvider_invalid_sitemapnode_"...
0x33475  ldc.i4.1
0x33476  newarr   [mscorlib]System.Object
0x3347b  dup
0x3347c  ldc.i4.0
0x3347d  ldarg.1
0x3347e  callvirt instance string [System.Configuration]System.Configuration.Provider.ProviderBase::get_Name()
0x33483  stelem.ref
0x33484  call     string System.Web.SR::GetString(string name, object[] args)
0x33489  newobj   instance void [System.Configuration]System.Configuration.Provider.ProviderException::.ctor(string)
0x3348e  throw
0x3348f  ldloc.0
0x33490  ldloc.1
0x33491  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x33496  brtrue   loc_335DF
0x3349b  ldarg.0
0x3349c  ldfld    class System.Web.SiteMapNode System.Web.XmlSiteMapProvider::_siteMapNode
0x334a1  ldloc.0
0x334a2  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x334a7  brfalse.s loc_334F6
0x334a9  ldarg.0
0x334aa  call     instance class [mscorlib]System.Collections.IDictionary System.Web.StaticSiteMapProvider::get_UrlTable()
0x334af  ldloc.0
0x334b0  callvirt instance string System.Web.SiteMapNode::get_Url()
0x334b5  callvirt instance void [mscorlib]System.Collections.IDictionary::Remove(object)
0x334ba  ldarg.0
0x334bb  call     instance class [mscorlib]System.Collections.IDictionary System.Web.StaticSiteMapProvider::get_KeyTable()
0x334c0  ldloc.0
0x334c1  callvirt instance string System.Web.SiteMapNode::get_Key()
0x334c6  callvirt instance void [mscorlib]System.Collections.IDictionary::Remove(object)
0x334cb  ldarg.0
0x334cc  call     instance class [mscorlib]System.Collections.IDictionary System.Web.StaticSiteMapProvider::get_UrlTable()
0x334d1  ldloc.1
0x334d2  callvirt instance string System.Web.SiteMapNode::get_Url()
0x334d7  ldloc.1
0x334d8  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x334dd  ldarg.0
0x334de  call     instance class [mscorlib]System.Collections.IDictionary System.Web.StaticSiteMapProvider::get_KeyTable()
0x334e3  ldloc.1
0x334e4  callvirt instance string System.Web.SiteMapNode::get_Key()
0x334e9  ldloc.1
0x334ea  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x334ef  ldarg.0
0x334f0  ldloc.1
0x334f1  stfld    class System.Web.SiteMapNode System.Web.XmlSiteMapProvider::_siteMapNode
0x334f6  ldarg.0
0x334f7  call     instance class [mscorlib]System.Collections.IDictionary System.Web.StaticSiteMapProvider::get_ParentNodeTable()
0x334fc  ldloc.0
0x334fd  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x33502  castclass System.Web.SiteMapNode
0x33507  stloc.s  4
0x33509  ldloc.s  4
0x3350b  brfalse  loc_335B2
0x33510  ldarg.0
0x33511  call     instance class [mscorlib]System.Collections.IDictionary System.Web.StaticSiteMapProvider::get_ChildNodeCollectionTable()
0x33516  ldloc.s  4
0x33518  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x3351d  castclass System.Web.SiteMapNodeCollection
0x33522  stloc.s  5
0x33524  ldloc.s  5
0x33526  ldloc.0
0x33527  callvirt instance int32 System.Web.SiteMapNodeCollection::IndexOf(class System.Web.SiteMapNode value)
0x3352c  stloc.s  6
0x3352e  ldloc.s  6
0x33530  ldc.i4.m1
0x33531  beq.s    loc_33547
0x33533  ldloc.s  5
0x33535  ldloc.0
0x33536  callvirt instance void System.Web.SiteMapNodeCollection::Remove(class System.Web.SiteMapNode value)
0x3353b  ldloc.s  5
0x3353d  ldloc.s  6
0x3353f  ldloc.1
0x33540  callvirt instance void System.Web.SiteMapNodeCollection::Insert(int32 index, class System.Web.SiteMapNode value)
0x33545  br.s     loc_33550
0x33547  ldloc.s  5
0x33549  ldloc.1
0x3354a  callvirt instance int32 System.Web.SiteMapNodeCollection::Add(class System.Web.SiteMapNode value)
0x3354f  pop
0x33550  ldarg.0
0x33551  call     instance class [mscorlib]System.Collections.IDictionary System.Web.StaticSiteMapProvider::get_ParentNodeTable()
0x33556  ldloc.1
0x33557  ldloc.s  4
0x33559  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x3355e  ldarg.0
0x3355f  call     instance class [mscorlib]System.Collections.IDictionary System.Web.StaticSiteMapProvider::get_ParentNodeTable()
0x33564  ldloc.0
0x33565  callvirt instance void [mscorlib]System.Collections.IDictionary::Remove(object)
0x3356a  ldarg.0
0x3356b  call     instance class [mscorlib]System.Collections.IDictionary System.Web.StaticSiteMapProvider::get_UrlTable()
0x33570  ldloc.0
0x33571  callvirt instance string System.Web.SiteMapNode::get_Url()
0x33576  callvirt instance void [mscorlib]System.Collections.IDictionary::Remove(object)
0x3357b  ldarg.0
0x3357c  call     instance class [mscorlib]System.Collections.IDictionary System.Web.StaticSiteMapProvider::get_KeyTable()
0x33581  ldloc.0
0x33582  callvirt instance string System.Web.SiteMapNode::get_Key()
0x33587  callvirt instance void [mscorlib]System.Collections.IDictionary::Remove(object)
0x3358c  ldarg.0
0x3358d  call     instance class [mscorlib]System.Collections.IDictionary System.Web.StaticSiteMapProvider::get_UrlTable()
0x33592  ldloc.1
0x33593  callvirt instance string System.Web.SiteMapNode::get_Url()
0x33598  ldloc.1
0x33599  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x3359e  ldarg.0
0x3359f  call     instance class [mscorlib]System.Collections.IDictionary System.Web.StaticSiteMapProvider::get_KeyTable()
0x335a4  ldloc.1
0x335a5  callvirt instance string System.Web.SiteMapNode::get_Key()
0x335aa  ldloc.1
0x335ab  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x335b0  br.s     loc_335CB
0x335b2  ldarg.0
0x335b3  callvirt instance class System.Web.SiteMapProvider System.Web.SiteMapProvider::get_ParentProvider()
0x335b8  isinst   System.Web.XmlSiteMapProvider
0x335bd  stloc.s  7
0x335bf  ldloc.s  7
0x335c1  brfalse.s loc_335CB
0x335c3  ldloc.s  7
0x335c5  ldarg.0
0x335c6  callvirt instance void System.Web.XmlSiteMapProvider::EnsureChildSiteMapProviderUpToDate(class System.Web.SiteMapProvider childProvider)
0x335cb  ldarg.0
0x335cc  call     instance class [mscorlib]System.Collections.Hashtable System.Web.XmlSiteMapProvider::get_ChildProviderTable()
0x335d1  ldarg.1
0x335d2  ldloc.1
0x335d3  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x335d8  ldarg.0
0x335d9  ldnull
0x335da  stfld    class [mscorlib]System.Collections.ArrayList System.Web.XmlSiteMapProvider::_childProviderList
0x335df  leave.s  loc_335EB
0x335e1  ldloc.3
0x335e2  brfalse.s loc_335EA
0x335e4  ldloc.2
0x335e5  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x335ea  endfinally
0x335eb  ret
```
