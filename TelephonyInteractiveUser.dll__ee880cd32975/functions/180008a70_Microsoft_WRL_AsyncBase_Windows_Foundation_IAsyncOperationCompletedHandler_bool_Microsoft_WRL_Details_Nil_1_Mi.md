# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Cancel(void)

- ea: `0x180008a70`
- end: `0x180008ae1`
- name: `?Cancel@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@UEAAJXZ`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008a70`
- `0x18000f720`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Cancel(
        __int64 a1)
{
  void (__fastcall *v2)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, int); // rax
  GUID v4; // [rsp+40h] [rbp-18h] BYREF

  if ( Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
         a1,
         2) )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 152LL))(a1);
    if ( Microsoft::WRL::gCausality )
    {
      v2 = *(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, __int64, __int64, GUID *, __int64, int))(*(_QWORD *)Microsoft::WRL::gCausality + 64LL);
      v4 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
      v2(Microsoft::WRL::gCausality, 1, 2, &v4, a1, 3);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180008a70  push    rbx
0x180008a72  sub     rsp, 50h
0x180008a76  mov     edx, 2
0x180008a7b  mov     rbx, rcx
0x180008a7e  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x180008a83  test    al, al
0x180008a85  jz      short loc_180008AD9
0x180008a87  mov     rax, [rbx]
0x180008a8a  mov     rcx, rbx
0x180008a8d  mov     rax, [rax+98h]
0x180008a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a99  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x180008aa0  test    rcx, rcx
0x180008aa3  jz      short loc_180008AD9
0x180008aa5  mov     rax, [rcx]
0x180008aa8  lea     r9, [rsp+58h+var_18]
0x180008aad  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x180008ab4  mov     edx, 1
0x180008ab9  mov     [rsp+58h+var_30], 3
0x180008ac1  mov     [rsp+58h+var_38], rbx
0x180008ac6  mov     rax, [rax+40h]
0x180008aca  movdqu  xmmword ptr [rsp+58h+var_18.Data1], xmm0
0x180008ad0  lea     r8d, [rdx+1]
0x180008ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ad9  xor     eax, eax
0x180008adb  add     rsp, 50h
0x180008adf  pop     rbx
0x180008ae0  retn
```
