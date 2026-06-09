# PrintRandomDocument

- ea: `0x180036f80`
- end: `0x180038189`
- name: `PrintRandomDocument`
- size: `4617`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180038190`

## callees

- `0x1800084ac`
- `0x18000abe4`
- `0x18000ac14`
- `0x18002bb58`
- `0x18002dff4`
- `0x18002ea78`
- `0x1800309c4`
- `0x1800366d0`
- `0x180036dbc`
- `0x180036f80`
- `0x18003d014`
- `0x18003d4ca`
- `0x18003d4e2`
- `0x18003d510`

## import_xrefs

- `msvcrt!wcschr` at `0x180037a1c`
- `msvcrt!wcschr` at `0x180037a1c`
- `msvcrt!_wsplitpath_s` at `0x18003714b`
- `msvcrt!_wsplitpath_s` at `0x1800372d4`
- `msvcrt!_wsplitpath_s` at `0x18003714b`
- `msvcrt!_wsplitpath_s` at `0x1800372d4`
- `msvcrt!_wcsnicmp` at `0x180037d69`
- `msvcrt!_wcsnicmp` at `0x180037d90`
- `msvcrt!_wcsnicmp` at `0x180037d69`
- `msvcrt!_wcsnicmp` at `0x180037d90`
- `msvcrt!wcsrchr` at `0x180037042`
- `msvcrt!wcsrchr` at `0x180037d38`
- `msvcrt!wcsrchr` at `0x180037042`
- `msvcrt!wcsrchr` at `0x180037d38`
- `msvcrt!_wcsicmp` at `0x180037bd9`
- `msvcrt!_wcsicmp` at `0x180037bd9`
- `KERNEL32!GetTempPath2W` at `0x1800370bd`
- `KERNEL32!GetTempPath2W` at `0x1800370bd`
- `KERNEL32!DeleteFileW` at `0x1800380d9`
- `KERNEL32!DeleteFileW` at `0x1800380d9`
- `KERNEL32!Sleep` at `0x18003812d`
- `KERNEL32!Sleep` at `0x18003812d`
- `KERNEL32!CreateEventW` at `0x1800375ad`
- `KERNEL32!CreateEventW` at `0x1800375ad`
- `KERNEL32!UnmapViewOfFile` at `0x180037f68`
- `KERNEL32!UnmapViewOfFile` at `0x180037f68`
- `KERNEL32!CopyFileW` at `0x180037243`
- `KERNEL32!CopyFileW` at `0x180037243`
- `KERNEL32!CreateFileMappingW` at `0x180037867`
- `KERNEL32!CreateFileMappingW` at `0x180037867`
- `KERNEL32!WaitForSingleObject` at `0x18003745f`
- `KERNEL32!WaitForSingleObject` at `0x18003745f`
- `KERNEL32!ReleaseMutex` at `0x18003801e`
- `KERNEL32!ReleaseMutex` at `0x18003801e`
- `KERNEL32!CloseHandle` at `0x1800374b1`
- `KERNEL32!CloseHandle` at `0x180037690`
- `KERNEL32!CloseHandle` at `0x1800376fb`
- `KERNEL32!CloseHandle` at `0x180037eea`
- `KERNEL32!CloseHandle` at `0x180037fc3`
- `KERNEL32!CloseHandle` at `0x180038070`
- `KERNEL32!CloseHandle` at `0x1800374b1`
- `KERNEL32!CloseHandle` at `0x180037690`
- `KERNEL32!CloseHandle` at `0x1800376fb`
- `KERNEL32!CloseHandle` at `0x180037eea`
- `KERNEL32!CloseHandle` at `0x180037fc3`
- `KERNEL32!CloseHandle` at `0x180038070`
- `KERNEL32!SetLastError` at `0x18003709e`
- `KERNEL32!SetLastError` at `0x180037189`
- `KERNEL32!SetLastError` at `0x1800380c6`
- `KERNEL32!SetLastError` at `0x18003709e`
- `KERNEL32!SetLastError` at `0x180037189`
- `KERNEL32!SetLastError` at `0x1800380c6`
- `KERNEL32!GetLastError` at `0x1800370e9`
- `KERNEL32!GetLastError` at `0x180037200`
- `KERNEL32!GetLastError` at `0x180037255`
- `KERNEL32!GetLastError` at `0x180037348`
- `KERNEL32!GetLastError` at `0x18003739e`
- `KERNEL32!GetLastError` at `0x180037400`
- `KERNEL32!GetLastError` at `0x180037470`
- `KERNEL32!GetLastError` at `0x18003754d`
- `KERNEL32!GetLastError` at `0x1800375ca`
- `KERNEL32!GetLastError` at `0x18003765a`
- `KERNEL32!GetLastError` at `0x1800376bc`
- `KERNEL32!GetLastError` at `0x18003773e`
- `KERNEL32!GetLastError` at `0x180037797`
- `KERNEL32!GetLastError` at `0x180037802`
- `KERNEL32!GetLastError` at `0x18003787f`
- `KERNEL32!GetLastError` at `0x180037913`
- `KERNEL32!GetLastError` at `0x180037c0f`
- `KERNEL32!GetLastError` at `0x180037c70`
- `KERNEL32!GetLastError` at `0x180037ce2`
- `KERNEL32!GetLastError` at `0x180037e0c`
- `KERNEL32!GetLastError` at `0x180037f1d`
- `KERNEL32!GetLastError` at `0x180037f94`
- `KERNEL32!GetLastError` at `0x180037fef`
- `KERNEL32!GetLastError` at `0x18003804a`
- `KERNEL32!GetLastError` at `0x18003809c`
- `KERNEL32!GetLastError` at `0x180038105`
- `KERNEL32!GetLastError` at `0x1800370e9`
- `KERNEL32!GetLastError` at `0x180037200`
- `KERNEL32!GetLastError` at `0x180037255`
- `KERNEL32!GetLastError` at `0x180037348`
- `KERNEL32!GetLastError` at `0x18003739e`
- `KERNEL32!GetLastError` at `0x180037400`
- `KERNEL32!GetLastError` at `0x180037470`
- `KERNEL32!GetLastError` at `0x18003754d`
- `KERNEL32!GetLastError` at `0x1800375ca`
- `KERNEL32!GetLastError` at `0x18003765a`
- `KERNEL32!GetLastError` at `0x1800376bc`
- `KERNEL32!GetLastError` at `0x18003773e`
- `KERNEL32!GetLastError` at `0x180037797`
- `KERNEL32!GetLastError` at `0x180037802`
- `KERNEL32!GetLastError` at `0x18003787f`
- `KERNEL32!GetLastError` at `0x180037913`
- `KERNEL32!GetLastError` at `0x180037c0f`
- `KERNEL32!GetLastError` at `0x180037c70`
- `KERNEL32!GetLastError` at `0x180037ce2`
- `KERNEL32!GetLastError` at `0x180037e0c`
- `KERNEL32!GetLastError` at `0x180037f1d`
- `KERNEL32!GetLastError` at `0x180037f94`
- `KERNEL32!GetLastError` at `0x180037fef`
- `KERNEL32!GetLastError` at `0x18003804a`
- `KERNEL32!GetLastError` at `0x18003809c`
- `KERNEL32!GetLastError` at `0x180038105`
- `KERNEL32!WaitForMultipleObjects` at `0x180037dfb`
- `KERNEL32!WaitForMultipleObjects` at `0x180037dfb`
- `KERNEL32!SetEnvironmentVariableW` at `0x18003762e`
- `KERNEL32!SetEnvironmentVariableW` at `0x180037787`
- `KERNEL32!SetEnvironmentVariableW` at `0x18003762e`
- `KERNEL32!SetEnvironmentVariableW` at `0x180037787`
- `KERNEL32!CreateMutexW` at `0x1800373e7`
- `KERNEL32!CreateMutexW` at `0x180037c5c`
- `KERNEL32!CreateMutexW` at `0x1800373e7`
- `KERNEL32!CreateMutexW` at `0x180037c5c`
- `KERNEL32!MapViewOfFile` at `0x1800378f7`
- `KERNEL32!MapViewOfFile` at `0x1800378f7`
- `KERNEL32!OpenMutexW` at `0x18003732b`
- `KERNEL32!OpenMutexW` at `0x18003732b`
- `SHELL32!ShellExecuteExW` at `0x180037cce`
- `SHELL32!ShellExecuteExW` at `0x180037cce`

## pseudocode

```c
__int64 __fastcall PrintRandomDocument(__int64 a1, const wchar_t *a2, const wchar_t *a3)
{
  wchar_t *v5; // rax
  wchar_t *v6; // r15
  wchar_t *v7; // rcx
  DWORD v8; // eax
  DWORD v9; // edi
  __int64 v11; // rbx
  DWORD LastError; // eax
  __int64 v13; // r8
  wchar_t *p_String1; // r13
  __int64 v15; // rbx
  DWORD v16; // eax
  unsigned int v17; // r13d
  void *v18; // r14
  DWORD v19; // eax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  HANDLE v22; // rax
  struct _SECURITY_ATTRIBUTES *SecurityAttributesWithThreadAsOwner; // rax
  struct _SECURITY_ATTRIBUTES *v24; // rbx
  DWORD v25; // eax
  DWORD v26; // eax
  DWORD v27; // eax
  HANDLE v28; // r12
  struct _SECURITY_ATTRIBUTES *v29; // rsi
  unsigned int i; // ebx
  HANDLE EventW; // rax
  __int64 v32; // rbx
  DWORD v33; // eax
  __int64 j; // rsi
  HANDLE v35; // rcx
  __int64 v36; // rbx
  DWORD v37; // eax
  __int64 v38; // rbx
  DWORD v39; // eax
  DWORD v40; // eax
  _QWORD *v41; // rcx
  __int64 v42; // rdx
  struct _SECURITY_ATTRIBUTES *v43; // rbx
  size_t v44; // r15
  HANDLE v45; // rsi
  DWORD v46; // eax
  DWORD v47; // eax
  _QWORD *v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // r14
  unsigned __int64 v51; // rsi
  __int64 v52; // rax
  __int64 v53; // rdx
  const wchar_t *v54; // rcx
  wchar_t *v55; // r8
  wchar_t *v56; // rcx
  unsigned int v57; // ebx
  _QWORD *v58; // rcx
  __int64 v59; // rdx
  wchar_t *v60; // rdx
  __int64 v61; // rax
  wchar_t *v62; // rax
  wchar_t *v63; // rcx
  __int64 v64; // rsi
  int v65; // eax
  DWORD v66; // ebx
  struct _SECURITY_ATTRIBUTES *v67; // rax
  struct _SECURITY_ATTRIBUTES *v68; // rbx
  DWORD v69; // eax
  wchar_t *v70; // rax
  const wchar_t *v71; // rbx
  size_t v72; // r8
  DWORD v73; // eax
  DWORD v74; // eax
  __int64 v75; // rbx
  DWORD v76; // eax
  __int64 v77; // rbx
  DWORD v78; // eax
  __int64 v79; // rbx
  DWORD v80; // eax
  __int64 v81; // rbx
  DWORD v82; // eax
  __int64 v83; // rbx
  DWORD v84; // eax
  unsigned int k; // r13d
  __int64 v86; // rbx
  DWORD v87; // eax
  int v88; // [rsp+50h] [rbp-B0h]
  HANDLE MutexW; // [rsp+60h] [rbp-A0h]
  wchar_t *Str; // [rsp+68h] [rbp-98h]
  LPVOID lpName[3]; // [rsp+70h] [rbp-90h] BYREF
  HANDLE FileMappingW; // [rsp+88h] [rbp-78h]
  HANDLE hObject[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v94; // [rsp+A0h] [rbp-60h]
  SHELLEXECUTEINFOW pExecInfo; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR NewFileName[264]; // [rsp+120h] [rbp+20h] BYREF
  wchar_t String1; // [rsp+330h] [rbp+230h] BYREF
  wchar_t v98[255]; // [rsp+332h] [rbp+232h] BYREF
  wchar_t Filename[256]; // [rsp+530h] [rbp+430h] BYREF
  _BYTE v100[528]; // [rsp+730h] [rbp+630h] BYREF
  unsigned __int16 v101[520]; // [rsp+940h] [rbp+840h] BYREF

  v94 = a1;
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  *(_OWORD *)hObject = 0;
  *(_OWORD *)lpName = 0;
  memset_0(&String1, 0, 0x200u);
  memset_0(Filename, 0, sizeof(Filename));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids);
  }
  v5 = wcsrchr(a3, 0x5Cu);
  v6 = 0;
  v7 = v5 + 1;
  if ( !v5 )
    v7 = 0;
  v8 = PrepareDriverEventNames(v7, lpName, &lpName[1]);
  v9 = v8;
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v8);
    }
    SetLastError(v9);
    return 0;
  }
  if ( !(unsigned int)GetTempPath2W(260, v100) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      LastError = GetLastError();
      WPP_SF_d(v11, 92, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, LastError);
    }
