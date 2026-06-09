# CRegZone::Init(ushort const *,int,REGZONEUSE,int)

- ea: `0x180033740`
- end: `0x1800342bd`
- name: `?Init@CRegZone@@QEAAHPEBGHW4REGZONEUSE@@H@Z`
- size: `2941`
- prototype: `int __high(const unsigned __int16 *, int, enum REGZONEUSE, int)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800330bc`
- `0x18003434c`
- `0x180106f00`
- `0x180107e28`
- `0x18010806c`

## callees

- `0x180033740`
- `0x1800342d0`
- `0x180034300`
- `0x180056d60`
- `0x18011a7c4`
- `0x18011baa0`
- `0x18011c010`

## import_xrefs

- `iertutil!__imp_?SetKernelHandleToLowIL@@YAJPEAX@Z` at `0x180033a26`
- `iertutil!__imp_?SetKernelHandleToLowIL@@YAJPEAX@Z` at `0x180033a26`
- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x1800337c1`
- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x1800337c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800337f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033a3d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800337f6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180033a3d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800337d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800337d7`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x180033bdc`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrToIntW` at `0x180033bdc`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x1800339a5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x180033b8d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x180033bb0`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x1800339a5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x180033b8d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x180033bb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033a12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033a46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180033a46`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegDeleteUSValueW` at `0x180034089`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegDeleteUSValueW` at `0x1800340a3`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegDeleteUSValueW` at `0x180034089`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegDeleteUSValueW` at `0x1800340a3`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x180033e99`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x180033edd`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x180033f24`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x180033f59`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x180033e99`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x180033edd`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x180033f24`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegWriteUSValueW` at `0x180033f59`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003398a`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180033b76`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180033ca9`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180033d3e`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180033e38`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003401f`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180034067`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x1800340d6`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003398a`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180033b76`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180033ca9`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180033d3e`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180033e38`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x18003401f`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x180034067`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegOpenUSKeyW` at `0x1800340d6`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x180033da5`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x1800341a1`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x180033da5`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegQueryUSValueW` at `0x1800341a1`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180033f87`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180033f9c`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180033faf`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180033fc6`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180034145`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003415f`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180033f87`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180033f9c`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180033faf`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180033fc6`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x180034145`
- `api-ms-win-core-registryuserspecific-l1-1-0!SHRegCloseUSKey` at `0x18003415f`

## string_xrefs

- `0x1800337ba`: `Local\ZonesLockedCacheCounterMutex`
- `0x180033a31`: `Local\ZonesCacheCounterMutex`
- `0x18003420a`: `Software\Policies\Microsoft\Windows\CurrentVersion\Internet Settings\TemplatePolicies\`
- `0x1800341bc`: `Software\Microsoft\Windows\CurrentVersion\Internet Settings\TemplatePolicies\`
- `0x180034266`: `TemplateIndex`

## pseudocode

```c
__int64 __fastcall CRegZone::Init(__int64 a1, const WCHAR *a2, BOOL a3, int a4)
{
  const WCHAR *v6; // r13
  char *v8; // rbx
  const CHAR *v9; // r8
  HANDLE MutexA; // rdi
  struct _RTL_CRITICAL_SECTION *v11; // rcx
  __int64 v12; // rbx
  const WCHAR *v13; // rdi
  __int64 v14; // rsi
  __int64 v15; // rcx
  WCHAR *v16; // r8
  const WCHAR *v17; // rdx
  __int64 v18; // r9
  __int64 v19; // rcx
  const wchar_t *v20; // rdx
  WCHAR *v21; // rcx
  __int64 v22; // r8
  __int64 v23; // rdx
  WCHAR *v24; // rax
  __int64 v25; // rcx
  const WCHAR *v26; // r8
  _WORD *v27; // r9
  _WORD *v28; // rcx
  BOOL fIgnoreHKCU; // eax
  PWSTR v30; // rax
  const wchar_t *v31; // rdx
  __int64 v32; // rcx
  WCHAR *v33; // r8
  __int64 v34; // r9
  const wchar_t *v35; // rdx
  __int64 v36; // rcx
  WCHAR *v37; // rcx
  __int64 v38; // r8
  __int64 v39; // rdx
  WCHAR *v40; // rax
  __int64 v41; // rcx
  const WCHAR *v42; // r8
  _WORD *v43; // r9
  _WORD *v44; // rcx
  BOOL v45; // eax
  PWSTR v46; // rax
  const WCHAR *v47; // rax
  WCHAR *v48; // rdx
  __int64 v49; // rcx
  __int64 v50; // r8
  WCHAR *v51; // rcx
  WCHAR *v52; // rax
  __int64 v53; // r9
  _WORD *v54; // rdx
  _WORD *v55; // rcx
  BOOL v56; // eax
  HUSKEY v57; // rcx
  _BYTE *v58; // rbx
  BOOL v59; // eax
  HUSKEY v60; // rcx
  DWORD v61; // edi
  DWORD v62; // eax
  DWORD v63; // eax
  unsigned int v64; // ebx
  int v65; // ebx
  DWORD v66; // eax
  SHREGDEL_FLAGS v68; // r8d
  SHREGDEL_FLAGS v69; // r8d
  __int64 v70; // rcx
  const wchar_t *v71; // r8
  __int64 v72; // rdx
  WCHAR *v73; // rax
  HUSKEY phNewUSKey; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v75; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+4Ch] [rbp-B4h] BYREF
  const unsigned int *v77; // [rsp+50h] [rbp-B0h] BYREF
  HUSKEY hUSKey; // [rsp+58h] [rbp-A8h]
  BOOL v79; // [rsp+60h] [rbp-A0h]
  __int64 v80; // [rsp+64h] [rbp-9Ch]
  const unsigned int *v81; // [rsp+70h] [rbp-90h] BYREF
  HUSKEY v82; // [rsp+78h] [rbp-88h]
  BOOL v83; // [rsp+80h] [rbp-80h]
  __int64 v84; // [rsp+84h] [rbp-7Ch]
  const unsigned int *v85; // [rsp+90h] [rbp-70h] BYREF
  HUSKEY v86; // [rsp+98h] [rbp-68h]
  BOOL v87; // [rsp+A0h] [rbp-60h]
  __int64 v88; // [rsp+A4h] [rbp-5Ch]
  const unsigned int *v89; // [rsp+B0h] [rbp-50h] BYREF
  HUSKEY v90; // [rsp+B8h] [rbp-48h]
  BOOL v91; // [rsp+C0h] [rbp-40h]
  __int64 v92; // [rsp+C4h] [rbp-3Ch]
  WCHAR pwzPath[259]; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v94; // [rsp+2D6h] [rbp+1D6h]
  _BYTE v95[8]; // [rsp+2D8h] [rbp+1D8h] BYREF

  v6 = a2;
  if ( !a2 )
    return 0;
  *(_DWORD *)(a1 + 40) = a3;
  *(_DWORD *)(a1 + 56) = a4;
  v8 = (char *)&CRegZone::s_lockrzcache;
  if ( a4 != 2 )
    v8 = (char *)&CRegZone::s_rzcache;
  *(_QWORD *)(a1 + 64) = v8;
  if ( !*((_DWORD *)v8 + 15) )
  {
    if ( *((_DWORD *)v8 + 14) )
      v9 = "Local\\ZonesLockedCacheCounterMutex";
    else
      v9 = "Local\\ZonesCacheCounterMutex";
    MutexA = CreateMutexA(0, 0, v9);
    if ( MutexA && GetLastError() != 183 )
      SetKernelHandleToLowIL(MutexA);
    EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 16));
    v11 = (struct _RTL_CRITICAL_SECTION *)(v8 + 16);
    if ( *((_DWORD *)v8 + 15) )
    {
      LeaveCriticalSection(v11);
      CloseHandle(MutexA);
    }
    else
    {
      *((_QWORD *)v8 + 1) = MutexA;
      *((_DWORD *)v8 + 15) = 1;
      LeaveCriticalSection(v11);
    }
  }
  v91 = a3;
  v90 = 0;
  v89 = &CRegKey::`vftable';
  v12 = 260;
  v92 = 1;
  v85 = &CRegKey::`vftable';
  v13 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Zones\\";
  v86 = 0;
  v14 = -1;
  v87 = a3;
  v88 = 0;
  if ( !a4 )
  {
    v15 = 259;
    v16 = pwzPath;
    v17 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Zones\\";
    v18 = 260;
    do
    {
      if ( !v15 )
        break;
      if ( !*v17 )
        break;
      *v16++ = *v17++;
      --v15;
      --v18;
    }
    while ( v18 );
LABEL_22:
    v21 = v16 - 1;
    if ( v18 )
      v21 = v16;
    goto LABEL_24;
  }
  if ( a4 != 1 )
  {
    if ( a4 != 2 )
      goto LABEL_38;
    v19 = 259;
    v20 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Lockdown_Zones\\";
    v18 = 260;
    v16 = pwzPath;
    do
    {
      if ( !v19 )
        break;
      if ( !*v20 )
        break;
      *v16++ = *v20++;
      --v19;
      --v18;
    }
    while ( v18 );
    goto LABEL_22;
  }
  v70 = 259;
  v71 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\TemplatePolicies\\";
  v72 = 260;
  v73 = pwzPath;
  do
  {
    if ( !v70 )
      break;
    if ( !*v71 )
      break;
    *v73++ = *v71++;
    --v70;
    --v72;
  }
  while ( v72 );
  v21 = v73 - 1;
  if ( v72 )
    v21 = v73;
