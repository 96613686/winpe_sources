# System.Net.Http.Handlers.ProgressWriteAsyncResult::WriteCompletedCallback

- ea: `0x4960`
- end: `0x498a`
- name: `System.Net.Http.Handlers.ProgressWriteAsyncResult::WriteCompletedCallback`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x4960`
- `0x4990`
- `0x5160`

## pseudocode

```c

```

## disassembly

```asm
0x4960  ldarg.0
0x4961  callvirt instance bool [mscorlib]System.IAsyncResult::get_CompletedSynchronously()
0x4966  brfalse.s loc_4969
0x4968  ret
0x4969  ldarg.0
0x496a  callvirt instance object [mscorlib]System.IAsyncResult::get_AsyncState()
0x496f  castclass System.Net.Http.Handlers.ProgressWriteAsyncResult
0x4974  stloc.0
0x4975  ldloc.0
0x4976  ldarg.0
0x4977  callvirt instance void System.Net.Http.Handlers.ProgressWriteAsyncResult::WriteCompleted(class [mscorlib]System.IAsyncResult result)
0x497c  leave.s  loc_4989
0x497e  stloc.1
0x497f  ldloc.0
0x4980  ldc.i4.0
0x4981  ldloc.1
0x4982  callvirt instance void System.Net.Http.Internal.AsyncResult::Complete(bool completedSynchronously, class [mscorlib]System.Exception exception)
0x4987  leave.s  loc_4989
0x4989  ret
```
