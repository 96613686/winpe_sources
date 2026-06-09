# Windows::Internal::UI::WindowsTip::UpdateToastTemplateWithData(Windows::Data::Xml::Dom::IXmlDocument *,Windows::Internal::UI::SoftLanding::SOFTLANDING_NOTIFICATION const &,HSTRING__ *,HSTRING__ *,Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON const &,Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON const &,HSTRING__ *)

- ea: `0x18033ae24`
- end: `0x18033b55d`
- name: `?UpdateToastTemplateWithData@WindowsTip@UI@Internal@Windows@@YAJPEAUIXmlDocument@Dom@Xml@Data@4@AEBUSOFTLANDING_NOTIFICATION@SoftLanding@234@PEAUHSTRING__@@2AEBUSOFTLANDING_BUTTON@SoftLanding@234@32@Z`
- size: `1849`
- prototype: `__int64 __usercall@<rax>(Windows::Internal::UI::WindowsTip *__hidden this@<rcx>, struct Windows::Data::Xml::Dom::IXmlDocument *@<rdx>, const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_NOTIFICATION *@<r8>, HSTRING@<r9>, HSTRING, const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *, const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *, HSTRING)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1803322ac`

## callees

- `0x180009dd0`
- `0x18001c710`
- `0x1800378dc`
- `0x180037b9c`
- `0x180053740`
- `0x180136c44`
- `0x180142e10`
- `0x1802282c4`
- `0x1802284b0`
- `0x1803278b0`
- `0x180331d04`
- `0x180331dbc`
- `0x180337d50`
- `0x18033805c`
- `0x180338dec`
- `0x18033923c`
- `0x18033ae24`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033b2ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033b307`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033b39b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033b4f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033b51f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033b2ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033b307`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033b39b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033b4f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033b51f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18033b2c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18033b2c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033ae92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033aead`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033aec5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033aee0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033b279`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033b28d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033b3b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033b3c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033b3db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033b493`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033ae92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033aead`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033aec5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033aee0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033b279`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033b28d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033b3b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033b3c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033b3db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033b493`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Internal::UI::WindowsTip::UpdateToastTemplateWithData(
        Windows::Internal::UI::WindowsTip *this,
        HSTRING *a2,
        const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_NOTIFICATION *a3,
        HSTRING a4,
        struct Windows::Data::Xml::Dom::IXmlDocument *a5,
        const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *a6,
        const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *string)
{
  HSTRING v9; // r14
  unsigned __int16 *StringRawBuffer; // r13
  unsigned __int16 *v11; // rdi
  struct Windows::Data::Xml::Dom::IXmlDocument *v12; // rdx
  int v13; // eax
  unsigned int v14; // ebx
  __int64 (__fastcall *v15)(Windows::Internal::UI::WindowsTip *, __int64, __int64 *); // rbx
  int v16; // eax
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, _QWORD, HSTRING *); // rbx
  int appended; // eax
  __int64 v22; // rdx
  unsigned int v23; // r14d
  int v24; // eax
  HSTRING v25; // rbx
  __int64 v26; // rax
  struct Windows::Data::Xml::Dom::IXmlNode *v27; // r8
  struct Windows::Data::Xml::Dom::IXmlNode **v28; // r9
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, _QWORD, HSTRING *); // rbx
  int v31; // eax
  int v32; // eax
  const unsigned __int16 *v33; // r9
  HSTRING v34; // rdi
  HSTRING v35; // r13
  HSTRING v36; // rbx
  __int64 v37; // rax
  struct Windows::Data::Xml::Dom::IXmlNode *v38; // r8
  struct Windows::Data::Xml::Dom::IXmlNode **v39; // r9
  PCWSTR v40; // rbx
  PCWSTR v41; // rax
  HRESULT v42; // eax
  unsigned int v43; // ebx
  __int64 (__fastcall *v45)(Windows::Internal::UI::WindowsTip *, GUID *, unsigned __int64 *); // rbx
  int v46; // eax
  const unsigned __int16 *v47; // rdi
  const unsigned __int16 *v48; // rbx
  Windows::Internal::UI::WindowsTip *v49; // rax
  int ActionString; // eax
  unsigned __int64 v51; // rdi
  __int64 (__fastcall *v52)(unsigned __int64, __int64, Windows::Internal::UI::WindowsTip **); // rbx
  int v53; // eax
  __int64 v54; // rdx
  const unsigned __int16 *v55; // rax
  const unsigned __int16 *v56; // r9
  HSTRING *v57; // [rsp+20h] [rbp-E8h]
  HSTRING v58; // [rsp+38h] [rbp-D0h]
  HSTRING newString; // [rsp+40h] [rbp-C8h] BYREF
  unsigned __int64 v60; // [rsp+48h] [rbp-C0h] BYREF
  Windows::Internal::UI::WindowsTip *v61; // [rsp+50h] [rbp-B8h] BYREF
  HSTRING v62; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v63; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int v64; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int16 *v65; // [rsp+70h] [rbp-98h]
  const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *v66; // [rsp+78h] [rbp-90h]
  unsigned __int16 *v67; // [rsp+80h] [rbp-88h]
  HSTRING v68; // [rsp+88h] [rbp-80h]
  HSTRING v69; // [rsp+90h] [rbp-78h]
  struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *v70; // [rsp+98h] [rbp-70h]
  struct Windows::Data::Xml::Dom::IXmlDocument *v71; // [rsp+A0h] [rbp-68h]
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v73; // [rsp+C0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v68 = a4;
  v69 = (HSTRING)a3;
  v71 = a5;
  v70 = a6;
  v9 = (HSTRING)string;
  v66 = string;
  StringRawBuffer = (unsigned __int16 *)WindowsGetStringRawBuffer(*a2, 0);
  v62 = (HSTRING)StringRawBuffer;
  v61 = (Windows::Internal::UI::WindowsTip *)WindowsGetStringRawBuffer(a2[1], 0);
  v11 = (unsigned __int16 *)WindowsGetStringRawBuffer(a2[2], 0);
  v65 = v11;
  v67 = (unsigned __int16 *)WindowsGetStringRawBuffer(a2[3], 0);
  v60 = 0;
  v64 = 0;
  v13 = Windows::Internal::UI::WindowsTip::SetToastTemplateToToastGeneric(this, v12);
  v14 = v13;
  if ( v13 >= 0 )
  {
    v63 = 0;
    v15 = *(__int64 (__fastcall **)(Windows::Internal::UI::WindowsTip *, __int64, __int64 *))(*(_QWORD *)this + 128LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v63);
    v73 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"text", 5u, 4u);
    v16 = v15(this, v73, &v63);
    v14 = v16;
    if ( v16 < 0 )
    {
      v17 = 369;
LABEL_27:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v16,
        (int)v57);
      goto LABEL_53;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v63 + 48LL))(v63, &v64);
    if ( v18 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x172,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v18,
        (int)v57);
      goto LABEL_23;
    }
    if ( v64 )
    {
      newString = 0;
      v19 = v63;
      v20 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v63 + 56LL);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&newString);
      appended = v20(v19, 0, &newString);
      v14 = appended;
      if ( appended < 0 )
      {
        v22 = 374;
LABEL_10:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
          (const char *)(unsigned int)appended,
          (int)v57);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&newString);
