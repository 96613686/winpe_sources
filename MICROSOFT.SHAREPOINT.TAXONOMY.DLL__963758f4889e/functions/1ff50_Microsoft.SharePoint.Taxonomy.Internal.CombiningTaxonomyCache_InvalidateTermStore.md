# Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::InvalidateTermStore

- ea: `0x1ff50`
- end: `0x20128`
- name: `Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::InvalidateTermStore`
- size: `472`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1fd00`

## callees

- `0x1ec60`
- `0x1ec70`
- `0x1ed10`
- `0x1ff50`
- `0x38f60`
- `0x38fb0`
- `0x39d60`
- `0x39d70`

## string_xrefs

- `0x1ff77`: `Flushing entire TaxonomyCache due to all-partition TermStore Edit event`
- `0x1ff94`: `TaxonomyCache ignoring all-partition {0} event`
- `0x1ffca`: `Flushing all TaxonomyCache objects for partition {0} due to TermStore Delete event`
- `0x2000c`: `Flushing all TaxonomyCache objects for partition {0} due to TermStore Import event`
- `0x2004e`: `Flushing all TaxonomyCache objects for partition {0} due to TermStore Move event`
- `0x200ad`: `Flushing all TaxonomyCache objects for partition {0} due to TermStore language change`

## pseudocode

```c

