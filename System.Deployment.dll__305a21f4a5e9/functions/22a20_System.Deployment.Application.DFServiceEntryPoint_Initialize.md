# System.Deployment.Application.DFServiceEntryPoint::Initialize

- ea: `0x22a20`
- end: `0x22b0c`
- name: `System.Deployment.Application.DFServiceEntryPoint::Initialize`
- size: `236`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task`

## callees

- `0x40`
- `0x1d0`
- `0x16d00`
- `0x1c670`
- `0x229a0`
- `0x22a20`
- `0x22b20`
- `0x2c7f0`
- `0x2c850`
- `0x2c8a0`
- `0x2d7e0`

## pseudocode

```c

```

## disassembly

```asm
0x22a20  call     class Microsoft.Internal.Performance.CodeMarkers System.Deployment.Application.CodeMarker_Singleton::get_Instance()
0x22a25  ldc.i4   0x20B
0x22a2a  callvirt instance bool Microsoft.Internal.Performance.CodeMarkers::CodeMarker(int32 nTimerID)
0x22a2f  pop
0x22a30  call     bool System.Deployment.Application.PlatformSpecific::get_OnWin9x()
0x22a35  brfalse.s loc_22A4F
0x22a37  ldnull
0x22a38  ldftn    void System.Deployment.Application.DFServiceEntryPoint::MessageLoopThread()
0x22a3e  newobj   instance void [mscorlib]System.Threading.ThreadStart::.ctor(object, native int)
0x22a43  newobj   instance void [mscorlib]System.Threading.Thread::.ctor(class [mscorlib]System.Threading.ThreadStart)
0x22a48  stloc.2
0x22a49  ldloc.2
0x22a4a  callvirt instance void [mscorlib]System.Threading.Thread::Start()
0x22a4f  call     void System.Deployment.Application.DFServiceEntryPoint::ObtainDfdllExports()
0x22a54  ldsfld   class CreateDeploymentServiceComDelegate <>c::<>9__12_0
0x22a59  dup
0x22a5a  brtrue.s loc_22A73
0x22a5c  pop
0x22a5d  ldsfld   class <>c <>c::<>9
0x22a62  ldftn    instance class System.Deployment.Application.IManagedDeploymentServiceCom <>c::<Initialize>b__12_0()
0x22a68  newobj   instance void CreateDeploymentServiceComDelegate::.ctor(object object, native int method)
0x22a6d  dup
0x22a6e  stsfld   class CreateDeploymentServiceComDelegate <>c::<>9__12_0
0x22a73  stsfld   class CreateDeploymentServiceComDelegate System.Deployment.Application.DFServiceEntryPoint::s_createDeploymentServiceComDelegate
0x22a78  ldsfld   class RegisterDeploymentServiceComDelegate System.Deployment.Application.DFServiceEntryPoint::RegisterDeploymentServiceCom
0x22a7d  ldsfld   class CreateDeploymentServiceComDelegate System.Deployment.Application.DFServiceEntryPoint::s_createDeploymentServiceComDelegate
0x22a82  callvirt instance int32 RegisterDeploymentServiceComDelegate::Invoke([hasfieldmarshal] class CreateDeploymentServiceComDelegate createDeploymentServiceComDelegate)
0x22a87  stloc.0
0x22a88  ldloc.0
0x22a89  ldc.i4.0
0x22a8a  bge.s    loc_22A93
0x22a8c  ldloc.0
0x22a8d  call     class [mscorlib]System.Exception [mscorlib]System.Runtime.InteropServices.Marshal::GetExceptionForHR(int32)
0x22a92  throw
0x22a93  call     class Microsoft.Internal.Performance.CodeMarkers System.Deployment.Application.CodeMarker_Singleton::get_Instance()
0x22a98  ldc.i4   0x20C
0x22a9d  callvirt instance bool Microsoft.Internal.Performance.CodeMarkers::CodeMarker(int32 nTimerID)
0x22aa2  pop
0x22aa3  call     bool System.Deployment.Application.LifetimeManager::WaitForEnd()
0x22aa8  stloc.1
0x22aa9  ldsfld   class DfsvcForm System.Deployment.Application.DFServiceEntryPoint::_dfsvcForm
0x22aae  brfalse.s loc_22ADA
0x22ab0  ldsfld   class DfsvcForm System.Deployment.Application.DFServiceEntryPoint::_dfsvcForm
0x22ab5  ldsfld   class DfsvcForm System.Deployment.Application.DFServiceEntryPoint::_dfsvcForm
0x22aba  ldftn    instance void DfsvcForm::CloseForm(bool lifetimeManagerAlreadyTerminated)
0x22ac0  newobj   instance void CloseFormDelegate::.ctor(object object, native int method)
0x22ac5  ldc.i4.1
0x22ac6  newarr   [mscorlib]System.Object
0x22acb  dup
0x22acc  ldc.i4.0
0x22acd  ldc.i4.1
0x22ace  box      [mscorlib]System.Boolean
0x22ad3  stelem.ref
0x22ad4  callvirt instance object [System.Windows.Forms]System.Windows.Forms.Control::Invoke(class [mscorlib]System.Delegate, object[])
0x22ad9  pop
0x22ada  ldsfld   class UnregisterDeploymentServiceComDelegate System.Deployment.Application.DFServiceEntryPoint::UnregisterDeploymentServiceCom
0x22adf  callvirt instance int32 UnregisterDeploymentServiceComDelegate::Invoke()
0x22ae4  pop
0x22ae5  ldloc.1
0x22ae6  brtrue.s loc_22AF9
0x22ae8  call     bool System.Deployment.Application.PlatformSpecific::get_OnWin9x()
0x22aed  brfalse.s loc_22AF9
0x22aef  ldc.i4   0x1388
0x22af4  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x22af9  call     class Microsoft.Internal.Performance.CodeMarkers System.Deployment.Application.CodeMarker_Singleton::get_Instance()
0x22afe  ldc.i4.s 0x3F
0x22b00  callvirt instance void Microsoft.Internal.Performance.CodeMarkers::UninitializePerformanceDLL(int32 iApp)
0x22b05  ldc.i4.0
0x22b06  call     void [mscorlib]System.Environment::Exit(int32)
0x22b0b  ret
```
