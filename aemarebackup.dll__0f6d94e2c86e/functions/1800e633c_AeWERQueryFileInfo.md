# AeWERQueryFileInfo

- ea: `0x1800e633c`
- end: `0x1800e66e0`
- name: `AeWERQueryFileInfo`
- size: `932`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800e3cb0`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x18000d62c`
- `0x18001767c`
- `0x18004c020`
- `0x1800e6288`
- `0x1800e633c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x1800e64b5`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x1800e64b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e652c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e656b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e652c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800e656b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e65c5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e662b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e65c5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800e662b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e6691`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e66a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e66b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e6691`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e66a1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800e66b1`

## string_xrefs

- `0x1800e6458`: `Amcache.hve`
- `0x1800e653d`: `Failed to open file key [%d]`
- `0x1800e657c`: `Failed to open file key [%d]`
- `0x1800e63d5`: `Failed to hash File path [%#x]`
- `0x1800e63f7`: `AppCompat\Programs`
- `0x1800e6424`: `StringCchPrintf for StoreDirectory [%#x]`

## pseudocode

```c
__int64 __fastcall AeWERQueryFileInfo(__int64 a1)
{
  __int64 v2; // rdx
  bool v3; // zf
  unsigned int v4; // edi
  int PersistedLocation; // eax
  signed int v6; // ebx
  const char *v7; // r9
  __int64 v8; // r8
  __int64 v9; // rdx
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
0x1800e633c  mov     [rsp-8+arg_8], rbx
0x1800e6341  mov     [rsp-8+arg_10], rsi
0x1800e6346  push    rbp
0x1800e6347  push    rdi
0x1800e6348  push    r14
0x1800e634a  lea     rbp, [rsp-600h]
0x1800e6352  sub     rsp, 700h
0x1800e6359  mov     rax, cs:__security_cookie
0x1800e6360  xor     rax, rsp
0x1800e6363  mov     [rbp+610h+var_20], rax
0x1800e636a  mov     rsi, rcx
0x1800e636d  mov     ebx, 20Ah
0x1800e6372  mov     r8d, ebx; Size
0x1800e6375  lea     rcx, [rbp+610h+Destination]; void *
0x1800e637c  xor     edx, edx; Val
0x1800e637e  call    memset_0
0x1800e6383  mov     r8d, ebx; Size
0x1800e6386  lea     rcx, [rbp+610h+var_650]; void *
0x1800e638a  xor     edx, edx; Val
0x1800e638c  call    memset_0
0x1800e6391  xor     r14d, r14d
0x1800e6394  cmp     dword ptr [rsi+4], 210h
0x1800e639b  mov     [rsp+710h+var_6D0], r14d
0x1800e63a0  mov     [rsp+710h+phkResult], r14
0x1800e63a5  mov     [rsp+710h+hkey], r14
0x1800e63aa  mov     [rsp+710h+hKey], r14
0x1800e63af  jnz     loc_1800E6682
0x1800e63b5  lea     edi, [r14+1]
0x1800e63b9  cmp     [rsi], edi
0x1800e63bb  jnz     loc_1800E6682
0x1800e63c1  mov     r8, [rsi+8]; unsigned __int16 *
0x1800e63c5  lea     rcx, [rsp+710h+SubKey]; unsigned __int16 *
0x1800e63ca  call    ?ComputeFileCacheKey@@YAJPEAGKPEBG@Z; ComputeFileCacheKey(ushort *,ulong,ushort const *)
0x1800e63cf  mov     ebx, eax
0x1800e63d1  test    eax, eax
0x1800e63d3  jns     short loc_1800E63F7
0x1800e63d5  lea     r9, aFailedToHashFi; "Failed to hash File path [%#x]"
0x1800e63dc  lea     r8d, [r14+7Dh]
0x1800e63e0  lea     rdx, aAewerqueryfile; "AeWERQueryFileInfo"
0x1800e63e7  mov     [rsp+710h+Reserved], eax
0x1800e63eb  mov     ecx, edi
0x1800e63ed  call    AslLogCallPrintf
0x1800e63f2  jmp     loc_1800E6687
0x1800e63f7  lea     rax, aAppcompatProgr; "AppCompat\\Programs"
0x1800e63fe  mov     r9d, 7FFE0030h
0x1800e6404  lea     r8, aSS_1; "%s\\%s"
0x1800e640b  mov     qword ptr [rsp+710h+Reserved], rax
0x1800e6410  mov     edx, 105h; unsigned __int64
0x1800e6415  lea     rcx, [rbp+610h+var_650]; unsigned __int16 *
0x1800e6419  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800e641e  mov     ebx, eax
0x1800e6420  test    eax, eax
0x1800e6422  jns     short loc_1800E6433
0x1800e6424  lea     r9, aStringcchprint_0; "StringCchPrintf for StoreDirectory [%#x"...
0x1800e642b  mov     r8d, 88h
0x1800e6431  jmp     short loc_1800E63E0
0x1800e6433  lea     r8, [rbp+610h+var_650]; unsigned __int16 *
0x1800e6437  lea     rcx, [rbp+610h+Destination]; Destination
0x1800e643e  call    ?AeGetPersistedLocation@@YAJPEAGKQEBG@Z; AeGetPersistedLocation(ushort *,ulong,ushort const * const)
0x1800e6443  mov     ebx, eax
0x1800e6445  test    eax, eax
0x1800e6447  jns     short loc_1800E6458
0x1800e6449  lea     r9, aAegetpersisted; "AeGetPersistedLocation failed [%#x]"
0x1800e6450  mov     r8d, 93h
0x1800e6456  jmp     short loc_1800E63E0
0x1800e6458  lea     rax, aAmcacheHve; "Amcache.hve"
0x1800e645f  mov     edx, 104h; unsigned __int64
0x1800e6464  lea     r9, [rbp+610h+Destination]
0x1800e646b  mov     qword ptr [rsp+710h+Reserved], rax
0x1800e6470  lea     r8, aSS_1; "%s\\%s"
0x1800e6477  lea     rcx, [rbp+610h+File]; unsigned __int16 *
0x1800e647e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800e6483  mov     ebx, eax
0x1800e6485  test    eax, eax
0x1800e6487  jns     short loc_1800E649B
0x1800e6489  lea     r9, aStringcchprint_1; "StringCchPrintf [%#x]"
0x1800e6490  mov     r8d, 9Dh
0x1800e6496  jmp     loc_1800E63E0
0x1800e649b  xor     r9d, r9d; dwOptions
0x1800e649e  mov     [rsp+710h+Reserved], r14d; Reserved
0x1800e64a3  mov     r8d, 20019h; samDesired
0x1800e64a9  lea     rdx, [rsp+710h+phkResult]; phkResult
0x1800e64ae  lea     rcx, [rbp+610h+File]; lpFile
0x1800e64b5  call    cs:__imp_RegLoadAppKeyW
0x1800e64bb  mov     ebx, eax
0x1800e64bd  test    eax, eax
0x1800e64bf  jz      short loc_1800E650D
0x1800e64c1  cmp     eax, 5
0x1800e64c4  jz      short loc_1800E64D3
0x1800e64c6  cmp     eax, 2
0x1800e64c9  jz      short loc_1800E64D3
0x1800e64cb  mov     r8d, 0AFh
0x1800e64d1  jmp     short loc_1800E64DE
0x1800e64d3  mov     edi, 3
0x1800e64d8  mov     r8d, 0ABh
0x1800e64de  lea     r9, aRegloadappkeyF; "RegLoadAppKey failed [%d]"
0x1800e64e5  mov     ecx, edi
0x1800e64e7  lea     rdx, aAewerqueryfile; "AeWERQueryFileInfo"
0x1800e64ee  mov     [rsp+710h+Reserved], ebx
0x1800e64f2  call    AslLogCallPrintf
0x1800e64f7  test    ebx, ebx
0x1800e64f9  jle     loc_1800E6687
0x1800e64ff  movzx   ebx, bx
0x1800e6502  or      ebx, 80070000h
0x1800e6508  jmp     loc_1800E6687
0x1800e650d  mov     rcx, [rsp+710h+phkResult]; hKey
0x1800e6512  lea     rax, [rsp+710h+hKey]
0x1800e6517  mov     r9d, 20019h; samDesired
0x1800e651d  mov     qword ptr [rsp+710h+Reserved], rax; phkResult
0x1800e6522  xor     r8d, r8d; ulOptions
0x1800e6525  lea     rdx, aRoot; "Root"
0x1800e652c  call    cs:__imp_RegOpenKeyExW
0x1800e6532  mov     ebx, eax
0x1800e6534  test    eax, eax
0x1800e6536  jz      short loc_1800E654C
0x1800e6538  cmp     eax, 2
0x1800e653b  jz      short loc_1800E64FF
0x1800e653d  lea     r9, aFailedToOpenFi; "Failed to open file key [%d]"
0x1800e6544  mov     r8d, 0BDh
0x1800e654a  jmp     short loc_1800E64E5
0x1800e654c  mov     rcx, [rsp+710h+hKey]; hKey
0x1800e6551  lea     rax, [rsp+710h+hkey]
0x1800e6556  mov     r9d, 20019h; samDesired
0x1800e655c  mov     qword ptr [rsp+710h+Reserved], rax; phkResult
0x1800e6561  xor     r8d, r8d; ulOptions
0x1800e6564  lea     rdx, aInventoryappli_1; "InventoryApplicationFile"
0x1800e656b  call    cs:__imp_RegOpenKeyExW
0x1800e6571  mov     ebx, eax
0x1800e6573  test    eax, eax
0x1800e6575  jz      short loc_1800E658E
0x1800e6577  cmp     eax, 2
0x1800e657a  jz      short loc_1800E64FF
0x1800e657c  lea     r9, aFailedToOpenFi; "Failed to open file key [%d]"
0x1800e6583  mov     r8d, 0C7h
0x1800e6589  jmp     loc_1800E64E5
0x1800e658e  mov     rcx, [rsp+710h+hkey]; hkey
0x1800e6593  lea     rax, [rsp+710h+var_6D0]
0x1800e6598  mov     [rsp+710h+pcbData], rax; pcbData
0x1800e659d  lea     rdi, [rsi+10h]
0x1800e65a1  mov     [rsp+710h+pvData], rdi; pvData
0x1800e65a6  lea     r8, aProgramid_0; "ProgramId"
0x1800e65ad  mov     r9d, 2; dwFlags
0x1800e65b3  mov     qword ptr [rsp+710h+Reserved], r14; pdwType
0x1800e65b8  lea     rdx, [rsp+710h+SubKey]; lpSubKey
0x1800e65bd  mov     [rsp+710h+var_6D0], 100h
0x1800e65c5  call    cs:__imp_RegGetValueW
0x1800e65cb  mov     ebx, eax
0x1800e65cd  test    eax, eax
0x1800e65cf  jz      short loc_1800E65F1
0x1800e65d1  cmp     eax, 2
0x1800e65d4  jz      loc_1800E64FF
0x1800e65da  lea     r9, aFailedToGetPro; "Failed to get program id [%d]"
0x1800e65e1  mov     r8d, 0DCh
0x1800e65e7  mov     ecx, 3
0x1800e65ec  jmp     loc_1800E64E7
0x1800e65f1  mov     rcx, [rsp+710h+hkey]; hkey
0x1800e65f6  lea     rax, [rsp+710h+var_6D0]
0x1800e65fb  mov     [rsp+710h+pcbData], rax; pcbData
0x1800e6600  lea     r8, aFileid; "FileId"
0x1800e6607  add     rsi, 110h
0x1800e660e  mov     [rsp+710h+var_6D0], 100h
0x1800e6616  mov     [rsp+710h+pvData], rsi; pvData
0x1800e661b  lea     rdx, [rsp+710h+SubKey]; lpSubKey
0x1800e6620  mov     r9d, 2; dwFlags
0x1800e6626  mov     qword ptr [rsp+710h+Reserved], r14; pdwType
0x1800e662b  call    cs:__imp_RegGetValueW
0x1800e6631  mov     ebx, eax
0x1800e6633  test    eax, eax
0x1800e6635  jz      short loc_1800E664F
0x1800e6637  cmp     eax, 2
0x1800e663a  jz      loc_1800E64FF
0x1800e6640  lea     r9, aFailedToGetFil_0; "Failed to get file id [%d]"
0x1800e6647  mov     r8d, 0F2h
0x1800e664d  jmp     short loc_1800E65E7
0x1800e664f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800e6653  mov     rcx, rax
0x1800e6656  inc     rcx
0x1800e6659  cmp     [rsi+rcx*2], r14w
0x1800e665e  jnz     short loc_1800E6656
0x1800e6660  cmp     rcx, 2Ch ; ','
0x1800e6664  jnz     short loc_1800E667B
0x1800e6666  inc     rax
0x1800e6669  cmp     [rdi+rax*2], r14w
0x1800e666e  jnz     short loc_1800E6666
0x1800e6670  cmp     rax, 2Ch ; ','
0x1800e6674  jnz     short loc_1800E667B
0x1800e6676  mov     ebx, r14d
0x1800e6679  jmp     short loc_1800E6687
0x1800e667b  mov     ebx, 80070002h
0x1800e6680  jmp     short loc_1800E6687
0x1800e6682  mov     ebx, 80070057h
0x1800e6687  mov     rcx, [rsp+710h+hkey]; hKey
0x1800e668c  test    rcx, rcx
0x1800e668f  jz      short loc_1800E6697
0x1800e6691  call    cs:__imp_RegCloseKey
0x1800e6697  mov     rcx, [rsp+710h+hKey]; hKey
0x1800e669c  test    rcx, rcx
0x1800e669f  jz      short loc_1800E66A7
0x1800e66a1  call    cs:__imp_RegCloseKey
0x1800e66a7  mov     rcx, [rsp+710h+phkResult]; hKey
0x1800e66ac  test    rcx, rcx
0x1800e66af  jz      short loc_1800E66B7
0x1800e66b1  call    cs:__imp_RegCloseKey
0x1800e66b7  mov     eax, ebx
0x1800e66b9  mov     rcx, [rbp+610h+var_20]
0x1800e66c0  xor     rcx, rsp; StackCookie
0x1800e66c3  call    __security_check_cookie
0x1800e66c8  lea     r11, [rsp+710h+var_10]
0x1800e66d0  mov     rbx, [r11+28h]
0x1800e66d4  mov     rsi, [r11+30h]
0x1800e66d8  mov     rsp, r11
0x1800e66db  pop     r14
0x1800e66dd  pop     rdi
0x1800e66de  pop     rbp
0x1800e66df  retn
```
