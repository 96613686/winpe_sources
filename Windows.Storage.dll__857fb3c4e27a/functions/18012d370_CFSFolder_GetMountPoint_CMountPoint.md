# CFSFolder::_GetMountPoint(CMountPoint * *)

- ea: `0x18012d370`
- end: `0x18012db9d`
- name: `?_GetMountPoint@CFSFolder@@IEAAJPEAPEAVCMountPoint@@@Z`
- size: `2093`
- prototype: `__int64 __fastcall(CFSFolder *__hidden this, struct CMountPoint **)`
- caller_count: `6`
- callee_count: `17`
- tags: `reparse_path, loader_planting, service_task, broker_com_uri`

## callers

- `0x18012ce88`
- `0x18012e870`
- `0x18013189c`
- `0x18027a680`
- `0x180296440`
- `0x18031b220`

## callees

- `0x1800412a0`
- `0x1800432f0`
- `0x1800451f0`
- `0x18009d164`
- `0x1800a743c`
- `0x18012c990`
- `0x18012d080`
- `0x18012d370`
- `0x18012dbb0`
- `0x18012e3c0`
- `0x180148460`
- `0x1802ac0a0`
- `0x1803460c8`
- `0x1803a4cb0`
- `0x1803a570a`
- `0x1803a57e0`
- `0x1803a96e5`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18012db57`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18012db57`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012d4c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012d4c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012d60a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012d60a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012d7c7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012d976`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012d7c7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18012d976`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x18012d870`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x18012d870`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18012d4b4`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18012d4b4`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18012d6fa`
- `api-ms-win-core-path-l1-1-0!PathCchAddBackslash` at `0x18012d6fa`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18012d76c`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18012da22`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18012d76c`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18012da22`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18012d487`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18012d487`
- `OLEAUT32!__imp_SysAllocString` at `0x18012db2e`
- `OLEAUT32!__imp_SysAllocString` at `0x18012db2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18012d421`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18012d421`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012d63a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012d6b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012d63a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18012d6b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFSFolder::_GetMountPoint(CFSFolder *this, struct CMountPoint **a2)
{
  struct CMtPtLocal *v2; // rsi
  const KNOWNFOLDERID *v4; // rcx
  __int64 v5; // rax
  _BYTE *v6; // rbx
  __int64 v7; // rcx
  char *v8; // rax
  size_t v9; // rdi
  size_t v10; // r14
  WCHAR *v11; // rax
  __int64 v12; // r8
  const WCHAR *v13; // rsi
  WCHAR *v14; // r12
  volatile signed __int32 *v15; // rdi
  int DriveNumberW; // ebx
  int Error; // r15d
  int v18; // r13d
  __int64 v19; // rbx
  WCHAR *v20; // r14
  WCHAR *v21; // r8
  unsigned __int64 v22; // rsi
  unsigned __int64 v23; // rdi
  struct CMountPoint *v24; // rdi
  __int64 v25; // r8
  int v26; // ebx
  WCHAR *v27; // rcx
  HRESULT v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r9
  unsigned __int64 v32; // rdx
  const WCHAR *v33; // rax
  const WCHAR *i; // rcx
  WCHAR *v35; // r8
  unsigned __int64 v36; // rsi
  unsigned __int64 v37; // rdi
  __int64 v38; // rcx
  WCHAR *v39; // rdx
  __int64 v40; // r8
  WCHAR v41; // ax
  _WORD *v42; // rcx
  unsigned __int64 v43; // rdx
  _WORD *v44; // rax
  unsigned __int64 j; // rcx
  __int64 v46; // rcx
  __int64 v47; // r8
  WCHAR *p_szVolumePathName; // rdx
  WCHAR v49; // ax
  WCHAR *v50; // rcx
  const ITEMIDLIST *v51; // rcx
  HRESULT v52; // eax
  __int64 v53; // rcx
  const ITEMIDLIST *v54; // rcx
  int bIgnoreCase; // [rsp+20h] [rbp-E0h]
  volatile signed __int32 *v56; // [rsp+30h] [rbp-D0h]
  int v57; // [rsp+38h] [rbp-C8h]
  int v58; // [rsp+3Ch] [rbp-C4h]
  LPCWSTR pszPath; // [rsp+40h] [rbp-C0h] BYREF
  struct CMountPoint *v60[2]; // [rsp+48h] [rbp-B8h] BYREF
  struct CMtPtLocal *v61[3]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR szVolumePathName; // [rsp+70h] [rbp-90h] BYREF
  char v63[526]; // [rsp+72h] [rbp-8Eh] BYREF
  WCHAR v64[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR v65[264]; // [rsp+490h] [rbp+390h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6E8h] [rbp+5E8h]

  v2 = (struct CMtPtLocal *)a2;
  v61[0] = (struct CMtPtLocal *)a2;
  *a2 = 0;
  pszPath = 0;
  v4 = (const KNOWNFOLDERID *)((char *)this + 496);
  v5 = *(_QWORD *)&v4->Data1 - *(_QWORD *)&GUID_NULL.Data1;
  if ( *(_QWORD *)&v4->Data1 == *(_QWORD *)&GUID_NULL.Data1 )
    v5 = *(_QWORD *)v4->Data4 - *(_QWORD *)GUID_NULL.Data4;
  if ( v5 )
  {
    v29 = SHGetKnownFolderPath(v4, 0x4000u, 0, (PWSTR *)&pszPath);
    v26 = v29;
    if ( v29 >= 0 )
      goto LABEL_13;
    v30 = 1163;
    goto LABEL_51;
  }
  v6 = (_BYTE *)*((_QWORD *)this + 56);
  if ( !v6 )
  {
    v51 = (const ITEMIDLIST *)*((_QWORD *)this + 55);
    if ( v51 )
    {
      v52 = SHGetNameFromIDList(v51, SIGDN_DESKTOPABSOLUTEPARSING, (PWSTR *)&pszPath);
      v26 = v52;
      if ( v52 < 0 )
      {
        v30 = 1177;
        v31 = (unsigned int)v52;
        goto LABEL_53;
      }
LABEL_126:
      if ( pszPath )
      {
        *((_QWORD *)this + 56) = SysAllocString(pszPath);
        goto LABEL_13;
      }
      v26 = -2147024893;
LABEL_54:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2214,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
        (const char *)(unsigned int)v26,
        bIgnoreCase);
      v27 = (WCHAR *)pszPath;
      goto LABEL_55;
    }
    v54 = (const ITEMIDLIST *)*((_QWORD *)this + 54);
    if ( !v54 )
      goto LABEL_126;
    v29 = SHGetNameFromIDList(v54, SIGDN_DESKTOPABSOLUTEPARSING, (PWSTR *)&pszPath);
    v26 = v29;
    if ( v29 >= 0 )
      goto LABEL_126;
    v30 = 1181;
LABEL_51:
    v31 = (unsigned int)v29;
LABEL_53:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)v31,
      bIgnoreCase);
    goto LABEL_54;
  }
  v7 = 0x7FFFFFFF;
  v8 = (char *)*((_QWORD *)this + 56);
  do
  {
    if ( !*(_WORD *)v8 )
      break;
    v8 += 2;
    --v7;
  }
  while ( v7 );
  v9 = 2 * ((v8 - v6) >> 1);
  v10 = v9 + 2;
  v11 = (WCHAR *)CoTaskMemAlloc(v9 + 2);
  v13 = v11;
  if ( !v11 )
  {
    pszPath = 0;
    v26 = -2147024882;
    v31 = 2147942414LL;
    v30 = 1171;
    goto LABEL_53;
  }
  if ( v9 )
  {
    if ( v10 < v9 )
    {
      memset_0(v11, 0, v10);
      *(_DWORD *)_o__errno(v53) = 34;
      invalid_parameter_noinfo();
    }
    else
    {
      memcpy_0(v11, v6, v9);
    }
  }
  v13[v9 / 2] = 0;
  pszPath = v13;
  v2 = v61[0];
