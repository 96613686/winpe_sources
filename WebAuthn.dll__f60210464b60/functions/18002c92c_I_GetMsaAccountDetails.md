# I_GetMsaAccountDetails

- ea: `0x18002c92c`
- end: `0x18002cbab`
- name: `I_GetMsaAccountDetails`
- size: `639`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002be64`

## callees

- `0x180017764`
- `0x180017a88`
- `0x1800205e4`
- `0x18002bbc8`
- `0x18002c92c`
- `0x18002cbfc`
- `0x18002cc4c`
- `0x180031708`
- `0x18005378c`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002caba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002caf4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002caba`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002caf4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c9c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ca59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002cb6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002cb7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c9c6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ca59`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002cb6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002cb7b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c9f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002ca8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c9f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002ca8e`

## string_xrefs

- `0x18002c9a3`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`
- `0x18002ca11`: `onecore\ds\security\fido\webauthn\dll\webauthnngc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall I_GetMsaAccountDetails(const WCHAR *a1, _QWORD *a2, _QWORD *a3)
{
  __int64 v6; // rcx
  int WebAccount; // eax
  unsigned int v8; // ebx
  wil::details::in1diag3 *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rsi
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, HSTRING *); // rbx
  PCWSTR v18; // rbx
  HLOCAL v19; // rax
  void *v20; // r14
  HLOCAL v21; // rax
  void *v22; // rdi
  int v24; // [rsp+20h] [rbp-58h]
  UINT32 v25; // [rsp+30h] [rbp-48h] BYREF
  HSTRING v26; // [rsp+38h] [rbp-40h] BYREF
  HSTRING string; // [rsp+40h] [rbp-38h] BYREF
  int v28[2]; // [rsp+48h] [rbp-30h] BYREF
  void *v29; // [rsp+50h] [rbp-28h] BYREF
  void *v30; // [rsp+58h] [rbp-20h] BYREF
  _QWORD v31[3]; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  UINT32 length; // [rsp+D8h] [rbp+60h] BYREF

  *(_QWORD *)v28 = 0;
  v31[0] = 0;
  string = 0;
  length = 0;
  v26 = 0;
  v25 = 0;
  v30 = 0;
  v29 = 0;
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(v28);
  WebAccount = I_GetWebAccount(v6, L"consumers", L"SafeCustomerId", a1, (__int64)v28);
  v8 = WebAccount;
  v9 = retaddr;
  if ( WebAccount >= 0 )
  {
    v11 = *(_QWORD *)v28;
    v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(**(_QWORD **)v28 + 56LL);
    WindowsDeleteString(string);
    string = 0;
    WebAccount = v12(v11, &string);
    v8 = WebAccount;
    v9 = retaddr;
    if ( WebAccount < 0 )
    {
      v10 = 513;
      goto LABEL_3;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    if ( StringRawBuffer )
    {
      WebAccount = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(
                     (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))v28,
                     (__int64)v31);
      v8 = WebAccount;
      v9 = retaddr;
      if ( WebAccount < 0 )
      {
        v10 = 521;
        goto LABEL_3;
      }
      v16 = v31[0];
      v17 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v31[0] + 48LL);
      WindowsDeleteString(v26);
      v26 = 0;
      WebAccount = v17(v16, &v26);
      v8 = WebAccount;
      v9 = retaddr;
      if ( WebAccount < 0 )
      {
        v10 = 522;
        goto LABEL_3;
      }
      v18 = WindowsGetStringRawBuffer(v26, &v25);
      if ( v18 )
      {
        v19 = LocalAlloc(0x40u, 2LL * ++length);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v30,
          v19);
        v20 = v30;
        if ( v30 )
        {
          v21 = LocalAlloc(0x40u, 2LL * ++v25);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &v29,
            v21);
          v22 = v29;
          if ( v29 )
          {
            memcpy_0(v20, StringRawBuffer, 2LL * length);
            memcpy_0(v22, v18, 2LL * v25);
            v30 = 0;
            *a2 = v20;
            v29 = 0;
            *a3 = v22;
            v8 = 0;
            goto LABEL_21;
          }
          v15 = 2147942414LL;
          v14 = 535;
        }
        else
        {
          v15 = 2147942414LL;
          v14 = 531;
        }
        goto LABEL_9;
      }
      v14 = 526;
    }
    else
    {
      v14 = 517;
    }
    v15 = 2148073489LL;
LABEL_9:
    v8 = v15;
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
      (const char *)v15,
      v24);
    goto LABEL_21;
  }
  v10 = 510;
LABEL_3:
  wil::details::in1diag3::_Log_Hr(
    v9,
    (void *)v10,
    (unsigned int)"onecore\\ds\\security\\fido\\webauthn\\dll\\webauthnngc.cpp",
    (const char *)(unsigned int)WebAccount,
    v24);
