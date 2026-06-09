# FAX_SendDocumentEx

- ea: `0x14001dbc0`
- end: `0x14001ee39`
- name: `FAX_SendDocumentEx`
- size: `4729`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *, __int64, const struct _FAX_PERSONAL_PROFILEW *, unsigned int, struct _FAX_PERSONAL_PROFILEW *, struct _FAX_JOB_PARAM_EXW *, __int64, _QWORD *, __int64)`
- caller_count: `0`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callees

- `0x140002c73`
- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004e48`
- `0x140004f64`
- `0x140004fe4`
- `0x1400109a0`
- `0x1400164d4`
- `0x14001dbc0`
- `0x140023a0c`
- `0x14002e3d4`
- `0x14003735c`
- `0x140038090`
- `0x14003cd94`
- `0x1400408a8`
- `0x140047d20`
- `0x140048010`
- `0x140048284`
- `0x140058d78`
- `0x14005900c`
- `0x14006998c`
- `0x14006e124`
- `0x14007551c`
- `0x14007ab38`
- `0x140086ec0`

## import_xrefs

- `ADVAPI32!ConvertSidToStringSidW` at `0x14001de05`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14001de05`
- `KERNEL32!GetLastError` at `0x14001ddb4`
- `KERNEL32!GetLastError` at `0x14001de18`
- `KERNEL32!GetLastError` at `0x14001e29b`
- `KERNEL32!GetLastError` at `0x14001e414`
- `KERNEL32!GetLastError` at `0x14001e487`
- `KERNEL32!GetLastError` at `0x14001e512`
- `KERNEL32!GetLastError` at `0x14001e586`
- `KERNEL32!GetLastError` at `0x14001e771`
- `KERNEL32!GetLastError` at `0x14001e910`
- `KERNEL32!GetLastError` at `0x14001ea62`
- `KERNEL32!GetLastError` at `0x14001ead0`
- `KERNEL32!GetLastError` at `0x14001ec4c`
- `KERNEL32!GetLastError` at `0x14001edbf`
- `KERNEL32!GetLastError` at `0x14001ddb4`
- `KERNEL32!GetLastError` at `0x14001de18`
- `KERNEL32!GetLastError` at `0x14001e29b`
- `KERNEL32!GetLastError` at `0x14001e414`
- `KERNEL32!GetLastError` at `0x14001e487`
- `KERNEL32!GetLastError` at `0x14001e512`
- `KERNEL32!GetLastError` at `0x14001e586`
- `KERNEL32!GetLastError` at `0x14001e771`
- `KERNEL32!GetLastError` at `0x14001e910`
- `KERNEL32!GetLastError` at `0x14001ea62`
- `KERNEL32!GetLastError` at `0x14001ead0`
- `KERNEL32!GetLastError` at `0x14001ec4c`
- `KERNEL32!GetLastError` at `0x14001edbf`
- `KERNEL32!CloseHandle` at `0x14001e4cf`
- `KERNEL32!CloseHandle` at `0x14001e4e3`
- `KERNEL32!CloseHandle` at `0x14001e4cf`
- `KERNEL32!CloseHandle` at `0x14001e4e3`
- `KERNEL32!LocalFree` at `0x14001ee24`
- `KERNEL32!LocalFree` at `0x14001ee24`
- `KERNEL32!DeleteFileW` at `0x14001ec24`
- `KERNEL32!DeleteFileW` at `0x14001ed97`
- `KERNEL32!DeleteFileW` at `0x14001ec24`
- `KERNEL32!DeleteFileW` at `0x14001ed97`
- `KERNEL32!EnterCriticalSection` at `0x14001e21a`
- `KERNEL32!EnterCriticalSection` at `0x14001e712`
- `KERNEL32!EnterCriticalSection` at `0x14001e21a`
- `KERNEL32!EnterCriticalSection` at `0x14001e712`
- `KERNEL32!LeaveCriticalSection` at `0x14001e237`
- `KERNEL32!LeaveCriticalSection` at `0x14001e7bd`
- `KERNEL32!LeaveCriticalSection` at `0x14001e95a`
- `KERNEL32!LeaveCriticalSection` at `0x14001eaa3`
- `KERNEL32!LeaveCriticalSection` at `0x14001e237`
- `KERNEL32!LeaveCriticalSection` at `0x14001e7bd`
- `KERNEL32!LeaveCriticalSection` at `0x14001e95a`
- `KERNEL32!LeaveCriticalSection` at `0x14001eaa3`
- `KERNEL32!GetFileSize` at `0x14001e474`
- `KERNEL32!GetFileSize` at `0x14001e474`
- `FXSTIFF!TiffClose` at `0x14001e5d0`
- `FXSTIFF!TiffClose` at `0x14001e5d0`
- `FXSTIFF!TiffOpen` at `0x14001e575`
- `FXSTIFF!TiffOpen` at `0x14001e575`
- `ntdll!WinSqmIncrementDWORD` at `0x14001e2ed`
- `ntdll!WinSqmIncrementDWORD` at `0x14001e2ed`

## pseudocode

```c
__int64 __fastcall FAX_SendDocumentEx(
        void *a1,
        unsigned __int16 *a2,
        __int64 a3,
        const struct _FAX_PERSONAL_PROFILEW *a4,
        unsigned int a5,
        struct _FAX_PERSONAL_PROFILEW *a6,
        struct _FAX_JOB_PARAM_EXW *a7,
        __int64 a8,
        _QWORD *a9,
        __int64 a10)
{
  CMapDeviceId *v13; // rcx
  __int64 v14; // rdx
  const unsigned __int16 *v15; // rcx
  void *ClientUserSID; // rax
  unsigned int LastError; // ebx
  void *v19; // rcx
  unsigned int v20; // r8d
  CMapDeviceId *v21; // rcx
  __int64 v22; // r9
  __int64 v23; // rdx
  DWORD v24; // ecx
  __int64 v25; // rdx
  __int64 v26; // r9
  int v27; // eax
  unsigned int v28; // eax
  int v29; // ebx
  int v30; // eax
  __int64 v31; // rdi
  struct _JOB_QUEUE *v32; // r15
  void *File; // rax
  void *v34; // rdi
  DWORD v35; // eax
  int v36; // edx
  DWORD FileSize; // ebx
  DWORD v38; // eax
  DWORD v39; // eax
  __int64 v40; // rax
  const struct _FAX_COVERPAGE_INFO_EXW *v41; // rbx
  int v42; // eax
  __int128 v43; // xmm1
  DWORD v44; // eax
  __int64 v45; // rbx
  struct _JOB_QUEUE *v46; // rax
  _QWORD *v47; // rdi
  unsigned int v48; // esi
  _DWORD *v49; // r15
  __int64 v50; // rbx
  int QueueEvent; // eax
  struct _JOB_QUEUE *v52; // r15
  _QWORD *i; // rcx
  __int64 v54; // rax
  __int64 v55; // rbx
  int v56; // eax
  DWORD v57; // eax
  __int64 v58; // r9
  __int64 v59; // rax
  int v60; // eax
  char v61; // al
  unsigned __int16 *v62; // rdi
  int v63; // eax
  char v64; // al
  int v65; // [rsp+20h] [rbp-E0h]
  struct _JOB_QUEUE *v66; // [rsp+50h] [rbp-B0h]
  LPWSTR StringSid; // [rsp+60h] [rbp-A0h] BYREF
  int v69; // [rsp+68h] [rbp-98h] BYREF
  int v70; // [rsp+6Ch] [rbp-94h] BYREF
  struct _FAX_JOB_PARAM_EXW *v71; // [rsp+70h] [rbp-90h]
  unsigned __int16 *v72; // [rsp+78h] [rbp-88h]
  unsigned __int16 *v73; // [rsp+80h] [rbp-80h]
  unsigned __int16 *ClientUserName; // [rsp+88h] [rbp-78h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  unsigned __int16 *RecipientList; // [rsp+98h] [rbp-68h]
  __int64 v77; // [rsp+A0h] [rbp-60h]
  __int64 v78; // [rsp+A8h] [rbp-58h]
  __int128 v79; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v80; // [rsp+C0h] [rbp-40h]
  __int64 v81; // [rsp+D0h] [rbp-30h]
  _OWORD v82[2]; // [rsp+D8h] [rbp-28h] BYREF
  WCHAR v83[264]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR FileName[264]; // [rsp+310h] [rbp+210h] BYREF

  v71 = a7;
  v77 = a8;
  v73 = a2;
  StringSid = 0;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 210, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
  }
  memset_0(v83, 0, 0x208u);
  v81 = 0;
  v79 = 0;
  v80 = 0;
  memset_0(FileName, 0, 0x208u);
  v69 = 0;
  if ( !a5 || !a4 || !a6 || !v71 || !a9 || !a10 || !a3 )
    return 87;
  if ( v73 && !(unsigned int)ValidateCopiedQueueFileName(v73, 0) )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 87;
    }
    v14 = 211;