LABEL_24:
  *v21 = 0;
  v94 = 0;
  v22 = -1;
  do
    ++v22;
  while ( pwzPath[v22] );
  v23 = 260;
  v24 = pwzPath;
  while ( *v24 )
  {
    ++v24;
    if ( !--v23 )
      goto LABEL_38;
  }
  v25 = 259 - v22;
  if ( (unsigned __int64)(259 - v22) <= 0x7FFFFFFE )
  {
    v26 = v6;
    v27 = &v95[-2 * v23];
    do
    {
      if ( !v25 )
        break;
      if ( !*v26 )
        break;
      *v27++ = *v26++;
      --v25;
      --v23;
    }
    while ( v23 );
    v28 = v27 - 1;
    if ( v23 )
      v28 = v27;
    *v28 = 0;
  }
LABEL_38:
  phNewUSKey = 0;
  CRegKey::Close((CRegKey *)&v85);
  if ( !(_DWORD)v88 )
  {
LABEL_39:
    fIgnoreHKCU = v87;
    goto LABEL_40;
  }
  fIgnoreHKCU = v87;
  if ( !v87 )
  {
    if ( !SHRegOpenUSKeyW(pwzPath, 0x20019u, 0, &phNewUSKey, 1) )
      goto LABEL_41;
    goto LABEL_39;
  }
