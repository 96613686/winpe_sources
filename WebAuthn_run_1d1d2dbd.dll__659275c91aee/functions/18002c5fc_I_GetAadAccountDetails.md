# I_GetAadAccountDetails

- ea: `0x18002c5fc`
- end: `0x18002c924`
- name: `I_GetAadAccountDetails`
- size: `808`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002be64`

## callees

- `0x180017764`
- `0x180017a88`
- `0x1800205e4`
- `0x18002bbc8`
- `0x18002c5fc`
- `0x18002cbb4`
- `0x18002cbfc`
- `0x18002cc4c`
- `0x180031708`
- `0x18005378c`
- `0x18013c090`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c799`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c86b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c799`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002c86b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c6fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c7e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c8c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c8d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c6fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c7e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c8c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c8d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c756`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c841`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c756`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c841`

## string_xrefs

- `0x18002c68c`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18002c76f`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall I_GetAadAccountDetails(const WCHAR *a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v6; // rcx
  int WebAccount; // eax
  unsigned int v8; // ebx
  wil::details::in1diag3 *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rbx
  __int64 v16; // rdx
  __int64 v17; // r9
  HLOCAL v18; // rax
  void *v19; // rdi
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64, HSTRING *); // rbx
  PCWSTR v22; // rdi
  HLOCAL v23; // rax
  void *v24; // rbx
  int v26; // [rsp+20h] [rbp-49h]
  UINT32 length; // [rsp+30h] [rbp-39h] BYREF
  UINT32 v28; // [rsp+34h] [rbp-35h] BYREF
  HSTRING v29; // [rsp+38h] [rbp-31h] BYREF
  HSTRING string; // [rsp+40h] [rbp-29h] BYREF
  __int64 v31; // [rsp+48h] [rbp-21h] BYREF
  void *v32; // [rsp+50h] [rbp-19h] BYREF
  void *v33; // [rsp+58h] [rbp-11h] BYREF
  int v34[2]; // [rsp+60h] [rbp-9h] BYREF
  __int64 v35; // [rsp+68h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp+7h] BYREF
  __int64 v37; // [rsp+88h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *(_QWORD *)v34 = 0;
  v35 = 0;
  v31 = 0;
  string = 0;
  length = 0;
  v33 = 0;
  v29 = 0;
  v28 = 0;
  v32 = 0;
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(v34);
  WebAccount = I_GetWebAccount(v6, L"organizations", (__int64)L"UPN", a1, (__int64)v34);
  v8 = WebAccount;
  v9 = retaddr;
  if ( WebAccount >= 0 )
  {
    WebAccount = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
                   v34,
                   &v35);
    v8 = WebAccount;
    v9 = retaddr;
    if ( WebAccount < 0 )
    {
      v10 = 574;
      goto LABEL_3;
    }
    v11 = v35;
    v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v35 + 56LL);
    _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v31);
    WebAccount = v12(v11, &v31);
    v8 = WebAccount;
    v9 = retaddr;
    if ( WebAccount < 0 )
    {
      v10 = 576;
      goto LABEL_3;
    }
    v13 = v31;
    v14 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v31 + 48LL);
    WindowsDeleteString(string);
    string = 0;
    v37 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"DisplayName", 0xCu, 0xBu);
    WebAccount = v14(v13, v37, &string);
    v8 = WebAccount;
    v9 = retaddr;
    if ( WebAccount < 0 )
    {
      v10 = 581;
      goto LABEL_3;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    if ( StringRawBuffer )
    {
      v18 = LocalAlloc(0x40u, 2LL * ++length);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v33,
        v18);
      v19 = v33;
      if ( !v33 )
      {
        v17 = 2147942414LL;
        v16 = 591;
        goto LABEL_13;
      }
      memcpy_0(v33, StringRawBuffer, 2LL * length);
      v33 = 0;
      *a2 = v19;
      v20 = v31;
      v21 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v31 + 48LL);
      WindowsDeleteString(v29);
      v29 = 0;
      v37 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"OID", 4u, 3u);
      WebAccount = v21(v20, v37, &v29);
      v8 = WebAccount;
      v9 = retaddr;
      if ( WebAccount < 0 )
      {
        v10 = 599;
        goto LABEL_3;
      }
      v22 = WindowsGetStringRawBuffer(v29, &v28);
      if ( v22 )
      {
        v23 = LocalAlloc(0x40u, 2LL * ++v28);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v32,
          v23);
        v24 = v32;
        if ( v32 )
        {
          memcpy_0(v32, v22, 2LL * v28);
          v32 = 0;
          *a3 = v24;
          v8 = 0;
          goto LABEL_23;
        }
        v17 = 2147942414LL;
        v16 = 609;
        goto LABEL_13;
      }
      v16 = 604;
    }
    else
    {
      v16 = 586;
    }
    v17 = 2148073489LL;
