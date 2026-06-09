# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(void)

- ea: `0x18000f610`
- end: `0x18000f68f`
- name: `?TraceOperationComplete@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `127`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800072e8`
- `0x180007880`
- `0x180009720`
- `0x180009bc0`

## callees

- `0x180001dc0`
- `0x18000f610`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationComplete(
        __int64 a1)
{
  signed __int32 v1; // edx
  __int64 v2; // rax
  __int64 result; // rax
  GUID v4; // [rsp+40h] [rbp-28h] BYREF
  signed __int32 v5; // [rsp+50h] [rbp-18h] BYREF

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
0x18000f610  sub     rsp, 68h
0x18000f614  mov     rax, cs:__security_cookie
0x18000f61b  xor     rax, rsp
0x18000f61e  mov     [rsp+68h+var_10], rax
0x18000f623  cmp     cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA, 0; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000f62b  mov     r8, rcx
0x18000f62e  jz      short loc_18000F67D
0x18000f630  mov     edx, [rcx+38h]
0x18000f633  mov     [rsp+68h+var_18], 0
0x18000f63b  mov     eax, [rsp+68h+var_18]
0x18000f63f  lock cmpxchg [rsp+68h+var_18], edx
0x18000f645  mov     edx, [rsp+68h+var_18]
0x18000f649  lea     r9, [rsp+68h+var_28]
0x18000f64e  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000f655  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000f65c  mov     [rsp+68h+var_40], edx
0x18000f660  xor     edx, edx
0x18000f662  mov     [rsp+68h+var_48], r8
0x18000f667  mov     rax, [rcx]
0x18000f66a  movdqu  [rsp+68h+var_28], xmm0
0x18000f670  lea     r8d, [rdx+2]
0x18000f674  mov     rax, [rax+38h]
0x18000f678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f67d  mov     rcx, [rsp+68h+var_10]
0x18000f682  xor     rcx, rsp; StackCookie
0x18000f685  call    __security_check_cookie
0x18000f68a  add     rsp, 68h
0x18000f68e  retn
```