LABEL_25:
    WPP_SF_(*((_QWORD *)v13 + 2), v14, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
    return 87;
  }
  v15 = *(const unsigned __int16 **)(a3 + 8);
  if ( v15 && !*(_DWORD *)(a3 + 16) && !(unsigned int)ValidateCopiedQueueFileName(v15, 1) )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 87;
    }
    v14 = 212;
    goto LABEL_25;
  }
  ClientUserSID = GetClientUserSID();
  lpMem = ClientUserSID;
  if ( !ClientUserSID )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 213, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, LastError);
    }
    return LastError;
  }
  if ( !ConvertSidToStringSidW(ClientUserSID, &StringSid) )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 214, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, LastError);
    }
    v19 = lpMem;
    goto LABEL_39;
  }
  ClientUserName = 0;
  v72 = 0;
  v78 = *((_QWORD *)v71 + 4);
  RecipientList = 0;
  v20 = *((_DWORD *)g_pFaxConfig + 22);
  if ( v20 && a5 > v20 )
  {
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 215, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
    }
    LastError = FindClientAPIVersion(a1) < 0x20000 ? 5 : 7013;
    goto LABEL_47;
  }
  v22 = 0;
  do
  {
    if ( !*((_QWORD *)a6 + 17 * (unsigned int)v22 + 2) )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_65;
      }
      v23 = 216;
