# CRecoveryAdminHelper::CRecoveryAdminHelper(void)

- ea: `0x18000dcec`
- end: `0x18000ded5`
- name: `??0CRecoveryAdminHelper@@QEAA@XZ`
- size: `489`
- prototype: `CRecoveryAdminHelper *__fastcall(CRecoveryAdminHelper *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800058d0`

## callees

- `0x180002350`
- `0x180002ed4`
- `0x18000bef4`
- `0x18000dcec`
- `0x18000e110`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ddca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ddca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000de3b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000dd81`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000dd81`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000dd92`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000dd92`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000de35`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000dea6`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000de35`
- `WDSCORE!WdsSetupLogMessageW` at `0x18000dea6`
- `WDSCORE!CurrentIP` at `0x18000ddd2`
- `WDSCORE!CurrentIP` at `0x18000de43`
- `WDSCORE!CurrentIP` at `0x18000ddd2`
- `WDSCORE!CurrentIP` at `0x18000de43`
- `WDSCORE!WdsInitialize` at `0x18000ddc4`
- `WDSCORE!WdsInitialize` at `0x18000ddc4`

## string_xrefs

- `0x18000de12`: `pcshell\shell\systemsettings\recoveryhandlers\dll\pointintimerestorehelper.cpp`
- `0x18000de83`: `pcshell\shell\systemsettings\recoveryhandlers\dll\recoveryadminhelper.cpp`

## pseudocode

```c
CRecoveryAdminHelper *__fastcall CRecoveryAdminHelper::CRecoveryAdminHelper(CRecoveryAdminHelper *this)
{
  DWORD LastError; // edi
  __int64 v3; // rbx
  struct tagLOG_PARTIAL_MSG *v4; // rax
  DWORD v5; // edi
  __int64 v6; // rbx
  struct tagLOG_PARTIAL_MSG *v7; // rax
  WCHAR Dst[264]; // [rsp+70h] [rbp-228h] BYREF

  *((_DWORD *)this + 3) = 1;
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRecoveryAdminHelper>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &CRecoveryAdminHelper::`vftable';
  *((_QWORD *)this + 2) = 0;
  CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper(this);
  memset_0(Dst, 0, 0x208u);
  if ( ExpandEnvironmentStringsW(L"%windir%\\Logs\\PITR", Dst, 0x104u) )
  {
    CreateDirectoryW(Dst, 0);
    WdsInitialize(L"PITR", 1, Dst, Dst, 50393088, 0, 0);
  }
  LastError = GetLastError();
  v3 = CurrentIP();
  v4 = ConstructPartialMsgW(0x4000000u, "CPointInTimeRestoreHelper::InitializeLogging: logging initialized.");
  WdsSetupLogMessageW(
    v4,
    0,
    L"D",
    0,
    40,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\pointintimerestorehelper.cpp",
    L"CPointInTimeRestoreHelper::InitializeLogging",
    v3,
    LastError,
    0,
    0);
  v5 = GetLastError();
  v6 = CurrentIP();
  v7 = ConstructPartialMsgW(0x4000000u, "CRecoveryAdminHelper::CRecoveryAdminHelper: initialized.");
  WdsSetupLogMessageW(
    v7,
    0,
    L"D",
    0,
    10,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\dll\\recoveryadminhelper.cpp",
    L"CRecoveryAdminHelper::CRecoveryAdminHelper",
    v6,
    v5,
    0,
    0);
  return this;
}

```

## disassembly

```asm
0x18000dcec  mov     [rsp+arg_8], rbx
0x18000dcf1  mov     [rsp+arg_10], rsi
0x18000dcf6  push    rdi
0x18000dcf7  sub     rsp, 290h
0x18000dcfe  mov     rax, cs:__security_cookie
0x18000dd05  xor     rax, rsp
0x18000dd08  mov     [rsp+298h+var_18], rax
0x18000dd10  mov     rsi, rcx
0x18000dd13  mov     [rsp+298h+var_238], rcx
0x18000dd18  mov     ebx, 1
0x18000dd1d  mov     [rcx+0Ch], ebx
0x18000dd20  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIRecoveryAdminHelper@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IRecoveryAdminHelper>::`vftable'
0x18000dd27  mov     [rcx], rax
0x18000dd2a  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000dd31  test    rcx, rcx
0x18000dd34  jz      short loc_18000DD43
0x18000dd36  mov     rax, [rcx]
0x18000dd39  mov     rax, [rax+8]
0x18000dd3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd42  nop
0x18000dd43  lea     rax, ??_7CRecoveryAdminHelper@@6B@; const CRecoveryAdminHelper::`vftable'
0x18000dd4a  mov     [rsi], rax
0x18000dd4d  mov     qword ptr [rsi+10h], 0
0x18000dd55  mov     rcx, rsi; this
0x18000dd58  call    ?GetCurrentPointInTimeRestoreHelper@CRecoveryAdminHelper@@AEAAPEAVCPointInTimeRestoreHelper@@XZ; CRecoveryAdminHelper::GetCurrentPointInTimeRestoreHelper(void)
0x18000dd5d  xor     edx, edx; Val
0x18000dd5f  mov     r8d, 208h; Size
0x18000dd65  lea     rcx, [rsp+298h+Dst]; void *
0x18000dd6a  call    memset_0
0x18000dd6f  mov     r8d, 104h; nSize
0x18000dd75  lea     rdx, [rsp+298h+Dst]; lpDst
0x18000dd7a  lea     rcx, Src; "%windir%\\Logs\\PITR"
0x18000dd81  call    cs:__imp_ExpandEnvironmentStringsW
0x18000dd87  test    eax, eax
0x18000dd89  jz      short loc_18000DDCA
0x18000dd8b  xor     edx, edx; lpSecurityAttributes
0x18000dd8d  lea     rcx, [rsp+298h+Dst]; lpPathName
0x18000dd92  call    cs:__imp_CreateDirectoryW
0x18000dd98  mov     [rsp+298h+var_268], 0
0x18000dda1  mov     dword ptr [rsp+298h+var_270], 0
0x18000dda9  mov     [rsp+298h+var_278], 300F000h
0x18000ddb1  lea     r9, [rsp+298h+Dst]
0x18000ddb6  lea     r8, [rsp+298h+Dst]
0x18000ddbb  mov     edx, ebx
0x18000ddbd  lea     rcx, aPitr; "PITR"
0x18000ddc4  call    cs:__imp_WdsInitialize
0x18000ddca  call    cs:__imp_GetLastError
0x18000ddd0  mov     edi, eax
0x18000ddd2  call    cs:__imp_CurrentIP
0x18000ddd8  mov     rbx, rax
0x18000dddb  lea     rdx, aCpointintimere_39; "CPointInTimeRestoreHelper::InitializeLo"...
0x18000dde2  mov     ecx, 4000000h; unsigned int
0x18000dde7  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000ddec  mov     [rsp+298h+var_248], 0
0x18000ddf4  mov     [rsp+298h+var_250], 0
0x18000ddfd  mov     [rsp+298h+var_258], edi
0x18000de01  mov     [rsp+298h+var_260], rbx
0x18000de06  lea     rcx, aCpointintimere_63; "CPointInTimeRestoreHelper::InitializeLo"...
0x18000de0d  mov     [rsp+298h+var_268], rcx
0x18000de12  lea     rdx, aPcshellShellSy_3; "pcshell\\shell\\systemsettings\\recover"...
0x18000de19  mov     [rsp+298h+var_270], rdx
0x18000de1e  mov     [rsp+298h+var_278], 28h ; '('
0x18000de26  xor     r9d, r9d
0x18000de29  lea     r8, aD; "D"
0x18000de30  xor     edx, edx
0x18000de32  mov     rcx, rax
0x18000de35  call    cs:__imp_WdsSetupLogMessageW
0x18000de3b  call    cs:__imp_GetLastError
0x18000de41  mov     edi, eax
0x18000de43  call    cs:__imp_CurrentIP
0x18000de49  mov     rbx, rax
0x18000de4c  lea     rdx, aCrecoveryadmin_1; "CRecoveryAdminHelper::CRecoveryAdminHel"...
0x18000de53  mov     ecx, 4000000h; unsigned int
0x18000de58  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18000de5d  mov     [rsp+298h+var_248], 0
0x18000de65  mov     [rsp+298h+var_250], 0
0x18000de6e  mov     [rsp+298h+var_258], edi
0x18000de72  mov     [rsp+298h+var_260], rbx
0x18000de77  lea     rcx, aCrecoveryadmin_8; "CRecoveryAdminHelper::CRecoveryAdminHel"...
0x18000de7e  mov     [rsp+298h+var_268], rcx
0x18000de83  lea     rcx, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\recover"...
0x18000de8a  mov     [rsp+298h+var_270], rcx
0x18000de8f  mov     [rsp+298h+var_278], 0Ah
0x18000de97  xor     r9d, r9d
0x18000de9a  lea     r8, aD; "D"
0x18000dea1  xor     edx, edx
0x18000dea3  mov     rcx, rax
0x18000dea6  call    cs:__imp_WdsSetupLogMessageW
0x18000deac  nop
0x18000dead  mov     rax, rsi
0x18000deb0  mov     rcx, [rsp+298h+var_18]
0x18000deb8  xor     rcx, rsp; StackCookie
0x18000debb  call    __security_check_cookie
0x18000dec0  lea     r11, [rsp+298h+var_8]
0x18000dec8  mov     rbx, [r11+18h]
0x18000decc  mov     rsi, [r11+20h]
0x18000ded0  mov     rsp, r11
0x18000ded3  pop     rdi
0x18000ded4  retn
```
