# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<uchar,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(long)

- ea: `0x180010524`
- end: `0x1800105e5`
- name: `?_AfterExecute@?$AsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@V?$CBasicResult@E$0A@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXJ@Z`
- size: `193`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180008e70`
- `0x18000cff0`
- `0x18000ed40`
- `0x180010c40`

## callees

- `0x180001dc0`
- `0x18000f720`
- `0x18000fa28`
- `0x180010478`
- `0x180010524`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<unsigned char,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(
        volatile signed __int32 *a1,
        __int64 a2)
{
  bool v3; // di
  signed __int32 v4; // ecx
  __int64 result; // rax
  signed __int32 v6; // r10d
  signed __int32 v7; // [rsp+20h] [rbp-18h] BYREF

  v3 = _InterlockedExchangeAdd(a1 + 65, 0xFFFFFFFF) == 1;
  if ( _InterlockedIncrement(a1 + 63) == 1 )
    v3 = _InterlockedExchangeAdd(a1 + 65, 0xFFFFFFFF) == 1;
  if ( (int)a2 >= 0 )
  {
    result = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
               a1 + 2,
               1);
    if ( !(_BYTE)result )
      result = (unsigned int)_InterlockedCompareExchange(a1 + 16, v6, 2);
  }
  else
  {
    v4 = *((_DWORD *)a1 + 16);
    v7 = -2;
    result = (unsigned int)_InterlockedCompareExchange(&v7, v4, -2);
    if ( v7 != 2 )
      result = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
                 a1 + 2,
                 a2);
  }
  if ( v3 )
    return Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<unsigned char,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete((__int64)a1);
  return result;
}

```

## disassembly

```asm
0x180010524  mov     [rsp+arg_10], rbx
0x180010529  push    rdi
0x18001052a  sub     rsp, 30h
0x18001052e  mov     rax, cs:__security_cookie
0x180010535  xor     rax, rsp
0x180010538  mov     [rsp+38h+var_10], rax
0x18001053d  mov     rbx, rcx
0x180010540  or      ecx, 0FFFFFFFFh
0x180010543  mov     eax, ecx
0x180010545  lock xadd [rbx+104h], eax
0x18001054d  add     eax, ecx
0x18001054f  lea     r10d, [rcx+2]
0x180010553  mov     eax, r10d
0x180010556  setz    dil
0x18001055a  lock xadd [rbx+0FCh], eax
0x180010562  add     eax, r10d
0x180010565  cmp     eax, r10d
0x180010568  jnz     short loc_18001057A
0x18001056a  mov     eax, ecx
0x18001056c  lock xadd [rbx+104h], eax
0x180010574  add     eax, ecx
0x180010576  setz    dil
0x18001057a  test    edx, edx
0x18001057c  jns     short loc_1800105A5
0x18001057e  mov     ecx, [rbx+40h]
0x180010581  mov     [rsp+38h+var_18], 0FFFFFFFEh
0x180010589  mov     eax, [rsp+38h+var_18]
0x18001058d  lock cmpxchg [rsp+38h+var_18], ecx
0x180010593  cmp     [rsp+38h+var_18], 2
0x180010598  jz      short loc_1800105C0
0x18001059a  lea     rcx, [rbx+8]
0x18001059e  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x1800105a3  jmp     short loc_1800105C0
0x1800105a5  mov     edx, r10d
0x1800105a8  lea     rcx, [rbx+8]
0x1800105ac  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x1800105b1  test    al, al
0x1800105b3  jnz     short loc_1800105C0
0x1800105b5  mov     eax, 2
0x1800105ba  lock cmpxchg [rbx+40h], r10d
0x1800105c0  test    dil, dil
0x1800105c3  jz      short loc_1800105CD
0x1800105c5  mov     rcx, rbx
0x1800105c8  call    ?_AfterComplete@?$AsyncOperation@U?$IAsyncOperation@_N@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@_N@23@V?$CBasicResult@E$0A@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<bool>,Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Windows::Internal::CBasicResult<uchar,0>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)
0x1800105cd  mov     rcx, [rsp+38h+var_10]
0x1800105d2  xor     rcx, rsp; StackCookie
0x1800105d5  call    __security_check_cookie
0x1800105da  mov     rbx, [rsp+38h+arg_10]
0x1800105df  add     rsp, 30h
0x1800105e3  pop     rdi
0x1800105e4  retn
```
