# AeWERQueryFileInfo

- ea: `0x180036ad0`
- end: `0x180036e74`
- name: `AeWERQueryFileInfo`
- size: `932`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c860`
- `0x1800e34b0`

## callees

- `0x180005890`
- `0x180006938`
- `0x18000cb74`
- `0x1800295dc`
- `0x180036924`
- `0x1800369d8`
- `0x180036ad0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036cc0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036cff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036cc0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180036cff`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x180036c49`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x180036c49`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036d59`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036dbf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036d59`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180036dbf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036e25`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036e35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036e45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036e25`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036e35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180036e45`

## string_xrefs

- `0x180036b69`: `Failed to hash File path [%#x]`
- `0x180036b8b`: `AppCompat\Programs`
- `0x180036bb8`: `StringCchPrintf for StoreDirectory [%#x]`
- `0x180036bec`: `Amcache.hve`
- `0x180036cd1`: `Failed to open file key [%d]`
- `0x180036d10`: `Failed to open file key [%d]`

## pseudocode

```c
__int64 __fastcall AeWERQueryFileInfo(__int64 a1)
{
  unsigned int v2; // edx
  bool v3; // zf
  unsigned int v4; // edi
  int PersistedLocation; // eax
  signed int v6; // ebx
  const char *v7; // r9
  __int64 v8; // r8
  unsigned int v9; // edx
  LSTATUS v10; // eax
  __int64 v11; // r8
  const char *v12; // r9
  __int64 v13; // rcx
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
      AslLogCallPrintf(1, "AeWERQueryFileInfo", v8, v7, *(_QWORD *)Reserved);
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
      AslLogCallPrintf(v13, "AeWERQueryFileInfo", v11, v12, *(_QWORD *)Reserveda);
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
0x180036ad0  mov     [rsp-8+arg_8], rbx
0x180036ad5  mov     [rsp-8+arg_10], rsi
0x180036ada  push    rbp
0x180036adb  push    rdi
0x180036adc  push    r14
0x180036ade  lea     rbp, [rsp-600h]
0x180036ae6  sub     rsp, 700h
0x180036aed  mov     rax, cs:__security_cookie
0x180036af4  xor     rax, rsp
0x180036af7  mov     [rbp+610h+var_20], rax
0x180036afe  mov     rsi, rcx
0x180036b01  mov     ebx, 20Ah
0x180036b06  mov     r8d, ebx; Size
0x180036b09  lea     rcx, [rbp+610h+Destination]; void *
0x180036b10  xor     edx, edx; Val
0x180036b12  call    memset_0
0x180036b17  mov     r8d, ebx; Size
0x180036b1a  lea     rcx, [rbp+610h+var_650]; void *
0x180036b1e  xor     edx, edx; Val
0x180036b20  call    memset_0
0x180036b25  xor     r14d, r14d
0x180036b28  cmp     dword ptr [rsi+4], 210h
0x180036b2f  mov     [rsp+710h+var_6D0], r14d
0x180036b34  mov     [rsp+710h+phkResult], r14
0x180036b39  mov     [rsp+710h+hkey], r14
0x180036b3e  mov     [rsp+710h+hKey], r14
0x180036b43  jnz     loc_180036E16
0x180036b49  lea     edi, [r14+1]
0x180036b4d  cmp     [rsi], edi
0x180036b4f  jnz     loc_180036E16
0x180036b55  mov     r8, [rsi+8]; unsigned __int16 *
0x180036b59  lea     rcx, [rsp+710h+SubKey]; unsigned __int16 *
0x180036b5e  call    ?ComputeFileCacheKey@@YAJPEAGKPEBG@Z; ComputeFileCacheKey(ushort *,ulong,ushort const *)
0x180036b63  mov     ebx, eax
0x180036b65  test    eax, eax
0x180036b67  jns     short loc_180036B8B
0x180036b69  lea     r9, aFailedToHashFi; "Failed to hash File path [%#x]"
0x180036b70  lea     r8d, [r14+7Dh]
0x180036b74  lea     rdx, aAewerqueryfile; "AeWERQueryFileInfo"
0x180036b7b  mov     [rsp+710h+Reserved], eax
0x180036b7f  mov     ecx, edi
0x180036b81  call    AslLogCallPrintf
0x180036b86  jmp     loc_180036E1B
0x180036b8b  lea     rax, aAppcompatProgr; "AppCompat\\Programs"
0x180036b92  mov     r9d, 7FFE0030h
0x180036b98  lea     r8, aSS_1; "%s\\%s"
0x180036b9f  mov     qword ptr [rsp+710h+Reserved], rax
0x180036ba4  mov     edx, 105h; unsigned __int64
0x180036ba9  lea     rcx, [rbp+610h+var_650]; unsigned __int16 *
0x180036bad  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180036bb2  mov     ebx, eax
0x180036bb4  test    eax, eax
0x180036bb6  jns     short loc_180036BC7
0x180036bb8  lea     r9, aStringcchprint_1; "StringCchPrintf for StoreDirectory [%#x"...
0x180036bbf  mov     r8d, 88h
0x180036bc5  jmp     short loc_180036B74
0x180036bc7  lea     r8, [rbp+610h+var_650]; unsigned __int16 *
0x180036bcb  lea     rcx, [rbp+610h+Destination]; Destination
0x180036bd2  call    ?AeGetPersistedLocation@@YAJPEAGKQEBG@Z; AeGetPersistedLocation(ushort *,ulong,ushort const * const)
0x180036bd7  mov     ebx, eax
0x180036bd9  test    eax, eax
0x180036bdb  jns     short loc_180036BEC
0x180036bdd  lea     r9, aAegetpersisted; "AeGetPersistedLocation failed [%#x]"
0x180036be4  mov     r8d, 93h
0x180036bea  jmp     short loc_180036B74
0x180036bec  lea     rax, aAmcacheHve; "Amcache.hve"
0x180036bf3  mov     edx, 104h; unsigned __int64
0x180036bf8  lea     r9, [rbp+610h+Destination]
0x180036bff  mov     qword ptr [rsp+710h+Reserved], rax
0x180036c04  lea     r8, aSS_1; "%s\\%s"
0x180036c0b  lea     rcx, [rbp+610h+File]; unsigned __int16 *
0x180036c12  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180036c17  mov     ebx, eax
0x180036c19  test    eax, eax
0x180036c1b  jns     short loc_180036C2F
0x180036c1d  lea     r9, aStringcchprint_3; "StringCchPrintf [%#x]"
0x180036c24  mov     r8d, 9Dh
0x180036c2a  jmp     loc_180036B74
0x180036c2f  xor     r9d, r9d; dwOptions
0x180036c32  mov     [rsp+710h+Reserved], r14d; Reserved
0x180036c37  mov     r8d, 20019h; samDesired
0x180036c3d  lea     rdx, [rsp+710h+phkResult]; phkResult
0x180036c42  lea     rcx, [rbp+610h+File]; lpFile
0x180036c49  call    cs:__imp_RegLoadAppKeyW
0x180036c4f  mov     ebx, eax
0x180036c51  test    eax, eax
0x180036c53  jz      short loc_180036CA1
0x180036c55  cmp     eax, 5
0x180036c58  jz      short loc_180036C67
0x180036c5a  cmp     eax, 2
0x180036c5d  jz      short loc_180036C67
0x180036c5f  mov     r8d, 0AFh
0x180036c65  jmp     short loc_180036C72
0x180036c67  mov     edi, 3
0x180036c6c  mov     r8d, 0ABh
0x180036c72  lea     r9, aRegloadappkeyF; "RegLoadAppKey failed [%d]"
0x180036c79  mov     ecx, edi
0x180036c7b  lea     rdx, aAewerqueryfile; "AeWERQueryFileInfo"
0x180036c82  mov     [rsp+710h+Reserved], ebx
0x180036c86  call    AslLogCallPrintf
0x180036c8b  test    ebx, ebx
0x180036c8d  jle     loc_180036E1B
0x180036c93  movzx   ebx, bx
0x180036c96  or      ebx, 80070000h
0x180036c9c  jmp     loc_180036E1B
0x180036ca1  mov     rcx, [rsp+710h+phkResult]; hKey
0x180036ca6  lea     rax, [rsp+710h+hKey]
0x180036cab  mov     r9d, 20019h; samDesired
0x180036cb1  mov     qword ptr [rsp+710h+Reserved], rax; phkResult
0x180036cb6  xor     r8d, r8d; ulOptions
0x180036cb9  lea     rdx, aRoot; "Root"
0x180036cc0  call    cs:__imp_RegOpenKeyExW
0x180036cc6  mov     ebx, eax
0x180036cc8  test    eax, eax
0x180036cca  jz      short loc_180036CE0
0x180036ccc  cmp     eax, 2
0x180036ccf  jz      short loc_180036C93
0x180036cd1  lea     r9, aFailedToOpenFi; "Failed to open file key [%d]"
0x180036cd8  mov     r8d, 0BDh
0x180036cde  jmp     short loc_180036C79
0x180036ce0  mov     rcx, [rsp+710h+hKey]; hKey
0x180036ce5  lea     rax, [rsp+710h+hkey]
0x180036cea  mov     r9d, 20019h; samDesired
0x180036cf0  mov     qword ptr [rsp+710h+Reserved], rax; phkResult
0x180036cf5  xor     r8d, r8d; ulOptions
0x180036cf8  lea     rdx, aInventoryappli_0; "InventoryApplicationFile"
0x180036cff  call    cs:__imp_RegOpenKeyExW
0x180036d05  mov     ebx, eax
0x180036d07  test    eax, eax
0x180036d09  jz      short loc_180036D22
0x180036d0b  cmp     eax, 2
0x180036d0e  jz      short loc_180036C93
0x180036d10  lea     r9, aFailedToOpenFi; "Failed to open file key [%d]"
0x180036d17  mov     r8d, 0C7h
0x180036d1d  jmp     loc_180036C79
0x180036d22  mov     rcx, [rsp+710h+hkey]; hkey
0x180036d27  lea     rax, [rsp+710h+var_6D0]
0x180036d2c  mov     [rsp+710h+pcbData], rax; pcbData
0x180036d31  lea     rdi, [rsi+10h]
0x180036d35  mov     [rsp+710h+pvData], rdi; pvData
0x180036d3a  lea     r8, String1; "ProgramId"
0x180036d41  mov     r9d, 2; dwFlags
0x180036d47  mov     qword ptr [rsp+710h+Reserved], r14; pdwType
0x180036d4c  lea     rdx, [rsp+710h+SubKey]; lpSubKey
0x180036d51  mov     [rsp+710h+var_6D0], 100h
0x180036d59  call    cs:__imp_RegGetValueW
0x180036d5f  mov     ebx, eax
0x180036d61  test    eax, eax
0x180036d63  jz      short loc_180036D85
0x180036d65  cmp     eax, 2
0x180036d68  jz      loc_180036C93
0x180036d6e  lea     r9, aFailedToGetPro_0; "Failed to get program id [%d]"
0x180036d75  mov     r8d, 0DCh
0x180036d7b  mov     ecx, 3
0x180036d80  jmp     loc_180036C7B
0x180036d85  mov     rcx, [rsp+710h+hkey]; hkey
0x180036d8a  lea     rax, [rsp+710h+var_6D0]
0x180036d8f  mov     [rsp+710h+pcbData], rax; pcbData
0x180036d94  lea     r8, aFileid; "FileId"
0x180036d9b  add     rsi, 110h
0x180036da2  mov     [rsp+710h+var_6D0], 100h
0x180036daa  mov     [rsp+710h+pvData], rsi; pvData
0x180036daf  lea     rdx, [rsp+710h+SubKey]; lpSubKey
0x180036db4  mov     r9d, 2; dwFlags
0x180036dba  mov     qword ptr [rsp+710h+Reserved], r14; pdwType
0x180036dbf  call    cs:__imp_RegGetValueW
0x180036dc5  mov     ebx, eax
0x180036dc7  test    eax, eax
0x180036dc9  jz      short loc_180036DE3
0x180036dcb  cmp     eax, 2
0x180036dce  jz      loc_180036C93
0x180036dd4  lea     r9, aFailedToGetFil_0; "Failed to get file id [%d]"
0x180036ddb  mov     r8d, 0F2h
0x180036de1  jmp     short loc_180036D7B
0x180036de3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180036de7  mov     rcx, rax
0x180036dea  inc     rcx
0x180036ded  cmp     [rsi+rcx*2], r14w
0x180036df2  jnz     short loc_180036DEA
0x180036df4  cmp     rcx, 2Ch ; ','
0x180036df8  jnz     short loc_180036E0F
0x180036dfa  inc     rax
0x180036dfd  cmp     [rdi+rax*2], r14w
0x180036e02  jnz     short loc_180036DFA
0x180036e04  cmp     rax, 2Ch ; ','
0x180036e08  jnz     short loc_180036E0F
0x180036e0a  mov     ebx, r14d
0x180036e0d  jmp     short loc_180036E1B
0x180036e0f  mov     ebx, 80070002h
0x180036e14  jmp     short loc_180036E1B
0x180036e16  mov     ebx, 80070057h
0x180036e1b  mov     rcx, [rsp+710h+hkey]; hKey
0x180036e20  test    rcx, rcx
0x180036e23  jz      short loc_180036E2B
0x180036e25  call    cs:__imp_RegCloseKey
0x180036e2b  mov     rcx, [rsp+710h+hKey]; hKey
0x180036e30  test    rcx, rcx
0x180036e33  jz      short loc_180036E3B
0x180036e35  call    cs:__imp_RegCloseKey
0x180036e3b  mov     rcx, [rsp+710h+phkResult]; hKey
0x180036e40  test    rcx, rcx
0x180036e43  jz      short loc_180036E4B
0x180036e45  call    cs:__imp_RegCloseKey
0x180036e4b  mov     eax, ebx
0x180036e4d  mov     rcx, [rbp+610h+var_20]
0x180036e54  xor     rcx, rsp; StackCookie
0x180036e57  call    __security_check_cookie
0x180036e5c  lea     r11, [rsp+710h+var_10]
0x180036e64  mov     rbx, [r11+28h]
0x180036e68  mov     rsi, [r11+30h]
0x180036e6c  mov     rsp, r11
0x180036e6f  pop     r14
0x180036e71  pop     rdi
0x180036e72  pop     rbp
0x180036e73  retn
```
