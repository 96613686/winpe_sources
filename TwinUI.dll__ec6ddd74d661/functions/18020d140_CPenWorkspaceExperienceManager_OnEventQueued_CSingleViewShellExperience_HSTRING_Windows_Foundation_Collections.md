# CPenWorkspaceExperienceManager::OnEventQueued(CSingleViewShellExperience *,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *)

- ea: `0x18020d140`
- end: `0x18020dcb2`
- name: `?OnEventQueued@CPenWorkspaceExperienceManager@@EEAAJPEAVCSingleViewShellExperience@@PEAUHSTRING__@@PEAUIPropertySet@Collections@Foundation@Windows@@@Z`
- size: `2930`
- prototype: `int(CPenWorkspaceExperienceManager *__hidden this, struct CSingleViewShellExperience *, HSTRING, struct Windows::Foundation::Collections::IPropertySet *)`
- caller_count: `0`
- callee_count: `43`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180009dd0`
- `0x180009dfc`
- `0x18000edd4`
- `0x180013848`
- `0x180017808`
- `0x18001c710`
- `0x1800378dc`
- `0x180037b9c`
- `0x18003cd88`
- `0x180053740`
- `0x18006f0ec`
- `0x180084964`
- `0x1800862bc`
- `0x1800946a4`
- `0x1800a5ab8`
- `0x1800c4bf4`
- `0x1800f4b10`
- `0x1800f4fe4`
- `0x1801003f8`
- `0x18011fe50`
- `0x180135318`
- `0x180142e10`
- `0x18020645c`
- `0x1802066a4`
- `0x180206a18`
- `0x180207458`
- `0x180207490`
- `0x18020a320`
- `0x18020a6f8`
- `0x18020aa0c`
- `0x18020b450`
- `0x18020b990`
- `0x18020bb90`
- `0x18020be64`
- `0x18020c348`
- `0x18020c4fc`
- `0x18020c634`
- `0x18020d140`
- `0x18020f198`
- `0x18020f558`
- `0x180210520`
- `0x180231f74`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020d1ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020d277`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020d7b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020d86e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020d1ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020d277`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020d7b9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18020d86e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18020d18c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18020d253`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18020d80e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18020d18c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18020d253`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18020d80e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x18020d266`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowTextW` at `0x18020d266`

## string_xrefs

- `0x18020d99c`: `WhiteboardInstallStatusChanged`
- `0x18020db1f`: `WhiteboardInstallStatusChanged`
- `0x18020d9a3`: `JournalInstallStatusChanged`
- `0x18020db26`: `JournalInstallStatusChanged`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CPenWorkspaceExperienceManager::OnEventQueued(
        CPenWorkspaceExperienceManager *this,
        struct CSingleViewShellExperience *a2,
        Microsoft::WRL::Wrappers::Details *a3,
        struct Windows::Foundation::Collections::IPropertySet *a4)
{
  const struct _tlgProvider_t *v7; // rax
  int v8; // esi
  int v9; // r9d
  __int64 v10; // rax
  HSTRING v11; // r8
  __int64 v12; // rax
  unsigned int ViewWindow; // esi
  HSTRING v14; // r8
  const WCHAR *StringRawBuffer; // rax
  __int64 v16; // rax
  HSTRING v17; // r8
  __int64 v18; // rax
  HSTRING v19; // r8
  __int64 v20; // rax
  HSTRING v21; // r8
  __int64 v22; // rax
  int v23; // eax
  int v24; // ebx
  __int64 v26; // rax
  HSTRING v27; // r8
  int v28; // edx
  __int64 v29; // rax
  HSTRING v30; // r8
  __int64 v31; // rax
  HSTRING v32; // r8
  __int64 v33; // rdx
  __int64 v34; // rax
  HSTRING v35; // r8
  __int64 v36; // rax
  HSTRING v37; // r8
  __int64 v38; // rax
  HSTRING v39; // r8
  __int64 v40; // rax
  HSTRING v41; // r8
  __int64 v42; // rax
  HSTRING v43; // r8
  __int64 v44; // rcx
  __int64 v45; // rax
  HSTRING v46; // r8
  char *v47; // r14
  int LockAppHost; // eax
  __int64 v49; // rdx
  HSTRING v50; // rbx
  __int64 (__fastcall *v51)(HSTRING, GUID *, HSTRING *); // rdi
  __int64 v52; // rax
  HSTRING v53; // r8
  __int64 v54; // rax
  HSTRING v55; // r8
  int v56; // eax
  int v57; // eax
  __int64 v58; // rdx
  __int64 v59; // rax
  HSTRING v60; // r8
  int v61; // eax
  __int64 v62; // rax
  HSTRING v63; // r8
  __int64 v64; // rax
  int v65; // eax
  const unsigned __int16 *v66; // rax
  int v67; // eax
  int v68; // eax
  HSTRING *p_string; // rcx
  __int64 v70; // rax
  HSTRING v71; // r8
  __int64 v72; // rdx
  __int64 v73; // rax
  HSTRING v74; // r8
  __int64 v75; // rax
  HSTRING v76; // r8
  __int64 v77; // rdx
  __int64 v78; // rax
  HSTRING v79; // r8
  __int64 v80; // rax
  HSTRING v81; // r8
  __int64 v82; // rax
  HSTRING v83; // r8
  const unsigned __int16 *v84; // r14
  __int64 v85; // rax
  HSTRING v86; // r8
  const wchar_t *v87; // r15
  CPenWorkspaceExperienceManager *v88; // rdi
  int IsAppInstalling; // eax
  __int64 v90; // rax
  int v91; // eax
  __int64 v92; // rax
  __int64 v93; // rbx
  __int64 v94; // rax
  HSTRING v95; // r8
  const unsigned __int16 *v96; // r14
  __int64 v97; // rax
  HSTRING v98; // r8
  wchar_t *v99; // r15
  int v100; // eax
  int v101; // eax
  __int64 v102; // rax
  int v103; // eax
  __int64 v104; // rdx
  struct Windows::Foundation::Collections::IPropertySet *v105; // rbx
  __int64 v106; // rax
  int v107; // [rsp+20h] [rbp-59h]
  bool v108; // [rsp+30h] [rbp-49h] BYREF
  HSTRING v109; // [rsp+38h] [rbp-41h] BYREF
  HSTRING string; // [rsp+40h] [rbp-39h] BYREF
  std::_Ref_count_base *v111; // [rsp+48h] [rbp-31h]
  HWND hWnd; // [rsp+50h] [rbp-29h] BYREF
  std::_Ref_count_base *v113; // [rsp+58h] [rbp-21h]
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-19h] BYREF
  __int64 v115; // [rsp+78h] [rbp-1h]
  _BYTE v116[8]; // [rsp+80h] [rbp+7h] BYREF
  std::_Ref_count_base *v117; // [rsp+88h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v7 = SingleViewExperienceLogging::Provider();
  v8 = (int)v7;
  if ( *(_DWORD *)v7 > 5u )
  {
    hWnd = (HWND)WindowsGetStringRawBuffer((HSTRING)a3, 0);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v8,
      (unsigned int)byte_18045EB53,
      0,
      v9,
      (__int64)&hWnd);
  }
  v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F99F8);
  if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v10 + 24), v11) )
  {
    v109 = (HSTRING)a4;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v109);
    string = 0;
    WindowsDeleteString(0);
    string = 0;
    v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &off_1803F9A00);
    ViewWindow = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
                   (Windows::Internal::ShellHelpers::PropertySetHelper *)&v109,
                   *(HSTRING *)(v12 + 24));
    if ( (ViewWindow & 0x80000000) == 0
      && (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                         (Microsoft::WRL::Wrappers::Details *)string,
                         0,
                         v14) )
    {
      hWnd = 0;
      ViewWindow = CPenWorkspaceExperienceManager::GetViewWindow(
                     (CPenWorkspaceExperienceManager *)((char *)this - 104),
                     &hWnd);
      if ( (ViewWindow & 0x80000000) == 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        SetWindowTextW(hWnd, StringRawBuffer);
      }
    }
    WindowsDeleteString(string);
    string = 0;
    goto LABEL_119;
  }
  ViewWindow = 0;
  v16 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F99F0);
  if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v16 + 24), v17) )
  {
    v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F99A8);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v18 + 24), v19) )
    {
      CPenWorkspaceExperienceManager::DestroyExperienceView((CPenWorkspaceExperienceManager *)((char *)this - 104));
      return ViewWindow;
    }
    v20 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F99B0);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v20 + 24), v21) )
    {
      v109 = (HSTRING)a4;
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v109);
      LODWORD(string) = -1;
      v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F99B8);
      ViewWindow = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<int>(
                     (Windows::Internal::ShellHelpers::PropertySetHelper *)&v109,
                     *(HSTRING *)(v22 + 24));
      if ( (ViewWindow & 0x80000000) == 0 && (int)string >= 0 )
      {
        if ( *((_QWORD *)this + 8) )
        {
          v23 = CSingleViewShellExperience::SetWindowBand((char *)this + 40);
          v24 = v23;
          if ( v23 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x487,
              (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
              (const char *)(unsigned int)v23,
              v107);
LABEL_19:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v109);
            return (unsigned int)v24;
          }
        }
      }
LABEL_119:
      p_string = &v109;
LABEL_120:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(p_string);
      return ViewWindow;
    }
    v26 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F99D0);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v26 + 24), v27) )
    {
      v28 = 0;
LABEL_26:
      CPenWorkspaceExperienceManager::SetBorderAccent((CPenWorkspaceExperienceManager *)((char *)this - 104), v28);
      return ViewWindow;
    }
    v29 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F99D8);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v29 + 24), v30) )
    {
      v28 = 1;
      goto LABEL_26;
    }
    v31 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F9940);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v31 + 24), v32) )
    {
      v24 = CPenWorkspaceExperienceManager::ShowRemember((CPenWorkspaceExperienceManager *)((char *)this - 104));
      if ( v24 >= 0 )
        return (unsigned int)v24;
      v33 = 1173;
LABEL_30:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v33,
        (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
        (const char *)(unsigned int)v24,
        v107);
      return (unsigned int)v24;
    }
    v34 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F9948);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v34 + 24), v35) )
    {
      v24 = CPenWorkspaceExperienceManager::HideRemember((CPenWorkspaceExperienceManager *)((char *)this - 104));
      if ( v24 >= 0 )
        return (unsigned int)v24;
      v33 = 1177;
      goto LABEL_30;
    }
    v36 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F9950);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v36 + 24), v37) )
    {
      v24 = CPenWorkspaceExperienceManager::SizeWindowForHome((CPenWorkspaceExperienceManager *)((char *)this - 104));
      if ( v24 >= 0 )
        return (unsigned int)v24;
      v33 = 1181;
      goto LABEL_30;
    }
    v38 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F9958);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v38 + 24), v39) )
    {
      v24 = CPenWorkspaceExperienceManager::ShowExperienceView((CPenWorkspaceExperienceManager *)((char *)this - 104));
      if ( v24 >= 0 )
        return ViewWindow;
      v33 = 1186;
      goto LABEL_30;
    }
    v40 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F9960);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v40 + 24), v41) )
    {
      v24 = CPenWorkspaceExperienceManager::CloseUI((CPenWorkspaceExperienceManager *)((char *)this - 104));
      if ( v24 >= 0 )
        return (unsigned int)v24;
      v33 = 1190;
      goto LABEL_30;
    }
    v42 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F9968);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v42 + 24), v43) )
    {
      v44 = *((_QWORD *)this + 50);
      if ( v44 )
        return (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v44 + 72LL))(v44);
      v24 = -2147418113;
      v33 = 1194;
      goto LABEL_30;
    }
    v45 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F9970);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v45 + 24), v46) )
    {
      v47 = (char *)this - 104;
      if ( !*((_BYTE *)this + 336) )
        return ViewWindow;
      v109 = 0;
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v109);
      LockAppHost = GetLockAppHost((struct ILockAppHost **)&v109);
      v24 = LockAppHost;
      if ( LockAppHost >= 0 )
      {
        v50 = v109;
        v51 = **(__int64 (__fastcall ***)(HSTRING, GUID *, HSTRING *))v109;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
        LockAppHost = v51(v50, &GUID_f2f2e6cf_4806_4728_954a_ef83a6301791, &string);
        v24 = LockAppHost;
        if ( LockAppHost >= 0 )
        {
          LockAppHost = (*(__int64 (__fastcall **)(HSTRING, char *))(*(_QWORD *)string + 32LL))(string, v47);
          v24 = LockAppHost;
          if ( LockAppHost >= 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v109);
            return ViewWindow;
          }
          v49 = 1206;
        }
        else
        {
          v49 = 1205;
        }
      }
      else
      {
        v49 = 1204;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v49,
        (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
        (const char *)(unsigned int)LockAppHost,
        v107);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v109);
      return (unsigned int)v24;
    }
    v52 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F9978);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v52 + 24), v53) )
    {
      v24 = CPenWorkspaceExperienceManager::BringToForeground((CPenWorkspaceExperienceManager *)((char *)this - 104));
      if ( v24 >= 0 )
        return ViewWindow;
      v33 = 1211;
      goto LABEL_30;
    }
    v54 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F98F0);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v54 + 24), v55) )
    {
      v56 = CPenWorkspaceExperienceManager::LaunchCustomSketchApp((CPenWorkspaceExperienceManager *)((char *)this - 104));
      if ( v56 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4BF,
          (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
          (const char *)(unsigned int)v56,
          v107);
      v57 = CPenWorkspaceExperienceManager::Hide((CPenWorkspaceExperienceManager *)((char *)this - 104), 1);
      if ( v57 >= 0 )
        return ViewWindow;
      v58 = 1216;
      goto LABEL_70;
    }
    v59 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F9910);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v59 + 24), v60) )
    {
      v61 = CPenWorkspaceExperienceManager::LaunchInkGrabApp((CPenWorkspaceExperienceManager *)((char *)this - 104));
      if ( v61 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4C4,
          (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
          (const char *)(unsigned int)v61,
          v107);
      v57 = CPenWorkspaceExperienceManager::Hide((CPenWorkspaceExperienceManager *)((char *)this - 104), 1);
      if ( v57 >= 0 )
        return ViewWindow;
      v58 = 1221;
LABEL_70:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v58,
        (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
        (const char *)(unsigned int)v57,
        v107);
      return ViewWindow;
    }
    v62 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F9918);
    if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v62 + 24), v63) )
    {
      string = (HSTRING)a4;
      Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&string);
      WindowsDeleteString(0);
      v109 = 0;
      v64 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F9920);
      v65 = Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(
              (Windows::Internal::ShellHelpers::PropertySetHelper *)&string,
              *(HSTRING *)(v64 + 24));
      if ( v65 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4CB,
          (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
          (const char *)(unsigned int)v65,
          v107);
      v66 = WindowsGetStringRawBuffer(v109, 0);
      v67 = CPenWorkspaceExperienceManager::LaunchScreenSketchApp(
              (CPenWorkspaceExperienceManager *)((char *)this - 104),
              v66);
      if ( v67 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4CC,
          (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
          (const char *)(unsigned int)v67,
          v107);
      v68 = CPenWorkspaceExperienceManager::Hide((CPenWorkspaceExperienceManager *)((char *)this - 104), 1);
      if ( v68 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4CD,
          (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
          (const char *)(unsigned int)v68,
          v107);
      WindowsDeleteString(v109);
      v109 = 0;
      p_string = &string;
      goto LABEL_120;
    }
    v70 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F9930);
    if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v70 + 24), v71) )
    {
      v73 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v116, off_1803F98F8);
      if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v73 + 24), v74) )
      {
        v75 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F9938);
        if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v75 + 24), v76) )
        {
          v78 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v116, off_1803F9900);
          if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v78 + 24), v79) )
          {
            v80 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F9908);
            if ( !(unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v80 + 24), v81) )
              Concurrency::details::_CancellationTokenState::_Cancel(*((Concurrency::details::_CancellationTokenState **)this
                                                                     + 69));
            return ViewWindow;
          }
        }
        LOBYTE(v77) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenDetachIWS>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_PenDetachIWS>::GetImpl'::`2'::impl,
          v77);
        v82 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F9900);
        v84 = L"9n318r854rhh";
        if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v82 + 24), v83) )
          v84 = L"9MSPC6MP8FM4";
        v85 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F9900);
        v87 = L"JournalInstallStatusChanged";
        if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v85 + 24), v86) )
          v87 = L"WhiteboardInstallStatusChanged";
        v108 = 0;
        v88 = (CPenWorkspaceExperienceManager *)((char *)this - 104);
        IsAppInstalling = CPenWorkspaceExperienceManager::GetIsAppInstalling(v88, v84, &v108);
        if ( IsAppInstalling < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4F0,
            (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
            (const char *)(unsigned int)IsAppInstalling,
            v107);
        if ( v108 )
          return 0;
        v109 = 0;
        hWnd = (HWND)&v109;
        v90 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&hWnd);
        v91 = Microsoft::WRL::AsWeak<CPenWorkspaceExperienceManager>(v88, v90);
        v24 = v91;
        if ( v91 >= 0 )
        {
          v92 = CPenWorkspaceExperienceManager::InstallApp(v88, v116, v84, v87);
          v93 = Concurrency::create_task<void>(&string, v92);
          hstringHeader.Reserved.Reserved1 = v88;
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = v109;
          Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&hstringHeader.Reserved.Reserved2[8]);
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = v87;
          Concurrency::task_bool_::then__lambda_150eaf9c64461fd64252382c642fd320___(v93, &hWnd, &hstringHeader);
          if ( v113 )
            std::_Ref_count_base::_Decref(v113);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&hstringHeader.Reserved.Reserved2[8]);
          if ( v111 )
            std::_Ref_count_base::_Decref(v111);
          if ( v117 )
            std::_Ref_count_base::_Decref(v117);
          Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v109);
          return ViewWindow;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4F7,
          (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
          (const char *)(unsigned int)v91,
          v107);
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v109);
        return (unsigned int)v24;
      }
    }
    LOBYTE(v72) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_PenDetachIWS>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_PenDetachIWS>::GetImpl'::`2'::impl,
      v72);
    v94 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F98F8);
    v96 = L"9n318r854rhh";
    if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v94 + 24), v95) )
      v96 = L"9MSPC6MP8FM4";
    v97 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F98F8);
    v99 = L"JournalInstallStatusChanged";
    if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(a3, *(HSTRING *)(v97 + 24), v98) )
      v99 = L"WhiteboardInstallStatusChanged";
    hWnd = (HWND)v99;
    v109 = 0;
    v115 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Foundation.Collections.ValueSet",
      0x28u,
      0x27u);
    v100 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
             v115,
             &v109);
    v24 = v100;
    if ( v100 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D7,
        (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
        (const char *)(unsigned int)v100,
        v107);
      goto LABEL_19;
    }
    string = v109;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&string);
    v108 = 0;
    v101 = CPenWorkspaceExperienceManager::GetIsAppInstalling(
             (CPenWorkspaceExperienceManager *)((char *)this - 104),
             v96,
             &v108);
    if ( v101 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4DB,
        (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
        (const char *)(unsigned int)v101,
        v107);
    v102 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1803F9928);
    if ( v108 )
    {
      v103 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<int>(
               (Windows::Internal::ShellHelpers::PropertySetHelper *)&string,
               *(HSTRING *)(v102 + 24));
      v24 = v103;
      if ( v103 < 0 )
      {
        v104 = 1246;
        goto LABEL_117;
      }
    }
    else
    {
      v103 = Windows::Internal::ShellHelpers::PropertySetHelper::SetValue<int>(
               (Windows::Internal::ShellHelpers::PropertySetHelper *)&string,
               *(HSTRING *)(v102 + 24));
      v24 = v103;
      if ( v103 < 0 )
      {
        v104 = 1250;
        goto LABEL_117;
      }
    }
    v105 = (struct Windows::Foundation::Collections::IPropertySet *)v109;
    v106 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &hWnd);
    v103 = CSingleViewShellExperience::Reactivate(
             (CPenWorkspaceExperienceManager *)((char *)this + 40),
             *(HSTRING *)(v106 + 24),
             v105,
             0);
    v24 = v103;
    if ( v103 >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
      goto LABEL_119;
    }
    v104 = 1253;
