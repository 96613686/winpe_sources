# AeWERQueryFileInfo

- ea: `0x18005466c`
- end: `0x180054a10`
- name: `AeWERQueryFileInfo`
- size: `932`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b280`

## callees

- `0x180015ba0`
- `0x180015eec`
- `0x1800197d4`
- `0x18005466c`
- `0x180059920`
- `0x18005a8bc`
- `0x18012526c`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x1800548f5`
- `ADVAPI32!RegGetValueW` at `0x18005495b`
- `ADVAPI32!RegGetValueW` at `0x1800548f5`
- `ADVAPI32!RegGetValueW` at `0x18005495b`
- `ADVAPI32!RegLoadAppKeyW` at `0x1800547e5`
- `ADVAPI32!RegLoadAppKeyW` at `0x1800547e5`
- `ADVAPI32!RegOpenKeyExW` at `0x18005485c`
- `ADVAPI32!RegOpenKeyExW` at `0x18005489b`
- `ADVAPI32!RegOpenKeyExW` at `0x18005485c`
- `ADVAPI32!RegOpenKeyExW` at `0x18005489b`
- `ADVAPI32!RegCloseKey` at `0x1800549c1`
- `ADVAPI32!RegCloseKey` at `0x1800549d1`
- `ADVAPI32!RegCloseKey` at `0x1800549e1`
- `ADVAPI32!RegCloseKey` at `0x1800549c1`
- `ADVAPI32!RegCloseKey` at `0x1800549d1`
- `ADVAPI32!RegCloseKey` at `0x1800549e1`

## string_xrefs

- `0x18005486d`: `Failed to open file key [%d]`
- `0x1800548ac`: `Failed to open file key [%d]`
- `0x180054788`: `Amcache.hve`
- `0x180054727`: `AppCompat\Programs`
- `0x180054754`: `StringCchPrintf for StoreDirectory [%#x]`
- `0x180054705`: `Failed to hash File path [%#x]`

## pseudocode

