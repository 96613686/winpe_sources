# Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(void)

- ea: `0x18001cec4`
- end: `0x18001cf92`
- name: `?TraceOperationStart@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVApplicationData@Storage@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAAXXZ`
- size: `206`
- prototype: `void __fastcall(Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001b560`

## callees

- `0x18001cec4`
- `0x180041620`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001cf2d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001cf2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001cf17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001cf17`

## string_xrefs

- `0x18001ceff`: `Windows.Foundation.AsyncOperationCompletedHandler`1<Windows.Storage.ApplicationData>`

## pseudocode

```c
void __fastcall Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TraceOperationStart(
        Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *this)
{
  __int64 id; // rsi
  Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics_vtbl *v3; // rdi
  signed int v4; // eax
  HRESULT (__fastcall *TraceOperationCreation)(Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, Windows::Foundation::Diagnostics::CausalityTraceLevel, Windows::Foundation::Diagnostics::CausalitySource, _GUID, unsigned __int64, HSTRING__ *, unsigned __int64); // rax
  GUID v6; // [rsp+40h] [rbp-48h] BYREF
  HSTRING_HEADER v7; // [rsp+50h] [rbp-38h] BYREF
  HSTRING v8; // [rsp+68h] [rbp-20h] BYREF

  if ( Microsoft::WRL::gCausality )
  {
    id = this->id_;
    v3 = Microsoft::WRL::gCausality->__vftable;
    v8 = 0;
    v4 = WindowsCreateStringReference(
           L"Windows.Foundation.AsyncOperationCompletedHandler`1<Windows.Storage.ApplicationData>",
           0x54u,
           &v7,
           &v8);
    if ( v4 < 0 )
    {
      RaiseException(v4, 1u, 0, 0);
      __debugbreak();
    }
    TraceOperationCreation = v3->TraceOperationCreation;
    v6 = GUID_CAUSALITY_WINDOWS_PLATFORM_ID;
    ((void (__fastcall *)(Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics *, _QWORD, __int64, GUID *, Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::ApplicationData *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2> > *, HSTRING, __int64))TraceOperationCreation)(
      Microsoft::WRL::gCausality,
      0,
      2,
      &v6,
      this,
      v8,
      id);
  }
}

```

## disassembly

```asm
0x18001cec4  mov     r11, rsp
0x18001cec7  mov     [r11+10h], rbx
0x18001cecb  mov     [r11+18h], rsi
0x18001cecf  push    rdi
0x18001ced0  sub     rsp, 80h
0x18001ced7  mov     rax, cs:__security_cookie
0x18001cede  xor     rax, rsp
0x18001cee1  mov     [rsp+88h+var_18], rax
0x18001cee6  mov     rax, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18001ceed  mov     rbx, this
0x18001cef0  test    rax, rax
0x18001cef3  jz      short loc_18001CF70
0x18001cef5  mov     esi, [this+40h]
0x18001cef8  lea     r9, [r11-20h]; string
0x18001cefc  mov     rdi, [rax]
0x18001ceff  lea     this, aWindowsFoundat_10; "Windows.Foundation.AsyncOperationComple"...
0x18001cf06  lea     r8, [r11-38h]; hstringHeader
0x18001cf0a  mov     qword ptr [r11-20h], 0
0x18001cf12  mov     edx, 54h ; 'T'; length
0x18001cf17  call    cs:__imp_WindowsCreateStringReference
0x18001cf1d  test    eax, eax
0x18001cf1f  jns     short loc_18001CF34
0x18001cf21  xor     r9d, r9d; lpArguments
0x18001cf24  xor     r8d, r8d; nNumberOfArguments
0x18001cf27  mov     ecx, eax; dwExceptionCode
0x18001cf29  lea     edx, [r9+1]; dwExceptionFlags
0x18001cf2d  call    cs:__imp_RaiseException
0x18001cf33  int     3; Trap to Debugger
0x18001cf34  mov     this, [rsp+88h+var_20]
0x18001cf39  lea     r9, [rsp+88h+var_48]
0x18001cf3e  movups  xmm0, xmmword ptr cs:?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B.Data1; _GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID ...
0x18001cf45  mov     rax, [rdi+30h]
0x18001cf49  xor     edx, edx
0x18001cf4b  mov     [rsp+88h+var_58], rsi
0x18001cf50  mov     [rsp+88h+var_60], this
0x18001cf55  mov     this, cs:?gCausality@WRL@Microsoft@@3PEAUIAsyncCausalityTracerStatics@Diagnostics@Foundation@Windows@@EA; Windows::Foundation::Diagnostics::IAsyncCausalityTracerStatics * Microsoft::WRL::gCausality
0x18001cf5c  lea     r8d, [rdx+2]
0x18001cf60  mov     [rsp+88h+var_68], rbx
0x18001cf65  movdqu  [rsp+88h+var_48], xmm0
0x18001cf6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf70  mov     this, [rsp+88h+var_18]
0x18001cf75  xor     this, rsp; StackCookie
0x18001cf78  call    __security_check_cookie
0x18001cf7d  lea     r11, [rsp+88h+var_8]
0x18001cf85  mov     rbx, [r11+18h]
0x18001cf89  mov     rsi, [r11+20h]
0x18001cf8d  mov     rsp, r11
0x18001cf90  pop     rdi
0x18001cf91  retn
```
