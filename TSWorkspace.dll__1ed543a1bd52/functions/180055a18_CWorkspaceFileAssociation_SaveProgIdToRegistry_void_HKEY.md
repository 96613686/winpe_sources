# CWorkspaceFileAssociation::SaveProgIdToRegistry(void *,HKEY__ *)

- ea: `0x180055a18`
- end: `0x180056a91`
- name: `?SaveProgIdToRegistry@CWorkspaceFileAssociation@@IEAAJPEAXPEAUHKEY__@@@Z`
- size: `4217`
- prototype: `__int64 __fastcall(CWorkspaceFileAssociation *this, void *, HKEY)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180053648`
- `0x180054b64`

## callees

- `0x1800055d0`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec94`
- `0x18000ece0`
- `0x18001e41c`
- `0x180020bf0`
- `0x180025824`
- `0x180025950`
- `0x18005269c`
- `0x1800526cc`
- `0x180055a18`
- `0x18009a520`

## import_xrefs

- `ADVAPI32!RegCreateKeyTransactedW` at `0x180055b1e`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x180055ef0`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x1800560e6`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x1800562ca`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x1800564ac`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x180055b1e`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x180055ef0`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x1800560e6`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x1800562ca`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x1800564ac`
- `ADVAPI32!RegCloseKey` at `0x180055e70`
- `ADVAPI32!RegCloseKey` at `0x18005604c`
- `ADVAPI32!RegCloseKey` at `0x180056242`
- `ADVAPI32!RegCloseKey` at `0x18005642c`
- `ADVAPI32!RegCloseKey` at `0x180056a66`
- `ADVAPI32!RegCloseKey` at `0x180055e70`
- `ADVAPI32!RegCloseKey` at `0x18005604c`
- `ADVAPI32!RegCloseKey` at `0x180056242`
- `ADVAPI32!RegCloseKey` at `0x18005642c`
- `ADVAPI32!RegCloseKey` at `0x180056a66`
- `ADVAPI32!RegSetValueExW` at `0x180055d29`
- `ADVAPI32!RegSetValueExW` at `0x180055de3`
- `ADVAPI32!RegSetValueExW` at `0x180055fbf`
- `ADVAPI32!RegSetValueExW` at `0x1800561b5`
- `ADVAPI32!RegSetValueExW` at `0x18005639f`
- `ADVAPI32!RegSetValueExW` at `0x18005669e`
- `ADVAPI32!RegSetValueExW` at `0x18005674b`
- `ADVAPI32!RegSetValueExW` at `0x180056807`
- `ADVAPI32!RegSetValueExW` at `0x1800568c3`
- `ADVAPI32!RegSetValueExW` at `0x180055d29`
- `ADVAPI32!RegSetValueExW` at `0x180055de3`
- `ADVAPI32!RegSetValueExW` at `0x180055fbf`
- `ADVAPI32!RegSetValueExW` at `0x1800561b5`
- `ADVAPI32!RegSetValueExW` at `0x18005639f`
- `ADVAPI32!RegSetValueExW` at `0x18005669e`
- `ADVAPI32!RegSetValueExW` at `0x18005674b`
- `ADVAPI32!RegSetValueExW` at `0x180056807`
- `ADVAPI32!RegSetValueExW` at `0x1800568c3`

## string_xrefs

- `0x180056265`: `shell\open\command`
- `0x1800568b7`: `ApplicationCompany`

## pseudocode

