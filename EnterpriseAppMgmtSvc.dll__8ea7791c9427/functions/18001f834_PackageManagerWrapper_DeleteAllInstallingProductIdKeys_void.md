# PackageManagerWrapper::DeleteAllInstallingProductIdKeys(void)

- ea: `0x18001f834`
- end: `0x18001fb25`
- name: `?DeleteAllInstallingProductIdKeys@PackageManagerWrapper@@AEAAJXZ`
- size: `753`
- prototype: `__int64 __fastcall(PackageManagerWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180011b6c`

## callees

- `0x18000cfe8`
- `0x18001c5b8`
- `0x18001f834`
- `0x18001fb2c`
- `0x18002636c`
- `0x18002a6ec`
- `0x180066df0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fa77`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fa77`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fa3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fae0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fa3a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fae0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001f942`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001f942`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f883`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f96f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f99b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001faa4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f883`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f96f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f99b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001faa4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f8b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f9d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f9e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fa4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fa6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001faf1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fb02`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f8b4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f9d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f9e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fa4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fa6f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001faf1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fb02`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001f8f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001f8f9`

## string_xrefs

- `0x18001f892`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001f9bc`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001fa1e`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001fac6`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v18; // [rsp+68h] [rbp-98h] BYREF
  HKEY v19; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchName; // [rsp+80h] [rbp-80h] BYREF
  HKEY v22; // [rsp+88h] [rbp-78h] BYREF
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
        v18 = 0;
        if ( !RegOpenKeyExW(HKEY_USERS, Name, 0, 0xF003Fu, &v18) )
        {
          v22 = 0;
          if ( !RegOpenKeyExW(v18, L"Software\\Microsoft\\EnterpriseModernAppManagement\\AppIDs", 0, 0xF003Fu, &v22) )
          {
            v9 = PackageManagerWrapper::DeleteInstallingProductIdKey(v8, v22);
            if ( v9 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x1D9,
                (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
                (const char *)(unsigned int)v9);
          }
          if ( v22 )
            RegCloseKey(v22);
        }
        v6 = v18;
        if ( v18 )
          RegCloseKey(v18);
      }
    }
  }
  v19 = 0;
  v18 = 0;
  HKLMStateSeparationRedirectionPath = EnterpriseModernAppManagement::GetHKLMStateSeparationRedirectionPath(
                                         v6,
                                         v5,
                                         &v18);
  v3 = HKLMStateSeparationRedirectionPath;
  if ( HKLMStateSeparationRedirectionPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EA,
      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
      (const char *)(unsigned int)HKLMStateSeparationRedirectionPath,
      phkResult);
    if ( v18 )
      LocalFree(v18);
    if ( v19 )
      RegCloseKey(v19);
    goto LABEL_4;
  }
  v11 = v19;
  if ( v19 )
  {
    LastError = GetLastError();
    RegCloseKey(v11);
    SetLastError(LastError);
  }
  v19 = 0;
  v13 = v18;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)v18, 0, 0xF013Fu, &v19) )
  {
    v15 = PackageManagerWrapper::DeleteInstallingProductIdKey(v14, v19);
    if ( v15 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1F4,
        (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
        (const char *)(unsigned int)v15);
  }
  if ( v13 )
    LocalFree(v13);
  if ( v19 )
    RegCloseKey(v19);
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18001f834  push    rbp
0x18001f836  push    rbx
0x18001f837  push    rsi
0x18001f838  push    rdi
0x18001f839  lea     rbp, [rsp-1B8h]
0x18001f841  sub     rsp, 2B8h
0x18001f848  mov     rax, cs:__security_cookie
0x18001f84f  xor     rax, rsp
0x18001f852  mov     [rbp+1D0h+var_30], rax
0x18001f859  xor     esi, esi
0x18001f85b  mov     [rsp+2D0h+cSubKeys], esi
0x18001f85f  mov     [rsp+2D0h+hKey], rsi
0x18001f864  lea     rax, [rsp+2D0h+hKey]
0x18001f869  mov     [rsp+2D0h+phkResult], rax; unsigned int
0x18001f86e  mov     r9d, 0F003Fh; samDesired
0x18001f874  xor     r8d, r8d; ulOptions
0x18001f877  xor     edx, edx; lpSubKey
0x18001f879  mov     rdi, 0FFFFFFFF80000003h
0x18001f880  mov     rcx, rdi; hKey
0x18001f883  call    cs:__imp_RegOpenKeyExW
0x18001f889  test    eax, eax
0x18001f88b  jz      short loc_18001F8C1
0x18001f88d  mov     edx, 1A8h; void *
0x18001f892  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001f899  mov     r9d, eax; char *
0x18001f89c  mov     rcx, [rbp+1D8h]; this
0x18001f8a3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001f8a8  mov     ebx, eax
0x18001f8aa  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18001f8af  test    rcx, rcx
0x18001f8b2  jz      short loc_18001F8BA
0x18001f8b4  call    cs:__imp_RegCloseKey
0x18001f8ba  mov     eax, ebx
0x18001f8bc  jmp     loc_18001FB0A
0x18001f8c1  mov     [rsp+2D0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18001f8c6  mov     [rsp+2D0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18001f8cb  mov     [rsp+2D0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x18001f8d0  mov     [rsp+2D0h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x18001f8d5  mov     [rsp+2D0h+lpcValues], rsi; lpcValues
0x18001f8da  mov     [rsp+2D0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x18001f8df  mov     [rsp+2D0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x18001f8e4  lea     rax, [rsp+2D0h+cSubKeys]
0x18001f8e9  mov     [rsp+2D0h+phkResult], rax; lpcSubKeys
0x18001f8ee  xor     r9d, r9d; lpReserved
0x18001f8f1  xor     r8d, r8d; lpcchClass
0x18001f8f4  xor     edx, edx; lpClass
0x18001f8f6  mov     rcx, rdi; hKey
0x18001f8f9  call    cs:__imp_RegQueryInfoKeyW
0x18001f8ff  test    eax, eax
0x18001f901  jz      short loc_18001F90A
0x18001f903  mov     edx, 1B5h
0x18001f908  jmp     short loc_18001F892
0x18001f90a  mov     eax, [rsp+2D0h+cSubKeys]
0x18001f90e  test    eax, eax
0x18001f910  jz      loc_18001F9FA
0x18001f916  mov     ebx, esi
0x18001f918  mov     [rbp+1D0h+cchName], 104h
0x18001f91f  mov     [rsp+2D0h+lpcValues], rsi; lpftLastWriteTime
0x18001f924  mov     [rsp+2D0h+lpcbMaxClassLen], rsi; lpcchClass
0x18001f929  mov     [rsp+2D0h+lpcbMaxSubKeyLen], rsi; lpClass
0x18001f92e  mov     [rsp+2D0h+phkResult], rsi; lpReserved
0x18001f933  lea     r9, [rbp+1D0h+cchName]; lpcchName
0x18001f937  lea     r8, [rbp+1D0h+Name]; lpName
0x18001f93b  mov     edx, ebx; dwIndex
0x18001f93d  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18001f942  call    cs:__imp_RegEnumKeyExW
0x18001f948  test    eax, eax
0x18001f94a  jnz     loc_18001F9EE
0x18001f950  mov     [rsp+2D0h+var_268], rsi
0x18001f955  lea     rax, [rsp+2D0h+var_268]
0x18001f95a  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18001f95f  mov     r9d, 0F003Fh; samDesired
0x18001f965  xor     r8d, r8d; ulOptions
0x18001f968  lea     rdx, [rbp+1D0h+Name]; lpSubKey
0x18001f96c  mov     rcx, rdi; hKey
0x18001f96f  call    cs:__imp_RegOpenKeyExW
0x18001f975  test    eax, eax
0x18001f977  jnz     short loc_18001F9DE
0x18001f979  mov     [rbp+1D0h+var_248], rsi
0x18001f97d  lea     rax, [rbp+1D0h+var_248]
0x18001f981  mov     [rsp+2D0h+phkResult], rax; int
0x18001f986  mov     r9d, 0F003Fh; samDesired
0x18001f98c  xor     r8d, r8d; ulOptions
0x18001f98f  lea     rdx, ?c_AppIDsRegistryPath@EnterpriseModernAppManagement@@3QBGB; "Software\\Microsoft\\EnterpriseModernAp"...
0x18001f996  mov     rcx, [rsp+2D0h+var_268]; hKey
0x18001f99b  call    cs:__imp_RegOpenKeyExW
0x18001f9a1  test    eax, eax
0x18001f9a3  jnz     short loc_18001F9CE
0x18001f9a5  mov     rdx, [rbp+1D0h+var_248]; HKEY
0x18001f9a9  call    ?DeleteInstallingProductIdKey@PackageManagerWrapper@@AEAAJPEAUHKEY__@@@Z; PackageManagerWrapper::DeleteInstallingProductIdKey(HKEY__ *)
0x18001f9ae  mov     rcx, [rbp+1D8h]; this
0x18001f9b5  test    eax, eax
0x18001f9b7  jns     short loc_18001F9CE
0x18001f9b9  mov     r9d, eax; char *
0x18001f9bc  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001f9c3  mov     edx, 1D9h; void *
0x18001f9c8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001f9cd  nop
0x18001f9ce  mov     rcx, [rbp+1D0h+var_248]; hKey
0x18001f9d2  test    rcx, rcx
0x18001f9d5  jz      short loc_18001F9DE
0x18001f9d7  call    cs:__imp_RegCloseKey
0x18001f9dd  nop
0x18001f9de  mov     rcx, [rsp+2D0h+var_268]; hKey
0x18001f9e3  test    rcx, rcx
0x18001f9e6  jz      short loc_18001F9EE
0x18001f9e8  call    cs:__imp_RegCloseKey
0x18001f9ee  inc     ebx
0x18001f9f0  cmp     ebx, [rsp+2D0h+cSubKeys]
0x18001f9f4  jb      loc_18001F918
0x18001f9fa  mov     [rsp+2D0h+var_260], rsi
0x18001f9ff  mov     [rsp+2D0h+var_268], rsi
0x18001fa04  lea     r8, [rsp+2D0h+var_268]
0x18001fa09  call    ?GetHKLMStateSeparationRedirectionPath@EnterpriseModernAppManagement@@YAJPEBG0AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; EnterpriseModernAppManagement::GetHKLMStateSeparationRedirectionPath(ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18001fa0e  mov     ebx, eax
0x18001fa10  test    eax, eax
0x18001fa12  jns     short loc_18001FA5A
0x18001fa14  mov     rcx, [rbp+1D8h]; this
0x18001fa1b  mov     r9d, eax; char *
0x18001fa1e  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001fa25  mov     edx, 1EAh; void *
0x18001fa2a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fa2f  nop
0x18001fa30  mov     rcx, [rsp+2D0h+var_268]; hMem
0x18001fa35  test    rcx, rcx
0x18001fa38  jz      short loc_18001FA41
0x18001fa3a  call    cs:__imp_LocalFree
0x18001fa40  nop
0x18001fa41  mov     rcx, [rsp+2D0h+var_260]; hKey
0x18001fa46  test    rcx, rcx
0x18001fa49  jz      loc_18001F8AA
0x18001fa4f  call    cs:__imp_RegCloseKey
0x18001fa55  jmp     loc_18001F8AA
0x18001fa5a  mov     rdi, [rsp+2D0h+var_260]
0x18001fa5f  test    rdi, rdi
0x18001fa62  jz      short loc_18001FA7D
0x18001fa64  call    cs:__imp_GetLastError
0x18001fa6a  mov     ebx, eax
0x18001fa6c  mov     rcx, rdi; hKey
0x18001fa6f  call    cs:__imp_RegCloseKey
0x18001fa75  mov     ecx, ebx; dwErrCode
0x18001fa77  call    cs:__imp_SetLastError
0x18001fa7d  mov     [rsp+2D0h+var_260], rsi
0x18001fa82  lea     rax, [rsp+2D0h+var_260]
0x18001fa87  mov     [rsp+2D0h+phkResult], rax; int
0x18001fa8c  mov     r9d, 0F013Fh; samDesired
0x18001fa92  xor     r8d, r8d; ulOptions
0x18001fa95  mov     rbx, [rsp+2D0h+var_268]
0x18001fa9a  mov     rdx, rbx; lpSubKey
0x18001fa9d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001faa4  call    cs:__imp_RegOpenKeyExW
0x18001faaa  test    eax, eax
0x18001faac  jnz     short loc_18001FAD8
0x18001faae  mov     rdx, [rsp+2D0h+var_260]; HKEY
0x18001fab3  call    ?DeleteInstallingProductIdKey@PackageManagerWrapper@@AEAAJPEAUHKEY__@@@Z; PackageManagerWrapper::DeleteInstallingProductIdKey(HKEY__ *)
0x18001fab8  mov     rcx, [rbp+1D8h]; this
0x18001fabf  test    eax, eax
0x18001fac1  jns     short loc_18001FAD8
0x18001fac3  mov     r9d, eax; char *
0x18001fac6  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001facd  mov     edx, 1F4h; void *
0x18001fad2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001fad7  nop
0x18001fad8  test    rbx, rbx
0x18001fadb  jz      short loc_18001FAE7
0x18001fadd  mov     rcx, rbx; hMem
0x18001fae0  call    cs:__imp_LocalFree
0x18001fae6  nop
0x18001fae7  mov     rcx, [rsp+2D0h+var_260]; hKey
0x18001faec  test    rcx, rcx
0x18001faef  jz      short loc_18001FAF8
0x18001faf1  call    cs:__imp_RegCloseKey
0x18001faf7  nop
0x18001faf8  mov     rcx, [rsp+2D0h+hKey]; hKey
0x18001fafd  test    rcx, rcx
0x18001fb00  jz      short loc_18001FB08
0x18001fb02  call    cs:__imp_RegCloseKey
0x18001fb08  xor     eax, eax
0x18001fb0a  mov     rcx, [rbp+1D0h+var_30]
0x18001fb11  xor     rcx, rsp; StackCookie
0x18001fb14  call    __security_check_cookie
0x18001fb19  add     rsp, 2B8h
0x18001fb20  pop     rdi
0x18001fb21  pop     rsi
0x18001fb22  pop     rbx
0x18001fb23  pop     rbp
0x18001fb24  retn
```
