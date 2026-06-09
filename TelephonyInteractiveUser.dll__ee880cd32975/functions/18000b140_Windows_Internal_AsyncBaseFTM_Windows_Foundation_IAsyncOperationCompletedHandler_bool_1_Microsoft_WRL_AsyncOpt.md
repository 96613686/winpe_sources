# Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetOnComplete(Windows::Foundation::IAsyncOperationCompletedHandler<bool> * *)

- ea: `0x18000b140`
- end: `0x18000b236`
- name: `?GetOnComplete@?$AsyncBaseFTM@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@UEAAJPEAPEAU?$IAsyncOperationCompletedHandler@_N@Foundation@3@@Z`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800110e0`

## callees

- `0x180001dc0`
- `0x18000b140`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b18b`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000b18b`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::GetOnComplete(
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
    v6 = *(_DWORD *)(a1 + 136);
    v5 = 0;
    while ( v6 > 0 )
    {
      if ( v6 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 136), v6 + 1, v6) )
      {
        v7 = *(_QWORD *)(a1 + 120);
        *a2 = 0;
        if ( v7 )
        {
          v8 = *(_QWORD *)(a1 + 120);
          if ( v8 )
            v5 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v8 + 24LL))(
                   v8,
                   &GUID_c1d3d1a2_ae17_5a5f_b5a2_bdcc8844889a);
        }
        else
        {
          v5 = -2147024809;
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 136), 0xFFFFFFFF) == 1 )
        {
          _InterlockedOr(v11, 0);
          v9 = *(_QWORD *)(a1 + 120);
          *(_QWORD *)(a1 + 120) = 0;
          if ( v9 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        }
        return v5;
      }
      v6 = *(_DWORD *)(a1 + 136);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000b140  mov     [rsp+arg_10], rbx
0x18000b145  push    rdi
0x18000b146  sub     rsp, 30h
0x18000b14a  mov     rax, cs:__security_cookie
0x18000b151  xor     rax, rsp
0x18000b154  mov     [rsp+38h+var_10], rax
0x18000b159  mov     r8, rdx
0x18000b15c  mov     qword ptr [rdx], 0
0x18000b163  mov     edx, [rcx+38h]
0x18000b166  mov     rbx, rcx
0x18000b169  mov     [rsp+38h+var_18], 0FFFFFFFEh
0x18000b171  mov     eax, [rsp+38h+var_18]
0x18000b175  lock cmpxchg [rsp+38h+var_18], edx
0x18000b17b  cmp     [rsp+38h+var_18], 4
0x18000b180  jnz     short loc_18000B196
0x18000b182  mov     edi, 8000000Eh
0x18000b187  xor     edx, edx
0x18000b189  mov     ecx, edi
0x18000b18b  call    cs:__imp_RoOriginateError
0x18000b191  jmp     loc_18000B21C
0x18000b196  mov     eax, [rcx+88h]
0x18000b19c  xor     edi, edi
0x18000b19e  jmp     short loc_18000B1B3
0x18000b1a0  lea     ecx, [rax+1]
0x18000b1a3  lock cmpxchg [rbx+88h], ecx
0x18000b1ab  jz      short loc_18000B1B9
0x18000b1ad  mov     eax, [rbx+88h]
0x18000b1b3  test    eax, eax
0x18000b1b5  jg      short loc_18000B1A0
0x18000b1b7  jmp     short loc_18000B21C
0x18000b1b9  mov     rax, [rbx+78h]
0x18000b1bd  mov     [r8], rdi
0x18000b1c0  test    rax, rax
0x18000b1c3  jz      short loc_18000B1E5
0x18000b1c5  mov     rcx, [rbx+78h]
0x18000b1c9  test    rcx, rcx
0x18000b1cc  jz      short loc_18000B1EA
0x18000b1ce  mov     rax, [rcx]
0x18000b1d1  lea     rdx, _GUID_c1d3d1a2_ae17_5a5f_b5a2_bdcc8844889a
0x18000b1d8  mov     rax, [rax+18h]
0x18000b1dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1e1  mov     edi, eax
0x18000b1e3  jmp     short loc_18000B1EA
0x18000b1e5  mov     edi, 80070057h
0x18000b1ea  or      eax, 0FFFFFFFFh
0x18000b1ed  lock xadd [rbx+88h], eax
0x18000b1f5  cmp     eax, 1
0x18000b1f8  jnz     short loc_18000B21C
0x18000b1fa  lock or [rsp+38h+var_38], 0
0x18000b1ff  mov     rcx, [rbx+78h]
0x18000b203  mov     qword ptr [rbx+78h], 0
0x18000b20b  test    rcx, rcx
0x18000b20e  jz      short loc_18000B21C
0x18000b210  mov     rdx, [rcx]
0x18000b213  mov     rax, [rdx+10h]
0x18000b217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b21c  mov     eax, edi
0x18000b21e  mov     rcx, [rsp+38h+var_10]
0x18000b223  xor     rcx, rsp; StackCookie
0x18000b226  call    __security_check_cookie
0x18000b22b  mov     rbx, [rsp+38h+arg_10]
0x18000b230  add     rsp, 30h
0x18000b234  pop     rdi
0x18000b235  retn
```
