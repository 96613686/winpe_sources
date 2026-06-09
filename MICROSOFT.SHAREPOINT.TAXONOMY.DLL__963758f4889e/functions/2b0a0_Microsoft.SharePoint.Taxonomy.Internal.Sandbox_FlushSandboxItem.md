# Microsoft.SharePoint.Taxonomy.Internal.Sandbox::FlushSandboxItem

- ea: `0x2b0a0`
- end: `0x2b1bb`
- name: `Microsoft.SharePoint.Taxonomy.Internal.Sandbox::FlushSandboxItem`
- size: `283`
- prototype: ``
- caller_count: `16`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x48cb0`
- `0x48d90`
- `0x48ee0`
- `0x4d000`
- `0x4d7e0`
- `0x4e0d0`
- `0x4e9a0`
- `0x4f950`
- `0x4fe30`
- `0x4ff50`
- `0x50d60`
- `0x50e90`
- `0x51c20`
- `0x51d30`
- `0x53460`
- `0x53fc0`

## callees

- `0x2b0a0`
- `0x2bbb0`
- `0x2bc10`
- `0x2bc20`
- `0x2bc40`
- `0x2bca0`
- `0x2ebf0`

## string_xrefs

- `0x2b0c5`: `Flushing add, copy, and/or move operations for sandbox item.  ID: '{0}' OperationType: '{1}'`
- `0x2b1a1`: `Skipped flushing sandbox item because not an Add/Copy/Move operation.  ID: '{0}'`

## pseudocode

```c

```

## disassembly

```asm
0x2b0a0  ldarg.1
0x2b0a1  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedItem Microsoft.SharePoint.Taxonomy.Internal.SandboxItem::get_SharedItem()
0x2b0a6  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.SharedItem::get_Id()
0x2b0ab  stloc.2
0x2b0ac  ldloca.s 2
0x2b0ae  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2b0b3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2b0b8  stloc.0
0x2b0b9  ldc.i4   0x3265746A
0x2b0be  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2b0c3  ldc.i4.s 0x64
0x2b0c5  ldstr    aFlushingAddCop// "Flushing add, copy, and/or move operati"...
0x2b0ca  ldc.i4.2
0x2b0cb  newarr   [mscorlib]System.Object
0x2b0d0  stloc.3
0x2b0d1  ldloc.3
0x2b0d2  ldc.i4.0
0x2b0d3  ldloc.0
0x2b0d4  callvirt instance string [mscorlib]System.Object::ToString()
0x2b0d9  stelem.ref
0x2b0da  ldloc.3
0x2b0db  ldc.i4.1
0x2b0dc  ldarg.1
0x2b0dd  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Internal.SandboxOperationType Microsoft.SharePoint.Taxonomy.Internal.SandboxItem::get_OperationType()
0x2b0e2  box      Microsoft.SharePoint.Taxonomy.Internal.SandboxOperationType
0x2b0e7  callvirt instance string [mscorlib]System.Object::ToString()
0x2b0ec  stelem.ref
0x2b0ed  ldloc.3
0x2b0ee  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x2b0f3  ldarg.1
0x2b0f4  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Internal.SandboxOperationType Microsoft.SharePoint.Taxonomy.Internal.SandboxItem::get_OperationType()
0x2b0f9  ldc.i4.1
0x2b0fa  and
0x2b0fb  ldc.i4.1
0x2b0fc  beq.s    loc_2B139
0x2b0fe  ldarg.1
0x2b0ff  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Internal.SandboxOperationType Microsoft.SharePoint.Taxonomy.Internal.SandboxItem::get_OperationType()
0x2b104  ldc.i4.s 0x10
0x2b106  and
0x2b107  ldc.i4.s 0x10
0x2b109  beq.s    loc_2B139
0x2b10b  ldarg.1
0x2b10c  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Internal.SandboxOperationType Microsoft.SharePoint.Taxonomy.Internal.SandboxItem::get_OperationType()
0x2b111  ldc.i4.2
0x2b112  and
0x2b113  ldc.i4.2
0x2b114  beq.s    loc_2B139
0x2b116  ldarg.1
0x2b117  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Internal.SandboxOperationType Microsoft.SharePoint.Taxonomy.Internal.SandboxItem::get_OperationType()
0x2b11c  ldc.i4.8
0x2b11d  and
0x2b11e  ldc.i4.8
0x2b11f  beq.s    loc_2B139
0x2b121  ldarg.1
0x2b122  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Internal.SandboxOperationType Microsoft.SharePoint.Taxonomy.Internal.SandboxItem::get_OperationType()
0x2b127  ldc.i4.s 0x40
0x2b129  and
0x2b12a  ldc.i4.s 0x40
0x2b12c  beq.s    loc_2B139
0x2b12e  ldarg.1
0x2b12f  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Internal.SandboxOperationType Microsoft.SharePoint.Taxonomy.Internal.SandboxItem::get_OperationType()
0x2b134  ldc.i4.4
0x2b135  and
0x2b136  ldc.i4.4
0x2b137  bne.un.s loc_2B195
0x2b139  ldarg.1
0x2b13a  ldarg.0
0x2b13b  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Internal.Sandbox::termStore
0x2b140  ldarg.0
0x2b141  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.SharePoint.Taxonomy.Internal.Sandbox::xmlWriter
0x2b146  call     void Microsoft.SharePoint.Taxonomy.Internal.SandboxXmlGenerator::GetXml(class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem item, class Microsoft.SharePoint.Taxonomy.TermStore termStore, class [System.Xml]System.Xml.XmlWriter writer)
0x2b14b  ldarg.0
0x2b14c  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.SharePoint.Taxonomy.Internal.Sandbox::xmlWriter
0x2b151  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x2b156  ldarg.1
0x2b157  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SandboxItem::RefreshOriginalSharedItem()
0x2b15c  ldc.i4.s 0x5F
0x2b15e  stloc.1
0x2b15f  ldarg.1
0x2b160  dup
0x2b161  callvirt instance valuetype Microsoft.SharePoint.Taxonomy.Internal.SandboxOperationType Microsoft.SharePoint.Taxonomy.Internal.SandboxItem::get_OperationType()
0x2b166  ldc.i4.m1
0x2b167  ldloc.1
0x2b168  xor
0x2b169  and
0x2b16a  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SandboxItem::set_OperationType(valuetype Microsoft.SharePoint.Taxonomy.Internal.SandboxOperationType value)
0x2b16f  ldc.i4   0x3265746B
0x2b174  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2b179  ldc.i4.s 0x64
0x2b17b  ldstr    aFlushedSandbox// "Flushed sandbox item.  ID: '{0}'"
0x2b180  ldc.i4.1
0x2b181  newarr   [mscorlib]System.Object
0x2b186  stloc.s  4
0x2b188  ldloc.s  4
0x2b18a  ldc.i4.0
0x2b18b  ldloc.0
0x2b18c  stelem.ref
0x2b18d  ldloc.s  4
0x2b18f  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x2b194  ret
0x2b195  ldc.i4   0x3265746C
0x2b19a  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2b19f  ldc.i4.s 0x64
0x2b1a1  ldstr    aSkippedFlushin// "Skipped flushing sandbox item because n"...
0x2b1a6  ldc.i4.1
0x2b1a7  newarr   [mscorlib]System.Object
0x2b1ac  stloc.s  5
0x2b1ae  ldloc.s  5
0x2b1b0  ldc.i4.0
0x2b1b1  ldloc.0
0x2b1b2  stelem.ref
0x2b1b3  ldloc.s  5
0x2b1b5  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x2b1ba  ret
```
