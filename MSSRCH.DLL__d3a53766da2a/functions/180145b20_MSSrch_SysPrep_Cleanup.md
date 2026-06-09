# MSSrch_SysPrep_Cleanup

- ea: `0x180145b20`
- end: `0x1801461d5`
- name: `MSSrch_SysPrep_Cleanup`
- size: `1717`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x1800e7370`
- `0x180118c78`
- `0x180119140`
- `0x1801244c0`
- `0x180143ef0`
- `0x180143f8c`
- `0x1801446ac`
- `0x180144de8`
- `0x18014519c`
- `0x1801457b0`
- `0x180145b20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145bf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145c6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145cc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145d49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145dc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145e1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145ea9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145f07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145f8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180146051`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801460af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145bf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145c6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145cc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145d49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145dc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145e1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145ea9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145f07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145f8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180146051`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801460af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18014619a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801461ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18014619a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801461ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180146043`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180146043`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180146037`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180146037`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180145e90`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180145e90`
- `WDSCORE!CurrentIP` at `0x180145bfc`
- `WDSCORE!CurrentIP` at `0x180145c74`
- `WDSCORE!CurrentIP` at `0x180145cce`
- `WDSCORE!CurrentIP` at `0x180145d51`
- `WDSCORE!CurrentIP` at `0x180145dc9`
- `WDSCORE!CurrentIP` at `0x180145e26`
- `WDSCORE!CurrentIP` at `0x180145eb1`
- `WDSCORE!CurrentIP` at `0x180145f0f`
- `WDSCORE!CurrentIP` at `0x180145f96`
- `WDSCORE!CurrentIP` at `0x180146059`
- `WDSCORE!CurrentIP` at `0x1801460b7`
- `WDSCORE!CurrentIP` at `0x180145bfc`
- `WDSCORE!CurrentIP` at `0x180145c74`
- `WDSCORE!CurrentIP` at `0x180145cce`
- `WDSCORE!CurrentIP` at `0x180145d51`
- `WDSCORE!CurrentIP` at `0x180145dc9`
- `WDSCORE!CurrentIP` at `0x180145e26`
- `WDSCORE!CurrentIP` at `0x180145eb1`
- `WDSCORE!CurrentIP` at `0x180145f0f`
- `WDSCORE!CurrentIP` at `0x180145f96`
- `WDSCORE!CurrentIP` at `0x180146059`
- `WDSCORE!CurrentIP` at `0x1801460b7`
- `WDSCORE!WdsSetupLogMessageW` at `0x180145c5b`
- `WDSCORE!WdsSetupLogMessageW` at `0x180145d2d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180145db0`
- `WDSCORE!WdsSetupLogMessageW` at `0x180145e85`
- `WDSCORE!WdsSetupLogMessageW` at `0x180145f71`
- `WDSCORE!WdsSetupLogMessageW` at `0x18014611d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180145c5b`
- `WDSCORE!WdsSetupLogMessageW` at `0x180145d2d`
- `WDSCORE!WdsSetupLogMessageW` at `0x180145db0`
- `WDSCORE!WdsSetupLogMessageW` at `0x180145e85`
- `WDSCORE!WdsSetupLogMessageW` at `0x180145f71`
- `WDSCORE!WdsSetupLogMessageW` at `0x18014611d`

## string_xrefs

- `0x18014602c`: `SetupCompletedSuccessfully`
- `0x180145c44`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x180145cad`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x180145d16`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x180145d99`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x180145e05`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x180145e6e`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x180145eed`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x180145f4b`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x180145fcf`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x180146099`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x1801460f7`: `onecoreuap\base\appmodel\search\mssrch\dll\sysprep.cxx`
- `0x180145b8a`: `SeBackupPrivilege`
- `0x18014612b`: `SeBackupPrivilege`
- `0x180145bb8`: `SeDebugPrivilege`
- `0x18014615b`: `SeDebugPrivilege`
- `0x180145ba1`: `SeRestorePrivilege`
- `0x180146143`: `SeRestorePrivilege`
- `0x180145c02`: `MSS: MSSrch_SysPrep_Cleanup _DisableService returned successfully.`
- `0x180145cd4`: `MSS: MSSrch_SysPrep_Cleanup _CreateBlockingRegKey returned successfully.`
- `0x180145c7a`: `MSS:MSSrch_SysPrep_Cleanup _CreateBlockingRegKey failed.`
- `0x180145dd2`: `MSS: MSSrch_SysPrep_Cleanup _KillSearchService returned error 0x%x.`
- `0x180145d57`: `MSS: MSSrch_SysPrep_Cleanup _StopWithDependentServices returned timeout, try to kill it.`
- `0x180145eba`: `MSS:MSSrch_SysPrep_Cleanup 2nd _StopWithDependentServices failed with 0x%x`
- `0x180145e2c`: `MSS: MSSrch_SysPrep_Cleanup _KillSearchService succeeded.`
- `0x180145f18`: `MSS: MSSrch_SysPrep_Cleanup _StopWithDependentServices returned unhandled error 0x%x.`
- `0x1801460c1`: `MSS:MSSrch_SysPrep_Cleanup Error 0x%X occurred while opening reg key %ls.`

