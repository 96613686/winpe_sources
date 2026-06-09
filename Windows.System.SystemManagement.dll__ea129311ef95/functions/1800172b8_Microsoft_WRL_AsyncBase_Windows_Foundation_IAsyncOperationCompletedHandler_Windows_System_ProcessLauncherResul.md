# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::ProcessLauncherResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)

- ea: `0x1800172b8`
- end: `0x180017342`
- name: `?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVProcessLauncherResult@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z`
- size: `138`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800160f0`
- `0x180017478`
- `0x180019d90`
- `0x18001bfa0`
- `0x18001c0a0`
- `0x18001c110`

## callees

- `0x180007248`
- `0x180017224`
- `0x1800172b8`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x1800172dd`
- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x1800172dd`

## pseudocode

```c
bool __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::ProcessLauncherResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
        __int64 a1,
        signed __int32 a2)
{
  bool v2; // bl
  void (__fastcall *v4)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, int); // rax
  GUID v6; // [rsp+40h] [rbp-18h] BYREF

  v2 = 0;
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 60), a2, 0) )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((__int64 *)(a1 + 48));
    GetRestrictedErrorInfo(a1 + 48);
    v2 = Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::System::AutoUpdateTimeZoneStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
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
0x1800172b8  mov     [rsp+arg_0], rbx
0x1800172bd  push    rdi
0x1800172be  sub     rsp, 50h
0x1800172c2  xor     bl, bl
0x1800172c4  mov     rdi, rcx
0x1800172c7  xor     eax, eax
0x1800172c9  lock cmpxchg [rcx+3Ch], edx
0x1800172ce  jnz     short loc_180017335
0x1800172d0  add     rcx, 30h ; '0'
0x1800172d4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800172d9  lea     rcx, [rdi+30h]
0x1800172dd  call    cs:__imp_GetRestrictedErrorInfo
0x1800172e3  mov     edx, 3
0x1800172e8  mov     rcx, rdi
0x1800172eb  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@W4AutoUpdateTimeZoneStatus@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::AutoUpdateTimeZoneStatus>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x1800172f0  mov     bl, al
0x1800172f2  test    al, al
0x1800172f4  jz      short loc_180017335
0x1800172f6  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x1800172fd  test    rcx, rcx
0x180017300  jz      short loc_180017335
0x180017302  mov     rdx, [rcx]
0x180017305  lea     r9, [rsp+58h+var_18]
0x18001730a  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180017311  mov     [rsp+58h+var_30], 4
0x180017319  mov     [rsp+58h+var_38], rdi
0x18001731e  mov     rax, [rdx+40h]
0x180017322  mov     edx, 2
0x180017327  mov     r8d, edx
0x18001732a  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm0
0x180017330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017335  mov     al, bl
0x180017337  mov     rbx, [rsp+58h+arg_0]
0x18001733c  add     rsp, 50h
0x180017340  pop     rdi
0x180017341  retn
```
