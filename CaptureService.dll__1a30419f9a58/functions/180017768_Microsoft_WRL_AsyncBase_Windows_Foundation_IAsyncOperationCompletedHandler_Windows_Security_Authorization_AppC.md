# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)

- ea: `0x180017768`
- end: `0x1800177f2`
- name: `?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z`
- size: `138`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180012e30`
- `0x180017974`
- `0x180019bf0`
- `0x18001a198`

## callees

- `0x180007630`
- `0x180015ca4`
- `0x180017768`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x18001778d`
- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x18001778d`

## pseudocode

```c
bool __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
        __int64 a1,
        signed __int32 a2)
{
  bool v2; // bl
  void (__fastcall *v4)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, int); // rax
  GUID v6; // [rsp+40h] [rbp-18h] BYREF

  v2 = 0;
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 60), a2, 0) )
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)(a1 + 48));
    GetRestrictedErrorInfo(a1 + 48);
    v2 = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
           a1,
           3);
    if ( v2 )
    {
      if ( Microsoft::WRL::gCausality )
      {
        v4 = *(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, int))(*(_QWORD *)Microsoft::WRL::gCausality + 64LL);
        v6 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
        v4(Microsoft::WRL::gCausality, 2, 2, &v6, a1, 4);
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180017768  mov     [rsp+arg_0], rbx
0x18001776d  push    rdi
0x18001776e  sub     rsp, 50h
0x180017772  xor     bl, bl
0x180017774  mov     rdi, rcx
0x180017777  xor     eax, eax
0x180017779  lock cmpxchg [rcx+3Ch], edx
0x18001777e  jnz     short loc_1800177E5
0x180017780  add     rcx, 30h ; '0'
0x180017784  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017789  lea     rcx, [rdi+30h]
0x18001778d  call    cs:__imp_GetRestrictedErrorInfo
0x180017793  mov     edx, 3
0x180017798  mov     rcx, rdi
0x18001779b  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x1800177a0  mov     bl, al
0x1800177a2  test    al, al
0x1800177a4  jz      short loc_1800177E5
0x1800177a6  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1800177ad  test    rcx, rcx
0x1800177b0  jz      short loc_1800177E5
0x1800177b2  mov     rdx, [rcx]
0x1800177b5  lea     r9, [rsp+58h+var_18]
0x1800177ba  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x1800177c1  mov     [rsp+58h+var_30], 4
0x1800177c9  mov     [rsp+58h+var_38], rdi
0x1800177ce  mov     rax, [rdx+40h]
0x1800177d2  mov     edx, 2
0x1800177d7  mov     r8d, edx
0x1800177da  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm0
0x1800177e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800177e5  mov     al, bl
0x1800177e7  mov     rbx, [rsp+58h+arg_0]
0x1800177ec  add     rsp, 50h
0x1800177f0  pop     rdi
0x1800177f1  retn
```
