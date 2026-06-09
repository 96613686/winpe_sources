# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::get_Id(uint *)

- ea: `0x180011310`
- end: `0x18001137b`
- name: `?get_Id@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJPEAI@Z`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x180011310`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001134f`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18001134f`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::get_Id(
        __int64 a1,
        _DWORD *a2)
{
  signed __int32 v2; // ecx
  unsigned int v3; // ebx
  signed __int32 v5; // [rsp+20h] [rbp-18h] BYREF

  *a2 = *(_DWORD *)(a1 + 64);
  v2 = *(_DWORD *)(a1 + 56);
  v5 = -2;
  _InterlockedCompareExchange(&v5, v2, -2);
  if ( v5 == 4 )
  {
    v3 = -2147483634;
    RoOriginateError(2147483662LL);
  }
  else
  {
    v3 = 0;
    if ( v5 == -1 )
      return (unsigned int)-2147483623;
  }
  return v3;
}

```

## disassembly

```asm
0x180011310  push    rbx
0x180011312  sub     rsp, 30h
0x180011316  mov     rax, cs:__security_cookie
0x18001131d  xor     rax, rsp
0x180011320  mov     [rsp+38h+var_10], rax
0x180011325  mov     eax, [rcx+40h]
0x180011328  mov     [rdx], eax
0x18001132a  mov     ecx, [rcx+38h]
0x18001132d  mov     [rsp+38h+var_18], 0FFFFFFFEh
0x180011335  mov     eax, [rsp+38h+var_18]
0x180011339  lock cmpxchg [rsp+38h+var_18], ecx
0x18001133f  cmp     [rsp+38h+var_18], 4
0x180011344  jnz     short loc_180011357
0x180011346  mov     ebx, 8000000Eh
0x18001134b  xor     edx, edx
0x18001134d  mov     ecx, ebx
0x18001134f  call    cs:__imp_RoOriginateError
0x180011355  jmp     short loc_180011366
0x180011357  xor     ebx, ebx
0x180011359  mov     eax, 80000019h
0x18001135e  cmp     [rsp+38h+var_18], 0FFFFFFFFh
0x180011363  cmovz   ebx, eax
0x180011366  mov     eax, ebx
0x180011368  mov     rcx, [rsp+38h+var_10]
0x18001136d  xor     rcx, rsp; StackCookie
0x180011370  call    __security_check_cookie
0x180011375  add     rsp, 30h
0x180011379  pop     rbx
0x18001137a  retn
```
