# ServerCacheStartup(void)

- ea: `0x18001943c`
- end: `0x1800195db`
- name: `?ServerCacheStartup@@YAKXZ`
- size: `415`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010f50`

## callees

- `0x180014dc0`
- `0x18001943c`
- `0x18002b044`
- `0x180030d4c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800194b7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800194b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800194f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019537`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001957a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800194f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019537`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001957a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800195cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800195cc`

## string_xrefs

- `0x180019459`: `Software\Microsoft\Cryptography\Calais\Cache`
- `0x1800194d4`: `CacheMaxBytesTotal`
- `0x18001951a`: `CacheMaxBytesPerItem`
- `0x18001955d`: `CacheMaxItemAgeDays`

## pseudocode

```c
__int64 ServerCacheStartup(void)
{
  unsigned int v0; // ebx
  LSTATUS v1; // eax
  LSTATUS v2; // eax
  LSTATUS v3; // eax
  __int64 v4; // rcx
  unsigned __int16 *v6; // [rsp+30h] [rbp-38h] BYREF
  int v7; // [rsp+38h] [rbp-30h] BYREF
  int v8; // [rsp+3Ch] [rbp-2Ch]
  __int64 v9; // [rsp+40h] [rbp-28h]
  void *(__fastcall *v10)(unsigned __int64); // [rsp+48h] [rbp-20h]
  void (__fastcall *v11)(const unsigned __int16 *); // [rsp+50h] [rbp-18h]
  DWORD cbData; // [rsp+80h] [rbp+18h] BYREF
  int Data; // [rsp+88h] [rbp+20h] BYREF
  unsigned int v14; // [rsp+90h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+30h] BYREF

  v6 = 0;
  v10 = AllocH;
  v14 = 0;
  v11 = ConstStringHeapFree;
  hKey = 0;
  Data = 0;
  cbData = 0;
  v9 = 5;
  v7 = 50000;
  v8 = 10000;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Cryptography\\Calais\\Cache", 0, 0x20019u, &hKey);
  if ( !v0 )
  {
    cbData = 4;
    v1 = RegQueryValueExW(hKey, L"CacheMaxBytesTotal", 0, 0, (LPBYTE)&Data, &cbData);
    v0 = v1;
    if ( v1 )
    {
      if ( v1 != 2 )
        goto LABEL_16;
    }
    else
    {
      v7 = Data;
    }
    cbData = 4;
    v2 = RegQueryValueExW(hKey, L"CacheMaxBytesPerItem", 0, 0, (LPBYTE)&Data, &cbData);
    v0 = v2;
    if ( v2 )
    {
      if ( v2 != 2 )
        goto LABEL_16;
    }
    else
    {
      v8 = Data;
    }
    cbData = 4;
    v3 = RegQueryValueExW(hKey, L"CacheMaxItemAgeDays", 0, 0, (LPBYTE)&Data, &cbData);
    v0 = v3;
    if ( v3 )
    {
      if ( v3 != 2 )
        goto LABEL_16;
    }
    else
    {
      LODWORD(v9) = Data;
    }
    I_ServerCacheReadDataFromDisk((unsigned __int8 **)&v6, &v14);
    v0 = ScCacheInitializeCache(v4, &v7, v6, v14);
    if ( v6 )
      ConstStringHeapFree(v6);
  }
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x18001943c  push    rbp
0x18001943e  push    rbx
0x18001943f  mov     rbp, rsp
0x180019442  sub     rsp, 68h
0x180019446  lea     rax, ?AllocH@@YAPEAX_K@Z; AllocH(unsigned __int64)
0x18001944d  mov     [rbp+var_38], 0
0x180019455  mov     [rbp+var_20], rax
0x180019459  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Cryptography\\Cala"...
0x180019460  lea     rax, ?ConstStringHeapFree@@YAXPEBG@Z; ConstStringHeapFree(ushort const *)
0x180019467  mov     [rbp+arg_10], 0
0x18001946e  mov     [rbp+var_18], rax
0x180019472  mov     r9d, 20019h; samDesired
0x180019478  lea     rax, [rbp+hKey]
0x18001947c  mov     [rbp+hKey], 0
0x180019484  xor     r8d, r8d; ulOptions
0x180019487  mov     [rsp+68h+phkResult], rax; phkResult
0x18001948c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019493  mov     [rbp+Data], 0
0x18001949a  mov     [rbp+cbData], 0
0x1800194a1  mov     [rbp+var_28], 5
0x1800194a9  mov     [rbp+var_30], 0C350h
0x1800194b0  mov     [rbp+var_2C], 2710h
0x1800194b7  call    cs:__imp_RegOpenKeyExW
0x1800194bd  mov     ebx, eax
0x1800194bf  test    eax, eax
0x1800194c1  jnz     loc_1800195C3
0x1800194c7  mov     rcx, [rbp+hKey]; hKey
0x1800194cb  lea     rax, [rbp+cbData]
0x1800194cf  mov     [rsp+68h+lpcbData], rax; lpcbData
0x1800194d4  lea     rdx, ValueName; "CacheMaxBytesTotal"
0x1800194db  lea     rax, [rbp+Data]
0x1800194df  mov     [rbp+cbData], 4
0x1800194e6  xor     r9d, r9d; lpType
0x1800194e9  mov     [rsp+68h+phkResult], rax; lpData
0x1800194ee  xor     r8d, r8d; lpReserved
0x1800194f1  call    cs:__imp_RegQueryValueExW
0x1800194f7  mov     ebx, eax
0x1800194f9  test    eax, eax
0x1800194fb  jz      short loc_180019507
0x1800194fd  cmp     eax, 2
0x180019500  jz      short loc_18001950D
0x180019502  jmp     loc_1800195C3
0x180019507  mov     eax, [rbp+Data]
0x18001950a  mov     [rbp+var_30], eax
0x18001950d  mov     rcx, [rbp+hKey]; hKey
0x180019511  lea     rax, [rbp+cbData]
0x180019515  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18001951a  lea     rdx, aCachemaxbytesp; "CacheMaxBytesPerItem"
0x180019521  lea     rax, [rbp+Data]
0x180019525  mov     [rbp+cbData], 4
0x18001952c  xor     r9d, r9d; lpType
0x18001952f  mov     [rsp+68h+phkResult], rax; lpData
0x180019534  xor     r8d, r8d; lpReserved
0x180019537  call    cs:__imp_RegQueryValueExW
0x18001953d  mov     ebx, eax
0x18001953f  test    eax, eax
0x180019541  jz      short loc_18001954A
0x180019543  cmp     eax, 2
0x180019546  jz      short loc_180019550
0x180019548  jmp     short loc_1800195C3
0x18001954a  mov     eax, [rbp+Data]
0x18001954d  mov     [rbp+var_2C], eax
0x180019550  mov     rcx, [rbp+hKey]; hKey
0x180019554  lea     rax, [rbp+cbData]
0x180019558  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18001955d  lea     rdx, aCachemaxitemag; "CacheMaxItemAgeDays"
0x180019564  lea     rax, [rbp+Data]
0x180019568  mov     [rbp+cbData], 4
0x18001956f  xor     r9d, r9d; lpType
0x180019572  mov     [rsp+68h+phkResult], rax; lpData
0x180019577  xor     r8d, r8d; lpReserved
0x18001957a  call    cs:__imp_RegQueryValueExW
0x180019580  mov     ebx, eax
0x180019582  test    eax, eax
0x180019584  jz      short loc_18001958D
0x180019586  cmp     eax, 2
0x180019589  jz      short loc_180019593
0x18001958b  jmp     short loc_1800195C3
0x18001958d  mov     eax, [rbp+Data]
0x180019590  mov     dword ptr [rbp+var_28], eax
0x180019593  lea     rdx, [rbp+arg_10]; unsigned int *
0x180019597  lea     rcx, [rbp+var_38]; unsigned __int8 **
0x18001959b  call    ?I_ServerCacheReadDataFromDisk@@YAKPEAPEAEPEAK@Z; I_ServerCacheReadDataFromDisk(uchar * *,ulong *)
0x1800195a0  mov     r9d, [rbp+arg_10]
0x1800195a4  lea     rdx, [rbp+var_30]
0x1800195a8  mov     r8, [rbp+var_38]
0x1800195ac  call    ScCacheInitializeCache
0x1800195b1  mov     ebx, eax
0x1800195b3  cmp     [rbp+var_38], 0
0x1800195b8  jz      short loc_1800195C3
0x1800195ba  mov     rcx, [rbp+var_38]; unsigned __int16 *
0x1800195be  call    ?ConstStringHeapFree@@YAXPEBG@Z; ConstStringHeapFree(ushort const *)
0x1800195c3  mov     rcx, [rbp+hKey]; hKey
0x1800195c7  test    rcx, rcx
0x1800195ca  jz      short loc_1800195D2
0x1800195cc  call    cs:__imp_RegCloseKey
0x1800195d2  mov     eax, ebx
0x1800195d4  add     rsp, 68h
0x1800195d8  pop     rbx
0x1800195d9  pop     rbp
0x1800195da  retn
```
