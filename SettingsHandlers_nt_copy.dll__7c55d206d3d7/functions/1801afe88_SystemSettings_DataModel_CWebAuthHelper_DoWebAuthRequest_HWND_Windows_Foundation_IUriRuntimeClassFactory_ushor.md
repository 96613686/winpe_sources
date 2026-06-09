# SystemSettings::DataModel::CWebAuthHelper::DoWebAuthRequest(HWND__ *,Windows::Foundation::IUriRuntimeClassFactory *,ushort const *,ushort const *,ushort const *,Windows::Security::Authentication::Web::WebAuthenticationOptions,bool)

- ea: `0x1801afe88`
- end: `0x1801b0081`
- name: `?DoWebAuthRequest@CWebAuthHelper@DataModel@SystemSettings@@QEAAJPEAUHWND__@@PEAUIUriRuntimeClassFactory@Foundation@Windows@@PEBG22W4WebAuthenticationOptions@Web@Authentication@Security@7@_N@Z`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1801ab77c`

## callees

- `0x18000c840`
- `0x180011bb0`
- `0x18001d624`
- `0x18002012c`
- `0x1801afe88`
- `0x1801b0430`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801aff8f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801aff8f`
- `AuthBroker!AuthBrokerClearThreadClientContext` at `0x1801b0028`
- `AuthBroker!AuthBrokerClearThreadClientContext` at `0x1801b0028`
- `AuthBroker!AuthBrokerSetThreadClientContext` at `0x1801affd2`
- `AuthBroker!AuthBrokerSetThreadClientContext` at `0x1801affd2`
- `AuthBroker!AuthBrokerFreeClientContext` at `0x1801b0038`
- `AuthBroker!AuthBrokerFreeClientContext` at `0x1801b0038`
- `AuthBroker!AuthBrokerCreateClientContext` at `0x1801affbc`
- `AuthBroker!AuthBrokerCreateClientContext` at `0x1801affbc`

## string_xrefs

