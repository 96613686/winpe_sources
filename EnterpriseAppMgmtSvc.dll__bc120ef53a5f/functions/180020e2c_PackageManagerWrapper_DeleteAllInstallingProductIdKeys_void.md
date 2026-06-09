# PackageManagerWrapper::DeleteAllInstallingProductIdKeys(void)

- ea: `0x180020e2c`
- end: `0x180021187`
- name: `?DeleteAllInstallingProductIdKeys@PackageManagerWrapper@@AEAAJXZ`
- size: `859`
- prototype: `__int64 __fastcall(PackageManagerWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180012388`

## callees

- `0x18000d3dc`
- `0x18001d65c`
- `0x180020e2c`
- `0x180021190`
- `0x180028154`
- `0x18002c98c`
- `0x18006c910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002109b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002109b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800210ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800210ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021065`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002112f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021065`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002112f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180020f4f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180020f4f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020e7b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020f82`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020fb4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800210ed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020e7b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020f82`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180020fb4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800210ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020eb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020ff6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002100d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021080`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800210ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021146`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002115d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020eb2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020ff6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002100d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021080`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800210ac`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021146`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002115d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180020efd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180020efd`

## string_xrefs

- `0x180020e90`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180020fdb`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180021049`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x180021115`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall PackageManagerWrapper::DeleteAllInstallingProductIdKeys(PackageManagerWrapper *this)
{
  unsigned int v1; // eax
  __int64 v2; // rdx
  unsigned int v3; // ebx
  __int64 v5; // rdx
  HKEY v6; // rcx
  DWORD i; // ebx
  PackageManagerWrapper *v8; // rcx
  int v9; // eax
  int HKLMStateSeparationRedirectionPath; // eax
  HKEY v11; // rdi
  DWORD LastError; // ebx
  HKEY v13; // rbx
  PackageManagerWrapper *v14; // rcx
  int v15; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v19; // [rsp+68h] [rbp-98h] BYREF
  HKEY v20; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchName; // [rsp+80h] [rbp-80h] BYREF
  HKEY v23; // [rsp+88h] [rbp-78h] BYREF
  WCHAR Name[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  cSubKeys = 0;
  hKey = 0;
  v1 = RegOpenKeyExW(HKEY_USERS, 0, 0, 0xF003Fu, &hKey);
  if ( v1 )
  {
    v2 = 424;
LABEL_3:
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v2,
           (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
           (const char *)v1,
           phkResult);
LABEL_4:
    if ( hKey )
      RegCloseKey(hKey);
    return v3;
  }
  v1 = RegQueryInfoKeyW(HKEY_USERS, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( v1 )
  {
    v2 = 437;
    goto LABEL_3;
  }
  if ( cSubKeys )
  {
    for ( i = 0; i < cSubKeys; ++i )
    {
      cchName = 260;
      if ( !RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0) )
      {
        v19 = 0;
        if ( !RegOpenKeyExW(HKEY_USERS, Name, 0, 0xF003Fu, &v19) )
        {
          v23 = 0;
          if ( !RegOpenKeyExW(v19, L"Software\\Microsoft\\EnterpriseModernAppManagement\\AppIDs", 0, 0xF003Fu, &v23) )
          {
            v9 = PackageManagerWrapper::DeleteInstallingProductIdKey(v8, v23);
            if ( v9 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x1D9,
                (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\pa"
                              "ckagemanager.cpp",
                (const char *)(unsigned int)v9,
                phkResult);
          }
          if ( v23 )
            RegCloseKey(v23);
        }
        v6 = v19;
        if ( v19 )
          RegCloseKey(v19);
      }
    }
  }
  v20 = 0;
  v19 = 0;
  HKLMStateSeparationRedirectionPath = EnterpriseModernAppManagement::GetHKLMStateSeparationRedirectionPath(
                                         v6,
                                         v5,
                                         &v19);
  v3 = HKLMStateSeparationRedirectionPath;
  if ( HKLMStateSeparationRedirectionPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EA,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)HKLMStateSeparationRedirectionPath,
      phkResult);
    if ( v19 )
      LocalFree(v19);
    if ( v20 )
      RegCloseKey(v20);
    goto LABEL_4;
  }
  v11 = v20;
  if ( v20 )
  {
    LastError = GetLastError();
    RegCloseKey(v11);
    SetLastError(LastError);
  }
  v20 = 0;
  v13 = v19;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v19, 0, 0xF013Fu, &v20) )
  {
    v15 = PackageManagerWrapper::DeleteInstallingProductIdKey(v14, v20);
    if ( v15 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1F4,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
        (const char *)(unsigned int)v15,
        phkResulta);
  }
  if ( v13 )
    LocalFree(v13);
  if ( v20 )
    RegCloseKey(v20);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x180020e2c  push    rbp
