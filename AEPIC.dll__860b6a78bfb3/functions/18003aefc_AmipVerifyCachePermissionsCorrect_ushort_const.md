# AmipVerifyCachePermissionsCorrect(ushort const *)

- ea: `0x18003aefc`
- end: `0x18003b247`
- name: `?AmipVerifyCachePermissionsCorrect@@YA_NPEBG@Z`
- size: `843`
- prototype: `bool __fastcall(LPCWSTR lpFile)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003b2c4`

## callees

- `0x180005890`
- `0x180006938`
- `0x1800295dc`
- `0x180039e08`
- `0x18003a5a8`
- `0x18003aefc`
- `0x18003b5e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b10a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003b10a`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18003b0c9`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18003b0c9`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18003b21f`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18003b21f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003afe6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003b026`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003afe6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003b026`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b201`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003b201`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003b17d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003b1ba`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003b17d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003b1ba`

## string_xrefs

- `0x18003af6b`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x18003af76`: `AppCompatFlags`
- `0x18003b187`: `RegSetKeyValue failed [%d]`
- `0x18003b1c4`: `RegSetKeyValue failed [%d]`
- `0x18003b145`: `AmipVerifyCachePermissionsCorrect`
- `0x18003b1e7`: `AmipVerifyCachePermissionsCorrect`
- `0x18003b0a0`: `AmiUtilitySetPrivilege(SE_BACKUP_PRIVILEGE) failed [%d]`
- `0x18003b060`: `AmiUtilitySetPrivilege(SE_RESTORE_PRIVILEGE) failed [%d]`
- `0x18003b114`: `RegOpenKeyEx failed [%d]`

## pseudocode

```c
char __fastcall AmipVerifyCachePermissionsCorrect(LPCWSTR lpFile)
{
  char v2; // di
  unsigned int v3; // ebx
  char v4; // r14
  LSTATUS PersistedLocation; // eax
  const char *v6; // r9
  __int64 v7; // r8
  unsigned __int8 v8; // dl
  unsigned __int8 v9; // dl
  unsigned int v10; // r9d
  bool v11; // zf
  unsigned int v12; // r9d
  bool v13; // zf
  __int64 v14; // rcx
  LPDWORD pdwType; // [rsp+20h] [rbp-E0h]
  int Data; // [rsp+40h] [rbp-C0h] BYREF
  int pvData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v20; // [rsp+4Ch] [rbp-B4h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  Data = 0;
  pcbData = 0;
  pvData = 0;
  v20 = 0;
  v2 = 0;
  memset_0(SubKey, 0, 0x20Au);
  v3 = 1;
  phkResult = 0;
  v4 = 0;
  PersistedLocation = AmiUtilityGetPersistedLocation(
                        (unsigned int)SubKey,
                        261,
                        (unsigned int)L"AppCompatFlags",
                        (unsigned int)L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
                        1);
  if ( PersistedLocation < 0 )
  {
    v6 = "AmiUtilityGetPersistedLocation [%#x]";
    v7 = 763;
LABEL_28:
    v14 = v3;
    goto LABEL_29;
  }
  pcbData = 4;
  RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"AmiHivePermissionsCorrect", 0x20000018u, 0, &Data, &pcbData);
  v20 = 4;
  RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"AmiHiveOwnerCorrect", 0x20000018u, 0, &pvData, &v20);
  if ( Data == 1 && pvData == 1 )
  {
LABEL_26:
    v2 = 1;
    goto LABEL_30;
  }
  v10 = AmiUtilitySetPrivilege(0x12u, v8);
  if ( v10 )
  {
    v11 = v10 == 1314;
    PersistedLocation = 1314;
    if ( v10 != 1314 )
      PersistedLocation = v10;
    v6 = "AmiUtilitySetPrivilege(SE_RESTORE_PRIVILEGE) failed [%d]";
    v7 = 802;
    if ( v11 )
    {
      v7 = 806;
      v3 = 3;
    }
    goto LABEL_28;
  }
  v12 = AmiUtilitySetPrivilege(0x11u, v9);
  if ( v12 )
  {
    v13 = v12 == 1314;
    PersistedLocation = 1314;
    if ( v12 != 1314 )
      PersistedLocation = v12;
    v6 = "AmiUtilitySetPrivilege(SE_BACKUP_PRIVILEGE) failed [%d]";
    v7 = 814;
    if ( v13 )
    {
      v7 = 818;
      v3 = 3;
    }
    goto LABEL_28;
  }
  PersistedLocation = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"{11517B7C-E79D-4e20-961B-75A811715ADD}", lpFile);
  if ( !PersistedLocation )
  {
    v4 = 1;
    PersistedLocation = RegOpenKeyExW(
                          HKEY_LOCAL_MACHINE,
                          L"{11517B7C-E79D-4e20-961B-75A811715ADD}",
                          0,
                          0xF003Fu,
                          &phkResult);
    if ( PersistedLocation )
    {
      v6 = "RegOpenKeyEx failed [%d]";
      v7 = 842;
      goto LABEL_28;
    }
    PersistedLocation = AmiFixKeyPermissionsRecursive(phkResult);
    if ( PersistedLocation )
    {
      v6 = "AmiFixKeyPermissionsRecursive failed [%d]";
      v7 = 883;
      goto LABEL_28;
    }
    AslLogCallPrintf(
      3,
      "AmipVerifyCachePermissionsCorrect",
      849,
      "AmiFixKeyPermissionsRecursive succeeded. Setting Permissions/Owner correct values in reg.");
    Data = 1;
    PersistedLocation = RegSetKeyValueW(HKEY_LOCAL_MACHINE, SubKey, L"AmiHivePermissionsCorrect", 4u, &Data, 4u);
    if ( PersistedLocation )
    {
      v6 = "RegSetKeyValue failed [%d]";
      v7 = 863;
      goto LABEL_28;
    }
    pvData = 1;
    PersistedLocation = RegSetKeyValueW(HKEY_LOCAL_MACHINE, SubKey, L"AmiHiveOwnerCorrect", 4u, &pvData, 4u);
    if ( PersistedLocation )
    {
      v6 = "RegSetKeyValue failed [%d]";
      v7 = 875;
      goto LABEL_28;
    }
    goto LABEL_26;
  }
  v6 = "RegLoadKey failed [%d]";
  v7 = 831;
  v14 = 3;
LABEL_29:
  LODWORD(pdwType) = PersistedLocation;
  AslLogCallPrintf(v14, "AmipVerifyCachePermissionsCorrect", v7, v6, pdwType);
LABEL_30:
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( v4 )
    RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"{11517B7C-E79D-4e20-961B-75A811715ADD}");
  return v2;
}

```