## pseudocode

```c
__int64 MSSrch_SysPrep_Cleanup()
{
  BOOL v0; // r14d
  BOOL v1; // r15d
  BOOL v2; // r12d
  unsigned int BlockingRegKey; // esi
  DWORD LastError; // edi
  __int64 v5; // rbx
  struct tagLOG_PARTIAL_MSG *v6; // rax
  DWORD v7; // edi
  __int64 v8; // rbx
  struct tagLOG_PARTIAL_MSG *v9; // rax
  DWORD v10; // edi
  __int64 v11; // rbx
  struct tagLOG_PARTIAL_MSG *v12; // rax
  DWORD v13; // edi
  __int64 v14; // rbx
  struct tagLOG_PARTIAL_MSG *v15; // rax
  DWORD v16; // edi
  __int64 v17; // rbx
  struct tagLOG_PARTIAL_MSG *v18; // rax
  DWORD v19; // edi
  __int64 v20; // rbx
  struct tagLOG_PARTIAL_MSG *v21; // rax
  DWORD v22; // edi
  __int64 v23; // rbx
  struct tagLOG_PARTIAL_MSG *v24; // rax
  DWORD v25; // edi
  __int64 v26; // rbx
  struct tagLOG_PARTIAL_MSG *v27; // rax
  DWORD v28; // edi
  __int64 v29; // rbx
  struct tagLOG_PARTIAL_MSG *v30; // rax
  DWORD v31; // edi
  __int64 v32; // rbx
  struct tagLOG_PARTIAL_MSG *v33; // rax
  DWORD v34; // edi
  __int64 v35; // rbx
  struct tagLOG_PARTIAL_MSG *v36; // rax
  unsigned int v37; // eax
  unsigned int v39; // [rsp+60h] [rbp-29h] BYREF
  BYTE Data[4]; // [rsp+64h] [rbp-25h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-21h] BYREF
  void **v42; // [rsp+70h] [rbp-19h] BYREF
  HANDLE hObject[2]; // [rsp+78h] [rbp-11h]
  wchar_t v44[8]; // [rsp+88h] [rbp-1h] BYREF

  v39 = -1;
  v42 = &UserToken::`vftable';
  wcscpy(v44, L"WSearch");
  *(_OWORD *)hObject = 0;
  if ( UserToken::OpenCurrentProcToken((UserToken *)&v42, 0x20u) )
  {
    v0 = UserToken::AdjustPrivilegeByName((UserToken *)&v42, L"SeBackupPrivilege", 2u);
    v1 = UserToken::AdjustPrivilegeByName((UserToken *)&v42, L"SeRestorePrivilege", 2u);
    v2 = UserToken::AdjustPrivilegeByName((UserToken *)&v42, L"SeDebugPrivilege", 2u);
  }
  else
  {
    v0 = 0;
    v2 = 0;
    v1 = 0;
  }
  BlockingRegKey = _EnableOrDisableService(v44, &v39, 1);
  if ( BlockingRegKey )
    goto LABEL_14;
  LastError = GetLastError();
  v5 = CurrentIP();
  v6 = ConstructPartialMsgW(0x4000000u, "MSS: MSSrch_SysPrep_Cleanup _DisableService returned successfully.");
  WdsSetupLogMessageW(
    v6,
    983040,
    L"D",
    0,
    877,
    L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
    L"MSSrch_SysPrep_Cleanup",
    v5,
    LastError,
    0,
    0);
  BlockingRegKey = CreateBlockingRegKey();
  if ( BlockingRegKey )
  {
    v7 = GetLastError();
    v8 = CurrentIP();
    v9 = ConstructPartialMsgW(0x2000000u, "MSS:MSSrch_SysPrep_Cleanup _CreateBlockingRegKey failed.");
    WdsSetupLogMessageW(
      v9,
      983040,
      L"D",
      0,
      879,
      L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
      L"MSSrch_SysPrep_Cleanup",
      v8,
      v7,
      0,
      0);
    goto LABEL_14;
  }
  v10 = GetLastError();
  v11 = CurrentIP();
  v12 = ConstructPartialMsgW(0x4000000u, "MSS: MSSrch_SysPrep_Cleanup _CreateBlockingRegKey returned successfully.");
  WdsSetupLogMessageW(
    v12,
    983040,
    L"D",
    0,
    882,
    L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
    L"MSSrch_SysPrep_Cleanup",
    v11,
    v10,
    0,
    0);
  BlockingRegKey = StopWithDependentServices(v44);
  if ( BlockingRegKey != 1053 )
  {
    if ( !BlockingRegKey )
      goto LABEL_15;
    v25 = GetLastError();
    v26 = CurrentIP();
    v27 = ConstructPartialMsgW(
            0x2000000u,
            "MSS: MSSrch_SysPrep_Cleanup _StopWithDependentServices returned unhandled error 0x%x.",
            BlockingRegKey);
    WdsSetupLogMessageW(
      v27,
      983040,
      L"D",
      0,
      918,
      L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
      L"MSSrch_SysPrep_Cleanup",
      v26,
      v25,
      0,
      0);
LABEL_14:
    if ( BlockingRegKey != 258 )
      goto LABEL_21;
    goto LABEL_15;
  }
  v13 = GetLastError();
  v14 = CurrentIP();
  v15 = ConstructPartialMsgW(
          0x4000000u,
          "MSS: MSSrch_SysPrep_Cleanup _StopWithDependentServices returned timeout, try to kill it.");
  WdsSetupLogMessageW(
    v15,
    983040,
    L"D",
    0,
    888,
    L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
    L"MSSrch_SysPrep_Cleanup",
    v14,
    v13,
    0,
    0);
  BlockingRegKey = KillSearchService();
  if ( BlockingRegKey )
  {
    v16 = GetLastError();
    v17 = CurrentIP();
    v18 = ConstructPartialMsgW(
            0x4000000u,
            "MSS: MSSrch_SysPrep_Cleanup _KillSearchService returned error 0x%x.",
            BlockingRegKey);
    WdsSetupLogMessageW(
      v18,
      983040,
      L"D",
      0,
      893,
      L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
      L"MSSrch_SysPrep_Cleanup",
      v17,
      v16,
      0,
      0);
    goto LABEL_14;
  }
  v19 = GetLastError();
  v20 = CurrentIP();
  v21 = ConstructPartialMsgW(0x4000000u, "MSS: MSSrch_SysPrep_Cleanup _KillSearchService succeeded.");
  WdsSetupLogMessageW(
    v21,
    983040,
    L"D",
    0,
    897,
    L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
    L"MSSrch_SysPrep_Cleanup",
    v20,
    v19,
    0,
    0);
  Sleep(0xBB8u);
  BlockingRegKey = StopWithDependentServices(v44);
  if ( BlockingRegKey )
  {
    v22 = GetLastError();
    v23 = CurrentIP();
    v24 = ConstructPartialMsgW(
            0x4000000u,
            "MSS:MSSrch_SysPrep_Cleanup 2nd _StopWithDependentServices failed with 0x%x",
            BlockingRegKey);
    WdsSetupLogMessageW(
      v24,
      983040,
      L"D",
      0,
      909,
      L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
      L"MSSrch_SysPrep_Cleanup",
      v23,
      v22,
      0,
      0);
    goto LABEL_14;
  }
