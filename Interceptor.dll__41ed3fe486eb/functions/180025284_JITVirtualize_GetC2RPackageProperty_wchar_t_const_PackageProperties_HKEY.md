# JITVirtualize::GetC2RPackageProperty(wchar_t const *,PackageProperties &,HKEY__ *)

- ea: `0x180025284`
- end: `0x180025554`
- name: `?GetC2RPackageProperty@JITVirtualize@@CA_NPEB_WAEAUPackageProperties@@PEAUHKEY__@@@Z`
- size: `720`
- prototype: `bool __fastcall(const wchar_t *String1, struct PackageProperties *, HKEY)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800251b8`

## callees

- `0x180025284`
- `0x1800266e0`
- `0x18002b400`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x1800252c5`
- `KERNEL32!GetCurrentProcess` at `0x180025466`
- `KERNEL32!GetCurrentProcess` at `0x1800252c5`
- `KERNEL32!GetCurrentProcess` at `0x180025466`
- `KERNEL32!IsWow64Process` at `0x1800252d3`
- `KERNEL32!IsWow64Process` at `0x180025474`
- `KERNEL32!IsWow64Process` at `0x1800252d3`
- `KERNEL32!IsWow64Process` at `0x180025474`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800253fc`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x1800253fc`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x18002543b`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180025456`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180025514`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x18002543b`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180025456`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180025514`
- `ADVAPI32!RegEnumValueW` at `0x1800253dc`
- `ADVAPI32!RegEnumValueW` at `0x1800253dc`
- `ADVAPI32!RegCloseKey` at `0x180025520`
- `ADVAPI32!RegCloseKey` at `0x18002552b`
- `ADVAPI32!RegCloseKey` at `0x180025520`
- `ADVAPI32!RegCloseKey` at `0x18002552b`
- `ADVAPI32!RegOpenKeyExW` at `0x180025308`
- `ADVAPI32!RegOpenKeyExW` at `0x1800254a0`
- `ADVAPI32!RegOpenKeyExW` at `0x180025308`
- `ADVAPI32!RegOpenKeyExW` at `0x1800254a0`
- `ADVAPI32!RegQueryValueExW` at `0x1800254f4`
- `ADVAPI32!RegQueryValueExW` at `0x1800254f4`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180025354`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180025354`

## pseudocode

```c
char __fastcall JITVirtualize::GetC2RPackageProperty(const wchar_t *String1, wchar_t *a2, HKEY a3)
{
  char v3; // bl
  int v5; // edi
  HANDLE CurrentProcess; // rax
  DWORD v9; // edi
  int v10; // edi
  HANDLE v11; // rax
  BOOL Wow64Process; // [rsp+60h] [rbp-A0h] BYREF
  BOOL v14; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD Type; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchValueName; // [rsp+6Ch] [rbp-94h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbData; // [rsp+78h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-80h] BYREF
  BYTE Data[2]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v21[76]; // [rsp+92h] [rbp-6Eh] BYREF
  WCHAR ValueName[264]; // [rsp+E0h] [rbp-20h] BYREF
  BYTE v23[2]; // [rsp+2F0h] [rbp+1F0h] BYREF
  _BYTE v24[518]; // [rsp+2F2h] [rbp+1F2h] BYREF

  v3 = 0;
  hKey = 0;
  v5 = 0;
  Wow64Process = 0;
  CurrentProcess = GetCurrentProcess();
  if ( IsWow64Process(CurrentProcess, &Wow64Process) && Wow64Process )
    v5 = 256;
  if ( !RegOpenKeyExW(a3, L"Software\\Microsoft\\Office\\16.0\\ClickToRunStore\\Packages", 0, v5 | 1, &hKey) )
  {
    Wow64Process = 0;
    if ( !RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, (LPDWORD)&Wow64Process, 0, 0, 0, 0) && Wow64Process )
    {
      v9 = 0;
      while ( 1 )
      {
        memset(ValueName, 0, 520);
        cchValueName = 260;
        *(_WORD *)Data = 0;
        memset(v21, 0, sizeof(v21));
        cbData = 78;
        Type = 0;
        if ( !RegEnumValueW(hKey, v9, ValueName, &cchValueName, 0, &Type, Data, &cbData)
          && Type == 1
          && !_wcsnicmp(String1, ValueName, cchValueName - 1) )
        {
          break;
        }
        if ( ++v9 >= Wow64Process )
          goto LABEL_20;
      }
      *(_DWORD *)a2 = ((HKEY)((char *)a3 + 0x7FFFFFFF) != 0) + 1;
      wcsncpy_s(a2 + 2, 0x104u, ValueName, 0xFFFFFFFFFFFFFFFFuLL);
      wcsncpy_s(a2 + 262, 0x27u, (const wchar_t *)Data, 0xFFFFFFFFFFFFFFFFuLL);
      phkResult = 0;
      v10 = 0;
      v14 = 0;
      v11 = GetCurrentProcess();
      if ( IsWow64Process(v11, &v14) && v14 )
        v10 = 256;
      if ( !RegOpenKeyExW(hKey, a2 + 262, 0, v10 | 1, &phkResult) )
      {
        *(_WORD *)v23 = 0;
        memset(v24, 0, sizeof(v24));
        v14 = 520;
        if ( !RegQueryValueExW(phkResult, L"JitV64", 0, 0, v23, (LPDWORD)&v14) )
        {
          wcsncpy_s(a2 + 301, 0x104u, (const wchar_t *)v23, 0xFFFFFFFFFFFFFFFFuLL);
          v3 = 1;
        }
        RegCloseKey(phkResult);
      }
    }
LABEL_20:
    RegCloseKey(hKey);
  }
  return v3;
}

