# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetOnComplete(Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState> * *)

- ea: `0x18000b7b0`
- end: `0x18000b891`
- name: `?GetOnComplete@?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAPEAU?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@3@@Z`
- size: `225`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ea90`

## callees

- `0x18000b7b0`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b7eb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b7eb`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetOnComplete(
        __int64 a1,
        _QWORD *a2)
{
  unsigned int v3; // edi
  signed __int32 i; // eax
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rcx
  signed __int32 v9[10]; // [rsp+0h] [rbp-28h] BYREF
  signed __int32 v10; // [rsp+30h] [rbp+8h] BYREF

  *a2 = 0;
  v10 = -2;
  _InterlockedCompareExchange(&v10, *(_DWORD *)(a1 + 56), -2);
  if ( v10 == 4 )
  {
    v3 = -2147483634;
    RoOriginateError(2147483662LL, 0);
  }
  else
  {
    v3 = 0;
    for ( i = *(_DWORD *)(a1 + 136); i > 0; i = *(_DWORD *)(a1 + 136) )
    {
      if ( i == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 136), i + 1, i) )
      {
        v5 = *(_QWORD *)(a1 + 120);
        *a2 = 0;
        if ( v5 )
        {
          v6 = *(_QWORD *)(a1 + 120);
          if ( v6 )
            v3 = (*(__int64 (__fastcall **)(__int64, GUID *, _QWORD *))(*(_QWORD *)v6 + 24LL))(
                   v6,
                   &GUID_390b0091_caf7_5b64_839d_4990ae7f753c,
                   a2);
          else
            v3 = 0;
        }
        else
        {
          v3 = -2147024809;
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 136), 0xFFFFFFFF) == 1 )
        {
          _InterlockedOr(v9, 0);
          v7 = *(_QWORD *)(a1 + 120);
          *(_QWORD *)(a1 + 120) = 0;
          if ( v7 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
        }
        return v3;
      }
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000b7b0  mov     [rsp+arg_8], rbx
0x18000b7b5  push    rdi
0x18000b7b6  sub     rsp, 20h
0x18000b7ba  mov     rbx, rcx
0x18000b7bd  mov     qword ptr [rdx], 0
0x18000b7c4  mov     [rsp+28h+arg_0], 0FFFFFFFEh
0x18000b7cc  mov     r8d, [rcx+38h]
0x18000b7d0  mov     eax, [rsp+28h+arg_0]
0x18000b7d4  lock cmpxchg [rsp+28h+arg_0], r8d
0x18000b7db  cmp     [rsp+28h+arg_0], 4
0x18000b7e0  jnz     short loc_18000B7F6
0x18000b7e2  xor     edx, edx
0x18000b7e4  mov     edi, 8000000Eh
0x18000b7e9  mov     ecx, edi
0x18000b7eb  call    cs:__imp_RoOriginateError
0x18000b7f1  jmp     loc_18000B884
0x18000b7f6  xor     edi, edi
0x18000b7f8  mov     eax, [rcx+88h]
0x18000b7fe  jmp     short loc_18000B813
0x18000b800  lea     ecx, [rax+1]
0x18000b803  lock cmpxchg [rbx+88h], ecx
0x18000b80b  jz      short loc_18000B819
0x18000b80d  mov     eax, [rbx+88h]
0x18000b813  test    eax, eax
0x18000b815  jg      short loc_18000B800
0x18000b817  jmp     short loc_18000B884
0x18000b819  mov     rax, [rbx+78h]
0x18000b81d  mov     [rdx], rdi
0x18000b820  test    rax, rax
0x18000b823  jz      short loc_18000B84C
0x18000b825  mov     rcx, [rbx+78h]
0x18000b829  test    rcx, rcx
0x18000b82c  jnz     short loc_18000B832
0x18000b82e  xor     edi, edi
0x18000b830  jmp     short loc_18000B84A
0x18000b832  mov     rax, [rcx]
0x18000b835  mov     r8, rdx
0x18000b838  lea     rdx, _GUID_390b0091_caf7_5b64_839d_4990ae7f753c
0x18000b83f  mov     rax, [rax+18h]
0x18000b843  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b848  mov     edi, eax
0x18000b84a  jmp     short loc_18000B851
0x18000b84c  mov     edi, 80070057h
0x18000b851  or      eax, 0FFFFFFFFh
0x18000b854  lock xadd [rbx+88h], eax
0x18000b85c  cmp     eax, 1
0x18000b85f  jnz     short loc_18000B884
0x18000b861  lock or [rsp+28h+var_28], 0
0x18000b866  mov     rcx, [rbx+78h]
0x18000b86a  mov     qword ptr [rbx+78h], 0
0x18000b872  test    rcx, rcx
0x18000b875  jz      short loc_18000B884
0x18000b877  mov     rdx, [rcx]
0x18000b87a  mov     rax, [rdx+10h]
0x18000b87e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b883  nop
0x18000b884  mov     eax, edi
0x18000b886  mov     rbx, [rsp+28h+arg_8]
0x18000b88b  add     rsp, 20h
0x18000b88f  pop     rdi
0x18000b890  retn
```
