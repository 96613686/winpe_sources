# System.Deployment.Application.ShellExposure::MoveDeleteEmptyFolder

- ea: `0x1d880`
- end: `0x1d964`
- name: `System.Deployment.Application.ShellExposure::MoveDeleteEmptyFolder`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1d970`

## callees

- `0x17d40`
- `0x1d880`

## string_xrefs

- `0x1d8bf`: `Deleted successfully: `

## pseudocode

```c

```

## disassembly

```asm
0x1d880  ldarg.0
0x1d881  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x1d886  brtrue.s loc_1D889
0x1d888  ret
0x1d889  ldarg.0
0x1d88a  call     string[] [mscorlib]System.IO.Directory::GetFiles(string)
0x1d88f  stloc.0
0x1d890  ldloc.0
0x1d891  ldlen
0x1d892  brfalse.s loc_1D895
0x1d894  ret
0x1d895  ldarg.0
0x1d896  stloc.1
0x1d897  call     string [mscorlib]System.IO.Path::GetTempPath()
0x1d89c  call     string [mscorlib]System.IO.Path::GetRandomFileName()
0x1d8a1  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1d8a6  stloc.2
0x1d8a7  ldarg.0
0x1d8a8  ldloc.2
0x1d8a9  call     void [mscorlib]System.IO.Directory::Move(string, string)
0x1d8ae  ldloc.2
0x1d8af  stloc.1
0x1d8b0  leave.s  loc_1D8B8
0x1d8b2  pop
0x1d8b3  leave.s  loc_1D8B8
0x1d8b5  pop
0x1d8b6  leave.s  loc_1D8B8
0x1d8b8  nop
0x1d8b9  ldloc.1
0x1d8ba  call     void [mscorlib]System.IO.Directory::Delete(string)
0x1d8bf  ldstr    aDeletedSuccess// "Deleted successfully: "
0x1d8c4  ldloc.1
0x1d8c5  call     string [mscorlib]System.String::Concat(string, string)
0x1d8ca  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1d8cf  leave    loc_1D963
0x1d8d4  stloc.3
0x1d8d5  ldc.i4.6
0x1d8d6  newarr   [mscorlib]System.String
0x1d8db  dup
0x1d8dc  ldc.i4.0
0x1d8dd  ldstr    aExceptionThrow_14// "Exception thrown deleting "
0x1d8e2  stelem.ref
0x1d8e3  dup
0x1d8e4  ldc.i4.1
0x1d8e5  ldloc.1
0x1d8e6  stelem.ref
0x1d8e7  dup
0x1d8e8  ldc.i4.2
0x1d8e9  ldstr    asc_32300// ":"
0x1d8ee  stelem.ref
0x1d8ef  dup
0x1d8f0  ldc.i4.3
0x1d8f1  ldloc.3
0x1d8f2  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x1d8f7  callvirt instance string [mscorlib]System.Object::ToString()
0x1d8fc  stelem.ref
0x1d8fd  dup
0x1d8fe  ldc.i4.4
0x1d8ff  ldstr    asc_32300// ":"
0x1d904  stelem.ref
0x1d905  dup
0x1d906  ldc.i4.5
0x1d907  ldloc.3
0x1d908  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1d90d  stelem.ref
0x1d90e  call     string [mscorlib]System.String::Concat(string[])
0x1d913  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1d918  leave.s  loc_1D963
0x1d91a  stloc.s  4
0x1d91c  ldc.i4.6
0x1d91d  newarr   [mscorlib]System.String
0x1d922  dup
0x1d923  ldc.i4.0
0x1d924  ldstr    aExceptionThrow_14// "Exception thrown deleting "
0x1d929  stelem.ref
0x1d92a  dup
0x1d92b  ldc.i4.1
0x1d92c  ldloc.1
0x1d92d  stelem.ref
0x1d92e  dup
0x1d92f  ldc.i4.2
0x1d930  ldstr    asc_32300// ":"
0x1d935  stelem.ref
0x1d936  dup
0x1d937  ldc.i4.3
0x1d938  ldloc.s  4
0x1d93a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x1d93f  callvirt instance string [mscorlib]System.Object::ToString()
0x1d944  stelem.ref
0x1d945  dup
0x1d946  ldc.i4.4
0x1d947  ldstr    asc_32300// ":"
0x1d94c  stelem.ref
0x1d94d  dup
0x1d94e  ldc.i4.5
0x1d94f  ldloc.s  4
0x1d951  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1d956  stelem.ref
0x1d957  call     string [mscorlib]System.String::Concat(string[])
0x1d95c  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1d961  leave.s  loc_1D963
0x1d963  ret
```
