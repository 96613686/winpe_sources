# ClassRegistration::Unregister(void)

- ea: `0x18007317c`
- end: `0x1800735f9`
- name: `?Unregister@ClassRegistration@@QEAAJXZ`
- size: `1149`
- prototype: `HRESULT __fastcall(ClassRegistration *this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800688c4`

## callees

- `0x180051abc`
- `0x180052390`
- `0x180053014`
- `0x180072d9c`
- `0x180072e1c`
- `0x180072eb4`
- `0x180072fb0`
- `0x180073044`
- `0x18007317c`
- `0x1800c4639`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18007323e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18007323e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800734a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800734c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073512`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007357d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800735a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800735b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800735c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cd104`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cd114`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cd124`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800734a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800734c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073512`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007357d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800735a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800735b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800735c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cd104`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cd114`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800cd124`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800733e1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800733f9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180073411`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180073429`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180073441`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800733e1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800733f9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180073411`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180073429`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x180073441`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073279`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800732a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800734f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007354c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073279`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800732a4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800734f2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007354c`

## pseudocode

```c
__int64 __fastcall ClassRegistration::Unregister(ClassRegistration *this)
{
  HINSTANCE__ *hModule; // rcx
  const wchar_t *v4; // r8
  const wchar_t *progID; // rdx
  const wchar_t *versionIndependentProgID; // rdx
  _BYTE v7[32]; // [rsp+0h] [rbp-4F8h] BYREF
  HKEY__ *hKeyGuid; // [rsp+30h] [rbp-4C8h] BYREF
  HKEY__ *hKeyProgID; // [rsp+38h] [rbp-4C0h] BYREF
  HKEY__ *hKeyCLSID; // [rsp+40h] [rbp-4B8h] BYREF
  _EXCEPTION_POINTERS *e; // [rsp+50h] [rbp-4A8h]
  int v12; // [rsp+58h] [rbp-4A0h]
  _BYTE *v13; // [rsp+60h] [rbp-498h]
  wchar_t szClsid[40]; // [rsp+70h] [rbp-488h] BYREF
  wchar_t szProgID[264]; // [rsp+C0h] [rbp-438h] BYREF
  wchar_t szModuleName[264]; // [rsp+2D0h] [rbp-228h] BYREF

  v13 = v7;
  hKeyCLSID = 0;
  hKeyGuid = 0;
  hKeyProgID = 0;
  e = 0;
  memset_0(szProgID, 0, 0x208u);
  GetGuidString(&this->clsid, szClsid);
  hModule = this->hModule;
  if ( hModule )
  {
    if ( GetModuleFileNameW(hModule, szModuleName, 0x104u) )
      UnRegisterTypeLib(szModuleName);
    if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, Com::Catalog::Constants::CLSID, 0, 0xF003Fu, &hKeyCLSID) )
    {
      if ( !RegOpenKeyExW(hKeyCLSID, szClsid, 0, 0xF003Fu, &hKeyGuid) )
      {
        if ( !this->progID )
          this->progID = GetSubkeyValue(hKeyGuid, Com::Catalog::Constants::ProgID, v4, szProgID);
        if ( !this->versionIndependentProgID )
          this->versionIndependentProgID = GetSubkeyValue(
                                             hKeyGuid,
                                             Com::Catalog::Constants::VersionIndependentProgID,
                                             v4,
                                             szProgID);
        DeleteValue(hKeyGuid, 0, Com::Catalog::Constants::AppID);
        DeleteValue(hKeyGuid, Com::Catalog::Constants::InprocServer32, Com::Catalog::Constants::ThreadingModel);
        GuardedDeleteKey(hKeyGuid, Com::Catalog::Constants::InprocServer32);
        GuardedDeleteKey(hKeyGuid, L"LocalServer");
        GuardedDeleteKey(hKeyGuid, L"InprocHandler");
        GuardedDeleteKey(hKeyGuid, Com::Catalog::Constants::LocalServer32);
        GuardedDeleteKey(hKeyGuid, Com::Catalog::Constants::InprocHandler32);
        GuardedDeleteKey(hKeyGuid, L"Control");
        GuardedDeleteKey(hKeyGuid, L"Programmable");
        GuardedDeleteKey(hKeyGuid, L"DocObject");
        GuardedDeleteKey(hKeyGuid, Com::Catalog::Constants::Insertable);
        GuardedDeleteKey(hKeyGuid, L"Printable");
        RegDeleteKeyExW(hKeyGuid, Com::Catalog::Constants::MiscStatus, 0, 0);
        RegDeleteKeyExW(hKeyGuid, Com::Catalog::Constants::Verb, 0, 0);
        RegDeleteKeyExW(hKeyGuid, Com::Catalog::Constants::AuxUserType, 0, 0);
        RegDeleteKeyExW(hKeyGuid, Com::Catalog::Constants::Conversion, 0, 0);
        RegDeleteKeyExW(hKeyGuid, Com::Catalog::Constants::DataFormats, 0, 0);
        GuardedDeleteKey(hKeyGuid, Com::Catalog::Constants::ToolBoxBitmap32);
        GuardedDeleteKey(hKeyGuid, Com::Catalog::Constants::DefaultIcon);
        GuardedDeleteKey(hKeyGuid, Com::Catalog::Constants::Version);
        GuardedDeleteKey(hKeyGuid, Com::Catalog::Constants::ProgID);
        GuardedDeleteKey(hKeyGuid, Com::Catalog::Constants::VersionIndependentProgID);
        RegCloseKey(hKeyGuid);
        hKeyGuid = 0;
      }
      GuardedDeleteKey(hKeyCLSID, szClsid);
      RegCloseKey(hKeyCLSID);
      hKeyCLSID = 0;
    }
    progID = this->progID;
    if ( progID && !RegOpenKeyExW(HKEY_CLASSES_ROOT, progID, 0, 0xF003Fu, &hKeyProgID) )
    {
      GuardedDeleteKey(hKeyProgID, Com::Catalog::Constants::CLSID);
      RegCloseKey(hKeyProgID);
      hKeyProgID = 0;
      GuardedDeleteKey((HKEY__ *)0xFFFFFFFF80000000LL, this->progID);
    }
    versionIndependentProgID = this->versionIndependentProgID;
    if ( versionIndependentProgID
      && !RegOpenKeyExW(HKEY_CLASSES_ROOT, versionIndependentProgID, 0, 0xF003Fu, &hKeyProgID) )
    {
      GuardedDeleteKey(hKeyProgID, Com::Catalog::Constants::CLSID);
      GuardedDeleteKey(hKeyProgID, Com::Catalog::Constants::CurVer);
      RegCloseKey(hKeyProgID);
      hKeyProgID = 0;
      GuardedDeleteKey((HKEY__ *)0xFFFFFFFF80000000LL, this->versionIndependentProgID);
    }
    if ( hKeyCLSID )
      RegCloseKey(hKeyCLSID);
    if ( hKeyGuid )
      RegCloseKey(hKeyGuid);
    if ( hKeyProgID )
      RegCloseKey(hKeyProgID);
    return 0;
  }
  else
  {
    v12 = -2147024809;
    local_unwind_0(v7, &_LN32_0);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x18007317c  mov     [rsp+arg_8], rbx
0x180073181  push    rsi
0x180073182  sub     rsp, 4F0h
0x180073189  mov     rax, cs:__security_cookie
0x180073190  xor     rax, rsp
0x180073193  mov     [rsp+4F8h+var_18], rax
0x18007319b  mov     [rsp+4F8h+var_498], rsp
0x1800731a0  mov     rbx, this
0x1800731a3  mov     [rsp+4F8h+hKeyCLSID], 0
0x1800731ac  mov     [rsp+4F8h+hKeyGuid], 0
0x1800731b5  mov     [rsp+4F8h+hKeyProgID], 0
0x1800731be  mov     [rsp+4F8h+e], 0
0x1800731c7  xor     edx, edx; Val
0x1800731c9  mov     r8d, 208h; Size
0x1800731cf  lea     this, [rsp+4F8h+szProgID]; void *
0x1800731d7  call    memset_0
0x1800731dc  lea     rdx, [rsp+4F8h+szClsid]; pstrGuid
0x1800731e1  mov     this, rbx; rGuid
0x1800731e4  call    GetGuidString
0x1800731e9  mov     this, [rbx+18h]; hModule
0x1800731ed  test    this, this
0x1800731f0  jnz     short loc_180073230
0x1800731f2  mov     [rsp+4F8h+var_4A0], 80070057h
0x1800731fa  lea     rdx, $LN32_0
0x180073201  mov     this, rsp
0x180073204  call    _local_unwind_0
0x180073209  nop
0x18007320a  mov     eax, 80070057h
0x18007320f  mov     this, [rsp+4F8h+var_18]
0x180073217  xor     this, rsp; StackCookie
0x18007321a  call    __security_check_cookie
0x18007321f  mov     rbx, [rsp+4F8h+arg_8]
0x180073227  add     rsp, 4F0h
0x18007322e  pop     rsi
0x18007322f  retn
0x180073230  mov     r8d, 104h; nSize
0x180073236  lea     rdx, [rsp+4F8h+szModuleName]; lpFilename
0x18007323e  call    cs:__imp_GetModuleFileNameW
0x180073244  test    eax, eax
0x180073246  jz      short loc_180073255
0x180073248  lea     this, [rsp+4F8h+szModuleName]; szModuleName
0x180073250  call    UnRegisterTypeLib
0x180073255  lea     rax, [rsp+4F8h+hKeyCLSID]
0x18007325a  mov     [rsp+4F8h+phkResult], rax; phkResult
0x18007325f  mov     r9d, 0F003Fh; samDesired
0x180073265  xor     r8d, r8d; ulOptions
0x180073268  lea     rdx, ?CLSID@Constants@Catalog@Com@@3QBGB; lpSubKey
0x18007326f  mov     rsi, 0FFFFFFFF80000000h
0x180073276  mov     this, rsi; hKey
0x180073279  call    cs:__imp_RegOpenKeyExW
0x18007327f  test    eax, eax
0x180073281  jnz     loc_1800734D3
0x180073287  lea     rax, [rsp+4F8h+hKeyGuid]
0x18007328c  mov     [rsp+4F8h+phkResult], rax; phkResult
0x180073291  mov     r9d, 0F003Fh; samDesired
0x180073297  xor     r8d, r8d; ulOptions
0x18007329a  lea     rdx, [rsp+4F8h+szClsid]; lpSubKey
0x18007329f  mov     this, [rsp+4F8h+hKeyCLSID]; hKey
0x1800732a4  call    cs:__imp_RegOpenKeyExW
0x1800732aa  test    eax, eax
0x1800732ac  jnz     loc_1800734B0
0x1800732b2  cmp     qword ptr [rbx+28h], 0
0x1800732b7  jnz     short loc_1800732D6
0x1800732b9  lea     r9, [rsp+4F8h+szProgID]; hkey
0x1800732c1  lea     rdx, ?ProgID@Constants@Catalog@Com@@3QBGB; szSubKeyName
0x1800732c8  mov     this, [rsp+4F8h+hKeyGuid]; hkey
0x1800732cd  call    GetSubkeyValue
0x1800732d2  mov     [rbx+28h], rax
0x1800732d6  cmp     qword ptr [rbx+30h], 0
0x1800732db  jnz     short loc_1800732FA
0x1800732dd  lea     r9, [rsp+4F8h+szProgID]; hkey
0x1800732e5  lea     rdx, ?VersionIndependentProgID@Constants@Catalog@Com@@3QBGB; szSubKeyName
0x1800732ec  mov     this, [rsp+4F8h+hKeyGuid]; hkey
0x1800732f1  call    GetSubkeyValue
0x1800732f6  mov     [rbx+30h], rax
0x1800732fa  lea     r8, ?AppID@Constants@Catalog@Com@@3QBGB; szValue
0x180073301  xor     edx, edx; szSubkey
0x180073303  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x180073308  call    DeleteValue
0x18007330d  lea     r8, ?ThreadingModel@Constants@Catalog@Com@@3QBGB; szValue
0x180073314  lea     rdx, ?InprocServer32@Constants@Catalog@Com@@3QBGB; szSubkey
0x18007331b  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x180073320  call    DeleteValue
0x180073325  lea     rdx, ?InprocServer32@Constants@Catalog@Com@@3QBGB; szSubKey
0x18007332c  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x180073331  call    GuardedDeleteKey
0x180073336  lea     rdx, aLocalserver; "LocalServer"
0x18007333d  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x180073342  call    GuardedDeleteKey
0x180073347  lea     rdx, aInprochandler; "InprocHandler"
0x18007334e  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x180073353  call    GuardedDeleteKey
0x180073358  lea     rdx, ?LocalServer32@Constants@Catalog@Com@@3QBGB; szSubKey
0x18007335f  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x180073364  call    GuardedDeleteKey
0x180073369  lea     rdx, ?InprocHandler32@Constants@Catalog@Com@@3QBGB; szSubKey
0x180073370  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x180073375  call    GuardedDeleteKey
0x18007337a  lea     rdx, aControl; "Control"
0x180073381  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x180073386  call    GuardedDeleteKey
0x18007338b  lea     rdx, aProgrammable; "Programmable"
0x180073392  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x180073397  call    GuardedDeleteKey
0x18007339c  lea     rdx, aDocobject; "DocObject"
0x1800733a3  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x1800733a8  call    GuardedDeleteKey
0x1800733ad  lea     rdx, ?Insertable@Constants@Catalog@Com@@3QBGB; szSubKey
0x1800733b4  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x1800733b9  call    GuardedDeleteKey
0x1800733be  lea     rdx, aPrintable; "Printable"
0x1800733c5  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x1800733ca  call    GuardedDeleteKey
0x1800733cf  xor     r9d, r9d; Reserved
0x1800733d2  xor     r8d, r8d; samDesired
0x1800733d5  lea     rdx, ?MiscStatus@Constants@Catalog@Com@@3QBGB; lpSubKey
0x1800733dc  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x1800733e1  call    cs:__imp_RegDeleteKeyExW
0x1800733e7  xor     r9d, r9d; Reserved
0x1800733ea  xor     r8d, r8d; samDesired
0x1800733ed  lea     rdx, ?Verb@Constants@Catalog@Com@@3QBGB; lpSubKey
0x1800733f4  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x1800733f9  call    cs:__imp_RegDeleteKeyExW
0x1800733ff  xor     r9d, r9d; Reserved
0x180073402  xor     r8d, r8d; samDesired
0x180073405  lea     rdx, ?AuxUserType@Constants@Catalog@Com@@3QBGB; lpSubKey
0x18007340c  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x180073411  call    cs:__imp_RegDeleteKeyExW
0x180073417  xor     r9d, r9d; Reserved
0x18007341a  xor     r8d, r8d; samDesired
0x18007341d  lea     rdx, ?Conversion@Constants@Catalog@Com@@3QBGB; lpSubKey
0x180073424  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x180073429  call    cs:__imp_RegDeleteKeyExW
0x18007342f  xor     r9d, r9d; Reserved
0x180073432  xor     r8d, r8d; samDesired
0x180073435  lea     rdx, ?DataFormats@Constants@Catalog@Com@@3QBGB; lpSubKey
0x18007343c  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x180073441  call    cs:__imp_RegDeleteKeyExW
0x180073447  lea     rdx, ?ToolBoxBitmap32@Constants@Catalog@Com@@3QBGB; szSubKey
0x18007344e  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x180073453  call    GuardedDeleteKey
0x180073458  lea     rdx, ?DefaultIcon@Constants@Catalog@Com@@3QBGB; szSubKey
0x18007345f  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x180073464  call    GuardedDeleteKey
0x180073469  lea     rdx, ?Version@Constants@Catalog@Com@@3QBGB; szSubKey
0x180073470  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x180073475  call    GuardedDeleteKey
0x18007347a  lea     rdx, ?ProgID@Constants@Catalog@Com@@3QBGB; szSubKey
0x180073481  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x180073486  call    GuardedDeleteKey
0x18007348b  lea     rdx, ?VersionIndependentProgID@Constants@Catalog@Com@@3QBGB; szSubKey
0x180073492  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x180073497  call    GuardedDeleteKey
0x18007349c  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x1800734a1  call    cs:__imp_RegCloseKey
0x1800734a7  mov     [rsp+4F8h+hKeyGuid], 0
0x1800734b0  lea     rdx, [rsp+4F8h+szClsid]; szSubKey
0x1800734b5  mov     this, [rsp+4F8h+hKeyCLSID]; hKey
0x1800734ba  call    GuardedDeleteKey
0x1800734bf  mov     this, [rsp+4F8h+hKeyCLSID]; hKey
0x1800734c4  call    cs:__imp_RegCloseKey
0x1800734ca  mov     [rsp+4F8h+hKeyCLSID], 0
0x1800734d3  mov     rdx, [rbx+28h]; lpSubKey
0x1800734d7  test    rdx, rdx
0x1800734da  jz      short loc_18007352D
0x1800734dc  lea     rax, [rsp+4F8h+hKeyProgID]
0x1800734e1  mov     [rsp+4F8h+phkResult], rax; phkResult
0x1800734e6  mov     r9d, 0F003Fh; samDesired
0x1800734ec  xor     r8d, r8d; ulOptions
0x1800734ef  mov     this, rsi; hKey
0x1800734f2  call    cs:__imp_RegOpenKeyExW
0x1800734f8  test    eax, eax
0x1800734fa  jnz     short loc_18007352D
0x1800734fc  lea     rdx, ?CLSID@Constants@Catalog@Com@@3QBGB; szSubKey
0x180073503  mov     this, [rsp+4F8h+hKeyProgID]; hKey
0x180073508  call    GuardedDeleteKey
0x18007350d  mov     this, [rsp+4F8h+hKeyProgID]; hKey
0x180073512  call    cs:__imp_RegCloseKey
0x180073518  mov     [rsp+4F8h+hKeyProgID], 0
0x180073521  mov     rdx, [rbx+28h]; szSubKey
0x180073525  mov     this, rsi; hKey
0x180073528  call    GuardedDeleteKey
0x18007352d  mov     rdx, [rbx+30h]; lpSubKey
0x180073531  test    rdx, rdx
0x180073534  jz      short $LN27_1
0x180073536  lea     rax, [rsp+4F8h+hKeyProgID]
0x18007353b  mov     [rsp+4F8h+phkResult], rax; phkResult
0x180073540  mov     r9d, 0F003Fh; samDesired
0x180073546  xor     r8d, r8d; ulOptions
0x180073549  mov     this, rsi; hKey
0x18007354c  call    cs:__imp_RegOpenKeyExW
0x180073552  test    eax, eax
0x180073554  jnz     short $LN27_1
0x180073556  lea     rdx, ?CLSID@Constants@Catalog@Com@@3QBGB; szSubKey
0x18007355d  mov     this, [rsp+4F8h+hKeyProgID]; hKey
0x180073562  call    GuardedDeleteKey
0x180073567  lea     rdx, ?CurVer@Constants@Catalog@Com@@3QBGB; szSubKey
0x18007356e  mov     this, [rsp+4F8h+hKeyProgID]; hKey
0x180073573  call    GuardedDeleteKey
0x180073578  mov     this, [rsp+4F8h+hKeyProgID]; hKey
0x18007357d  call    cs:__imp_RegCloseKey
0x180073583  mov     [rsp+4F8h+hKeyProgID], 0
0x18007358c  mov     rdx, [rbx+30h]; szSubKey
0x180073590  mov     this, rsi; hKey
0x180073593  call    GuardedDeleteKey
0x180073598  nop
0x180073599  mov     this, [rsp+4F8h+hKeyCLSID]; hKey
0x18007359e  test    this, this
0x1800735a1  jz      short loc_1800735A9
0x1800735a3  call    cs:__imp_RegCloseKey
0x1800735a9  mov     this, [rsp+4F8h+hKeyGuid]; hKey
0x1800735ae  test    this, this
0x1800735b1  jz      short loc_1800735B9
0x1800735b3  call    cs:__imp_RegCloseKey
0x1800735b9  mov     this, [rsp+4F8h+hKeyProgID]; hKey
0x1800735be  test    this, this
0x1800735c1  jz      short loc_1800735C9
0x1800735c3  call    cs:__imp_RegCloseKey
0x1800735c9  xor     eax, eax
0x1800735cb  jmp     $LN23_2
0x1800735d0  mov     this, [rsp+4F8h+e]; e
0x1800735d5  call    HRESULTFrom
0x1800735da  mov     [rsp+4F8h+var_4B0], eax
0x1800735de  lea     rdx, $LN33
0x1800735e5  mov     this, [rsp+4F8h+var_498]
0x1800735ea  call    _local_unwind_0
0x1800735ef  nop
0x1800735f0  mov     eax, [rsp+4F8h+var_4B0]
0x1800735f4  jmp     $LN23_2
0x1800cd0cd  push    rbp
0x1800cd0cf  sub     rsp, 30h
0x1800cd0d3  mov     rbp, rdx
0x1800cd0d6  mov     rax, [rcx]
0x1800cd0d9  cmp     dword ptr [rax], 0
0x1800cd0dc  jnz     short loc_1800CD0E9
0x1800cd0de  mov     [rbp+50h], rcx
0x1800cd0e2  mov     eax, 1
0x1800cd0e7  jmp     short loc_1800CD0EB
0x1800cd0e9  xor     eax, eax
0x1800cd0eb  add     rsp, 30h
0x1800cd0ef  pop     rbp
0x1800cd0f0  retn
0x1800cd0f2  push    rbp
0x1800cd0f4  sub     rsp, 30h
0x1800cd0f8  mov     rbp, rdx
0x1800cd0fb  mov     rcx, [rbp+40h]; hKey
0x1800cd0ff  test    rcx, rcx
0x1800cd102  jz      short loc_1800CD10B
0x1800cd104  call    cs:__imp_RegCloseKey
0x1800cd10a  nop
0x1800cd10b  mov     rcx, [rbp+30h]; hKey
0x1800cd10f  test    rcx, rcx
0x1800cd112  jz      short loc_1800CD11B
0x1800cd114  call    cs:__imp_RegCloseKey
0x1800cd11a  nop
0x1800cd11b  mov     rcx, [rbp+38h]; hKey
0x1800cd11f  test    rcx, rcx
0x1800cd122  jz      short loc_1800CD12B
0x1800cd124  call    cs:__imp_RegCloseKey
0x1800cd12a  nop
0x1800cd12b  add     rsp, 30h
0x1800cd12f  pop     rbp
0x1800cd130  retn
```