## disassembly

```asm
0x18003aefc  push    rbp
0x18003aefe  push    rbx
0x18003aeff  push    rsi
0x18003af00  push    rdi
0x18003af01  push    r13
0x18003af03  push    r14
0x18003af05  lea     rbp, [rsp-188h]
0x18003af0d  sub     rsp, 288h
0x18003af14  mov     rax, cs:__security_cookie
0x18003af1b  xor     rax, rsp
0x18003af1e  mov     [rbp+1B0h+var_40], rax
0x18003af25  mov     rsi, rcx
0x18003af28  mov     [rsp+2B0h+Data], 0
0x18003af30  lea     rcx, [rsp+2B0h+SubKey]; void *
0x18003af35  mov     [rsp+2B0h+var_268], 0
0x18003af3d  xor     edx, edx; Val
0x18003af3f  mov     [rsp+2B0h+var_26C], 0
0x18003af47  mov     r8d, 20Ah; Size
0x18003af4d  mov     [rsp+2B0h+var_264], 0
0x18003af55  xor     dil, dil
0x18003af58  call    memset_0
0x18003af5d  mov     ebx, 1
0x18003af62  mov     [rsp+2B0h+phkResult], 0
0x18003af6b  lea     r9, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003af72  mov     dword ptr [rsp+2B0h+pdwType], ebx
0x18003af76  lea     r8, aAppcompatflags; "AppCompatFlags"
0x18003af7d  mov     edx, 105h
0x18003af82  lea     rcx, [rsp+2B0h+SubKey]
0x18003af87  xor     r14b, r14b
0x18003af8a  call    AmiUtilityGetPersistedLocation
0x18003af8f  mov     r13, 0FFFFFFFF80000002h
0x18003af96  test    eax, eax
0x18003af98  jns     short loc_18003AFAC
0x18003af9a  lea     r9, aAmiutilitygetp; "AmiUtilityGetPersistedLocation [%#x]"
0x18003afa1  mov     r8d, 2FBh
0x18003afa7  jmp     loc_18003B1E5
0x18003afac  lea     rax, [rsp+2B0h+var_268]
0x18003afb1  mov     [rsp+2B0h+var_268], 4
0x18003afb9  mov     [rsp+2B0h+pcbData], rax; pcbData
0x18003afbe  lea     r8, aAmihivepermiss; "AmiHivePermissionsCorrect"
0x18003afc5  lea     rax, [rsp+2B0h+Data]
0x18003afca  mov     r9d, 20000018h; dwFlags
0x18003afd0  mov     [rsp+2B0h+pvData], rax; pvData
0x18003afd5  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x18003afda  mov     rcx, r13; hkey
0x18003afdd  mov     [rsp+2B0h+pdwType], 0; pdwType
0x18003afe6  call    cs:__imp_RegGetValueW
0x18003afec  lea     rax, [rsp+2B0h+var_264]
0x18003aff1  mov     [rsp+2B0h+var_264], 4
0x18003aff9  mov     [rsp+2B0h+pcbData], rax; pcbData
0x18003affe  lea     r8, aAmihiveownerco; "AmiHiveOwnerCorrect"
0x18003b005  lea     rax, [rsp+2B0h+var_26C]
0x18003b00a  mov     r9d, 20000018h; dwFlags
0x18003b010  mov     [rsp+2B0h+pvData], rax; pvData
0x18003b015  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x18003b01a  mov     rcx, r13; hkey
0x18003b01d  mov     [rsp+2B0h+pdwType], 0; pdwType
0x18003b026  call    cs:__imp_RegGetValueW
0x18003b02c  cmp     [rsp+2B0h+Data], ebx
0x18003b030  jnz     short loc_18003B03C
0x18003b032  cmp     [rsp+2B0h+var_26C], ebx
0x18003b036  jz      loc_18003B1D3
0x18003b03c  mov     ecx, 12h; unsigned int
0x18003b041  call    ?AmiUtilitySetPrivilege@@YAKKE@Z; AmiUtilitySetPrivilege(ulong,uchar)
0x18003b046  mov     r9d, eax
0x18003b049  test    eax, eax
0x18003b04b  jz      short loc_18003B07C
0x18003b04d  mov     ecx, 326h
0x18003b052  mov     edx, 522h
0x18003b057  cmp     r9d, edx
0x18003b05a  mov     eax, edx
0x18003b05c  cmovnz  eax, r9d
0x18003b060  lea     r9, aAmiutilitysetp; "AmiUtilitySetPrivilege(SE_RESTORE_PRIVI"...
0x18003b067  lea     r8d, [rcx-4]
0x18003b06b  cmovz   r8d, ecx
0x18003b06f  mov     ecx, 3
0x18003b074  cmovz   ebx, ecx
0x18003b077  jmp     loc_18003B1E5
0x18003b07c  mov     ecx, 11h; unsigned int
0x18003b081  call    ?AmiUtilitySetPrivilege@@YAKKE@Z; AmiUtilitySetPrivilege(ulong,uchar)
0x18003b086  mov     r9d, eax
0x18003b089  test    eax, eax
0x18003b08b  jz      short loc_18003B0BC
0x18003b08d  mov     ecx, 332h
0x18003b092  mov     edx, 522h
0x18003b097  cmp     r9d, edx
0x18003b09a  mov     eax, edx
0x18003b09c  cmovnz  eax, r9d
0x18003b0a0  lea     r9, aAmiutilitysetp_0; "AmiUtilitySetPrivilege(SE_BACKUP_PRIVIL"...
0x18003b0a7  lea     r8d, [rcx-4]
0x18003b0ab  cmovz   r8d, ecx
0x18003b0af  mov     ecx, 3
0x18003b0b4  cmovz   ebx, ecx
0x18003b0b7  jmp     loc_18003B1E5
0x18003b0bc  mov     r8, rsi; lpFile
0x18003b0bf  lea     rdx, a11517b7cE79d4e; "{11517B7C-E79D-4e20-961B-75A811715ADD}"
0x18003b0c6  mov     rcx, r13; hKey
0x18003b0c9  call    cs:__imp_RegLoadKeyW
0x18003b0cf  test    eax, eax
0x18003b0d1  jz      short loc_18003B0EA
0x18003b0d3  lea     r9, aRegloadkeyFail; "RegLoadKey failed [%d]"
0x18003b0da  mov     r8d, 33Fh
0x18003b0e0  mov     ecx, 3
0x18003b0e5  jmp     loc_18003B1E7
0x18003b0ea  lea     rax, [rsp+2B0h+phkResult]
0x18003b0ef  mov     r9d, 0F003Fh; samDesired
0x18003b0f5  xor     r8d, r8d; ulOptions
0x18003b0f8  mov     [rsp+2B0h+pdwType], rax; phkResult
0x18003b0fd  lea     rdx, a11517b7cE79d4e; "{11517B7C-E79D-4e20-961B-75A811715ADD}"
0x18003b104  mov     rcx, r13; hKey
0x18003b107  mov     r14b, bl
0x18003b10a  call    cs:__imp_RegOpenKeyExW
0x18003b110  test    eax, eax
0x18003b112  jz      short loc_18003B126
0x18003b114  lea     r9, aRegopenkeyexFa; "RegOpenKeyEx failed [%d]"
0x18003b11b  mov     r8d, 34Ah
0x18003b121  jmp     loc_18003B1E5
0x18003b126  mov     rcx, [rsp+2B0h+phkResult]; HKEY
0x18003b12b  call    ?AmiFixKeyPermissionsRecursive@@YAKPEAUHKEY__@@@Z; AmiFixKeyPermissionsRecursive(HKEY__ *)
0x18003b130  test    eax, eax
0x18003b132  jnz     loc_18003B1D8
0x18003b138  lea     r9, aAmifixkeypermi_3; "AmiFixKeyPermissionsRecursive succeeded"...
0x18003b13f  mov     r8d, 351h
0x18003b145  lea     rdx, aAmipverifycach; "AmipVerifyCachePermissionsCorrect"
0x18003b14c  lea     ecx, [rax+3]
0x18003b14f  call    AslLogCallPrintf
0x18003b154  mov     esi, 4
0x18003b159  mov     [rsp+2B0h+Data], ebx
0x18003b15d  lea     rax, [rsp+2B0h+Data]
0x18003b162  mov     dword ptr [rsp+2B0h+pvData], esi; cbData
0x18003b166  mov     r9d, esi; dwType
0x18003b169  mov     [rsp+2B0h+pdwType], rax; lpData
0x18003b16e  lea     r8, aAmihivepermiss; "AmiHivePermissionsCorrect"
0x18003b175  mov     rcx, r13; hKey
0x18003b178  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x18003b17d  call    cs:__imp_RegSetKeyValueW
0x18003b183  test    eax, eax
0x18003b185  jz      short loc_18003B196
0x18003b187  lea     r9, aRegsetkeyvalue; "RegSetKeyValue failed [%d]"
0x18003b18e  mov     r8d, 35Fh
0x18003b194  jmp     short loc_18003B1E5
0x18003b196  lea     rax, [rsp+2B0h+var_26C]
0x18003b19b  mov     dword ptr [rsp+2B0h+pvData], esi; cbData
0x18003b19f  mov     r9d, esi; dwType
0x18003b1a2  mov     [rsp+2B0h+pdwType], rax; lpData
0x18003b1a7  lea     r8, aAmihiveownerco; "AmiHiveOwnerCorrect"
0x18003b1ae  mov     [rsp+2B0h+var_26C], ebx
0x18003b1b2  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x18003b1b7  mov     rcx, r13; hKey
0x18003b1ba  call    cs:__imp_RegSetKeyValueW
0x18003b1c0  test    eax, eax
0x18003b1c2  jz      short loc_18003B1D3
0x18003b1c4  lea     r9, aRegsetkeyvalue; "RegSetKeyValue failed [%d]"
0x18003b1cb  mov     r8d, 36Bh
0x18003b1d1  jmp     short loc_18003B1E5
0x18003b1d3  mov     dil, bl
0x18003b1d6  jmp     short loc_18003B1F7
0x18003b1d8  lea     r9, aAmifixkeypermi; "AmiFixKeyPermissionsRecursive failed [%"...
0x18003b1df  mov     r8d, 373h
0x18003b1e5  mov     ecx, ebx
0x18003b1e7  lea     rdx, aAmipverifycach; "AmipVerifyCachePermissionsCorrect"
0x18003b1ee  mov     dword ptr [rsp+2B0h+pdwType], eax
0x18003b1f2  call    AslLogCallPrintf
0x18003b1f7  mov     rcx, [rsp+2B0h+phkResult]; hKey
0x18003b1fc  test    rcx, rcx
0x18003b1ff  jz      short loc_18003B210
0x18003b201  call    cs:__imp_RegCloseKey
0x18003b207  mov     [rsp+2B0h+phkResult], 0
0x18003b210  test    r14b, r14b
0x18003b213  jz      short loc_18003B225
0x18003b215  lea     rdx, a11517b7cE79d4e; "{11517B7C-E79D-4e20-961B-75A811715ADD}"
0x18003b21c  mov     rcx, r13; hKey
0x18003b21f  call    cs:__imp_RegUnLoadKeyW
0x18003b225  mov     al, dil
0x18003b228  mov     rcx, [rbp+1B0h+var_40]
0x18003b22f  xor     rcx, rsp; StackCookie
0x18003b232  call    __security_check_cookie
0x18003b237  add     rsp, 288h
0x18003b23e  pop     r14
0x18003b240  pop     r13
0x18003b242  pop     rdi
0x18003b243  pop     rsi
0x18003b244  pop     rbx
0x18003b245  pop     rbp
0x18003b246  retn
```
