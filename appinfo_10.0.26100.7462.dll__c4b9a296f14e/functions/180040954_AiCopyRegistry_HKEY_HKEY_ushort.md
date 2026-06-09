# AiCopyRegistry(HKEY__ *,HKEY__ *,ushort *)

- ea: `0x180040954`
- end: `0x180040c69`
- name: `?AiCopyRegistry@@YAJPEAUHKEY__@@0PEAG@Z`
- size: `789`
- prototype: `__int64 __fastcall(HKEY, HKEY, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180040954`
- `0x180040c70`

## callees

- `0x180007c78`
- `0x180012634`
- `0x180018530`
- `0x1800272d0`
- `0x18003a260`
- `0x180040954`
- `0x180044a20`
- `0x180044ae0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040af1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040af1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180040bf8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180040bf8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800409b7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800409b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180040abc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180040abc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180040a26`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180040a26`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180040b42`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180040b42`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040a85`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040a85`

## string_xrefs

- `0x1800409ce`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x180040a3d`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x180040b8a`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x180040c50`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`

## pseudocode

```c
__int64 __fastcall AiCopyRegistry(HKEY a1, HKEY a2, unsigned __int16 *a3)
{
  unsigned int v6; // eax
  signed int v7; // ebx
  unsigned int v8; // eax
  DWORD v9; // edi
  DWORD i; // edx
  BYTE *v11; // rbx
  unsigned int v12; // eax
  LSTATUS v13; // eax
  __int64 v14; // rdx
  DWORD v15; // edi
  DWORD j; // edx
  int v17; // eax
  LSTATUS v18; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  int phkResultc; // [rsp+20h] [rbp-E0h]
  SIZE_T uBytes; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v25; // [rsp+58h] [rbp-A8h] BYREF
  DWORD Type; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchValueName; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchName; // [rsp+74h] [rbp-8Ch] BYREF
  BYTE *v30; // [rsp+78h] [rbp-88h] BYREF
  WCHAR Name[512]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[32768]; // [rsp+480h] [rbp+380h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+104B8h] [rbp+103B8h]

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v6 = RegOpenKeyExW(a1, a3, 0, 0x20019u, &hKey);
  if ( v6 )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x60,
           (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\sync.cxx",
           (const char *)v6,
           phkResult);
    goto LABEL_23;
  }
  v25 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &v25,
    0);
  v8 = RegCreateKeyExW(a2, a3, 0, 0, 0, 0xF003Fu, 0, &v25, 0);
  if ( v8 )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x63,
           (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\sync.cxx",
           (const char *)v8,
           phkResulta);
LABEL_5:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
    goto LABEL_23;
  }
  Type = 0;
  cchValueName = 0x7FFF;
  v9 = 0;
  LODWORD(uBytes) = 0;
  for ( i = 0; ; i = v9 )
  {
    v13 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, &Type, 0, (LPDWORD)&uBytes);
    v7 = v13;
    if ( v13 )
      break;
    v11 = (BYTE *)LocalAlloc(0, (unsigned int)uBytes);
    v30 = v11;
    v12 = RegQueryValueExW(hKey, ValueName, 0, &Type, v11, (LPDWORD)&uBytes);
    if ( v12 )
    {
      v14 = 114;
      goto LABEL_16;
    }
    v12 = RegSetValueExW(v25, ValueName, 0, Type, v11, uBytes);
    if ( v12 )
    {
      v14 = 116;
LABEL_16:
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v14,
             (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\sync.cxx",
             (const char *)v12,
             phkResultb);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v30);
      goto LABEL_5;
    }
    ++v9;
    cchValueName = 0x7FFF;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v30);
  }
  if ( v13 != 259 )
  {
LABEL_12:
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
    goto LABEL_5;
  }
  v15 = 0;
  for ( j = 0; ; j = v15 )
  {
    cchName = 512;
    v18 = RegEnumKeyExW(hKey, j, Name, &cchName, 0, 0, 0, 0);
    v7 = v18;
    if ( v18 )
      break;
    v17 = AiCopyRegistry(hKey, v25, Name);
    v7 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x86,
        (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\sync.cxx",
        (const char *)(unsigned int)v17,
        phkResultc);
      goto LABEL_5;
    }
    ++v15;
  }
  if ( v18 != 259 )
    goto LABEL_12;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v25);
  v7 = 0;
