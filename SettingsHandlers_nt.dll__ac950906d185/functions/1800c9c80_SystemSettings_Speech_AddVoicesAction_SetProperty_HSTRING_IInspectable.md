# SystemSettings::Speech::AddVoicesAction::SetProperty(HSTRING__ *,IInspectable *)

- ea: `0x1800c9c80`
- end: `0x1800ca27a`
- name: `?SetProperty@AddVoicesAction@Speech@SystemSettings@@MEAAJPEAUHSTRING__@@PEAUIInspectable@@@Z`
- size: `1530`
- prototype: `__int64 __fastcall(SystemSettings::Speech::AddVoicesAction *__hidden this, HSTRING, struct IInspectable *)`
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000c840`
- `0x180011bb0`
- `0x180019a20`
- `0x18001ecfc`
- `0x180021398`
- `0x180021640`
- `0x180022980`
- `0x1800234f8`
- `0x18002373c`
- `0x18002395c`
- `0x180027d00`
- `0x18002dcbc`
- `0x18002f220`
- `0x180043948`
- `0x18004528c`
- `0x180045b2c`
- `0x180078604`
- `0x1800c6380`
- `0x1800c6a28`
- `0x1800c9c80`
- `0x1800ca52c`
- `0x1800d76fc`
- `0x1800d81b8`
- `0x1800d9854`
- `0x180289010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9d53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9d9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9e62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9eab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9ff8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ca0f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ca13c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ca195`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9d53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9d9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9e62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9eab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c9ff8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ca0f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ca13c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ca195`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9dcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9ed4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ca165`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9dcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9ed4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ca165`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall SystemSettings::Speech::AddVoicesAction::SetProperty(
        SystemSettings::Speech::AddVoicesAction *this,
        SystemSettings::DataModel *a2,
        struct IInspectable *a3)
{
  HRESULT (__stdcall *QueryInterface)(IInspectable *, const IID *const, void **); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  const unsigned __int16 *v10; // r8
  const unsigned __int16 *v11; // r8
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  unsigned int v15; // ebx
  PCWSTR StringRawBuffer; // rdx
  __int64 v17; // rcx
  __int64 LanguageCodeForBaseLanguage; // rax
  __int64 v19; // rdx
  const unsigned __int16 *v20; // r8
  __int64 v21; // r9
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, HSTRING *); // rbx
  int v24; // eax
  unsigned int v25; // ebx
  PCWSTR v26; // rax
  _QWORD **v27; // rdi
  _QWORD *v28; // rbx
  _QWORD *v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r14
  __int64 v32; // rax
  __int64 v33; // rcx
  int v34; // eax
  unsigned int v35; // ebx
  int v36; // eax
  unsigned int v37; // ebx
  const unsigned __int16 *v38; // r8
  __int64 v39; // rdi
  __int64 (__fastcall *v40)(__int64, HSTRING *); // rbx
  int v41; // eax
  unsigned int v42; // ebx
  PCWSTR v43; // rax
  int v44; // eax
  unsigned int v45; // ebx
  int v46[4]; // [rsp+20h] [rbp-A8h] BYREF
  __int64 v47; // [rsp+30h] [rbp-98h] BYREF
  __int64 v48; // [rsp+38h] [rbp-90h]
  __int128 *v49; // [rsp+40h] [rbp-88h]
  HSTRING string; // [rsp+48h] [rbp-80h] BYREF
  __int64 v51; // [rsp+50h] [rbp-78h] BYREF
  __int128 v52; // [rsp+58h] [rbp-70h] BYREF
  __int64 v53; // [rsp+68h] [rbp-60h]
  _BYTE v54[16]; // [rsp+70h] [rbp-58h] BYREF
  __int64 v55; // [rsp+80h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v51 = 0;
  QueryInterface = a3->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
  v7 = ((__int64 (__fastcall *)(struct IInspectable *, GUID *, __int64 *))QueryInterface)(
         a3,
         &GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62,
         &v51);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14C,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\addvoicesaction.cpp",
      (const char *)(unsigned int)v7,
      v46[0]);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    return v8;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NOCDM>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NOCDM>::GetImpl'::`2'::impl) )
  {
    if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802FFE78, v10) )
    {
      string = 0;
      v12 = v51;
      v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v51 + 152LL);
      WindowsDeleteString(0);
      string = 0;
      v14 = v13(v12, &string);
      v15 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x153,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\addvoicesaction.cpp",
          (const char *)(unsigned int)v14,
          v46[0]);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
        return v15;
      }
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      std::wstring::assign((char *)this + 248, StringRawBuffer);
      LanguageCodeForBaseLanguage = SystemSettings::Speech::AddVoicesSingleton::GetLanguageCodeForBaseLanguage(
                                      v17,
                                      v54,
                                      (char *)this + 248);
      std::wstring::operator=((char *)this + 352, LanguageCodeForBaseLanguage);
      std::wstring::_Tidy_deallocate(v54);
      SystemSettings::DataModel::CSettingBase::OnValueChanged(this, L"Value");
