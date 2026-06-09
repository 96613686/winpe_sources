# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(void)

- ea: `0x18000ca80`
- end: `0x18000cb9d`
- name: `?OnStart@?$AsyncOperation@U?$IAsyncOperationWithProgress@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@V?$ProgressResult@V?$CMarshaledInterfaceResult@UIDiagnosticActionResult@Diagnostics@System@Windows@@@Internal@Windows@@W4DiagnosticActionState@Diagnostics@System@3@@Internal@3@VComTaskPoolHandler@63@U?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ`
- size: `285`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000ca80`
- `0x18000e700`
- `0x18000e8a8`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cabf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cabf`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18000cafe`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18000cafe`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::OnStart(
        __int64 a1)
{
  unsigned int v2; // esi
  __int64 v3; // rdi
  DWORD CurrentThreadId; // eax
  int v5; // eax
  int v6; // edx

  v2 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**(_QWORD **)(a1 + 256) + 8LL))(
         *(_QWORD *)(a1 + 256),
         0,
         0,
         a1 + 280);
  if ( (v2 & 0x80000000) != 0 )
    goto LABEL_11;
  v3 = a1 - 8;
  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(a1 + 376) = CurrentThreadId;
  v2 = SHTaskPoolQueueTask(
         *(unsigned int *)(a1 + 368),
         *(unsigned int *)(a1 + 372),
         CurrentThreadId,
         0,
         (a1 + 200) & -(__int64)(a1 != 8),
         0);
  if ( (v2 & 0x80000000) != 0 )
  {
    if ( *(_DWORD *)(a1 + 248) )
    {
      Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
        a1,
        v2);
      return 0;
    }
    if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 248)) != 1 )
      goto LABEL_11;
    v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64))(**(_QWORD **)(v3 + 264) + 8LL))(
           *(_QWORD *)(v3 + 264),
           1,
           v2,
           v3 + 288);
    if ( v5 >= 0 && *(_BYTE *)(v3 + 305) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v3 + 280), 0xFFFFFFFF) != 1 )
      {
LABEL_11:
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
          a1,
          v2);
        return v2;
      }
      v6 = *(_DWORD *)(v3 + 284);
    }
    else
    {
      v6 = v5;
    }
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(
      a1 - 8,
      v6);
    goto LABEL_11;
  }
  return v2;
}

```

## disassembly

```asm
0x18000ca80  mov     [rsp+arg_0], rbx
0x18000ca85  mov     [rsp+arg_8], rsi
0x18000ca8a  push    rdi
0x18000ca8b  sub     rsp, 30h
0x18000ca8f  mov     rbx, rcx
0x18000ca92  xor     r8d, r8d
0x18000ca95  mov     rcx, [rcx+100h]
0x18000ca9c  xor     edx, edx
0x18000ca9e  lea     r9, [rbx+118h]
0x18000caa5  mov     rax, [rcx]
0x18000caa8  mov     rax, [rax+8]
0x18000caac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cab1  mov     esi, eax
0x18000cab3  test    eax, eax
0x18000cab5  js      loc_18000CB73
0x18000cabb  lea     rdi, [rbx-8]
0x18000cabf  call    cs:__imp_GetCurrentThreadId
0x18000cac5  lea     rdx, [rbx+0C8h]
0x18000cacc  mov     [rsp+38h+var_10], 0
0x18000cad5  mov     rcx, rdi
0x18000cad8  mov     [rbx+178h], eax
0x18000cade  neg     rcx
0x18000cae1  mov     ecx, [rbx+170h]
0x18000cae7  sbb     r8, r8
0x18000caea  xor     r9d, r9d
0x18000caed  and     r8, rdx
0x18000caf0  mov     edx, [rbx+174h]
0x18000caf6  mov     [rsp+38h+var_18], r8
0x18000cafb  mov     r8d, eax
0x18000cafe  call    cs:__imp_SHTaskPoolQueueTask
0x18000cb04  mov     esi, eax
0x18000cb06  test    eax, eax
0x18000cb08  jns     short loc_18000CB7D
0x18000cb0a  mov     eax, [rbx+0F8h]
0x18000cb10  test    eax, eax
0x18000cb12  jnz     short loc_18000CB8F
0x18000cb14  lea     edx, [rax+1]
0x18000cb17  mov     eax, edx
0x18000cb19  lock xadd [rbx+0F8h], eax
0x18000cb21  add     eax, edx
0x18000cb23  cmp     eax, edx
0x18000cb25  jnz     short loc_18000CB73
0x18000cb27  mov     rcx, [rdi+108h]
0x18000cb2e  lea     r9, [rdi+120h]
0x18000cb35  mov     r8d, esi
0x18000cb38  mov     rax, [rcx]
0x18000cb3b  mov     rax, [rax+8]
0x18000cb3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb44  test    eax, eax
0x18000cb46  js      short loc_18000CB69
0x18000cb48  cmp     byte ptr [rdi+131h], 0
0x18000cb4f  jz      short loc_18000CB69
0x18000cb51  or      eax, 0FFFFFFFFh
0x18000cb54  lock xadd [rdi+118h], eax
0x18000cb5c  cmp     eax, 1
0x18000cb5f  jnz     short loc_18000CB73
0x18000cb61  mov     edx, [rdi+11Ch]
0x18000cb67  jmp     short loc_18000CB6B
0x18000cb69  mov     edx, eax
0x18000cb6b  mov     rcx, rdi
0x18000cb6e  call    ?_AfterExecute@?$AsyncOperation@U?$IAsyncOperationWithProgress@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@V?$ProgressResult@V?$CMarshaledInterfaceResult@UIDiagnosticActionResult@Diagnostics@System@Windows@@@Internal@Windows@@W4DiagnosticActionState@Diagnostics@System@3@@Internal@3@VComTaskPoolHandler@63@U?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXJ@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(long)
0x18000cb73  mov     edx, esi
0x18000cb75  mov     rcx, rbx
0x18000cb78  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x18000cb7d  mov     rbx, [rsp+38h+arg_0]
0x18000cb82  mov     eax, esi
0x18000cb84  mov     rsi, [rsp+38h+arg_8]
0x18000cb89  add     rsp, 30h
0x18000cb8d  pop     rdi
0x18000cb8e  retn
0x18000cb8f  mov     edx, esi
0x18000cb91  mov     rcx, rbx
0x18000cb94  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x18000cb99  xor     esi, esi
0x18000cb9b  jmp     short loc_18000CB7D
```
