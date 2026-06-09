# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)

- ea: `0x180015b80`
- end: `0x180015be3`
- name: `?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `99`
- prototype: `__int64(void)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000d970`
- `0x18000fe60`
- `0x18000ff50`
- `0x18001932c`
- `0x180019720`
- `0x180019810`

## callees

- `0x180015b80`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(
        __int64 a1)
{
  signed __int32 v1; // edx
  __int64 v2; // rax
  __int64 result; // rax
  GUID v4; // [rsp+40h] [rbp-18h] BYREF
  signed __int32 v5; // [rsp+68h] [rbp+10h] BYREF

  if ( Microsoft::WRL::gCausality )
  {
    v1 = *(_DWORD *)(a1 + 56);
    v5 = 0;
    _InterlockedCompareExchange(&v5, v1, 0);
    v2 = *(_QWORD *)Microsoft::WRL::gCausality;
    v4 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
    return (*(__int64 (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, __int64, signed __int32))(v2 + 56))(
             Microsoft::WRL::gCausality,
             0,
             2,
             &v4,
             a1,
             v5);
  }
  return result;
}

```

## disassembly

```asm
0x180015b80  sub     rsp, 58h
0x180015b84  cmp     cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA, 0; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180015b8c  mov     r8, rcx
0x180015b8f  jz      short loc_180015BDE
0x180015b91  mov     edx, [rcx+38h]
0x180015b94  mov     [rsp+58h+arg_8], 0
0x180015b9c  mov     eax, [rsp+58h+arg_8]
0x180015ba0  lock cmpxchg [rsp+58h+arg_8], edx
0x180015ba6  mov     edx, [rsp+58h+arg_8]
0x180015baa  lea     r9, [rsp+58h+var_18]
0x180015baf  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180015bb6  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180015bbd  mov     [rsp+58h+var_30], edx
0x180015bc1  xor     edx, edx
0x180015bc3  mov     [rsp+58h+var_38], r8
0x180015bc8  mov     rax, [rcx]
0x180015bcb  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm0
0x180015bd1  lea     r8d, [rdx+2]
0x180015bd5  mov     rax, [rax+38h]
0x180015bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bde  add     rsp, 58h
0x180015be2  retn
```