LABEL_31:
      WindowsDeleteString(string);
      goto LABEL_36;
    }
    if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802EDE08, v11) )
    {
      if ( !SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802FFF50, v20) )
      {
        v36 = SystemSettings::DataModel::CSettingBase::SetValue(this, (HSTRING)a2, a3);
        v37 = v36;
        if ( v36 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x17F,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\addvoicesaction.cpp",
            (const char *)(unsigned int)v36,
            v46[0]);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
          return v37;
        }
        goto LABEL_36;
      }
      string = 0;
      v22 = v51;
      v23 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v51 + 152LL);
      WindowsDeleteString(0);
      string = 0;
      v24 = v23(v22, &string);
      v25 = v24;
      if ( v24 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x168,
          (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\addvoicesaction.cpp",
          (const char *)(unsigned int)v24,
          v46[0]);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
        return v25;
      }
      v26 = WindowsGetStringRawBuffer(string, 0);
      std::wstring::wstring(v54, v26);
      if ( v55 )
      {
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::clear((char *)this + 280);
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
          (char *)this + 280,
          v46,
          v54);
        v27 = (_QWORD **)*((_QWORD *)this + 36);
        v28 = *v27;
        v52 = 0;
        v53 = 0;
        v29 = v28;
        v30 = 0;
        while ( v29 != v27 )
        {
          ++v30;
          v29 = (_QWORD *)*v29;
        }
        if ( v30 )
        {
          std::vector<std::wstring>::_Buy_nonzero(&v52);
          *(_QWORD *)v46 = &v52;
          v31 = v52;
          v47 = v52;
          v48 = v52;
          v49 = &v52;
          while ( v28 != v27 )
          {
            std::_Uninitialized_backout_al<std::allocator<std::wstring>>::_Emplace_back<std::wstring const &>(
              &v47,
              v28 + 2);
            v28 = (_QWORD *)*v28;
            v31 = v48;
          }
          std::_Destroy_range<std::allocator<std::wstring>>(v31, v31);
          *((_QWORD *)&v52 + 1) = v31;
          *(_QWORD *)v46 = 0;
          std::_Tidy_guard<std::vector<std::wstring>>::~_Tidy_guard<std::vector<std::wstring>>(v46);
        }
        v32 = std::vector<std::wstring>::vector<std::wstring>(&v47, &v52);
        v34 = SystemSettings::Speech::AddVoicesSingleton::RequestInstall(v33, v32);
        v35 = v34;
        if ( v34 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x173,
            (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\addvoicesaction.cpp",
            (const char *)(unsigned int)v34,
            v46[0]);
          std::vector<std::wstring>::_Tidy(&v52);
          std::wstring::_Tidy_deallocate(v54);
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
          return v35;
        }
        *((_BYTE *)this + 344) = 1;
        std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::clear((char *)this + 280);
        SystemSettings::Speech::AddVoicesSingleton::NotifyInstalledVoicesListChanged((SystemSettings::Speech::AddVoicesSingleton *)&SystemSettings::Speech::g_AddVoicesSingleton);
        SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_1802FFF08);
        SystemSettings::DataModel::CSettingBase::OnValueChanged(this, L"Value");
        std::vector<std::wstring>::_Tidy(&v52);
      }
      std::wstring::_Tidy_deallocate(v54);
      goto LABEL_31;
    }
    goto LABEL_33;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802FFE78, v10) )
  {
    string = 0;
    v39 = v51;
    v40 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v51 + 152LL);
    WindowsDeleteString(0);
    string = 0;
    v41 = v40(v39, &string);
    v42 = v41;
    if ( v41 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x187,
        (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\addvoicesaction.cpp",
        (const char *)(unsigned int)v41,
        v46[0]);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
      return v42;
    }
    v43 = WindowsGetStringRawBuffer(string, 0);
    std::wstring::assign((char *)this + 248, v43);
    SystemSettings::DataModel::CSettingBase::OnValueChanged(this, L"Value");
    goto LABEL_31;
  }
  if ( SystemSettings::DataModel::IsHstringEqual(a2, (HSTRING)&stru_1802EDE08, v38) )
  {
LABEL_33:
    *((_QWORD *)this + 33) = 0;
    *(_WORD *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)this + 248, v19, v20, v21) = 0;
    std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::clear((char *)this + 280);
    *((_BYTE *)this + 344) = 0;
    SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_1802FFF08);
    SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_1802FFEE0);
    goto LABEL_36;
  }
  v44 = SystemSettings::DataModel::CSettingBase::SetValue(this, (HSTRING)a2, a3);
  v45 = v44;
  if ( v44 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x195,
      (unsigned int)"shell\\systemsettingsthreshold\\handlers\\internal\\speech\\lib\\addvoicesaction.cpp",
      (const char *)(unsigned int)v44,
      v46[0]);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    return v45;
  }
