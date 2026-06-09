# AeWERQueryFileInfo

- ea: `0x1801af0d4`
- end: `0x1801af478`
- name: `AeWERQueryFileInfo`
- size: `932`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18011c4b0`

## callees

- `0x180008570`
- `0x1800092dc`
- `0x180011d94`
- `0x18001a2f4`
- `0x1800c6cf8`
- `0x1801af020`
- `0x1801af0d4`

## import_xrefs

- `ADVAPI32!RegLoadAppKeyW` at `0x1801af24d`
- `ADVAPI32!RegLoadAppKeyW` at `0x1801af24d`
- `ADVAPI32!RegCloseKey` at `0x1801af429`
- `ADVAPI32!RegCloseKey` at `0x1801af439`
- `ADVAPI32!RegCloseKey` at `0x1801af449`
- `ADVAPI32!RegCloseKey` at `0x1801af429`
- `ADVAPI32!RegCloseKey` at `0x1801af439`
- `ADVAPI32!RegCloseKey` at `0x1801af449`
- `ADVAPI32!RegOpenKeyExW` at `0x1801af2c4`
- `ADVAPI32!RegOpenKeyExW` at `0x1801af303`
- `ADVAPI32!RegOpenKeyExW` at `0x1801af2c4`
- `ADVAPI32!RegOpenKeyExW` at `0x1801af303`
- `ADVAPI32!RegGetValueW` at `0x1801af35d`
- `ADVAPI32!RegGetValueW` at `0x1801af3c3`
- `ADVAPI32!RegGetValueW` at `0x1801af35d`
- `ADVAPI32!RegGetValueW` at `0x1801af3c3`

## string_xrefs

- `0x1801af16d`: `Failed to hash File path [%#x]`
- `0x1801af18f`: `AppCompat\Programs`
- `0x1801af1bc`: `StringCchPrintf for StoreDirectory [%#x]`
- `0x1801af2d5`: `Failed to open file key [%d]`
- `0x1801af314`: `Failed to open file key [%d]`
- `0x1801af1f0`: `Amcache.hve`

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
0x1801af0d4  mov     [rsp-8+arg_8], rbx
0x1801af0d9  mov     [rsp-8+arg_10], rsi
0x1801af0de  push    rbp
0x1801af0df  push    rdi
0x1801af0e0  push    r14
0x1801af0e2  lea     rbp, [rsp-600h]
0x1801af0ea  sub     rsp, 700h
0x1801af0f1  mov     rax, cs:__security_cookie
0x1801af0f8  xor     rax, rsp
0x1801af0fb  mov     [rbp+610h+var_20], rax
0x1801af102  mov     rsi, rcx
0x1801af105  mov     ebx, 20Ah
0x1801af10a  mov     r8d, ebx; Size
0x1801af10d  lea     rcx, [rbp+610h+Destination]; void *
0x1801af114  xor     edx, edx; Val
0x1801af116  call    memset_0
0x1801af11b  mov     r8d, ebx; Size
0x1801af11e  lea     rcx, [rbp+610h+var_650]; void *
0x1801af122  xor     edx, edx; Val
0x1801af124  call    memset_0
0x1801af129  xor     r14d, r14d
0x1801af12c  cmp     dword ptr [rsi+4], 210h
0x1801af133  mov     [rsp+710h+var_6D0], r14d
0x1801af138  mov     [rsp+710h+phkResult], r14
0x1801af13d  mov     [rsp+710h+hkey], r14
0x1801af142  mov     [rsp+710h+hKey], r14
0x1801af147  jnz     loc_1801AF41A
0x1801af14d  lea     edi, [r14+1]
0x1801af151  cmp     [rsi], edi
0x1801af153  jnz     loc_1801AF41A
0x1801af159  mov     r8, [rsi+8]; unsigned __int16 *
0x1801af15d  lea     rcx, [rsp+710h+SubKey]; unsigned __int16 *
0x1801af162  call    ?ComputeFileCacheKey@@YAJPEAGKPEBG@Z; ComputeFileCacheKey(ushort *,ulong,ushort const *)
0x1801af167  mov     ebx, eax
0x1801af169  test    eax, eax
0x1801af16b  jns     short loc_1801AF18F
0x1801af16d  lea     r9, aFailedToHashFi; "Failed to hash File path [%#x]"
0x1801af174  lea     r8d, [r14+7Dh]
0x1801af178  lea     rdx, aAewerqueryfile; "AeWERQueryFileInfo"
0x1801af17f  mov     [rsp+710h+Reserved], eax
0x1801af183  mov     ecx, edi
0x1801af185  call    AslLogCallPrintf
0x1801af18a  jmp     loc_1801AF41F
0x1801af18f  lea     rax, aAppcompatProgr; "AppCompat\\Programs"
0x1801af196  mov     r9d, 7FFE0030h
0x1801af19c  lea     r8, aSS_1; "%s\\%s"
0x1801af1a3  mov     qword ptr [rsp+710h+Reserved], rax
0x1801af1a8  mov     edx, 105h; unsigned __int64
0x1801af1ad  lea     rcx, [rbp+610h+var_650]; unsigned __int16 *
0x1801af1b1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801af1b6  mov     ebx, eax
0x1801af1b8  test    eax, eax
0x1801af1ba  jns     short loc_1801AF1CB
0x1801af1bc  lea     r9, aStringcchprint_0; "StringCchPrintf for StoreDirectory [%#x"...
0x1801af1c3  mov     r8d, 88h
0x1801af1c9  jmp     short loc_1801AF178
0x1801af1cb  lea     r8, [rbp+610h+var_650]; unsigned __int16 *
0x1801af1cf  lea     rcx, [rbp+610h+Destination]; Destination
0x1801af1d6  call    ?AeGetPersistedLocation@@YAJPEAGKQEBG@Z; AeGetPersistedLocation(ushort *,ulong,ushort const * const)
0x1801af1db  mov     ebx, eax
0x1801af1dd  test    eax, eax
0x1801af1df  jns     short loc_1801AF1F0
0x1801af1e1  lea     r9, aAegetpersisted; "AeGetPersistedLocation failed [%#x]"
0x1801af1e8  mov     r8d, 93h
0x1801af1ee  jmp     short loc_1801AF178
0x1801af1f0  lea     rax, aAmcacheHve; "Amcache.hve"
0x1801af1f7  mov     edx, 104h; unsigned __int64
0x1801af1fc  lea     r9, [rbp+610h+Destination]
0x1801af203  mov     qword ptr [rsp+710h+Reserved], rax
0x1801af208  lea     r8, aSS_1; "%s\\%s"
0x1801af20f  lea     rcx, [rbp+610h+File]; unsigned __int16 *
0x1801af216  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801af21b  mov     ebx, eax
0x1801af21d  test    eax, eax
0x1801af21f  jns     short loc_1801AF233
0x1801af221  lea     r9, aStringcchprint_2; "StringCchPrintf [%#x]"
0x1801af228  mov     r8d, 9Dh
0x1801af22e  jmp     loc_1801AF178
0x1801af233  xor     r9d, r9d; dwOptions
0x1801af236  mov     [rsp+710h+Reserved], r14d; Reserved
0x1801af23b  mov     r8d, 20019h; samDesired
0x1801af241  lea     rdx, [rsp+710h+phkResult]; phkResult
0x1801af246  lea     rcx, [rbp+610h+File]; lpFile
0x1801af24d  call    cs:__imp_RegLoadAppKeyW
0x1801af253  mov     ebx, eax
0x1801af255  test    eax, eax
0x1801af257  jz      short loc_1801AF2A5
0x1801af259  cmp     eax, 5
0x1801af25c  jz      short loc_1801AF26B
0x1801af25e  cmp     eax, 2
0x1801af261  jz      short loc_1801AF26B
0x1801af263  mov     r8d, 0AFh
0x1801af269  jmp     short loc_1801AF276
0x1801af26b  mov     edi, 3
0x1801af270  mov     r8d, 0ABh
0x1801af276  lea     r9, aRegloadappkeyF; "RegLoadAppKey failed [%d]"
0x1801af27d  mov     ecx, edi
0x1801af27f  lea     rdx, aAewerqueryfile; "AeWERQueryFileInfo"
0x1801af286  mov     [rsp+710h+Reserved], ebx
0x1801af28a  call    AslLogCallPrintf
0x1801af28f  test    ebx, ebx
0x1801af291  jle     loc_1801AF41F
0x1801af297  movzx   ebx, bx
0x1801af29a  or      ebx, 80070000h
0x1801af2a0  jmp     loc_1801AF41F
0x1801af2a5  mov     rcx, [rsp+710h+phkResult]; hKey
0x1801af2aa  lea     rax, [rsp+710h+hKey]
0x1801af2af  mov     r9d, 20019h; samDesired
0x1801af2b5  mov     qword ptr [rsp+710h+Reserved], rax; phkResult
0x1801af2ba  xor     r8d, r8d; ulOptions
0x1801af2bd  lea     rdx, aRoot; "Root"
0x1801af2c4  call    cs:__imp_RegOpenKeyExW
0x1801af2ca  mov     ebx, eax
0x1801af2cc  test    eax, eax
0x1801af2ce  jz      short loc_1801AF2E4
0x1801af2d0  cmp     eax, 2
0x1801af2d3  jz      short loc_1801AF297
0x1801af2d5  lea     r9, aFailedToOpenFi_1; "Failed to open file key [%d]"
0x1801af2dc  mov     r8d, 0BDh
0x1801af2e2  jmp     short loc_1801AF27D
0x1801af2e4  mov     rcx, [rsp+710h+hKey]; hKey
0x1801af2e9  lea     rax, [rsp+710h+hkey]
0x1801af2ee  mov     r9d, 20019h; samDesired
0x1801af2f4  mov     qword ptr [rsp+710h+Reserved], rax; phkResult
0x1801af2f9  xor     r8d, r8d; ulOptions
0x1801af2fc  lea     rdx, aInventoryappli_0; "InventoryApplicationFile"
0x1801af303  call    cs:__imp_RegOpenKeyExW
0x1801af309  mov     ebx, eax
0x1801af30b  test    eax, eax
0x1801af30d  jz      short loc_1801AF326
0x1801af30f  cmp     eax, 2
0x1801af312  jz      short loc_1801AF297
0x1801af314  lea     r9, aFailedToOpenFi_1; "Failed to open file key [%d]"
0x1801af31b  mov     r8d, 0C7h
0x1801af321  jmp     loc_1801AF27D
0x1801af326  mov     rcx, [rsp+710h+hkey]; hkey
0x1801af32b  lea     rax, [rsp+710h+var_6D0]
0x1801af330  mov     [rsp+710h+pcbData], rax; pcbData
0x1801af335  lea     rdi, [rsi+10h]
0x1801af339  mov     [rsp+710h+pvData], rdi; pvData
0x1801af33e  lea     r8, aProgramid_2; "ProgramId"
0x1801af345  mov     r9d, 2; dwFlags
0x1801af34b  mov     qword ptr [rsp+710h+Reserved], r14; pdwType
0x1801af350  lea     rdx, [rsp+710h+SubKey]; lpSubKey
0x1801af355  mov     [rsp+710h+var_6D0], 100h
0x1801af35d  call    cs:__imp_RegGetValueW
0x1801af363  mov     ebx, eax
0x1801af365  test    eax, eax
0x1801af367  jz      short loc_1801AF389
0x1801af369  cmp     eax, 2
0x1801af36c  jz      loc_1801AF297
0x1801af372  lea     r9, aFailedToGetPro_6; "Failed to get program id [%d]"
0x1801af379  mov     r8d, 0DCh
0x1801af37f  mov     ecx, 3
0x1801af384  jmp     loc_1801AF27F
0x1801af389  mov     rcx, [rsp+710h+hkey]; hkey
0x1801af38e  lea     rax, [rsp+710h+var_6D0]
0x1801af393  mov     [rsp+710h+pcbData], rax; pcbData
0x1801af398  lea     r8, aFileid; "FileId"
0x1801af39f  add     rsi, 110h
0x1801af3a6  mov     [rsp+710h+var_6D0], 100h
0x1801af3ae  mov     [rsp+710h+pvData], rsi; pvData
0x1801af3b3  lea     rdx, [rsp+710h+SubKey]; lpSubKey
0x1801af3b8  mov     r9d, 2; dwFlags
0x1801af3be  mov     qword ptr [rsp+710h+Reserved], r14; pdwType
0x1801af3c3  call    cs:__imp_RegGetValueW
0x1801af3c9  mov     ebx, eax
0x1801af3cb  test    eax, eax
0x1801af3cd  jz      short loc_1801AF3E7
0x1801af3cf  cmp     eax, 2
0x1801af3d2  jz      loc_1801AF297
0x1801af3d8  lea     r9, aFailedToGetFil_0; "Failed to get file id [%d]"
0x1801af3df  mov     r8d, 0F2h
0x1801af3e5  jmp     short loc_1801AF37F
0x1801af3e7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801af3eb  mov     rcx, rax
0x1801af3ee  inc     rcx
0x1801af3f1  cmp     [rsi+rcx*2], r14w
0x1801af3f6  jnz     short loc_1801AF3EE
0x1801af3f8  cmp     rcx, 2Ch ; ','
0x1801af3fc  jnz     short loc_1801AF413
0x1801af3fe  inc     rax
0x1801af401  cmp     [rdi+rax*2], r14w
0x1801af406  jnz     short loc_1801AF3FE
0x1801af408  cmp     rax, 2Ch ; ','
0x1801af40c  jnz     short loc_1801AF413
0x1801af40e  mov     ebx, r14d
0x1801af411  jmp     short loc_1801AF41F
0x1801af413  mov     ebx, 80070002h
0x1801af418  jmp     short loc_1801AF41F
0x1801af41a  mov     ebx, 80070057h
0x1801af41f  mov     rcx, [rsp+710h+hkey]; hKey
0x1801af424  test    rcx, rcx
0x1801af427  jz      short loc_1801AF42F
0x1801af429  call    cs:__imp_RegCloseKey
0x1801af42f  mov     rcx, [rsp+710h+hKey]; hKey
0x1801af434  test    rcx, rcx
0x1801af437  jz      short loc_1801AF43F
0x1801af439  call    cs:__imp_RegCloseKey
0x1801af43f  mov     rcx, [rsp+710h+phkResult]; hKey
0x1801af444  test    rcx, rcx
0x1801af447  jz      short loc_1801AF44F
0x1801af449  call    cs:__imp_RegCloseKey
0x1801af44f  mov     eax, ebx
0x1801af451  mov     rcx, [rbp+610h+var_20]
0x1801af458  xor     rcx, rsp; StackCookie
0x1801af45b  call    __security_check_cookie
0x1801af460  lea     r11, [rsp+710h+var_10]
0x1801af468  mov     rbx, [r11+28h]
0x1801af46c  mov     rsi, [r11+30h]
0x1801af470  mov     rsp, r11
0x1801af473  pop     r14
0x1801af475  pop     rdi
0x1801af476  pop     rbp
0x1801af477  retn
```
