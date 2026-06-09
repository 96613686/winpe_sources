# CPITRSettings::CPITRSettings(CPITRBase *)

- ea: `0x180004dc8`
- end: `0x1800050f6`
- name: `??0CPITRSettings@@QEAA@PEAVCPITRBase@@@Z`
- size: `814`
- prototype: `CPITRSettings *__fastcall(CPITRSettings *this, struct CPITRBase *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000f5f4`

## callees

- `0x180004dc8`
- `0x180009e04`
- `0x180011530`
- `0x18001178c`
- `0x18001def0`
- `0x18001eca0`
- `0x180020a10`
- `0x18002125c`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004f4a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180004f4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000502f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004e84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004f5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000502f`
- `WDSCORE!CurrentIP` at `0x180004e8c`
- `WDSCORE!CurrentIP` at `0x180004f63`
- `WDSCORE!CurrentIP` at `0x180005037`
- `WDSCORE!CurrentIP` at `0x180004e8c`
- `WDSCORE!CurrentIP` at `0x180004f63`
- `WDSCORE!CurrentIP` at `0x180005037`
- `WDSCORE!WdsSetupLogMessageW` at `0x180004fdc`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005097`
- `WDSCORE!WdsSetupLogMessageW` at `0x180004fdc`
- `WDSCORE!WdsSetupLogMessageW` at `0x180005097`
- `unbcl!??0Object@UnBCL@@QEAA@XZ` at `0x180004dea`
- `unbcl!??0Object@UnBCL@@QEAA@XZ` at `0x180004dea`

## string_xrefs

- `0x180004ecf`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180004fb9`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180005074`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180004e47`: `SeBackupPrivilege`
- `0x1800050bf`: `SeBackupPrivilege`
- `0x180004e59`: `SeRestorePrivilege`
- `0x1800050d5`: `SeRestorePrivilege`
- `0x180004f87`: `Failed to open PITR settings key %s. Error: 0x%08X`

## pseudocode

```c
CPITRSettings *__fastcall CPITRSettings::CPITRSettings(CPITRSettings *this, struct CPITRBase *a2)
{
  int v4; // r13d
  int v5; // r12d
  struct UnBCL::String *v6; // rsi
  int v7; // r15d
  DWORD v8; // edi
  __int64 v9; // rbx
  struct tagLOG_PARTIAL_MSG *v10; // rax
  unsigned int v11; // eax
  LSTATUS Key; // r15d
  DWORD LastError; // edi
  __int64 v14; // rbx
  unsigned int v15; // ecx
  struct tagLOG_PARTIAL_MSG *v16; // rax
  char IsEnabled; // al
  unsigned int v18; // ecx
  int *v19; // rdx
  DWORD v20; // edi
  __int64 v21; // rbx
  struct tagLOG_PARTIAL_MSG *v22; // rax
  struct UnBCL::String *v24; // [rsp+60h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-10h] BYREF
  int v26; // [rsp+C0h] [rbp+48h]
  int v27; // [rsp+C8h] [rbp+50h] BYREF
  int v28; // [rsp+D0h] [rbp+58h] BYREF
  int v29; // [rsp+D8h] [rbp+60h]

  UnBCL::Object::Object((CPITRSettings *)((char *)this + 8));
  *(_QWORD *)this = &CPITRSettings::`vftable'{for `PITR::IPITRSettings'};
  *((_QWORD *)this + 1) = &CPITRSettings::`vftable'{for `UnBCL::Object'};
  v4 = 0;
  v27 = 0;
  v5 = 0;
  v28 = 0;
  v29 = 0;
  hKey = 0;
  v6 = 0;
  v24 = 0;
  *((_QWORD *)this + 3) = a2;
  if ( a2 )
  {
    if ( (unsigned int)CPITRBase::IsOffline(a2, &v24) )
    {
      v29 = 1;
      pEnablePrivilege(L"SeBackupPrivilege", 1, &v27);
      pEnablePrivilege(L"SeRestorePrivilege", 1, &v28);
      v4 = v27;
      v5 = v28;
    }
    v6 = v24;
  }
  v7 = CPITRBase::LockSoftwareKey(a2, &hKey);
  if ( v7 >= 0 )
  {
    v11 = pOpenRegKeyMaxAccess(
            hKey,
            L"Microsoft\\Windows\\CurrentVersion\\Setup\\Recovery\\PITR\\Settings",
            (PHKEY)this + 4);
    Key = v11;
    if ( v11 )
    {
      if ( v11 - 2 > 1
        || (Key = RegCreateKeyExW(
                    hKey,
                    L"Microsoft\\Windows\\CurrentVersion\\Setup\\Recovery\\PITR\\Settings",
                    0,
                    0,
                    0,
                    0xF003Fu,
                    0,
                    (PHKEY)this + 4,
                    0)) != 0 )
      {
        LastError = GetLastError();
        v14 = CurrentIP();
        v15 = 0x2000000;
        if ( Key == 2 )
          v15 = 50331648;
        v16 = ConstructPartialMsgW(
                v15,
                "Failed to open PITR settings key %s. Error: 0x%08X",
                (const char *)L"Microsoft\\Windows\\CurrentVersion\\Setup\\Recovery\\PITR\\Settings",
                Key);
        WdsSetupLogMessageW(
          v16,
          0,
          L"D",
          0,
          2195,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRSettings::CPITRSettings",
          v14,
          LastError,
          0,
          0);
      }
    }
    *((_DWORD *)this + 10) = 1;
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl);
    v18 = 3072;
    if ( IsEnabled )
      v18 = g_GlobalSizeVal;
    *((_DWORD *)this + 11) = v18;
    v19 = 0;
    if ( !v29 )
      v19 = (int *)((char *)this + 40);
    v26 = pCalculateDefaults(v6, v19, (unsigned int *)this + 11);
    if ( v26 < 0 )
    {
      v20 = GetLastError();
      v21 = CurrentIP();
      v22 = ConstructPartialMsgW(0x2000000u, "Failed to calculate default values. Error: 0x%08X", v26);
      WdsSetupLogMessageW(
        v22,
        0,
        L"D",
        0,
        2216,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRSettings::CPITRSettings",
        v21,
        v20,
        0,
        0);
    }
  }
  else
  {
    v8 = GetLastError();
    v9 = CurrentIP();
    v10 = ConstructPartialMsgW(0x2000000u, "Failed to lock SOFTWARE key. Error: 0x%08X", v7);
    WdsSetupLogMessageW(
      v10,
      0,
      L"D",
      0,
      2159,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"CPITRSettings::CPITRSettings",
      v9,
      v8,
      0,
      0);
  }
  if ( v6 )
    (**(void (__fastcall ***)(struct UnBCL::String *, __int64))v6)(v6, 1);
  if ( v4 )
    pEnablePrivilege(L"SeBackupPrivilege", 0, 0);
  if ( v5 )
    pEnablePrivilege(L"SeRestorePrivilege", 0, 0);
  return this;
}

