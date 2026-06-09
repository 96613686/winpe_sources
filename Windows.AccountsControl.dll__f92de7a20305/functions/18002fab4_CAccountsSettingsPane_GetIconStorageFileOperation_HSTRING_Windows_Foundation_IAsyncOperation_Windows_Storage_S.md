# CAccountsSettingsPane::_GetIconStorageFileOperation(HSTRING__ *,Windows::Foundation::IAsyncOperation<Windows::Storage::StorageFile *> * *)

- ea: `0x18002fab4`
- end: `0x18002fc84`
- name: `?_GetIconStorageFileOperation@CAccountsSettingsPane@@AEAAJPEAUHSTRING__@@PEAPEAU?$IAsyncOperation@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@@Z`
- size: `464`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f910`

## callees

- `0x180006eac`
- `0x18000e87c`
- `0x180011ffc`
- `0x18001ba14`
- `0x18002fab4`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002fbe2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002fbe2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002fbc9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002fbc9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002fb29`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002fb29`

## string_xrefs

- `0x18002fafe`: `Windows.Foundation.Uri`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CAccountsSettingsPane::_GetIconStorageFileOperation(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // rbx
  int ActivationFactory; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, __int64, __int64 *); // rbx
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  __int64 v14; // [rsp+20h] [rbp-40h] BYREF
  __int64 v15; // [rsp+28h] [rbp-38h] BYREF
  __int64 v16; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  *a3 = 0;
  v16 = 0;
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    (HSTRING_HEADER *)&string,
    L"Windows.Foundation.Uri",
    0x17u,
    0x16u);
  v5 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[16];
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
  ActivationFactory = RoGetActivationFactory(v5, &GUID_44a9796f_723e_4fdf_a218_033e75b0c084, &v16);
  v7 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v14 = 0;
    v8 = v16;
    v9 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v16 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
    v10 = v9(v8, a2, &v14);
    v7 = v10;
    if ( v10 >= 0 )
    {
      v15 = 0;
      if ( WindowsCreateStringReference(L"Windows.Storage.StorageFile", 0x1Bu, &hstringHeader, &string) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v11 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Storage::IStorageFileStatics>>(
              string,
              &v15);
      v7 = v11;
      if ( v11 >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v15 + 56LL))(v15, v14, a3);
        v7 = v11;
        if ( v11 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
          v7 = 0;
          goto LABEL_14;
        }
        v12 = 392;
      }
      else
      {
        v12 = 391;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
        (const char *)(unsigned int)v11,
        v14);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v15);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x184,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
        (const char *)(unsigned int)v10,
        v14);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v14);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x181,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountssettingspanestatics.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v14);
  }
LABEL_14:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v16);
  return v7;
}

```

## disassembly

