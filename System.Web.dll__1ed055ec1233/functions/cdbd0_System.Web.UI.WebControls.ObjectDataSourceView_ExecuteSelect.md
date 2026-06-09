# System.Web.UI.WebControls.ObjectDataSourceView::ExecuteSelect

- ea: `0xcdbd0`
- end: `0xce0ea`
- name: `System.Web.UI.WebControls.ObjectDataSourceView::ExecuteSelect`
- size: `1306`
- prototype: ``
- caller_count: `0`
- callee_count: `42`
- tags: ``

## callees

- `0x34f20`
- `0x5f1b0`
- `0x68550`
- `0x68ee0`
- `0x68f30`
- `0x68f70`
- `0x68f90`
- `0x68fc0`
- `0x69020`
- `0x69030`
- `0x690e0`
- `0x691b0`
- `0x691c0`
- `0x691d0`
- `0xad550`
- `0xcbe60`
- `0xcc630`
- `0xcc650`
- `0xcc750`
- `0xcca20`
- `0xccda0`
- `0xccdd0`
- `0xcced0`
- `0xccf60`
- `0xccfb0`
- `0xcd000`
- `0xcd050`
- `0xcd0a0`
- `0xcd0f0`
- `0xcd720`
- `0xcd7f0`
- `0xcdbd0`
- `0xce670`
- `0xce8d0`
- `0xce960`
- `0xceba0`
- `0xcee40`
- `0xceed0`
- `0xcef20`
- `0xcefa0`
- `0xcefd0`
- `0xd1140`

## string_xrefs

- `0xcdff1`: `ObjectDataSourceView_CacheNotSupportedOnSortedDataView`
- `0xce0b7`: `ObjectDataSourceView_CacheNotSupportedOnIDataReader`

## pseudocode

```c

```

## disassembly

