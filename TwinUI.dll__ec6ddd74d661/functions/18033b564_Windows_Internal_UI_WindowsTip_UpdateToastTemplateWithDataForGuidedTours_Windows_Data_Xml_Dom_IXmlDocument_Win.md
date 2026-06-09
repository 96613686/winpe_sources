# Windows::Internal::UI::WindowsTip::UpdateToastTemplateWithDataForGuidedTours(Windows::Data::Xml::Dom::IXmlDocument *,Windows::Internal::UI::WindowsTip::CreativeVisualDataForGuidedTours &,HSTRING__ *)

- ea: `0x18033b564`
- end: `0x18033bb60`
- name: `?UpdateToastTemplateWithDataForGuidedTours@WindowsTip@UI@Internal@Windows@@YAJPEAUIXmlDocument@Dom@Xml@Data@4@AEAUCreativeVisualDataForGuidedTours@1234@PEAUHSTRING__@@@Z`
- size: `1532`
- prototype: `__int64 __fastcall(Windows::Internal::UI::WindowsTip *__hidden this, struct Windows::Data::Xml::Dom::IXmlDocument *, struct Windows::Internal::UI::WindowsTip::CreativeVisualDataForGuidedTours *, HSTRING)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180331ff4`

## callees

- `0x180009dd0`
- `0x18001c710`
- `0x1800378dc`
- `0x180037b9c`
- `0x180053740`
- `0x180136c44`
- `0x180142e10`
- `0x1802283fc`
- `0x1802284b0`
- `0x1803278b0`
- `0x180331dbc`
- `0x180337d50`
- `0x1803387d4`
- `0x180338dec`
- `0x18033923c`
- `0x18033b564`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033b946`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033b99f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033bb03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033bb4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033b946`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033b99f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033bb03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18033bb4c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18033b961`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18033b961`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033b925`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033babb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033b925`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18033babb`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Internal::UI::WindowsTip::UpdateToastTemplateWithDataForGuidedTours(
        Windows::Internal::UI::WindowsTip *this,
        struct Windows::Data::Xml::Dom::IXmlDocument *a2,
        struct Windows::Internal::UI::WindowsTip::CreativeVisualDataForGuidedTours *a3,
        HSTRING a4)
{
  struct Windows::Internal::UI::WindowsTip::CreativeVisualDataForGuidedTours *v4; // r14
  unsigned __int16 *v7; // r13
  __int64 v8; // r8
  __int64 v9; // r8
  unsigned __int16 *v10; // rdi
  __int64 v11; // r8
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
  unsigned __int16 *v33; // r9
  HSTRING v34; // rbx
  __int64 v35; // rax
  struct Windows::Data::Xml::Dom::IXmlNode *v36; // r8
  struct Windows::Data::Xml::Dom::IXmlNode **v37; // r9
  const unsigned __int16 *v38; // rbx
  PCWSTR StringRawBuffer; // rax
  HRESULT v40; // eax
  unsigned int v41; // ebx
  __int64 (__fastcall *v43)(Windows::Internal::UI::WindowsTip *, GUID *, unsigned __int64 *); // rbx
  int v44; // eax
  unsigned __int64 v45; // rdi
  __int64 (__fastcall *v46)(unsigned __int64, __int64, Windows::Internal::UI::WindowsTip **); // rbx
  int v47; // eax
  __int64 v48; // rdx
  const unsigned __int16 *v49; // rax
  const unsigned __int16 *v50; // r9
  HSTRING v51; // [rsp+20h] [rbp-A8h] BYREF
  unsigned __int64 v52; // [rsp+28h] [rbp-A0h] BYREF
  HSTRING string; // [rsp+30h] [rbp-98h] BYREF
  Windows::Internal::UI::WindowsTip *v54; // [rsp+38h] [rbp-90h] BYREF
  __int64 v55; // [rsp+40h] [rbp-88h] BYREF
  unsigned int v56; // [rsp+48h] [rbp-80h] BYREF
  unsigned __int16 *v57; // [rsp+50h] [rbp-78h]
  struct Windows::Internal::UI::WindowsTip::CreativeVisualDataForGuidedTours *v58; // [rsp+58h] [rbp-70h]
  unsigned __int16 *v59; // [rsp+60h] [rbp-68h]
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-60h] BYREF
  __int64 v61; // [rsp+80h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v4 = a3;
  v58 = a3;
  v7 = (unsigned __int16 *)winrt::hstring::c_str((winrt::hstring *)(*((_QWORD *)a2 + 9) + 8LL));
  string = (HSTRING)v7;
  v54 = (Windows::Internal::UI::WindowsTip *)winrt::hstring::c_str((winrt::hstring *)(v8 + 16));
  v10 = (unsigned __int16 *)winrt::hstring::c_str((winrt::hstring *)(v9 + 64));
  v57 = v10;
  v59 = (unsigned __int16 *)winrt::hstring::c_str((winrt::hstring *)(v11 + 96));
  v52 = 0;
  v56 = 0;
  v13 = Windows::Internal::UI::WindowsTip::SetToastTemplateToToastGeneric(this, v12);
  v14 = v13;
  if ( v13 >= 0 )
  {
    v55 = 0;
    v15 = *(__int64 (__fastcall **)(Windows::Internal::UI::WindowsTip *, __int64, __int64 *))(*(_QWORD *)this + 128LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v55);
    v61 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"text", 5u, 4u);
    v16 = v15(this, v61, &v55);
    v14 = v16;
    if ( v16 < 0 )
    {
      v17 = 289;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v16,
        (int)v51);
      goto LABEL_49;
    }
    v18 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v55 + 48LL))(v55, &v56);
    if ( v18 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x122,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v18,
        (int)v51);
LABEL_23:
      v32 = StringCchLengthW(v10, 0x104u, &v52);
      if ( v32 >= 0 )
      {
        if ( v52 )
        {
          v16 = Windows::Internal::UI::WindowsTip::SetToastImageSrc(
                  this,
                  (struct Windows::Data::Xml::Dom::IXmlDocument *)v10,
                  v59,
                  v33);
          v14 = v16;
          if ( v16 < 0 )
          {
            v17 = 315;
            goto LABEL_28;
          }
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x139,
          (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
          (const char *)(unsigned int)v32,
          (int)v51);
      }
      if ( !*(_BYTE *)a2 )
      {
        v16 = Windows::Internal::UI::WindowsTip::SetToastActionsForGuidedTours(this, a2, v4, (HSTRING)v33);
        v14 = v16;
        if ( v16 < 0 )
        {
          v17 = 321;
          goto LABEL_28;
        }
        if ( *((_DWORD *)a2 + 2) <= 1u )
        {
          string = 0;
          v38 = winrt::hstring::c_str((struct Windows::Data::Xml::Dom::IXmlDocument *)((char *)a2 + 40));
          StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)v4, 0);
          try
          {
            Windows::Internal::UI::WindowsTip::SoftLandingV2Helper::CreateActionString(&v51, StringRawBuffer, v38);
            WindowsDeleteString(string);
            string = 0;
            v40 = WindowsDuplicateString(v51, &string);
          }
          catch ( ... )
          {
            LODWORD(v51) = *(_DWORD *)winrt::to_hresult(&v51);
            v14 = (unsigned int)v51;
            goto LABEL_51;
          }
          v41 = v40;
          if ( v40 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x14B,
              (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
              (const char *)(unsigned int)v40,
              (int)v51);
            winrt::handle_type<winrt::impl::hstring_traits>::close(&v51);
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v55);
            return v41;
          }
          winrt::handle_type<winrt::impl::hstring_traits>::close(&v51);
          v52 = 0;
          v43 = **(__int64 (__fastcall ***)(Windows::Internal::UI::WindowsTip *, GUID *, unsigned __int64 *))this;
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v52);
          v44 = v43(this, &GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b, &v52);
          v14 = v44;
          if ( v44 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x154,
              (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
              (const char *)(unsigned int)v44,
              (int)v51);
            goto LABEL_41;
          }
          v54 = 0;
          v45 = v52;
          v46 = *(__int64 (__fastcall **)(unsigned __int64, __int64, Windows::Internal::UI::WindowsTip **))(*(_QWORD *)v52 + 48LL);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v54);
          v61 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"toast", 6u, 5u);
          v47 = v46(v45, v61, &v54);
          v14 = v47;
          if ( v47 < 0 )
          {
            v48 = 342;
LABEL_44:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v48,
              (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
              (const char *)(unsigned int)v47,
              (int)v51);
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v54);
LABEL_41:
            Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v52);
LABEL_51:
            WindowsDeleteString(string);
            string = 0;
            goto LABEL_49;
          }
          v49 = WindowsGetStringRawBuffer(string, 0);
          v47 = Windows::Internal::UI::WindowsTip::SetNodeAttribute(
                  v54,
                  (struct Windows::Data::Xml::Dom::IXmlNode *)L"launch",
                  v49,
                  v50);
          v14 = v47;
          if ( v47 < 0 )
          {
            v48 = 343;
            goto LABEL_44;
          }
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v54);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v52);
          WindowsDeleteString(string);
        }
      }
      v14 = 0;
      goto LABEL_49;
    }
    if ( !v56 )
      goto LABEL_23;
    v51 = 0;
    v19 = v55;
    v20 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v55 + 56LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v51);
    appended = v20(v19, 0, &v51);
    v14 = appended;
    if ( appended < 0 )
    {
      v22 = 294;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)appended,
        (int)v51);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v51);
LABEL_49:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v55);
      return v14;
    }
    v23 = 0;
    v24 = StringCchLengthW(v7, 0x7FFFFFFFu, &v52);
    if ( v24 >= 0 )
    {
      if ( v52 )
      {
        v25 = v51;
        v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &string);
        appended = Windows::Internal::UI::WindowsTip::CreateAndAppendTextNode(
                     *(Windows::Internal::UI::WindowsTip **)(v26 + 24),
                     v25,
                     v27,
                     v28);
        v14 = appended;
        if ( appended < 0 )
        {
          v22 = 298;
          goto LABEL_10;
        }
        v23 = 1;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x128,
        (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
        (const char *)(unsigned int)v24,
        (int)v51);
    }
    if ( v56 > v23 )
    {
      v29 = v55;
      v30 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v55 + 56LL);
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v51);
      appended = v30(v29, v23, &v51);
      v14 = appended;
      if ( appended < 0 )
      {
        v22 = 304;
        goto LABEL_10;
      }
      v31 = StringCchLengthW((const unsigned __int16 *)v54, 0x7FFFFFFFu, &v52);
      if ( v31 >= 0 )
      {
        if ( v52 )
        {
          v34 = v51;
          v35 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v54);
          appended = Windows::Internal::UI::WindowsTip::CreateAndAppendTextNode(
                       *(Windows::Internal::UI::WindowsTip **)(v35 + 24),
                       v34,
                       v36,
                       v37);
          v14 = appended;
          if ( appended < 0 )
          {
            v22 = 308;
            goto LABEL_10;
          }
        }
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x132,
          (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
          (const char *)(unsigned int)v31,
          (int)v51);
      }
    }
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v51);
    v10 = v57;
    v4 = v58;
    goto LABEL_23;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x11E,
    (unsigned int)"shell\\twinui\\softlanding\\lib\\windowstippresenter.cpp",
    (const char *)(unsigned int)v13,
    (int)v51);
  return v14;
}

```

