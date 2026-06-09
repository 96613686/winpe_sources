# System.Net.Http.Handlers.ProgressWriteAsyncResult::.ctor

- ea: `0x4910`
- end: `0x495f`
- name: `System.Net.Http.Handlers.ProgressWriteAsyncResult::.ctor`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x4770`

## callees

- `0x4910`
- `0x4990`
- `0x5090`
- `0x5160`

## pseudocode

```c

```

## disassembly

```asm
0x4910  ldarg.0
0x4911  ldarg.s  6
0x4913  ldarg.s  7
0x4915  call     instance void System.Net.Http.Internal.AsyncResult::.ctor(class [mscorlib]System.AsyncCallback callback, object state)
0x491a  ldarg.0
0x491b  ldarg.1
0x491c  stfld    class [mscorlib]System.IO.Stream System.Net.Http.Handlers.ProgressWriteAsyncResult::_innerStream
0x4921  ldarg.0
0x4922  ldarg.2
0x4923  stfld    class System.Net.Http.Handlers.ProgressStream System.Net.Http.Handlers.ProgressWriteAsyncResult::_progressStream
0x4928  ldarg.0
0x4929  ldarg.s  5
0x492b  stfld    int32 System.Net.Http.Handlers.ProgressWriteAsyncResult::_count
0x4930  ldarg.1
0x4931  ldarg.3
0x4932  ldarg.s  4
0x4934  ldarg.s  5
0x4936  ldsfld   class [mscorlib]System.AsyncCallback System.Net.Http.Handlers.ProgressWriteAsyncResult::_writeCompletedCallback
0x493b  ldarg.0
0x493c  callvirt instance class [mscorlib]System.IAsyncResult [mscorlib]System.IO.Stream::BeginWrite(unsigned int8[], int32, int32, class [mscorlib]System.AsyncCallback, object)
0x4941  stloc.0
0x4942  ldloc.0
0x4943  callvirt instance bool [mscorlib]System.IAsyncResult::get_CompletedSynchronously()
0x4948  brfalse.s loc_4951
0x494a  ldarg.0
0x494b  ldloc.0
0x494c  call     instance void System.Net.Http.Handlers.ProgressWriteAsyncResult::WriteCompleted(class [mscorlib]System.IAsyncResult result)
0x4951  leave.s  loc_495E
0x4953  stloc.1
0x4954  ldarg.0
0x4955  ldc.i4.1
0x4956  ldloc.1
0x4957  call     instance void System.Net.Http.Internal.AsyncResult::Complete(bool completedSynchronously, class [mscorlib]System.Exception exception)
0x495c  leave.s  loc_495E
0x495e  ret
```