LABEL_64:
      WPP_SF_d(*((_QWORD *)v21 + 2), v23, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v22);
      v21 = WPP_GLOBAL_Control;
      goto LABEL_65;
    }
    v22 = (unsigned int)(v22 + 1);
  }
  while ( (unsigned int)v22 < a5 );
  if ( *((_DWORD *)v71 + 11) || *((_QWORD *)v71 + 6) == 4294906420LL )
  {
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 217, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
      v21 = WPP_GLOBAL_Control;
    }
    LastError = 50;
    goto LABEL_231;
  }
  v22 = *((unsigned int *)v71 + 10);
  if ( (_DWORD)v22 )
  {
    if ( (_DWORD)v22 == 1 )
    {
      v24 = 2;
    }
    else
    {
      if ( (_DWORD)v22 != 2 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v23 = 218;
          goto LABEL_64;
        }
LABEL_65:
        LastError = 87;
        goto LABEL_231;
      }
      v24 = 4;
    }
  }
  else
  {
    v24 = 1;
  }
  LastError = FaxSvcAccessCheck(v24, &v69, 0, 1);
  if ( !LastError )
  {
    if ( !v69 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 220, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
        v21 = WPP_GLOBAL_Control;
      }
      LastError = 5;
      goto LABEL_231;
    }
    v22 = *((unsigned int *)v71 + 6);
    if ( (v22 & 0xFFFFFFE2) != 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_65;
      }
      v23 = 221;
      goto LABEL_64;
    }
    v27 = v22 & 0xFFFFFFE7;
    if ( (v22 & 0xFFFFFFE7) == 1 || v27 == 4 )
    {
      if ( (v27 & dword_1400A7644) == 0 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 223, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v22);
          v21 = WPP_GLOBAL_Control;
        }
        LastError = 1630;
        goto LABEL_231;
      }
    }
    else if ( v27 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_65;
      }
      v23 = 222;
      goto LABEL_64;
    }
    if ( !(unsigned int)IsFaxShared() )
    {
      v70 = 0;
      v28 = IsLocalRPCConnectionNP(&v70);
      LastError = v28;
      if ( v28 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_231;
        }
        v25 = 224;
LABEL_105:
        v26 = v28;
LABEL_74:
        WPP_SF_d(*((_QWORD *)v21 + 2), v25, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v26);
        goto LABEL_47;
      }
      if ( !v70 )
      {
        if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 225, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
        }
        LastError = FindClientAPIVersion(a1) < 0x10000 ? 87 : 7011;
        goto LABEL_47;
      }
    }
    EnterCriticalSection(&g_CsConfig);
    v29 = *((_DWORD *)g_pFaxConfig + 2);
    LeaveCriticalSection(&g_CsConfig);
    if ( (v29 & 2) != 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 226, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids);
        v21 = WPP_GLOBAL_Control;
      }
      LastError = 19;
      goto LABEL_231;
    }
    ClientUserName = GetClientUserName();
    if ( !ClientUserName )
    {
      v28 = GetLastError();
      LastError = v28;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_231;
      }
      v25 = 227;
      goto LABEL_105;
    }
    WinSqmIncrementDWORD(0, 9627, 1);
    if ( !v73 )
    {
      v72 = 0;
      goto LABEL_164;
    }
    v30 = StringCchPrintfW(v83, 0x104u, L"%s\\%s%s%s", *((_QWORD *)g_pFaxConfig + 12), StringSid, L"$", v73);
    LastError = v30;
    if ( v30 < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          228,
          &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
          (unsigned int)v30);
        v21 = WPP_GLOBAL_Control;
      }
      v31 = a3;
LABEL_130:
      v32 = 0;
      if ( (LastError & 0x1FFF0000) == 0x70000 )
        LastError = (unsigned __int16)LastError;
      goto LABEL_232;
    }
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 229, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v83);
    }
    v72 = v83;
    File = (void *)InternalSafeCreateFile(v83, 0x80000000, 1u, 3u, 128);
    v34 = File;
    if ( File == (void *)-1LL )
    {
      v35 = GetLastError();
      LastError = v35;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_231;
      }
      v36 = 230;
LABEL_141:
      WPP_SF_Sd(
        *((_QWORD *)v21 + 2),
        v36,
        (unsigned int)&WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
        (unsigned int)v83,
        v35);
