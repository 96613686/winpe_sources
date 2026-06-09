# COSInstaller::~COSInstaller(void)

- ea: `0x18003c71c`
- end: `0x18003c887`
- name: `??1COSInstaller@@EEAA@XZ`
- size: `363`
- prototype: `void __fastcall(COSInstaller *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003c6e0`

## callees

- `0x18000bbd8`
- `0x18002532c`
- `0x18003c71c`
- `0x18004f03c`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003c865`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003c865`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003c7a5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003c801`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003c7a5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003c801`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c789`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c7e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c789`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c7e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c7b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c81d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c7b5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c81d`

## string_xrefs

- `0x18003c7d7`: `Software\Classes\CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall COSInstaller::~COSInstaller(COSInstaller *this)
{
  unsigned int v2; // edx
  __int64 v3; // rcx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  *(_QWORD *)this = &COSInstaller::`vftable'{for `ISusUpdateDeploy'};
  *((_QWORD *)this + 1) = &COSInstaller::`vftable'{for `ISusUpdatePostRebootResult'};
  *((_QWORD *)this + 2) = &CUHHandlerDeployBase::`vftable'{for `ISusQueryDeploymentCustomReportingData'};
  *((_QWORD *)this + 3) = &CUHHandlerDeployBase::`vftable'{for `IUpdateDeploymentHandlerInfo'};
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Classes\\AppID", 0, 0x20006u, &hKey) >= 0 )
    RegDeleteKeyExW(hKey, &word_1800A2628, 0, 0);
  if ( hKey )
    RegCloseKey(hKey);
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Classes\\CLSID", 0, 0x20006u, &hKey) >= 0 )
    RegDeleteKeyExW(hKey, &sz, 0, 0);
  CWuaClassFactoryBase::UnregisterClassFactory((CWuaClassFactoryBase *)&g_OSDeploymentInformationCFForDeployment, v2);
  if ( hKey )
    RegCloseKey(hKey);
  CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::~CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>((__int64)this + 144);
  CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::~CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>((__int64)this + 120);
  v3 = *((_QWORD *)this + 14);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 14) = 0;
  }
  *((_QWORD *)this + 8) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  CUHHandlerDeployBase::~CUHHandlerDeployBase(this);
}

