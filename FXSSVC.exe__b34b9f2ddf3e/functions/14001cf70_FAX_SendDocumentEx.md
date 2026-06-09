# FAX_SendDocumentEx

- ea: `0x14001cf70`
- end: `0x14001e13a`
- name: `FAX_SendDocumentEx`
- size: `4554`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *, __int64, const struct _FAX_PERSONAL_PROFILEW *, unsigned int, struct _FAX_PERSONAL_PROFILEW *, struct _FAX_JOB_PARAM_EXW *, __int64, _QWORD *, __int64)`
- caller_count: `0`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callees

- `0x140002c43`
- `0x140004aa4`
- `0x140004b30`
- `0x140004b58`
- `0x140004ce4`
- `0x140004df0`
- `0x140004e68`
- `0x1400102b0`
- `0x140015bf4`
- `0x14001cf70`
- `0x140022a4c`
- `0x14002ce80`
- `0x14003567c`
- `0x1400362a0`
- `0x14003ac78`
- `0x14003e488`
- `0x1400452ac`
- `0x140045560`
- `0x140045798`
- `0x14005584c`
- `0x140055acc`
- `0x140065dbc`
- `0x14006a3a4`
- `0x140070e74`
- `0x140075efc`
- `0x1400818b0`

## import_xrefs

- `ADVAPI32!ConvertSidToStringSidW` at `0x14001d1ae`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14001d1ae`
- `KERNEL32!GetLastError` at `0x14001d163`
- `KERNEL32!GetLastError` at `0x14001d1bb`
- `KERNEL32!GetLastError` at `0x14001d62c`
- `KERNEL32!GetLastError` at `0x14001d799`
- `KERNEL32!GetLastError` at `0x14001d800`
- `KERNEL32!GetLastError` at `0x14001d879`
- `KERNEL32!GetLastError` at `0x14001d8e1`
- `KERNEL32!GetLastError` at `0x14001daba`
- `KERNEL32!GetLastError` at `0x14001dc4d`
- `KERNEL32!GetLastError` at `0x14001dd93`
- `KERNEL32!GetLastError` at `0x14001ddf5`
- `KERNEL32!GetLastError` at `0x14001df65`
- `KERNEL32!GetLastError` at `0x14001e0cc`
- `KERNEL32!GetLastError` at `0x14001d163`
- `KERNEL32!GetLastError` at `0x14001d1bb`
- `KERNEL32!GetLastError` at `0x14001d62c`
- `KERNEL32!GetLastError` at `0x14001d799`
- `KERNEL32!GetLastError` at `0x14001d800`
- `KERNEL32!GetLastError` at `0x14001d879`
- `KERNEL32!GetLastError` at `0x14001d8e1`
- `KERNEL32!GetLastError` at `0x14001daba`
- `KERNEL32!GetLastError` at `0x14001dc4d`
- `KERNEL32!GetLastError` at `0x14001dd93`
- `KERNEL32!GetLastError` at `0x14001ddf5`
- `KERNEL32!GetLastError` at `0x14001df65`
- `KERNEL32!GetLastError` at `0x14001e0cc`
- `KERNEL32!CloseHandle` at `0x14001d842`
- `KERNEL32!CloseHandle` at `0x14001d850`
- `KERNEL32!CloseHandle` at `0x14001d842`
- `KERNEL32!CloseHandle` at `0x14001d850`
- `KERNEL32!LocalFree` at `0x14001e12b`
- `KERNEL32!LocalFree` at `0x14001e12b`
- `KERNEL32!DeleteFileW` at `0x14001df43`
- `KERNEL32!DeleteFileW` at `0x14001e0aa`
- `KERNEL32!DeleteFileW` at `0x14001df43`
- `KERNEL32!DeleteFileW` at `0x14001e0aa`
- `KERNEL32!EnterCriticalSection` at `0x14001d5b7`
- `KERNEL32!EnterCriticalSection` at `0x14001da61`
- `KERNEL32!EnterCriticalSection` at `0x14001d5b7`
- `KERNEL32!EnterCriticalSection` at `0x14001da61`
- `KERNEL32!LeaveCriticalSection` at `0x14001d5ce`
- `KERNEL32!LeaveCriticalSection` at `0x14001db00`
- `KERNEL32!LeaveCriticalSection` at `0x14001dc91`
- `KERNEL32!LeaveCriticalSection` at `0x14001ddce`
- `KERNEL32!LeaveCriticalSection` at `0x14001d5ce`
- `KERNEL32!LeaveCriticalSection` at `0x14001db00`
- `KERNEL32!LeaveCriticalSection` at `0x14001dc91`
- `KERNEL32!LeaveCriticalSection` at `0x14001ddce`
- `KERNEL32!GetFileSize` at `0x14001d7f3`
- `KERNEL32!GetFileSize` at `0x14001d7f3`
- `FXSTIFF!TiffClose` at `0x14001d925`
- `FXSTIFF!TiffClose` at `0x14001d925`
- `FXSTIFF!TiffOpen` at `0x14001d8d6`
- `FXSTIFF!TiffOpen` at `0x14001d8d6`
- `ntdll!WinSqmIncrementDWORD` at `0x14001d678`
- `ntdll!WinSqmIncrementDWORD` at `0x14001d678`