```c
__int64 __fastcall CWorkspaceFileAssociation::SaveProgIdToRegistry(CWorkspaceFileAssociation *this, void *a2, HKEY a3)
{
  HKEY v3; // rbx
  __int64 v6; // rbx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  const WCHAR *v8; // rax
  int v9; // ebx
  unsigned int v10; // r14d
  unsigned int v11; // eax
  __int64 v12; // rax
  unsigned __int64 v13; // rdx
  unsigned int v14; // eax
  unsigned __int64 v15; // rcx
  unsigned int v16; // eax
  const BYTE *v17; // rax
  unsigned int v18; // r14d
  unsigned int v19; // eax
  unsigned int v20; // r14d
  unsigned int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rax
  const WCHAR *v24; // rax
  unsigned int v25; // r14d
  unsigned int v26; // eax
  const BYTE *v27; // rax
  unsigned int v28; // r14d
  unsigned int v29; // eax
  __int64 v30; // rax
  __int64 v31; // rax
  const WCHAR *v32; // rax
  unsigned int v33; // r14d
  unsigned int v34; // eax
  const BYTE *v35; // rax
  unsigned int v36; // r14d
  unsigned int v37; // eax
  __int64 v38; // rax
  __int64 v39; // rax
  const WCHAR *v40; // rax
  HANDLE v41; // r12
  unsigned int v42; // r14d
  unsigned int v43; // eax
  const BYTE *v44; // rax
  unsigned int v45; // r14d
  unsigned int v46; // eax
  __int64 v47; // rax
  __int64 v48; // rax
  const WCHAR *v49; // rax
  unsigned __int64 v50; // rdx
  unsigned int v51; // r14d
  unsigned int v52; // eax
  unsigned int v53; // eax
  char *v54; // rcx
  unsigned int v55; // eax
  const BYTE *v56; // rax
  DWORD v57; // r12d
  unsigned int v58; // r14d
  unsigned int v59; // eax
  const BYTE *v60; // rax
  unsigned int v61; // r14d
  unsigned int v62; // eax
  const BYTE *v63; // rax
  unsigned int v64; // r14d
  unsigned int v65; // eax
  const BYTE *v66; // rax
  unsigned int v67; // r14d
  unsigned int v68; // eax
  unsigned int v69; // eax
  unsigned int v70; // eax
  __int64 samDesired; // [rsp+28h] [rbp-130h]
  __int64 samDesireda; // [rsp+28h] [rbp-130h]
  HKEY phkResult; // [rsp+68h] [rbp-F0h] BYREF
  DWORD dwDisposition; // [rsp+70h] [rbp-E8h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-E0h] BYREF
  HANDLE v77; // [rsp+80h] [rbp-D8h] BYREF
  DWORD cbData; // [rsp+88h] [rbp-D0h] BYREF
  unsigned __int64 v79; // [rsp+90h] [rbp-C8h] BYREF
  BYTE Data[8]; // [rsp+98h] [rbp-C0h] BYREF
  __int64 v81; // [rsp+A0h] [rbp-B8h]
  _BYTE v82[16]; // [rsp+A8h] [rbp-B0h] BYREF
  unsigned __int64 v83; // [rsp+B8h] [rbp-A0h]
  _BYTE v84[32]; // [rsp+C8h] [rbp-90h] BYREF
  _BYTE v85[40]; // [rsp+E8h] [rbp-70h] BYREF

  v81 = -2;
  v3 = a3;
  hKey = a3;
  v77 = a2;
  phkResult = 0;
  dwDisposition = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 216);
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      (unsigned int)WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
      CurrentThreadActivityIdPrefix,
      v6);
    v3 = hKey;
  }
  v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 216);
  v9 = RegCreateKeyTransactedW(v3, v8, 0, 0, 0, 0x20006u, 0, &phkResult, &dwDisposition, a2, 0);
  if ( !v9 )
  {
    v12 = std::operator+<unsigned short>(v84, (char *)this + 112, L" ");
    std::operator+<unsigned short>(v82, v12, (char *)this + 48);
    std::wstring::~wstring(v84);
    v79 = 0;
    v9 = ULongLongMult(v83, v13, &v79);
    if ( v9 >= 0 )
    {
      v15 = v79 + 1;
      if ( v79 + 1 < v79 )
      {
        v79 = -1;
        v9 = -2147024362;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v70 = RdpWppGetCurrentThreadActivityIdPrefix();
          LODWORD(samDesired) = -2147024362;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            27,
            (unsigned int)WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
            v70,
            (__int64)"SizeTAdd(ProgID Friendly name length) failed",
            samDesired);
        }
        goto LABEL_197;
      }
      ++v79;
      cbData = 0;
      v9 = ULongLongToULong(v15, &cbData);
      if ( v9 >= 0 )
      {
        v17 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v82);
        v9 = RegSetValueExW(phkResult, 0, 0, 1u, v17, cbData);
        if ( v9 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            if ( v9 > 0 )
              v18 = (unsigned __int16)v9 | 0x80070000;
            else
              v18 = v9;
            v19 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              29,
              WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
              v19,
              v18);
          }
          if ( v9 > 0 )
            v9 = (unsigned __int16)v9 | 0x80070000;
        }
        else
        {
          *(_DWORD *)Data = 1;
          v9 = RegSetValueExW(phkResult, L"RemoteApp", 0, 4u, Data, 4u);
          if ( v9 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              if ( v9 > 0 )
                v20 = (unsigned __int16)v9 | 0x80070000;
              else
                v20 = v9;
              v21 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Dd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                30,
                WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
                v21,
                v20);
            }
            if ( v9 > 0 )
              v9 = (unsigned __int16)v9 | 0x80070000;
          }
          else
          {
            RegCloseKey(phkResult);
            phkResult = 0;
            v22 = std::operator+<unsigned short>(v85, (char *)this + 216, L"\\");
            v23 = std::operator+<unsigned short>(v84, v22, L"CurVer");
            v24 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
            v9 = RegCreateKeyTransactedW(hKey, v24, 0, 0, 0, 0x20006u, 0, &phkResult, &dwDisposition, a2, 0);
            std::wstring::~wstring(v84);
            std::wstring::~wstring(v85);
            if ( v9 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                if ( v9 > 0 )
                  v25 = (unsigned __int16)v9 | 0x80070000;
                else
                  v25 = v9;
                v26 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  31,
                  WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
                  v26,
                  v25);
              }
              if ( v9 > 0 )
                v9 = (unsigned __int16)v9 | 0x80070000;
            }
            else
            {
              v27 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 216);
              v9 = RegSetValueExW(phkResult, 0, 0, 1u, v27, 2 * *((_DWORD *)this + 58) + 2);
              if ( !v9 )
              {
                RegCloseKey(phkResult);
                phkResult = 0;
                if ( *((_QWORD *)this + 37) )
                {
                  v30 = std::operator+<unsigned short>(v84, (char *)this + 216, L"\\");
                  v31 = std::operator+<unsigned short>(v85, v30, L"DefaultIcon");
                  v32 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v31);
                  v9 = RegCreateKeyTransactedW(hKey, v32, 0, 0, 0, 0x20006u, 0, &phkResult, &dwDisposition, v77, 0);
                  std::wstring::~wstring(v85);
                  std::wstring::~wstring(v84);
                  if ( v9 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      if ( v9 > 0 )
                        v33 = (unsigned __int16)v9 | 0x80070000;
                      else
                        v33 = v9;
                      v34 = RdpWppGetCurrentThreadActivityIdPrefix();
                      WPP_SF_Dd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        33,
                        WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
                        v34,
                        v33);
                    }
                    if ( v9 > 0 )
                      v9 = (unsigned __int16)v9 | 0x80070000;
                    goto LABEL_197;
                  }
                  v35 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 280);
                  v9 = RegSetValueExW(phkResult, 0, 0, 1u, v35, 2 * *((_DWORD *)this + 74) + 2);
                  if ( v9 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      if ( v9 > 0 )
                        v36 = (unsigned __int16)v9 | 0x80070000;
                      else
                        v36 = v9;
                      v37 = RdpWppGetCurrentThreadActivityIdPrefix();
                      WPP_SF_Dd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        34,
                        WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
                        v37,
                        v36);
                    }
                    if ( v9 > 0 )
                      v9 = (unsigned __int16)v9 | 0x80070000;
                    goto LABEL_197;
                  }
                  RegCloseKey(phkResult);
                  phkResult = 0;
                }
                v38 = std::operator+<unsigned short>(v84, (char *)this + 216, L"\\");
                v39 = std::operator+<unsigned short>(v85, v38, L"shell\\open\\command");
                v40 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v39);
                v41 = v77;
                v9 = RegCreateKeyTransactedW(hKey, v40, 0, 0, 0, 0x20006u, 0, &phkResult, &dwDisposition, v77, 0);
                std::wstring::~wstring(v85);
                std::wstring::~wstring(v84);
                if ( v9 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                  {
                    if ( v9 > 0 )
                      v42 = (unsigned __int16)v9 | 0x80070000;
                    else
                      v42 = v9;
                    v43 = RdpWppGetCurrentThreadActivityIdPrefix();
                    WPP_SF_Dd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      35,
                      WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
                      v43,
                      v42);
                  }
                  if ( v9 > 0 )
                    v9 = (unsigned __int16)v9 | 0x80070000;
                }
                else
                {
                  v44 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 248);
                  v9 = RegSetValueExW(phkResult, 0, 0, 2u, v44, 2 * *((_DWORD *)this + 66) + 2);
                  if ( v9 )
                  {
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                    {
                      if ( v9 > 0 )
                        v45 = (unsigned __int16)v9 | 0x80070000;
                      else
                        v45 = v9;
                      v46 = RdpWppGetCurrentThreadActivityIdPrefix();
                      WPP_SF_Dd(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        36,
                        WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
                        v46,
                        v45);
                    }
                    if ( v9 > 0 )
                      v9 = (unsigned __int16)v9 | 0x80070000;
                  }
                  else
                  {
                    RegCloseKey(phkResult);
                    phkResult = 0;
                    v47 = std::operator+<unsigned short>(v84, (char *)this + 216, L"\\");
                    v48 = std::operator+<unsigned short>(v85, v47, L"Application");
                    v49 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v48);
                    v9 = RegCreateKeyTransactedW(hKey, v49, 0, 0, 0, 0x20006u, 0, &phkResult, &dwDisposition, v41, 0);
                    std::wstring::~wstring(v85);
                    std::wstring::~wstring(v84);
                    if ( v9 )
                    {
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        if ( v9 > 0 )
                          v51 = (unsigned __int16)v9 | 0x80070000;
                        else
                          v51 = v9;
                        v52 = RdpWppGetCurrentThreadActivityIdPrefix();
                        WPP_SF_Dd(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          37,
                          WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
                          v52,
                          v51);
                      }
                      if ( v9 > 0 )
                        v9 = (unsigned __int16)v9 | 0x80070000;
                    }
                    else
                    {
                      v77 = 0;
                      v9 = ULongLongMult(*((_QWORD *)this + 16), v50, (unsigned __int64 *)&v77);
                      if ( v9 >= 0 )
                      {
                        v54 = (char *)v77 + 1;
                        if ( (char *)v77 + 1 < v77 )
                        {
                          v77 = (HANDLE)-1LL;
                          v9 = -2147024362;
                          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                          {
                            v69 = RdpWppGetCurrentThreadActivityIdPrefix();
                            LODWORD(samDesireda) = -2147024362;
                            WPP_SF_DsD(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              39,
                              (unsigned int)WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
                              v69,
                              (__int64)"SizeTAdd(friendly name length) failed",
                              samDesireda);
                          }
                        }
                        else
                        {
                          v77 = (char *)v77 + 1;
                          LODWORD(hKey) = 0;
                          v9 = ULongLongToULong((unsigned __int64)v54, (unsigned int *)&hKey);
                          if ( v9 >= 0 )
                          {
                            v56 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 112);
                            v57 = (unsigned int)hKey;
                            v9 = RegSetValueExW(phkResult, L"ApplicationName", 0, 1u, v56, (DWORD)hKey);
                            if ( v9 )
                            {
                              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                              {
                                if ( v9 > 0 )
                                  v58 = (unsigned __int16)v9 | 0x80070000;
                                else
                                  v58 = v9;
                                v59 = RdpWppGetCurrentThreadActivityIdPrefix();
                                WPP_SF_Dd(
                                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                                  41,
                                  WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
                                  v59,
                                  v58);
                              }
                              if ( v9 > 0 )
                                v9 = (unsigned __int16)v9 | 0x80070000;
                            }
                            else
                            {
                              v60 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 112);
                              v9 = RegSetValueExW(phkResult, L"ApplicationDescription", 0, 1u, v60, v57);
                              if ( v9 )
                              {
                                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                {
                                  if ( v9 > 0 )
                                    v61 = (unsigned __int16)v9 | 0x80070000;
                                  else
                                    v61 = v9;
                                  v62 = RdpWppGetCurrentThreadActivityIdPrefix();
                                  WPP_SF_Dd(
                                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                                    42,
                                    WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
                                    v62,
                                    v61);
                                }
                                if ( v9 > 0 )
                                  v9 = (unsigned __int16)v9 | 0x80070000;
                              }
                              else
                              {
                                v63 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 144);
                                v9 = RegSetValueExW(
                                       phkResult,
                                       L"ApplicationIcon",
                                       0,
                                       1u,
                                       v63,
                                       2 * *((_DWORD *)this + 40) + 2);
                                if ( v9 )
                                {
                                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                  {
                                    if ( v9 > 0 )
                                      v64 = (unsigned __int16)v9 | 0x80070000;
                                    else
                                      v64 = v9;
                                    v65 = RdpWppGetCurrentThreadActivityIdPrefix();
                                    WPP_SF_Dd(
                                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                                      43,
                                      WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
                                      v65,
                                      v64);
                                  }
                                  if ( v9 > 0 )
                                    v9 = (unsigned __int16)v9 | 0x80070000;
                                }
                                else
                                {
                                  v66 = (const BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 176);
                                  v9 = RegSetValueExW(
                                         phkResult,
                                         L"ApplicationCompany",
                                         0,
                                         1u,
                                         v66,
                                         2 * *((_DWORD *)this + 48) + 2);
                                  if ( !v9 )
                                  {
                                    v9 = 0;
                                    std::wstring::~wstring(v82);
                                    goto LABEL_198;
                                  }
                                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                                  {
                                    if ( v9 > 0 )
                                      v67 = (unsigned __int16)v9 | 0x80070000;
                                    else
                                      v67 = v9;
                                    v68 = RdpWppGetCurrentThreadActivityIdPrefix();
                                    WPP_SF_Dd(
                                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                                      44,
                                      WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
                                      v68,
                                      v67);
                                  }
                                  if ( v9 > 0 )
                                    v9 = (unsigned __int16)v9 | 0x80070000;
                                }
                              }
                            }
                          }
                          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                          {
                            v55 = RdpWppGetCurrentThreadActivityIdPrefix();
                            LODWORD(samDesireda) = v9;
                            WPP_SF_DsD(
                              *((_QWORD *)WPP_GLOBAL_Control + 2),
                              40,
                              (unsigned int)WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
                              v55,
                              (__int64)"SizeTToDWord(friendly name length) failed",
                              samDesireda);
                          }
                        }
                      }
                      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                      {
                        v53 = RdpWppGetCurrentThreadActivityIdPrefix();
                        LODWORD(samDesireda) = v9;
                        WPP_SF_DsD(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          38,
                          (unsigned int)WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
                          v53,
                          (__int64)"SizeTMult(friendly name length) failed",
                          samDesireda);
                      }
                    }
                  }
                }
                goto LABEL_197;
              }
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                if ( v9 > 0 )
                  v28 = (unsigned __int16)v9 | 0x80070000;
                else
                  v28 = v9;
                v29 = RdpWppGetCurrentThreadActivityIdPrefix();
                WPP_SF_Dd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  32,
                  WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
                  v29,
                  v28);
              }
              if ( v9 > 0 )
                v9 = (unsigned __int16)v9 | 0x80070000;
            }
          }
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(samDesired) = v9;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          (unsigned int)WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
          v16,
          (__int64)"SizeTToDWord(ProgID friendly name length) failed",
          samDesired);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(samDesired) = v9;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        26,
        (unsigned int)WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids,
        v14,
        (__int64)"SizeTMult(ProgID friendly name length) failed",
        samDesired);
    }
LABEL_197:
    std::wstring::~wstring(v82);
    goto LABEL_198;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    else
      v10 = v9;
    v11 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids, v11, v10);
  }
  if ( v9 > 0 )
    v9 = (unsigned __int16)v9 | 0x80070000;
LABEL_198:
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180055a18  push    rbx
0x180055a1a  push    rsi
0x180055a1b  push    rdi
0x180055a1c  push    r12
0x180055a1e  push    r13
0x180055a20  push    r14
0x180055a22  push    r15
0x180055a24  sub     rsp, 120h
0x180055a2b  mov     [rsp+158h+var_B8], 0FFFFFFFFFFFFFFFEh
0x180055a37  mov     rax, cs:__security_cookie
0x180055a3e  xor     rax, rsp
0x180055a41  mov     [rsp+158h+var_48], rax
0x180055a49  mov     rbx, r8
0x180055a4c  mov     [rsp+158h+hKey], rbx
0x180055a51  mov     r12, rdx
0x180055a54  mov     [rsp+158h+var_D8], rdx
0x180055a5c  mov     r15, rcx
0x180055a5f  xor     edi, edi
0x180055a61  mov     [rsp+158h+var_F0], rdi
0x180055a66  mov     [rsp+158h+dwDisposition], edi
0x180055a6a  lea     rcx, WPP_GLOBAL_Control
0x180055a71  mov     rax, cs:WPP_GLOBAL_Control
0x180055a78  lea     r14d, [rdi+1]
0x180055a7c  cmp     rax, rcx
0x180055a7f  jz      short loc_180055ACD
0x180055a81  test    [rax+1Ch], r14b
0x180055a85  jz      short loc_180055ACD
0x180055a87  cmp     byte ptr [rax+19h], 4
0x180055a8b  jb      short loc_180055ACD
0x180055a8d  lea     rcx, [r15+0D8h]
0x180055a94  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180055a99  mov     rbx, rax
0x180055a9c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180055aa1  lea     edx, [rdi+18h]
0x180055aa4  mov     qword ptr [rsp+158h+dwOptions], rbx
0x180055aa9  mov     r9d, eax
0x180055aac  lea     rsi, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180055ab3  mov     r8, rsi
0x180055ab6  mov     rcx, cs:WPP_GLOBAL_Control
0x180055abd  mov     rcx, [rcx+10h]
0x180055ac1  call    WPP_SF_DS
0x180055ac6  mov     rbx, [rsp+158h+hKey]
0x180055acb  jmp     short loc_180055AD4
0x180055acd  lea     rsi, WPP_1b4a91e28c533a877c5d59eaaa244463_Traceguids
0x180055ad4  lea     r13, [r15+0D8h]
0x180055adb  mov     rcx, r13
0x180055ade  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180055ae3  mov     [rsp+158h+pExtendedParemeter], rdi; pExtendedParemeter
0x180055ae8  mov     [rsp+158h+hTransaction], r12; hTransaction
0x180055aed  lea     rcx, [rsp+158h+dwDisposition]
0x180055af2  mov     [rsp+158h+lpdwDisposition], rcx; lpdwDisposition
0x180055af7  lea     rcx, [rsp+158h+var_F0]
0x180055afc  mov     [rsp+158h+phkResult], rcx; phkResult
0x180055b01  mov     [rsp+158h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180055b06  mov     dword ptr [rsp+158h+samDesired], 20006h; samDesired
0x180055b0e  mov     [rsp+158h+dwOptions], edi; dwOptions
0x180055b12  xor     r9d, r9d; lpClass
0x180055b15  xor     r8d, r8d; Reserved
0x180055b18  mov     rdx, rax; lpSubKey
0x180055b1b  mov     rcx, rbx; hKey
0x180055b1e  call    cs:__imp_RegCreateKeyTransactedW
0x180055b24  mov     ebx, eax
0x180055b26  test    eax, eax
0x180055b28  jz      short loc_180055B98
0x180055b2a  mov     rax, cs:WPP_GLOBAL_Control
0x180055b31  lea     rcx, WPP_GLOBAL_Control
0x180055b38  cmp     rax, rcx
0x180055b3b  jz      short loc_180055B82
0x180055b3d  test    byte ptr [rax+1Ch], 8
0x180055b41  jz      short loc_180055B82
0x180055b43  cmp     byte ptr [rax+19h], 2
0x180055b47  jb      short loc_180055B82
0x180055b49  test    ebx, ebx
0x180055b4b  jg      short loc_180055B52
0x180055b4d  mov     r14d, ebx
0x180055b50  jmp     short loc_180055B5D
0x180055b52  movzx   r14d, bx
0x180055b56  or      r14d, 80070000h
0x180055b5d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180055b62  mov     edx, 19h
0x180055b67  mov     [rsp+158h+dwOptions], r14d
0x180055b6c  mov     r9d, eax
0x180055b6f  mov     r8, rsi
0x180055b72  mov     rcx, cs:WPP_GLOBAL_Control
0x180055b79  mov     rcx, [rcx+10h]
0x180055b7d  call    WPP_SF_Dd
0x180055b82  test    ebx, ebx
0x180055b84  jle     short loc_180055B8F
0x180055b86  movzx   ebx, bx
0x180055b89  or      ebx, 80070000h
0x180055b8f  mov     [rsp+158h+var_F8], ebx
0x180055b93  jmp     loc_180056A5C
0x180055b98  lea     rdx, [r15+70h]
0x180055b9c  lea     r8, asc_1800B7ECC; " "
0x180055ba3  lea     rcx, [rsp+158h+var_90]
0x180055bab  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x180055bb0  nop
0x180055bb1  lea     r8, [r15+30h]
0x180055bb5  mov     rdx, rax
0x180055bb8  lea     rcx, [rsp+158h+var_B0]
0x180055bc0  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180055bc5  nop
0x180055bc6  lea     rcx, [rsp+158h+var_90]; void *
0x180055bce  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180055bd3  mov     [rsp+158h+var_C8], rdi
0x180055bdb  lea     r8, [rsp+158h+var_C8]; unsigned __int64 *
0x180055be3  mov     rcx, [rsp+158h+var_A0]; unsigned __int64
0x180055beb  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180055bf0  mov     ebx, eax
0x180055bf2  mov     [rsp+158h+var_F8], eax
0x180055bf6  test    eax, eax
0x180055bf8  jns     short loc_180055C5D
0x180055bfa  mov     rax, cs:WPP_GLOBAL_Control
0x180055c01  lea     rcx, WPP_GLOBAL_Control
0x180055c08  cmp     rax, rcx
0x180055c0b  jz      short loc_180055C4A
0x180055c0d  test    byte ptr [rax+1Ch], 8
0x180055c11  jz      short loc_180055C4A
0x180055c13  cmp     byte ptr [rax+19h], 2
0x180055c17  jb      short loc_180055C4A
0x180055c19  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180055c1e  mov     edx, 1Ah
0x180055c23  mov     dword ptr [rsp+158h+samDesired], ebx
0x180055c27  lea     rcx, aSizetmultProgi; "SizeTMult(ProgID friendly name length) "...
0x180055c2e  mov     qword ptr [rsp+158h+dwOptions], rcx
0x180055c33  mov     r9d, eax
0x180055c36  mov     r8, rsi
0x180055c39  mov     rcx, cs:WPP_GLOBAL_Control
0x180055c40  mov     rcx, [rcx+10h]
0x180055c44  call    WPP_SF_DsD
0x180055c49  nop
0x180055c4a  lea     rcx, [rsp+158h+var_B0]; void *
0x180055c52  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180055c57  nop
0x180055c58  jmp     loc_180056A5C
0x180055c5d  mov     rax, [rsp+158h+var_C8]
0x180055c65  lea     rcx, [rax+1]; unsigned __int64
0x180055c69  cmp     rcx, rax
0x180055c6c  jb      loc_1800569DD
0x180055c72  mov     [rsp+158h+var_C8], rcx
0x180055c7a  mov     [rsp+158h+var_F8], edi
0x180055c7e  mov     [rsp+158h+cbData], edi
0x180055c85  lea     rdx, [rsp+158h+cbData]; unsigned int *
0x180055c8d  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x180055c92  mov     ebx, eax
0x180055c94  mov     [rsp+158h+var_F8], eax
0x180055c98  test    eax, eax
0x180055c9a  jns     short loc_180055CFF
0x180055c9c  mov     rax, cs:WPP_GLOBAL_Control
0x180055ca3  lea     rcx, WPP_GLOBAL_Control
0x180055caa  cmp     rax, rcx
0x180055cad  jz      short loc_180055CEC
0x180055caf  test    byte ptr [rax+1Ch], 8
0x180055cb3  jz      short loc_180055CEC
0x180055cb5  cmp     byte ptr [rax+19h], 2
0x180055cb9  jb      short loc_180055CEC
0x180055cbb  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180055cc0  mov     edx, 1Ch
0x180055cc5  mov     dword ptr [rsp+158h+samDesired], ebx
0x180055cc9  lea     rcx, aSizettodwordPr; "SizeTToDWord(ProgID friendly name lengt"...
0x180055cd0  mov     qword ptr [rsp+158h+dwOptions], rcx
0x180055cd5  mov     r9d, eax
0x180055cd8  mov     r8, rsi
0x180055cdb  mov     rcx, cs:WPP_GLOBAL_Control
0x180055ce2  mov     rcx, [rcx+10h]
0x180055ce6  call    WPP_SF_DsD
0x180055ceb  nop
0x180055cec  lea     rcx, [rsp+158h+var_B0]; void *
0x180055cf4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180055cf9  nop
0x180055cfa  jmp     loc_180056A5C
0x180055cff  lea     rcx, [rsp+158h+var_B0]
0x180055d07  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180055d0c  mov     edx, [rsp+158h+cbData]
0x180055d13  mov     dword ptr [rsp+158h+samDesired], edx; cbData
0x180055d17  mov     qword ptr [rsp+158h+dwOptions], rax; lpData
0x180055d1c  mov     r9d, r14d; dwType
0x180055d1f  xor     r8d, r8d; Reserved
0x180055d22  xor     edx, edx; lpValueName
0x180055d24  mov     rcx, [rsp+158h+var_F0]; hKey
0x180055d29  call    cs:__imp_RegSetValueExW
0x180055d2f  mov     ebx, eax
0x180055d31  test    eax, eax
0x180055d33  jz      short loc_180055DB1
0x180055d35  mov     rax, cs:WPP_GLOBAL_Control
0x180055d3c  lea     rcx, WPP_GLOBAL_Control
0x180055d43  cmp     rax, rcx
0x180055d46  jz      short loc_180055D8D
0x180055d48  test    byte ptr [rax+1Ch], 8
0x180055d4c  jz      short loc_180055D8D
0x180055d4e  cmp     byte ptr [rax+19h], 2
0x180055d52  jb      short loc_180055D8D
0x180055d54  test    ebx, ebx
0x180055d56  jg      short loc_180055D5D
0x180055d58  mov     r14d, ebx
0x180055d5b  jmp     short loc_180055D68
0x180055d5d  movzx   r14d, bx
0x180055d61  or      r14d, 80070000h
0x180055d68  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180055d6d  mov     edx, 1Dh
0x180055d72  mov     [rsp+158h+dwOptions], r14d
0x180055d77  mov     r9d, eax
0x180055d7a  mov     r8, rsi
0x180055d7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180055d84  mov     rcx, [rcx+10h]
0x180055d88  call    WPP_SF_Dd
0x180055d8d  test    ebx, ebx
0x180055d8f  jle     short loc_180055D9A
0x180055d91  movzx   ebx, bx
0x180055d94  or      ebx, 80070000h
0x180055d9a  mov     [rsp+158h+var_F8], ebx
0x180055d9e  lea     rcx, [rsp+158h+var_B0]; void *
0x180055da6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180055dab  nop
0x180055dac  jmp     loc_180056A5C
0x180055db1  mov     dword ptr [rsp+158h+Data], r14d
0x180055db9  mov     dword ptr [rsp+158h+samDesired], 4; cbData
0x180055dc1  lea     rax, [rsp+158h+Data]
0x180055dc9  mov     qword ptr [rsp+158h+dwOptions], rax; lpData
0x180055dce  mov     r9d, 4; dwType
0x180055dd4  xor     r8d, r8d; Reserved
0x180055dd7  lea     rdx, aRemoteapp; "RemoteApp"
0x180055dde  mov     rcx, [rsp+158h+var_F0]; hKey
0x180055de3  call    cs:__imp_RegSetValueExW
0x180055de9  mov     ebx, eax
0x180055deb  test    eax, eax
0x180055ded  jz      short loc_180055E6B
0x180055def  mov     rax, cs:WPP_GLOBAL_Control
0x180055df6  lea     rcx, WPP_GLOBAL_Control
0x180055dfd  cmp     rax, rcx
0x180055e00  jz      short loc_180055E47
0x180055e02  test    byte ptr [rax+1Ch], 8
0x180055e06  jz      short loc_180055E47
0x180055e08  cmp     byte ptr [rax+19h], 2
0x180055e0c  jb      short loc_180055E47
0x180055e0e  test    ebx, ebx
0x180055e10  jg      short loc_180055E17
0x180055e12  mov     r14d, ebx
0x180055e15  jmp     short loc_180055E22
0x180055e17  movzx   r14d, bx
0x180055e1b  or      r14d, 80070000h
0x180055e22  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180055e27  mov     edx, 1Eh
0x180055e2c  mov     [rsp+158h+dwOptions], r14d
0x180055e31  mov     r9d, eax
0x180055e34  mov     r8, rsi
0x180055e37  mov     rcx, cs:WPP_GLOBAL_Control
0x180055e3e  mov     rcx, [rcx+10h]
0x180055e42  call    WPP_SF_Dd
0x180055e47  test    ebx, ebx
0x180055e49  jle     short loc_180055E54
0x180055e4b  movzx   ebx, bx
0x180055e4e  or      ebx, 80070000h
0x180055e54  mov     [rsp+158h+var_F8], ebx
0x180055e58  lea     rcx, [rsp+158h+var_B0]; void *
0x180055e60  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180055e65  nop
0x180055e66  jmp     loc_180056A5C
0x180055e6b  mov     rcx, [rsp+158h+var_F0]; hKey
0x180055e70  call    cs:__imp_RegCloseKey
0x180055e76  mov     [rsp+158h+var_F0], rdi
0x180055e7b  lea     r8, SubStr; "\\"
0x180055e82  mov     rdx, r13
0x180055e85  lea     rcx, [rsp+158h+var_70]
0x180055e8d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x180055e92  nop
0x180055e93  lea     r8, aCurver; "CurVer"
0x180055e9a  mov     rdx, rax
0x180055e9d  lea     rcx, [rsp+158h+var_90]
0x180055ea5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x180055eaa  nop
0x180055eab  mov     rcx, rax
0x180055eae  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180055eb3  mov     [rsp+158h+pExtendedParemeter], rdi; pExtendedParemeter
0x180055eb8  mov     [rsp+158h+hTransaction], r12; hTransaction
0x180055ebd  lea     rcx, [rsp+158h+dwDisposition]
0x180055ec2  mov     [rsp+158h+lpdwDisposition], rcx; lpdwDisposition
0x180055ec7  lea     rcx, [rsp+158h+var_F0]
0x180055ecc  mov     [rsp+158h+phkResult], rcx; phkResult
0x180055ed1  mov     [rsp+158h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180055ed6  mov     dword ptr [rsp+158h+samDesired], 20006h; samDesired
0x180055ede  mov     [rsp+158h+dwOptions], edi; dwOptions
0x180055ee2  xor     r9d, r9d; lpClass
0x180055ee5  xor     r8d, r8d; Reserved
0x180055ee8  mov     rdx, rax; lpSubKey
0x180055eeb  mov     rcx, [rsp+158h+hKey]; hKey
0x180055ef0  call    cs:__imp_RegCreateKeyTransactedW
0x180055ef6  mov     ebx, eax
0x180055ef8  lea     rcx, [rsp+158h+var_90]; void *
0x180055f00  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180055f05  nop
0x180055f06  lea     rcx, [rsp+158h+var_70]; void *
0x180055f0e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180055f13  test    ebx, ebx
0x180055f15  jz      short loc_180055F93
0x180055f17  mov     rax, cs:WPP_GLOBAL_Control
0x180055f1e  lea     rcx, WPP_GLOBAL_Control
0x180055f25  cmp     rax, rcx
0x180055f28  jz      short loc_180055F6F
0x180055f2a  test    byte ptr [rax+1Ch], 8
  ... truncated ...
```
