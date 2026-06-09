# GetProvisioningDiagnosticsFolderPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x140004d3c`
- end: `0x140005079`
- name: `?GetProvisioningDiagnosticsFolderPath@@YAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `829`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140008694`

## callees

- `0x140002ee4`
- `0x140003028`
- `0x140003450`
- `0x140003474`
- `0x14000363c`
- `0x140004d3c`
- `0x1400065e4`
- `0x140007610`
- `0x1400083ac`
- `0x140008448`
- `0x140009cc6`
- `0x140009d00`

## import_xrefs

- `msvcrt!wprintf` at `0x140004dc4`
- `msvcrt!wprintf` at `0x140004e3f`
- `msvcrt!wprintf` at `0x140004ef0`
- `msvcrt!wprintf` at `0x140004f1e`
- `msvcrt!wprintf` at `0x140004f81`
- `msvcrt!wprintf` at `0x140004fd8`
- `msvcrt!wprintf` at `0x140004dc4`
- `msvcrt!wprintf` at `0x140004e3f`
- `msvcrt!wprintf` at `0x140004ef0`
- `msvcrt!wprintf` at `0x140004f1e`
- `msvcrt!wprintf` at `0x140004f81`
- `msvcrt!wprintf` at `0x140004fd8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004d96`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004d96`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140004eca`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x140004eca`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140004e19`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140004e19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004f5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004f5d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140004f4d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x140004f4d`

## string_xrefs

- `0x140004dbd`: `\nFailed to collect logs. Cannot open DeviceProvisionning. Path:'%s', HResult:0x%08x\n`
- `0x140004e38`: `\nFailed to collect logs. Cannot retreive filpath character count. HResult:0x%08x\n`
- `0x140004ee9`: `\nFailed to collect logs. Cannot retreive filepath. HResult:0x%08x\n`
- `0x140004fd1`: `\nFailed to collect logs. Invalid path name. path: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetProvisioningDiagnosticsFolderPath(__int64 a1)
{
  LSTATUS v2; // eax
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  const WCHAR *v5; // rbx
  LSTATUS v6; // eax
  unsigned int v7; // edi
  signed int LastError; // eax
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rdx
  int phkResult; // [rsp+20h] [rbp-E0h]
  __int16 v19; // [rsp+60h] [rbp-A0h] BYREF
  LPWSTR lpValueName; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+70h] [rbp-90h] BYREF
  DWORD Type; // [rsp+74h] [rbp-8Ch] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  DWORD cchValueName; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v25[32]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v26[40]; // [rsp+A8h] [rbp-58h] BYREF
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
    goto LABEL_26;
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
    goto LABEL_26;
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
LABEL_11:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpValueName);
    goto LABEL_26;
  }
  v6 = RegEnumValueW(hKey, 0, lpValueName, &cchValueName, 0, &Type, 0, 0);
  v7 = v6;
  if ( !v6 )
  {
    if ( Type == 4 )
    {
      memset_0(Dst, 0, 0x20Au);
      if ( !ExpandEnvironmentStringsW(v5, Dst, 0x104u) )
      {
        LastError = GetLastError();
        v3 = LastError;
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
        wprintf(L"\nUnable to expand environment variables. HResult:0x%08x", v3);
        goto LABEL_11;
      }
      v9 = std::wstring::wstring(v25, Dst);
      v19 = 92;
      v10 = std::wstring::rfind(v9, &v19);
      LOBYTE(v11) = 1;
      std::wstring::_Tidy(v25, v11, 0);
      if ( v10 == -1 )
      {
        wprintf(L"\nFailed to collect logs. Invalid path name. path: %s", Dst);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpValueName);
        v3 = -2147024809;
        goto LABEL_26;
      }
      v12 = std::wstring::wstring(v26, Dst);
      v14 = std::wstring::substr(v12, v25, v13, v10);
      std::wstring::operator=(a1, v14);
      LOBYTE(v15) = 1;
      std::wstring::_Tidy(v25, v15, 0);
      LOBYTE(v16) = 1;
      std::wstring::_Tidy(v26, v16, 0);
    }
    else
    {
      wprintf(L"\nInvalid type, expected REG_DWORD. type:%d\n");
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpValueName);
    v3 = 0;
    goto LABEL_26;
  }
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  wprintf(L"\nFailed to collect logs. Cannot retreive filepath. HResult:0x%08x\n", v7);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpValueName);
  v3 = v7;
LABEL_26:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v3;
}

