# System.Printing.PrintQueueStream::EndWrite

- ea: `0x18e30`
- end: `0x18e6e`
- name: `System.Printing.PrintQueueStream::EndWrite`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0xe540`
- `0x18e30`
- `0x19380`

## pseudocode

```c

```

## disassembly

```asm
0x18e30  ldarg.0
0x18e31  ldfld    class System.Printing.PrintQueue System.Printing.PrintQueueStream::printQueue
0x18e36  call     instance bool System.Printing.PrintQueue::get_PrintingIsCancelled()
0x18e3b  brfalse.s loc_18E4D
0x18e3d  ldc.i4   0x8007003F
0x18e42  ldstr    aPrintsystemexc_25// "PrintSystemException.PrintingCancelled."...
0x18e47  call     class [mscorlib]System.Exception System.Printing.PrintQueueStream::CreatePrintingCanceledException(int32 hresult, string messageId)
0x18e4c  throw
0x18e4d  ldarg.1
0x18e4e  brtrue.s loc_18E5B
0x18e50  ldstr    aAsyncresult// "asyncResult"
0x18e55  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x18e5a  throw
0x18e5b  ldarg.1
0x18e5c  callvirt instance class [mscorlib]System.Threading.WaitHandle [mscorlib]System.IAsyncResult::get_AsyncWaitHandle()
0x18e61  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0x18e66  pop
0x18e67  ldarg.0
0x18e68  call     void [mscorlib]System.GC::KeepAlive(object)
0x18e6d  ret
```
