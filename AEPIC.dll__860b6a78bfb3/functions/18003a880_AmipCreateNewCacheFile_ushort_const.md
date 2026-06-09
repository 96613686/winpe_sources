# AmipCreateNewCacheFile(ushort const *)

- ea: `0x18003a880`
- end: `0x18003ad11`
- name: `?AmipCreateNewCacheFile@@YAKPEBG@Z`
- size: `1169`
- prototype: `unsigned int __fastcall(LPCWSTR lpFile)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003b2c4`

## callees

- `0x180005890`
- `0x180006938`
- `0x18000cb30`
- `0x1800295dc`
- `0x180039b54`
- `0x180039e08`
- `0x18003a880`
- `0x18003b5e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18003a9ba`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18003a9db`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18003a9ba`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18003a9db`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18003a97b`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18003a97b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003ab4c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003ab4c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18003ab68`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18003ab68`
- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x18003ac98`
- `api-ms-win-core-registry-l1-1-0!RegSaveKeyExW` at `0x18003ac98`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003acde`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18003acde`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003aa1c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003aa1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003acc3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003acc3`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18003aa5c`
- `api-ms-win-core-processenvironment-l1-1-0!GetCommandLineW` at `0x18003aa5c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003ab11`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003abc7`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003ac24`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003ac69`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003ab11`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003abc7`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003ac24`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18003ac69`

## string_xrefs

- `0x18003aa90`: `StringCchCopyW failed [%#x]`
- `0x18003a92b`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x18003a938`: `AppCompatFlags`
- `0x18003a911`: `AmipCreateNewCacheFile`
- `0x18003a995`: `AmipCreateNewCacheFile`
- `0x18003aaa1`: `AmipCreateNewCacheFile`
- `0x18003aace`: `AmipCreateNewCacheFile`
- `0x18003ab2c`: `AmipCreateNewCacheFile`
- `0x18003ab8b`: `AmipCreateNewCacheFile`
- `0x18003abe2`: `AmipCreateNewCacheFile`
- `0x18003aa28`: `RegCreateKeyEx failed [%d]`
- `0x18003aabc`: `AmiCache creating command: %ls`
- `0x18003aa4a`: `AmiUtilityGivePrivilegesToServices failed [%d]`
- `0x18003ab1b`: `RegSetKeyValue failed [%d]`
- `0x18003abd1`: `RegSetKeyValue failed [%d]`
- `0x18003ac30`: `RegSetKeyValue failed [%d]`
- `0x18003ac75`: `RegSetKeyValue failed [%d]`
- `0x18003ab00`: `CreatingCommand`
- `0x18003ab79`: `AmiCache creating module: %ls`
- `0x18003acd4`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\{11517B7C-E79D-4e20-961B-75A811715ADD}`

## pseudocode

