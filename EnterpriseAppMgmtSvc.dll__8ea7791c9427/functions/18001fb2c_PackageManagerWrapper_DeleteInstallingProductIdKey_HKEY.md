# PackageManagerWrapper::DeleteInstallingProductIdKey(HKEY__ *)

- ea: `0x18001fb2c`
- end: `0x18001fe6b`
- name: `?DeleteInstallingProductIdKey@PackageManagerWrapper@@AEAAJPEAUHKEY__@@@Z`
- size: `831`
- prototype: `__int64 __fastcall(PackageManagerWrapper *this, HKEY)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, installer_update`

## callers

- `0x18001f834`

## callees

- `0x18001bdfc`
- `0x18001bf0c`
- `0x18001c5b8`
- `0x18001d914`
- `0x18001fb2c`
- `0x18002636c`
- `0x180027668`
- `0x180066df0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001fd80`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fe5b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fd80`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001fe5b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001fc45`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001fc45`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fc82`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fc82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fcb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fd92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fdab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fcb4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fd92`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fdab`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001fba5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001fba5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001fe22`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001fe22`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001fce7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001fce7`

## string_xrefs

- `0x18001fbba`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001fc97`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`
- `0x18001fe37`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\enterpriseappmgmt\packagemanager.cpp`

## pseudocode

