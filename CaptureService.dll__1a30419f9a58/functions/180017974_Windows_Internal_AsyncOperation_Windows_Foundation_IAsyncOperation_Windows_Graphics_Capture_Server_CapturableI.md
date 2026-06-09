# Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Graphics::Capture::Server::ICapturableItem>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(long)

- ea: `0x180017974`
- end: `0x180017a14`
- name: `?_AfterExecute@?$AsyncOperation@U?$IAsyncOperation@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@23@V?$CMarshaledInterfaceResult@UICapturableItem@Server@Capture@Graphics@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXJ@Z`
- size: `160`
- prototype: `__int64 __fastcall(volatile signed __int32 *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000f5e0`
- `0x180017c6c`

## callees

- `0x180015ca4`
- `0x180017768`
- `0x18001791c`
- `0x180017974`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Graphics::Capture::Server::ICapturableItem>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterExecute(
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
    return Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Graphics::Capture::Server::ICapturableItem>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete((__int64)a1);
  return result;
}

```

## disassembly

```asm
0x180017974  mov     [rsp+arg_0], rbx
0x180017979  push    rdi
0x18001797a  sub     rsp, 20h
0x18001797e  mov     rbx, rcx
0x180017981  mov     r8d, edx
0x180017984  or      ecx, 0FFFFFFFFh
0x180017987  mov     eax, ecx
0x180017989  lock xadd [rbx+104h], eax
0x180017991  add     eax, ecx
0x180017993  lea     edx, [rcx+2]
0x180017996  mov     eax, edx
0x180017998  setz    dil
0x18001799c  lock xadd [rbx+0FCh], eax
0x1800179a4  add     eax, edx
0x1800179a6  cmp     eax, edx
0x1800179a8  jnz     short loc_1800179BA
0x1800179aa  mov     eax, ecx
0x1800179ac  lock xadd [rbx+104h], eax
0x1800179b4  add     eax, ecx
0x1800179b6  setz    dil
0x1800179ba  lea     rcx, [rbx+8]
0x1800179be  test    r8d, r8d
0x1800179c1  jns     short loc_1800179E9
0x1800179c3  mov     edx, [rcx+38h]
0x1800179c6  mov     [rsp+28h+arg_8], 0FFFFFFFEh
0x1800179ce  mov     eax, [rsp+28h+arg_8]
0x1800179d2  lock cmpxchg [rsp+28h+arg_8], edx
0x1800179d8  cmp     [rsp+28h+arg_8], 2
0x1800179dd  jz      short loc_1800179FC
0x1800179df  mov     edx, r8d
0x1800179e2  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x1800179e7  jmp     short loc_1800179FC
0x1800179e9  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x1800179ee  test    al, al
0x1800179f0  jnz     short loc_1800179FC
0x1800179f2  mov     eax, 2
0x1800179f7  lock cmpxchg [rbx+40h], edx
0x1800179fc  test    dil, dil
0x1800179ff  jz      short loc_180017A09
0x180017a01  mov     rcx, rbx
0x180017a04  call    ?_AfterComplete@?$AsyncOperation@U?$IAsyncOperation@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVCapturableItem@Server@Capture@Graphics@Windows@@@23@V?$CMarshaledInterfaceResult@UICapturableItem@Server@Capture@Graphics@Windows@@@Internal@3@VComTaskPoolHandler@63@UINilDelegate@63@U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@AEAAXXZ; Windows::Internal::AsyncOperation<Windows::Foundation::IAsyncOperation<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Graphics::Capture::Server::CapturableItem *>,Windows::Internal::CMarshaledInterfaceResult<Windows::Graphics::Capture::Server::ICapturableItem>,Windows::Internal::ComTaskPoolHandler,Windows::Internal::INilDelegate,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::_AfterComplete(void)
0x180017a09  mov     rbx, [rsp+28h+arg_0]
0x180017a0e  add     rsp, 20h
0x180017a12  pop     rdi
0x180017a13  retn
```
