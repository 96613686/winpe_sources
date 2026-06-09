# Common::UserProfile::GetUserProfileFolderPath(Common::UserProfile::PROFILE_FOLDER_ID,ushort const *,Common::StringBuffer &)

- ea: `0x18004d3b0`
- end: `0x18004dd61`
- name: `?GetUserProfileFolderPath@UserProfile@Common@@YAJW4PROFILE_FOLDER_ID@12@PEBGAEAVStringBuffer@2@@Z`
- size: `2481`
- prototype: `int __high(enum Common::UserProfile::PROFILE_FOLDER_ID, const unsigned __int16 *, struct Common::StringBuffer *)`
- caller_count: `4`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18004cdd0`
- `0x1800649e0`
- `0x180065e74`
- `0x180066490`

## callees

- `0x180020b70`
- `0x18004c240`
- `0x18004cdd0`
- `0x18004d3b0`
- `0x18004df24`
- `0x18004eda0`
- `0x18004fd70`
- `0x180056ec0`
- `0x180058768`
- `0x180058790`
- `0x1800588a0`
- `0x180059e60`
- `0x18005b460`
- `0x18005b710`
- `0x1800689c8`
- `0x1800e48ac`
- `0x18011f9a8`

## import_xrefs

- `ntdll!RtlExpandEnvironmentStrings` at `0x18004d64b`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18004d6a4`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18004db98`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18004dbfa`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18004d64b`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18004d6a4`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18004db98`
- `ntdll!RtlExpandEnvironmentStrings` at `0x18004dbfa`
- `ntdll!RtlFreeHeap` at `0x18004d75c`
- `ntdll!RtlFreeHeap` at `0x18004d75c`

## string_xrefs

- `0x18004d736`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18004d7ba`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18004d7d6`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18004d86a`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18004d8bf`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18004d93b`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18004da15`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18004da53`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18004da69`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18004db0f`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18004dc3f`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18004dc82`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18004dcb0`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18004dccc`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18004dd34`: `onecore\base\appmodel\common\userprofile.cpp`
- `0x18004d4d5`: `ProfileImagePath`
- `0x18004d71e`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18004d842`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18004d923`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18004d9b4`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18004d9fd`: `onecore\base\appmodel\common\widestring.cpp`
- `0x18004d852`: `onecore\base\appmodel\common\registrykey.cpp`
- `0x18004db52`: `%PROGRAMDATA%`

## pseudocode

```c
__int64 __fastcall Common::UserProfile::GetUserProfileFolderPath(
        int a1,
        const WCHAR *a2,
        Common::StringBuffer *a3,
        const char *a4)
{
  __int64 v5; // r15
  _WORD *v6; // rdx
  int v8; // ecx
  __int64 v9; // rax
  __int64 v11; // rdi
  WCHAR *v12; // rsi
  int v13; // eax
  HRESULT v14; // eax
  unsigned int v15; // ebx
  int v16; // eax
  BYTE *v17; // rdi
  unsigned int v18; // r13d
  unsigned int v19; // eax
  unsigned int v20; // r12d
  LSTATUS v21; // eax
  DWORD v22; // edx
  int v23; // eax
  bool v24; // cf
  __int64 v25; // r15
  int v26; // eax
  int v27; // ecx
  unsigned int v28; // ebx
  PWSTR v29; // rbx
  int v30; // eax
  int v31; // eax
  int v32; // eax
  unsigned int v33; // r14d
  WCHAR *v34; // rcx
  int v36; // eax
  unsigned int v37; // esi
  int UserProfileFolderPathFromSid; // eax
  unsigned int v39; // ebx
  HKEY v40; // rcx
  __int64 v41; // r9
  __int64 v42; // rdx
  PWSTR v43; // rcx
  int v44; // eax
  unsigned int v45; // r12d
  int v46; // eax
  int v47; // eax
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rsi
  PWSTR v51; // rbx
  int v52; // eax
  int v53; // eax
  unsigned int v54; // edi
  int v55; // eax
  unsigned __int16 *v56; // rdi
  int v57; // eax
  int v58; // eax
  unsigned int v59; // edi
  unsigned int v60; // ebx
  int dwFlags; // [rsp+20h] [rbp-29h]
  int dwFlagsa; // [rsp+20h] [rbp-29h]
  int dwFlagsb; // [rsp+20h] [rbp-29h]
  int dwFlagsc; // [rsp+20h] [rbp-29h]
  int dwFlagsd; // [rsp+20h] [rbp-29h]
  int dwFlagse; // [rsp+20h] [rbp-29h]
  int dwFlagsh; // [rsp+20h] [rbp-29h]
  int dwFlagsi; // [rsp+20h] [rbp-29h]
  int dwFlagsj; // [rsp+20h] [rbp-29h]
  int dwFlagsk; // [rsp+20h] [rbp-29h]
  int dwFlagsf; // [rsp+20h] [rbp-29h]
  int dwFlagsg; // [rsp+20h] [rbp-29h]
  __int64 v73; // [rsp+30h] [rbp-19h] BYREF
  __int64 v74; // [rsp+38h] [rbp-11h] BYREF
  LPBYTE lpData[2]; // [rsp+40h] [rbp-9h] BYREF
  int v76; // [rsp+50h] [rbp+7h]
  PWSTR pszPathOut[2]; // [rsp+58h] [rbp+Fh] BYREF
  int v78; // [rsp+68h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]
  DWORD cbData; // [rsp+B0h] [rbp+67h] BYREF
  HKEY hKey; // [rsp+C0h] [rbp+77h] BYREF
  void *v82; // [rsp+C8h] [rbp+7Fh] BYREF

  LODWORD(v5) = 0;
  v6 = (_WORD *)*((_QWORD *)a3 + 1);
  if ( v6 )
    *v6 = 0;
  *(_DWORD *)a3 = 0;
  if ( a1 == 5 )
  {
    v8 = 0;
    *(_OWORD *)pszPathOut = 0;
    v78 = 0;
    v9 = -1;
    while ( a2[++v9] != 0 )
      ;
    v11 = (unsigned int)(v9 + 57);
    if ( (_DWORD)v9 == -57 )
    {
      v12 = pszPathOut[1];
LABEL_8:
      LODWORD(pszPathOut[0]) = v11;
      v13 = 0;
      if ( v8 )
        v13 = v8 - 1;
      v14 = PathCchCombineEx(
              v12,
              (unsigned int)(v13 + 1),
              L"Software\\Microsoft\\Windows NT\\CurrentVersion\\ProfileList",
              a2,
              0);
      v15 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7D,
          (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
          (const char *)(unsigned int)v14,
          dwFlagsa);
      }
      else
      {
        hKey = 0;
        v16 = RegOpenKeyExInternalW(HKEY_LOCAL_MACHINE, v12, (PHANDLE)&hKey, 0);
        v15 = v16;
        if ( v16 > 0 )
          v15 = (unsigned __int16)v16 | 0x80070000;
        if ( (v15 & 0x80000000) == 0 )
        {
          v76 = 0;
          *(_OWORD *)lpData = 0;
          v17 = 0;
          v18 = 0;
          while ( 1 )
          {
            if ( v17 )
            {
              v19 = 0;
              if ( v18 )
                v19 = v18 - 1;
              v20 = v19 + 1;
            }
            else
            {
              v20 = 0;
            }
            cbData = 2 * v20;
            v21 = RegQueryValueExW(hKey, L"ProfileImagePath", 0, 0, v17, &cbData);
            v15 = v21;
            if ( !v21 || v21 == 234 )
            {
              if ( (cbData & 1) != 0 )
              {
                v15 = -2147024883;
                goto LABEL_50;
              }
              v22 = cbData >> 1;
              if ( !(cbData >> 1) )
              {
                LODWORD(v5) = 0;
                goto LABEL_25;
              }
              if ( v21 || !v17 )
              {
                LODWORD(v5) = v22 - 1;
LABEL_25:
                if ( v21 <= 0 )
                  goto LABEL_28;
LABEL_26:
                v15 = (unsigned __int16)v15;
LABEL_27:
                v15 |= 0x80070000;
                goto LABEL_28;
              }
              v5 = v22 - 1;
              if ( *(_WORD *)&v17[2 * v5] )
              {
                LODWORD(v5) = v22 + 1;
                if ( v22 + 1 > v20 )
                {
                  LOWORD(v15) = 234;
                  goto LABEL_26;
                }
                LODWORD(v5) = cbData >> 1;
                *(_WORD *)&v17[2 * v22] = 0;
              }
            }
            else if ( v21 > 0 )
            {
              v15 = (unsigned __int16)v21;
              goto LABEL_27;
            }
LABEL_28:
            if ( v15 )
            {
              if ( v15 != -2147024662 )
                goto LABEL_50;
            }
            else if ( (unsigned int)v5 <= v20 )
            {
              if ( v18 )
                --v18;
              if ( (unsigned int)v5 > v18 )
              {
                v46 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)lpData, v5);
                v15 = v46;
                if ( v46 < 0 )
                {
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x20C,
                    (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
                    (const char *)(unsigned int)v46,
                    dwFlagsc);
                  v17 = lpData[1];
                  goto LABEL_50;
                }
                v17 = lpData[1];
              }
              LODWORD(lpData[0]) = v5;
              if ( (_DWORD)v5 )
                *(_WORD *)&v17[2 * (unsigned int)v5] = 0;
              v15 = 0;
LABEL_50:
              if ( (v15 & 0x80000000) != 0 )
                goto LABEL_85;
              v25 = LODWORD(lpData[0]);
              v73 = 0;
              v26 = RtlExpandEnvironmentStrings(0, v17, LODWORD(lpData[0]), 0, 0, &v73);
              if ( v26 != -1073741789 && v26 < 0 )
              {
                v60 = wil::details::in1diag3::Return_NtStatus(
                        retaddr,
                        (void *)0x8E,
                        (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
                        (const char *)(unsigned int)v26,
                        dwFlagsd);
                Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpData);
                if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
                  RegCloseKey(hKey);
                Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pszPathOut);
                return v60;
              }
              v27 = 0;
              v78 = 0;
              *(_OWORD *)pszPathOut = 0;
              v28 = v73 - 1;
              if ( (_DWORD)v73 == 1 )
              {
                v29 = pszPathOut[1];
                goto LABEL_54;
              }
              v44 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)pszPathOut, v28);
              v45 = v44;
              if ( v44 < 0 )
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x20C,
                  (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
                  (const char *)(unsigned int)v44,
                  dwFlagsd);
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x92,
                  (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
                  (const char *)v45,
                  dwFlagsj);
                if ( pszPathOut[1] )
                  Common::GlobalHeap::Free(pszPathOut[1]);
                if ( v17 )
                  Common::GlobalHeap::Free(v17);
                if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
                  RegCloseKey(hKey);
                if ( v12 )
                  Common::GlobalHeap::Free(v12);
                return v45;
              }
              v49 = v28;
              v29 = pszPathOut[1];
              pszPathOut[1][v49] = 0;
              v27 = v78;