LABEL_13:
    v8 = v17;
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)v17,
      v26);
    goto LABEL_23;
  }
  v10 = 572;
LABEL_3:
  wil::details::in1diag3::_Log_Hr(
    v9,
    (void *)v10,
    (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
    (const char *)(unsigned int)WebAccount,
    v26);
LABEL_23:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v32);
  WindowsDeleteString(v29);
  v29 = 0;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v33);
  WindowsDeleteString(string);
  string = 0;
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v31);
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(&v35);
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(v34);
  return v8;
}

```

## disassembly

```asm
0x18002c5fc  mov     [rsp-8+arg_18], rbx
0x18002c601  push    rbp
0x18002c602  push    rsi
0x18002c603  push    rdi
0x18002c604  push    r14
0x18002c606  push    r15
0x18002c608  lea     rbp, [rsp-37h]
0x18002c60d  sub     rsp, 0A0h
0x18002c614  mov     rax, cs:__security_cookie
0x18002c61b  xor     rax, rsp
0x18002c61e  mov     [rbp+57h+var_30], rax
0x18002c622  mov     rsi, r8
0x18002c625  mov     r14, rdx
0x18002c628  mov     rbx, rcx
0x18002c62b  xor     r15d, r15d
0x18002c62e  mov     qword ptr [rbp+57h+var_60], r15
0x18002c632  mov     [rbp+57h+var_58], r15
0x18002c636  mov     [rbp+57h+var_78], r15
0x18002c63a  mov     [rbp+57h+string], r15
0x18002c63e  mov     [rbp+57h+length], r15d
0x18002c642  mov     [rbp+57h+var_68], r15
0x18002c646  mov     [rbp+57h+var_88], r15
0x18002c64a  mov     [rbp+57h+var_8C], r15d
0x18002c64e  mov     [rbp+57h+var_70], r15
0x18002c652  lea     rcx, [rbp+57h+var_60]
0x18002c656  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002c65b  lea     rax, [rbp+57h+var_60]
0x18002c65f  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x18002c664  mov     r9, rbx
0x18002c667  lea     r8, aUpn; "UPN"
0x18002c66e  lea     rdx, aOrganizations; "organizations"
0x18002c675  call    I_GetWebAccount
0x18002c67a  mov     ebx, eax
0x18002c67c  mov     rcx, [rbp+5Fh]; this
0x18002c680  test    eax, eax
0x18002c682  jns     short loc_18002C69D
0x18002c684  mov     edx, 23Ch; void *
0x18002c689  mov     r9d, eax; char *
0x18002c68c  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18002c693  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002c698  jmp     loc_18002C8B2
0x18002c69d  lea     rdx, [rbp+57h+var_58]
0x18002c6a1  lea     rcx, [rbp+57h+var_60]
0x18002c6a5  call    ??$As@UIWebAccount2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccount2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount2>>)
0x18002c6aa  mov     ebx, eax
0x18002c6ac  mov     rcx, [rbp+5Fh]
0x18002c6b0  test    eax, eax
0x18002c6b2  jns     short loc_18002C6BB
0x18002c6b4  mov     edx, 23Eh
0x18002c6b9  jmp     short loc_18002C689
0x18002c6bb  mov     rdi, [rbp+57h+var_58]
0x18002c6bf  mov     rax, [rdi]
0x18002c6c2  mov     rbx, [rax+38h]
0x18002c6c6  lea     rcx, [rbp+57h+var_78]
0x18002c6ca  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002c6cf  lea     rdx, [rbp+57h+var_78]
0x18002c6d3  mov     rcx, rdi
0x18002c6d6  mov     rax, rbx
0x18002c6d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c6de  mov     ebx, eax
0x18002c6e0  mov     rcx, [rbp+5Fh]
0x18002c6e4  test    eax, eax
0x18002c6e6  jns     short loc_18002C6EF
0x18002c6e8  mov     edx, 240h
0x18002c6ed  jmp     short loc_18002C689
0x18002c6ef  mov     rdi, [rbp+57h+var_78]
0x18002c6f3  mov     rax, [rdi]
0x18002c6f6  mov     rbx, [rax+30h]
0x18002c6fa  mov     rcx, [rbp+57h+string]; string
0x18002c6fe  call    cs:__imp_WindowsDeleteString
0x18002c704  mov     [rbp+57h+string], r15
0x18002c708  mov     [rbp+57h+var_38], r15
0x18002c70c  mov     r9d, 0Bh; unsigned int
0x18002c712  lea     r8d, [r9+1]; unsigned int
0x18002c716  lea     rdx, sourceString; "DisplayName"
0x18002c71d  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18002c721  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002c726  nop
0x18002c727  lea     r8, [rbp+57h+string]
0x18002c72b  mov     rdx, [rbp+57h+var_38]
0x18002c72f  mov     rcx, rdi
0x18002c732  mov     rax, rbx
0x18002c735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c73a  mov     ebx, eax
0x18002c73c  mov     rcx, [rbp+5Fh]
0x18002c740  test    eax, eax
0x18002c742  jns     short loc_18002C74E
0x18002c744  mov     edx, 245h
0x18002c749  jmp     loc_18002C689
0x18002c74e  lea     rdx, [rbp+57h+length]; length
0x18002c752  mov     rcx, [rbp+57h+string]; string
0x18002c756  call    cs:__imp_WindowsGetStringRawBuffer
0x18002c75c  mov     rbx, rax
0x18002c75f  test    rax, rax
0x18002c762  jnz     short loc_18002C787
0x18002c764  mov     edx, 24Ah; void *
0x18002c769  mov     r9d, 80090011h; char *
0x18002c76f  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18002c776  mov     rcx, [rbp+5Fh]; this
0x18002c77a  mov     ebx, r9d
0x18002c77d  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18002c782  jmp     loc_18002C8B2
0x18002c787  mov     eax, [rbp+57h+length]
0x18002c78a  inc     eax
0x18002c78c  mov     [rbp+57h+length], eax
0x18002c78f  mov     edx, eax
0x18002c791  add     rdx, rdx; uBytes
0x18002c794  mov     ecx, 40h ; '@'; uFlags
0x18002c799  call    cs:__imp_LocalAlloc
0x18002c79f  mov     rdx, rax
0x18002c7a2  lea     rcx, [rbp+57h+var_68]
0x18002c7a6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002c7ab  mov     rdi, [rbp+57h+var_68]
0x18002c7af  test    rdi, rdi
0x18002c7b2  jnz     short loc_18002C7C1
0x18002c7b4  mov     r9d, 8007000Eh
0x18002c7ba  mov     edx, 24Fh
0x18002c7bf  jmp     short loc_18002C76F
0x18002c7c1  mov     r8d, [rbp+57h+length]
0x18002c7c5  add     r8, r8; Size
0x18002c7c8  mov     rdx, rbx; Src
0x18002c7cb  mov     rcx, rdi; void *
0x18002c7ce  call    memcpy_0
0x18002c7d3  mov     [rbp+57h+var_68], r15
0x18002c7d7  mov     [r14], rdi
0x18002c7da  mov     rdi, [rbp+57h+var_78]
0x18002c7de  mov     rax, [rdi]
0x18002c7e1  mov     rbx, [rax+30h]
0x18002c7e5  mov     rcx, [rbp+57h+var_88]; string
0x18002c7e9  call    cs:__imp_WindowsDeleteString
0x18002c7ef  mov     [rbp+57h+var_88], r15
0x18002c7f3  mov     [rbp+57h+var_38], r15
0x18002c7f7  mov     r9d, 3; unsigned int
0x18002c7fd  lea     r8d, [r9+1]; unsigned int
0x18002c801  lea     rdx, aOid; "OID"
0x18002c808  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x18002c80c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002c811  nop
0x18002c812  lea     r8, [rbp+57h+var_88]
0x18002c816  mov     rdx, [rbp+57h+var_38]
0x18002c81a  mov     rcx, rdi
0x18002c81d  mov     rax, rbx
0x18002c820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c825  mov     ebx, eax
0x18002c827  mov     rcx, [rbp+5Fh]
0x18002c82b  test    eax, eax
0x18002c82d  jns     short loc_18002C839
0x18002c82f  mov     edx, 257h
0x18002c834  jmp     loc_18002C689
0x18002c839  lea     rdx, [rbp+57h+var_8C]; length
0x18002c83d  mov     rcx, [rbp+57h+var_88]; string
0x18002c841  call    cs:__imp_WindowsGetStringRawBuffer
0x18002c847  mov     rdi, rax
0x18002c84a  test    rax, rax
0x18002c84d  jnz     short loc_18002C859
0x18002c84f  mov     edx, 25Ch
0x18002c854  jmp     loc_18002C769
0x18002c859  mov     eax, [rbp+57h+var_8C]
0x18002c85c  inc     eax
0x18002c85e  mov     [rbp+57h+var_8C], eax
0x18002c861  mov     edx, eax
0x18002c863  add     rdx, rdx; uBytes
0x18002c866  mov     ecx, 40h ; '@'; uFlags
0x18002c86b  call    cs:__imp_LocalAlloc
0x18002c871  mov     rdx, rax
0x18002c874  lea     rcx, [rbp+57h+var_70]
0x18002c878  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002c87d  mov     rbx, [rbp+57h+var_70]
0x18002c881  test    rbx, rbx
0x18002c884  jnz     short loc_18002C896
0x18002c886  mov     r9d, 8007000Eh
0x18002c88c  mov     edx, 261h
0x18002c891  jmp     loc_18002C76F
0x18002c896  mov     r8d, [rbp+57h+var_8C]
0x18002c89a  add     r8, r8; Size
0x18002c89d  mov     rdx, rdi; Src
0x18002c8a0  mov     rcx, rbx; void *
0x18002c8a3  call    memcpy_0
0x18002c8a8  mov     [rbp+57h+var_70], r15
0x18002c8ac  mov     [rsi], rbx
0x18002c8af  mov     ebx, r15d
0x18002c8b2  lea     rcx, [rbp+57h+var_70]
0x18002c8b6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18002c8bb  nop
0x18002c8bc  mov     rcx, [rbp+57h+var_88]; string
0x18002c8c0  call    cs:__imp_WindowsDeleteString
0x18002c8c6  mov     [rbp+57h+var_88], r15
0x18002c8ca  lea     rcx, [rbp+57h+var_68]
0x18002c8ce  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18002c8d3  nop
0x18002c8d4  mov     rcx, [rbp+57h+string]; string
0x18002c8d8  call    cs:__imp_WindowsDeleteString
0x18002c8de  mov     [rbp+57h+string], r15
0x18002c8e2  lea     rcx, [rbp+57h+var_78]
0x18002c8e6  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002c8eb  nop
0x18002c8ec  lea     rcx, [rbp+57h+var_58]
0x18002c8f0  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002c8f5  nop
0x18002c8f6  lea     rcx, [rbp+57h+var_60]
0x18002c8fa  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002c8ff  mov     eax, ebx
0x18002c901  mov     rcx, [rbp+57h+var_30]
0x18002c905  xor     rcx, rsp; StackCookie
0x18002c908  call    __security_check_cookie
0x18002c90d  mov     rbx, [rsp+0C0h+arg_18]
0x18002c915  add     rsp, 0A0h
0x18002c91c  pop     r15
0x18002c91e  pop     r14
0x18002c920  pop     rdi
0x18002c921  pop     rsi
0x18002c922  pop     rbp
0x18002c923  retn
```
