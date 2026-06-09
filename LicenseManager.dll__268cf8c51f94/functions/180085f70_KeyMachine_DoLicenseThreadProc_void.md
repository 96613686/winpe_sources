# KeyMachine::DoLicenseThreadProc(void *)

- ea: `0x180085f70`
- end: `0x180086e4e`
- name: `?DoLicenseThreadProc@KeyMachine@@KAKPEAX@Z`
- size: `3806`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000138c`
- `0x180001dd0`
- `0x180004738`
- `0x18000b7fc`
- `0x180013b50`
- `0x18001bcb8`
- `0x18001dad0`
- `0x18002aae8`
- `0x1800377b0`
- `0x18003ae24`
- `0x18003b3d4`
- `0x18003ccd0`
- `0x180045030`
- `0x180046f88`
- `0x1800593bc`
- `0x180068af0`
- `0x180075e60`
- `0x180085f70`
- `0x1800b8010`

## import_xrefs

- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x180086157`
- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x18008641e`
- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x180086a02`
- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x180086157`
- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x18008641e`
- `ext-ms-win-xblauth-console-l1-1-0!XblaIsConsole` at `0x180086a02`

## string_xrefs

- `0x180086241`: `KeyMachine::DoLicenseThreadProc`
- `0x180086384`: `KeyMachine::DoLicenseThreadProc`
- `0x1800863fb`: `KeyMachine::DoLicenseThreadProc`
- `0x1800864f2`: `KeyMachine::DoLicenseThreadProc`
- `0x18008652b`: `KeyMachine::DoLicenseThreadProc`
- `0x180086566`: `KeyMachine::DoLicenseThreadProc`
- `0x1800866f8`: `KeyMachine::DoLicenseThreadProc`
- `0x1800867d3`: `KeyMachine::DoLicenseThreadProc`
- `0x1800868a2`: `KeyMachine::DoLicenseThreadProc`
- `0x180086aa4`: `KeyMachine::DoLicenseThreadProc`
- `0x180086b77`: `KeyMachine::DoLicenseThreadProc`
- `0x180086be9`: `KeyMachine::DoLicenseThreadProc`
- `0x18008651f`: `content is alreadyLicensed, lease is cached`
- `0x18008655a`: `content is alreadyLicensed, cached lease not available but it is not required`
- `0x180086bdd`: `Returning client error 0x%08x in place of service error 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall KeyMachine::DoLicenseThreadProc(_DWORD *Parameter)
{
  int v2; // r12d
  _QWORD *v3; // r15
  __int64 v4; // rbx
  __int64 v5; // rdi
  unsigned __int8 HasLicenseExpired; // r13
  unsigned int v7; // r14d
  __int64 v8; // r15
  void (__fastcall *v9)(__int64, _QWORD *, __int64 *, __int64 *); // r12
  _QWORD *v10; // rbx
  _QWORD *v11; // rdx
  int v12; // eax
  bool v13; // zf
  int v14; // eax
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  _QWORD *v18; // rax
  int v19; // eax
  __int64 *v20; // rcx
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rax
  int v24; // eax
  wil *v25; // rcx
  __int64 *v26; // rcx
  int v27; // eax
  __int64 v28; // rax
  __int64 v29; // rax
  int v30; // eax
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  int v34; // ecx
  int v35; // r8d
  int v36; // r9d
  _QWORD *v37; // r12
  void (__fastcall *v38)(_QWORD *, _QWORD, _QWORD, __int64 *, __int64 *, __int64 **, __int64 *, int *); // rbx
  int v39; // eax
  int v40; // eax
  char v41; // al
  int v42; // eax
  int v43; // eax
  char v44; // bl
  int v45; // eax
  wil::details::in1diag3 *v46; // rcx
  int v47; // eax
  int v48; // eax
  _QWORD *v49; // r12
  unsigned int v50; // eax
  __int64 v51; // rdx
  const char *v53; // r9
  __int64 v54; // rcx
  int Format; // [rsp+20h] [rbp-168h]
  int Formata; // [rsp+20h] [rbp-168h]
  __int64 v57; // [rsp+28h] [rbp-160h]
  __int64 **v58; // [rsp+30h] [rbp-158h]
  __int64 v59; // [rsp+30h] [rbp-158h]
  unsigned __int8 v60; // [rsp+60h] [rbp-128h]
  char v61; // [rsp+61h] [rbp-127h]
  int v62; // [rsp+64h] [rbp-124h] BYREF
  char v63; // [rsp+68h] [rbp-120h]
  int v64; // [rsp+6Ch] [rbp-11Ch] BYREF
  int v65[2]; // [rsp+70h] [rbp-118h] BYREF
  char v66; // [rsp+78h] [rbp-110h]
  int v67; // [rsp+7Ch] [rbp-10Ch] BYREF
  __int64 *v68; // [rsp+80h] [rbp-108h] BYREF
  int v69; // [rsp+88h] [rbp-100h] BYREF
  int v70; // [rsp+8Ch] [rbp-FCh] BYREF
  int v71; // [rsp+90h] [rbp-F8h]
  int v72; // [rsp+94h] [rbp-F4h] BYREF
  __int64 v73; // [rsp+98h] [rbp-F0h] BYREF
  __int64 v74; // [rsp+A0h] [rbp-E8h] BYREF
  int v75; // [rsp+A8h] [rbp-E0h] BYREF
  _QWORD *v76; // [rsp+B0h] [rbp-D8h] BYREF
  __int64 v77; // [rsp+B8h] [rbp-D0h] BYREF
  __int64 v78; // [rsp+C0h] [rbp-C8h] BYREF
  __int64 v79; // [rsp+C8h] [rbp-C0h] BYREF
  int v80; // [rsp+D0h] [rbp-B8h] BYREF
  char v81; // [rsp+D4h] [rbp-B4h]
  unsigned int v82; // [rsp+D8h] [rbp-B0h]
  __int64 v83; // [rsp+E0h] [rbp-A8h] BYREF
  __int64 v84; // [rsp+E8h] [rbp-A0h] BYREF
  __int64 *v85; // [rsp+F0h] [rbp-98h] BYREF
  _DWORD *v86; // [rsp+F8h] [rbp-90h] BYREF
  _BYTE v87[56]; // [rsp+100h] [rbp-88h] BYREF
  __int64 v88; // [rsp+138h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v86 = Parameter;
  v2 = *Parameter;
  v71 = v2;
  v75 = v2;
  v62 = Parameter[1];
  v61 = *((_BYTE *)Parameter + 8);
  v63 = *((_BYTE *)Parameter + 9);
  v3 = (_QWORD *)*((_QWORD *)Parameter + 3);
  v76 = v3;
  Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(&v76);
  v77 = *((_QWORD *)Parameter + 2);
  Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(&v77);
  v4 = *((_QWORD *)Parameter + 4);
  v79 = v4;
  Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(&v79);
  v5 = *((_QWORD *)Parameter + 5);
  v78 = v5;
  Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(&v78);
  try
  {
    v73 = 0;
    v68 = 0;
    v66 = 0;
    HasLicenseExpired = 0;
    v60 = 0;
    v7 = 0;
    v67 = 1;
    if ( v2 != 5 )
    {
      v8 = v3[20];
      v9 = *(void (__fastcall **)(__int64, _QWORD *, __int64 *, __int64 *))(*(_QWORD *)v8 + 48LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v68);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v73);
      *(_QWORD *)v65 = v5;
      Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(v65);
      v74 = v4;
      Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(&v74);
      v10 = v76 + 21;
      if ( v76[24] <= 7u )
        v11 = v76 + 21;
      else
        v11 = (_QWORD *)*v10;
      v58 = &v68;
      v9(v8, v11, &v77, &v74);
      if ( !v73 )
      {
        if ( v61
          && !v63
          && (unsigned int)dword_1800F11D0 > 5
          && (unsigned __int8)tlgKeywordOn(&dword_1800F11D0, 0x200000000000LL) )
        {
          if ( v10[3] > 7u )
            v10 = (_QWORD *)*v10;
          *(_QWORD *)v65 = v10;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v34,
            (unsigned int)byte_1800D6C0B,
            v35,
            v36,
            (__int64)v65);
        }
        goto LABEL_67;
      }
      v64 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v73 + 48LL))(v73, &v64, &v67);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x37F,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
          (const char *)(unsigned int)v12,
          (int)v65);
      if ( v64 != 2130706432 )
      {
        v13 = (unsigned int)XblaIsConsole(retaddr) == 0;
        v14 = v64;
        if ( (v13 || v64 < 2130706432) && (v63 || v64 <= 0x10000000) )
        {
          if ( v61 && !v63 )
          {
            if ( (unsigned int)dword_1800F11D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800F11D0, 0x200000000000LL) )
            {
              v70 = v67;
              v72 = v64;
              if ( v10[3] <= 7u )
                v18 = v10;
              else
                v18 = (_QWORD *)*v10;
              *(_QWORD *)v65 = v18;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v15,
                (unsigned int)&unk_1800D6C50,
                v16,
                v17,
                (__int64)v65,
                (__int64)&v72,
                (__int64)&v70);
            }
            v14 = v64;
          }
          if ( v10[3] > 7u )
            v10 = (_QWORD *)*v10;
          LODWORD(v58) = v14;
          LogMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
            0x405u,
            "KeyMachine::DoLicenseThreadProc",
            (wchar_t *)L"Replacing key for %s of quality %x (0x%08x)",
            v10,
            v58,
            v67);
          goto LABEL_67;
        }
      }
      v69 = 0;
      v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v73 + 112LL))(v73, (unsigned int)v62, &v69);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x38D,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
          (const char *)(unsigned int)v19,
          (int)v65);
      v72 = 0;
      v20 = v68;
      if ( v68 )
      {
        HasLicenseExpired = KeyMachine::HasLicenseExpired(v68, &v73, &v68);
        v60 = HasLicenseExpired;
        v21 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v68 + 88))(v68, &v72);
        if ( v21 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x393,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
            (const char *)(unsigned int)v21,
            (int)v65);
        v20 = v68;
      }
      v22 = 0;
      *(_QWORD *)v65 = 0;
      if ( v20 )
      {
        v23 = *v20;
        *(_QWORD *)v65 = 0;
        v24 = (*(__int64 (__fastcall **)(__int64 *, int *))(v23 + 24))(v20, v65);
        if ( v24 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x39B,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
            (const char *)(unsigned int)v24,
            (int)v65);
        v22 = *(_QWORD *)v65;
      }
      LODWORD(v58) = v62;
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        0x3A3u,
        "KeyMachine::DoLicenseThreadProc",
        (wchar_t *)L"lease = %s, usage = %d, policy = %d, operation = %d, leaseBehavior = %d, shouldContentBeDeactivated = %d",
        v22,
        v58,
        v69,
        v71,
        v72,
        HasLicenseExpired);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v65);
      if ( v69 < 4 )
      {
        if ( !v69 || v69 < 2 && v71 > 2 && (unsigned int)(v72 - 2) <= 1 )
        {
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v68);
          LogMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
            0x3BCu,
            "KeyMachine::DoLicenseThreadProc",
            (wchar_t *)L"reset lease as Key cannot ever have a lease or it doesn't want a lease when activated");
        }
        if ( !v61 && (!(unsigned int)XblaIsConsole(v25) || v64 <= 2130706432) )
          goto LABEL_67;
LABEL_54:
        v66 = 1;
        goto LABEL_144;
      }
      if ( v61 )
      {
        LODWORD(v74) = 1;
        v70 = 0x10000000;
        v26 = v68;
        if ( v68 )
        {
          v27 = (*(__int64 (__fastcall **)(__int64 *, int *, __int64 *))(*v68 + 48))(v68, &v70, &v74);
          if ( v27 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x3C9,
              (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
              (const char *)(unsigned int)v27,
              Format);
          v26 = v68;
        }
        v28 = 0;
        *(_QWORD *)v65 = 0;
        if ( v26 )
        {
          v29 = *v26;
          *(_QWORD *)v65 = 0;
          v30 = (*(__int64 (__fastcall **)(__int64 *, int *))(v29 + 24))(v26, v65);
          if ( v30 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x3D1,
              (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
              (const char *)(unsigned int)v30,
              Format);
          v28 = *(_QWORD *)v65;
        }
        LODWORD(v59) = v70;
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
          0x3D3u,
          "KeyMachine::DoLicenseThreadProc",
          (wchar_t *)L"lease = %s, quality = %d",
          v28,
          v59);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v65);
        if ( v70 > 0x10000000 )
        {
          LogMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
            0x3DFu,
            "KeyMachine::DoLicenseThreadProc",
            (wchar_t *)L"content is alreadyLicensed, lease is cached");
          goto LABEL_54;
        }
        if ( !v63 )
        {
          if ( (v69 & 0x10) != 0 )
          {
            if ( (unsigned int)dword_1800F11D0 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800F11D0, 0x200000000000LL) )
            {
              if ( v10[3] > 7u )
                v10 = (_QWORD *)*v10;
              *(_QWORD *)v65 = v10;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
                v31,
                (unsigned int)byte_1800D6CAD,
                v32,
                v33,
                (__int64)v65);
            }
            goto LABEL_67;
          }
          LogMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
            0x3E7u,
            "KeyMachine::DoLicenseThreadProc",
            (wchar_t *)L"content is alreadyLicensed, cached lease not available but it is not required");
          goto LABEL_54;
        }
      }
    }
LABEL_67:
    v74 = 0;
    *(_QWORD *)v65 = 0;
    v37 = v76;
    v38 = *(void (__fastcall **)(_QWORD *, _QWORD, _QWORD, __int64 *, __int64 *, __int64 **, __int64 *, int *))(*v76 + 72LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v65);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v74);
    v38(v37, (unsigned int)v71, (unsigned int)v62, &v77, &v73, &v68, &v74, v65);
    Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(&v73, &v74);
    Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(&v68, v65);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
      0x427u,
      "KeyMachine::DoLicenseThreadProc",
      (wchar_t *)L"Replacing invalid key and lease with new ones");
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v65);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v74);
  }
  catch ( ... )
  {
    v64 = wil::ResultFromCaughtException(v25);
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x42D,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
      v53);
    v7 = v64;
    if ( v64 < 0 && v73 )
    {
      v70 = 0;
      LODWORD(v74) = 0;
      HasLicenseExpired = (v64 & 0xF000) == 0x8000 && (v64 & 0x1FFF0000) == 0x3F0000
                       || (v64 & 0x1FFF0000) == 0x7DE0000
                       || (unsigned __int8)KeyMachine::HasLicenseExpired(v54, &v73, &v68) && IsNetworkFailure(v7);
      LogMessage(
        3u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
        0x437u,
        "KeyMachine::DoLicenseThreadProc",
        (wchar_t *)L"Failed with error hr = 0x%08x, shouldContentBeDeactivated = %d");
      v39 = (*(__int64 (__fastcall **)(__int64, int *, __int64 *))(*(_QWORD *)v73 + 48LL))(v73, &v70, &v74);
      if ( v39 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x439,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
          (const char *)(unsigned int)v39,
          Formata);
      if ( v70 > 0x10000000 )
      {
        v69 = 0;
        v40 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v73 + 112LL))(v73, (unsigned int)v62, &v69);
        if ( v40 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x43D,
            (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
            (const char *)(unsigned int)v40,
            Formata);
        v41 = v69;
        if ( v69 >= 8 )
        {
          if ( v68 )
          {
            v65[0] = 0;
            v72 = 0;
            v42 = (*(__int64 (__fastcall **)(__int64 *, int *, int *))(*v68 + 48))(v68, v65, &v72);
            if ( v42 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x44E,
                (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
                (const char *)(unsigned int)v42,
                Formata);
            if ( v70 > 0x10000000 && !HasLicenseExpired )
            {
              v62 = 0;
              v43 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v68 + 88))(v68, &v62);
              if ( v43 < 0 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x452,
                  (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
                  (const char *)(unsigned int)v43,
                  Formata);
              if ( v62 < 3 )
              {
                LODWORD(v59) = v7;
                LODWORD(v57) = v62;
                LogMessage(
                  3u,
                  "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
                  0x455u,
                  "KeyMachine::DoLicenseThreadProc",
                  L"Ignoring leasing error for offline lease with behavior %x: hr = 0x%08x",
                  v57,
                  v59);
                goto LABEL_108;
              }
            }
            v41 = v69;
          }
        }
        else if ( !HasLicenseExpired )
        {
          LODWORD(v59) = v7;
          LODWORD(v57) = v69;
          LogMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
            0x445u,
            "KeyMachine::DoLicenseThreadProc",
            (wchar_t *)L"Ignoring leasing error for valid key with policy %x: hr = 0x%08x",
            v57,
            v59);
LABEL_108:
          v7 = 0;
          v64 = 0;
          goto LABEL_144;
        }
        v44 = 0;
        if ( (v41 & 8) != 0 && v67 >= 0 && IsNetworkFailure(v7) )
        {
          v62 = 0;
          if ( v68 )
          {
            v45 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v68 + 120))(v68, &v62);
            v46 = retaddr;
            if ( v45 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x467,
                (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
                (const char *)(unsigned int)v45,
                Formata);
          }
          else
          {
            v47 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v73 + 144LL))(v73, &v62);
            v46 = retaddr;
            if ( v47 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x46B,
                (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
                (const char *)(unsigned int)v47,
                Formata);
          }
          v7 = (v62 != 0) - 2143318008;
          v64 = v7;
          if ( (unsigned int)XblaIsConsole(v46) )
          {
            v44 = 1;
            HasLicenseExpired = 1;
          }
        }
        if ( v75 == 4 && v68 && !v44 && (!HasLicenseExpired || v7 + 2143318008 <= 1) )
        {
          v62 = 0;
          v75 = 0;
          v48 = (*(__int64 (__fastcall **)(__int64 *, int *, int *))(*v68 + 48))(v68, &v62, &v75);
          if ( v48 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x481,
              (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
              (const char *)(unsigned int)v48,
              Formata);
          if ( v62 > 0x10000000 )
          {
            LODWORD(v59) = v7;
            LODWORD(v57) = v62;
            LogMessage(
              3u,
              "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
              0x485u,
              "KeyMachine::DoLicenseThreadProc",
              (wchar_t *)L"Ignoring leasing error for valid key with existing lease of quality %x: hr = 0x%08x",
              v57,
              v59);
            goto LABEL_108;
          }
        }
      }
    }
    else
    {
      HasLicenseExpired = v60;
    }
  }
LABEL_144:
  v49 = v76;
  if ( HasLicenseExpired )
  {
    v75 = 0;
    v62 = 0;
    if ( v68 )
    {
      if ( (*(int (__fastcall **)(__int64 *, int *, int *))(*v68 + 48))(v68, &v75, &v62) >= 0
        && (v62 >= 0 || (v62 & 0xF000) == 0x8000 && (v62 & 0x1FFF0000) == 0x3F0000) )
      {
        v50 = v7;
        if ( v67 < 0 )
          v50 = v67;
        LODWORD(v57) = v50;
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
          0x49Cu,
          "KeyMachine::DoLicenseThreadProc",
          (wchar_t *)L"Invalidating lease with reason hr = 0x%08x",
          v57);
        v51 = v7;
        if ( v67 < 0 )
          v51 = (unsigned int)v67;
        (*(void (__fastcall **)(__int64 *, __int64))(*v68 + 160))(v68, v51);
      }
    }
  }
  if ( v67 < 0 && (v7 + 2143322111 <= 0x62 || IsNetworkFailure(v7)) )
  {
    LODWORD(v59) = v7;
    LODWORD(v57) = v67;
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\keymachine.cpp",
      0x4AAu,
      "KeyMachine::DoLicenseThreadProc",
      (wchar_t *)L"Returning client error 0x%08x in place of service error 0x%08x",
      v57,
      v59);
    v7 = v67;
  }
  v80 = v71;
  v81 = v66;
  v82 = v7;
  v83 = v77;
  Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(&v83);
  v84 = v73;
  Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(&v84);
  v85 = v68;
  Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(&v85);
  v88 = 0;
  v88 = std::_Func_impl_no_alloc<_lambda_4be6cc26683cc743ae703b10b755c444_,void,KeyMachine &>::_Func_impl_no_alloc<_lambda_4be6cc26683cc743ae703b10b755c444_,void,KeyMachine &>(
          v87,
          &v80);
  StateMachine<KeyMachine,KeyState>::Enqueue(v49 + 4);
  std::_Func_class<void,RootMachine &>::~_Func_class<void,RootMachine &>(v87);
  _lambda_4be6cc26683cc743ae703b10b755c444_::~_lambda_4be6cc26683cc743ae703b10b755c444_((_lambda_4be6cc26683cc743ae703b10b755c444_ *)&v80);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v68);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v73);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v78);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v79);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v77);
  if ( v49 )
    (*(void (__fastcall **)(_QWORD *))(*v49 + 16LL))(v49);
  std::unique_ptr<KeyMachine::BeginLicenseParams>::~unique_ptr<KeyMachine::BeginLicenseParams>(&v86);
  return 0;
}

```

