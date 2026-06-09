# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)

- ea: `0x18000fa28`
- end: `0x18000fac7`
- name: `?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z`
- size: `159`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000cff0`
- `0x180010524`

## callees

- `0x18000f720`
- `0x18000fa28`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x18000fa62`
- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x18000fa62`

## pseudocode

```c
bool __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
        __int64 a1,
        signed __int32 a2)
{
  bool v2; // bl
  _QWORD *v4; // rbx
  __int64 v5; // rcx
  void (__fastcall *v6)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, int); // rax
  GUID v8; // [rsp+40h] [rbp-18h] BYREF

  v2 = 0;
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 60), a2, 0) )
  {
    v4 = (_QWORD *)(a1 + 48);
    v5 = *(_QWORD *)(a1 + 48);
    if ( v5 )
    {
      *v4 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    GetRestrictedErrorInfo(v4);
    v2 = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
           a1,
           3);
    if ( v2 && Microsoft::WRL::gCausality )
    {
      v6 = *(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, int))(*(_QWORD *)Microsoft::WRL::gCausality + 64LL);
      v8 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
      v6(Microsoft::WRL::gCausality, 2, 2, &v8, a1, 4);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18000fa28  mov     [rsp+arg_0], rbx
0x18000fa2d  push    rdi
0x18000fa2e  sub     rsp, 50h
0x18000fa32  xor     bl, bl
0x18000fa34  mov     rdi, rcx
0x18000fa37  xor     eax, eax
0x18000fa39  lock cmpxchg [rcx+3Ch], edx
0x18000fa3e  jnz     short loc_18000FABA
0x18000fa40  lea     rbx, [rcx+30h]
0x18000fa44  mov     rcx, [rbx]
0x18000fa47  test    rcx, rcx
0x18000fa4a  jz      short loc_18000FA5F
0x18000fa4c  mov     qword ptr [rbx], 0
0x18000fa53  mov     rax, [rcx]
0x18000fa56  mov     rax, [rax+10h]
0x18000fa5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa5f  mov     rcx, rbx
0x18000fa62  call    cs:__imp_GetRestrictedErrorInfo
0x18000fa68  mov     edx, 3
0x18000fa6d  mov     rcx, rdi
0x18000fa70  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x18000fa75  mov     bl, al
0x18000fa77  test    al, al
0x18000fa79  jz      short loc_18000FABA
0x18000fa7b  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000fa82  test    rcx, rcx
0x18000fa85  jz      short loc_18000FABA
0x18000fa87  mov     rdx, [rcx]
0x18000fa8a  lea     r9, [rsp+58h+var_18]
0x18000fa8f  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000fa96  mov     [rsp+58h+var_30], 4
0x18000fa9e  mov     [rsp+58h+var_38], rdi
0x18000faa3  mov     rax, [rdx+40h]
0x18000faa7  mov     edx, 2
0x18000faac  mov     r8d, edx
0x18000faaf  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm0
0x18000fab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000faba  mov     al, bl
0x18000fabc  mov     rbx, [rsp+58h+arg_0]
0x18000fac1  add     rsp, 50h
0x18000fac5  pop     rdi
0x18000fac6  retn
```