LABEL_40:
  if ( SHRegOpenUSKeyW(pwzPath, 0x20019u, 0, &phNewUSKey, fIgnoreHKCU) )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    goto LABEL_42;
  }
LABEL_41:
  v86 = phNewUSKey;
  v30 = StrDupW(pwzPath);
  *(_QWORD *)(a1 + 16) = v30;
  if ( !v30 )
  {
    v85 = &CRegKey::`vftable';
    if ( v86 )
    {
      SHRegCloseUSKey(v86);
      v86 = 0;
    }
    v89 = &CRegKey::`vftable';
    if ( v90 )
      SHRegCloseUSKey(v90);
    return 0;
  }
LABEL_42:
  switch ( a4 )
  {
    case 1:
      goto LABEL_78;
    case 0:
      v31 = L"Software\\Policies\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Zones\\";
      v32 = 259;
      v33 = pwzPath;
      v34 = 260;
      do
      {
        if ( !v32 )
          break;
        if ( !*v31 )
          break;
        *v33++ = *v31++;
        --v32;
        --v34;
      }
      while ( v34 );
      goto LABEL_58;
    case 2:
      v35 = L"Software\\Policies\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\Lockdown_Zones\\";
      v36 = 259;
      v33 = pwzPath;
      v34 = 260;
      do
      {
        if ( !v36 )
          break;
        if ( !*v35 )
          break;
        *v33++ = *v35++;
        --v36;
        --v34;
      }
      while ( v34 );
LABEL_58:
      v37 = v33 - 1;
      if ( v34 )
        v37 = v33;
      *v37 = 0;
      v38 = -1;
      v94 = 0;
      do
        ++v38;
      while ( pwzPath[v38] );
      v39 = 260;
      v40 = pwzPath;
      while ( *v40 )
      {
        ++v40;
        if ( !--v39 )
          goto LABEL_74;
      }
      v41 = 259 - v38;
      if ( (unsigned __int64)(259 - v38) <= 0x7FFFFFFE )
      {
        v42 = v6;
        v43 = &v95[-2 * v39];
        do
        {
          if ( !v41 )
            break;
          if ( !*v42 )
            break;
          *v43++ = *v42++;
          --v41;
          --v39;
        }
        while ( v39 );
        v44 = v43 - 1;
        if ( v39 )
          v44 = v43;
        *v44 = 0;
      }
      break;
  }
LABEL_74:
  phNewUSKey = 0;
  (*((void (__fastcall **)(const unsigned int **))v89 + 2))(&v89);
  if ( !(_DWORD)v92 )
    goto LABEL_75;
  v45 = v91;
  if ( v91 )
  {
LABEL_76:
    if ( SHRegOpenUSKeyW(pwzPath, 0x20019u, 0, &phNewUSKey, v45) )
      goto LABEL_78;
    goto LABEL_77;
  }
  if ( SHRegOpenUSKeyW(pwzPath, 0x20019u, 0, &phNewUSKey, 1) )
  {
LABEL_75:
    v45 = v91;
    goto LABEL_76;
  }
LABEL_77:
  v90 = phNewUSKey;
  v46 = StrDupW(pwzPath);
  *(_QWORD *)(a1 + 24) = v46;
  if ( !v46 )
  {
LABEL_159:
    v85 = &CRegKey::`vftable';
    CRegKey::Close((CRegKey *)&v85);
    v89 = &CRegKey::`vftable';
    CRegKey::Close((CRegKey *)&v89);
    return 0;
  }