LABEL_36:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
  return 0;
}

```

## disassembly

```asm
0x1800c9c80  mov     [rsp+arg_18], rbx
0x1800c9c85  push    rsi
0x1800c9c86  push    rdi
0x1800c9c87  push    r12
0x1800c9c89  push    r14
0x1800c9c8b  push    r15
0x1800c9c8d  sub     rsp, 0A0h
0x1800c9c94  mov     rax, cs:__security_cookie
0x1800c9c9b  xor     rax, rsp
0x1800c9c9e  mov     [rsp+0C8h+var_38], rax
0x1800c9ca6  mov     r14, r8
0x1800c9ca9  mov     rdi, rdx
0x1800c9cac  mov     rsi, rcx
0x1800c9caf  xor     r12d, r12d
0x1800c9cb2  mov     [rsp+0C8h+var_78], r12
0x1800c9cb7  mov     rax, [r8]
0x1800c9cba  mov     rbx, [rax]
0x1800c9cbd  lea     rcx, [rsp+0C8h+var_78]
0x1800c9cc2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c9cc7  lea     r8, [rsp+0C8h+var_78]
0x1800c9ccc  lea     rdx, _GUID_4bd682dd_7554_40e9_9a9b_82654ede7e62
0x1800c9cd3  mov     rcx, r14
0x1800c9cd6  mov     rax, rbx
0x1800c9cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9cde  mov     ebx, eax
0x1800c9ce0  test    eax, eax
0x1800c9ce2  jns     short loc_1800C9D12
0x1800c9ce4  mov     rcx, [rsp+0C8h]; this
0x1800c9cec  mov     r9d, eax; char *
0x1800c9cef  lea     r8, aShellSystemset_70; "shell\\systemsettingsthreshold\\handler"...
0x1800c9cf6  mov     edx, 14Ch; void *
0x1800c9cfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9d00  nop
0x1800c9d01  lea     rcx, [rsp+0C8h+var_78]
0x1800c9d06  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c9d0b  mov     eax, ebx
0x1800c9d0d  jmp     loc_1800CA251
0x1800c9d12  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NOCDM@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NOCDM@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NOCDM> `wil::Feature<__WilFeatureTraits_Feature_NOCDM>::GetImpl(void)'::`2'::impl
0x1800c9d19  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NOCDM@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NOCDM>::__private_IsEnabled(void)
0x1800c9d1e  lea     rdx, stru_1802FFE78; HSTRING
0x1800c9d25  mov     rcx, rdi; this
0x1800c9d28  test    al, al
0x1800c9d2a  jz      loc_1800CA0D0
0x1800c9d30  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800c9d35  test    al, al
0x1800c9d37  jz      loc_1800C9E1E
0x1800c9d3d  mov     [rsp+0C8h+string], r12
0x1800c9d42  mov     rdi, [rsp+0C8h+var_78]
0x1800c9d47  mov     rax, [rdi]
0x1800c9d4a  mov     rbx, [rax+98h]
0x1800c9d51  xor     ecx, ecx; string
0x1800c9d53  call    cs:__imp_WindowsDeleteString
0x1800c9d5a  nop     dword ptr [rax+rax+00h]
0x1800c9d5f  mov     [rsp+0C8h+string], r12
0x1800c9d64  lea     rdx, [rsp+0C8h+string]
0x1800c9d69  mov     rcx, rdi
0x1800c9d6c  mov     rax, rbx
0x1800c9d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9d74  mov     ebx, eax
0x1800c9d76  test    eax, eax
0x1800c9d78  jns     short loc_1800C9DBE
0x1800c9d7a  mov     rcx, [rsp+0C8h]; this
0x1800c9d82  mov     r9d, eax; char *
0x1800c9d85  lea     r8, aShellSystemset_70; "shell\\systemsettingsthreshold\\handler"...
0x1800c9d8c  mov     edx, 153h; void *
0x1800c9d91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9d96  nop
0x1800c9d97  mov     rcx, [rsp+0C8h+string]; string
0x1800c9d9c  call    cs:__imp_WindowsDeleteString
0x1800c9da3  nop     dword ptr [rax+rax+00h]
0x1800c9da8  mov     [rsp+0C8h+string], r12
0x1800c9dad  lea     rcx, [rsp+0C8h+var_78]
0x1800c9db2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c9db7  mov     eax, ebx
0x1800c9db9  jmp     loc_1800CA251
0x1800c9dbe  lea     rbx, [rsi+0F8h]
0x1800c9dc5  xor     edx, edx; length
0x1800c9dc7  mov     rcx, [rsp+0C8h+string]; string
0x1800c9dcc  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c9dd3  nop     dword ptr [rax+rax+00h]
0x1800c9dd8  mov     rdx, rax
0x1800c9ddb  mov     rcx, rbx
0x1800c9dde  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800c9de3  mov     r8, rbx
0x1800c9de6  lea     rdx, [rsp+0C8h+var_58]
0x1800c9deb  call    ?GetLanguageCodeForBaseLanguage@AddVoicesSingleton@Speech@SystemSettings@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV45@@Z; SystemSettings::Speech::AddVoicesSingleton::GetLanguageCodeForBaseLanguage(std::wstring const &)
0x1800c9df0  lea     rcx, [rsi+160h]
0x1800c9df7  mov     rdx, rax
0x1800c9dfa  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800c9dff  lea     rcx, [rsp+0C8h+var_58]
0x1800c9e04  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c9e09  lea     rdx, aValue_0; "Value"
0x1800c9e10  mov     rcx, rsi; this
0x1800c9e13  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x1800c9e18  nop
0x1800c9e19  jmp     loc_1800CA190
0x1800c9e1e  lea     rdx, stru_1802EDE08; HSTRING
0x1800c9e25  mov     rcx, rdi; this
0x1800c9e28  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800c9e2d  test    al, al
0x1800c9e2f  jnz     loc_1800CA1B9
0x1800c9e35  lea     rdx, stru_1802FFF50; HSTRING
0x1800c9e3c  mov     rcx, rdi; this
0x1800c9e3f  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800c9e44  test    al, al
0x1800c9e46  jz      loc_1800CA08A
0x1800c9e4c  mov     [rsp+0C8h+string], r12
0x1800c9e51  mov     rdi, [rsp+0C8h+var_78]
0x1800c9e56  mov     rax, [rdi]
0x1800c9e59  mov     rbx, [rax+98h]
0x1800c9e60  xor     ecx, ecx; string
0x1800c9e62  call    cs:__imp_WindowsDeleteString
0x1800c9e69  nop     dword ptr [rax+rax+00h]
0x1800c9e6e  mov     [rsp+0C8h+string], r12
0x1800c9e73  lea     rdx, [rsp+0C8h+string]
0x1800c9e78  mov     rcx, rdi
0x1800c9e7b  mov     rax, rbx
0x1800c9e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9e83  mov     ebx, eax
0x1800c9e85  test    eax, eax
0x1800c9e87  jns     short loc_1800C9ECD
0x1800c9e89  mov     rcx, [rsp+0C8h]; this
0x1800c9e91  mov     r9d, eax; char *
0x1800c9e94  lea     r8, aShellSystemset_70; "shell\\systemsettingsthreshold\\handler"...
0x1800c9e9b  mov     edx, 168h; void *
0x1800c9ea0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9ea5  nop
0x1800c9ea6  mov     rcx, [rsp+0C8h+string]; string
0x1800c9eab  call    cs:__imp_WindowsDeleteString
0x1800c9eb2  nop     dword ptr [rax+rax+00h]
0x1800c9eb7  mov     [rsp+0C8h+string], r12
0x1800c9ebc  lea     rcx, [rsp+0C8h+var_78]
0x1800c9ec1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c9ec6  mov     eax, ebx
0x1800c9ec8  jmp     loc_1800CA251
0x1800c9ecd  xor     edx, edx; length
0x1800c9ecf  mov     rcx, [rsp+0C8h+string]; string
0x1800c9ed4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c9edb  nop     dword ptr [rax+rax+00h]
0x1800c9ee0  mov     rdx, rax
0x1800c9ee3  lea     rcx, [rsp+0C8h+var_58]
0x1800c9ee8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800c9eed  nop
0x1800c9eee  cmp     [rsp+0C8h+var_48], r12
0x1800c9ef6  jz      loc_1800CA05F
0x1800c9efc  lea     r15, [rsi+118h]
0x1800c9f03  mov     rcx, r15
0x1800c9f06  call    ?clear@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::clear(void)
0x1800c9f0b  lea     r8, [rsp+0C8h+var_58]
0x1800c9f10  lea     rdx, [rsp+0C8h+var_A8]
0x1800c9f15  mov     rcx, r15
0x1800c9f18  call    ??$emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(std::wstring const &)
0x1800c9f1d  mov     rdi, [rsi+120h]
0x1800c9f24  mov     rbx, [rdi]
0x1800c9f27  xorps   xmm0, xmm0
0x1800c9f2a  movdqu  [rsp+0C8h+var_70], xmm0
0x1800c9f30  mov     [rsp+0C8h+var_60], r12
0x1800c9f35  mov     rax, rbx
0x1800c9f38  mov     rdx, r12
0x1800c9f3b  cmp     rax, rdi
0x1800c9f3e  jz      short loc_1800C9F48
0x1800c9f40  inc     rdx
0x1800c9f43  mov     rax, [rax]
0x1800c9f46  jmp     short loc_1800C9F3B
0x1800c9f48  test    rdx, rdx
0x1800c9f4b  jz      short loc_1800C9FA3
0x1800c9f4d  lea     rcx, [rsp+0C8h+var_70]
0x1800c9f52  call    ?_Buy_nonzero@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAX_K@Z; std::vector<std::wstring>::_Buy_nonzero(unsigned __int64)
0x1800c9f57  lea     rax, [rsp+0C8h+var_70]
0x1800c9f5c  mov     qword ptr [rsp+0C8h+var_A8], rax
0x1800c9f61  mov     r14, qword ptr [rsp+0C8h+var_70]
0x1800c9f66  mov     [rsp+0C8h+var_98], r14
0x1800c9f6b  mov     [rsp+0C8h+var_90], r14
0x1800c9f70  lea     rax, [rsp+0C8h+var_70]
0x1800c9f75  mov     [rsp+0C8h+var_88], rax
0x1800c9f7a  cmp     rbx, rdi
0x1800c9f7d  jnz     loc_1800CA06F
0x1800c9f83  mov     rdx, r14
0x1800c9f86  mov     rcx, r14
0x1800c9f89  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x1800c9f8e  mov     qword ptr [rsp+0C8h+var_70+8], r14
0x1800c9f93  mov     qword ptr [rsp+0C8h+var_A8], r12; int
0x1800c9f98  lea     rcx, [rsp+0C8h+var_A8]
0x1800c9f9d  call    ??1?$_Tidy_guard@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<std::wstring>>::~_Tidy_guard<std::vector<std::wstring>>(void)
0x1800c9fa2  nop
0x1800c9fa3  lea     rdx, [rsp+0C8h+var_70]
0x1800c9fa8  lea     rcx, [rsp+0C8h+var_98]
0x1800c9fad  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x1800c9fb2  mov     rdx, rax
0x1800c9fb5  call    ?RequestInstall@AddVoicesSingleton@Speech@SystemSettings@@QEAAJV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; SystemSettings::Speech::AddVoicesSingleton::RequestInstall(std::vector<std::wstring>)
0x1800c9fba  mov     ebx, eax
0x1800c9fbc  test    eax, eax
0x1800c9fbe  jns     short loc_1800CA01A
0x1800c9fc0  mov     rcx, [rsp+0C8h]; this
0x1800c9fc8  mov     r9d, eax; char *
0x1800c9fcb  lea     r8, aShellSystemset_70; "shell\\systemsettingsthreshold\\handler"...
0x1800c9fd2  mov     edx, 173h; void *
0x1800c9fd7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9fdc  nop
0x1800c9fdd  lea     rcx, [rsp+0C8h+var_70]
0x1800c9fe2  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800c9fe7  nop
0x1800c9fe8  lea     rcx, [rsp+0C8h+var_58]
0x1800c9fed  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800c9ff2  nop
0x1800c9ff3  mov     rcx, [rsp+0C8h+string]; string
0x1800c9ff8  call    cs:__imp_WindowsDeleteString
0x1800c9fff  nop     dword ptr [rax+rax+00h]
0x1800ca004  mov     [rsp+0C8h+string], r12
0x1800ca009  lea     rcx, [rsp+0C8h+var_78]
0x1800ca00e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ca013  mov     eax, ebx
0x1800ca015  jmp     loc_1800CA251
0x1800ca01a  mov     byte ptr [rsi+158h], 1
0x1800ca021  mov     rcx, r15
0x1800ca024  call    ?clear@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::clear(void)
0x1800ca029  lea     rcx, ?g_AddVoicesSingleton@Speech@SystemSettings@@3VAddVoicesSingleton@12@A; this
0x1800ca030  call    ?NotifyInstalledVoicesListChanged@AddVoicesSingleton@Speech@SystemSettings@@QEAAXXZ; SystemSettings::Speech::AddVoicesSingleton::NotifyInstalledVoicesListChanged(void)
0x1800ca035  lea     rdx, stru_1802FFF08; unsigned __int16 *
0x1800ca03c  mov     rcx, rsi; this
0x1800ca03f  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x1800ca044  lea     rdx, aValue_0; "Value"
0x1800ca04b  mov     rcx, rsi; this
0x1800ca04e  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x1800ca053  nop
0x1800ca054  lea     rcx, [rsp+0C8h+var_70]
0x1800ca059  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800ca05e  nop
0x1800ca05f  lea     rcx, [rsp+0C8h+var_58]
0x1800ca064  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ca069  nop
0x1800ca06a  jmp     loc_1800CA190
0x1800ca06f  lea     rdx, [rbx+10h]
0x1800ca073  lea     rcx, [rsp+0C8h+var_98]
0x1800ca078  call    ??$_Emplace_back@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Uninitialized_backout_al@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Uninitialized_backout_al<std::allocator<std::wstring>>::_Emplace_back<std::wstring const &>(std::wstring const &)
0x1800ca07d  mov     rbx, [rbx]
0x1800ca080  mov     r14, [rsp+0C8h+var_90]
0x1800ca085  jmp     loc_1800C9F7A
0x1800ca08a  mov     r8, r14; struct IInspectable *
0x1800ca08d  mov     rdx, rdi; HSTRING
0x1800ca090  mov     rcx, rsi; this
0x1800ca093  call    ?SetValue@CSettingBase@DataModel@SystemSettings@@UEAAJPEAUHSTRING__@@PEAUIInspectable@@@Z; SystemSettings::DataModel::CSettingBase::SetValue(HSTRING__ *,IInspectable *)
0x1800ca098  mov     ebx, eax
0x1800ca09a  test    eax, eax
0x1800ca09c  jns     loc_1800CA23F
0x1800ca0a2  mov     rcx, [rsp+0C8h]; this
0x1800ca0aa  mov     r9d, eax; char *
0x1800ca0ad  lea     r8, aShellSystemset_70; "shell\\systemsettingsthreshold\\handler"...
0x1800ca0b4  mov     edx, 17Fh; void *
0x1800ca0b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ca0be  nop
0x1800ca0bf  lea     rcx, [rsp+0C8h+var_78]
0x1800ca0c4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ca0c9  mov     eax, ebx
0x1800ca0cb  jmp     loc_1800CA251
0x1800ca0d0  call    ?IsHstringEqual@DataModel@SystemSettings@@YA_NPEAUHSTRING__@@PEBG@Z; SystemSettings::DataModel::IsHstringEqual(HSTRING__ *,ushort const *)
0x1800ca0d5  test    al, al
0x1800ca0d7  jz      loc_1800CA1A6
0x1800ca0dd  mov     [rsp+0C8h+string], r12
0x1800ca0e2  mov     rdi, [rsp+0C8h+var_78]
0x1800ca0e7  mov     rax, [rdi]
0x1800ca0ea  mov     rbx, [rax+98h]
0x1800ca0f1  xor     ecx, ecx; string
0x1800ca0f3  call    cs:__imp_WindowsDeleteString
0x1800ca0fa  nop     dword ptr [rax+rax+00h]
0x1800ca0ff  mov     [rsp+0C8h+string], r12
0x1800ca104  lea     rdx, [rsp+0C8h+string]
0x1800ca109  mov     rcx, rdi
0x1800ca10c  mov     rax, rbx
0x1800ca10f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca114  mov     ebx, eax
0x1800ca116  test    eax, eax
0x1800ca118  jns     short loc_1800CA15E
0x1800ca11a  mov     rcx, [rsp+0C8h]; this
0x1800ca122  mov     r9d, eax; char *
0x1800ca125  lea     r8, aShellSystemset_70; "shell\\systemsettingsthreshold\\handler"...
0x1800ca12c  mov     edx, 187h; void *
0x1800ca131  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ca136  nop
0x1800ca137  mov     rcx, [rsp+0C8h+string]; string
0x1800ca13c  call    cs:__imp_WindowsDeleteString
0x1800ca143  nop     dword ptr [rax+rax+00h]
0x1800ca148  mov     [rsp+0C8h+string], r12
0x1800ca14d  lea     rcx, [rsp+0C8h+var_78]
0x1800ca152  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800ca157  mov     eax, ebx
0x1800ca159  jmp     loc_1800CA251
0x1800ca15e  xor     edx, edx; length
0x1800ca160  mov     rcx, [rsp+0C8h+string]; string
0x1800ca165  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ca16c  nop     dword ptr [rax+rax+00h]
0x1800ca171  lea     rcx, [rsi+0F8h]
0x1800ca178  mov     rdx, rax
0x1800ca17b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800ca180  lea     rdx, aValue_0; "Value"
0x1800ca187  mov     rcx, rsi; this
0x1800ca18a  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x1800ca18f  nop
0x1800ca190  mov     rcx, [rsp+0C8h+string]; string
0x1800ca195  call    cs:__imp_WindowsDeleteString
  ... truncated ...
```
