# System.Windows.Clipboard::SetFileDropList

- ea: `0x15650`
- end: `0x156f2`
- name: `System.Windows.Clipboard::SetFileDropList`
- size: `162`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x15650`
- `0x15b10`
- `0x146e70`

## string_xrefs

- `0x1569b`: `DataObject_FileDropListHasInvalidFileDropPath`

## pseudocode

```c

```

## disassembly

```asm
0x15650  ldarg.0
0x15651  brtrue.s loc_1565E
0x15653  ldstr    aFiledroplist// "fileDropList"
0x15658  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1565d  throw
0x1565e  ldarg.0
0x1565f  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::get_Count()
0x15664  brtrue.s loc_15680
0x15666  ldstr    aDataobjectFile// "DataObject_FileDropListIsEmpty"
0x1566b  ldc.i4.1
0x1566c  newarr   [mscorlib]System.Object
0x15671  dup
0x15672  ldc.i4.0
0x15673  ldarg.0
0x15674  stelem.ref
0x15675  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x1567a  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x1567f  throw
0x15680  ldarg.0
0x15681  callvirt instance class [System]System.Collections.Specialized.StringEnumerator [System]System.Collections.Specialized.StringCollection::GetEnumerator()
0x15686  stloc.0
0x15687  br.s     loc_156B7
0x15689  ldloc.0
0x1568a  callvirt instance string [System]System.Collections.Specialized.StringEnumerator::get_Current()
0x1568f  stloc.3
0x15690  ldloc.3
0x15691  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x15696  stloc.s  4
0x15698  leave.s  loc_156B7
0x1569a  pop
0x1569b  ldstr    aDataobjectFile_0// "DataObject_FileDropListHasInvalidFileDr"...
0x156a0  ldc.i4.1
0x156a1  newarr   [mscorlib]System.Object
0x156a6  dup
0x156a7  ldc.i4.0
0x156a8  ldarg.0
0x156a9  stelem.ref
0x156aa  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x156af  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x156b4  throw
0x156b5  leave.s  loc_156B7
0x156b7  ldloc.0
0x156b8  callvirt instance bool [System]System.Collections.Specialized.StringEnumerator::MoveNext()
0x156bd  brtrue.s loc_15689
0x156bf  leave.s  loc_156D2
0x156c1  ldloc.0
0x156c2  isinst   [mscorlib]System.IDisposable
0x156c7  stloc.2
0x156c8  ldloc.2
0x156c9  brfalse.s loc_156D1
0x156cb  ldloc.2
0x156cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x156d1  endfinally
0x156d2  ldarg.0
0x156d3  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::get_Count()
0x156d8  newarr   [mscorlib]System.String
0x156dd  stloc.1
0x156de  ldarg.0
0x156df  ldloc.1
0x156e0  ldc.i4.0
0x156e1  callvirt instance void [System]System.Collections.Specialized.StringCollection::CopyTo(string[], int32)
0x156e6  ldsfld   string System.Windows.DataFormats::FileDrop
0x156eb  ldloc.1
0x156ec  call     void System.Windows.Clipboard::SetDataInternal(string format, object data)
0x156f1  ret
```