```c
__int64 __fastcall AmipCreateNewCacheFile(LPCWSTR lpFile)
{
  unsigned __int8 v2; // dl
  LSTATUS PersistedLocation; // eax
  unsigned int v4; // ebx
  const char *v5; // r9
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // r8
  const unsigned __int16 *CommandLineW; // rax
  int v10; // eax
  WCHAR *v11; // rdi
  WCHAR *v12; // rbx
  __int64 v13; // rsi
  __int64 v14; // rax
  LSTATUS v15; // eax
  LSTATUS v16; // eax
  DWORD dwOptions[2]; // [rsp+20h] [rbp-E0h]
  int Data; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  HMODULE phModule; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v23[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR Filename[264]; // [rsp+490h] [rbp+390h] BYREF

  Data = 0;
  memset_0(v23, 0, 0x20Au);
  memset_0(SubKey, 0, 0x20Au);
  hKey = 0;
  phModule = 0;
  PersistedLocation = AmiUtilitySetPrivilege(0x11u, v2);
  v4 = PersistedLocation;
  if ( PersistedLocation )
  {
    v5 = "You must be logged on as Administrator/System [%d]";
    v6 = 56;
    v7 = 3;
LABEL_3:
    dwOptions[0] = PersistedLocation;
    AslLogCallPrintf(v7, "AmipCreateNewCacheFile", v6, v5, *(_QWORD *)dwOptions);
    goto LABEL_40;
  }
  PersistedLocation = AmiUtilityGetPersistedLocation(
                        (unsigned int)v23,
                        261,
                        (unsigned int)L"AppCompatFlags",
                        (unsigned int)L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
                        1);
  if ( PersistedLocation < 0 )
  {
    v4 = 1287;
    v5 = "AmiUtilityGetPersistedLocation [%#x]";
    v6 = 67;
LABEL_6:
    v7 = 1;
    goto LABEL_3;
  }
  if ( (unsigned int)_o_wcscpy_s(SubKey, 261, v23) )
  {
    v8 = 74;
LABEL_9:
    v4 = 1287;
    AslLogCallPrintf(1, "AmipCreateNewCacheFile", v8, "wcscpy_s failed");
    goto LABEL_40;
  }
  if ( (unsigned int)_o_wcscat_s(SubKey, 261, L"\\") )
  {
    v8 = 81;
    goto LABEL_9;
  }
  if ( (unsigned int)_o_wcscat_s(SubKey, 261, L"{11517B7C-E79D-4e20-961B-75A811715ADD}") )
  {
    v8 = 88;
    goto LABEL_9;
  }
  PersistedLocation = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  v4 = PersistedLocation;
  if ( PersistedLocation )
  {
    v5 = "RegCreateKeyEx failed [%d]";
    v6 = 107;
    goto LABEL_6;
  }
  PersistedLocation = AmiUtilityGivePrivilegesToServices(hKey);
  v4 = PersistedLocation;
  if ( PersistedLocation )
  {
    v5 = "AmiUtilityGivePrivilegesToServices failed [%d]";
    v6 = 118;
    goto LABEL_6;
  }
  CommandLineW = GetCommandLineW();
  v10 = StringCchCopyW(Filename, 0x104u, CommandLineW);
  v11 = L"Unknown";
  if ( (int)(v10 + 0x80000000) < 0 || v10 == -2147024774 )
  {
    v12 = Filename;
  }
  else
  {
    AslLogCallPrintf(1, "AmipCreateNewCacheFile", 134, "StringCchCopyW failed [%#x]", v10);
    v12 = L"Unknown";
  }
  AslLogCallPrintf(3, "AmipCreateNewCacheFile", 138, "AmiCache creating command: %ls", v12);
  v13 = -1;
  v14 = -1;
  do
    ++v14;
  while ( v12[v14] );
  v15 = RegSetKeyValueW(hKey, 0, L"CreatingCommand", 1u, v12, 2 * v14 + 2);
  if ( v15 )
    AslLogCallPrintf(1, "AmipCreateNewCacheFile", 147, "RegSetKeyValue failed [%d]", v15);
  if ( GetModuleHandleExW(6u, (LPCWSTR)AmipCreateNewCacheFile, &phModule)
    && GetModuleFileNameW(phModule, Filename, 0x104u) )
  {
    v11 = Filename;
  }
  AslLogCallPrintf(3, "AmipCreateNewCacheFile", 162, "AmiCache creating module: %ls", v11);
  do
    ++v13;
  while ( v11[v13] );
  v16 = RegSetKeyValueW(hKey, 0, L"CreatingModule", 1u, v11, 2 * v13 + 2);
  if ( v16 )
    AslLogCallPrintf(1, "AmipCreateNewCacheFile", 171, "RegSetKeyValue failed [%d]", v16);
  Data = 1;
  PersistedLocation = RegSetKeyValueW(HKEY_LOCAL_MACHINE, v23, L"AmiHivePermissionsCorrect", 4u, &Data, 4u);
  v4 = PersistedLocation;
  if ( PersistedLocation )
  {
    v5 = "RegSetKeyValue failed [%d]";
    v6 = 186;
    goto LABEL_6;
  }
  Data = 1;
  PersistedLocation = RegSetKeyValueW(HKEY_LOCAL_MACHINE, v23, L"AmiHiveOwnerCorrect", 4u, &Data, 4u);
  v4 = PersistedLocation;
  if ( PersistedLocation )
  {
    v5 = "RegSetKeyValue failed [%d]";
    v6 = 198;
    goto LABEL_6;
  }
  PersistedLocation = RegSaveKeyExW(hKey, lpFile, 0, 2u);
  v4 = PersistedLocation;
  if ( PersistedLocation )
  {
    v5 = "RegSaveKeyEx failed [%d]";
    v6 = 208;
    goto LABEL_6;
  }
  v4 = 0;
LABEL_40:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
    RegDeleteKeyExW(
      HKEY_LOCAL_MACHINE,
      L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags\\{11517B7C-E79D-4e20-961B-75A811715ADD}",
      0,
      0);
  }
  return v4;
}

```

