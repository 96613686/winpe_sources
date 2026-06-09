# CEnumInstalledApps::_GetNextDarwinApp(IInstalledApp * *)

- ea: `0x18002d784`
- end: `0x18002d9c3`
- name: `?_GetNextDarwinApp@CEnumInstalledApps@@IEAAJPEAPEAUIInstalledApp@@@Z`
- size: `575`
- prototype: `int(CEnumInstalledApps *__hidden this, struct IInstalledApp **)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002d580`

## callees

- `0x180007960`
- `0x18002cf38`
- `0x18002d784`
- `0x1800582e0`

## import_xrefs

- `SHCORE!SHQueryValueExW` at `0x18002d867`
- `SHCORE!SHQueryValueExW` at `0x18002d911`
- `SHCORE!SHQueryValueExW` at `0x18002d867`
- `SHCORE!SHQueryValueExW` at `0x18002d911`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d829`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d8d3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d829`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002d8d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d884`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d92f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d884`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d92f`
- `msi!__imp_MsiEnumProductsW` at `0x18002d7c5`
- `msi!__imp_MsiEnumProductsW` at `0x18002d7c5`
- `msi!__imp_MsiQueryProductStateW` at `0x18002d940`
- `msi!__imp_MsiQueryProductStateW` at `0x18002d940`

## string_xrefs

- `0x18002d7d6`: `Software\Microsoft\Windows\CurrentVersion\Uninstall`
- `0x18002d841`: `SystemComponent`
- `0x18002d8eb`: `SystemComponent`
- `0x18002d892`: `Software\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall`

## pseudocode

```c
__int64 __fastcall CEnumInstalledApps::_GetNextDarwinApp(CEnumInstalledApps *this, struct IInstalledApp **a2)
{
  WCHAR *v3; // r14
  int Instance; // edi
  UINT v6; // eax
  BOOL v7; // ebx
  const struct _GUID *v8; // r9
  int pvData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pdwType; // [rsp+34h] [rbp-CCh] BYREF
  DWORD pcbData; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hkey[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-B0h] BYREF

  v3 = (WCHAR *)((char *)this + 40);
  Instance = -2147467259;
  while ( 1 )
  {
    while ( 1 )
    {
      v6 = MsiEnumProductsW(*((_DWORD *)this + 5), v3);
      if ( v6 )
        break;
      ++*((_DWORD *)this + 5);
      hkey[0] = 0;
      pdwType = 0;
      StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall", v3);
      v7 = 1;
      if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, hkey) )
        goto LABEL_27;
      pvData = 0;
      pcbData = 4;
      if ( !SHQueryValueExW(hkey[0], L"SystemComponent", 0, &pdwType, &pvData, &pcbData) && pdwType == 4 )
        v7 = pvData != 1;
      RegCloseKey(hkey[0]);
      if ( v7 )
      {
LABEL_27:
        StringCchPrintfW(
          SubKey,
          0x104u,
          L"%s\\%s",
          L"Software\\Wow6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall",
          v3);
        if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, hkey) )
          goto LABEL_28;
        pvData = 0;
        pcbData = 4;
        if ( !SHQueryValueExW(hkey[0], L"SystemComponent", 0, &pdwType, &pvData, &pcbData)
          && pdwType == 4
          && pvData == 1 )
        {
          v7 = 0;
        }
        RegCloseKey(hkey[0]);
        if ( v7 )
        {
LABEL_28:
          if ( ((MsiQueryProductStateW(v3) - 1) & 0xFFFFFFFB) == 0 )
          {
            Instance = CInstalledApp::s_CreateInstance(0, v3, MSIINSTALLCONTEXT_FIRSTVISIBLE, v8, (void **)a2);
            if ( Instance >= 0 )
              return (unsigned int)Instance;
          }
        }
      }
    }
    if ( v6 == 5 )
      break;
    if ( v6 == 87 )
      return (unsigned int)-2147024809;
    if ( v6 == 120 || v6 == 259 )
      return (unsigned int)Instance;
    ++*((_DWORD *)this + 5);
  }
  return (unsigned int)-2147024891;
}

