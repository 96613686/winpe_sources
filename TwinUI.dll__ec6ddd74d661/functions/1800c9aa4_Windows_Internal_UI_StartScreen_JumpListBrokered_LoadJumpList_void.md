# Windows::Internal::UI::StartScreen::JumpListBrokered::LoadJumpList(void)

- ea: `0x1800c9aa4`
- end: `0x1800ca298`
- name: `?LoadJumpList@JumpListBrokered@StartScreen@UI@Internal@Windows@@AEAAJXZ`
- size: `2036`
- prototype: `__int64 __fastcall(Windows::Internal::UI::StartScreen::JumpListBrokered *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800a3d04`

## callees

- `0x180009dd0`
- `0x180009dfc`
- `0x18000aa70`
- `0x18000c4f4`
- `0x180017e44`
- `0x1800378dc`
- `0x18003a2c0`
- `0x18008f2dc`
- `0x180091f58`
- `0x1800bb9ac`
- `0x1800c9aa4`
- `0x1801038fc`
- `0x180142e10`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ca1f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ca1f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9b2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c9b2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9eb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9f73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9eb2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c9f73`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c9afc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c9afc`

## string_xrefs

- `0x1800c9b50`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800c9b88`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800c9bd1`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800c9c10`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800c9c6d`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800c9cc1`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800c9efa`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800c9f1e`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800c9f47`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800c9fd2`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800ca15a`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800ca196`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`
- `0x1800ca1bf`: `shell\twinui\jumplist\broker\jumplistbrokered.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall Windows::Internal::UI::StartScreen::JumpListBrokered::LoadJumpList(
        Windows::Internal::UI::StartScreen::JumpListBrokered *this)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  HSTRING v5; // rcx
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, PCWSTR); // rbx
  PCWSTR StringRawBuffer; // rax
  int v9; // eax
  const unsigned __int16 *v10; // rdx
  _QWORD *v11; // rax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, HSTRING, _QWORD); // rbx
  int v16; // eax
  __int64 (__fastcall ***v17)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v18)(_QWORD, GUID *, __int64 *); // rbx
  int v19; // eax
  __int64 v20; // rdx
  unsigned int v21; // r15d
  unsigned int v22; // r14d
  int v23; // eax
  void *v24; // rcx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, _QWORD, GUID *, __int64); // rbx
  __int64 v27; // rax
  int v28; // eax
  unsigned int v29; // esi
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, _QWORD, GUID *, __int64); // rbx
  __int64 v32; // rax
  int v33; // eax
  int v34; // eax
  __int64 v35; // rdx
  LPVOID v36; // rdi
  __int64 (__fastcall *v37)(LPVOID, int *, GUID *, __int64 *); // rbx
  int v38; // eax
  __int64 v39; // rdx
  unsigned int v40; // esi
  __int64 v41; // rdi
  __int64 (__fastcall *v42)(__int64, _QWORD, GUID *, __int64); // rbx
  __int64 v43; // rax
  int v44; // eax
  struct Windows::UI::StartScreen::IJumpListItem *v45; // rbx
  __int64 (__fastcall *v46)(struct Windows::UI::StartScreen::IJumpListItem *, GUID *, __int64 *); // rdi
  int v47; // eax
  __int64 v48; // rdx
  __int64 (__fastcall ***v49)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v50)(_QWORD, GUID *, __int64 *); // rdi
  int v51; // eax
  __int64 v52; // rdx
  __int64 v53; // rdx
  __int64 v54; // rsi
  __int64 (__fastcall *v55)(__int64, char *); // rdi
  int ppv; // [rsp+20h] [rbp-B9h]
  __int64 v58; // [rsp+30h] [rbp-A9h] BYREF
  __int64 (__fastcall ***v59)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-A1h] BYREF
  __int64 v60; // [rsp+40h] [rbp-99h] BYREF
  __int64 v61; // [rsp+48h] [rbp-91h] BYREF
  __int64 v62; // [rsp+50h] [rbp-89h] BYREF
  __int64 v63; // [rsp+58h] [rbp-81h] BYREF
  __int64 v64; // [rsp+60h] [rbp-79h] BYREF
  struct Windows::UI::StartScreen::IJumpListItem *v65; // [rsp+68h] [rbp-71h] BYREF
  unsigned int v66; // [rsp+70h] [rbp-69h] BYREF
  unsigned int v67; // [rsp+74h] [rbp-65h] BYREF
  unsigned int v68; // [rsp+78h] [rbp-61h] BYREF
  __int64 v69; // [rsp+80h] [rbp-59h] BYREF
  __int64 v70; // [rsp+88h] [rbp-51h] BYREF
  LPVOID v71; // [rsp+90h] [rbp-49h] BYREF
  struct Windows::UI::StartScreen::IJumpListItem *v72; // [rsp+98h] [rbp-41h] BYREF
  struct IUnknown *v73; // [rsp+A0h] [rbp-39h] BYREF
  struct IUnknown *v74; // [rsp+A8h] [rbp-31h] BYREF
  char v75; // [rsp+B0h] [rbp-29h]
  int v76; // [rsp+B8h] [rbp-21h] BYREF
  LPVOID pv[2]; // [rsp+C0h] [rbp-19h] BYREF
  __int64 v78; // [rsp+D0h] [rbp-9h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  v71 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
  v2 = CoCreateInstance(&CLSID_DestinationListBoth, 0, 3u, &GUID_6332debf_87b5_4670_90c0_5e57b408a49e, &v71);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 545;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
      (const char *)(unsigned int)v2,
      ppv);
    goto LABEL_84;
  }
  v5 = (HSTRING)*((_QWORD *)this + 8);
  if ( v5 )
  {
    v6 = v71;
    v7 = *(__int64 (__fastcall **)(LPVOID, PCWSTR))(*(_QWORD *)v71 + 24LL);
    StringRawBuffer = WindowsGetStringRawBuffer(v5, 0);
    v2 = v7(v6, StringRawBuffer);
    v3 = v2;
    if ( v2 < 0 )
    {
      v4 = 549;
      goto LABEL_6;
    }
  }
  v58 = 0;
  v9 = Microsoft::WRL::ComPtr<ICustomDestinationList>::As<IInternalCustomDestinationList>(&v71, &v58);
  v3 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x229,
      (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
      (const char *)(unsigned int)v9,
      ppv);
    goto LABEL_9;
  }
  v60 = 0;
  v11 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                    (HSTRING *)pv,
                    (const unsigned __int16 (*)[32])v10);
  v12 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::UI::StartScreen::IJumpListStatics>>(
          *v11,
          &v60);
  v3 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22C,
      (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
      (const char *)(unsigned int)v12,
      ppv);
    goto LABEL_12;
  }
  v62 = 0;
  v13 = Microsoft::WRL::ComPtr<Windows::UI::StartScreen::IJumpListStatics>::As<Windows::Internal::UI::StartScreen::IJumpListSerializationStatics>(
          &v60,
          &v62);
  v3 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22F,
      (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
      (const char *)(unsigned int)v13,
      ppv);
    goto LABEL_15;
  }
  v59 = 0;
  v14 = v62;
  v15 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v62 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
  v16 = v15(v14, string, &v59);
  v3 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x232,
      (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
      (const char *)(unsigned int)v16,
      ppv);
    goto LABEL_18;
  }
  v61 = 0;
  v17 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v59;
  v18 = (*v59)[6];
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
  v19 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64 *))v18)(v17, &v61);
  v3 = v19;
  if ( v19 < 0 )
  {
    v20 = 565;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
      (const char *)(unsigned int)v19,
      ppv);
    goto LABEL_22;
  }
  v67 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v58 + 48LL))(v58, &v67);
  v3 = v19;
  if ( v19 < 0 )
  {
    v20 = 570;
    goto LABEL_21;
  }
  v21 = 2;
  v22 = 0;
  if ( !v67 )
  {
LABEL_47:
    v19 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD))(*v59)[8])(v59, v21);
    v3 = v19;
    if ( v19 < 0 )
    {
      v20 = 621;
      goto LABEL_21;
    }
    v76 = 0;
    v63 = 0;
    v36 = v71;
    v37 = *(__int64 (__fastcall **)(LPVOID, int *, GUID *, __int64 *))(*(_QWORD *)v71 + 32LL);
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v63);
    v38 = v37(v36, &v76, &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9, &v63);
    v3 = v38;
    if ( v38 >= 0 )
    {
      v68 = 0;
      v38 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v63 + 24LL))(v63, &v68);
      v3 = v38;
      if ( v38 >= 0 )
      {
        v40 = 0;
        if ( v68 )
        {
          while ( 1 )
          {
            v74 = 0;
            v41 = v63;
            v42 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64))(*(_QWORD *)v63 + 32LL);
            v43 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IClassFactory>>(&v74);
            v44 = v42(v41, v40, &GUID_00000000_0000_0000_c000_000000000046, v43);
            v3 = v44;
            if ( v44 < 0 )
              break;
            v65 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
            if ( (int)Windows::Internal::UI::StartScreen::JumpListBrokered::CreateJumpListItemForShellObject(
                        this,
                        v74,
                        &v65) >= 0 )
            {
              v69 = 0;
              v45 = v65;
              v46 = **(__int64 (__fastcall ***)(struct Windows::UI::StartScreen::IJumpListItem *, GUID *, __int64 *))v65;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
              v47 = v46(v45, &GUID_64384f1c_d1b5_43eb_a2b3_2befbde9a7a2, &v69);
              v3 = v47;
              if ( v47 < 0 )
              {
                v53 = 639;
                goto LABEL_78;
              }
              LOBYTE(v48) = 1;
              v47 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v69 + 48LL))(v69, v48);
              v3 = v47;
              if ( v47 < 0 )
              {
                v53 = 641;
                goto LABEL_78;
              }
              v47 = (*(__int64 (__fastcall **)(__int64, struct Windows::UI::StartScreen::IJumpListItem *))(*(_QWORD *)v61 + 104LL))(
                      v61,
                      v65);
              v3 = v47;
              if ( v47 < 0 )
              {
                v53 = 643;
LABEL_78:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v53,
                  (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
                  (const char *)(unsigned int)v47,
                  ppv);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
                goto LABEL_80;
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v65);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74);
            if ( ++v40 >= v68 )
              goto LABEL_72;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x279,
            (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
            (const char *)(unsigned int)v44,
            ppv);
LABEL_80:
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v74);
        }
        else
        {
LABEL_72:
          v70 = 0;
          v49 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v59;
          v50 = **v59;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
          v51 = v50(v49, &GUID_fa29c8a5_125f_4162_806b_3a7ffdb40eed, &v70);
          v3 = v51;
          if ( v51 >= 0 )
          {
            v54 = v70;
            v55 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v70 + 48LL);
            WindowsDeleteString(*((HSTRING *)this + 10));
            *((_QWORD *)this + 10) = 0;
            v51 = v55(v54, (char *)this + 80);
            v3 = v51;
            if ( v51 >= 0 )
            {
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
              Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v63);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
              v3 = 0;
              goto LABEL_84;
            }
            v52 = 650;
          }
          else
          {
            v52 = 649;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v52,
            (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
            (const char *)(unsigned int)v51,
            ppv);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v70);
        }
LABEL_61:
        Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v63);
        goto LABEL_22;
      }
      v39 = 629;
    }
    else
    {
      v39 = 625;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v39,
      (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
      (const char *)(unsigned int)v38,
      ppv);
    goto LABEL_61;
  }
  while ( 1 )
  {
    *(_OWORD *)pv = 0;
    v78 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, LPVOID *))(*(_QWORD *)v58 + 56LL))(v58, v22, 1, pv);
    v3 = v19;
    if ( v19 < 0 )
    {
      v20 = 574;
      goto LABEL_21;
    }
    v74 = (struct IUnknown *)pv;
    v75 = 1;
    v23 = (int)pv[0];
    if ( LODWORD(pv[0]) == 1 )
    {
      v24 = pv[1];
      switch ( LODWORD(pv[1]) )
      {
        case 2:
          v21 = (unsigned int)pv[1];
          break;
        case 1:
          v21 = 1;
          break;
        case 0xFFFFFFFF:
          v21 = 0;
          break;
      }
      goto LABEL_44;
    }
    if ( ((__int64)pv[0] & 0xFFFFFFFD) == 0 )
      break;
LABEL_43:
    v24 = pv[1];
LABEL_44:
    v75 = 0;
    if ( !v23 )
      CoTaskMemFree(v24);
    if ( ++v22 >= v67 )
      goto LABEL_47;
  }
  v64 = 0;
  v25 = v58;
  v26 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64))(*(_QWORD *)v58 + 72LL);
  v27 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(&v64);
  v28 = v26(v25, v22, &GUID_5632b1a4_e38a_400a_928a_d4cd63230295, v27);
  v3 = v28;
  if ( v28 < 0 )
  {
    v35 = 603;
    goto LABEL_54;
  }
  v66 = 0;
  v28 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v64 + 24LL))(v64, &v66);
  v3 = v28;
  if ( v28 < 0 )
  {
    v35 = 606;
LABEL_54:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
      (const char *)(unsigned int)v28,
      ppv);
    goto LABEL_55;
  }
  v29 = 0;
  if ( !v66 )
  {
LABEL_42:
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v64);
    v23 = (int)pv[0];
    goto LABEL_43;
  }
  while ( 1 )
  {
    v73 = 0;
    v30 = v64;
    v31 = *(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64))(*(_QWORD *)v64 + 32LL);
    v32 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IClassFactory>>(&v73);
    v33 = v31(v30, v29, &GUID_00000000_0000_0000_c000_000000000046, v32);
    v3 = v33;
    if ( v33 < 0 )
      break;
    v72 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
    if ( (int)Windows::Internal::UI::StartScreen::JumpListBrokered::CreateJumpListItemForShellObject(this, v73, &v72) >= 0 )
    {
      v34 = (*(__int64 (__fastcall **)(__int64, struct Windows::UI::StartScreen::IJumpListItem *))(*(_QWORD *)v61 + 104LL))(
              v61,
              v72);
      v3 = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x267,
          (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
          (const char *)(unsigned int)v34,
          ppv);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
        goto LABEL_51;
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v72);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
    if ( ++v29 >= v66 )
      goto LABEL_42;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x262,
    (unsigned int)"shell\\twinui\\jumplist\\broker\\jumplistbrokered.cpp",
    (const char *)(unsigned int)v33,
    ppv);
LABEL_51:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v73);
LABEL_55:
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v64);
  if ( !LODWORD(pv[0]) )
    CoTaskMemFree(pv[1]);
LABEL_22:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v61);
LABEL_18:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v59);
LABEL_15:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
LABEL_12:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
LABEL_9:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v58);
LABEL_84:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v71);
  return v3;
}

```

