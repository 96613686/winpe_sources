# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnProgress(Windows::Internal::INilDelegate *)

- ea: `0x18000d7a0`
- end: `0x18000d904`
- name: `?PutOnProgress@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAUINilDelegate@23@@Z`
- size: `356`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x18000d7a0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000d7eb`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000d7eb`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18000d85f`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18000d85f`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::PutOnProgress(
        __int64 a1,
        __int64 a2)
{
  signed __int32 v2; // r8d
  unsigned int AgileReference; // ebx
  __int64 *v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rax
  void (__fastcall *v10)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, _DWORD); // rax
  signed __int32 v12[8]; // [rsp+0h] [rbp-68h] BYREF
  __int64 v13; // [rsp+20h] [rbp-48h]
  int v14; // [rsp+28h] [rbp-40h]
  GUID v15; // [rsp+40h] [rbp-28h] BYREF
  signed __int32 v16; // [rsp+50h] [rbp-18h] BYREF

  v2 = *(_DWORD *)(a1 + 56);
  v16 = -2;
  _InterlockedCompareExchange(&v16, v2, -2);
  if ( v16 == 4 )
  {
    AgileReference = -2147483634;
    RoOriginateError(2147483662LL);
  }
  else if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 164)) == 1 )
  {
    v6 = (__int64 *)(a1 + 144);
    v7 = *(_QWORD *)(a1 + 144);
    *v6 = 0;
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v8 = *v6;
    if ( a2 )
    {
      if ( v8 )
      {
        *v6 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      AgileReference = RoGetAgileReference(0, &GUID_2fafaaf9_2986_48ee_919d_98f66edf0a31, a2, v6);
      *(_QWORD *)(a1 + 152) = *(_QWORD *)(*(_QWORD *)a2 + 24LL);
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 160));
    }
    else
    {
      *v6 = 0;
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      AgileReference = 0;
    }
    _InterlockedOr(v12, 0);
    if ( Microsoft::WRL::gCausality )
    {
      v9 = *(_QWORD *)Microsoft::WRL::gCausality;
      v14 = 0;
      v13 = a1;
      v10 = *(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, _DWORD))(v9 + 64);
      v15 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
      v10(Microsoft::WRL::gCausality, 2, 2, &v15, a1, 0);
    }
  }
  else
  {
    return (unsigned int)-2147483624;
  }
  return AgileReference;
}

```

## disassembly

```asm
0x18000d7a0  mov     [rsp+arg_10], rbx
0x18000d7a5  mov     [rsp+arg_18], rsi
0x18000d7aa  push    rdi
0x18000d7ab  sub     rsp, 60h
0x18000d7af  mov     rax, cs:__security_cookie
0x18000d7b6  xor     rax, rsp
0x18000d7b9  mov     [rsp+68h+var_10], rax
0x18000d7be  mov     r8d, [rcx+38h]
0x18000d7c2  mov     rsi, rdx
0x18000d7c5  mov     [rsp+68h+var_18], 0FFFFFFFEh
0x18000d7cd  mov     rdi, rcx
0x18000d7d0  mov     eax, [rsp+68h+var_18]
0x18000d7d4  lock cmpxchg [rsp+68h+var_18], r8d
0x18000d7db  cmp     [rsp+68h+var_18], 4
0x18000d7e0  jnz     short loc_18000D7F6
0x18000d7e2  mov     ebx, 8000000Eh
0x18000d7e7  xor     edx, edx
0x18000d7e9  mov     ecx, ebx
0x18000d7eb  call    cs:__imp_RoOriginateError
0x18000d7f1  jmp     loc_18000D8E3
0x18000d7f6  mov     eax, 1
0x18000d7fb  lock xadd [rcx+0A4h], eax
0x18000d803  inc     eax
0x18000d805  cmp     eax, 1
0x18000d808  jnz     loc_18000D8DE
0x18000d80e  lea     rbx, [rcx+90h]
0x18000d815  mov     rcx, [rbx]
0x18000d818  mov     qword ptr [rbx], 0
0x18000d81f  test    rcx, rcx
0x18000d822  jz      short loc_18000D830
0x18000d824  mov     rax, [rcx]
0x18000d827  mov     rax, [rax+10h]
0x18000d82b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d830  mov     rcx, [rbx]
0x18000d833  test    rsi, rsi
0x18000d836  jz      short loc_18000D87E
0x18000d838  test    rcx, rcx
0x18000d83b  jz      short loc_18000D850
0x18000d83d  mov     qword ptr [rbx], 0
0x18000d844  mov     rax, [rcx]
0x18000d847  mov     rax, [rax+10h]
0x18000d84b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d850  mov     r9, rbx
0x18000d853  lea     rdx, _GUID_2fafaaf9_2986_48ee_919d_98f66edf0a31
0x18000d85a  mov     r8, rsi
0x18000d85d  xor     ecx, ecx
0x18000d85f  call    cs:__imp_RoGetAgileReference
0x18000d865  mov     ebx, eax
0x18000d867  mov     rax, [rsi]
0x18000d86a  mov     rcx, [rax+18h]
0x18000d86e  mov     [rdi+98h], rcx
0x18000d875  lock inc dword ptr [rdi+0A0h]
0x18000d87c  jmp     short loc_18000D898
0x18000d87e  mov     qword ptr [rbx], 0
0x18000d885  test    rcx, rcx
0x18000d888  jz      short loc_18000D896
0x18000d88a  mov     rax, [rcx]
0x18000d88d  mov     rax, [rax+10h]
0x18000d891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d896  xor     ebx, ebx
0x18000d898  lock or [rsp+68h+var_68], 0
0x18000d89d  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000d8a4  test    rcx, rcx
0x18000d8a7  jz      short loc_18000D8E3
0x18000d8a9  mov     rax, [rcx]
0x18000d8ac  lea     r9, [rsp+68h+var_28]
0x18000d8b1  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000d8b8  mov     edx, 2
0x18000d8bd  mov     [rsp+68h+var_40], 0
0x18000d8c5  mov     r8d, edx
0x18000d8c8  mov     [rsp+68h+var_48], rdi
0x18000d8cd  mov     rax, [rax+40h]
0x18000d8d1  movdqu  [rsp+68h+var_28], xmm0
0x18000d8d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8dc  jmp     short loc_18000D8E3
0x18000d8de  mov     ebx, 80000018h
0x18000d8e3  mov     eax, ebx
0x18000d8e5  mov     rcx, [rsp+68h+var_10]
0x18000d8ea  xor     rcx, rsp; StackCookie
0x18000d8ed  call    __security_check_cookie
0x18000d8f2  lea     r11, [rsp+68h+var_8]
0x18000d8f7  mov     rbx, [r11+20h]
0x18000d8fb  mov     rsi, [r11+28h]
0x18000d8ff  mov     rsp, r11
0x18000d902  pop     rdi
0x18000d903  retn
```
