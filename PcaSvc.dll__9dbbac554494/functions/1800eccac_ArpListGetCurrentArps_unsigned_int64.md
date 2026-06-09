# ArpListGetCurrentArps(unsigned __int64 *)

- ea: `0x1800eccac`
- end: `0x1800ecf82`
- name: `?ArpListGetCurrentArps@@YAKPEA_K@Z`
- size: `726`
- prototype: `unsigned int __fastcall(unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b2fa4`

## callees

- `0x180010b1c`
- `0x180012920`
- `0x1800161c4`
- `0x180022ed0`
- `0x1800eccac`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x1800ece2b`
- `msvcrt!_wcsnicmp` at `0x1800ece2b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ecdd6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800ecdd6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ece96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ececb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ecedb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ecf47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ecf57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ece96`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ececb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ecedb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ecf47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ecf57`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ece58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ece87`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ece58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ece87`

## string_xrefs

- `0x1800ecf03`: `Failed to open key [%d]`
- `0x1800ecd34`: `Software\Microsoft\Windows\CurrentVersion\Uninstall`
- `0x1800ece80`: `Software\Microsoft\Windows\CurrentVersion\Uninstall`
- `0x1800ecd72`: `Software\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall`
- `0x1800ecd19`: `Failed to create list [%d]`
- `0x1800ecdf2`: `Failed to enum deleted key [%d]`

## pseudocode

```c
__int64 __fastcall ArpListGetCurrentArps(unsigned __int64 *a1)
{
  unsigned int v2; // eax
  PVOID v3; // r14
  unsigned int v4; // esi
  int v5; // r8d
  const char *v6; // r9
  DWORD i; // r15d
  LPDWORD lpReserved; // [rsp+20h] [rbp-E0h]
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  PVOID P; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  cchName = 0;
  P = 0;
  hKey = 0;
  phkResult = 0;
  v2 = ArpListCreate((unsigned __int64 *)&P);
  v3 = P;
  v4 = v2;
  if ( v2 )
  {
    v5 = 1006;
    v6 = "Failed to create list [%d]";
    goto LABEL_22;
  }
  v4 = ArpListSnapshot(
         (unsigned __int64)P,
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall",
         0,
         0);
  if ( v4 )
  {
    v5 = 1020;
    v6 = "Failed to take snapshot from HKLM [%d]";
    goto LABEL_22;
  }
  v4 = ArpListSnapshot(
         (unsigned __int64)v3,
         HKEY_LOCAL_MACHINE,
         L"Software\\Wow6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall",
         1,
         0);
  if ( v4 )
  {
    v5 = 1031;
    v6 = "Failed to take snapshot from HKLM WOW [%d]";
LABEL_22:
    LODWORD(lpReserved) = v4;
    AslLogCallPrintf(1, (unsigned int)"ArpListGetCurrentArps", v5, (_DWORD)v6, lpReserved);
    if ( v3 )
      PcaChainHistoryDelete(v3);
    goto LABEL_25;
  }
  for ( i = 0; ; ++i )
  {
    cchName = 260;
    v4 = RegEnumKeyExW(HKEY_USERS, i, Name, &cchName, 0, 0, 0, 0);
    if ( v4 == 259 )
      break;
    if ( v4 == 1018 )
    {
      LODWORD(lpReserved) = 1018;
      AslLogCallPrintf(
        2,
        (unsigned int)"ArpListGetCurrentArps",
        1056,
        (unsigned int)"Failed to enum deleted key [%d]",
        lpReserved);
    }
    else
    {
      if ( v4 )
      {
        v5 = 1061;
        v6 = "Error enumerating user key [%d]";
        goto LABEL_22;
      }
      if ( !_wcsnicmp(Name, L"S-", 2u) )
      {
        v4 = RegOpenKeyExW(HKEY_USERS, Name, 0, 0x20019u, &phkResult);
        if ( v4 )
        {
          v5 = 1079;
          v6 = "Failed to open key [%d]";
          goto LABEL_22;
        }
        if ( RegOpenKeyExW(phkResult, L"Software\\Microsoft\\Windows\\CurrentVersion\\Uninstall", 0, 0x20019u, &hKey) )
        {
          RegCloseKey(phkResult);
          phkResult = 0;
        }
        else
        {
          v4 = ArpListSnapshot((unsigned __int64)v3, hKey, 0, 0, Name);
          if ( v4 )
          {
            v5 = 1100;
            v6 = "Failed to inventory user key [%d]";
            goto LABEL_22;
          }
          RegCloseKey(phkResult);
          phkResult = 0;
          RegCloseKey(hKey);
          hKey = 0;
        }
      }
    }
  }
  *a1 = (unsigned __int64)v3;
  v4 = 0;
LABEL_25:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  return v4;
}

```

