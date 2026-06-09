# AmipVerifyCachePermissionsCorrect(ushort const *)

- ea: `0x140019fa0`
- end: `0x14001a2eb`
- name: `?AmipVerifyCachePermissionsCorrect@@YA_NPEBG@Z`
- size: `843`
- prototype: `char __fastcall(LPCWSTR lpFile)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14001a914`

## callees

- `0x140001ba0`
- `0x1400026c0`
- `0x1400151b0`
- `0x140018c3c`
- `0x140019610`
- `0x140019fa0`
- `0x14001ac30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a2a5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14001a2a5`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x14001a2c3`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x14001a2c3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001a08a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001a0ca`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001a08a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001a0ca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001a1ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001a1ae`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x14001a16d`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x14001a16d`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14001a221`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14001a25e`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14001a221`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x14001a25e`

## string_xrefs

- `0x14001a00f`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x14001a01a`: `AppCompatFlags`
- `0x14001a22b`: `RegSetKeyValue failed [%d]`
- `0x14001a268`: `RegSetKeyValue failed [%d]`
- `0x14001a104`: `AmiUtilitySetPrivilege(SE_RESTORE_PRIVILEGE) failed [%d]`
- `0x14001a1e9`: `AmipVerifyCachePermissionsCorrect`
- `0x14001a28b`: `AmipVerifyCachePermissionsCorrect`
- `0x14001a144`: `AmiUtilitySetPrivilege(SE_BACKUP_PRIVILEGE) failed [%d]`
- `0x14001a1b8`: `RegOpenKeyEx failed [%d]`

## pseudocode

