# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(Windows::Foundation::IAsyncOperationCompletedHandler<bool> *)

- ea: `0x18000d600`
- end: `0x18000d78d`
- name: `?PutOnComplete@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAU?$IAsyncOperationCompletedHandler@_N@Foundation@3@@Z`
- size: `397`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800114c0`

## callees

- `0x180001dc0`
- `0x18000d600`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000d644`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000d644`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18000d6b2`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18000d6b2`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(
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
0x18000d600  mov     [rsp-18h+arg_10], rbx
0x18000d605  push    rbp
0x18000d606  push    rsi
0x18000d607  push    rdi
0x18000d608  mov     rbp, rsp
0x18000d60b  sub     rsp, 60h
0x18000d60f  mov     rax, cs:__security_cookie
0x18000d616  xor     rax, rsp
0x18000d619  mov     [rbp+var_8], rax
0x18000d61d  mov     rbx, rcx
0x18000d620  mov     [rbp+var_10], 0FFFFFFFEh
0x18000d627  mov     ecx, [rcx+38h]
0x18000d62a  mov     rsi, rdx
0x18000d62d  mov     eax, [rbp+var_10]
0x18000d630  lock cmpxchg [rbp+var_10], ecx
0x18000d635  cmp     [rbp+var_10], 4
0x18000d639  jnz     short loc_18000D64F
0x18000d63b  mov     edi, 8000000Eh
0x18000d640  xor     edx, edx
0x18000d642  mov     ecx, edi
0x18000d644  call    cs:__imp_RoOriginateError
0x18000d64a  jmp     loc_18000D76F
0x18000d64f  mov     eax, 1
0x18000d654  lock xadd [rbx+14h], eax
0x18000d659  inc     eax
0x18000d65b  cmp     eax, 1
0x18000d65e  jnz     loc_18000D76A
0x18000d664  lea     rdi, [rbx+78h]
0x18000d668  mov     rcx, [rdi]
0x18000d66b  mov     qword ptr [rdi], 0
0x18000d672  test    rcx, rcx
0x18000d675  jz      short loc_18000D683
0x18000d677  mov     rax, [rcx]
0x18000d67a  mov     rax, [rax+10h]
0x18000d67e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d683  mov     rcx, [rdi]
0x18000d686  test    rsi, rsi
0x18000d689  jz      short loc_18000D6C4
0x18000d68b  test    rcx, rcx
0x18000d68e  jz      short loc_18000D6A3
0x18000d690  mov     qword ptr [rdi], 0
0x18000d697  mov     rax, [rcx]
0x18000d69a  mov     rax, [rax+10h]
0x18000d69e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6a3  mov     r9, rdi
0x18000d6a6  lea     rdx, _GUID_c1d3d1a2_ae17_5a5f_b5a2_bdcc8844889a
0x18000d6ad  mov     r8, rsi
0x18000d6b0  xor     ecx, ecx
0x18000d6b2  call    cs:__imp_RoGetAgileReference
0x18000d6b8  mov     edi, eax
0x18000d6ba  test    eax, eax
0x18000d6bc  js      loc_18000D76F
0x18000d6c2  jmp     short loc_18000D6DE
0x18000d6c4  mov     qword ptr [rdi], 0
0x18000d6cb  test    rcx, rcx
0x18000d6ce  jz      short loc_18000D6DC
0x18000d6d0  mov     rax, [rcx]
0x18000d6d3  mov     rax, [rax+10h]
0x18000d6d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6dc  xor     edi, edi
0x18000d6de  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000d6e5  test    rcx, rcx
0x18000d6e8  jz      short loc_18000D71B
0x18000d6ea  mov     rax, [rcx]
0x18000d6ed  lea     r9, [rbp+var_20]
0x18000d6f1  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000d6f8  mov     edx, 2
0x18000d6fd  mov     [rsp+60h+var_38], 0
0x18000d705  mov     r8d, edx
0x18000d708  mov     [rsp+60h+var_40], rbx
0x18000d70d  mov     rax, [rax+40h]
0x18000d711  movdqu  [rbp+var_20], xmm0
0x18000d716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d71b  test    rsi, rsi
0x18000d71e  jz      short loc_18000D735
0x18000d720  mov     rax, [rsi]
0x18000d723  mov     rcx, [rax+18h]
0x18000d727  mov     [rbx+80h], rcx
0x18000d72e  lock inc dword ptr [rbx+88h]
0x18000d735  lock or [rsp+60h+var_60], 0
0x18000d73a  mov     edx, [rbx+38h]
0x18000d73d  mov     [rbp+var_10], 0FFFFFFFEh
0x18000d744  mov     eax, [rbp+var_10]
0x18000d747  lock cmpxchg [rbp+var_10], edx
0x18000d74c  mov     edx, [rbp+var_10]
0x18000d74f  dec     edx
0x18000d751  cmp     edx, 3
0x18000d754  ja      short loc_18000D76F
0x18000d756  mov     rax, [rbx]
0x18000d759  mov     rcx, rbx
0x18000d75c  mov     rax, [rax+80h]
0x18000d763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d768  jmp     short loc_18000D76F
0x18000d76a  mov     edi, 80000018h
0x18000d76f  mov     eax, edi
0x18000d771  mov     rcx, [rbp+var_8]
0x18000d775  xor     rcx, rsp; StackCookie
0x18000d778  call    __security_check_cookie
0x18000d77d  mov     rbx, [rsp+60h+arg_10]
0x18000d785  add     rsp, 60h
0x18000d789  pop     rdi
0x18000d78a  pop     rsi
0x18000d78b  pop     rbp
0x18000d78c  retn
```