- `0x1801aff64`: `Windows.Security.Authentication.Web.WebAuthenticationBroker`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall SystemSettings::DataModel::CWebAuthHelper::DoWebAuthRequest(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7)
{
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64 *); // rbx
  __int64 v11; // rax
  int ActivationFactory; // ebx
  __int64 (__fastcall *v13)(__int64, _QWORD, __int64 *); // rbx
  __int64 v14; // rax
  __int64 v15; // rbx
  __int64 v17; // [rsp+30h] [rbp-49h] BYREF
  __int64 v18; // [rsp+38h] [rbp-41h] BYREF
  __int64 v19; // [rsp+40h] [rbp-39h] BYREF
  __int64 v20; // [rsp+48h] [rbp-31h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+50h] [rbp-29h] BYREF
  __int64 v22; // [rsp+68h] [rbp-11h]

  v18 = a4;
  v17 = a5;
  v20 = 0;
  v19 = 0;
  v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a3 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v18);
  ActivationFactory = v10(a3, *(_QWORD *)(v11 + 24), &v20);
  if ( ActivationFactory >= 0 )
  {
    v13 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)a3 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
    v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v17);
    ActivationFactory = v13(a3, *(_QWORD *)(v14 + 24), &v19);
    if ( ActivationFactory >= 0 )
    {
      v17 = 0;
      v22 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Security.Authentication.Web.WebAuthenticationBroker",
        0x3Cu,
        0x3Bu);
      v15 = v22;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
      ActivationFactory = RoGetActivationFactory(v15, &GUID_2f149f1a_e673_40b5_bc22_201a6864a37b, &v17);
      if ( ActivationFactory >= 0 )
      {
        v18 = 0;
        ActivationFactory = AuthBrokerCreateClientContext(1, a2, a6, &v18);
        if ( ActivationFactory >= 0 )
        {
          ActivationFactory = AuthBrokerSetThreadClientContext(v18);
          if ( ActivationFactory >= 0 )
          {
            ActivationFactory = SystemSettings::DataModel::CWebAuthHelper::_DoWebAuth(a1, v17, v20, v19, a7 | 1u);
            if ( ActivationFactory < 0 )
              ActivationFactory = SystemSettings::DataModel::CWebAuthHelper::_DoWebAuth(a1, v17, v20, v19, a7);
            AuthBrokerClearThreadClientContext(v18);
          }
          AuthBrokerFreeClientContext(v18);
        }
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v17);
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v19);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v20);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1801afe88  push    rbp
0x1801afe8a  push    rbx
0x1801afe8b  push    rsi
0x1801afe8c  push    rdi
0x1801afe8d  push    r14
0x1801afe8f  push    r15
0x1801afe91  lea     rbp, [rsp-0Fh]
0x1801afe96  sub     rsp, 88h
0x1801afe9d  mov     rax, cs:__security_cookie
0x1801afea4  xor     rax, rsp
0x1801afea7  mov     [rbp+37h+var_40], rax
0x1801afeab  mov     rdi, r8
0x1801afeae  mov     r14, rdx
0x1801afeb1  mov     rsi, rcx
0x1801afeb4  mov     [rbp+37h+var_78], r9
0x1801afeb8  mov     rax, [rbp+37h+arg_20]
0x1801afebc  mov     [rbp+37h+var_80], rax
0x1801afec0  mov     r15, [rbp+37h+arg_28]
0x1801afec4  mov     [rbp+37h+var_68], 0
0x1801afecc  mov     [rbp+37h+var_70], 0
0x1801afed4  mov     rax, [r8]
0x1801afed7  mov     rbx, [rax+30h]
0x1801afedb  lea     rcx, [rbp+37h+var_68]
0x1801afedf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801afee4  lea     rdx, [rbp+37h+var_78]
0x1801afee8  lea     rcx, [rbp+37h+hstringHeader]
0x1801afeec  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801afef1  nop
0x1801afef2  lea     r8, [rbp+37h+var_68]
0x1801afef6  mov     rdx, [rax+18h]
0x1801afefa  mov     rcx, rdi
0x1801afefd  mov     rax, rbx
0x1801aff00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801aff05  mov     ebx, eax
0x1801aff07  test    eax, eax
0x1801aff09  js      loc_1801B004F
0x1801aff0f  mov     rax, [rdi]
0x1801aff12  mov     rbx, [rax+30h]
0x1801aff16  lea     rcx, [rbp+37h+var_70]
0x1801aff1a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801aff1f  lea     rdx, [rbp+37h+var_80]
0x1801aff23  lea     rcx, [rbp+37h+hstringHeader]
0x1801aff27  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801aff2c  nop
0x1801aff2d  lea     r8, [rbp+37h+var_70]
0x1801aff31  mov     rdx, [rax+18h]
0x1801aff35  mov     rcx, rdi
0x1801aff38  mov     rax, rbx
0x1801aff3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801aff40  mov     ebx, eax
0x1801aff42  test    eax, eax
0x1801aff44  js      loc_1801B004F
0x1801aff4a  mov     [rbp+37h+var_80], 0
0x1801aff52  mov     [rbp+37h+var_48], 0
0x1801aff5a  mov     r9d, 3Bh ; ';'; unsigned int
0x1801aff60  lea     r8d, [r9+1]; unsigned int
0x1801aff64  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_Web_WebAuthenticationBroker@@3QBGB; "Windows.Security.Authentication.Web.Web"...
0x1801aff6b  lea     rcx, [rbp+37h+hstringHeader]; hstringHeader
0x1801aff6f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801aff74  mov     rbx, [rbp+37h+var_48]
0x1801aff78  lea     rcx, [rbp+37h+var_80]
0x1801aff7c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801aff81  lea     r8, [rbp+37h+var_80]
0x1801aff85  lea     rdx, _GUID_2f149f1a_e673_40b5_bc22_201a6864a37b
0x1801aff8c  mov     rcx, rbx
0x1801aff8f  call    cs:__imp_RoGetActivationFactory
0x1801aff96  nop     dword ptr [rax+rax+00h]
0x1801aff9b  mov     ebx, eax
0x1801aff9d  test    eax, eax
0x1801aff9f  js      loc_1801B0045
0x1801affa5  mov     [rbp+37h+var_78], 0
0x1801affad  lea     r9, [rbp+37h+var_78]
0x1801affb1  mov     r8, r15
0x1801affb4  mov     rdx, r14
0x1801affb7  mov     ecx, 1
0x1801affbc  call    cs:__imp_AuthBrokerCreateClientContext
0x1801affc3  nop     dword ptr [rax+rax+00h]
0x1801affc8  mov     ebx, eax
0x1801affca  test    eax, eax
0x1801affcc  js      short loc_1801B0045
0x1801affce  mov     rcx, [rbp+37h+var_78]
0x1801affd2  call    cs:__imp_AuthBrokerSetThreadClientContext
0x1801affd9  nop     dword ptr [rax+rax+00h]
0x1801affde  mov     ebx, eax
0x1801affe0  test    eax, eax
0x1801affe2  js      short loc_1801B0034
0x1801affe4  mov     edi, [rbp+37h+arg_30]
0x1801affe7  mov     eax, edi
0x1801affe9  or      eax, 1
0x1801affec  mov     [rsp+0B0h+var_90], eax
0x1801afff0  mov     r9, [rbp+37h+var_70]
0x1801afff4  mov     r8, [rbp+37h+var_68]
0x1801afff8  mov     rdx, [rbp+37h+var_80]
0x1801afffc  mov     rcx, rsi
0x1801affff  call    ?_DoWebAuth@CWebAuthHelper@DataModel@SystemSettings@@IEAAJPEAUIWebAuthenticationBrokerStatics@Web@Authentication@Security@Windows@@PEAUIUriRuntimeClass@Foundation@8@1W4WebAuthenticationOptions@5678@@Z; SystemSettings::DataModel::CWebAuthHelper::_DoWebAuth(Windows::Security::Authentication::Web::IWebAuthenticationBrokerStatics *,Windows::Foundation::IUriRuntimeClass *,Windows::Foundation::IUriRuntimeClass *,Windows::Security::Authentication::Web::WebAuthenticationOptions)
0x1801b0004  mov     ebx, eax
0x1801b0006  test    eax, eax
0x1801b0008  jns     short loc_1801B0024
0x1801b000a  mov     [rsp+0B0h+var_90], edi
0x1801b000e  mov     r9, [rbp+37h+var_70]
0x1801b0012  mov     r8, [rbp+37h+var_68]
0x1801b0016  mov     rdx, [rbp+37h+var_80]
0x1801b001a  mov     rcx, rsi
0x1801b001d  call    ?_DoWebAuth@CWebAuthHelper@DataModel@SystemSettings@@IEAAJPEAUIWebAuthenticationBrokerStatics@Web@Authentication@Security@Windows@@PEAUIUriRuntimeClass@Foundation@8@1W4WebAuthenticationOptions@5678@@Z; SystemSettings::DataModel::CWebAuthHelper::_DoWebAuth(Windows::Security::Authentication::Web::IWebAuthenticationBrokerStatics *,Windows::Foundation::IUriRuntimeClass *,Windows::Foundation::IUriRuntimeClass *,Windows::Security::Authentication::Web::WebAuthenticationOptions)
0x1801b0022  mov     ebx, eax
0x1801b0024  mov     rcx, [rbp+37h+var_78]
0x1801b0028  call    cs:__imp_AuthBrokerClearThreadClientContext
0x1801b002f  nop     dword ptr [rax+rax+00h]
0x1801b0034  mov     rcx, [rbp+37h+var_78]
0x1801b0038  call    cs:__imp_AuthBrokerFreeClientContext
0x1801b003f  nop     dword ptr [rax+rax+00h]
0x1801b0044  nop
0x1801b0045  lea     rcx, [rbp+37h+var_80]
0x1801b0049  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801b004e  nop
0x1801b004f  lea     rcx, [rbp+37h+var_70]
0x1801b0053  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801b0058  nop
0x1801b0059  lea     rcx, [rbp+37h+var_68]
0x1801b005d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1801b0062  mov     eax, ebx
0x1801b0064  mov     rcx, [rbp+37h+var_40]
0x1801b0068  xor     rcx, rsp; StackCookie
0x1801b006b  call    __security_check_cookie
0x1801b0070  add     rsp, 88h
0x1801b0077  pop     r15
0x1801b0079  pop     r14
0x1801b007b  pop     rdi
0x1801b007c  pop     rsi
0x1801b007d  pop     rbx
0x1801b007e  pop     rbp
0x1801b007f  retn
```
