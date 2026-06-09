# System.Printing.PrintQueueStream::BeginWrite

- ea: `0x18dc0`
- end: `0x18e21`
- name: `System.Printing.PrintQueueStream::BeginWrite`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0xe540`
- `0x18dc0`
- `0x19380`
- `0x193e0`

## pseudocode

```c

```

## disassembly

```asm
0x18dc0  ldarg.1
0x18dc1  brfalse.s loc_18E14
0x18dc3  ldarg.3
0x18dc4  brfalse.s loc_18E14
0x18dc6  ldarg.3
0x18dc7  ldarg.1
0x18dc8  ldlen
0x18dc9  bgt.s    loc_18E14
0x18dcb  ldarg.0
0x18dcc  ldfld    class System.Printing.PrintQueue System.Printing.PrintQueueStream::printQueue
0x18dd1  call     instance bool System.Printing.PrintQueue::get_PrintingIsCancelled()
0x18dd6  brfalse.s loc_18DE8
0x18dd8  ldc.i4   0x8007003F
0x18ddd  ldstr    aPrintsystemexc_25// "PrintSystemException.PrintingCancelled."...
0x18de2  call     class [mscorlib]System.Exception System.Printing.PrintQueueStream::CreatePrintingCanceledException(int32 hresult, string messageId)
0x18de7  throw
0x18de8  ldarg.0
0x18de9  ldarg.1
0x18dea  ldarg.2
0x18deb  ldarg.3
0x18dec  ldarg.s  4
0x18dee  ldarg.s  5
0x18df0  newobj   instance void System.Printing.WritePrinterAsyncResult::.ctor(class [mscorlib]System.IO.Stream stream, unsigned int8[] array, int32 offset, int32 numBytes, class [mscorlib]System.AsyncCallback userCallBack, object stateObject)
0x18df5  stloc.0
0x18df6  ldloc.0
0x18df7  ldftn    instance void System.Printing.WritePrinterAsyncResult::AsyncWrite()
0x18dfd  newobj   instance void [mscorlib]System.Threading.ThreadStart::.ctor(object, native int)
0x18e02  newobj   instance void [mscorlib]System.Threading.Thread::.ctor(class [mscorlib]System.Threading.ThreadStart)
0x18e07  call     instance void [mscorlib]System.Threading.Thread::Start()
0x18e0c  ldarg.0
0x18e0d  call     void [mscorlib]System.GC::KeepAlive(object)
0x18e12  ldloc.0
0x18e13  ret
0x18e14  ldstr    aBuffer// "buffer"
0x18e19  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x18e1e  throw
0x18e1f  ldnull
0x18e20  ret
```