```

## disassembly

```asm
0x1ff50  ldarg.1
0x1ff51  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ChangedItem::get_PartitionId()
0x1ff56  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.CommonUtilities::AllPartitionsId
0x1ff5b  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1ff60  brfalse.s loc_1FFB5
0x1ff62  ldarg.1
0x1ff63  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.ChangedOperationType Microsoft.SharePoint.Taxonomy.ChangedItem::get_Operation()
0x1ff68  ldc.i4.2
0x1ff69  bne.un.s loc_1FF88
0x1ff6b  ldc.i4   0x706653
0x1ff70  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1ff75  ldc.i4.s 0xF
0x1ff77  ldstr    aFlushingEntire// "Flushing entire TaxonomyCache due to al"...
0x1ff7c  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x1ff81  ldarg.0
0x1ff82  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache::Flush()
0x1ff87  ret
0x1ff88  ldc.i4   0x79E889
0x1ff8d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1ff92  ldc.i4.s 0xF
0x1ff94  ldstr    aTaxonomycacheI// "TaxonomyCache ignoring all-partition {0"...
0x1ff99  ldc.i4.1
0x1ff9a  newarr   [mscorlib]System.Object
0x1ff9f  stloc.1
0x1ffa0  ldloc.1
0x1ffa1  ldc.i4.0
0x1ffa2  ldarg.1
0x1ffa3  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.ChangedOperationType Microsoft.SharePoint.Taxonomy.ChangedItem::get_Operation()
0x1ffa8  box      Microsoft.SharePoint.Taxonomy.ChangedOperationType
0x1ffad  stelem.ref
0x1ffae  ldloc.1
0x1ffaf  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1ffb4  ret
0x1ffb5  ldarg.1
0x1ffb6  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.ChangedOperationType Microsoft.SharePoint.Taxonomy.ChangedItem::get_Operation()
0x1ffbb  ldc.i4.3
0x1ffbc  bne.un.s loc_1FFF7
0x1ffbe  ldc.i4   0x79E88A
0x1ffc3  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1ffc8  ldc.i4.s 0x32
0x1ffca  ldstr    aFlushingAllTax// "Flushing all TaxonomyCache objects for "...
0x1ffcf  ldc.i4.1
0x1ffd0  newarr   [mscorlib]System.Object
0x1ffd5  stloc.2
0x1ffd6  ldloc.2
0x1ffd7  ldc.i4.0
0x1ffd8  ldarg.1
0x1ffd9  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ChangedItem::get_PartitionId()
0x1ffde  box      [mscorlib]System.Guid
0x1ffe3  stelem.ref
0x1ffe4  ldloc.2
0x1ffe5  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1ffea  ldarg.0
0x1ffeb  ldarg.1
0x1ffec  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ChangedItem::get_PartitionId()
0x1fff1  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache::Flush(valuetype [mscorlib]System.Guid partitionId)
0x1fff6  ret
0x1fff7  ldarg.1
0x1fff8  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.ChangedOperationType Microsoft.SharePoint.Taxonomy.ChangedItem::get_Operation()
0x1fffd  ldc.i4.8
0x1fffe  bne.un.s loc_20039
0x20000  ldc.i4   0x79E88B
0x20005  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2000a  ldc.i4.s 0x32
0x2000c  ldstr    aFlushingAllTax_0// "Flushing all TaxonomyCache objects for "...
0x20011  ldc.i4.1
0x20012  newarr   [mscorlib]System.Object
0x20017  stloc.3
0x20018  ldloc.3
0x20019  ldc.i4.0
0x2001a  ldarg.1
0x2001b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ChangedItem::get_PartitionId()
0x20020  box      [mscorlib]System.Guid
0x20025  stelem.ref
0x20026  ldloc.3
0x20027  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x2002c  ldarg.0
0x2002d  ldarg.1
0x2002e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ChangedItem::get_PartitionId()
0x20033  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache::Flush(valuetype [mscorlib]System.Guid partitionId)
0x20038  ret
0x20039  ldarg.1
0x2003a  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.ChangedOperationType Microsoft.SharePoint.Taxonomy.ChangedItem::get_Operation()
0x2003f  ldc.i4.4
0x20040  bne.un.s loc_2007E
0x20042  ldc.i4   0x79E88C
0x20047  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2004c  ldc.i4.s 0x32
0x2004e  ldstr    aFlushingAllTax_1// "Flushing all TaxonomyCache objects for "...
0x20053  ldc.i4.1
0x20054  newarr   [mscorlib]System.Object
0x20059  stloc.s  4
0x2005b  ldloc.s  4
0x2005d  ldc.i4.0
0x2005e  ldarg.1
0x2005f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ChangedItem::get_PartitionId()
0x20064  box      [mscorlib]System.Guid
0x20069  stelem.ref
0x2006a  ldloc.s  4
0x2006c  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x20071  ldarg.0
0x20072  ldarg.1
0x20073  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ChangedItem::get_PartitionId()
0x20078  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache::Flush(valuetype [mscorlib]System.Guid partitionId)
0x2007d  ret
0x2007e  ldarg.1
0x2007f  isinst   Microsoft.SharePoint.Taxonomy.ChangedTermStore
0x20084  stloc.0
0x20085  ldloc.0
0x20086  brfalse.s loc_200DD
0x20088  ldloc.0
0x20089  callvirt instance bool Microsoft.SharePoint.Taxonomy.ChangedTermStore::get_IsDefaultLanguageChanged()
0x2008e  brtrue.s loc_200A1
0x20090  ldarg.1
0x20091  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.ChangedOperationType Microsoft.SharePoint.Taxonomy.ChangedItem::get_Operation()
0x20096  ldc.i4.1
0x20097  bne.un.s loc_200DD
0x20099  ldloc.0
0x2009a  callvirt instance int32 Microsoft.SharePoint.Taxonomy.ChangedTermStore::get_ChangedLanguage()
0x2009f  brfalse.s loc_200DD
0x200a1  ldc.i4   0x79E88D
0x200a6  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x200ab  ldc.i4.s 0x32
0x200ad  ldstr    aFlushingAllTax_2// "Flushing all TaxonomyCache objects for "...
0x200b2  ldc.i4.1
0x200b3  newarr   [mscorlib]System.Object
0x200b8  stloc.s  5
0x200ba  ldloc.s  5
0x200bc  ldc.i4.0
0x200bd  ldarg.1
0x200be  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ChangedItem::get_PartitionId()
0x200c3  box      [mscorlib]System.Guid
0x200c8  stelem.ref
0x200c9  ldloc.s  5
0x200cb  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x200d0  ldarg.0
0x200d1  ldarg.1
0x200d2  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ChangedItem::get_PartitionId()
0x200d7  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache::Flush(valuetype [mscorlib]System.Guid partitionId)
0x200dc  ret
0x200dd  ldc.i4   0x79E88E
0x200e2  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x200e7  ldc.i4.s 0x32
0x200e9  ldstr    aFlushingTheTer// "Flushing the TermStore object for parti"...
0x200ee  ldc.i4.2
0x200ef  newarr   [mscorlib]System.Object
0x200f4  stloc.s  6
0x200f6  ldloc.s  6
0x200f8  ldc.i4.0
0x200f9  ldarg.1
0x200fa  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ChangedItem::get_PartitionId()
0x200ff  box      [mscorlib]System.Guid
0x20104  stelem.ref
0x20105  ldloc.s  6
0x20107  ldc.i4.1
0x20108  ldarg.1
0x20109  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.ChangedOperationType Microsoft.SharePoint.Taxonomy.ChangedItem::get_Operation()
0x2010e  box      Microsoft.SharePoint.Taxonomy.ChangedOperationType
0x20113  stelem.ref
0x20114  ldloc.s  6
0x20116  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x2011b  ldarg.0
0x2011c  ldarg.1
0x2011d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.ChangedItem::get_PartitionId()
0x20122  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache::FlushTermStoreData(valuetype [mscorlib]System.Guid partitionId)
0x20127  ret
```