LABEL_54:
              v74 = 0;
              v30 = 0;
              if ( v27 )
                v30 = v27 - 1;
              v31 = RtlExpandEnvironmentStrings(0, v17, v25, v29, (unsigned int)(v30 + 1), &v74);
              if ( v31 < 0 )
              {
                v33 = wil::details::in1diag3::Return_NtStatus(
                        retaddr,
                        (void *)0x9B,
                        (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
                        (const char *)(unsigned int)v31,
                        dwFlagse);
                if ( v29 )
                  Common::GlobalHeap::Free(v29);
                if ( v17 )
                  Common::GlobalHeap::Free(v17);
                v40 = hKey;
                if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
                  goto LABEL_98;
              }
              else
              {
                v32 = Common::StringBuffer::SetValueFromString(a3, v29);
                v33 = v32;
                if ( v32 >= 0 )
                {
                  if ( v29 )
                    Common::GlobalHeap::Free(v29);
                  if ( v17 )
                    Common::GlobalHeap::Free(v17);
                  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
                    RegCloseKey(hKey);
                  if ( v12 )
                  {
                    v34 = v12;
                    goto LABEL_66;
                  }
                  return 0;
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x9D,
                  (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
                  (const char *)(unsigned int)v32,
                  dwFlagse);
                if ( v29 )
                  Common::GlobalHeap::Free(v29);
                if ( v17 )
                  Common::GlobalHeap::Free(v17);
                v40 = hKey;
                if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
LABEL_98:
                  RegCloseKey(v40);
              }
              if ( v12 )
                Common::GlobalHeap::Free(v12);
              return v33;
            }
            if ( (unsigned int)v5 > 0x3FFFFFFF )
            {
              v15 = -2147023613;
              v42 = 425;
              v41 = 2147943683LL;
LABEL_84:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v42,
                (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
                (const char *)v41,
                dwFlagsc);
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2D8,
                (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
                (const char *)v15,
                dwFlagsi);
LABEL_85:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x82,
                (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
                (const char *)v15,
                dwFlagsc);
              if ( v17 )
                Common::GlobalHeap::Free(v17);
              goto LABEL_87;
            }
            if ( (_DWORD)v5 )
            {
              if ( (_DWORD)v5 + 1 == v18 )
              {
                LODWORD(v5) = 0;
              }
              else
              {
                v82 = 0;
                v23 = CommonHeapReAllocDefault(v17, 2LL * v18, 2LL * (unsigned int)(v5 + 1), &v82);
                v15 = v23;
                if ( v23 < 0 )
                {
                  v41 = (unsigned int)v23;
                  v42 = 458;
                  goto LABEL_84;
                }
                v17 = (BYTE *)v82;
                v18 = v5 + 1;
                lpData[1] = (LPBYTE)v82;
                v76 = v5 + 1;
                v24 = LODWORD(lpData[0]) < (unsigned int)v5;
                if ( LODWORD(lpData[0]) > (unsigned int)v5 )
                {
                  v48 = (unsigned int)v5;
                  LODWORD(lpData[0]) = v5;
                  LODWORD(v5) = 0;
                  *((_WORD *)v82 + v48) = 0;
                }
                else
                {
                  LODWORD(v5) = 0;
                  if ( v24 && !LODWORD(lpData[0]) )
                    *(_WORD *)v82 = 0;
                }
              }
            }
            else
            {
              if ( v17 )
              {
                Common::GlobalHeap::Free(v17);
                LODWORD(v5) = 0;
                v17 = 0;
                lpData[1] = 0;
                LODWORD(lpData[0]) = 0;
              }
              else
              {
                LODWORD(v5) = 0;
              }
              v18 = 0;
              v76 = 0;
            }
          }
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x80,
          (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
          (const char *)v15,
          dwFlagsb);
