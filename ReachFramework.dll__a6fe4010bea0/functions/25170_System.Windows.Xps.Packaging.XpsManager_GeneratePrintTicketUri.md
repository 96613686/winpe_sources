# System.Windows.Xps.Packaging.XpsManager::GeneratePrintTicketUri

- ea: `0x25170`
- end: `0x25236`
- name: `System.Windows.Xps.Packaging.XpsManager::GeneratePrintTicketUri`
- size: `198`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x24ac0`
- `0x24b60`

## callees

- `0x21270`
- `0x220d0`
- `0x23100`
- `0x25170`

## string_xrefs

- `0x2518c`: `/MetaData/Job_PT.xml`
- `0x251b9`: `/Document_PT.xml`
- `0x2521d`: `_PT.xml`

## pseudocode

```c

```

## disassembly

```asm
0x25170  ldarg.1
0x25171  brtrue.s loc_2517E
0x25173  ldstr    aRelatedpart// "relatedPart"
0x25178  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2517d  throw
0x2517e  ldstr    asc_41B18// ""
0x25183  stloc.0
0x25184  ldarg.1
0x25185  isinst   System.Windows.Xps.Packaging.XpsFixedDocumentSequenceReaderWriter
0x2518a  brfalse.s loc_25197
0x2518c  ldstr    aMetadataJobPtX// "/MetaData/Job_PT.xml"
0x25191  stloc.0
0x25192  br       loc_25229
0x25197  ldarg.1
0x25198  isinst   System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter
0x2519d  brfalse.s loc_251C6
0x2519f  ldarg.1
0x251a0  isinst   System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter
0x251a5  stloc.1
0x251a6  ldstr    aDocuments// "/Documents/"
0x251ab  ldloc.1
0x251ac  callvirt instance int32 System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::get_DocumentNumber()
0x251b1  stloc.2
0x251b2  ldloca.s 2
0x251b4  call     instance string [mscorlib]System.Int32::ToString()
0x251b9  ldstr    aDocumentPtXml// "/Document_PT.xml"
0x251be  call     string [mscorlib]System.String::Concat(string, string, string)
0x251c3  stloc.0
0x251c4  br.s     loc_25229
0x251c6  ldarg.1
0x251c7  isinst   System.Windows.Xps.Packaging.XpsFixedPageReaderWriter
0x251cc  brfalse.s loc_25229
0x251ce  ldarg.1
0x251cf  isinst   System.Windows.Xps.Packaging.XpsFixedPageReaderWriter
0x251d4  stloc.3
0x251d5  ldarg.1
0x251d6  isinst   System.Windows.Xps.Packaging.XpsFixedPageReaderWriter
0x251db  callvirt instance class System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::get_Parent()
0x251e0  stloc.s  4
0x251e2  ldc.i4.5
0x251e3  newarr   [mscorlib]System.String
0x251e8  dup
0x251e9  ldc.i4.0
0x251ea  ldstr    aDocuments// "/Documents/"
0x251ef  stelem.ref
0x251f0  dup
0x251f1  ldc.i4.1
0x251f2  ldloc.s  4
0x251f4  callvirt instance int32 System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::get_DocumentNumber()
0x251f9  stloc.2
0x251fa  ldloca.s 2
0x251fc  call     instance string [mscorlib]System.Int32::ToString()
0x25201  stelem.ref
0x25202  dup
0x25203  ldc.i4.2
0x25204  ldstr    aPage// "/Page"
0x25209  stelem.ref
0x2520a  dup
0x2520b  ldc.i4.3
0x2520c  ldloc.3
0x2520d  callvirt instance int32 System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::get_PageNumber()
0x25212  stloc.2
0x25213  ldloca.s 2
0x25215  call     instance string [mscorlib]System.Int32::ToString()
0x2521a  stelem.ref
0x2521b  dup
0x2521c  ldc.i4.4
0x2521d  ldstr    aPtXml// "_PT.xml"
0x25222  stelem.ref
0x25223  call     string [mscorlib]System.String::Concat(string[])
0x25228  stloc.0
0x25229  ldloc.0
0x2522a  ldc.i4.2
0x2522b  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x25230  call     class [System]System.Uri [WindowsBase]System.IO.Packaging.PackUriHelper::CreatePartUri(class [System]System.Uri)
0x25235  ret
```
