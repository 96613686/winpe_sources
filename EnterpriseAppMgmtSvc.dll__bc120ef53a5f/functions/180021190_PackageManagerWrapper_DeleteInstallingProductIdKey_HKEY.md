# PackageManagerWrapper::DeleteInstallingProductIdKey(HKEY__ *)

- ea: `0x180021190`
- end: `0x18002150c`
- name: `?DeleteInstallingProductIdKey@PackageManagerWrapper@@AEAAJPEAUHKEY__@@@Z`
- size: `892`
- prototype: `int(PackageManagerWrapper *__hidden this, HKEY)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x180020e2c`

## callees

- `0x18001d050`
- `0x18001d160`
- `0x18001d65c`
- `0x18001ed24`
- `0x180021190`
- `0x180028154`
- `0x1800297a0`
- `0x18006c910`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180021403`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800214f6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180021403`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800214f6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800212b0`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800212b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800212f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800212f3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002132b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002141b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002143a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002132b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002141b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002143a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180021209`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180021209`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800214b7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800214b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021364`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180021364`

## string_xrefs

- `0x180021224`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18002130e`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x1800214d2`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PackageManagerWrapper::DeleteInstallingProductIdKey(PackageManagerWrapper *this, HKEY a2)
{
  unsigned int v3; // edi
  unsigned int v4; // eax
  DWORD v6; // eax
  DWORD i; // ebx
  unsigned int v8; // eax
  int v9; // ebx
  __int64 v10; // r8
  const char *v11; // r9
  __int64 j; // rbx
  const WCHAR *v13; // rdx
  LSTATUS v14; // eax
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-2C8h]
  unsigned int lpcSubKeysa; // [rsp+20h] [rbp-2C8h]
  DWORD cSubKeys; // [rsp+60h] [rbp-288h] BYREF
  BYTE Data[4]; // [rsp+64h] [rbp-284h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-280h] BYREF
  DWORD cchName; // [rsp+70h] [rbp-278h] BYREF
  DWORD cbData; // [rsp+74h] [rbp-274h] BYREF
  unsigned int v22; // [rsp+78h] [rbp-270h]
  __int128 v23; // [rsp+80h] [rbp-268h] BYREF
  __int64 v24; // [rsp+90h] [rbp-258h]
  LPCWSTR lpSubKey[2]; // [rsp+98h] [rbp-250h] BYREF
  __int64 v26; // [rsp+A8h] [rbp-240h]
  unsigned __int64 v27; // [rsp+B0h] [rbp-238h]
  WCHAR Name[264]; // [rsp+C0h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+0h]

  v3 = 0;
  cSubKeys = 0;
  v23 = 0;
  v24 = 0;
  v4 = RegQueryInfoKeyW(a2, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( v4 )
  {
    v3 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x210,
           (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
           (const char *)v4,
           lpcSubKeys);
  }
  else
  {
    v6 = cSubKeys;
    if ( cSubKeys )
    {
      for ( i = 0; i < v6; ++i )
      {
        cchName = 260;
        if ( !RegEnumKeyExW(a2, i, Name, &cchName, 0, 0, 0, 0) )
        {
          *(_DWORD *)Data = 0;
          cbData = 4;
          phkResult = 0;
          v8 = RegOpenKeyExW(a2, Name, 0, 0xF003Fu, &phkResult);
          if ( v8 )
          {
            v9 = wil::details::in1diag3::Return_Win32(
                   retaddr,
                   (void *)0x22B,
                   (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\"
                                 "packagemanager.cpp",
                   (const char *)v8,
                   lpcSubKeysa);
            if ( phkResult )
              RegCloseKey(phkResult);
            v3 = v9;
            goto LABEL_3;
          }
          if ( !RegQueryValueExW(phkResult, L"Status", 0, 0, Data, &cbData) && *(_DWORD *)Data == 1 )
          {
            v27 = 7;
            v26 = 0;
            LOWORD(lpSubKey[0]) = 0;
            if ( Name[0] )
            {
              v10 = -1;
              do
                ++v10;
              while ( Name[v10] );
            }
            try
            {
              std::wstring::assign(lpSubKey, Name);
              std::vector<std::wstring>::push_back(&v23, lpSubKey);
              if ( v27 >= 8 )
                operator delete((void *)lpSubKey[0]);
            }
            catch ( ... )
            {
              v22 = wil::details::in1diag3::Return_CaughtException(
                      retaddr,
                      (void *)0x23C,
                      (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmg"
                                    "mt\\packagemanager.cpp",
                      v11);
              if ( phkResult )
                RegCloseKey(phkResult);
              v3 = v22;
              goto LABEL_3;
            }
          }
          if ( phkResult )
            RegCloseKey(phkResult);
        }
        v6 = cSubKeys;
      }
    }
    for ( j = v23; j != *((_QWORD *)&v23 + 1); j += 32 )
    {
      v27 = 7;
      v26 = 0;
      LOWORD(lpSubKey[0]) = 0;
      std::wstring::assign(lpSubKey);
      v13 = (const WCHAR *)lpSubKey;
      if ( v27 >= 8 )
        v13 = lpSubKey[0];
      v14 = RegDeleteTreeW(a2, v13);
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x246,
          (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)(unsigned int)v14,
          lpcSubKeys);
      if ( v27 >= 8 )
        operator delete((void *)lpSubKey[0]);
    }
  }
LABEL_3:
  std::vector<std::wstring>::~vector<std::wstring>(&v23);
  return v3;
}

```

