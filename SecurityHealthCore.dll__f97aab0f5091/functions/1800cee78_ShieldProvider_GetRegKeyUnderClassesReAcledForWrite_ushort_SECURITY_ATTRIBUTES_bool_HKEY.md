# ShieldProvider::GetRegKeyUnderClassesReAcledForWrite(ushort *,_SECURITY_ATTRIBUTES *,bool,HKEY__ * *)

- ea: `0x1800cee78`
- end: `0x1800cf6f2`
- name: `?GetRegKeyUnderClassesReAcledForWrite@ShieldProvider@@YAJPEAGPEAU_SECURITY_ATTRIBUTES@@_NPEAPEAUHKEY__@@@Z`
- size: `2170`
- prototype: `__int64 __fastcall(ShieldProvider *this, unsigned __int16 *, struct _SECURITY_ATTRIBUTES *, HKEY *)`
- caller_count: `3`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000d8c8`
- `0x18000db9c`
- `0x18000dddc`

## callees

- `0x180004710`
- `0x180004ae0`
- `0x180004bd0`
- `0x18000d7fc`
- `0x18000f058`
- `0x18000f688`
- `0x1800cee78`
- `0x1800db5b8`
- `0x1800dc038`
- `0x1800dd3e8`
- `0x1800dde6c`
- `0x1800ded2c`
- `0x1800df240`
- `0x1800df3f4`
- `0x1800df990`
- `0x1800dfa1c`
- `0x1800e7010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800cf159`
- `KERNEL32!GetLastError` at `0x1800cf1ba`
- `KERNEL32!GetLastError` at `0x1800cf159`
- `KERNEL32!GetLastError` at `0x1800cf1ba`
- `KERNEL32!CloseHandle` at `0x1800cf128`
- `KERNEL32!CloseHandle` at `0x1800cf209`
- `KERNEL32!CloseHandle` at `0x1800cf2a5`
- `KERNEL32!CloseHandle` at `0x1800cf622`
- `KERNEL32!CloseHandle` at `0x1800cf686`
- `KERNEL32!CloseHandle` at `0x1800cf128`
- `KERNEL32!CloseHandle` at `0x1800cf209`
- `KERNEL32!CloseHandle` at `0x1800cf2a5`
- `KERNEL32!CloseHandle` at `0x1800cf622`
- `KERNEL32!CloseHandle` at `0x1800cf686`
- `KERNEL32!GetCurrentProcess` at `0x1800cf0d0`
- `KERNEL32!GetCurrentProcess` at `0x1800cf0d0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cef47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cef56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf039`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf23c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf2d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf654`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf6c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cef47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cef56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf039`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf23c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf2d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf654`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cf6c3`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800cf1ac`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800cf1ac`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800cf149`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800cf149`

## string_xrefs

- `0x1800cf138`: `SeTakeOwnershipPrivilege`

## pseudocode

```c
__int64 __fastcall ShieldProvider::GetRegKeyUnderClassesReAcledForWrite(
        ShieldProvider *this,
        unsigned __int16 *a2,
        struct _SECURITY_ATTRIBUTES *a3,
        HKEY *a4)
{
  char v4; // si
  unsigned int v5; // ebx
  int Key; // eax
  unsigned int v8; // ebx
  HKEY v9; // rcx
  int v11; // eax
  const unsigned __int16 *v12; // r8
  const struct std::nothrow_t *v13; // rdx
  void *v14; // rbx
  int NamedSecurityInfo; // eax
  const unsigned __int16 *v16; // r8
  signed int v17; // edi
  const struct std::nothrow_t *v18; // rdx
  int v19; // eax
  void **CurrentProcess; // rax
  unsigned int v21; // r9d
  _QWORD *v22; // rcx
  __int64 v23; // rdx
  signed int LastError; // eax
  HANDLE v25; // rdi
  signed int v26; // eax
  unsigned int v27; // esi
  const struct std::nothrow_t *v28; // rdx
  void *v29; // rsi
  int v30; // eax
  const unsigned __int16 *v31; // r8
  int v32; // r15d
  const struct std::nothrow_t *v33; // rdx
  HKEY v34; // rcx
  int v35; // eax
  struct CommonUtil::IExplicitAccessControl **v36; // rdx
  unsigned int v37; // r8d
  _QWORD *v38; // rcx
  __int64 v39; // rdx
  void *v40; // r12
  __int64 v41; // r15
  _QWORD *v42; // rcx
  __int64 v43; // rdx
  void *v44; // rax
  int v45; // eax
  const struct std::nothrow_t *v46; // rdx
  const struct std::nothrow_t *v47; // rdx
  unsigned int PreviousState; // [rsp+20h] [rbp-79h]
  unsigned int PreviousStatea; // [rsp+20h] [rbp-79h]
  PTOKEN_PRIVILEGES PreviousStateb; // [rsp+20h] [rbp-79h]
  unsigned int PreviousStatec; // [rsp+20h] [rbp-79h]
  PTOKEN_PRIVILEGES PreviousStated; // [rsp+20h] [rbp-79h]
  unsigned int PreviousStatee; // [rsp+20h] [rbp-79h]
  struct _SECURITY_ATTRIBUTES *ReturnLength; // [rsp+28h] [rbp-71h]
  struct _ACL *v55; // [rsp+30h] [rbp-69h]
  struct _ACL *v56; // [rsp+30h] [rbp-69h]
  struct _ACL *v57; // [rsp+38h] [rbp-61h]
  struct _ACL *v58; // [rsp+38h] [rbp-61h]
  unsigned int v59; // [rsp+40h] [rbp-59h]
  unsigned int v60; // [rsp+48h] [rbp-51h]
  unsigned int v61; // [rsp+50h] [rbp-49h]
  unsigned int v62; // [rsp+58h] [rbp-41h]
  void *Block; // [rsp+60h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-31h] BYREF
  __int64 v65; // [rsp+70h] [rbp-29h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp-21h] BYREF
  char v67; // [rsp+80h] [rbp-19h]
  CommonUtil::CRefObject *v68; // [rsp+88h] [rbp-11h] BYREF
  HKEY v69; // [rsp+90h] [rbp-9h] BYREF
  __int64 (__fastcall *v70)(void *, CommonUtil::CRefObject **, __int64); // [rsp+98h] [rbp-1h]
  HKEY *v71; // [rsp+A0h] [rbp+7h]
  struct _TOKEN_PRIVILEGES NewState; // [rsp+A8h] [rbp+Fh] BYREF

  v67 = (char)a3;
  v4 = (char)a3;
  *a4 = 0;
  v71 = a4;
  v5 = (unsigned int)a2;
  v69 = 0;
  hKey = 0;
  if ( CommonUtil::UtilRegOpenKey(
         (CommonUtil *)&hKey,
         (HKEY *)0xFFFFFFFF80000000LL,
         (HKEY)this,
         (const unsigned __int16 *)0x20019,
         PreviousState) == -2147024894 )
  {
    Key = CommonUtil::UtilRegCreateKey(
            (CommonUtil *)&v69,
            (HKEY *)0xFFFFFFFF80000000LL,
            (HKEY)this,
            (const unsigned __int16 *)0x20006,
            v5,
            ReturnLength,
            (unsigned int)v55);
    v8 = Key;
    if ( Key < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_33a0f43f06d933957ab6919b163618ef_Traceguids,
          (unsigned int)Key);
      if ( hKey )
        RegCloseKey(hKey);
      v9 = v69;
LABEL_9:
      if ( v9 )
        RegCloseKey(v9);
      return v8;
    }
    goto LABEL_136;
  }
  Block = 0;
  v11 = CommonUtil::NewSprintfW(
          (CommonUtil *)&Block,
          (unsigned __int16 **)L"CLASSES_ROOT\\%s",
          (const unsigned __int16 *)this);
  v8 = v11;
  if ( v11 < 0 )
  {
    v13 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_33a0f43f06d933957ab6919b163618ef_Traceguids,
        (unsigned int)v11);
    if ( Block )
      operator delete(Block, v13);
    v9 = hKey;
    goto LABEL_9;
  }
  v14 = Block;
  v65 = 0;
  NamedSecurityInfo = CommonUtil::UtilGetNamedSecurityInfo(
                        (CommonUtil *)&v65,
                        (struct CommonUtil::ISecurityAttributes **)Block,
                        v12,
                        SE_FILE_OBJECT,
                        PreviousStatea);
  v17 = NamedSecurityInfo;
  if ( NamedSecurityInfo < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_33a0f43f06d933957ab6919b163618ef_Traceguids,
        (unsigned int)NamedSecurityInfo);
