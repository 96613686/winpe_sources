# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(void)

- ea: `0x18000f2f0`
- end: `0x18000f3e2`
- name: `?Start@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@MEAAJXZ`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800092d0`

## callees

- `0x18000e284`
- `0x18000f2f0`
- `0x18000f720`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000f33b`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18000f33b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f37a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f37a`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000f3c9`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18000f3c9`

## string_xrefs

- `0x18000f373`: `Windows.Foundation.AsyncOperationCompletedHandler`1<Boolean>`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::Start(
        unsigned int *a1)
{
  int v2; // ebx
  __int64 v3; // rsi
  __int64 v4; // rbp
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  void (__fastcall *v8)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, unsigned int *, HSTRING, __int64); // rax
  GUID v10; // [rsp+40h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-48h] BYREF
  HSTRING string; // [rsp+68h] [rbp-30h] BYREF

  if ( (unsigned __int8)Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(
                          a1,
                          0) )
  {
    v2 = (*(__int64 (__fastcall **)(unsigned int *))(*(_QWORD *)a1 + 136LL))(a1);
    if ( v2 >= 0
      && InitOnceExecuteOnce(
           &Microsoft::WRL::gCausalityInitOnce,
           Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::InitCausality,
           0,
           0)
      && Microsoft::WRL::gCausality )
    {
      v3 = *(_QWORD *)Microsoft::WRL::gCausality;
      v4 = a1[16];
      string = 0;
      v5 = WindowsCreateStringReference(
             L"Windows.Foundation.AsyncOperationCompletedHandler`1<Boolean>",
             0x3Cu,
             &hstringHeader,
             &string);
      if ( v5 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
        JUMPOUT(0x18000F3E1LL);
      }
      v8 = *(void (__fastcall **)(struct Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, unsigned int *, HSTRING, __int64))(v3 + 48);
      v10 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
      v8(Microsoft::WRL::gCausality, 0, 2, &v10, a1, string, v4);
    }
  }
  else
  {
    v2 = -2147483635;
    RoOriginateError(2147483661LL);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000f2f0  push    rbx
0x18000f2f2  push    rbp
0x18000f2f3  push    rsi
0x18000f2f4  push    rdi
0x18000f2f5  sub     rsp, 78h
0x18000f2f9  xor     edx, edx
0x18000f2fb  mov     rdi, rcx
0x18000f2fe  call    ?TransitionToState@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@AEAA_NW4AsyncStatusInternal@Details@23@@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<bool>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TransitionToState(Microsoft::WRL::Details::AsyncStatusInternal)
0x18000f303  test    al, al
0x18000f305  jz      loc_18000F3C2
0x18000f30b  mov     rax, [rdi]
0x18000f30e  mov     rcx, rdi
0x18000f311  mov     rax, [rax+88h]
0x18000f318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f31d  mov     ebx, eax
0x18000f31f  test    eax, eax
0x18000f321  js      loc_18000F3CF
0x18000f327  xor     r9d, r9d; Context
0x18000f32a  lea     rdx, ?InitCausality@?$AsyncBase@U?$IAsyncOperationCompletedHandler@_N@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18000f331  xor     r8d, r8d; Parameter
0x18000f334  lea     rcx, ?gCausalityInitOnce@WRL@Microsoft@@3T_RTL_RUN_ONCE@@A; InitOnce
0x18000f33b  call    cs:__imp_InitOnceExecuteOnce
0x18000f341  test    eax, eax
0x18000f343  jz      loc_18000F3CF
0x18000f349  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000f350  test    rax, rax
0x18000f353  jz      short loc_18000F3CF
0x18000f355  mov     rsi, [rax]
0x18000f358  lea     r9, [rsp+98h+string]; string
0x18000f35d  mov     ebp, [rdi+40h]
0x18000f360  lea     r8, [rsp+98h+hstringHeader]; hstringHeader
0x18000f365  mov     edx, 3Ch ; '<'; length
0x18000f36a  mov     [rsp+98h+string], 0
0x18000f373  lea     rcx, aWindowsFoundat_0; "Windows.Foundation.AsyncOperationComple"...
0x18000f37a  call    cs:__imp_WindowsCreateStringReference
0x18000f380  test    eax, eax
0x18000f382  js      short loc_18000F3DA
0x18000f384  mov     rcx, [rsp+98h+string]
0x18000f389  lea     r9, [rsp+98h+var_58]
0x18000f38e  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18000f395  mov     rax, [rsi+30h]
0x18000f399  xor     edx, edx
0x18000f39b  mov     [rsp+98h+var_68], rbp
0x18000f3a0  mov     [rsp+98h+var_70], rcx
0x18000f3a5  mov     rcx, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18000f3ac  lea     r8d, [rdx+2]
0x18000f3b0  mov     [rsp+98h+var_78], rdi
0x18000f3b5  movdqu  [rsp+98h+var_58], xmm0
0x18000f3bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3c0  jmp     short loc_18000F3CF
0x18000f3c2  mov     ebx, 8000000Dh
0x18000f3c7  mov     ecx, ebx
0x18000f3c9  call    cs:__imp_RoOriginateError
0x18000f3cf  mov     eax, ebx
0x18000f3d1  add     rsp, 78h
0x18000f3d5  pop     rdi
0x18000f3d6  pop     rsi
0x18000f3d7  pop     rbp
0x18000f3d8  pop     rbx
0x18000f3d9  retn
0x18000f3da  mov     ecx, eax; this
0x18000f3dc  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
