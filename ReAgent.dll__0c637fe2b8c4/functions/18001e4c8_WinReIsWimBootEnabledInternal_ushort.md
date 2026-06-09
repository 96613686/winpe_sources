# WinReIsWimBootEnabledInternal(ushort *)

- ea: `0x18001e4c8`
- end: `0x18001e866`
- name: `?WinReIsWimBootEnabledInternal@@YAHPEAG@Z`
- size: `926`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `7`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x180018870`
- `0x180020478`
- `0x180024770`
- `0x180025a60`
- `0x18002dd30`
- `0x180036c38`
- `0x180039dd4`

## callees

- `0x1800059fc`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x18001e4c8`
- `0x180030b98`
- `0x180031238`
- `0x18004f8d0`
- `0x18005cee2`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001e7cf`
- `KERNEL32!GetLastError` at `0x18001e7cf`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18001e55d`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x18001e55d`
- `KERNEL32!GetVersionExW` at `0x18001e5af`
- `KERNEL32!GetVersionExW` at `0x18001e5af`
- `ADVAPI32!RegOpenKeyExW` at `0x18001e740`
- `ADVAPI32!RegOpenKeyExW` at `0x18001e77c`
- `ADVAPI32!RegOpenKeyExW` at `0x18001e740`
- `ADVAPI32!RegOpenKeyExW` at `0x18001e77c`
- `ADVAPI32!RegCloseKey` at `0x18001e808`
- `ADVAPI32!RegCloseKey` at `0x18001e821`
- `ADVAPI32!RegCloseKey` at `0x18001e808`
- `ADVAPI32!RegCloseKey` at `0x18001e821`
- `ADVAPI32!RegUnLoadKeyW` at `0x18001e83f`
- `ADVAPI32!RegUnLoadKeyW` at `0x18001e83f`
- `ADVAPI32!RegLoadKeyW` at `0x18001e6f2`
- `ADVAPI32!RegLoadKeyW` at `0x18001e6f2`
- `ADVAPI32!RegGetValueW` at `0x18001e7b3`
- `ADVAPI32!RegGetValueW` at `0x18001e7b3`

## string_xrefs

- `0x18001e593`: `Failed to check whether %s is the current Windows directory`
- `0x18001e5dc`: `Failed to get system windows directory`
- `0x18001e66b`: `System32\config\SYSTEM`
- `0x18001e6cb`: `AppendPath failed. Error: 0x%x.`
- `0x18001e74a`: `RegOpenKeyEx failed. Error: 0x%x.`

## pseudocode

```c
__int64 __fastcall WinReIsWimBootEnabledInternal(LPCWSTR lpFileName)
{
  int v2; // r14d
  unsigned int v4; // edi
  int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  const unsigned __int16 *v8; // r8
  unsigned int v9; // eax
  unsigned int v10; // eax
  unsigned int ValueW; // eax
  DWORD LastError; // eax
  unsigned __int64 v13; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  int pvData; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcbData; // [rsp+5Ch] [rbp-A4h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v20[606]; // [rsp+182h] [rbp+82h] BYREF

  hKey = 0;
  hkey = 0;
  v2 = 0;
  pcbData = 4;
  pvData = 0;
  memset_0(&VersionInformation, 0, sizeof(VersionInformation));
  if ( lpFileName )
  {
    Buffer = 0;
    memset_0(v20, 0, 0x206u);
    if ( GetSystemWindowsDirectoryW(&Buffer, 0x104u) )
    {
      LODWORD(v13) = 0;
      if ( !(unsigned int)winreArePathsEqual(lpFileName, &Buffer) )
        UnattendLogW(2, L"Failed to check whether %s is the current Windows directory", &Buffer);
    }
    else
    {
      UnattendLogW(2, L"Failed to get system windows directory");
    }
    Buffer = 0;
    v4 = 0;
    memset_0(v20, 0, 0x25Au);
    v13 = 0;
    v5 = StringCchLengthW(lpFileName, 0x7FFFFFFFu, &v13);
    if ( v5 >= 0 )
    {
      if ( !v13 || (v8 = L"%s\\%s", lpFileName[v13 - 1] == 92) )
        v8 = L"%s%s";
      v5 = StringCchPrintfW(&Buffer, 0x12Eu, v8, lpFileName, L"System32\\config\\SYSTEM");
      if ( v5 >= 0 )
        goto LABEL_25;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v7 = 15;
        goto LABEL_22;
      }
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v7 = 14;
LABEL_22:
        WPP_SF_d(v6[2], v7, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v5);
      }
    }
    if ( (_WORD)v5 )
    {
      UnattendLogW(1, L"AppendPath failed. Error: 0x%x.");
      goto LABEL_37;
    }
