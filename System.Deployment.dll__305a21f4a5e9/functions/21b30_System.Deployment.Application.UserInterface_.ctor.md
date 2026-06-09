# System.Deployment.Application.UserInterface::.ctor

- ea: `0x21b30`
- end: `0x21bb0`
- name: `System.Deployment.Application.UserInterface::.ctor`
- size: `128`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0xa8c0`
- `0x21bb0`

## callees

- `0x228f0`

## string_xrefs

- `0x21b9a`: `UIThread`

## pseudocode

```c

```

## disassembly

```asm
0x21b30  ldarg.0
0x21b31  ldc.i4.0
0x21b32  newobj   instance void [mscorlib]System.Threading.ManualResetEvent::.ctor(bool)
0x21b37  stfld    class [mscorlib]System.Threading.ManualResetEvent System.Deployment.Application.UserInterface::_appctxExitThreadFinished
0x21b3c  ldarg.0
0x21b3d  ldc.i4.0
0x21b3e  newobj   instance void [mscorlib]System.Threading.ManualResetEvent::.ctor(bool)
0x21b43  stfld    class [mscorlib]System.Threading.ManualResetEvent System.Deployment.Application.UserInterface::_uiConstructed
0x21b48  ldarg.0
0x21b49  ldc.i4.0
0x21b4a  newobj   instance void [mscorlib]System.Threading.ManualResetEvent::.ctor(bool)
0x21b4f  stfld    class [mscorlib]System.Threading.ManualResetEvent System.Deployment.Application.UserInterface::_uiReady
0x21b54  ldarg.0
0x21b55  call     instance void [mscorlib]System.Object::.ctor()
0x21b5a  ldarg.0
0x21b5b  newobj   instance void System.Deployment.Application.SplashInfo::.ctor()
0x21b60  stfld    class System.Deployment.Application.SplashInfo System.Deployment.Application.UserInterface::_splashInfo
0x21b65  ldarg.0
0x21b66  ldfld    class System.Deployment.Application.SplashInfo System.Deployment.Application.UserInterface::_splashInfo
0x21b6b  ldarg.1
0x21b6c  stfld    bool System.Deployment.Application.SplashInfo::initializedAsWait
0x21b71  ldarg.0
0x21b72  ldarg.0
0x21b73  ldftn    instance void System.Deployment.Application.UserInterface::UIThread()
0x21b79  newobj   instance void [mscorlib]System.Threading.ThreadStart::.ctor(object, native int)
0x21b7e  newobj   instance void [mscorlib]System.Threading.Thread::.ctor(class [mscorlib]System.Threading.ThreadStart)
0x21b83  stfld    class [mscorlib]System.Threading.Thread System.Deployment.Application.UserInterface::_uiThread
0x21b88  ldarg.0
0x21b89  ldfld    class [mscorlib]System.Threading.Thread System.Deployment.Application.UserInterface::_uiThread
0x21b8e  ldc.i4.0
0x21b8f  callvirt instance void [mscorlib]System.Threading.Thread::SetApartmentState(valuetype [mscorlib]System.Threading.ApartmentState)
0x21b94  ldarg.0
0x21b95  ldfld    class [mscorlib]System.Threading.Thread System.Deployment.Application.UserInterface::_uiThread
0x21b9a  ldstr    aUithread// "UIThread"
0x21b9f  callvirt instance void [mscorlib]System.Threading.Thread::set_Name(string)
0x21ba4  ldarg.0
0x21ba5  ldfld    class [mscorlib]System.Threading.Thread System.Deployment.Application.UserInterface::_uiThread
0x21baa  callvirt instance void [mscorlib]System.Threading.Thread::Start()
0x21baf  ret
```
