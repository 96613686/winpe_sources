# AmiProviderInit

- ea: `0x18003a1e4`
- end: `0x18003a5a0`
- name: `AmiProviderInit`
- size: `956`
- prototype: `__int64 __fastcall(HKEY **, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180029000`

## callees

- `0x180005890`
- `0x180006938`
- `0x18000cb74`
- `0x1800295dc`
- `0x180039f04`
- `0x18003a1e4`
- `0x18003b2c4`
- `0x18003b5e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18003a34b`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18003a34b`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18003a345`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x18003a345`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003a33d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18003a33d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003a3cf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003a3cf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003a46e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003a46e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a4bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a4bc`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18003a504`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18003a518`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18003a504`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18003a518`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18003a4cb`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18003a4cb`

## string_xrefs

- `0x18003a297`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x18003a29e`: `AppCompatFlags`
- `0x18003a26b`: `Failed to get store full path [%d]`
- `0x18003a2fd`: `Failed to initialize store [%d] - Attempting to reset cache permissions`
- `0x18003a3b8`: `WritePermissionsCheck`
- `0x18003a489`: `Failed to create test key under provider: %ws [%d]`
- `0x18003a412`: `Failed to write to provider: %ws [%d]`
- `0x18003a4d9`: `Failed to delete test key under provider: %ws [%d]`
- `0x18003a545`: `Failed to update store permissions [%d]`
- `0x18003a557`: `Updated store permissions`
- `0x18003a3e0`: `RegSetValueEx failed [%d]`
- `0x18003a3f1`: `AmiUtilityRegSetValue`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall AmiProviderInit(HKEY **a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  unsigned int v6; // ebx
  int StoreFullPath; // eax
  __int64 v8; // r8
  const char *v9; // r9
  __int64 v10; // rcx
  DWORD TickCount; // eax
  int v12; // eax
  HKEY *v13; // r14
  int v14; // ebx
  char v15; // r12
  LSTATUS v16; // eax
  __int64 v17; // rcx
  __int64 v18; // r8
  LSTATUS v19; // eax
  int v20; // edx
  __int64 v21; // r8
  __int64 v22; // rcx
  LSTATUS v23; // eax
  unsigned int v24; // eax
  BYTE *lpData; // [rsp+20h] [rbp-E0h]
  BYTE *lpDataa; // [rsp+20h] [rbp-E0h]
  __int64 cbData; // [rsp+28h] [rbp-D8h]
  __int64 cbDataa; // [rsp+28h] [rbp-D8h]
  void *v30; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[40]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v34[264]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v35[264]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v30 = 0;
  memset_0(v34, 0, 0x20Au);
  hKey = 0;
  if ( a1 )
  {
    if ( !a2 )
    {
      StoreFullPath = AmiRegGetStoreFullPath(v35);
      v6 = StoreFullPath;
      if ( StoreFullPath )
      {
        v8 = 67;
        v9 = "Failed to get store full path [%d]";
        v10 = 1;
LABEL_6:
        LODWORD(lpData) = StoreFullPath;
LABEL_7:
        AslLogCallPrintf(v10, "AmiProviderInit", v8, v9, lpData);
        return v6;
      }
      a2 = v35;
    }
    StoreFullPath = AmiUtilityGetPersistedLocation(
                      (unsigned int)v34,
                      261,
                      (unsigned int)L"AppCompatFlags",
                      (unsigned int)L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
                      1);
    if ( StoreFullPath < 0 )
    {
      v6 = 1287;
      v9 = "AmiUtilityGetPersistedLocation [%#x]";
      v8 = 83;
      v10 = 1;
      goto LABEL_6;
    }
    v6 = AmiStoreInitialize(&v30, a2, a3);
    if ( v6 == 5 )
      return v6;
    if ( v6 == 1009 )
    {
      AslLogCallPrintf(
        3,
        "AmiProviderInit",
        100,
        "Failed to initialize store [%d] - Attempting to reset cache permissions",
        1009);
      goto LABEL_41;
    }
    if ( v6 )
    {
      v8 = 105;
      LODWORD(lpData) = v6;
      v9 = "Failed to initialize store [%d]";
      v10 = 3;
      goto LABEL_7;
    }
    *(_DWORD *)Data = 1;
    TickCount = GetTickCount();
    _o_srand(TickCount);
    LODWORD(lpData) = rand();
    v12 = StringCchPrintfW(SubKey, 0x28u, L"%ls%i", L"PermissionsCheckTestKey", lpData);
    if ( v12 < 0 )
      AslLogCallPrintf(1, "AmiProviderInit", 128, "StringCchPrintfW [%#x]", v12);
    v13 = (HKEY *)v30;
    if ( v30 )
    {
      v15 = 0;
      v16 = RegSetValueExW(*((HKEY *)v30 + 1), L"WritePermissionsCheck", 0, 4u, Data, 4u);
      v14 = v16;
      if ( !v16 )
        goto LABEL_29;
      if ( v16 != 5 )
        AslLogCallPrintf(1, "AmiUtilityRegSetValue", 638, "RegSetValueEx failed [%d]", v16);
    }
    else
    {
      v14 = 87;
    }
    LODWORD(cbData) = v14;
    v17 = 1;
    if ( v14 == 5 )
      v17 = 3;
    v18 = 142;
    if ( v14 == 5 )
      v18 = 146;
    AslLogCallPrintf(v17, "AmiProviderInit", v18, "Failed to write to provider: %ws [%d]", a3, cbData);
    v15 = 1;
LABEL_29:
    v19 = RegCreateKeyExW(v13[1], SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    if ( v19 )
    {
      v20 = 5;
      if ( v19 != 5 )
        v20 = v19;
      v21 = 162;
      LODWORD(cbDataa) = v20;
      if ( v19 == 5 )
        v21 = 166;
      v22 = 3;
      if ( v19 == 5 )
        v22 = 1;
      AslLogCallPrintf(v22, "AmiProviderInit", v21, "Failed to create test key under provider: %ws [%d]", a3, cbDataa);
    }
    else
    {
      RegCloseKey(hKey);
      v23 = RegDeleteKeyW(v13[1], SubKey);
      if ( v23 )
      {
        LODWORD(cbDataa) = v23;
        AslLogCallPrintf(1, "AmiProviderInit", 183, "Failed to delete test key under provider: %ws [%d]", a3, cbDataa);
      }
      else if ( !v15 )
      {
        goto LABEL_44;
      }
    }
LABEL_41:
    RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, v34, L"AmiHivePermissionsCorrect");
    RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, v34, L"AmiHiveOwnerCorrect");
    v24 = AmiStoreInitialize(&v30, v35, a3);
    v6 = v24;
    if ( v24 )
    {
      LODWORD(lpDataa) = v24;
      AslLogCallPrintf(3, "AmiProviderInit", 207, "Failed to update store permissions [%d]", lpDataa);
      return v6;
    }
    AslLogCallPrintf(3, "AmiProviderInit", 211, "Updated store permissions");
    v13 = (HKEY *)v30;
LABEL_44:
    *a1 = v13;
    return 0;
  }
  return 87;
}

```