LABEL_13:
  v14 = (WCHAR *)pszPath;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      &Shell32_MountPoint_GetMountPoint_Start,
      v12,
      1,
      v60);
  *(_QWORD *)v2 = 0;
  v15 = 0;
  v56 = 0;
  v60[0] = 0;
  DriveNumberW = PathGetDriveNumberW(v14);
  v57 = DriveNumberW;
  if ( DriveNumberW != -1 )
  {
    InitOnceExecuteOnce(
      &stru_180803DC0,
      _lambda_c12b5e827bbdb1597ce6a3af58750a50_::_lambda_invoker_cdecl_,
      &Parameter,
      0);
    EnterCriticalSection(&Parameter);
    if ( !HIDWORD(qword_1808041C0) )
    {
      if ( CMountPoint::_ExtractDriveLetter(v14) || (unsigned int)CMountPoint::_IsNetDriveLazyLoadNetDLLs(DriveNumberW) )
      {
        CMountPoint::_GetMountPointForDriveLetter(DriveNumberW, v60);
        v24 = v60[0];
        goto LABEL_40;
      }
      memset_0(v63, 0, 0x206u);
      szVolumePathName = 0;
      Error = 1;
      if ( qword_1808041A8 )
      {
        v58 = *(_DWORD *)qword_1808041A8;
        v18 = 0;
        if ( *(int *)qword_1808041A8 > 0 )
        {
          while ( 1 )
          {
            if ( v15 )
            {
LABEL_37:
              DriveNumberW = v57;
              v2 = v61[0];
              if ( szVolumePathName )
                goto LABEL_38;
              goto LABEL_65;
            }
            v19 = qword_1808041A8 && v18 >= 0 && v18 < *(_DWORD *)qword_1808041A8
                ? *(_QWORD *)(*(_QWORD *)(qword_1808041A8 + 8) + 8LL * v18)
                : 0LL;
            v20 = (WCHAR *)(v19 + 520);
            if ( (unsigned __int64)(v19 + 520) < 0x10000 )
            {
              if ( SHGetFolderPathW(0, (unsigned int)v20 | 0x4000, 0, 0, v64) < 0 )
                goto LABEL_36;
              v21 = v64;
            }
            else
            {
              v21 = (WCHAR *)(v19 + 520);
            }
            v22 = -1;
            do
              ++v22;
            while ( v21[v22] );
            if ( v22 && v21[v22 - 1] == 92 )
              --v22;
            v23 = -1;
            do
              ++v23;
            while ( v14[v23] );
            if ( v23 && v14[v23 - 1] == 92 )
              --v23;
            if ( v22 <= v23 )
            {
              v32 = v22;
              if ( v14[v22] != 92 )
                v32 = v23;
              if ( v32 == v22 && CompareStringOrdinal(v14, v32, v21, v22, 1) == 2 )
                break;
            }
LABEL_35:
            v15 = v56;
LABEL_36:
            if ( ++v18 >= v58 )
              goto LABEL_37;
          }
          if ( v22 < v23 )
          {
            v33 = &v14[v22 + 1];
            for ( i = &v14[v23]; v33 < i; ++v33 )
            {
              if ( *v33 == 92 )
                break;
            }
          }
          if ( (unsigned __int64)v14 < 0x10000 )
          {
            if ( SHGetFolderPathW(0, (unsigned int)v14 | 0x4000, 0, 0, v65) < 0 )
              goto LABEL_87;
            v35 = v65;
          }
          else
          {
            v35 = v14;
          }
          v36 = -1;
          do
            ++v36;
          while ( v35[v36] );
          if ( v36 && v35[v36 - 1] == 92 )
            --v36;
          v37 = -1;
          do
            ++v37;
          while ( *(_WORD *)(v19 + 2 * v37) );
          if ( v37 && *(_WORD *)(v19 + 2 * v37 - 2) == 92 )
            --v37;
          if ( v36 <= v37 )
          {
            v43 = v36;
            if ( *(_WORD *)(v19 + 2 * v36) != 92 )
              v43 = v37;
            if ( v43 == v36 && CompareStringOrdinal((LPCWCH)v19, v43, v35, v36, 1) == 2 )
            {
              if ( v36 < v37 )
              {
                v44 = (_WORD *)(v19 + 2 * (v36 + 1));
                for ( j = v19 + 2 * v37; (unsigned __int64)v44 < j; ++v44 )
                {
                  if ( *v44 == 92 )
                    break;
                }
              }
              v15 = *(volatile signed __int32 **)(v19 + 1040);
              v56 = v15;
              v60[0] = (struct CMountPoint *)v15;
              _InterlockedIncrement(v15 + 12);
              v46 = 2147483646;
              v47 = 260;
              p_szVolumePathName = &szVolumePathName;
              do
              {
                if ( !v46 )
                  break;
                v49 = *v20;
                if ( !*v20 )
                  break;
                ++v20;
                *p_szVolumePathName++ = v49;
                --v46;
                --v47;
              }
              while ( v47 );
              v50 = p_szVolumePathName - 1;
              if ( v47 )
                v50 = p_szVolumePathName;
              *v50 = 0;
              ++*(_DWORD *)(v19 + 1048);
              Error = 0;
              goto LABEL_36;
            }
          }
LABEL_87:
          if ( (szVolumePathName
             || GetVolumePathNameW(v14, &szVolumePathName, 0x104u)
             || (int)ResultFromKnownLastError() >= 0)
            && !StrCmpIW(&szVolumePathName, (PCWSTR)(v19 + 520)) )
          {
            v15 = *(volatile signed __int32 **)(v19 + 1040);
            v56 = v15;
            v60[0] = (struct CMountPoint *)v15;
            _InterlockedIncrement(v15 + 12);
            v38 = 2147483646;
            v39 = v14;
            v40 = 260;
            do
            {
              if ( !v38 )
                break;
              v41 = *v39;
              if ( !*v39 )
                break;
              ++v39;
              *(_WORD *)v19 = v41;
              v19 += 2;
              --v38;
              --v40;
            }
            while ( v40 );
            v42 = (_WORD *)(v19 - 2);
            if ( v40 )
              v42 = (_WORD *)v19;
            *v42 = 0;
            Error = 0;
            goto LABEL_36;
          }
          goto LABEL_35;
        }
      }
LABEL_65:
      if ( !GetVolumePathNameW(v14, &szVolumePathName, 0x104u) )
        Error = ResultFromKnownLastError();
LABEL_38:
      if ( Error >= 0 && !v15 )
      {
        PathCchAddBackslash(&szVolumePathName, 0x104u);
        if ( CMountPoint::_ExtractDriveLetter(&szVolumePathName) )
        {
          CMountPoint::_GetMountPointForDriveLetter(DriveNumberW, v60);
          v24 = v60[0];
        }
        else
        {
          v61[0] = 0;
          CMountPoint::_GetMountPointForFolder(&szVolumePathName, v61);
          v24 = v61[0];
        }
        if ( v24 )
          CDriveLetterCache::AddPathLookupEntry((CDriveLetterCache *)&unk_180803E68, v14, &szVolumePathName, v24);
        goto LABEL_40;
      }
    }
    v24 = (struct CMountPoint *)v56;
LABEL_40:
    LeaveCriticalSection(&Parameter);
    goto LABEL_41;
  }
  CMountPoint::GetSimulatedMountPointFromVolumeGuid(v14, v60);
  v24 = v60[0];