0x180020e2e  push    rbx
0x180020e2f  push    rsi
0x180020e30  push    rdi
0x180020e31  lea     rbp, [rsp-1B8h]
0x180020e39  sub     rsp, 2B8h
0x180020e40  mov     rax, cs:__security_cookie
0x180020e47  xor     rax, rsp
0x180020e4a  mov     [rbp+1D0h+var_30], rax
0x180020e51  xor     esi, esi
0x180020e53  mov     [rsp+2D0h+cSubKeys], esi
0x180020e57  mov     [rsp+2D0h+hKey], rsi
0x180020e5c  lea     rax, [rsp+2D0h+hKey]
0x180020e61  mov     [rsp+2D0h+phkResult], rax; unsigned int
0x180020e66  mov     r9d, 0F003Fh; samDesired
0x180020e6c  xor     r8d, r8d; ulOptions
0x180020e6f  xor     edx, edx; lpSubKey
0x180020e71  mov     rdi, 0FFFFFFFF80000003h
0x180020e78  mov     rcx, rdi; hKey
0x180020e7b  call    cs:__imp_RegOpenKeyExW
0x180020e82  nop     dword ptr [rax+rax+00h]
0x180020e87  test    eax, eax
0x180020e89  jz      short loc_180020EC5
0x180020e8b  mov     edx, 1A8h; void *
0x180020e90  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180020e97  mov     r9d, eax; char *
0x180020e9a  mov     rcx, [rbp+1D8h]; this
0x180020ea1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180020ea6  mov     ebx, eax
0x180020ea8  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180020ead  test    rcx, rcx
0x180020eb0  jz      short loc_180020EBE
0x180020eb2  call    cs:__imp_RegCloseKey
0x180020eb9  nop     dword ptr [rax+rax+00h]
0x180020ebe  mov     eax, ebx
0x180020ec0  jmp     loc_18002116B
0x180020ec5  mov     [rsp+2D0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x180020eca  mov     [rsp+2D0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x180020ecf  mov     [rsp+2D0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x180020ed4  mov     [rsp+2D0h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x180020ed9  mov     [rsp+2D0h+lpcValues], rsi; lpcValues
0x180020ede  mov     [rsp+2D0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x180020ee3  mov     [rsp+2D0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x180020ee8  lea     rax, [rsp+2D0h+cSubKeys]
0x180020eed  mov     [rsp+2D0h+phkResult], rax; lpcSubKeys
0x180020ef2  xor     r9d, r9d; lpReserved
0x180020ef5  xor     r8d, r8d; lpcchClass
0x180020ef8  xor     edx, edx; lpClass
0x180020efa  mov     rcx, rdi; hKey
0x180020efd  call    cs:__imp_RegQueryInfoKeyW
0x180020f04  nop     dword ptr [rax+rax+00h]
0x180020f09  test    eax, eax
0x180020f0b  jz      short loc_180020F17
0x180020f0d  mov     edx, 1B5h
0x180020f12  jmp     loc_180020E90
0x180020f17  mov     eax, [rsp+2D0h+cSubKeys]
0x180020f1b  test    eax, eax
0x180020f1d  jz      loc_180021025
0x180020f23  mov     ebx, esi
0x180020f25  mov     [rbp+1D0h+cchName], 104h
0x180020f2c  mov     [rsp+2D0h+lpcValues], rsi; lpftLastWriteTime
0x180020f31  mov     [rsp+2D0h+lpcbMaxClassLen], rsi; lpcchClass
0x180020f36  mov     [rsp+2D0h+lpcbMaxSubKeyLen], rsi; lpClass
0x180020f3b  mov     [rsp+2D0h+phkResult], rsi; lpReserved
0x180020f40  lea     r9, [rbp+1D0h+cchName]; lpcchName
0x180020f44  lea     r8, [rbp+1D0h+Name]; lpName
0x180020f48  mov     edx, ebx; dwIndex
0x180020f4a  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180020f4f  call    cs:__imp_RegEnumKeyExW
0x180020f56  nop     dword ptr [rax+rax+00h]
0x180020f5b  test    eax, eax
0x180020f5d  jnz     loc_180021019
0x180020f63  mov     [rsp+2D0h+var_268], rsi
0x180020f68  lea     rax, [rsp+2D0h+var_268]
0x180020f6d  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180020f72  mov     r9d, 0F003Fh; samDesired
0x180020f78  xor     r8d, r8d; ulOptions
0x180020f7b  lea     rdx, [rbp+1D0h+Name]; lpSubKey
0x180020f7f  mov     rcx, rdi; hKey
0x180020f82  call    cs:__imp_RegOpenKeyExW
0x180020f89  nop     dword ptr [rax+rax+00h]
0x180020f8e  test    eax, eax
0x180020f90  jnz     short loc_180021003
0x180020f92  mov     [rbp+1D0h+var_248], rsi
0x180020f96  lea     rax, [rbp+1D0h+var_248]
0x180020f9a  mov     [rsp+2D0h+phkResult], rax; int
0x180020f9f  mov     r9d, 0F003Fh; samDesired
0x180020fa5  xor     r8d, r8d; ulOptions
0x180020fa8  lea     rdx, ?c_AppIDsRegistryPath@EnterpriseModernAppManagement@@3QBGB; "Software\\Microsoft\\EnterpriseModernAp"...
0x180020faf  mov     rcx, [rsp+2D0h+var_268]; hKey
0x180020fb4  call    cs:__imp_RegOpenKeyExW
0x180020fbb  nop     dword ptr [rax+rax+00h]
0x180020fc0  test    eax, eax
0x180020fc2  jnz     short loc_180020FED
0x180020fc4  mov     rdx, [rbp+1D0h+var_248]; HKEY
0x180020fc8  call    ?DeleteInstallingProductIdKey@PackageManagerWrapper@@AEAAJPEAUHKEY__@@@Z; PackageManagerWrapper::DeleteInstallingProductIdKey(HKEY__ *)
0x180020fcd  mov     rcx, [rbp+1D8h]; this
0x180020fd4  test    eax, eax
0x180020fd6  jns     short loc_180020FED
0x180020fd8  mov     r9d, eax; char *
0x180020fdb  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180020fe2  mov     edx, 1D9h; void *
0x180020fe7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020fec  nop
0x180020fed  mov     rcx, [rbp+1D0h+var_248]; hKey
0x180020ff1  test    rcx, rcx
0x180020ff4  jz      short loc_180021003
0x180020ff6  call    cs:__imp_RegCloseKey
0x180020ffd  nop     dword ptr [rax+rax+00h]
0x180021002  nop
0x180021003  mov     rcx, [rsp+2D0h+var_268]; hKey
0x180021008  test    rcx, rcx
0x18002100b  jz      short loc_180021019
0x18002100d  call    cs:__imp_RegCloseKey
0x180021014  nop     dword ptr [rax+rax+00h]
0x180021019  inc     ebx
0x18002101b  cmp     ebx, [rsp+2D0h+cSubKeys]
0x18002101f  jb      loc_180020F25
0x180021025  mov     [rsp+2D0h+var_260], rsi
0x18002102a  mov     [rsp+2D0h+var_268], rsi
0x18002102f  lea     r8, [rsp+2D0h+var_268]
0x180021034  call    ?GetHKLMStateSeparationRedirectionPath@EnterpriseModernAppManagement@@YAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; EnterpriseModernAppManagement::GetHKLMStateSeparationRedirectionPath(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180021039  mov     ebx, eax
0x18002103b  test    eax, eax
0x18002103d  jns     short loc_180021091
0x18002103f  mov     rcx, [rbp+1D8h]; this
0x180021046  mov     r9d, eax; char *
0x180021049  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180021050  mov     edx, 1EAh; void *
0x180021055  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002105a  nop
0x18002105b  mov     rcx, [rsp+2D0h+var_268]; hMem
0x180021060  test    rcx, rcx
0x180021063  jz      short loc_180021072
0x180021065  call    cs:__imp_LocalFree
0x18002106c  nop     dword ptr [rax+rax+00h]
0x180021071  nop
0x180021072  mov     rcx, [rsp+2D0h+var_260]; hKey
0x180021077  test    rcx, rcx
0x18002107a  jz      loc_180020EA8
0x180021080  call    cs:__imp_RegCloseKey
0x180021087  nop     dword ptr [rax+rax+00h]
0x18002108c  jmp     loc_180020EA8
0x180021091  mov     rdi, [rsp+2D0h+var_260]
0x180021096  test    rdi, rdi
0x180021099  jz      short loc_1800210C6
0x18002109b  call    cs:__imp_GetLastError
0x1800210a2  nop     dword ptr [rax+rax+00h]
0x1800210a7  mov     ebx, eax
0x1800210a9  mov     rcx, rdi; hKey
0x1800210ac  call    cs:__imp_RegCloseKey
0x1800210b3  nop     dword ptr [rax+rax+00h]
0x1800210b8  mov     ecx, ebx; dwErrCode
0x1800210ba  call    cs:__imp_SetLastError
0x1800210c1  nop     dword ptr [rax+rax+00h]
0x1800210c6  mov     [rsp+2D0h+var_260], rsi
0x1800210cb  lea     rax, [rsp+2D0h+var_260]
0x1800210d0  mov     [rsp+2D0h+phkResult], rax; int
0x1800210d5  mov     r9d, 0F013Fh; samDesired
0x1800210db  xor     r8d, r8d; ulOptions
0x1800210de  mov     rbx, [rsp+2D0h+var_268]
0x1800210e3  mov     rdx, rbx; lpSubKey
0x1800210e6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800210ed  call    cs:__imp_RegOpenKeyExW
0x1800210f4  nop     dword ptr [rax+rax+00h]
0x1800210f9  test    eax, eax
0x1800210fb  jnz     short loc_180021127
0x1800210fd  mov     rdx, [rsp+2D0h+var_260]; HKEY
0x180021102  call    ?DeleteInstallingProductIdKey@PackageManagerWrapper@@AEAAJPEAUHKEY__@@@Z; PackageManagerWrapper::DeleteInstallingProductIdKey(HKEY__ *)
0x180021107  mov     rcx, [rbp+1D8h]; this
0x18002110e  test    eax, eax
0x180021110  jns     short loc_180021127
0x180021112  mov     r9d, eax; char *
0x180021115  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002111c  mov     edx, 1F4h; void *
0x180021121  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180021126  nop
0x180021127  test    rbx, rbx
0x18002112a  jz      short loc_18002113C
0x18002112c  mov     rcx, rbx; hMem
0x18002112f  call    cs:__imp_LocalFree
0x180021136  nop     dword ptr [rax+rax+00h]
0x18002113b  nop
0x18002113c  mov     rcx, [rsp+2D0h+var_260]; hKey
0x180021141  test    rcx, rcx
0x180021144  jz      short loc_180021153
0x180021146  call    cs:__imp_RegCloseKey
0x18002114d  nop     dword ptr [rax+rax+00h]
0x180021152  nop
0x180021153  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180021158  test    rcx, rcx
0x18002115b  jz      short loc_180021169
0x18002115d  call    cs:__imp_RegCloseKey
0x180021164  nop     dword ptr [rax+rax+00h]
0x180021169  xor     eax, eax
0x18002116b  mov     rcx, [rbp+1D0h+var_30]
0x180021172  xor     rcx, rsp; StackCookie
0x180021175  call    __security_check_cookie
0x18002117a  add     rsp, 2B8h
0x180021181  pop     rdi
0x180021182  pop     rsi
0x180021183  pop     rbx
0x180021184  pop     rbp
0x180021185  retn
```