## pseudocode

```c
// Hidden C++ exception states: #wind=72 #try_helpers=1
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
  DWORD LastError; // ebx
  void *v19; // rcx
  unsigned int v20; // r8d
  CMapDeviceId *v21; // rcx
  __int64 v22; // r9
  __int64 v23; // rdx
  unsigned int v24; // ecx
  __int64 v25; // rdx
  __int64 v26; // r9
  int v27; // eax
  DWORD v28; // eax
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
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 215, &WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids, a5, v20);
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
      if ( (v27 & dword_1400A1644) == 0 )
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
0x14001cf70  push    rbp
0x14001cf72  push    rbx
0x14001cf73  push    rsi
0x14001cf74  push    rdi
0x14001cf75  push    r12
0x14001cf77  push    r13
0x14001cf79  push    r14
0x14001cf7b  push    r15
0x14001cf7d  lea     rbp, [rsp-438h]
0x14001cf85  sub     rsp, 538h
0x14001cf8c  mov     rax, cs:__security_cookie
0x14001cf93  xor     rax, rsp
0x14001cf96  mov     [rbp+470h+var_50], rax
0x14001cf9d  mov     rax, [rbp+470h+arg_30]
0x14001cfa4  mov     rbx, r8
0x14001cfa7  mov     r14d, [rbp+470h+arg_20]
0x14001cfae  mov     r15, r9
0x14001cfb1  mov     rsi, [rbp+470h+arg_28]
0x14001cfb8  mov     rdi, rcx
0x14001cfbb  mov     r12, [rbp+470h+arg_40]
0x14001cfc2  mov     r13, [rbp+470h+arg_48]
0x14001cfc9  mov     [rsp+570h+var_500], rax
0x14001cfce  mov     rax, [rbp+470h+arg_38]
0x14001cfd5  mov     [rbp+470h+var_4D0], rax
0x14001cfd9  mov     [rsp+570h+var_518], rbx
0x14001cfde  mov     [rbp+470h+var_4F0], rdx
0x14001cfe2  mov     [rsp+570h+StringSid], 0
0x14001cfeb  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cff2  lea     rax, WPP_GLOBAL_Control
0x14001cff9  cmp     rcx, rax
0x14001cffc  jz      short loc_14001D01F
0x14001cffe  test    byte ptr [rcx+1Ch], 4
0x14001d002  jz      short loc_14001D01F
0x14001d004  cmp     byte ptr [rcx+19h], 5
0x14001d008  jb      short loc_14001D01F
0x14001d00a  mov     rcx, [rcx+10h]
0x14001d00e  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001d015  mov     edx, 0D2h
0x14001d01a  call    WPP_SF_
0x14001d01f  xor     edx, edx; Val
0x14001d021  lea     rcx, [rbp+470h+var_470]; void *
0x14001d025  mov     r8d, 208h; Size
0x14001d02b  call    memset_0
0x14001d030  xorps   xmm0, xmm0
0x14001d033  lea     rcx, [rbp+470h+FileName]; void *
0x14001d03a  xor     eax, eax
0x14001d03c  xor     edx, edx; Val
0x14001d03e  mov     r8d, 208h; Size
0x14001d044  mov     [rbp+470h+var_4A0], rax
0x14001d048  movups  [rbp+470h+var_4C0], xmm0
0x14001d04c  movups  [rbp+470h+var_4B0], xmm0
0x14001d050  call    memset_0
0x14001d055  mov     [rsp+570h+var_508], 0
0x14001d05d  test    r14d, r14d
0x14001d060  jz      loc_14001D12D
0x14001d066  test    r15, r15
0x14001d069  jz      loc_14001D12D
0x14001d06f  test    rsi, rsi
0x14001d072  jz      loc_14001D12D
0x14001d078  cmp     [rsp+570h+var_500], 0
0x14001d07e  jz      loc_14001D12D
0x14001d084  test    r12, r12
0x14001d087  jz      loc_14001D12D
0x14001d08d  test    r13, r13
0x14001d090  jz      loc_14001D12D
0x14001d096  test    rbx, rbx
0x14001d099  jz      loc_14001D12D
0x14001d09f  mov     rax, [rbp+470h+var_4F0]
0x14001d0a3  test    rax, rax
0x14001d0a6  jz      short loc_14001D0DC
0x14001d0a8  xor     edx, edx; int
0x14001d0aa  mov     rcx, rax; unsigned __int16 *
0x14001d0ad  call    ?ValidateCopiedQueueFileName@@YAHPEBGH@Z; ValidateCopiedQueueFileName(ushort const *,int)
0x14001d0b2  test    eax, eax
0x14001d0b4  jnz     short loc_14001D0DC
0x14001d0b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d0bd  lea     rax, WPP_GLOBAL_Control
0x14001d0c4  cmp     rcx, rax
0x14001d0c7  jz      short loc_14001D12D
0x14001d0c9  test    byte ptr [rcx+1Ch], 4
0x14001d0cd  jz      short loc_14001D12D
0x14001d0cf  cmp     byte ptr [rcx+19h], 2
0x14001d0d3  jb      short loc_14001D12D
0x14001d0d5  mov     edx, 0D3h
0x14001d0da  jmp     short loc_14001D11D
0x14001d0dc  mov     rcx, [rbx+8]; unsigned __int16 *
0x14001d0e0  test    rcx, rcx
0x14001d0e3  jz      short loc_14001D155
0x14001d0e5  cmp     dword ptr [rbx+10h], 0
0x14001d0e9  jnz     short loc_14001D155
0x14001d0eb  mov     edx, 1; int
0x14001d0f0  call    ?ValidateCopiedQueueFileName@@YAHPEBGH@Z; ValidateCopiedQueueFileName(ushort const *,int)
0x14001d0f5  test    eax, eax
0x14001d0f7  jnz     short loc_14001D155
0x14001d0f9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d100  lea     rax, WPP_GLOBAL_Control
0x14001d107  cmp     rcx, rax
0x14001d10a  jz      short loc_14001D12D
0x14001d10c  test    byte ptr [rcx+1Ch], 4
0x14001d110  jz      short loc_14001D12D
0x14001d112  cmp     byte ptr [rcx+19h], 2
0x14001d116  jb      short loc_14001D12D
0x14001d118  mov     edx, 0D4h
0x14001d11d  mov     rcx, [rcx+10h]
0x14001d121  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001d128  call    WPP_SF_
0x14001d12d  mov     eax, 57h ; 'W'
0x14001d132  mov     rcx, [rbp+470h+var_50]
0x14001d139  xor     rcx, rsp; StackCookie
0x14001d13c  call    __security_check_cookie
0x14001d141  add     rsp, 538h
0x14001d148  pop     r15
0x14001d14a  pop     r14
0x14001d14c  pop     r13
0x14001d14e  pop     r12
0x14001d150  pop     rdi
0x14001d151  pop     rsi
0x14001d152  pop     rbx
0x14001d153  pop     rbp
0x14001d154  retn
0x14001d155  call    ?GetClientUserSID@@YAPEAXXZ; GetClientUserSID(void)
0x14001d15a  mov     [rbp+470h+lpMem], rax
0x14001d15e  test    rax, rax
0x14001d161  jnz     short loc_14001D1A6
0x14001d163  call    cs:__imp_GetLastError
0x14001d169  mov     ebx, eax
0x14001d16b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d172  lea     rax, WPP_GLOBAL_Control
0x14001d179  cmp     rcx, rax
0x14001d17c  jz      short loc_14001D1A2
0x14001d17e  test    byte ptr [rcx+1Ch], 4
0x14001d182  jz      short loc_14001D1A2
0x14001d184  cmp     byte ptr [rcx+19h], 2
0x14001d188  jb      short loc_14001D1A2
0x14001d18a  mov     rcx, [rcx+10h]
0x14001d18e  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001d195  mov     edx, 0D5h
0x14001d19a  mov     r9d, ebx
0x14001d19d  call    WPP_SF_d
0x14001d1a2  mov     eax, ebx
0x14001d1a4  jmp     short loc_14001D132
0x14001d1a6  lea     rdx, [rsp+570h+StringSid]; StringSid
0x14001d1ab  mov     rcx, rax; Sid
0x14001d1ae  call    cs:__imp_ConvertSidToStringSidW
0x14001d1b4  xor     r10d, r10d
0x14001d1b7  test    eax, eax
0x14001d1b9  jnz     short loc_14001D205
0x14001d1bb  call    cs:__imp_GetLastError
0x14001d1c1  mov     ebx, eax
0x14001d1c3  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d1ca  lea     rax, WPP_GLOBAL_Control
0x14001d1d1  cmp     rcx, rax
0x14001d1d4  jz      short loc_14001D1FA
0x14001d1d6  test    byte ptr [rcx+1Ch], 4
0x14001d1da  jz      short loc_14001D1FA
0x14001d1dc  cmp     byte ptr [rcx+19h], 2
0x14001d1e0  jb      short loc_14001D1FA
0x14001d1e2  mov     rcx, [rcx+10h]
0x14001d1e6  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001d1ed  mov     edx, 0D6h
0x14001d1f2  mov     r9d, ebx
0x14001d1f5  call    WPP_SF_d
0x14001d1fa  mov     rcx, [rbp+470h+lpMem]; lpMem
0x14001d1fe  call    pMemFree
0x14001d203  jmp     short loc_14001D1A2
0x14001d205  mov     rdx, [rsp+570h+var_500]
0x14001d20a  mov     [rbp+470h+var_4E8], r10
0x14001d20e  mov     [rsp+570h+var_520], r10
0x14001d213  mov     [rsp+570h+var_4F8], r10
0x14001d218  mov     rax, [rdx+20h]
0x14001d21c  mov     [rbp+470h+var_4C8], rax
0x14001d220  mov     rax, cs:?g_pFaxConfig@@3PEAVCFaxConfiguration@@EA; CFaxConfiguration * g_pFaxConfig
0x14001d227  mov     [rbp+470h+var_4D8], r10
0x14001d22b  mov     r8d, [rax+58h]
0x14001d22f  test    r8d, r8d
0x14001d232  jz      short loc_14001D29C
0x14001d234  cmp     r14d, r8d
0x14001d237  jbe     short loc_14001D29C
0x14001d239  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d240  lea     rsi, WPP_GLOBAL_Control
0x14001d247  cmp     rcx, rsi
0x14001d24a  jz      short loc_14001D275
0x14001d24c  test    byte ptr [rcx+1Ch], 4
0x14001d250  jz      short loc_14001D275
0x14001d252  cmp     byte ptr [rcx+19h], 2
0x14001d256  jb      short loc_14001D275
0x14001d258  mov     rcx, [rcx+10h]
0x14001d25c  mov     edx, 0D7h
0x14001d261  mov     [rsp+570h+var_550], r8d
0x14001d266  mov     r9d, r14d
0x14001d269  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001d270  call    WPP_SF_dd
0x14001d275  mov     rcx, rdi; void *
0x14001d278  call    ?FindClientAPIVersion@@YAKPEAX@Z; FindClientAPIVersion(void *)
0x14001d27d  cmp     eax, 20000h
0x14001d282  sbb     ebx, ebx
0x14001d284  and     ebx, 0FFFFE4A0h
0x14001d28a  add     ebx, 1B65h
0x14001d290  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d297  jmp     loc_14001DE62
0x14001d29c  mov     r9d, r10d
0x14001d29f  test    r14d, r14d
0x14001d2a2  jz      short loc_14001D2BD
0x14001d2a4  mov     eax, r9d
0x14001d2a7  imul    rcx, rax, 88h
0x14001d2ae  cmp     [rcx+rsi+10h], r10
0x14001d2b3  jz      short loc_14001D316
0x14001d2b5  inc     r9d
0x14001d2b8  cmp     r9d, r14d
0x14001d2bb  jb      short loc_14001D2A4
0x14001d2bd  cmp     [rdx+2Ch], r10d
0x14001d2c1  jnz     loc_14001DE22
0x14001d2c7  mov     eax, 0FFFF1234h
0x14001d2cc  cmp     [rdx+30h], rax
0x14001d2d0  jz      loc_14001DE22
0x14001d2d6  mov     r9d, [rdx+28h]
0x14001d2da  mov     ecx, r9d
0x14001d2dd  test    r9d, r9d
0x14001d2e0  jz      loc_14001D369
0x14001d2e6  sub     ecx, 1
0x14001d2e9  jz      short loc_14001D362
0x14001d2eb  cmp     ecx, 1
0x14001d2ee  jz      short loc_14001D35B
0x14001d2f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d2f7  lea     rsi, WPP_GLOBAL_Control
0x14001d2fe  cmp     rcx, rsi
0x14001d301  jz      short loc_14001D351
0x14001d303  test    byte ptr [rcx+1Ch], 4
0x14001d307  jz      short loc_14001D351
0x14001d309  cmp     byte ptr [rcx+19h], 2
0x14001d30d  jb      short loc_14001D351
0x14001d30f  mov     edx, 0DAh
0x14001d314  jmp     short loc_14001D33A
0x14001d316  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d31d  lea     rsi, WPP_GLOBAL_Control
0x14001d324  cmp     rcx, rsi
0x14001d327  jz      short loc_14001D351
0x14001d329  test    byte ptr [rcx+1Ch], 4
0x14001d32d  jz      short loc_14001D351
0x14001d32f  cmp     byte ptr [rcx+19h], 2
0x14001d333  jb      short loc_14001D351
0x14001d335  mov     edx, 0D8h
0x14001d33a  mov     rcx, [rcx+10h]
0x14001d33e  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001d345  call    WPP_SF_d
0x14001d34a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d351  mov     ebx, 57h ; 'W'
0x14001d356  jmp     loc_14001DE62
0x14001d35b  mov     ecx, 4
0x14001d360  jmp     short loc_14001D36E
0x14001d362  mov     ecx, 2
0x14001d367  jmp     short loc_14001D36E
0x14001d369  mov     ecx, 1; unsigned int
0x14001d36e  mov     r9d, 1; int
0x14001d374  lea     rdx, [rsp+570h+var_508]; int *
0x14001d379  xor     r8d, r8d; unsigned int *
0x14001d37c  call    ?FaxSvcAccessCheck@@YAKKPEAHPEAKH@Z; FaxSvcAccessCheck(ulong,int *,ulong *,int)
0x14001d381  mov     ebx, eax
0x14001d383  test    eax, eax
0x14001d385  jz      short loc_14001D3CF
0x14001d387  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d38e  lea     rsi, WPP_GLOBAL_Control
0x14001d395  cmp     rcx, rsi
0x14001d398  jz      loc_14001DE62
0x14001d39e  test    byte ptr [rcx+1Ch], 4
0x14001d3a2  jz      loc_14001DE62
0x14001d3a8  cmp     byte ptr [rcx+19h], 2
0x14001d3ac  jb      loc_14001DE62
0x14001d3b2  mov     edx, 0DBh
0x14001d3b7  xor     r9d, r9d
0x14001d3ba  mov     rcx, [rcx+10h]
0x14001d3be  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001d3c5  call    WPP_SF_d
0x14001d3ca  jmp     loc_14001D290
0x14001d3cf  cmp     [rsp+570h+var_508], 0
0x14001d3d4  jnz     short loc_14001D41B
0x14001d3d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d3dd  lea     rsi, WPP_GLOBAL_Control
0x14001d3e4  cmp     rcx, rsi
0x14001d3e7  jz      short loc_14001D411
0x14001d3e9  test    byte ptr [rcx+1Ch], 4
0x14001d3ed  jz      short loc_14001D411
0x14001d3ef  cmp     byte ptr [rcx+19h], 2
0x14001d3f3  jb      short loc_14001D411
0x14001d3f5  mov     rcx, [rcx+10h]
0x14001d3f9  lea     r8, WPP_bf13a1f9149c312b3fa8c47129651a46_Traceguids
0x14001d400  mov     edx, 0DCh
0x14001d405  call    WPP_SF_
0x14001d40a  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d411  mov     ebx, 5
0x14001d416  jmp     loc_14001DE62
0x14001d41b  mov     r9, [rsp+570h+var_500]
0x14001d420  mov     r9d, [r9+18h]
0x14001d424  test    r9d, 0FFFFFFE2h
0x14001d42b  jz      short loc_14001D462
0x14001d42d  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d434  lea     rsi, WPP_GLOBAL_Control
0x14001d43b  cmp     rcx, rsi
0x14001d43e  jz      loc_14001D351
0x14001d444  test    byte ptr [rcx+1Ch], 4
  ... truncated ...
```
