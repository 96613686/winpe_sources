# Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetOnProgress(Windows::Internal::INilDelegate * *)

- ea: `0x18000b240`
- end: `0x18000b342`
- name: `?GetOnProgress@?$AsyncBaseWithProgressFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@UINilDelegate@Internal@3@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAPEAUINilDelegate@23@@Z`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x18000b240`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b28b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b28b`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseWithProgressFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::INilDelegate,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetOnProgress(
        __int64 a1,
        _QWORD *a2)
{
  signed __int32 v3; // edx
  unsigned int v5; // edi
  signed __int32 v6; // eax
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  signed __int32 v11[8]; // [rsp+0h] [rbp-38h] BYREF
  signed __int32 v12; // [rsp+20h] [rbp-18h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)(a1 + 56);
  v12 = -2;
  _InterlockedCompareExchange(&v12, v3, -2);
  if ( v12 == 4 )
  {
    v5 = -2147483634;
    RoOriginateError(2147483662LL);
  }
  else
  {
    v6 = *(_DWORD *)(a1 + 160);
    v5 = 0;
    while ( v6 > 0 )
    {
      if ( v6 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 160), v6 + 1, v6) )
      {
        v7 = *(_QWORD *)(a1 + 144);
        *a2 = 0;
        if ( v7 )
        {
          v8 = *(_QWORD *)(a1 + 144);
          if ( v8 )
            v5 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v8 + 24LL))(
                   v8,
                   &GUID_2fafaaf9_2986_48ee_919d_98f66edf0a31);
        }
        else
        {
          v5 = -2147024809;
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 160), 0xFFFFFFFF) == 1 )
        {
          _InterlockedOr(v11, 0);
          v9 = *(_QWORD *)(a1 + 144);
          *(_QWORD *)(a1 + 144) = 0;
          if ( v9 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        }
        return v5;
      }
      v6 = *(_DWORD *)(a1 + 160);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000b240  mov     [rsp+arg_10], rbx
0x18000b245  push    rdi
0x18000b246  sub     rsp, 30h
0x18000b24a  mov     rax, cs:__security_cookie
0x18000b251  xor     rax, rsp
0x18000b254  mov     [rsp+38h+var_10], rax
0x18000b259  mov     r8, rdx
0x18000b25c  mov     qword ptr [rdx], 0
0x18000b263  mov     edx, [rcx+38h]
0x18000b266  mov     rbx, rcx
0x18000b269  mov     [rsp+38h+var_18], 0FFFFFFFEh
0x18000b271  mov     eax, [rsp+38h+var_18]
0x18000b275  lock cmpxchg [rsp+38h+var_18], edx
0x18000b27b  cmp     [rsp+38h+var_18], 4
0x18000b280  jnz     short loc_18000B296
0x18000b282  mov     edi, 8000000Eh
0x18000b287  xor     edx, edx
0x18000b289  mov     ecx, edi
0x18000b28b  call    cs:__imp_RoOriginateError
0x18000b291  jmp     loc_18000B328
0x18000b296  mov     eax, [rcx+0A0h]
0x18000b29c  xor     edi, edi
0x18000b29e  jmp     short loc_18000B2B3
0x18000b2a0  lea     ecx, [rax+1]
0x18000b2a3  lock cmpxchg [rbx+0A0h], ecx
0x18000b2ab  jz      short loc_18000B2B9
0x18000b2ad  mov     eax, [rbx+0A0h]
0x18000b2b3  test    eax, eax
0x18000b2b5  jg      short loc_18000B2A0
0x18000b2b7  jmp     short loc_18000B328
0x18000b2b9  mov     rax, [rbx+90h]
0x18000b2c0  mov     [r8], rdi
0x18000b2c3  test    rax, rax
0x18000b2c6  jz      short loc_18000B2EB
0x18000b2c8  mov     rcx, [rbx+90h]
0x18000b2cf  test    rcx, rcx
0x18000b2d2  jz      short loc_18000B2F0
0x18000b2d4  mov     rax, [rcx]
0x18000b2d7  lea     rdx, _GUID_2fafaaf9_2986_48ee_919d_98f66edf0a31
0x18000b2de  mov     rax, [rax+18h]
0x18000b2e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2e7  mov     edi, eax
0x18000b2e9  jmp     short loc_18000B2F0
0x18000b2eb  mov     edi, 80070057h
0x18000b2f0  or      eax, 0FFFFFFFFh
0x18000b2f3  lock xadd [rbx+0A0h], eax
0x18000b2fb  cmp     eax, 1
0x18000b2fe  jnz     short loc_18000B328
0x18000b300  lock or [rsp+38h+var_38], 0
0x18000b305  mov     rcx, [rbx+90h]
0x18000b30c  mov     qword ptr [rbx+90h], 0
0x18000b317  test    rcx, rcx
0x18000b31a  jz      short loc_18000B328
0x18000b31c  mov     rdx, [rcx]
0x18000b31f  mov     rax, [rdx+10h]
0x18000b323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b328  mov     eax, edi
0x18000b32a  mov     rcx, [rsp+38h+var_10]
0x18000b32f  xor     rcx, rsp; StackCookie
0x18000b332  call    __security_check_cookie
0x18000b337  mov     rbx, [rsp+38h+arg_10]
0x18000b33c  add     rsp, 30h
0x18000b340  pop     rdi
0x18000b341  retn
```