LABEL_47:
      v21 = WPP_GLOBAL_Control;
      goto LABEL_231;
    }
    FileSize = GetFileSize(File, 0);
    if ( FileSize == -1 )
    {
      v38 = GetLastError();
      LastError = v38;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 231, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v38);
      }
      CloseHandle(v34);
      goto LABEL_47;
    }
    if ( !CloseHandle(v34) )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_154:
        if ( !FileSize )
        {
          LastError = 13;
          goto LABEL_231;
        }
        memset(v82, 0, sizeof(v82));
        v40 = TiffOpen(v83, v82, 0, 1);
        if ( v40 )
        {
          TiffClose(v40);
        }
        else
        {
          v35 = GetLastError();
          LastError = v35;
          if ( v35 )
          {
            v21 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_231;
            }
            v36 = 233;
            goto LABEL_141;
          }
        }
LABEL_164:
        v31 = a3;
        v41 = (const struct _FAX_COVERPAGE_INFO_EXW *)a3;
        if ( *(_QWORD *)(a3 + 8) && !*(_DWORD *)(a3 + 16) )
        {
          v42 = StringCchPrintfW(
                  FileName,
                  0x104u,
                  L"%s\\%s%s%s",
                  *((_QWORD *)g_pFaxConfig + 12),
                  StringSid,
                  L"$",
                  *(_QWORD *)(a3 + 8));
          LastError = v42;
          if ( v42 < 0 )
          {
            v21 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                234,
                &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                (unsigned int)v42);
              v21 = WPP_GLOBAL_Control;
            }
            goto LABEL_130;
          }
          v43 = *(_OWORD *)(a3 + 16);
          v41 = (const struct _FAX_COVERPAGE_INFO_EXW *)&v79;
          *(_QWORD *)&v79 = *(_QWORD *)a3;
          *((_QWORD *)&v79 + 1) = FileName;
          v81 = *(_QWORD *)(a3 + 32);
          v80 = v43;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              235,
              &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
              FileName);
          }
        }
        RecipientList = CreateRecipientList(a6, a5);
        EnterCriticalSection(&g_CsQueue);
        v66 = AddParentJob(&g_QueueListHead, v72, a4, v71, v41, ClientUserName, lpMem, a6, RecipientList, 1);
        v32 = v66;
        if ( !v66 )
        {
          v44 = GetLastError();
          LastError = v44;
          if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 236, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v44);
          }
          LeaveCriticalSection(&g_CsQueue);
          v21 = WPP_GLOBAL_Control;
          goto LABEL_232;
        }
        v45 = 0;
        while ( 1 )
        {
          v46 = AddRecipientJob(
                  &g_QueueListHead,
                  v66,
                  (struct _FAX_PERSONAL_PROFILEW *)((char *)a6 + 136 * (unsigned int)v45),
                  1,
                  1u);
          if ( !v46 )
            break;
          *(_QWORD *)(a10 + 8 * v45) = *((_QWORD *)v46 + 2);
          v45 = (unsigned int)(v45 + 1);
          if ( (unsigned int)v45 >= a5 )
          {
            *a9 = *((_QWORD *)v66 + 2);
            v47 = (_QWORD *)*((_QWORD *)v66 + 27);
            v48 = 0;
            v49 = (_DWORD *)v77;
            if ( v77 )
            {
              do
              {
                v50 = v47[2];
                if ( !v48 )
                  *v49 = *(_DWORD *)(v50 + 32);
                QueueEvent = CreateQueueEvent(0, v50);
                if ( QueueEvent
                  && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  LOWORD(v65) = QueueEvent;
                  WPP_SF_lh(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    237,
                    &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                    *(unsigned int *)(v50 + 16),
                    v65);
                }
                if ( !CreateFaxEvent(0, 0x16u, *(_DWORD *)(v50 + 32), *((void **)v66 + 51))
                  && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    238,
                    &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                    *(unsigned int *)(v50 + 32));
                }
                v47 = (_QWORD *)*v47;
                ++v48;
              }
              while ( v48 < a5 );
              v52 = v66;
            }
            else
            {
              v52 = v66;
              do
              {
                v55 = v47[2];
                v56 = CreateQueueEvent(0, v55);
                if ( v56
                  && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  LOWORD(v65) = v56;
                  WPP_SF_lh(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    237,
                    &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                    *(unsigned int *)(v55 + 16),
                    v65);
                }
                if ( !CreateFaxEvent(0, 0x16u, *(_DWORD *)(v55 + 32), *((void **)v66 + 51))
                  && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    238,
                    &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                    *(unsigned int *)(v55 + 32));
                }
                v47 = (_QWORD *)*v47;
                ++v48;
              }
              while ( v48 < a5 );
            }
            if ( a5 > 1
              && !CreateFaxEvent(0, 0x16u, *((_DWORD *)v52 + 8), *((void **)v52 + 51))
              && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              LOWORD(v65) = GetLastError();
              WPP_SF_lh(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                239,
                &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
                *((unsigned int *)v52 + 8),
                v65);
            }
            LeaveCriticalSection(&g_CsQueue);
            if ( !(unsigned int)StartJobQueueTimer()
              && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v57 = GetLastError();
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 240, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v57);
            }
            LastError = 0;
            goto LABEL_275;
          }
        }
        LastError = GetLastError();
        for ( i = (_QWORD *)*((_QWORD *)v66 + 27); i != (_QWORD *)((char *)v66 + 216); --*((_DWORD *)v66 + 12) )
        {
          v54 = i[2];
          i = (_QWORD *)*i;
          *(_DWORD *)(v54 + 48) = 0;
        }
        RemoveParentJob(v66, 1, 0);
        LeaveCriticalSection(&g_CsQueue);
        goto LABEL_251;
      }
      v39 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 232, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v39);
    }
    v21 = WPP_GLOBAL_Control;
    goto LABEL_154;
  }
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v25 = 219;
    v26 = 0;
    goto LABEL_74;
  }