LABEL_53:
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v63);
        return v14;
      }
      v23 = 0;
      v24 = StringCchLengthW(StringRawBuffer, 0x7FFFFFFFu, &v60);
      if ( v24 >= 0 )
      {
        if ( v60 )
        {
          v25 = newString;
          v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v62);
          appended = Windows::Internal::UI::WindowsTip::CreateAndAppendTextNode(
                       *(Windows::Internal::UI::WindowsTip **)(v26 + 24),
                       v25,
                       v27,
                       v28);
          v14 = appended;
          if ( appended < 0 )
          {
            v22 = 378;
            goto LABEL_10;
          }
          v23 = 1;
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x178,
          (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
          (const char *)(unsigned int)v24,
          (int)v57);
      }
      if ( v64 > v23 )
      {
        v29 = v63;
        v30 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v63 + 56LL);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&newString);
        appended = v30(v29, v23, &newString);
        v14 = appended;
        if ( appended < 0 )
        {
          v22 = 384;
          goto LABEL_10;
        }
        v31 = StringCchLengthW((const unsigned __int16 *)v61, 0x7FFFFFFFu, &v60);
        if ( v31 >= 0 )
        {
          if ( v60 )
          {
            v36 = newString;
            v37 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v61);
            appended = Windows::Internal::UI::WindowsTip::CreateAndAppendTextNode(
                         *(Windows::Internal::UI::WindowsTip **)(v37 + 24),
                         v36,
                         v38,
                         v39);
            v14 = appended;
            if ( appended < 0 )
            {
              v22 = 388;
              goto LABEL_10;
            }
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x182,
            (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
            (const char *)(unsigned int)v31,
            (int)v57);
        }
      }
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&newString);
      v11 = v65;
      v9 = (HSTRING)v66;
    }