## disassembly

```asm
0x1800eccac  push    rbp
0x1800eccae  push    rbx
0x1800eccaf  push    rsi
0x1800eccb0  push    rdi
0x1800eccb1  push    r12
0x1800eccb3  push    r13
0x1800eccb5  push    r14
0x1800eccb7  push    r15
0x1800eccb9  lea     rbp, [rsp-188h]
0x1800eccc1  sub     rsp, 288h
0x1800eccc8  mov     rax, cs:__security_cookie
0x1800ecccf  xor     rax, rsp
0x1800eccd2  mov     [rbp+1C0h+var_50], rax
0x1800eccd9  xor     r13d, r13d
0x1800eccdc  mov     r12, rcx
0x1800eccdf  lea     rcx, [rsp+2C0h+P]; unsigned __int64 *
0x1800ecce4  mov     [rsp+2C0h+cchName], r13d
0x1800ecce9  mov     [rsp+2C0h+P], r13
0x1800eccee  mov     [rsp+2C0h+hKey], r13
0x1800eccf3  mov     [rsp+2C0h+phkResult], r13
0x1800eccf8  call    ?ArpListCreate@@YAKPEA_K@Z; ArpListCreate(unsigned __int64 *)
0x1800eccfd  mov     r14, [rsp+2C0h+P]
0x1800ecd02  mov     esi, eax
0x1800ecd04  test    eax, eax
0x1800ecd06  jz      short loc_1800ECD25
0x1800ecd08  lea     edi, [r13+1]
0x1800ecd0c  mov     r8d, 3EEh
0x1800ecd12  lea     rbx, aArplistgetcurr; "ArpListGetCurrentArps"
0x1800ecd19  lea     r9, aFailedToCreate_2; "Failed to create list [%d]"
0x1800ecd20  jmp     loc_1800ECF19
0x1800ecd25  mov     rbx, 0FFFFFFFF80000002h
0x1800ecd2c  mov     [rsp+2C0h+lpReserved], r13; unsigned __int16 *
0x1800ecd31  mov     rdx, rbx; HKEY
0x1800ecd34  lea     r8, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800ecd3b  xor     r9d, r9d; int
0x1800ecd3e  mov     rcx, r14; unsigned __int64
0x1800ecd41  call    ?ArpListSnapshot@@YAK_KPEAUHKEY__@@PEBGH2@Z; ArpListSnapshot(unsigned __int64,HKEY__ *,ushort const *,int,ushort const *)
0x1800ecd46  mov     esi, eax
0x1800ecd48  mov     edi, 1
0x1800ecd4d  test    eax, eax
0x1800ecd4f  jz      short loc_1800ECD6A
0x1800ecd51  lea     rbx, aArplistgetcurr; "ArpListGetCurrentArps"
0x1800ecd58  mov     r8d, 3FCh
0x1800ecd5e  lea     r9, aFailedToTakeSn; "Failed to take snapshot from HKLM [%d]"
0x1800ecd65  jmp     loc_1800ECF19
0x1800ecd6a  mov     r9d, edi; int
0x1800ecd6d  mov     [rsp+2C0h+lpReserved], r13; unsigned __int16 *
0x1800ecd72  lea     r8, aSoftwareWow643; "Software\\Wow6432Node\\Microsoft\\Windo"...
0x1800ecd79  mov     rdx, rbx; HKEY
0x1800ecd7c  mov     rcx, r14; unsigned __int64
0x1800ecd7f  call    ?ArpListSnapshot@@YAK_KPEAUHKEY__@@PEBGH2@Z; ArpListSnapshot(unsigned __int64,HKEY__ *,ushort const *,int,ushort const *)
0x1800ecd84  lea     rbx, aArplistgetcurr; "ArpListGetCurrentArps"
0x1800ecd8b  mov     esi, eax
0x1800ecd8d  test    eax, eax
0x1800ecd8f  jz      short loc_1800ECDA3
0x1800ecd91  mov     r8d, 407h
0x1800ecd97  lea     r9, aFailedToTakeSn_0; "Failed to take snapshot from HKLM WOW ["...
0x1800ecd9e  jmp     loc_1800ECF19
0x1800ecda3  mov     r15d, r13d
0x1800ecda6  mov     [rsp+2C0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800ecdab  lea     r9, [rsp+2C0h+cchName]; lpcchName
0x1800ecdb0  mov     [rsp+2C0h+lpcchClass], r13; lpcchClass
0x1800ecdb5  lea     r8, [rsp+2C0h+Name]; lpName
0x1800ecdba  mov     [rsp+2C0h+lpClass], r13; lpClass
0x1800ecdbf  mov     edx, r15d; dwIndex
0x1800ecdc2  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800ecdc9  mov     [rsp+2C0h+lpReserved], r13; lpReserved
0x1800ecdce  mov     [rsp+2C0h+cchName], 104h
0x1800ecdd6  call    cs:__imp_RegEnumKeyExW
0x1800ecddc  mov     esi, eax
0x1800ecdde  cmp     eax, 103h
0x1800ecde3  jz      loc_1800ECF36
0x1800ecde9  mov     eax, 3FAh
0x1800ecdee  cmp     esi, eax
0x1800ecdf0  jnz     short loc_1800ECE13
0x1800ecdf2  lea     r9, aFailedToEnumDe; "Failed to enum deleted key [%d]"
0x1800ecdf9  mov     dword ptr [rsp+2C0h+lpReserved], eax
0x1800ecdfd  lea     r8d, [rax+26h]
0x1800ece01  mov     rdx, rbx
0x1800ece04  mov     ecx, 2
0x1800ece09  call    AslLogCallPrintf
0x1800ece0e  jmp     loc_1800ECEE6
0x1800ece13  test    esi, esi
0x1800ece15  jnz     loc_1800ECF0C
0x1800ece1b  lea     r8d, [rsi+2]; MaxCount
0x1800ece1f  lea     rdx, aS_1; "S-"
0x1800ece26  lea     rcx, [rsp+2C0h+Name]; String1
0x1800ece2b  call    cs:__imp__wcsnicmp
0x1800ece31  test    eax, eax
0x1800ece33  jnz     loc_1800ECEE6
0x1800ece39  lea     rax, [rsp+2C0h+phkResult]
0x1800ece3e  mov     r9d, 20019h; samDesired
0x1800ece44  xor     r8d, r8d; ulOptions
0x1800ece47  mov     [rsp+2C0h+lpReserved], rax; phkResult
0x1800ece4c  lea     rdx, [rsp+2C0h+Name]; lpSubKey
0x1800ece51  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800ece58  call    cs:__imp_RegOpenKeyExW
0x1800ece5e  mov     esi, eax
0x1800ece60  test    eax, eax
0x1800ece62  jnz     loc_1800ECEFD
0x1800ece68  mov     rcx, [rsp+2C0h+phkResult]; hKey
0x1800ece6d  lea     rax, [rsp+2C0h+hKey]
0x1800ece72  mov     r9d, 20019h; samDesired
0x1800ece78  mov     [rsp+2C0h+lpReserved], rax; phkResult
0x1800ece7d  xor     r8d, r8d; ulOptions
0x1800ece80  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800ece87  call    cs:__imp_RegOpenKeyExW
0x1800ece8d  test    eax, eax
0x1800ece8f  jz      short loc_1800ECEA3
0x1800ece91  mov     rcx, [rsp+2C0h+phkResult]; hKey
0x1800ece96  call    cs:__imp_RegCloseKey
0x1800ece9c  mov     [rsp+2C0h+phkResult], r13
0x1800ecea1  jmp     short loc_1800ECEE6
0x1800ecea3  mov     rdx, [rsp+2C0h+hKey]; HKEY
0x1800ecea8  lea     rax, [rsp+2C0h+Name]
0x1800ecead  xor     r9d, r9d; int
0x1800eceb0  mov     [rsp+2C0h+lpReserved], rax; unsigned __int16 *
0x1800eceb5  xor     r8d, r8d; unsigned __int16 *
0x1800eceb8  mov     rcx, r14; unsigned __int64
0x1800ecebb  call    ?ArpListSnapshot@@YAK_KPEAUHKEY__@@PEBGH2@Z; ArpListSnapshot(unsigned __int64,HKEY__ *,ushort const *,int,ushort const *)
0x1800ecec0  mov     esi, eax
0x1800ecec2  test    eax, eax
0x1800ecec4  jnz     short loc_1800ECEEE
0x1800ecec6  mov     rcx, [rsp+2C0h+phkResult]; hKey
0x1800ececb  call    cs:__imp_RegCloseKey
0x1800eced1  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800eced6  mov     [rsp+2C0h+phkResult], r13
0x1800ecedb  call    cs:__imp_RegCloseKey
0x1800ecee1  mov     [rsp+2C0h+hKey], r13
0x1800ecee6  add     r15d, edi
0x1800ecee9  jmp     loc_1800ECDA6
0x1800eceee  mov     r8d, 44Ch
0x1800ecef4  lea     r9, aFailedToInvent; "Failed to inventory user key [%d]"
0x1800ecefb  jmp     short loc_1800ECF19
0x1800ecefd  mov     r8d, 437h
0x1800ecf03  lea     r9, aFailedToOpenKe_2; "Failed to open key [%d]"
0x1800ecf0a  jmp     short loc_1800ECF19
0x1800ecf0c  mov     r8d, 425h
0x1800ecf12  lea     r9, aErrorEnumerati; "Error enumerating user key [%d]"
0x1800ecf19  mov     rdx, rbx
0x1800ecf1c  mov     dword ptr [rsp+2C0h+lpReserved], esi
0x1800ecf20  mov     ecx, edi
0x1800ecf22  call    AslLogCallPrintf
0x1800ecf27  test    r14, r14
0x1800ecf2a  jz      short loc_1800ECF3D
0x1800ecf2c  mov     rcx, r14; P
0x1800ecf2f  call    ?PcaChainHistoryDelete@@YAX_K@Z; PcaChainHistoryDelete(unsigned __int64)
0x1800ecf34  jmp     short loc_1800ECF3D
0x1800ecf36  mov     [r12], r14
0x1800ecf3a  mov     esi, r13d
0x1800ecf3d  mov     rcx, [rsp+2C0h+phkResult]; hKey
0x1800ecf42  test    rcx, rcx
0x1800ecf45  jz      short loc_1800ECF4D
0x1800ecf47  call    cs:__imp_RegCloseKey
0x1800ecf4d  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800ecf52  test    rcx, rcx
0x1800ecf55  jz      short loc_1800ECF5D
0x1800ecf57  call    cs:__imp_RegCloseKey
0x1800ecf5d  mov     eax, esi
0x1800ecf5f  mov     rcx, [rbp+1C0h+var_50]
0x1800ecf66  xor     rcx, rsp; StackCookie
0x1800ecf69  call    __security_check_cookie
0x1800ecf6e  add     rsp, 288h
0x1800ecf75  pop     r15
0x1800ecf77  pop     r14
0x1800ecf79  pop     r13
0x1800ecf7b  pop     r12
0x1800ecf7d  pop     rdi
0x1800ecf7e  pop     rsi
0x1800ecf7f  pop     rbx
0x1800ecf80  pop     rbp
0x1800ecf81  retn
```
