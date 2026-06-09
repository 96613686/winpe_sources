# WwanPmGetProfileIndex

- ea: `0x18009d8d8`
- end: `0x18009dc0e`
- name: `WwanPmGetProfileIndex`
- size: `822`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18009d0c8`
- `0x1800acb60`
- `0x1800bafc0`

## callees

- `0x1800085d0`
- `0x1800094f4`
- `0x180012300`
- `0x180014f1c`
- `0x180016c50`
- `0x180074758`
- `0x180074cec`
- `0x18009d718`
- `0x18009d8d8`
- `0x1800a24a0`
- `0x1800a4810`
- `0x1800b6ac0`
- `0x1800c8520`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009d988`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009dad9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009d988`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009dad9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009db33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009db98`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009db33`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009db98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009dbc9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18009dbc9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009da6a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009da6a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009daaa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009daaa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009db12`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009db12`
- `WwanPrfl!WwanProfileCleanup` at `0x18009dba2`
- `WwanPrfl!WwanProfileCleanup` at `0x18009dba2`
- `WwanPrfl!WwanProfileInit` at `0x18009d97b`
- `WwanPrfl!WwanProfileInit` at `0x18009d97b`
- `WwanPrfl!WwanProfileDeinit` at `0x18009dbac`
- `WwanPrfl!WwanProfileDeinit` at `0x18009dbac`

## string_xrefs

- `0x18009da76`: `RegOpenKeyEx failed, dwError (0x%8x)`
- `0x18009da40`: `WwanRegBuildMetadataPath failed, dwError (0x%8x)`
- `0x18009db40`: `RegSetValueEx query profile index failed, dwError (0x%8x)`

## pseudocode

```c
__int64 __fastcall WwanPmGetProfileIndex(__int64 a1, const unsigned __int16 *a2, _DWORD *a3, unsigned int *a4)
{
  unsigned __int16 *v8; // rdi
  unsigned int ProfileContextStruct; // eax
  unsigned int v10; // ebx
  const unsigned __int16 *v11; // r8
  unsigned int ProfileGuid; // eax
  unsigned __int64 v13; // r9
  LSTATUS v14; // eax
  int v15; // eax
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v21; // [rsp+48h] [rbp-B8h] BYREF
  struct WPKEY *v22[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v23; // [rsp+60h] [rbp-A0h]
  __int128 v24; // [rsp+70h] [rbp-90h]
  _BYTE v25[6320]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SubKey[264]; // [rsp+1930h] [rbp+1830h] BYREF

  memset_0(SubKey, 0, 0x208u);
  v8 = 0;
  v21 = 0;
  memset_0(v25, 0, sizeof(v25));
  hKey = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  *(_OWORD *)v22 = 0;
  Type = 0;
  v23 = 0;
  v24 = 0;
  WwanLog::Enter("WwanPmGetProfileIndex");
  WwanProfileInit(v25);
  EnterCriticalSection(&g_pmCs);
  if ( !a1 || !a2 || !a3 )
  {
    v10 = 87;
    goto LABEL_28;
  }
  *a3 = 0;
  if ( a4 )
    *a4 = 0;
  ProfileContextStruct = WwanPmGetProfileContextStruct(a2, v25, v22);
  v10 = ProfileContextStruct;
  if ( ProfileContextStruct )
  {
    v11 = L"WwanPmGetProfileContextStruct failed, dwError (0x%8x)";
LABEL_8:
    WwanLog::Error("WwanPmGetProfileIndex", 0, v11, ProfileContextStruct);
    goto LABEL_28;
  }
  ProfileGuid = WpKeyGetProfileGuid(v22[1], a2, (const unsigned __int16 **)&v21);
  v10 = ProfileGuid;
  if ( ProfileGuid )
  {
    WwanLog::Error("WwanPmGetProfileIndex", 0, L"WpKeyGetProfileGuid failed, dwError (0x%8x)", ProfileGuid);
    v8 = v21;
    goto LABEL_28;
  }
  v8 = v21;
  ProfileContextStruct = WwanRegBuildMetadataPath((const unsigned __int16 *)v22[1] + 40, v21, SubKey, v13, 0);
  v10 = ProfileContextStruct;
  if ( ProfileContextStruct )
  {
    v11 = L"WwanRegBuildMetadataPath failed, dwError (0x%8x)";
    goto LABEL_8;
  }
  ProfileContextStruct = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20007u, &hKey);
  v10 = ProfileContextStruct;
  if ( ProfileContextStruct )
  {
    v11 = L"RegOpenKeyEx failed, dwError (0x%8x)";
    goto LABEL_8;
  }
  ProfileContextStruct = RegQueryValueExW(hKey, L"ProfileIndex", 0, &Type, Data, &cbData);
  v10 = ProfileContextStruct;
  if ( ProfileContextStruct == 2 )
  {
    WwanLog::Info(
      "WwanPmGetProfileIndex",
      0,
      L"RegQueryValueEx == ERROR_FILE_NOT_FOUND. Assign new profile index!, dwError (0x%8x)");
    EnterCriticalSection(&g_csHighestProfileIndex);
    *(_DWORD *)Data = g_dwHighestProfileIndex + 1;
    v14 = RegSetValueExW(hKey, L"ProfileIndex", 0, 4u, Data, 4u);
    Type = 4;
    v10 = v14;
    if ( !v14 )
      ++g_dwHighestProfileIndex;
    LeaveCriticalSection(&g_csHighestProfileIndex);
    if ( v10 )
    {
      WwanLog::Error("WwanPmGetProfileIndex", 0, L"RegSetValueEx query profile index failed, dwError (0x%8x)", v10);
      goto LABEL_28;
    }
  }
  else if ( ProfileContextStruct )
  {
    v11 = L"RegQueryValueEx query profile index failed, dwError (0x%8x)";
    goto LABEL_8;
  }
  if ( Type == 4 )
  {
    v15 = *(_DWORD *)Data;
    *a3 = *(_DWORD *)Data;
    if ( a4 )
      *a4 = v15 | 0x80000000;
  }
  else
  {
    v10 = 13;
    WwanLog::Error("WwanPmGetProfileIndex", 0, L"RegQueryValueEx get invalid type %d", Type);
  }
LABEL_28:
  LeaveCriticalSection(&g_pmCs);
  WwanProfileCleanup(v25);
  WwanProfileDeinit(v25);
  if ( v8 )
    WwanMemFree(v8);
  if ( hKey )
    RegCloseKey(hKey);
  WwanLog::Verbose("WwanPmGetProfileIndex", 0, L"dwError (0x%8x)", v10);
  WwanLog::Exit("WwanPmGetProfileIndex");
  return v10;
}

