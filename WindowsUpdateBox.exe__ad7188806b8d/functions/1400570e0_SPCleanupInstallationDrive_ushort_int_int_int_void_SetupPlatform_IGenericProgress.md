# SPCleanupInstallationDrive(ushort,int,int,int,void *,SetupPlatform::IGenericProgress *)

- ea: `0x1400570e0`
- end: `0x1400579ff`
- name: `?SPCleanupInstallationDrive@@YAJGHHHPEAXPEAUIGenericProgress@SetupPlatform@@@Z`
- size: `2335`
- prototype: `__int64 __fastcall(unsigned __int16, int, int, int, void *, struct SetupPlatform::IGenericProgress *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x140007b94`

## callees

- `0x140021d5c`
- `0x140021dd4`
- `0x140024510`
- `0x140028afc`
- `0x140055c70`
- `0x140055d10`
- `0x1400570e0`
- `0x140057a08`
- `0x140058a24`
- `0x140059484`
- `0x14005aa68`
- `0x14005b208`
- `0x140080d70`
- `0x140082010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x14005777a`
- `ADVAPI32!RegQueryValueExW` at `0x14005777a`
- `ADVAPI32!RegOpenKeyExW` at `0x140057742`
- `ADVAPI32!RegOpenKeyExW` at `0x140057742`
- `ADVAPI32!RegCloseKey` at `0x14005778c`
- `ADVAPI32!RegCloseKey` at `0x14005778c`
- `KERNEL32!HeapFree` at `0x140057227`
- `KERNEL32!HeapFree` at `0x140057563`
- `KERNEL32!HeapFree` at `0x140057992`
- `KERNEL32!HeapFree` at `0x1400579c3`
- `KERNEL32!HeapFree` at `0x140057227`
- `KERNEL32!HeapFree` at `0x140057563`
- `KERNEL32!HeapFree` at `0x140057992`
- `KERNEL32!HeapFree` at `0x1400579c3`
- `KERNEL32!GetProcessHeap` at `0x140057213`
- `KERNEL32!GetProcessHeap` at `0x14005754f`
- `KERNEL32!GetProcessHeap` at `0x14005797e`
- `KERNEL32!GetProcessHeap` at `0x1400579af`
- `KERNEL32!GetProcessHeap` at `0x140057213`
- `KERNEL32!GetProcessHeap` at `0x14005754f`
- `KERNEL32!GetProcessHeap` at `0x14005797e`
- `KERNEL32!GetProcessHeap` at `0x1400579af`
- `KERNEL32!GetLastError` at `0x14005717f`
- `KERNEL32!GetLastError` at `0x14005723a`
- `KERNEL32!GetLastError` at `0x1400572e0`
- `KERNEL32!GetLastError` at `0x14005736c`
- `KERNEL32!GetLastError` at `0x1400573f3`
- `KERNEL32!GetLastError` at `0x1400574cd`
- `KERNEL32!GetLastError` at `0x14005759d`
- `KERNEL32!GetLastError` at `0x140057657`
- `KERNEL32!GetLastError` at `0x140057673`
- `KERNEL32!GetLastError` at `0x14005769d`
- `KERNEL32!GetLastError` at `0x1400577ae`
- `KERNEL32!GetLastError` at `0x140057825`
- `KERNEL32!GetLastError` at `0x140057842`
- `KERNEL32!GetLastError` at `0x14005785e`
- `KERNEL32!GetLastError` at `0x1400578d5`
- `KERNEL32!GetLastError` at `0x14005717f`
- `KERNEL32!GetLastError` at `0x14005723a`
- `KERNEL32!GetLastError` at `0x1400572e0`
- `KERNEL32!GetLastError` at `0x14005736c`
- `KERNEL32!GetLastError` at `0x1400573f3`
- `KERNEL32!GetLastError` at `0x1400574cd`
- `KERNEL32!GetLastError` at `0x14005759d`
- `KERNEL32!GetLastError` at `0x140057657`
- `KERNEL32!GetLastError` at `0x140057673`
- `KERNEL32!GetLastError` at `0x14005769d`
- `KERNEL32!GetLastError` at `0x1400577ae`
- `KERNEL32!GetLastError` at `0x140057825`
- `KERNEL32!GetLastError` at `0x140057842`
- `KERNEL32!GetLastError` at `0x14005785e`
- `KERNEL32!GetLastError` at `0x1400578d5`
- `KERNEL32!SetLastError` at `0x14005779a`
- `KERNEL32!SetLastError` at `0x1400578c9`
- `KERNEL32!SetLastError` at `0x14005779a`
- `KERNEL32!SetLastError` at `0x1400578c9`
- `WDSCORE!WdsSetupLogMessageW` at `0x1400571f2`
- `WDSCORE!WdsSetupLogMessageW` at `0x1400572b1`
- `WDSCORE!WdsSetupLogMessageW` at `0x140057355`
- `WDSCORE!WdsSetupLogMessageW` at `0x1400573cd`
- `WDSCORE!WdsSetupLogMessageW` at `0x140057454`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005752e`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005760f`
- `WDSCORE!WdsSetupLogMessageW` at `0x140057712`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005780c`
- `WDSCORE!WdsSetupLogMessageW` at `0x140057933`
- `WDSCORE!WdsSetupLogMessageW` at `0x1400571f2`
- `WDSCORE!WdsSetupLogMessageW` at `0x1400572b1`
- `WDSCORE!WdsSetupLogMessageW` at `0x140057355`
- `WDSCORE!WdsSetupLogMessageW` at `0x1400573cd`
- `WDSCORE!WdsSetupLogMessageW` at `0x140057454`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005752e`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005760f`
- `WDSCORE!WdsSetupLogMessageW` at `0x140057712`
- `WDSCORE!WdsSetupLogMessageW` at `0x14005780c`
- `WDSCORE!WdsSetupLogMessageW` at `0x140057933`
- `WDSCORE!CurrentIP` at `0x14005718d`
- `WDSCORE!CurrentIP` at `0x140057248`
- `WDSCORE!CurrentIP` at `0x1400572ee`
- `WDSCORE!CurrentIP` at `0x14005737a`
- `WDSCORE!CurrentIP` at `0x140057401`
- `WDSCORE!CurrentIP` at `0x1400574db`
- `WDSCORE!CurrentIP` at `0x1400575ab`
- `WDSCORE!CurrentIP` at `0x1400576ab`
- `WDSCORE!CurrentIP` at `0x1400577bc`
- `WDSCORE!CurrentIP` at `0x140057833`
- `WDSCORE!CurrentIP` at `0x1400578e3`
- `WDSCORE!CurrentIP` at `0x14005718d`
- `WDSCORE!CurrentIP` at `0x140057248`
- `WDSCORE!CurrentIP` at `0x1400572ee`
- `WDSCORE!CurrentIP` at `0x14005737a`
- `WDSCORE!CurrentIP` at `0x140057401`
- `WDSCORE!CurrentIP` at `0x1400574db`
- `WDSCORE!CurrentIP` at `0x1400575ab`
- `WDSCORE!CurrentIP` at `0x1400576ab`
- `WDSCORE!CurrentIP` at `0x1400577bc`
- `WDSCORE!CurrentIP` at `0x140057833`
- `WDSCORE!CurrentIP` at `0x1400578e3`
- `WIMGAPI!WIMUnmountImage` at `0x140057643`
- `WIMGAPI!WIMUnmountImage` at `0x140057643`

## string_xrefs

- `0x1400571c3`: `SPCleanupInstallationDrive`
- `0x14005727f`: `SPCleanupInstallationDrive`
- `0x14005719f`: `SPCleanupInstallationDrive: Failure while building path to Setup Platform working directory. Error: 0x%08X`
- `0x14005725b`: `SPCleanupInstallationDrive: Cleaning up %s`
- `0x140057314`: `SPCleanupInstallationDrive: Unable to unload mounted hives under %s. Error: 0x%08X`
- `0x14005738c`: `SPCleanupInstallationDrive: Unable to stop Setup Platform ETW session. Error: 0x%08X`
- `0x140057413`: `SPCleanupInstallationDrive: Unable to stop Setup Platform monitoring driver. Error: 0x%08X`
- `0x140057494`: `SafeOS.Mount`
- `0x1400574ed`: `SPCleanupInstallationDrive: Failure while building path to safe OS mount directory. Error: 0x%08X`
- `0x1400575ce`: `SPCleanupInstallationDrive: Unmounting directory %s`
- `0x1400576d1`: `SPCleanupInstallationDrive: Unable to unmount the directory %s. Error: 0x%08X`
- `0x1400577cb`: `SPCleanupInstallationDrive: Cleanup suspended data from registry keys`
- `0x14005788f`: `SPCleanupInstallationDrive: Failure to delete %s [%s]. Error: 0x%08X`
- `0x1400578f2`: `SPCleanupInstallationDrive: Not suspended data in registry keys, no need for cleanup`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall SPCleanupInstallationDrive(__int16 a1)
{
  const struct _LUTF8_STRING *Namespace; // rax
  int v3; // esi
  DWORD LastError; // edi
  __int64 v5; // rbx
  struct tagLOG_PARTIAL_MSG *v6; // rax
  void *v7; // rbx
  HANDLE ProcessHeap; // rax
  DWORD v9; // edi
  __int64 v10; // rbx
  struct tagLOG_PARTIAL_MSG *v11; // rax
  const unsigned __int16 *v12; // rax
  int v13; // esi
  DWORD v14; // edi
  __int64 v15; // rbx
  const char *v16; // rax
  struct tagLOG_PARTIAL_MSG *v17; // rax
  int v18; // esi
  DWORD v19; // edi
  __int64 v20; // rbx
  struct tagLOG_PARTIAL_MSG *v21; // rax
  int v22; // esi
  DWORD v23; // edi
  __int64 v24; // rbx
  struct tagLOG_PARTIAL_MSG *v25; // rax
  __int64 v26; // rbx
  const struct _LUTF8_STRING *v27; // rax
  DWORD v28; // edi
  __int64 v29; // rbx
  struct tagLOG_PARTIAL_MSG *v30; // rax
  void *v31; // rbx
  HANDLE v32; // rax
  unsigned __int16 *v33; // rax
  DWORD v34; // edi
  __int64 v35; // rbx
  const char *v36; // rax
  struct tagLOG_PARTIAL_MSG *v37; // rax
  __int64 v38; // rax
  signed int v39; // esi
  signed int v40; // eax
  bool v41; // sf
  signed int v42; // eax
  DWORD v43; // edi
  __int64 v44; // rbx
  const char *v45; // rax
  struct tagLOG_PARTIAL_MSG *v46; // rax
  LSTATUS Value; // ebx
  DWORD v48; // edi
  __int64 v49; // rbx
  struct tagLOG_PARTIAL_MSG *v50; // rax
  DWORD v51; // ebx
  __int64 v52; // rdi
  signed int v53; // eax
  bool v54; // sf
  signed int v55; // eax
  struct tagLOG_PARTIAL_MSG *v56; // rax
  DWORD v57; // edi
  __int64 v58; // rbx
  struct tagLOG_PARTIAL_MSG *v59; // rax
  const unsigned __int16 *v60; // rax
  int v61; // edx
  unsigned int v62; // edi
  void *v63; // rbx
  HANDLE v64; // rax
  void *v65; // rbx
  HANDLE v66; // rax
  void *v67; // [rsp+38h] [rbp-49h]
  struct SetupPlatform::IGenericProgress *v68; // [rsp+40h] [rbp-41h]
  void **v69; // [rsp+68h] [rbp-19h] BYREF
  LPVOID v70; // [rsp+70h] [rbp-11h]
  void **v71; // [rsp+78h] [rbp-9h] BYREF
  LPVOID lpMem; // [rsp+80h] [rbp-1h]
  HKEY hKey[2]; // [rsp+88h] [rbp+7h] BYREF
  __int64 v74; // [rsp+98h] [rbp+17h] BYREF

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  if ( (unsigned __int16)(a1 - 97) > 0x19u && (unsigned __int16)(a1 - 65) > 0x19u )
    return 2147942487LL;
  v74 = 0x5C003A003FLL;
  LOWORD(v74) = a1;
  lpMem = 0;
  v71 = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
  Namespace = CBasicNodeType::GetNamespace((CBasicNodeType *)&v71);
  v3 = BuildPathHr(&v74, L"$WINDOWS.~BT", Namespace);
  if ( v3 < 0 )
  {
    LastError = GetLastError();
    v5 = CurrentIP();
    v6 = ConstructPartialMsgW(
           0x2000000,
           "SPCleanupInstallationDrive: Failure while building path to Setup Platform working directory. Error: 0x%08X",
           v3);
    WdsSetupLogMessageW(
      v6,
      0,
      L"D",
      0,
      929,
      L"base\\ntsetup\\setupplatform\\lib\\static\\utilities.cpp",
      L"SPCleanupInstallationDrive",
      v5,
      LastError,
      0,
      0);
    v71 = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
LABEL_6:
    v7 = lpMem;
    if ( lpMem )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v7);
    }
    return (unsigned int)v3;
  }
  v9 = GetLastError();
  v10 = CurrentIP();
  v11 = ConstructPartialMsgW(0x4000000, "SPCleanupInstallationDrive: Cleaning up %s", (const char *)&v74);
  WdsSetupLogMessageW(
    v11,
    0,
    L"D",
    0,
    933,
    L"base\\ntsetup\\setupplatform\\lib\\static\\utilities.cpp",
    L"SPCleanupInstallationDrive",
    v10,
    v9,
    0,
    0);
  v12 = (const unsigned __int16 *)((__int64 (__fastcall *)(void ***))v71[4])(&v71);
  v13 = pUnloadMountedHives(v12);
  if ( v13 < 0 )
  {
    v14 = GetLastError();
    v15 = CurrentIP();
    v16 = (const char *)((__int64 (__fastcall *)(void ***))v71[4])(&v71);
    v17 = ConstructPartialMsgW(
            50331648,
            "SPCleanupInstallationDrive: Unable to unload mounted hives under %s. Error: 0x%08X",
            v16,
            v13);
    WdsSetupLogMessageW(
      v17,
      0,
      L"D",
      0,
      939,
      L"base\\ntsetup\\setupplatform\\lib\\static\\utilities.cpp",
      L"SPCleanupInstallationDrive",
      v15,
      v14,
      0,
      0);
  }
  v18 = pStopSetupPlatformETWSession();
  if ( v18 < 0 )
  {
    v19 = GetLastError();
    v20 = CurrentIP();
    v21 = ConstructPartialMsgW(
            50331648,
            "SPCleanupInstallationDrive: Unable to stop Setup Platform ETW session. Error: 0x%08X",
            v18);
    WdsSetupLogMessageW(
      v21,
      0,
      L"D",
      0,
      948,
      L"base\\ntsetup\\setupplatform\\lib\\static\\utilities.cpp",
      L"SPCleanupInstallationDrive",
      v20,
      v19,
      0,
      0);
  }
  v22 = WsmUnload();
  if ( v22 < 0 || (v22 = WsmUninstall(0), v22 < 0) )
  {
    v23 = GetLastError();
    v24 = CurrentIP();
    v25 = ConstructPartialMsgW(
            50331648,
            "SPCleanupInstallationDrive: Unable to stop Setup Platform monitoring driver. Error: 0x%08X",
            v22);
    WdsSetupLogMessageW(
      v25,
      0,
      L"D",
      0,
      957,
      L"base\\ntsetup\\setupplatform\\lib\\static\\utilities.cpp",
      L"SPCleanupInstallationDrive",
      v24,
      v23,
      0,
      0);
  }
  v70 = 0;
  v69 = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
  v26 = ((__int64 (__fastcall *)(void ***))v71[4])(&v71);
  v27 = CBasicNodeType::GetNamespace((CBasicNodeType *)&v69);
  v3 = BuildPathMultiHr(v27, 4, v26, L"Sources", L"SafeOS", L"SafeOS.Mount");
  if ( v3 < 0 )
  {
    v28 = GetLastError();
    v29 = CurrentIP();
    v30 = ConstructPartialMsgW(
            0x2000000,
            "SPCleanupInstallationDrive: Failure while building path to safe OS mount directory. Error: 0x%08X",
            v3);
    WdsSetupLogMessageW(
      v30,
      0,
      L"D",
      0,
      975,
      L"base\\ntsetup\\setupplatform\\lib\\static\\utilities.cpp",
      L"SPCleanupInstallationDrive",
      v29,
      v28,
      0,
      0);
    v69 = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
    v31 = v70;
    if ( v70 )
    {
      v32 = GetProcessHeap();
      HeapFree(v32, 0, v31);
      v70 = 0;
    }
    v71 = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
    goto LABEL_6;
  }
  v33 = (unsigned __int16 *)((__int64 (__fastcall *)(void ***))v69[4])(&v69);
  if ( (unsigned int)DirectoryExists(v33) )
  {
    v34 = GetLastError();
    v35 = CurrentIP();
    v36 = (const char *)((__int64 (__fastcall *)(void ***))v69[4])(&v69);
    v37 = ConstructPartialMsgW(0x4000000, "SPCleanupInstallationDrive: Unmounting directory %s", v36);
    WdsSetupLogMessageW(
      v37,
      0,
      L"D",
      0,
      981,
      L"base\\ntsetup\\setupplatform\\lib\\static\\utilities.cpp",
      L"SPCleanupInstallationDrive",
      v35,
      v34,
      0,
      0);
    v38 = ((__int64 (__fastcall *)(void ***))v69[4])(&v69);
    if ( !v38 )
    {
      v39 = -2147024809;
LABEL_31:
      v43 = GetLastError();
      v44 = CurrentIP();
      v45 = (const char *)((__int64 (__fastcall *)(void ***))v69[4])(&v69);
      v46 = ConstructPartialMsgW(
              50331648,
              "SPCleanupInstallationDrive: Unable to unmount the directory %s. Error: 0x%08X",
              v45,
              v39);
      WdsSetupLogMessageW(
        v46,
        0,
        L"D",
        0,
        985,
        L"base\\ntsetup\\setupplatform\\lib\\static\\utilities.cpp",
        L"SPCleanupInstallationDrive",
        v44,
        v43,
        0,
        0);
      goto LABEL_32;
    }
    if ( !(unsigned int)WIMUnmountImage(v38, 0, 0, 0) )
    {
      v40 = GetLastError();
      v41 = v40 < 0;
      if ( v40 > 0 )
        v41 = 1;
      if ( v41 )
      {
        v42 = GetLastError();
        v39 = v42;
        if ( v42 > 0 )
          v39 = (unsigned __int16)v42 | 0x80070000;
      }
      else
      {
        v39 = -2147467259;
      }
      if ( v39 < 0 )
        goto LABEL_31;
    }
  }
LABEL_32:
  hKey[0] = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup\\SetupPlatform", 0, 0x20019u, hKey) || !hKey[0] )
  {
    SetLastError(0);
  }
  else
  {
    Value = RegQueryValueExW(hKey[0], L"SuspendedData", 0, 0, 0, 0);
    RegCloseKey(hKey[0]);
    SetLastError(0);
    if ( !Value )
    {
      v48 = GetLastError();
      v49 = CurrentIP();
      v50 = ConstructPartialMsgW(0x4000000, "SPCleanupInstallationDrive: Cleanup suspended data from registry keys");
      WdsSetupLogMessageW(
        v50,
        0,
        L"D",
        0,
        1001,
        L"base\\ntsetup\\setupplatform\\lib\\static\\utilities.cpp",
        L"SPCleanupInstallationDrive",
        v49,
        v48,
        0,
        0);
      if ( !(unsigned int)RegDelete() )
      {
        v51 = GetLastError();
        v52 = CurrentIP();
        v53 = GetLastError();
        v54 = v53 < 0;
        if ( v53 > 0 )
          v54 = 1;
        if ( v54 )
        {
          v55 = GetLastError();
          if ( v55 > 0 )
            v55 = (unsigned __int16)v55 | 0x80070000;
        }
        else
        {
          v55 = -2147467259;
        }
        v56 = ConstructPartialMsgW(
                50331648,
                "SPCleanupInstallationDrive: Failure to delete %s [%s]. Error: 0x%08X",
                (const char *)L"SYSTEM\\Setup\\SetupPlatform",
                (const char *)L"SuspendedData",
                v55);
        WdsSetupLogMessageW(
          v56,
          0,
          L"D",
          0,
          1007,
          L"base\\ntsetup\\setupplatform\\lib\\static\\utilities.cpp",
          L"SPCleanupInstallationDrive",
          v52,
          v51,
          0,
          0);
      }
      goto LABEL_45;
    }
  }
  v57 = GetLastError();
  v58 = CurrentIP();
  v59 = ConstructPartialMsgW(
          0x4000000,
          "SPCleanupInstallationDrive: Not suspended data in registry keys, no need for cleanup");
  WdsSetupLogMessageW(
    v59,
    0,
    L"D",
    0,
    1012,
    L"base\\ntsetup\\setupplatform\\lib\\static\\utilities.cpp",
    L"SPCleanupInstallationDrive",
    v58,
    v57,
    0,
    0);
LABEL_45:
  v60 = (const unsigned __int16 *)((__int64 (__fastcall *)(void ***))v71[4])(&v71);
  v62 = SPExecuteCleanup(v60, v61, 0, 0, 0, 0, v67, v68);
  v69 = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
  v63 = v70;
  if ( v70 )
  {
    v64 = GetProcessHeap();
    HeapFree(v64, 0, v63);
    v70 = 0;
  }
  v71 = &RAII::CAutoWdsLibFree<unsigned short *>::`vftable';
  v65 = lpMem;
  if ( lpMem )
  {
    v66 = GetProcessHeap();
    HeapFree(v66, 0, v65);
  }
  return v62;
}

