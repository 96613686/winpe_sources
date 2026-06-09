# System.Windows.DataObject::SetFileDropList

- ea: `0x19590`
- end: `0x19636`
- name: `System.Windows.DataObject::SetFileDropList`
- size: `166`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x193e0`
- `0x19590`
- `0x146e70`

## string_xrefs

- `0x195dd`: `DataObject_FileDropListHasInvalidFileDropPath`

## pseudocode

```c

```

## disassembly

```asm
0x19590  ldarg.1
0x19591  brtrue.s loc_1959E
0x19593  ldstr    aFiledroplist// "fileDropList"
0x19598  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1959d  throw
0x1959e  ldarg.1
0x1959f  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::get_Count()
0x195a4  brtrue.s loc_195C0
0x195a6  ldstr    aDataobjectFile// "DataObject_FileDropListIsEmpty"
0x195ab  ldc.i4.1
0x195ac  newarr   [mscorlib]System.Object
0x195b1  dup
0x195b2  ldc.i4.0
0x195b3  ldarg.1
0x195b4  stelem.ref
0x195b5  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x195ba  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x195bf  throw
0x195c0  ldarg.1
0x195c1  callvirt instance class [System]System.Collections.Specialized.StringEnumerator [System]System.Collections.Specialized.StringCollection::GetEnumerator()
0x195c6  stloc.0
0x195c7  br.s     loc_195F9
0x195c9  ldloc.0
0x195ca  callvirt instance string [System]System.Collections.Specialized.StringEnumerator::get_Current()
0x195cf  stloc.s  4
0x195d1  ldloc.s  4
0x195d3  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x195d8  stloc.s  5
0x195da  leave.s  loc_195F9
0x195dc  stloc.3
0x195dd  ldstr    aDataobjectFile_0// "DataObject_FileDropListHasInvalidFileDr"...
0x195e2  ldc.i4.1
0x195e3  newarr   [mscorlib]System.Object
0x195e8  dup
0x195e9  ldc.i4.0
0x195ea  ldloc.3
0x195eb  stelem.ref
0x195ec  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x195f1  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x195f6  throw
0x195f7  leave.s  loc_195F9
0x195f9  ldloc.0
0x195fa  callvirt instance bool [System]System.Collections.Specialized.StringEnumerator::MoveNext()
0x195ff  brtrue.s loc_195C9
0x19601  leave.s  loc_19614
0x19603  ldloc.0
0x19604  isinst   [mscorlib]System.IDisposable
0x19609  stloc.2
0x1960a  ldloc.2
0x1960b  brfalse.s loc_19613
0x1960d  ldloc.2
0x1960e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19613  endfinally
0x19614  ldarg.1
0x19615  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::get_Count()
0x1961a  newarr   [mscorlib]System.String
0x1961f  stloc.1
0x19620  ldarg.1
0x19621  ldloc.1
0x19622  ldc.i4.0
0x19623  callvirt instance void [System]System.Collections.Specialized.StringCollection::CopyTo(string[], int32)
0x19628  ldarg.0
0x19629  ldsfld   string System.Windows.DataFormats::FileDrop
0x1962e  ldloc.1
0x1962f  ldc.i4.1
0x19630  call     instance void System.Windows.DataObject::SetData(string format, object data, bool autoConvert)
0x19635  ret
```
