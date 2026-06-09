# CtaManager::InitializeCapabilityListeners(Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityStatics *)

- ea: `0x18003b6b8`
- end: `0x18003b8eb`
- name: `?InitializeCapabilityListeners@CtaManager@@AEAAXPEAUIAppCapabilityStatics@AppCapabilityAccess@Authorization@Security@Windows@@@Z`
- size: `563`
- prototype: `void __fastcall(CtaManager *__hidden this, struct Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityStatics *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18009b8ec`

## callees

- `0x180004e38`
- `0x18000e5f4`
- `0x18003b6b8`
- `0x180096cb8`
- `0x18009da74`
- `0x18009db18`
- `0x1800b99f0`
- `0x180118010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003b728`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003b7e2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003b728`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003b7e2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003b70f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003b7c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003b70f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003b7c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CtaManager::InitializeCapabilityListeners(
        CtaManager *this,
        struct Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityStatics *a2)
{
  __int64 (__fastcall *v4)(struct Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityStatics *, HSTRING, _QWORD *); // rsi
  _QWORD *v5; // r12
  int v6; // eax
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 (__fastcall *v9)(struct Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityStatics *, HSTRING, char *); // r15
  int v10; // eax
  __int64 v11; // rax
  __int64 v12; // rcx
  int v13; // eax
  int v14; // eax
  __int64 v15; // [rsp+20h] [rbp-40h] BYREF
  CtaManager *v16; // [rsp+28h] [rbp-38h] BYREF
  HSTRING string; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v4 = *(__int64 (__fastcall **)(struct Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityStatics *, HSTRING, _QWORD *))(*(_QWORD *)a2 + 64LL);
  v5 = (_QWORD *)((char *)this + 144);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 144);
  if ( WindowsCreateStringReference(L"wifiData", 8u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v6 = v4(a2, string, v5);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x162,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\ctamanager.cpp",
      (const char *)(unsigned int)v6,
      v15);
  v16 = this;
  v7 = wil::MakeAgileCallback_Windows::Foundation::ITypedEventHandler_Windows::Security::Authorization::AppCapabilityAccess::AppCapability___Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessChangedEventArgs_____lambda_01a4a2593e51feb0f23d1c085623bbec___(
         &v15,
         &v16);
  Microsoft::WRL::ComPtr<Windows::Security::Authorization::AppCapabilityAccess::IAppCapability>::operator=(
    (char *)this + 176,
    v7);
  v8 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  v9 = *(__int64 (__fastcall **)(struct Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityStatics *, HSTRING, char *))(*(_QWORD *)a2 + 64LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((char *)this + 152);
  if ( WindowsCreateStringReference(L"cellularData", 0xCu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v10 = v9(a2, string, (char *)this + 152);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x16B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\ctamanager.cpp",
      (const char *)(unsigned int)v10,
      v15);
  v16 = this;
  v11 = wil::MakeAgileCallback_Windows::Foundation::ITypedEventHandler_Windows::Security::Authorization::AppCapabilityAccess::AppCapability___Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessChangedEventArgs_____lambda_c6f59fab5249b3a5c3eca177a2f2c885___(
          &v15,
          &v16);
  Microsoft::WRL::ComPtr<Windows::Security::Authorization::AppCapabilityAccess::IAppCapability>::operator=(
    (char *)this + 184,
    v11);
  v12 = v15;
  if ( v15 )
  {
    v15 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(*(_QWORD *)*v5 + 80LL))(
          *v5,
          *((_QWORD *)this + 22),
          (char *)this + 160);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x173,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\ctamanager.cpp",
      (const char *)(unsigned int)v13,
      v15);
  v14 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(**((_QWORD **)this + 19) + 80LL))(
          *((_QWORD *)this + 19),
          *((_QWORD *)this + 23),
          (char *)this + 168);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x174,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\endpoint\\ctamanager.cpp",
      (const char *)(unsigned int)v14,
      v15);
}

```

## disassembly