LABEL_78:
  if ( !*(_QWORD *)(a1 + 16) && !*(_QWORD *)(a1 + 24) )
    goto LABEL_159;
  v47 = StrDupW(v6);
  *(_QWORD *)(a1 + 8) = v47;
  if ( !v47 )
    goto LABEL_159;
  v75 = -1;
  if ( (a4 & 0xFFFFFFFD) != 0 )
  {
    if ( a4 != 1 )
    {
LABEL_82:
      v83 = a3;
      v81 = &CRegKey::`vftable';
      v48 = pwzPath;
      v82 = 0;
      v49 = 259;
      v84 = 0;
      v50 = 260;
      do
      {
        if ( !v49 )
          break;
        if ( !*v13 )
          break;
        *v48++ = *v13++;
        --v49;
        --v50;
      }
      while ( v50 );
      v51 = v48 - 1;
      if ( v50 )
        v51 = v48;
      *v51 = 0;
      v94 = 0;
      do
        ++v14;
      while ( pwzPath[v14] );
      v52 = pwzPath;
      while ( *v52 )
      {
        ++v52;
        if ( !--v12 )
          goto LABEL_105;
      }
      v53 = 259 - v14;
      if ( (unsigned __int64)(259 - v14) <= 0x7FFFFFFE )
      {
        v54 = &v95[-2 * v12];
        do
        {
          if ( !v53 )
            break;
          if ( !*v6 )
            break;
          *v54++ = *v6++;
          --v53;
          --v12;
        }
        while ( v12 );
        v55 = v54 - 1;
        if ( v12 )
          v55 = v54;
        *v55 = 0;
      }
LABEL_105:
      phNewUSKey = 0;
      CRegKey::Close((CRegKey *)&v81);
      if ( (_DWORD)v84 )
      {
        v56 = v83;
        if ( v83 )
        {
LABEL_107:
          if ( SHRegOpenUSKeyW(pwzPath, 0x20019u, 0, &phNewUSKey, v56) )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs();
            v57 = v82;
LABEL_109:
            LODWORD(phNewUSKey) = 0;
            v58 = (_BYTE *)(a1 + 4);
            pcbData = 4;
            if ( v57 )
            {
              if ( (_DWORD)v84 && !v83 )
              {
                if ( !SHRegQueryUSValueW(v57, L"Flags", (DWORD *)&phNewUSKey, (void *)(a1 + 4), &pcbData, 1, 0, 0) )
                  goto LABEL_112;
                v57 = v82;
              }
              if ( !SHRegQueryUSValueW(v57, L"Flags", (DWORD *)&phNewUSKey, (void *)(a1 + 4), &pcbData, v83, 0, 0) )
              {
LABEL_112:
                if ( *(_DWORD *)a1 != 1
                  || (CSharedMem::IncrementCounter((CSharedMem *)&g_SharedMem, 4u),
                      v77 = &CRegKey::`vftable',
                      v79 = g_bUseHKLMOnly,
                      hUSKey = 0,
                      v80 = 0,
                      (NtCurrentPeb()->BitField & 0x20) != 0) )
                {
LABEL_143:
                  v57 = v82;
                  goto LABEL_133;
                }
                phNewUSKey = 0;
                CRegKey::Close((CRegKey *)&v77);
                if ( (_DWORD)v80 )
                {
                  v59 = v79;
                  if ( v79 )
                  {
LABEL_116:
                    if ( SHRegOpenUSKeyW(
                           L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\ZoneMap\\",
                           0x2001Fu,
                           0,
                           &phNewUSKey,
                           v59) )
                    {
                      goto LABEL_131;
                    }
                    goto LABEL_117;
                  }
                  if ( !SHRegOpenUSKeyW(
                          L"Software\\Microsoft\\Windows\\CurrentVersion\\Internet Settings\\ZoneMap\\",
                          0x2001Fu,
                          0,
                          &phNewUSKey,
                          1) )
                  {
LABEL_117:
                    v60 = phNewUSKey;
                    hUSKey = phNewUSKey;
                    v61 = 2;
                    if ( (*v58 & 8) != 0 )
                    {
                      LODWORD(phNewUSKey) = *(_DWORD *)a1;
                      v62 = 2;
                      if ( v79 )
                        v62 = 8;
                      SHRegWriteUSValueW(v60, L"ProxyBypass", 4u, &phNewUSKey, 4u, v62);
                    }
                    else
                    {
                      v68 = SHREGDEL_HKCU;
                      if ( v79 )
                        v68 = SHREGDEL_HKLM;
                      SHRegDeleteUSValueW(phNewUSKey, L"ProxyBypass", v68);
                    }
                    if ( (*v58 & 0x10) != 0 )
                    {
                      LODWORD(phNewUSKey) = *(_DWORD *)a1;
                      v63 = 2;
                      if ( v79 )
                        v63 = 8;
                      SHRegWriteUSValueW(hUSKey, L"IntranetName", 4u, &phNewUSKey, 4u, v63);
                    }
                    else
                    {
                      v69 = SHREGDEL_HKCU;
                      if ( v79 )
                        v69 = SHREGDEL_HKLM;
                      SHRegDeleteUSValueW(hUSKey, L"IntranetName", v69);
                    }
                    v64 = *(_DWORD *)v58;
                    LODWORD(phNewUSKey) = (v64 >> 7) & 1;
                    v65 = (v64 >> 8) & 1;
                    v66 = 2;
                    if ( v79 )
                      v66 = 8;
                    SHRegWriteUSValueW(hUSKey, L"UNCAsIntranet", 4u, &phNewUSKey, 4u, v66);
                    if ( v79 )
                      v61 = 8;
                    LODWORD(phNewUSKey) = v65;
                    SHRegWriteUSValueW(hUSKey, L"AutoDetect", 4u, &phNewUSKey, 4u, v61);
                    if ( v65 != g_dwAutoDetectFlag )
                      g_dwAutoDetectFlag = -1;
LABEL_131:
                    v77 = &CRegKey::`vftable';
                    if ( hUSKey )
                    {
                      SHRegCloseUSKey(hUSKey);
                      v57 = v82;
                      goto LABEL_133;
                    }
                    goto LABEL_143;
                  }
                }
                v59 = v79;
                goto LABEL_116;
              }
              v57 = v82;
            }
            *(_DWORD *)v58 = 2;
LABEL_133:
            v81 = &CRegKey::`vftable';
            if ( v57 )
              SHRegCloseUSKey(v57);
            goto LABEL_135;
          }
LABEL_108:
          v57 = phNewUSKey;
          v82 = phNewUSKey;
          goto LABEL_109;
        }
        if ( !SHRegOpenUSKeyW(pwzPath, 0x20019u, 0, &phNewUSKey, 1) )
          goto LABEL_108;
      }
      v56 = v83;
      goto LABEL_107;
    }
    if ( CRegKey::QueryValue((CRegKey *)&v85, &v75, L"TemplateIndex") )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    else
      *(_DWORD *)a1 = v75;
  }
  else
  {
    *(_DWORD *)a1 = StrToIntW(v47);
    if ( a4 != 1 )
      goto LABEL_82;
  }
  *(_DWORD *)(a1 + 4) = 2;