LABEL_25:
    v9 = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"$OFFLINE$SYSTEM", &Buffer);
    if ( v9 )
    {
      UnattendLogW(0, L"RegLoadKey %s failed. Error: 0x%x.", L"$OFFLINE$SYSTEM", v9);
    }
    else
    {
      v2 = 1;
      v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"$OFFLINE$SYSTEM", 0, 0x20019u, &hKey);
      if ( v10 || (v10 = RegOpenKeyExW(hKey, L"Setup", 0, 0x20019u, &hkey)) != 0 )
      {
        UnattendLogW(0, L"RegOpenKeyEx failed. Error: 0x%x.", v10);
      }
      else
      {
        ValueW = RegGetValueW(hkey, 0, L"Wimboot", 0x18u, 0, &pvData, &pcbData);
        if ( ValueW )
        {
          UnattendLogW(0, L"RegGetValue failed. Error: 0x%x.", ValueW);
        }
        else if ( pvData )
        {
          v4 = 1;
        }
      }
    }
    goto LABEL_37;
  }
  VersionInformation.dwOSVersionInfoSize = 276;
  if ( GetVersionExW(&VersionInformation) )
  {
    if ( VersionInformation.dwMajorVersion > 6
      || VersionInformation.dwMajorVersion == 6 && VersionInformation.dwMinorVersion > 3 )
    {
      return 0;
    }
  }
  else
  {
    LastError = GetLastError();
    UnattendLogW(1, L"GetVersionEx failed. Error: 0x%x.", LastError);
  }
  v4 = CheckRegKey(L"SYSTEM\\Setup", L"Wimboot");
LABEL_37:
  if ( hkey )
  {
    RegCloseKey(hkey);
    hkey = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v2 )
    RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"$OFFLINE$SYSTEM");
  return v4;
}

