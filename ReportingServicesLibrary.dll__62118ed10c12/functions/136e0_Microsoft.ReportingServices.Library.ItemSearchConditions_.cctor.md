# Microsoft.ReportingServices.Library.ItemSearchConditions::.cctor

- ea: `0x136e0`
- end: `0x1378f`
- name: `Microsoft.ReportingServices.Library.ItemSearchConditions::.cctor`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x14cb0`

## string_xrefs

- `0x13701`: `CreatedBy`
- `0x13729`: `ComponentID`

## pseudocode

```c

```

## disassembly

```asm
0x136e0  ldc.i4.s 9
0x136e2  newarr   [mscorlib]System.String
0x136e7  dup
0x136e8  ldc.i4.0
0x136e9  ldstr    aName// "Name"
0x136ee  stelem.ref
0x136ef  dup
0x136f0  ldc.i4.1
0x136f1  ldstr    aType_0// "Type"
0x136f6  stelem.ref
0x136f7  dup
0x136f8  ldc.i4.2
0x136f9  ldstr    aDescription_0// "Description"
0x136fe  stelem.ref
0x136ff  dup
0x13700  ldc.i4.3
0x13701  ldstr    aCreatedby// "CreatedBy"
0x13706  stelem.ref
0x13707  dup
0x13708  ldc.i4.4
0x13709  ldstr    aCreationdate_0// "CreationDate"
0x1370e  stelem.ref
0x1370f  dup
0x13710  ldc.i4.5
0x13711  ldstr    aModifiedby// "ModifiedBy"
0x13716  stelem.ref
0x13717  dup
0x13718  ldc.i4.6
0x13719  ldstr    aModifieddate_0// "ModifiedDate"
0x1371e  stelem.ref
0x1371f  dup
0x13720  ldc.i4.7
0x13721  ldstr    aSubtype_0// "Subtype"
0x13726  stelem.ref
0x13727  dup
0x13728  ldc.i4.8
0x13729  ldstr    aComponentid_0// "ComponentID"
0x1372e  stelem.ref
0x1372f  stsfld   string[] Microsoft.ReportingServices.Library.ItemSearchConditions::m_SearchablePropertyNames
0x13734  ldsfld   string[] Microsoft.ReportingServices.Library.ItemSearchConditions::m_SearchablePropertyNames
0x13739  call     class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.PropertyHashTable::Create(string[] strings)
0x1373e  stsfld   class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.ItemSearchConditions::SearchableProperties
0x13743  ldc.i4.2
0x13744  newarr   [mscorlib]System.String
0x13749  dup
0x1374a  ldc.i4.0
0x1374b  ldstr    aName// "Name"
0x13750  stelem.ref
0x13751  dup
0x13752  ldc.i4.1
0x13753  ldstr    aDescription_0// "Description"
0x13758  stelem.ref
0x13759  stsfld   string[] Microsoft.ReportingServices.Library.ItemSearchConditions::m_textPropertyNames
0x1375e  ldnull
0x1375f  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.ReportingServices.Library.ItemType> Microsoft.ReportingServices.Library.ItemSearchConditions::ItemTypeNames
0x13764  ldc.i4.2
0x13765  newarr   [mscorlib]System.String
0x1376a  dup
0x1376b  ldc.i4.0
0x1376c  ldstr    aCreationdate_0// "CreationDate"
0x13771  stelem.ref
0x13772  dup
0x13773  ldc.i4.1
0x13774  ldstr    aModifieddate_0// "ModifiedDate"
0x13779  stelem.ref
0x1377a  stsfld   string[] Microsoft.ReportingServices.Library.ItemSearchConditions::m_dateTimePropertyNames
0x1377f  ldsfld   string[] Microsoft.ReportingServices.Library.ItemSearchConditions::m_dateTimePropertyNames
0x13784  call     class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.PropertyHashTable::Create(string[] strings)
0x13789  stsfld   class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.ItemSearchConditions::DateTimeProperties
0x1378e  ret
```
