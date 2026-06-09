# AmiRegGetStoreFullPath

- ea: `0x180039f04`
- end: `0x18003a1c1`
- name: `AmiRegGetStoreFullPath`
- size: `701`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003a1e4`

## callees

- `0x180005890`
- `0x180006938`
- `0x18000cb30`
- `0x18000cb74`
- `0x1800295dc`
- `0x180039f04`
- `0x18003b5e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18003a10f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18003a13c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18003a10f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18003a13c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a15d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a15d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18003a05f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18003a05f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003a008`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003a008`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003a01d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003a01d`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18003a03d`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18003a03d`

## string_xrefs

- `0x18003a0d1`: `Amcache`
- `0x18003a163`: `GetSystemWindowsDirectory [%d]`
- `0x180039f84`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x18003a072`: `AppCompat\Programs`
- `0x18003a12d`: `Amcache.hve`
- `0x180039fb8`: `AmiRegGetStoreFullPath`
- `0x18003a0b3`: `AmiRegGetStoreFullPath`
- `0x180039fde`: `AmiOverridePath`
- `0x18003a028`: `AmiOverridePath`
- `0x180039f8f`: `AppCompatFlags`

## pseudocode

```c
__int64 __fastcall AmiRegGetStoreFullPath(unsigned __int16 *a1)
{
  signed int PersistedLocation; // eax
  unsigned int v3; // ebx
  const char *v4; // r9
  __int64 v5; // r8
  __int64 v6; // r8
  LPDWORD pdwType; // [rsp+20h] [rbp-E0h]
  DWORD pcbData[4]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+260h] [rbp+160h] BYREF
  WCHAR Buffer[264]; // [rsp+470h] [rbp+370h] BYREF
  unsigned __int16 v13[264]; // [rsp+680h] [rbp+580h] BYREF

  memset_0(SubKey, 0, 0x20Au);
  memset_0(v13, 0, 0x20Au);
  pcbData[0] = 0;
  Buffer[0] = 0;
  memset_0(a1, 0, 0x208u);
  PersistedLocation = AmiUtilityGetPersistedLocation(
                        (unsigned int)SubKey,
                        261,
                        (unsigned int)L"AppCompatFlags",
                        (unsigned int)L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
                        1);
  if ( PersistedLocation >= 0 )
  {
    pcbData[0] = 520;
    if ( RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"AmiOverridePath", 0x20000002u, 0, FileName, pcbData)
      || GetFileAttributesW(FileName) != -1 )
    {
      if ( FileName[0] )
        goto LABEL_20;
    }
    else
    {
      RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, SubKey, L"AmiOverridePath");
      FileName[0] = 0;
    }
    if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) - 1 > 0x103 )
    {
      PersistedLocation = GetLastError();
      v4 = "GetSystemWindowsDirectory [%d]";
      v5 = 353;
      v3 = PersistedLocation;
      goto LABEL_3;
    }
    if ( StringCchPrintfW(v13, 0x105u, L"%s\\%s", Buffer, L"AppCompat\\Programs") < 0 )
    {
      v6 = 367;
      goto LABEL_11;
    }
    PersistedLocation = AmiUtilityGetPersistedLocation(
                          (unsigned int)FileName,
                          260,
                          (unsigned int)L"Amcache",
                          (unsigned int)v13,
                          0);
    if ( PersistedLocation < 0 )
    {
      v3 = 111;
      v4 = "AmiUtilityGetPersistedLocation failed [%#x]";
      v5 = 378;
      goto LABEL_3;
    }
    if ( (unsigned int)_o_wcscat_s(FileName, 260, L"\\") )
    {
      v3 = 1287;
      AslLogCallPrintf(1, "AmiRegGetStoreFullPath", 385, "wcscpy_s failed");
      return v3;
    }
    if ( (unsigned int)_o_wcscat_s(FileName, 260, L"Amcache.hve") )
    {
      v3 = 1287;
      AslLogCallPrintf(1, "AmiRegGetStoreFullPath", 392, "wcscpy_s failed");
      return v3;
    }
LABEL_20:
    if ( StringCchCopyW(a1, 0x104u, FileName) >= 0 )
      return 0;
    v6 = 406;
LABEL_11:
    v3 = 111;
    AslLogCallPrintf(1, "AmiRegGetStoreFullPath", v6, "Buffer overflow");
    return v3;
  }
  v3 = 1287;
  v4 = "AmiUtilityGetPersistedLocation [%#x]";
  v5 = 311;
LABEL_3:
  LODWORD(pdwType) = PersistedLocation;
  AslLogCallPrintf(1, "AmiRegGetStoreFullPath", v5, v4, pdwType);
  return v3;
}

```

