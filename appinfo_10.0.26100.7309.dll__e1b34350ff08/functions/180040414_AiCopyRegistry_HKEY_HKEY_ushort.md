# AiCopyRegistry(HKEY__ *,HKEY__ *,ushort *)

- ea: `0x180040414`
- end: `0x180040729`
- name: `?AiCopyRegistry@@YAJPEAUHKEY__@@0PEAG@Z`
- size: `789`
- prototype: `__int64 __fastcall(HKEY, HKEY, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180040414`
- `0x180040730`

## callees

- `0x180007c78`
- `0x180012634`
- `0x180018530`
- `0x180027200`
- `0x180039ee0`
- `0x180040414`
- `0x1800444e0`
- `0x1800445a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800405b1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800405b1`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800406b8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800406b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040477`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040477`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004057c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004057c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800404e6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800404e6`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180040602`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180040602`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040545`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180040545`

## string_xrefs

- `0x18004048e`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x1800404fd`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x18004064a`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x180040710`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`

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
0x180040414  push    rbp
0x180040416  push    rbx
0x180040417  push    rsi
0x180040418  push    rdi
0x180040419  push    r14
0x18004041b  lea     rbp, [rsp-10390h]
0x180040423  mov     eax, 10490h
0x180040428  call    _alloca_probe
0x18004042d  sub     rsp, rax
0x180040430  mov     rax, cs:__security_cookie
0x180040437  xor     rax, rsp
0x18004043a  mov     [rbp+103B0h+var_30], rax
0x180040441  mov     rsi, rdx
0x180040444  mov     rbx, rcx
0x180040447  xor     r14d, r14d
0x18004044a  lea     rcx, [rsp+104B0h+hKey]
0x18004044f  xor     edx, edx
0x180040451  mov     [rsp+104B0h+hKey], r14
0x180040456  mov     rdi, r8
0x180040459  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004045e  lea     rax, [rsp+104B0h+hKey]
0x180040463  mov     r9d, 20019h; samDesired
0x180040469  xor     r8d, r8d; ulOptions
0x18004046c  mov     [rsp+104B0h+phkResult], rax; unsigned int
0x180040471  mov     rdx, rdi; lpSubKey
0x180040474  mov     rcx, rbx; hKey
0x180040477  call    cs:__imp_RegOpenKeyExW
0x18004047e  nop     dword ptr [rax+rax+00h]
0x180040483  test    eax, eax
0x180040485  jz      short loc_1800404A8
0x180040487  mov     rcx, [rbp+103B8h]; this
0x18004048e  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x180040495  mov     r9d, eax; char *
0x180040498  lea     edx, [r14+60h]; void *
0x18004049c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800404a1  mov     ebx, eax
0x1800404a3  jmp     loc_1800406DF
0x1800404a8  xor     edx, edx
0x1800404aa  mov     [rsp+104B0h+var_10458], r14
0x1800404af  lea     rcx, [rsp+104B0h+var_10458]
0x1800404b4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800404b9  mov     [rsp+104B0h+lpdwDisposition], r14; lpdwDisposition
0x1800404be  lea     rax, [rsp+104B0h+var_10458]
0x1800404c3  mov     [rsp+104B0h+var_10478], rax; phkResult
0x1800404c8  xor     r9d, r9d; lpClass
0x1800404cb  mov     [rsp+104B0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800404d0  xor     r8d, r8d; Reserved
0x1800404d3  mov     [rsp+104B0h+samDesired], 0F003Fh; samDesired
0x1800404db  mov     rdx, rdi; lpSubKey
0x1800404de  mov     rcx, rsi; hKey
0x1800404e1  mov     dword ptr [rsp+104B0h+phkResult], r14d; unsigned int
0x1800404e6  call    cs:__imp_RegCreateKeyExW
0x1800404ed  nop     dword ptr [rax+rax+00h]
0x1800404f2  test    eax, eax
0x1800404f4  jz      short loc_180040522
0x1800404f6  mov     rcx, [rbp+103B8h]; this
0x1800404fd  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x180040504  mov     r9d, eax; char *
0x180040507  mov     edx, 63h ; 'c'; void *
0x18004050c  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180040511  mov     ebx, eax
0x180040513  lea     rcx, [rsp+104B0h+var_10458]
0x180040518  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004051d  jmp     loc_1800406DF
0x180040522  mov     esi, 7FFFh
0x180040527  mov     [rsp+104B0h+Type], r14d
0x18004052c  mov     [rsp+104B0h+cchValueName], esi
0x180040530  mov     edi, r14d
0x180040533  mov     dword ptr [rsp+104B0h+uBytes], r14d
0x180040538  xor     edx, edx
0x18004053a  jmp     loc_1800405D3
0x18004053f  mov     edx, dword ptr [rsp+104B0h+uBytes]; uBytes
0x180040543  xor     ecx, ecx; uFlags
0x180040545  call    cs:__imp_LocalAlloc
0x18004054c  nop     dword ptr [rax+rax+00h]
0x180040551  mov     rcx, [rsp+104B0h+hKey]; hKey
0x180040556  lea     r9, [rsp+104B0h+Type]; lpType
0x18004055b  mov     rbx, rax
0x18004055e  mov     [rsp+104B0h+var_10438], rax
0x180040563  lea     rax, [rsp+104B0h+uBytes]
0x180040568  xor     r8d, r8d; lpReserved
0x18004056b  mov     qword ptr [rsp+104B0h+samDesired], rax; lpcbData
0x180040570  lea     rdx, [rbp+103B0h+ValueName]; lpValueName
0x180040577  mov     [rsp+104B0h+phkResult], rbx; unsigned int
0x18004057c  call    cs:__imp_RegQueryValueExW
0x180040583  nop     dword ptr [rax+rax+00h]
0x180040588  test    eax, eax
0x18004058a  jnz     loc_18004063E
0x180040590  mov     eax, dword ptr [rsp+104B0h+uBytes]
0x180040594  lea     rdx, [rbp+103B0h+ValueName]; lpValueName
0x18004059b  mov     r9d, [rsp+104B0h+Type]; dwType
0x1800405a0  xor     r8d, r8d; Reserved
0x1800405a3  mov     rcx, [rsp+104B0h+var_10458]; hKey
0x1800405a8  mov     [rsp+104B0h+samDesired], eax; cbData
0x1800405ac  mov     [rsp+104B0h+phkResult], rbx; lpData
0x1800405b1  call    cs:__imp_RegSetValueExW
0x1800405b8  nop     dword ptr [rax+rax+00h]
0x1800405bd  test    eax, eax
0x1800405bf  jnz     short loc_180040637
0x1800405c1  inc     edi
0x1800405c3  mov     [rsp+104B0h+cchValueName], esi
0x1800405c7  lea     rcx, [rsp+104B0h+var_10438]
0x1800405cc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800405d1  mov     edx, edi; dwIndex
0x1800405d3  mov     rcx, [rsp+104B0h+hKey]; hKey
0x1800405d8  lea     rax, [rsp+104B0h+uBytes]
0x1800405dd  mov     [rsp+104B0h+var_10478], rax; lpcbData
0x1800405e2  lea     r9, [rsp+104B0h+cchValueName]; lpcchValueName
0x1800405e7  lea     rax, [rsp+104B0h+Type]
0x1800405ec  mov     [rsp+104B0h+lpSecurityAttributes], r14; lpData
0x1800405f1  mov     qword ptr [rsp+104B0h+samDesired], rax; lpType
0x1800405f6  lea     r8, [rbp+103B0h+ValueName]; lpValueName
0x1800405fd  mov     [rsp+104B0h+phkResult], r14; lpReserved
0x180040602  call    cs:__imp_RegEnumValueW
0x180040609  nop     dword ptr [rax+rax+00h]
0x18004060e  mov     ebx, eax
0x180040610  test    eax, eax
0x180040612  jz      loc_18004053F
0x180040618  mov     esi, 103h
0x18004061d  cmp     eax, esi
0x18004061f  jz      short loc_18004066A
0x180040621  test    ebx, ebx
0x180040623  jle     loc_180040513
0x180040629  movzx   ebx, bx
0x18004062c  or      ebx, 80070000h
0x180040632  jmp     loc_180040513
0x180040637  mov     edx, 74h ; 't'
0x18004063c  jmp     short loc_180040643
0x18004063e  mov     edx, 72h ; 'r'; void *
0x180040643  mov     rcx, [rbp+103B8h]; this
0x18004064a  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x180040651  mov     r9d, eax; char *
0x180040654  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180040659  lea     rcx, [rsp+104B0h+var_10438]
0x18004065e  mov     ebx, eax
0x180040660  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180040665  jmp     loc_180040513
0x18004066a  mov     edi, r14d
0x18004066d  xor     edx, edx
0x18004066f  jmp     short loc_18004068E
0x180040671  mov     rdx, [rsp+104B0h+var_10458]; HKEY
0x180040676  lea     r8, [rbp+103B0h+Name]; unsigned __int16 *
0x18004067a  mov     rcx, [rsp+104B0h+hKey]; HKEY
0x18004067f  call    ?AiCopyRegistry@@YAJPEAUHKEY__@@0PEAG@Z; AiCopyRegistry(HKEY__ *,HKEY__ *,ushort *)
0x180040684  mov     ebx, eax
0x180040686  test    eax, eax
0x180040688  js      short loc_180040709
0x18004068a  inc     edi
0x18004068c  mov     edx, edi; dwIndex
0x18004068e  mov     rcx, [rsp+104B0h+hKey]; hKey
0x180040693  lea     r9, [rsp+104B0h+cchName]; lpcchName
0x180040698  mov     [rsp+104B0h+var_10478], r14; lpftLastWriteTime
0x18004069d  lea     r8, [rbp+103B0h+Name]; lpName
0x1800406a1  mov     [rsp+104B0h+lpSecurityAttributes], r14; lpcchClass
0x1800406a6  mov     qword ptr [rsp+104B0h+samDesired], r14; lpClass
0x1800406ab  mov     [rsp+104B0h+phkResult], r14; int
0x1800406b0  mov     [rsp+104B0h+cchName], 200h
0x1800406b8  call    cs:__imp_RegEnumKeyExW
0x1800406bf  nop     dword ptr [rax+rax+00h]
0x1800406c4  mov     ebx, eax
0x1800406c6  test    eax, eax
0x1800406c8  jz      short loc_180040671
0x1800406ca  cmp     eax, esi
0x1800406cc  jnz     loc_180040621
0x1800406d2  lea     rcx, [rsp+104B0h+var_10458]
0x1800406d7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800406dc  mov     ebx, r14d
0x1800406df  lea     rcx, [rsp+104B0h+hKey]
0x1800406e4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800406e9  mov     eax, ebx
0x1800406eb  mov     rcx, [rbp+103B0h+var_30]
0x1800406f2  xor     rcx, rsp; StackCookie
0x1800406f5  call    __security_check_cookie
0x1800406fa  add     rsp, 10490h
0x180040701  pop     r14
0x180040703  pop     rdi
0x180040704  pop     rsi
0x180040705  pop     rbx
0x180040706  pop     rbp
0x180040707  retn
0x180040709  mov     rcx, [rbp+103B8h]; this
0x180040710  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x180040717  mov     r9d, eax; char *
0x18004071a  mov     edx, 86h; void *
0x18004071f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040724  jmp     loc_180040513
```