```

## disassembly

```asm
0x1400570e0  mov     rax, rsp
0x1400570e3  push    rbp
0x1400570e4  push    r12
0x1400570e6  push    r13
0x1400570e8  push    r14
0x1400570ea  push    r15
0x1400570ec  lea     rbp, [rax-4Fh]
0x1400570f0  sub     rsp, 0A0h
0x1400570f7  mov     [rbp+47h+var_38], 0FFFFFFFFFFFFFFFEh
0x1400570ff  mov     [rax+8], rbx
0x140057103  mov     [rax+10h], rsi
0x140057107  mov     [rax+18h], rdi
0x14005710b  mov     rax, cs:__security_cookie
0x140057112  xor     rax, rsp
0x140057115  mov     [rbp+47h+var_28], rax
0x140057119  lea     eax, [rcx-61h]
0x14005711c  cmp     ax, 19h
0x140057120  jbe     short loc_140057135
0x140057122  lea     eax, [rcx-41h]
0x140057125  cmp     ax, 19h
0x140057129  jbe     short loc_140057135
0x14005712b  mov     eax, 80070057h
0x140057130  jmp     loc_1400579D1
0x140057135  mov     rax, 5C003A003Fh
0x14005713f  mov     [rbp+47h+var_30], rax
0x140057143  mov     word ptr [rbp+47h+var_30], cx
0x140057147  xor     r13d, r13d
0x14005714a  mov     [rbp+47h+lpMem], r13
0x14005714e  lea     rax, ??_7?$CAutoWdsLibFree@PEAG@RAII@@6B@; const RAII::CAutoWdsLibFree<ushort *>::`vftable'
0x140057155  mov     [rbp+47h+var_50], rax
0x140057159  lea     rcx, [rbp+47h+var_50]; this
0x14005715d  call    ?GetNamespace@CBasicNodeType@@UEBAPEBU_LUTF8_STRING@@XZ; CBasicNodeType::GetNamespace(void)
0x140057162  mov     r8, rax
0x140057165  lea     rdx, aWindowsBt_0; "$WINDOWS.~BT"
0x14005716c  lea     rcx, [rbp+47h+var_30]
0x140057170  call    BuildPathHr
0x140057175  mov     esi, eax
0x140057177  test    eax, eax
0x140057179  jns     loc_14005723A
0x14005717f  call    cs:__imp_GetLastError
0x140057186  nop     dword ptr [rax+rax+00h]
0x14005718b  mov     edi, eax
0x14005718d  call    cs:__imp_CurrentIP
0x140057194  nop     dword ptr [rax+rax+00h]
0x140057199  mov     rbx, rax
0x14005719c  mov     r8d, esi
0x14005719f  lea     rdx, aSpcleanupinsta_6; "SPCleanupInstallationDrive: Failure whi"...
0x1400571a6  mov     ecx, 2000000h; unsigned int
0x1400571ab  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1400571b0  mov     [rsp+0C0h+var_70], r13d
0x1400571b5  mov     qword ptr [rsp+0C0h+var_78], r13
0x1400571ba  mov     dword ptr [rsp+0C0h+var_80], edi
0x1400571be  mov     [rsp+0C0h+var_88], rbx
0x1400571c3  lea     r15, aSpcleanupinsta_5; "SPCleanupInstallationDrive"
0x1400571ca  mov     [rsp+0C0h+var_90], r15
0x1400571cf  lea     r12, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\lib\\stat"...
0x1400571d6  mov     [rsp+0C0h+lpcbData], r12
0x1400571db  mov     dword ptr [rsp+0C0h+phkResult], 3A1h
0x1400571e3  xor     r9d, r9d
0x1400571e6  lea     r8, aD; "D"
0x1400571ed  xor     edx, edx
0x1400571ef  mov     rcx, rax
0x1400571f2  call    cs:__imp_WdsSetupLogMessageW
0x1400571f9  nop     dword ptr [rax+rax+00h]
0x1400571fe  nop
0x1400571ff  lea     rax, ??_7?$CAutoWdsLibFree@PEAG@RAII@@6B@; const RAII::CAutoWdsLibFree<ushort *>::`vftable'
0x140057206  mov     [rbp+47h+var_50], rax
0x14005720a  mov     rbx, [rbp+47h+lpMem]
0x14005720e  test    rbx, rbx
0x140057211  jz      short loc_140057233
0x140057213  call    cs:__imp_GetProcessHeap
0x14005721a  nop     dword ptr [rax+rax+00h]
0x14005721f  mov     r8, rbx; lpMem
0x140057222  xor     edx, edx; dwFlags
0x140057224  mov     rcx, rax; hHeap
0x140057227  call    cs:__imp_HeapFree
0x14005722e  nop     dword ptr [rax+rax+00h]
0x140057233  mov     eax, esi
0x140057235  jmp     loc_1400579D1
0x14005723a  call    cs:__imp_GetLastError
0x140057241  nop     dword ptr [rax+rax+00h]
0x140057246  mov     edi, eax
0x140057248  call    cs:__imp_CurrentIP
0x14005724f  nop     dword ptr [rax+rax+00h]
0x140057254  mov     rbx, rax
0x140057257  lea     r8, [rbp+47h+var_30]
0x14005725b  lea     rdx, aSpcleanupinsta_7; "SPCleanupInstallationDrive: Cleaning up"...
0x140057262  mov     ecx, 4000000h; unsigned int
0x140057267  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x14005726c  mov     [rsp+0C0h+var_70], r13d
0x140057271  mov     qword ptr [rsp+0C0h+var_78], r13
0x140057276  mov     dword ptr [rsp+0C0h+var_80], edi
0x14005727a  mov     [rsp+0C0h+var_88], rbx
0x14005727f  lea     r15, aSpcleanupinsta_5; "SPCleanupInstallationDrive"
0x140057286  mov     [rsp+0C0h+var_90], r15
0x14005728b  lea     r12, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\lib\\stat"...
0x140057292  mov     [rsp+0C0h+lpcbData], r12
0x140057297  mov     dword ptr [rsp+0C0h+phkResult], 3A5h
0x14005729f  xor     r9d, r9d
0x1400572a2  lea     r14, aD; "D"
0x1400572a9  mov     r8, r14
0x1400572ac  xor     edx, edx
0x1400572ae  mov     rcx, rax
0x1400572b1  call    cs:__imp_WdsSetupLogMessageW
0x1400572b8  nop     dword ptr [rax+rax+00h]
0x1400572bd  mov     rax, [rbp+47h+var_50]
0x1400572c1  lea     rcx, [rbp+47h+var_50]
0x1400572c5  mov     rax, [rax+20h]
0x1400572c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400572ce  mov     rcx, rax; unsigned __int16 *
0x1400572d1  call    ?pUnloadMountedHives@@YAJPEBG@Z; pUnloadMountedHives(ushort const *)
0x1400572d6  mov     esi, eax
0x1400572d8  test    eax, eax
0x1400572da  jns     loc_140057361
0x1400572e0  call    cs:__imp_GetLastError
0x1400572e7  nop     dword ptr [rax+rax+00h]
0x1400572ec  mov     edi, eax
0x1400572ee  call    cs:__imp_CurrentIP
0x1400572f5  nop     dword ptr [rax+rax+00h]
0x1400572fa  mov     rbx, rax
0x1400572fd  mov     rcx, [rbp+47h+var_50]
0x140057301  mov     rax, [rcx+20h]
0x140057305  lea     rcx, [rbp+47h+var_50]
0x140057309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005730e  mov     r8, rax
0x140057311  mov     r9d, esi
0x140057314  lea     rdx, aSpcleanupinsta_8; "SPCleanupInstallationDrive: Unable to u"...
0x14005731b  mov     ecx, 3000000h; unsigned int
0x140057320  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x140057325  mov     [rsp+0C0h+var_70], r13d
0x14005732a  mov     qword ptr [rsp+0C0h+var_78], r13
0x14005732f  mov     dword ptr [rsp+0C0h+var_80], edi
0x140057333  mov     [rsp+0C0h+var_88], rbx
0x140057338  mov     [rsp+0C0h+var_90], r15
0x14005733d  mov     [rsp+0C0h+lpcbData], r12
0x140057342  mov     dword ptr [rsp+0C0h+phkResult], 3ABh
0x14005734a  xor     r9d, r9d
0x14005734d  mov     r8, r14
0x140057350  xor     edx, edx
0x140057352  mov     rcx, rax
0x140057355  call    cs:__imp_WdsSetupLogMessageW
0x14005735c  nop     dword ptr [rax+rax+00h]
0x140057361  call    ?pStopSetupPlatformETWSession@@YAJXZ; pStopSetupPlatformETWSession(void)
0x140057366  mov     esi, eax
0x140057368  test    eax, eax
0x14005736a  jns     short loc_1400573D9
0x14005736c  call    cs:__imp_GetLastError
0x140057373  nop     dword ptr [rax+rax+00h]
0x140057378  mov     edi, eax
0x14005737a  call    cs:__imp_CurrentIP
0x140057381  nop     dword ptr [rax+rax+00h]
0x140057386  mov     rbx, rax
0x140057389  mov     r8d, esi
0x14005738c  lea     rdx, aSpcleanupinsta_9; "SPCleanupInstallationDrive: Unable to s"...
0x140057393  mov     ecx, 3000000h; unsigned int
0x140057398  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x14005739d  mov     [rsp+0C0h+var_70], r13d
0x1400573a2  mov     qword ptr [rsp+0C0h+var_78], r13
0x1400573a7  mov     dword ptr [rsp+0C0h+var_80], edi
0x1400573ab  mov     [rsp+0C0h+var_88], rbx
0x1400573b0  mov     [rsp+0C0h+var_90], r15
0x1400573b5  mov     [rsp+0C0h+lpcbData], r12
0x1400573ba  mov     dword ptr [rsp+0C0h+phkResult], 3B4h
0x1400573c2  xor     r9d, r9d
0x1400573c5  mov     r8, r14
0x1400573c8  xor     edx, edx
0x1400573ca  mov     rcx, rax
0x1400573cd  call    cs:__imp_WdsSetupLogMessageW
0x1400573d4  nop     dword ptr [rax+rax+00h]
0x1400573d9  call    ?WsmUnload@@YAJXZ; WsmUnload(void)
0x1400573de  mov     esi, eax
0x1400573e0  test    eax, eax
0x1400573e2  js      short loc_1400573F3
0x1400573e4  xor     edx, edx; int
0x1400573e6  xor     ecx, ecx; unsigned __int16 *
0x1400573e8  call    ?WsmUninstall@@YAJPEBGH@Z; WsmUninstall(ushort const *,int)
0x1400573ed  mov     esi, eax
0x1400573ef  test    eax, eax
0x1400573f1  jns     short loc_140057460
0x1400573f3  call    cs:__imp_GetLastError
0x1400573fa  nop     dword ptr [rax+rax+00h]
0x1400573ff  mov     edi, eax
0x140057401  call    cs:__imp_CurrentIP
0x140057408  nop     dword ptr [rax+rax+00h]
0x14005740d  mov     rbx, rax
0x140057410  mov     r8d, esi
0x140057413  lea     rdx, aSpcleanupinsta_1; "SPCleanupInstallationDrive: Unable to s"...
0x14005741a  mov     ecx, 3000000h; unsigned int
0x14005741f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x140057424  mov     [rsp+0C0h+var_70], r13d
0x140057429  mov     qword ptr [rsp+0C0h+var_78], r13
0x14005742e  mov     dword ptr [rsp+0C0h+var_80], edi
0x140057432  mov     [rsp+0C0h+var_88], rbx
0x140057437  mov     [rsp+0C0h+var_90], r15
0x14005743c  mov     [rsp+0C0h+lpcbData], r12
0x140057441  mov     dword ptr [rsp+0C0h+phkResult], 3BDh
0x140057449  xor     r9d, r9d
0x14005744c  mov     r8, r14
0x14005744f  xor     edx, edx
0x140057451  mov     rcx, rax
0x140057454  call    cs:__imp_WdsSetupLogMessageW
0x14005745b  nop     dword ptr [rax+rax+00h]
0x140057460  mov     [rbp+47h+var_58], r13
0x140057464  lea     rax, ??_7?$CAutoWdsLibFree@PEAG@RAII@@6B@; const RAII::CAutoWdsLibFree<ushort *>::`vftable'
0x14005746b  mov     [rbp+47h+var_60], rax
0x14005746f  mov     rax, [rbp+47h+var_50]
0x140057473  lea     rcx, [rbp+47h+var_50]
0x140057477  mov     rax, [rax+20h]
0x14005747b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057480  mov     rbx, rax
0x140057483  mov     rcx, [rbp+47h+var_60]
0x140057487  mov     rax, [rcx+8]
0x14005748b  lea     rcx, [rbp+47h+var_60]
0x14005748f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140057494  lea     rcx, aSafeosMount; "SafeOS.Mount"
0x14005749b  mov     [rsp+0C0h+lpcbData], rcx
0x1400574a0  lea     rcx, aSafeos; "SafeOS"
0x1400574a7  mov     [rsp+0C0h+phkResult], rcx
0x1400574ac  lea     r9, aSources; "Sources"
0x1400574b3  mov     r8, rbx
0x1400574b6  mov     edx, 4
0x1400574bb  mov     rcx, rax
0x1400574be  call    BuildPathMultiHr
0x1400574c3  mov     esi, eax
0x1400574c5  test    eax, eax
0x1400574c7  jns     loc_14005757C
0x1400574cd  call    cs:__imp_GetLastError
0x1400574d4  nop     dword ptr [rax+rax+00h]
0x1400574d9  mov     edi, eax
0x1400574db  call    cs:__imp_CurrentIP
0x1400574e2  nop     dword ptr [rax+rax+00h]
0x1400574e7  mov     rbx, rax
0x1400574ea  mov     r8d, esi
0x1400574ed  lea     rdx, aSpcleanupinsta_4; "SPCleanupInstallationDrive: Failure whi"...
0x1400574f4  mov     ecx, 2000000h; unsigned int
0x1400574f9  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1400574fe  mov     [rsp+0C0h+var_70], r13d
0x140057503  mov     qword ptr [rsp+0C0h+var_78], r13
0x140057508  mov     dword ptr [rsp+0C0h+var_80], edi
0x14005750c  mov     [rsp+0C0h+var_88], rbx
0x140057511  mov     [rsp+0C0h+var_90], r15
0x140057516  mov     [rsp+0C0h+lpcbData], r12
0x14005751b  mov     dword ptr [rsp+0C0h+phkResult], 3CFh
0x140057523  xor     r9d, r9d
0x140057526  mov     r8, r14
0x140057529  xor     edx, edx
0x14005752b  mov     rcx, rax
0x14005752e  call    cs:__imp_WdsSetupLogMessageW
0x140057535  nop     dword ptr [rax+rax+00h]
0x14005753a  nop
0x14005753b  lea     rdi, ??_7?$CAutoWdsLibFree@PEAG@RAII@@6B@; const RAII::CAutoWdsLibFree<ushort *>::`vftable'
0x140057542  mov     [rbp+47h+var_60], rdi
0x140057546  mov     rbx, [rbp+47h+var_58]
0x14005754a  test    rbx, rbx
0x14005754d  jz      short loc_140057573
0x14005754f  call    cs:__imp_GetProcessHeap
0x140057556  nop     dword ptr [rax+rax+00h]
0x14005755b  mov     r8, rbx; lpMem
0x14005755e  xor     edx, edx; dwFlags
0x140057560  mov     rcx, rax; hHeap
0x140057563  call    cs:__imp_HeapFree
0x14005756a  nop     dword ptr [rax+rax+00h]
0x14005756f  mov     [rbp+47h+var_58], r13
0x140057573  mov     [rbp+47h+var_50], rdi
0x140057577  jmp     loc_14005720A
0x14005757c  mov     rax, [rbp+47h+var_60]
0x140057580  lea     rcx, [rbp+47h+var_60]
0x140057584  mov     rax, [rax+20h]
0x140057588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005758d  mov     rcx, rax
0x140057590  call    DirectoryExists
0x140057595  test    eax, eax
0x140057597  jz      loc_14005771E
0x14005759d  call    cs:__imp_GetLastError
0x1400575a4  nop     dword ptr [rax+rax+00h]
0x1400575a9  mov     edi, eax
0x1400575ab  call    cs:__imp_CurrentIP
0x1400575b2  nop     dword ptr [rax+rax+00h]
0x1400575b7  mov     rbx, rax
0x1400575ba  mov     rcx, [rbp+47h+var_60]
0x1400575be  mov     rax, [rcx+20h]
0x1400575c2  lea     rcx, [rbp+47h+var_60]
0x1400575c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400575cb  mov     r8, rax
0x1400575ce  lea     rdx, aSpcleanupinsta; "SPCleanupInstallationDrive: Unmounting "...
0x1400575d5  mov     ecx, 4000000h; unsigned int
0x1400575da  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1400575df  mov     [rsp+0C0h+var_70], r13d
0x1400575e4  mov     qword ptr [rsp+0C0h+var_78], r13
0x1400575e9  mov     dword ptr [rsp+0C0h+var_80], edi
0x1400575ed  mov     [rsp+0C0h+var_88], rbx
0x1400575f2  mov     [rsp+0C0h+var_90], r15
0x1400575f7  mov     [rsp+0C0h+lpcbData], r12
0x1400575fc  mov     dword ptr [rsp+0C0h+phkResult], 3D5h
0x140057604  xor     r9d, r9d
0x140057607  mov     r8, r14
0x14005760a  xor     edx, edx
0x14005760c  mov     rcx, rax
0x14005760f  call    cs:__imp_WdsSetupLogMessageW
0x140057616  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
