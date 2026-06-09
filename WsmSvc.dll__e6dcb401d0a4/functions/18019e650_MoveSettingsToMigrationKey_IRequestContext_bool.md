# MoveSettingsToMigrationKey(IRequestContext *,bool)

- ea: `0x18019e650`
- end: `0x18019e9af`
- name: `?MoveSettingsToMigrationKey@@YAHPEAVIRequestContext@@_N@Z`
- size: `863`
- prototype: `__int64 __fastcall(struct IRequestContext *, bool)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005d10`
- `0x18000f700`
- `0x1800bac30`
- `0x18010e030`
- `0x180127d28`
- `0x18019e068`
- `0x18019e650`

## import_xrefs

- `msvcrt!fwprintf` at `0x18019e781`
- `msvcrt!fwprintf` at `0x18019e8fa`
- `msvcrt!fwprintf` at `0x18019e95e`
- `msvcrt!fwprintf` at `0x18019e97a`
- `msvcrt!fwprintf` at `0x18019e9a3`
- `msvcrt!fwprintf` at `0x18019e781`
- `msvcrt!fwprintf` at `0x18019e8fa`
- `msvcrt!fwprintf` at `0x18019e95e`
- `msvcrt!fwprintf` at `0x18019e97a`
- `msvcrt!fwprintf` at `0x18019e9a3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18019e824`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18019e863`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18019e824`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18019e863`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18019e6ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18019e755`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18019e6ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18019e755`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18019e7dc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18019e7dc`

## string_xrefs

- `0x18019e6d0`: `Plugin`
- `0x18019e890`: `Plugin`
- `0x18019e691`: `onecore\admin\wmi\wmx\config\configutils.cpp`
- `0x18019e6a4`: `Service`
- `0x18019e77a`: `Can not RegOpenKeyEx error: %d \n`
- `0x18019e8da`: `Can not RegCreateKeyEx.\n`
- `0x18019e973`: `Can not RegCreateKeyEx.\n`
- `0x18019e957`: `Can not WSManSHCopyKeyW Error - %d.\n`
- `0x18019e8f3`: `Can not ClearRegistrySettings.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MoveSettingsToMigrationKey(struct IRequestContext *a1, char a2)
{
  unsigned int v5; // ebx
  unsigned int v6; // edi
  const WCHAR *v7; // r14
  LSTATUS v8; // eax
  unsigned int v9; // esi
  FILE *v10; // rax
  HKEY v11; // rcx
  unsigned int v12; // r9d
  unsigned int v13; // esi
  FILE *v14; // rax
  FILE *v15; // rax
  FILE *v16; // rax
  FILE *v17; // rax
  FILE *v18; // rax
  HKEY phkResult; // [rsp+60h] [rbp-19h] BYREF
  HKEY v20; // [rsp+68h] [rbp-11h] BYREF
  HKEY hKeyDest; // [rsp+70h] [rbp-9h] BYREF
  LPCWSTR lpSubKey[11]; // [rsp+78h] [rbp-1h]
  DWORD cValues; // [rsp+E0h] [rbp+67h] BYREF
  DWORD cSubKeys; // [rsp+F0h] [rbp+77h] BYREF
  HKEY hKey; // [rsp+F8h] [rbp+7Fh] BYREF

  if ( !a1 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\config\\configutils.cpp", 2188, L"2188", 0x54Fu, 0);
    return 0;
  }
  lpSubKey[0] = L"Service";
  lpSubKey[1] = L"Client";
  lpSubKey[2] = L"Listener";
  lpSubKey[3] = L"CertMapping";
  lpSubKey[4] = L"Plugin";
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WSMAN", 0, 0xF013Fu, &hKey) )
  {
LABEL_5:
    AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&hKey);
    return 0;
  }
  v20 = 0;
  v5 = 0;
  v6 = 1;
  while ( 1 )
  {
    if ( v5 >= 5 )
      goto LABEL_25;
    phkResult = 0;
    cSubKeys = 0;
    cValues = 0;
    v7 = lpSubKey[v5];
    v8 = RegOpenKeyExW(hKey, v7, 0, 0x10Bu, &phkResult);
    v9 = v8;
    if ( !v8 )
      break;
    if ( v8 != 2 )
    {
      v10 = _acrt_iob_func(2u);
      fwprintf(v10, L"Can not RegOpenKeyEx error: %d \n", v9);
LABEL_11:
      AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&phkResult);
      AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&v20);
      goto LABEL_5;
    }
LABEL_22:
    AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&phkResult);
    ++v5;
  }
  if ( RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, 0, 0, &cValues, 0, 0, 0, 0) )
  {
    v18 = _acrt_iob_func(2u);
    fwprintf(v18, L"Can not RegQueryInfoKey.\n");
    goto LABEL_11;
  }
  v11 = v20;
  if ( !v20 )
  {
    if ( RegCreateKeyExW(hKey, L"Migration", 0, 0, 0, 0x103u, 0, &v20, 0) )
    {
      v14 = _acrt_iob_func(2u);
      fwprintf(v14, L"Can not RegCreateKeyEx.\n");
      goto LABEL_11;
    }
    v11 = v20;
  }
  hKeyDest = 0;
  if ( RegCreateKeyExW(v11, v7, 0, 0, 0, 0xF013Fu, 0, &hKeyDest, 0) )
  {
    v17 = _acrt_iob_func(2u);
    fwprintf(v17, L"Can not RegCreateKeyEx.\n");
    goto LABEL_28;
  }
  v13 = WSManSHCopyKeyW(hKey, v7, hKeyDest, v12);
  if ( v13 )
  {
    v16 = _acrt_iob_func(2u);
    fwprintf(v16, L"Can not WSManSHCopyKeyW Error - %d.\n", v13);
LABEL_28:
    AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&hKeyDest);
    goto LABEL_11;
  }
  if ( !a2 || (unsigned int)StringCchEquals(v7, L"Plugin") || ClearRegistrySettings(phkResult, v7, a1) )
  {
    AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&hKeyDest);
    goto LABEL_22;
  }
  v15 = _acrt_iob_func(2u);
  fwprintf(v15, L"Can not ClearRegistrySettings.\n");
  AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&hKeyDest);
  AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&phkResult);
  v6 = 0;
LABEL_25:
  AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&v20);
  AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(&hKey);
  return v6;
}

```