LABEL_23:
    CommonUtil::AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>::~AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>(&v65);
    if ( v14 )
      operator delete(v14, v18);
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v17;
  }
  Block = 0;
  if ( v4 )
    v19 = CommonUtil::UtilSidFromRid(
            (CommonUtil *)&Block,
            (void **)2,
            0x20u,
            0x220u,
            0,
            (const struct _SID_IDENTIFIER_AUTHORITY *)ReturnLength,
            (unsigned int)v55,
            (unsigned int)v57,
            v59,
            v60,
            v61,
            v62);
  else
    v19 = CommonUtil::UtilConvertStringSidToSid((CommonUtil *)&Block, L"S-1-5-18", v16);
  v17 = v19;
  if ( v19 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_33a0f43f06d933957ab6919b163618ef_Traceguids,
        (unsigned int)v19);
LABEL_35:
    if ( Block )
      operator delete(Block);
    goto LABEL_23;
  }
  hObject = 0;
  CurrentProcess = (void **)GetCurrentProcess();
  v17 = CommonUtil::UtilOpenProcessToken((CommonUtil *)&hObject, CurrentProcess, (void *)0x20, v21);
  if ( v17 < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v23 = 14;
LABEL_41:
      WPP_SF_d(v22[2], v23, WPP_33a0f43f06d933957ab6919b163618ef_Traceguids, (unsigned int)v17);
      goto LABEL_42;
    }
    goto LABEL_42;
  }
  NewState.Privileges[0].Luid = 0;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Attributes = 2;
  if ( !LookupPrivilegeValueW(0, L"SeTakeOwnershipPrivilege", &NewState.Privileges[0].Luid) )
  {
    LastError = GetLastError();
    v17 = LastError;
    if ( LastError > 0 )
      v17 = (unsigned __int16)LastError | 0x80070000;
    if ( v17 < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v23 = 15;
        goto LABEL_41;
      }
LABEL_42:
      if ( hObject )
        CloseHandle(hObject);
      goto LABEL_35;
    }
  }
  v25 = hObject;
  if ( !AdjustTokenPrivileges(hObject, 0, &NewState, 0, 0, 0) )
  {
    v26 = GetLastError();
    v27 = v26;
    if ( v26 > 0 )
      v27 = (unsigned __int16)v26 | 0x80070000;
    if ( (v27 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_33a0f43f06d933957ab6919b163618ef_Traceguids, v27);
      if ( v25 )
        CloseHandle(v25);
      if ( Block )
        operator delete(Block);
      CommonUtil::AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>::~AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>(&v65);
      if ( v14 )
        operator delete(v14, v28);
      if ( hKey )
        RegCloseKey(hKey);
      return v27;
    }
  }
  v29 = Block;
  v30 = CommonUtil::UtilSetNamedSecurityInfo(
          (CommonUtil *)v14,
          (const unsigned __int16 *)4,
          SE_FILE_OBJECT,
          (unsigned int)Block,
          PreviousStateb,
          0,
          v55,
          v57);
  v32 = v30;
  if ( v30 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_33a0f43f06d933957ab6919b163618ef_Traceguids,
        (unsigned int)v30);
    goto LABEL_71;
  }
  hObject = 0;
  v35 = CommonUtil::UtilGetNamedSecurityInfo(
          (CommonUtil *)&hObject,
          (struct CommonUtil::ISecurityAttributes **)v14,
          v31,
          SE_REGISTRY_KEY,
          PreviousStatec);
  v32 = v35;
  if ( v35 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_33a0f43f06d933957ab6919b163618ef_Traceguids,
        (unsigned int)v35);
    goto LABEL_85;
  }
  Block = 0;
  v32 = MpUtilsExports::NewExplicitAccessControlImpl((MpUtilsExports *)&Block, v36, v37);
  if ( v32 < 0 )
  {
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_91;
    v39 = 19;
    goto LABEL_90;
  }
  v40 = Block;
  LODWORD(v56) = 3;
  v32 = (*(__int64 (__fastcall **)(void *, __int64, __int64, __int64, _DWORD, _QWORD))(*(_QWORD *)Block + 24LL))(
          Block,
          18,
          0x10000000,
          2,
          0,
          0);
  if ( v32 < 0 )
  {
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_91;
    v39 = 20;
    goto LABEL_90;
  }
  LODWORD(PreviousStated) = 0;
  v32 = (*(__int64 (__fastcall **)(void *, const wchar_t *, __int64, __int64))(*(_QWORD *)v40 + 40LL))(
          v40,
          L"S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464",
          0x10000000,
          2);
  if ( v32 < 0 )
  {
    v38 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_91;
    v39 = 21;
    goto LABEL_90;
  }
  if ( !v67
    || (LODWORD(v56) = 3,
        LODWORD(PreviousStated) = 544,
        v32 = (*(__int64 (__fastcall **)(void *, __int64, __int64, __int64))(*(_QWORD *)v40 + 24LL))(
                v40,
                32,
                0x10000000,
                2),
        v32 >= 0) )
  {
    v68 = 0;
    v70 = *(__int64 (__fastcall **)(void *, CommonUtil::CRefObject **, __int64))(*(_QWORD *)v40 + 8LL);
    v41 = (*(__int64 (__fastcall **)(HANDLE))(*(_QWORD *)hObject + 24LL))(hObject);
    if ( v68 )
    {
      CommonUtil::CRefObject::Release(v68);
      v68 = 0;
    }
    v32 = v70(v40, &v68, v41);
    if ( v32 >= 0 )
    {
      v44 = (void *)(*(__int64 (__fastcall **)(CommonUtil::CRefObject *))(*(_QWORD *)v68 + 8LL))(v68);
      v32 = CommonUtil::UtilSetNamedSecurityInfo(
              (CommonUtil *)v14,
              (const unsigned __int16 *)4,
              SE_REGISTRY_KEY,
              0,
              PreviousStated,
              v44,
              v56,
              v58);
      if ( v32 >= 0 )
      {
        v45 = CommonUtil::UtilRegOpenKey(
                (CommonUtil *)&v69,
                (HKEY *)0xFFFFFFFF80000000LL,
                (HKEY)this,
                (const unsigned __int16 *)0x20006,
                PreviousStatee);
        v32 = v45;
        if ( v45 >= 0 )
        {
          CommonUtil::AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>::~AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>(&v68);
          CommonUtil::AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>::~AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>(&Block);
          CommonUtil::AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>::~AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>(&hObject);
          if ( v25 )
            CloseHandle(v25);
          if ( v29 )
            operator delete(v29);
          CommonUtil::AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>::~AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>(&v65);
          if ( v14 )
            operator delete(v14, v47);
LABEL_136:
          *v71 = v69;
          if ( hKey )
            RegCloseKey(hKey);
          return 0;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            25,
            WPP_33a0f43f06d933957ab6919b163618ef_Traceguids,
            (unsigned int)v45);
        CommonUtil::AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>::~AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>(&v68);
        CommonUtil::AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>::~AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>(&Block);
        CommonUtil::AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>::~AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>(&hObject);
        if ( v25 )
          CloseHandle(v25);
        if ( v29 )
          operator delete(v29);
        CommonUtil::AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>::~AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>(&v65);
        if ( v14 )
          operator delete(v14, v46);
        if ( hKey )
          RegCloseKey(hKey);
        v34 = v69;
        goto LABEL_78;
      }
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_112;
      v43 = 24;
    }
    else
    {
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_112;
      v43 = 23;
    }
    WPP_SF_d(v42[2], v43, WPP_33a0f43f06d933957ab6919b163618ef_Traceguids, (unsigned int)v32);
LABEL_112:
    CommonUtil::AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>::~AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>(&v68);
    goto LABEL_91;
  }
  v38 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    goto LABEL_91;
  v39 = 22;