## disassembly

```asm
0x1800c9aa4  push    rbp
0x1800c9aa6  push    rbx
0x1800c9aa7  push    rsi
0x1800c9aa8  push    rdi
0x1800c9aa9  push    r12
0x1800c9aab  push    r13
0x1800c9aad  push    r14
0x1800c9aaf  push    r15
0x1800c9ab1  lea     rbp, [rsp-1Fh]
0x1800c9ab6  sub     rsp, 0F8h
0x1800c9abd  mov     rax, cs:__security_cookie
0x1800c9ac4  xor     rax, rsp
0x1800c9ac7  mov     [rbp+57h+var_50], rax
0x1800c9acb  mov     r13, rcx
0x1800c9ace  xor     r12d, r12d
0x1800c9ad1  mov     [rbp+57h+var_A0], r12
0x1800c9ad5  lea     rcx, [rbp+57h+var_A0]
0x1800c9ad9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c9ade  lea     rax, [rbp+57h+var_A0]
0x1800c9ae2  mov     qword ptr [rsp+130h+ppv], rax; int
0x1800c9ae7  lea     r9, _GUID_6332debf_87b5_4670_90c0_5e57b408a49e; riid
0x1800c9aee  xor     edx, edx; pUnkOuter
0x1800c9af0  lea     r8d, [r12+3]; dwClsContext
0x1800c9af5  lea     rcx, CLSID_DestinationListBoth; rclsid
0x1800c9afc  call    cs:__imp_CoCreateInstance
0x1800c9b03  nop     dword ptr [rax+rax+00h]
0x1800c9b08  mov     ebx, eax
0x1800c9b0a  test    eax, eax
0x1800c9b0c  jns     short loc_1800C9B15
0x1800c9b0e  mov     edx, 221h
0x1800c9b13  jmp     short loc_1800C9B50
0x1800c9b15  mov     rcx, [r13+40h]; string
0x1800c9b19  test    rcx, rcx
0x1800c9b1c  jz      short loc_1800C9B68
0x1800c9b1e  mov     rdi, [rbp+57h+var_A0]
0x1800c9b22  mov     rax, [rdi]
0x1800c9b25  mov     rbx, [rax+18h]
0x1800c9b29  xor     edx, edx; length
0x1800c9b2b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c9b32  nop     dword ptr [rax+rax+00h]
0x1800c9b37  mov     rdx, rax
0x1800c9b3a  mov     rcx, rdi
0x1800c9b3d  mov     rax, rbx
0x1800c9b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9b45  mov     ebx, eax
0x1800c9b47  test    eax, eax
0x1800c9b49  jns     short loc_1800C9B68
0x1800c9b4b  mov     edx, 225h; void *
0x1800c9b50  lea     r8, aShellTwinuiJum; "shell\\twinui\\jumplist\\broker\\jumpli"...
0x1800c9b57  mov     r9d, eax; char *
0x1800c9b5a  mov     rcx, [rbp+5Fh]; this
0x1800c9b5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9b63  jmp     loc_1800CA26C
0x1800c9b68  mov     [rsp+130h+var_100], r12
0x1800c9b6d  lea     rdx, [rsp+130h+var_100]
0x1800c9b72  lea     rcx, [rbp+57h+var_A0]
0x1800c9b76  call    ??$As@UIInternalCustomDestinationList@@@?$ComPtr@UICustomDestinationList@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIInternalCustomDestinationList@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ICustomDestinationList>::As<IInternalCustomDestinationList>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IInternalCustomDestinationList>>)
0x1800c9b7b  mov     ebx, eax
0x1800c9b7d  test    eax, eax
0x1800c9b7f  jns     short loc_1800C9BA9
0x1800c9b81  mov     rcx, [rbp+5Fh]; this
0x1800c9b85  mov     r9d, eax; char *
0x1800c9b88  lea     r8, aShellTwinuiJum; "shell\\twinui\\jumplist\\broker\\jumpli"...
0x1800c9b8f  mov     edx, 229h; void *
0x1800c9b94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9b99  nop
0x1800c9b9a  lea     rcx, [rsp+130h+var_100]
0x1800c9b9f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c9ba4  jmp     loc_1800CA26C
0x1800c9ba9  mov     [rsp+130h+var_F0], r12
0x1800c9bae  lea     rcx, [rbp+57h+pv]; string
0x1800c9bb2  call    ??$?0$0CA@@StringReference@Internal@Windows@@QEAA@AEAY0CA@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[32])
0x1800c9bb7  lea     rdx, [rsp+130h+var_F0]
0x1800c9bbc  mov     rcx, [rax]
0x1800c9bbf  call    ??$GetActivationFactory@V?$ComPtr@UIJumpListStatics@StartScreen@UI@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJumpListStatics@StartScreen@UI@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::UI::StartScreen::IJumpListStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::UI::StartScreen::IJumpListStatics>>)
0x1800c9bc4  mov     ebx, eax
0x1800c9bc6  test    eax, eax
0x1800c9bc8  jns     short loc_1800C9BEF
0x1800c9bca  mov     rcx, [rbp+5Fh]; this
0x1800c9bce  mov     r9d, eax; char *
0x1800c9bd1  lea     r8, aShellTwinuiJum; "shell\\twinui\\jumplist\\broker\\jumpli"...
0x1800c9bd8  mov     edx, 22Ch; void *
0x1800c9bdd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9be2  nop
0x1800c9be3  lea     rcx, [rsp+130h+var_F0]
0x1800c9be8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c9bed  jmp     short loc_1800C9B9A
0x1800c9bef  mov     [rsp+130h+var_E0], r12
0x1800c9bf4  lea     rdx, [rsp+130h+var_E0]
0x1800c9bf9  lea     rcx, [rsp+130h+var_F0]
0x1800c9bfe  call    ??$As@UIJumpListSerializationStatics@StartScreen@UI@Internal@Windows@@@?$ComPtr@UIJumpListStatics@StartScreen@UI@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIJumpListSerializationStatics@StartScreen@UI@Internal@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::UI::StartScreen::IJumpListStatics>::As<Windows::Internal::UI::StartScreen::IJumpListSerializationStatics>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::UI::StartScreen::IJumpListSerializationStatics>>)
0x1800c9c03  mov     ebx, eax
0x1800c9c05  test    eax, eax
0x1800c9c07  jns     short loc_1800C9C2E
0x1800c9c09  mov     rcx, [rbp+5Fh]; this
0x1800c9c0d  mov     r9d, eax; char *
0x1800c9c10  lea     r8, aShellTwinuiJum; "shell\\twinui\\jumplist\\broker\\jumpli"...
0x1800c9c17  mov     edx, 22Fh; void *
0x1800c9c1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9c21  nop
0x1800c9c22  lea     rcx, [rsp+130h+var_E0]
0x1800c9c27  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c9c2c  jmp     short loc_1800C9BE3
0x1800c9c2e  mov     [rsp+130h+var_F8], r12
0x1800c9c33  mov     rdi, [rsp+130h+var_E0]
0x1800c9c38  mov     rax, [rdi]
0x1800c9c3b  mov     rbx, [rax+30h]
0x1800c9c3f  lea     rcx, [rsp+130h+var_F8]
0x1800c9c44  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c9c49  lea     r8, [rsp+130h+var_F8]
0x1800c9c4e  mov     rdx, cs:string
0x1800c9c55  mov     rcx, rdi
0x1800c9c58  mov     rax, rbx
0x1800c9c5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9c60  mov     ebx, eax
0x1800c9c62  test    eax, eax
0x1800c9c64  jns     short loc_1800C9C8B
0x1800c9c66  mov     rcx, [rbp+5Fh]; this
0x1800c9c6a  mov     r9d, eax; char *
0x1800c9c6d  lea     r8, aShellTwinuiJum; "shell\\twinui\\jumplist\\broker\\jumpli"...
0x1800c9c74  mov     edx, 232h; void *
0x1800c9c79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9c7e  nop
0x1800c9c7f  lea     rcx, [rsp+130h+var_F8]
0x1800c9c84  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c9c89  jmp     short loc_1800C9C22
0x1800c9c8b  mov     [rsp+130h+var_E8], r12
0x1800c9c90  mov     rdi, [rsp+130h+var_F8]
0x1800c9c95  mov     rax, [rdi]
0x1800c9c98  mov     rbx, [rax+30h]
0x1800c9c9c  lea     rcx, [rsp+130h+var_E8]
0x1800c9ca1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c9ca6  lea     rdx, [rsp+130h+var_E8]
0x1800c9cab  mov     rcx, rdi
0x1800c9cae  mov     rax, rbx
0x1800c9cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9cb6  mov     ebx, eax
0x1800c9cb8  test    eax, eax
0x1800c9cba  jns     short loc_1800C9CE1
0x1800c9cbc  mov     edx, 235h; void *
0x1800c9cc1  lea     r8, aShellTwinuiJum; "shell\\twinui\\jumplist\\broker\\jumpli"...
0x1800c9cc8  mov     r9d, eax; char *
0x1800c9ccb  mov     rcx, [rbp+5Fh]; this
0x1800c9ccf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9cd4  nop
0x1800c9cd5  lea     rcx, [rsp+130h+var_E8]
0x1800c9cda  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c9cdf  jmp     short loc_1800C9C7F
0x1800c9ce1  mov     [rbp+57h+var_BC], r12d
0x1800c9ce5  mov     rcx, [rsp+130h+var_100]
0x1800c9cea  mov     rax, [rcx]
0x1800c9ced  lea     rdx, [rbp+57h+var_BC]
0x1800c9cf1  mov     rax, [rax+30h]
0x1800c9cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9cfa  mov     ebx, eax
0x1800c9cfc  test    eax, eax
0x1800c9cfe  jns     short loc_1800C9D07
0x1800c9d00  mov     edx, 23Ah
0x1800c9d05  jmp     short loc_1800C9CC1
0x1800c9d07  mov     r15d, 2
0x1800c9d0d  mov     r14d, r12d
0x1800c9d10  cmp     [rbp+57h+var_BC], r12d
0x1800c9d14  jbe     loc_1800C9ECB
0x1800c9d1a  xorps   xmm0, xmm0
0x1800c9d1d  xor     eax, eax
0x1800c9d1f  movups  xmmword ptr [rbp+57h+pv], xmm0
0x1800c9d23  mov     [rbp+57h+var_60], rax
0x1800c9d27  mov     rcx, [rsp+130h+var_100]
0x1800c9d2c  mov     rax, [rcx]
0x1800c9d2f  lea     r9, [rbp+57h+pv]
0x1800c9d33  mov     r8d, 1
0x1800c9d39  mov     edx, r14d
0x1800c9d3c  mov     rax, [rax+38h]
0x1800c9d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9d45  mov     ebx, eax
0x1800c9d47  test    eax, eax
0x1800c9d49  js      loc_1800C9F84
0x1800c9d4f  lea     rax, [rbp+57h+pv]
0x1800c9d53  mov     [rbp+57h+var_88], rax
0x1800c9d57  mov     [rbp+57h+var_80], 1
0x1800c9d5b  mov     eax, dword ptr [rbp+57h+pv]
0x1800c9d5e  cmp     eax, 1
0x1800c9d61  jnz     short loc_1800C9D92
0x1800c9d63  mov     rcx, [rbp+57h+pv+8]
0x1800c9d67  cmp     ecx, 2
0x1800c9d6a  jnz     short loc_1800C9D74
0x1800c9d6c  mov     r15d, ecx
0x1800c9d6f  jmp     loc_1800C9EAA
0x1800c9d74  cmp     ecx, 1
0x1800c9d77  jnz     short loc_1800C9D81
0x1800c9d79  mov     r15d, ecx
0x1800c9d7c  jmp     loc_1800C9EAA
0x1800c9d81  cmp     ecx, 0FFFFFFFFh
0x1800c9d84  jnz     loc_1800C9EAA
0x1800c9d8a  mov     r15d, r12d
0x1800c9d8d  jmp     loc_1800C9EAA
0x1800c9d92  test    eax, 0FFFFFFFDh
0x1800c9d97  jnz     loc_1800C9EA6
0x1800c9d9d  mov     [rbp+57h+var_D0], r12
0x1800c9da1  mov     rdi, [rsp+130h+var_100]
0x1800c9da6  mov     rax, [rdi]
0x1800c9da9  mov     rbx, [rax+48h]
0x1800c9dad  lea     rcx, [rbp+57h+var_D0]
0x1800c9db1  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIImmersiveMonitor@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IImmersiveMonitor>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IImmersiveMonitor>>)
0x1800c9db6  mov     r9, rax
0x1800c9db9  lea     r8, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295
0x1800c9dc0  mov     edx, r14d
0x1800c9dc3  mov     rcx, rdi
0x1800c9dc6  mov     rax, rbx
0x1800c9dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9dce  mov     ebx, eax
0x1800c9dd0  test    eax, eax
0x1800c9dd2  js      loc_1800C9F42
0x1800c9dd8  mov     [rbp+57h+var_C0], r12d
0x1800c9ddc  mov     rcx, [rbp+57h+var_D0]
0x1800c9de0  mov     rax, [rcx]
0x1800c9de3  lea     rdx, [rbp+57h+var_C0]
0x1800c9de7  mov     rax, [rax+18h]
0x1800c9deb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9df0  mov     ebx, eax
0x1800c9df2  test    eax, eax
0x1800c9df4  js      loc_1800C9F3B
0x1800c9dfa  mov     esi, r12d
0x1800c9dfd  cmp     [rbp+57h+var_C0], r12d
0x1800c9e01  jbe     loc_1800C9E9A
0x1800c9e07  mov     [rbp+57h+var_90], r12
0x1800c9e0b  mov     rdi, [rbp+57h+var_D0]
0x1800c9e0f  mov     rax, [rdi]
0x1800c9e12  mov     rbx, [rax+20h]
0x1800c9e16  lea     rcx, [rbp+57h+var_90]
0x1800c9e1a  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIClassFactory@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIClassFactory@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IClassFactory>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IClassFactory>>)
0x1800c9e1f  mov     r9, rax
0x1800c9e22  lea     r8, _GUID_00000000_0000_0000_c000_000000000046
0x1800c9e29  mov     edx, esi
0x1800c9e2b  mov     rcx, rdi
0x1800c9e2e  mov     rax, rbx
0x1800c9e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9e36  mov     ebx, eax
0x1800c9e38  test    eax, eax
0x1800c9e3a  js      loc_1800C9F17
0x1800c9e40  mov     [rbp+57h+var_98], r12
0x1800c9e44  lea     rcx, [rbp+57h+var_98]
0x1800c9e48  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c9e4d  lea     r8, [rbp+57h+var_98]; struct Windows::UI::StartScreen::IJumpListItem **
0x1800c9e51  mov     rdx, [rbp+57h+var_90]; struct IUnknown *
0x1800c9e55  mov     rcx, r13; this
0x1800c9e58  call    ?CreateJumpListItemForShellObject@JumpListBrokered@StartScreen@UI@Internal@Windows@@AEAAJPEAUIUnknown@@PEAPEAUIJumpListItem@235@@Z; Windows::Internal::UI::StartScreen::JumpListBrokered::CreateJumpListItemForShellObject(IUnknown *,Windows::UI::StartScreen::IJumpListItem * *)
0x1800c9e5d  test    eax, eax
0x1800c9e5f  js      short loc_1800C9E7C
0x1800c9e61  mov     rcx, [rsp+130h+var_E8]
0x1800c9e66  mov     rax, [rcx]
0x1800c9e69  mov     rdx, [rbp+57h+var_98]
0x1800c9e6d  mov     rax, [rax+68h]
0x1800c9e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9e76  mov     ebx, eax
0x1800c9e78  test    eax, eax
0x1800c9e7a  js      short loc_1800C9EF3
0x1800c9e7c  lea     rcx, [rbp+57h+var_98]
0x1800c9e80  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c9e85  nop
0x1800c9e86  lea     rcx, [rbp+57h+var_90]
0x1800c9e8a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c9e8f  inc     esi
0x1800c9e91  cmp     esi, [rbp+57h+var_C0]
0x1800c9e94  jb      loc_1800C9E07
0x1800c9e9a  lea     rcx, [rbp+57h+var_D0]
0x1800c9e9e  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1800c9ea3  mov     eax, dword ptr [rbp+57h+pv]
0x1800c9ea6  mov     rcx, [rbp+57h+pv+8]; pv
0x1800c9eaa  mov     [rbp+57h+var_80], r12b
0x1800c9eae  test    eax, eax
0x1800c9eb0  jnz     short loc_1800C9EBE
0x1800c9eb2  call    cs:__imp_CoTaskMemFree
0x1800c9eb9  nop     dword ptr [rax+rax+00h]
0x1800c9ebe  inc     r14d
0x1800c9ec1  cmp     r14d, [rbp+57h+var_BC]
0x1800c9ec5  jb      loc_1800C9D1A
0x1800c9ecb  mov     rcx, [rsp+130h+var_F8]
0x1800c9ed0  mov     rax, [rcx]
0x1800c9ed3  mov     edx, r15d
0x1800c9ed6  mov     rax, [rax+40h]
0x1800c9eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9edf  mov     ebx, eax
0x1800c9ee1  test    eax, eax
0x1800c9ee3  jns     loc_1800C9F8E
0x1800c9ee9  mov     edx, 26Dh
0x1800c9eee  jmp     loc_1800C9CC1
0x1800c9ef3  mov     rcx, [rbp+5Fh]; this
0x1800c9ef7  mov     r9d, eax; char *
0x1800c9efa  lea     r8, aShellTwinuiJum; "shell\\twinui\\jumplist\\broker\\jumpli"...
0x1800c9f01  mov     edx, 267h; void *
0x1800c9f06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9f0b  nop
0x1800c9f0c  lea     rcx, [rbp+57h+var_98]
0x1800c9f10  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c9f15  jmp     short loc_1800C9F30
0x1800c9f17  mov     rcx, [rbp+5Fh]; this
0x1800c9f1b  mov     r9d, eax; char *
0x1800c9f1e  lea     r8, aShellTwinuiJum; "shell\\twinui\\jumplist\\broker\\jumpli"...
0x1800c9f25  mov     edx, 262h; void *
  ... truncated ...
```