## disassembly

```asm
0x180021190  mov     [rsp+arg_0], rbx
0x180021195  mov     [rsp+arg_10], rsi
0x18002119a  push    rdi
0x18002119b  sub     rsp, 2E0h
0x1800211a2  mov     rax, cs:__security_cookie
0x1800211a9  xor     rax, rsp
0x1800211ac  mov     [rsp+2E8h+var_18], rax
0x1800211b4  mov     rsi, rdx
0x1800211b7  xor     edi, edi
0x1800211b9  mov     [rsp+2E8h+cSubKeys], edi
0x1800211bd  xorps   xmm0, xmm0
0x1800211c0  movdqu  [rsp+2E8h+var_268], xmm0
0x1800211c9  mov     [rsp+2E8h+var_258], rdi
0x1800211d1  mov     [rsp+2E8h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x1800211d6  mov     [rsp+2E8h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x1800211db  mov     [rsp+2E8h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x1800211e0  mov     [rsp+2E8h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x1800211e5  mov     [rsp+2E8h+lpcValues], rdi; lpcValues
0x1800211ea  mov     [rsp+2E8h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x1800211ef  mov     [rsp+2E8h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x1800211f4  lea     rax, [rsp+2E8h+cSubKeys]
0x1800211f9  mov     [rsp+2E8h+lpcSubKeys], rax; int
0x1800211fe  xor     r9d, r9d; lpReserved
0x180021201  xor     r8d, r8d; lpcchClass
0x180021204  xor     edx, edx; lpClass
0x180021206  mov     rcx, rsi; hKey
0x180021209  call    cs:__imp_RegQueryInfoKeyW
0x180021210  nop     dword ptr [rax+rax+00h]
0x180021215  test    eax, eax
0x180021217  jz      short loc_18002126C
0x180021219  mov     rcx, [rsp+2E8h]; this
0x180021221  mov     r9d, eax; char *
0x180021224  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18002122b  mov     edx, 210h; void *
0x180021230  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180021235  mov     edi, eax
0x180021237  lea     rcx, [rsp+2E8h+var_268]
0x18002123f  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x180021244  mov     eax, edi
0x180021246  mov     rcx, [rsp+2E8h+var_18]
0x18002124e  xor     rcx, rsp; StackCookie
0x180021251  call    __security_check_cookie
0x180021256  lea     r11, [rsp+2E8h+var_8]
0x18002125e  mov     rbx, [r11+10h]
0x180021262  mov     rsi, [r11+20h]
0x180021266  mov     rsp, r11
0x180021269  pop     rdi
0x18002126a  retn
0x18002126c  mov     eax, [rsp+2E8h+cSubKeys]
0x180021270  test    eax, eax
0x180021272  jz      loc_180021451
0x180021278  mov     ebx, edi
0x18002127a  cmp     ebx, eax
0x18002127c  jnb     loc_180021451
0x180021282  mov     [rsp+2E8h+cchName], 104h
0x18002128a  mov     [rsp+2E8h+lpcValues], rdi; lpftLastWriteTime
0x18002128f  mov     [rsp+2E8h+lpcbMaxClassLen], rdi; lpcchClass
0x180021294  mov     [rsp+2E8h+lpcbMaxSubKeyLen], rdi; lpClass
0x180021299  mov     [rsp+2E8h+lpcSubKeys], rdi; lpReserved
0x18002129e  lea     r9, [rsp+2E8h+cchName]; lpcchName
0x1800212a3  lea     r8, [rsp+2E8h+Name]; lpName
0x1800212ab  mov     edx, ebx; dwIndex
0x1800212ad  mov     rcx, rsi; hKey
0x1800212b0  call    cs:__imp_RegEnumKeyExW
0x1800212b7  nop     dword ptr [rax+rax+00h]
0x1800212bc  test    eax, eax
0x1800212be  jnz     loc_180021446
0x1800212c4  mov     dword ptr [rsp+2E8h+Data], edi
0x1800212c8  mov     [rsp+2E8h+cbData], 4
0x1800212d0  mov     [rsp+2E8h+phkResult], rdi
0x1800212d5  lea     rax, [rsp+2E8h+phkResult]
0x1800212da  mov     [rsp+2E8h+lpcSubKeys], rax; unsigned int
0x1800212df  mov     r9d, 0F003Fh; samDesired
0x1800212e5  xor     r8d, r8d; ulOptions
0x1800212e8  lea     rdx, [rsp+2E8h+Name]; lpSubKey
0x1800212f0  mov     rcx, rsi; hKey
0x1800212f3  call    cs:__imp_RegOpenKeyExW
0x1800212fa  nop     dword ptr [rax+rax+00h]
0x1800212ff  test    eax, eax
0x180021301  jz      short loc_18002133E
0x180021303  mov     rcx, [rsp+2E8h]; this
0x18002130b  mov     r9d, eax; char *
0x18002130e  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x180021315  mov     edx, 22Bh; void *
0x18002131a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002131f  mov     ebx, eax
0x180021321  mov     rcx, [rsp+2E8h+phkResult]; hKey
0x180021326  test    rcx, rcx
0x180021329  jz      short loc_180021337
0x18002132b  call    cs:__imp_RegCloseKey
0x180021332  nop     dword ptr [rax+rax+00h]
0x180021337  mov     edi, ebx
0x180021339  jmp     loc_180021237
0x18002133e  lea     rax, [rsp+2E8h+cbData]
0x180021343  mov     [rsp+2E8h+lpcbMaxSubKeyLen], rax; lpcbData
0x180021348  lea     rax, [rsp+2E8h+Data]
0x18002134d  mov     [rsp+2E8h+lpcSubKeys], rax; lpData
0x180021352  xor     r9d, r9d; lpType
0x180021355  xor     r8d, r8d; lpReserved
0x180021358  lea     rdx, ValueName; "Status"
0x18002135f  mov     rcx, [rsp+2E8h+phkResult]; hKey
0x180021364  call    cs:__imp_RegQueryValueExW
0x18002136b  nop     dword ptr [rax+rax+00h]
0x180021370  test    eax, eax
0x180021372  jnz     loc_180021430
0x180021378  cmp     dword ptr [rsp+2E8h+Data], 1
0x18002137d  jnz     loc_180021430
0x180021383  mov     [rsp+2E8h+var_238], 7
0x18002138f  mov     [rsp+2E8h+var_240], rdi
0x180021397  mov     word ptr [rsp+2E8h+lpSubKey], di
0x18002139f  cmp     [rsp+2E8h+Name], di
0x1800213a7  jnz     short loc_1800213AE
0x1800213a9  mov     r8, rdi
0x1800213ac  jmp     short loc_1800213C4
0x1800213ae  lea     rax, [rsp+2E8h+Name]
0x1800213b6  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800213ba  inc     r8
0x1800213bd  cmp     [rax+r8*2], di
0x1800213c2  jnz     short loc_1800213BA
0x1800213c4  lea     rdx, [rsp+2E8h+Name]; Src
0x1800213cc  lea     rcx, [rsp+2E8h+lpSubKey]; void *
0x1800213d4  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800213d9  nop
0x1800213da  lea     rdx, [rsp+2E8h+lpSubKey]
0x1800213e2  lea     rcx, [rsp+2E8h+var_268]
0x1800213ea  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x1800213ef  nop
0x1800213f0  cmp     [rsp+2E8h+var_238], 8
0x1800213f9  jb      short loc_18002140F
0x1800213fb  mov     rcx, [rsp+2E8h+lpSubKey]
0x180021403  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002140a  nop     dword ptr [rax+rax+00h]
0x18002140f  jmp     short loc_180021430
0x180021411  mov     rcx, [rsp+2E8h+phkResult]; hKey
0x180021416  test    rcx, rcx
0x180021419  jz      short loc_180021427
0x18002141b  call    cs:__imp_RegCloseKey
0x180021422  nop     dword ptr [rax+rax+00h]
0x180021427  mov     edi, [rsp+2E8h+var_270]
0x18002142b  jmp     loc_180021237
0x180021430  mov     rcx, [rsp+2E8h+phkResult]; hKey
0x180021435  test    rcx, rcx
0x180021438  jz      short loc_180021446
0x18002143a  call    cs:__imp_RegCloseKey
0x180021441  nop     dword ptr [rax+rax+00h]
0x180021446  inc     ebx
0x180021448  mov     eax, [rsp+2E8h+cSubKeys]
0x18002144c  jmp     loc_18002127A
0x180021451  mov     rbx, qword ptr [rsp+2E8h+var_268]
0x180021459  cmp     rbx, qword ptr [rsp+2E8h+var_268+8]
0x180021461  jz      loc_180021237
0x180021467  mov     [rsp+2E8h+var_238], 7
0x180021473  mov     [rsp+2E8h+var_240], rdi
0x18002147b  mov     word ptr [rsp+2E8h+lpSubKey], di
0x180021483  or      r9, 0FFFFFFFFFFFFFFFFh
0x180021487  xor     r8d, r8d
0x18002148a  mov     rdx, rbx
0x18002148d  lea     rcx, [rsp+2E8h+lpSubKey]; void *
0x180021495  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18002149a  lea     rdx, [rsp+2E8h+lpSubKey]
0x1800214a2  cmp     [rsp+2E8h+var_238], 8
0x1800214ab  cmovnb  rdx, [rsp+2E8h+lpSubKey]; lpSubKey
0x1800214b4  mov     rcx, rsi; hKey
0x1800214b7  call    cs:__imp_RegDeleteTreeW
0x1800214be  nop     dword ptr [rax+rax+00h]
0x1800214c3  test    eax, eax
0x1800214c5  jns     short loc_1800214E3
0x1800214c7  mov     rcx, [rsp+2E8h]; this
0x1800214cf  mov     r9d, eax; char *
0x1800214d2  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x1800214d9  mov     edx, 246h; void *
0x1800214de  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800214e3  cmp     [rsp+2E8h+var_238], 8
0x1800214ec  jb      short loc_180021502
0x1800214ee  mov     rcx, [rsp+2E8h+lpSubKey]
0x1800214f6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800214fd  nop     dword ptr [rax+rax+00h]
0x180021502  add     rbx, 20h ; ' '
0x180021506  jmp     loc_180021459
```