```

## disassembly

```asm
0x18003c71c  push    rbx
0x18003c71e  sub     rsp, 40h
0x18003c722  mov     rax, cs:__security_cookie
0x18003c729  xor     rax, rsp
0x18003c72c  mov     [rsp+48h+var_10], rax
0x18003c731  mov     rbx, rcx
0x18003c734  lea     rax, ??_7COSInstaller@@6BISusUpdateDeploy@@@; const COSInstaller::`vftable'{for `ISusUpdateDeploy'}
0x18003c73b  mov     [rcx], rax
0x18003c73e  lea     rax, ??_7COSInstaller@@6BISusUpdatePostRebootResult@@@; const COSInstaller::`vftable'{for `ISusUpdatePostRebootResult'}
0x18003c745  mov     [rcx+8], rax
0x18003c749  lea     rax, ??_7CUHHandlerDeployBase@@6BISusQueryDeploymentCustomReportingData@@@; const CUHHandlerDeployBase::`vftable'{for `ISusQueryDeploymentCustomReportingData'}
0x18003c750  mov     [rcx+10h], rax
0x18003c754  lea     rax, ??_7CUHHandlerDeployBase@@6BIUpdateDeploymentHandlerInfo@@@; const CUHHandlerDeployBase::`vftable'{for `IUpdateDeploymentHandlerInfo'}
0x18003c75b  mov     [rcx+18h], rax
0x18003c75f  mov     [rsp+48h+hKey], 0
0x18003c768  lea     rax, [rsp+48h+hKey]
0x18003c76d  mov     [rsp+48h+phkResult], rax; phkResult
0x18003c772  mov     r9d, 20006h; samDesired
0x18003c778  xor     r8d, r8d; ulOptions
0x18003c77b  lea     rdx, SubKey; "Software\\Classes\\AppID"
0x18003c782  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003c789  call    cs:__imp_RegOpenKeyExW
0x18003c78f  test    eax, eax
0x18003c791  js      short loc_18003C7AB
0x18003c793  xor     r9d, r9d; Reserved
0x18003c796  xor     r8d, r8d; samDesired
0x18003c799  lea     rdx, word_1800A2628; lpSubKey
0x18003c7a0  mov     rcx, [rsp+48h+hKey]; hKey
0x18003c7a5  call    cs:__imp_RegDeleteKeyExW
0x18003c7ab  mov     rcx, [rsp+48h+hKey]; hKey
0x18003c7b0  test    rcx, rcx
0x18003c7b3  jz      short loc_18003C7BB
0x18003c7b5  call    cs:__imp_RegCloseKey
0x18003c7bb  mov     [rsp+48h+hKey], 0
0x18003c7c4  lea     rax, [rsp+48h+hKey]
0x18003c7c9  mov     [rsp+48h+phkResult], rax; phkResult
0x18003c7ce  mov     r9d, 20006h; samDesired
0x18003c7d4  xor     r8d, r8d; ulOptions
0x18003c7d7  lea     rdx, aSoftwareClasse; "Software\\Classes\\CLSID"
0x18003c7de  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003c7e5  call    cs:__imp_RegOpenKeyExW
0x18003c7eb  test    eax, eax
0x18003c7ed  js      short loc_18003C807
0x18003c7ef  xor     r9d, r9d; Reserved
0x18003c7f2  xor     r8d, r8d; samDesired
0x18003c7f5  lea     rdx, sz; lpSubKey
0x18003c7fc  mov     rcx, [rsp+48h+hKey]; hKey
0x18003c801  call    cs:__imp_RegDeleteKeyExW
0x18003c807  lea     rcx, ?g_OSDeploymentInformationCFForDeployment@@3VOSDeploymentInformationFactory@@A; this
0x18003c80e  call    ?UnregisterClassFactory@CWuaClassFactoryBase@@QEAAJK@Z; CWuaClassFactoryBase::UnregisterClassFactory(ulong)
0x18003c813  mov     rcx, [rsp+48h+hKey]; hKey
0x18003c818  test    rcx, rcx
0x18003c81b  jz      short loc_18003C823
0x18003c81d  call    cs:__imp_RegCloseKey
0x18003c823  lea     rcx, [rbx+90h]
0x18003c82a  call    ??1?$CSusArrayList@UtagDSGlobalUpdateId@@V?$CSusArrayListItemOpNoop@UtagDSGlobalUpdateId@@@@@@UEAA@XZ; CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::~CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>(void)
0x18003c82f  lea     rcx, [rbx+78h]
0x18003c833  call    ??1?$CSusArrayList@UtagDSGlobalUpdateId@@V?$CSusArrayListItemOpNoop@UtagDSGlobalUpdateId@@@@@@UEAA@XZ; CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>::~CSusArrayList<tagDSGlobalUpdateId,CSusArrayListItemOpNoop<tagDSGlobalUpdateId>>(void)
0x18003c838  nop
0x18003c839  mov     rcx, [rbx+70h]
0x18003c83d  test    rcx, rcx
0x18003c840  jz      short loc_18003C856
0x18003c842  mov     rax, [rcx]
0x18003c845  mov     rax, [rax+10h]
0x18003c849  call    _guard_dispatch_icall
0x18003c84e  mov     qword ptr [rbx+70h], 0
0x18003c856  lea     rax, ??_7CSusLock@@6B@; const CSusLock::`vftable'
0x18003c85d  mov     [rbx+40h], rax
0x18003c861  lea     rcx, [rbx+48h]; lpCriticalSection
0x18003c865  call    cs:__imp_DeleteCriticalSection
0x18003c86b  mov     rcx, rbx; this
0x18003c86e  call    ??1CUHHandlerDeployBase@@UEAA@XZ; CUHHandlerDeployBase::~CUHHandlerDeployBase(void)
0x18003c873  nop
0x18003c874  mov     rcx, [rsp+48h+var_10]
0x18003c879  xor     rcx, rsp; StackCookie
0x18003c87c  call    __security_check_cookie
0x18003c881  add     rsp, 40h
0x18003c885  pop     rbx
0x18003c886  retn
```