LABEL_15:
  BlockingRegKey = Cleanup();
  if ( BlockingRegKey )
  {
    v28 = GetLastError();
    v29 = CurrentIP();
    v30 = ConstructPartialMsgW(0x2000000u, "MSS:MSSrch_SysPrep_Cleanup Cleanup failed.");
    WdsSetupLogMessageW(
      v30,
      983040,
      L"D",
      0,
      927,
      L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
      L"MSSrch_SysPrep_Cleanup",
      v29,
      v28,
      0,
      0);
  }
  else
  {
    hKey = 0;
    BlockingRegKey = OpenKeyForBackupRestore(-2147483646, L"SOFTWARE\\Microsoft\\Windows Search", 2, &hKey);
    if ( BlockingRegKey )
    {
      v34 = GetLastError();
      v35 = CurrentIP();
      v36 = ConstructPartialMsgW(
              0x2000000u,
              "MSS:MSSrch_SysPrep_Cleanup Error 0x%X occurred while opening reg key %ls.",
              BlockingRegKey,
              (const wchar_t *)hKey);
      WdsSetupLogMessageW(
        v36,
        983040,
        L"D",
        0,
        959,
        L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
        L"MSSrch_SysPrep_Cleanup",
        v35,
        v34,
        0,
        0);
    }
    else
    {
      *(_DWORD *)Data = 0;
      BlockingRegKey = RegSetValueExW(hKey, L"SetupCompletedSuccessfully", 0, 4u, Data, 4u);
      RegCloseKey(hKey);
      if ( BlockingRegKey )
      {
        v31 = GetLastError();
        v32 = CurrentIP();
        v33 = ConstructPartialMsgW(
                0x2000000u,
                "MSS:MSSrch_SysPrep_Cleanup Error 0x%X occurred while setting reg valuey %ls.",
                BlockingRegKey,
                (const wchar_t *)*(unsigned int *)Data);
        WdsSetupLogMessageW(
          v33,
          983040,
          L"D",
          0,
          951,
          L"onecoreuap\\base\\appmodel\\search\\mssrch\\dll\\sysprep.cxx",
          L"MSSrch_SysPrep_Cleanup",
          v32,
          v31,
          0,
          0);
      }
    }
  }
