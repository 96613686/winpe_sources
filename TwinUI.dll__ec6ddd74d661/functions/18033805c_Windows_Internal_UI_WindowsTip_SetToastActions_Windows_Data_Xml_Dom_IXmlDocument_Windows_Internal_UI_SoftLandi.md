# Windows::Internal::UI::WindowsTip::SetToastActions(Windows::Data::Xml::Dom::IXmlDocument *,Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON const &,Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON const &,Windows::Internal::UI::SoftLanding::SOFTLANDING_NOTIFICATION const &,HSTRING__ *,HSTRING__ *,HSTRING__ *)

- ea: `0x18033805c`
- end: `0x1803387cd`
- name: `?SetToastActions@WindowsTip@UI@Internal@Windows@@YAJPEAUIXmlDocument@Dom@Xml@Data@4@AEBUSOFTLANDING_BUTTON@SoftLanding@234@1AEBUSOFTLANDING_NOTIFICATION@SoftLanding@234@PEAUHSTRING__@@33@Z`
- size: `1905`
- prototype: `__int64 __fastcall(Windows::Internal::UI::WindowsTip *__hidden this, struct Windows::Data::Xml::Dom::IXmlDocument *, const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *, const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *, const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_NOTIFICATION *, HSTRING, HSTRING, HSTRING)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18033ae24`

## callees