LABEL_23:
    v32 = StringCchLengthW(v11, 0x104u, &v60);
    if ( v32 >= 0 )
    {
      if ( v60 )
      {
        v16 = Windows::Internal::UI::WindowsTip::SetToastImageSrc(
                this,
                (struct Windows::Data::Xml::Dom::IXmlDocument *)v11,
                v67,
                v33);
        v14 = v16;
        if ( v16 < 0 )
        {
          v17 = 395;
          goto LABEL_27;
        }
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x189,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v32,
        (int)v57);
    }
    v34 = v68;
    v35 = v69;
    v16 = Windows::Internal::UI::WindowsTip::SetToastActions(
            this,
            v71,
            v70,
            (const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *)a2,
            (const struct Windows::Internal::UI::SoftLanding::SOFTLANDING_NOTIFICATION *)v69,
            v68,
            v9,
            v58);
    v14 = v16;
    if ( v16 < 0 )
    {
      v17 = 405;
      goto LABEL_27;
    }
    if ( *((_DWORD *)a2 + 10) <= 1u )
    {
      newString = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SoftLandingV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SoftLandingV2>::GetImpl'::`2'::impl) )
      {
        v40 = WindowsGetStringRawBuffer(a2[4], 0);
        v41 = WindowsGetStringRawBuffer(v9, 0);
        try
        {
          Windows::Internal::UI::WindowsTip::SoftLandingV2Helper::CreateActionString(&v62, v41, v40);
          WindowsDeleteString(newString);
          newString = 0;
          v42 = WindowsDuplicateString(v62, &newString);
        }
        catch ( ... )
        {
          LODWORD(v62) = *(_DWORD *)winrt::to_hresult(&v62);
          v14 = (unsigned int)v62;
          goto LABEL_50;
        }
        v43 = v42;
        if ( v42 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1A2,
            (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
            (const char *)(unsigned int)v42,
            (int)v57);
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v62);
          WindowsDeleteString(newString);
          newString = 0;
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v63);
          return v43;
        }
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v62);
      }
      else
      {
        WindowsDeleteString(newString);
        newString = 0;
        v47 = WindowsGetStringRawBuffer(v34, 0);
        v48 = WindowsGetStringRawBuffer(a2[4], 0);
        v49 = (Windows::Internal::UI::WindowsTip *)WindowsGetStringRawBuffer(v35, 0);
        ActionString = Windows::Internal::UI::WindowsTip::CreateActionString(
                         v49,
                         v48,
                         v47,
                         (const unsigned __int16 *)&newString,
                         v57);
        v14 = ActionString;
        if ( ActionString < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1AF,
            (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
            (const char *)(unsigned int)ActionString,
            (int)v57);
LABEL_50:
          WindowsDeleteString(newString);
          newString = 0;
          goto LABEL_53;
        }
      }
      v60 = 0;
      v45 = **(__int64 (__fastcall ***)(Windows::Internal::UI::WindowsTip *, GUID *, unsigned __int64 *))this;
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v60);
      v46 = v45(this, &GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b, &v60);
      v14 = v46;
      if ( v46 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1B4,
          (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
          (const char *)(unsigned int)v46,
          (int)v57);
LABEL_49:
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v60);
        goto LABEL_50;
      }
      v61 = 0;
      v51 = v60;
      v52 = *(__int64 (__fastcall **)(unsigned __int64, __int64, Windows::Internal::UI::WindowsTip **))(*(_QWORD *)v60 + 48LL);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v61);
      v73 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"toast", 6u, 5u);
      v53 = v52(v51, v73, &v61);
      v14 = v53;
      if ( v53 < 0 )
      {
        v54 = 438;
LABEL_48:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v54,
          (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
          (const char *)(unsigned int)v53,
          (int)v57);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v61);
        goto LABEL_49;
      }
      v55 = WindowsGetStringRawBuffer(newString, 0);
      v53 = Windows::Internal::UI::WindowsTip::SetNodeAttribute(
              v61,
              (struct Windows::Data::Xml::Dom::IXmlNode *)L"launch",
              v55,
              v56);
      v14 = v53;
      if ( v53 < 0 )
      {
        v54 = 439;
        goto LABEL_48;
      }
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v61);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v60);
      WindowsDeleteString(newString);
    }
    v14 = 0;
    goto LABEL_53;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x16E,
    (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
    (const char *)(unsigned int)v13,
    (int)v57);
  return v14;
}

