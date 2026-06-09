# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::CBasicResult<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(long)

- ea: `0x18001a198`
- end: `0x18001a238`
- name: `?_AfterExecute@?$AsyncOperation@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@23@V?$CBasicResult@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@$02@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXJ@Z`
- size: `160`
- prototype: `__int64 __fastcall(volatile signed __int32 *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180019670`
- `0x18001a240`

## callees

- `0x180015ca4`
- `0x180017768`
- `0x18001a140`
- `0x18001a198`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::CBasicResult<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(
        volatile signed __int32 *a1,
        int a2)
{
  bool v4; // di
  volatile signed __int32 *v5; // rcx
  signed __int32 v6; // edx
  __int64 result; // rax
  signed __int32 v8; // edx
  signed __int32 v9; // [rsp+38h] [rbp+10h] BYREF

  v4 = _InterlockedExchangeAdd(a1 + 65, 0xFFFFFFFF) == 1;
  if ( _InterlockedIncrement(a1 + 63) == 1 )
    v4 = _InterlockedExchangeAdd(a1 + 65, 0xFFFFFFFF) == 1;
  v5 = a1 + 2;
  if ( a2 >= 0 )
  {
    result = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(v5);
    if ( !(_BYTE)result )
      result = (unsigned int)_InterlockedCompareExchange(a1 + 16, v8, 2);
  }
  else
  {
    v6 = *((_DWORD *)a1 + 16);
    v9 = -2;
    result = (unsigned int)_InterlockedCompareExchange(&v9, v6, -2);
    if ( v9 != 2 )
      result = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
                 v5,
                 (unsigned int)a2);
  }
  if ( v4 )
    return Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::CBasicResult<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete((__int64)a1);
  return result;
}

```

## disassembly

```asm
0x18001a198  mov     [rsp+arg_0], rbx
0x18001a19d  push    rdi
0x18001a19e  sub     rsp, 20h
0x18001a1a2  mov     rbx, rcx
0x18001a1a5  mov     r8d, edx
0x18001a1a8  or      ecx, 0FFFFFFFFh
0x18001a1ab  mov     eax, ecx
0x18001a1ad  lock xadd [rbx+104h], eax
0x18001a1b5  add     eax, ecx
0x18001a1b7  lea     edx, [rcx+2]
0x18001a1ba  mov     eax, edx
0x18001a1bc  setz    dil
0x18001a1c0  lock xadd [rbx+0FCh], eax
0x18001a1c8  add     eax, edx
0x18001a1ca  cmp     eax, edx
0x18001a1cc  jnz     short loc_18001A1DE
0x18001a1ce  mov     eax, ecx
0x18001a1d0  lock xadd [rbx+104h], eax
0x18001a1d8  add     eax, ecx
0x18001a1da  setz    dil
0x18001a1de  lea     rcx, [rbx+8]
0x18001a1e2  test    r8d, r8d
0x18001a1e5  jns     short loc_18001A20D
0x18001a1e7  mov     edx, [rcx+38h]
0x18001a1ea  mov     [rsp+28h+arg_8], 0FFFFFFFEh
0x18001a1f2  mov     eax, [rsp+28h+arg_8]
0x18001a1f6  lock cmpxchg [rsp+28h+arg_8], edx
0x18001a1fc  cmp     [rsp+28h+arg_8], 2
0x18001a201  jz      short loc_18001A220
0x18001a203  mov     edx, r8d
0x18001a206  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x18001a20b  jmp     short loc_18001A220
0x18001a20d  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x18001a212  test    al, al
0x18001a214  jnz     short loc_18001A220
0x18001a216  mov     eax, 2
0x18001a21b  lock cmpxchg [rbx+40h], edx
0x18001a220  test    dil, dil
0x18001a223  jz      short loc_18001A22D
0x18001a225  mov     rcx, rbx
0x18001a228  call    ?_AfterComplete@?$AsyncOperation@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@23@V?$CBasicResult@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@$02@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Internal::CBasicResult<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,3>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)
0x18001a22d  mov     rbx, [rsp+28h+arg_0]
0x18001a232  add     rsp, 20h
0x18001a236  pop     rdi
0x18001a237  retn
```