LABEL_23:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180040954  push    rbp
0x180040956  push    rbx
0x180040957  push    rsi
0x180040958  push    rdi
0x180040959  push    r14
0x18004095b  lea     rbp, [rsp-10390h]
0x180040963  mov     eax, 10490h
0x180040968  call    _alloca_probe
0x18004096d  sub     rsp, rax
0x180040970  mov     rax, cs:__security_cookie
0x180040977  xor     rax, rsp
0x18004097a  mov     [rbp+103B0h+var_30], rax
0x180040981  mov     rsi, rdx
0x180040984  mov     rbx, rcx
0x180040987  xor     r14d, r14d
0x18004098a  lea     rcx, [rsp+104B0h+hKey]
0x18004098f  xor     edx, edx
0x180040991  mov     [rsp+104B0h+hKey], r14
0x180040996  mov     rdi, r8
0x180040999  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004099e  lea     rax, [rsp+104B0h+hKey]
0x1800409a3  mov     r9d, 20019h; samDesired
0x1800409a9  xor     r8d, r8d; ulOptions
0x1800409ac  mov     [rsp+104B0h+phkResult], rax; unsigned int
0x1800409b1  mov     rdx, rdi; lpSubKey
0x1800409b4  mov     rcx, rbx; hKey
0x1800409b7  call    cs:__imp_RegOpenKeyExW
0x1800409be  nop     dword ptr [rax+rax+00h]
0x1800409c3  test    eax, eax
0x1800409c5  jz      short loc_1800409E8
0x1800409c7  mov     rcx, [rbp+103B8h]; this
0x1800409ce  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x1800409d5  mov     r9d, eax; char *
0x1800409d8  lea     edx, [r14+60h]; void *
0x1800409dc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800409e1  mov     ebx, eax
0x1800409e3  jmp     loc_180040C1F
0x1800409e8  xor     edx, edx
0x1800409ea  mov     [rsp+104B0h+var_10458], r14
0x1800409ef  lea     rcx, [rsp+104B0h+var_10458]
0x1800409f4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800409f9  mov     [rsp+104B0h+lpdwDisposition], r14; lpdwDisposition
0x1800409fe  lea     rax, [rsp+104B0h+var_10458]
0x180040a03  mov     [rsp+104B0h+var_10478], rax; phkResult
0x180040a08  xor     r9d, r9d; lpClass
0x180040a0b  mov     [rsp+104B0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180040a10  xor     r8d, r8d; Reserved
0x180040a13  mov     [rsp+104B0h+samDesired], 0F003Fh; samDesired
0x180040a1b  mov     rdx, rdi; lpSubKey
0x180040a1e  mov     rcx, rsi; hKey
0x180040a21  mov     dword ptr [rsp+104B0h+phkResult], r14d; unsigned int
0x180040a26  call    cs:__imp_RegCreateKeyExW
0x180040a2d  nop     dword ptr [rax+rax+00h]
0x180040a32  test    eax, eax
0x180040a34  jz      short loc_180040A62
0x180040a36  mov     rcx, [rbp+103B8h]; this
0x180040a3d  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x180040a44  mov     r9d, eax; char *
0x180040a47  mov     edx, 63h ; 'c'; void *
0x180040a4c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180040a51  mov     ebx, eax
0x180040a53  lea     rcx, [rsp+104B0h+var_10458]
0x180040a58  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180040a5d  jmp     loc_180040C1F
0x180040a62  mov     esi, 7FFFh
0x180040a67  mov     [rsp+104B0h+Type], r14d
0x180040a6c  mov     [rsp+104B0h+cchValueName], esi
0x180040a70  mov     edi, r14d
0x180040a73  mov     dword ptr [rsp+104B0h+uBytes], r14d
0x180040a78  xor     edx, edx
0x180040a7a  jmp     loc_180040B13
0x180040a7f  mov     edx, dword ptr [rsp+104B0h+uBytes]; uBytes
0x180040a83  xor     ecx, ecx; uFlags
0x180040a85  call    cs:__imp_LocalAlloc
0x180040a8c  nop     dword ptr [rax+rax+00h]
0x180040a91  mov     rcx, [rsp+104B0h+hKey]; hKey
0x180040a96  lea     r9, [rsp+104B0h+Type]; lpType
0x180040a9b  mov     rbx, rax
0x180040a9e  mov     [rsp+104B0h+var_10438], rax
0x180040aa3  lea     rax, [rsp+104B0h+uBytes]
0x180040aa8  xor     r8d, r8d; lpReserved
0x180040aab  mov     qword ptr [rsp+104B0h+samDesired], rax; lpcbData
0x180040ab0  lea     rdx, [rbp+103B0h+ValueName]; lpValueName
0x180040ab7  mov     [rsp+104B0h+phkResult], rbx; unsigned int
0x180040abc  call    cs:__imp_RegQueryValueExW
0x180040ac3  nop     dword ptr [rax+rax+00h]
0x180040ac8  test    eax, eax
0x180040aca  jnz     loc_180040B7E
0x180040ad0  mov     eax, dword ptr [rsp+104B0h+uBytes]
0x180040ad4  lea     rdx, [rbp+103B0h+ValueName]; lpValueName
0x180040adb  mov     r9d, [rsp+104B0h+Type]; dwType
0x180040ae0  xor     r8d, r8d; Reserved
0x180040ae3  mov     rcx, [rsp+104B0h+var_10458]; hKey
0x180040ae8  mov     [rsp+104B0h+samDesired], eax; cbData
0x180040aec  mov     [rsp+104B0h+phkResult], rbx; lpData
0x180040af1  call    cs:__imp_RegSetValueExW
0x180040af8  nop     dword ptr [rax+rax+00h]
0x180040afd  test    eax, eax
0x180040aff  jnz     short loc_180040B77
0x180040b01  inc     edi
0x180040b03  mov     [rsp+104B0h+cchValueName], esi
0x180040b07  lea     rcx, [rsp+104B0h+var_10438]
0x180040b0c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180040b11  mov     edx, edi; dwIndex
0x180040b13  mov     rcx, [rsp+104B0h+hKey]; hKey
0x180040b18  lea     rax, [rsp+104B0h+uBytes]
0x180040b1d  mov     [rsp+104B0h+var_10478], rax; lpcbData
0x180040b22  lea     r9, [rsp+104B0h+cchValueName]; lpcchValueName
0x180040b27  lea     rax, [rsp+104B0h+Type]
0x180040b2c  mov     [rsp+104B0h+lpSecurityAttributes], r14; lpData
0x180040b31  mov     qword ptr [rsp+104B0h+samDesired], rax; lpType
0x180040b36  lea     r8, [rbp+103B0h+ValueName]; lpValueName
0x180040b3d  mov     [rsp+104B0h+phkResult], r14; lpReserved
0x180040b42  call    cs:__imp_RegEnumValueW
0x180040b49  nop     dword ptr [rax+rax+00h]
0x180040b4e  mov     ebx, eax
0x180040b50  test    eax, eax
0x180040b52  jz      loc_180040A7F
0x180040b58  mov     esi, 103h
0x180040b5d  cmp     eax, esi
0x180040b5f  jz      short loc_180040BAA
0x180040b61  test    ebx, ebx
0x180040b63  jle     loc_180040A53
0x180040b69  movzx   ebx, bx
0x180040b6c  or      ebx, 80070000h
0x180040b72  jmp     loc_180040A53
0x180040b77  mov     edx, 74h ; 't'
0x180040b7c  jmp     short loc_180040B83
0x180040b7e  mov     edx, 72h ; 'r'; void *
0x180040b83  mov     rcx, [rbp+103B8h]; this
0x180040b8a  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x180040b91  mov     r9d, eax; char *
0x180040b94  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180040b99  lea     rcx, [rsp+104B0h+var_10438]
0x180040b9e  mov     ebx, eax
0x180040ba0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180040ba5  jmp     loc_180040A53
0x180040baa  mov     edi, r14d
0x180040bad  xor     edx, edx
0x180040baf  jmp     short loc_180040BCE
0x180040bb1  mov     rdx, [rsp+104B0h+var_10458]; HKEY
0x180040bb6  lea     r8, [rbp+103B0h+Name]; unsigned __int16 *
0x180040bba  mov     rcx, [rsp+104B0h+hKey]; HKEY
0x180040bbf  call    ?AiCopyRegistry@@YAJPEAUHKEY__@@0PEAG@Z; AiCopyRegistry(HKEY__ *,HKEY__ *,ushort *)
0x180040bc4  mov     ebx, eax
0x180040bc6  test    eax, eax
0x180040bc8  js      short loc_180040C49
0x180040bca  inc     edi
0x180040bcc  mov     edx, edi; dwIndex
0x180040bce  mov     rcx, [rsp+104B0h+hKey]; hKey
0x180040bd3  lea     r9, [rsp+104B0h+cchName]; lpcchName
0x180040bd8  mov     [rsp+104B0h+var_10478], r14; lpftLastWriteTime
0x180040bdd  lea     r8, [rbp+103B0h+Name]; lpName
0x180040be1  mov     [rsp+104B0h+lpSecurityAttributes], r14; lpcchClass
0x180040be6  mov     qword ptr [rsp+104B0h+samDesired], r14; lpClass
0x180040beb  mov     [rsp+104B0h+phkResult], r14; int
0x180040bf0  mov     [rsp+104B0h+cchName], 200h
0x180040bf8  call    cs:__imp_RegEnumKeyExW
0x180040bff  nop     dword ptr [rax+rax+00h]
0x180040c04  mov     ebx, eax
0x180040c06  test    eax, eax
0x180040c08  jz      short loc_180040BB1
0x180040c0a  cmp     eax, esi
0x180040c0c  jnz     loc_180040B61
0x180040c12  lea     rcx, [rsp+104B0h+var_10458]
0x180040c17  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180040c1c  mov     ebx, r14d
0x180040c1f  lea     rcx, [rsp+104B0h+hKey]
0x180040c24  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180040c29  mov     eax, ebx
0x180040c2b  mov     rcx, [rbp+103B0h+var_30]
0x180040c32  xor     rcx, rsp; StackCookie
0x180040c35  call    __security_check_cookie
0x180040c3a  add     rsp, 10490h
0x180040c41  pop     r14
0x180040c43  pop     rdi
0x180040c44  pop     rsi
0x180040c45  pop     rbx
0x180040c46  pop     rbp
0x180040c47  retn
0x180040c49  mov     rcx, [rbp+103B8h]; this
0x180040c50  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x180040c57  mov     r9d, eax; char *
0x180040c5a  mov     edx, 86h; void *
0x180040c5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040c64  jmp     loc_180040A53
```