```

## disassembly

```asm
0x18033ae24  push    rbx
0x18033ae26  push    rsi
0x18033ae27  push    rdi
0x18033ae28  push    r12
0x18033ae2a  push    r13
0x18033ae2c  push    r14
0x18033ae2e  push    r15
0x18033ae30  sub     rsp, 0D0h
0x18033ae37  mov     rax, cs:__security_cookie
0x18033ae3e  xor     rax, rsp
0x18033ae41  mov     [rsp+108h+var_40], rax
0x18033ae49  mov     [rsp+108h+var_80], r9
0x18033ae51  mov     [rsp+108h+var_78], r8
0x18033ae59  mov     r12, rdx
0x18033ae5c  mov     r15, rcx
0x18033ae5f  mov     rax, [rsp+108h+arg_20]
0x18033ae67  mov     [rsp+108h+var_68], rax
0x18033ae6f  mov     rax, [rsp+108h+arg_28]
0x18033ae77  mov     [rsp+108h+var_70], rax
0x18033ae7f  mov     r14, [rsp+108h+string]
0x18033ae87  mov     [rsp+108h+var_90], r14
0x18033ae8c  xor     edx, edx; length
0x18033ae8e  mov     rcx, [r12]; string
0x18033ae92  call    cs:__imp_WindowsGetStringRawBuffer
0x18033ae99  nop     dword ptr [rax+rax+00h]
0x18033ae9e  mov     r13, rax
0x18033aea1  mov     [rsp+108h+var_B0], rax
0x18033aea6  xor     edx, edx; length
0x18033aea8  mov     rcx, [r12+8]; string
0x18033aead  call    cs:__imp_WindowsGetStringRawBuffer
0x18033aeb4  nop     dword ptr [rax+rax+00h]
0x18033aeb9  mov     [rsp+108h+var_B8], rax
0x18033aebe  xor     edx, edx; length
0x18033aec0  mov     rcx, [r12+10h]; string
0x18033aec5  call    cs:__imp_WindowsGetStringRawBuffer
0x18033aecc  nop     dword ptr [rax+rax+00h]
0x18033aed1  mov     rdi, rax
0x18033aed4  mov     [rsp+108h+var_98], rax
0x18033aed9  xor     edx, edx; length
0x18033aedb  mov     rcx, [r12+18h]; string
0x18033aee0  call    cs:__imp_WindowsGetStringRawBuffer
0x18033aee7  nop     dword ptr [rax+rax+00h]
0x18033aeec  mov     [rsp+108h+var_88], rax
0x18033aef4  xor     esi, esi
0x18033aef6  mov     [rsp+108h+var_C0], rsi
0x18033aefb  mov     [rsp+108h+var_A0], esi
0x18033aeff  mov     rcx, r15; this
0x18033af02  call    ?SetToastTemplateToToastGeneric@WindowsTip@UI@Internal@Windows@@YAJPEAUIXmlDocument@Dom@Xml@Data@4@@Z; Windows::Internal::UI::WindowsTip::SetToastTemplateToToastGeneric(Windows::Data::Xml::Dom::IXmlDocument *)
0x18033af07  mov     ebx, eax
0x18033af09  test    eax, eax
0x18033af0b  jns     short loc_18033AF2E
0x18033af0d  mov     rcx, [rsp+108h]; this
0x18033af15  mov     r9d, eax; char *
0x18033af18  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18033af1f  mov     edx, 16Eh; void *
0x18033af24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033af29  jmp     loc_18033B537
0x18033af2e  mov     [rsp+108h+var_A8], rsi
0x18033af33  mov     rax, [r15]
0x18033af36  mov     rbx, [rax+80h]
0x18033af3d  lea     rcx, [rsp+108h+var_A8]
0x18033af42  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033af47  mov     [rsp+108h+var_48], rsi
0x18033af4f  mov     r9d, 4; unsigned int
0x18033af55  lea     r8d, [r9+1]; unsigned int
0x18033af59  lea     rdx, aText_0; "text"
0x18033af60  lea     rcx, [rsp+108h+hstringHeader]; hstringHeader
0x18033af68  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18033af6d  nop
0x18033af6e  lea     r8, [rsp+108h+var_A8]
0x18033af73  mov     rdx, [rsp+108h+var_48]
0x18033af7b  mov     rcx, r15
0x18033af7e  mov     rax, rbx
0x18033af81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033af86  mov     ebx, eax
0x18033af88  test    eax, eax
0x18033af8a  jns     short loc_18033AF96
0x18033af8c  mov     edx, 171h
0x18033af91  jmp     loc_18033B1BD
0x18033af96  mov     rcx, [rsp+108h+var_A8]
0x18033af9b  mov     rax, [rcx]
0x18033af9e  lea     rdx, [rsp+108h+var_A0]
0x18033afa3  mov     rax, [rax+30h]
0x18033afa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033afac  mov     rcx, [rsp+108h]; this
0x18033afb4  test    eax, eax
0x18033afb6  jns     short loc_18033AFD1
0x18033afb8  mov     r9d, eax; char *
0x18033afbb  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18033afc2  mov     edx, 172h; void *
0x18033afc7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18033afcc  jmp     loc_18033B13E
0x18033afd1  cmp     [rsp+108h+var_A0], esi
0x18033afd5  jbe     loc_18033B13E
0x18033afdb  mov     [rsp+108h+newString], rsi
0x18033afe0  mov     rdi, [rsp+108h+var_A8]
0x18033afe5  mov     rax, [rdi]
0x18033afe8  mov     rbx, [rax+38h]
0x18033afec  lea     rcx, [rsp+108h+newString]
0x18033aff1  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033aff6  lea     r8, [rsp+108h+newString]
0x18033affb  xor     edx, edx
0x18033affd  mov     rcx, rdi
0x18033b000  mov     rax, rbx
0x18033b003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033b008  mov     ebx, eax
0x18033b00a  test    eax, eax
0x18033b00c  jns     short loc_18033B03A
0x18033b00e  mov     edx, 176h; void *
0x18033b013  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18033b01a  mov     r9d, eax; char *
0x18033b01d  mov     rcx, [rsp+108h]; this
0x18033b025  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033b02a  nop
0x18033b02b  lea     rcx, [rsp+108h+newString]
0x18033b030  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033b035  jmp     loc_18033B52D
0x18033b03a  mov     r14d, esi
0x18033b03d  lea     r8, [rsp+108h+var_C0]; unsigned __int64 *
0x18033b042  mov     edx, 7FFFFFFFh; unsigned __int64
0x18033b047  mov     rcx, r13; unsigned __int16 *
0x18033b04a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18033b04f  mov     rcx, [rsp+108h]; this
0x18033b057  test    eax, eax
0x18033b059  jns     short loc_18033B071
0x18033b05b  mov     r9d, eax; char *
0x18033b05e  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18033b065  mov     edx, 178h; void *
0x18033b06a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18033b06f  jmp     short loc_18033B0B1
0x18033b071  cmp     [rsp+108h+var_C0], rsi
0x18033b076  jbe     short loc_18033B0B1
0x18033b078  mov     rbx, [rsp+108h+newString]
0x18033b07d  lea     rdx, [rsp+108h+var_B0]
0x18033b082  lea     rcx, [rsp+108h+hstringHeader]
0x18033b08a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18033b08f  mov     rdx, rbx; HSTRING
0x18033b092  mov     rcx, [rax+18h]; this
0x18033b096  call    ?CreateAndAppendTextNode@WindowsTip@UI@Internal@Windows@@YAJPEAUHSTRING__@@PEAUIXmlNode@Dom@Xml@Data@4@PEAPEAU67894@@Z; Windows::Internal::UI::WindowsTip::CreateAndAppendTextNode(HSTRING__ *,Windows::Data::Xml::Dom::IXmlNode *,Windows::Data::Xml::Dom::IXmlNode * *)
0x18033b09b  mov     ebx, eax
0x18033b09d  test    eax, eax
0x18033b09f  jns     short loc_18033B0AB
0x18033b0a1  mov     edx, 17Ah
0x18033b0a6  jmp     loc_18033B013
0x18033b0ab  mov     r14d, 1
0x18033b0b1  cmp     [rsp+108h+var_A0], r14d
0x18033b0b6  jbe     short loc_18033B12A
0x18033b0b8  mov     rdi, [rsp+108h+var_A8]
0x18033b0bd  mov     rax, [rdi]
0x18033b0c0  mov     rbx, [rax+38h]
0x18033b0c4  lea     rcx, [rsp+108h+newString]
0x18033b0c9  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033b0ce  lea     r8, [rsp+108h+newString]
0x18033b0d3  mov     edx, r14d
0x18033b0d6  mov     rcx, rdi
0x18033b0d9  mov     rax, rbx
0x18033b0dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033b0e1  mov     ebx, eax
0x18033b0e3  test    eax, eax
0x18033b0e5  jns     short loc_18033B0F1
0x18033b0e7  mov     edx, 180h
0x18033b0ec  jmp     loc_18033B013
0x18033b0f1  lea     r8, [rsp+108h+var_C0]; unsigned __int64 *
0x18033b0f6  mov     edx, 7FFFFFFFh; unsigned __int64
0x18033b0fb  mov     rcx, [rsp+108h+var_B8]; unsigned __int16 *
0x18033b100  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18033b105  mov     rcx, [rsp+108h]; this
0x18033b10d  test    eax, eax
0x18033b10f  jns     loc_18033B1D9
0x18033b115  mov     r9d, eax; char *
0x18033b118  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18033b11f  mov     edx, 182h; void *
0x18033b124  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18033b129  nop
0x18033b12a  lea     rcx, [rsp+108h+newString]
0x18033b12f  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033b134  mov     rdi, [rsp+108h+var_98]
0x18033b139  mov     r14, [rsp+108h+var_90]
0x18033b13e  lea     r8, [rsp+108h+var_C0]; unsigned __int64 *
0x18033b143  mov     edx, 104h; unsigned __int64
0x18033b148  mov     rcx, rdi; unsigned __int16 *
0x18033b14b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18033b150  mov     rcx, [rsp+108h]; this
0x18033b158  test    eax, eax
0x18033b15a  jns     loc_18033B21B
0x18033b160  mov     r9d, eax; char *
0x18033b163  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18033b16a  mov     edx, 189h; void *
0x18033b16f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18033b174  mov     [rsp+108h+var_D8], r14; HSTRING
0x18033b179  mov     rdi, [rsp+108h+var_80]
0x18033b181  mov     [rsp+108h+var_E0], rdi; HSTRING
0x18033b186  mov     r13, [rsp+108h+var_78]
0x18033b18e  mov     [rsp+108h+var_E8], r13; int
0x18033b193  mov     r9, r12; struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *
0x18033b196  mov     r8, [rsp+108h+var_70]; struct Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON *
0x18033b19e  mov     rdx, [rsp+108h+var_68]; struct Windows::Data::Xml::Dom::IXmlDocument *
0x18033b1a6  mov     rcx, r15; this
0x18033b1a9  call    ?SetToastActions@WindowsTip@UI@Internal@Windows@@YAJPEAUIXmlDocument@Dom@Xml@Data@4@AEBUSOFTLANDING_BUTTON@SoftLanding@234@1AEBUSOFTLANDING_NOTIFICATION@SoftLanding@234@PEAUHSTRING__@@33@Z; Windows::Internal::UI::WindowsTip::SetToastActions(Windows::Data::Xml::Dom::IXmlDocument *,Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON const &,Windows::Internal::UI::SoftLanding::SOFTLANDING_BUTTON const &,Windows::Internal::UI::SoftLanding::SOFTLANDING_NOTIFICATION const &,HSTRING__ *,HSTRING__ *,HSTRING__ *)
0x18033b1ae  mov     ebx, eax
0x18033b1b0  test    eax, eax
0x18033b1b2  jns     loc_18033B24D
0x18033b1b8  mov     edx, 195h; void *
0x18033b1bd  mov     r9d, eax; char *
0x18033b1c0  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18033b1c7  mov     rcx, [rsp+108h]; this
0x18033b1cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033b1d4  jmp     loc_18033B52D
0x18033b1d9  cmp     [rsp+108h+var_C0], rsi
0x18033b1de  jbe     loc_18033B12A
0x18033b1e4  mov     rbx, [rsp+108h+newString]
0x18033b1e9  lea     rdx, [rsp+108h+var_B8]
0x18033b1ee  lea     rcx, [rsp+108h+hstringHeader]
0x18033b1f6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18033b1fb  mov     rdx, rbx; HSTRING
0x18033b1fe  mov     rcx, [rax+18h]; this
0x18033b202  call    ?CreateAndAppendTextNode@WindowsTip@UI@Internal@Windows@@YAJPEAUHSTRING__@@PEAUIXmlNode@Dom@Xml@Data@4@PEAPEAU67894@@Z; Windows::Internal::UI::WindowsTip::CreateAndAppendTextNode(HSTRING__ *,Windows::Data::Xml::Dom::IXmlNode *,Windows::Data::Xml::Dom::IXmlNode * *)
0x18033b207  mov     ebx, eax
0x18033b209  test    eax, eax
0x18033b20b  jns     loc_18033B12A
0x18033b211  mov     edx, 184h
0x18033b216  jmp     loc_18033B013
0x18033b21b  cmp     [rsp+108h+var_C0], rsi
0x18033b220  jbe     loc_18033B174
0x18033b226  mov     r8, [rsp+108h+var_88]; unsigned __int16 *
0x18033b22e  mov     rdx, rdi; struct Windows::Data::Xml::Dom::IXmlDocument *
0x18033b231  mov     rcx, r15; this
0x18033b234  call    ?SetToastImageSrc@WindowsTip@UI@Internal@Windows@@YAJPEAUIXmlDocument@Dom@Xml@Data@4@PEBG1@Z; Windows::Internal::UI::WindowsTip::SetToastImageSrc(Windows::Data::Xml::Dom::IXmlDocument *,ushort const *,ushort const *)
0x18033b239  mov     ebx, eax
0x18033b23b  test    eax, eax
0x18033b23d  jns     loc_18033B174
0x18033b243  mov     edx, 18Bh
0x18033b248  jmp     loc_18033B1BD
0x18033b24d  cmp     dword ptr [r12+28h], 1
0x18033b253  ja      loc_18033B52B
0x18033b259  mov     [rsp+108h+newString], rsi
0x18033b25e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SoftLandingV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SoftLandingV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SoftLandingV2> `wil::Feature<__WilFeatureTraits_Feature_SoftLandingV2>::GetImpl(void)'::`2'::impl
0x18033b265  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SoftLandingV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SoftLandingV2>::__private_IsEnabled(void)
0x18033b26a  test    al, al
0x18033b26c  jz      loc_18033B396
0x18033b272  xor     edx, edx; length
0x18033b274  mov     rcx, [r12+20h]; string
0x18033b279  call    cs:__imp_WindowsGetStringRawBuffer
0x18033b280  nop     dword ptr [rax+rax+00h]
0x18033b285  mov     rbx, rax
0x18033b288  xor     edx, edx; length
0x18033b28a  mov     rcx, r14; string
0x18033b28d  call    cs:__imp_WindowsGetStringRawBuffer
0x18033b294  nop     dword ptr [rax+rax+00h]
0x18033b299  mov     r8, rbx
0x18033b29c  mov     rdx, rax
0x18033b29f  lea     rcx, [rsp+108h+var_B0]
0x18033b2a4  call    ?CreateActionString@SoftLandingV2Helper@WindowsTip@UI@Internal@Windows@@SA?AUhstring@winrt@@PEBG0@Z; Windows::Internal::UI::WindowsTip::SoftLandingV2Helper::CreateActionString(ushort const *,ushort const *)
0x18033b2a9  mov     rcx, [rsp+108h+newString]; string
0x18033b2ae  call    cs:__imp_WindowsDeleteString
0x18033b2b5  nop     dword ptr [rax+rax+00h]
0x18033b2ba  mov     [rsp+108h+newString], rsi
0x18033b2bf  lea     rdx, [rsp+108h+newString]; newString
0x18033b2c4  mov     rcx, [rsp+108h+var_B0]; string
0x18033b2c9  call    cs:__imp_WindowsDuplicateString
0x18033b2d0  nop     dword ptr [rax+rax+00h]
0x18033b2d5  mov     ebx, eax
0x18033b2d7  test    eax, eax
0x18033b2d9  jns     short loc_18033B329
0x18033b2db  mov     rcx, [rsp+108h]; this
0x18033b2e3  mov     r9d, eax; char *
0x18033b2e6  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18033b2ed  mov     edx, 1A2h; void *
0x18033b2f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033b2f7  lea     rcx, [rsp+108h+var_B0]
0x18033b2fc  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18033b301  nop
0x18033b302  mov     rcx, [rsp+108h+newString]; string
0x18033b307  call    cs:__imp_WindowsDeleteString
0x18033b30e  nop     dword ptr [rax+rax+00h]
0x18033b313  mov     [rsp+108h+newString], rsi
0x18033b318  lea     rcx, [rsp+108h+var_A8]
0x18033b31d  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033b322  mov     eax, ebx
0x18033b324  jmp     loc_18033B539
0x18033b329  lea     rcx, [rsp+108h+var_B0]
0x18033b32e  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18033b333  nop
0x18033b334  mov     [rsp+108h+var_C0], rsi
0x18033b339  mov     rax, [r15]
0x18033b33c  mov     rbx, [rax]
0x18033b33f  lea     rcx, [rsp+108h+var_C0]
0x18033b344  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033b349  lea     r8, [rsp+108h+var_C0]
0x18033b34e  lea     rdx, _GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b
0x18033b355  mov     rcx, r15
0x18033b358  mov     rax, rbx
0x18033b35b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033b360  mov     ebx, eax
0x18033b362  test    eax, eax
0x18033b364  jns     loc_18033B425
0x18033b36a  mov     rcx, [rsp+108h]; this
0x18033b372  mov     r9d, eax; char *
0x18033b375  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18033b37c  mov     edx, 1B4h; void *
  ... truncated ...
```
