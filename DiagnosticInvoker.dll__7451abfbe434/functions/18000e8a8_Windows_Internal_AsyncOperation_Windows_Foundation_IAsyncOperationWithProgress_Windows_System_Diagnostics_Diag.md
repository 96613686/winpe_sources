# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(long)

- ea: `0x18000e8a8`
- end: `0x18000e960`
- name: `?_AfterExecute@?$AsyncOperation@U?$IAsyncOperationWithProgress@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@V?$ProgressResult@V?$CMarshaledInterfaceResult@UIDiagnosticActionResult@Diagnostics@System@Windows@@@Internal@Windows@@W4DiagnosticActionState@Diagnostics@System@3@@Internal@3@VComTaskPoolHandler@63@U?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXJ@Z`
- size: `184`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a4c0`
- `0x18000ca80`
- `0x18000d970`
- `0x18000e968`

## callees

- `0x18000e700`
- `0x18000e7fc`
- `0x18000e8a8`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(
        __int64 a1,
        int a2)
{
  bool v3; // di
  __int64 result; // rax
  signed __int32 v5; // [rsp+38h] [rbp+10h] BYREF

  v3 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 260), 0xFFFFFFFF) == 1;
  if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 252)) == 1 )
    v3 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 260), 0xFFFFFFFF) == 1;
  v5 = -2;
  if ( a2 >= 0 )
  {
    _InterlockedCompareExchange(&v5, *(_DWORD *)(a1 + 64), v5);
    if ( v5
      || (result = (unsigned int)_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 64), 1, 0),
          (_DWORD)result != v5) )
    {
      result = (unsigned int)_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 64), 1, 2);
    }
  }
  else
  {
    result = (unsigned int)_InterlockedCompareExchange(&v5, *(_DWORD *)(a1 + 64), v5);
    if ( v5 != 2 )
      result = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
                 a1 + 8,
                 (unsigned int)a2);
  }
  if ( v3 )
    return Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(a1);
  return result;
}

```

## disassembly

```asm
0x18000e8a8  mov     [rsp+arg_0], rbx
0x18000e8ad  push    rdi
0x18000e8ae  sub     rsp, 20h
0x18000e8b2  mov     rbx, rcx
0x18000e8b5  mov     r9d, edx
0x18000e8b8  or      ecx, 0FFFFFFFFh
0x18000e8bb  mov     eax, ecx
0x18000e8bd  lock xadd [rbx+104h], eax
0x18000e8c5  add     eax, ecx
0x18000e8c7  lea     edx, [rcx+2]
0x18000e8ca  mov     eax, edx
0x18000e8cc  setz    dil
0x18000e8d0  lock xadd [rbx+0FCh], eax
0x18000e8d8  add     eax, edx
0x18000e8da  cmp     eax, edx
0x18000e8dc  jnz     short loc_18000E8EE
0x18000e8de  mov     eax, ecx
0x18000e8e0  lock xadd [rbx+104h], eax
0x18000e8e8  add     eax, ecx
0x18000e8ea  setz    dil
0x18000e8ee  mov     [rsp+28h+arg_8], 0FFFFFFFEh
0x18000e8f6  test    r9d, r9d
0x18000e8f9  jns     short loc_18000E91D
0x18000e8fb  mov     edx, [rbx+40h]
0x18000e8fe  mov     eax, [rsp+28h+arg_8]
0x18000e902  lock cmpxchg [rsp+28h+arg_8], edx
0x18000e908  cmp     [rsp+28h+arg_8], 2
0x18000e90d  jz      short loc_18000E948
0x18000e90f  mov     edx, r9d
0x18000e912  lea     rcx, [rbx+8]
0x18000e916  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x18000e91b  jmp     short loc_18000E948
0x18000e91d  mov     ecx, [rbx+40h]
0x18000e920  mov     eax, [rsp+28h+arg_8]
0x18000e924  lock cmpxchg [rsp+28h+arg_8], ecx
0x18000e92a  cmp     [rsp+28h+arg_8], 0
0x18000e92f  jnz     short loc_18000E93E
0x18000e931  xor     eax, eax
0x18000e933  lock cmpxchg [rbx+40h], edx
0x18000e938  cmp     eax, [rsp+28h+arg_8]
0x18000e93c  jz      short loc_18000E948
0x18000e93e  mov     eax, 2
0x18000e943  lock cmpxchg [rbx+40h], edx
0x18000e948  test    dil, dil
0x18000e94b  jz      short loc_18000E955
0x18000e94d  mov     rcx, rbx
0x18000e950  call    ?_AfterComplete@?$AsyncOperation@U?$IAsyncOperationWithProgress@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@V?$ProgressResult@V?$CMarshaledInterfaceResult@UIDiagnosticActionResult@Diagnostics@System@Windows@@@Internal@Windows@@W4DiagnosticActionState@Diagnostics@System@3@@Internal@3@VComTaskPoolHandler@63@U?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)
0x18000e955  mov     rbx, [rsp+28h+arg_0]
0x18000e95a  add     rsp, 20h
0x18000e95e  pop     rdi
0x18000e95f  retn
```