LABEL_19:
    pMemFree(lpName[0]);
    pMemFree(lpName[1]);
    return 0;
  }
  if ( _wsplitpath_s(a2, 0, 0, 0, 0, 0, 0, &String1, 0x100u) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 93, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids);
    }
    SetLastError(0x65Bu);
    goto LABEL_19;
  }
  p_String1 = &String1;
  if ( !wcsncmp_0(&String1, L".", 1u) )
    p_String1 = v98;
  if ( GenerateUniqueFileNameWithPrefix(v98, v100, v13, p_String1, NewFileName) )
  {
    FileMappingW = 0;
    v88 = 0;
    v18 = 0;
    if ( !CopyFileW(a2, NewFileName, 0) )
    {
      v19 = GetLastError();
      v9 = v19;
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_95;
      }
      v21 = 95;
LABEL_39:
      WPP_SF_d(v20[2], v21, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v19);
LABEL_95:
      v28 = 0;
      goto LABEL_96;
    }
    if ( _wsplitpath_s(NewFileName, 0, 0, 0, 0, Filename, 0x100u, 0, 0) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids);
      }
      v9 = 1627;
      goto LABEL_95;
    }
    v22 = OpenMutexW(0x1F0001u, 0, L"MS_FAXXP_ATTACHMENT_MUTEX");
    MutexW = v22;
    v18 = v22;
    if ( !v22 )
    {
      v19 = GetLastError();
      v9 = v19;
      if ( v19 != 2 )
      {
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_95;
        }
        v21 = 97;
        goto LABEL_39;
      }
      SecurityAttributesWithThreadAsOwner = (struct _SECURITY_ATTRIBUTES *)CreateSecurityAttributesWithThreadAsOwner(
                                                                             2031617,
                                                                             2031617,
                                                                             0);
      v9 = 0;
      v24 = SecurityAttributesWithThreadAsOwner;
      if ( !SecurityAttributesWithThreadAsOwner )
      {
        v19 = GetLastError();
        v9 = v19;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_95;
        }
        v21 = 98;
        goto LABEL_39;
      }
      MutexW = CreateMutexW(SecurityAttributesWithThreadAsOwner, 1, L"MS_FAXXP_ATTACHMENT_MUTEX");
      v18 = MutexW;
      if ( !MutexW )
      {
        v25 = GetLastError();
        v9 = v25;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v25);
        }
        DestroySecurityAttributes(v24);
        goto LABEL_95;
      }
      DestroySecurityAttributes(v24);
