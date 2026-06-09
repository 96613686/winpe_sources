# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Close(void)

- ea: `0x180008de0`
- end: `0x180008e60`
- name: `?Close@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJXZ`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180001dc0`
- `0x180008de0`
- `0x18000f720`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008e45`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x180008e45`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Close(
        __int64 a1)
{
  int v1; // edx
  _DWORD *v2; // r10
  unsigned int v3; // ebx
  signed __int32 v4; // ecx
  signed __int32 v6; // [rsp+20h] [rbp-18h] BYREF

  if ( Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
         a1,
         4) )
  {
    v3 = 0;
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v2 + 144LL))(v2);
  }
  else
  {
    v4 = v2[14];
    v6 = -2;
    _InterlockedCompareExchange(&v6, v4, -2);
    if ( v6 == v1 )
    {
      return 0;
    }
    else
    {
      v3 = -2147483635;
      RoOriginateError(2147483661LL);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180008de0  push    rbx
0x180008de2  sub     rsp, 30h
0x180008de6  mov     rax, cs:__security_cookie
0x180008ded  xor     rax, rsp
0x180008df0  mov     [rsp+38h+var_10], rax
0x180008df5  mov     edx, 4
0x180008dfa  mov     r10, rcx
0x180008dfd  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x180008e02  test    al, al
0x180008e04  jz      short loc_180008E1C
0x180008e06  mov     rax, [r10]
0x180008e09  xor     ebx, ebx
0x180008e0b  mov     rcx, r10
0x180008e0e  mov     rax, [rax+90h]
0x180008e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e1a  jmp     short loc_180008E4B
0x180008e1c  mov     ecx, [r10+38h]
0x180008e20  mov     [rsp+38h+var_18], 0FFFFFFFEh
0x180008e28  mov     eax, [rsp+38h+var_18]
0x180008e2c  lock cmpxchg [rsp+38h+var_18], ecx
0x180008e32  cmp     [rsp+38h+var_18], edx
0x180008e36  jnz     short loc_180008E3C
0x180008e38  xor     ebx, ebx
0x180008e3a  jmp     short loc_180008E4B
0x180008e3c  mov     ebx, 8000000Dh
0x180008e41  xor     edx, edx
0x180008e43  mov     ecx, ebx
0x180008e45  call    cs:__imp_RoOriginateError
0x180008e4b  mov     eax, ebx
0x180008e4d  mov     rcx, [rsp+38h+var_10]
0x180008e52  xor     rcx, rsp; StackCookie
0x180008e55  call    __security_check_cookie
0x180008e5a  add     rsp, 30h
0x180008e5e  pop     rbx
0x180008e5f  retn
```
