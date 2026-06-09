# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Run(void)

- ea: `0x18000d970`
- end: `0x18000da63`
- name: `?Run@?$AsyncOperation@U?$IAsyncOperationWithProgress@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@V?$ProgressResult@V?$CMarshaledInterfaceResult@UIDiagnosticActionResult@Diagnostics@System@Windows@@@Internal@Windows@@W4DiagnosticActionState@Diagnostics@System@3@@Internal@3@VComTaskPoolHandler@63@U?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAXXZ`
- size: `243`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000d970`
- `0x18000e8a8`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18000d9d4`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18000d9d4`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Run(
        __int64 a1)
{
  signed __int32 v2; // edx
  __int64 v3; // r8
  __int64 v4; // rbx
  __int64 result; // rax
  int v6; // eax
  __int64 v7; // rdx
  unsigned __int32 v8; // [rsp+40h] [rbp+10h] BYREF
  signed __int32 v9; // [rsp+48h] [rbp+18h] BYREF

  v8 = 0;
  v9 = -2;
  _InterlockedCompareExchange(&v9, *(_DWORD *)(a1 - 144), -2);
  if ( v9 )
  {
    v2 = *(_DWORD *)(a1 - 144);
    v9 = -2;
    _InterlockedCompareExchange(&v9, v2, -2);
    if ( v9 != 3 )
      goto LABEL_6;
    _InterlockedCompareExchange((volatile signed __int32 *)&v8, *(_DWORD *)(a1 - 140), v8);
    if ( *(_QWORD *)(a1 - 152) )
      SetRestrictedErrorInfo();
    v3 = v8;
    if ( (v8 & 0x80000000) == 0 )
    {
LABEL_6:
      v3 = 2147943623LL;
      v8 = -2147023673;
    }
  }
  else
  {
    v3 = v8;
  }
  v4 = a1 - 208;
  result = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(v4 + 256));
  if ( (_DWORD)result == 1 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(v4 + 264) + 8LL))(
           *(_QWORD *)(v4 + 264),
           1,
           v3,
           v4 + 288);
    if ( v6 >= 0 && *(_BYTE *)(v4 + 305) )
    {
      result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 280), 0xFFFFFFFF);
      if ( (_DWORD)result != 1 )
        return result;
      v7 = *(unsigned int *)(v4 + 284);
    }
    else
    {
      v7 = (unsigned int)v6;
    }
    return Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(
             v4,
             v7);
  }
  return result;
}

```

## disassembly

```asm
0x18000d970  mov     [rsp-8+arg_10], rbx
0x18000d975  push    rbp
0x18000d976  mov     rbp, rsp
0x18000d979  sub     rsp, 30h
0x18000d97d  mov     rbx, rcx
0x18000d980  mov     [rbp+arg_0], 0
0x18000d987  mov     ecx, 0FFFFFFFEh
0x18000d98c  mov     [rbp+arg_8], ecx
0x18000d98f  mov     edx, [rbx-90h]
0x18000d995  mov     eax, [rbp+arg_8]
0x18000d998  lock cmpxchg [rbp+arg_8], edx
0x18000d99d  cmp     [rbp+arg_8], 0
0x18000d9a1  jz      short loc_18000D9EF
0x18000d9a3  mov     edx, [rbx-90h]
0x18000d9a9  mov     [rbp+arg_8], ecx
0x18000d9ac  mov     eax, [rbp+arg_8]
0x18000d9af  lock cmpxchg [rbp+arg_8], edx
0x18000d9b4  cmp     [rbp+arg_8], 3
0x18000d9b8  jnz     short loc_18000D9E3
0x18000d9ba  mov     ecx, [rbx-8Ch]
0x18000d9c0  mov     eax, [rbp+arg_0]
0x18000d9c3  lock cmpxchg [rbp+arg_0], ecx
0x18000d9c8  mov     rcx, [rbx-98h]
0x18000d9cf  test    rcx, rcx
0x18000d9d2  jz      short loc_18000D9DA
0x18000d9d4  call    cs:__imp_SetRestrictedErrorInfo
0x18000d9da  mov     r8d, [rbp+arg_0]
0x18000d9de  test    r8d, r8d
0x18000d9e1  js      short loc_18000D9F3
0x18000d9e3  mov     r8d, 800704C7h
0x18000d9e9  mov     [rbp+arg_0], r8d
0x18000d9ed  jmp     short loc_18000D9F3
0x18000d9ef  mov     r8d, [rbp+arg_0]
0x18000d9f3  mov     edx, 1
0x18000d9f8  add     rbx, 0FFFFFFFFFFFFFF30h
0x18000d9ff  mov     eax, edx
0x18000da01  lock xadd [rbx+100h], eax
0x18000da09  add     eax, edx
0x18000da0b  cmp     eax, edx
0x18000da0d  jnz     short loc_18000DA58
0x18000da0f  mov     rcx, [rbx+108h]
0x18000da16  lea     r9, [rbx+120h]
0x18000da1d  mov     rax, [rcx]
0x18000da20  mov     rax, [rax+8]
0x18000da24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da29  test    eax, eax
0x18000da2b  js      short loc_18000DA4E
0x18000da2d  cmp     byte ptr [rbx+131h], 0
0x18000da34  jz      short loc_18000DA4E
0x18000da36  or      eax, 0FFFFFFFFh
0x18000da39  lock xadd [rbx+118h], eax
0x18000da41  cmp     eax, 1
0x18000da44  jnz     short loc_18000DA58
0x18000da46  mov     edx, [rbx+11Ch]
0x18000da4c  jmp     short loc_18000DA50
0x18000da4e  mov     edx, eax
0x18000da50  mov     rcx, rbx
0x18000da53  call    ?_AfterExecute@?$AsyncOperation@U?$IAsyncOperationWithProgress@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@V?$ProgressResult@V?$CMarshaledInterfaceResult@UIDiagnosticActionResult@Diagnostics@System@Windows@@@Internal@Windows@@W4DiagnosticActionState@Diagnostics@System@3@@Internal@3@VComTaskPoolHandler@63@U?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXJ@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(long)
0x18000da58  mov     rbx, [rsp+30h+arg_10]
0x18000da5d  add     rsp, 30h
0x18000da61  pop     rbp
0x18000da62  retn
```