```c
__int64 __fastcall PackageManagerWrapper::DeleteInstallingProductIdKey(PackageManagerWrapper *this, HKEY a2)
{
  unsigned int v3; // edi
  unsigned int v4; // eax
  DWORD v6; // eax
  DWORD i; // ebx
  unsigned int v8; // eax
  int v9; // ebx
  unsigned __int64 v10; // r8
  const char *v11; // r9
  void **j; // rbx
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
            else
            {
              v10 = 0;
            }
            try
            {
              std::wstring::assign(lpSubKey, (char *)Name, v10);
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
    for ( j = (void **)v23; j != *((void ***)&v23 + 1); j += 4 )
    {
      v27 = 7;
      v26 = 0;
      LOWORD(lpSubKey[0]) = 0;
      std::wstring::assign((void **)lpSubKey, j, 0, 0xFFFFFFFFFFFFFFFFuLL);
      v13 = (const WCHAR *)lpSubKey;
      if ( v27 >= 8 )
        v13 = lpSubKey[0];
      v14 = RegDeleteTreeW(a2, v13);
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x246,
          (int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\enterpriseappmgmt\\packagemanager.cpp",
          (const char *)(unsigned int)v14);
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
0x18001fb2c  mov     [rsp+arg_0], rbx
0x18001fb31  mov     [rsp+arg_10], rsi
0x18001fb36  push    rdi
0x18001fb37  sub     rsp, 2E0h
0x18001fb3e  mov     rax, cs:__security_cookie
0x18001fb45  xor     rax, rsp
0x18001fb48  mov     [rsp+2E8h+var_18], rax
0x18001fb50  mov     rsi, rdx
0x18001fb53  xor     edi, edi
0x18001fb55  mov     [rsp+2E8h+cSubKeys], edi
0x18001fb59  xorps   xmm0, xmm0
0x18001fb5c  movdqu  [rsp+2E8h+var_268], xmm0
0x18001fb65  mov     [rsp+2E8h+var_258], rdi
0x18001fb6d  mov     [rsp+2E8h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18001fb72  mov     [rsp+2E8h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x18001fb77  mov     [rsp+2E8h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x18001fb7c  mov     [rsp+2E8h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x18001fb81  mov     [rsp+2E8h+lpcValues], rdi; lpcValues
0x18001fb86  mov     [rsp+2E8h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x18001fb8b  mov     [rsp+2E8h+lpcbMaxSubKeyLen], rdi; lpcbMaxSubKeyLen
0x18001fb90  lea     rax, [rsp+2E8h+cSubKeys]
0x18001fb95  mov     [rsp+2E8h+lpcSubKeys], rax; int
0x18001fb9a  xor     r9d, r9d; lpReserved
0x18001fb9d  xor     r8d, r8d; lpcchClass
0x18001fba0  xor     edx, edx; lpClass
0x18001fba2  mov     rcx, rsi; hKey
0x18001fba5  call    cs:__imp_RegQueryInfoKeyW
0x18001fbab  test    eax, eax
0x18001fbad  jz      short loc_18001FC01
0x18001fbaf  mov     rcx, [rsp+2E8h]; this
0x18001fbb7  mov     r9d, eax; char *
0x18001fbba  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001fbc1  mov     edx, 210h; void *
0x18001fbc6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001fbcb  mov     edi, eax
0x18001fbcd  lea     rcx, [rsp+2E8h+var_268]
0x18001fbd5  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x18001fbda  mov     eax, edi
0x18001fbdc  mov     rcx, [rsp+2E8h+var_18]
0x18001fbe4  xor     rcx, rsp; StackCookie
0x18001fbe7  call    __security_check_cookie
0x18001fbec  lea     r11, [rsp+2E8h+var_8]
0x18001fbf4  mov     rbx, [r11+10h]
0x18001fbf8  mov     rsi, [r11+20h]
0x18001fbfc  mov     rsp, r11
0x18001fbff  pop     rdi
0x18001fc00  retn
0x18001fc01  mov     eax, [rsp+2E8h+cSubKeys]
0x18001fc05  test    eax, eax
0x18001fc07  jz      loc_18001FDBC
0x18001fc0d  mov     ebx, edi
0x18001fc0f  cmp     ebx, eax
0x18001fc11  jnb     loc_18001FDBC
0x18001fc17  mov     [rsp+2E8h+cchName], 104h
0x18001fc1f  mov     [rsp+2E8h+lpcValues], rdi; lpftLastWriteTime
0x18001fc24  mov     [rsp+2E8h+lpcbMaxClassLen], rdi; lpcchClass
0x18001fc29  mov     [rsp+2E8h+lpcbMaxSubKeyLen], rdi; lpClass
0x18001fc2e  mov     [rsp+2E8h+lpcSubKeys], rdi; lpReserved
0x18001fc33  lea     r9, [rsp+2E8h+cchName]; lpcchName
0x18001fc38  lea     r8, [rsp+2E8h+Name]; lpName
0x18001fc40  mov     edx, ebx; dwIndex
0x18001fc42  mov     rcx, rsi; hKey
0x18001fc45  call    cs:__imp_RegEnumKeyExW
0x18001fc4b  test    eax, eax
0x18001fc4d  jnz     loc_18001FDB1
0x18001fc53  mov     dword ptr [rsp+2E8h+Data], edi
0x18001fc57  mov     [rsp+2E8h+cbData], 4
0x18001fc5f  mov     [rsp+2E8h+phkResult], rdi
0x18001fc64  lea     rax, [rsp+2E8h+phkResult]
0x18001fc69  mov     [rsp+2E8h+lpcSubKeys], rax; unsigned int
0x18001fc6e  mov     r9d, 0F003Fh; samDesired
0x18001fc74  xor     r8d, r8d; ulOptions
0x18001fc77  lea     rdx, [rsp+2E8h+Name]; lpSubKey
0x18001fc7f  mov     rcx, rsi; hKey
0x18001fc82  call    cs:__imp_RegOpenKeyExW
0x18001fc88  test    eax, eax
0x18001fc8a  jz      short loc_18001FCC1
0x18001fc8c  mov     rcx, [rsp+2E8h]; this
0x18001fc94  mov     r9d, eax; char *
0x18001fc97  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001fc9e  mov     edx, 22Bh; void *
0x18001fca3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001fca8  mov     ebx, eax
0x18001fcaa  mov     rcx, [rsp+2E8h+phkResult]; hKey
0x18001fcaf  test    rcx, rcx
0x18001fcb2  jz      short loc_18001FCBA
0x18001fcb4  call    cs:__imp_RegCloseKey
0x18001fcba  mov     edi, ebx
0x18001fcbc  jmp     loc_18001FBCD
0x18001fcc1  lea     rax, [rsp+2E8h+cbData]
0x18001fcc6  mov     [rsp+2E8h+lpcbMaxSubKeyLen], rax; lpcbData
0x18001fccb  lea     rax, [rsp+2E8h+Data]
0x18001fcd0  mov     [rsp+2E8h+lpcSubKeys], rax; lpData
0x18001fcd5  xor     r9d, r9d; lpType
0x18001fcd8  xor     r8d, r8d; lpReserved
0x18001fcdb  lea     rdx, ValueName; "Status"
0x18001fce2  mov     rcx, [rsp+2E8h+phkResult]; hKey
0x18001fce7  call    cs:__imp_RegQueryValueExW
0x18001fced  test    eax, eax
0x18001fcef  jnz     loc_18001FDA1
0x18001fcf5  cmp     dword ptr [rsp+2E8h+Data], 1
0x18001fcfa  jnz     loc_18001FDA1
0x18001fd00  mov     [rsp+2E8h+var_238], 7
0x18001fd0c  mov     [rsp+2E8h+var_240], rdi
0x18001fd14  mov     word ptr [rsp+2E8h+lpSubKey], di
0x18001fd1c  cmp     [rsp+2E8h+Name], di
0x18001fd24  jnz     short loc_18001FD2B
0x18001fd26  mov     r8, rdi
0x18001fd29  jmp     short loc_18001FD41
0x18001fd2b  lea     rax, [rsp+2E8h+Name]
0x18001fd33  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001fd37  inc     r8
0x18001fd3a  cmp     [rax+r8*2], di
0x18001fd3f  jnz     short loc_18001FD37
0x18001fd41  lea     rdx, [rsp+2E8h+Name]; Src
0x18001fd49  lea     rcx, [rsp+2E8h+lpSubKey]; void *
0x18001fd51  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18001fd56  nop
0x18001fd57  lea     rdx, [rsp+2E8h+lpSubKey]
0x18001fd5f  lea     rcx, [rsp+2E8h+var_268]
0x18001fd67  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring const &)
0x18001fd6c  nop
0x18001fd6d  cmp     [rsp+2E8h+var_238], 8
0x18001fd76  jb      short loc_18001FD86
0x18001fd78  mov     rcx, [rsp+2E8h+lpSubKey]
0x18001fd80  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001fd86  jmp     short loc_18001FDA1
0x18001fd88  mov     rcx, [rsp+2E8h+phkResult]; hKey
0x18001fd8d  test    rcx, rcx
0x18001fd90  jz      short loc_18001FD98
0x18001fd92  call    cs:__imp_RegCloseKey
0x18001fd98  mov     edi, [rsp+2E8h+var_270]
0x18001fd9c  jmp     loc_18001FBCD
0x18001fda1  mov     rcx, [rsp+2E8h+phkResult]; hKey
0x18001fda6  test    rcx, rcx
0x18001fda9  jz      short loc_18001FDB1
0x18001fdab  call    cs:__imp_RegCloseKey
0x18001fdb1  inc     ebx
0x18001fdb3  mov     eax, [rsp+2E8h+cSubKeys]
0x18001fdb7  jmp     loc_18001FC0F
0x18001fdbc  mov     rbx, qword ptr [rsp+2E8h+var_268]
0x18001fdc4  cmp     rbx, qword ptr [rsp+2E8h+var_268+8]
0x18001fdcc  jz      loc_18001FBCD
0x18001fdd2  mov     [rsp+2E8h+var_238], 7
0x18001fdde  mov     [rsp+2E8h+var_240], rdi
0x18001fde6  mov     word ptr [rsp+2E8h+lpSubKey], di
0x18001fdee  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001fdf2  xor     r8d, r8d
0x18001fdf5  mov     rdx, rbx
0x18001fdf8  lea     rcx, [rsp+2E8h+lpSubKey]; void *
0x18001fe00  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001fe05  lea     rdx, [rsp+2E8h+lpSubKey]
0x18001fe0d  cmp     [rsp+2E8h+var_238], 8
0x18001fe16  cmovnb  rdx, [rsp+2E8h+lpSubKey]; lpSubKey
0x18001fe1f  mov     rcx, rsi; hKey
0x18001fe22  call    cs:__imp_RegDeleteTreeW
0x18001fe28  test    eax, eax
0x18001fe2a  jns     short loc_18001FE48
0x18001fe2c  mov     rcx, [rsp+2E8h]; this
0x18001fe34  mov     r9d, eax; char *
0x18001fe37  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18001fe3e  mov     edx, 246h; void *
0x18001fe43  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001fe48  cmp     [rsp+2E8h+var_238], 8
0x18001fe51  jb      short loc_18001FE61
0x18001fe53  mov     rcx, [rsp+2E8h+lpSubKey]
0x18001fe5b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001fe61  add     rbx, 20h ; ' '
0x18001fe65  jmp     loc_18001FDC4
```