- `0x180009dd0`
- `0x18001c710`
- `0x1800378dc`
- `0x180107a50`
- `0x180142e10`
- `0x1802282c4`
- `0x1802284b0`
- `0x1803278b0`
- `0x180331d04`
- `0x18033805c`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803383dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180338436`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180338502`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803386bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803386f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803383dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180338436`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180338502`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803386bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1803386f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1803383f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1803383f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803383a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803383bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033851a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033852e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180338544`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803383a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1803383bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033851a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033852e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180338544`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall Windows::Internal::UI::WindowsTip::SetToastActions(
        __int64 (__fastcall ***this)(Windows::Internal::UI::WindowsTip *, GUID *, __int64 *),
        struct Windows::Data::Xml::Dom::IXmlDocument *a2,
        const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *a3,
        const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *a4,
        const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_NOTIFICATION *a5,
        HSTRING a6,
        HSTRING a7)
{
  __int64 (__fastcall *v11)(Windows::Internal::UI::WindowsTip *, GUID *, __int64 *); // rbx
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64, __int64 *); // rbx
  int v16; // eax
  __int64 (__fastcall *v17)(Windows::Internal::UI::WindowsTip *, __int64, __int64 *); // rbx
  int v18; // eax
  int v19; // eax
  HSTRING *v20; // r15
  HSTRING v21; // r13
  __int64 (__fastcall *v22)(Windows::Internal::UI::WindowsTip *, __int64, __int64 *); // rbx
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rsi
  __int64 (__fastcall *v26)(__int64, __int64, __int64); // rdi
  __int64 v27; // rbx
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v29; // rax
  HRESULT v30; // eax
  unsigned int v31; // ebx
  __int64 v33; // rsi
  __int64 (__fastcall *v34)(__int64, __int64, HSTRING); // rdi
  HSTRING v35; // rbx
  int ActionString; // eax
  __int64 v37; // rdx
  const unsigned __int16 *v38; // rdi
  const unsigned __int16 *v39; // rbx
  Windows::Internal::UI::WindowsTip *v40; // rax
  __int64 v41; // rsi
  __int64 (__fastcall *v42)(__int64, __int64, __int64); // rdi
  __int64 v43; // rbx
  int v44; // eax
  __int64 v45; // rdi
  __int64 (__fastcall *v46)(__int64, __int64, HSTRING *); // rbx
  int v47; // eax
  __int64 v48; // rdi
  __int64 (__fastcall *v49)(__int64, __int64, __int64 *); // rbx
  int v50; // eax
  HSTRING newString; // [rsp+20h] [rbp-F8h] BYREF
  __int64 v52; // [rsp+28h] [rbp-F0h] BYREF
  __int64 v53; // [rsp+30h] [rbp-E8h] BYREF
  __int64 v54; // [rsp+38h] [rbp-E0h] BYREF
  __int64 v55; // [rsp+40h] [rbp-D8h] BYREF
  HSTRING v56; // [rsp+48h] [rbp-D0h] BYREF
  __int64 v57; // [rsp+50h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+58h] [rbp-C0h] BYREF
  __int64 v59; // [rsp+60h] [rbp-B8h] BYREF
  __int64 v60; // [rsp+68h] [rbp-B0h] BYREF
  HSTRING v61; // [rsp+70h] [rbp-A8h]
  HSTRING v62; // [rsp+78h] [rbp-A0h]
  _QWORD v63[3]; // [rsp+80h] [rbp-98h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+98h] [rbp-80h] BYREF
  __int64 v65; // [rsp+B0h] [rbp-68h]
  HSTRING_HEADER v66; // [rsp+B8h] [rbp-60h] BYREF
  __int64 v67; // [rsp+D0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v62 = (HSTRING)a5;
  v61 = a6;
  string = a7;
  v57 = 0;
  v11 = **this;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v57);
  v12 = v11((Windows::Internal::UI::WindowsTip *)this, &GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b, &v57);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v53 = 0;
    v14 = v57;
    v15 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v57 + 48LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v53);
    v65 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"/toast", 7u, 6u);
    v16 = v15(v14, v65, &v53);
    v13 = v16;
    if ( v16 >= 0 )
    {
      v54 = 0;
      v17 = (__int64 (__fastcall *)(Windows::Internal::UI::WindowsTip *, __int64, __int64 *))(*this)[9];
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v54);
      v65 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"actions", 8u, 7u);
      v18 = v17((Windows::Internal::UI::WindowsTip *)this, v65, &v54);
      v13 = v18;
      if ( v18 >= 0 )
      {
        v55 = 0;
        v19 = Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlElement>::As<Windows::Data::Xml::Dom::IXmlNode>(
                &v54,
                &v55);
        v13 = v19;
        if ( v19 >= 0 )
        {
          v63[0] = *((_QWORD *)a4 + 4);
          v63[1] = *((_QWORD *)a2 + 1);
          v63[2] = *((_QWORD *)a3 + 1);
          v20 = (HSTRING *)v63;
          v21 = string;
          while ( v20 != (HSTRING *)&hstringHeader )
          {
            v52 = 0;
            v22 = (__int64 (__fastcall *)(Windows::Internal::UI::WindowsTip *, __int64, __int64 *))(*this)[9];
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v52);
            v65 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"action", 7u, 6u);
            v23 = v22((Windows::Internal::UI::WindowsTip *)this, v65, &v52);
            v13 = v23;
            if ( v23 < 0 )
            {
              v24 = 194;
LABEL_15:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v24,
                (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
                (const char *)(unsigned int)v23,
                (int)newString);
              goto LABEL_34;
            }
            v25 = v52;
            v26 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v52 + 64LL);
            v65 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"foreground", 0xBu, 0xAu);
            v27 = v65;
            v67 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v66, L"activationType", 0xFu, 0xEu);
            v23 = v26(v25, v67, v27);
            v13 = v23;
            if ( v23 < 0 )
            {
              v24 = 195;
              goto LABEL_15;
            }
            newString = 0;
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SoftLandingV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SoftLandingV2>::GetImpl'::`2'::impl) )
            {
              StringRawBuffer = WindowsGetStringRawBuffer(*v20, 0);
              v29 = WindowsGetStringRawBuffer(v21, 0);
              try
              {
                Windows::Internal::UI::WindowsTip::SoftLandingV2Helper::CreateActionString(&v56, v29, StringRawBuffer);
                WindowsDeleteString(newString);
                newString = 0;
                v30 = WindowsDuplicateString(v56, &newString);
              }
              catch ( ... )
              {
                LODWORD(v56) = *(_DWORD *)winrt::to_hresult(&v56);
                v13 = (unsigned int)v56;
                goto LABEL_33;
              }
              v31 = v30;
              if ( v30 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xCD,
                  (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
                  (const char *)(unsigned int)v30,
                  (int)newString);
                winrt::handle_type<winrt::impl::hstring_traits>::close(&v56);
                WindowsDeleteString(newString);
                newString = 0;
                Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v52);
                Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v55);
                Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v54);
                Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v53);
                Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v57);
                return v31;
              }
              winrt::handle_type<winrt::impl::hstring_traits>::close(&v56);
            }
            else
            {
              WindowsDeleteString(newString);
              newString = 0;
              v38 = WindowsGetStringRawBuffer(v61, 0);
              v39 = WindowsGetStringRawBuffer(*v20, 0);
              v40 = (Windows::Internal::UI::WindowsTip *)WindowsGetStringRawBuffer(v62, 0);
              ActionString = Windows::Internal::UI::WindowsTip::CreateActionString(
                               v40,
                               v39,
                               v38,
                               (const unsigned __int16 *)&newString,
                               (HSTRING *)newString);
              v13 = ActionString;
              if ( ActionString < 0 )
              {
                v37 = 218;
                goto LABEL_25;
              }
            }
            v33 = v52;
            v34 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING))(*(_QWORD *)v52 + 64LL);
            v35 = newString;
            v67 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v66, L"arguments", 0xAu, 9u);
            ActionString = v34(v33, v67, v35);
            v13 = ActionString;
            if ( ActionString < 0 )
            {
              v37 = 221;
LABEL_25:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v37,
                (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
                (const char *)(unsigned int)ActionString,
                (int)newString);
              goto LABEL_33;
            }
            v41 = v52;
            v42 = *(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v52 + 64LL);
            v67 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v66, &pszDefault, 1u, 0);
            v43 = v67;
            v65 = 0;
            Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"content", 8u, 7u);
            ActionString = v42(v41, v65, v43);
            v13 = ActionString;
            if ( ActionString < 0 )
            {
              v37 = 222;
              goto LABEL_25;
            }
            v59 = 0;
            v44 = Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlElement>::As<Windows::Data::Xml::Dom::IXmlNode>(
                    &v52,
                    &v59);
            v13 = v44;
            if ( v44 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xE1,
                (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
                (const char *)(unsigned int)v44,
                (int)newString);
              goto LABEL_32;
            }
            string = 0;
            v45 = v55;
            v46 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v55 + 176LL);
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&string);
            v47 = v46(v45, v59, &string);
            v13 = v47;
            if ( v47 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xE4,
                (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
                (const char *)(unsigned int)v47,
                (int)newString);
              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&string);