```c
char __fastcall AmipVerifyCachePermissionsCorrect(LPCWSTR lpFile)
{
  char v2; // di
  unsigned int v3; // ebx
  char v4; // r14
  int PersistedLocation; // eax
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
0x140019fa0  push    rbp
0x140019fa2  push    rbx
0x140019fa3  push    rsi
0x140019fa4  push    rdi
0x140019fa5  push    r13
0x140019fa7  push    r14
0x140019fa9  lea     rbp, [rsp-188h]
0x140019fb1  sub     rsp, 288h
0x140019fb8  mov     rax, cs:__security_cookie
0x140019fbf  xor     rax, rsp
0x140019fc2  mov     [rbp+1B0h+var_40], rax
0x140019fc9  mov     rsi, rcx
0x140019fcc  mov     [rsp+2B0h+Data], 0
0x140019fd4  lea     rcx, [rsp+2B0h+SubKey]; void *
0x140019fd9  mov     [rsp+2B0h+var_268], 0
0x140019fe1  xor     edx, edx; Val
0x140019fe3  mov     [rsp+2B0h+var_26C], 0
0x140019feb  mov     r8d, 20Ah; Size
0x140019ff1  mov     [rsp+2B0h+var_264], 0
0x140019ff9  xor     dil, dil
0x140019ffc  call    memset_0
0x14001a001  mov     ebx, 1
0x14001a006  mov     [rsp+2B0h+phkResult], 0
0x14001a00f  lea     r9, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x14001a016  mov     dword ptr [rsp+2B0h+pdwType], ebx
0x14001a01a  lea     r8, aAppcompatflags; "AppCompatFlags"
0x14001a021  mov     edx, 105h
0x14001a026  lea     rcx, [rsp+2B0h+SubKey]
0x14001a02b  xor     r14b, r14b
0x14001a02e  call    AmiUtilityGetPersistedLocation
0x14001a033  mov     r13, 0FFFFFFFF80000002h
0x14001a03a  test    eax, eax
0x14001a03c  jns     short loc_14001A050
0x14001a03e  lea     r9, aAmiutilitygetp; "AmiUtilityGetPersistedLocation [%#x]"
0x14001a045  mov     r8d, 2FBh
0x14001a04b  jmp     loc_14001A289
0x14001a050  lea     rax, [rsp+2B0h+var_268]
0x14001a055  mov     [rsp+2B0h+var_268], 4
0x14001a05d  mov     [rsp+2B0h+pcbData], rax; pcbData
0x14001a062  lea     r8, aAmihivepermiss; "AmiHivePermissionsCorrect"
0x14001a069  lea     rax, [rsp+2B0h+Data]
0x14001a06e  mov     r9d, 20000018h; dwFlags
0x14001a074  mov     [rsp+2B0h+pvData], rax; pvData
0x14001a079  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x14001a07e  mov     rcx, r13; hkey
0x14001a081  mov     [rsp+2B0h+pdwType], 0; pdwType
0x14001a08a  call    cs:__imp_RegGetValueW
0x14001a090  lea     rax, [rsp+2B0h+var_264]
0x14001a095  mov     [rsp+2B0h+var_264], 4
0x14001a09d  mov     [rsp+2B0h+pcbData], rax; pcbData
0x14001a0a2  lea     r8, aAmihiveownerco; "AmiHiveOwnerCorrect"
0x14001a0a9  lea     rax, [rsp+2B0h+var_26C]
0x14001a0ae  mov     r9d, 20000018h; dwFlags
0x14001a0b4  mov     [rsp+2B0h+pvData], rax; pvData
0x14001a0b9  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x14001a0be  mov     rcx, r13; hkey
0x14001a0c1  mov     [rsp+2B0h+pdwType], 0; pdwType
0x14001a0ca  call    cs:__imp_RegGetValueW
0x14001a0d0  cmp     [rsp+2B0h+Data], ebx
0x14001a0d4  jnz     short loc_14001A0E0
0x14001a0d6  cmp     [rsp+2B0h+var_26C], ebx
0x14001a0da  jz      loc_14001A277
0x14001a0e0  mov     ecx, 12h; unsigned int
0x14001a0e5  call    ?AmiUtilitySetPrivilege@@YAKKE@Z; AmiUtilitySetPrivilege(ulong,uchar)
0x14001a0ea  mov     r9d, eax
0x14001a0ed  test    eax, eax
0x14001a0ef  jz      short loc_14001A120
0x14001a0f1  mov     ecx, 326h
0x14001a0f6  mov     edx, 522h
0x14001a0fb  cmp     r9d, edx
0x14001a0fe  mov     eax, edx
0x14001a100  cmovnz  eax, r9d
0x14001a104  lea     r9, aAmiutilitysetp; "AmiUtilitySetPrivilege(SE_RESTORE_PRIVI"...
0x14001a10b  lea     r8d, [rcx-4]
0x14001a10f  cmovz   r8d, ecx
0x14001a113  mov     ecx, 3
0x14001a118  cmovz   ebx, ecx
0x14001a11b  jmp     loc_14001A289
0x14001a120  mov     ecx, 11h; unsigned int
0x14001a125  call    ?AmiUtilitySetPrivilege@@YAKKE@Z; AmiUtilitySetPrivilege(ulong,uchar)
0x14001a12a  mov     r9d, eax
0x14001a12d  test    eax, eax
0x14001a12f  jz      short loc_14001A160
0x14001a131  mov     ecx, 332h
0x14001a136  mov     edx, 522h
0x14001a13b  cmp     r9d, edx
0x14001a13e  mov     eax, edx
0x14001a140  cmovnz  eax, r9d
0x14001a144  lea     r9, aAmiutilitysetp_0; "AmiUtilitySetPrivilege(SE_BACKUP_PRIVIL"...
0x14001a14b  lea     r8d, [rcx-4]
0x14001a14f  cmovz   r8d, ecx
0x14001a153  mov     ecx, 3
0x14001a158  cmovz   ebx, ecx
0x14001a15b  jmp     loc_14001A289
0x14001a160  mov     r8, rsi; lpFile
0x14001a163  lea     rdx, a11517b7cE79d4e; "{11517B7C-E79D-4e20-961B-75A811715ADD}"
0x14001a16a  mov     rcx, r13; hKey
0x14001a16d  call    cs:__imp_RegLoadKeyW
0x14001a173  test    eax, eax
0x14001a175  jz      short loc_14001A18E
0x14001a177  lea     r9, aRegloadkeyFail; "RegLoadKey failed [%d]"
0x14001a17e  mov     r8d, 33Fh
0x14001a184  mov     ecx, 3
0x14001a189  jmp     loc_14001A28B
0x14001a18e  lea     rax, [rsp+2B0h+phkResult]
0x14001a193  mov     r9d, 0F003Fh; samDesired
0x14001a199  xor     r8d, r8d; ulOptions
0x14001a19c  mov     [rsp+2B0h+pdwType], rax; phkResult
0x14001a1a1  lea     rdx, a11517b7cE79d4e; "{11517B7C-E79D-4e20-961B-75A811715ADD}"
0x14001a1a8  mov     rcx, r13; hKey
0x14001a1ab  mov     r14b, bl
0x14001a1ae  call    cs:__imp_RegOpenKeyExW
0x14001a1b4  test    eax, eax
0x14001a1b6  jz      short loc_14001A1CA
0x14001a1b8  lea     r9, aRegopenkeyexFa_0; "RegOpenKeyEx failed [%d]"
0x14001a1bf  mov     r8d, 34Ah
0x14001a1c5  jmp     loc_14001A289
0x14001a1ca  mov     rcx, [rsp+2B0h+phkResult]; HKEY
0x14001a1cf  call    ?AmiFixKeyPermissionsRecursive@@YAKPEAUHKEY__@@@Z; AmiFixKeyPermissionsRecursive(HKEY__ *)
0x14001a1d4  test    eax, eax
0x14001a1d6  jnz     loc_14001A27C
0x14001a1dc  lea     r9, aAmifixkeypermi_3; "AmiFixKeyPermissionsRecursive succeeded"...
0x14001a1e3  mov     r8d, 351h
0x14001a1e9  lea     rdx, aAmipverifycach; "AmipVerifyCachePermissionsCorrect"
0x14001a1f0  lea     ecx, [rax+3]
0x14001a1f3  call    AslLogCallPrintf
0x14001a1f8  mov     esi, 4
0x14001a1fd  mov     [rsp+2B0h+Data], ebx
0x14001a201  lea     rax, [rsp+2B0h+Data]
0x14001a206  mov     dword ptr [rsp+2B0h+pvData], esi; cbData
0x14001a20a  mov     r9d, esi; dwType
0x14001a20d  mov     [rsp+2B0h+pdwType], rax; lpData
0x14001a212  lea     r8, aAmihivepermiss; "AmiHivePermissionsCorrect"
0x14001a219  mov     rcx, r13; hKey
0x14001a21c  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x14001a221  call    cs:__imp_RegSetKeyValueW
0x14001a227  test    eax, eax
0x14001a229  jz      short loc_14001A23A
0x14001a22b  lea     r9, aRegsetkeyvalue; "RegSetKeyValue failed [%d]"
0x14001a232  mov     r8d, 35Fh
0x14001a238  jmp     short loc_14001A289
0x14001a23a  lea     rax, [rsp+2B0h+var_26C]
0x14001a23f  mov     dword ptr [rsp+2B0h+pvData], esi; cbData
0x14001a243  mov     r9d, esi; dwType
0x14001a246  mov     [rsp+2B0h+pdwType], rax; lpData
0x14001a24b  lea     r8, aAmihiveownerco; "AmiHiveOwnerCorrect"
0x14001a252  mov     [rsp+2B0h+var_26C], ebx
0x14001a256  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x14001a25b  mov     rcx, r13; hKey
0x14001a25e  call    cs:__imp_RegSetKeyValueW
0x14001a264  test    eax, eax
0x14001a266  jz      short loc_14001A277
0x14001a268  lea     r9, aRegsetkeyvalue; "RegSetKeyValue failed [%d]"
0x14001a26f  mov     r8d, 36Bh
0x14001a275  jmp     short loc_14001A289
0x14001a277  mov     dil, bl
0x14001a27a  jmp     short loc_14001A29B
0x14001a27c  lea     r9, aAmifixkeypermi; "AmiFixKeyPermissionsRecursive failed [%"...
0x14001a283  mov     r8d, 373h
0x14001a289  mov     ecx, ebx
0x14001a28b  lea     rdx, aAmipverifycach; "AmipVerifyCachePermissionsCorrect"
0x14001a292  mov     dword ptr [rsp+2B0h+pdwType], eax
0x14001a296  call    AslLogCallPrintf
0x14001a29b  mov     rcx, [rsp+2B0h+phkResult]; hKey
0x14001a2a0  test    rcx, rcx
0x14001a2a3  jz      short loc_14001A2B4
0x14001a2a5  call    cs:__imp_RegCloseKey
0x14001a2ab  mov     [rsp+2B0h+phkResult], 0
0x14001a2b4  test    r14b, r14b
0x14001a2b7  jz      short loc_14001A2C9
0x14001a2b9  lea     rdx, a11517b7cE79d4e; "{11517B7C-E79D-4e20-961B-75A811715ADD}"
0x14001a2c0  mov     rcx, r13; hKey
0x14001a2c3  call    cs:__imp_RegUnLoadKeyW
0x14001a2c9  mov     al, dil
0x14001a2cc  mov     rcx, [rbp+1B0h+var_40]
0x14001a2d3  xor     rcx, rsp; StackCookie
0x14001a2d6  call    __security_check_cookie
0x14001a2db  add     rsp, 288h
0x14001a2e2  pop     r14
0x14001a2e4  pop     r13
0x14001a2e6  pop     rdi
0x14001a2e7  pop     rsi
0x14001a2e8  pop     rbx
0x14001a2e9  pop     rbp
0x14001a2ea  retn
```
