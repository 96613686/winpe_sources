# SystemSettings::PointInTimeRestore::PointInTimeRestoreManager::InitializeLogging(void)

- ea: `0x1800265b4`
- end: `0x1800266d5`
- name: `?InitializeLogging@PointInTimeRestoreManager@PointInTimeRestore@SystemSettings@@QEAAXXZ`
- size: `289`
- prototype: `void __fastcall(SystemSettings::PointInTimeRestore::PointInTimeRestoreManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180025c88`

## callees

- `0x180002350`
- `0x180002ed4`
- `0x18000bef4`
- `0x1800265b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026643`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800265f7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800265f7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180026608`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180026608`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800266ae`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800266ae`
- `WDSCORE!CurrentIP` at `0x18002664b`
- `WDSCORE!CurrentIP` at `0x18002664b`
- `WDSCORE!WdsInitialize` at `0x18002663d`
- `WDSCORE!WdsInitialize` at `0x18002663d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SystemSettings::PointInTimeRestore::PointInTimeRestoreManager::InitializeLogging(
        SystemSettings::PointInTimeRestore::PointInTimeRestoreManager *this)
{
  DWORD LastError; // edi
  __int64 v2; // rbx
  struct tagLOG_PARTIAL_MSG *v3; // rax
  WCHAR Dst[264]; // [rsp+60h] [rbp-228h] BYREF

  memset_0(Dst, 0, 0x208u);
  if ( ExpandEnvironmentStringsW(L"%windir%\\Logs\\PITR", Dst, 0x104u) )
  {
    CreateDirectoryW(Dst, 0);
    WdsInitialize(L"PITR", 1, Dst, Dst, 50393088, 0, 0);
  }
  LastError = GetLastError();
  v2 = CurrentIP();
  v3 = ConstructPartialMsgW(
         0x4000000u,
         "SystemSettings::PointInTimeRestore::PointInTimeRestoreManager::InitializeLogging logging initialized");
  WdsSetupLogMessageW(
    v3,
    0,
    L"D",
    0,
    36,
    L"pcshell\\shell\\systemsettings\\recoveryhandlers\\lib\\pointintimerestoremanager.cpp",
    L"SystemSettings::PointInTimeRestore::PointInTimeRestoreManager::InitializeLogging",
    v2,
    LastError,
    0,
    0);
}

```

## disassembly

```asm
0x1800265b4  mov     [rsp+arg_0], rbx
0x1800265b9  push    rdi
0x1800265ba  sub     rsp, 280h
0x1800265c1  mov     rax, cs:__security_cookie
0x1800265c8  xor     rax, rsp
0x1800265cb  mov     [rsp+288h+var_18], rax
0x1800265d3  xor     edx, edx; Val
0x1800265d5  lea     rcx, [rsp+288h+Dst]; void *
0x1800265da  mov     r8d, 208h; Size
0x1800265e0  call    memset_0
0x1800265e5  mov     r8d, 104h; nSize
0x1800265eb  lea     rdx, [rsp+288h+Dst]; lpDst
0x1800265f0  lea     rcx, Src; "%windir%\\Logs\\PITR"
0x1800265f7  call    cs:__imp_ExpandEnvironmentStringsW
0x1800265fd  test    eax, eax
0x1800265ff  jz      short loc_180026643
0x180026601  xor     edx, edx; lpSecurityAttributes
0x180026603  lea     rcx, [rsp+288h+Dst]; lpPathName
0x180026608  call    cs:__imp_CreateDirectoryW
0x18002660e  mov     [rsp+288h+var_258], 0
0x180026617  lea     r9, [rsp+288h+Dst]
0x18002661c  mov     dword ptr [rsp+288h+var_260], 0
0x180026624  lea     r8, [rsp+288h+Dst]
0x180026629  mov     edx, 1
0x18002662e  mov     [rsp+288h+var_268], 300F000h
0x180026636  lea     rcx, aPitr; "PITR"
0x18002663d  call    cs:__imp_WdsInitialize
0x180026643  call    cs:__imp_GetLastError
0x180026649  mov     edi, eax
0x18002664b  call    cs:__imp_CurrentIP
0x180026651  lea     rdx, aSystemsettings_70; "SystemSettings::PointInTimeRestore::Poi"...
0x180026658  mov     ecx, 4000000h; unsigned int
0x18002665d  mov     rbx, rax
0x180026660  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180026665  mov     [rsp+288h+var_238], 0
0x18002666d  lea     rcx, aSystemsettings_10; "SystemSettings::PointInTimeRestore::Poi"...
0x180026674  mov     [rsp+288h+var_240], 0
0x18002667d  lea     r8, aD; "D"
0x180026684  mov     [rsp+288h+var_248], edi
0x180026688  xor     r9d, r9d
0x18002668b  mov     [rsp+288h+var_250], rbx
0x180026690  xor     edx, edx
0x180026692  mov     [rsp+288h+var_258], rcx
0x180026697  lea     rcx, aPcshellShellSy_2; "pcshell\\shell\\systemsettings\\recover"...
0x18002669e  mov     [rsp+288h+var_260], rcx
0x1800266a3  mov     rcx, rax
0x1800266a6  mov     [rsp+288h+var_268], 24h ; '$'
0x1800266ae  call    cs:__imp_WdsSetupLogMessageW
0x1800266b4  mov     rcx, [rsp+288h+var_18]
0x1800266bc  xor     rcx, rsp; StackCookie
0x1800266bf  call    __security_check_cookie
0x1800266c4  mov     rbx, [rsp+288h+arg_0]
0x1800266cc  add     rsp, 280h
0x1800266d3  pop     rdi
0x1800266d4  retn
```
