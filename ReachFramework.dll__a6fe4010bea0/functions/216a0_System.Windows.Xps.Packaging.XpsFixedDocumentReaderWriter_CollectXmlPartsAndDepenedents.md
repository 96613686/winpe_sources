# System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::CollectXmlPartsAndDepenedents

- ea: `0x216a0`
- end: `0x21729`
- name: `System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::CollectXmlPartsAndDepenedents`
- size: `137`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x20cb0`

## callees

- `0x216a0`
- `0x218d0`
- `0x21a40`
- `0x22800`
- `0x24570`
- `0x24c80`
- `0x25a70`
- `0x25aa0`

## pseudocode

```c

```

## disassembly

```asm
0x216a0  ldarg.1
0x216a1  ldarg.0
0x216a2  ldfld    class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_metroPart
0x216a7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [WindowsBase]System.IO.Packaging.PackagePart>::Add(var<u1>)
0x216ac  ldarg.0
0x216ad  call     instance void System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::UpdatePageCache()
0x216b2  ldarg.0
0x216b3  ldfld    class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Xps.Packaging.IXpsFixedPageReader> System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_pageCache
0x216b8  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class System.Windows.Xps.Packaging.IXpsFixedPageReader>::GetEnumerator()
0x216bd  stloc.1
0x216be  br.s     loc_216D4
0x216c0  ldloca.s 1
0x216c2  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Windows.Xps.Packaging.IXpsFixedPageReader>::get_Current()
0x216c7  stloc.2
0x216c8  ldloc.2
0x216c9  isinst   System.Windows.Xps.Packaging.XpsFixedPageReaderWriter
0x216ce  ldarg.1
0x216cf  callvirt instance void System.Windows.Xps.Packaging.XpsFixedPageReaderWriter::CollectXmlPartsAndDepenedents(class [mscorlib]System.Collections.Generic.List`1<class [WindowsBase]System.IO.Packaging.PackagePart> xmlPartList)
0x216d4  ldloca.s 1
0x216d6  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Windows.Xps.Packaging.IXpsFixedPageReader>::MoveNext()
0x216db  brtrue.s loc_216C0
0x216dd  leave.s  loc_216ED
0x216df  ldloca.s 1
0x216e1  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class System.Windows.Xps.Packaging.IXpsFixedPageReader>
0x216e7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x216ec  endfinally
0x216ed  ldarg.0
0x216ee  call     instance void System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::EnsureDoucmentStructure()
0x216f3  ldarg.0
0x216f4  ldfld    class System.Windows.Xps.Packaging.XpsStructure System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_documentStructure
0x216f9  brfalse.s loc_2170C
0x216fb  ldarg.1
0x216fc  ldarg.0
0x216fd  ldfld    class System.Windows.Xps.Packaging.XpsStructure System.Windows.Xps.Packaging.XpsFixedDocumentReaderWriter::_documentStructure
0x21702  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.INode::GetPart()
0x21707  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [WindowsBase]System.IO.Packaging.PackagePart>::Add(var<u1>)
0x2170c  ldarg.0
0x2170d  call     instance class System.Windows.Xps.Packaging.XpsManager System.Windows.Xps.Packaging.XpsPartBase::get_CurrentXpsManager()
0x21712  ldarg.0
0x21713  call     instance class [System]System.Uri System.Windows.Xps.Packaging.XpsPartBase::get_Uri()
0x21718  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Xps.Packaging.XpsManager::GetSignatureDefinitionPart(class [System]System.Uri documentUri)
0x2171d  stloc.0
0x2171e  ldloc.0
0x2171f  brfalse.s loc_21728
0x21721  ldarg.1
0x21722  ldloc.0
0x21723  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [WindowsBase]System.IO.Packaging.PackagePart>::Add(var<u1>)
0x21728  ret
```
