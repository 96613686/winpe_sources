# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(Windows::Foundation::IAsyncOperationCompletedHandler<bool> *)

- ea: `0x18000d310`
- end: `0x18000d456`
- name: `?PutOnComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJPEAU?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@@Z`
- size: `326`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x18000d310`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000d42d`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000d42d`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnComplete(
        __int64 a1,
        __int64 a2)
{
  unsigned int v4; // esi
  __int64 v5; // rcx
  __int64 v6; // rax
  void (__fastcall *v7)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, _DWORD); // rax
  signed __int32 v8; // edx
  signed __int32 v10[8]; // [rsp+0h] [rbp-60h] BYREF
  __int64 v11; // [rsp+20h] [rbp-40h]
  int v12; // [rsp+28h] [rbp-38h]
  GUID v13; // [rsp+40h] [rbp-20h] BYREF
  signed __int32 v14; // [rsp+50h] [rbp-10h] BYREF

  v14 = -2;
  _InterlockedCompareExchange(&v14, *(_DWORD *)(a1 + 56), -2);
  if ( v14 == 4 )
  {
    v4 = -2147483634;
LABEL_16:
    RoOriginateError(v4);
    return v4;
  }
  if ( _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 20), 1, 0) )
  {
    v4 = -2147483624;
    goto LABEL_16;
  }
  v4 = 0;
  if ( a2 )
    *(_QWORD *)(a1 + 40) = *(_QWORD *)(*(_QWORD *)a2 + 24LL);
  if ( *(_QWORD *)(a1 + 24) != a2 )
  {
    if ( a2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    v5 = *(_QWORD *)(a1 + 24);
    *(_QWORD *)(a1 + 24) = a2;
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  _InterlockedOr(v10, 0);
  _InterlockedAdd((volatile signed __int32 *)(a1 + 32), 1u);
  if ( Microsoft::WRL::gCausality )
  {
    v6 = *(_QWORD *)Microsoft::WRL::gCausality;
    v12 = 0;
    v11 = a1;
    v7 = *(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, _DWORD))(v6 + 64);
    v13 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
    v7(Microsoft::WRL::gCausality, 2, 2, &v13, a1, 0);
  }
  v8 = *(_DWORD *)(a1 + 56);
  v14 = -2;
  _InterlockedCompareExchange(&v14, v8, -2);
  if ( (unsigned int)(v14 - 1) <= 3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 128LL))(a1);
  return v4;
}

```

## disassembly

```asm
0x18000d310  mov     [rsp-18h+arg_8], rbx
0x18000d315  mov     [rsp-18h+arg_10], rsi
0x18000d31a  push    rbp
0x18000d31b  push    rdi
0x18000d31c  push    r14
0x18000d31e  mov     rbp, rsp
0x18000d321  sub     rsp, 60h
0x18000d325  mov     rax, cs:__security_cookie
0x18000d32c  xor     rax, rsp
0x18000d32f  mov     [rbp+var_8], rax
0x18000d333  mov     rbx, rcx
0x18000d336  mov     [rbp+var_10], 0FFFFFFFEh
0x18000d33d  mov     ecx, [rcx+38h]
0x18000d340  mov     rdi, rdx
0x18000d343  mov     eax, [rbp+var_10]
0x18000d346  lock cmpxchg [rbp+var_10], ecx
0x18000d34b  cmp     [rbp+var_10], 4
0x18000d34f  jnz     short loc_18000D35B
0x18000d351  mov     esi, 8000000Eh
0x18000d356  jmp     loc_18000D429
0x18000d35b  xor     eax, eax
0x18000d35d  lea     r14d, [rax+1]
0x18000d361  lock cmpxchg [rbx+14h], r14d
0x18000d367  jnz     loc_18000D424
0x18000d36d  xor     esi, esi
0x18000d36f  test    rdi, rdi
0x18000d372  jz      short loc_18000D37F
0x18000d374  mov     rax, [rdx]
0x18000d377  mov     rcx, [rax+18h]
0x18000d37b  mov     [rbx+28h], rcx
0x18000d37f  cmp     [rbx+18h], rdi
0x18000d383  jz      short loc_18000D3B2
0x18000d385  test    rdi, rdi
0x18000d388  jz      short loc_18000D399
0x18000d38a  mov     rax, [rdx]
0x18000d38d  mov     rcx, rdi
0x18000d390  mov     rax, [rax+8]
0x18000d394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d399  mov     rcx, [rbx+18h]
0x18000d39d  mov     [rbx+18h], rdi
0x18000d3a1  test    rcx, rcx
0x18000d3a4  jz      short loc_18000D3B2
0x18000d3a6  mov     rax, [rcx]
0x18000d3a9  mov     rax, [rax+10h]
0x18000d3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3b2  lock or [rsp+60h+var_60], esi
0x18000d3b6  lock add [rbx+20h], r14d
0x18000d3bb  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000d3c2  test    rcx, rcx
0x18000d3c5  jz      short loc_18000D3F4
0x18000d3c7  mov     rax, [rcx]
0x18000d3ca  lea     r9, [rbp+var_20]
0x18000d3ce  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000d3d5  mov     edx, 2
0x18000d3da  mov     [rsp+60h+var_38], esi
0x18000d3de  mov     r8d, edx
0x18000d3e1  mov     [rsp+60h+var_40], rbx
0x18000d3e6  mov     rax, [rax+40h]
0x18000d3ea  movdqu  [rbp+var_20], xmm0
0x18000d3ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3f4  mov     edx, [rbx+38h]
0x18000d3f7  mov     [rbp+var_10], 0FFFFFFFEh
0x18000d3fe  mov     eax, [rbp+var_10]
0x18000d401  lock cmpxchg [rbp+var_10], edx
0x18000d406  mov     edx, [rbp+var_10]
0x18000d409  dec     edx
0x18000d40b  cmp     edx, 3
0x18000d40e  ja      short loc_18000D433
0x18000d410  mov     rax, [rbx]
0x18000d413  mov     rcx, rbx
0x18000d416  mov     rax, [rax+80h]
0x18000d41d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d422  jmp     short loc_18000D433
0x18000d424  mov     esi, 80000018h
0x18000d429  xor     edx, edx
0x18000d42b  mov     ecx, esi
0x18000d42d  call    cs:__imp_RoOriginateError
0x18000d433  mov     eax, esi
0x18000d435  mov     rcx, [rbp+var_8]
0x18000d439  xor     rcx, rsp; StackCookie
0x18000d43c  call    __security_check_cookie
0x18000d441  lea     r11, [rsp+60h+var_s0]
0x18000d446  mov     rbx, [r11+28h]
0x18000d44a  mov     rsi, [r11+30h]
0x18000d44e  mov     rsp, r11
0x18000d451  pop     r14
0x18000d453  pop     rdi
0x18000d454  pop     rbp
0x18000d455  retn
```