LABEL_117:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v104,
      (unsigned int)"shell\\twinui\\experiencemanagers\\lib\\penworkspaceexperiencemanager.cpp",
      (const char *)(unsigned int)v103,
      v107);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
    goto LABEL_19;
  }
  CPenWorkspaceExperienceManager::Hide((CPenWorkspaceExperienceManager *)((char *)this - 104), 0);
  return ViewWindow;
}

```

## disassembly

```asm
0x18020d140  mov     [rsp-8+arg_8], rbx
0x18020d145  mov     [rsp-8+arg_18], rsi
0x18020d14a  push    rbp
0x18020d14b  push    rdi
0x18020d14c  push    r12
0x18020d14e  push    r14
0x18020d150  push    r15
0x18020d152  lea     rbp, [rsp-37h]
0x18020d157  sub     rsp, 0B0h
0x18020d15e  mov     rax, cs:__security_cookie
0x18020d165  xor     rax, rsp
0x18020d168  mov     [rbp+57h+var_30], rax
0x18020d16c  mov     r14, r9
0x18020d16f  mov     rbx, r8
0x18020d172  mov     rdi, rcx
0x18020d175  xor     r12d, r12d
0x18020d178  call    ?Provider@SingleViewExperienceLogging@@SAPEBU_tlgProvider_t@@XZ; SingleViewExperienceLogging::Provider(void)
0x18020d17d  mov     rsi, rax
0x18020d180  mov     ecx, [rax]
0x18020d182  cmp     ecx, 5
0x18020d185  jbe     short loc_18020D1B7
0x18020d187  xor     edx, edx; length
0x18020d189  mov     rcx, rbx; string
0x18020d18c  call    cs:__imp_WindowsGetStringRawBuffer
0x18020d193  nop     dword ptr [rax+rax+00h]
0x18020d198  mov     [rbp+57h+hWnd], rax
0x18020d19c  lea     rax, [rbp+57h+hWnd]
0x18020d1a0  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18020d1a5  xor     r8d, r8d
0x18020d1a8  lea     rdx, byte_18045EB53
0x18020d1af  mov     rcx, rsi
0x18020d1b2  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18020d1b7  lea     rdx, off_1803F99F8; "NotifyWindowName"
0x18020d1be  lea     rcx, [rbp+57h+hstringHeader]
0x18020d1c2  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d1c7  mov     rdx, [rax+18h]; HSTRING
0x18020d1cb  mov     rcx, rbx; this
0x18020d1ce  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020d1d3  test    eax, eax
0x18020d1d5  jnz     loc_18020D28C
0x18020d1db  mov     [rbp+57h+var_98], r14
0x18020d1df  lea     rcx, [rbp+57h+var_98]
0x18020d1e3  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18020d1e8  nop
0x18020d1e9  mov     [rbp+57h+string], r12
0x18020d1ed  xor     ecx, ecx; string
0x18020d1ef  call    cs:__imp_WindowsDeleteString
0x18020d1f6  nop     dword ptr [rax+rax+00h]
0x18020d1fb  mov     [rbp+57h+string], r12
0x18020d1ff  lea     rdx, off_1803F9A00; "Name"
0x18020d206  lea     rcx, [rbp+57h+hstringHeader]
0x18020d20a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d20f  nop
0x18020d210  lea     r9, [rbp+57h+string]
0x18020d214  mov     rdx, [rax+18h]; HSTRING
0x18020d218  lea     rcx, [rbp+57h+var_98]; this
0x18020d21c  call    ??$GetValue@PEAUHSTRING__@@@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAPEAU4@@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<HSTRING__ *>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(HSTRING__ * *),HSTRING__ * *)
0x18020d221  mov     esi, eax
0x18020d223  test    eax, eax
0x18020d225  js      short loc_18020D273
0x18020d227  xor     edx, edx; HSTRING
0x18020d229  mov     rcx, [rbp+57h+string]; this
0x18020d22d  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020d232  test    eax, eax
0x18020d234  jz      short loc_18020D273
0x18020d236  mov     [rbp+57h+hWnd], r12
0x18020d23a  lea     rcx, [rdi-68h]; this
0x18020d23e  lea     rdx, [rbp+57h+hWnd]; HWND *
0x18020d242  call    ?GetViewWindow@CPenWorkspaceExperienceManager@@AEAAJPEAPEAUHWND__@@@Z; CPenWorkspaceExperienceManager::GetViewWindow(HWND__ * *)
0x18020d247  mov     esi, eax
0x18020d249  test    eax, eax
0x18020d24b  js      short loc_18020D273
0x18020d24d  xor     edx, edx; length
0x18020d24f  mov     rcx, [rbp+57h+string]; string
0x18020d253  call    cs:__imp_WindowsGetStringRawBuffer
0x18020d25a  nop     dword ptr [rax+rax+00h]
0x18020d25f  mov     rdx, rax; lpString
0x18020d262  mov     rcx, [rbp+57h+hWnd]; hWnd
0x18020d266  call    cs:__imp_SetWindowTextW
0x18020d26d  nop     dword ptr [rax+rax+00h]
0x18020d272  nop
0x18020d273  mov     rcx, [rbp+57h+string]; string
0x18020d277  call    cs:__imp_WindowsDeleteString
0x18020d27e  nop     dword ptr [rax+rax+00h]
0x18020d283  mov     [rbp+57h+string], r12
0x18020d287  jmp     loc_18020DC7E
0x18020d28c  mov     esi, r12d
0x18020d28f  lea     rdx, off_1803F99F0; "Dismiss"
0x18020d296  lea     rcx, [rbp+57h+hstringHeader]
0x18020d29a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d29f  mov     rdx, [rax+18h]; HSTRING
0x18020d2a3  mov     rcx, rbx; this
0x18020d2a6  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020d2ab  test    eax, eax
0x18020d2ad  jnz     short loc_18020D2BF
0x18020d2af  lea     rcx, [rdi-68h]; this
0x18020d2b3  xor     edx, edx; bool
0x18020d2b5  call    ?Hide@CPenWorkspaceExperienceManager@@AEAAJ_N@Z; CPenWorkspaceExperienceManager::Hide(bool)
0x18020d2ba  jmp     loc_18020DC87
0x18020d2bf  lea     rdx, off_1803F99A8; "StartActualDestroy"
0x18020d2c6  lea     rcx, [rbp+57h+hstringHeader]
0x18020d2ca  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d2cf  mov     rdx, [rax+18h]; HSTRING
0x18020d2d3  mov     rcx, rbx; this
0x18020d2d6  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020d2db  test    eax, eax
0x18020d2dd  jnz     short loc_18020D2ED
0x18020d2df  lea     rcx, [rdi-68h]; this
0x18020d2e3  call    ?DestroyExperienceView@CPenWorkspaceExperienceManager@@AEAAJXZ; CPenWorkspaceExperienceManager::DestroyExperienceView(void)
0x18020d2e8  jmp     loc_18020DC87
0x18020d2ed  lea     rdx, off_1803F99B0; "ChangeZBand"
0x18020d2f4  lea     rcx, [rbp+57h+hstringHeader]
0x18020d2f8  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d2fd  mov     rdx, [rax+18h]; HSTRING
0x18020d301  mov     rcx, rbx; this
0x18020d304  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020d309  test    eax, eax
0x18020d30b  jnz     loc_18020D398
0x18020d311  mov     [rbp+57h+var_98], r14
0x18020d315  lea     rcx, [rbp+57h+var_98]
0x18020d319  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18020d31e  nop
0x18020d31f  mov     dword ptr [rbp+57h+string], 0FFFFFFFFh
0x18020d326  lea     rdx, off_1803F99B8; "ZBandValue"
0x18020d32d  lea     rcx, [rbp+57h+hstringHeader]
0x18020d331  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d336  nop
0x18020d337  lea     r9, [rbp+57h+string]
0x18020d33b  mov     rdx, [rax+18h]; HSTRING
0x18020d33f  lea     rcx, [rbp+57h+var_98]; this
0x18020d343  call    ??$GetValue@H@PropertySetHelper@ShellHelpers@Internal@Windows@@AEAAJPEAUHSTRING__@@P8IPropertyValue@Foundation@3@EAAJPEAH@Z1@Z; Windows::Internal::ShellHelpers::PropertySetHelper::GetValue<int>(HSTRING__ *,long (Windows::Foundation::IPropertyValue::*)(int *),int *)
0x18020d348  mov     esi, eax
0x18020d34a  test    eax, eax
0x18020d34c  js      short loc_18020D393
0x18020d34e  mov     edx, dword ptr [rbp+57h+string]
0x18020d351  test    edx, edx
0x18020d353  js      short loc_18020D393
0x18020d355  cmp     [rdi+40h], r12
0x18020d359  jz      short loc_18020D393
0x18020d35b  lea     rcx, [rdi+28h]
0x18020d35f  call    ?SetWindowBand@CSingleViewShellExperience@@QEAAJW4ZBID@@@Z; CSingleViewShellExperience::SetWindowBand(ZBID)
0x18020d364  mov     ebx, eax
0x18020d366  test    eax, eax
0x18020d368  jns     short loc_18020D393
0x18020d36a  mov     rcx, [rbp+5Fh]; this
0x18020d36e  mov     r9d, eax; char *
0x18020d371  lea     r8, aShellTwinuiExp_9; "shell\\twinui\\experiencemanagers\\lib"...
0x18020d378  mov     edx, 487h; void *
0x18020d37d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020d382  nop
0x18020d383  lea     rcx, [rbp+57h+var_98]
0x18020d387  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18020d38c  mov     eax, ebx
0x18020d38e  jmp     loc_18020DC89
0x18020d393  jmp     loc_18020DC7E
0x18020d398  lea     rdx, off_1803F99D0; "HideBlur"
0x18020d39f  lea     rcx, [rbp+57h+hstringHeader]
0x18020d3a3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d3a8  mov     rdx, [rax+18h]; HSTRING
0x18020d3ac  mov     rcx, rbx; this
0x18020d3af  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020d3b4  test    eax, eax
0x18020d3b6  jnz     short loc_18020D3BC
0x18020d3b8  xor     edx, edx
0x18020d3ba  jmp     short loc_18020D3DF
0x18020d3bc  lea     rdx, off_1803F99D8; "ShowBlur"
0x18020d3c3  lea     rcx, [rbp+57h+hstringHeader]
0x18020d3c7  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d3cc  mov     rdx, [rax+18h]; HSTRING
0x18020d3d0  mov     rcx, rbx; this
0x18020d3d3  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020d3d8  test    eax, eax
0x18020d3da  jnz     short loc_18020D3ED
0x18020d3dc  lea     edx, [rax+1]; int
0x18020d3df  lea     rcx, [rdi-68h]; this
0x18020d3e3  call    ?SetBorderAccent@CPenWorkspaceExperienceManager@@AEAAJH@Z; CPenWorkspaceExperienceManager::SetBorderAccent(int)
0x18020d3e8  jmp     loc_18020DC87
0x18020d3ed  lea     rdx, off_1803F9940; "ShowRemember"
0x18020d3f4  lea     rcx, [rbp+57h+hstringHeader]
0x18020d3f8  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d3fd  mov     rdx, [rax+18h]; HSTRING
0x18020d401  mov     rcx, rbx; this
0x18020d404  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020d409  test    eax, eax
0x18020d40b  jnz     short loc_18020D43D
0x18020d40d  lea     rcx, [rdi-68h]; this
0x18020d411  call    ?ShowRemember@CPenWorkspaceExperienceManager@@AEAAJXZ; CPenWorkspaceExperienceManager::ShowRemember(void)
0x18020d416  mov     ebx, eax
0x18020d418  test    eax, eax
0x18020d41a  jns     loc_18020D38C
0x18020d420  mov     edx, 495h; void *
0x18020d425  mov     rcx, [rbp+5Fh]; this
0x18020d429  mov     r9d, ebx; char *
0x18020d42c  lea     r8, aShellTwinuiExp_9; "shell\\twinui\\experiencemanagers\\lib"...
0x18020d433  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18020d438  jmp     loc_18020D38C
0x18020d43d  lea     rdx, off_1803F9948; "HideRemember"
0x18020d444  lea     rcx, [rbp+57h+hstringHeader]
0x18020d448  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d44d  mov     rdx, [rax+18h]; HSTRING
0x18020d451  mov     rcx, rbx; this
0x18020d454  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020d459  test    eax, eax
0x18020d45b  jnz     short loc_18020D477
0x18020d45d  lea     rcx, [rdi-68h]; this
0x18020d461  call    ?HideRemember@CPenWorkspaceExperienceManager@@AEAAJXZ; CPenWorkspaceExperienceManager::HideRemember(void)
0x18020d466  mov     ebx, eax
0x18020d468  test    eax, eax
0x18020d46a  jns     loc_18020D38C
0x18020d470  mov     edx, 499h
0x18020d475  jmp     short loc_18020D425
0x18020d477  lea     rdx, off_1803F9950; "SizeWindowForHome"
0x18020d47e  lea     rcx, [rbp+57h+hstringHeader]
0x18020d482  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d487  mov     rdx, [rax+18h]; HSTRING
0x18020d48b  mov     rcx, rbx; this
0x18020d48e  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020d493  test    eax, eax
0x18020d495  jnz     short loc_18020D4B4
0x18020d497  lea     rcx, [rdi-68h]; this
0x18020d49b  call    ?SizeWindowForHome@CPenWorkspaceExperienceManager@@AEAAJXZ; CPenWorkspaceExperienceManager::SizeWindowForHome(void)
0x18020d4a0  mov     ebx, eax
0x18020d4a2  test    eax, eax
0x18020d4a4  jns     loc_18020D38C
0x18020d4aa  mov     edx, 49Dh
0x18020d4af  jmp     loc_18020D425
0x18020d4b4  lea     rdx, off_1803F9958; "ShowExperienceFromUri"
0x18020d4bb  lea     rcx, [rbp+57h+hstringHeader]
0x18020d4bf  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d4c4  mov     rdx, [rax+18h]; HSTRING
0x18020d4c8  mov     rcx, rbx; this
0x18020d4cb  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020d4d0  test    eax, eax
0x18020d4d2  jnz     short loc_18020D4F1
0x18020d4d4  lea     rcx, [rdi-68h]; this
0x18020d4d8  call    ?ShowExperienceView@CPenWorkspaceExperienceManager@@AEAAJXZ; CPenWorkspaceExperienceManager::ShowExperienceView(void)
0x18020d4dd  mov     ebx, eax
0x18020d4df  test    eax, eax
0x18020d4e1  jns     loc_18020DC87
0x18020d4e7  mov     edx, 4A2h
0x18020d4ec  jmp     loc_18020D425
0x18020d4f1  lea     rdx, off_1803F9960; "CloseUI"
0x18020d4f8  lea     rcx, [rbp+57h+hstringHeader]
0x18020d4fc  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d501  mov     rdx, [rax+18h]; HSTRING
0x18020d505  mov     rcx, rbx; this
0x18020d508  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020d50d  test    eax, eax
0x18020d50f  jnz     short loc_18020D52E
0x18020d511  lea     rcx, [rdi-68h]; this
0x18020d515  call    ?CloseUI@CPenWorkspaceExperienceManager@@AEAAJXZ; CPenWorkspaceExperienceManager::CloseUI(void)
0x18020d51a  mov     ebx, eax
0x18020d51c  test    eax, eax
0x18020d51e  jns     loc_18020D38C
0x18020d524  mov     edx, 4A6h
0x18020d529  jmp     loc_18020D425
0x18020d52e  lea     rdx, off_1803F9968; "GiveFocusToNotes"
0x18020d535  lea     rcx, [rbp+57h+hstringHeader]
0x18020d539  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d53e  mov     rdx, [rax+18h]; HSTRING
0x18020d542  mov     rcx, rbx; this
0x18020d545  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020d54a  test    eax, eax
0x18020d54c  jnz     short loc_18020D57C
0x18020d54e  mov     rcx, [rdi+190h]
0x18020d555  test    rcx, rcx
0x18020d558  jnz     short loc_18020D569
0x18020d55a  mov     ebx, 8000FFFFh
0x18020d55f  mov     edx, 4AAh
0x18020d564  jmp     loc_18020D425
0x18020d569  mov     rax, [rcx]
0x18020d56c  mov     rax, [rax+48h]
0x18020d570  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18020d575  mov     esi, eax
0x18020d577  jmp     loc_18020DC87
0x18020d57c  lea     rdx, off_1803F9970; "RequestUnlock"
0x18020d583  lea     rcx, [rbp+57h+hstringHeader]
0x18020d587  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18020d58c  mov     rdx, [rax+18h]; HSTRING
0x18020d590  mov     rcx, rbx; this
0x18020d593  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x18020d598  test    eax, eax
0x18020d59a  jnz     loc_18020D670
0x18020d5a0  lea     r14, [rdi-68h]
0x18020d5a4  cmp     [r14+1B8h], r12b
0x18020d5ab  jz      loc_18020DC87
0x18020d5b1  mov     [rbp+57h+var_98], r12
0x18020d5b5  mov     [rbp+57h+string], r12
0x18020d5b9  lea     rcx, [rbp+57h+var_98]
0x18020d5bd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18020d5c2  lea     rcx, [rbp+57h+var_98]; struct ILockAppHost **
0x18020d5c6  call    ?GetLockAppHost@@YAJPEAPEAUILockAppHost@@@Z; GetLockAppHost(ILockAppHost * *)
0x18020d5cb  mov     ebx, eax
0x18020d5cd  test    eax, eax
0x18020d5cf  jns     short loc_18020D5D8
0x18020d5d1  mov     edx, 4B4h
0x18020d5d6  jmp     short loc_18020D62C
0x18020d5d8  mov     rbx, [rbp+57h+var_98]
0x18020d5dc  mov     rax, [rbx]
0x18020d5df  mov     rdi, [rax]
  ... truncated ...
```
