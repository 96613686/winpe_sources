# GetProvisioningDiagnosticsFolderPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x140004a60`
- end: `0x140004de7`
- name: `?GetProvisioningDiagnosticsFolderPath@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `903`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140008130`

## callees

- `0x140002e60`
- `0x140002f94`
- `0x1400033f8`
- `0x140003418`
- `0x1400035ac`
- `0x140004a60`
- `0x140006244`
- `0x140007204`
- `0x140007f64`
- `0x140009696`
- `0x1400096d0`

## import_xrefs

- `msvcrt!wprintf` at `0x140004ae2`
- `msvcrt!wprintf` at `0x140004b51`
- `msvcrt!wprintf` at `0x140004bca`
- `msvcrt!wprintf` at `0x140004bf2`
- `msvcrt!wprintf` at `0x140004c51`
- `msvcrt!wprintf` at `0x140004d12`
- `msvcrt!wprintf` at `0x140004ae2`
- `msvcrt!wprintf` at `0x140004b51`
- `msvcrt!wprintf` at `0x140004bca`
- `msvcrt!wprintf` at `0x140004bf2`
- `msvcrt!wprintf` at `0x140004c51`
- `msvcrt!wprintf` at `0x140004d12`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004aba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004aba`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140004baa`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140004baa`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140004b31`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140004b31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004c33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004c33`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140004c29`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140004c29`

## string_xrefs

- `0x140004adb`: `\nFailed to collect logs. Cannot open DeviceProvisionning. Path:'%s', HResult:0x%08x\n`
- `0x140004b4a`: `\nFailed to collect logs. Cannot retreive filpath character count. HResult:0x%08x\n`
- `0x140004bc3`: `\nFailed to collect logs. Cannot retreive filepath. HResult:0x%08x\n`
- `0x140004d0b`: `\nFailed to collect logs. Invalid path name. path: %s`

## pseudocode

```c
__int64 __fastcall GetProvisioningDiagnosticsFolderPath(__int64 a1)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  const WCHAR *v5; // rbx
  LSTATUS v6; // eax
  unsigned int v7; // edi
  signed int LastError; // eax
  char *v9; // rax
  char *v10; // rcx
  __int64 v11; // rdx
  char *i; // rbx
  __int16 *v13; // r8
  char *v14; // r9
  char *v15; // rax
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  __int16 v24; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR lpValueName; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+78h] [rbp-88h] BYREF
  DWORD Type; // [rsp+7Ch] [rbp-84h] BYREF
  DWORD cchValueName; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v30[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v31[40]; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR Dst[264]; // [rsp+D0h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\MdmDiagnostics\\Area\\DeviceProvisioning\\FileEntry",
         0,
         0x20019u,
         &hKey);
  v3 = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      v3 = (unsigned __int16)v2 | 0x80070000;
    wprintf(
      L"\nFailed to collect logs. Cannot open DeviceProvisionning. Path:'%s', HResult:0x%08x\n",
      L"SOFTWARE\\Microsoft\\MdmDiagnostics\\Area\\DeviceProvisioning\\FileEntry",
      v3);
    goto LABEL_43;
  }
  Type = 0;
  cbMaxValueNameLen = 0;
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueNameLen, 0, 0, 0);
  v3 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v3 = (unsigned __int16)v4 | 0x80070000;
    wprintf(L"\nFailed to collect logs. Cannot retreive filpath character count. HResult:0x%08x\n", v3);
    goto LABEL_43;
  }
  cchValueName = cbMaxValueNameLen + 1;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpValueName,
    0,
    cbMaxValueNameLen + 1);
  v5 = lpValueName;
  if ( !lpValueName )
  {
    v3 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDC,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\exe\\main.cpp",
      (const char *)0x8007000ELL,
      phkResult);