```c
__int64 __fastcall AeWERQueryFileInfo(__int64 a1)
{
  unsigned int v2; // edx
  bool v3; // zf
  int v4; // edi
  int PersistedLocation; // ebx
  const char *v6; // r9
  int v7; // r8d
  __int64 v8; // rdx
  LSTATUS v9; // eax
  int v10; // r8d
  const char *v11; // r9
  int v12; // ecx
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  __int64 v15; // rdi
  LSTATUS ValueW; // eax
  void *pvData; // rsi
  LSTATUS v18; // eax
  __int64 v19; // rax
  __int64 v20; // rcx
  DWORD pcbData; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[48]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v27[264]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t Destination[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR File[264]; // [rsp+4E0h] [rbp+3E0h] BYREF

  memset_0(Destination, 0, 0x20Au);
  memset_0(v27, 0, 0x20Au);
  v3 = *(_DWORD *)(a1 + 4) == 528;
  pcbData = 0;
  phkResult = 0;
  hkey = 0;
  hKey = 0;
  if ( v3 && (v4 = 1, *(_DWORD *)a1 == 1) )
  {
    PersistedLocation = ComputeFileCacheKey(SubKey, v2, *(const unsigned __int16 **)(a1 + 8));
    if ( PersistedLocation < 0 )
    {
      v6 = "Failed to hash File path [%#x]";
      v7 = 125;
LABEL_5:
      AslLogCallPrintf(1, (unsigned int)"AeWERQueryFileInfo", v7, (_DWORD)v6);
      goto LABEL_42;
    }
    PersistedLocation = StringCchPrintfW(v27, 0x105u, L"%s\\%s", 2147352624, L"AppCompat\\Programs");
    if ( PersistedLocation < 0 )
    {
      v6 = "StringCchPrintf for StoreDirectory [%#x]";
      v7 = 136;
      goto LABEL_5;
    }
    PersistedLocation = AeGetPersistedLocation(Destination, v8, v27);
    if ( PersistedLocation < 0 )
    {
      v6 = "AeGetPersistedLocation failed [%#x]";
      v7 = 147;
      goto LABEL_5;
    }
    PersistedLocation = StringCchPrintfW(File, 0x104u, L"%s\\%s", Destination, L"Amcache.hve");
    if ( PersistedLocation < 0 )
    {
      v6 = "StringCchPrintf [%#x]";
      v7 = 157;
      goto LABEL_5;
    }
    v9 = RegLoadAppKeyW(File, &phkResult, 0x20019u, 0, 0);
    PersistedLocation = v9;
    if ( v9 )
    {
      if ( v9 == 5 || v9 == 2 )
      {
        v4 = 3;
        v10 = 171;
      }
      else
      {
        v10 = 175;
      }
      v11 = "RegLoadAppKey failed [%d]";
      goto LABEL_18;
    }
    v13 = RegOpenKeyExW(phkResult, L"Root", 0, 0x20019u, &hKey);
    PersistedLocation = v13;
    if ( v13 )
    {
      if ( v13 != 2 )
      {
        v11 = "Failed to open file key [%d]";
        v10 = 189;
LABEL_18:
        v12 = v4;
        goto LABEL_19;
      }
      goto LABEL_20;
    }
    v14 = RegOpenKeyExW(hKey, L"InventoryApplicationFile", 0, 0x20019u, &hkey);
    PersistedLocation = v14;
    if ( v14 )
    {
      if ( v14 != 2 )
      {
        v11 = "Failed to open file key [%d]";
        v10 = 199;
        goto LABEL_18;
      }
LABEL_20:
      PersistedLocation = (unsigned __int16)PersistedLocation | 0x80070000;
      goto LABEL_42;
    }
    v15 = a1 + 16;
    pcbData = 256;
    ValueW = RegGetValueW(hkey, SubKey, L"ProgramId", 2u, 0, (PVOID)(a1 + 16), &pcbData);
    PersistedLocation = ValueW;
    if ( ValueW )
    {
      if ( ValueW == 2 )
        goto LABEL_20;
      v11 = "Failed to get program id [%d]";
      v10 = 220;
LABEL_30:
      v12 = 3;
LABEL_19:
      AslLogCallPrintf(v12, (unsigned int)"AeWERQueryFileInfo", v10, (_DWORD)v11);
      if ( PersistedLocation <= 0 )
        goto LABEL_42;
      goto LABEL_20;
    }
    pvData = (void *)(a1 + 272);
    pcbData = 256;
    v18 = RegGetValueW(hkey, SubKey, L"FileId", 2u, 0, pvData, &pcbData);
    PersistedLocation = v18;
    if ( v18 )
    {
      if ( v18 == 2 )
        goto LABEL_20;
      v11 = "Failed to get file id [%d]";
      v10 = 242;
      goto LABEL_30;
    }
    v19 = -1;
    v20 = -1;
    do
      ++v20;
    while ( *((_WORD *)pvData + v20) );
    if ( v20 != 44 )
      goto LABEL_40;
    do
      ++v19;
    while ( *(_WORD *)(v15 + 2 * v19) );
    if ( v19 == 44 )
      PersistedLocation = 0;
    else
LABEL_40:
      PersistedLocation = -2147024894;
  }
  else
  {
    PersistedLocation = -2147024809;
  }
LABEL_42:
  if ( hkey )
    RegCloseKey(hkey);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)PersistedLocation;
}

```

## disassembly