```

## disassembly

```asm
0x18009d8d8  push    rbp
0x18009d8da  push    rbx
0x18009d8db  push    rsi
0x18009d8dc  push    rdi
0x18009d8dd  push    r13
0x18009d8df  push    r14
0x18009d8e1  push    r15
0x18009d8e3  lea     rbp, [rsp-1A50h]
0x18009d8eb  mov     eax, 1B50h
0x18009d8f0  call    _alloca_probe
0x18009d8f5  sub     rsp, rax
0x18009d8f8  mov     rax, cs:__security_cookie
0x18009d8ff  xor     rax, rsp
0x18009d902  mov     [rbp+1A80h+var_40], rax
0x18009d909  mov     r15, r8
0x18009d90c  mov     r14, rdx
0x18009d90f  mov     rbx, rcx
0x18009d912  xor     edx, edx; Val
0x18009d914  mov     r8d, 208h; Size
0x18009d91a  lea     rcx, [rbp+1A80h+SubKey]; void *
0x18009d921  mov     rsi, r9
0x18009d924  call    memset_0
0x18009d929  xor     edi, edi
0x18009d92b  lea     rcx, [rbp+1A80h+var_1B00]; void *
0x18009d92f  xor     edx, edx; Val
0x18009d931  mov     [rsp+1B80h+var_1B38], rdi
0x18009d936  mov     r8d, 18B0h; Size
0x18009d93c  call    memset_0
0x18009d941  xorps   xmm0, xmm0
0x18009d944  mov     [rsp+1B80h+hKey], rdi
0x18009d949  lea     r13, aWwanpmgetprofi_1; "WwanPmGetProfileIndex"
0x18009d950  mov     dword ptr [rsp+1B80h+Data], edi
0x18009d954  mov     rcx, r13; char *
0x18009d957  mov     [rsp+1B80h+cbData], 4
0x18009d95f  movups  xmmword ptr [rsp+1B80h+var_1B30], xmm0
0x18009d964  mov     [rsp+1B80h+Type], edi
0x18009d968  movups  [rsp+1B80h+var_1B20], xmm0
0x18009d96d  movups  [rsp+1B80h+var_1B10], xmm0
0x18009d972  call    ?Enter@WwanLog@@SAXPEBD@Z; WwanLog::Enter(char const *)
0x18009d977  lea     rcx, [rbp+1A80h+var_1B00]
0x18009d97b  call    cs:__imp_WwanProfileInit
0x18009d981  lea     rcx, g_pmCs; lpCriticalSection
0x18009d988  call    cs:__imp_EnterCriticalSection
0x18009d98e  test    rbx, rbx
0x18009d991  jz      loc_18009DB8C
0x18009d997  test    r14, r14
0x18009d99a  jz      loc_18009DB8C
0x18009d9a0  test    r15, r15
0x18009d9a3  jz      loc_18009DB8C
0x18009d9a9  mov     [r15], edi
0x18009d9ac  test    rsi, rsi
0x18009d9af  jz      short loc_18009D9B3
0x18009d9b1  mov     [rsi], edi
0x18009d9b3  lea     r8, [rsp+1B80h+var_1B30]
0x18009d9b8  mov     rcx, r14
0x18009d9bb  lea     rdx, [rbp+1A80h+var_1B00]
0x18009d9bf  call    WwanPmGetProfileContextStruct
0x18009d9c4  mov     ebx, eax
0x18009d9c6  test    eax, eax
0x18009d9c8  jz      short loc_18009D9E3
0x18009d9ca  lea     r8, aWwanpmgetprofi_13; "WwanPmGetProfileContextStruct failed, d"...
0x18009d9d1  mov     r9d, eax
0x18009d9d4  xor     edx, edx; struct _GUID *
0x18009d9d6  mov     rcx, r13; char *
0x18009d9d9  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18009d9de  jmp     loc_18009DB91
0x18009d9e3  mov     rcx, [rsp+1B80h+var_1B30+8]; struct WPKEY *
0x18009d9e8  lea     r8, [rsp+1B80h+var_1B38]; unsigned __int16 **
0x18009d9ed  mov     rdx, r14; unsigned __int16 *
0x18009d9f0  call    ?WpKeyGetProfileGuid@@YAKPEAUWPKEY@@PEBGPEAPEBG@Z; WpKeyGetProfileGuid(WPKEY *,ushort const *,ushort const * *)
0x18009d9f5  mov     ebx, eax
0x18009d9f7  test    eax, eax
0x18009d9f9  jz      short loc_18009DA19
0x18009d9fb  mov     r9d, eax
0x18009d9fe  lea     r8, aWpkeygetprofil_5; "WpKeyGetProfileGuid failed, dwError (0x"...
0x18009da05  xor     edx, edx; struct _GUID *
0x18009da07  mov     rcx, r13; char *
0x18009da0a  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x18009da0f  mov     rdi, [rsp+1B80h+var_1B38]
0x18009da14  jmp     loc_18009DB91
0x18009da19  mov     rcx, [rsp+1B80h+var_1B30+8]
0x18009da1e  lea     r8, [rbp+1A80h+SubKey]; unsigned __int16 *
0x18009da25  mov     dword ptr [rsp+1B80h+phkResult], edi; int
0x18009da29  add     rcx, 50h ; 'P'; unsigned __int16 *
0x18009da2d  mov     rdi, [rsp+1B80h+var_1B38]
0x18009da32  mov     rdx, rdi; unsigned __int16 *
0x18009da35  call    ?WwanRegBuildMetadataPath@@YAKPEBG0PEAG_KH@Z; WwanRegBuildMetadataPath(ushort const *,ushort const *,ushort *,unsigned __int64,int)
0x18009da3a  mov     ebx, eax
0x18009da3c  test    eax, eax
0x18009da3e  jz      short loc_18009DA49
0x18009da40  lea     r8, aWwanregbuildme; "WwanRegBuildMetadataPath failed, dwErro"...
0x18009da47  jmp     short loc_18009D9D1
0x18009da49  lea     rax, [rsp+1B80h+hKey]
0x18009da4e  mov     r9d, 20007h; samDesired
0x18009da54  xor     r8d, r8d; ulOptions
0x18009da57  mov     [rsp+1B80h+phkResult], rax; phkResult
0x18009da5c  lea     rdx, [rbp+1A80h+SubKey]; lpSubKey
0x18009da63  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009da6a  call    cs:__imp_RegOpenKeyExW
0x18009da70  mov     ebx, eax
0x18009da72  test    eax, eax
0x18009da74  jz      short loc_18009DA82
0x18009da76  lea     r8, aRegopenkeyexFa_0; "RegOpenKeyEx failed, dwError (0x%8x)"
0x18009da7d  jmp     loc_18009D9D1
0x18009da82  mov     rcx, [rsp+1B80h+hKey]; hKey
0x18009da87  lea     rax, [rsp+1B80h+cbData]
0x18009da8c  mov     [rsp+1B80h+lpcbData], rax; lpcbData
0x18009da91  lea     r9, [rsp+1B80h+Type]; lpType
0x18009da96  lea     rax, [rsp+1B80h+Data]
0x18009da9b  xor     r8d, r8d; lpReserved
0x18009da9e  lea     rdx, aProfileindex; "ProfileIndex"
0x18009daa5  mov     [rsp+1B80h+phkResult], rax; lpData
0x18009daaa  call    cs:__imp_RegQueryValueExW
0x18009dab0  mov     r9d, 2
0x18009dab6  mov     ebx, eax
0x18009dab8  cmp     eax, r9d
0x18009dabb  jnz     loc_18009DB4C
0x18009dac1  lea     r8, aRegqueryvaluee_12; "RegQueryValueEx == ERROR_FILE_NOT_FOUND"...
0x18009dac8  xor     edx, edx; struct _GUID *
0x18009daca  mov     rcx, r13; char *
0x18009dacd  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x18009dad2  lea     rcx, ?g_csHighestProfileIndex@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009dad9  call    cs:__imp_EnterCriticalSection
0x18009dadf  mov     eax, cs:?g_dwHighestProfileIndex@@3KA; ulong g_dwHighestProfileIndex
0x18009dae5  lea     rdx, aProfileindex; "ProfileIndex"
0x18009daec  mov     rcx, [rsp+1B80h+hKey]; hKey
0x18009daf1  inc     eax
0x18009daf3  mov     dword ptr [rsp+1B80h+Data], eax
0x18009daf7  mov     r9d, 4; dwType
0x18009dafd  lea     rax, [rsp+1B80h+Data]
0x18009db02  mov     dword ptr [rsp+1B80h+lpcbData], 4; cbData
0x18009db0a  xor     r8d, r8d; Reserved
0x18009db0d  mov     [rsp+1B80h+phkResult], rax; lpData
0x18009db12  call    cs:__imp_RegSetValueExW
0x18009db18  mov     [rsp+1B80h+Type], 4
0x18009db20  mov     ebx, eax
0x18009db22  test    eax, eax
0x18009db24  jnz     short loc_18009DB2C
0x18009db26  inc     cs:?g_dwHighestProfileIndex@@3KA; ulong g_dwHighestProfileIndex
0x18009db2c  lea     rcx, ?g_csHighestProfileIndex@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009db33  call    cs:__imp_LeaveCriticalSection
0x18009db39  test    ebx, ebx
0x18009db3b  jz      short loc_18009DB5C
0x18009db3d  mov     r9d, ebx
0x18009db40  lea     r8, aRegsetvalueexQ; "RegSetValueEx query profile index faile"...
0x18009db47  jmp     loc_18009D9D4
0x18009db4c  test    eax, eax
0x18009db4e  jz      short loc_18009DB5C
0x18009db50  lea     r8, aRegqueryvaluee_4; "RegQueryValueEx query profile index fai"...
0x18009db57  jmp     loc_18009D9D1
0x18009db5c  mov     r9d, [rsp+1B80h+Type]
0x18009db61  cmp     r9d, 4
0x18009db65  jz      short loc_18009DB78
0x18009db67  mov     ebx, 0Dh
0x18009db6c  lea     r8, aRegqueryvaluee_3; "RegQueryValueEx get invalid type %d"
0x18009db73  jmp     loc_18009D9D4
0x18009db78  mov     eax, dword ptr [rsp+1B80h+Data]
0x18009db7c  mov     [r15], eax
0x18009db7f  test    rsi, rsi
0x18009db82  jz      short loc_18009DB91
0x18009db84  bts     eax, 1Fh
0x18009db88  mov     [rsi], eax
0x18009db8a  jmp     short loc_18009DB91
0x18009db8c  mov     ebx, 57h ; 'W'
0x18009db91  lea     rcx, g_pmCs; lpCriticalSection
0x18009db98  call    cs:__imp_LeaveCriticalSection
0x18009db9e  lea     rcx, [rbp+1A80h+var_1B00]
0x18009dba2  call    cs:__imp_WwanProfileCleanup
0x18009dba8  lea     rcx, [rbp+1A80h+var_1B00]
0x18009dbac  call    cs:__imp_WwanProfileDeinit
0x18009dbb2  test    rdi, rdi
0x18009dbb5  jz      short loc_18009DBBF
0x18009dbb7  mov     rcx, rdi
0x18009dbba  call    WwanMemFree
0x18009dbbf  mov     rcx, [rsp+1B80h+hKey]; hKey
0x18009dbc4  test    rcx, rcx
0x18009dbc7  jz      short loc_18009DBCF
0x18009dbc9  call    cs:__imp_RegCloseKey
0x18009dbcf  mov     r9d, ebx
0x18009dbd2  lea     r8, aDwerror0x8x; "dwError (0x%8x)"
0x18009dbd9  xor     edx, edx; struct _GUID *
0x18009dbdb  mov     rcx, r13; char *
0x18009dbde  call    ?Verbose@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Verbose(char const *,_GUID const *,ushort const *,...)
0x18009dbe3  mov     rcx, r13; char *
0x18009dbe6  call    ?Exit@WwanLog@@SAXPEBD@Z; WwanLog::Exit(char const *)
0x18009dbeb  mov     eax, ebx
0x18009dbed  mov     rcx, [rbp+1A80h+var_40]
0x18009dbf4  xor     rcx, rsp; StackCookie
0x18009dbf7  call    __security_check_cookie
0x18009dbfc  add     rsp, 1B50h
0x18009dc03  pop     r15
0x18009dc05  pop     r14
0x18009dc07  pop     r13
0x18009dc09  pop     rdi
0x18009dc0a  pop     rsi
0x18009dc0b  pop     rbx
0x18009dc0c  pop     rbp
0x18009dc0d  retn
```
