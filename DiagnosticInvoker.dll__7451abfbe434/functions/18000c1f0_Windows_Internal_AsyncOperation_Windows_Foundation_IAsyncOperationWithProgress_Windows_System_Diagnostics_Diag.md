# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetResults(Windows::System::Diagnostics::IDiagnosticActionResult * *)

- ea: `0x18000c1f0`
- end: `0x18000c29b`
- name: `?GetResults@?$AsyncOperation@U?$IAsyncOperationWithProgress@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@V?$ProgressResult@V?$CMarshaledInterfaceResult@UIDiagnosticActionResult@Diagnostics@System@Windows@@@Internal@Windows@@W4DiagnosticActionState@Diagnostics@System@3@@Internal@3@VComTaskPoolHandler@63@U?$IAsyncOperationProgressHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@23@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAPEAUIDiagnosticActionResult@Diagnostics@System@3@@Z`
- size: `171`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b0f8`
- `0x18000c1f0`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18000c25a`
- `api-ms-win-core-winrt-error-l1-1-0!SetRestrictedErrorInfo` at `0x18000c25a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000c293`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000c293`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperationWithProgress<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ProgressResult<Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>,enum Windows::System::Diagnostics::DiagnosticActionState>,Windows::Internal::ComTaskPoolHandler,Windows::Foundation::IAsyncOperationProgressHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetResults(
        __int64 a1,
        _QWORD *a2)
{
  signed __int32 v4; // ecx
  int v5; // ebx
  signed __int32 v7; // [rsp+40h] [rbp+20h] BYREF
  signed __int32 v8; // [rsp+48h] [rbp+28h] BYREF
  signed __int32 v9; // [rsp+50h] [rbp+30h] BYREF

  *a2 = 0;
  v8 = -2;
  _InterlockedCompareExchange(&v8, *(_DWORD *)(a1 - 120), -2);
  if ( v8 != 3 )
  {
    if ( v8 != 1 )
    {
      v5 = -2147483634;
      RoOriginateError(2147483662LL, 0);
      return (unsigned int)v5;
    }
    return (unsigned int)Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>::Get(
                           a1 + 112,
                           a2);
  }
  v9 = -2;
  v4 = *(_DWORD *)(a1 - 120);
  v7 = 0;
  _InterlockedCompareExchange(&v9, v4, -2);
  if ( v9 == 3 )
  {
    _InterlockedCompareExchange(&v7, *(_DWORD *)(a1 - 116), v7);
    if ( *(_QWORD *)(a1 - 128) )
      SetRestrictedErrorInfo();
    v5 = v7;
  }
  else
  {
    v5 = 0;
  }
  if ( v5 >= 0 )
    return (unsigned int)Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>::Get(
                           a1 + 112,
                           a2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000c1f0  mov     [rsp-18h+arg_18], rbx
0x18000c1f5  push    rbp
0x18000c1f6  push    rsi
0x18000c1f7  push    rdi
0x18000c1f8  mov     rbp, rsp
0x18000c1fb  sub     rsp, 20h
0x18000c1ff  mov     rdi, rcx
0x18000c202  mov     qword ptr [rdx], 0
0x18000c209  mov     ecx, 0FFFFFFFEh
0x18000c20e  mov     rsi, rdx
0x18000c211  mov     [rbp+arg_8], ecx
0x18000c214  mov     r8d, [rdi-78h]
0x18000c218  mov     eax, [rbp+arg_8]
0x18000c21b  lock cmpxchg [rbp+arg_8], r8d
0x18000c221  cmp     [rbp+arg_8], 3
0x18000c225  jnz     short loc_18000C284
0x18000c227  mov     [rbp+arg_10], ecx
0x18000c22a  mov     ecx, [rdi-78h]
0x18000c22d  mov     eax, [rbp+arg_10]
0x18000c230  mov     [rbp+arg_0], 0
0x18000c237  lock cmpxchg [rbp+arg_10], ecx
0x18000c23c  cmp     [rbp+arg_10], 3
0x18000c240  jz      short loc_18000C246
0x18000c242  xor     ebx, ebx
0x18000c244  jmp     short loc_18000C263
0x18000c246  mov     ecx, [rdi-74h]
0x18000c249  mov     eax, [rbp+arg_0]
0x18000c24c  lock cmpxchg [rbp+arg_0], ecx
0x18000c251  mov     rcx, [rdi-80h]
0x18000c255  test    rcx, rcx
0x18000c258  jz      short loc_18000C260
0x18000c25a  call    cs:__imp_SetRestrictedErrorInfo
0x18000c260  mov     ebx, [rbp+arg_0]
0x18000c263  test    ebx, ebx
0x18000c265  js      short loc_18000C275
0x18000c267  lea     rcx, [rdi+70h]
0x18000c26b  mov     rdx, rsi
0x18000c26e  call    ?Get@?$CMarshaledInterfaceResult@UIDiagnosticActionResult@Diagnostics@System@Windows@@@Internal@Windows@@QEAAJPEAPEAUIDiagnosticActionResult@Diagnostics@System@3@@Z; Windows::Internal::CMarshaledInterfaceResult<Windows::System::Diagnostics::IDiagnosticActionResult>::Get(Windows::System::Diagnostics::IDiagnosticActionResult * *)
0x18000c273  mov     ebx, eax
0x18000c275  mov     eax, ebx
0x18000c277  mov     rbx, [rsp+20h+arg_18]
0x18000c27c  add     rsp, 20h
0x18000c280  pop     rdi
0x18000c281  pop     rsi
0x18000c282  pop     rbp
0x18000c283  retn
0x18000c284  cmp     [rbp+arg_8], 1
0x18000c288  jz      short loc_18000C267
0x18000c28a  mov     ebx, 8000000Eh
0x18000c28f  xor     edx, edx
0x18000c291  mov     ecx, ebx
0x18000c293  call    cs:__imp_RoOriginateError
0x18000c299  jmp     short loc_18000C275
```
