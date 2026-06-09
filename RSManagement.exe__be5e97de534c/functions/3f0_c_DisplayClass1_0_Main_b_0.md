# <>c__DisplayClass1_0::<Main>b__0

- ea: `0x3f0`
- end: `0x413`
- name: `<>c__DisplayClass1_0::<Main>b__0`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c

```

## disassembly

```asm
0x3f0  ldstr    aReceivedStopEv// "Received stop event: Stopping..."
0x3f5  call     T0x2B000001
0x3fa  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x3ff  ldarg.0
0x400  ldfld    class [mscorlib]System.Threading.ManualResetEvent <>c__DisplayClass1_0::resetEvent
0x405  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0x40a  pop
0x40b  ldarg.2
0x40c  ldc.i4.1
0x40d  callvirt instance void [mscorlib]System.ConsoleCancelEventArgs::set_Cancel(bool)
0x412  ret
```
