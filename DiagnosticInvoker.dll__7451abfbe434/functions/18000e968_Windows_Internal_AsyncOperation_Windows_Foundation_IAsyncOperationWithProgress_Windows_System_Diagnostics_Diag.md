# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(Windows::Internal::AsyncStage,long)

- ea: `0x18000e968`
- end: `0x18000ea7f`
- name: `?_Run@?$AsyncOperation@U?$IAsyncOperationWithProgress@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@V?$ProgressResult@V?$CMarshaledInterfaceResult@UIDiagnosticActionResult@Diagnostics@System@Windows@@@Internal@Windows@@W4DiagnosticActionState@Diagnostics@System@3@@Internal@3@VComTaskPoolHandler@63@U?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXW4AsyncStage@23@J@Z`
- size: `279`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ca30`

## callees

- `0x18000e7fc`
- `0x18000e8a8`
- `0x18000e968`
- `0x180011010`

## pseudocode

```c
void __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_Run(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // rbp
  bool v5; // cl
  int v6; // eax
  int v7; // edx

  if ( (_DWORD)a2 == 2 )
  {
    if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 252)) != 1 )
      return;
    v4 = a1 + 288;
    (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(a1 + 264) + 8LL))(
      *(_QWORD *)(a1 + 264),
      a2,
      a3,
      a1 + 288);
    v5 = _InterlockedAdd((volatile signed __int32 *)(a1 + 260), 0xFFFFFFFF) == 0;
    if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 256)) == 1 )
    {
      (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(a1 + 264) + 8LL))(
        *(_QWORD *)(a1 + 264),
        1,
        2147943623LL,
        v4);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 260), 0xFFFFFFFF) != 1 )
        return;
    }
    else if ( !v5 )
    {
      return;
    }
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(a1);
  }
  else if ( (_DWORD)a2 == 1 && _InterlockedIncrement((volatile signed __int32 *)(a1 + 256)) == 1 )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**(_QWORD **)(a1 + 264) + 8LL))(
           *(_QWORD *)(a1 + 264),
           1,
           a3,
           a1 + 288);
    if ( v6 >= 0 && *(_BYTE *)(a1 + 305) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 280), 0xFFFFFFFF) != 1 )
        return;
      v7 = *(_DWORD *)(a1 + 284);
    }
    else
    {
      v7 = v6;
    }
    Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(
      a1,
      v7);
  }
}

```

## disassembly

```asm
0x18000e968  mov     [rsp+arg_0], rbx
0x18000e96d  mov     [rsp+arg_8], rbp
0x18000e972  push    rdi
0x18000e973  sub     rsp, 30h
0x18000e977  mov     rbx, rcx
0x18000e97a  mov     edi, 1
0x18000e97f  cmp     edx, 2
0x18000e982  jnz     loc_18000EA11
0x18000e988  mov     eax, edi
0x18000e98a  lock xadd [rcx+0FCh], eax
0x18000e992  add     eax, edi
0x18000e994  cmp     eax, edi
0x18000e996  jnz     loc_18000EA6F
0x18000e99c  lea     rbp, [rcx+120h]
0x18000e9a3  mov     rcx, [rcx+108h]
0x18000e9aa  mov     r9, rbp
0x18000e9ad  mov     rax, [rcx]
0x18000e9b0  mov     rax, [rax+8]
0x18000e9b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9b9  lock add dword ptr [rbx+104h], 0FFFFFFFFh
0x18000e9c1  setz    cl
0x18000e9c4  mov     eax, edi
0x18000e9c6  lock xadd [rbx+100h], eax
0x18000e9ce  add     eax, edi
0x18000e9d0  cmp     eax, edi
0x18000e9d2  jnz     short loc_18000EA03
0x18000e9d4  mov     rcx, [rbx+108h]
0x18000e9db  mov     r9, rbp
0x18000e9de  mov     r8d, 800704C7h
0x18000e9e4  mov     edx, edi
0x18000e9e6  mov     rax, [rcx]
0x18000e9e9  mov     rax, [rax+8]
0x18000e9ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9f2  or      eax, 0FFFFFFFFh
0x18000e9f5  lock xadd [rbx+104h], eax
0x18000e9fd  cmp     eax, edi
0x18000e9ff  jnz     short loc_18000EA6F
0x18000ea01  jmp     short loc_18000EA07
0x18000ea03  test    cl, cl
0x18000ea05  jz      short loc_18000EA6F
0x18000ea07  mov     rcx, rbx
0x18000ea0a  call    ?_AfterComplete@?$AsyncOperation@U?$IAsyncOperationWithProgress@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@V?$ProgressResult@V?$CMarshaledInterfaceResult@UIDiagnosticActionResult@Diagnostics@System@Windows@@@Internal@Windows@@W4DiagnosticActionState@Diagnostics@System@3@@Internal@3@VComTaskPoolHandler@63@U?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)
0x18000ea0f  jmp     short loc_18000EA6F
0x18000ea11  cmp     edx, edi
0x18000ea13  jnz     short loc_18000EA6F
0x18000ea15  mov     eax, edi
0x18000ea17  lock xadd [rcx+100h], eax
0x18000ea1f  add     eax, edi
0x18000ea21  cmp     eax, edi
0x18000ea23  jnz     short loc_18000EA6F
0x18000ea25  mov     rcx, [rcx+108h]
0x18000ea2c  lea     r9, [rbx+120h]
0x18000ea33  mov     edx, edi
0x18000ea35  mov     rax, [rcx]
0x18000ea38  mov     rax, [rax+8]
0x18000ea3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea41  test    eax, eax
0x18000ea43  js      short loc_18000EA65
0x18000ea45  cmp     byte ptr [rbx+131h], 0
0x18000ea4c  jz      short loc_18000EA65
0x18000ea4e  or      eax, 0FFFFFFFFh
0x18000ea51  lock xadd [rbx+118h], eax
0x18000ea59  cmp     eax, edi
0x18000ea5b  jnz     short loc_18000EA6F
0x18000ea5d  mov     edx, [rbx+11Ch]
0x18000ea63  jmp     short loc_18000EA67
0x18000ea65  mov     edx, eax
0x18000ea67  mov     rcx, rbx
0x18000ea6a  call    ?_AfterExecute@?$AsyncOperation@U?$IAsyncOperationWithProgress@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@V?$ProgressResult@V?$CMarshaledInterfaceResult@UIDiagnosticActionResult@Diagnostics@System@Windows@@@Internal@Windows@@W4DiagnosticActionState@Diagnostics@System@3@@Internal@3@VComTaskPoolHandler@63@U?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXJ@Z; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(long)
0x18000ea6f  mov     rbx, [rsp+38h+arg_0]
0x18000ea74  mov     rbp, [rsp+38h+arg_8]
0x18000ea79  add     rsp, 30h
0x18000ea7d  pop     rdi
0x18000ea7e  retn
```