```

## disassembly

```asm
0x180004dc8  mov     [rsp-40h+arg_0], rcx
0x180004dcd  push    rbp
0x180004dce  push    rbx
0x180004dcf  push    rsi
0x180004dd0  push    rdi
0x180004dd1  push    r12
0x180004dd3  push    r13
0x180004dd5  push    r14
0x180004dd7  push    r15
0x180004dd9  mov     rbp, rsp
0x180004ddc  sub     rsp, 78h
0x180004de0  mov     rdi, rdx
0x180004de3  mov     r14, rcx
0x180004de6  add     rcx, 8
0x180004dea  call    cs:__imp_??0Object@UnBCL@@QEAA@XZ; UnBCL::Object::Object(void)
0x180004df0  nop
0x180004df1  lea     rax, ??_7CPITRSettings@@6BIPITRSettings@PITR@@@; const CPITRSettings::`vftable'{for `PITR::IPITRSettings'}
0x180004df8  mov     [r14], rax
0x180004dfb  lea     rax, ??_7CPITRSettings@@6BObject@UnBCL@@@; const CPITRSettings::`vftable'{for `UnBCL::Object'}
0x180004e02  mov     [r14+8], rax
0x180004e06  xor     r13d, r13d
0x180004e09  mov     [rbp+arg_8], r13d
0x180004e0d  xor     r12d, r12d
0x180004e10  mov     [rbp+arg_10], r12d
0x180004e14  mov     [rbp+arg_18], r12d
0x180004e18  mov     [rbp+hKey], r12
0x180004e1c  xor     esi, esi
0x180004e1e  mov     [rbp+var_18], rsi
0x180004e22  mov     [r14+18h], rdi
0x180004e26  lea     ebx, [rsi+1]
0x180004e29  test    rdi, rdi
0x180004e2c  jz      short loc_180004E71
0x180004e2e  lea     rdx, [rbp+var_18]; struct UnBCL::String **
0x180004e32  mov     rcx, rdi; this
0x180004e35  call    ?IsOffline@CPITRBase@@QEAAHPEAPEAVString@UnBCL@@@Z; CPITRBase::IsOffline(UnBCL::String * *)
0x180004e3a  test    eax, eax
0x180004e3c  jz      short loc_180004E6D
0x180004e3e  mov     [rbp+arg_18], ebx
0x180004e41  lea     r8, [rbp+arg_8]; int *
0x180004e45  mov     edx, ebx; int
0x180004e47  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x180004e4e  call    ?pEnablePrivilege@@YAHPEBGHPEAH@Z; pEnablePrivilege(ushort const *,int,int *)
0x180004e53  lea     r8, [rbp+arg_10]; int *
0x180004e57  mov     edx, ebx; int
0x180004e59  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x180004e60  call    ?pEnablePrivilege@@YAHPEBGHPEAH@Z; pEnablePrivilege(ushort const *,int,int *)
0x180004e65  mov     r13d, [rbp+arg_8]
0x180004e69  mov     r12d, [rbp+arg_10]
0x180004e6d  mov     rsi, [rbp+var_18]
0x180004e71  lea     rdx, [rbp+hKey]; HKEY *
0x180004e75  mov     rcx, rdi; this
0x180004e78  call    ?LockSoftwareKey@CPITRBase@@QEAAJPEAPEAUHKEY__@@@Z; CPITRBase::LockSoftwareKey(HKEY__ * *)
0x180004e7d  mov     r15d, eax
0x180004e80  test    eax, eax
0x180004e82  jns     short loc_180004EE8
0x180004e84  call    cs:__imp_GetLastError
0x180004e8a  mov     edi, eax
0x180004e8c  call    cs:__imp_CurrentIP
0x180004e92  mov     rbx, rax
0x180004e95  mov     r8d, r15d
0x180004e98  lea     rdx, aFailedToLockSo; "Failed to lock SOFTWARE key. Error: 0x%"...
0x180004e9f  mov     ecx, 2000000h; unsigned int
0x180004ea4  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180004ea9  mov     [rsp+78h+var_28], 0
0x180004eb1  mov     [rsp+78h+var_30], 0
0x180004eba  mov     dword ptr [rsp+78h+lpdwDisposition], edi
0x180004ebe  mov     [rsp+78h+phkResult], rbx
0x180004ec3  lea     rcx, aCpitrsettingsC; "CPITRSettings::CPITRSettings"
0x180004eca  mov     [rsp+78h+lpSecurityAttributes], rcx
0x180004ecf  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180004ed6  mov     qword ptr [rsp+78h+samDesired], rcx
0x180004edb  mov     [rsp+78h+dwOptions], 86Fh
0x180004ee3  jmp     loc_180005088
0x180004ee8  lea     rbx, [r14+20h]
0x180004eec  mov     r8, rbx; phkResult
0x180004eef  lea     rdx, SubKey; "Microsoft\\Windows\\CurrentVersion\\Set"...
0x180004ef6  mov     rcx, [rbp+hKey]; hKey
0x180004efa  call    ?pOpenRegKeyMaxAccess@@YAKPEAUHKEY__@@PEBGPEAPEAU1@@Z; pOpenRegKeyMaxAccess(HKEY__ *,ushort const *,HKEY__ * *)
0x180004eff  mov     r15d, eax
0x180004f02  test    eax, eax
0x180004f04  jz      loc_180004FE4
0x180004f0a  lea     edx, [rax-2]
0x180004f0d  cmp     edx, 1
0x180004f10  ja      short loc_180004F5B
0x180004f12  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x180004f1b  mov     [rsp+78h+phkResult], rbx; phkResult
0x180004f20  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180004f29  mov     [rsp+78h+samDesired], 0F003Fh; samDesired
0x180004f31  mov     [rsp+78h+dwOptions], 0; dwOptions
0x180004f39  xor     r9d, r9d; lpClass
0x180004f3c  xor     r8d, r8d; Reserved
0x180004f3f  lea     rdx, SubKey; "Microsoft\\Windows\\CurrentVersion\\Set"...
0x180004f46  mov     rcx, [rbp+hKey]; hKey
0x180004f4a  call    cs:__imp_RegCreateKeyExW
0x180004f50  mov     r15d, eax
0x180004f53  test    eax, eax
0x180004f55  jz      loc_180004FE4
0x180004f5b  call    cs:__imp_GetLastError
0x180004f61  mov     edi, eax
0x180004f63  call    cs:__imp_CurrentIP
0x180004f69  mov     rbx, rax
0x180004f6c  mov     ecx, 2000000h
0x180004f71  mov     eax, 3000000h
0x180004f76  cmp     r15d, 2
0x180004f7a  cmovz   ecx, eax; unsigned int
0x180004f7d  mov     r9d, r15d
0x180004f80  lea     r8, SubKey; "Microsoft\\Windows\\CurrentVersion\\Set"...
0x180004f87  lea     rdx, aFailedToOpenPi_1; "Failed to open PITR settings key %s. Er"...
0x180004f8e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180004f93  mov     [rsp+78h+var_28], 0
0x180004f9b  mov     [rsp+78h+var_30], 0
0x180004fa4  mov     dword ptr [rsp+78h+lpdwDisposition], edi
0x180004fa8  mov     [rsp+78h+phkResult], rbx
0x180004fad  lea     r15, aCpitrsettingsC; "CPITRSettings::CPITRSettings"
0x180004fb4  mov     [rsp+78h+lpSecurityAttributes], r15
0x180004fb9  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180004fc0  mov     qword ptr [rsp+78h+samDesired], rcx
0x180004fc5  mov     [rsp+78h+dwOptions], 893h
0x180004fcd  xor     r9d, r9d
0x180004fd0  lea     r8, aD; "D"
0x180004fd7  xor     edx, edx
0x180004fd9  mov     rcx, rax
0x180004fdc  call    cs:__imp_WdsSetupLogMessageW
0x180004fe2  jmp     short loc_180004FEB
0x180004fe4  lea     r15, aCpitrsettingsC; "CPITRSettings::CPITRSettings"
0x180004feb  lea     rbx, [r14+28h]
0x180004fef  mov     dword ptr [rbx], 1
0x180004ff5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x180004ffc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x180005001  mov     ecx, 0C00h
0x180005006  test    al, al
0x180005008  cmovnz  ecx, cs:?g_GlobalSizeVal@@3KA; ulong g_GlobalSizeVal
0x18000500f  mov     [r14+2Ch], ecx
0x180005013  lea     r8, [r14+2Ch]; unsigned int *
0x180005017  xor     edx, edx
0x180005019  cmp     [rbp+arg_18], edx
0x18000501c  cmovz   rdx, rbx; int *
0x180005020  mov     rcx, rsi; struct UnBCL::String *
0x180005023  call    ?pCalculateDefaults@@YAJPEAVString@UnBCL@@PEAHPEAK@Z; pCalculateDefaults(UnBCL::String *,int *,ulong *)
0x180005028  mov     dword ptr [rbp+arg_0], eax
0x18000502b  test    eax, eax
0x18000502d  jns     short loc_18000509D
0x18000502f  call    cs:__imp_GetLastError
0x180005035  mov     edi, eax
0x180005037  call    cs:__imp_CurrentIP
0x18000503d  mov     rbx, rax
0x180005040  mov     r8d, dword ptr [rbp+arg_0]
0x180005044  lea     rdx, aFailedToCalcul_0; "Failed to calculate default values. Err"...
0x18000504b  mov     ecx, 2000000h; unsigned int
0x180005050  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180005055  mov     [rsp+78h+var_28], 0
0x18000505d  mov     [rsp+78h+var_30], 0
0x180005066  mov     dword ptr [rsp+78h+lpdwDisposition], edi
0x18000506a  mov     [rsp+78h+phkResult], rbx
0x18000506f  mov     [rsp+78h+lpSecurityAttributes], r15
0x180005074  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18000507b  mov     qword ptr [rsp+78h+samDesired], rcx
0x180005080  mov     [rsp+78h+dwOptions], 8A8h
0x180005088  xor     r9d, r9d
0x18000508b  lea     r8, aD; "D"
0x180005092  xor     edx, edx
0x180005094  mov     rcx, rax
0x180005097  call    cs:__imp_WdsSetupLogMessageW
0x18000509d  test    rsi, rsi
0x1800050a0  jz      short loc_1800050B5
0x1800050a2  mov     rax, [rsi]
0x1800050a5  mov     edx, 1
0x1800050aa  mov     rcx, rsi
0x1800050ad  mov     rax, [rax]
0x1800050b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050b5  test    r13d, r13d
0x1800050b8  jz      short loc_1800050CB
0x1800050ba  xor     r8d, r8d; int *
0x1800050bd  xor     edx, edx; int
0x1800050bf  lea     rcx, aSebackupprivil; "SeBackupPrivilege"
0x1800050c6  call    ?pEnablePrivilege@@YAHPEBGHPEAH@Z; pEnablePrivilege(ushort const *,int,int *)
0x1800050cb  test    r12d, r12d
0x1800050ce  jz      short loc_1800050E2
0x1800050d0  xor     r8d, r8d; int *
0x1800050d3  xor     edx, edx; int
0x1800050d5  lea     rcx, aSerestoreprivi; "SeRestorePrivilege"
0x1800050dc  call    ?pEnablePrivilege@@YAHPEBGHPEAH@Z; pEnablePrivilege(ushort const *,int,int *)
0x1800050e1  nop
0x1800050e2  mov     rax, r14
0x1800050e5  add     rsp, 78h
0x1800050e9  pop     r15
0x1800050eb  pop     r14
0x1800050ed  pop     r13
0x1800050ef  pop     r12
0x1800050f1  pop     rdi
0x1800050f2  pop     rsi
0x1800050f3  pop     rbx
0x1800050f4  pop     rbp
0x1800050f5  retn
```