```asm
0x18002fab4  mov     [rsp-18h+arg_0], rbx
0x18002fab9  mov     [rsp-18h+arg_18], rsi
0x18002fabe  push    rbp
0x18002fabf  push    rdi
0x18002fac0  push    r14
0x18002fac2  mov     rbp, rsp
0x18002fac5  sub     rsp, 60h
0x18002fac9  mov     rax, cs:__security_cookie
0x18002fad0  xor     rax, rsp
0x18002fad3  mov     [rbp+var_8], rax
0x18002fad7  mov     rsi, r8
0x18002fada  mov     r14, rdx
0x18002fadd  mov     qword ptr [r8], 0
0x18002fae4  mov     [rbp+var_30], 0
0x18002faec  mov     qword ptr [rbp+hstringHeader.Reserved+10h], 0
0x18002faf4  mov     r9d, 16h; unsigned int
0x18002fafa  lea     r8d, [r9+1]; unsigned int
0x18002fafe  lea     rdx, ?RuntimeClass_Windows_Foundation_Uri@@3QBGB; "Windows.Foundation.Uri"
0x18002fb05  lea     rcx, [rbp+string]; hstringHeader
0x18002fb09  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002fb0e  mov     rbx, qword ptr [rbp+hstringHeader.Reserved+10h]
0x18002fb12  lea     rcx, [rbp+var_30]
0x18002fb16  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002fb1b  lea     r8, [rbp+var_30]
0x18002fb1f  lea     rdx, _GUID_44a9796f_723e_4fdf_a218_033e75b0c084
0x18002fb26  mov     rcx, rbx
0x18002fb29  call    cs:__imp_RoGetActivationFactory
0x18002fb2f  mov     ebx, eax
0x18002fb31  test    eax, eax
0x18002fb33  jns     short loc_18002FB52
0x18002fb35  mov     rcx, [rbp+18h]; this
0x18002fb39  mov     r9d, eax; char *
0x18002fb3c  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x18002fb43  mov     edx, 181h; void *
0x18002fb48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fb4d  jmp     loc_18002FC58
0x18002fb52  mov     [rbp+var_40], 0
0x18002fb5a  mov     rdi, [rbp+var_30]
0x18002fb5e  mov     rax, [rdi]
0x18002fb61  mov     rbx, [rax+30h]
0x18002fb65  lea     rcx, [rbp+var_40]
0x18002fb69  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002fb6e  lea     r8, [rbp+var_40]
0x18002fb72  mov     rdx, r14
0x18002fb75  mov     rcx, rdi
0x18002fb78  mov     rax, rbx
0x18002fb7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb80  mov     ebx, eax
0x18002fb82  test    eax, eax
0x18002fb84  jns     short loc_18002FBAD
0x18002fb86  mov     rcx, [rbp+18h]; this
0x18002fb8a  mov     r9d, eax; char *
0x18002fb8d  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x18002fb94  mov     edx, 184h; void *
0x18002fb99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fb9e  nop
0x18002fb9f  lea     rcx, [rbp+var_40]
0x18002fba3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002fba8  jmp     loc_18002FC58
0x18002fbad  mov     [rbp+var_38], 0
0x18002fbb5  lea     r9, [rbp+string]; string
0x18002fbb9  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18002fbbd  mov     edx, 1Bh; length
0x18002fbc2  lea     rcx, ?RuntimeClass_Windows_Storage_StorageFile@@3QBGB; "Windows.Storage.StorageFile"
0x18002fbc9  call    cs:__imp_WindowsCreateStringReference
0x18002fbcf  test    eax, eax
0x18002fbd1  jns     short loc_18002FBE8
0x18002fbd3  xor     r9d, r9d; lpArguments
0x18002fbd6  xor     r8d, r8d; nNumberOfArguments
0x18002fbd9  lea     edx, [r9+1]; dwExceptionFlags
0x18002fbdd  mov     ecx, 0C000000Dh; dwExceptionCode
0x18002fbe2  call    cs:__imp_RaiseException
0x18002fbe8  lea     rdx, [rbp+var_38]
0x18002fbec  mov     rcx, [rbp+string]
0x18002fbf0  call    ??$GetActivationFactory@V?$ComPtr@UIStorageFileStatics@Storage@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIStorageFileStatics@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Storage::IStorageFileStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::IStorageFileStatics>>)
0x18002fbf5  mov     ebx, eax
0x18002fbf7  test    eax, eax
0x18002fbf9  jns     short loc_18002FC1F
0x18002fbfb  mov     edx, 187h; void *
0x18002fc00  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\accountscontrol\\api"...
0x18002fc07  mov     r9d, eax; char *
0x18002fc0a  mov     rcx, [rbp+18h]; this
0x18002fc0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fc13  nop
0x18002fc14  lea     rcx, [rbp+var_38]
0x18002fc18  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002fc1d  jmp     short loc_18002FB9F
0x18002fc1f  mov     rcx, [rbp+var_38]
0x18002fc23  mov     rax, [rcx]
0x18002fc26  mov     r8, rsi
0x18002fc29  mov     rdx, [rbp+var_40]
0x18002fc2d  mov     rax, [rax+38h]
0x18002fc31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fc36  mov     ebx, eax
0x18002fc38  test    eax, eax
0x18002fc3a  jns     short loc_18002FC43
0x18002fc3c  mov     edx, 188h
0x18002fc41  jmp     short loc_18002FC00
0x18002fc43  lea     rcx, [rbp+var_38]
0x18002fc47  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002fc4c  nop
0x18002fc4d  lea     rcx, [rbp+var_40]
0x18002fc51  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002fc56  xor     ebx, ebx
0x18002fc58  lea     rcx, [rbp+var_30]
0x18002fc5c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002fc61  mov     eax, ebx
0x18002fc63  mov     rcx, [rbp+var_8]
0x18002fc67  xor     rcx, rsp; StackCookie
0x18002fc6a  call    __security_check_cookie
0x18002fc6f  lea     r11, [rsp+60h+var_s0]
0x18002fc74  mov     rbx, [r11+20h]
0x18002fc78  mov     rsi, [r11+38h]
0x18002fc7c  mov     rsp, r11
0x18002fc7f  pop     r14
0x18002fc81  pop     rdi
0x18002fc82  pop     rbp
0x18002fc83  retn
```
