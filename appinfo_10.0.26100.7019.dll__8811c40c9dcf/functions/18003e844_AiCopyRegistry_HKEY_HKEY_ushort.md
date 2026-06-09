# AiCopyRegistry(HKEY__ *,HKEY__ *,ushort *)

- ea: `0x18003e844`
- end: `0x18003eb59`
- name: `?AiCopyRegistry@@YAJPEAUHKEY__@@0PEAG@Z`
- size: `789`
- prototype: `__int64 __fastcall(HKEY, HKEY, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003e844`
- `0x18003eb60`

## callees

- `0x180007c78`
- `0x1800124f4`
- `0x180018280`
- `0x180028840`
- `0x1800396d0`
- `0x18003e844`
- `0x180042950`
- `0x180042a10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e8a7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e8a7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003eae8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003eae8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003e9ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003e9ac`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003ea32`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003ea32`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003e916`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003e916`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e9e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003e9e1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003e975`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18003e975`

## string_xrefs

- `0x18003e8be`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x18003e92d`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x18003ea7a`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x18003eb40`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`

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
0x18003e844  push    rbp
0x18003e846  push    rbx
0x18003e847  push    rsi
0x18003e848  push    rdi
0x18003e849  push    r14
0x18003e84b  lea     rbp, [rsp-10390h]
0x18003e853  mov     eax, 10490h
0x18003e858  call    _alloca_probe
0x18003e85d  sub     rsp, rax
0x18003e860  mov     rax, cs:__security_cookie
0x18003e867  xor     rax, rsp
0x18003e86a  mov     [rbp+103B0h+var_30], rax
0x18003e871  mov     rsi, rdx
0x18003e874  mov     rbx, rcx
0x18003e877  xor     r14d, r14d
0x18003e87a  lea     rcx, [rsp+104B0h+hKey]
0x18003e87f  xor     edx, edx
0x18003e881  mov     [rsp+104B0h+hKey], r14
0x18003e886  mov     rdi, r8
0x18003e889  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003e88e  lea     rax, [rsp+104B0h+hKey]
0x18003e893  mov     r9d, 20019h; samDesired
0x18003e899  xor     r8d, r8d; ulOptions
0x18003e89c  mov     [rsp+104B0h+phkResult], rax; unsigned int
0x18003e8a1  mov     rdx, rdi; lpSubKey
0x18003e8a4  mov     rcx, rbx; hKey
0x18003e8a7  call    cs:__imp_RegOpenKeyExW
0x18003e8ae  nop     dword ptr [rax+rax+00h]
0x18003e8b3  test    eax, eax
0x18003e8b5  jz      short loc_18003E8D8
0x18003e8b7  mov     rcx, [rbp+103B8h]; this
0x18003e8be  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x18003e8c5  mov     r9d, eax; char *
0x18003e8c8  lea     edx, [r14+60h]; void *
0x18003e8cc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003e8d1  mov     ebx, eax
0x18003e8d3  jmp     loc_18003EB0F
0x18003e8d8  xor     edx, edx
0x18003e8da  mov     [rsp+104B0h+var_10458], r14
0x18003e8df  lea     rcx, [rsp+104B0h+var_10458]
0x18003e8e4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003e8e9  mov     [rsp+104B0h+lpdwDisposition], r14; lpdwDisposition
0x18003e8ee  lea     rax, [rsp+104B0h+var_10458]
0x18003e8f3  mov     [rsp+104B0h+var_10478], rax; phkResult
0x18003e8f8  xor     r9d, r9d; lpClass
0x18003e8fb  mov     [rsp+104B0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18003e900  xor     r8d, r8d; Reserved
0x18003e903  mov     [rsp+104B0h+samDesired], 0F003Fh; samDesired
0x18003e90b  mov     rdx, rdi; lpSubKey
0x18003e90e  mov     rcx, rsi; hKey
0x18003e911  mov     dword ptr [rsp+104B0h+phkResult], r14d; unsigned int
0x18003e916  call    cs:__imp_RegCreateKeyExW
0x18003e91d  nop     dword ptr [rax+rax+00h]
0x18003e922  test    eax, eax
0x18003e924  jz      short loc_18003E952
0x18003e926  mov     rcx, [rbp+103B8h]; this
0x18003e92d  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x18003e934  mov     r9d, eax; char *
0x18003e937  mov     edx, 63h ; 'c'; void *
0x18003e93c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003e941  mov     ebx, eax
0x18003e943  lea     rcx, [rsp+104B0h+var_10458]
0x18003e948  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003e94d  jmp     loc_18003EB0F
0x18003e952  mov     esi, 7FFFh
0x18003e957  mov     [rsp+104B0h+Type], r14d
0x18003e95c  mov     [rsp+104B0h+cchValueName], esi
0x18003e960  mov     edi, r14d
0x18003e963  mov     dword ptr [rsp+104B0h+uBytes], r14d
0x18003e968  xor     edx, edx
0x18003e96a  jmp     loc_18003EA03
0x18003e96f  mov     edx, dword ptr [rsp+104B0h+uBytes]; uBytes
0x18003e973  xor     ecx, ecx; uFlags
0x18003e975  call    cs:__imp_LocalAlloc
0x18003e97c  nop     dword ptr [rax+rax+00h]
0x18003e981  mov     rcx, [rsp+104B0h+hKey]; hKey
0x18003e986  lea     r9, [rsp+104B0h+Type]; lpType
0x18003e98b  mov     rbx, rax
0x18003e98e  mov     [rsp+104B0h+var_10438], rax
0x18003e993  lea     rax, [rsp+104B0h+uBytes]
0x18003e998  xor     r8d, r8d; lpReserved
0x18003e99b  mov     qword ptr [rsp+104B0h+samDesired], rax; lpcbData
0x18003e9a0  lea     rdx, [rbp+103B0h+ValueName]; lpValueName
0x18003e9a7  mov     [rsp+104B0h+phkResult], rbx; unsigned int
0x18003e9ac  call    cs:__imp_RegQueryValueExW
0x18003e9b3  nop     dword ptr [rax+rax+00h]
0x18003e9b8  test    eax, eax
0x18003e9ba  jnz     loc_18003EA6E
0x18003e9c0  mov     eax, dword ptr [rsp+104B0h+uBytes]
0x18003e9c4  lea     rdx, [rbp+103B0h+ValueName]; lpValueName
0x18003e9cb  mov     r9d, [rsp+104B0h+Type]; dwType
0x18003e9d0  xor     r8d, r8d; Reserved
0x18003e9d3  mov     rcx, [rsp+104B0h+var_10458]; hKey
0x18003e9d8  mov     [rsp+104B0h+samDesired], eax; cbData
0x18003e9dc  mov     [rsp+104B0h+phkResult], rbx; lpData
0x18003e9e1  call    cs:__imp_RegSetValueExW
0x18003e9e8  nop     dword ptr [rax+rax+00h]
0x18003e9ed  test    eax, eax
0x18003e9ef  jnz     short loc_18003EA67
0x18003e9f1  inc     edi
0x18003e9f3  mov     [rsp+104B0h+cchValueName], esi
0x18003e9f7  lea     rcx, [rsp+104B0h+var_10438]
0x18003e9fc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003ea01  mov     edx, edi; dwIndex
0x18003ea03  mov     rcx, [rsp+104B0h+hKey]; hKey
0x18003ea08  lea     rax, [rsp+104B0h+uBytes]
0x18003ea0d  mov     [rsp+104B0h+var_10478], rax; lpcbData
0x18003ea12  lea     r9, [rsp+104B0h+cchValueName]; lpcchValueName
0x18003ea17  lea     rax, [rsp+104B0h+Type]
0x18003ea1c  mov     [rsp+104B0h+lpSecurityAttributes], r14; lpData
0x18003ea21  mov     qword ptr [rsp+104B0h+samDesired], rax; lpType
0x18003ea26  lea     r8, [rbp+103B0h+ValueName]; lpValueName
0x18003ea2d  mov     [rsp+104B0h+phkResult], r14; lpReserved
0x18003ea32  call    cs:__imp_RegEnumValueW
0x18003ea39  nop     dword ptr [rax+rax+00h]
0x18003ea3e  mov     ebx, eax
0x18003ea40  test    eax, eax
0x18003ea42  jz      loc_18003E96F
0x18003ea48  mov     esi, 103h
0x18003ea4d  cmp     eax, esi
0x18003ea4f  jz      short loc_18003EA9A
0x18003ea51  test    ebx, ebx
0x18003ea53  jle     loc_18003E943
0x18003ea59  movzx   ebx, bx
0x18003ea5c  or      ebx, 80070000h
0x18003ea62  jmp     loc_18003E943
0x18003ea67  mov     edx, 74h ; 't'
0x18003ea6c  jmp     short loc_18003EA73
0x18003ea6e  mov     edx, 72h ; 'r'; void *
0x18003ea73  mov     rcx, [rbp+103B8h]; this
0x18003ea7a  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x18003ea81  mov     r9d, eax; char *
0x18003ea84  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003ea89  lea     rcx, [rsp+104B0h+var_10438]
0x18003ea8e  mov     ebx, eax
0x18003ea90  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003ea95  jmp     loc_18003E943
0x18003ea9a  mov     edi, r14d
0x18003ea9d  xor     edx, edx
0x18003ea9f  jmp     short loc_18003EABE
0x18003eaa1  mov     rdx, [rsp+104B0h+var_10458]; HKEY
0x18003eaa6  lea     r8, [rbp+103B0h+Name]; unsigned __int16 *
0x18003eaaa  mov     rcx, [rsp+104B0h+hKey]; HKEY
0x18003eaaf  call    ?AiCopyRegistry@@YAJPEAUHKEY__@@0PEAG@Z; AiCopyRegistry(HKEY__ *,HKEY__ *,ushort *)
0x18003eab4  mov     ebx, eax
0x18003eab6  test    eax, eax
0x18003eab8  js      short loc_18003EB39
0x18003eaba  inc     edi
0x18003eabc  mov     edx, edi; dwIndex
0x18003eabe  mov     rcx, [rsp+104B0h+hKey]; hKey
0x18003eac3  lea     r9, [rsp+104B0h+cchName]; lpcchName
0x18003eac8  mov     [rsp+104B0h+var_10478], r14; lpftLastWriteTime
0x18003eacd  lea     r8, [rbp+103B0h+Name]; lpName
0x18003ead1  mov     [rsp+104B0h+lpSecurityAttributes], r14; lpcchClass
0x18003ead6  mov     qword ptr [rsp+104B0h+samDesired], r14; lpClass
0x18003eadb  mov     [rsp+104B0h+phkResult], r14; int
0x18003eae0  mov     [rsp+104B0h+cchName], 200h
0x18003eae8  call    cs:__imp_RegEnumKeyExW
0x18003eaef  nop     dword ptr [rax+rax+00h]
0x18003eaf4  mov     ebx, eax
0x18003eaf6  test    eax, eax
0x18003eaf8  jz      short loc_18003EAA1
0x18003eafa  cmp     eax, esi
0x18003eafc  jnz     loc_18003EA51
0x18003eb02  lea     rcx, [rsp+104B0h+var_10458]
0x18003eb07  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003eb0c  mov     ebx, r14d
0x18003eb0f  lea     rcx, [rsp+104B0h+hKey]
0x18003eb14  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003eb19  mov     eax, ebx
0x18003eb1b  mov     rcx, [rbp+103B0h+var_30]
0x18003eb22  xor     rcx, rsp; StackCookie
0x18003eb25  call    __security_check_cookie
0x18003eb2a  add     rsp, 10490h
0x18003eb31  pop     r14
0x18003eb33  pop     rdi
0x18003eb34  pop     rsi
0x18003eb35  pop     rbx
0x18003eb36  pop     rbp
0x18003eb37  retn
0x18003eb39  mov     rcx, [rbp+103B8h]; this
0x18003eb40  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x18003eb47  mov     r9d, eax; char *
0x18003eb4a  mov     edx, 86h; void *
0x18003eb4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003eb54  jmp     loc_18003E943
```