## disassembly

```asm
0x180039f04  mov     [rsp-8+arg_8], rbx
0x180039f09  mov     [rsp-8+arg_10], rsi
0x180039f0e  push    rbp
0x180039f0f  push    rdi
0x180039f10  push    r14
0x180039f12  lea     rbp, [rsp-7A0h]
0x180039f1a  sub     rsp, 8A0h
0x180039f21  mov     rax, cs:__security_cookie
0x180039f28  xor     rax, rsp
0x180039f2b  mov     [rbp+7B0h+var_20], rax
0x180039f32  mov     rbx, rcx
0x180039f35  mov     edi, 20Ah
0x180039f3a  mov     r8d, edi; Size
0x180039f3d  lea     rcx, [rbp+7B0h+SubKey]; void *
0x180039f44  xor     edx, edx; Val
0x180039f46  call    memset_0
0x180039f4b  mov     r8d, edi; Size
0x180039f4e  lea     rcx, [rbp+7B0h+var_230]; void *
0x180039f55  xor     edx, edx; Val
0x180039f57  call    memset_0
0x180039f5c  xor     edi, edi
0x180039f5e  mov     r14d, 208h
0x180039f64  mov     r8d, r14d; Size
0x180039f67  mov     [rsp+8B0h+var_870], edi
0x180039f6b  xor     edx, edx; Val
0x180039f6d  mov     [rbp+7B0h+Buffer], di
0x180039f74  mov     rcx, rbx; void *
0x180039f77  call    memset_0
0x180039f7c  lea     esi, [rdi+1]
0x180039f7f  mov     edx, 105h
0x180039f84  lea     r9, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x180039f8b  mov     dword ptr [rsp+8B0h+pdwType], esi
0x180039f8f  lea     r8, aAppcompatflags; "AppCompatFlags"
0x180039f96  lea     rcx, [rbp+7B0h+SubKey]
0x180039f9d  call    AmiUtilityGetPersistedLocation
0x180039fa2  test    eax, eax
0x180039fa4  jns     short loc_180039FCF
0x180039fa6  mov     ebx, 507h
0x180039fab  lea     r9, aAmiutilitygetp; "AmiUtilityGetPersistedLocation [%#x]"
0x180039fb2  mov     r8d, 137h
0x180039fb8  lea     rdx, aAmireggetstore; "AmiRegGetStoreFullPath"
0x180039fbf  mov     dword ptr [rsp+8B0h+pdwType], eax
0x180039fc3  mov     ecx, esi
0x180039fc5  call    AslLogCallPrintf
0x180039fca  jmp     loc_18003A198
0x180039fcf  lea     rax, [rsp+8B0h+var_870]
0x180039fd4  mov     [rsp+8B0h+var_870], r14d
0x180039fd9  mov     [rsp+8B0h+pcbData], rax; pcbData
0x180039fde  lea     r8, ValueName; "AmiOverridePath"
0x180039fe5  lea     rax, [rsp+8B0h+FileName]
0x180039fea  mov     r9d, 20000002h; dwFlags
0x180039ff0  mov     [rsp+8B0h+pvData], rax; pvData
0x180039ff5  lea     rdx, [rbp+7B0h+SubKey]; lpSubKey
0x180039ffc  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18003a003  mov     [rsp+8B0h+pdwType], rdi; pdwType
0x18003a008  call    cs:__imp_RegGetValueW
0x18003a00e  mov     r14d, 104h
0x18003a014  test    eax, eax
0x18003a016  jnz     short loc_18003A04A
0x18003a018  lea     rcx, [rsp+8B0h+FileName]; lpFileName
0x18003a01d  call    cs:__imp_GetFileAttributesW
0x18003a023  cmp     eax, 0FFFFFFFFh
0x18003a026  jnz     short loc_18003A04A
0x18003a028  lea     r8, ValueName; "AmiOverridePath"
0x18003a02f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003a036  lea     rdx, [rbp+7B0h+SubKey]; lpSubKey
0x18003a03d  call    cs:__imp_RegDeleteKeyValueW
0x18003a043  mov     [rsp+8B0h+FileName], di
0x18003a048  jmp     short loc_18003A055
0x18003a04a  cmp     [rsp+8B0h+FileName], di
0x18003a04f  jnz     loc_18003A177
0x18003a055  mov     edx, r14d; uSize
0x18003a058  lea     rcx, [rbp+7B0h+Buffer]; lpBuffer
0x18003a05f  call    cs:__imp_GetSystemWindowsDirectoryW
0x18003a065  dec     eax
0x18003a067  cmp     eax, 103h
0x18003a06c  ja      loc_18003A15D
0x18003a072  lea     rax, aAppcompatProgr; "AppCompat\\Programs"
0x18003a079  mov     edx, 105h; unsigned __int64
0x18003a07e  lea     r9, [rbp+7B0h+Buffer]
0x18003a085  mov     [rsp+8B0h+pdwType], rax
0x18003a08a  lea     r8, aSS_1; "%s\\%s"
0x18003a091  lea     rcx, [rbp+7B0h+var_230]; unsigned __int16 *
0x18003a098  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003a09d  test    eax, eax
0x18003a09f  jns     short loc_18003A0C6
0x18003a0a1  mov     r8d, 16Fh
0x18003a0a7  lea     r9, aBufferOverflow; "Buffer overflow"
0x18003a0ae  mov     ebx, 6Fh ; 'o'
0x18003a0b3  lea     rdx, aAmireggetstore; "AmiRegGetStoreFullPath"
0x18003a0ba  mov     ecx, esi
0x18003a0bc  call    AslLogCallPrintf
0x18003a0c1  jmp     loc_18003A198
0x18003a0c6  lea     r9, [rbp+7B0h+var_230]
0x18003a0cd  mov     dword ptr [rsp+8B0h+pdwType], edi
0x18003a0d1  lea     r8, aAmcache; "Amcache"
0x18003a0d8  mov     edx, r14d
0x18003a0db  lea     rcx, [rsp+8B0h+FileName]
0x18003a0e0  call    AmiUtilityGetPersistedLocation
0x18003a0e5  test    eax, eax
0x18003a0e7  jns     short loc_18003A100
0x18003a0e9  mov     ebx, 6Fh ; 'o'
0x18003a0ee  lea     r9, aAmiutilitygetp_0; "AmiUtilityGetPersistedLocation failed ["...
0x18003a0f5  mov     r8d, 17Ah
0x18003a0fb  jmp     loc_180039FB8
0x18003a100  lea     r8, Source; "\\"
0x18003a107  mov     rdx, r14
0x18003a10a  lea     rcx, [rsp+8B0h+FileName]
0x18003a10f  call    cs:__imp__o_wcscat_s
0x18003a115  test    eax, eax
0x18003a117  jz      short loc_18003A12D
0x18003a119  mov     ebx, 507h
0x18003a11e  lea     r9, aWcscpySFailed; "wcscpy_s failed"
0x18003a125  mov     r8d, 181h
0x18003a12b  jmp     short loc_18003A0B3
0x18003a12d  lea     r8, aAmcacheHve; "Amcache.hve"
0x18003a134  mov     rdx, r14
0x18003a137  lea     rcx, [rsp+8B0h+FileName]
0x18003a13c  call    cs:__imp__o_wcscat_s
0x18003a142  test    eax, eax
0x18003a144  jz      short loc_18003A177
0x18003a146  mov     ebx, 507h
0x18003a14b  lea     r9, aWcscpySFailed; "wcscpy_s failed"
0x18003a152  mov     r8d, 188h
0x18003a158  jmp     loc_18003A0B3
0x18003a15d  call    cs:__imp_GetLastError
0x18003a163  lea     r9, aGetsystemwindo; "GetSystemWindowsDirectory [%d]"
0x18003a16a  mov     r8d, 161h
0x18003a170  mov     ebx, eax
0x18003a172  jmp     loc_180039FB8
0x18003a177  lea     r8, [rsp+8B0h+FileName]; unsigned __int16 *
0x18003a17c  mov     rdx, r14; unsigned __int64
0x18003a17f  mov     rcx, rbx; unsigned __int16 *
0x18003a182  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003a187  test    eax, eax
0x18003a189  jns     short loc_18003A196
0x18003a18b  mov     r8d, 196h
0x18003a191  jmp     loc_18003A0A7
0x18003a196  mov     ebx, edi
0x18003a198  mov     eax, ebx
0x18003a19a  mov     rcx, [rbp+7B0h+var_20]
0x18003a1a1  xor     rcx, rsp; StackCookie
0x18003a1a4  call    __security_check_cookie
0x18003a1a9  lea     r11, [rsp+8B0h+var_10]
0x18003a1b1  mov     rbx, [r11+28h]
0x18003a1b5  mov     rsi, [r11+30h]
0x18003a1b9  mov     rsp, r11
0x18003a1bc  pop     r14
0x18003a1be  pop     rdi
0x18003a1bf  pop     rbp
0x18003a1c0  retn
```