```

## disassembly

```asm
0x140004d3c  mov     [rsp-8+arg_8], rbx
0x140004d41  mov     [rsp-8+arg_10], rsi
0x140004d46  push    rbp
0x140004d47  push    rdi
0x140004d48  push    r14
0x140004d4a  lea     rbp, [rsp-1F0h]
0x140004d52  sub     rsp, 2F0h
0x140004d59  mov     rax, cs:__security_cookie
0x140004d60  xor     rax, rsp
0x140004d63  mov     [rbp+200h+var_20], rax
0x140004d6a  mov     rsi, rcx
0x140004d6d  xor     r14d, r14d
0x140004d70  mov     [rsp+300h+hKey], r14
0x140004d75  lea     rax, [rsp+300h+hKey]
0x140004d7a  mov     [rsp+300h+phkResult], rax; phkResult
0x140004d7f  mov     r9d, 20019h; samDesired
0x140004d85  xor     r8d, r8d; ulOptions
0x140004d88  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\MdmDiagnostics\\Ar"...
0x140004d8f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140004d96  call    cs:__imp_RegOpenKeyExW
0x140004d9d  nop     dword ptr [rax+rax+00h]
0x140004da2  mov     ebx, eax
0x140004da4  test    eax, eax
0x140004da6  jz      short loc_140004DD5
0x140004da8  jle     short loc_140004DB3
0x140004daa  movzx   ebx, ax
0x140004dad  or      ebx, 80070000h
0x140004db3  mov     r8d, ebx
0x140004db6  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\MdmDiagnostics\\Ar"...
0x140004dbd  lea     rcx, aFailedToCollec_2; "\nFailed to collect logs. Cannot open D"...
0x140004dc4  call    cs:__imp_wprintf
0x140004dcb  nop     dword ptr [rax+rax+00h]
0x140004dd0  jmp     loc_140005045
0x140004dd5  mov     [rsp+300h+Type], r14d
0x140004dda  mov     [rsp+300h+cbMaxValueNameLen], r14d
0x140004ddf  mov     [rsp+300h+lpftLastWriteTime], r14; lpftLastWriteTime
0x140004de4  mov     [rsp+300h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x140004de9  mov     [rsp+300h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x140004dee  lea     rax, [rsp+300h+cbMaxValueNameLen]
0x140004df3  mov     [rsp+300h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x140004df8  mov     [rsp+300h+lpcValues], r14; lpcValues
0x140004dfd  mov     [rsp+300h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x140004e02  mov     [rsp+300h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x140004e07  mov     [rsp+300h+phkResult], r14; int
0x140004e0c  xor     r9d, r9d; lpReserved
0x140004e0f  xor     r8d, r8d; lpcchClass
0x140004e12  xor     edx, edx; lpClass
0x140004e14  mov     rcx, [rsp+300h+hKey]; hKey
0x140004e19  call    cs:__imp_RegQueryInfoKeyW
0x140004e20  nop     dword ptr [rax+rax+00h]
0x140004e25  mov     ebx, eax
0x140004e27  test    eax, eax
0x140004e29  jz      short loc_140004E50
0x140004e2b  jle     short loc_140004E36
0x140004e2d  movzx   ebx, ax
0x140004e30  or      ebx, 80070000h
0x140004e36  mov     edx, ebx
0x140004e38  lea     rcx, aFailedToCollec_3; "\nFailed to collect logs. Cannot retrei"...
0x140004e3f  call    cs:__imp_wprintf
0x140004e46  nop     dword ptr [rax+rax+00h]
0x140004e4b  jmp     loc_140005045
0x140004e50  mov     eax, [rsp+300h+cbMaxValueNameLen]
0x140004e54  inc     eax
0x140004e56  mov     [rbp+200h+cchValueName], eax
0x140004e59  mov     r8d, eax
0x140004e5c  xor     edx, edx
0x140004e5e  lea     rcx, [rsp+300h+lpValueName]
0x140004e63  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x140004e68  nop
0x140004e69  mov     rbx, [rsp+300h+lpValueName]
0x140004e6e  test    rbx, rbx
0x140004e71  jnz     short loc_140004EA3
0x140004e73  mov     rcx, [rbp+208h]; this
0x140004e7a  mov     ebx, 8007000Eh
0x140004e7f  mov     r9d, ebx; char *
0x140004e82  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x140004e89  mov     edx, 0DCh; void *
0x140004e8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140004e93  nop
0x140004e94  lea     rcx, [rsp+300h+lpValueName]
0x140004e99  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140004e9e  jmp     loc_140005045
0x140004ea3  mov     [rsp+300h+lpcValues], r14; lpcbData
0x140004ea8  mov     [rsp+300h+lpcbMaxClassLen], r14; lpData
0x140004ead  lea     rax, [rsp+300h+Type]
0x140004eb2  mov     [rsp+300h+lpcbMaxSubKeyLen], rax; lpType
0x140004eb7  mov     [rsp+300h+phkResult], r14; lpReserved
0x140004ebc  lea     r9, [rbp+200h+cchValueName]; lpcchValueName
0x140004ec0  mov     r8, rbx; lpValueName
0x140004ec3  xor     edx, edx; dwIndex
0x140004ec5  mov     rcx, [rsp+300h+hKey]; hKey
0x140004eca  call    cs:__imp_RegEnumValueW
0x140004ed1  nop     dword ptr [rax+rax+00h]
0x140004ed6  mov     edi, eax
0x140004ed8  test    eax, eax
0x140004eda  jz      short loc_140004F0E
0x140004edc  jle     short loc_140004EE7
0x140004ede  movzx   edi, ax
0x140004ee1  or      edi, 80070000h
0x140004ee7  mov     edx, edi
0x140004ee9  lea     rcx, aFailedToCollec_4; "\nFailed to collect logs. Cannot retrei"...
0x140004ef0  call    cs:__imp_wprintf
0x140004ef7  nop     dword ptr [rax+rax+00h]
0x140004efc  nop
0x140004efd  lea     rcx, [rsp+300h+lpValueName]
0x140004f02  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140004f07  mov     ebx, edi
0x140004f09  jmp     loc_140005045
0x140004f0e  mov     edx, [rsp+300h+Type]
0x140004f12  cmp     edx, 4
0x140004f15  jz      short loc_140004F2F
0x140004f17  lea     rcx, aInvalidTypeExp; "\nInvalid type, expected REG_DWORD. typ"...
0x140004f1e  call    cs:__imp_wprintf
0x140004f25  nop     dword ptr [rax+rax+00h]
0x140004f2a  jmp     loc_140005038
0x140004f2f  xor     edx, edx; Val
0x140004f31  mov     r8d, 20Ah; Size
0x140004f37  lea     rcx, [rbp+200h+Dst]; void *
0x140004f3b  call    memset_0
0x140004f40  mov     r8d, 104h; nSize
0x140004f46  lea     rdx, [rbp+200h+Dst]; lpDst
0x140004f4a  mov     rcx, rbx; lpSrc
0x140004f4d  call    cs:__imp_ExpandEnvironmentStringsW
0x140004f54  nop     dword ptr [rax+rax+00h]
0x140004f59  test    eax, eax
0x140004f5b  jnz     short loc_140004F92
0x140004f5d  call    cs:__imp_GetLastError
0x140004f64  nop     dword ptr [rax+rax+00h]
0x140004f69  mov     ebx, eax
0x140004f6b  test    eax, eax
0x140004f6d  jle     short loc_140004F78
0x140004f6f  movzx   ebx, ax
0x140004f72  or      ebx, 80070000h
0x140004f78  mov     edx, ebx
0x140004f7a  lea     rcx, aUnableToExpand; "\nUnable to expand environment variable"...
0x140004f81  call    cs:__imp_wprintf
0x140004f88  nop     dword ptr [rax+rax+00h]
0x140004f8d  jmp     loc_140004E94
0x140004f92  lea     rdx, [rbp+200h+Dst]
0x140004f96  lea     rcx, [rbp+200h+var_278]
0x140004f9a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140004f9f  mov     ecx, 5Ch ; '\'
0x140004fa4  mov     [rsp+300h+var_2A0], cx
0x140004fa9  lea     rdx, [rsp+300h+var_2A0]
0x140004fae  mov     rcx, rax
0x140004fb1  call    ?rfind@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KPEBG_K1@Z; std::wstring::rfind(ushort const *,unsigned __int64,unsigned __int64)
0x140004fb6  mov     rbx, rax
0x140004fb9  xor     r8d, r8d
0x140004fbc  mov     dl, 1
0x140004fbe  lea     rcx, [rbp+200h+var_278]
0x140004fc2  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140004fc7  lea     rdx, [rbp+200h+Dst]
0x140004fcb  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140004fcf  jnz     short loc_140004FF6
0x140004fd1  lea     rcx, aFailedToCollec; "\nFailed to collect logs. Invalid path "...
0x140004fd8  call    cs:__imp_wprintf
0x140004fdf  nop     dword ptr [rax+rax+00h]
0x140004fe4  nop
0x140004fe5  lea     rcx, [rsp+300h+lpValueName]
0x140004fea  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140004fef  mov     ebx, 80070057h
0x140004ff4  jmp     short loc_140005045
0x140004ff6  lea     rcx, [rbp+200h+var_258]
0x140004ffa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x140004fff  nop
0x140005000  mov     r9, rbx
0x140005003  lea     rdx, [rbp+200h+var_278]
0x140005007  mov     rcx, rax
0x14000500a  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x14000500f  mov     rdx, rax
0x140005012  mov     rcx, rsi
0x140005015  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x14000501a  xor     r8d, r8d
0x14000501d  mov     dl, 1
0x14000501f  lea     rcx, [rbp+200h+var_278]
0x140005023  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140005028  nop
0x140005029  xor     r8d, r8d
0x14000502c  mov     dl, 1
0x14000502e  lea     rcx, [rbp+200h+var_258]
0x140005032  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140005037  nop
0x140005038  lea     rcx, [rsp+300h+lpValueName]
0x14000503d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x140005042  mov     ebx, r14d
0x140005045  lea     rcx, [rsp+300h+hKey]
0x14000504a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14000504f  mov     eax, ebx
0x140005051  mov     rcx, [rbp+200h+var_20]
0x140005058  xor     rcx, rsp; StackCookie
0x14000505b  call    __security_check_cookie
0x140005060  lea     r11, [rsp+300h+var_10]
0x140005068  mov     rbx, [r11+28h]
0x14000506c  mov     rsi, [r11+30h]
0x140005070  mov     rsp, r11
0x140005073  pop     r14
0x140005075  pop     rdi
0x140005076  pop     rbp
0x140005077  retn
```