```asm
0xcdbd0  ldarg.0
0xcdbd1  call     instance string System.Web.UI.WebControls.ObjectDataSourceView::get_SelectMethod()
0xcdbd6  callvirt instance int32 [mscorlib]System.String::get_Length()
0xcdbdb  brtrue.s loc_CDC01
0xcdbdd  ldstr    aObjectdatasour_8// "ObjectDataSourceView_SelectNotSupported"
0xcdbe2  ldc.i4.1
0xcdbe3  newarr   [mscorlib]System.Object
0xcdbe8  dup
0xcdbe9  ldc.i4.0
0xcdbea  ldarg.0
0xcdbeb  ldfld    class System.Web.UI.WebControls.ObjectDataSource System.Web.UI.WebControls.ObjectDataSourceView::_owner
0xcdbf0  callvirt instance string System.Web.UI.Control::get_ID()
0xcdbf5  stelem.ref
0xcdbf6  call     string System.Web.SR::GetString(string name, object[] args)
0xcdbfb  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xcdc00  throw
0xcdc01  ldarg.0
0xcdc02  callvirt instance bool System.Web.UI.DataSourceView::get_CanSort()
0xcdc07  brfalse.s loc_CDC10
0xcdc09  ldarg.1
0xcdc0a  ldc.i4.1
0xcdc0b  callvirt instance void System.Web.UI.DataSourceSelectArguments::AddSupportedCapabilities(valuetype System.Web.UI.DataSourceCapabilities capabilities)
0xcdc10  ldarg.0
0xcdc11  callvirt instance bool System.Web.UI.DataSourceView::get_CanPage()
0xcdc16  brfalse.s loc_CDC1F
0xcdc18  ldarg.1
0xcdc19  ldc.i4.2
0xcdc1a  callvirt instance void System.Web.UI.DataSourceSelectArguments::AddSupportedCapabilities(valuetype System.Web.UI.DataSourceCapabilities capabilities)
0xcdc1f  ldarg.0
0xcdc20  callvirt instance bool System.Web.UI.DataSourceView::get_CanRetrieveTotalRowCount()
0xcdc25  brfalse.s loc_CDC2E
0xcdc27  ldarg.1
0xcdc28  ldc.i4.4
0xcdc29  callvirt instance void System.Web.UI.DataSourceSelectArguments::AddSupportedCapabilities(valuetype System.Web.UI.DataSourceCapabilities capabilities)
0xcdc2e  ldarg.1
0xcdc2f  ldarg.0
0xcdc30  callvirt instance void System.Web.UI.DataSourceSelectArguments::RaiseUnsupportedCapabilitiesError(class System.Web.UI.DataSourceView view)
0xcdc35  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xcdc3a  newobj   instance void [System]System.Collections.Specialized.OrderedDictionary::.ctor(class [mscorlib]System.Collections.IEqualityComparer)
0xcdc3f  stloc.0
0xcdc40  ldarg.0
0xcdc41  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.ObjectDataSourceView::get_SelectParameters()
0xcdc46  ldarg.0
0xcdc47  ldfld    class System.Web.HttpContext System.Web.UI.WebControls.ObjectDataSourceView::_context
0xcdc4c  ldarg.0
0xcdc4d  ldfld    class System.Web.UI.WebControls.ObjectDataSource System.Web.UI.WebControls.ObjectDataSourceView::_owner
0xcdc52  callvirt instance class [System]System.Collections.Specialized.IOrderedDictionary System.Web.UI.WebControls.ParameterCollection::GetValues(class System.Web.HttpContext context, class System.Web.UI.Control control)
0xcdc57  stloc.1
0xcdc58  ldloc.1
0xcdc59  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator [mscorlib]System.Collections.IDictionary::GetEnumerator()
0xcdc5e  stloc.s  9
0xcdc60  br.s     loc_CDC84
0xcdc62  ldloc.s  9
0xcdc64  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xcdc69  unbox.any [mscorlib]System.Collections.DictionaryEntry
0xcdc6e  stloc.s  0xA
0xcdc70  ldloc.0
0xcdc71  ldloca.s 0xA
0xcdc73  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Key()
0xcdc78  ldloca.s 0xA
0xcdc7a  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Value()
0xcdc7f  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0xcdc84  ldloc.s  9
0xcdc86  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xcdc8b  brtrue.s loc_CDC62
0xcdc8d  leave.s  loc_CDCA4
0xcdc8f  ldloc.s  9
0xcdc91  isinst   [mscorlib]System.IDisposable
0xcdc96  stloc.s  0xB
0xcdc98  ldloc.s  0xB
0xcdc9a  brfalse.s loc_CDCA3
0xcdc9c  ldloc.s  0xB
0xcdc9e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcdca3  endfinally
0xcdca4  ldarg.0
0xcdca5  ldfld    class System.Web.UI.WebControls.ObjectDataSource System.Web.UI.WebControls.ObjectDataSourceView::_owner
0xcdcaa  callvirt instance class System.Web.UI.SqlDataSourceCache System.Web.UI.WebControls.ObjectDataSource::get_Cache()
0xcdcaf  callvirt instance bool System.Web.UI.DataSourceCache::get_Enabled()
0xcdcb4  stloc.2
0xcdcb5  ldloc.2
0xcdcb6  brfalse  loc_CDD92
0xcdcbb  ldarg.0
0xcdcbc  ldfld    class System.Web.UI.WebControls.ObjectDataSource System.Web.UI.WebControls.ObjectDataSourceView::_owner
0xcdcc1  ldarg.1
0xcdcc2  callvirt instance int32 System.Web.UI.DataSourceSelectArguments::get_StartRowIndex()
0xcdcc7  ldarg.1
0xcdcc8  callvirt instance int32 System.Web.UI.DataSourceSelectArguments::get_MaximumRows()
0xcdccd  callvirt instance object System.Web.UI.WebControls.ObjectDataSource::LoadDataFromCache(int32 startRowIndex, int32 maximumRows)
0xcdcd2  stloc.s  0xC
0xcdcd4  ldloc.s  0xC
0xcdcd6  brfalse  loc_CDD92
0xcdcdb  ldloc.s  0xC
0xcdcdd  isinst   [System.Data]System.Data.DataView
0xcdce2  stloc.s  0xD
0xcdce4  ldloc.s  0xD
0xcdce6  brfalse.s loc_CDD4C
0xcdce8  ldarg.1
0xcdce9  callvirt instance bool System.Web.UI.DataSourceSelectArguments::get_RetrieveTotalRowCount()
0xcdcee  brfalse.s loc_CDD0A
0xcdcf0  ldarg.0
0xcdcf1  call     instance string System.Web.UI.WebControls.ObjectDataSourceView::get_SelectCountMethod()
0xcdcf6  callvirt instance int32 [mscorlib]System.String::get_Length()
0xcdcfb  brtrue.s loc_CDD0A
0xcdcfd  ldarg.1
0xcdcfe  ldloc.s  0xD
0xcdd00  callvirt instance int32 [System.Data]System.Data.DataView::get_Count()
0xcdd05  callvirt instance void System.Web.UI.DataSourceSelectArguments::set_TotalRowCount(int32 value)
0xcdd0a  ldarg.0
0xcdd0b  call     instance string System.Web.UI.WebControls.ObjectDataSourceView::get_FilterExpression()
0xcdd10  callvirt instance int32 [mscorlib]System.String::get_Length()
0xcdd15  ldc.i4.0
0xcdd16  ble.s    loc_CDD3C
0xcdd18  ldstr    aObjectdatasour_2// "ObjectDataSourceView_FilterNotSupported"
0xcdd1d  ldc.i4.1
0xcdd1e  newarr   [mscorlib]System.Object
0xcdd23  dup
0xcdd24  ldc.i4.0
0xcdd25  ldarg.0
0xcdd26  ldfld    class System.Web.UI.WebControls.ObjectDataSource System.Web.UI.WebControls.ObjectDataSourceView::_owner
0xcdd2b  callvirt instance string System.Web.UI.Control::get_ID()
0xcdd30  stelem.ref
0xcdd31  call     string System.Web.SR::GetString(string name, object[] args)
0xcdd36  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xcdd3b  throw
0xcdd3c  ldarg.1
0xcdd3d  callvirt instance string System.Web.UI.DataSourceSelectArguments::get_SortExpression()
0xcdd42  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xcdd47  brfalse.s loc_CDD92
0xcdd49  ldloc.s  0xD
0xcdd4b  ret
0xcdd4c  ldarg.0
0xcdd4d  ldfld    class System.Web.UI.WebControls.ObjectDataSource System.Web.UI.WebControls.ObjectDataSourceView::_owner
0xcdd52  ldloc.s  0xC
0xcdd54  call     class [System.Data]System.Data.DataTable System.Web.UI.WebControls.FilteredDataSetHelper::GetDataTable(class System.Web.UI.Control owner, object dataObject)
0xcdd59  stloc.s  0xE
0xcdd5b  ldloc.s  0xE
0xcdd5d  brfalse.s loc_CDD7C
0xcdd5f  ldarg.0
0xcdd60  ldarg.1
0xcdd61  ldloc.0
0xcdd62  call     instance void System.Web.UI.WebControls.ObjectDataSourceView::ProcessPagingData(class System.Web.UI.DataSourceSelectArguments arguments, class [System]System.Collections.Specialized.IOrderedDictionary parameters)
0xcdd67  ldarg.0
0xcdd68  ldloc.s  0xE
0xcdd6a  ldarg.1
0xcdd6b  callvirt instance string System.Web.UI.DataSourceSelectArguments::get_SortExpression()
0xcdd70  ldarg.0
0xcdd71  call     instance string System.Web.UI.WebControls.ObjectDataSourceView::get_FilterExpression()
0xcdd76  call     instance class [mscorlib]System.Collections.IEnumerable System.Web.UI.WebControls.ObjectDataSourceView::CreateFilteredDataView(class [System.Data]System.Data.DataTable dataTable, string sortExpression, string filterExpression)
0xcdd7b  ret
0xcdd7c  ldarg.0
0xcdd7d  ldloc.s  0xC
0xcdd7f  ldarg.1
0xcdd80  call     instance class [mscorlib]System.Collections.IEnumerable System.Web.UI.WebControls.ObjectDataSourceView::CreateEnumerableData(object dataObject, class System.Web.UI.DataSourceSelectArguments arguments)
0xcdd85  stloc.s  0xF
0xcdd87  ldarg.0
0xcdd88  ldarg.1
0xcdd89  ldloc.0
0xcdd8a  call     instance void System.Web.UI.WebControls.ObjectDataSourceView::ProcessPagingData(class System.Web.UI.DataSourceSelectArguments arguments, class [System]System.Collections.Specialized.IOrderedDictionary parameters)
0xcdd8f  ldloc.s  0xF
0xcdd91  ret
0xcdd92  ldloc.0
0xcdd93  ldarg.1
0xcdd94  ldc.i4.0
0xcdd95  newobj   instance void System.Web.UI.WebControls.ObjectDataSourceSelectingEventArgs::.ctor(class [System]System.Collections.Specialized.IOrderedDictionary inputParameters, class System.Web.UI.DataSourceSelectArguments arguments, bool executingSelectCount)
0xcdd9a  stloc.3
0xcdd9b  ldarg.0
0xcdd9c  ldloc.3
0xcdd9d  callvirt instance void System.Web.UI.WebControls.ObjectDataSourceView::OnSelecting(class System.Web.UI.WebControls.ObjectDataSourceSelectingEventArgs e)
0xcdda2  ldloc.3
0xcdda3  callvirt instance bool [System]System.ComponentModel.CancelEventArgs::get_Cancel()
0xcdda8  brfalse.s loc_CDDAC
0xcddaa  ldnull
0xcddab  ret
0xcddac  ldloc.0
0xcddad  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0xcddb2  newobj   instance void [System]System.Collections.Specialized.OrderedDictionary::.ctor(int32)
0xcddb7  stloc.s  4
0xcddb9  ldloc.0
0xcddba  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator [System]System.Collections.Specialized.IOrderedDictionary::GetEnumerator()
0xcddbf  stloc.s  0x10
0xcddc1  br.s     loc_CDDE6
0xcddc3  ldloc.s  0x10
0xcddc5  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xcddca  unbox.any [mscorlib]System.Collections.DictionaryEntry
0xcddcf  stloc.s  0x11
0xcddd1  ldloc.s  4
0xcddd3  ldloca.s 0x11
0xcddd5  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Key()
0xcddda  ldloca.s 0x11
0xcdddc  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Value()
0xcdde1  callvirt instance void [System]System.Collections.Specialized.OrderedDictionary::Add(object, object)
0xcdde6  ldloc.s  0x10
0xcdde8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xcdded  brtrue.s loc_CDDC3
0xcddef  leave.s  loc_CDE06
0xcddf1  ldloc.s  0x10
0xcddf3  isinst   [mscorlib]System.IDisposable
0xcddf8  stloc.s  0xB
0xcddfa  ldloc.s  0xB
0xcddfc  brfalse.s loc_CDE05
0xcddfe  ldloc.s  0xB
0xcde00  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcde05  endfinally
0xcde06  ldarg.0
0xcde07  call     instance string System.Web.UI.WebControls.ObjectDataSourceView::get_SortParameterName()
0xcde0c  stloc.s  5
0xcde0e  ldloc.s  5
0xcde10  callvirt instance int32 [mscorlib]System.String::get_Length()
0xcde15  ldc.i4.0
0xcde16  ble.s    loc_CDE31
0xcde18  ldloc.0
0xcde19  ldloc.s  5
0xcde1b  ldarg.1
0xcde1c  callvirt instance string System.Web.UI.DataSourceSelectArguments::get_SortExpression()
0xcde21  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0xcde26  ldarg.1
0xcde27  ldsfld   string [mscorlib]System.String::Empty
0xcde2c  callvirt instance void System.Web.UI.DataSourceSelectArguments::set_SortExpression(string value)
0xcde31  ldarg.0
0xcde32  call     instance bool System.Web.UI.WebControls.ObjectDataSourceView::get_EnablePaging()
0xcde37  brfalse  loc_CDEC4
0xcde3c  ldarg.0
0xcde3d  call     instance string System.Web.UI.WebControls.ObjectDataSourceView::get_MaximumRowsParameterName()
0xcde42  stloc.s  0x12
0xcde44  ldarg.0
0xcde45  call     instance string System.Web.UI.WebControls.ObjectDataSourceView::get_StartRowIndexParameterName()
0xcde4a  stloc.s  0x13
0xcde4c  ldloc.s  0x12
0xcde4e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xcde53  brtrue.s loc_CDE5E
0xcde55  ldloc.s  0x13
0xcde57  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xcde5c  brfalse.s loc_CDE82
0xcde5e  ldstr    aObjectdatasour_9// "ObjectDataSourceView_MissingPagingSetti"...
0xcde63  ldc.i4.1
0xcde64  newarr   [mscorlib]System.Object
0xcde69  dup
0xcde6a  ldc.i4.0
0xcde6b  ldarg.0
0xcde6c  ldfld    class System.Web.UI.WebControls.ObjectDataSource System.Web.UI.WebControls.ObjectDataSourceView::_owner
0xcde71  callvirt instance string System.Web.UI.Control::get_ID()
0xcde76  stelem.ref
0xcde77  call     string System.Web.SR::GetString(string name, object[] args)
0xcde7c  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xcde81  throw
0xcde82  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0xcde87  newobj   instance void [System]System.Collections.Specialized.OrderedDictionary::.ctor(class [mscorlib]System.Collections.IEqualityComparer)
0xcde8c  stloc.s  0x14
0xcde8e  ldloc.s  0x14
0xcde90  ldloc.s  0x12
0xcde92  ldarg.1
0xcde93  callvirt instance int32 System.Web.UI.DataSourceSelectArguments::get_MaximumRows()
0xcde98  box      [mscorlib]System.Int32
0xcde9d  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0xcdea2  ldloc.s  0x14
0xcdea4  ldloc.s  0x13
0xcdea6  ldarg.1
0xcdea7  callvirt instance int32 System.Web.UI.DataSourceSelectArguments::get_StartRowIndex()
0xcdeac  box      [mscorlib]System.Int32
0xcdeb1  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0xcdeb6  ldarg.0
0xcdeb7  call     instance class System.Web.UI.WebControls.ParameterCollection System.Web.UI.WebControls.ObjectDataSourceView::get_SelectParameters()
0xcdebc  ldloc.s  0x14
0xcdebe  ldloc.0
0xcdebf  call     void System.Web.UI.WebControls.ObjectDataSourceView::MergeDictionaries(class System.Web.UI.WebControls.ParameterCollection reference, class [mscorlib]System.Collections.IDictionary source, class [mscorlib]System.Collections.IDictionary destination)
0xcdec4  ldarg.0
0xcdec5  ldarg.0
0xcdec6  call     instance string System.Web.UI.WebControls.ObjectDataSourceView::get_TypeName()
0xcdecb  call     instance class [mscorlib]System.Type System.Web.UI.WebControls.ObjectDataSourceView::GetType(string typeName)
0xcded0  stloc.s  6
0xcded2  ldnull
0xcded3  stloc.s  7
0xcded5  ldnull
0xcded6  stloc.s  8
0xcded8  ldarg.0
0xcded9  ldloc.s  6
0xcdedb  ldarg.0
0xcdedc  call     instance string System.Web.UI.WebControls.ObjectDataSourceView::get_SelectMethod()
0xcdee1  ldloc.0
0xcdee2  ldc.i4.2
0xcdee3  call     instance valuetype ObjectDataSourceMethod System.Web.UI.WebControls.ObjectDataSourceView::GetResolvedMethodData(class [mscorlib]System.Type type, string methodName, class [mscorlib]System.Collections.IDictionary allParameters, valuetype System.Web.UI.DataSourceOperation operation)
0xcdee8  stloc.s  0x15
0xcdeea  ldarg.0
0xcdeeb  ldloc.s  0x15
0xcdeed  ldc.i4.0
0xcdeee  ldloca.s 7
0xcdef0  call     instance class ObjectDataSourceResult System.Web.UI.WebControls.ObjectDataSourceView::InvokeMethod(valuetype ObjectDataSourceMethod method, bool disposeInstance, object& instance)
0xcdef5  stloc.s  8
0xcdef7  ldloc.s  8
0xcdef9  ldfld    object ObjectDataSourceResult::ReturnValue
0xcdefe  brtrue.s loc_CDF08
0xcdf00  ldnull
0xcdf01  stloc.s  0x16
0xcdf03  leave    loc_CE0E7
0xcdf08  ldarg.1
0xcdf09  callvirt instance bool System.Web.UI.DataSourceSelectArguments::get_RetrieveTotalRowCount()
0xcdf0e  brfalse.s loc_CDF69
0xcdf10  ldarg.0
0xcdf11  call     instance string System.Web.UI.WebControls.ObjectDataSourceView::get_SelectCountMethod()
0xcdf16  callvirt instance int32 [mscorlib]System.String::get_Length()
  ... truncated ...
```
