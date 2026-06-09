# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)

- ea: `0x18000e7fc`
- end: `0x18000e8a2`
- name: `?_AfterComplete@?$AsyncOperation@U?$IAsyncOperationWithProgress@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@V?$ProgressResult@V?$CMarshaledInterfaceResult@UIDiagnosticActionResult@Diagnostics@System@Windows@@@Internal@Windows@@W4DiagnosticActionState@Diagnostics@System@3@@Internal@3@VComTaskPoolHandler@63@U?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ`
- size: `166`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000e8a8`
- `0x18000e968`

## callees

- `0x18000a7e0`
- `0x18000e7fc`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e836`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e836`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x18000e840`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolAllowThreadReuse` at `0x18000e840`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(
        __int64 a1)
{
  void (__fastcall ***v2)(_QWORD, __int64); // rcx
  int v3; // ebx
  __int64 v4; // rcx
  signed __int32 v6[10]; // [rsp+0h] [rbp-28h] BYREF

  v2 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 264);
  if ( v2 )
    (**v2)(v2, 1);
  *(_QWORD *)(a1 + 264) = 0;
  v3 = *(_DWORD *)(a1 + 384);
  if ( GetCurrentThreadId() != v3 )
    SHTaskPoolAllowThreadReuse();
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 272));
  if ( *(int *)(a1 + 168) > 0 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 168), 0xFFFFFFFF) == 1 )
  {
    _InterlockedOr(v6, 0);
    v4 = *(_QWORD *)(a1 + 152);
    *(_QWORD *)(a1 + 152) = 0;
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(a1 + 8);
}

```

## disassembly

```asm
0x18000e7fc  mov     [rsp+arg_0], rbx
0x18000e801  push    rdi
0x18000e802  sub     rsp, 20h
0x18000e806  mov     rdi, rcx
0x18000e809  mov     rcx, [rcx+108h]
0x18000e810  test    rcx, rcx
0x18000e813  jz      short loc_18000E825
0x18000e815  mov     rax, [rcx]
0x18000e818  mov     edx, 1
0x18000e81d  mov     rax, [rax]
0x18000e820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e825  mov     qword ptr [rdi+108h], 0
0x18000e830  mov     ebx, [rdi+180h]
0x18000e836  call    cs:__imp_GetCurrentThreadId
0x18000e83c  cmp     eax, ebx
0x18000e83e  jz      short loc_18000E846
0x18000e840  call    cs:__imp_SHTaskPoolAllowThreadReuse
0x18000e846  lock inc dword ptr [rdi+110h]
0x18000e84d  cmp     dword ptr [rdi+0A8h], 0
0x18000e854  jle     short loc_18000E88F
0x18000e856  or      eax, 0FFFFFFFFh
0x18000e859  lock xadd [rdi+0A8h], eax
0x18000e861  cmp     eax, 1
0x18000e864  jnz     short loc_18000E88F
0x18000e866  lock or [rsp+28h+var_28], 0
0x18000e86b  mov     rcx, [rdi+98h]
0x18000e872  mov     qword ptr [rdi+98h], 0
0x18000e87d  test    rcx, rcx
0x18000e880  jz      short loc_18000E88F
0x18000e882  mov     rax, [rcx]
0x18000e885  mov     rax, [rax+10h]
0x18000e889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e88e  nop
0x18000e88f  lea     rcx, [rdi+8]
0x18000e893  mov     rbx, [rsp+28h+arg_0]
0x18000e898  add     rsp, 20h
0x18000e89c  pop     rdi
0x18000e89d  jmp     ?FireCompletion@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJXZ; Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::FireCompletion(void)
```
