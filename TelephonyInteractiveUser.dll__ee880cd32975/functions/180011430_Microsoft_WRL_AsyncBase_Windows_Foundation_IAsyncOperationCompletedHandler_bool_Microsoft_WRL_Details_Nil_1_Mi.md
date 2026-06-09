# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::get_Status(ABI::Windows::Foundation::AsyncStatus *)

- ea: `0x180011430`
- end: `0x1800114b3`
- name: `?get_Status@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJPEAW4AsyncStatus@Foundation@Windows@ABI@@@Z`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x180011430`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180011487`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180011487`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::get_Status(
        __int64 a1,
        _DWORD *a2)
{
  signed __int32 v2; // r8d
  signed __int32 v3; // ecx
  unsigned int v4; // ebx
  signed __int32 v6; // [rsp+20h] [rbp-18h] BYREF
  signed __int32 v7; // [rsp+24h] [rbp-14h] BYREF

  v2 = *(_DWORD *)(a1 + 56);
  v7 = -2;
  _InterlockedCompareExchange(&v7, v2, -2);
  *a2 = v7;
  v3 = *(_DWORD *)(a1 + 56);
  v6 = -2;
  _InterlockedCompareExchange(&v6, v3, -2);
  if ( v6 == 4 )
  {
    v4 = -2147483634;
    RoOriginateError(2147483662LL);
  }
  else
  {
    v4 = 0;
    if ( v6 == -1 )
      return (unsigned int)-2147483623;
  }
  return v4;
}

```

## disassembly

```asm
0x180011430  mov     r11, rsp
0x180011433  push    rbx
0x180011434  sub     rsp, 30h
0x180011438  mov     rax, cs:__security_cookie
0x18001143f  xor     rax, rsp
0x180011442  mov     [rsp+38h+var_10], rax
0x180011447  mov     r8d, [rcx+38h]
0x18001144b  mov     r9d, 0FFFFFFFEh
0x180011451  mov     [r11-14h], r9d
0x180011455  mov     eax, [rsp+38h+var_14]
0x180011459  lock cmpxchg [r11-14h], r8d
0x18001145f  mov     r8d, [r11-14h]
0x180011463  mov     [rdx], r8d
0x180011466  mov     ecx, [rcx+38h]
0x180011469  mov     [r11-18h], r9d
0x18001146d  mov     eax, [rsp+38h+var_18]
0x180011471  lock cmpxchg [rsp+38h+var_18], ecx
0x180011477  cmp     [rsp+38h+var_18], 4
0x18001147c  jnz     short loc_18001148F
0x18001147e  mov     ebx, 8000000Eh
0x180011483  xor     edx, edx
0x180011485  mov     ecx, ebx
0x180011487  call    cs:__imp_RoOriginateError
0x18001148d  jmp     short loc_18001149E
0x18001148f  xor     ebx, ebx
0x180011491  mov     eax, 80000019h
0x180011496  cmp     [rsp+38h+var_18], 0FFFFFFFFh
0x18001149b  cmovz   ebx, eax
0x18001149e  mov     eax, ebx
0x1800114a0  mov     rcx, [rsp+38h+var_10]
0x1800114a5  xor     rcx, rsp; StackCookie
0x1800114a8  call    __security_check_cookie
0x1800114ad  add     rsp, 30h
0x1800114b1  pop     rbx
0x1800114b2  retn
```