```asm
0x18003b6b8  mov     [rsp-28h+arg_10], rbx
0x18003b6bd  mov     [rsp-28h+arg_18], rsi
0x18003b6c2  push    rbp
0x18003b6c3  push    rdi
0x18003b6c4  push    r12
0x18003b6c6  push    r14
0x18003b6c8  push    r15
0x18003b6ca  mov     rbp, rsp
0x18003b6cd  sub     rsp, 60h
0x18003b6d1  mov     rax, cs:__security_cookie
0x18003b6d8  xor     rax, rsp
0x18003b6db  mov     [rbp+var_10], rax
0x18003b6df  mov     rdi, rdx
0x18003b6e2  mov     rbx, rcx
0x18003b6e5  mov     rax, [rdx]
0x18003b6e8  mov     rsi, [rax+40h]
0x18003b6ec  lea     r12, [rcx+90h]
0x18003b6f3  mov     rcx, r12
0x18003b6f6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003b6fb  lea     r9, [rbp+string]; string
0x18003b6ff  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003b703  mov     edx, 8; length
0x18003b708  lea     rcx, sourceString; "wifiData"
0x18003b70f  call    cs:__imp_WindowsCreateStringReference
0x18003b715  test    eax, eax
0x18003b717  jns     short loc_18003B72E
0x18003b719  xor     r9d, r9d; lpArguments
0x18003b71c  xor     r8d, r8d; nNumberOfArguments
0x18003b71f  lea     edx, [r9+1]; dwExceptionFlags
0x18003b723  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003b728  call    cs:__imp_RaiseException
0x18003b72e  mov     r8, r12
0x18003b731  mov     rdx, [rbp+string]
0x18003b735  mov     rcx, rdi
0x18003b738  mov     rax, rsi
0x18003b73b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b740  mov     rcx, [rbp+28h]; this
0x18003b744  test    eax, eax
0x18003b746  jns     short loc_18003B75D
0x18003b748  mov     r9d, eax; char *
0x18003b74b  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003b752  mov     edx, 162h; void *
0x18003b757  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003b75d  mov     [rbp+var_38], rbx
0x18003b761  lea     rdx, [rbp+var_38]
0x18003b765  lea     rcx, [rbp+var_40]
0x18003b769  call    wil__MakeAgileCallback_Windows__Foundation__ITypedEventHandler_Windows__Security__Authorization__AppCapabilityAccess__AppCapability___Windows__Security__Authorization__AppCapabilityAccess__AppCapabilityAccessChangedEventArgs_____lambda_01a4a2593e51feb0f23d1c085623bbec___
0x18003b76e  lea     r14, [rbx+0B0h]
0x18003b775  mov     rdx, rax
0x18003b778  mov     rcx, r14
0x18003b77b  call    ??4?$ComPtr@UIAppCapability@AppCapabilityAccess@Authorization@Security@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::Security::Authorization::AppCapabilityAccess::IAppCapability>::operator=(Microsoft::WRL::ComPtr<Windows::Security::Authorization::AppCapabilityAccess::IAppCapability> &&)
0x18003b780  nop
0x18003b781  mov     rcx, [rbp+var_40]
0x18003b785  test    rcx, rcx
0x18003b788  jz      short loc_18003B79F
0x18003b78a  mov     [rbp+var_40], 0
0x18003b792  mov     rax, [rcx]
0x18003b795  mov     rax, [rax+10h]
0x18003b799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b79e  nop
0x18003b79f  mov     rax, [rdi]
0x18003b7a2  mov     r15, [rax+40h]
0x18003b7a6  lea     rsi, [rbx+98h]
0x18003b7ad  mov     rcx, rsi
0x18003b7b0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003b7b5  lea     r9, [rbp+string]; string
0x18003b7b9  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18003b7bd  mov     edx, 0Ch; length
0x18003b7c2  lea     rcx, aCellulardata_0; "cellularData"
0x18003b7c9  call    cs:__imp_WindowsCreateStringReference
0x18003b7cf  test    eax, eax
0x18003b7d1  jns     short loc_18003B7E8
0x18003b7d3  xor     r9d, r9d; lpArguments
0x18003b7d6  xor     r8d, r8d; nNumberOfArguments
0x18003b7d9  lea     edx, [r9+1]; dwExceptionFlags
0x18003b7dd  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003b7e2  call    cs:__imp_RaiseException
0x18003b7e8  mov     r8, rsi
0x18003b7eb  mov     rdx, [rbp+string]
0x18003b7ef  mov     rcx, rdi
0x18003b7f2  mov     rax, r15
0x18003b7f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b7fa  mov     rcx, [rbp+28h]; this
0x18003b7fe  test    eax, eax
0x18003b800  jns     short loc_18003B817
0x18003b802  mov     r9d, eax; char *
0x18003b805  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003b80c  mov     edx, 16Bh; void *
0x18003b811  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003b817  mov     [rbp+var_38], rbx
0x18003b81b  lea     rdx, [rbp+var_38]
0x18003b81f  lea     rcx, [rbp+var_40]
0x18003b823  call    wil__MakeAgileCallback_Windows__Foundation__ITypedEventHandler_Windows__Security__Authorization__AppCapabilityAccess__AppCapability___Windows__Security__Authorization__AppCapabilityAccess__AppCapabilityAccessChangedEventArgs_____lambda_c6f59fab5249b3a5c3eca177a2f2c885___
0x18003b828  lea     rdi, [rbx+0B8h]
0x18003b82f  mov     rdx, rax
0x18003b832  mov     rcx, rdi
0x18003b835  call    ??4?$ComPtr@UIAppCapability@AppCapabilityAccess@Authorization@Security@Windows@@@WRL@Microsoft@@QEAAAEAV012@$$QEAV012@@Z; Microsoft::WRL::ComPtr<Windows::Security::Authorization::AppCapabilityAccess::IAppCapability>::operator=(Microsoft::WRL::ComPtr<Windows::Security::Authorization::AppCapabilityAccess::IAppCapability> &&)
0x18003b83a  nop
0x18003b83b  mov     rcx, [rbp+var_40]
0x18003b83f  test    rcx, rcx
0x18003b842  jz      short loc_18003B859
0x18003b844  mov     [rbp+var_40], 0
0x18003b84c  mov     rax, [rcx]
0x18003b84f  mov     rax, [rax+10h]
0x18003b853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b858  nop
0x18003b859  mov     rcx, [r12]
0x18003b85d  mov     rax, [rcx]
0x18003b860  lea     r8, [rbx+0A0h]
0x18003b867  mov     rdx, [r14]
0x18003b86a  mov     rax, [rax+50h]
0x18003b86e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b873  test    eax, eax
0x18003b875  jns     short loc_18003B890
0x18003b877  mov     rcx, [rbp+28h]; this
0x18003b87b  mov     r9d, eax; char *
0x18003b87e  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003b885  mov     edx, 173h; void *
0x18003b88a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003b890  mov     rcx, [rsi]
0x18003b893  mov     rax, [rcx]
0x18003b896  lea     r8, [rbx+0A8h]
0x18003b89d  mov     rdx, [rdi]
0x18003b8a0  mov     rax, [rax+50h]
0x18003b8a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8a9  test    eax, eax
0x18003b8ab  jns     short loc_18003B8C6
0x18003b8ad  mov     rcx, [rbp+28h]; this
0x18003b8b1  mov     r9d, eax; char *
0x18003b8b4  lea     r8, aOnecoreuapBase_67; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18003b8bb  mov     edx, 174h; void *
0x18003b8c0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003b8c6  mov     rcx, [rbp+var_10]
0x18003b8ca  xor     rcx, rsp; StackCookie
0x18003b8cd  call    __security_check_cookie
0x18003b8d2  lea     r11, [rsp+60h+var_s0]
0x18003b8d7  mov     rbx, [r11+40h]
0x18003b8db  mov     rsi, [r11+48h]
0x18003b8df  mov     rsp, r11
0x18003b8e2  pop     r15
0x18003b8e4  pop     r14
0x18003b8e6  pop     r12
0x18003b8e8  pop     rdi
0x18003b8e9  pop     rbp
0x18003b8ea  retn
```