LABEL_231:
  v32 = 0;
  v31 = a3;
LABEL_232:
  if ( *(_DWORD *)(v31 + 16) )
    goto LABEL_252;
  v58 = *(_QWORD *)(v31 + 8);
  if ( !v58 )
    goto LABEL_252;
  if ( v21 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 4) != 0 && *((_BYTE *)v21 + 25) >= 5u )
    WPP_SF_S(*((_QWORD *)v21 + 2), 241, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v58);
  v59 = -1;
  do
    ++v59;
  while ( FileName[v59] );
  if ( !v59 )
  {
    v60 = StringCchPrintfW(
            FileName,
            0x104u,
            L"%s\\%s%s%s",
            *((_QWORD *)g_pFaxConfig + 12),
            StringSid,
            L"$",
            *(_QWORD *)(v31 + 8));
    if ( v60 < 0
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        242,
        &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
        (unsigned int)v60);
    }
  }
  if ( DeleteFileW(FileName) )
  {
LABEL_251:
    v21 = WPP_GLOBAL_Control;
    goto LABEL_252;
  }
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v61 = GetLastError();
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      243,
      (unsigned int)&WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
      *(_QWORD *)(v31 + 8),
      v61);
    goto LABEL_251;
  }
LABEL_252:
  if ( v73 && !v32 )
  {
    v62 = v72;
    if ( !v72 )
    {
      v63 = StringCchPrintfW(v83, 0x104u, L"%s\\%s%s%s", *((_QWORD *)g_pFaxConfig + 12), StringSid, L"$", v73);
      if ( v63 >= 0 )
        goto LABEL_260;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            244,
            &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
            (unsigned int)v63);
LABEL_260:
          v21 = WPP_GLOBAL_Control;
        }
        if ( v21 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 4) != 0 && *((_BYTE *)v21 + 25) >= 5u )
        {
          WPP_SF_S(*((_QWORD *)v21 + 2), 245, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v83);
          v21 = WPP_GLOBAL_Control;
        }
      }
      v62 = v83;
    }
    if ( v21 != (CMapDeviceId *)&WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 4) != 0 && *((_BYTE *)v21 + 25) >= 5u )
      WPP_SF_S(*((_QWORD *)v21 + 2), 246, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, v62);
    if ( !DeleteFileW(v62)
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v64 = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        247,
        (unsigned int)&WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids,
        (_DWORD)v62,
        v64);
    }
  }
LABEL_275:
  if ( v78 != *((_QWORD *)v71 + 4) )
    *((_QWORD *)v71 + 4) = v78;
  pMemFree(ClientUserName);
  pMemFree(lpMem);
  pMemFree(0);
  if ( StringSid )
    LocalFree(StringSid);
  v19 = RecipientList;
LABEL_39:
  pMemFree(v19);
  return LastError;
}