LABEL_81:
      v29 = (struct _SECURITY_ATTRIBUTES *)CreateSecurityAttributesWithThreadAsOwner(2031619, 0, 0);
      if ( !v29 )
      {
        v19 = GetLastError();
        v9 = v19;
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_95;
        }
        v21 = 103;
        goto LABEL_39;
      }
      for ( i = 0; i < 2; ++i )
      {
        if ( !hObject[i] )
        {
          EventW = CreateEventW(v29, 0, 0, (LPCWSTR)lpName[i]);
          hObject[i] = EventW;
          if ( !EventW )
          {
            v9 = GetLastError();
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v9);
            }
            DestroySecurityAttributes(v29);
            goto LABEL_94;
          }
        }
      }
      DestroySecurityAttributes(v29);
      if ( !SetEnvironmentVariableW(L"MS_FAX_PRINTFILE", a3) )
      {
        v40 = GetLastError();
        v9 = v40;
        v41 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v42 = 105;
          goto LABEL_121;
        }
        goto LABEL_94;
      }
      v43 = (struct _SECURITY_ATTRIBUTES *)CreateSecurityAttributesWithThreadAsOwner(6, 0, 0);
      if ( !v43 )
      {
        v40 = GetLastError();
        v9 = v40;
        v41 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v42 = 106;
LABEL_121:
          WPP_SF_d(v41[2], v42, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v40);
        }