## disassembly

```asm
0x18003a1e4  mov     [rsp-8+arg_18], rbx
0x18003a1e9  push    rbp
0x18003a1ea  push    rsi
0x18003a1eb  push    rdi
0x18003a1ec  push    r12
0x18003a1ee  push    r13
0x18003a1f0  push    r14
0x18003a1f2  push    r15
0x18003a1f4  lea     rbp, [rsp-3F0h]
0x18003a1fc  sub     rsp, 4F0h
0x18003a203  mov     rax, cs:__security_cookie
0x18003a20a  xor     rax, rsp
0x18003a20d  mov     [rbp+420h+var_40], rax
0x18003a214  mov     r15, r8
0x18003a217  mov     [rsp+520h+var_4D0], 0
0x18003a220  mov     rbx, rdx
0x18003a223  mov     r13, rcx
0x18003a226  xor     edx, edx; Val
0x18003a228  lea     rcx, [rbp+420h+var_460]; void *
0x18003a22c  mov     r8d, 20Ah; Size
0x18003a232  call    memset_0
0x18003a237  mov     [rsp+520h+hKey], 0
0x18003a240  test    r13, r13
0x18003a243  jnz     short loc_18003A24E
0x18003a245  lea     ebx, [r13+57h]
0x18003a249  jmp     loc_18003A574
0x18003a24e  test    rbx, rbx
0x18003a251  jnz     short loc_18003A292
0x18003a253  lea     rcx, [rbp+420h+var_250]; unsigned __int16 *
0x18003a25a  call    AmiRegGetStoreFullPath
0x18003a25f  mov     ebx, eax
0x18003a261  test    eax, eax
0x18003a263  jz      short loc_18003A28B
0x18003a265  mov     r8d, 43h ; 'C'
0x18003a26b  lea     r9, aFailedToGetSto; "Failed to get store full path [%d]"
0x18003a272  lea     ecx, [r8-42h]
0x18003a276  mov     dword ptr [rsp+520h+lpData], eax
0x18003a27a  lea     rdx, aAmiproviderini; "AmiProviderInit"
0x18003a281  call    AslLogCallPrintf
0x18003a286  jmp     loc_18003A574
0x18003a28b  lea     rbx, [rbp+420h+var_250]
0x18003a292  mov     edi, 1
0x18003a297  lea     r9, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003a29e  lea     r8, aAppcompatflags; "AppCompatFlags"
0x18003a2a5  mov     dword ptr [rsp+520h+lpData], edi
0x18003a2a9  mov     edx, 105h
0x18003a2ae  lea     rcx, [rbp+420h+var_460]
0x18003a2b2  call    AmiUtilityGetPersistedLocation
0x18003a2b7  test    eax, eax
0x18003a2b9  jns     short loc_18003A2CF
0x18003a2bb  mov     ebx, 507h
0x18003a2c0  lea     r9, aAmiutilitygetp; "AmiUtilityGetPersistedLocation [%#x]"
0x18003a2c7  lea     r8d, [rdi+52h]
0x18003a2cb  mov     ecx, edi
0x18003a2cd  jmp     short loc_18003A276
0x18003a2cf  mov     r8, r15; unsigned __int16 *
0x18003a2d2  lea     rcx, [rsp+520h+var_4D0]; void **
0x18003a2d7  mov     rdx, rbx; unsigned __int16 *
0x18003a2da  call    AmiStoreInitialize
0x18003a2df  mov     ebx, eax
0x18003a2e1  cmp     eax, 5
0x18003a2e4  jz      loc_18003A574
0x18003a2ea  mov     eax, 3F1h
0x18003a2ef  cmp     ebx, eax
0x18003a2f1  jnz     short loc_18003A31B
0x18003a2f3  mov     r8d, 64h ; 'd'
0x18003a2f9  mov     dword ptr [rsp+520h+lpData], eax
0x18003a2fd  lea     r9, aFailedToInitia_1; "Failed to initialize store [%d] - Attem"...
0x18003a304  lea     rdx, aAmiproviderini; "AmiProviderInit"
0x18003a30b  lea     esi, [r8-61h]
0x18003a30f  mov     ecx, esi
0x18003a311  call    AslLogCallPrintf
0x18003a316  jmp     loc_18003A4EF
0x18003a31b  test    ebx, ebx
0x18003a31d  jz      short loc_18003A339
0x18003a31f  mov     r8d, 69h ; 'i'
0x18003a325  mov     dword ptr [rsp+520h+lpData], ebx
0x18003a329  lea     r9, aFailedToInitia_2; "Failed to initialize store [%d]"
0x18003a330  lea     ecx, [r8-66h]
0x18003a334  jmp     loc_18003A27A
0x18003a339  mov     dword ptr [rsp+520h+Data], edi
0x18003a33d  call    cs:__imp_GetTickCount
0x18003a343  mov     ecx, eax
0x18003a345  call    cs:__imp__o_srand
0x18003a34b  call    cs:__imp_rand
0x18003a351  lea     r9, aPermissionsche; "PermissionsCheckTestKey"
0x18003a358  mov     edx, 28h ; '('; unsigned __int64
0x18003a35d  lea     r8, aLsI; "%ls%i"
0x18003a364  mov     dword ptr [rsp+520h+lpData], eax
0x18003a368  lea     rcx, [rsp+520h+SubKey]; unsigned __int16 *
0x18003a36d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003a372  test    eax, eax
0x18003a374  jns     short loc_18003A395
0x18003a376  lea     r9, aStringcchprint_2; "StringCchPrintfW [%#x]"
0x18003a37d  mov     dword ptr [rsp+520h+lpData], eax
0x18003a381  mov     r8d, 80h
0x18003a387  lea     rdx, aAmiproviderini; "AmiProviderInit"
0x18003a38e  mov     ecx, edi
0x18003a390  call    AslLogCallPrintf
0x18003a395  mov     r14, [rsp+520h+var_4D0]
0x18003a39a  mov     esi, 3
0x18003a39f  test    r14, r14
0x18003a3a2  jnz     short loc_18003A3A9
0x18003a3a4  lea     ebx, [rsi+54h]
0x18003a3a7  jmp     short loc_18003A3FF
0x18003a3a9  mov     rcx, [r14+8]; hKey
0x18003a3ad  lea     rax, [rsp+520h+Data]
0x18003a3b2  mov     r9d, 4; dwType
0x18003a3b8  lea     rdx, aWritepermissio; "WritePermissionsCheck"
0x18003a3bf  mov     dword ptr [rsp+520h+cbData], r9d; cbData
0x18003a3c4  xor     r8d, r8d; Reserved
0x18003a3c7  mov     [rsp+520h+lpData], rax; lpData
0x18003a3cc  xor     r12b, r12b
0x18003a3cf  call    cs:__imp_RegSetValueExW
0x18003a3d5  mov     ebx, eax
0x18003a3d7  test    eax, eax
0x18003a3d9  jz      short loc_18003A433
0x18003a3db  cmp     eax, 5
0x18003a3de  jz      short loc_18003A3FF
0x18003a3e0  lea     r9, aRegsetvalueexF; "RegSetValueEx failed [%d]"
0x18003a3e7  mov     dword ptr [rsp+520h+lpData], eax
0x18003a3eb  mov     r8d, 27Eh
0x18003a3f1  lea     rdx, aAmiutilityregs; "AmiUtilityRegSetValue"
0x18003a3f8  mov     ecx, edi
0x18003a3fa  call    AslLogCallPrintf
0x18003a3ff  mov     eax, 92h
0x18003a404  mov     dword ptr [rsp+520h+cbData], ebx
0x18003a408  cmp     ebx, 5
0x18003a40b  mov     [rsp+520h+lpData], r15
0x18003a410  mov     ecx, edi
0x18003a412  lea     r9, aFailedToWriteT; "Failed to write to provider: %ws [%d]"
0x18003a419  cmovz   ecx, esi
0x18003a41c  lea     rdx, aAmiproviderini; "AmiProviderInit"
0x18003a423  lea     r8d, [rax-4]
0x18003a427  cmovz   r8d, eax
0x18003a42b  call    AslLogCallPrintf
0x18003a430  mov     r12b, dil
0x18003a433  mov     rcx, [r14+8]; hKey
0x18003a437  lea     rax, [rsp+520h+hKey]
0x18003a43c  mov     [rsp+520h+lpdwDisposition], 0; lpdwDisposition
0x18003a445  lea     rdx, [rsp+520h+SubKey]; lpSubKey
0x18003a44a  mov     [rsp+520h+phkResult], rax; phkResult
0x18003a44f  xor     r9d, r9d; lpClass
0x18003a452  mov     [rsp+520h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003a45b  xor     r8d, r8d; Reserved
0x18003a45e  mov     dword ptr [rsp+520h+cbData], 0F003Fh; samDesired
0x18003a466  mov     dword ptr [rsp+520h+lpData], 0; dwOptions
0x18003a46e  call    cs:__imp_RegCreateKeyExW
0x18003a474  test    eax, eax
0x18003a476  jz      short loc_18003A4B7
0x18003a478  mov     ecx, 0A6h
0x18003a47d  mov     r9d, 5
0x18003a483  cmp     eax, r9d
0x18003a486  mov     edx, r9d
0x18003a489  lea     r9, aFailedToCreate; "Failed to create test key under provide"...
0x18003a490  cmovnz  edx, eax
0x18003a493  lea     r8d, [rcx-4]
0x18003a497  mov     dword ptr [rsp+520h+cbData], edx
0x18003a49b  cmovz   r8d, ecx
0x18003a49f  mov     ecx, esi
0x18003a4a1  cmovz   ecx, edi
0x18003a4a4  lea     rdx, aAmiproviderini; "AmiProviderInit"
0x18003a4ab  mov     [rsp+520h+lpData], r15
0x18003a4b0  call    AslLogCallPrintf
0x18003a4b5  jmp     short loc_18003A4EF
0x18003a4b7  mov     rcx, [rsp+520h+hKey]; hKey
0x18003a4bc  call    cs:__imp_RegCloseKey
0x18003a4c2  mov     rcx, [r14+8]; hKey
0x18003a4c6  lea     rdx, [rsp+520h+SubKey]; lpSubKey
0x18003a4cb  call    cs:__imp_RegDeleteKeyW
0x18003a4d1  test    eax, eax
0x18003a4d3  jz      short loc_18003A4EA
0x18003a4d5  mov     dword ptr [rsp+520h+cbData], eax
0x18003a4d9  lea     r9, aFailedToDelete; "Failed to delete test key under provide"...
0x18003a4e0  mov     r8d, 0B7h
0x18003a4e6  mov     ecx, edi
0x18003a4e8  jmp     short loc_18003A4A4
0x18003a4ea  test    r12b, r12b
0x18003a4ed  jz      short loc_18003A56E
0x18003a4ef  mov     rbx, 0FFFFFFFF80000002h
0x18003a4f6  lea     r8, aAmihivepermiss; "AmiHivePermissionsCorrect"
0x18003a4fd  mov     rcx, rbx; hKey
0x18003a500  lea     rdx, [rbp+420h+var_460]; lpSubKey
0x18003a504  call    cs:__imp_RegDeleteKeyValueW
0x18003a50a  lea     r8, aAmihiveownerco; "AmiHiveOwnerCorrect"
0x18003a511  mov     rcx, rbx; hKey
0x18003a514  lea     rdx, [rbp+420h+var_460]; lpSubKey
0x18003a518  call    cs:__imp_RegDeleteKeyValueW
0x18003a51e  mov     r8, r15; unsigned __int16 *
0x18003a521  lea     rdx, [rbp+420h+var_250]; unsigned __int16 *
0x18003a528  lea     rcx, [rsp+520h+var_4D0]; void **
0x18003a52d  call    AmiStoreInitialize
0x18003a532  lea     rdx, aAmiproviderini; "AmiProviderInit"
0x18003a539  mov     ebx, eax
0x18003a53b  mov     ecx, esi
0x18003a53d  test    eax, eax
0x18003a53f  jz      short loc_18003A557
0x18003a541  mov     dword ptr [rsp+520h+lpData], eax
0x18003a545  lea     r9, aFailedToUpdate; "Failed to update store permissions [%d]"
0x18003a54c  mov     r8d, 0CFh
0x18003a552  jmp     loc_18003A281
0x18003a557  lea     r9, aUpdatedStorePe; "Updated store permissions"
0x18003a55e  mov     r8d, 0D3h
0x18003a564  call    AslLogCallPrintf
0x18003a569  mov     r14, [rsp+520h+var_4D0]
0x18003a56e  mov     [r13+0], r14
0x18003a572  xor     ebx, ebx
0x18003a574  mov     eax, ebx
0x18003a576  mov     rcx, [rbp+420h+var_40]
0x18003a57d  xor     rcx, rsp; StackCookie
0x18003a580  call    __security_check_cookie
0x18003a585  mov     rbx, [rsp+520h+arg_18]
0x18003a58d  add     rsp, 4F0h
0x18003a594  pop     r15
0x18003a596  pop     r14
0x18003a598  pop     r13
0x18003a59a  pop     r12
0x18003a59c  pop     rdi
0x18003a59d  pop     rsi
0x18003a59e  pop     rbp
0x18003a59f  retn
```