LABEL_87:
        if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
          RegCloseKey(hKey);
      }
      if ( !v12 )
        return v15;
      v43 = v12;
LABEL_91:
      Common::GlobalHeap::Free(v43);
      return v15;
    }
    v36 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)pszPathOut, v11);
    v37 = v36;
    if ( v36 >= 0 )
    {
      v12 = pszPathOut[1];
      v8 = v78;
      pszPathOut[1][v11] = 0;
      goto LABEL_8;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x20C,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)(unsigned int)v36,
      dwFlags);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
      (const char *)v37,
      dwFlagsh);
    if ( pszPathOut[1] )
      RtlFreeHeap(ReservedForLocalUse::g_heap, 0, pszPathOut[1]);
    return v37;
  }
  if ( a1 == 6 )
  {
    UserProfileFolderPathFromSid = GetUserProfileFolderPathFromSid(a2, L"Local AppData", a3);
    v39 = UserProfileFolderPathFromSid;
    if ( UserProfileFolderPathFromSid < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA5,
        (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
        (const char *)(unsigned int)UserProfileFolderPathFromSid,
        dwFlags);
      return v39;
    }
    return 0;
  }
  if ( a1 != 4 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xCA,
      (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
      a4);
  v78 = 0;
  *(_OWORD *)pszPathOut = 0;
  v47 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)pszPathOut, 0xDu);
  v15 = v47;
  if ( v47 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x20C,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)(unsigned int)v47,
      dwFlags);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAA,
      (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
      (const char *)v15,
      dwFlagsk);
    v43 = pszPathOut[1];
    if ( !pszPathOut[1] )
      return v15;
    goto LABEL_91;
  }
  LODWORD(pszPathOut[0]) = 13;
  pszPathOut[1][13] = 0;
  Common::StringBuffer::SetValue((Common::StringBuffer *)pszPathOut, L"%PROGRAMDATA%", 0xDu);
  v50 = LODWORD(pszPathOut[0]);
  v51 = pszPathOut[1];
  hKey = 0;
  v52 = RtlExpandEnvironmentStrings(0, pszPathOut[1], LODWORD(pszPathOut[0]), 0, 0, &hKey);
  if ( v52 == -1073741789 || v52 >= 0 )
  {
    v76 = 0;
    *(_OWORD *)lpData = 0;
    v53 = Common::StringBuffer::SetLength((Common::StringBuffer *)lpData, (_DWORD)hKey - 1);
    v54 = v53;
    if ( v53 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBB,
        (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
        (const char *)(unsigned int)v53,
        dwFlagsf);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)lpData);
      Common::StringBuffer::~StringBuffer((Common::StringBuffer *)pszPathOut);
      return v54;
    }
    v82 = 0;
    if ( v76 )
      v55 = v76 - 1;
    else
      v55 = 0;
    v56 = (unsigned __int16 *)lpData[1];
    v57 = RtlExpandEnvironmentStrings(0, v51, v50, lpData[1], (unsigned int)(v55 + 1), &v82);
    if ( v57 < 0 )
    {
      v37 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)0xC4,
              (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
              (const char *)(unsigned int)v57,
              dwFlagsg);
    }
    else
    {
      v58 = Common::StringBuffer::SetValueFromString(a3, v56);
      v37 = v58;
      if ( v58 >= 0 )
      {
        if ( v56 )
          Common::GlobalHeap::Free(v56);
        if ( v51 )
        {
          v34 = v51;
LABEL_66:
          Common::GlobalHeap::Free(v34);
        }
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC6,
        (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
        (const char *)(unsigned int)v58,
        dwFlagsg);
    }
    if ( v56 )
      Common::GlobalHeap::Free(v56);
    if ( v51 )
      Common::GlobalHeap::Free(v51);
    return v37;
  }
  v59 = wil::details::in1diag3::Return_NtStatus(
          retaddr,
          (void *)0xB7,
          (unsigned int)"onecore\\base\\appmodel\\common\\userprofile.cpp",
          (const char *)(unsigned int)v52,
          dwFlagsf);
  if ( v51 )
    Common::GlobalHeap::Free(v51);
  return v59;
}