LABEL_42:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpValueName);
    goto LABEL_43;
  }
  v6 = RegEnumValueW(hKey, 0, lpValueName, &cchValueName, 0, &Type, 0, 0);
  v7 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v7 = (unsigned __int16)v6 | 0x80070000;
    wprintf(L"\nFailed to collect logs. Cannot retreive filepath. HResult:0x%08x\n", v7);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpValueName);
    v3 = v7;
    goto LABEL_43;
  }
  if ( Type != 4 )
  {
    wprintf(L"\nInvalid type, expected REG_DWORD. type:%d\n");
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpValueName);
    v3 = 0;
    goto LABEL_43;
  }
  memset_0(Dst, 0, 0x20Au);
  if ( !ExpandEnvironmentStringsW(v5, Dst, 0x104u) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    wprintf(L"\nUnable to expand environment variables. HResult:0x%08x", v3);
    goto LABEL_42;
  }
  v9 = (char *)std::wstring::wstring(v30, Dst);
  v10 = v9;
  v24 = 92;
  v11 = *((_QWORD *)v9 + 2);
  if ( v11 )
  {
    if ( *((_QWORD *)v9 + 3) >= 8u )
      v9 = *(char **)v9;
    for ( i = &v9[2 * v11 - 2]; *(_WORD *)i != 92; i -= 2 )
    {
LABEL_29:
      if ( *((_QWORD *)v10 + 3) < 8u )
        v15 = v10;
      else
        v15 = *(char **)v10;
      if ( i == v15 )
        goto LABEL_37;
    }
    v11 = 1;
    v13 = &v24;
    v14 = i;
    while ( v11 )
    {
      if ( *(_WORD *)v14 != *v13 )
        goto LABEL_29;
      v14 += 2;
      ++v13;
      --v11;
    }
    if ( *((_QWORD *)v10 + 3) >= 8u )
      v10 = *(char **)v10;
    v16 = (i - v10) >> 1;
  }
  else
  {
LABEL_37:
    v16 = -1;
  }
  LOBYTE(v11) = 1;
  std::wstring::_Tidy(v30, v11, 0);
  if ( v16 != -1 )
  {
    v17 = std::wstring::wstring(v31, Dst);
    v19 = std::wstring::substr(v17, v30, v18, v16);
    std::wstring::operator=(a1, v19);
    LOBYTE(v20) = 1;
    std::wstring::_Tidy(v30, v20, 0);
    LOBYTE(v21) = 1;
    std::wstring::_Tidy(v31, v21, 0);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpValueName);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return 0;
  }
  wprintf(L"\nFailed to collect logs. Invalid path name. path: %s", Dst);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpValueName);
  v3 = -2147024809;
LABEL_43:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v3;
}