LABEL_41:
  v26 = -2147467259;
  if ( v24 )
  {
    *(_QWORD *)v2 = v24;
    v26 = 0;
  }
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      &Shell32_MountPoint_GetMountPoint_Stop,
      v25,
      1,
      v61);
  v27 = (WCHAR *)pszPath;
  if ( v26 >= 0 )
  {
    if ( pszPath )
      CoTaskMemFree((LPVOID)pszPath);
    return 0;
  }
LABEL_55:
  if ( v27 )
    CoTaskMemFree(v27);
  return (unsigned int)v26;
}

```

## disassembly

```asm
0x18012d370  mov     [rsp-8+arg_10], rbx
0x18012d375  push    rbp
0x18012d376  push    rsi
0x18012d377  push    rdi
0x18012d378  push    r12
0x18012d37a  push    r13
0x18012d37c  push    r14
0x18012d37e  push    r15
0x18012d380  lea     rbp, [rsp-5B0h]
0x18012d388  sub     rsp, 6B0h
0x18012d38f  mov     rax, cs:__security_cookie
0x18012d396  xor     rax, rsp
0x18012d399  mov     [rbp+5E0h+var_40], rax
0x18012d3a0  mov     rsi, rdx
0x18012d3a3  mov     [rsp+6E0h+var_688], rdx
0x18012d3a8  mov     rdi, rcx
0x18012d3ab  mov     qword ptr [rdx], 0
0x18012d3b2  mov     [rsp+6E0h+pszPath], 0
0x18012d3bb  add     rcx, 1F0h; rfid
0x18012d3c2  mov     rax, [rcx]
0x18012d3c5  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18012d3cc  jnz     short loc_18012D3D9
0x18012d3ce  mov     rax, [rcx+8]
0x18012d3d2  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18012d3d9  test    rax, rax
0x18012d3dc  jnz     loc_18012D644
0x18012d3e2  mov     rbx, [rdi+1C0h]
0x18012d3e9  test    rbx, rbx
0x18012d3ec  jz      loc_18012DAE3
0x18012d3f2  mov     ecx, 7FFFFFFFh
0x18012d3f7  mov     rax, rbx
0x18012d3fa  nop     word ptr [rax+rax+00h]
0x18012d400  cmp     word ptr [rax], 0
0x18012d404  jz      short loc_18012D410
0x18012d406  add     rax, 2
0x18012d40a  sub     rcx, 1
0x18012d40e  jnz     short loc_18012D400
0x18012d410  sub     rax, rbx
0x18012d413  sar     rax, 1
0x18012d416  lea     rdi, [rax+rax]
0x18012d41a  lea     r14, [rdi+2]
0x18012d41e  mov     rcx, r14; cb
0x18012d421  call    cs:__imp_CoTaskMemAlloc
0x18012d427  mov     rsi, rax
0x18012d42a  test    rax, rax
0x18012d42d  jz      loc_18012D66A
0x18012d433  test    rdi, rdi
0x18012d436  jz      short loc_18012D44F
0x18012d438  mov     rcx, rax; void *
0x18012d43b  cmp     r14, rdi
0x18012d43e  jb      loc_18012DB4D
0x18012d444  mov     r8, rdi; Size
0x18012d447  mov     rdx, rbx; Src
0x18012d44a  call    memcpy_0
0x18012d44f  xor     eax, eax
0x18012d451  mov     [rdi+rsi], ax
0x18012d455  mov     [rsp+6E0h+pszPath], rsi
0x18012d45a  mov     rsi, [rsp+6E0h+var_688]
0x18012d45f  mov     r12, [rsp+6E0h+pszPath]
0x18012d464  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18012d46b  jnz     loc_18012D902
0x18012d471  mov     qword ptr [rsi], 0
0x18012d478  xor     edi, edi
0x18012d47a  mov     [rsp+6E0h+var_6B0], rdi
0x18012d47f  mov     [rsp+6E0h+var_698], rdi
0x18012d484  mov     rcx, r12; pszPath
0x18012d487  call    cs:__imp_PathGetDriveNumberW
0x18012d48d  mov     ebx, eax
0x18012d48f  mov     [rsp+6E0h+var_6A8], eax
0x18012d493  cmp     eax, 0FFFFFFFFh
0x18012d496  jz      loc_18012DA42
0x18012d49c  xor     r9d, r9d; Context
0x18012d49f  lea     r8, Parameter; Parameter
0x18012d4a6  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_c12b5e827bbdb1597ce6a3af58750a50_@@CA@PEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18012d4ad  lea     rcx, stru_180803DC0; InitOnce
0x18012d4b4  call    cs:__imp_InitOnceExecuteOnce
0x18012d4ba  lea     rcx, Parameter; lpCriticalSection
0x18012d4c1  call    cs:__imp_EnterCriticalSection
0x18012d4c7  cmp     dword ptr cs:qword_1808041C0+4, edi
0x18012d4cd  jnz     loc_18012D5FE
0x18012d4d3  mov     rcx, r12; unsigned __int16 *
0x18012d4d6  call    ?_ExtractDriveLetter@CMountPoint@@CAGPEBG@Z; CMountPoint::_ExtractDriveLetter(ushort const *)
0x18012d4db  test    ax, ax
0x18012d4de  jnz     loc_18012DB18
0x18012d4e4  mov     ecx, ebx; int
0x18012d4e6  call    ?_IsNetDriveLazyLoadNetDLLs@CMountPoint@@CAHH@Z; CMountPoint::_IsNetDriveLazyLoadNetDLLs(int)
0x18012d4eb  test    eax, eax
0x18012d4ed  jnz     loc_18012DB18
0x18012d4f3  xor     edx, edx; Val
0x18012d4f5  mov     r8d, 206h; Size
0x18012d4fb  lea     rcx, [rsp+6E0h+var_66E]; void *
0x18012d500  call    memset_0
0x18012d505  xor     eax, eax
0x18012d507  mov     [rsp+6E0h+szVolumePathName], ax
0x18012d50c  mov     r15d, 1
0x18012d512  mov     rax, cs:qword_1808041A8
0x18012d519  test    rax, rax
0x18012d51c  jz      loc_18012D75E
0x18012d522  mov     eax, [rax]
0x18012d524  mov     [rsp+6E0h+var_6A4], eax
0x18012d528  xor     r13d, r13d
0x18012d52b  test    eax, eax
0x18012d52d  jle     loc_18012D75E
0x18012d533  test    rdi, rdi
0x18012d536  jnz     loc_18012D5E0
0x18012d53c  mov     rax, cs:qword_1808041A8
0x18012d543  test    rax, rax
0x18012d546  jz      loc_18012D79C
0x18012d54c  test    r13d, r13d
0x18012d54f  js      loc_18012D79C
0x18012d555  cmp     r13d, [rax]
0x18012d558  jge     loc_18012D79C
0x18012d55e  movsxd  rcx, r13d
0x18012d561  mov     rax, [rax+8]
0x18012d565  mov     rbx, [rax+rcx*8]
0x18012d569  lea     r14, [rbx+208h]
0x18012d570  cmp     r14, 10000h
0x18012d577  jb      loc_18012DA7B
0x18012d57d  mov     r8, r14; lpString2
0x18012d580  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18012d587  nop     word ptr [rax+rax+00000000h]
0x18012d590  inc     rsi
0x18012d593  cmp     word ptr [r8+rsi*2], 0
0x18012d599  jnz     short loc_18012D590
0x18012d59b  test    rsi, rsi
0x18012d59e  jnz     loc_18012D787
0x18012d5a4  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18012d5ab  nop     dword ptr [rax+rax+00h]
0x18012d5b0  inc     rdi
0x18012d5b3  cmp     word ptr [r12+rdi*2], 0
0x18012d5b9  jnz     short loc_18012D5B0
0x18012d5bb  test    rdi, rdi
0x18012d5be  jnz     loc_18012D749
0x18012d5c4  cmp     rsi, rdi
0x18012d5c7  jbe     loc_18012D7A3
0x18012d5cd  mov     rdi, [rsp+6E0h+var_6B0]
0x18012d5d2  inc     r13d
0x18012d5d5  cmp     r13d, [rsp+6E0h+var_6A4]
0x18012d5da  jl      loc_18012D533
0x18012d5e0  mov     ebx, [rsp+6E0h+var_6A8]
0x18012d5e4  mov     rsi, [rsp+6E0h+var_688]
0x18012d5e9  cmp     [rsp+6E0h+szVolumePathName], 0
0x18012d5ef  jz      loc_18012D75E
0x18012d5f5  test    r15d, r15d
0x18012d5f8  jns     loc_18012D6E7
0x18012d5fe  mov     rdi, [rsp+6E0h+var_6B0]
0x18012d603  lea     rcx, Parameter; lpCriticalSection
0x18012d60a  call    cs:__imp_LeaveCriticalSection
0x18012d610  mov     ebx, 80004005h
0x18012d615  test    rdi, rdi
0x18012d618  jz      short loc_18012D61F
0x18012d61a  mov     [rsi], rdi
0x18012d61d  xor     ebx, ebx
0x18012d61f  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x18012d626  jnz     loc_18012D8DA
0x18012d62c  mov     rcx, [rsp+6E0h+pszPath]; pv
0x18012d631  test    ebx, ebx
0x18012d633  js      short loc_18012D6B0
0x18012d635  test    rcx, rcx
0x18012d638  jz      short loc_18012D640
0x18012d63a  call    cs:__imp_CoTaskMemFree
0x18012d640  xor     eax, eax
0x18012d642  jmp     short loc_18012D6BD
0x18012d644  lea     r9, [rsp+6E0h+pszPath]; ppszPath
0x18012d649  xor     r8d, r8d; hToken
0x18012d64c  mov     edx, 4000h; dwFlags
0x18012d651  call    SHGetKnownFolderPath
0x18012d656  mov     ebx, eax
0x18012d658  test    eax, eax
0x18012d65a  jns     loc_18012D45F
0x18012d660  mov     edx, 48Bh
0x18012d665  mov     r9d, eax
0x18012d668  jmp     short loc_18012D67C
0x18012d66a  mov     [rsp+6E0h+pszPath], rsi
0x18012d66f  mov     ebx, 8007000Eh
0x18012d674  mov     r9d, ebx; char *
0x18012d677  mov     edx, 493h; void *
0x18012d67c  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x18012d683  mov     rcx, [rbp+5E8h]; this
0x18012d68a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012d68f  mov     rcx, [rbp+5E8h]; this
0x18012d696  mov     r9d, ebx; char *
0x18012d699  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x18012d6a0  mov     edx, 2214h; void *
0x18012d6a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012d6aa  nop
0x18012d6ab  mov     rcx, [rsp+6E0h+pszPath]; pv
0x18012d6b0  test    rcx, rcx
0x18012d6b3  jz      short loc_18012D6BB
0x18012d6b5  call    cs:__imp_CoTaskMemFree
0x18012d6bb  mov     eax, ebx
0x18012d6bd  mov     rcx, [rbp+5E0h+var_40]
0x18012d6c4  xor     rcx, rsp; StackCookie
0x18012d6c7  call    __security_check_cookie
0x18012d6cc  mov     rbx, [rsp+6E0h+arg_10]
0x18012d6d4  add     rsp, 6B0h
0x18012d6db  pop     r15
0x18012d6dd  pop     r14
0x18012d6df  pop     r13
0x18012d6e1  pop     r12
0x18012d6e3  pop     rdi
0x18012d6e4  pop     rsi
0x18012d6e5  pop     rbp
0x18012d6e6  retn
0x18012d6e7  test    rdi, rdi
0x18012d6ea  jnz     loc_18012D5FE
0x18012d6f0  mov     edx, 104h; cchPath
0x18012d6f5  lea     rcx, [rsp+6E0h+szVolumePathName]; pszPath
0x18012d6fa  call    cs:__imp_PathCchAddBackslash
0x18012d700  lea     rcx, [rsp+6E0h+szVolumePathName]; unsigned __int16 *
0x18012d705  call    ?_ExtractDriveLetter@CMountPoint@@CAGPEBG@Z; CMountPoint::_ExtractDriveLetter(ushort const *)
0x18012d70a  test    ax, ax
0x18012d70d  jz      loc_18012DA59
0x18012d713  lea     rdx, [rsp+6E0h+var_698]; struct CMountPoint **
0x18012d718  mov     ecx, ebx; int
0x18012d71a  call    ?_GetMountPointForDriveLetter@CMountPoint@@CAJHPEAPEAV1@@Z; CMountPoint::_GetMountPointForDriveLetter(int,CMountPoint * *)
0x18012d71f  mov     rdi, [rsp+6E0h+var_698]
0x18012d724  test    rdi, rdi
0x18012d727  jz      loc_18012D603
0x18012d72d  mov     r9, rdi; struct CMountPoint *
0x18012d730  lea     r8, [rsp+6E0h+szVolumePathName]; unsigned __int16 *
0x18012d735  mov     rdx, r12; unsigned __int16 *
0x18012d738  lea     rcx, unk_180803E68; this
0x18012d73f  call    ?AddPathLookupEntry@CDriveLetterCache@@QEAAJPEBG0PEAVCMountPoint@@@Z; CDriveLetterCache::AddPathLookupEntry(ushort const *,ushort const *,CMountPoint *)
0x18012d744  jmp     loc_18012D603
0x18012d749  cmp     word ptr [r12+rdi*2-2], 5Ch ; '\'
0x18012d750  jnz     loc_18012D5C4
0x18012d756  dec     rdi
0x18012d759  jmp     loc_18012D5C4
0x18012d75e  mov     r8d, 104h; cchBufferLength
0x18012d764  lea     rdx, [rsp+6E0h+szVolumePathName]; lpszVolumePathName
0x18012d769  mov     rcx, r12; lpszFileName
0x18012d76c  call    cs:__imp_GetVolumePathNameW
0x18012d772  test    eax, eax
0x18012d774  jnz     loc_18012D5F5
0x18012d77a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18012d77f  mov     r15d, eax
0x18012d782  jmp     loc_18012D5F5
0x18012d787  cmp     word ptr [r8+rsi*2-2], 5Ch ; '\'
0x18012d78e  jnz     loc_18012D5A4
0x18012d794  dec     rsi
0x18012d797  jmp     loc_18012D5A4
0x18012d79c  xor     ebx, ebx
0x18012d79e  jmp     loc_18012D569
0x18012d7a3  mov     rdx, rsi
0x18012d7a6  cmp     word ptr [r12+rsi*2], 5Ch ; '\'
0x18012d7ac  cmovnz  rdx, rdi; cchCount1
0x18012d7b0  cmp     rdx, rsi
0x18012d7b3  jnz     loc_18012D5CD
0x18012d7b9  mov     r9d, esi; cchCount2
0x18012d7bc  mov     [rsp+6E0h+bIgnoreCase], 1; bIgnoreCase
0x18012d7c4  mov     rcx, r12; lpString1
0x18012d7c7  call    cs:__imp_CompareStringOrdinal
0x18012d7cd  cmp     eax, 2
0x18012d7d0  jnz     loc_18012D5CD
0x18012d7d6  cmp     rsi, rdi
0x18012d7d9  jnb     short loc_18012D7FF
0x18012d7db  lea     rax, [r12+2]
0x18012d7e0  lea     rax, [rax+rsi*2]
0x18012d7e4  lea     rcx, [r12+rdi*2]
0x18012d7e8  cmp     rax, rcx
0x18012d7eb  jnb     short loc_18012D7FF
0x18012d7ed  nop     dword ptr [rax]
0x18012d7f0  cmp     word ptr [rax], 5Ch ; '\'
0x18012d7f4  jz      short loc_18012D7FF
0x18012d7f6  add     rax, 2
0x18012d7fa  cmp     rax, rcx
0x18012d7fd  jb      short loc_18012D7F0
0x18012d7ff  cmp     r12, 10000h
0x18012d806  jb      loc_18012DAAF
0x18012d80c  mov     r8, r12; lpString2
0x18012d80f  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18012d816  nop     word ptr [rax+rax+00000000h]
0x18012d820  inc     rsi
0x18012d823  cmp     word ptr [r8+rsi*2], 0
0x18012d829  jnz     short loc_18012D820
0x18012d82b  test    rsi, rsi
0x18012d82e  jnz     loc_18012D93E
0x18012d834  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18012d83b  nop     dword ptr [rax+rax+00h]
0x18012d840  inc     rdi
0x18012d843  cmp     word ptr [rbx+rdi*2], 0
0x18012d848  jnz     short loc_18012D840
0x18012d84a  test    rdi, rdi
0x18012d84d  jnz     loc_18012D92A
0x18012d853  cmp     rsi, rdi
0x18012d856  jbe     loc_18012D953
0x18012d85c  cmp     [rsp+6E0h+szVolumePathName], 0
0x18012d862  jz      loc_18012DA14
0x18012d868  mov     rdx, r14; psz2
0x18012d86b  lea     rcx, [rsp+6E0h+szVolumePathName]; psz1
0x18012d870  call    cs:__imp_StrCmpIW
0x18012d876  test    eax, eax
0x18012d878  jnz     loc_18012D5CD
0x18012d87e  mov     rdi, [rbx+410h]
0x18012d885  mov     [rsp+6E0h+var_6B0], rdi
0x18012d88a  mov     [rsp+6E0h+var_698], rdi
0x18012d88f  lock inc dword ptr [rdi+30h]
0x18012d893  mov     ecx, 7FFFFFFEh
0x18012d898  mov     rdx, r12
  ... truncated ...
```
