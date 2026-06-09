# AmiProviderInit

- ea: `0x140019258`
- end: `0x140019609`
- name: `AmiProviderInit`
- size: `945`
- prototype: `__int64 __fastcall(HKEY **, __int64, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000f130`
- `0x1400105e0`
- `0x140010df0`

## callees

- `0x140001ba0`
- `0x1400026c0`
- `0x1400093e8`
- `0x1400151b0`
- `0x140018f70`
- `0x140019258`
- `0x14001a914`
- `0x14001ac30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x1400193b4`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x1400193b4`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x1400193ae`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x1400193ae`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140019525`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140019525`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400194d7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1400194d7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140019438`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140019438`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400193a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400193a6`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x14001956d`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140019581`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x14001956d`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x140019581`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x140019534`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x140019534`

## string_xrefs

- `0x1400192fc`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x140019303`: `AppCompatFlags`
- `0x1400192d7`: `Failed to get store full path [%d]`
- `0x140019366`: `Failed to initialize store [%d] - Attempting to reset cache permissions`
- `0x140019421`: `WritePermissionsCheck`
- `0x14001947b`: `Failed to write to provider: %ws [%d]`
- `0x140019542`: `Failed to delete test key under provider: %ws [%d]`
- `0x1400194f2`: `Failed to create test key under provider: %ws [%d]`
- `0x1400195c0`: `Updated store permissions`
- `0x1400195ae`: `Failed to update store permissions [%d]`
- `0x140019449`: `RegSetValueEx failed [%d]`
- `0x14001945a`: `AmiUtilityRegSetValue`

## pseudocode

```c
__int64 __fastcall AmiProviderInit(HKEY **a1, __int64 a2, unsigned __int16 *a3)
{
  unsigned int v5; // ebx
  int StoreFullPath; // eax
  __int64 v7; // r8
  const char *v8; // r9
  __int64 v9; // rcx
  DWORD TickCount; // eax
  int v11; // eax
  HKEY *v12; // r14
  int v13; // ebx
  char v14; // r12
  LSTATUS v15; // eax
  __int64 v16; // rcx
  __int64 v17; // r8
  LSTATUS v18; // eax
  int v19; // edx
  __int64 v20; // r8
  __int64 v21; // rcx
  LSTATUS v22; // eax
  unsigned int v23; // eax
  BYTE *lpData; // [rsp+20h] [rbp-E0h]
  BYTE *lpDataa; // [rsp+20h] [rbp-E0h]
  __int64 cbData; // [rsp+28h] [rbp-D8h]
  __int64 cbDataa; // [rsp+28h] [rbp-D8h]
  void *v29; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[40]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v33[264]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v34[264]; // [rsp+2D0h] [rbp+1D0h] BYREF

  v29 = 0;
  memset_0(v33, 0, 0x20Au);
  hKey = 0;
  if ( a1 )
  {
    StoreFullPath = AmiRegGetStoreFullPath(v34);
    v5 = StoreFullPath;
    if ( StoreFullPath )
    {
      v7 = 67;
      v8 = "Failed to get store full path [%d]";
      v9 = 1;
LABEL_5:
      LODWORD(lpData) = StoreFullPath;
LABEL_6:
      AslLogCallPrintf(v9, "AmiProviderInit", v7, v8, lpData);
      return v5;
    }
    StoreFullPath = AmiUtilityGetPersistedLocation(
                      (unsigned int)v33,
                      261,
                      (unsigned int)L"AppCompatFlags",
                      (unsigned int)L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
                      1);
    if ( StoreFullPath < 0 )
    {
      v5 = 1287;
      v8 = "AmiUtilityGetPersistedLocation [%#x]";
      v7 = 83;
      v9 = 1;
      goto LABEL_5;
    }
    v5 = AmiStoreInitialize(&v29, v34, a3);
    if ( v5 == 5 )
      return v5;
    if ( v5 == 1009 )
    {
      AslLogCallPrintf(
        3,
        "AmiProviderInit",
        100,
        "Failed to initialize store [%d] - Attempting to reset cache permissions",
        1009);
      goto LABEL_39;
    }
    if ( v5 )
    {
      v7 = 105;
      LODWORD(lpData) = v5;
      v8 = "Failed to initialize store [%d]";
      v9 = 3;
      goto LABEL_6;
    }
    *(_DWORD *)Data = 1;
    TickCount = GetTickCount();
    _o_srand(TickCount);
    LODWORD(lpData) = rand();
    v11 = StringCchPrintfW(SubKey, 0x28u, L"%ls%i", L"PermissionsCheckTestKey", lpData);
    if ( v11 < 0 )
      AslLogCallPrintf(1, "AmiProviderInit", 128, "StringCchPrintfW [%#x]", v11);
    v12 = (HKEY *)v29;
    if ( v29 )
    {
      v14 = 0;
      v15 = RegSetValueExW(*((HKEY *)v29 + 1), L"WritePermissionsCheck", 0, 4u, Data, 4u);
      v13 = v15;
      if ( !v15 )
        goto LABEL_27;
      if ( v15 != 5 )
        AslLogCallPrintf(1, "AmiUtilityRegSetValue", 638, "RegSetValueEx failed [%d]", v15);
    }
    else
    {
      v13 = 87;
    }
    LODWORD(cbData) = v13;
    v16 = 1;
    if ( v13 == 5 )
      v16 = 3;
    v17 = 142;
    if ( v13 == 5 )
      v17 = 146;
    AslLogCallPrintf(v16, "AmiProviderInit", v17, "Failed to write to provider: %ws [%d]", a3, cbData);
    v14 = 1;
LABEL_27:
    v18 = RegCreateKeyExW(v12[1], SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
    if ( v18 )
    {
      v19 = 5;
      if ( v18 != 5 )
        v19 = v18;
      v20 = 162;
      LODWORD(cbDataa) = v19;
      if ( v18 == 5 )
        v20 = 166;
      v21 = 3;
      if ( v18 == 5 )
        v21 = 1;
      AslLogCallPrintf(v21, "AmiProviderInit", v20, "Failed to create test key under provider: %ws [%d]", a3, cbDataa);
    }
    else
    {
      RegCloseKey(hKey);
      v22 = RegDeleteKeyW(v12[1], SubKey);
      if ( v22 )
      {
        LODWORD(cbDataa) = v22;
        AslLogCallPrintf(1, "AmiProviderInit", 183, "Failed to delete test key under provider: %ws [%d]", a3, cbDataa);
      }
      else if ( !v14 )
      {
        goto LABEL_42;
      }
    }
LABEL_39:
    RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, v33, L"AmiHivePermissionsCorrect");
    RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, v33, L"AmiHiveOwnerCorrect");
    v23 = AmiStoreInitialize(&v29, v34, a3);
    v5 = v23;
    if ( v23 )
    {
      LODWORD(lpDataa) = v23;
      AslLogCallPrintf(3, "AmiProviderInit", 207, "Failed to update store permissions [%d]", lpDataa);
      return v5;
    }
    AslLogCallPrintf(3, "AmiProviderInit", 211, "Updated store permissions");
    v12 = (HKEY *)v29;
LABEL_42:
    *a1 = v12;
    return 0;
  }
  return 87;
}