LABEL_21:
  if ( v0 )
    UserToken::AdjustPrivilegeByName((UserToken *)&v42, L"SeBackupPrivilege", 0);
  if ( v1 )
    UserToken::AdjustPrivilegeByName((UserToken *)&v42, L"SeRestorePrivilege", 0);
  if ( v2 )
    UserToken::AdjustPrivilegeByName((UserToken *)&v42, L"SeDebugPrivilege", 0);
  if ( v39 != -1 )
  {
    v37 = _EnableOrDisableService(v44, &v39, 0);
    if ( !BlockingRegKey )
      BlockingRegKey = v37;
  }
  v42 = &UserToken::`vftable';
  if ( hObject[0] )
    CloseHandle(hObject[0]);
  hObject[0] = 0;
  if ( hObject[1] )
    CloseHandle(hObject[1]);
  return BlockingRegKey;
}

```

## disassembly

```asm
0x180145b20  push    rbp
0x180145b22  push    rbx
0x180145b23  push    rsi
0x180145b24  push    rdi
0x180145b25  push    r12
0x180145b27  push    r13
0x180145b29  push    r14
0x180145b2b  push    r15
0x180145b2d  lea     rbp, [rsp-1Fh]
0x180145b32  sub     rsp, 0A8h
0x180145b39  mov     rax, cs:__security_cookie
0x180145b40  xor     rax, rsp
0x180145b43  mov     [rbp+57h+var_48], rax
0x180145b47  movups  xmm0, xmmword ptr cs:aWsearch; "WSearch"
0x180145b4e  lea     rax, ??_7UserToken@@6B@; const UserToken::`vftable'
0x180145b55  mov     [rbp+57h+var_80], 0FFFFFFFFh
0x180145b5c  mov     edx, 20h ; ' '; unsigned int
0x180145b61  mov     [rbp+57h+var_70], rax
0x180145b65  movdqu  xmmword ptr [rbp+57h+var_58], xmm0
0x180145b6a  lea     rcx, [rbp+57h+var_70]; this
0x180145b6e  xorps   xmm0, xmm0
0x180145b71  movdqu  xmmword ptr [rbp+57h+hObject], xmm0
0x180145b76  call    ?OpenCurrentProcToken@UserToken@@QEAA_NK@Z; UserToken::OpenCurrentProcToken(ulong)
0x180145b7b  xor     r13d, r13d
0x180145b7e  mov     ebx, 2
0x180145b83  test    al, al
0x180145b85  jz      short loc_180145BCE
0x180145b87  mov     r8d, ebx; unsigned int
0x180145b8a  lea     rdx, aSebackupprivil; "SeBackupPrivilege"
0x180145b91  lea     rcx, [rbp+57h+var_70]; this
0x180145b95  call    ?AdjustPrivilegeByName@UserToken@@QEAA_NPEB_WK@Z; UserToken::AdjustPrivilegeByName(wchar_t const *,ulong)
0x180145b9a  mov     r8d, ebx; unsigned int
0x180145b9d  movzx   r14d, al
0x180145ba1  lea     rdx, aSerestoreprivi; "SeRestorePrivilege"
0x180145ba8  lea     rcx, [rbp+57h+var_70]; this
0x180145bac  call    ?AdjustPrivilegeByName@UserToken@@QEAA_NPEB_WK@Z; UserToken::AdjustPrivilegeByName(wchar_t const *,ulong)
0x180145bb1  mov     r8d, ebx; unsigned int
0x180145bb4  movzx   r15d, al
0x180145bb8  lea     rdx, aSedebugprivile; "SeDebugPrivilege"
0x180145bbf  lea     rcx, [rbp+57h+var_70]; this
0x180145bc3  call    ?AdjustPrivilegeByName@UserToken@@QEAA_NPEB_WK@Z; UserToken::AdjustPrivilegeByName(wchar_t const *,ulong)
0x180145bc8  movzx   r12d, al
0x180145bcc  jmp     short loc_180145BD7
0x180145bce  mov     r14d, r13d
0x180145bd1  mov     r12d, r13d
0x180145bd4  mov     r15d, r13d
0x180145bd7  mov     r8d, 1; int
0x180145bdd  lea     rdx, [rbp+57h+var_80]; unsigned int *
0x180145be1  lea     rcx, [rbp+57h+var_58]; wchar_t *
0x180145be5  call    ?_EnableOrDisableService@@YAKPEB_WAEAKH@Z; _EnableOrDisableService(wchar_t const *,ulong &,int)
0x180145bea  mov     esi, eax
0x180145bec  test    eax, eax
0x180145bee  jnz     loc_180145F77
0x180145bf4  call    cs:__imp_GetLastError
0x180145bfa  mov     edi, eax
0x180145bfc  call    cs:__imp_CurrentIP
0x180145c02  lea     rdx, aMssMssrchSyspr_5; "MSS: MSSrch_SysPrep_Cleanup _DisableSer"...
0x180145c09  mov     ecx, 4000000h; unsigned int
0x180145c0e  mov     rbx, rax
0x180145c11  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180145c16  mov     [rsp+0E0h+var_90], r13d
0x180145c1b  lea     rcx, aMssrchSysprepC_0; "MSSrch_SysPrep_Cleanup"
0x180145c22  mov     [rsp+0E0h+var_98], r13
0x180145c27  lea     r8, aD_2; "D"
0x180145c2e  mov     [rsp+0E0h+var_A0], edi
0x180145c32  xor     r9d, r9d
0x180145c35  mov     [rsp+0E0h+var_A8], rbx
0x180145c3a  mov     edx, 0F0000h
0x180145c3f  mov     [rsp+0E0h+var_B0], rcx
0x180145c44  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180145c4b  mov     qword ptr [rsp+0E0h+cbData], rcx
0x180145c50  mov     rcx, rax
0x180145c53  mov     dword ptr [rsp+0E0h+lpData], 36Dh
0x180145c5b  call    cs:__imp_WdsSetupLogMessageW
0x180145c61  call    _CreateBlockingRegKey
0x180145c66  mov     esi, eax
0x180145c68  test    eax, eax
0x180145c6a  jz      short loc_180145CC6
0x180145c6c  call    cs:__imp_GetLastError
0x180145c72  mov     edi, eax
0x180145c74  call    cs:__imp_CurrentIP
0x180145c7a  lea     rdx, aMssMssrchSyspr; "MSS:MSSrch_SysPrep_Cleanup _CreateBlock"...
0x180145c81  mov     ecx, 2000000h; unsigned int
0x180145c86  mov     rbx, rax
0x180145c89  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180145c8e  mov     [rsp+0E0h+var_90], r13d
0x180145c93  lea     rcx, aMssrchSysprepC_0; "MSSrch_SysPrep_Cleanup"
0x180145c9a  mov     [rsp+0E0h+var_98], r13
0x180145c9f  mov     [rsp+0E0h+var_A0], edi
0x180145ca3  mov     [rsp+0E0h+var_A8], rbx
0x180145ca8  mov     [rsp+0E0h+var_B0], rcx
0x180145cad  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180145cb4  mov     qword ptr [rsp+0E0h+cbData], rcx
0x180145cb9  mov     dword ptr [rsp+0E0h+lpData], 36Fh
0x180145cc1  jmp     loc_180145F5F
0x180145cc6  call    cs:__imp_GetLastError
0x180145ccc  mov     edi, eax
0x180145cce  call    cs:__imp_CurrentIP
0x180145cd4  lea     rdx, aMssMssrchSyspr_9; "MSS: MSSrch_SysPrep_Cleanup _CreateBloc"...
0x180145cdb  mov     ecx, 4000000h; unsigned int
0x180145ce0  mov     rbx, rax
0x180145ce3  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180145ce8  mov     [rsp+0E0h+var_90], r13d
0x180145ced  lea     rcx, aMssrchSysprepC_0; "MSSrch_SysPrep_Cleanup"
0x180145cf4  mov     [rsp+0E0h+var_98], r13
0x180145cf9  lea     r8, aD_2; "D"
0x180145d00  mov     [rsp+0E0h+var_A0], edi
0x180145d04  xor     r9d, r9d
0x180145d07  mov     [rsp+0E0h+var_A8], rbx
0x180145d0c  mov     edx, 0F0000h
0x180145d11  mov     [rsp+0E0h+var_B0], rcx
0x180145d16  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180145d1d  mov     qword ptr [rsp+0E0h+cbData], rcx
0x180145d22  mov     rcx, rax
0x180145d25  mov     dword ptr [rsp+0E0h+lpData], 372h
0x180145d2d  call    cs:__imp_WdsSetupLogMessageW
0x180145d33  lea     rcx, [rbp+57h+var_58]
0x180145d37  call    _StopWithDependentServices
0x180145d3c  mov     esi, eax
0x180145d3e  cmp     eax, 41Dh
0x180145d43  jnz     loc_180145F03
0x180145d49  call    cs:__imp_GetLastError
0x180145d4f  mov     edi, eax
0x180145d51  call    cs:__imp_CurrentIP
0x180145d57  lea     rdx, aMssMssrchSyspr_6; "MSS: MSSrch_SysPrep_Cleanup _StopWithDe"...
0x180145d5e  mov     ecx, 4000000h; unsigned int
0x180145d63  mov     rbx, rax
0x180145d66  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180145d6b  mov     [rsp+0E0h+var_90], r13d
0x180145d70  lea     rcx, aMssrchSysprepC_0; "MSSrch_SysPrep_Cleanup"
0x180145d77  mov     [rsp+0E0h+var_98], r13
0x180145d7c  lea     r8, aD_2; "D"
0x180145d83  mov     [rsp+0E0h+var_A0], edi
0x180145d87  xor     r9d, r9d
0x180145d8a  mov     [rsp+0E0h+var_A8], rbx
0x180145d8f  mov     edx, 0F0000h
0x180145d94  mov     [rsp+0E0h+var_B0], rcx
0x180145d99  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180145da0  mov     qword ptr [rsp+0E0h+cbData], rcx
0x180145da5  mov     rcx, rax
0x180145da8  mov     dword ptr [rsp+0E0h+lpData], 378h
0x180145db0  call    cs:__imp_WdsSetupLogMessageW
0x180145db6  call    _KillSearchService
0x180145dbb  mov     esi, eax
0x180145dbd  test    eax, eax
0x180145dbf  jz      short loc_180145E1E
0x180145dc1  call    cs:__imp_GetLastError
0x180145dc7  mov     edi, eax
0x180145dc9  call    cs:__imp_CurrentIP
0x180145dcf  mov     r8d, esi
0x180145dd2  lea     rdx, aMssMssrchSyspr_2; "MSS: MSSrch_SysPrep_Cleanup _KillSearch"...
0x180145dd9  mov     ecx, 4000000h; unsigned int
0x180145dde  mov     rbx, rax
0x180145de1  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180145de6  mov     [rsp+0E0h+var_90], r13d
0x180145deb  lea     rcx, aMssrchSysprepC_0; "MSSrch_SysPrep_Cleanup"
0x180145df2  mov     [rsp+0E0h+var_98], r13
0x180145df7  mov     [rsp+0E0h+var_A0], edi
0x180145dfb  mov     [rsp+0E0h+var_A8], rbx
0x180145e00  mov     [rsp+0E0h+var_B0], rcx
0x180145e05  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180145e0c  mov     qword ptr [rsp+0E0h+cbData], rcx
0x180145e11  mov     dword ptr [rsp+0E0h+lpData], 37Dh
0x180145e19  jmp     loc_180145F5F
0x180145e1e  call    cs:__imp_GetLastError
0x180145e24  mov     edi, eax
0x180145e26  call    cs:__imp_CurrentIP
0x180145e2c  lea     rdx, aMssMssrchSyspr_0; "MSS: MSSrch_SysPrep_Cleanup _KillSearch"...
0x180145e33  mov     ecx, 4000000h; unsigned int
0x180145e38  mov     rbx, rax
0x180145e3b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180145e40  mov     [rsp+0E0h+var_90], r13d
0x180145e45  lea     rcx, aMssrchSysprepC_0; "MSSrch_SysPrep_Cleanup"
0x180145e4c  mov     [rsp+0E0h+var_98], r13
0x180145e51  lea     r8, aD_2; "D"
0x180145e58  mov     [rsp+0E0h+var_A0], edi
0x180145e5c  xor     r9d, r9d
0x180145e5f  mov     [rsp+0E0h+var_A8], rbx
0x180145e64  mov     edx, 0F0000h
0x180145e69  mov     [rsp+0E0h+var_B0], rcx
0x180145e6e  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180145e75  mov     qword ptr [rsp+0E0h+cbData], rcx
0x180145e7a  mov     rcx, rax
0x180145e7d  mov     dword ptr [rsp+0E0h+lpData], 381h
0x180145e85  call    cs:__imp_WdsSetupLogMessageW
0x180145e8b  mov     ecx, 0BB8h; dwMilliseconds
0x180145e90  call    cs:__imp_Sleep
0x180145e96  lea     rcx, [rbp+57h+var_58]
0x180145e9a  call    _StopWithDependentServices
0x180145e9f  mov     esi, eax
0x180145ea1  test    eax, eax
0x180145ea3  jz      loc_180145F83
0x180145ea9  call    cs:__imp_GetLastError
0x180145eaf  mov     edi, eax
0x180145eb1  call    cs:__imp_CurrentIP
0x180145eb7  mov     r8d, esi
0x180145eba  lea     rdx, aMssMssrchSyspr_4; "MSS:MSSrch_SysPrep_Cleanup 2nd _StopWit"...
0x180145ec1  mov     ecx, 4000000h; unsigned int
0x180145ec6  mov     rbx, rax
0x180145ec9  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180145ece  mov     [rsp+0E0h+var_90], r13d
0x180145ed3  lea     rcx, aMssrchSysprepC_0; "MSSrch_SysPrep_Cleanup"
0x180145eda  mov     [rsp+0E0h+var_98], r13
0x180145edf  mov     [rsp+0E0h+var_A0], edi
0x180145ee3  mov     [rsp+0E0h+var_A8], rbx
0x180145ee8  mov     [rsp+0E0h+var_B0], rcx
0x180145eed  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180145ef4  mov     qword ptr [rsp+0E0h+cbData], rcx
0x180145ef9  mov     dword ptr [rsp+0E0h+lpData], 38Dh
0x180145f01  jmp     short loc_180145F5F
0x180145f03  test    esi, esi
0x180145f05  jz      short loc_180145F83
0x180145f07  call    cs:__imp_GetLastError
0x180145f0d  mov     edi, eax
0x180145f0f  call    cs:__imp_CurrentIP
0x180145f15  mov     r8d, esi
0x180145f18  lea     rdx, aMssMssrchSyspr_3; "MSS: MSSrch_SysPrep_Cleanup _StopWithDe"...
0x180145f1f  mov     ecx, 2000000h; unsigned int
0x180145f24  mov     rbx, rax
0x180145f27  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180145f2c  mov     [rsp+0E0h+var_90], r13d
0x180145f31  lea     rcx, aMssrchSysprepC_0; "MSSrch_SysPrep_Cleanup"
0x180145f38  mov     [rsp+0E0h+var_98], r13
0x180145f3d  mov     [rsp+0E0h+var_A0], edi
0x180145f41  mov     [rsp+0E0h+var_A8], rbx
0x180145f46  mov     [rsp+0E0h+var_B0], rcx
0x180145f4b  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180145f52  mov     qword ptr [rsp+0E0h+cbData], rcx
0x180145f57  mov     dword ptr [rsp+0E0h+lpData], 396h
0x180145f5f  xor     r9d, r9d
0x180145f62  lea     r8, aD_2; "D"
0x180145f69  mov     edx, 0F0000h
0x180145f6e  mov     rcx, rax
0x180145f71  call    cs:__imp_WdsSetupLogMessageW
0x180145f77  cmp     esi, 102h
0x180145f7d  jnz     loc_180146123
0x180145f83  call    Cleanup
0x180145f88  mov     esi, eax
0x180145f8a  test    eax, eax
0x180145f8c  jz      short loc_180145FE8
0x180145f8e  call    cs:__imp_GetLastError
0x180145f94  mov     edi, eax
0x180145f96  call    cs:__imp_CurrentIP
0x180145f9c  lea     rdx, aMssMssrchSyspr_7; "MSS:MSSrch_SysPrep_Cleanup Cleanup fail"...
0x180145fa3  mov     ecx, 2000000h; unsigned int
0x180145fa8  mov     rbx, rax
0x180145fab  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180145fb0  mov     [rsp+0E0h+var_90], r13d
0x180145fb5  lea     rcx, aMssrchSysprepC_0; "MSSrch_SysPrep_Cleanup"
0x180145fbc  mov     [rsp+0E0h+var_98], r13
0x180145fc1  mov     [rsp+0E0h+var_A0], edi
0x180145fc5  mov     [rsp+0E0h+var_A8], rbx
0x180145fca  mov     [rsp+0E0h+var_B0], rcx
0x180145fcf  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180145fd6  mov     qword ptr [rsp+0E0h+cbData], rcx
0x180145fdb  mov     dword ptr [rsp+0E0h+lpData], 39Fh
0x180145fe3  jmp     loc_18014610B
0x180145fe8  lea     r9, [rbp+57h+hKey]
0x180145fec  mov     [rbp+57h+hKey], r13
0x180145ff0  mov     r8d, 2
0x180145ff6  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows Search"
0x180145ffd  mov     rcx, 0FFFFFFFF80000002h
0x180146004  call    _OpenKeyForBackupRestore
0x180146009  mov     esi, eax
0x18014600b  test    eax, eax
0x18014600d  jnz     loc_1801460AF
0x180146013  mov     rcx, [rbp+57h+hKey]; hKey
0x180146017  lea     r9d, [rax+4]; dwType
0x18014601b  lea     rax, [rbp+57h+Data]
0x18014601f  mov     [rsp+0E0h+cbData], r9d; cbData
0x180146024  xor     r8d, r8d; Reserved
0x180146027  mov     [rsp+0E0h+lpData], rax; lpData
0x18014602c  lea     rdx, pszValue; "SetupCompletedSuccessfully"
0x180146033  mov     dword ptr [rbp+57h+Data], r13d
0x180146037  call    cs:__imp_RegSetValueExW
0x18014603d  mov     rcx, [rbp+57h+hKey]; hKey
0x180146041  mov     esi, eax
0x180146043  call    cs:__imp_RegCloseKey
0x180146049  test    esi, esi
0x18014604b  jz      loc_180146123
0x180146051  call    cs:__imp_GetLastError
0x180146057  mov     edi, eax
0x180146059  call    cs:__imp_CurrentIP
0x18014605f  mov     r9d, dword ptr [rbp+57h+Data]
0x180146063  lea     rdx, aMssMssrchSyspr_1; "MSS:MSSrch_SysPrep_Cleanup Error 0x%X o"...
0x18014606a  mov     r8d, esi
0x18014606d  mov     ecx, 2000000h; unsigned int
0x180146072  mov     rbx, rax
0x180146075  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18014607a  mov     [rsp+0E0h+var_90], r13d
0x18014607f  lea     rcx, aMssrchSysprepC_0; "MSSrch_SysPrep_Cleanup"
0x180146086  mov     [rsp+0E0h+var_98], r13
0x18014608b  mov     [rsp+0E0h+var_A0], edi
0x18014608f  mov     [rsp+0E0h+var_A8], rbx
0x180146094  mov     [rsp+0E0h+var_B0], rcx
0x180146099  lea     rcx, aOnecoreuapBase_219; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1801460a0  mov     qword ptr [rsp+0E0h+cbData], rcx
0x1801460a5  mov     dword ptr [rsp+0E0h+lpData], 3B7h
0x1801460ad  jmp     short loc_18014610B
0x1801460af  call    cs:__imp_GetLastError
  ... truncated ...
```
