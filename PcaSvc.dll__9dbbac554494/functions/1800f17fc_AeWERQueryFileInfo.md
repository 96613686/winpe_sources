# AeWERQueryFileInfo

- ea: `0x1800f17fc`
- end: `0x1800f1ba0`
- name: `AeWERQueryFileInfo`
- size: `932`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180040340`

## callees

- `0x18000dc08`
- `0x180012920`
- `0x18007a9cf`
- `0x1800f1650`
- `0x1800f1704`
- `0x1800f17fc`
- `0x1800f1f10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f1b51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f1b61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f1b71`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f1b51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f1b61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800f1b71`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x1800f1975`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x1800f1975`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f1a85`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f1aeb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f1a85`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800f1aeb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f19ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f1a2b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f19ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800f1a2b`

## string_xrefs

- `0x1800f1895`: `Failed to hash File path [%#x]`
- `0x1800f18b7`: `AppCompat\Programs`
- `0x1800f18e4`: `StringCchPrintf for StoreDirectory [%#x]`
- `0x1800f1918`: `Amcache.hve`
- `0x1800f19fd`: `Failed to open file key [%d]`
- `0x1800f1a3c`: `Failed to open file key [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall AeWERQueryFileInfo(__int64 a1)
{
  unsigned int v2; // edx
  bool v3; // zf
  int v4; // edi
  int PersistedLocation; // eax
  signed int v6; // ebx
  const char *v7; // r9
  int v8; // r8d
  unsigned int v9; // edx
  LSTATUS v10; // eax
  int v11; // r8d
  const char *v12; // r9
  int v13; // ecx
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  __int64 v16; // rdi
  LSTATUS ValueW; // eax
  void *pvData; // rsi
  LSTATUS v19; // eax
  __int64 v20; // rax
  __int64 v21; // rcx
  DWORD Reserved[2]; // [rsp+20h] [rbp-E0h]
  DWORD Reserveda[2]; // [rsp+20h] [rbp-E0h]
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[48]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v30[264]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t Destination[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR File[264]; // [rsp+4E0h] [rbp+3E0h] BYREF

  memset_0(Destination, 0, 0x20Au);
  memset_0(v30, 0, 0x20Au);
  v3 = *(_DWORD *)(a1 + 4) == 528;
  pcbData = 0;
  phkResult = 0;
  hkey = 0;
  hKey = 0;
  if ( v3 && (v4 = 1, *(_DWORD *)a1 == 1) )
  {
    PersistedLocation = ComputeFileCacheKey(SubKey, v2, *(const unsigned __int16 **)(a1 + 8));
    v6 = PersistedLocation;
    if ( PersistedLocation < 0 )
    {
      v7 = "Failed to hash File path [%#x]";
      v8 = 125;
LABEL_5:
      Reserved[0] = PersistedLocation;
      AslLogCallPrintf(1, (unsigned int)"AeWERQueryFileInfo", v8, (_DWORD)v7, *(_QWORD *)Reserved);
      goto LABEL_42;
    }
    PersistedLocation = StringCchPrintfW(v30, 0x105u, L"%s\\%s", 2147352624, L"AppCompat\\Programs");
    v6 = PersistedLocation;
    if ( PersistedLocation < 0 )
    {
      v7 = "StringCchPrintf for StoreDirectory [%#x]";
      v8 = 136;
      goto LABEL_5;
    }
    PersistedLocation = AeGetPersistedLocation(Destination, v9, v30);
    v6 = PersistedLocation;
    if ( PersistedLocation < 0 )
    {
      v7 = "AeGetPersistedLocation failed [%#x]";
      v8 = 147;
      goto LABEL_5;
    }
    PersistedLocation = StringCchPrintfW(File, 0x104u, L"%s\\%s", Destination, L"Amcache.hve");
    v6 = PersistedLocation;
    if ( PersistedLocation < 0 )
    {
      v7 = "StringCchPrintf [%#x]";
      v8 = 157;
      goto LABEL_5;
    }
    v10 = RegLoadAppKeyW(File, &phkResult, 0x20019u, 0, 0);
    v6 = v10;
    if ( v10 )
    {
      if ( v10 == 5 || v10 == 2 )
      {
        v4 = 3;
        v11 = 171;
      }
      else
      {
        v11 = 175;
      }
      v12 = "RegLoadAppKey failed [%d]";
      goto LABEL_18;
    }
    v14 = RegOpenKeyExW(phkResult, L"Root", 0, 0x20019u, &hKey);
    v6 = v14;
    if ( v14 )
    {
      if ( v14 != 2 )
      {
        v12 = "Failed to open file key [%d]";
        v11 = 189;
LABEL_18:
        v13 = v4;
        goto LABEL_19;
      }
      goto LABEL_20;
    }
    v15 = RegOpenKeyExW(hKey, L"InventoryApplicationFile", 0, 0x20019u, &hkey);
    v6 = v15;
    if ( v15 )
    {
      if ( v15 != 2 )
      {
        v12 = "Failed to open file key [%d]";
        v11 = 199;
        goto LABEL_18;
      }
LABEL_20:
      v6 = (unsigned __int16)v6 | 0x80070000;
      goto LABEL_42;
    }
    v16 = a1 + 16;
    pcbData = 256;
    ValueW = RegGetValueW(hkey, SubKey, L"ProgramId", 2u, 0, (PVOID)(a1 + 16), &pcbData);
    v6 = ValueW;
    if ( ValueW )
    {
      if ( ValueW == 2 )
        goto LABEL_20;
      v12 = "Failed to get program id [%d]";
      v11 = 220;
LABEL_30:
      v13 = 3;
LABEL_19:
      Reserveda[0] = v6;
      AslLogCallPrintf(v13, (unsigned int)"AeWERQueryFileInfo", v11, (_DWORD)v12, *(_QWORD *)Reserveda);
      if ( v6 <= 0 )
        goto LABEL_42;
      goto LABEL_20;
    }
    pvData = (void *)(a1 + 272);
    pcbData = 256;
    v19 = RegGetValueW(hkey, SubKey, L"FileId", 2u, 0, pvData, &pcbData);
    v6 = v19;
    if ( v19 )
    {
      if ( v19 == 2 )
        goto LABEL_20;
      v12 = "Failed to get file id [%d]";
      v11 = 242;
      goto LABEL_30;
    }
    v20 = -1;
    v21 = -1;
    do
      ++v21;
    while ( *((_WORD *)pvData + v21) );
    if ( v21 != 44 )
      goto LABEL_40;
    do
      ++v20;
    while ( *(_WORD *)(v16 + 2 * v20) );
    if ( v20 == 44 )
      v6 = 0;
    else
LABEL_40:
      v6 = -2147024894;
  }
  else
  {
    v6 = -2147024809;
  }
LABEL_42:
  if ( hkey )
    RegCloseKey(hkey);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800f17fc  mov     [rsp-8+arg_8], rbx
0x1800f1801  mov     [rsp-8+arg_10], rsi
0x1800f1806  push    rbp
0x1800f1807  push    rdi
0x1800f1808  push    r14
0x1800f180a  lea     rbp, [rsp-600h]
0x1800f1812  sub     rsp, 700h
0x1800f1819  mov     rax, cs:__security_cookie
0x1800f1820  xor     rax, rsp
0x1800f1823  mov     [rbp+610h+var_20], rax
0x1800f182a  mov     rsi, rcx
0x1800f182d  mov     ebx, 20Ah
0x1800f1832  mov     r8d, ebx; Size
0x1800f1835  lea     rcx, [rbp+610h+Destination]; void *
0x1800f183c  xor     edx, edx; Val
0x1800f183e  call    memset_0
0x1800f1843  mov     r8d, ebx; Size
0x1800f1846  lea     rcx, [rbp+610h+var_650]; void *
0x1800f184a  xor     edx, edx; Val
0x1800f184c  call    memset_0
0x1800f1851  xor     r14d, r14d
0x1800f1854  cmp     dword ptr [rsi+4], 210h
0x1800f185b  mov     [rsp+710h+var_6D0], r14d
0x1800f1860  mov     [rsp+710h+phkResult], r14
0x1800f1865  mov     [rsp+710h+hkey], r14
0x1800f186a  mov     [rsp+710h+hKey], r14
0x1800f186f  jnz     loc_1800F1B42
0x1800f1875  lea     edi, [r14+1]
0x1800f1879  cmp     [rsi], edi
0x1800f187b  jnz     loc_1800F1B42
0x1800f1881  mov     r8, [rsi+8]; unsigned __int16 *
0x1800f1885  lea     rcx, [rsp+710h+SubKey]; unsigned __int16 *
0x1800f188a  call    ?ComputeFileCacheKey@@YAJPEAGKPEBG@Z; ComputeFileCacheKey(ushort *,ulong,ushort const *)
0x1800f188f  mov     ebx, eax
0x1800f1891  test    eax, eax
0x1800f1893  jns     short loc_1800F18B7
0x1800f1895  lea     r9, aFailedToHashFi; "Failed to hash File path [%#x]"
0x1800f189c  lea     r8d, [r14+7Dh]
0x1800f18a0  lea     rdx, aAewerqueryfile; "AeWERQueryFileInfo"
0x1800f18a7  mov     [rsp+710h+Reserved], eax
0x1800f18ab  mov     ecx, edi
0x1800f18ad  call    AslLogCallPrintf
0x1800f18b2  jmp     loc_1800F1B47
0x1800f18b7  lea     rax, aAppcompatProgr; "AppCompat\\Programs"
0x1800f18be  mov     r9d, 7FFE0030h
0x1800f18c4  lea     r8, aSS_0; "%s\\%s"
0x1800f18cb  mov     qword ptr [rsp+710h+Reserved], rax
0x1800f18d0  mov     edx, 105h; unsigned __int64
0x1800f18d5  lea     rcx, [rbp+610h+var_650]; unsigned __int16 *
0x1800f18d9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800f18de  mov     ebx, eax
0x1800f18e0  test    eax, eax
0x1800f18e2  jns     short loc_1800F18F3
0x1800f18e4  lea     r9, aStringcchprint_2; "StringCchPrintf for StoreDirectory [%#x"...
0x1800f18eb  mov     r8d, 88h
0x1800f18f1  jmp     short loc_1800F18A0
0x1800f18f3  lea     r8, [rbp+610h+var_650]; unsigned __int16 *
0x1800f18f7  lea     rcx, [rbp+610h+Destination]; Destination
0x1800f18fe  call    ?AeGetPersistedLocation@@YAJPEAGKQEBG@Z; AeGetPersistedLocation(ushort *,ulong,ushort const * const)
0x1800f1903  mov     ebx, eax
0x1800f1905  test    eax, eax
0x1800f1907  jns     short loc_1800F1918
0x1800f1909  lea     r9, aAegetpersisted; "AeGetPersistedLocation failed [%#x]"
0x1800f1910  mov     r8d, 93h
0x1800f1916  jmp     short loc_1800F18A0
0x1800f1918  lea     rax, aAmcacheHve; "Amcache.hve"
0x1800f191f  mov     edx, 104h; unsigned __int64
0x1800f1924  lea     r9, [rbp+610h+Destination]
0x1800f192b  mov     qword ptr [rsp+710h+Reserved], rax
0x1800f1930  lea     r8, aSS_0; "%s\\%s"
0x1800f1937  lea     rcx, [rbp+610h+File]; unsigned __int16 *
0x1800f193e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800f1943  mov     ebx, eax
0x1800f1945  test    eax, eax
0x1800f1947  jns     short loc_1800F195B
0x1800f1949  lea     r9, aStringcchprint_5; "StringCchPrintf [%#x]"
0x1800f1950  mov     r8d, 9Dh
0x1800f1956  jmp     loc_1800F18A0
0x1800f195b  xor     r9d, r9d; dwOptions
0x1800f195e  mov     [rsp+710h+Reserved], r14d; Reserved
0x1800f1963  mov     r8d, 20019h; samDesired
0x1800f1969  lea     rdx, [rsp+710h+phkResult]; phkResult
0x1800f196e  lea     rcx, [rbp+610h+File]; lpFile
0x1800f1975  call    cs:__imp_RegLoadAppKeyW
0x1800f197b  mov     ebx, eax
0x1800f197d  test    eax, eax
0x1800f197f  jz      short loc_1800F19CD
0x1800f1981  cmp     eax, 5
0x1800f1984  jz      short loc_1800F1993
0x1800f1986  cmp     eax, 2
0x1800f1989  jz      short loc_1800F1993
0x1800f198b  mov     r8d, 0AFh
0x1800f1991  jmp     short loc_1800F199E
0x1800f1993  mov     edi, 3
0x1800f1998  mov     r8d, 0ABh
0x1800f199e  lea     r9, aRegloadappkeyF; "RegLoadAppKey failed [%d]"
0x1800f19a5  mov     ecx, edi
0x1800f19a7  lea     rdx, aAewerqueryfile; "AeWERQueryFileInfo"
0x1800f19ae  mov     [rsp+710h+Reserved], ebx
0x1800f19b2  call    AslLogCallPrintf
0x1800f19b7  test    ebx, ebx
0x1800f19b9  jle     loc_1800F1B47
0x1800f19bf  movzx   ebx, bx
0x1800f19c2  or      ebx, 80070000h
0x1800f19c8  jmp     loc_1800F1B47
0x1800f19cd  mov     rcx, [rsp+710h+phkResult]; hKey
0x1800f19d2  lea     rax, [rsp+710h+hKey]
0x1800f19d7  mov     r9d, 20019h; samDesired
0x1800f19dd  mov     qword ptr [rsp+710h+Reserved], rax; phkResult
0x1800f19e2  xor     r8d, r8d; ulOptions
0x1800f19e5  lea     rdx, aRoot; "Root"
0x1800f19ec  call    cs:__imp_RegOpenKeyExW
0x1800f19f2  mov     ebx, eax
0x1800f19f4  test    eax, eax
0x1800f19f6  jz      short loc_1800F1A0C
0x1800f19f8  cmp     eax, 2
0x1800f19fb  jz      short loc_1800F19BF
0x1800f19fd  lea     r9, aFailedToOpenFi_1; "Failed to open file key [%d]"
0x1800f1a04  mov     r8d, 0BDh
0x1800f1a0a  jmp     short loc_1800F19A5
0x1800f1a0c  mov     rcx, [rsp+710h+hKey]; hKey
0x1800f1a11  lea     rax, [rsp+710h+hkey]
0x1800f1a16  mov     r9d, 20019h; samDesired
0x1800f1a1c  mov     qword ptr [rsp+710h+Reserved], rax; phkResult
0x1800f1a21  xor     r8d, r8d; ulOptions
0x1800f1a24  lea     rdx, aInventoryappli_0; "InventoryApplicationFile"
0x1800f1a2b  call    cs:__imp_RegOpenKeyExW
0x1800f1a31  mov     ebx, eax
0x1800f1a33  test    eax, eax
0x1800f1a35  jz      short loc_1800F1A4E
0x1800f1a37  cmp     eax, 2
0x1800f1a3a  jz      short loc_1800F19BF
0x1800f1a3c  lea     r9, aFailedToOpenFi_1; "Failed to open file key [%d]"
0x1800f1a43  mov     r8d, 0C7h
0x1800f1a49  jmp     loc_1800F19A5
0x1800f1a4e  mov     rcx, [rsp+710h+hkey]; hkey
0x1800f1a53  lea     rax, [rsp+710h+var_6D0]
0x1800f1a58  mov     [rsp+710h+pcbData], rax; pcbData
0x1800f1a5d  lea     rdi, [rsi+10h]
0x1800f1a61  mov     [rsp+710h+pvData], rdi; pvData
0x1800f1a66  lea     r8, aProgramid; "ProgramId"
0x1800f1a6d  mov     r9d, 2; dwFlags
0x1800f1a73  mov     qword ptr [rsp+710h+Reserved], r14; pdwType
0x1800f1a78  lea     rdx, [rsp+710h+SubKey]; lpSubKey
0x1800f1a7d  mov     [rsp+710h+var_6D0], 100h
0x1800f1a85  call    cs:__imp_RegGetValueW
0x1800f1a8b  mov     ebx, eax
0x1800f1a8d  test    eax, eax
0x1800f1a8f  jz      short loc_1800F1AB1
0x1800f1a91  cmp     eax, 2
0x1800f1a94  jz      loc_1800F19BF
0x1800f1a9a  lea     r9, aFailedToGetPro_7; "Failed to get program id [%d]"
0x1800f1aa1  mov     r8d, 0DCh
0x1800f1aa7  mov     ecx, 3
0x1800f1aac  jmp     loc_1800F19A7
0x1800f1ab1  mov     rcx, [rsp+710h+hkey]; hkey
0x1800f1ab6  lea     rax, [rsp+710h+var_6D0]
0x1800f1abb  mov     [rsp+710h+pcbData], rax; pcbData
0x1800f1ac0  lea     r8, aFileid; "FileId"
0x1800f1ac7  add     rsi, 110h
0x1800f1ace  mov     [rsp+710h+var_6D0], 100h
0x1800f1ad6  mov     [rsp+710h+pvData], rsi; pvData
0x1800f1adb  lea     rdx, [rsp+710h+SubKey]; lpSubKey
0x1800f1ae0  mov     r9d, 2; dwFlags
0x1800f1ae6  mov     qword ptr [rsp+710h+Reserved], r14; pdwType
0x1800f1aeb  call    cs:__imp_RegGetValueW
0x1800f1af1  mov     ebx, eax
0x1800f1af3  test    eax, eax
0x1800f1af5  jz      short loc_1800F1B0F
0x1800f1af7  cmp     eax, 2
0x1800f1afa  jz      loc_1800F19BF
0x1800f1b00  lea     r9, aFailedToGetFil_2; "Failed to get file id [%d]"
0x1800f1b07  mov     r8d, 0F2h
0x1800f1b0d  jmp     short loc_1800F1AA7
0x1800f1b0f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800f1b13  mov     rcx, rax
0x1800f1b16  inc     rcx
0x1800f1b19  cmp     [rsi+rcx*2], r14w
0x1800f1b1e  jnz     short loc_1800F1B16
0x1800f1b20  cmp     rcx, 2Ch ; ','
0x1800f1b24  jnz     short loc_1800F1B3B
0x1800f1b26  inc     rax
0x1800f1b29  cmp     [rdi+rax*2], r14w
0x1800f1b2e  jnz     short loc_1800F1B26
0x1800f1b30  cmp     rax, 2Ch ; ','
0x1800f1b34  jnz     short loc_1800F1B3B
0x1800f1b36  mov     ebx, r14d
0x1800f1b39  jmp     short loc_1800F1B47
0x1800f1b3b  mov     ebx, 80070002h
0x1800f1b40  jmp     short loc_1800F1B47
0x1800f1b42  mov     ebx, 80070057h
0x1800f1b47  mov     rcx, [rsp+710h+hkey]; hKey
0x1800f1b4c  test    rcx, rcx
0x1800f1b4f  jz      short loc_1800F1B57
0x1800f1b51  call    cs:__imp_RegCloseKey
0x1800f1b57  mov     rcx, [rsp+710h+hKey]; hKey
0x1800f1b5c  test    rcx, rcx
0x1800f1b5f  jz      short loc_1800F1B67
0x1800f1b61  call    cs:__imp_RegCloseKey
0x1800f1b67  mov     rcx, [rsp+710h+phkResult]; hKey
0x1800f1b6c  test    rcx, rcx
0x1800f1b6f  jz      short loc_1800F1B77
0x1800f1b71  call    cs:__imp_RegCloseKey
0x1800f1b77  mov     eax, ebx
0x1800f1b79  mov     rcx, [rbp+610h+var_20]
0x1800f1b80  xor     rcx, rsp; StackCookie
0x1800f1b83  call    __security_check_cookie
0x1800f1b88  lea     r11, [rsp+710h+var_10]
0x1800f1b90  mov     rbx, [r11+28h]
0x1800f1b94  mov     rsi, [r11+30h]
0x1800f1b98  mov     rsp, r11
0x1800f1b9b  pop     r14
0x1800f1b9d  pop     rdi
0x1800f1b9e  pop     rbp
0x1800f1b9f  retn
```