LABEL_94:
        v18 = MutexW;
        goto LABEL_95;
      }
      v44 = -1;
      FileMappingW = CreateFileMappingW(
                       (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                       v43,
                       0x8000004u,
                       0,
                       0x1000u,
                       L"MS_FAXXP_ATTACHMENT_REGION");
      v45 = FileMappingW;
      if ( !FileMappingW )
      {
        v46 = GetLastError();
        v9 = v46;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v46);
        }
        DestroySecurityAttributes(v43);
        v28 = 0;
        v18 = MutexW;
        v6 = 0;
        goto LABEL_96;
      }
      DestroySecurityAttributes(v43);
      Str = (wchar_t *)MapViewOfFile(v45, 2u, 0, 0, 0);
      if ( !Str )
      {
        v47 = GetLastError();
        v9 = v47;
        v48 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_139;
        }
        v49 = 108;
LABEL_138:
        WPP_SF_d(v48[2], v49, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v47);
LABEL_139:
        v28 = 0;
LABEL_140:
        v18 = MutexW;
        v6 = Str;
        goto LABEL_96;
      }
      v50 = 2147483646;
      v51 = 2048;
      v52 = 2147483646;
      v53 = 2048;
      v54 = a3;
      v55 = Str;
      do
      {
        if ( !v52 )
          break;
        if ( !*v54 )
          break;
        *v55++ = *v54++;
        --v52;
        --v53;
      }
      while ( v53 );
      v56 = v55 - 1;
      v57 = v53 == 0 ? 0x8007007A : 0;
      if ( v53 )
        v56 = v55;
      *v56 = 0;
      if ( !v53 )
      {
        v58 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v59 = 109;
LABEL_152:
          WPP_SF_d(v58[2], v59, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v57);
          goto LABEL_153;
        }
        goto LABEL_153;
      }
      v60 = wcschr(Str, 0) + 1;
      if ( a3 )
      {
        v61 = -1;
        do
          ++v61;
        while ( a3[v61] );
        v51 = (unsigned __int64)(2 * (2047 - v61)) >> 1;
        if ( v51 - 1 > 0x7FFFFFFE )
        {
          v57 = -2147024809;
          if ( v51 )
            *v60 = 0;
          goto LABEL_169;
        }
      }
      v62 = Filename;
      do
      {
        if ( !v50 )
          break;
        if ( !*v62 )
          break;
        *v60++ = *v62++;
        --v50;
        --v51;
      }
      while ( v51 );
      v63 = v60 - 1;
      v57 = v51 == 0 ? 0x8007007A : 0;
      if ( v51 )
        v63 = v60;
      *v63 = 0;
      if ( !v51 )
      {
LABEL_169:
        v58 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v59 = 110;
          goto LABEL_152;
        }