## disassembly

```asm
0x18033b564  push    rbx
0x18033b566  push    rsi
0x18033b567  push    rdi
0x18033b568  push    r12
0x18033b56a  push    r13
0x18033b56c  push    r14
0x18033b56e  push    r15
0x18033b570  sub     rsp, 90h
0x18033b577  mov     rax, cs:__security_cookie
0x18033b57e  xor     rax, rsp
0x18033b581  mov     [rsp+0C8h+var_40], rax
0x18033b589  mov     r14, r8
0x18033b58c  mov     [rsp+0C8h+var_70], r8
0x18033b591  mov     r15, rdx
0x18033b594  mov     r12, rcx
0x18033b597  mov     r8, [rdx+48h]
0x18033b59b  lea     rcx, [r8+8]; this
0x18033b59f  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18033b5a4  mov     r13, rax
0x18033b5a7  mov     [rsp+0C8h+string], rax
0x18033b5ac  lea     rcx, [r8+10h]; this
0x18033b5b0  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18033b5b5  mov     [rsp+0C8h+var_90], rax
0x18033b5ba  lea     rcx, [r8+40h]; this
0x18033b5be  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18033b5c3  mov     rdi, rax
0x18033b5c6  mov     [rsp+0C8h+var_78], rax
0x18033b5cb  lea     rcx, [r8+60h]; this
0x18033b5cf  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18033b5d4  mov     [rsp+0C8h+var_68], rax
0x18033b5d9  xor     esi, esi
0x18033b5db  mov     [rsp+0C8h+var_A0], rsi
0x18033b5e0  mov     [rsp+0C8h+var_80], esi
0x18033b5e4  mov     rcx, r12; this
0x18033b5e7  call    ?SetToastTemplateToToastGeneric@WindowsTip@UI@Internal@Windows@@YAJPEAUIXmlDocument@Dom@Xml@Data@4@@Z; Windows::Internal::UI::WindowsTip::SetToastTemplateToToastGeneric(Windows::Data::Xml::Dom::IXmlDocument *)
0x18033b5ec  mov     ebx, eax
0x18033b5ee  test    eax, eax
0x18033b5f0  jns     short loc_18033B613
0x18033b5f2  mov     rcx, [rsp+0C8h]; this
0x18033b5fa  mov     r9d, eax; char *
0x18033b5fd  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18033b604  mov     edx, 11Eh; void *
0x18033b609  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033b60e  jmp     loc_18033BB1B
0x18033b613  mov     [rsp+0C8h+var_88], rsi
0x18033b618  mov     rax, [r12]
0x18033b61c  mov     rbx, [rax+80h]
0x18033b623  lea     rcx, [rsp+0C8h+var_88]
0x18033b628  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033b62d  mov     [rsp+0C8h+var_48], rsi
0x18033b635  mov     r9d, 4; unsigned int
0x18033b63b  lea     r8d, [r9+1]; unsigned int
0x18033b63f  lea     rdx, aText_0; "text"
0x18033b646  lea     rcx, [rsp+0C8h+hstringHeader]; hstringHeader
0x18033b64b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18033b650  nop
0x18033b651  lea     r8, [rsp+0C8h+var_88]
0x18033b656  mov     rdx, [rsp+0C8h+var_48]
0x18033b65e  mov     rcx, r12
0x18033b661  mov     rax, rbx
0x18033b664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033b669  mov     ebx, eax
0x18033b66b  test    eax, eax
0x18033b66d  jns     short loc_18033B679
0x18033b66f  mov     edx, 121h
0x18033b674  jmp     loc_18033B87A
0x18033b679  mov     rcx, [rsp+0C8h+var_88]
0x18033b67e  mov     rax, [rcx]
0x18033b681  lea     rdx, [rsp+0C8h+var_80]
0x18033b686  mov     rax, [rax+30h]
0x18033b68a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033b68f  mov     rcx, [rsp+0C8h]; this
0x18033b697  test    eax, eax
0x18033b699  jns     short loc_18033B6B4
0x18033b69b  mov     r9d, eax; char *
0x18033b69e  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18033b6a5  mov     edx, 122h; void *
0x18033b6aa  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18033b6af  jmp     loc_18033B81E
0x18033b6b4  cmp     [rsp+0C8h+var_80], esi
0x18033b6b8  jbe     loc_18033B81E
0x18033b6be  mov     [rsp+0C8h+var_A8], rsi; int
0x18033b6c3  mov     rdi, [rsp+0C8h+var_88]
0x18033b6c8  mov     rax, [rdi]
0x18033b6cb  mov     rbx, [rax+38h]
0x18033b6cf  lea     rcx, [rsp+0C8h+var_A8]
0x18033b6d4  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033b6d9  lea     r8, [rsp+0C8h+var_A8]
0x18033b6de  xor     edx, edx
0x18033b6e0  mov     rcx, rdi
0x18033b6e3  mov     rax, rbx
0x18033b6e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033b6eb  mov     ebx, eax
0x18033b6ed  test    eax, eax
0x18033b6ef  jns     short loc_18033B71D
0x18033b6f1  mov     edx, 126h; void *
0x18033b6f6  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18033b6fd  mov     r9d, eax; char *
0x18033b700  mov     rcx, [rsp+0C8h]; this
0x18033b708  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033b70d  nop
0x18033b70e  lea     rcx, [rsp+0C8h+var_A8]
0x18033b713  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033b718  jmp     loc_18033BB11
0x18033b71d  mov     r14d, esi
0x18033b720  lea     r8, [rsp+0C8h+var_A0]; unsigned __int64 *
0x18033b725  mov     edx, 7FFFFFFFh; unsigned __int64
0x18033b72a  mov     rcx, r13; unsigned __int16 *
0x18033b72d  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18033b732  mov     rcx, [rsp+0C8h]; this
0x18033b73a  test    eax, eax
0x18033b73c  jns     short loc_18033B754
0x18033b73e  mov     r9d, eax; char *
0x18033b741  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18033b748  mov     edx, 128h; void *
0x18033b74d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18033b752  jmp     short loc_18033B791
0x18033b754  cmp     [rsp+0C8h+var_A0], rsi
0x18033b759  jbe     short loc_18033B791
0x18033b75b  mov     rbx, [rsp+0C8h+var_A8]
0x18033b760  lea     rdx, [rsp+0C8h+string]
0x18033b765  lea     rcx, [rsp+0C8h+hstringHeader]
0x18033b76a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18033b76f  mov     rdx, rbx; HSTRING
0x18033b772  mov     rcx, [rax+18h]; this
0x18033b776  call    ?CreateAndAppendTextNode@WindowsTip@UI@Internal@Windows@@YAJPEAUHSTRING__@@PEAUIXmlNode@Dom@Xml@Data@4@PEAPEAU67894@@Z; Windows::Internal::UI::WindowsTip::CreateAndAppendTextNode(HSTRING__ *,Windows::Data::Xml::Dom::IXmlNode *,Windows::Data::Xml::Dom::IXmlNode * *)
0x18033b77b  mov     ebx, eax
0x18033b77d  test    eax, eax
0x18033b77f  jns     short loc_18033B78B
0x18033b781  mov     edx, 12Ah
0x18033b786  jmp     loc_18033B6F6
0x18033b78b  mov     r14d, 1
0x18033b791  cmp     [rsp+0C8h+var_80], r14d
0x18033b796  jbe     short loc_18033B80A
0x18033b798  mov     rdi, [rsp+0C8h+var_88]
0x18033b79d  mov     rax, [rdi]
0x18033b7a0  mov     rbx, [rax+38h]
0x18033b7a4  lea     rcx, [rsp+0C8h+var_A8]
0x18033b7a9  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033b7ae  lea     r8, [rsp+0C8h+var_A8]
0x18033b7b3  mov     edx, r14d
0x18033b7b6  mov     rcx, rdi
0x18033b7b9  mov     rax, rbx
0x18033b7bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033b7c1  mov     ebx, eax
0x18033b7c3  test    eax, eax
0x18033b7c5  jns     short loc_18033B7D1
0x18033b7c7  mov     edx, 130h
0x18033b7cc  jmp     loc_18033B6F6
0x18033b7d1  lea     r8, [rsp+0C8h+var_A0]; unsigned __int64 *
0x18033b7d6  mov     edx, 7FFFFFFFh; unsigned __int64
0x18033b7db  mov     rcx, [rsp+0C8h+var_90]; unsigned __int16 *
0x18033b7e0  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18033b7e5  mov     rcx, [rsp+0C8h]; this
0x18033b7ed  test    eax, eax
0x18033b7ef  jns     loc_18033B896
0x18033b7f5  mov     r9d, eax; char *
0x18033b7f8  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18033b7ff  mov     edx, 132h; void *
0x18033b804  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18033b809  nop
0x18033b80a  lea     rcx, [rsp+0C8h+var_A8]
0x18033b80f  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033b814  mov     rdi, [rsp+0C8h+var_78]
0x18033b819  mov     r14, [rsp+0C8h+var_70]
0x18033b81e  lea     r8, [rsp+0C8h+var_A0]; unsigned __int64 *
0x18033b823  mov     edx, 104h; unsigned __int64
0x18033b828  mov     rcx, rdi; unsigned __int16 *
0x18033b82b  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18033b830  mov     rcx, [rsp+0C8h]; this
0x18033b838  test    eax, eax
0x18033b83a  jns     loc_18033B8D5
0x18033b840  mov     r9d, eax; char *
0x18033b843  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18033b84a  mov     edx, 139h; void *
0x18033b84f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18033b854  cmp     [r15], sil
0x18033b857  jnz     loc_18033BB0F
0x18033b85d  mov     r8, r14; struct Windows::Internal::UI::WindowsTip::CreativeVisualDataForGuidedTours *
0x18033b860  mov     rdx, r15; struct Windows::Data::Xml::Dom::IXmlDocument *
0x18033b863  mov     rcx, r12; this
0x18033b866  call    ?SetToastActionsForGuidedTours@WindowsTip@UI@Internal@Windows@@YAJPEAUIXmlDocument@Dom@Xml@Data@4@AEAUCreativeVisualDataForGuidedTours@1234@PEAUHSTRING__@@@Z; Windows::Internal::UI::WindowsTip::SetToastActionsForGuidedTours(Windows::Data::Xml::Dom::IXmlDocument *,Windows::Internal::UI::WindowsTip::CreativeVisualDataForGuidedTours &,HSTRING__ *)
0x18033b86b  mov     ebx, eax
0x18033b86d  test    eax, eax
0x18033b86f  jns     loc_18033B904
0x18033b875  mov     edx, 141h; void *
0x18033b87a  mov     r9d, eax; char *
0x18033b87d  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18033b884  mov     rcx, [rsp+0C8h]; this
0x18033b88c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033b891  jmp     loc_18033BB11
0x18033b896  cmp     [rsp+0C8h+var_A0], rsi
0x18033b89b  jbe     loc_18033B80A
0x18033b8a1  mov     rbx, [rsp+0C8h+var_A8]
0x18033b8a6  lea     rdx, [rsp+0C8h+var_90]
0x18033b8ab  lea     rcx, [rsp+0C8h+hstringHeader]
0x18033b8b0  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18033b8b5  mov     rdx, rbx; HSTRING
0x18033b8b8  mov     rcx, [rax+18h]; this
0x18033b8bc  call    ?CreateAndAppendTextNode@WindowsTip@UI@Internal@Windows@@YAJPEAUHSTRING__@@PEAUIXmlNode@Dom@Xml@Data@4@PEAPEAU67894@@Z; Windows::Internal::UI::WindowsTip::CreateAndAppendTextNode(HSTRING__ *,Windows::Data::Xml::Dom::IXmlNode *,Windows::Data::Xml::Dom::IXmlNode * *)
0x18033b8c1  mov     ebx, eax
0x18033b8c3  test    eax, eax
0x18033b8c5  jns     loc_18033B80A
0x18033b8cb  mov     edx, 134h
0x18033b8d0  jmp     loc_18033B6F6
0x18033b8d5  cmp     [rsp+0C8h+var_A0], rsi
0x18033b8da  jbe     loc_18033B854
0x18033b8e0  mov     r8, [rsp+0C8h+var_68]; unsigned __int16 *
0x18033b8e5  mov     rdx, rdi; struct Windows::Data::Xml::Dom::IXmlDocument *
0x18033b8e8  mov     rcx, r12; this
0x18033b8eb  call    ?SetToastImageSrc@WindowsTip@UI@Internal@Windows@@YAJPEAUIXmlDocument@Dom@Xml@Data@4@PEBG1@Z; Windows::Internal::UI::WindowsTip::SetToastImageSrc(Windows::Data::Xml::Dom::IXmlDocument *,ushort const *,ushort const *)
0x18033b8f0  mov     ebx, eax
0x18033b8f2  test    eax, eax
0x18033b8f4  jns     loc_18033B854
0x18033b8fa  mov     edx, 13Bh
0x18033b8ff  jmp     loc_18033B87A
0x18033b904  cmp     dword ptr [r15+8], 1
0x18033b909  ja      loc_18033BB0F
0x18033b90f  mov     [rsp+0C8h+string], rsi
0x18033b914  lea     rcx, [r15+28h]; this
0x18033b918  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18033b91d  mov     rbx, rax
0x18033b920  xor     edx, edx; length
0x18033b922  mov     rcx, r14; string
0x18033b925  call    cs:__imp_WindowsGetStringRawBuffer
0x18033b92c  nop     dword ptr [rax+rax+00h]
0x18033b931  mov     r8, rbx
0x18033b934  mov     rdx, rax
0x18033b937  lea     rcx, [rsp+0C8h+var_A8]
0x18033b93c  call    ?CreateActionString@SoftLandingV2Helper@WindowsTip@UI@Internal@Windows@@SA?AUhstring@winrt@@PEBG0@Z; Windows::Internal::UI::WindowsTip::SoftLandingV2Helper::CreateActionString(ushort const *,ushort const *)
0x18033b941  mov     rcx, [rsp+0C8h+string]; string
0x18033b946  call    cs:__imp_WindowsDeleteString
0x18033b94d  nop     dword ptr [rax+rax+00h]
0x18033b952  mov     [rsp+0C8h+string], rsi
0x18033b957  lea     rdx, [rsp+0C8h+string]; newString
0x18033b95c  mov     rcx, [rsp+0C8h+var_A8]; string
0x18033b961  call    cs:__imp_WindowsDuplicateString
0x18033b968  nop     dword ptr [rax+rax+00h]
0x18033b96d  mov     ebx, eax
0x18033b96f  test    eax, eax
0x18033b971  jns     short loc_18033B9C1
0x18033b973  mov     rcx, [rsp+0C8h]; this
0x18033b97b  mov     r9d, eax; char *
0x18033b97e  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18033b985  mov     edx, 14Bh; void *
0x18033b98a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033b98f  lea     rcx, [rsp+0C8h+var_A8]
0x18033b994  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18033b999  nop
0x18033b99a  mov     rcx, [rsp+0C8h+string]; string
0x18033b99f  call    cs:__imp_WindowsDeleteString
0x18033b9a6  nop     dword ptr [rax+rax+00h]
0x18033b9ab  mov     [rsp+0C8h+string], rsi
0x18033b9b0  lea     rcx, [rsp+0C8h+var_88]
0x18033b9b5  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033b9ba  mov     eax, ebx
0x18033b9bc  jmp     loc_18033BB1D
0x18033b9c1  lea     rcx, [rsp+0C8h+var_A8]
0x18033b9c6  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18033b9cb  nop
0x18033b9cc  mov     [rsp+0C8h+var_A0], rsi
0x18033b9d1  mov     rax, [r12]
0x18033b9d5  mov     rbx, [rax]
0x18033b9d8  lea     rcx, [rsp+0C8h+var_A0]
0x18033b9dd  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033b9e2  lea     r8, [rsp+0C8h+var_A0]
0x18033b9e7  lea     rdx, _GUID_63dbba8b_d0db_4fe1_b745_f9433afdc25b
0x18033b9ee  mov     rcx, r12
0x18033b9f1  mov     rax, rbx
0x18033b9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18033b9f9  mov     ebx, eax
0x18033b9fb  test    eax, eax
0x18033b9fd  jns     short loc_18033BA2B
0x18033b9ff  mov     rcx, [rsp+0C8h]; this
0x18033ba07  mov     r9d, eax; char *
0x18033ba0a  lea     r8, aShellTwinuiSof_9; "shell\\twinui\\softlanding\\lib\\window"...
0x18033ba11  mov     edx, 154h; void *
0x18033ba16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18033ba1b  nop
0x18033ba1c  lea     rcx, [rsp+0C8h+var_A0]
0x18033ba21  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033ba26  jmp     loc_18033BB47
0x18033ba2b  mov     [rsp+0C8h+var_90], rsi
0x18033ba30  mov     rdi, [rsp+0C8h+var_A0]
0x18033ba35  mov     rax, [rdi]
0x18033ba38  mov     rbx, [rax+30h]
0x18033ba3c  lea     rcx, [rsp+0C8h+var_90]
0x18033ba41  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18033ba46  mov     [rsp+0C8h+var_48], rsi
0x18033ba4e  mov     r9d, 5; unsigned int
0x18033ba54  lea     r8d, [r9+1]; unsigned int
0x18033ba58  lea     rdx, aToast_0; "toast"
0x18033ba5f  lea     rcx, [rsp+0C8h+hstringHeader]; hstringHeader
0x18033ba64  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18033ba69  nop
0x18033ba6a  lea     r8, [rsp+0C8h+var_90]
0x18033ba6f  mov     rdx, [rsp+0C8h+var_48]
0x18033ba77  mov     rcx, rdi
0x18033ba7a  mov     rax, rbx
0x18033ba7d  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
