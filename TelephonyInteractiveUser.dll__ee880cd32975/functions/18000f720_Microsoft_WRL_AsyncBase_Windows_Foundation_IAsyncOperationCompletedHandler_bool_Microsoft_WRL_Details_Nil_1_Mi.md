# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)

- ea: `0x18000f720`
- end: `0x18000f7a1`
- name: `?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z`
- size: `129`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008a70`
- `0x180008de0`
- `0x180009720`
- `0x180009bc0`
- `0x18000f2f0`
- `0x18000fa28`
- `0x180010524`

## callees

- `0x180001dc0`
- `0x18000f720`

## pseudocode

```c
bool __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
        __int64 a1,
        signed __int32 a2)
{
  signed __int32 v2; // r8d
  signed __int32 v4; // ecx
  signed __int32 v6; // [rsp+0h] [rbp-18h] BYREF

  v2 = *(_DWORD *)(a1 + 56);
  v6 = -2;
  _InterlockedCompareExchange(&v6, v2, -2);
  switch ( a2 )
  {
    case 0:
      v4 = v6;
      if ( v6 != -1 )
        return 0;
      return v4 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 56), a2, v4);
    case 1:
    case 2:
    case 3:
      v4 = v6;
      if ( v6 )
        return 0;
      return v4 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 56), a2, v4);
    case 4:
      v4 = v6;
      if ( (unsigned int)(v6 - 1) <= 3 )
        return v4 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 56), a2, v4);
      break;
  }
  return 0;
}

```

## disassembly

```asm
0x18000f720  sub     rsp, 18h
0x18000f724  mov     rax, cs:__security_cookie
0x18000f72b  xor     rax, rsp
0x18000f72e  mov     [rsp+18h+var_10], rax
0x18000f733  mov     r8d, [rcx+38h]
0x18000f737  mov     r9, rcx
0x18000f73a  mov     [rsp+18h+var_18], 0FFFFFFFEh
0x18000f741  mov     eax, [rsp+18h+var_18]
0x18000f744  lock cmpxchg [rsp+18h+var_18], r8d
0x18000f74a  mov     eax, edx
0x18000f74c  test    edx, edx
0x18000f74e  jz      short loc_18000F795
0x18000f750  sub     eax, 1
0x18000f753  jz      short loc_18000F78C
0x18000f755  sub     eax, 1
0x18000f758  jz      short loc_18000F78C
0x18000f75a  sub     eax, 1
0x18000f75d  jz      short loc_18000F78C
0x18000f75f  cmp     eax, 1
0x18000f762  jnz     short loc_18000F79D
0x18000f764  mov     ecx, [rsp+18h+var_18]
0x18000f767  lea     eax, [rcx-1]
0x18000f76a  cmp     eax, 3
0x18000f76d  ja      short loc_18000F79D
0x18000f76f  mov     eax, ecx
0x18000f771  lock cmpxchg [r9+38h], edx
0x18000f777  setz    al
0x18000f77a  mov     rcx, [rsp+18h+var_10]
0x18000f77f  xor     rcx, rsp; StackCookie
0x18000f782  call    __security_check_cookie
0x18000f787  add     rsp, 18h
0x18000f78b  retn
0x18000f78c  mov     ecx, [rsp+18h+var_18]
0x18000f78f  test    ecx, ecx
0x18000f791  jnz     short loc_18000F79D
0x18000f793  jmp     short loc_18000F76F
0x18000f795  mov     ecx, [rsp+18h+var_18]
0x18000f798  cmp     ecx, 0FFFFFFFFh
0x18000f79b  jz      short loc_18000F76F
0x18000f79d  xor     al, al
0x18000f79f  jmp     short loc_18000F77A
```