```

## disassembly

```asm
0x14001dbc0  push    rbp
0x14001dbc2  push    rbx
0x14001dbc3  push    rsi
0x14001dbc4  push    rdi
0x14001dbc5  push    r12
0x14001dbc7  push    r13
0x14001dbc9  push    r14
0x14001dbcb  push    r15
0x14001dbcd  lea     rbp, [rsp-438h]
0x14001dbd5  sub     rsp, 538h
0x14001dbdc  mov     rax, cs:__security_cookie
0x14001dbe3  xor     rax, rsp
0x14001dbe6  mov     [rbp+470h+var_50], rax
0x14001dbed  mov     rax, [rbp+470h+arg_30]
0x14001dbf4  mov     rbx, r8
0x14001dbf7  mov     r14d, [rbp+470h+arg_20]
0x14001dbfe  mov     r15, r9
0x14001dc01  mov     rsi, [rbp+470h+arg_28]
0x14001dc08  mov     rdi, rcx
0x14001dc0b  mov     r12, [rbp+470h+arg_40]
0x14001dc12  mov     r13, [rbp+470h+arg_48]
0x14001dc19  mov     [rsp+570h+var_500], rax
0x14001dc1e  mov     rax, [rbp+470h+arg_38]
0x14001dc25  mov     [rbp+470h+var_4D0], rax
0x14001dc29  mov     [rsp+570h+var_518], rbx
0x14001dc2e  mov     [rbp+470h+var_4F0], rdx
0x14001dc32  mov     [rsp+570h+StringSid], 0
0x14001dc3b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dc42  lea     rax, WPP_GLOBAL_Control
0x14001dc49  cmp     rcx, rax
0x14001dc4c  jz      short loc_14001DC6F
0x14001dc4e  test    byte ptr [rcx+1Ch], 4
0x14001dc52  jz      short loc_14001DC6F
0x14001dc54  cmp     byte ptr [rcx+19h], 5
0x14001dc58  jb      short loc_14001DC6F
0x14001dc5a  mov     rcx, [rcx+10h]
0x14001dc5e  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001dc65  mov     edx, 0D2h
0x14001dc6a  call    WPP_SF_
0x14001dc6f  xor     edx, edx; Val
0x14001dc71  lea     rcx, [rbp+470h+var_470]; void *
0x14001dc75  mov     r8d, 208h; Size
0x14001dc7b  call    memset_0
0x14001dc80  xorps   xmm0, xmm0
0x14001dc83  lea     rcx, [rbp+470h+FileName]; void *
0x14001dc8a  xor     eax, eax
0x14001dc8c  xor     edx, edx; Val
0x14001dc8e  mov     r8d, 208h; Size
0x14001dc94  mov     [rbp+470h+var_4A0], rax
0x14001dc98  movups  [rbp+470h+var_4C0], xmm0
0x14001dc9c  movups  [rbp+470h+var_4B0], xmm0
0x14001dca0  call    memset_0
0x14001dca5  mov     [rsp+570h+var_508], 0
0x14001dcad  test    r14d, r14d
0x14001dcb0  jz      loc_14001DD7D
0x14001dcb6  test    r15, r15
0x14001dcb9  jz      loc_14001DD7D
0x14001dcbf  test    rsi, rsi
0x14001dcc2  jz      loc_14001DD7D
0x14001dcc8  cmp     [rsp+570h+var_500], 0
0x14001dcce  jz      loc_14001DD7D
0x14001dcd4  test    r12, r12
0x14001dcd7  jz      loc_14001DD7D
0x14001dcdd  test    r13, r13
0x14001dce0  jz      loc_14001DD7D
0x14001dce6  test    rbx, rbx
0x14001dce9  jz      loc_14001DD7D
0x14001dcef  mov     rax, [rbp+470h+var_4F0]
0x14001dcf3  test    rax, rax
0x14001dcf6  jz      short loc_14001DD2C
0x14001dcf8  xor     edx, edx; int
0x14001dcfa  mov     rcx, rax; unsigned __int16 *
0x14001dcfd  call    ?ValidateCopiedQueueFileName@@YAHPEBGH@Z; ValidateCopiedQueueFileName(ushort const *,int)
0x14001dd02  test    eax, eax
0x14001dd04  jnz     short loc_14001DD2C
0x14001dd06  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dd0d  lea     rax, WPP_GLOBAL_Control
0x14001dd14  cmp     rcx, rax
0x14001dd17  jz      short loc_14001DD7D
0x14001dd19  test    byte ptr [rcx+1Ch], 4
0x14001dd1d  jz      short loc_14001DD7D
0x14001dd1f  cmp     byte ptr [rcx+19h], 2
0x14001dd23  jb      short loc_14001DD7D
0x14001dd25  mov     edx, 0D3h
0x14001dd2a  jmp     short loc_14001DD6D
0x14001dd2c  mov     rcx, [rbx+8]; unsigned __int16 *
0x14001dd30  test    rcx, rcx
0x14001dd33  jz      short loc_14001DDA6
0x14001dd35  cmp     dword ptr [rbx+10h], 0
0x14001dd39  jnz     short loc_14001DDA6
0x14001dd3b  mov     edx, 1; int
0x14001dd40  call    ?ValidateCopiedQueueFileName@@YAHPEBGH@Z; ValidateCopiedQueueFileName(ushort const *,int)
0x14001dd45  test    eax, eax
0x14001dd47  jnz     short loc_14001DDA6
0x14001dd49  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dd50  lea     rax, WPP_GLOBAL_Control
0x14001dd57  cmp     rcx, rax
0x14001dd5a  jz      short loc_14001DD7D
0x14001dd5c  test    byte ptr [rcx+1Ch], 4
0x14001dd60  jz      short loc_14001DD7D
0x14001dd62  cmp     byte ptr [rcx+19h], 2
0x14001dd66  jb      short loc_14001DD7D
0x14001dd68  mov     edx, 0D4h
0x14001dd6d  mov     rcx, [rcx+10h]
0x14001dd71  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001dd78  call    WPP_SF_
0x14001dd7d  mov     eax, 57h ; 'W'
0x14001dd82  mov     rcx, [rbp+470h+var_50]
0x14001dd89  xor     rcx, rsp; StackCookie
0x14001dd8c  call    __security_check_cookie
0x14001dd91  add     rsp, 538h
0x14001dd98  pop     r15
0x14001dd9a  pop     r14
0x14001dd9c  pop     r13
0x14001dd9e  pop     r12
0x14001dda0  pop     rdi
0x14001dda1  pop     rsi
0x14001dda2  pop     rbx
0x14001dda3  pop     rbp
0x14001dda4  retn
0x14001dda6  call    ?GetClientUserSID@@YAPEAXXZ; GetClientUserSID(void)
0x14001ddab  mov     [rbp+470h+lpMem], rax
0x14001ddaf  test    rax, rax
0x14001ddb2  jnz     short loc_14001DDFD
0x14001ddb4  call    cs:__imp_GetLastError
0x14001ddbb  nop     dword ptr [rax+rax+00h]
0x14001ddc0  mov     ebx, eax
0x14001ddc2  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ddc9  lea     rax, WPP_GLOBAL_Control
0x14001ddd0  cmp     rcx, rax
0x14001ddd3  jz      short loc_14001DDF9
0x14001ddd5  test    byte ptr [rcx+1Ch], 4
0x14001ddd9  jz      short loc_14001DDF9
0x14001dddb  cmp     byte ptr [rcx+19h], 2
0x14001dddf  jb      short loc_14001DDF9
0x14001dde1  mov     rcx, [rcx+10h]
0x14001dde5  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001ddec  mov     edx, 0D5h
0x14001ddf1  mov     r9d, ebx
0x14001ddf4  call    WPP_SF_d
0x14001ddf9  mov     eax, ebx
0x14001ddfb  jmp     short loc_14001DD82
0x14001ddfd  lea     rdx, [rsp+570h+StringSid]; StringSid
0x14001de02  mov     rcx, rax; Sid
0x14001de05  call    cs:__imp_ConvertSidToStringSidW
0x14001de0c  nop     dword ptr [rax+rax+00h]
0x14001de11  xor     r10d, r10d
0x14001de14  test    eax, eax
0x14001de16  jnz     short loc_14001DE68
0x14001de18  call    cs:__imp_GetLastError
0x14001de1f  nop     dword ptr [rax+rax+00h]
0x14001de24  mov     ebx, eax
0x14001de26  mov     rcx, cs:WPP_GLOBAL_Control
0x14001de2d  lea     rax, WPP_GLOBAL_Control
0x14001de34  cmp     rcx, rax
0x14001de37  jz      short loc_14001DE5D
0x14001de39  test    byte ptr [rcx+1Ch], 4
0x14001de3d  jz      short loc_14001DE5D
0x14001de3f  cmp     byte ptr [rcx+19h], 2
0x14001de43  jb      short loc_14001DE5D
0x14001de45  mov     rcx, [rcx+10h]
0x14001de49  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001de50  mov     edx, 0D6h
0x14001de55  mov     r9d, ebx
0x14001de58  call    WPP_SF_d
0x14001de5d  mov     rcx, [rbp+470h+lpMem]; lpMem
0x14001de61  call    pMemFree
0x14001de66  jmp     short loc_14001DDF9
0x14001de68  mov     rdx, [rsp+570h+var_500]
0x14001de6d  mov     [rbp+470h+var_4E8], r10
0x14001de71  mov     [rsp+570h+var_520], r10
0x14001de76  mov     [rsp+570h+var_4F8], r10
0x14001de7b  mov     rax, [rdx+20h]
0x14001de7f  mov     [rbp+470h+var_4C8], rax
0x14001de83  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14001de8a  mov     [rbp+470h+var_4D8], r10
0x14001de8e  mov     r8d, [rax+58h]
0x14001de92  test    r8d, r8d
0x14001de95  jz      short loc_14001DEFF
0x14001de97  cmp     r14d, r8d
0x14001de9a  jbe     short loc_14001DEFF
0x14001de9c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dea3  lea     rsi, WPP_GLOBAL_Control
0x14001deaa  cmp     rcx, rsi
0x14001dead  jz      short loc_14001DED8
0x14001deaf  test    byte ptr [rcx+1Ch], 4
0x14001deb3  jz      short loc_14001DED8
0x14001deb5  cmp     byte ptr [rcx+19h], 2
0x14001deb9  jb      short loc_14001DED8
0x14001debb  mov     rcx, [rcx+10h]
0x14001debf  mov     edx, 0D7h
0x14001dec4  mov     [rsp+570h+var_550], r8d
0x14001dec9  mov     r9d, r14d
0x14001decc  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001ded3  call    WPP_SF_dd
0x14001ded8  mov     rcx, rdi; void *
0x14001dedb  call    ?FindClientAPIVersion@@YAKPEAX@Z; FindClientAPIVersion(void *)
0x14001dee0  cmp     eax, 20000h
0x14001dee5  sbb     ebx, ebx
0x14001dee7  and     ebx, 0FFFFE4A0h
0x14001deed  add     ebx, 1B65h
0x14001def3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001defa  jmp     loc_14001EB43
0x14001deff  mov     r9d, r10d
0x14001df02  test    r14d, r14d
0x14001df05  jz      short loc_14001DF20
0x14001df07  mov     eax, r9d
0x14001df0a  imul    rcx, rax, 88h
0x14001df11  cmp     [rcx+rsi+10h], r10
0x14001df16  jz      short loc_14001DF79
0x14001df18  inc     r9d
0x14001df1b  cmp     r9d, r14d
0x14001df1e  jb      short loc_14001DF07
0x14001df20  cmp     [rdx+2Ch], r10d
0x14001df24  jnz     loc_14001EB03
0x14001df2a  mov     eax, 0FFFF1234h
0x14001df2f  cmp     [rdx+30h], rax
0x14001df33  jz      loc_14001EB03
0x14001df39  mov     r9d, [rdx+28h]
0x14001df3d  mov     ecx, r9d
0x14001df40  test    r9d, r9d
0x14001df43  jz      loc_14001DFCC
0x14001df49  sub     ecx, 1
0x14001df4c  jz      short loc_14001DFC5
0x14001df4e  cmp     ecx, 1
0x14001df51  jz      short loc_14001DFBE
0x14001df53  mov     rcx, cs:WPP_GLOBAL_Control
0x14001df5a  lea     rsi, WPP_GLOBAL_Control
0x14001df61  cmp     rcx, rsi
0x14001df64  jz      short loc_14001DFB4
0x14001df66  test    byte ptr [rcx+1Ch], 4
0x14001df6a  jz      short loc_14001DFB4
0x14001df6c  cmp     byte ptr [rcx+19h], 2
0x14001df70  jb      short loc_14001DFB4
0x14001df72  mov     edx, 0DAh
0x14001df77  jmp     short loc_14001DF9D
0x14001df79  mov     rcx, cs:WPP_GLOBAL_Control
0x14001df80  lea     rsi, WPP_GLOBAL_Control
0x14001df87  cmp     rcx, rsi
0x14001df8a  jz      short loc_14001DFB4
0x14001df8c  test    byte ptr [rcx+1Ch], 4
0x14001df90  jz      short loc_14001DFB4
0x14001df92  cmp     byte ptr [rcx+19h], 2
0x14001df96  jb      short loc_14001DFB4
0x14001df98  mov     edx, 0D8h
0x14001df9d  mov     rcx, [rcx+10h]
0x14001dfa1  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001dfa8  call    WPP_SF_d
0x14001dfad  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dfb4  mov     ebx, 57h ; 'W'
0x14001dfb9  jmp     loc_14001EB43
0x14001dfbe  mov     ecx, 4
0x14001dfc3  jmp     short loc_14001DFD1
0x14001dfc5  mov     ecx, 2
0x14001dfca  jmp     short loc_14001DFD1
0x14001dfcc  mov     ecx, 1; unsigned int
0x14001dfd1  mov     r9d, 1; int
0x14001dfd7  lea     rdx, [rsp+570h+var_508]; int *
0x14001dfdc  xor     r8d, r8d; unsigned int *
0x14001dfdf  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x14001dfe4  mov     ebx, eax
0x14001dfe6  test    eax, eax
0x14001dfe8  jz      short loc_14001E032
0x14001dfea  mov     rcx, cs:WPP_GLOBAL_Control
0x14001dff1  lea     rsi, WPP_GLOBAL_Control
0x14001dff8  cmp     rcx, rsi
0x14001dffb  jz      loc_14001EB43
0x14001e001  test    byte ptr [rcx+1Ch], 4
0x14001e005  jz      loc_14001EB43
0x14001e00b  cmp     byte ptr [rcx+19h], 2
0x14001e00f  jb      loc_14001EB43
0x14001e015  mov     edx, 0DBh
0x14001e01a  xor     r9d, r9d
0x14001e01d  mov     rcx, [rcx+10h]
0x14001e021  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001e028  call    WPP_SF_d
0x14001e02d  jmp     loc_14001DEF3
0x14001e032  cmp     [rsp+570h+var_508], 0
0x14001e037  jnz     short loc_14001E07E
0x14001e039  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e040  lea     rsi, WPP_GLOBAL_Control
0x14001e047  cmp     rcx, rsi
0x14001e04a  jz      short loc_14001E074
0x14001e04c  test    byte ptr [rcx+1Ch], 4
0x14001e050  jz      short loc_14001E074
0x14001e052  cmp     byte ptr [rcx+19h], 2
0x14001e056  jb      short loc_14001E074
0x14001e058  mov     rcx, [rcx+10h]
0x14001e05c  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001e063  mov     edx, 0DCh
0x14001e068  call    WPP_SF_
0x14001e06d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e074  mov     ebx, 5
0x14001e079  jmp     loc_14001EB43
0x14001e07e  mov     r9, [rsp+570h+var_500]
0x14001e083  mov     r9d, [r9+18h]
0x14001e087  test    r9d, 0FFFFFFE2h
0x14001e08e  jz      short loc_14001E0C5
0x14001e090  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e097  lea     rsi, WPP_GLOBAL_Control
  ... truncated ...
```