```

## disassembly

```asm
0x18002d784  mov     [rsp-8+arg_10], rbx
0x18002d789  push    rbp
0x18002d78a  push    rsi
0x18002d78b  push    rdi
0x18002d78c  push    r14
0x18002d78e  push    r15
0x18002d790  lea     rbp, [rsp-170h]
0x18002d798  sub     rsp, 270h
0x18002d79f  mov     rax, cs:__security_cookie
0x18002d7a6  xor     rax, rsp
0x18002d7a9  mov     [rbp+190h+var_30], rax
0x18002d7b0  mov     r15, rdx
0x18002d7b3  lea     r14, [rcx+28h]
0x18002d7b7  mov     rsi, rcx
0x18002d7ba  mov     edi, 80004005h
0x18002d7bf  mov     ecx, [rsi+14h]; iProductIndex
0x18002d7c2  mov     rdx, r14; lpProductBuf
0x18002d7c5  call    cs:__imp_MsiEnumProductsW
0x18002d7cb  test    eax, eax
0x18002d7cd  jnz     loc_18002D971
0x18002d7d3  inc     dword ptr [rsi+14h]
0x18002d7d6  lea     r9, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002d7dd  lea     r8, aSS; "%s\\%s"
0x18002d7e4  mov     [rsp+290h+hkey], 0
0x18002d7ed  mov     edx, 104h; unsigned __int64
0x18002d7f2  mov     [rsp+290h+pdwType], eax
0x18002d7f6  lea     rcx, [rsp+290h+SubKey]; unsigned __int16 *
0x18002d7fb  mov     [rsp+290h+phkResult], r14
0x18002d800  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002d805  lea     rax, [rsp+290h+hkey]
0x18002d80a  mov     r9d, 20019h; samDesired
0x18002d810  xor     r8d, r8d; ulOptions
0x18002d813  mov     [rsp+290h+phkResult], rax; phkResult
0x18002d818  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x18002d81d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d824  mov     ebx, 1
0x18002d829  call    cs:__imp_RegOpenKeyExW
0x18002d82f  test    eax, eax
0x18002d831  jnz     short loc_18002D892
0x18002d833  mov     rcx, [rsp+290h+hkey]; hkey
0x18002d838  lea     r9, [rsp+290h+pdwType]; pdwType
0x18002d83d  mov     [rsp+290h+pvData], eax
0x18002d841  lea     rdx, aSystemcomponen; "SystemComponent"
0x18002d848  lea     rax, [rsp+290h+var_258]
0x18002d84d  mov     [rsp+290h+var_258], 4
0x18002d855  mov     [rsp+290h+pcbData], rax; pcbData
0x18002d85a  xor     r8d, r8d; pdwReserved
0x18002d85d  lea     rax, [rsp+290h+pvData]
0x18002d862  mov     [rsp+290h+phkResult], rax; pvData
0x18002d867  call    cs:__imp_SHQueryValueExW
0x18002d86d  test    eax, eax
0x18002d86f  jnz     short loc_18002D87F
0x18002d871  cmp     [rsp+290h+pdwType], 4
0x18002d876  jnz     short loc_18002D87F
0x18002d878  cmp     [rsp+290h+pvData], ebx
0x18002d87c  cmovz   ebx, eax
0x18002d87f  mov     rcx, [rsp+290h+hkey]; hKey
0x18002d884  call    cs:__imp_RegCloseKey
0x18002d88a  test    ebx, ebx
0x18002d88c  jz      loc_18002D7BF
0x18002d892  lea     r9, aSoftwareWow643; "Software\\Wow6432Node\\Microsoft\\Windo"...
0x18002d899  mov     [rsp+290h+phkResult], r14
0x18002d89e  lea     r8, aSS; "%s\\%s"
0x18002d8a5  mov     edx, 104h; unsigned __int64
0x18002d8aa  lea     rcx, [rsp+290h+SubKey]; unsigned __int16 *
0x18002d8af  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002d8b4  lea     rax, [rsp+290h+hkey]
0x18002d8b9  mov     r9d, 20019h; samDesired
0x18002d8bf  xor     r8d, r8d; ulOptions
0x18002d8c2  mov     [rsp+290h+phkResult], rax; phkResult
0x18002d8c7  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x18002d8cc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d8d3  call    cs:__imp_RegOpenKeyExW
0x18002d8d9  test    eax, eax
0x18002d8db  jnz     short loc_18002D93D
0x18002d8dd  mov     rcx, [rsp+290h+hkey]; hkey
0x18002d8e2  lea     r9, [rsp+290h+pdwType]; pdwType
0x18002d8e7  mov     [rsp+290h+pvData], eax
0x18002d8eb  lea     rdx, aSystemcomponen; "SystemComponent"
0x18002d8f2  lea     rax, [rsp+290h+var_258]
0x18002d8f7  mov     [rsp+290h+var_258], 4
0x18002d8ff  mov     [rsp+290h+pcbData], rax; pcbData
0x18002d904  xor     r8d, r8d; pdwReserved
0x18002d907  lea     rax, [rsp+290h+pvData]
0x18002d90c  mov     [rsp+290h+phkResult], rax; pvData
0x18002d911  call    cs:__imp_SHQueryValueExW
0x18002d917  test    eax, eax
0x18002d919  jnz     short loc_18002D92A
0x18002d91b  cmp     [rsp+290h+pdwType], 4
0x18002d920  jnz     short loc_18002D92A
0x18002d922  cmp     [rsp+290h+pvData], 1
0x18002d927  cmovz   ebx, eax
0x18002d92a  mov     rcx, [rsp+290h+hkey]; hKey
0x18002d92f  call    cs:__imp_RegCloseKey
0x18002d935  test    ebx, ebx
0x18002d937  jz      loc_18002D7BF
0x18002d93d  mov     rcx, r14; szProduct
0x18002d940  call    cs:__imp_MsiQueryProductStateW
0x18002d946  dec     eax
0x18002d948  test    eax, 0FFFFFFFBh
0x18002d94d  jnz     loc_18002D7BF
0x18002d953  xor     r8d, r8d; enum tagMSIINSTALLCONTEXT
0x18002d956  mov     [rsp+290h+phkResult], r15; void **
0x18002d95b  mov     rdx, r14; szProduct
0x18002d95e  xor     ecx, ecx; unsigned __int16 *
0x18002d960  call    ?s_CreateInstance@CInstalledApp@@SAJPEBG0W4tagMSIINSTALLCONTEXT@@AEBU_GUID@@PEAPEAX@Z; CInstalledApp::s_CreateInstance(ushort const *,ushort const *,tagMSIINSTALLCONTEXT,_GUID const &,void * *)
0x18002d965  mov     edi, eax
0x18002d967  test    eax, eax
0x18002d969  js      loc_18002D7BF
0x18002d96f  jmp     short loc_18002D99B
0x18002d971  cmp     eax, 5
0x18002d974  jz      short loc_18002D996
0x18002d976  cmp     eax, 57h ; 'W'
0x18002d979  jz      short loc_18002D98F
0x18002d97b  cmp     eax, 78h ; 'x'
0x18002d97e  jz      short loc_18002D99B
0x18002d980  cmp     eax, 103h
0x18002d985  jz      short loc_18002D99B
0x18002d987  inc     dword ptr [rsi+14h]
0x18002d98a  jmp     loc_18002D7BF
0x18002d98f  mov     edi, 80070057h
0x18002d994  jmp     short loc_18002D99B
0x18002d996  mov     edi, 80070005h
0x18002d99b  mov     eax, edi
0x18002d99d  mov     rcx, [rbp+190h+var_30]
0x18002d9a4  xor     rcx, rsp; StackCookie
0x18002d9a7  call    __security_check_cookie
0x18002d9ac  mov     rbx, [rsp+290h+arg_10]
0x18002d9b4  add     rsp, 270h
0x18002d9bb  pop     r15
0x18002d9bd  pop     r14
0x18002d9bf  pop     rdi
0x18002d9c0  pop     rsi
0x18002d9c1  pop     rbp
0x18002d9c2  retn
```