## disassembly

```asm
0x18019e650  mov     [rsp-8+arg_8], rbx
0x18019e655  push    rbp
0x18019e656  push    rsi
0x18019e657  push    rdi
0x18019e658  push    r12
0x18019e65a  push    r13
0x18019e65c  push    r14
0x18019e65e  push    r15
0x18019e660  lea     rbp, [rsp-27h]
0x18019e665  sub     rsp, 0A0h
0x18019e66c  mov     r12b, dl
0x18019e66f  mov     r15, rcx
0x18019e672  xor     r13d, r13d
0x18019e675  test    rcx, rcx
0x18019e678  jnz     short loc_18019E6A4
0x18019e67a  mov     [rsp+0D0h+phkResult], r13; struct IRequestContext *
0x18019e67f  mov     r9d, 54Fh; unsigned int
0x18019e685  lea     r8, a2188; "2188"
0x18019e68c  mov     edx, 88Ch; unsigned int
0x18019e691  lea     rcx, aOnecoreAdminWm_22; "onecore\\admin\\wmi\\wmx\\config\\confi"...
0x18019e698  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18019e69d  xor     eax, eax
0x18019e69f  jmp     loc_18019E92C
0x18019e6a4  lea     rax, aService; "Service"
0x18019e6ab  mov     [rbp+57h+lpSubKey], rax
0x18019e6af  lea     rax, aClient_0; "Client"
0x18019e6b6  mov     [rbp+57h+var_50], rax
0x18019e6ba  lea     rax, aListener_0; "Listener"
0x18019e6c1  mov     [rbp+57h+var_48], rax
0x18019e6c5  lea     rax, aCertmapping; "CertMapping"
0x18019e6cc  mov     [rbp+57h+var_40], rax
0x18019e6d0  lea     rax, aPlugin; "Plugin"
0x18019e6d7  mov     [rbp+57h+var_38], rax
0x18019e6db  mov     [rbp+57h+hKey], r13
0x18019e6df  lea     rax, [rbp+57h+hKey]
0x18019e6e3  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18019e6e8  mov     r9d, 0F013Fh; samDesired
0x18019e6ee  xor     r8d, r8d; ulOptions
0x18019e6f1  lea     rdx, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18019e6f8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18019e6ff  call    cs:__imp_RegOpenKeyExW
0x18019e705  test    eax, eax
0x18019e707  jz      short loc_18019E714
0x18019e709  lea     rcx, [rbp+57h+hKey]
0x18019e70d  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x18019e712  jmp     short loc_18019E69D
0x18019e714  mov     [rbp+57h+var_68], r13
0x18019e718  mov     ebx, r13d
0x18019e71b  mov     edi, 1
0x18019e720  cmp     ebx, 5
0x18019e723  jnb     loc_18019E917
0x18019e729  mov     [rbp+57h+var_70], r13
0x18019e72d  mov     [rbp+57h+cSubKeys], r13d
0x18019e731  mov     [rbp+57h+cValues], r13d
0x18019e735  mov     eax, ebx
0x18019e737  mov     r14, [rbp+rax*8+57h+lpSubKey]
0x18019e73c  lea     rax, [rbp+57h+var_70]
0x18019e740  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18019e745  mov     r9d, 10Bh; samDesired
0x18019e74b  xor     r8d, r8d; ulOptions
0x18019e74e  mov     rdx, r14; lpSubKey
0x18019e751  mov     rcx, [rbp+57h+hKey]; hKey
0x18019e755  call    cs:__imp_RegOpenKeyExW
0x18019e75b  mov     esi, eax
0x18019e75d  test    eax, eax
0x18019e75f  jz      short loc_18019E7A0
0x18019e761  cmp     eax, 2
0x18019e764  jz      loc_18019E8C0
0x18019e76a  mov     ecx, 2; Ix
0x18019e76f  call    __acrt_iob_func
0x18019e774  mov     rcx, rax; Stream
0x18019e777  mov     r8d, esi
0x18019e77a  lea     rdx, aCanNotRegopenk; "Can not RegOpenKeyEx error: %d \n"
0x18019e781  call    cs:__imp_fwprintf
0x18019e787  nop
0x18019e788  lea     rcx, [rbp+57h+var_70]
0x18019e78c  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x18019e791  nop
0x18019e792  lea     rcx, [rbp+57h+var_68]
0x18019e796  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x18019e79b  jmp     loc_18019E709
0x18019e7a0  mov     [rsp+0D0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18019e7a5  mov     [rsp+0D0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18019e7aa  mov     [rsp+0D0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18019e7af  mov     [rsp+0D0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18019e7b4  lea     rax, [rbp+57h+cValues]
0x18019e7b8  mov     [rsp+0D0h+lpcValues], rax; lpcValues
0x18019e7bd  mov     [rsp+0D0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18019e7c2  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x18019e7c7  lea     rax, [rbp+57h+cSubKeys]
0x18019e7cb  mov     [rsp+0D0h+phkResult], rax; lpcSubKeys
0x18019e7d0  xor     r9d, r9d; lpReserved
0x18019e7d3  xor     r8d, r8d; lpcchClass
0x18019e7d6  xor     edx, edx; lpClass
0x18019e7d8  mov     rcx, [rbp+57h+var_70]; hKey
0x18019e7dc  call    cs:__imp_RegQueryInfoKeyW
0x18019e7e2  test    eax, eax
0x18019e7e4  jnz     loc_18019E98F
0x18019e7ea  mov     rcx, [rbp+57h+var_68]
0x18019e7ee  test    rcx, rcx
0x18019e7f1  jnz     short loc_18019E836
0x18019e7f3  mov     [rsp+0D0h+lpcbMaxValueNameLen], r13; lpdwDisposition
0x18019e7f8  lea     rax, [rbp+57h+var_68]
0x18019e7fc  mov     [rsp+0D0h+lpcValues], rax; phkResult
0x18019e801  mov     [rsp+0D0h+lpcbMaxClassLen], r13; lpSecurityAttributes
0x18019e806  mov     dword ptr [rsp+0D0h+lpcbMaxSubKeyLen], 103h; samDesired
0x18019e80e  mov     dword ptr [rsp+0D0h+phkResult], r13d; dwOptions
0x18019e813  xor     r9d, r9d; lpClass
0x18019e816  xor     r8d, r8d; Reserved
0x18019e819  lea     rdx, aMigration; "Migration"
0x18019e820  mov     rcx, [rbp+57h+hKey]; hKey
0x18019e824  call    cs:__imp_RegCreateKeyExW
0x18019e82a  test    eax, eax
0x18019e82c  jnz     loc_18019E8D0
0x18019e832  mov     rcx, [rbp+57h+var_68]; hKey
0x18019e836  mov     [rbp+57h+hKeyDest], r13
0x18019e83a  mov     [rsp+0D0h+lpcbMaxValueNameLen], r13; lpdwDisposition
0x18019e83f  lea     rax, [rbp+57h+hKeyDest]
0x18019e843  mov     [rsp+0D0h+lpcValues], rax; phkResult
0x18019e848  mov     [rsp+0D0h+lpcbMaxClassLen], r13; lpSecurityAttributes
0x18019e84d  mov     dword ptr [rsp+0D0h+lpcbMaxSubKeyLen], 0F013Fh; samDesired
0x18019e855  mov     dword ptr [rsp+0D0h+phkResult], r13d; dwOptions
0x18019e85a  xor     r9d, r9d; lpClass
0x18019e85d  xor     r8d, r8d; Reserved
0x18019e860  mov     rdx, r14; lpSubKey
0x18019e863  call    cs:__imp_RegCreateKeyExW
0x18019e869  test    eax, eax
0x18019e86b  jnz     loc_18019E966
0x18019e871  mov     r8, [rbp+57h+hKeyDest]; hKeyDest
0x18019e875  mov     rdx, r14; lpSubKey
0x18019e878  mov     rcx, [rbp+57h+hKey]; hKeySrc
0x18019e87c  call    ?WSManSHCopyKeyW@@YAJPEAUHKEY__@@PEBG0K@Z; WSManSHCopyKeyW(HKEY__ *,ushort const *,HKEY__ *,ulong)
0x18019e881  mov     esi, eax
0x18019e883  test    eax, eax
0x18019e885  jnz     loc_18019E947
0x18019e88b  test    r12b, r12b
0x18019e88e  jz      short loc_18019E8B6
0x18019e890  lea     rdx, aPlugin; "Plugin"
0x18019e897  mov     rcx, r14; unsigned __int16 *
0x18019e89a  call    ?StringCchEquals@@YAHPEBG0@Z; StringCchEquals(ushort const *,ushort const *)
0x18019e89f  test    eax, eax
0x18019e8a1  jnz     short loc_18019E8B6
0x18019e8a3  mov     r8, r15; struct IRequestContext *
0x18019e8a6  mov     rdx, r14; unsigned __int16 *
0x18019e8a9  mov     rcx, [rbp+57h+var_70]; HKEY
0x18019e8ad  call    ?ClearRegistrySettings@@YAHPEAUHKEY__@@PEBGPEAVIRequestContext@@@Z; ClearRegistrySettings(HKEY__ *,ushort const *,IRequestContext *)
0x18019e8b2  test    eax, eax
0x18019e8b4  jz      short loc_18019E8E6
0x18019e8b6  lea     rcx, [rbp+57h+hKeyDest]
0x18019e8ba  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x18019e8bf  nop
0x18019e8c0  lea     rcx, [rbp+57h+var_70]
0x18019e8c4  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x18019e8c9  add     ebx, edi
0x18019e8cb  jmp     loc_18019E720
0x18019e8d0  mov     ecx, 2; Ix
0x18019e8d5  call    __acrt_iob_func
0x18019e8da  lea     rdx, aCanNotRegcreat; "Can not RegCreateKeyEx.\n"
0x18019e8e1  jmp     loc_18019E9A0
0x18019e8e6  mov     ecx, 2; Ix
0x18019e8eb  call    __acrt_iob_func
0x18019e8f0  mov     rcx, rax; Stream
0x18019e8f3  lea     rdx, aCanNotClearreg; "Can not ClearRegistrySettings.\n"
0x18019e8fa  call    cs:__imp_fwprintf
0x18019e900  nop
0x18019e901  lea     rcx, [rbp+57h+hKeyDest]
0x18019e905  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x18019e90a  nop
0x18019e90b  lea     rcx, [rbp+57h+var_70]
0x18019e90f  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x18019e914  mov     edi, r13d
0x18019e917  lea     rcx, [rbp+57h+var_68]
0x18019e91b  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x18019e920  nop
0x18019e921  lea     rcx, [rbp+57h+hKey]
0x18019e925  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x18019e92a  mov     eax, edi
0x18019e92c  mov     rbx, [rsp+0D0h+arg_8]
0x18019e934  add     rsp, 0A0h
0x18019e93b  pop     r15
0x18019e93d  pop     r14
0x18019e93f  pop     r13
0x18019e941  pop     r12
0x18019e943  pop     rdi
0x18019e944  pop     rsi
0x18019e945  pop     rbp
0x18019e946  retn
0x18019e947  mov     ecx, 2; Ix
0x18019e94c  call    __acrt_iob_func
0x18019e951  mov     rcx, rax; Stream
0x18019e954  mov     r8d, esi
0x18019e957  lea     rdx, aCanNotWsmanshc; "Can not WSManSHCopyKeyW Error - %d.\n"
0x18019e95e  call    cs:__imp_fwprintf
0x18019e964  jmp     short loc_18019E981
0x18019e966  mov     ecx, 2; Ix
0x18019e96b  call    __acrt_iob_func
0x18019e970  mov     rcx, rax; Stream
0x18019e973  lea     rdx, aCanNotRegcreat; "Can not RegCreateKeyEx.\n"
0x18019e97a  call    cs:__imp_fwprintf
0x18019e980  nop
0x18019e981  lea     rcx, [rbp+57h+hKeyDest]
0x18019e985  call    ??1?$AutoCleanup@VAutoRegKey@@PEAUHKEY__@@@@QEAA@XZ; AutoCleanup<AutoRegKey,HKEY__ *>::~AutoCleanup<AutoRegKey,HKEY__ *>(void)
0x18019e98a  jmp     loc_18019E788
0x18019e98f  mov     ecx, 2; Ix
0x18019e994  call    __acrt_iob_func
0x18019e999  lea     rdx, aCanNotRegquery; "Can not RegQueryInfoKey.\n"
0x18019e9a0  mov     rcx, rax; Stream
0x18019e9a3  call    cs:__imp_fwprintf
0x18019e9a9  jmp     loc_18019E788
```
