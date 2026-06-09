# Microsoft.ReportingServices.Library.RSLocalCacheManager::PrintCachedItems

- ea: `0x5b610`
- end: `0x5b7c0`
- name: `Microsoft.ReportingServices.Library.RSLocalCacheManager::PrintCachedItems`
- size: `432`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x5b820`
- `0x5b860`
- `0x5b880`

## callees

- `0x59e30`
- `0x59e50`
- `0x59e80`
- `0x59e90`
- `0x5b610`

## string_xrefs

- `0x5b626`: `Cache content:`
- `0x5b68d`: `	Cached item:`

## pseudocode

```c

```

## disassembly

```asm
0x5b610  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x5b615  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x5b61a  brfalse  loc_5B7BF
0x5b61f  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x5b624  stloc.1
0x5b625  ldloc.1
0x5b626  ldstr    aCacheContent// "Cache content:"
0x5b62b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x5b630  pop
0x5b631  call     class [System.Web]System.Web.Caching.Cache [System.Web]System.Web.HttpRuntime::get_Cache()
0x5b636  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator [System.Web]System.Web.Caching.Cache::GetEnumerator()
0x5b63b  stloc.2
0x5b63c  br       loc_5B78B
0x5b641  ldloc.2
0x5b642  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5b647  unbox.any [mscorlib]System.Collections.DictionaryEntry
0x5b64c  stloc.3
0x5b64d  ldarg.0
0x5b64e  ldfld    class [System.Web]System.Web.Caching.Cache Microsoft.ReportingServices.Library.RSLocalCacheManager::cache
0x5b653  ldloca.s 3
0x5b655  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Key()
0x5b65a  castclass [mscorlib]System.String
0x5b65f  callvirt instance object [System.Web]System.Web.Caching.Cache::get_Item(string)
0x5b664  isinst   Microsoft.ReportingServices.Library.ICachedItem
0x5b669  stloc.s  4
0x5b66b  ldloc.s  4
0x5b66d  brfalse  loc_5B78B
0x5b672  ldloc.1
0x5b673  ldstr    aKey0// "Key: {0}"
0x5b678  ldloca.s 3
0x5b67a  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Key()
0x5b67f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x5b684  pop
0x5b685  ldloc.1
0x5b686  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x5b68b  pop
0x5b68c  ldloc.1
0x5b68d  ldstr    aCachedItem// "\tCached item:"
0x5b692  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x5b697  pop
0x5b698  ldloc.1
0x5b699  ldstr    aType0// "\tType: {0}"
0x5b69e  ldloc.s  4
0x5b6a0  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5b6a5  callvirt instance string [mscorlib]System.Object::ToString()
0x5b6aa  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x5b6af  pop
0x5b6b0  ldloc.1
0x5b6b1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x5b6b6  pop
0x5b6b7  ldloc.1
0x5b6b8  ldstr    aExpires0Estima// "\tExpires: {0}\t Estimated Size: {1} KB"
0x5b6bd  ldloc.s  4
0x5b6bf  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.ICachedItem::get_ExpirationDate()
0x5b6c4  stloc.s  6
0x5b6c6  ldloca.s 6
0x5b6c8  call     instance string [mscorlib]System.DateTime::ToString()
0x5b6cd  ldloc.s  4
0x5b6cf  callvirt instance int64 Microsoft.ReportingServices.Library.ICachedItem::get_SizeEstimateKb()
0x5b6d4  box      [mscorlib]System.Int64
0x5b6d9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x5b6de  pop
0x5b6df  ldloc.1
0x5b6e0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x5b6e5  pop
0x5b6e6  ldloc.s  4
0x5b6e8  isinst   Microsoft.ReportingServices.Library.IHierarchicalCachedItem
0x5b6ed  stloc.s  5
0x5b6ef  ldloc.s  5
0x5b6f1  brfalse  loc_5B784
0x5b6f6  ldloc.1
0x5b6f7  ldstr    aParentKey0// "\t\tParent key : {0}"
0x5b6fc  ldloc.s  5
0x5b6fe  callvirt instance string Microsoft.ReportingServices.Library.IHierarchicalCachedItem::get_ParentKey()
0x5b703  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x5b708  pop
0x5b709  ldloc.1
0x5b70a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x5b70f  pop
0x5b710  ldloc.1
0x5b711  ldstr    aChildren// "\t\tChildren:"
0x5b716  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x5b71b  pop
0x5b71c  ldloc.s  5
0x5b71e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Library.IHierarchicalCachedItem::get_ChildKeys()
0x5b723  stloc.s  7
0x5b725  ldc.i4.0
0x5b726  stloc.s  8
0x5b728  ldloc.s  7
0x5b72a  ldloca.s 8
0x5b72c  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x5b731  ldloc.s  5
0x5b733  callvirt instance class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Library.IHierarchicalCachedItem::get_ChildKeys()
0x5b738  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x5b73d  stloc.s  9
0x5b73f  br.s     loc_5B75F
0x5b741  ldloca.s 9
0x5b743  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x5b748  stloc.s  0xA
0x5b74a  ldloc.1
0x5b74b  ldstr    aChildKey0// "\t\t\t Child key: {0}"
0x5b750  ldloc.s  0xA
0x5b752  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x5b757  pop
0x5b758  ldloc.1
0x5b759  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x5b75e  pop
0x5b75f  ldloca.s 9
0x5b761  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x5b766  brtrue.s loc_5B741
0x5b768  leave.s  loc_5B784
0x5b76a  ldloca.s 9
0x5b76c  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x5b772  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5b777  endfinally
0x5b778  ldloc.s  8
0x5b77a  brfalse.s loc_5B783
0x5b77c  ldloc.s  7
0x5b77e  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x5b783  endfinally
0x5b784  ldloc.1
0x5b785  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x5b78a  pop
0x5b78b  ldloc.2
0x5b78c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5b791  brtrue   loc_5B641
0x5b796  leave.s  loc_5B7AC
0x5b798  ldloc.2
0x5b799  isinst   [mscorlib]System.IDisposable
0x5b79e  stloc.s  0xB
0x5b7a0  ldloc.s  0xB
0x5b7a2  brfalse.s loc_5B7AB
0x5b7a4  ldloc.s  0xB
0x5b7a6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5b7ab  endfinally
0x5b7ac  ldloc.1
0x5b7ad  callvirt instance string [mscorlib]System.Object::ToString()
0x5b7b2  stloc.0
0x5b7b3  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CacheTracer()
0x5b7b8  ldc.i4.4
0x5b7b9  ldloc.0
0x5b7ba  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5b7bf  ret
```