```

## disassembly

```asm
0x140019258  mov     [rsp-8+arg_8], rbx
0x14001925d  push    rbp
0x14001925e  push    rsi
0x14001925f  push    rdi
0x140019260  push    r12
0x140019262  push    r13
0x140019264  push    r14
0x140019266  push    r15
0x140019268  lea     rbp, [rsp-3F0h]
0x140019270  sub     rsp, 4F0h
0x140019277  mov     rax, cs:__security_cookie
0x14001927e  xor     rax, rsp
0x140019281  mov     [rbp+420h+var_40], rax
0x140019288  mov     r15, r8
0x14001928b  mov     [rsp+520h+var_4D0], 0
0x140019294  mov     r13, rcx
0x140019297  mov     r8d, 20Ah; Size
0x14001929d  lea     rcx, [rbp+420h+var_460]; void *
0x1400192a1  xor     edx, edx; Val
0x1400192a3  call    memset_0
0x1400192a8  mov     [rsp+520h+hKey], 0
0x1400192b1  test    r13, r13
0x1400192b4  jnz     short loc_1400192BF
0x1400192b6  lea     ebx, [r13+57h]
0x1400192ba  jmp     loc_1400195DD
0x1400192bf  lea     rcx, [rbp+420h+var_250]; void *
0x1400192c6  call    AmiRegGetStoreFullPath
0x1400192cb  mov     ebx, eax
0x1400192cd  test    eax, eax
0x1400192cf  jz      short loc_1400192F7
0x1400192d1  mov     r8d, 43h ; 'C'
0x1400192d7  lea     r9, aFailedToGetSto; "Failed to get store full path [%d]"
0x1400192de  lea     ecx, [r8-42h]
0x1400192e2  mov     dword ptr [rsp+520h+lpData], eax
0x1400192e6  lea     rdx, aAmiproviderini; "AmiProviderInit"
0x1400192ed  call    AslLogCallPrintf
0x1400192f2  jmp     loc_1400195DD
0x1400192f7  mov     edi, 1
0x1400192fc  lea     r9, SubKey; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140019303  lea     r8, aAppcompatflags; "AppCompatFlags"
0x14001930a  mov     dword ptr [rsp+520h+lpData], edi
0x14001930e  mov     edx, 105h
0x140019313  lea     rcx, [rbp+420h+var_460]
0x140019317  call    AmiUtilityGetPersistedLocation
0x14001931c  test    eax, eax
0x14001931e  jns     short loc_140019334
0x140019320  mov     ebx, 507h
0x140019325  lea     r9, aAmiutilitygetp; "AmiUtilityGetPersistedLocation [%#x]"
0x14001932c  lea     r8d, [rdi+52h]
0x140019330  mov     ecx, edi
0x140019332  jmp     short loc_1400192E2
0x140019334  mov     r8, r15; unsigned __int16 *
0x140019337  lea     rdx, [rbp+420h+var_250]; unsigned __int16 *
0x14001933e  lea     rcx, [rsp+520h+var_4D0]; void **
0x140019343  call    AmiStoreInitialize
0x140019348  mov     ebx, eax
0x14001934a  cmp     eax, 5
0x14001934d  jz      loc_1400195DD
0x140019353  mov     eax, 3F1h
0x140019358  cmp     ebx, eax
0x14001935a  jnz     short loc_140019384
0x14001935c  mov     r8d, 64h ; 'd'
0x140019362  mov     dword ptr [rsp+520h+lpData], eax
0x140019366  lea     r9, aFailedToInitia_1; "Failed to initialize store [%d] - Attem"...
0x14001936d  lea     rdx, aAmiproviderini; "AmiProviderInit"
0x140019374  lea     esi, [r8-61h]
0x140019378  mov     ecx, esi
0x14001937a  call    AslLogCallPrintf
0x14001937f  jmp     loc_140019558
0x140019384  test    ebx, ebx
0x140019386  jz      short loc_1400193A2
0x140019388  mov     r8d, 69h ; 'i'
0x14001938e  mov     dword ptr [rsp+520h+lpData], ebx
0x140019392  lea     r9, aFailedToInitia_2; "Failed to initialize store [%d]"
0x140019399  lea     ecx, [r8-66h]
0x14001939d  jmp     loc_1400192E6
0x1400193a2  mov     dword ptr [rsp+520h+Data], edi
0x1400193a6  call    cs:__imp_GetTickCount
0x1400193ac  mov     ecx, eax
0x1400193ae  call    cs:__imp__o_srand
0x1400193b4  call    cs:__imp_rand
0x1400193ba  lea     r9, aPermissionsche; "PermissionsCheckTestKey"
0x1400193c1  mov     edx, 28h ; '('; unsigned __int64
0x1400193c6  lea     r8, aLsI; "%ls%i"
0x1400193cd  mov     dword ptr [rsp+520h+lpData], eax
0x1400193d1  lea     rcx, [rsp+520h+SubKey]; unsigned __int16 *
0x1400193d6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400193db  test    eax, eax
0x1400193dd  jns     short loc_1400193FE
0x1400193df  lea     r9, aStringcchprint_0; "StringCchPrintfW [%#x]"
0x1400193e6  mov     dword ptr [rsp+520h+lpData], eax
0x1400193ea  mov     r8d, 80h
0x1400193f0  lea     rdx, aAmiproviderini; "AmiProviderInit"
0x1400193f7  mov     ecx, edi
0x1400193f9  call    AslLogCallPrintf
0x1400193fe  mov     r14, [rsp+520h+var_4D0]
0x140019403  mov     esi, 3
0x140019408  test    r14, r14
0x14001940b  jnz     short loc_140019412
0x14001940d  lea     ebx, [rsi+54h]
0x140019410  jmp     short loc_140019468
0x140019412  mov     rcx, [r14+8]; hKey
0x140019416  lea     rax, [rsp+520h+Data]
0x14001941b  mov     r9d, 4; dwType
0x140019421  lea     rdx, aWritepermissio; "WritePermissionsCheck"
0x140019428  mov     dword ptr [rsp+520h+cbData], r9d; cbData
0x14001942d  xor     r8d, r8d; Reserved
0x140019430  mov     [rsp+520h+lpData], rax; lpData
0x140019435  xor     r12b, r12b
0x140019438  call    cs:__imp_RegSetValueExW
0x14001943e  mov     ebx, eax
0x140019440  test    eax, eax
0x140019442  jz      short loc_14001949C
0x140019444  cmp     eax, 5
0x140019447  jz      short loc_140019468
0x140019449  lea     r9, aRegsetvalueexF; "RegSetValueEx failed [%d]"
0x140019450  mov     dword ptr [rsp+520h+lpData], eax
0x140019454  mov     r8d, 27Eh
0x14001945a  lea     rdx, aAmiutilityregs; "AmiUtilityRegSetValue"
0x140019461  mov     ecx, edi
0x140019463  call    AslLogCallPrintf
0x140019468  mov     eax, 92h
0x14001946d  mov     dword ptr [rsp+520h+cbData], ebx
0x140019471  cmp     ebx, 5
0x140019474  mov     [rsp+520h+lpData], r15
0x140019479  mov     ecx, edi
0x14001947b  lea     r9, aFailedToWriteT; "Failed to write to provider: %ws [%d]"
0x140019482  cmovz   ecx, esi
0x140019485  lea     rdx, aAmiproviderini; "AmiProviderInit"
0x14001948c  lea     r8d, [rax-4]
0x140019490  cmovz   r8d, eax
0x140019494  call    AslLogCallPrintf
0x140019499  mov     r12b, dil
0x14001949c  mov     rcx, [r14+8]; hKey
0x1400194a0  lea     rax, [rsp+520h+hKey]
0x1400194a5  mov     [rsp+520h+lpdwDisposition], 0; lpdwDisposition
0x1400194ae  lea     rdx, [rsp+520h+SubKey]; lpSubKey
0x1400194b3  mov     [rsp+520h+phkResult], rax; phkResult
0x1400194b8  xor     r9d, r9d; lpClass
0x1400194bb  mov     [rsp+520h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1400194c4  xor     r8d, r8d; Reserved
0x1400194c7  mov     dword ptr [rsp+520h+cbData], 0F003Fh; samDesired
0x1400194cf  mov     dword ptr [rsp+520h+lpData], 0; dwOptions
0x1400194d7  call    cs:__imp_RegCreateKeyExW
0x1400194dd  test    eax, eax
0x1400194df  jz      short loc_140019520
0x1400194e1  mov     ecx, 0A6h
0x1400194e6  mov     r9d, 5
0x1400194ec  cmp     eax, r9d
0x1400194ef  mov     edx, r9d
0x1400194f2  lea     r9, aFailedToCreate; "Failed to create test key under provide"...
0x1400194f9  cmovnz  edx, eax
0x1400194fc  lea     r8d, [rcx-4]
0x140019500  mov     dword ptr [rsp+520h+cbData], edx
0x140019504  cmovz   r8d, ecx
0x140019508  mov     ecx, esi
0x14001950a  cmovz   ecx, edi
0x14001950d  lea     rdx, aAmiproviderini; "AmiProviderInit"
0x140019514  mov     [rsp+520h+lpData], r15
0x140019519  call    AslLogCallPrintf
0x14001951e  jmp     short loc_140019558
0x140019520  mov     rcx, [rsp+520h+hKey]; hKey
0x140019525  call    cs:__imp_RegCloseKey
0x14001952b  mov     rcx, [r14+8]; hKey
0x14001952f  lea     rdx, [rsp+520h+SubKey]; lpSubKey
0x140019534  call    cs:__imp_RegDeleteKeyW
0x14001953a  test    eax, eax
0x14001953c  jz      short loc_140019553
0x14001953e  mov     dword ptr [rsp+520h+cbData], eax
0x140019542  lea     r9, aFailedToDelete; "Failed to delete test key under provide"...
0x140019549  mov     r8d, 0B7h
0x14001954f  mov     ecx, edi
0x140019551  jmp     short loc_14001950D
0x140019553  test    r12b, r12b
0x140019556  jz      short loc_1400195D7
0x140019558  mov     rbx, 0FFFFFFFF80000002h
0x14001955f  lea     r8, aAmihivepermiss; "AmiHivePermissionsCorrect"
0x140019566  mov     rcx, rbx; hKey
0x140019569  lea     rdx, [rbp+420h+var_460]; lpSubKey
0x14001956d  call    cs:__imp_RegDeleteKeyValueW
0x140019573  lea     r8, aAmihiveownerco; "AmiHiveOwnerCorrect"
0x14001957a  mov     rcx, rbx; hKey
0x14001957d  lea     rdx, [rbp+420h+var_460]; lpSubKey
0x140019581  call    cs:__imp_RegDeleteKeyValueW
0x140019587  mov     r8, r15; unsigned __int16 *
0x14001958a  lea     rdx, [rbp+420h+var_250]; unsigned __int16 *
0x140019591  lea     rcx, [rsp+520h+var_4D0]; void **
0x140019596  call    AmiStoreInitialize
0x14001959b  lea     rdx, aAmiproviderini; "AmiProviderInit"
0x1400195a2  mov     ebx, eax
0x1400195a4  mov     ecx, esi
0x1400195a6  test    eax, eax
0x1400195a8  jz      short loc_1400195C0
0x1400195aa  mov     dword ptr [rsp+520h+lpData], eax
0x1400195ae  lea     r9, aFailedToUpdate; "Failed to update store permissions [%d]"
0x1400195b5  mov     r8d, 0CFh
0x1400195bb  jmp     loc_1400192ED
0x1400195c0  lea     r9, aUpdatedStorePe; "Updated store permissions"
0x1400195c7  mov     r8d, 0D3h
0x1400195cd  call    AslLogCallPrintf
0x1400195d2  mov     r14, [rsp+520h+var_4D0]
0x1400195d7  mov     [r13+0], r14
0x1400195db  xor     ebx, ebx
0x1400195dd  mov     eax, ebx
0x1400195df  mov     rcx, [rbp+420h+var_40]
0x1400195e6  xor     rcx, rsp; StackCookie
0x1400195e9  call    __security_check_cookie
0x1400195ee  mov     rbx, [rsp+520h+arg_8]
0x1400195f6  add     rsp, 4F0h
0x1400195fd  pop     r15
0x1400195ff  pop     r14
0x140019601  pop     r13
0x140019603  pop     r12
0x140019605  pop     rdi
0x140019606  pop     rsi
0x140019607  pop     rbp
0x140019608  retn
```
