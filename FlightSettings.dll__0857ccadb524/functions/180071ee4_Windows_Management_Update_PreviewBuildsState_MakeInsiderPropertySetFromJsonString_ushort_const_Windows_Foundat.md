# Windows::Management::Update::PreviewBuildsState::MakeInsiderPropertySetFromJsonString(ushort const *,Windows::Foundation::Collections::IPropertySet * *)

- ea: `0x180071ee4`
- end: `0x180072161`
- name: `?MakeInsiderPropertySetFromJsonString@PreviewBuildsState@Update@Management@Windows@@AEAAJPEBGPEAPEAUIPropertySet@Collections@Foundation@4@@Z`
- size: `637`
- prototype: `int(Windows::Management::Update::PreviewBuildsState *__hidden this, const unsigned __int16 *, struct Windows::Foundation::Collections::IPropertySet **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180072e28`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x1800168c8`
- `0x18002dc8c`
- `0x180032640`
- `0x1800334b4`
- `0x18006ef08`
- `0x18006f4ac`
- `0x18006f670`
- `0x180071ee4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180071f95`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007204e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180071f95`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18007204e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180071fa9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180072035`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180071fa9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180072035`

## string_xrefs

- `0x180071f39`: `onecore\base\flighting\flightsettings\broker\libs\previewbuildsmanager\previewbuildsmanagerclass.cpp`
- `0x180071fcf`: `onecore\base\flighting\flightsettings\broker\libs\previewbuildsmanager\previewbuildsmanagerclass.cpp`
- `0x18007206e`: `onecore\base\flighting\flightsettings\broker\libs\previewbuildsmanager\previewbuildsmanagerclass.cpp`
- `0x1800720b4`: `onecore\base\flighting\flightsettings\broker\libs\previewbuildsmanager\previewbuildsmanagerclass.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Management::Update::PreviewBuildsState::MakeInsiderPropertySetFromJsonString(
        Windows::Management::Update::PreviewBuildsState *this,
        const unsigned __int16 *a2,
        struct Windows::Foundation::Collections::IPropertySet **a3)
{
  __int64 *v6; // rax
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, HSTRING, _QWORD); // rsi
  unsigned __int64 v11; // rcx
  int v12; // eax
  void (__fastcall ***v13)(_QWORD, _QWORD, _QWORD); // rbx
  void (__fastcall *v14)(_QWORD, GUID *, __int64 *); // rdi
  int v15; // eax
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rax
  struct Windows::Foundation::Collections::IPropertySet *v19; // rax
  struct Windows::Foundation::Collections::IPropertySet *v21; // [rsp+20h] [rbp-60h] BYREF
  void (__fastcall ***v22)(_QWORD, GUID *, __int64 *); // [rsp+28h] [rbp-58h] BYREF
  __int64 v23; // [rsp+30h] [rbp-50h] BYREF
  UINT32 length; // [rsp+38h] [rbp-48h] BYREF
  __int64 v25; // [rsp+40h] [rbp-40h] BYREF
  int v26; // [rsp+48h] [rbp-38h] BYREF
  __int64 v27; // [rsp+50h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v27 = 0;
  v6 = (__int64 *)Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[29])a2);
  v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(
         *v6,
         (__int64)&v27);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v22 = 0;
    v9 = v27;
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v27 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
    length = 0;
    v11 = -1;
    do
      ++v11;
    while ( a2[v11] );
    if ( (int)ULongLongToUInt(v11, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(a2, length, &hstringHeader, &string);
    v12 = v10(v9, string, &v22);
    v8 = v12;
    if ( v12 >= 0 )
    {
      v23 = 0;
      v13 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v22;
      v14 = **v22;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
      v14(v13, &GUID_c9d9a725_786b_5113_b4b7_9b61764c220b, &v23);
      v21 = 0;
      if ( WindowsCreateStringReference(L"Windows.Foundation.Collections.PropertySet", 0x2Au, &hstringHeader, &string) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v15 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
              (__int64)string,
              &v21);
      v8 = v15;
      if ( v15 >= 0 )
      {
        v25 = 0;
        v16 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
                (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v21,
                (__int64)&v25);
        v8 = v16;
        if ( v16 >= 0 )
        {
          v18 = _lambda_c13de4e5b747f9effa4e76b0f80b5260_::_lambda_c13de4e5b747f9effa4e76b0f80b5260_(
                  &string,
                  &v26,
                  this,
                  &v25);
          v16 = FoundationCollectionHelper::_ForEach_Windows::Foundation::Collections::IKeyValuePair_HSTRING_____Windows::Data::Json::IJsonValue______Microsoft::WRL::ComPtr_Windows::Foundation::Collections::IKeyValuePair_HSTRING_____Windows::Data::Json::IJsonValue_______lambda_ee232e89f020fff5bb35b11535e93406____(
                  v23,
                  v18);
          v8 = v16;
          v26 = v16;
          if ( v16 >= 0 )
          {
            v19 = v21;
            v21 = 0;
            *a3 = v19;
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v21);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
            v8 = 0;
            goto LABEL_21;
          }
          v17 = 186;
        }
        else
        {
          v17 = 164;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\previewbuildsmanager\\previewbuildsmanagerclass.cpp",
          (const char *)(unsigned int)v16,
          (int)v21);
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v25);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA1,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\previewbuildsmanager\\previewbuildsmanagerclass.cpp",
          (const char *)(unsigned int)v15,
          (int)v21);
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v21);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9B,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\previewbuildsmanager\\previewbuildsmanagerclass.cpp",
        (const char *)(unsigned int)v12,
        (int)v21);
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\previewbuildsmanager\\previewbuildsmanagerclass.cpp",
      (const char *)(unsigned int)v7,
      (int)v21);
  }
LABEL_21:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v27);
  return v8;
}

```