```

## disassembly

```asm
0x18004d3b0  push    rbp
0x18004d3b2  push    rbx
0x18004d3b3  push    r14
0x18004d3b5  push    r15
0x18004d3b7  lea     rbp, [rsp-3Fh]
0x18004d3bc  sub     rsp, 88h
0x18004d3c3  mov     rbx, rdx
0x18004d3c6  xor     r15d, r15d
0x18004d3c9  mov     rdx, [r8+8]
0x18004d3cd  mov     r14, r8
0x18004d3d0  test    rdx, rdx
0x18004d3d3  jnz     loc_18004D991
0x18004d3d9  mov     [rsp+0A0h+arg_8], rsi
0x18004d3e1  mov     [rsp+0A0h+var_20], rdi
0x18004d3e9  mov     [rsp+0A0h+var_28], r12
0x18004d3ee  mov     [rsp+0A0h+var_30], r13
0x18004d3f3  mov     [r8], r15d
0x18004d3f6  cmp     ecx, 5
0x18004d3f9  jnz     loc_18004D794
0x18004d3ff  xorps   xmm0, xmm0
0x18004d402  mov     ecx, r15d
0x18004d405  movups  xmmword ptr [rbp+57h+pszPathOut], xmm0
0x18004d409  mov     [rbp+57h+var_38], ecx
0x18004d40c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18004d413  cmp     [rbx+rax*2+2], cx
0x18004d418  lea     rax, [rax+1]
0x18004d41c  jnz     short loc_18004D413
0x18004d41e  lea     edi, [rax+39h]
0x18004d421  test    edi, edi
0x18004d423  jnz     loc_18004D705
0x18004d429  mov     rsi, [rbp+57h+pszPathOut+8]
0x18004d42d  mov     dword ptr [rbp+57h+pszPathOut], edi
0x18004d430  mov     eax, r15d
0x18004d433  test    ecx, ecx
0x18004d435  jz      short loc_18004D43A
0x18004d437  lea     eax, [rcx-1]
0x18004d43a  lea     edx, [rax+1]; cchPathOut
0x18004d43d  mov     [rsp+0A0h+dwFlags], r15d; int
0x18004d442  mov     r9, rbx; pszMore
0x18004d445  lea     r8, pszPathIn; "Software\\Microsoft\\Windows NT\\Curren"...
0x18004d44c  mov     rcx, rsi; pszPathOut
0x18004d44f  call    PathCchCombineEx
0x18004d454  mov     ebx, eax
0x18004d456  test    eax, eax
0x18004d458  js      loc_18004DB0B
0x18004d45e  lea     rax, [rbp+57h+hKey]
0x18004d462  mov     [rsp+0A0h+lpcbData], r15; __int64
0x18004d467  mov     r9d, 20019h
0x18004d46d  mov     qword ptr [rsp+0A0h+dwFlags], rax; int
0x18004d472  xor     r8d, r8d
0x18004d475  mov     [rbp+57h+hKey], r15
0x18004d479  mov     rdx, rsi; SourceString
0x18004d47c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004d483  call    RegOpenKeyExInternalW
0x18004d488  mov     ebx, eax
0x18004d48a  test    eax, eax
0x18004d48c  jle     short loc_18004D497
0x18004d48e  movzx   ebx, ax
0x18004d491  or      ebx, 80070000h
0x18004d497  test    ebx, ebx
0x18004d499  js      loc_18004DA65
0x18004d49f  xorps   xmm0, xmm0
0x18004d4a2  mov     [rbp+57h+var_50], r15d
0x18004d4a6  movups  xmmword ptr [rbp+57h+lpData], xmm0
0x18004d4aa  mov     rdi, [rbp+57h+lpData+8]
0x18004d4ae  mov     r13d, r15d
0x18004d4b1  test    rdi, rdi
0x18004d4b4  jz      loc_18004D5F1
0x18004d4ba  mov     eax, r15d
0x18004d4bd  test    r13d, r13d
0x18004d4c0  jz      short loc_18004D4C6
0x18004d4c2  lea     eax, [r13-1]
0x18004d4c6  lea     r12d, [rax+1]
0x18004d4ca  mov     rcx, [rbp+57h+hKey]; hKey
0x18004d4ce  lea     eax, [r12+r12]
0x18004d4d2  mov     [rbp+57h+cbData], eax
0x18004d4d5  lea     rdx, aProfileimagepa; "ProfileImagePath"
0x18004d4dc  lea     rax, [rbp+57h+cbData]
0x18004d4e0  xor     r9d, r9d; lpType
0x18004d4e3  mov     [rsp+0A0h+lpcbData], rax; lpcbData
0x18004d4e8  xor     r8d, r8d; lpReserved
0x18004d4eb  mov     qword ptr [rsp+0A0h+dwFlags], rdi; int
0x18004d4f0  call    RegQueryValueExW
0x18004d4f5  mov     ebx, eax
0x18004d4f7  test    eax, eax
0x18004d4f9  jnz     loc_18004DA8C
0x18004d4ff  mov     edx, [rbp+57h+cbData]
0x18004d502  test    dl, 1
0x18004d505  jnz     loc_18004DAA7
0x18004d50b  shr     edx, 1
0x18004d50d  jz      loc_18004DD16
0x18004d513  test    eax, eax
0x18004d515  jnz     short loc_18004D51C
0x18004d517  test    rdi, rdi
0x18004d51a  jnz     short loc_18004D53F
0x18004d51c  lea     r15d, [rdx-1]
0x18004d520  test    eax, eax
0x18004d522  jle     short loc_18004D52D
0x18004d524  movzx   ebx, bx
0x18004d527  or      ebx, 80070000h
0x18004d52d  test    ebx, ebx
0x18004d52f  jz      short loc_18004D563
0x18004d531  cmp     ebx, 800700EAh
0x18004d537  jnz     loc_18004D61F
0x18004d53d  jmp     short loc_18004D56C
0x18004d53f  lea     r15d, [rdx-1]
0x18004d543  cmp     word ptr [rdi+r15*2], 0
0x18004d549  jz      short loc_18004D52D
0x18004d54b  lea     r15d, [rdx+1]
0x18004d54f  cmp     r15d, r12d
0x18004d552  ja      loc_18004DAB1
0x18004d558  xor     eax, eax
0x18004d55a  mov     r15d, edx
0x18004d55d  mov     [rdi+rdx*2], ax
0x18004d561  jmp     short loc_18004D52D
0x18004d563  cmp     r15d, r12d
0x18004d566  jbe     loc_18004D5F9
0x18004d56c  cmp     r15d, 3FFFFFFFh
0x18004d573  ja      loc_18004DA3D
0x18004d579  test    r15d, r15d
0x18004d57c  jz      loc_18004DACC
0x18004d582  lea     r12d, [r15+1]
0x18004d586  cmp     r12d, r13d
0x18004d589  jz      loc_18004DD0E
0x18004d58f  mov     r8d, r12d
0x18004d592  lea     r9, [rbp+57h+arg_18]; void **
0x18004d596  mov     edx, r13d
0x18004d599  add     r8, r8; unsigned __int64
0x18004d59c  add     rdx, rdx; unsigned __int64
0x18004d59f  mov     [rbp+57h+arg_18], 0
0x18004d5a7  mov     rcx, rdi; Ptr
0x18004d5aa  call    ?CommonHeapReAllocDefault@@YAJPEAX_K1PEAPEAX@Z; CommonHeapReAllocDefault(void *,unsigned __int64,unsigned __int64,void * *)
0x18004d5af  mov     ebx, eax
0x18004d5b1  test    eax, eax
0x18004d5b3  js      loc_18004D836
0x18004d5b9  mov     rdi, [rbp+57h+arg_18]
0x18004d5bd  mov     r13d, r12d
0x18004d5c0  mov     eax, dword ptr [rbp+57h+lpData]
0x18004d5c3  mov     [rbp+57h+lpData+8], rdi
0x18004d5c7  mov     [rbp+57h+var_50], r12d
0x18004d5cb  cmp     eax, r15d
0x18004d5ce  ja      loc_18004DAF7
0x18004d5d4  mov     r15d, 0
0x18004d5da  jnb     loc_18004D4B1
0x18004d5e0  test    eax, eax
0x18004d5e2  jnz     loc_18004D4B1
0x18004d5e8  mov     [rdi], r15w
0x18004d5ec  jmp     loc_18004D4B1
0x18004d5f1  mov     r12d, r15d
0x18004d5f4  jmp     loc_18004D4CA
0x18004d5f9  test    r13d, r13d
0x18004d5fc  jnz     loc_18004D82E
0x18004d602  cmp     r15d, r13d
0x18004d605  ja      loc_18004D99A
0x18004d60b  mov     dword ptr [rbp+57h+lpData], r15d
0x18004d60f  test    r15d, r15d
0x18004d612  jz      short loc_18004D61D
0x18004d614  mov     ecx, r15d
0x18004d617  xor     eax, eax
0x18004d619  mov     [rdi+rcx*2], ax
0x18004d61d  xor     ebx, ebx
0x18004d61f  test    ebx, ebx
0x18004d621  js      loc_18004D866
0x18004d627  mov     r15d, dword ptr [rbp+57h+lpData]
0x18004d62b  lea     rax, [rbp+57h+var_70]
0x18004d62f  xor     r13d, r13d
0x18004d632  mov     [rsp+0A0h+lpcbData], rax
0x18004d637  mov     r8d, r15d
0x18004d63a  mov     qword ptr [rsp+0A0h+dwFlags], r13; int
0x18004d63f  xor     r9d, r9d
0x18004d642  mov     [rbp+57h+var_70], r13
0x18004d646  mov     rdx, rdi
0x18004d649  xor     ecx, ecx
0x18004d64b  call    cs:__imp_RtlExpandEnvironmentStrings
0x18004d651  cmp     eax, 0C0000023h
0x18004d656  jnz     loc_18004DD26
0x18004d65c  mov     ebx, dword ptr [rbp+57h+var_70]
0x18004d65f  xorps   xmm0, xmm0
0x18004d662  mov     ecx, r13d
0x18004d665  mov     [rbp+57h+var_38], ecx
0x18004d668  movups  xmmword ptr [rbp+57h+pszPathOut], xmm0
0x18004d66c  sub     ebx, 1
0x18004d66f  jnz     loc_18004D909
0x18004d675  mov     rbx, [rbp+57h+pszPathOut+8]
0x18004d679  mov     [rbp+57h+var_68], r13
0x18004d67d  mov     eax, r13d
0x18004d680  test    ecx, ecx
0x18004d682  jnz     loc_18004D78C
0x18004d688  lea     ecx, [rax+1]
0x18004d68b  mov     r9, rbx
0x18004d68e  lea     rax, [rbp+57h+var_68]
0x18004d692  mov     r8, r15
0x18004d695  mov     [rsp+0A0h+lpcbData], rax
0x18004d69a  mov     rdx, rdi
0x18004d69d  mov     qword ptr [rsp+0A0h+dwFlags], rcx; int
0x18004d6a2  xor     ecx, ecx
0x18004d6a4  call    cs:__imp_RtlExpandEnvironmentStrings
0x18004d6aa  test    eax, eax
0x18004d6ac  js      loc_18004D7D2
0x18004d6b2  mov     rdx, rbx; unsigned __int16 *
0x18004d6b5  mov     rcx, r14; this
0x18004d6b8  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x18004d6bd  mov     r14d, eax
0x18004d6c0  test    eax, eax
0x18004d6c2  js      loc_18004D8BB
0x18004d6c8  test    rbx, rbx
0x18004d6cb  jz      short loc_18004D6D5
0x18004d6cd  mov     rcx, rbx; void *
0x18004d6d0  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18004d6d5  test    rdi, rdi
0x18004d6d8  jz      short loc_18004D6E2
0x18004d6da  mov     rcx, rdi; void *
0x18004d6dd  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18004d6e2  mov     rcx, [rbp+57h+hKey]; hKey
0x18004d6e6  lea     rax, [rcx-1]
0x18004d6ea  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004d6ee  jbe     loc_18004D8B1
0x18004d6f4  test    rsi, rsi
0x18004d6f7  jz      short loc_18004D701
0x18004d6f9  mov     rcx, rsi; void *
0x18004d6fc  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18004d701  xor     eax, eax
0x18004d703  jmp     short loc_18004D764
0x18004d705  mov     edx, edi; unsigned int
0x18004d707  lea     rcx, [rbp+57h+pszPathOut]; this
0x18004d70b  call    ?SetCapacity@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetCapacity(ulong)
0x18004d710  mov     esi, eax
0x18004d712  test    eax, eax
0x18004d714  jns     loc_18004DABB
0x18004d71a  mov     rcx, [rbp+5Fh]; this
0x18004d71e  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\common\\widest"...
0x18004d725  mov     r9d, eax; char *
0x18004d728  mov     edx, 20Ch; void *
0x18004d72d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004d732  mov     rcx, [rbp+5Fh]; this
0x18004d736  lea     r8, aOnecoreBaseApp_15; "onecore\\base\\appmodel\\common\\userpr"...
0x18004d73d  mov     r9d, esi; char *
0x18004d740  mov     edx, 78h ; 'x'; void *
0x18004d745  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d74a  mov     r8, [rbp+57h+pszPathOut+8]; P
0x18004d74e  test    r8, r8
0x18004d751  jz      short loc_18004D762
0x18004d753  mov     rcx, cs:?g_heap@ReservedForLocalUse@@3PEAXEA; HeapHandle
0x18004d75a  xor     edx, edx; Flags
0x18004d75c  call    cs:__imp_RtlFreeHeap
0x18004d762  mov     eax, esi
0x18004d764  mov     r13, [rsp+0A0h+var_30]
0x18004d769  mov     r12, [rsp+0A0h+var_28]
0x18004d76e  mov     rdi, [rsp+0A0h+var_20]
0x18004d776  mov     rsi, [rsp+0A0h+arg_8]
0x18004d77e  add     rsp, 88h
0x18004d785  pop     r15
0x18004d787  pop     r14
0x18004d789  pop     rbx
0x18004d78a  pop     rbp
0x18004d78b  retn
0x18004d78c  lea     eax, [rcx-1]
0x18004d78f  jmp     loc_18004D688
0x18004d794  cmp     ecx, 6
0x18004d797  jnz     loc_18004D9D1
0x18004d79d  lea     rdx, aLocalAppdata; "Local AppData"
0x18004d7a4  mov     rcx, rbx; pszPathIn
0x18004d7a7  call    ?GetUserProfileFolderPathFromSid@@YAJPEBG0AEAVStringBuffer@Common@@@Z; GetUserProfileFolderPathFromSid(ushort const *,ushort const *,Common::StringBuffer &)
0x18004d7ac  mov     ebx, eax
0x18004d7ae  test    eax, eax
0x18004d7b0  jns     loc_18004D701
0x18004d7b6  mov     rcx, [rbp+5Fh]; this
0x18004d7ba  lea     r8, aOnecoreBaseApp_15; "onecore\\base\\appmodel\\common\\userpr"...
0x18004d7c1  mov     r9d, eax; char *
0x18004d7c4  mov     edx, 0A5h; void *
0x18004d7c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004d7ce  mov     eax, ebx
0x18004d7d0  jmp     short loc_18004D764
0x18004d7d2  mov     rcx, [rbp+5Fh]; this
0x18004d7d6  lea     r8, aOnecoreBaseApp_15; "onecore\\base\\appmodel\\common\\userpr"...
0x18004d7dd  mov     r9d, eax; char *
0x18004d7e0  mov     edx, 9Bh; void *
0x18004d7e5  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18004d7ea  mov     r14d, eax
0x18004d7ed  test    rbx, rbx
0x18004d7f0  jz      short loc_18004D7FA
0x18004d7f2  mov     rcx, rbx; void *
0x18004d7f5  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18004d7fa  test    rdi, rdi
0x18004d7fd  jz      short loc_18004D807
0x18004d7ff  mov     rcx, rdi; void *
0x18004d802  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18004d807  mov     rcx, [rbp+57h+hKey]
0x18004d80b  lea     rax, [rcx-1]
0x18004d80f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18004d813  jbe     loc_18004D8FF
0x18004d819  test    rsi, rsi
0x18004d81c  jz      short loc_18004D826
0x18004d81e  mov     rcx, rsi; void *
0x18004d821  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18004d826  mov     eax, r14d
0x18004d829  jmp     loc_18004D764
0x18004d82e  dec     r13d
0x18004d831  jmp     loc_18004D602
0x18004d836  mov     r9d, eax; char *
  ... truncated ...
```