```asm
0x18005466c  mov     [rsp-8+arg_8], rbx
0x180054671  mov     [rsp-8+arg_10], rsi
0x180054676  push    rbp
0x180054677  push    rdi
0x180054678  push    r14
0x18005467a  lea     rbp, [rsp-600h]
0x180054682  sub     rsp, 700h
0x180054689  mov     rax, cs:__security_cookie
0x180054690  xor     rax, rsp
0x180054693  mov     [rbp+610h+var_20], rax
0x18005469a  mov     rsi, rcx
0x18005469d  mov     ebx, 20Ah
0x1800546a2  mov     r8d, ebx; Size
0x1800546a5  lea     rcx, [rbp+610h+Destination]; void *
0x1800546ac  xor     edx, edx; Val
0x1800546ae  call    memset_0
0x1800546b3  mov     r8d, ebx; Size
0x1800546b6  lea     rcx, [rbp+610h+var_650]; void *
0x1800546ba  xor     edx, edx; Val
0x1800546bc  call    memset_0
0x1800546c1  xor     r14d, r14d
0x1800546c4  cmp     dword ptr [rsi+4], 210h
0x1800546cb  mov     [rsp+710h+var_6D0], r14d
0x1800546d0  mov     [rsp+710h+phkResult], r14
0x1800546d5  mov     [rsp+710h+hkey], r14
0x1800546da  mov     [rsp+710h+hKey], r14
0x1800546df  jnz     loc_1800549B2
0x1800546e5  lea     edi, [r14+1]
0x1800546e9  cmp     [rsi], edi
0x1800546eb  jnz     loc_1800549B2
0x1800546f1  mov     r8, [rsi+8]; unsigned __int16 *
0x1800546f5  lea     rcx, [rsp+710h+SubKey]; unsigned __int16 *
0x1800546fa  call    ?ComputeFileCacheKey@@YAJPEAGKPEBG@Z; ComputeFileCacheKey(ushort *,ulong,ushort const *)
0x1800546ff  mov     ebx, eax
0x180054701  test    eax, eax
0x180054703  jns     short loc_180054727
0x180054705  lea     r9, aFailedToHashFi; "Failed to hash File path [%#x]"
0x18005470c  lea     r8d, [r14+7Dh]
0x180054710  lea     rdx, aAewerqueryfile; "AeWERQueryFileInfo"
0x180054717  mov     [rsp+710h+Reserved], eax
0x18005471b  mov     ecx, edi
0x18005471d  call    AslLogCallPrintf
0x180054722  jmp     loc_1800549B7
0x180054727  lea     rax, aAppcompatProgr; "AppCompat\\Programs"
0x18005472e  mov     r9d, 7FFE0030h
0x180054734  lea     r8, aSS_1; "%s\\%s"
0x18005473b  mov     qword ptr [rsp+710h+Reserved], rax
0x180054740  mov     edx, 105h; unsigned __int64
0x180054745  lea     rcx, [rbp+610h+var_650]; unsigned __int16 *
0x180054749  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005474e  mov     ebx, eax
0x180054750  test    eax, eax
0x180054752  jns     short loc_180054763
0x180054754  lea     r9, aStringcchprint_1; "StringCchPrintf for StoreDirectory [%#x"...
0x18005475b  mov     r8d, 88h
0x180054761  jmp     short loc_180054710
0x180054763  lea     r8, [rbp+610h+var_650]; unsigned __int16 *
0x180054767  lea     rcx, [rbp+610h+Destination]; Destination
0x18005476e  call    ?AeGetPersistedLocation@@YAJPEAGKQEBG@Z; AeGetPersistedLocation(ushort *,ulong,ushort const * const)
0x180054773  mov     ebx, eax
0x180054775  test    eax, eax
0x180054777  jns     short loc_180054788
0x180054779  lea     r9, aAegetpersisted; "AeGetPersistedLocation failed [%#x]"
0x180054780  mov     r8d, 93h
0x180054786  jmp     short loc_180054710
0x180054788  lea     rax, aAmcacheHve; "Amcache.hve"
0x18005478f  mov     edx, 104h; unsigned __int64
0x180054794  lea     r9, [rbp+610h+Destination]
0x18005479b  mov     qword ptr [rsp+710h+Reserved], rax
0x1800547a0  lea     r8, aSS_1; "%s\\%s"
0x1800547a7  lea     rcx, [rbp+610h+File]; unsigned __int16 *
0x1800547ae  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800547b3  mov     ebx, eax
0x1800547b5  test    eax, eax
0x1800547b7  jns     short loc_1800547CB
0x1800547b9  lea     r9, aStringcchprint_2; "StringCchPrintf [%#x]"
0x1800547c0  mov     r8d, 9Dh
0x1800547c6  jmp     loc_180054710
0x1800547cb  xor     r9d, r9d; dwOptions
0x1800547ce  mov     [rsp+710h+Reserved], r14d; Reserved
0x1800547d3  mov     r8d, 20019h; samDesired
0x1800547d9  lea     rdx, [rsp+710h+phkResult]; phkResult
0x1800547de  lea     rcx, [rbp+610h+File]; lpFile
0x1800547e5  call    cs:__imp_RegLoadAppKeyW
0x1800547eb  mov     ebx, eax
0x1800547ed  test    eax, eax
0x1800547ef  jz      short loc_18005483D
0x1800547f1  cmp     eax, 5
0x1800547f4  jz      short loc_180054803
0x1800547f6  cmp     eax, 2
0x1800547f9  jz      short loc_180054803
0x1800547fb  mov     r8d, 0AFh
0x180054801  jmp     short loc_18005480E
0x180054803  mov     edi, 3
0x180054808  mov     r8d, 0ABh
0x18005480e  lea     r9, aRegloadappkeyF; "RegLoadAppKey failed [%d]"
0x180054815  mov     ecx, edi
0x180054817  lea     rdx, aAewerqueryfile; "AeWERQueryFileInfo"
0x18005481e  mov     [rsp+710h+Reserved], ebx
0x180054822  call    AslLogCallPrintf
0x180054827  test    ebx, ebx
0x180054829  jle     loc_1800549B7
0x18005482f  movzx   ebx, bx
0x180054832  or      ebx, 80070000h
0x180054838  jmp     loc_1800549B7
0x18005483d  mov     rcx, [rsp+710h+phkResult]; hKey
0x180054842  lea     rax, [rsp+710h+hKey]
0x180054847  mov     r9d, 20019h; samDesired
0x18005484d  mov     qword ptr [rsp+710h+Reserved], rax; phkResult
0x180054852  xor     r8d, r8d; ulOptions
0x180054855  lea     rdx, aRoot; "Root"
0x18005485c  call    cs:__imp_RegOpenKeyExW
0x180054862  mov     ebx, eax
0x180054864  test    eax, eax
0x180054866  jz      short loc_18005487C
0x180054868  cmp     eax, 2
0x18005486b  jz      short loc_18005482F
0x18005486d  lea     r9, aFailedToOpenFi_0; "Failed to open file key [%d]"
0x180054874  mov     r8d, 0BDh
0x18005487a  jmp     short loc_180054815
0x18005487c  mov     rcx, [rsp+710h+hKey]; hKey
0x180054881  lea     rax, [rsp+710h+hkey]
0x180054886  mov     r9d, 20019h; samDesired
0x18005488c  mov     qword ptr [rsp+710h+Reserved], rax; phkResult
0x180054891  xor     r8d, r8d; ulOptions
0x180054894  lea     rdx, aInventoryappli_5; "InventoryApplicationFile"
0x18005489b  call    cs:__imp_RegOpenKeyExW
0x1800548a1  mov     ebx, eax
0x1800548a3  test    eax, eax
0x1800548a5  jz      short loc_1800548BE
0x1800548a7  cmp     eax, 2
0x1800548aa  jz      short loc_18005482F
0x1800548ac  lea     r9, aFailedToOpenFi_0; "Failed to open file key [%d]"
0x1800548b3  mov     r8d, 0C7h
0x1800548b9  jmp     loc_180054815
0x1800548be  mov     rcx, [rsp+710h+hkey]; hkey
0x1800548c3  lea     rax, [rsp+710h+var_6D0]
0x1800548c8  mov     [rsp+710h+pcbData], rax; pcbData
0x1800548cd  lea     rdi, [rsi+10h]
0x1800548d1  mov     [rsp+710h+pvData], rdi; pvData
0x1800548d6  lea     r8, ValueName; "ProgramId"
0x1800548dd  mov     r9d, 2; dwFlags
0x1800548e3  mov     qword ptr [rsp+710h+Reserved], r14; pdwType
0x1800548e8  lea     rdx, [rsp+710h+SubKey]; lpSubKey
0x1800548ed  mov     [rsp+710h+var_6D0], 100h
0x1800548f5  call    cs:__imp_RegGetValueW
0x1800548fb  mov     ebx, eax
0x1800548fd  test    eax, eax
0x1800548ff  jz      short loc_180054921
0x180054901  cmp     eax, 2
0x180054904  jz      loc_18005482F
0x18005490a  lea     r9, aFailedToGetPro_0; "Failed to get program id [%d]"
0x180054911  mov     r8d, 0DCh
0x180054917  mov     ecx, 3
0x18005491c  jmp     loc_180054817
0x180054921  mov     rcx, [rsp+710h+hkey]; hkey
0x180054926  lea     rax, [rsp+710h+var_6D0]
0x18005492b  mov     [rsp+710h+pcbData], rax; pcbData
0x180054930  lea     r8, aFileid_0; "FileId"
0x180054937  add     rsi, 110h
0x18005493e  mov     [rsp+710h+var_6D0], 100h
0x180054946  mov     [rsp+710h+pvData], rsi; pvData
0x18005494b  lea     rdx, [rsp+710h+SubKey]; lpSubKey
0x180054950  mov     r9d, 2; dwFlags
0x180054956  mov     qword ptr [rsp+710h+Reserved], r14; pdwType
0x18005495b  call    cs:__imp_RegGetValueW
0x180054961  mov     ebx, eax
0x180054963  test    eax, eax
0x180054965  jz      short loc_18005497F
0x180054967  cmp     eax, 2
0x18005496a  jz      loc_18005482F
0x180054970  lea     r9, aFailedToGetFil_0; "Failed to get file id [%d]"
0x180054977  mov     r8d, 0F2h
0x18005497d  jmp     short loc_180054917
0x18005497f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180054983  mov     rcx, rax
0x180054986  inc     rcx
0x180054989  cmp     [rsi+rcx*2], r14w
0x18005498e  jnz     short loc_180054986
0x180054990  cmp     rcx, 2Ch ; ','
0x180054994  jnz     short loc_1800549AB
0x180054996  inc     rax
0x180054999  cmp     [rdi+rax*2], r14w
0x18005499e  jnz     short loc_180054996
0x1800549a0  cmp     rax, 2Ch ; ','
0x1800549a4  jnz     short loc_1800549AB
0x1800549a6  mov     ebx, r14d
0x1800549a9  jmp     short loc_1800549B7
0x1800549ab  mov     ebx, 80070002h
0x1800549b0  jmp     short loc_1800549B7
0x1800549b2  mov     ebx, 80070057h
0x1800549b7  mov     rcx, [rsp+710h+hkey]; hKey
0x1800549bc  test    rcx, rcx
0x1800549bf  jz      short loc_1800549C7
0x1800549c1  call    cs:__imp_RegCloseKey
0x1800549c7  mov     rcx, [rsp+710h+hKey]; hKey
0x1800549cc  test    rcx, rcx
0x1800549cf  jz      short loc_1800549D7
0x1800549d1  call    cs:__imp_RegCloseKey
0x1800549d7  mov     rcx, [rsp+710h+phkResult]; hKey
0x1800549dc  test    rcx, rcx
0x1800549df  jz      short loc_1800549E7
0x1800549e1  call    cs:__imp_RegCloseKey
0x1800549e7  mov     eax, ebx
0x1800549e9  mov     rcx, [rbp+610h+var_20]
0x1800549f0  xor     rcx, rsp; StackCookie
0x1800549f3  call    __security_check_cookie
0x1800549f8  lea     r11, [rsp+710h+var_10]
0x180054a00  mov     rbx, [r11+28h]
0x180054a04  mov     rsi, [r11+30h]
0x180054a08  mov     rsp, r11
0x180054a0b  pop     r14
0x180054a0d  pop     rdi
0x180054a0e  pop     rbp
0x180054a0f  retn
```