## disassembly

```asm
0x180071ee4  push    rbp
0x180071ee6  push    rbx
0x180071ee7  push    rsi
0x180071ee8  push    rdi
0x180071ee9  push    r12
0x180071eeb  push    r14
0x180071eed  push    r15
0x180071eef  mov     rbp, rsp
0x180071ef2  sub     rsp, 80h
0x180071ef9  mov     rax, cs:__security_cookie
0x180071f00  xor     rax, rsp
0x180071f03  mov     [rbp+var_8], rax
0x180071f07  mov     r14, r8
0x180071f0a  mov     rdi, rdx
0x180071f0d  mov     r15, rcx
0x180071f10  xor     r12d, r12d
0x180071f13  mov     [rbp+var_30], r12
0x180071f17  lea     rcx, [rbp+string]; string
0x180071f1b  call    ??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[29])
0x180071f20  lea     rdx, [rbp+var_30]
0x180071f24  mov     rcx, [rax]
0x180071f27  call    ??$GetActivationFactory@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>)
0x180071f2c  mov     ebx, eax
0x180071f2e  test    eax, eax
0x180071f30  jns     short loc_180071F4F
0x180071f32  mov     rcx, [rbp+38h]; this
0x180071f36  mov     r9d, eax; char *
0x180071f39  lea     r8, aOnecoreBaseFli_92; "onecore\\base\\flighting\\flightsetting"...
0x180071f40  mov     edx, 98h; void *
0x180071f45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071f4a  jmp     loc_180072138
0x180071f4f  mov     [rbp+var_58], r12
0x180071f53  mov     rbx, [rbp+var_30]
0x180071f57  mov     rax, [rbx]
0x180071f5a  mov     rsi, [rax+30h]
0x180071f5e  lea     rcx, [rbp+var_58]
0x180071f62  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180071f67  mov     [rbp+length], r12d
0x180071f6b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180071f6f  inc     rcx; unsigned __int64
0x180071f72  cmp     [rdi+rcx*2], r12w
0x180071f77  jnz     short loc_180071F6F
0x180071f79  lea     rdx, [rbp+length]; unsigned int *
0x180071f7d  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180071f82  test    eax, eax
0x180071f84  jns     short loc_180071F9B
0x180071f86  xor     r9d, r9d; lpArguments
0x180071f89  xor     r8d, r8d; nNumberOfArguments
0x180071f8c  lea     edx, [r9+1]; dwExceptionFlags
0x180071f90  mov     ecx, 0C000000Dh; dwExceptionCode
0x180071f95  call    cs:__imp_RaiseException
0x180071f9b  lea     r9, [rbp+string]; string
0x180071f9f  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180071fa3  mov     edx, [rbp+length]; length
0x180071fa6  mov     rcx, rdi; sourceString
0x180071fa9  call    cs:__imp_WindowsCreateStringReference
0x180071faf  lea     r8, [rbp+var_58]
0x180071fb3  mov     rdx, [rbp+string]
0x180071fb7  mov     rcx, rbx
0x180071fba  mov     rax, rsi
0x180071fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071fc2  mov     ebx, eax
0x180071fc4  test    eax, eax
0x180071fc6  jns     short loc_180071FEF
0x180071fc8  mov     rcx, [rbp+38h]; this
0x180071fcc  mov     r9d, eax; char *
0x180071fcf  lea     r8, aOnecoreBaseFli_92; "onecore\\base\\flighting\\flightsetting"...
0x180071fd6  mov     edx, 9Bh; void *
0x180071fdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071fe0  nop
0x180071fe1  lea     rcx, [rbp+var_58]
0x180071fe5  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180071fea  jmp     loc_180072138
0x180071fef  mov     [rbp+var_50], r12
0x180071ff3  mov     rbx, [rbp+var_58]
0x180071ff7  mov     rax, [rbx]
0x180071ffa  mov     rdi, [rax]
0x180071ffd  lea     rcx, [rbp+var_50]
0x180072001  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180072006  lea     r8, [rbp+var_50]
0x18007200a  lea     rdx, _GUID_c9d9a725_786b_5113_b4b7_9b61764c220b
0x180072011  mov     rcx, rbx
0x180072014  mov     rax, rdi
0x180072017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007201c  nop
0x18007201d  mov     [rbp+var_60], r12
0x180072021  lea     r9, [rbp+string]; string
0x180072025  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180072029  mov     edx, 2Ah ; '*'; length
0x18007202e  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_PropertySet@@3QBGB; "Windows.Foundation.Collections.Property"...
0x180072035  call    cs:__imp_WindowsCreateStringReference
0x18007203b  test    eax, eax
0x18007203d  jns     short loc_180072054
0x18007203f  xor     r9d, r9d; lpArguments
0x180072042  xor     r8d, r8d; nNumberOfArguments
0x180072045  lea     edx, [r9+1]; dwExceptionFlags
0x180072049  mov     ecx, 0C000000Dh; dwExceptionCode
0x18007204e  call    cs:__imp_RaiseException
0x180072054  lea     rdx, [rbp+var_60]
0x180072058  mov     rcx, [rbp+string]
0x18007205c  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x180072061  mov     ebx, eax
0x180072063  test    eax, eax
0x180072065  jns     short loc_180072098
0x180072067  mov     rcx, [rbp+38h]; this
0x18007206b  mov     r9d, eax; char *
0x18007206e  lea     r8, aOnecoreBaseFli_92; "onecore\\base\\flighting\\flightsetting"...
0x180072075  mov     edx, 0A1h; void *
0x18007207a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007207f  nop
0x180072080  lea     rcx, [rbp+var_60]
0x180072084  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180072089  nop
0x18007208a  lea     rcx, [rbp+var_50]
0x18007208e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180072093  jmp     loc_180071FE1
0x180072098  mov     [rbp+var_40], r12
0x18007209c  lea     rdx, [rbp+var_40]
0x1800720a0  lea     rcx, [rbp+var_60]
0x1800720a4  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x1800720a9  mov     ebx, eax
0x1800720ab  test    eax, eax
0x1800720ad  jns     short loc_1800720D3
0x1800720af  mov     edx, 0A4h; void *
0x1800720b4  lea     r8, aOnecoreBaseFli_92; "onecore\\base\\flighting\\flightsetting"...
0x1800720bb  mov     r9d, eax; char *
0x1800720be  mov     rcx, [rbp+38h]; this
0x1800720c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800720c7  nop
0x1800720c8  lea     rcx, [rbp+var_40]
0x1800720cc  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800720d1  jmp     short loc_180072080
0x1800720d3  lea     r9, [rbp+var_40]
0x1800720d7  mov     r8, r15
0x1800720da  lea     rdx, [rbp+var_38]
0x1800720de  lea     rcx, [rbp+string]
0x1800720e2  call    ??0_lambda_c13de4e5b747f9effa4e76b0f80b5260_@@QEAA@PEAV?$SimpleVectorView@PEAUIUnknown@@V?$Vector@PEAUIUnknown@@U?$DefaultEqualityPredicate@PEAUIUnknown@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIUnknown@@@3456@U?$VectorOptions@PEAUIUnknown@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIUnknown@@@3456@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@AEAIAEAPEAPEAUIUnknown@@@Z; _lambda_c13de4e5b747f9effa4e76b0f80b5260_::_lambda_c13de4e5b747f9effa4e76b0f80b5260_(Windows::Foundation::Collections::Internal::SimpleVectorView<IUnknown *,Windows::Foundation::Collections::Internal::Vector<IUnknown *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IUnknown *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IUnknown *>,Windows::Foundation::Collections::Internal::VectorOptions<IUnknown *,0,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IUnknown *>,XWinRT::IntVersionTag,1> *,uint &,IUnknown * * &)
0x1800720e7  mov     rdx, rax
0x1800720ea  mov     rcx, [rbp+var_50]
0x1800720ee  call    FoundationCollectionHelper___ForEach_Windows__Foundation__Collections__IKeyValuePair_HSTRING_____Windows__Data__Json__IJsonValue______Microsoft__WRL__ComPtr_Windows__Foundation__Collections__IKeyValuePair_HSTRING_____Windows__Data__Json__IJsonValue_______lambda_ee232e89f020fff5bb35b11535e93406____
0x1800720f3  mov     ebx, eax
0x1800720f5  mov     [rbp+var_38], eax
0x1800720f8  test    eax, eax
0x1800720fa  jns     short loc_180072103
0x1800720fc  mov     edx, 0BAh
0x180072101  jmp     short loc_1800720B4
0x180072103  mov     rax, [rbp+var_60]
0x180072107  mov     [rbp+var_60], r12
0x18007210b  mov     [r14], rax
0x18007210e  lea     rcx, [rbp+var_40]
0x180072112  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180072117  nop
0x180072118  lea     rcx, [rbp+var_60]
0x18007211c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180072121  nop
0x180072122  lea     rcx, [rbp+var_50]
0x180072126  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18007212b  nop
0x18007212c  lea     rcx, [rbp+var_58]
0x180072130  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180072135  mov     ebx, r12d
0x180072138  lea     rcx, [rbp+var_30]
0x18007213c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180072141  mov     eax, ebx
0x180072143  mov     rcx, [rbp+var_8]
0x180072147  xor     rcx, rsp; StackCookie
0x18007214a  call    __security_check_cookie
0x18007214f  add     rsp, 80h
0x180072156  pop     r15
0x180072158  pop     r14
0x18007215a  pop     r12
0x18007215c  pop     rdi
0x18007215d  pop     rsi
0x18007215e  pop     rbx
0x18007215f  pop     rbp
0x180072160  retn
```
