# AiCopyRegistry(HKEY__ *,HKEY__ *,ushort *)

- ea: `0x180042fb0`
- end: `0x18004329a`
- name: `?AiCopyRegistry@@YAJPEAUHKEY__@@0PEAG@Z`
- size: `746`
- prototype: `__int64 __fastcall(HKEY, HKEY, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180042fb0`
- `0x1800432a0`

## callees

- `0x18000720c`
- `0x180011414`
- `0x180018dbc`
- `0x18002b0a0`
- `0x18003c6e0`
- `0x180042fb0`
- `0x180046e50`
- `0x180046ee0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043013`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043013`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180043106`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180043106`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180043180`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180043180`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180043135`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180043135`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004307c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004307c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180043230`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180043230`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800430d5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800430d5`

## string_xrefs

- `0x180043024`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x18004308d`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x1800431c2`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x180043281`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`

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
           (void *)0x61,
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
           (void *)0x64,
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
      v14 = 115;
      goto LABEL_16;
    }
    v12 = RegSetValueExW(v25, ValueName, 0, Type, v11, uBytes);
    if ( v12 )
    {
      v14 = 117;
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
        (void *)0x87,
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
0x180042fb0  push    rbp
0x180042fb2  push    rbx
0x180042fb3  push    rsi
0x180042fb4  push    rdi
0x180042fb5  push    r14
0x180042fb7  lea     rbp, [rsp-10390h]
0x180042fbf  mov     eax, 10490h
0x180042fc4  call    _alloca_probe
0x180042fc9  sub     rsp, rax
0x180042fcc  mov     rax, cs:__security_cookie
0x180042fd3  xor     rax, rsp
0x180042fd6  mov     [rbp+103B0h+var_30], rax
0x180042fdd  mov     rsi, rdx
0x180042fe0  mov     rbx, rcx
0x180042fe3  xor     r14d, r14d
0x180042fe6  lea     rcx, [rsp+104B0h+hKey]
0x180042feb  xor     edx, edx
0x180042fed  mov     [rsp+104B0h+hKey], r14
0x180042ff2  mov     rdi, r8
0x180042ff5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180042ffa  lea     rax, [rsp+104B0h+hKey]
0x180042fff  mov     r9d, 20019h; samDesired
0x180043005  xor     r8d, r8d; ulOptions
0x180043008  mov     [rsp+104B0h+phkResult], rax; unsigned int
0x18004300d  mov     rdx, rdi; lpSubKey
0x180043010  mov     rcx, rbx; hKey
0x180043013  call    cs:__imp_RegOpenKeyExW
0x180043019  test    eax, eax
0x18004301b  jz      short loc_18004303E
0x18004301d  mov     rcx, [rbp+103B8h]; this
0x180043024  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x18004302b  mov     r9d, eax; char *
0x18004302e  lea     edx, [r14+61h]; void *
0x180043032  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180043037  mov     ebx, eax
0x180043039  jmp     loc_180043251
0x18004303e  xor     edx, edx
0x180043040  mov     [rsp+104B0h+var_10458], r14
0x180043045  lea     rcx, [rsp+104B0h+var_10458]
0x18004304a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004304f  mov     [rsp+104B0h+lpdwDisposition], r14; lpdwDisposition
0x180043054  lea     rax, [rsp+104B0h+var_10458]
0x180043059  mov     [rsp+104B0h+var_10478], rax; phkResult
0x18004305e  xor     r9d, r9d; lpClass
0x180043061  mov     [rsp+104B0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180043066  xor     r8d, r8d; Reserved
0x180043069  mov     [rsp+104B0h+samDesired], 0F003Fh; samDesired
0x180043071  mov     rdx, rdi; lpSubKey
0x180043074  mov     rcx, rsi; hKey
0x180043077  mov     dword ptr [rsp+104B0h+phkResult], r14d; unsigned int
0x18004307c  call    cs:__imp_RegCreateKeyExW
0x180043082  test    eax, eax
0x180043084  jz      short loc_1800430B2
0x180043086  mov     rcx, [rbp+103B8h]; this
0x18004308d  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x180043094  mov     r9d, eax; char *
0x180043097  mov     edx, 64h ; 'd'; void *
0x18004309c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800430a1  mov     ebx, eax
0x1800430a3  lea     rcx, [rsp+104B0h+var_10458]
0x1800430a8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800430ad  jmp     loc_180043251
0x1800430b2  mov     esi, 7FFFh
0x1800430b7  mov     [rsp+104B0h+Type], r14d
0x1800430bc  mov     [rsp+104B0h+cchValueName], esi
0x1800430c0  mov     edi, r14d
0x1800430c3  mov     dword ptr [rsp+104B0h+uBytes], r14d
0x1800430c8  xor     edx, edx
0x1800430ca  jmp     loc_180043151
0x1800430cf  mov     edx, dword ptr [rsp+104B0h+uBytes]; uBytes
0x1800430d3  xor     ecx, ecx; uFlags
0x1800430d5  call    cs:__imp_LocalAlloc
0x1800430db  mov     rcx, [rsp+104B0h+hKey]; hKey
0x1800430e0  lea     r9, [rsp+104B0h+Type]; lpType
0x1800430e5  mov     rbx, rax
0x1800430e8  mov     [rsp+104B0h+var_10438], rax
0x1800430ed  lea     rax, [rsp+104B0h+uBytes]
0x1800430f2  xor     r8d, r8d; lpReserved
0x1800430f5  mov     qword ptr [rsp+104B0h+samDesired], rax; lpcbData
0x1800430fa  lea     rdx, [rbp+103B0h+ValueName]; lpValueName
0x180043101  mov     [rsp+104B0h+phkResult], rbx; unsigned int
0x180043106  call    cs:__imp_RegQueryValueExW
0x18004310c  test    eax, eax
0x18004310e  jnz     loc_1800431B6
0x180043114  mov     eax, dword ptr [rsp+104B0h+uBytes]
0x180043118  lea     rdx, [rbp+103B0h+ValueName]; lpValueName
0x18004311f  mov     r9d, [rsp+104B0h+Type]; dwType
0x180043124  xor     r8d, r8d; Reserved
0x180043127  mov     rcx, [rsp+104B0h+var_10458]; hKey
0x18004312c  mov     [rsp+104B0h+samDesired], eax; cbData
0x180043130  mov     [rsp+104B0h+phkResult], rbx; lpData
0x180043135  call    cs:__imp_RegSetValueExW
0x18004313b  test    eax, eax
0x18004313d  jnz     short loc_1800431AF
0x18004313f  inc     edi
0x180043141  mov     [rsp+104B0h+cchValueName], esi
0x180043145  lea     rcx, [rsp+104B0h+var_10438]
0x18004314a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18004314f  mov     edx, edi; dwIndex
0x180043151  mov     rcx, [rsp+104B0h+hKey]; hKey
0x180043156  lea     rax, [rsp+104B0h+uBytes]
0x18004315b  mov     [rsp+104B0h+var_10478], rax; lpcbData
0x180043160  lea     r9, [rsp+104B0h+cchValueName]; lpcchValueName
0x180043165  lea     rax, [rsp+104B0h+Type]
0x18004316a  mov     [rsp+104B0h+lpSecurityAttributes], r14; lpData
0x18004316f  mov     qword ptr [rsp+104B0h+samDesired], rax; lpType
0x180043174  lea     r8, [rbp+103B0h+ValueName]; lpValueName
0x18004317b  mov     [rsp+104B0h+phkResult], r14; lpReserved
0x180043180  call    cs:__imp_RegEnumValueW
0x180043186  mov     ebx, eax
0x180043188  test    eax, eax
0x18004318a  jz      loc_1800430CF
0x180043190  mov     esi, 103h
0x180043195  cmp     eax, esi
0x180043197  jz      short loc_1800431E2
0x180043199  test    ebx, ebx
0x18004319b  jle     loc_1800430A3
0x1800431a1  movzx   ebx, bx
0x1800431a4  or      ebx, 80070000h
0x1800431aa  jmp     loc_1800430A3
0x1800431af  mov     edx, 75h ; 'u'
0x1800431b4  jmp     short loc_1800431BB
0x1800431b6  mov     edx, 73h ; 's'; void *
0x1800431bb  mov     rcx, [rbp+103B8h]; this
0x1800431c2  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x1800431c9  mov     r9d, eax; char *
0x1800431cc  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800431d1  lea     rcx, [rsp+104B0h+var_10438]
0x1800431d6  mov     ebx, eax
0x1800431d8  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800431dd  jmp     loc_1800430A3
0x1800431e2  mov     edi, r14d
0x1800431e5  xor     edx, edx
0x1800431e7  jmp     short loc_180043206
0x1800431e9  mov     rdx, [rsp+104B0h+var_10458]; HKEY
0x1800431ee  lea     r8, [rbp+103B0h+Name]; unsigned __int16 *
0x1800431f2  mov     rcx, [rsp+104B0h+hKey]; HKEY
0x1800431f7  call    ?AiCopyRegistry@@YAJPEAUHKEY__@@0PEAG@Z; AiCopyRegistry(HKEY__ *,HKEY__ *,ushort *)
0x1800431fc  mov     ebx, eax
0x1800431fe  test    eax, eax
0x180043200  js      short loc_18004327A
0x180043202  inc     edi
0x180043204  mov     edx, edi; dwIndex
0x180043206  mov     rcx, [rsp+104B0h+hKey]; hKey
0x18004320b  lea     r9, [rsp+104B0h+cchName]; lpcchName
0x180043210  mov     [rsp+104B0h+var_10478], r14; lpftLastWriteTime
0x180043215  lea     r8, [rbp+103B0h+Name]; lpName
0x180043219  mov     [rsp+104B0h+lpSecurityAttributes], r14; lpcchClass
0x18004321e  mov     qword ptr [rsp+104B0h+samDesired], r14; lpClass
0x180043223  mov     [rsp+104B0h+phkResult], r14; int
0x180043228  mov     [rsp+104B0h+cchName], 200h
0x180043230  call    cs:__imp_RegEnumKeyExW
0x180043236  mov     ebx, eax
0x180043238  test    eax, eax
0x18004323a  jz      short loc_1800431E9
0x18004323c  cmp     eax, esi
0x18004323e  jnz     loc_180043199
0x180043244  lea     rcx, [rsp+104B0h+var_10458]
0x180043249  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004324e  mov     ebx, r14d
0x180043251  lea     rcx, [rsp+104B0h+hKey]
0x180043256  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004325b  mov     eax, ebx
0x18004325d  mov     rcx, [rbp+103B0h+var_30]
0x180043264  xor     rcx, rsp; StackCookie
0x180043267  call    __security_check_cookie
0x18004326c  add     rsp, 10490h
0x180043273  pop     r14
0x180043275  pop     rdi
0x180043276  pop     rsi
0x180043277  pop     rbx
0x180043278  pop     rbp
0x180043279  retn
0x18004327a  mov     rcx, [rbp+103B8h]; this
0x180043281  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x180043288  mov     r9d, eax; char *
0x18004328b  mov     edx, 87h; void *
0x180043290  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043295  jmp     loc_1800430A3
```