```

## disassembly

```asm
0x140004a60  mov     [rsp-8+arg_8], rbx
0x140004a65  mov     [rsp-8+arg_10], rsi
0x140004a6a  push    rbp
0x140004a6b  push    rdi
0x140004a6c  push    r14
0x140004a6e  lea     rbp, [rsp-1F0h]
0x140004a76  sub     rsp, 2F0h
0x140004a7d  mov     rax, cs:__security_cookie
0x140004a84  xor     rax, rsp
0x140004a87  mov     [rbp+200h+var_20], rax
0x140004a8e  mov     rsi, rcx
0x140004a91  xor     r14d, r14d
0x140004a94  mov     [rsp+300h+hKey], r14
0x140004a99  lea     rax, [rsp+300h+hKey]
0x140004a9e  mov     [rsp+300h+phkResult], rax; phkResult
0x140004aa3  mov     r9d, 20019h; samDesired
0x140004aa9  xor     r8d, r8d; ulOptions
0x140004aac  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\MdmDiagnostics\\Ar"...
0x140004ab3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140004aba  call    cs:__imp_RegOpenKeyExW
0x140004ac0  mov     ebx, eax
0x140004ac2  test    eax, eax
0x140004ac4  jz      short loc_140004AED
0x140004ac6  jle     short loc_140004AD1
0x140004ac8  movzx   ebx, ax
0x140004acb  or      ebx, 80070000h
0x140004ad1  mov     r8d, ebx
0x140004ad4  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\MdmDiagnostics\\Ar"...
0x140004adb  lea     rcx, aFailedToCollec_2; "\nFailed to collect logs. Cannot open D"...
0x140004ae2  call    cs:__imp_wprintf
0x140004ae8  jmp     loc_140004DB4
0x140004aed  mov     [rsp+300h+Type], r14d
0x140004af2  mov     [rsp+300h+cbMaxValueNameLen], r14d
0x140004af7  mov     [rsp+300h+lpftLastWriteTime], r14; lpftLastWriteTime
0x140004afc  mov     [rsp+300h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x140004b01  mov     [rsp+300h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x140004b06  lea     rax, [rsp+300h+cbMaxValueNameLen]
0x140004b0b  mov     [rsp+300h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x140004b10  mov     [rsp+300h+lpcValues], r14; lpcValues
0x140004b15  mov     [rsp+300h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x140004b1a  mov     [rsp+300h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x140004b1f  mov     [rsp+300h+phkResult], r14; int
0x140004b24  xor     r9d, r9d; lpReserved
0x140004b27  xor     r8d, r8d; lpcchClass
0x140004b2a  xor     edx, edx; lpClass
0x140004b2c  mov     rcx, [rsp+300h+hKey]; hKey
0x140004b31  call    cs:__imp_RegQueryInfoKeyW
0x140004b37  mov     ebx, eax
0x140004b39  test    eax, eax
0x140004b3b  jz      short loc_140004B5C
0x140004b3d  jle     short loc_140004B48
0x140004b3f  movzx   ebx, ax
0x140004b42  or      ebx, 80070000h
0x140004b48  mov     edx, ebx
0x140004b4a  lea     rcx, aFailedToCollec_3; "\nFailed to collect logs. Cannot retrei"...
0x140004b51  call    cs:__imp_wprintf
0x140004b57  jmp     loc_140004DB4
0x140004b5c  mov     eax, [rsp+300h+cbMaxValueNameLen]
0x140004b60  inc     eax
0x140004b62  mov     [rbp+200h+cchValueName], eax
0x140004b65  mov     r8d, eax
0x140004b68  xor     edx, edx
0x140004b6a  lea     rcx, [rsp+300h+lpValueName]
0x140004b6f  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140004b74  nop
0x140004b75  mov     rbx, [rsp+300h+lpValueName]
0x140004b7a  test    rbx, rbx
0x140004b7d  jz      loc_140004D88
0x140004b83  mov     [rsp+300h+lpcValues], r14; lpcbData
0x140004b88  mov     [rsp+300h+lpcbMaxClassLen], r14; lpData
0x140004b8d  lea     rax, [rsp+300h+Type]
0x140004b92  mov     [rsp+300h+lpcbMaxSubKeyLen], rax; lpType
0x140004b97  mov     [rsp+300h+phkResult], r14; lpReserved
0x140004b9c  lea     r9, [rbp+200h+cchValueName]; lpcchValueName
0x140004ba0  mov     r8, rbx; lpValueName
0x140004ba3  xor     edx, edx; dwIndex
0x140004ba5  mov     rcx, [rsp+300h+hKey]; hKey
0x140004baa  call    cs:__imp_RegEnumValueW
0x140004bb0  mov     edi, eax
0x140004bb2  test    eax, eax
0x140004bb4  jz      short loc_140004BE2
0x140004bb6  jle     short loc_140004BC1
0x140004bb8  movzx   edi, ax
0x140004bbb  or      edi, 80070000h
0x140004bc1  mov     edx, edi
0x140004bc3  lea     rcx, aFailedToCollec_4; "\nFailed to collect logs. Cannot retrei"...
0x140004bca  call    cs:__imp_wprintf
0x140004bd0  nop
0x140004bd1  lea     rcx, [rsp+300h+lpValueName]
0x140004bd6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140004bdb  mov     ebx, edi
0x140004bdd  jmp     loc_140004DB4
0x140004be2  mov     edx, [rsp+300h+Type]
0x140004be6  cmp     edx, 4
0x140004be9  jz      short loc_140004C0B
0x140004beb  lea     rcx, aInvalidTypeExp; "\nInvalid type, expected REG_DWORD. typ"...
0x140004bf2  call    cs:__imp_wprintf
0x140004bf8  nop
0x140004bf9  lea     rcx, [rsp+300h+lpValueName]
0x140004bfe  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140004c03  mov     ebx, r14d
0x140004c06  jmp     loc_140004DB4
0x140004c0b  xor     edx, edx; Val
0x140004c0d  mov     r8d, 20Ah; Size
0x140004c13  lea     rcx, [rbp+200h+Dst]; void *
0x140004c17  call    memset_0
0x140004c1c  mov     r8d, 104h; nSize
0x140004c22  lea     rdx, [rbp+200h+Dst]; lpDst
0x140004c26  mov     rcx, rbx; lpSrc
0x140004c29  call    cs:__imp_ExpandEnvironmentStringsW
0x140004c2f  test    eax, eax
0x140004c31  jnz     short loc_140004C5C
0x140004c33  call    cs:__imp_GetLastError
0x140004c39  mov     ebx, eax
0x140004c3b  test    eax, eax
0x140004c3d  jle     short loc_140004C48
0x140004c3f  movzx   ebx, ax
0x140004c42  or      ebx, 80070000h
0x140004c48  mov     edx, ebx
0x140004c4a  lea     rcx, aUnableToExpand; "\nUnable to expand environment variable"...
0x140004c51  call    cs:__imp_wprintf
0x140004c57  jmp     loc_140004DA9
0x140004c5c  lea     rdx, [rbp+200h+Dst]
0x140004c60  lea     rcx, [rbp+200h+var_278]
0x140004c64  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140004c69  mov     rcx, rax
0x140004c6c  mov     r10d, 5Ch ; '\'
0x140004c72  mov     [rsp+300h+var_2A0], r10w
0x140004c78  mov     rdx, [rax+10h]
0x140004c7c  cmp     rdx, 1
0x140004c80  jb      short loc_140004CEF
0x140004c82  cmp     qword ptr [rax+18h], 8
0x140004c87  jb      short loc_140004C8C
0x140004c89  mov     rax, [rax]
0x140004c8c  lea     rbx, [rdx-1]
0x140004c90  lea     rbx, [rax+rbx*2]
0x140004c94  cmp     [rbx], r10w
0x140004c98  jnz     short loc_140004CC3
0x140004c9a  mov     edx, 1
0x140004c9f  lea     r8, [rsp+300h+var_2A0]
0x140004ca4  mov     r9, rbx
0x140004ca7  test    rdx, rdx
0x140004caa  jz      short loc_140004CDD
0x140004cac  movzx   eax, word ptr [r8]
0x140004cb0  cmp     [r9], ax
0x140004cb4  jnz     short loc_140004CC3
0x140004cb6  add     r9, 2
0x140004cba  add     r8, 2
0x140004cbe  dec     rdx
0x140004cc1  jmp     short loc_140004CA7
0x140004cc3  cmp     qword ptr [rcx+18h], 8
0x140004cc8  jb      short loc_140004CCF
0x140004cca  mov     rax, [rcx]
0x140004ccd  jmp     short loc_140004CD2
0x140004ccf  mov     rax, rcx
0x140004cd2  cmp     rbx, rax
0x140004cd5  jz      short loc_140004CEF
0x140004cd7  sub     rbx, 2
0x140004cdb  jmp     short loc_140004C94
0x140004cdd  cmp     qword ptr [rcx+18h], 8
0x140004ce2  jb      short loc_140004CE7
0x140004ce4  mov     rcx, [rcx]
0x140004ce7  sub     rbx, rcx
0x140004cea  sar     rbx, 1
0x140004ced  jmp     short loc_140004CF3
0x140004cef  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140004cf3  xor     r8d, r8d
0x140004cf6  mov     dl, 1
0x140004cf8  lea     rcx, [rbp+200h+var_278]
0x140004cfc  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140004d01  lea     rdx, [rbp+200h+Dst]
0x140004d05  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140004d09  jnz     short loc_140004D2D
0x140004d0b  lea     rcx, aFailedToCollec; "\nFailed to collect logs. Invalid path "...
0x140004d12  call    cs:__imp_wprintf
0x140004d18  nop
0x140004d19  lea     rcx, [rsp+300h+lpValueName]
0x140004d1e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140004d23  mov     ebx, 80070057h
0x140004d28  jmp     loc_140004DB4
0x140004d2d  lea     rcx, [rbp+200h+var_258]
0x140004d31  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140004d36  nop
0x140004d37  mov     r9, rbx
0x140004d3a  lea     rdx, [rbp+200h+var_278]
0x140004d3e  mov     rcx, rax
0x140004d41  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x140004d46  mov     rdx, rax
0x140004d49  mov     rcx, rsi
0x140004d4c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140004d51  xor     r8d, r8d
0x140004d54  mov     dl, 1
0x140004d56  lea     rcx, [rbp+200h+var_278]
0x140004d5a  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140004d5f  nop
0x140004d60  xor     r8d, r8d
0x140004d63  mov     dl, 1
0x140004d65  lea     rcx, [rbp+200h+var_258]
0x140004d69  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140004d6e  nop
0x140004d6f  lea     rcx, [rsp+300h+lpValueName]
0x140004d74  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140004d79  nop
0x140004d7a  lea     rcx, [rsp+300h+hKey]
0x140004d7f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140004d84  xor     eax, eax
0x140004d86  jmp     short loc_140004DC0
0x140004d88  mov     rcx, [rbp+208h]; this
0x140004d8f  mov     ebx, 8007000Eh
0x140004d94  mov     r9d, ebx; char *
0x140004d97  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x140004d9e  mov     edx, 0DCh; void *
0x140004da3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004da8  nop
0x140004da9  lea     rcx, [rsp+300h+lpValueName]
0x140004dae  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140004db3  nop
0x140004db4  lea     rcx, [rsp+300h+hKey]
0x140004db9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140004dbe  mov     eax, ebx
0x140004dc0  mov     rcx, [rbp+200h+var_20]
0x140004dc7  xor     rcx, rsp; StackCookie
0x140004dca  call    __security_check_cookie
0x140004dcf  lea     r11, [rsp+300h+var_10]
0x140004dd7  mov     rbx, [r11+28h]
0x140004ddb  mov     rsi, [r11+30h]
0x140004ddf  mov     rsp, r11
0x140004de2  pop     r14
0x140004de4  pop     rdi
0x140004de5  pop     rbp
0x140004de6  retn
```