## disassembly

```asm
0x18003a880  mov     [rsp-8+arg_8], rbx
0x18003a885  mov     [rsp-8+arg_10], rsi
0x18003a88a  push    rbp
0x18003a88b  push    rdi
0x18003a88c  push    r12
0x18003a88e  push    r14
0x18003a890  push    r15
0x18003a892  lea     rbp, [rsp-5B0h]
0x18003a89a  sub     rsp, 6B0h
0x18003a8a1  mov     rax, cs:__security_cookie
0x18003a8a8  xor     rax, rsp
0x18003a8ab  mov     [rbp+5D0h+var_30], rax
0x18003a8b2  mov     r14, rcx
0x18003a8b5  mov     ebx, 20Ah
0x18003a8ba  xor     r15d, r15d
0x18003a8bd  lea     rcx, [rbp+5D0h+var_450]; void *
0x18003a8c4  mov     r8d, ebx; Size
0x18003a8c7  mov     [rsp+6D0h+Data], r15d
0x18003a8cc  xor     edx, edx; Val
0x18003a8ce  call    memset_0
0x18003a8d3  mov     r8d, ebx; Size
0x18003a8d6  lea     rcx, [rsp+6D0h+SubKey]; void *
0x18003a8db  xor     edx, edx; Val
0x18003a8dd  call    memset_0
0x18003a8e2  lea     ecx, [r15+11h]; unsigned int
0x18003a8e6  mov     [rsp+6D0h+hKey], r15
0x18003a8eb  mov     [rsp+6D0h+phModule], r15
0x18003a8f0  call    ?AmiUtilitySetPrivilege@@YAKKE@Z; AmiUtilitySetPrivilege(ulong,uchar)
0x18003a8f5  mov     ebx, eax
0x18003a8f7  mov     rsi, 0FFFFFFFF80000002h
0x18003a8fe  test    eax, eax
0x18003a900  jz      short loc_18003A926
0x18003a902  lea     r9, aYouMustBeLogge; "You must be logged on as Administrator/"...
0x18003a909  lea     r8d, [r15+38h]
0x18003a90d  lea     ecx, [r15+3]
0x18003a911  lea     rdx, aAmipcreatenewc_0; "AmipCreateNewCacheFile"
0x18003a918  mov     [rsp+6D0h+dwOptions], eax
0x18003a91c  call    AslLogCallPrintf
0x18003a921  jmp     loc_18003ACB9
0x18003a926  mov     ebx, 105h
0x18003a92b  lea     r9, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003a932  mov     r12d, 1
0x18003a938  lea     r8, aAppcompatflags; "AppCompatFlags"
0x18003a93f  mov     edx, ebx
0x18003a941  mov     [rsp+6D0h+dwOptions], r12d
0x18003a946  lea     rcx, [rbp+5D0h+var_450]
0x18003a94d  call    AmiUtilityGetPersistedLocation
0x18003a952  test    eax, eax
0x18003a954  jns     short loc_18003A96C
0x18003a956  mov     ebx, 507h
0x18003a95b  lea     r9, aAmiutilitygetp; "AmiUtilityGetPersistedLocation [%#x]"
0x18003a962  lea     r8d, [r12+42h]
0x18003a967  mov     ecx, r12d
0x18003a96a  jmp     short loc_18003A911
0x18003a96c  lea     r8, [rbp+5D0h+var_450]
0x18003a973  mov     rdx, rbx
0x18003a976  lea     rcx, [rsp+6D0h+SubKey]
0x18003a97b  call    cs:__imp__o_wcscpy_s
0x18003a981  test    eax, eax
0x18003a983  jz      short loc_18003A9AB
0x18003a985  mov     r8d, 4Ah ; 'J'
0x18003a98b  lea     r9, aWcscpySFailed; "wcscpy_s failed"
0x18003a992  mov     ecx, r12d
0x18003a995  lea     rdx, aAmipcreatenewc_0; "AmipCreateNewCacheFile"
0x18003a99c  mov     ebx, 507h
0x18003a9a1  call    AslLogCallPrintf
0x18003a9a6  jmp     loc_18003ACB9
0x18003a9ab  lea     r8, Source; "\\"
0x18003a9b2  mov     rdx, rbx
0x18003a9b5  lea     rcx, [rsp+6D0h+SubKey]
0x18003a9ba  call    cs:__imp__o_wcscat_s
0x18003a9c0  test    eax, eax
0x18003a9c2  jz      short loc_18003A9CC
0x18003a9c4  mov     r8d, 51h ; 'Q'
0x18003a9ca  jmp     short loc_18003A98B
0x18003a9cc  lea     r8, a11517b7cE79d4e; "{11517B7C-E79D-4e20-961B-75A811715ADD}"
0x18003a9d3  mov     rdx, rbx
0x18003a9d6  lea     rcx, [rsp+6D0h+SubKey]
0x18003a9db  call    cs:__imp__o_wcscat_s
0x18003a9e1  test    eax, eax
0x18003a9e3  jz      short loc_18003A9ED
0x18003a9e5  mov     r8d, 58h ; 'X'
0x18003a9eb  jmp     short loc_18003A98B
0x18003a9ed  mov     [rsp+6D0h+lpdwDisposition], r15; lpdwDisposition
0x18003a9f2  lea     rax, [rsp+6D0h+hKey]
0x18003a9f7  mov     [rsp+6D0h+phkResult], rax; phkResult
0x18003a9fc  lea     rdx, [rsp+6D0h+SubKey]; lpSubKey
0x18003aa01  mov     [rsp+6D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x18003aa06  xor     r9d, r9d; lpClass
0x18003aa09  mov     [rsp+6D0h+samDesired], 0F003Fh; samDesired
0x18003aa11  xor     r8d, r8d; Reserved
0x18003aa14  mov     rcx, rsi; hKey
0x18003aa17  mov     [rsp+6D0h+dwOptions], r15d; dwOptions
0x18003aa1c  call    cs:__imp_RegCreateKeyExW
0x18003aa22  mov     ebx, eax
0x18003aa24  test    eax, eax
0x18003aa26  jz      short loc_18003AA3A
0x18003aa28  lea     r9, aRegcreatekeyex; "RegCreateKeyEx failed [%d]"
0x18003aa2f  mov     r8d, 6Bh ; 'k'
0x18003aa35  jmp     loc_18003A967
0x18003aa3a  mov     rcx, [rsp+6D0h+hKey]; hKey
0x18003aa3f  call    ?AmiUtilityGivePrivilegesToServices@@YAKPEAUHKEY__@@@Z; AmiUtilityGivePrivilegesToServices(HKEY__ *)
0x18003aa44  mov     ebx, eax
0x18003aa46  test    eax, eax
0x18003aa48  jz      short loc_18003AA5C
0x18003aa4a  lea     r9, aAmiutilitygive_0; "AmiUtilityGivePrivilegesToServices fail"...
0x18003aa51  mov     r8d, 76h ; 'v'
0x18003aa57  jmp     loc_18003A967
0x18003aa5c  call    cs:__imp_GetCommandLineW
0x18003aa62  mov     edx, 104h; unsigned __int64
0x18003aa67  lea     rcx, [rbp+5D0h+Filename]; unsigned __int16 *
0x18003aa6e  mov     r8, rax; unsigned __int16 *
0x18003aa71  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003aa76  mov     edx, 80000000h
0x18003aa7b  lea     rdi, aUnknown; "Unknown"
0x18003aa82  lea     ecx, [rax+rdx]
0x18003aa85  test    edx, ecx
0x18003aa87  jnz     short loc_18003AAB5
0x18003aa89  cmp     eax, 8007007Ah
0x18003aa8e  jz      short loc_18003AAB5
0x18003aa90  lea     r9, aStringcchcopyw; "StringCchCopyW failed [%#x]"
0x18003aa97  mov     [rsp+6D0h+dwOptions], eax
0x18003aa9b  mov     r8d, 86h
0x18003aaa1  lea     rdx, aAmipcreatenewc_0; "AmipCreateNewCacheFile"
0x18003aaa8  mov     ecx, r12d
0x18003aaab  call    AslLogCallPrintf
0x18003aab0  mov     rbx, rdi
0x18003aab3  jmp     short loc_18003AABC
0x18003aab5  lea     rbx, [rbp+5D0h+Filename]
0x18003aabc  lea     r9, aAmicacheCreati_0; "AmiCache creating command: %ls"
0x18003aac3  mov     qword ptr [rsp+6D0h+dwOptions], rbx
0x18003aac8  mov     r8d, 8Ah
0x18003aace  lea     rdx, aAmipcreatenewc_0; "AmipCreateNewCacheFile"
0x18003aad5  mov     ecx, 3
0x18003aada  call    AslLogCallPrintf
0x18003aadf  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003aae3  mov     rax, rsi
0x18003aae6  inc     rax
0x18003aae9  cmp     [rbx+rax*2], r15w
0x18003aaee  jnz     short loc_18003AAE6
0x18003aaf0  mov     rcx, [rsp+6D0h+hKey]; hKey
0x18003aaf5  lea     eax, ds:2[rax*2]
0x18003aafc  mov     [rsp+6D0h+samDesired], eax; cbData
0x18003ab00  lea     r8, aCreatingcomman; "CreatingCommand"
0x18003ab07  mov     r9d, r12d; dwType
0x18003ab0a  mov     qword ptr [rsp+6D0h+dwOptions], rbx; lpData
0x18003ab0f  xor     edx, edx; lpSubKey
0x18003ab11  call    cs:__imp_RegSetKeyValueW
0x18003ab17  test    eax, eax
0x18003ab19  jz      short loc_18003AB3B
0x18003ab1b  lea     r9, aRegsetkeyvalue; "RegSetKeyValue failed [%d]"
0x18003ab22  mov     [rsp+6D0h+dwOptions], eax
0x18003ab26  mov     r8d, 93h
0x18003ab2c  lea     rdx, aAmipcreatenewc_0; "AmipCreateNewCacheFile"
0x18003ab33  mov     ecx, r12d
0x18003ab36  call    AslLogCallPrintf
0x18003ab3b  lea     r8, [rsp+6D0h+phModule]; phModule
0x18003ab40  mov     ecx, 6; dwFlags
0x18003ab45  lea     rdx, ?AmipCreateNewCacheFile@@YAKPEBG@Z; lpModuleName
0x18003ab4c  call    cs:__imp_GetModuleHandleExW
0x18003ab52  test    eax, eax
0x18003ab54  jz      short loc_18003AB79
0x18003ab56  mov     rcx, [rsp+6D0h+phModule]; hModule
0x18003ab5b  lea     rdx, [rbp+5D0h+Filename]; lpFilename
0x18003ab62  mov     r8d, 104h; nSize
0x18003ab68  call    cs:__imp_GetModuleFileNameW
0x18003ab6e  test    eax, eax
0x18003ab70  jz      short loc_18003AB79
0x18003ab72  lea     rdi, [rbp+5D0h+Filename]
0x18003ab79  lea     r9, aAmicacheCreati; "AmiCache creating module: %ls"
0x18003ab80  mov     qword ptr [rsp+6D0h+dwOptions], rdi
0x18003ab85  mov     r8d, 0A2h
0x18003ab8b  lea     rdx, aAmipcreatenewc_0; "AmipCreateNewCacheFile"
0x18003ab92  mov     ecx, 3
0x18003ab97  call    AslLogCallPrintf
0x18003ab9c  inc     rsi
0x18003ab9f  cmp     [rdi+rsi*2], r15w
0x18003aba4  jnz     short loc_18003AB9C
0x18003aba6  mov     rcx, [rsp+6D0h+hKey]; hKey
0x18003abab  lea     eax, ds:2[rsi*2]
0x18003abb2  mov     [rsp+6D0h+samDesired], eax; cbData
0x18003abb6  lea     r8, aCreatingmodule; "CreatingModule"
0x18003abbd  mov     r9d, r12d; dwType
0x18003abc0  mov     qword ptr [rsp+6D0h+dwOptions], rdi; lpData
0x18003abc5  xor     edx, edx; lpSubKey
0x18003abc7  call    cs:__imp_RegSetKeyValueW
0x18003abcd  test    eax, eax
0x18003abcf  jz      short loc_18003ABF1
0x18003abd1  lea     r9, aRegsetkeyvalue; "RegSetKeyValue failed [%d]"
0x18003abd8  mov     [rsp+6D0h+dwOptions], eax
0x18003abdc  mov     r8d, 0ABh
0x18003abe2  lea     rdx, aAmipcreatenewc_0; "AmipCreateNewCacheFile"
0x18003abe9  mov     ecx, r12d
0x18003abec  call    AslLogCallPrintf
0x18003abf1  mov     edi, 4
0x18003abf6  mov     [rsp+6D0h+Data], r12d
0x18003abfb  lea     rax, [rsp+6D0h+Data]
0x18003ac00  mov     [rsp+6D0h+samDesired], edi; cbData
0x18003ac04  mov     rsi, 0FFFFFFFF80000002h
0x18003ac0b  mov     qword ptr [rsp+6D0h+dwOptions], rax; lpData
0x18003ac10  mov     r9d, edi; dwType
0x18003ac13  lea     r8, aAmihivepermiss; "AmiHivePermissionsCorrect"
0x18003ac1a  mov     rcx, rsi; hKey
0x18003ac1d  lea     rdx, [rbp+5D0h+var_450]; lpSubKey
0x18003ac24  call    cs:__imp_RegSetKeyValueW
0x18003ac2a  mov     ebx, eax
0x18003ac2c  test    eax, eax
0x18003ac2e  jz      short loc_18003AC42
0x18003ac30  lea     r9, aRegsetkeyvalue; "RegSetKeyValue failed [%d]"
0x18003ac37  mov     r8d, 0BAh
0x18003ac3d  jmp     loc_18003A967
0x18003ac42  lea     rax, [rsp+6D0h+Data]
0x18003ac47  mov     [rsp+6D0h+samDesired], edi; cbData
0x18003ac4b  mov     r9d, edi; dwType
0x18003ac4e  mov     qword ptr [rsp+6D0h+dwOptions], rax; lpData
0x18003ac53  lea     r8, aAmihiveownerco; "AmiHiveOwnerCorrect"
0x18003ac5a  mov     [rsp+6D0h+Data], r12d
0x18003ac5f  lea     rdx, [rbp+5D0h+var_450]; lpSubKey
0x18003ac66  mov     rcx, rsi; hKey
0x18003ac69  call    cs:__imp_RegSetKeyValueW
0x18003ac6f  mov     ebx, eax
0x18003ac71  test    eax, eax
0x18003ac73  jz      short loc_18003AC87
0x18003ac75  lea     r9, aRegsetkeyvalue; "RegSetKeyValue failed [%d]"
0x18003ac7c  mov     r8d, 0C6h
0x18003ac82  jmp     loc_18003A967
0x18003ac87  mov     rcx, [rsp+6D0h+hKey]; hKey
0x18003ac8c  mov     r9d, 2; Flags
0x18003ac92  xor     r8d, r8d; lpSecurityAttributes
0x18003ac95  mov     rdx, r14; lpFile
0x18003ac98  call    cs:__imp_RegSaveKeyExW
0x18003ac9e  mov     ebx, eax
0x18003aca0  test    eax, eax
0x18003aca2  jz      short loc_18003ACB6
0x18003aca4  lea     r9, aRegsavekeyexFa; "RegSaveKeyEx failed [%d]"
0x18003acab  mov     r8d, 0D0h
0x18003acb1  jmp     loc_18003A967
0x18003acb6  mov     ebx, r15d
0x18003acb9  mov     rcx, [rsp+6D0h+hKey]; hKey
0x18003acbe  test    rcx, rcx
0x18003acc1  jz      short loc_18003ACE4
0x18003acc3  call    cs:__imp_RegCloseKey
0x18003acc9  xor     r9d, r9d; Reserved
0x18003accc  mov     [rsp+6D0h+hKey], r15
0x18003acd1  xor     r8d, r8d; samDesired
0x18003acd4  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18003acdb  mov     rcx, rsi; hKey
0x18003acde  call    cs:__imp_RegDeleteKeyExW
0x18003ace4  mov     eax, ebx
0x18003ace6  mov     rcx, [rbp+5D0h+var_30]
0x18003aced  xor     rcx, rsp; StackCookie
0x18003acf0  call    __security_check_cookie
0x18003acf5  lea     r11, [rsp+6D0h+var_20]
0x18003acfd  mov     rbx, [r11+38h]
0x18003ad01  mov     rsi, [r11+40h]
0x18003ad05  mov     rsp, r11
0x18003ad08  pop     r15
0x18003ad0a  pop     r14
0x18003ad0c  pop     r12
0x18003ad0e  pop     rdi
0x18003ad0f  pop     rbp
0x18003ad10  retn
```