LABEL_32:
              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v59);
LABEL_33:
              WindowsDeleteString(newString);
              newString = 0;
LABEL_34:
              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v52);
              goto LABEL_39;
            }
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&string);
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v59);
            WindowsDeleteString(newString);
            newString = 0;
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v52);
            ++v20;
          }
          v60 = 0;
          v48 = v53;
          v49 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v53 + 176LL);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v60);
          v50 = v49(v48, v55, &v60);
          v13 = v50;
          if ( v50 < 0 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xE8,
              (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
              (const char *)(unsigned int)v50,
              (int)newString);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v60);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBB,
            (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
            (const char *)(unsigned int)v19,
            (int)newString);
        }
LABEL_39:
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v55);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB8,
          (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
          (const char *)(unsigned int)v18,
          (int)newString);
      }
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v54);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB5,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v16,
        (int)newString);
    }
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v53);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB2,
      (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
      (const char *)(unsigned int)v12,
      (int)newString);
  }
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v57);
  return v13;
}

```

## disassembly

```asm
0x18033805c  push    rbx
0x18033805e  push    rsi
0x18033805f  push    rdi
0x180338060  push    r12
0x180338062  push    r13
0x180338064  push    r14
0x180338066  push    r15
0x180338068  sub     rsp, 0E0h
0x18033806f  mov     rax, cs:__security_cookie
0x180338076  xor     rax, rsp
0x180338079  mov     [rsp+118h+var_40], rax
0x180338081  mov     r13, r9
0x180338084  mov     r15, r8
0x180338087  mov     rsi, rdx
0x18033808a  mov     r12, rcx
0x18033808d  mov     rax, [rsp+118h+arg_20]
0x180338095  mov     [rsp+118h+var_A0], rax
0x18033809a  mov     rax, [rsp+118h+arg_28]
0x1803380a2  mov     [rsp+118h+var_A8], rax
0x1803380a7  mov     rax, [rsp+118h+arg_30]
0x1803380af  mov     [rsp+118h+string], rax
0x1803380b4  xor     r14d, r14d
0x1803380b7  mov     [rsp+118h+var_C8], r14
0x1803380bc  mov     rax, [rcx]
0x1803380bf  mov     rbx, [rax]
0x1803380c2  lea     rcx, [rsp+118h+var_C8]
0x1803380c7  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1803380cc  lea     r8, [rsp+118h+var_C8]
0x1803380d1  lea     rdx, _GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b
0x1803380d8  mov     rcx, r12
0x1803380db  mov     rax, rbx
0x1803380de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803380e3  mov     ebx, eax
0x1803380e5  test    eax, eax
0x1803380e7  jns     short loc_18033810A
0x1803380e9  mov     rcx, [rsp+118h]; this
0x1803380f1  mov     r9d, eax; char *
0x1803380f4  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x1803380fb  mov     edx, 0B2h; void *
0x180338100  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180338105  jmp     loc_18033879D
0x18033810a  mov     [rsp+118h+var_E8], r14
0x18033810f  mov     rdi, [rsp+118h+var_C8]
0x180338114  mov     rax, [rdi]
0x180338117  mov     rbx, [rax+30h]
0x18033811b  lea     rcx, [rsp+118h+var_E8]
0x180338120  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180338125  mov     [rsp+118h+var_68], r14
0x18033812d  mov     r9d, 6; unsigned int
0x180338133  lea     r8d, [r9+1]; unsigned int
0x180338137  lea     rdx, aToast; "/toast"
0x18033813e  lea     rcx, [rsp+118h+hstringHeader]; hstringHeader
0x180338146  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18033814b  nop
0x18033814c  lea     r8, [rsp+118h+var_E8]
0x180338151  mov     rdx, [rsp+118h+var_68]
0x180338159  mov     rcx, rdi
0x18033815c  mov     rax, rbx
0x18033815f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180338164  mov     ebx, eax
0x180338166  test    eax, eax
0x180338168  jns     short loc_18033818B
0x18033816a  mov     rcx, [rsp+118h]; this
0x180338172  mov     r9d, eax; char *
0x180338175  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18033817c  mov     edx, 0B5h; void *
0x180338181  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180338186  jmp     loc_180338792
0x18033818b  mov     [rsp+118h+var_E0], r14
0x180338190  mov     rax, [r12]
0x180338194  mov     rbx, [rax+48h]
0x180338198  lea     rcx, [rsp+118h+var_E0]
0x18033819d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1803381a2  mov     [rsp+118h+var_68], r14
0x1803381aa  mov     r9d, 7; unsigned int
0x1803381b0  lea     r8d, [r9+1]; unsigned int
0x1803381b4  lea     rdx, aActions_0; "actions"
0x1803381bb  lea     rcx, [rsp+118h+hstringHeader]; hstringHeader
0x1803381c3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1803381c8  nop
0x1803381c9  lea     r8, [rsp+118h+var_E0]
0x1803381ce  mov     rdx, [rsp+118h+var_68]
0x1803381d6  mov     rcx, r12
0x1803381d9  mov     rax, rbx
0x1803381dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803381e1  mov     ebx, eax
0x1803381e3  test    eax, eax
0x1803381e5  jns     short loc_180338208
0x1803381e7  mov     rcx, [rsp+118h]; this
0x1803381ef  mov     r9d, eax; char *
0x1803381f2  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x1803381f9  mov     edx, 0B8h; void *
0x1803381fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180338203  jmp     loc_180338787
0x180338208  mov     [rsp+118h+var_D8], r14
0x18033820d  lea     rdx, [rsp+118h+var_D8]
0x180338212  lea     rcx, [rsp+118h+var_E0]
0x180338217  call    ??$As@UIXmlNode@Dom@Xml@Data@Windows@@@?$ComPtr@UIXmlElement@Dom@Xml@Data@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIXmlNode@Dom@Xml@Data@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlElement>::As<Windows::Data::Xml::Dom::IXmlNode>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Xml::Dom::IXmlNode>>)
0x18033821c  mov     ebx, eax
0x18033821e  test    eax, eax
0x180338220  jns     short loc_180338243
0x180338222  mov     rcx, [rsp+118h]; this
0x18033822a  mov     r9d, eax; char *
0x18033822d  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180338234  mov     edx, 0BBh; void *
0x180338239  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033823e  jmp     loc_18033877C
0x180338243  mov     rax, [r13+20h]
0x180338247  mov     [rsp+118h+var_98], rax
0x18033824f  mov     rax, [rsi+8]
0x180338253  mov     [rsp+118h+var_90], rax
0x18033825b  mov     rax, [r15+8]
0x18033825f  mov     [rsp+118h+var_88], rax
0x180338267  lea     r15, [rsp+118h+var_98]
0x18033826f  mov     r13, [rsp+118h+string]
0x180338274  lea     rax, [rsp+118h+hstringHeader]
0x18033827c  cmp     r15, rax
0x18033827f  jz      loc_18033871B
0x180338285  mov     [rsp+118h+var_F0], r14
0x18033828a  mov     rax, [r12]
0x18033828e  mov     rbx, [rax+48h]
0x180338292  lea     rcx, [rsp+118h+var_F0]
0x180338297  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033829c  mov     [rsp+118h+var_68], r14
0x1803382a4  mov     r9d, 6; unsigned int
0x1803382aa  lea     r8d, [r9+1]; unsigned int
0x1803382ae  lea     rdx, aAction; "action"
0x1803382b5  lea     rcx, [rsp+118h+hstringHeader]; hstringHeader
0x1803382bd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1803382c2  nop
0x1803382c3  lea     r8, [rsp+118h+var_F0]
0x1803382c8  mov     rdx, [rsp+118h+var_68]
0x1803382d0  mov     rcx, r12
0x1803382d3  mov     rax, rbx
0x1803382d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803382db  mov     ebx, eax
0x1803382dd  test    eax, eax
0x1803382df  jns     short loc_1803382EB
0x1803382e1  mov     edx, 0C2h
0x1803382e6  jmp     loc_18033836E
0x1803382eb  mov     rsi, [rsp+118h+var_F0]
0x1803382f0  mov     rax, [rsi]
0x1803382f3  mov     rdi, [rax+40h]
0x1803382f7  mov     [rsp+118h+var_68], r14
0x1803382ff  mov     r9d, 0Ah; unsigned int
0x180338305  lea     r8d, [r9+1]; unsigned int
0x180338309  lea     rdx, aForeground; "foreground"
0x180338310  lea     rcx, [rsp+118h+hstringHeader]; hstringHeader
0x180338318  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18033831d  nop
0x18033831e  mov     rbx, [rsp+118h+var_68]
0x180338326  mov     [rsp+118h+var_48], r14
0x18033832e  mov     r9d, 0Eh; unsigned int
0x180338334  lea     r8d, [r9+1]; unsigned int
0x180338338  lea     rdx, aActivationtype; "activationType"
0x18033833f  lea     rcx, [rsp+118h+var_60]; hstringHeader
0x180338347  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18033834c  nop
0x18033834d  mov     r8, rbx
0x180338350  mov     rdx, [rsp+118h+var_48]
0x180338358  mov     rcx, rsi
0x18033835b  mov     rax, rdi
0x18033835e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180338363  mov     ebx, eax
0x180338365  test    eax, eax
0x180338367  jns     short loc_18033838A
0x180338369  mov     edx, 0C3h; void *
0x18033836e  mov     r9d, eax; char *
0x180338371  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180338378  mov     rcx, [rsp+118h]; this
0x180338380  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180338385  jmp     loc_1803386CD
0x18033838a  mov     [rsp+118h+newString], r14
0x18033838f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SoftLandingV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SoftLandingV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SoftLandingV2> `wil::Feature<__WilFeatureTraits_Feature_SoftLandingV2>::GetImpl(void)'::`2'::impl
0x180338396  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SoftLandingV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SoftLandingV2>::__private_IsEnabled(void)
0x18033839b  test    al, al
0x18033839d  jz      loc_1803384FD
0x1803383a3  xor     edx, edx; length
0x1803383a5  mov     rcx, [r15]; string
0x1803383a8  call    cs:__imp_WindowsGetStringRawBuffer
0x1803383af  nop     dword ptr [rax+rax+00h]
0x1803383b4  mov     rbx, rax
0x1803383b7  xor     edx, edx; length
0x1803383b9  mov     rcx, r13; string
0x1803383bc  call    cs:__imp_WindowsGetStringRawBuffer
0x1803383c3  nop     dword ptr [rax+rax+00h]
0x1803383c8  mov     r8, rbx
0x1803383cb  mov     rdx, rax
0x1803383ce  lea     rcx, [rsp+118h+var_D0]
0x1803383d3  call    ?CreateActionString@SoftLandingV2Helper@WindowsTip@UI@Internal@Windows@@SA?AUhstring@winrt@@PEBG0@Z; Windows::Internal::UI::WindowsTip::SoftLandingV2Helper::CreateActionString(ushort const *,ushort const *)
0x1803383d8  mov     rcx, [rsp+118h+newString]; string
0x1803383dd  call    cs:__imp_WindowsDeleteString
0x1803383e4  nop     dword ptr [rax+rax+00h]
0x1803383e9  mov     [rsp+118h+newString], r14; int
0x1803383ee  lea     rdx, [rsp+118h+newString]; newString
0x1803383f3  mov     rcx, [rsp+118h+var_D0]; string
0x1803383f8  call    cs:__imp_WindowsDuplicateString
0x1803383ff  nop     dword ptr [rax+rax+00h]
0x180338404  mov     ebx, eax
0x180338406  test    eax, eax
0x180338408  jns     short loc_180338484
0x18033840a  mov     rcx, [rsp+118h]; this
0x180338412  mov     r9d, eax; char *
0x180338415  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18033841c  mov     edx, 0CDh; void *
0x180338421  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180338426  lea     rcx, [rsp+118h+var_D0]
0x18033842b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180338430  nop
0x180338431  mov     rcx, [rsp+118h+newString]; string
0x180338436  call    cs:__imp_WindowsDeleteString
0x18033843d  nop     dword ptr [rax+rax+00h]
0x180338442  mov     [rsp+118h+newString], r14
0x180338447  lea     rcx, [rsp+118h+var_F0]
0x18033844c  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180338451  nop
0x180338452  lea     rcx, [rsp+118h+var_D8]
0x180338457  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033845c  nop
0x18033845d  lea     rcx, [rsp+118h+var_E0]
0x180338462  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180338467  nop
0x180338468  lea     rcx, [rsp+118h+var_E8]
0x18033846d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180338472  nop
0x180338473  lea     rcx, [rsp+118h+var_C8]
0x180338478  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033847d  mov     eax, ebx
0x18033847f  jmp     loc_1803387A9
0x180338484  lea     rcx, [rsp+118h+var_D0]
0x180338489  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18033848e  nop
0x18033848f  mov     rsi, [rsp+118h+var_F0]
0x180338494  mov     rax, [rsi]
0x180338497  mov     rdi, [rax+40h]
0x18033849b  mov     rbx, [rsp+118h+newString]
0x1803384a0  mov     [rsp+118h+var_48], r14
0x1803384a8  mov     r9d, 9; unsigned int
0x1803384ae  lea     r8d, [r9+1]; unsigned int
0x1803384b2  lea     rdx, aArguments; "arguments"
0x1803384b9  lea     rcx, [rsp+118h+var_60]; hstringHeader
0x1803384c1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1803384c6  nop
0x1803384c7  mov     r8, rbx
0x1803384ca  mov     rdx, [rsp+118h+var_48]
0x1803384d2  mov     rcx, rsi
0x1803384d5  mov     rax, rdi
0x1803384d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803384dd  mov     ebx, eax
0x1803384df  test    eax, eax
0x1803384e1  jns     loc_18033858E
0x1803384e7  mov     edx, 0DDh
0x1803384ec  jmp     loc_180338572
0x1803384f1  mov     ebx, dword ptr [rsp+118h+var_D0]
0x1803384f5  xor     r14d, r14d
0x1803384f8  jmp     loc_1803386B7
0x1803384fd  mov     rcx, [rsp+118h+newString]; string
0x180338502  call    cs:__imp_WindowsDeleteString
0x180338509  nop     dword ptr [rax+rax+00h]
0x18033850e  mov     [rsp+118h+newString], r14; int
0x180338513  xor     edx, edx; length
0x180338515  mov     rcx, [rsp+118h+var_A8]; string
0x18033851a  call    cs:__imp_WindowsGetStringRawBuffer
0x180338521  nop     dword ptr [rax+rax+00h]
0x180338526  mov     rdi, rax
0x180338529  xor     edx, edx; length
0x18033852b  mov     rcx, [r15]; string
0x18033852e  call    cs:__imp_WindowsGetStringRawBuffer
0x180338535  nop     dword ptr [rax+rax+00h]
0x18033853a  mov     rbx, rax
0x18033853d  xor     edx, edx; length
0x18033853f  mov     rcx, [rsp+118h+var_A0]; string
0x180338544  call    cs:__imp_WindowsGetStringRawBuffer
0x18033854b  nop     dword ptr [rax+rax+00h]
0x180338550  lea     r9, [rsp+118h+newString]; unsigned __int16 *
0x180338555  mov     r8, rdi; unsigned __int16 *
0x180338558  mov     rdx, rbx; unsigned __int16 *
0x18033855b  mov     rcx, rax; this
0x18033855e  call    ?CreateActionString@WindowsTip@UI@Internal@Windows@@YAJPEBG00PEAPEAUHSTRING__@@@Z; Windows::Internal::UI::WindowsTip::CreateActionString(ushort const *,ushort const *,ushort const *,HSTRING__ * *)
0x180338563  mov     ebx, eax
0x180338565  test    eax, eax
0x180338567  jns     loc_18033848F
0x18033856d  mov     edx, 0DAh; void *
0x180338572  mov     rcx, [rsp+118h]; this
0x18033857a  mov     r9d, eax; char *
0x18033857d  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x180338584  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180338589  jmp     loc_1803386B7
0x18033858e  mov     rsi, [rsp+118h+var_F0]
0x180338593  mov     rax, [rsi]
0x180338596  mov     rdi, [rax+40h]
0x18033859a  mov     [rsp+118h+var_48], r14
0x1803385a2  xor     r9d, r9d; unsigned int
0x1803385a5  lea     r8d, [r9+1]; unsigned int
0x1803385a9  lea     rdx, pszDefault; sourceString
0x1803385b0  lea     rcx, [rsp+118h+var_60]; hstringHeader
0x1803385b8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1803385bd  nop
0x1803385be  mov     rbx, [rsp+118h+var_48]
0x1803385c6  mov     [rsp+118h+var_68], r14
  ... truncated ...
```
