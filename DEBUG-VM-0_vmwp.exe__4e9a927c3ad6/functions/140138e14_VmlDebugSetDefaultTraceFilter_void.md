# VmlDebugSetDefaultTraceFilter(void)

- ea: `0x140138e14`
- end: `0x1401390f9`
- name: `?VmlDebugSetDefaultTraceFilter@@YAXXZ`
- size: `741`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400c3818`
- `0x140139aac`
- `0x14013ae30`

## callees

- `0x140132940`
- `0x140135d78`
- `0x140136048`
- `0x140138e14`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140138e8d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140138ec9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140138ff0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140138e8d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140138ec9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140138ff0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140138f12`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140138f49`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140138f80`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140138fb7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140139043`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14013909c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140138f12`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140138f49`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140138f80`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140138fb7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140139043`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14013909c`

## pseudocode

```c
void VmlDebugSetDefaultTraceFilter(void)
{
  __int64 i; // rcx
  int j; // ebx
  DWORD pcbData; // [rsp+40h] [rbp-29h] BYREF
  int pvData; // [rsp+44h] [rbp-25h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-21h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-19h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-11h] BYREF
  volatile __int64 *v7; // [rsp+60h] [rbp-9h] BYREF
  WCHAR Value[12]; // [rsp+68h] [rbp-1h] BYREF

  g_TraceLevel = 2;
  for ( i = 0; i != 32; ++i )
    _InterlockedExchange64((volatile __int64 *)&(&g_TraceEnabled)[i], qword_1402F0E60[i]);
  hKey = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization",
          0,
          0x20019u,
          &hKey) )
  {
    pvData = 0;
    pcbData = 0;
    v7 = 0;
    hkey = 0;
    if ( !RegOpenKeyExW(hKey, L"VML", 0, 0x20019u, &hkey) )
    {
      pcbData = 4;
      RegGetValueW(hkey, 0, L"TraceFlags", 0x10u, 0, &pvData, &pcbData);
      pcbData = 4;
      RegGetValueW(hkey, 0, L"StopLevel", 0x10u, 0, &pvData, &pcbData);
      pcbData = 4;
      RegGetValueW(hkey, 0, L"DebugBreakEnabled", 0x10u, 0, &pvData, &pcbData);
      pcbData = 4;
      if ( !RegGetValueW(hkey, 0, L"TraceLevel", 0x10u, 0, &pvData, &pcbData) )
        g_TraceLevel = pvData;
      phkResult = 0;
      if ( !RegOpenKeyExW(hkey, L"TraceLevelsEnabled", 0, 0x20019u, &phkResult) )
      {
        for ( j = 0; j < 32; ++j )
        {
          swprintf_s<10>(Value, L"Trace%i", (unsigned int)j);
          pcbData = 8;
          if ( !RegGetValueW(phkResult, 0, Value, 0x40u, 0, &v7, &pcbData) )
            (&g_TraceEnabled)[j] = v7;
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    }
    pcbData = 4;
    if ( !RegGetValueW(hKey, 0, L"ClientAssertMask", 0x10u, 0, &pvData, &pcbData) )
    {
      g_BreakOnChildAssert = pvData & 1;
      g_RelaxErrorValidation = ((unsigned __int8)~(_BYTE)pvData >> 1) & 1;
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x140138e14  push    rbp
0x140138e16  push    rbx
0x140138e17  push    rsi
0x140138e18  push    rdi
0x140138e19  push    r14
0x140138e1b  push    r15
0x140138e1d  lea     rbp, [rsp-2Fh]
0x140138e22  sub     rsp, 98h
0x140138e29  mov     rax, cs:__security_cookie
0x140138e30  xor     rax, rsp
0x140138e33  mov     [rbp+57h+var_40], rax
0x140138e37  mov     eax, 2
0x140138e3c  lea     rsi, __ImageBase
0x140138e43  xor     edi, edi
0x140138e45  mov     cs:?g_TraceLevel@@3GA, ax; ushort g_TraceLevel
0x140138e4c  mov     ecx, edi
0x140138e4e  mov     rax, ds:rva qword_1402F0E60[rsi+rcx*8]
0x140138e56  xchg    rax, rva ?g_TraceEnabled@@3RC_JC[rsi+rcx*8]; __int64 volatile near * volatile g_TraceEnabled ...
0x140138e5e  inc     rcx
0x140138e61  cmp     rcx, 20h ; ' '
0x140138e65  jnz     short loc_140138E4E
0x140138e67  lea     rax, [rbp+57h+hKey]
0x140138e6b  mov     [rbp+57h+hKey], rdi
0x140138e6f  mov     ebx, 20019h
0x140138e74  mov     [rsp+0C0h+phkResult], rax; phkResult
0x140138e79  mov     r9d, ebx; samDesired
0x140138e7c  lea     rdx, ?g_SettingsRegistryPath@Vml@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140138e83  xor     r8d, r8d; ulOptions
0x140138e86  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140138e8d  call    cs:__imp_RegOpenKeyExW
0x140138e94  nop     dword ptr [rax+rax+00h]
0x140138e99  test    eax, eax
0x140138e9b  jnz     loc_1401390D3
0x140138ea1  mov     rcx, [rbp+57h+hKey]; hKey
0x140138ea5  lea     rax, [rbp+57h+hkey]
0x140138ea9  mov     r9d, ebx; samDesired
0x140138eac  mov     [rsp+0C0h+phkResult], rax; phkResult
0x140138eb1  xor     r8d, r8d; ulOptions
0x140138eb4  mov     [rbp+57h+var_7C], edi
0x140138eb7  lea     rdx, ?g_VmlRegistryKeyName@Vml@@3QBGB; "VML"
0x140138ebe  mov     [rbp+57h+var_80], edi
0x140138ec1  mov     [rbp+57h+var_60], rdi
0x140138ec5  mov     [rbp+57h+hkey], rdi
0x140138ec9  call    cs:__imp_RegOpenKeyExW
0x140138ed0  nop     dword ptr [rax+rax+00h]
0x140138ed5  mov     r14d, 4
0x140138edb  lea     r15d, [r14+0Ch]
0x140138edf  test    eax, eax
0x140138ee1  jnz     loc_140139071
0x140138ee7  mov     rcx, [rbp+57h+hkey]; hkey
0x140138eeb  lea     rax, [rbp+57h+var_80]
0x140138eef  mov     [rsp+0C0h+pcbData], rax; pcbData
0x140138ef4  lea     r8, aTraceflags; "TraceFlags"
0x140138efb  lea     rax, [rbp+57h+var_7C]
0x140138eff  mov     [rbp+57h+var_80], r14d
0x140138f03  mov     [rsp+0C0h+pvData], rax; pvData
0x140138f08  mov     r9d, r15d; dwFlags
0x140138f0b  xor     edx, edx; lpSubKey
0x140138f0d  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x140138f12  call    cs:__imp_RegGetValueW
0x140138f19  nop     dword ptr [rax+rax+00h]
0x140138f1e  mov     rcx, [rbp+57h+hkey]; hkey
0x140138f22  lea     rax, [rbp+57h+var_80]
0x140138f26  mov     [rsp+0C0h+pcbData], rax; pcbData
0x140138f2b  lea     r8, aStoplevel; "StopLevel"
0x140138f32  lea     rax, [rbp+57h+var_7C]
0x140138f36  mov     [rbp+57h+var_80], r14d
0x140138f3a  mov     [rsp+0C0h+pvData], rax; pvData
0x140138f3f  mov     r9d, r15d; dwFlags
0x140138f42  xor     edx, edx; lpSubKey
0x140138f44  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x140138f49  call    cs:__imp_RegGetValueW
0x140138f50  nop     dword ptr [rax+rax+00h]
0x140138f55  mov     rcx, [rbp+57h+hkey]; hkey
0x140138f59  lea     rax, [rbp+57h+var_80]
0x140138f5d  mov     [rsp+0C0h+pcbData], rax; pcbData
0x140138f62  lea     r8, aDebugbreakenab; "DebugBreakEnabled"
0x140138f69  lea     rax, [rbp+57h+var_7C]
0x140138f6d  mov     [rbp+57h+var_80], r14d
0x140138f71  mov     [rsp+0C0h+pvData], rax; pvData
0x140138f76  mov     r9d, r15d; dwFlags
0x140138f79  xor     edx, edx; lpSubKey
0x140138f7b  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x140138f80  call    cs:__imp_RegGetValueW
0x140138f87  nop     dword ptr [rax+rax+00h]
0x140138f8c  mov     rcx, [rbp+57h+hkey]; hkey
0x140138f90  lea     rax, [rbp+57h+var_80]
0x140138f94  mov     [rsp+0C0h+pcbData], rax; pcbData
0x140138f99  lea     r8, aTracelevel; "TraceLevel"
0x140138fa0  lea     rax, [rbp+57h+var_7C]
0x140138fa4  mov     [rbp+57h+var_80], r14d
0x140138fa8  mov     [rsp+0C0h+pvData], rax; pvData
0x140138fad  mov     r9d, r15d; dwFlags
0x140138fb0  xor     edx, edx; lpSubKey
0x140138fb2  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x140138fb7  call    cs:__imp_RegGetValueW
0x140138fbe  nop     dword ptr [rax+rax+00h]
0x140138fc3  test    eax, eax
0x140138fc5  jnz     short loc_140138FD2
0x140138fc7  movzx   eax, word ptr [rbp+57h+var_7C]
0x140138fcb  mov     cs:?g_TraceLevel@@3GA, ax; ushort g_TraceLevel
0x140138fd2  mov     rcx, [rbp+57h+hkey]; hKey
0x140138fd6  lea     rax, [rbp+57h+var_68]
0x140138fda  mov     r9d, ebx; samDesired
0x140138fdd  mov     [rsp+0C0h+phkResult], rax; phkResult
0x140138fe2  xor     r8d, r8d; ulOptions
0x140138fe5  mov     [rbp+57h+var_68], rdi
0x140138fe9  lea     rdx, aTracelevelsena; "TraceLevelsEnabled"
0x140138ff0  call    cs:__imp_RegOpenKeyExW
0x140138ff7  nop     dword ptr [rax+rax+00h]
0x140138ffc  test    eax, eax
0x140138ffe  jnz     short loc_140139068
0x140139000  mov     ebx, edi
0x140139002  mov     r8d, ebx
0x140139005  lea     rdx, aTraceI; "Trace%i"
0x14013900c  lea     rcx, [rbp+57h+Value]
0x140139010  call    ??$swprintf_s@$09@@YAHAEAY09GPEBGZZ; swprintf_s<10>(ushort (&)[10],ushort const *,...)
0x140139015  mov     rcx, [rbp+57h+var_68]; hkey
0x140139019  lea     rax, [rbp+57h+var_80]
0x14013901d  mov     [rsp+0C0h+pcbData], rax; pcbData
0x140139022  lea     r8, [rbp+57h+Value]; lpValue
0x140139026  lea     rax, [rbp+57h+var_60]
0x14013902a  mov     [rbp+57h+var_80], 8
0x140139031  mov     [rsp+0C0h+pvData], rax; pvData
0x140139036  mov     r9d, 40h ; '@'; dwFlags
0x14013903c  xor     edx, edx; lpSubKey
0x14013903e  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x140139043  call    cs:__imp_RegGetValueW
0x14013904a  nop     dword ptr [rax+rax+00h]
0x14013904f  test    eax, eax
0x140139051  jnz     short loc_140139061
0x140139053  mov     rax, [rbp+57h+var_60]
0x140139057  mov     ecx, ebx
0x140139059  mov     rva ?g_TraceEnabled@@3RC_JC[rsi+rcx*8], rax; __int64 volatile near * volatile g_TraceEnabled ...
0x140139061  inc     ebx
0x140139063  cmp     ebx, 20h ; ' '
0x140139066  jl      short loc_140139002
0x140139068  lea     rcx, [rbp+57h+var_68]
0x14013906c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140139071  mov     rcx, [rbp+57h+hKey]; hkey
0x140139075  lea     rax, [rbp+57h+var_80]
0x140139079  mov     [rsp+0C0h+pcbData], rax; pcbData
0x14013907e  lea     r8, ?g_DvClientAssertsMaskName@@3QBGB; "ClientAssertMask"
0x140139085  lea     rax, [rbp+57h+var_7C]
0x140139089  mov     [rbp+57h+var_80], r14d
0x14013908d  mov     [rsp+0C0h+pvData], rax; pvData
0x140139092  mov     r9d, r15d; dwFlags
0x140139095  xor     edx, edx; lpSubKey
0x140139097  mov     [rsp+0C0h+phkResult], rdi; pdwType
0x14013909c  call    cs:__imp_RegGetValueW
0x1401390a3  nop     dword ptr [rax+rax+00h]
0x1401390a8  test    eax, eax
0x1401390aa  jnz     short loc_1401390CA
0x1401390ac  mov     ecx, [rbp+57h+var_7C]
0x1401390af  mov     eax, ecx
0x1401390b1  and     eax, 1
0x1401390b4  not     cl
0x1401390b6  mov     cs:?g_BreakOnChildAssert@@3HA, eax; int g_BreakOnChildAssert
0x1401390bc  movzx   eax, cl
0x1401390bf  shr     eax, 1
0x1401390c1  and     eax, 1
0x1401390c4  mov     cs:?g_RelaxErrorValidation@@3HA, eax; int g_RelaxErrorValidation
0x1401390ca  lea     rcx, [rbp+57h+hkey]
0x1401390ce  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401390d3  lea     rcx, [rbp+57h+hKey]
0x1401390d7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1401390dc  mov     rcx, [rbp+57h+var_40]
0x1401390e0  xor     rcx, rsp; StackCookie
0x1401390e3  call    __security_check_cookie
0x1401390e8  add     rsp, 98h
0x1401390ef  pop     r15
0x1401390f1  pop     r14
0x1401390f3  pop     rdi
0x1401390f4  pop     rsi
0x1401390f5  pop     rbx
0x1401390f6  pop     rbp
0x1401390f7  retn
```