LABEL_21:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v29);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v30);
  WindowsDeleteString(v26);
  v26 = 0;
  WindowsDeleteString(string);
  string = 0;
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(v31);
  _InternalRelease___ComPtr_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__U__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___23___YAJPEAU__IAsyncOperation_PEAVGattCharacteristicsResult_GenericAttributeProfile_Bluetooth_Devices_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__WRL_Microsoft__IEAAKXZ(v28);
  return v8;
}

```

## disassembly

```asm
0x18002c92c  push    rbp
0x18002c92e  push    rbx
0x18002c92f  push    rsi
0x18002c930  push    rdi
0x18002c931  push    r12
0x18002c933  push    r13
0x18002c935  push    r14
0x18002c937  push    r15
0x18002c939  mov     rbp, rsp
0x18002c93c  sub     rsp, 78h
0x18002c940  mov     r15, r8
0x18002c943  mov     r12, rdx
0x18002c946  mov     rbx, rcx
0x18002c949  xor     r13d, r13d
0x18002c94c  mov     qword ptr [rbp+var_30], r13
0x18002c950  mov     [rbp+var_18], r13
0x18002c954  mov     [rbp+string], r13
0x18002c958  mov     [rbp+length], r13d
0x18002c95c  mov     [rbp+var_40], r13
0x18002c960  mov     [rbp+var_48], r13d
0x18002c964  mov     [rbp+var_20], r13
0x18002c968  mov     [rbp+var_28], r13
0x18002c96c  lea     rcx, [rbp+var_30]
0x18002c970  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002c975  lea     rax, [rbp+var_30]
0x18002c979  mov     qword ptr [rsp+78h+var_58], rax; int
0x18002c97e  mov     r9, rbx
0x18002c981  lea     r8, aSafecustomerid; "SafeCustomerId"
0x18002c988  lea     rdx, aConsumers; "consumers"
0x18002c98f  call    I_GetWebAccount
0x18002c994  mov     ebx, eax
0x18002c996  mov     rcx, [rbp+40h]; this
0x18002c99a  test    eax, eax
0x18002c99c  jns     short loc_18002C9B7
0x18002c99e  mov     edx, 1FEh; void *
0x18002c9a3  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18002c9aa  mov     r9d, eax; char *
0x18002c9ad  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002c9b2  jmp     loc_18002CB55
0x18002c9b7  mov     rdi, qword ptr [rbp+var_30]
0x18002c9bb  mov     rax, [rdi]
0x18002c9be  mov     rbx, [rax+38h]
0x18002c9c2  mov     rcx, [rbp+string]; string
0x18002c9c6  call    cs:__imp_WindowsDeleteString
0x18002c9cc  mov     [rbp+string], r13
0x18002c9d0  lea     rdx, [rbp+string]
0x18002c9d4  mov     rcx, rdi
0x18002c9d7  mov     rax, rbx
0x18002c9da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c9df  mov     ebx, eax
0x18002c9e1  mov     rcx, [rbp+40h]
0x18002c9e5  test    eax, eax
0x18002c9e7  jns     short loc_18002C9F0
0x18002c9e9  mov     edx, 201h
0x18002c9ee  jmp     short loc_18002C9A3
0x18002c9f0  lea     rdx, [rbp+length]; length
0x18002c9f4  mov     rcx, [rbp+string]; string
0x18002c9f8  call    cs:__imp_WindowsGetStringRawBuffer
0x18002c9fe  mov     rsi, rax
0x18002ca01  test    rax, rax
0x18002ca04  jnz     short loc_18002CA29
0x18002ca06  mov     edx, 205h; void *
0x18002ca0b  mov     r9d, 80090011h; char *
0x18002ca11  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\fido\\webauthn\\"...
0x18002ca18  mov     rcx, [rbp+40h]; this
0x18002ca1c  mov     ebx, r9d
0x18002ca1f  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18002ca24  jmp     loc_18002CB55
0x18002ca29  lea     rdx, [rbp+var_18]
0x18002ca2d  lea     rcx, [rbp+var_30]
0x18002ca31  call    ??$As@UIWebAccount2@Credentials@Security@Windows@@@?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccount2@Credentials@Security@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Security::Credentials::IWebAccount2>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount2>>)
0x18002ca36  mov     ebx, eax
0x18002ca38  mov     rcx, [rbp+40h]
0x18002ca3c  test    eax, eax
0x18002ca3e  jns     short loc_18002CA4A
0x18002ca40  mov     edx, 209h
0x18002ca45  jmp     loc_18002C9A3
0x18002ca4a  mov     rdi, [rbp+var_18]
0x18002ca4e  mov     rax, [rdi]
0x18002ca51  mov     rbx, [rax+30h]
0x18002ca55  mov     rcx, [rbp+var_40]; string
0x18002ca59  call    cs:__imp_WindowsDeleteString
0x18002ca5f  mov     [rbp+var_40], r13
0x18002ca63  lea     rdx, [rbp+var_40]
0x18002ca67  mov     rcx, rdi
0x18002ca6a  mov     rax, rbx
0x18002ca6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ca72  mov     ebx, eax
0x18002ca74  mov     rcx, [rbp+40h]
0x18002ca78  test    eax, eax
0x18002ca7a  jns     short loc_18002CA86
0x18002ca7c  mov     edx, 20Ah
0x18002ca81  jmp     loc_18002C9A3
0x18002ca86  lea     rdx, [rbp+var_48]; length
0x18002ca8a  mov     rcx, [rbp+var_40]; string
0x18002ca8e  call    cs:__imp_WindowsGetStringRawBuffer
0x18002ca94  mov     rbx, rax
0x18002ca97  test    rax, rax
0x18002ca9a  jnz     short loc_18002CAA6
0x18002ca9c  mov     edx, 20Eh
0x18002caa1  jmp     loc_18002CA0B
0x18002caa6  mov     eax, [rbp+length]
0x18002caa9  inc     eax
0x18002caab  mov     [rbp+length], eax
0x18002caae  mov     edx, eax
0x18002cab0  add     rdx, rdx; uBytes
0x18002cab3  mov     edi, 40h ; '@'
0x18002cab8  mov     ecx, edi; uFlags
0x18002caba  call    cs:__imp_LocalAlloc
0x18002cac0  mov     rdx, rax
0x18002cac3  lea     rcx, [rbp+var_20]
0x18002cac7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002cacc  mov     r14, [rbp+var_20]
0x18002cad0  test    r14, r14
0x18002cad3  jnz     short loc_18002CAE5
0x18002cad5  mov     r9d, 8007000Eh
0x18002cadb  mov     edx, 213h
0x18002cae0  jmp     loc_18002CA11
0x18002cae5  mov     eax, [rbp+var_48]
0x18002cae8  inc     eax
0x18002caea  mov     [rbp+var_48], eax
0x18002caed  mov     edx, eax
0x18002caef  add     rdx, rdx; uBytes
0x18002caf2  mov     ecx, edi; uFlags
0x18002caf4  call    cs:__imp_LocalAlloc
0x18002cafa  mov     rdx, rax
0x18002cafd  lea     rcx, [rbp+var_28]
0x18002cb01  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002cb06  mov     rdi, [rbp+var_28]
0x18002cb0a  test    rdi, rdi
0x18002cb0d  jnz     short loc_18002CB1F
0x18002cb0f  mov     r9d, 8007000Eh
0x18002cb15  mov     edx, 217h
0x18002cb1a  jmp     loc_18002CA11
0x18002cb1f  mov     r8d, [rbp+length]
0x18002cb23  add     r8, r8; Size
0x18002cb26  mov     rdx, rsi; Src
0x18002cb29  mov     rcx, r14; void *
0x18002cb2c  call    memcpy_0
0x18002cb31  mov     r8d, [rbp+var_48]
0x18002cb35  add     r8, r8; Size
0x18002cb38  mov     rdx, rbx; Src
0x18002cb3b  mov     rcx, rdi; void *
0x18002cb3e  call    memcpy_0
0x18002cb43  mov     [rbp+var_20], r13
0x18002cb47  mov     [r12], r14
0x18002cb4b  mov     [rbp+var_28], r13
0x18002cb4f  mov     [r15], rdi
0x18002cb52  mov     ebx, r13d
0x18002cb55  lea     rcx, [rbp+var_28]
0x18002cb59  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18002cb5e  nop
0x18002cb5f  lea     rcx, [rbp+var_20]
0x18002cb63  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18002cb68  nop
0x18002cb69  mov     rcx, [rbp+var_40]; string
0x18002cb6d  call    cs:__imp_WindowsDeleteString
0x18002cb73  mov     [rbp+var_40], r13
0x18002cb77  mov     rcx, [rbp+string]; string
0x18002cb7b  call    cs:__imp_WindowsDeleteString
0x18002cb81  mov     [rbp+string], r13
0x18002cb85  lea     rcx, [rbp+var_18]
0x18002cb89  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002cb8e  nop
0x18002cb8f  lea     rcx, [rbp+var_30]
0x18002cb93  call    ?InternalRelease@?$ComPtr@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVGattCharacteristicsResult@GenericAttributeProfile@Bluetooth@Devices@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>,Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *>>(Windows::Foundation::IAsyncOperation<Windows::Devices::Bluetooth::GenericAttributeProfile::GattCharacteristicsResult *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate>::InternalRelease(void)
0x18002cb98  mov     eax, ebx
0x18002cb9a  add     rsp, 78h
0x18002cb9e  pop     r15
0x18002cba0  pop     r14
0x18002cba2  pop     r13
0x18002cba4  pop     r12
0x18002cba6  pop     rdi
0x18002cba7  pop     rsi
0x18002cba8  pop     rbx
0x18002cba9  pop     rbp
0x18002cbaa  retn
```
