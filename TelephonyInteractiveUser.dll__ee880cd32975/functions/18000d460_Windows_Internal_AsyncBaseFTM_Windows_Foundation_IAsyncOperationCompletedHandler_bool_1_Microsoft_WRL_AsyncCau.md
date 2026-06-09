# Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::PutOnComplete

- ea: `0x18000d460`
- end: `0x18000d5ed`
- name: `Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions_&launchForActiveCallAsyncName_&GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::PutOnComplete`
- size: `397`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180011520`

## callees

- `0x180001dc0`
- `0x18000d460`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000d4a4`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000d4a4`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18000d512`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18000d512`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM_Windows::Foundation::IAsyncOperationCompletedHandler_bool__1_Microsoft::WRL::AsyncCausalityOptions__launchForActiveCallAsyncName__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2___::PutOnComplete(
        __int64 a1,
        __int64 a2)
{
  int AgileReference; // edi
  __int64 *v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rax
  void (__fastcall *v9)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, _DWORD); // rax
  signed __int32 v10; // edx
  signed __int32 v12[8]; // [rsp+0h] [rbp-60h] BYREF
  __int64 v13; // [rsp+20h] [rbp-40h]
  int v14; // [rsp+28h] [rbp-38h]
  GUID v15; // [rsp+40h] [rbp-20h] BYREF
  signed __int32 v16; // [rsp+50h] [rbp-10h] BYREF

  v16 = -2;
  _InterlockedCompareExchange(&v16, *(_DWORD *)(a1 + 56), -2);
  if ( v16 == 4 )
  {
    AgileReference = -2147483634;
    RoOriginateError(2147483662LL);
    return (unsigned int)AgileReference;
  }
  if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 20)) != 1 )
    return (unsigned int)-2147483624;
  v5 = (__int64 *)(a1 + 120);
  v6 = *(_QWORD *)(a1 + 120);
  *(_QWORD *)(a1 + 120) = 0;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = *v5;
  if ( !a2 )
  {
    *v5 = 0;
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    AgileReference = 0;
    goto LABEL_14;
  }
  if ( v7 )
  {
    *v5 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  AgileReference = RoGetAgileReference(0, &GUID_c1d3d1a2_ae17_5a5f_b5a2_bdcc8844889a, a2, a1 + 120);
  if ( AgileReference >= 0 )
  {
LABEL_14:
    if ( Microsoft::WRL::gCausality )
    {
      v8 = *(_QWORD *)Microsoft::WRL::gCausality;
      v14 = 0;
      v13 = a1;
      v9 = *(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, _DWORD))(v8 + 64);
      v15 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
      v9(Microsoft::WRL::gCausality, 2, 2, &v15, a1, 0);
    }
    if ( a2 )
    {
      *(_QWORD *)(a1 + 128) = *(_QWORD *)(*(_QWORD *)a2 + 24LL);
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 136));
    }
    _InterlockedOr(v12, 0);
    v10 = *(_DWORD *)(a1 + 56);
    v16 = -2;
    _InterlockedCompareExchange(&v16, v10, -2);
    if ( (unsigned int)(v16 - 1) <= 3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
  }
  return (unsigned int)AgileReference;
}

```

## disassembly

