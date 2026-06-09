# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetOnComplete(Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState> * *)

- ea: `0x18000b6e0`
- end: `0x18000b79b`
- name: `?GetOnComplete@?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJPEAPEAU?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@@Z`
- size: `187`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b6e0`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b722`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b722`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetOnComplete(
        __int64 a1,
        _QWORD *a2)
{
  unsigned int v4; // edi
  __int64 result; // rax
  int v6; // ett
  __int64 v7; // rcx
  __int64 v8; // rcx
  signed __int32 v9; // [rsp+30h] [rbp+8h] BYREF

  *a2 = 0;
  v9 = -2;
  _InterlockedCompareExchange(&v9, *(_DWORD *)(a1 + 56), -2);
  if ( v9 == 4 )
  {
    v4 = -2147483634;
    RoOriginateError(2147483662LL, 0);
    return v4;
  }
  else
  {
    result = *(unsigned int *)(a1 + 32);
    while ( (_DWORD)result )
    {
      v6 = result;
      result = (unsigned int)_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 32), result + 1, result);
      if ( v6 == (_DWORD)result )
      {
        v4 = 0;
        v7 = *(_QWORD *)(a1 + 24);
        if ( v7 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
        *a2 = *(_QWORD *)(a1 + 24);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 32), 0xFFFFFFFF) == 1 )
        {
          v8 = *(_QWORD *)(a1 + 24);
          if ( v8 )
          {
            *(_QWORD *)(a1 + 24) = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
          }
        }
        return v4;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000b6e0  mov     rax, rsp
0x18000b6e3  mov     [rax+10h], rbx
0x18000b6e7  mov     [rax+18h], rsi
0x18000b6eb  push    rdi
0x18000b6ec  sub     rsp, 20h
0x18000b6f0  mov     rsi, rdx
0x18000b6f3  mov     rbx, rcx
0x18000b6f6  mov     qword ptr [rdx], 0
0x18000b6fd  mov     dword ptr [rax+8], 0FFFFFFFEh
0x18000b704  mov     r8d, [rcx+38h]
0x18000b708  mov     eax, [rax+8]
0x18000b70b  lock cmpxchg [rsp+28h+arg_0], r8d
0x18000b712  cmp     [rsp+28h+arg_0], 4
0x18000b717  jnz     short loc_18000B72A
0x18000b719  xor     edx, edx
0x18000b71b  mov     edi, 8000000Eh
0x18000b720  mov     ecx, edi
0x18000b722  call    cs:__imp_RoOriginateError
0x18000b728  jmp     short loc_18000B797
0x18000b72a  mov     eax, [rcx+20h]
0x18000b72d  jmp     short loc_18000B739
0x18000b72f  lea     ecx, [rax+1]
0x18000b732  lock cmpxchg [rbx+20h], ecx
0x18000b737  jz      short loc_18000B74D
0x18000b739  test    eax, eax
0x18000b73b  jnz     short loc_18000B72F
0x18000b73d  mov     rbx, [rsp+28h+arg_8]
0x18000b742  mov     rsi, [rsp+28h+arg_10]
0x18000b747  add     rsp, 20h
0x18000b74b  pop     rdi
0x18000b74c  retn
0x18000b74d  xor     edi, edi
0x18000b74f  mov     rcx, [rbx+18h]
0x18000b753  test    rcx, rcx
0x18000b756  jz      short loc_18000B765
0x18000b758  mov     rax, [rcx]
0x18000b75b  mov     rax, [rax+8]
0x18000b75f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b764  nop
0x18000b765  mov     rax, [rbx+18h]
0x18000b769  mov     [rsi], rax
0x18000b76c  or      eax, 0FFFFFFFFh
0x18000b76f  lock xadd [rbx+20h], eax
0x18000b774  cmp     eax, 1
0x18000b777  jnz     short loc_18000B797
0x18000b779  mov     rcx, [rbx+18h]
0x18000b77d  test    rcx, rcx
0x18000b780  jz      short loc_18000B797
0x18000b782  mov     qword ptr [rbx+18h], 0
0x18000b78a  mov     rdx, [rcx]
0x18000b78d  mov     rax, [rdx+10h]
0x18000b791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b796  nop
0x18000b797  mov     eax, edi
0x18000b799  jmp     short loc_18000B73D
```