LABEL_90:
  WPP_SF_d(v38[2], v39, WPP_33a0f43f06d933957ab6919b163618ef_Traceguids, (unsigned int)v32);
LABEL_91:
  CommonUtil::AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>::~AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>(&Block);
LABEL_85:
  CommonUtil::AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>::~AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>(&hObject);
LABEL_71:
  if ( v25 )
    CloseHandle(v25);
  if ( v29 )
    operator delete(v29);
  CommonUtil::AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>::~AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>(&v65);
  if ( v14 )
    operator delete(v14, v33);
  v34 = hKey;
LABEL_78:
  if ( v34 )
    RegCloseKey(v34);
  return (unsigned int)v32;
}

```

## disassembly

```asm
0x1800cee78  mov     [rsp-8+arg_10], rbx
0x1800cee7d  push    rbp
0x1800cee7e  push    rsi
0x1800cee7f  push    rdi
0x1800cee80  push    r12
0x1800cee82  push    r13
0x1800cee84  push    r14
0x1800cee86  push    r15
0x1800cee88  lea     rbp, [rsp-27h]
0x1800cee8d  sub     rsp, 0C0h
0x1800cee94  mov     rax, cs:__security_cookie
0x1800cee9b  xor     rax, rsp
0x1800cee9e  mov     [rbp+57h+var_38], rax
0x1800ceea2  xor     r12d, r12d
0x1800ceea5  mov     [rbp+57h+var_70], r8b
0x1800ceea9  mov     sil, r8b
0x1800ceeac  mov     [r9], r12
0x1800ceeaf  mov     [rbp+57h+var_50], r9
0x1800ceeb3  mov     rbx, rdx
0x1800ceeb6  mov     r13, rcx
0x1800ceeb9  mov     [rbp+57h+var_60], r12
0x1800ceebd  mov     r8, rcx; HKEY
0x1800ceec0  mov     [rbp+57h+hKey], r12
0x1800ceec4  mov     rdi, 0FFFFFFFF80000000h
0x1800ceecb  lea     rcx, [rbp+57h+hKey]; this
0x1800ceecf  mov     r9d, 20019h; unsigned __int16 *
0x1800ceed5  mov     rdx, rdi; HKEY *
0x1800ceed8  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,ushort const *,ulong)
0x1800ceedd  mov     r8, r13; unsigned __int16 *
0x1800ceee0  cmp     eax, 80070002h
0x1800ceee5  jnz     short loc_1800CEF63
0x1800ceee7  mov     r9d, 20006h; unsigned __int16 *
0x1800ceeed  mov     [rsp+0F0h+PreviousState], rbx; unsigned int
0x1800ceef2  mov     rdx, rdi; HKEY *
0x1800ceef5  lea     rcx, [rbp+57h+var_60]; this
0x1800ceef9  call    ?UtilRegCreateKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEBGKPEAU_SECURITY_ATTRIBUTES@@K@Z; CommonUtil::UtilRegCreateKey(HKEY__ * *,HKEY__ *,ushort const *,ulong,_SECURITY_ATTRIBUTES *,ulong)
0x1800ceefe  mov     ebx, eax
0x1800cef00  test    eax, eax
0x1800cef02  jns     loc_1800CF6AF
0x1800cef08  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cef0f  lea     rdx, WPP_GLOBAL_Control
0x1800cef16  cmp     rcx, rdx
0x1800cef19  jz      short loc_1800CEF3E
0x1800cef1b  lea     r14d, [r12+1]
0x1800cef20  test    [rcx+1Ch], r14b
0x1800cef24  jz      short loc_1800CEF3E
0x1800cef26  mov     rcx, [rcx+10h]
0x1800cef2a  lea     edx, [r12+0Ah]
0x1800cef2f  mov     r9d, eax
0x1800cef32  lea     r8, WPP_33a0f43f06d933957ab6919b163618ef_Traceguids
0x1800cef39  call    WPP_SF_d
0x1800cef3e  mov     rcx, [rbp+57h+hKey]; hKey
0x1800cef42  test    rcx, rcx
0x1800cef45  jz      short loc_1800CEF4D
0x1800cef47  call    cs:__imp_RegCloseKey
0x1800cef4d  mov     rcx, [rbp+57h+var_60]; hKey
0x1800cef51  test    rcx, rcx
0x1800cef54  jz      short loc_1800CEF5C
0x1800cef56  call    cs:__imp_RegCloseKey
0x1800cef5c  mov     eax, ebx
0x1800cef5e  jmp     loc_1800CF6CB
0x1800cef63  lea     rdx, aClassesRootS; "CLASSES_ROOT\\%s"
0x1800cef6a  mov     [rbp+57h+Block], r12
0x1800cef6e  lea     rcx, [rbp+57h+Block]; this
0x1800cef72  call    ?NewSprintfW@CommonUtil@@YAJPEAPEAGPEBGZZ; CommonUtil::NewSprintfW(ushort * *,ushort const *,...)
0x1800cef77  mov     ebx, eax
0x1800cef79  test    eax, eax
0x1800cef7b  jns     short loc_1800CEFC7
0x1800cef7d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cef84  lea     rdx, WPP_GLOBAL_Control
0x1800cef8b  cmp     rcx, rdx
0x1800cef8e  jz      short loc_1800CEFB3
0x1800cef90  mov     r14d, 1
0x1800cef96  test    [rcx+1Ch], r14b
0x1800cef9a  jz      short loc_1800CEFB3
0x1800cef9c  mov     rcx, [rcx+10h]
0x1800cefa0  lea     edx, [r14+0Ah]
0x1800cefa4  mov     r9d, eax
0x1800cefa7  lea     r8, WPP_33a0f43f06d933957ab6919b163618ef_Traceguids
0x1800cefae  call    WPP_SF_d
0x1800cefb3  mov     rcx, [rbp+57h+Block]; void *
0x1800cefb7  test    rcx, rcx
0x1800cefba  jz      short loc_1800CEFC1
0x1800cefbc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800cefc1  mov     rcx, [rbp+57h+hKey]
0x1800cefc5  jmp     short loc_1800CEF51
0x1800cefc7  mov     rbx, [rbp+57h+Block]
0x1800cefcb  lea     rcx, [rbp+57h+var_80]; this
0x1800cefcf  mov     r14d, 1
0x1800cefd5  mov     [rbp+57h+var_80], r12
0x1800cefd9  mov     r9d, r14d; enum _SE_OBJECT_TYPE
0x1800cefdc  mov     rdx, rbx; struct CommonUtil::ISecurityAttributes **
0x1800cefdf  call    ?UtilGetNamedSecurityInfo@CommonUtil@@YAJPEAPEAUISecurityAttributes@1@PEBGW4_SE_OBJECT_TYPE@@K@Z; CommonUtil::UtilGetNamedSecurityInfo(CommonUtil::ISecurityAttributes * *,ushort const *,_SE_OBJECT_TYPE,ulong)
0x1800cefe4  mov     edi, eax
0x1800cefe6  test    eax, eax
0x1800cefe8  jns     short loc_1800CF046
0x1800cefea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ceff1  lea     rdx, WPP_GLOBAL_Control
0x1800ceff8  cmp     rcx, rdx
0x1800ceffb  jz      short loc_1800CF01A
0x1800ceffd  test    [rcx+1Ch], r14b
0x1800cf001  jz      short loc_1800CF01A
0x1800cf003  mov     rcx, [rcx+10h]
0x1800cf007  lea     edx, [r14+0Bh]
0x1800cf00b  mov     r9d, eax
0x1800cf00e  lea     r8, WPP_33a0f43f06d933957ab6919b163618ef_Traceguids
0x1800cf015  call    WPP_SF_d
0x1800cf01a  lea     rcx, [rbp+57h+var_80]
0x1800cf01e  call    ??1?$AutoRef@VUpdateMonitorTask@UpdateMonitor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>::~AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>(void)
0x1800cf023  test    rbx, rbx
0x1800cf026  jz      short loc_1800CF030
0x1800cf028  mov     rcx, rbx; void *
0x1800cf02b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800cf030  mov     rcx, [rbp+57h+hKey]; hKey
0x1800cf034  test    rcx, rcx
0x1800cf037  jz      short loc_1800CF03F
0x1800cf039  call    cs:__imp_RegCloseKey
0x1800cf03f  mov     eax, edi
0x1800cf041  jmp     loc_1800CF6CB
0x1800cf046  mov     [rbp+57h+Block], r12
0x1800cf04a  mov     r15d, 2
0x1800cf050  lea     rcx, [rbp+57h+Block]; this
0x1800cf054  test    sil, sil
0x1800cf057  jz      short loc_1800CF072
0x1800cf059  mov     r9d, 220h; unsigned int
0x1800cf05f  mov     [rsp+0F0h+PreviousState], r12; unsigned int
0x1800cf064  lea     r8d, [r15+1Eh]; unsigned int
0x1800cf068  mov     edx, r15d; void **
0x1800cf06b  call    ?UtilSidFromRid@CommonUtil@@YAJPEAPEAXKKKPEBU_SID_IDENTIFIER_AUTHORITY@@KKKKKK@Z; CommonUtil::UtilSidFromRid(void * *,ulong,ulong,ulong,_SID_IDENTIFIER_AUTHORITY const *,ulong,ulong,ulong,ulong,ulong,ulong)
0x1800cf070  jmp     short loc_1800CF07E
0x1800cf072  lea     rdx, StringSid; "S-1-5-18"
0x1800cf079  call    ?UtilConvertStringSidToSid@CommonUtil@@YAJPEAPEAXPEBG@Z; CommonUtil::UtilConvertStringSidToSid(void * *,ushort const *)
0x1800cf07e  mov     edi, eax
0x1800cf080  test    eax, eax
0x1800cf082  jns     short loc_1800CF0CC
0x1800cf084  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf08b  lea     rdx, WPP_GLOBAL_Control
0x1800cf092  cmp     rcx, rdx
0x1800cf095  jz      short loc_1800CF0B5
0x1800cf097  test    [rcx+1Ch], r14b
0x1800cf09b  jz      short loc_1800CF0B5
0x1800cf09d  mov     rcx, [rcx+10h]
0x1800cf0a1  lea     r8, WPP_33a0f43f06d933957ab6919b163618ef_Traceguids
0x1800cf0a8  mov     edx, 0Dh
0x1800cf0ad  mov     r9d, eax
0x1800cf0b0  call    WPP_SF_d
0x1800cf0b5  mov     rcx, [rbp+57h+Block]; Block
0x1800cf0b9  test    rcx, rcx
0x1800cf0bc  jz      loc_1800CF01A
0x1800cf0c2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800cf0c7  jmp     loc_1800CF01A
0x1800cf0cc  mov     [rbp+57h+hObject], r12
0x1800cf0d0  call    cs:__imp_GetCurrentProcess
0x1800cf0d6  mov     r8d, 20h ; ' '; void *
0x1800cf0dc  lea     rcx, [rbp+57h+hObject]; this
0x1800cf0e0  mov     rdx, rax; void **
0x1800cf0e3  call    ?UtilOpenProcessToken@CommonUtil@@YAJPEAPEAXPEAXK@Z; CommonUtil::UtilOpenProcessToken(void * *,void *,ulong)
0x1800cf0e8  mov     edi, eax
0x1800cf0ea  test    eax, eax
0x1800cf0ec  jns     short loc_1800CF130
0x1800cf0ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf0f5  lea     rdx, WPP_GLOBAL_Control
0x1800cf0fc  cmp     rcx, rdx
0x1800cf0ff  jz      short loc_1800CF11F
0x1800cf101  test    [rcx+1Ch], r14b
0x1800cf105  jz      short loc_1800CF11F
0x1800cf107  mov     edx, 0Eh
0x1800cf10c  mov     rcx, [rcx+10h]
0x1800cf110  lea     r8, WPP_33a0f43f06d933957ab6919b163618ef_Traceguids
0x1800cf117  mov     r9d, edi
0x1800cf11a  call    WPP_SF_d
0x1800cf11f  mov     rcx, [rbp+57h+hObject]; hObject
0x1800cf123  test    rcx, rcx
0x1800cf126  jz      short loc_1800CF0B5
0x1800cf128  call    cs:__imp_CloseHandle
0x1800cf12e  jmp     short loc_1800CF0B5
0x1800cf130  lea     r8, [rbp+57h+NewState.Privileges]; lpLuid
0x1800cf134  mov     qword ptr [rbp+57h+NewState.Privileges.Luid.LowPart], r12
0x1800cf138  lea     rdx, aSetakeownershi; "SeTakeOwnershipPrivilege"
0x1800cf13f  mov     [rbp+57h+NewState.PrivilegeCount], r14d
0x1800cf143  xor     ecx, ecx; lpSystemName
0x1800cf145  mov     [rbp+57h+NewState.Privileges.Attributes], r15d
0x1800cf149  call    cs:__imp_LookupPrivilegeValueW
0x1800cf14f  mov     r15d, 80070000h
0x1800cf155  test    eax, eax
0x1800cf157  jnz     short loc_1800CF192
0x1800cf159  call    cs:__imp_GetLastError
0x1800cf15f  mov     edi, eax
0x1800cf161  test    eax, eax
0x1800cf163  jle     short loc_1800CF16B
0x1800cf165  movzx   edi, ax
0x1800cf168  or      edi, r15d
0x1800cf16b  test    edi, edi
0x1800cf16d  jns     short loc_1800CF192
0x1800cf16f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf176  lea     rdx, WPP_GLOBAL_Control
0x1800cf17d  cmp     rcx, rdx
0x1800cf180  jz      short loc_1800CF11F
0x1800cf182  test    [rcx+1Ch], r14b
0x1800cf186  jz      short loc_1800CF11F
0x1800cf188  mov     edx, 0Fh
0x1800cf18d  jmp     loc_1800CF10C
0x1800cf192  mov     rdi, [rbp+57h+hObject]
0x1800cf196  lea     r8, [rbp+57h+NewState]; NewState
0x1800cf19a  mov     rcx, rdi; TokenHandle
0x1800cf19d  mov     [rsp+0F0h+ReturnLength], r12; ReturnLength
0x1800cf1a2  xor     r9d, r9d; BufferLength
0x1800cf1a5  mov     [rsp+0F0h+PreviousState], r12; unsigned int
0x1800cf1aa  xor     edx, edx; DisableAllPrivileges
0x1800cf1ac  call    cs:__imp_AdjustTokenPrivileges
0x1800cf1b2  test    eax, eax
0x1800cf1b4  jnz     loc_1800CF249
0x1800cf1ba  call    cs:__imp_GetLastError
0x1800cf1c0  mov     esi, eax
0x1800cf1c2  test    eax, eax
0x1800cf1c4  jle     short loc_1800CF1CC
0x1800cf1c6  movzx   esi, ax
0x1800cf1c9  or      esi, r15d
0x1800cf1cc  test    esi, esi
0x1800cf1ce  jns     short loc_1800CF249
0x1800cf1d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf1d7  lea     rdx, WPP_GLOBAL_Control
0x1800cf1de  cmp     rcx, rdx
0x1800cf1e1  jz      short loc_1800CF201
0x1800cf1e3  test    [rcx+1Ch], r14b
0x1800cf1e7  jz      short loc_1800CF201
0x1800cf1e9  mov     rcx, [rcx+10h]
0x1800cf1ed  lea     r8, WPP_33a0f43f06d933957ab6919b163618ef_Traceguids
0x1800cf1f4  mov     edx, 10h
0x1800cf1f9  mov     r9d, esi
0x1800cf1fc  call    WPP_SF_d
0x1800cf201  test    rdi, rdi
0x1800cf204  jz      short loc_1800CF20F
0x1800cf206  mov     rcx, rdi; hObject
0x1800cf209  call    cs:__imp_CloseHandle
0x1800cf20f  mov     rcx, [rbp+57h+Block]; Block
0x1800cf213  test    rcx, rcx
0x1800cf216  jz      short loc_1800CF21D
0x1800cf218  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800cf21d  lea     rcx, [rbp+57h+var_80]
0x1800cf221  call    ??1?$AutoRef@VUpdateMonitorTask@UpdateMonitor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>::~AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>(void)
0x1800cf226  test    rbx, rbx
0x1800cf229  jz      short loc_1800CF233
0x1800cf22b  mov     rcx, rbx; void *
0x1800cf22e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800cf233  mov     rcx, [rbp+57h+hKey]; hKey
0x1800cf237  test    rcx, rcx
0x1800cf23a  jz      short loc_1800CF242
0x1800cf23c  call    cs:__imp_RegCloseKey
0x1800cf242  mov     eax, esi
0x1800cf244  jmp     loc_1800CF6CB
0x1800cf249  mov     rsi, [rbp+57h+Block]
0x1800cf24d  mov     r8d, r14d; enum _SE_OBJECT_TYPE
0x1800cf250  mov     r9, rsi; unsigned int
0x1800cf253  mov     [rsp+0F0h+ReturnLength], r12; void *
0x1800cf258  mov     edx, 4; unsigned __int16 *
0x1800cf25d  mov     rcx, rbx; this
0x1800cf260  call    ?UtilSetNamedSecurityInfo@CommonUtil@@YAJPEBGW4_SE_OBJECT_TYPE@@KPEAX2PEAU_ACL@@3@Z; CommonUtil::UtilSetNamedSecurityInfo(ushort const *,_SE_OBJECT_TYPE,ulong,void *,void *,_ACL *,_ACL *)
0x1800cf265  mov     r15d, eax
0x1800cf268  test    eax, eax
0x1800cf26a  jns     short loc_1800CF2E5
0x1800cf26c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cf273  lea     rdx, WPP_GLOBAL_Control
0x1800cf27a  cmp     rcx, rdx
0x1800cf27d  jz      short loc_1800CF29D
0x1800cf27f  test    [rcx+1Ch], r14b
0x1800cf283  jz      short loc_1800CF29D
0x1800cf285  mov     rcx, [rcx+10h]
0x1800cf289  lea     r8, WPP_33a0f43f06d933957ab6919b163618ef_Traceguids
0x1800cf290  mov     edx, 11h
0x1800cf295  mov     r9d, eax
0x1800cf298  call    WPP_SF_d
0x1800cf29d  test    rdi, rdi
0x1800cf2a0  jz      short loc_1800CF2AB
0x1800cf2a2  mov     rcx, rdi; hObject
0x1800cf2a5  call    cs:__imp_CloseHandle
0x1800cf2ab  test    rsi, rsi
0x1800cf2ae  jz      short loc_1800CF2B8
0x1800cf2b0  mov     rcx, rsi; Block
0x1800cf2b3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800cf2b8  lea     rcx, [rbp+57h+var_80]
0x1800cf2bc  call    ??1?$AutoRef@VUpdateMonitorTask@UpdateMonitor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>::~AutoRef<WSD::UpdateMonitor::UpdateMonitorTask>(void)
0x1800cf2c1  test    rbx, rbx
0x1800cf2c4  jz      short loc_1800CF2CE
0x1800cf2c6  mov     rcx, rbx; void *
0x1800cf2c9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800cf2ce  mov     rcx, [rbp+57h+hKey]; hKey
0x1800cf2d2  test    rcx, rcx
0x1800cf2d5  jz      short loc_1800CF2DD
0x1800cf2d7  call    cs:__imp_RegCloseKey
0x1800cf2dd  mov     eax, r15d
0x1800cf2e0  jmp     loc_1800CF6CB
0x1800cf2e5  mov     r9d, 4; enum _SE_OBJECT_TYPE
0x1800cf2eb  mov     [rbp+57h+hObject], r12
0x1800cf2ef  mov     rdx, rbx; struct CommonUtil::ISecurityAttributes **
0x1800cf2f2  lea     rcx, [rbp+57h+hObject]; this
0x1800cf2f6  call    ?UtilGetNamedSecurityInfo@CommonUtil@@YAJPEAPEAUISecurityAttributes@1@PEBGW4_SE_OBJECT_TYPE@@K@Z; CommonUtil::UtilGetNamedSecurityInfo(CommonUtil::ISecurityAttributes * *,ushort const *,_SE_OBJECT_TYPE,ulong)
0x1800cf2fb  mov     r15d, eax
0x1800cf2fe  test    eax, eax
0x1800cf300  jns     short loc_1800CF341
  ... truncated ...
```