LABEL_153:
        v9 = (unsigned __int16)v57;
        if ( (v57 & 0x1FFF0000) != 0x70000 )
          v9 = v57;
        goto LABEL_139;
      }
      v64 = v94;
      v65 = StringCchPrintfW(v101, 0x208u, L"\"%s\"", v94);
      v66 = v65;
      if ( v65 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            111,
            WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids,
            (unsigned int)v65);
        }
        v18 = MutexW;
        v28 = 0;
        v6 = Str;
        if ( (v66 & 0x1FFF0000) == 0x70000 )
          v9 = (unsigned __int16)v66;
        else
          v9 = v66;
        goto LABEL_96;
      }
      pExecInfo.cbSize = 112;
      pExecInfo.fMask = 1280;
      pExecInfo.lpVerb = L"printto";
      pExecInfo.hwnd = 0;
      pExecInfo.lpFile = NewFileName;
      pExecInfo.nShow = 7;
      pExecInfo.lpParameters = v101;
      pExecInfo.lpDirectory = (LPCWSTR)v100;
      memset(&pExecInfo.hInstApp, 0, 36);
      *(_OWORD *)&pExecInfo.hIcon = 0;
      if ( !_wcsicmp(p_String1, L"bmp") )
      {
        pExecInfo.fMask |= 1u;
        pExecInfo.lpClass = L"Paint.Picture";
      }
      v67 = (struct _SECURITY_ATTRIBUTES *)CreateSecurityAttributesWithThreadAsOwner(2031617, 0, 0);
      v68 = v67;
      if ( !v67 )
      {
        v47 = GetLastError();
        v9 = v47;
        v48 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_139;
        }
        v49 = 112;
        goto LABEL_138;
      }
      v28 = CreateMutexW(v67, 0, L"MS_FAXXP_ATTACHMENTREGION_MUTEX");
      if ( !v28 )
      {
        v69 = GetLastError();
        v9 = v69;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v69);
        }
        DestroySecurityAttributes(v68);
        goto LABEL_140;
      }
      DestroySecurityAttributes(v68);
      if ( !ShellExecuteExW(&pExecInfo) )
      {
        v9 = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v9);
        }
        if ( v9 == 1155 )
        {
          v70 = wcsrchr(NewFileName, 0x2Eu);
          v71 = v70;
          if ( !v70 )
            goto LABEL_209;
          v72 = -1;
          do
            ++v72;
          while ( v70[v72] );
          if ( v72 < 4 )
            goto LABEL_209;
          if ( _wcsnicmp(v70, L".tif", v72) )
          {
            do
              ++v44;
            while ( v71[v44] );
            if ( _wcsnicmp(v71, L".tiff", v44) )
              goto LABEL_209;
          }
          v9 = InvokeTiffImageDocumentHandlerForPrinting(v64, NewFileName);
        }
        if ( v9 )
        {
LABEL_209:
          FaxLog(3, 1, 1, 3221257587LL, &String1);
          v18 = MutexW;
          v6 = Str;
LABEL_96:
          if ( !SetEnvironmentVariableW(L"MS_FAX_PRINTFILE", 0)
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            v32 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            v33 = GetLastError();
            WPP_SF_d(v32, 119, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v33);
          }
          for ( j = 0; j != 2; ++j )
          {
            v35 = hObject[j];
            if ( v35
              && !CloseHandle(v35)
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              v36 = *((_QWORD *)WPP_GLOBAL_Control + 2);
              v37 = GetLastError();
              WPP_SF_d(v36, 120, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v37);
            }
          }
          if ( v28
            && !CloseHandle(v28)
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            v38 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            v39 = GetLastError();
            WPP_SF_d(v38, 121, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v39);
          }
          if ( v6
            && !UnmapViewOfFile(v6)
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            v77 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            v78 = GetLastError();
            WPP_SF_d(v77, 122, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v78);
          }
          if ( FileMappingW
            && !CloseHandle(FileMappingW)
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            v79 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            v80 = GetLastError();
            WPP_SF_d(v79, 123, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v80);
          }
          if ( v18 )
          {
            if ( !ReleaseMutex(v18)
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              v81 = *((_QWORD *)WPP_GLOBAL_Control + 2);
              v82 = GetLastError();
              WPP_SF_d(v81, 124, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v82);
            }
            if ( !CloseHandle(v18)
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              v83 = *((_QWORD *)WPP_GLOBAL_Control + 2);
              v84 = GetLastError();
              WPP_SF_d(v83, 125, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v84);
            }
          }
          if ( !v88 )
            SetLastError(v9);
          for ( k = 0; k < 5; ++k )
          {
            if ( DeleteFileW(NewFileName) )
              break;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
            {
              v86 = *((_QWORD *)WPP_GLOBAL_Control + 2);
              v87 = GetLastError();
              WPP_SF_d(v86, 126, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v87);
            }
            Sleep(0x7D0u);
          }
          v17 = v88;
          goto LABEL_266;
        }
      }
      v73 = WaitForMultipleObjects(2u, hObject, 0, 0x493E0u);
      switch ( v73 )
      {
        case 0xFFFFFFFF:
          v74 = GetLastError();
          v9 = v74;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v74);
          }
          break;
        case 0x102u:
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 116, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids);
          }
          v9 = 258;
          break;
        case 1u:
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids);
          }
          v9 = 1235;
          break;
        default:
          if ( !CloseHandle(v28)
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
          {
            v75 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            v76 = GetLastError();
            WPP_SF_d(v75, 118, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v76);
          }
          v28 = 0;
          v88 = 1;
          break;
      }
      goto LABEL_140;
    }
    v26 = WaitForSingleObject(v22, 0x493E0u);
    if ( v26 == -1 )
    {
      v27 = GetLastError();
      v9 = v27;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v27);
      }
    }
    else
    {
      if ( v26 != 258 )
      {
        if ( v26 == 128
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 102, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids);
        }
        goto LABEL_81;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids);
      }
      v9 = 258;
    }
    CloseHandle(v18);
    v18 = 0;
    v28 = 0;
    goto LABEL_96;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v16 = GetLastError();
    WPP_SF_d(v15, 94, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids, v16);
  }
  v17 = 0;
LABEL_266:
  pMemFree(lpName[0]);
  pMemFree(lpName[1]);
  return v17;
}