```

## disassembly

```asm
0x180025284  push    rbp
0x180025286  push    rbx
0x180025287  push    rsi
0x180025288  push    rdi
0x180025289  push    r13
0x18002528b  push    r14
0x18002528d  push    r15
0x18002528f  lea     rbp, [rsp-410h]
0x180025297  sub     rsp, 510h
0x18002529e  mov     rax, cs:__security_cookie
0x1800252a5  xor     rax, rsp
0x1800252a8  mov     [rbp+440h+var_40], rax
0x1800252af  xor     ebx, ebx
0x1800252b1  mov     r14, r8
0x1800252b4  mov     [rsp+540h+hKey], rbx
0x1800252b9  mov     edi, ebx
0x1800252bb  mov     [rsp+540h+Wow64Process], ebx
0x1800252bf  mov     rsi, rdx
0x1800252c2  mov     r15, rcx
0x1800252c5  call    cs:__imp_GetCurrentProcess
0x1800252cb  mov     rcx, rax; hProcess
0x1800252ce  lea     rdx, [rsp+540h+Wow64Process]; Wow64Process
0x1800252d3  call    cs:__imp_IsWow64Process
0x1800252d9  mov     r13d, 100h
0x1800252df  test    eax, eax
0x1800252e1  jz      short loc_1800252EB
0x1800252e3  cmp     [rsp+540h+Wow64Process], ebx
0x1800252e7  cmovnz  edi, r13d
0x1800252eb  lea     rax, [rsp+540h+hKey]
0x1800252f0  or      edi, 1
0x1800252f3  mov     r9d, edi; samDesired
0x1800252f6  mov     [rsp+540h+phkResult], rax; phkResult
0x1800252fb  xor     r8d, r8d; ulOptions
0x1800252fe  lea     rdx, SubKey; "Software\\Microsoft\\Office\\16.0\\Clic"...
0x180025305  mov     rcx, r14; hKey
0x180025308  call    cs:__imp_RegOpenKeyExW
0x18002530e  test    eax, eax
0x180025310  jnz     loc_180025531
0x180025316  mov     rcx, [rsp+540h+hKey]; hKey
0x18002531b  lea     rax, [rsp+540h+Wow64Process]
0x180025320  mov     [rsp+540h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x180025325  xor     r9d, r9d; lpReserved
0x180025328  mov     [rsp+540h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x18002532d  xor     r8d, r8d; lpcchClass
0x180025330  mov     [rsp+540h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x180025335  xor     edx, edx; lpClass
0x180025337  mov     [rsp+540h+lpcbMaxValueNameLen], rbx; lpcbMaxValueNameLen
0x18002533c  mov     [rsp+540h+lpcValues], rax; lpcValues
0x180025341  mov     [rsp+540h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x180025346  mov     [rsp+540h+lpcbMaxSubKeyLen], rbx; lpcbMaxSubKeyLen
0x18002534b  mov     [rsp+540h+phkResult], rbx; lpcSubKeys
0x180025350  mov     [rsp+540h+Wow64Process], ebx
0x180025354  call    cs:__imp_RegQueryInfoKeyW
0x18002535a  test    eax, eax
0x18002535c  jnz     loc_180025526
0x180025362  cmp     [rsp+540h+Wow64Process], ebx
0x180025366  jbe     loc_180025526
0x18002536c  mov     edi, ebx
0x18002536e  xor     edx, edx; Val
0x180025370  mov     [rbp+440h+ValueName], bx
0x180025374  mov     r8d, 206h; Size
0x18002537a  lea     rcx, [rbp+440h+var_45E]; void *
0x18002537e  call    memset
0x180025383  xor     edx, edx; Val
0x180025385  mov     [rsp+540h+cchValueName], 104h
0x18002538d  lea     rcx, [rbp+440h+var_4AE]; void *
0x180025391  mov     word ptr [rbp+440h+Data], bx
0x180025395  lea     r8d, [rdx+4Ch]; Size
0x180025399  call    memset
0x18002539e  mov     rcx, [rsp+540h+hKey]; hKey
0x1800253a3  lea     rax, [rsp+540h+cbData]
0x1800253a8  mov     [rsp+540h+lpcValues], rax; lpcbData
0x1800253ad  lea     r9, [rsp+540h+cchValueName]; lpcchValueName
0x1800253b2  lea     rax, [rbp+440h+Data]
0x1800253b6  mov     [rsp+540h+cbData], 4Eh ; 'N'
0x1800253be  mov     [rsp+540h+lpcbMaxClassLen], rax; lpData
0x1800253c3  lea     r8, [rbp+440h+ValueName]; lpValueName
0x1800253c7  lea     rax, [rsp+540h+Type]
0x1800253cc  mov     [rsp+540h+Type], ebx
0x1800253d0  mov     [rsp+540h+lpcbMaxSubKeyLen], rax; lpType
0x1800253d5  mov     edx, edi; dwIndex
0x1800253d7  mov     [rsp+540h+phkResult], rbx; lpReserved
0x1800253dc  call    cs:__imp_RegEnumValueW
0x1800253e2  test    eax, eax
0x1800253e4  jnz     short loc_180025406
0x1800253e6  cmp     [rsp+540h+Type], 1
0x1800253eb  jnz     short loc_180025406
0x1800253ed  mov     r8d, [rsp+540h+cchValueName]
0x1800253f2  lea     rdx, [rbp+440h+ValueName]; String2
0x1800253f6  dec     r8d; MaxCount
0x1800253f9  mov     rcx, r15; String1
0x1800253fc  call    cs:__imp__wcsnicmp
0x180025402  test    eax, eax
0x180025404  jz      short loc_180025417
0x180025406  inc     edi
0x180025408  cmp     edi, [rsp+540h+Wow64Process]
0x18002540c  jb      loc_18002536E
0x180025412  jmp     loc_180025526
0x180025417  mov     eax, ebx
0x180025419  lea     rcx, [rsi+4]; Destination
0x18002541d  cmp     r14, 0FFFFFFFF80000001h
0x180025424  lea     r8, [rbp+440h+ValueName]; Source
0x180025428  mov     edx, 104h; SizeInWords
0x18002542d  setnz   al
0x180025430  or      r15, 0FFFFFFFFFFFFFFFFh
0x180025434  inc     eax
0x180025436  mov     r9, r15; MaxCount
0x180025439  mov     [rsi], eax
0x18002543b  call    cs:__imp_wcsncpy_s
0x180025441  lea     r14, [rsi+20Ch]
0x180025448  mov     r9, r15; MaxCount
0x18002544b  mov     rcx, r14; Destination
0x18002544e  lea     r8, [rbp+440h+Data]; Source
0x180025452  lea     edx, [r15+28h]; SizeInWords
0x180025456  call    cs:__imp_wcsncpy_s
0x18002545c  mov     [rbp+440h+var_4C0], rbx
0x180025460  mov     edi, ebx
0x180025462  mov     [rsp+540h+var_4DC], ebx
0x180025466  call    cs:__imp_GetCurrentProcess
0x18002546c  mov     rcx, rax; hProcess
0x18002546f  lea     rdx, [rsp+540h+var_4DC]; Wow64Process
0x180025474  call    cs:__imp_IsWow64Process
0x18002547a  test    eax, eax
0x18002547c  jz      short loc_180025486
0x18002547e  cmp     [rsp+540h+var_4DC], ebx
0x180025482  cmovnz  edi, r13d
0x180025486  mov     rcx, [rsp+540h+hKey]; hKey
0x18002548b  lea     rax, [rbp+440h+var_4C0]
0x18002548f  or      edi, 1
0x180025492  mov     [rsp+540h+phkResult], rax; phkResult
0x180025497  mov     r9d, edi; samDesired
0x18002549a  xor     r8d, r8d; ulOptions
0x18002549d  mov     rdx, r14; lpSubKey
0x1800254a0  call    cs:__imp_RegOpenKeyExW
0x1800254a6  test    eax, eax
0x1800254a8  jnz     short loc_180025526
0x1800254aa  xor     edx, edx; Val
0x1800254ac  mov     word ptr [rbp+440h+var_250], bx
0x1800254b3  mov     r8d, 206h; Size
0x1800254b9  lea     rcx, [rbp+440h+var_24E]; void *
0x1800254c0  call    memset
0x1800254c5  mov     rcx, [rbp+440h+var_4C0]; hKey
0x1800254c9  lea     rax, [rsp+540h+var_4DC]
0x1800254ce  mov     [rsp+540h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800254d3  lea     rdx, aJitv64; "JitV64"
0x1800254da  lea     rax, [rbp+440h+var_250]
0x1800254e1  mov     [rsp+540h+var_4DC], 208h
0x1800254e9  xor     r9d, r9d; lpType
0x1800254ec  mov     [rsp+540h+phkResult], rax; lpData
0x1800254f1  xor     r8d, r8d; lpReserved
0x1800254f4  call    cs:__imp_RegQueryValueExW
0x1800254fa  test    eax, eax
0x1800254fc  jnz     short loc_18002551C
0x1800254fe  lea     rcx, [rsi+25Ah]; Destination
0x180025505  mov     r9, r15; MaxCount
0x180025508  lea     r8, [rbp+440h+var_250]; Source
0x18002550f  mov     edx, 104h; SizeInWords
0x180025514  call    cs:__imp_wcsncpy_s
0x18002551a  mov     bl, 1
0x18002551c  mov     rcx, [rbp+440h+var_4C0]; hKey
0x180025520  call    cs:__imp_RegCloseKey
0x180025526  mov     rcx, [rsp+540h+hKey]; hKey
0x18002552b  call    cs:__imp_RegCloseKey
0x180025531  mov     al, bl
0x180025533  mov     rcx, [rbp+440h+var_40]
0x18002553a  xor     rcx, rsp; StackCookie
0x18002553d  call    __security_check_cookie
0x180025542  add     rsp, 510h
0x180025549  pop     r15
0x18002554b  pop     r14
0x18002554d  pop     r13
0x18002554f  pop     rdi
0x180025550  pop     rsi
0x180025551  pop     rbx
0x180025552  pop     rbp
0x180025553  retn
```