```

## disassembly

```asm
0x18001e4c8  push    rbp
0x18001e4ca  push    rbx
0x18001e4cb  push    rsi
0x18001e4cc  push    rdi
0x18001e4cd  push    r13
0x18001e4cf  push    r14
0x18001e4d1  lea     rbp, [rsp-2F8h]
0x18001e4d9  sub     rsp, 3F8h
0x18001e4e0  mov     rax, cs:__security_cookie
0x18001e4e7  xor     rax, rsp
0x18001e4ea  mov     [rbp+320h+var_40], rax
0x18001e4f1  mov     rsi, rcx
0x18001e4f4  mov     [rsp+420h+hKey], 0
0x18001e4fd  mov     edi, 114h
0x18001e502  mov     [rsp+420h+hkey], 0
0x18001e50b  xor     r14d, r14d
0x18001e50e  mov     [rsp+420h+var_3C4], 4
0x18001e516  mov     r8d, edi; Size
0x18001e519  mov     [rsp+420h+var_3C8], r14d
0x18001e51e  xor     edx, edx; Val
0x18001e520  lea     rcx, [rsp+420h+VersionInformation]; void *
0x18001e525  call    memset_0
0x18001e52a  mov     r13, 0FFFFFFFF80000002h
0x18001e531  test    rsi, rsi
0x18001e534  jz      short loc_18001E5A6
0x18001e536  xor     eax, eax
0x18001e538  lea     rcx, [rbp+320h+var_29E]; void *
0x18001e53f  xor     edx, edx; Val
0x18001e541  mov     [rbp+320h+Buffer], ax
0x18001e548  mov     r8d, 206h; Size
0x18001e54e  call    memset_0
0x18001e553  lea     edx, [rdi-10h]; uSize
0x18001e556  lea     rcx, [rbp+320h+Buffer]; lpBuffer
0x18001e55d  call    cs:__imp_GetSystemWindowsDirectoryW
0x18001e563  test    eax, eax
0x18001e565  jz      short loc_18001E5DC
0x18001e567  lea     r8, [rsp+420h+var_3E0]
0x18001e56c  mov     dword ptr [rsp+420h+var_3E0], r14d
0x18001e571  lea     rdx, [rbp+320h+Buffer]; LPCWSTR
0x18001e578  mov     rcx, rsi; lpFileName
0x18001e57b  call    winreArePathsEqual
0x18001e580  test    eax, eax
0x18001e582  jz      short loc_18001E58A
0x18001e584  mov     ebx, dword ptr [rsp+420h+var_3E0]
0x18001e588  jmp     short loc_18001E5A2
0x18001e58a  xor     ebx, ebx
0x18001e58c  lea     r8, [rbp+320h+Buffer]
0x18001e593  lea     rdx, aFailedToCheckW_1; "Failed to check whether %s is the curre"...
0x18001e59a  lea     ecx, [rbx+2]
0x18001e59d  call    UnattendLogW
0x18001e5a2  test    ebx, ebx
0x18001e5a4  jz      short loc_18001E5ED
0x18001e5a6  lea     rcx, [rsp+420h+VersionInformation]; lpVersionInformation
0x18001e5ab  mov     [rsp+420h+VersionInformation.dwOSVersionInfoSize], edi
0x18001e5af  call    cs:__imp_GetVersionExW
0x18001e5b5  test    eax, eax
0x18001e5b7  jz      loc_18001E7CF
0x18001e5bd  cmp     [rsp+420h+VersionInformation.dwMajorVersion], 6
0x18001e5c2  ja      short loc_18001E5D5
0x18001e5c4  jnz     loc_18001E7E9
0x18001e5ca  cmp     [rsp+420h+VersionInformation.dwMinorVersion], 3
0x18001e5cf  jbe     loc_18001E7E9
0x18001e5d5  xor     eax, eax
0x18001e5d7  jmp     loc_18001E847
0x18001e5dc  lea     rdx, aFailedToGetSys; "Failed to get system windows directory"
0x18001e5e3  mov     ecx, 2
0x18001e5e8  call    UnattendLogW
0x18001e5ed  xor     eax, eax
0x18001e5ef  lea     rcx, [rbp+320h+var_29E]; void *
0x18001e5f6  xor     edx, edx; Val
0x18001e5f8  mov     [rbp+320h+Buffer], ax
0x18001e5ff  mov     r8d, 25Ah; Size
0x18001e605  xor     edi, edi
0x18001e607  call    memset_0
0x18001e60c  lea     r8, [rsp+420h+var_3E0]; unsigned __int64 *
0x18001e611  mov     [rsp+420h+var_3E0], rdi
0x18001e616  mov     edx, 7FFFFFFFh; unsigned __int64
0x18001e61b  mov     rcx, rsi; unsigned __int16 *
0x18001e61e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001e623  mov     ebx, eax
0x18001e625  test    eax, eax
0x18001e627  jns     short loc_18001E64B
0x18001e629  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e630  lea     rax, WPP_GLOBAL_Control
0x18001e637  cmp     rcx, rax
0x18001e63a  jz      loc_18001E6C2
0x18001e640  test    byte ptr [rcx+1Ch], 2
0x18001e644  jz      short loc_18001E6C2
0x18001e646  lea     edx, [rdi+0Eh]
0x18001e649  jmp     short loc_18001E6AF
0x18001e64b  mov     rax, [rsp+420h+var_3E0]
0x18001e650  test    rax, rax
0x18001e653  jz      short loc_18001E664
0x18001e655  cmp     word ptr [rsi+rax*2-2], 5Ch ; '\'
0x18001e65b  lea     r8, aSS_1; "%s\\%s"
0x18001e662  jnz     short loc_18001E66B
0x18001e664  lea     r8, aSS_2; "%s%s"
0x18001e66b  lea     rax, aSystem32Config; "System32\\config\\SYSTEM"
0x18001e672  mov     r9, rsi
0x18001e675  mov     edx, 12Eh; unsigned __int64
0x18001e67a  mov     [rsp+420h+phkResult], rax
0x18001e67f  lea     rcx, [rbp+320h+Buffer]; unsigned __int16 *
0x18001e686  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e68b  mov     ebx, eax
0x18001e68d  test    eax, eax
0x18001e68f  jns     short loc_18001E6E1
0x18001e691  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e698  lea     rax, WPP_GLOBAL_Control
0x18001e69f  cmp     rcx, rax
0x18001e6a2  jz      short loc_18001E6C2
0x18001e6a4  test    byte ptr [rcx+1Ch], 2
0x18001e6a8  jz      short loc_18001E6C2
0x18001e6aa  mov     edx, 0Fh
0x18001e6af  mov     rcx, [rcx+10h]
0x18001e6b3  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18001e6ba  mov     r9d, ebx
0x18001e6bd  call    WPP_SF_d
0x18001e6c2  movzx   r8d, bx
0x18001e6c6  test    r8d, r8d
0x18001e6c9  jz      short loc_18001E6E1
0x18001e6cb  lea     rdx, aAppendpathFail_0; "AppendPath failed. Error: 0x%x."
0x18001e6d2  mov     ecx, 1
0x18001e6d7  call    UnattendLogW
0x18001e6dc  jmp     loc_18001E7FE
0x18001e6e1  lea     r8, [rbp+320h+Buffer]; lpFile
0x18001e6e8  mov     rcx, r13; hKey
0x18001e6eb  lea     rdx, aOfflineSystem; "$OFFLINE$SYSTEM"
0x18001e6f2  call    cs:__imp_RegLoadKeyW
0x18001e6f8  test    eax, eax
0x18001e6fa  jz      short loc_18001E719
0x18001e6fc  mov     r9d, eax
0x18001e6ff  lea     r8, aOfflineSystem; "$OFFLINE$SYSTEM"
0x18001e706  lea     rdx, aRegloadkeySFai; "RegLoadKey %s failed. Error: 0x%x."
0x18001e70d  xor     ecx, ecx
0x18001e70f  call    UnattendLogW
0x18001e714  jmp     loc_18001E7FE
0x18001e719  lea     rax, [rsp+420h+hKey]
0x18001e71e  mov     esi, 20019h
0x18001e723  mov     ebx, 1
0x18001e728  mov     [rsp+420h+phkResult], rax; phkResult
0x18001e72d  mov     r9d, esi; samDesired
0x18001e730  lea     rdx, aOfflineSystem; "$OFFLINE$SYSTEM"
0x18001e737  xor     r8d, r8d; ulOptions
0x18001e73a  mov     rcx, r13; hKey
0x18001e73d  mov     r14d, ebx
0x18001e740  call    cs:__imp_RegOpenKeyExW
0x18001e746  test    eax, eax
0x18001e748  jz      short loc_18001E760
0x18001e74a  lea     rdx, aRegopenkeyexFa; "RegOpenKeyEx failed. Error: 0x%x."
0x18001e751  mov     r8d, eax
0x18001e754  xor     ecx, ecx
0x18001e756  call    UnattendLogW
0x18001e75b  jmp     loc_18001E7FE
0x18001e760  mov     rcx, [rsp+420h+hKey]; hKey
0x18001e765  lea     rax, [rsp+420h+hkey]
0x18001e76a  mov     r9d, esi; samDesired
0x18001e76d  mov     [rsp+420h+phkResult], rax; phkResult
0x18001e772  xor     r8d, r8d; ulOptions
0x18001e775  lea     rdx, aSetup; "Setup"
0x18001e77c  call    cs:__imp_RegOpenKeyExW
0x18001e782  test    eax, eax
0x18001e784  jnz     short loc_18001E74A
0x18001e786  mov     rcx, [rsp+420h+hkey]; hkey
0x18001e78b  lea     rax, [rsp+420h+var_3C4]
0x18001e790  mov     [rsp+420h+pcbData], rax; pcbData
0x18001e795  lea     r8, Value; "Wimboot"
0x18001e79c  lea     rax, [rsp+420h+var_3C8]
0x18001e7a1  mov     r9d, 18h; dwFlags
0x18001e7a7  mov     [rsp+420h+pvData], rax; pvData
0x18001e7ac  xor     edx, edx; lpSubKey
0x18001e7ae  mov     [rsp+420h+phkResult], rdi; pdwType
0x18001e7b3  call    cs:__imp_RegGetValueW
0x18001e7b9  test    eax, eax
0x18001e7bb  jz      short loc_18001E7C6
0x18001e7bd  lea     rdx, aReggetvalueFai; "RegGetValue failed. Error: 0x%x."
0x18001e7c4  jmp     short loc_18001E751
0x18001e7c6  cmp     [rsp+420h+var_3C8], edi
0x18001e7ca  cmova   edi, ebx
0x18001e7cd  jmp     short loc_18001E7FE
0x18001e7cf  call    cs:__imp_GetLastError
0x18001e7d5  lea     rdx, aGetversionexFa; "GetVersionEx failed. Error: 0x%x."
0x18001e7dc  mov     ecx, 1
0x18001e7e1  mov     r8d, eax
0x18001e7e4  call    UnattendLogW
0x18001e7e9  lea     rdx, Value; "Wimboot"
0x18001e7f0  lea     rcx, aSystemSetup; "SYSTEM\\Setup"
0x18001e7f7  call    CheckRegKey
0x18001e7fc  mov     edi, eax
0x18001e7fe  mov     rcx, [rsp+420h+hkey]; hKey
0x18001e803  test    rcx, rcx
0x18001e806  jz      short loc_18001E817
0x18001e808  call    cs:__imp_RegCloseKey
0x18001e80e  mov     [rsp+420h+hkey], 0
0x18001e817  mov     rcx, [rsp+420h+hKey]; hKey
0x18001e81c  test    rcx, rcx
0x18001e81f  jz      short loc_18001E830
0x18001e821  call    cs:__imp_RegCloseKey
0x18001e827  mov     [rsp+420h+hKey], 0
0x18001e830  test    r14d, r14d
0x18001e833  jz      short loc_18001E845
0x18001e835  lea     rdx, aOfflineSystem; "$OFFLINE$SYSTEM"
0x18001e83c  mov     rcx, r13; hKey
0x18001e83f  call    cs:__imp_RegUnLoadKeyW
0x18001e845  mov     eax, edi
0x18001e847  mov     rcx, [rbp+320h+var_40]
0x18001e84e  xor     rcx, rsp; StackCookie
0x18001e851  call    __security_check_cookie
0x18001e856  add     rsp, 3F8h
0x18001e85d  pop     r14
0x18001e85f  pop     r13
0x18001e861  pop     rdi
0x18001e862  pop     rsi
0x18001e863  pop     rbx
0x18001e864  pop     rbp
0x18001e865  retn
```