LABEL_135:
  v85 = &CRegKey::`vftable';
  if ( v86 )
  {
    SHRegCloseUSKey(v86);
    v86 = 0;
  }
  v89 = &CRegKey::`vftable';
  if ( v90 )
    SHRegCloseUSKey(v90);
  return 1;
}

```

## disassembly

```asm
0x180033740  mov     [rsp-8+arg_10], rbx
0x180033745  push    rbp
0x180033746  push    rsi
0x180033747  push    rdi
0x180033748  push    r12
0x18003374a  push    r13
0x18003374c  push    r14
0x18003374e  push    r15
0x180033750  lea     rbp, [rsp-1F0h]
0x180033758  sub     rsp, 2F0h
0x18003375f  mov     rax, cs:__security_cookie
0x180033766  xor     rax, rsp
0x180033769  mov     [rbp+220h+var_40], rax
0x180033770  mov     r14d, r9d
0x180033773  mov     r15d, r8d
0x180033776  mov     r13, rdx
0x180033779  mov     r12, rcx
0x18003377c  test    rdx, rdx
0x18003377f  jz      loc_180034165
0x180033785  cmp     r9d, 2
0x180033789  mov     [rcx+28h], r8d
0x18003378d  mov     [rcx+38h], r9d
0x180033791  lea     rax, ?s_rzcache@CRegZone@@2VCRegZoneCache@1@A; CRegZone::CRegZoneCache CRegZone::s_rzcache
0x180033798  lea     rbx, ?s_lockrzcache@CRegZone@@2VCRegZoneCache@1@A; CRegZone::CRegZoneCache CRegZone::s_lockrzcache
0x18003379f  cmovnz  rbx, rax
0x1800337a3  mov     [rcx+40h], rbx
0x1800337a7  cmp     dword ptr [rbx+3Ch], 0
0x1800337ab  jnz     short loc_1800337FC
0x1800337ad  xor     edx, edx; bInitialOwner
0x1800337af  xor     ecx, ecx; lpMutexAttributes
0x1800337b1  cmp     [rbx+38h], ecx
0x1800337b4  jz      loc_180033A31
0x1800337ba  lea     r8, Name; "Local\\ZonesLockedCacheCounterMutex"
0x1800337c1  call    cs:__imp_CreateMutexA
0x1800337c7  mov     rdi, rax
0x1800337ca  test    rax, rax
0x1800337cd  jnz     loc_180033A12
0x1800337d3  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800337d7  call    cs:__imp_EnterCriticalSection
0x1800337dd  cmp     dword ptr [rbx+3Ch], 0
0x1800337e1  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800337e5  jnz     loc_180033A3D
0x1800337eb  mov     [rbx+8], rdi
0x1800337ef  mov     dword ptr [rbx+3Ch], 1
0x1800337f6  call    cs:__imp_LeaveCriticalSection
0x1800337fc  xor     r11d, r11d
0x1800337ff  mov     [rbp+220h+var_260], r15d
0x180033803  mov     [rbp+220h+var_268], r11
0x180033807  lea     rax, ??_7CRegKey@@6B@; const CRegKey::`vftable'
0x18003380e  mov     [rbp+220h+var_270], rax
0x180033812  mov     ebx, 104h
0x180033817  mov     [rbp+220h+var_25C], 1
0x18003381f  mov     r10d, 103h
0x180033825  mov     [rbp+220h+var_290], rax
0x180033829  lea     rdi, aSoftwareMicros_69; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180033830  mov     [rbp+220h+var_288], r11
0x180033834  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18003383b  mov     [rbp+220h+var_280], r15d
0x18003383f  mov     [rbp+220h+var_27C], r11
0x180033843  test    r14d, r14d
0x180033846  jnz     short loc_180033879
0x180033848  mov     ecx, r10d
0x18003384b  lea     r8, [rbp+220h+pwzPath]
0x18003384f  mov     rdx, rdi
0x180033852  mov     r9d, ebx
0x180033855  test    rcx, rcx
0x180033858  jz      short loc_1800338C2
0x18003385a  movzx   eax, word ptr [rdx]
0x18003385d  test    ax, ax
0x180033860  jz      short loc_1800338C2
0x180033862  mov     [r8], ax
0x180033866  add     rdx, 2
0x18003386a  add     r8, 2
0x18003386e  dec     rcx
0x180033871  sub     r9, 1
0x180033875  jnz     short loc_180033855
0x180033877  jmp     short loc_1800338C2
0x180033879  mov     ecx, r14d
0x18003387c  sub     ecx, 1
0x18003387f  jz      loc_1800341B9
0x180033885  cmp     ecx, 1
0x180033888  jnz     loc_18003395A
0x18003388e  mov     rcx, r10
0x180033891  lea     rdx, aSoftwareMicros_35; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180033898  mov     r9, rbx
0x18003389b  lea     r8, [rbp+220h+pwzPath]
0x18003389f  nop
0x1800338a0  test    rcx, rcx
0x1800338a3  jz      short loc_1800338C2
0x1800338a5  movzx   eax, word ptr [rdx]
0x1800338a8  test    ax, ax
0x1800338ab  jz      short loc_1800338C2
0x1800338ad  mov     [r8], ax
0x1800338b1  add     rdx, 2
0x1800338b5  add     r8, 2
0x1800338b9  dec     rcx
0x1800338bc  sub     r9, 1
0x1800338c0  jnz     short loc_1800338A0
0x1800338c2  test    r9, r9
0x1800338c5  lea     rcx, [r8-2]
0x1800338c9  cmovnz  rcx, r8
0x1800338cd  mov     [rcx], r11w
0x1800338d1  lea     rax, [rbp+220h+pwzPath]
0x1800338d5  mov     [rbp+220h+var_4A], r11w
0x1800338dd  mov     r8, rsi
0x1800338e0  inc     r8
0x1800338e3  cmp     [rax+r8*2], r11w
0x1800338e8  jnz     short loc_1800338E0
0x1800338ea  mov     rdx, rbx
0x1800338ed  lea     rax, [rbp+220h+pwzPath]
0x1800338f1  cmp     [rax], r11w
0x1800338f5  jz      short loc_180033903
0x1800338f7  add     rax, 2
0x1800338fb  sub     rdx, 1
0x1800338ff  jnz     short loc_1800338F1
0x180033901  jmp     short loc_18003395A
0x180033903  mov     rcx, r10
0x180033906  sub     rcx, r8
0x180033909  cmp     rcx, 7FFFFFFEh
0x180033910  ja      short loc_18003395A
0x180033912  lea     rax, [rdx+rdx]
0x180033916  mov     r8, r13
0x180033919  lea     r9, [rbp+220h+var_48]
0x180033920  sub     r9, rax
0x180033923  test    rdx, rdx
0x180033926  jz      short loc_18003394B
0x180033928  test    rcx, rcx
0x18003392b  jz      short loc_18003394B
0x18003392d  movzx   eax, word ptr [r8]
0x180033931  test    ax, ax
0x180033934  jz      short loc_18003394B
0x180033936  mov     [r9], ax
0x18003393a  add     r8, 2
0x18003393e  add     r9, 2
0x180033942  dec     rcx
0x180033945  sub     rdx, 1
0x180033949  jnz     short loc_180033928
0x18003394b  test    rdx, rdx
0x18003394e  lea     rcx, [r9-2]
0x180033952  cmovnz  rcx, r9
0x180033956  mov     [rcx], r11w
0x18003395a  lea     rcx, [rbp+220h+var_290]; this
0x18003395e  mov     [rsp+320h+phNewUSKey], r11
0x180033963  call    ?Close@CRegKey@@UEAAJXZ; CRegKey::Close(void)
0x180033968  cmp     dword ptr [rbp+220h+var_27C], 0
0x18003396c  jnz     loc_180033C85
0x180033972  mov     eax, [rbp+220h+var_280]
0x180033975  lea     r9, [rsp+320h+phNewUSKey]; phNewUSKey
0x18003397a  mov     [rsp+320h+fIgnoreHKCU], eax; fIgnoreHKCU
0x18003397e  xor     r8d, r8d; hRelativeUSKey
0x180033981  lea     rcx, [rbp+220h+pwzPath]; pwzPath
0x180033985  mov     edx, 20019h; samDesired
0x18003398a  call    cs:__imp_SHRegOpenUSKeyW
0x180033990  test    eax, eax
0x180033992  jnz     loc_1800340E9
0x180033998  mov     rax, [rsp+320h+phNewUSKey]
0x18003399d  lea     rcx, [rbp+220h+pwzPath]; pszSrch
0x1800339a1  mov     [rbp+220h+var_288], rax
0x1800339a5  call    cs:__imp_StrDupW
0x1800339ab  mov     [r12+10h], rax
0x1800339b0  test    rax, rax
0x1800339b3  jz      loc_180034131
0x1800339b9  cmp     r14d, 1
0x1800339bd  jz      loc_180033BA1
0x1800339c3  test    r14d, r14d
0x1800339c6  jnz     loc_180033A51
0x1800339cc  mov     r10d, 103h
0x1800339d2  lea     rdx, aSoftwarePolici_4; "Software\\Policies\\Microsoft\\Windows"...
0x1800339d9  mov     ecx, r10d
0x1800339dc  lea     r8, [rbp+220h+pwzPath]
0x1800339e0  mov     r9, rbx
0x1800339e3  test    rcx, rcx
0x1800339e6  jz      loc_180033AA2
0x1800339ec  movzx   eax, word ptr [rdx]
0x1800339ef  test    ax, ax
0x1800339f2  jz      loc_180033AA2
0x1800339f8  mov     [r8], ax
0x1800339fc  add     rdx, 2
0x180033a00  add     r8, 2
0x180033a04  dec     rcx
0x180033a07  sub     r9, 1
0x180033a0b  jnz     short loc_1800339E3
0x180033a0d  jmp     loc_180033AA2
0x180033a12  call    cs:__imp_GetLastError
0x180033a18  cmp     eax, 0B7h
0x180033a1d  jz      loc_1800337D3
0x180033a23  mov     rcx, rdi
0x180033a26  call    cs:__imp_?SetKernelHandleToLowIL@@YAJPEAX@Z; SetKernelHandleToLowIL(void *)
0x180033a2c  jmp     loc_1800337D3
0x180033a31  lea     r8, aLocalZonescach; "Local\\ZonesCacheCounterMutex"
0x180033a38  jmp     loc_1800337C1
0x180033a3d  call    cs:__imp_LeaveCriticalSection
0x180033a43  mov     rcx, rdi; hObject
0x180033a46  call    cs:__imp_CloseHandle
0x180033a4c  jmp     loc_1800337FC
0x180033a51  mov     ecx, r14d
0x180033a54  sub     ecx, 1
0x180033a57  jz      loc_180034204
0x180033a5d  cmp     ecx, 1
0x180033a60  jnz     loc_180034254
0x180033a66  mov     r10d, 103h
0x180033a6c  lea     rdx, aSoftwarePolici_7; "Software\\Policies\\Microsoft\\Windows"...
0x180033a73  mov     ecx, r10d
0x180033a76  lea     r8, [rbp+220h+pwzPath]
0x180033a7a  mov     r9, rbx
0x180033a7d  nop     dword ptr [rax]
0x180033a80  test    rcx, rcx
0x180033a83  jz      short loc_180033AA2
0x180033a85  movzx   eax, word ptr [rdx]
0x180033a88  test    ax, ax
0x180033a8b  jz      short loc_180033AA2
0x180033a8d  mov     [r8], ax
0x180033a91  add     rdx, 2
0x180033a95  add     r8, 2
0x180033a99  dec     rcx
0x180033a9c  sub     r9, 1
0x180033aa0  jnz     short loc_180033A80
0x180033aa2  test    r9, r9
0x180033aa5  lea     rcx, [r8-2]
0x180033aa9  cmovnz  rcx, r8
0x180033aad  xor     r11d, r11d
0x180033ab0  lea     rax, [rbp+220h+pwzPath]
0x180033ab4  mov     [rcx], r11w
0x180033ab8  mov     r8, rsi
0x180033abb  mov     [rbp+220h+var_4A], r11w
0x180033ac3  inc     r8
0x180033ac6  cmp     word ptr [rax+r8*2], 0
0x180033acc  jnz     short loc_180033AC3
0x180033ace  mov     rdx, rbx
0x180033ad1  lea     rax, [rbp+220h+pwzPath]
0x180033ad5  cmp     word ptr [rax], 0
0x180033ad9  jz      short loc_180033AE7
0x180033adb  add     rax, 2
0x180033adf  sub     rdx, 1
0x180033ae3  jnz     short loc_180033AD5
0x180033ae5  jmp     short loc_180033B3E
0x180033ae7  mov     rcx, r10
0x180033aea  sub     rcx, r8
0x180033aed  cmp     rcx, 7FFFFFFEh
0x180033af4  ja      short loc_180033B3E
0x180033af6  lea     rax, [rdx+rdx]
0x180033afa  mov     r8, r13
0x180033afd  lea     r9, [rbp+220h+var_48]
0x180033b04  sub     r9, rax
0x180033b07  test    rdx, rdx
0x180033b0a  jz      short loc_180033B2F
0x180033b0c  test    rcx, rcx
0x180033b0f  jz      short loc_180033B2F
0x180033b11  movzx   eax, word ptr [r8]
0x180033b15  test    ax, ax
0x180033b18  jz      short loc_180033B2F
0x180033b1a  mov     [r9], ax
0x180033b1e  add     r8, 2
0x180033b22  add     r9, 2
0x180033b26  dec     rcx
0x180033b29  sub     rdx, 1
0x180033b2d  jnz     short loc_180033B0C
0x180033b2f  test    rdx, rdx
0x180033b32  lea     rcx, [r9-2]
0x180033b36  cmovnz  rcx, r9
0x180033b3a  mov     [rcx], r11w
0x180033b3e  mov     rax, [rbp+220h+var_270]
0x180033b42  lea     rcx, [rbp+220h+var_270]
0x180033b46  mov     [rsp+320h+phNewUSKey], r11
0x180033b4b  mov     rax, [rax+10h]
0x180033b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b54  cmp     dword ptr [rbp+220h+var_25C], 0
0x180033b58  jnz     loc_180033FFB
0x180033b5e  mov     eax, [rbp+220h+var_260]
0x180033b61  lea     r9, [rsp+320h+phNewUSKey]; phNewUSKey
0x180033b66  mov     [rsp+320h+fIgnoreHKCU], eax; fIgnoreHKCU
0x180033b6a  xor     r8d, r8d; hRelativeUSKey
0x180033b6d  lea     rcx, [rbp+220h+pwzPath]; pwzPath
0x180033b71  mov     edx, 20019h; samDesired
0x180033b76  call    cs:__imp_SHRegOpenUSKeyW
0x180033b7c  test    eax, eax
0x180033b7e  jnz     short loc_180033BA1
0x180033b80  mov     rax, [rsp+320h+phNewUSKey]
0x180033b85  lea     rcx, [rbp+220h+pwzPath]; pszSrch
0x180033b89  mov     [rbp+220h+var_268], rax
0x180033b8d  call    cs:__imp_StrDupW
0x180033b93  mov     [r12+18h], rax
0x180033b98  test    rax, rax
0x180033b9b  jz      loc_18003410E
0x180033ba1  cmp     qword ptr [r12+10h], 0
0x180033ba7  jz      loc_180034102
0x180033bad  mov     rcx, r13; pszSrch
0x180033bb0  call    cs:__imp_StrDupW
0x180033bb6  mov     [r12+8], rax
0x180033bbb  test    rax, rax
0x180033bbe  jz      loc_18003410E
0x180033bc4  mov     [rsp+320h+var_2D8], 0FFFFFFFFh
0x180033bcc  test    r14d, 0FFFFFFFDh
0x180033bd3  jnz     loc_18003425C
0x180033bd9  mov     rcx, rax; pszSrc
0x180033bdc  call    cs:__imp_StrToIntW
0x180033be2  mov     [r12], eax
0x180033be6  cmp     r14d, 1
0x180033bea  jz      loc_180034287
0x180033bf0  lea     r14, ??_7CRegKey@@6B@; const CRegKey::`vftable'
  ... truncated ...
```
