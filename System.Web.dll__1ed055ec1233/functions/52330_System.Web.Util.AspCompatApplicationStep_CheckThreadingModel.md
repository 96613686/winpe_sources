# System.Web.Util.AspCompatApplicationStep::CheckThreadingModel

- ea: `0x52330`
- end: `0x523e8`
- name: `System.Web.Util.AspCompatApplicationStep::CheckThreadingModel`
- size: `184`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x25050`
- `0x250b0`
- `0x250e0`

## callees

- `0x18990`
- `0x243e0`
- `0x34f20`
- `0x52150`
- `0x52330`
- `0x58d50`
- `0x186590`
- `0x1865a0`
- `0x1868f0`

## string_xrefs

- `0x52366`: `CLSID\{`
- `0x5238f`: `ThreadingModel`
- `0x523cd`: `Apartment_component_not_allowed`

## pseudocode

```c

```

## disassembly

```asm
0x52330  call     bool System.Web.Util.AspCompatApplicationStep::get_IsInAspCompatMode()
0x52335  brfalse.s loc_52338
0x52337  ret
0x52338  call     class System.Web.Caching.Cache System.Web.HttpRuntime::get_Cache()
0x5233d  callvirt instance class System.Web.Caching.CacheStoreProvider System.Web.Caching.Cache::get_InternalCache()
0x52342  stloc.0
0x52343  ldstr    aS_0// "s"
0x52348  ldarg.0
0x52349  call     string [mscorlib]System.String::Concat(string, string)
0x5234e  stloc.1
0x5234f  ldloc.0
0x52350  ldloc.1
0x52351  callvirt instance object System.Web.Caching.CacheStoreProvider::Get(string key)
0x52356  castclass [mscorlib]System.String
0x5235b  stloc.2
0x5235c  ldnull
0x5235d  stloc.3
0x5235e  ldloc.2
0x5235f  brtrue.s loc_523C0
0x52361  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::ClassesRoot
0x52366  ldstr    aClsid// "CLSID\\{"
0x5236b  ldarg.1
0x5236c  stloc.s  4
0x5236e  ldloca.s 4
0x52370  constrained. [mscorlib]System.Guid
0x52376  callvirt instance string [mscorlib]System.Object::ToString()
0x5237b  ldstr    aInprocserver32// "}\\InprocServer32"
0x52380  call     string [mscorlib]System.String::Concat(string, string, string)
0x52385  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x5238a  stloc.3
0x5238b  ldloc.3
0x5238c  brfalse.s loc_5239F
0x5238e  ldloc.3
0x5238f  ldstr    aThreadingmodel// "ThreadingModel"
0x52394  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x52399  castclass [mscorlib]System.String
0x5239e  stloc.2
0x5239f  leave.s  loc_523AE
0x523a1  pop
0x523a2  leave.s  loc_523AE
0x523a4  ldloc.3
0x523a5  brfalse.s loc_523AD
0x523a7  ldloc.3
0x523a8  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::Close()
0x523ad  endfinally
0x523ae  ldloc.2
0x523af  brtrue.s loc_523B7
0x523b1  ldsfld   string [mscorlib]System.String::Empty
0x523b6  stloc.2
0x523b7  ldloc.0
0x523b8  ldloc.1
0x523b9  ldloc.2
0x523ba  ldnull
0x523bb  callvirt instance void System.Web.Caching.CacheStoreProvider::Insert(string key, object item, class System.Web.Caching.CacheInsertOptions options)
0x523c0  ldloc.2
0x523c1  ldstr    aApartment// "Apartment"
0x523c6  call     bool System.Web.Util.StringUtil::EqualsIgnoreCase(string s1, string s2)
0x523cb  brfalse.s loc_523E7
0x523cd  ldstr    aApartmentCompo// "Apartment_component_not_allowed"
0x523d2  ldc.i4.1
0x523d3  newarr   [mscorlib]System.Object
0x523d8  dup
0x523d9  ldc.i4.0
0x523da  ldarg.0
0x523db  stelem.ref
0x523dc  call     string System.Web.SR::GetString(string name, object[] args)
0x523e1  newobj   instance void System.Web.HttpException::.ctor(string message)
0x523e6  throw
0x523e7  ret
```