```

## disassembly

```asm
0x180036f80  mov     [rsp-8+arg_18], rbx
0x180036f85  push    rbp
0x180036f86  push    rsi
0x180036f87  push    rdi
0x180036f88  push    r12
0x180036f8a  push    r13
0x180036f8c  push    r14
0x180036f8e  push    r15
0x180036f90  lea     rbp, [rsp-0C60h]
0x180036f98  sub     rsp, 0D60h
0x180036f9f  mov     rax, cs:__security_cookie
0x180036fa6  xor     rax, rsp
0x180036fa9  mov     [rbp+0C90h+var_40], rax
0x180036fb0  mov     rbx, rdx
0x180036fb3  mov     [rbp+0C90h+var_CF0], rcx
0x180036fb7  xor     edx, edx; Val
0x180036fb9  lea     rcx, [rbp+0C90h+pExecInfo]; void *
0x180036fbd  mov     r12, r8
0x180036fc0  lea     r8d, [rdx+70h]; Size
0x180036fc4  call    memset_0
0x180036fc9  xorps   xmm0, xmm0
0x180036fcc  lea     rcx, [rbp+0C90h+String1]; void *
0x180036fd3  xorps   xmm1, xmm1
0x180036fd6  mov     edi, 200h
0x180036fdb  mov     r8d, edi; Size
0x180036fde  xor     edx, edx; Val
0x180036fe0  movups  xmmword ptr [rbp+0C90h+hObject], xmm0
0x180036fe4  movups  xmmword ptr [rsp+0D90h+lpName], xmm1
0x180036fe9  call    memset_0
0x180036fee  mov     r8d, edi; Size
0x180036ff1  lea     rcx, [rbp+0C90h+var_860]; void *
0x180036ff8  xor     edx, edx; Val
0x180036ffa  call    memset_0
0x180036fff  mov     rcx, cs:WPP_GLOBAL_Control
0x180037006  lea     rsi, WPP_GLOBAL_Control
0x18003700d  lea     r14, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids
0x180037014  cmp     rcx, rsi
0x180037017  jz      short loc_180037036
0x180037019  test    byte ptr [rcx+1Ch], 2
0x18003701d  jz      short loc_180037036
0x18003701f  cmp     byte ptr [rcx+19h], 5
0x180037023  jb      short loc_180037036
0x180037025  mov     rcx, [rcx+10h]
0x180037029  mov     edx, 5Ah ; 'Z'
0x18003702e  mov     r8, r14
0x180037031  call    WPP_SF_
0x180037036  mov     r13d, 5Ch ; '\'
0x18003703c  mov     rcx, r12; Str
0x18003703f  mov     edx, r13d; Ch
0x180037042  call    cs:__imp_wcsrchr
0x180037049  nop     dword ptr [rax+rax+00h]
0x18003704e  xor     r15d, r15d
0x180037051  lea     r8, [rsp+0D90h+lpName+8]
0x180037056  test    rax, rax
0x180037059  lea     rdx, [rsp+0D90h+lpName]
0x18003705e  lea     rcx, [rax+2]
0x180037062  cmovz   rcx, rax
0x180037066  call    PrepareDriverEventNames
0x18003706b  mov     edi, eax
0x18003706d  test    eax, eax
0x18003706f  jz      short loc_1800370B1
0x180037071  mov     rcx, cs:WPP_GLOBAL_Control
0x180037078  cmp     rcx, rsi
0x18003707b  jz      short loc_18003709C
0x18003707d  test    byte ptr [rcx+1Ch], 2
0x180037081  jz      short loc_18003709C
0x180037083  cmp     byte ptr [rcx+19h], 2
0x180037087  jb      short loc_18003709C
0x180037089  mov     rcx, [rcx+10h]
0x18003708d  lea     edx, [r13-1]
0x180037091  mov     r9d, eax
0x180037094  mov     r8, r14
0x180037097  call    WPP_SF_d
0x18003709c  mov     ecx, edi; dwErrCode
0x18003709e  call    cs:__imp_SetLastError
0x1800370a5  nop     dword ptr [rax+rax+00h]
0x1800370aa  xor     eax, eax
0x1800370ac  jmp     loc_18003815E
0x1800370b1  lea     rdx, [rbp+0C90h+var_660]
0x1800370b8  mov     ecx, 104h
0x1800370bd  call    cs:__imp_GetTempPath2W
0x1800370c4  nop     dword ptr [rax+rax+00h]
0x1800370c9  test    eax, eax
0x1800370cb  jnz     short loc_18003711C
0x1800370cd  mov     rbx, cs:WPP_GLOBAL_Control
0x1800370d4  cmp     rbx, rsi
0x1800370d7  jz      short loc_180037106
0x1800370d9  test    byte ptr [rbx+1Ch], 2
0x1800370dd  jz      short loc_180037106
0x1800370df  cmp     byte ptr [rbx+19h], 2
0x1800370e3  jb      short loc_180037106
0x1800370e5  mov     rbx, [rbx+10h]
0x1800370e9  call    cs:__imp_GetLastError
0x1800370f0  nop     dword ptr [rax+rax+00h]
0x1800370f5  mov     edx, r13d
0x1800370f8  mov     r8, r14
0x1800370fb  mov     r9d, eax
0x1800370fe  mov     rcx, rbx
0x180037101  call    WPP_SF_d
0x180037106  mov     rcx, [rsp+0D90h+lpName]; lpMem
0x18003710b  call    pMemFree
0x180037110  mov     rcx, [rsp+0D90h+lpName+8]; lpMem
0x180037115  call    pMemFree
0x18003711a  jmp     short loc_1800370AA
0x18003711c  mov     [rsp+0D90h+ExtCount], 100h; ExtCount
0x180037125  lea     rax, [rbp+0C90h+String1]
0x18003712c  mov     [rsp+0D90h+Ext], rax; Ext
0x180037131  xor     r9d, r9d; Dir
0x180037134  mov     [rsp+0D90h+FilenameCount], r15; FilenameCount
0x180037139  xor     r8d, r8d; DriveCount
0x18003713c  mov     [rsp+0D90h+Filename], r15; Filename
0x180037141  xor     edx, edx; Drive
0x180037143  mov     rcx, rbx; FullPath
0x180037146  mov     [rsp+0D90h+DirCount], r15; DirCount
0x18003714b  call    cs:__imp__wsplitpath_s
0x180037152  nop     dword ptr [rax+rax+00h]
0x180037157  test    eax, eax
0x180037159  jz      short loc_18003719A
0x18003715b  mov     rcx, cs:WPP_GLOBAL_Control
0x180037162  cmp     rcx, rsi
0x180037165  jz      short loc_180037184
0x180037167  test    byte ptr [rcx+1Ch], 2
0x18003716b  jz      short loc_180037184
0x18003716d  cmp     byte ptr [rcx+19h], 2
0x180037171  jb      short loc_180037184
0x180037173  mov     rcx, [rcx+10h]
0x180037177  mov     edx, 5Dh ; ']'
0x18003717c  mov     r8, r14
0x18003717f  call    WPP_SF_
0x180037184  mov     ecx, 65Bh; dwErrCode
0x180037189  call    cs:__imp_SetLastError
0x180037190  nop     dword ptr [rax+rax+00h]
0x180037195  jmp     loc_180037106
0x18003719a  mov     r8d, 1; MaxCount
0x1800371a0  lea     rdx, asc_180043CF4; "."
0x1800371a7  lea     rcx, [rbp+0C90h+String1]; String1
0x1800371ae  call    wcsncmp_0
0x1800371b3  test    eax, eax
0x1800371b5  lea     rcx, [rbp+0C90h+var_A5E]
0x1800371bc  lea     rax, [rbp+0C90h+NewFileName]
0x1800371c0  lea     r13, [rbp+0C90h+String1]
0x1800371c7  mov     [rsp+0D90h+DirCount], rax
0x1800371cc  cmovz   r13, rcx
0x1800371d0  lea     rdx, [rbp+0C90h+var_660]
0x1800371d7  mov     r9, r13
0x1800371da  call    GenerateUniqueFileNameWithPrefix
0x1800371df  test    rax, rax
0x1800371e2  jnz     short loc_180037227
0x1800371e4  mov     rbx, cs:WPP_GLOBAL_Control
0x1800371eb  cmp     rbx, rsi
0x1800371ee  jz      short loc_18003721F
0x1800371f0  test    byte ptr [rbx+1Ch], 2
0x1800371f4  jz      short loc_18003721F
0x1800371f6  cmp     byte ptr [rbx+19h], 2
0x1800371fa  jb      short loc_18003721F
0x1800371fc  mov     rbx, [rbx+10h]
0x180037200  call    cs:__imp_GetLastError
0x180037207  nop     dword ptr [rax+rax+00h]
0x18003720c  mov     edx, 5Eh ; '^'
0x180037211  mov     r8, r14
0x180037214  mov     r9d, eax
0x180037217  mov     rcx, rbx
0x18003721a  call    WPP_SF_d
0x18003721f  mov     r13d, r15d
0x180037222  jmp     loc_180038147
0x180037227  xor     eax, eax
0x180037229  mov     [rbp+0C90h+var_D08], r15
0x18003722d  xor     r8d, r8d; bFailIfExists
0x180037230  mov     [rsp+0D90h+var_D40], eax
0x180037234  lea     rdx, [rbp+0C90h+NewFileName]; lpNewFileName
0x180037238  mov     [rsp+0D90h+var_D38], r15
0x18003723d  mov     rcx, rbx; lpExistingFileName
0x180037240  mov     r14, r15
0x180037243  call    cs:__imp_CopyFileW
0x18003724a  nop     dword ptr [rax+rax+00h]
0x18003724f  xor     ecx, ecx
0x180037251  test    eax, eax
0x180037253  jnz     short loc_1800372A4
0x180037255  call    cs:__imp_GetLastError
0x18003725c  nop     dword ptr [rax+rax+00h]
0x180037261  mov     edi, eax
0x180037263  mov     rcx, cs:WPP_GLOBAL_Control
0x18003726a  cmp     rcx, rsi
0x18003726d  jz      loc_180037622
0x180037273  test    byte ptr [rcx+1Ch], 2
0x180037277  jz      loc_180037622
0x18003727d  cmp     byte ptr [rcx+19h], 2
0x180037281  jb      loc_180037622
0x180037287  mov     edx, 5Fh ; '_'
0x18003728c  mov     rcx, [rcx+10h]
0x180037290  lea     r8, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids
0x180037297  mov     r9d, eax
0x18003729a  call    WPP_SF_d
0x18003729f  jmp     loc_180037622
0x1800372a4  mov     [rsp+0D90h+ExtCount], rcx; ExtCount
0x1800372a9  lea     rax, [rbp+0C90h+var_860]
0x1800372b0  mov     [rsp+0D90h+Ext], rcx; Ext
0x1800372b5  xor     r9d, r9d; Dir
0x1800372b8  mov     [rsp+0D90h+FilenameCount], 100h; FilenameCount
0x1800372c1  xor     r8d, r8d; DriveCount
0x1800372c4  mov     [rsp+0D90h+Filename], rax; Filename
0x1800372c9  xor     edx, edx; Drive
0x1800372cb  mov     [rsp+0D90h+DirCount], rcx; DirCount
0x1800372d0  lea     rcx, [rbp+0C90h+NewFileName]; FullPath
0x1800372d4  call    cs:__imp__wsplitpath_s
0x1800372db  nop     dword ptr [rax+rax+00h]
0x1800372e0  test    eax, eax
0x1800372e2  jz      short loc_18003731B
0x1800372e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800372eb  cmp     rcx, rsi
0x1800372ee  jz      short loc_180037311
0x1800372f0  test    byte ptr [rcx+1Ch], 2
0x1800372f4  jz      short loc_180037311
0x1800372f6  cmp     byte ptr [rcx+19h], 2
0x1800372fa  jb      short loc_180037311
0x1800372fc  mov     rcx, [rcx+10h]
0x180037300  lea     r8, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids
0x180037307  mov     edx, 60h ; '`'
0x18003730c  call    WPP_SF_
0x180037311  mov     edi, 65Bh
0x180037316  jmp     loc_180037622
0x18003731b  mov     ebx, 1F0001h
0x180037320  lea     r8, aMsFaxxpAttachm_1; "MS_FAXXP_ATTACHMENT_MUTEX"
0x180037327  mov     ecx, ebx; dwDesiredAccess
0x180037329  xor     edx, edx; bInheritHandle
0x18003732b  call    cs:__imp_OpenMutexW
0x180037332  nop     dword ptr [rax+rax+00h]
0x180037337  mov     [rsp+0D90h+var_D30], rax
0x18003733c  mov     r14, rax
0x18003733f  test    rax, rax
0x180037342  jnz     loc_180037457
0x180037348  call    cs:__imp_GetLastError
0x18003734f  nop     dword ptr [rax+rax+00h]
0x180037354  mov     edi, eax
0x180037356  cmp     eax, 2
0x180037359  jz      short loc_180037388
0x18003735b  mov     rcx, cs:WPP_GLOBAL_Control
0x180037362  cmp     rcx, rsi
0x180037365  jz      loc_180037622
0x18003736b  test    byte ptr [rcx+1Ch], 2
0x18003736f  jz      loc_180037622
0x180037375  cmp     byte ptr [rcx+19h], 2
0x180037379  jb      loc_180037622
0x18003737f  lea     edx, [r14+61h]
0x180037383  jmp     loc_18003728C
0x180037388  xor     r8d, r8d
0x18003738b  mov     edx, ebx
0x18003738d  mov     ecx, ebx
0x18003738f  call    CreateSecurityAttributesWithThreadAsOwner
0x180037394  xor     edi, edi
0x180037396  mov     rbx, rax
0x180037399  test    rax, rax
0x18003739c  jnz     short loc_1800373D8
0x18003739e  call    cs:__imp_GetLastError
0x1800373a5  nop     dword ptr [rax+rax+00h]
0x1800373aa  mov     edi, eax
0x1800373ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800373b3  cmp     rcx, rsi
0x1800373b6  jz      loc_180037622
0x1800373bc  test    byte ptr [rcx+1Ch], 2
0x1800373c0  jz      loc_180037622
0x1800373c6  cmp     byte ptr [rcx+19h], 2
0x1800373ca  jb      loc_180037622
0x1800373d0  lea     edx, [rbx+62h]
0x1800373d3  jmp     loc_18003728C
0x1800373d8  lea     r8, aMsFaxxpAttachm_1; "MS_FAXXP_ATTACHMENT_MUTEX"
0x1800373df  mov     edx, 1; bInitialOwner
0x1800373e4  mov     rcx, rbx; lpMutexAttributes
0x1800373e7  call    cs:__imp_CreateMutexW
0x1800373ee  nop     dword ptr [rax+rax+00h]
0x1800373f3  mov     [rsp+0D90h+var_D30], rax
0x1800373f8  mov     r14, rax
0x1800373fb  test    rax, rax
0x1800373fe  jnz     short loc_18003744A
0x180037400  call    cs:__imp_GetLastError
0x180037407  nop     dword ptr [rax+rax+00h]
0x18003740c  mov     edi, eax
0x18003740e  mov     rcx, cs:WPP_GLOBAL_Control
0x180037415  cmp     rcx, rsi
0x180037418  jz      short loc_18003743D
0x18003741a  test    byte ptr [rcx+1Ch], 2
0x18003741e  jz      short loc_18003743D
0x180037420  cmp     byte ptr [rcx+19h], 2
0x180037424  jb      short loc_18003743D
0x180037426  mov     rcx, [rcx+10h]
0x18003742a  lea     edx, [r14+63h]
0x18003742e  mov     r9d, eax
0x180037431  lea     r8, WPP_d810acecea0d31e4a47bc3dce0391ae0_Traceguids
0x180037438  call    WPP_SF_d
0x18003743d  mov     rcx, rbx; lpMem
0x180037440  call    DestroySecurityAttributes
0x180037445  jmp     loc_180037622
0x18003744a  mov     rcx, rbx; lpMem
0x18003744d  call    DestroySecurityAttributes
0x180037452  jmp     loc_180037534
0x180037457  mov     edx, 493E0h; dwMilliseconds
0x18003745c  mov     rcx, r14; hHandle
0x18003745f  call    cs:__imp_WaitForSingleObject
0x180037466  nop     dword ptr [rax+rax+00h]
0x18003746b  cmp     eax, 0FFFFFFFFh
  ... truncated ...
```