## disassembly

```asm
0x180085f70  push    rbx
0x180085f72  push    rsi
0x180085f73  push    rdi
0x180085f74  push    r12
0x180085f76  push    r13
0x180085f78  push    r14
0x180085f7a  push    r15
0x180085f7c  sub     rsp, 150h
0x180085f83  mov     rax, cs:__security_cookie
0x180085f8a  xor     rax, rsp
0x180085f8d  mov     [rsp+188h+var_48], rax
0x180085f95  mov     rdi, rcx
0x180085f98  mov     [rsp+188h+var_90], rcx
0x180085fa0  mov     r12d, [rcx]
0x180085fa3  mov     [rsp+188h+var_F8], r12d
0x180085fab  mov     [rsp+188h+var_E0], r12d
0x180085fb3  mov     eax, [rcx+4]
0x180085fb6  mov     [rsp+188h+var_124], eax
0x180085fba  mov     al, [rcx+8]
0x180085fbd  mov     [rsp+188h+var_127], al
0x180085fc1  mov     al, [rcx+9]
0x180085fc4  mov     [rsp+188h+var_120], al
0x180085fc8  mov     r15, [rcx+18h]
0x180085fcc  mov     [rsp+188h+var_D8], r15
0x180085fd4  lea     rcx, [rsp+188h+var_D8]
0x180085fdc  call    ?InternalAddRef@?$ComPtr@VClipKeyDocument@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(void)
0x180085fe1  nop
0x180085fe2  mov     rax, [rdi+10h]
0x180085fe6  mov     [rsp+188h+var_D0], rax
0x180085fee  lea     rcx, [rsp+188h+var_D0]
0x180085ff6  call    ?InternalAddRef@?$ComPtr@VClipKeyDocument@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(void)
0x180085ffb  nop
0x180085ffc  mov     rbx, [rdi+20h]
0x180086000  mov     [rsp+188h+var_C0], rbx
0x180086008  lea     rcx, [rsp+188h+var_C0]
0x180086010  call    ?InternalAddRef@?$ComPtr@VClipKeyDocument@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(void)
0x180086015  nop
0x180086016  mov     rdi, [rdi+28h]
0x18008601a  mov     [rsp+188h+var_C8], rdi
0x180086022  lea     rcx, [rsp+188h+var_C8]
0x18008602a  call    ?InternalAddRef@?$ComPtr@VClipKeyDocument@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(void)
0x18008602f  nop
0x180086030  xor     esi, esi
0x180086032  mov     [rsp+188h+var_F0], rsi
0x18008603a  mov     [rsp+188h+var_108], rsi
0x180086042  mov     [rsp+188h+var_110], sil
0x180086047  mov     r13b, sil
0x18008604a  mov     [rsp+188h+var_128], sil
0x18008604f  mov     r14d, esi
0x180086052  mov     [rsp+188h+var_10C], 1
0x18008605a  cmp     r12d, 5
0x18008605e  jz      loc_180086634
0x180086064  mov     r15, [r15+0A0h]
0x18008606b  mov     rax, [r15]
0x18008606e  mov     r12, [rax+30h]
0x180086072  lea     rcx, [rsp+188h+var_108]
0x18008607a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008607f  lea     rcx, [rsp+188h+var_F0]
0x180086087  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18008608c  mov     qword ptr [rsp+188h+var_118], rdi
0x180086091  lea     rcx, [rsp+188h+var_118]
0x180086096  call    ?InternalAddRef@?$ComPtr@VClipKeyDocument@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(void)
0x18008609b  mov     [rsp+188h+var_E8], rbx
0x1800860a3  lea     rcx, [rsp+188h+var_E8]
0x1800860ab  call    ?InternalAddRef@?$ComPtr@VClipKeyDocument@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(void)
0x1800860b0  mov     rbx, [rsp+188h+var_D8]
0x1800860b8  add     rbx, 0A8h
0x1800860bf  cmp     qword ptr [rbx+18h], 7
0x1800860c4  jbe     short loc_1800860CB
0x1800860c6  mov     rdx, [rbx]
0x1800860c9  jmp     short loc_1800860CE
0x1800860cb  mov     rdx, rbx
0x1800860ce  lea     rax, [rsp+188h+var_108]
0x1800860d6  mov     [rsp+188h+var_158], rax
0x1800860db  lea     rax, [rsp+188h+var_F0]
0x1800860e3  mov     [rsp+188h+var_160], rax
0x1800860e8  lea     rax, [rsp+188h+var_118]
0x1800860ed  mov     [rsp+188h+Format], rax; int
0x1800860f2  lea     r9, [rsp+188h+var_E8]
0x1800860fa  lea     r8, [rsp+188h+var_D0]
0x180086102  mov     rcx, r15
0x180086105  mov     rax, r12
0x180086108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008610d  mov     rcx, [rsp+188h+var_F0]
0x180086115  test    rcx, rcx
0x180086118  jz      loc_1800865DC
0x18008611e  mov     [rsp+188h+var_11C], esi
0x180086122  mov     rax, [rcx]
0x180086125  lea     r8, [rsp+188h+var_10C]
0x18008612a  lea     rdx, [rsp+188h+var_11C]
0x18008612f  mov     rax, [rax+30h]
0x180086133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086138  mov     rcx, [rsp+188h]; this
0x180086140  test    eax, eax
0x180086142  js      loc_180086D68
0x180086148  mov     edi, 7F000000h
0x18008614d  cmp     [rsp+188h+var_11C], edi
0x180086151  jz      loc_18008626B
0x180086157  call    cs:__imp_XblaIsConsole
0x18008615d  test    eax, eax
0x18008615f  mov     eax, [rsp+188h+var_11C]
0x180086163  jz      short loc_18008616D
0x180086165  cmp     eax, edi
0x180086167  jge     loc_18008626B
0x18008616d  mov     cl, [rsp+188h+var_120]
0x180086171  test    cl, cl
0x180086173  jnz     short loc_180086184
0x180086175  mov     r12d, 10000000h
0x18008617b  cmp     eax, r12d
0x18008617e  jg      loc_180086271
0x180086184  cmp     [rsp+188h+var_127], sil
0x180086189  jz      loc_18008621A
0x18008618f  test    cl, cl
0x180086191  jnz     loc_18008621A
0x180086197  mov     eax, cs:dword_1800F11D0
0x18008619d  cmp     eax, 5
0x1800861a0  jbe     short loc_180086216
0x1800861a2  mov     rdx, 200000000000h
0x1800861ac  lea     rcx, dword_1800F11D0
0x1800861b3  call    _tlgKeywordOn
0x1800861b8  test    al, al
0x1800861ba  jz      short loc_180086216
0x1800861bc  mov     eax, [rsp+188h+var_10C]
0x1800861c0  mov     [rsp+188h+var_FC], eax
0x1800861c7  mov     eax, [rsp+188h+var_11C]
0x1800861cb  mov     [rsp+188h+var_F4], eax
0x1800861d2  cmp     qword ptr [rbx+18h], 7
0x1800861d7  jbe     short loc_1800861DE
0x1800861d9  mov     rax, [rbx]
0x1800861dc  jmp     short loc_1800861E1
0x1800861de  mov     rax, rbx
0x1800861e1  mov     qword ptr [rsp+188h+var_118], rax
0x1800861e6  lea     rax, [rsp+188h+var_FC]
0x1800861ee  mov     [rsp+188h+var_158], rax
0x1800861f3  lea     rax, [rsp+188h+var_F4]
0x1800861fb  mov     [rsp+188h+var_160], rax
0x180086200  lea     rax, [rsp+188h+var_118]
0x180086205  mov     [rsp+188h+Format], rax
0x18008620a  lea     rdx, unk_1800D6C50
0x180086211  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180086216  mov     eax, [rsp+188h+var_11C]
0x18008621a  mov     ecx, [rsp+188h+var_10C]
0x18008621e  cmp     qword ptr [rbx+18h], 7
0x180086223  jbe     short loc_180086228
0x180086225  mov     rbx, [rbx]
0x180086228  mov     dword ptr [rsp+188h+var_150], ecx
0x18008622c  mov     dword ptr [rsp+188h+var_158], eax
0x180086230  mov     [rsp+188h+var_160], rbx
0x180086235  lea     rax, aReplacingKeyFo; "Replacing key for %s of quality %x (0x%"...
0x18008623c  mov     [rsp+188h+Format], rax; Format
0x180086241  lea     r9, aKeymachineDoli; "KeyMachine::DoLicenseThreadProc"
0x180086248  mov     r8d, 405h; unsigned int
0x18008624e  lea     rdi, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x180086255  mov     rdx, rdi; char *
0x180086258  mov     r15d, 3
0x18008625e  mov     ecx, r15d; unsigned int
0x180086261  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180086266  jmp     loc_180086641
0x18008626b  mov     r12d, 10000000h
0x180086271  mov     [rsp+188h+var_100], esi
0x180086278  mov     rcx, [rsp+188h+var_F0]
0x180086280  mov     rax, [rcx]
0x180086283  lea     r8, [rsp+188h+var_100]
0x18008628b  mov     edi, [rsp+188h+var_124]
0x18008628f  mov     edx, edi
0x180086291  mov     rax, [rax+70h]
0x180086295  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008629a  mov     rcx, [rsp+188h]; this
0x1800862a2  test    eax, eax
0x1800862a4  js      loc_180086D7C
0x1800862aa  mov     [rsp+188h+var_F4], esi
0x1800862b1  mov     rcx, [rsp+188h+var_108]
0x1800862b9  test    rcx, rcx
0x1800862bc  jz      short loc_18008630E
0x1800862be  lea     r8, [rsp+188h+var_108]
0x1800862c6  lea     rdx, [rsp+188h+var_F0]
0x1800862ce  call    ?HasLicenseExpired@KeyMachine@@IEAA_NAEBV?$ComPtr@UIStoredKeyDocument@@@WRL@Microsoft@@AEBV?$ComPtr@UIStoredLeaseDocument@@@34@@Z; KeyMachine::HasLicenseExpired(Microsoft::WRL::ComPtr<IStoredKeyDocument> const &,Microsoft::WRL::ComPtr<IStoredLeaseDocument> const &)
0x1800862d3  mov     r13b, al
0x1800862d6  mov     [rsp+188h+var_128], al
0x1800862da  mov     rcx, [rsp+188h+var_108]
0x1800862e2  mov     rdx, [rcx]
0x1800862e5  mov     rax, [rdx+58h]
0x1800862e9  lea     rdx, [rsp+188h+var_F4]
0x1800862f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800862f6  mov     rcx, [rsp+188h]; this
0x1800862fe  test    eax, eax
0x180086300  js      loc_180086D90
0x180086306  mov     rcx, [rsp+188h+var_108]
0x18008630e  mov     rax, rsi
0x180086311  mov     qword ptr [rsp+188h+var_118], rax
0x180086316  test    rcx, rcx
0x180086319  jz      short loc_180086346
0x18008631b  mov     rax, [rcx]
0x18008631e  mov     qword ptr [rsp+188h+var_118], rsi
0x180086323  lea     rdx, [rsp+188h+var_118]
0x180086328  mov     rax, [rax+18h]
0x18008632c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086331  mov     rcx, [rsp+188h]; this
0x180086339  test    eax, eax
0x18008633b  js      loc_180086DA5
0x180086341  mov     rax, qword ptr [rsp+188h+var_118]
0x180086346  movzx   ecx, r13b
0x18008634a  mov     [rsp+188h+var_138], ecx
0x18008634e  mov     ecx, [rsp+188h+var_F4]
0x180086355  mov     [rsp+188h+var_140], ecx
0x180086359  mov     ecx, [rsp+188h+var_F8]
0x180086360  mov     [rsp+188h+var_148], ecx
0x180086364  mov     ecx, [rsp+188h+var_100]
0x18008636b  mov     dword ptr [rsp+188h+var_150], ecx
0x18008636f  mov     dword ptr [rsp+188h+var_158], edi
0x180086373  mov     [rsp+188h+var_160], rax
0x180086378  lea     rax, aLeaseSUsageDPo; "lease = %s, usage = %d, policy = %d, op"...
0x18008637f  mov     [rsp+188h+Format], rax; int
0x180086384  lea     r9, aKeymachineDoli; "KeyMachine::DoLicenseThreadProc"
0x18008638b  mov     r8d, 3A3h; unsigned int
0x180086391  lea     rdi, aOnecoreuapEndu_1; "onecoreuap\\enduser\\winstore\\licensem"...
0x180086398  mov     rdx, rdi; char *
0x18008639b  mov     r15d, 3
0x1800863a1  mov     ecx, r15d; unsigned int
0x1800863a4  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x1800863a9  nop
0x1800863aa  lea     rcx, [rsp+188h+var_118]
0x1800863af  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800863b4  mov     eax, [rsp+188h+var_100]
0x1800863bb  cmp     eax, 4
0x1800863be  jge     short loc_18008643F
0x1800863c0  test    eax, eax
0x1800863c2  jz      short loc_1800863E2
0x1800863c4  cmp     eax, 2
0x1800863c7  jge     short loc_180086413
0x1800863c9  cmp     [rsp+188h+var_F8], 2
0x1800863d1  jle     short loc_180086413
0x1800863d3  mov     eax, [rsp+188h+var_F4]
0x1800863da  add     eax, 0FFFFFFFEh
0x1800863dd  cmp     eax, 1
0x1800863e0  ja      short loc_180086413
0x1800863e2  lea     rcx, [rsp+188h+var_108]
0x1800863ea  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800863ef  lea     rax, aResetLeaseAsKe; "reset lease as Key cannot ever have a l"...
0x1800863f6  mov     [rsp+188h+Format], rax; Format
0x1800863fb  lea     r9, aKeymachineDoli; "KeyMachine::DoLicenseThreadProc"
0x180086402  mov     r8d, 3BCh; unsigned int
0x180086408  mov     rdx, rdi; char *
0x18008640b  mov     ecx, r15d; unsigned int
0x18008640e  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x180086413  cmp     [rsp+188h+var_127], sil
0x180086418  jnz     loc_18008657E
0x18008641e  call    cs:__imp_XblaIsConsole
0x180086424  test    eax, eax
0x180086426  jz      loc_180086641
0x18008642c  cmp     [rsp+188h+var_11C], 7F000000h
0x180086434  jg      loc_18008657E
0x18008643a  jmp     loc_180086641
0x18008643f  cmp     [rsp+188h+var_127], sil
0x180086444  jz      loc_180086641
0x18008644a  mov     dword ptr [rsp+188h+var_E8], 1
0x180086455  mov     [rsp+188h+var_FC], r12d
0x18008645d  mov     rcx, [rsp+188h+var_108]
0x180086465  test    rcx, rcx
0x180086468  jz      short loc_18008649E
0x18008646a  mov     rax, [rcx]
0x18008646d  lea     r8, [rsp+188h+var_E8]
0x180086475  lea     rdx, [rsp+188h+var_FC]
0x18008647d  mov     rax, [rax+30h]
0x180086481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086486  mov     rcx, [rsp+188h]; this
0x18008648e  test    eax, eax
0x180086490  js      loc_180086DBA
0x180086496  mov     rcx, [rsp+188h+var_108]
0x18008649e  mov     rax, rsi
0x1800864a1  mov     qword ptr [rsp+188h+var_118], rax
0x1800864a6  test    rcx, rcx
0x1800864a9  jz      short loc_1800864D6
0x1800864ab  mov     rax, [rcx]
0x1800864ae  mov     qword ptr [rsp+188h+var_118], rsi
0x1800864b3  lea     rdx, [rsp+188h+var_118]
0x1800864b8  mov     rax, [rax+18h]
0x1800864bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800864c1  mov     rcx, [rsp+188h]; this
0x1800864c9  test    eax, eax
0x1800864cb  js      loc_180086DCB
0x1800864d1  mov     rax, qword ptr [rsp+188h+var_118]
0x1800864d6  mov     ecx, [rsp+188h+var_FC]
0x1800864dd  mov     dword ptr [rsp+188h+var_158], ecx
0x1800864e1  mov     [rsp+188h+var_160], rax
0x1800864e6  lea     rax, aLeaseSQualityD; "lease = %s, quality = %d"
0x1800864ed  mov     [rsp+188h+Format], rax; Format
0x1800864f2  lea     r9, aKeymachineDoli; "KeyMachine::DoLicenseThreadProc"
0x1800864f9  mov     r8d, 3D3h; unsigned int
0x1800864ff  mov     rdx, rdi; char *
0x180086502  mov     ecx, r15d; unsigned int
0x180086505  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18008650a  nop
0x18008650b  lea     rcx, [rsp+188h+var_118]
0x180086510  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180086515  cmp     [rsp+188h+var_FC], r12d
0x18008651d  jle     short loc_180086545
0x18008651f  lea     rax, aContentIsAlrea_0; "content is alreadyLicensed, lease is ca"...
0x180086526  mov     [rsp+188h+Format], rax; Format
0x18008652b  lea     r9, aKeymachineDoli; "KeyMachine::DoLicenseThreadProc"
  ... truncated ...
```
