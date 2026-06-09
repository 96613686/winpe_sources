# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::CreateNewSyndicationItem

- ea: `0x32a0`
- end: `0x336e`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::CreateNewSyndicationItem`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x3370`

## callees

- `0x32a0`
- `0x3cb0`
- `0x3d70`

## pseudocode

```c

```

## disassembly

```asm
0x32a0  ldarg.0
0x32a1  ldc.i4.0
0x32a2  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnCount
0x32a7  ldarg.0
0x32a8  newobj   instance void [System.ServiceModel]System.ServiceModel.Syndication.SyndicationItem::.ctor()
0x32ad  stfld    class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationItem Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_syndicationItem
0x32b2  ldarg.0
0x32b3  ldfld    class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationItem Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_syndicationItem
0x32b8  ldsfld   string [mscorlib]System.String::Empty
0x32bd  newobj   instance void [System.ServiceModel]System.ServiceModel.Syndication.TextSyndicationContent::.ctor(string)
0x32c2  callvirt instance void [System.ServiceModel]System.ServiceModel.Syndication.SyndicationItem::set_Title(class [System.ServiceModel]System.ServiceModel.Syndication.TextSyndicationContent)
0x32c7  ldarg.0
0x32c8  ldfld    class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationItem Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_syndicationItem
0x32cd  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationPerson> [System.ServiceModel]System.ServiceModel.Syndication.SyndicationItem::get_Authors()
0x32d2  newobj   instance void [System.ServiceModel]System.ServiceModel.Syndication.SyndicationPerson::.ctor()
0x32d7  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationPerson>::Add(var<u1>)
0x32dc  ldarg.0
0x32dd  ldarg.0
0x32de  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_selectedColumns
0x32e3  newobj   instance void Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::.ctor(class [mscorlib]System.Collections.Hashtable selectedColumns)
0x32e8  stfld    class Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_rowContent
0x32ed  ldarg.0
0x32ee  ldfld    class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationItem Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_syndicationItem
0x32f3  ldarg.0
0x32f4  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_rowContent
0x32f9  callvirt instance void [System.ServiceModel]System.ServiceModel.Syndication.SyndicationItem::set_Content(class [System.ServiceModel]System.ServiceModel.Syndication.SyndicationContent)
0x32fe  ldarg.0
0x32ff  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TypedColumnValue> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_feedLevelRowContent
0x3304  brfalse.s loc_336D
0x3306  ldarg.0
0x3307  ldfld    class [mscorlib]System.Collections.Generic.List`1<class TypedColumnValue> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_feedLevelRowContent
0x330c  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class TypedColumnValue>::GetEnumerator()
0x3311  stloc.0
0x3312  br.s     loc_3354
0x3314  ldloca.s 0
0x3316  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class TypedColumnValue>::get_Current()
0x331b  stloc.1
0x331c  ldarg.0
0x331d  ldarg.0
0x331e  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnCount
0x3323  ldc.i4.1
0x3324  add
0x3325  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnCount
0x332a  ldarg.0
0x332b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnNames
0x3330  ldarg.0
0x3331  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnCount
0x3336  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::get_Item(void)
0x333b  stloc.2
0x333c  ldarg.0
0x333d  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_rowContent
0x3342  ldloc.2
0x3343  ldloc.1
0x3344  ldfld    string TypedColumnValue::EdmType
0x3349  ldloc.1
0x334a  ldfld    string TypedColumnValue::Value
0x334f  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.DictionaryContent::Add(string columnName, string edmType, string value)
0x3354  ldloca.s 0
0x3356  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class TypedColumnValue>::MoveNext()
0x335b  brtrue.s loc_3314
0x335d  leave.s  loc_336D
0x335f  ldloca.s 0
0x3361  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class TypedColumnValue>
0x3367  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x336c  endfinally
0x336d  ret
```