```asm
0x18000d460  mov     [rsp-18h+arg_10], rbx
0x18000d465  push    rbp
0x18000d466  push    rsi
0x18000d467  push    rdi
0x18000d468  mov     rbp, rsp
0x18000d46b  sub     rsp, 60h
0x18000d46f  mov     rax, cs:__security_cookie
0x18000d476  xor     rax, rsp
0x18000d479  mov     [rbp+var_8], rax
0x18000d47d  mov     rbx, rcx
0x18000d480  mov     [rbp+var_10], 0FFFFFFFEh
0x18000d487  mov     ecx, [rcx+38h]
0x18000d48a  mov     rsi, rdx
0x18000d48d  mov     eax, [rbp+var_10]
0x18000d490  lock cmpxchg [rbp+var_10], ecx
0x18000d495  cmp     [rbp+var_10], 4
0x18000d499  jnz     short loc_18000D4AF
0x18000d49b  mov     edi, 8000000Eh
0x18000d4a0  xor     edx, edx
0x18000d4a2  mov     ecx, edi
0x18000d4a4  call    cs:__imp_RoOriginateError
0x18000d4aa  jmp     loc_18000D5CF
0x18000d4af  mov     eax, 1
0x18000d4b4  lock xadd [rbx+14h], eax
0x18000d4b9  inc     eax
0x18000d4bb  cmp     eax, 1
0x18000d4be  jnz     loc_18000D5CA
0x18000d4c4  lea     rdi, [rbx+78h]
0x18000d4c8  mov     rcx, [rdi]
0x18000d4cb  mov     qword ptr [rdi], 0
0x18000d4d2  test    rcx, rcx
0x18000d4d5  jz      short loc_18000D4E3
0x18000d4d7  mov     rax, [rcx]
0x18000d4da  mov     rax, [rax+10h]
0x18000d4de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4e3  mov     rcx, [rdi]
0x18000d4e6  test    rsi, rsi
0x18000d4e9  jz      short loc_18000D524
0x18000d4eb  test    rcx, rcx
0x18000d4ee  jz      short loc_18000D503
0x18000d4f0  mov     qword ptr [rdi], 0
0x18000d4f7  mov     rax, [rcx]
0x18000d4fa  mov     rax, [rax+10h]
0x18000d4fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d503  mov     r9, rdi
0x18000d506  lea     rdx, _GUID_c1d3d1a2_ae17_5a5f_b5a2_bdcc8844889a
0x18000d50d  mov     r8, rsi
0x18000d510  xor     ecx, ecx
0x18000d512  call    cs:__imp_RoGetAgileReference
0x18000d518  mov     edi, eax
0x18000d51a  test    eax, eax
0x18000d51c  js      loc_18000D5CF
0x18000d522  jmp     short loc_18000D53E
0x18000d524  mov     qword ptr [rdi], 0
0x18000d52b  test    rcx, rcx
0x18000d52e  jz      short loc_18000D53C
0x18000d530  mov     rax, [rcx]
0x18000d533  mov     rax, [rax+10h]
0x18000d537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d53c  xor     edi, edi
0x18000d53e  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000d545  test    rcx, rcx
0x18000d548  jz      short loc_18000D57B
0x18000d54a  mov     rax, [rcx]
0x18000d54d  lea     r9, [rbp+var_20]
0x18000d551  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000d558  mov     edx, 2
0x18000d55d  mov     [rsp+60h+var_38], 0
0x18000d565  mov     r8d, edx
0x18000d568  mov     [rsp+60h+var_40], rbx
0x18000d56d  mov     rax, [rax+40h]
0x18000d571  movdqu  [rbp+var_20], xmm0
0x18000d576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d57b  test    rsi, rsi
0x18000d57e  jz      short loc_18000D595
0x18000d580  mov     rax, [rsi]
0x18000d583  mov     rcx, [rax+18h]
0x18000d587  mov     [rbx+80h], rcx
0x18000d58e  lock inc dword ptr [rbx+88h]
0x18000d595  lock or [rsp+60h+var_60], 0
0x18000d59a  mov     edx, [rbx+38h]
0x18000d59d  mov     [rbp+var_10], 0FFFFFFFEh
0x18000d5a4  mov     eax, [rbp+var_10]
0x18000d5a7  lock cmpxchg [rbp+var_10], edx
0x18000d5ac  mov     edx, [rbp+var_10]
0x18000d5af  dec     edx
0x18000d5b1  cmp     edx, 3
0x18000d5b4  ja      short loc_18000D5CF
0x18000d5b6  mov     rax, [rbx]
0x18000d5b9  mov     rcx, rbx
0x18000d5bc  mov     rax, [rax+80h]
0x18000d5c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5c8  jmp     short loc_18000D5CF
0x18000d5ca  mov     edi, 80000018h
0x18000d5cf  mov     eax, edi
0x18000d5d1  mov     rcx, [rbp+var_8]
0x18000d5d5  xor     rcx, rsp; StackCookie
0x18000d5d8  call    __security_check_cookie
0x18000d5dd  mov     rbx, [rsp+60h+arg_10]
0x18000d5e5  add     rsp, 60h
0x18000d5e9  pop     rdi
0x18000d5ea  pop     rsi
0x18000d5eb  pop     rbp
0x18000d5ec  retn
```
