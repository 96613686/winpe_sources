# IsClientEdition(_GUID *,int *)

- ea: `0x180037780`
- end: `0x180037caf`
- name: `?IsClientEdition@@YAKPEAU_GUID@@PEAH@Z`
- size: `1327`
- prototype: `__int64 __fastcall(struct _GUID *, int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800170a4`
- `0x180036c38`

## callees

- `0x1800059fc`
- `0x18000c6c0`
- `0x18000c6f0`
- `0x180031238`
- `0x180031fa4`
- `0x180037780`
- `0x18004d2fc`
- `0x18004d584`
- `0x18004f8d0`
- `0x18005cee2`
- `0x18005cefa`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180037883`
- `KERNEL32!GetLastError` at `0x1800378b1`
- `KERNEL32!GetLastError` at `0x180037bdd`
- `KERNEL32!GetLastError` at `0x180037883`
- `KERNEL32!GetLastError` at `0x1800378b1`
- `KERNEL32!GetLastError` at `0x180037bdd`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180037879`
- `KERNEL32!GetSystemWindowsDirectoryW` at `0x180037879`
- `KERNEL32!GetVersionExW` at `0x180037bc5`
- `KERNEL32!GetVersionExW` at `0x180037bc5`
- `ADVAPI32!RegOpenKeyExW` at `0x180037afd`
- `ADVAPI32!RegOpenKeyExW` at `0x180037b3b`
- `ADVAPI32!RegOpenKeyExW` at `0x180037afd`
- `ADVAPI32!RegOpenKeyExW` at `0x180037b3b`
- `ADVAPI32!RegCloseKey` at `0x180037c0a`
- `ADVAPI32!RegCloseKey` at `0x180037c23`
- `ADVAPI32!RegCloseKey` at `0x180037c0a`
- `ADVAPI32!RegCloseKey` at `0x180037c23`
- `ADVAPI32!RegUnLoadKeyW` at `0x180037c44`
- `ADVAPI32!RegUnLoadKeyW` at `0x180037c44`
- `ADVAPI32!RegLoadKeyW` at `0x180037aae`
- `ADVAPI32!RegLoadKeyW` at `0x180037aae`
- `ADVAPI32!RegGetValueW` at `0x180037b78`
- `ADVAPI32!RegGetValueW` at `0x180037b78`

## string_xrefs

- `0x180037a8d`: `AppendPath failed. Error: 0x%x.`
- `0x180037b09`: `RegOpenKeyEx failed. Error: 0x%x.`
- `0x180037889`: `Failed to System Windows Directory. Error: 0x%08X`
- `0x1800378b7`: `Failed to compare Windows Directories. Error: 0x%08X`
- `0x18003793b`: `InstallationType`
- `0x18003796c`: `Failed to enable backup privilege`
- `0x180037998`: `Failed to enable restore privilege`
- `0x180037a2a`: `System32\config\Software`

## pseudocode

```c
__int64 __fastcall IsClientEdition(struct _GUID *a1, int *a2)
{
  int v4; // esi
  unsigned int WinDir; // eax
  int v6; // ebx
  DWORD LastError; // eax
  const wchar_t *v8; // rdx
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  const unsigned __int16 *v11; // r8
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int ValueW; // eax
  int v15; // eax
  int v16; // ecx
  bool v17; // zf
  unsigned int KeyW; // eax
  int v20; // [rsp+40h] [rbp-C0h] BYREF
  int v21; // [rsp+44h] [rbp-BCh] BYREF
  unsigned __int64 v22; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcbData[4]; // [rsp+60h] [rbp-A0h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+70h] [rbp-90h] BYREF
  char v27; // [rsp+18Ah] [rbp+8Ah]
  WCHAR SubKey[20]; // [rsp+190h] [rbp+90h] BYREF
  WCHAR Value[20]; // [rsp+1B8h] [rbp+B8h] BYREF
  WCHAR v30[40]; // [rsp+1E0h] [rbp+E0h] BYREF
  WCHAR Buffer; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v32[606]; // [rsp+232h] [rbp+132h] BYREF
  WCHAR FileName[304]; // [rsp+490h] [rbp+390h] BYREF
  wchar_t String1[304]; // [rsp+6F0h] [rbp+5F0h] BYREF

  pcbData[0] = 0;
  v4 = 0;
  hKey = 0;
  hkey = 0;
  memset_0(&VersionInformation, 0, 0x11Cu);
  memset_0(FileName, 0, 0x25Cu);
  v20 = 1;
  wcscpy(SubKey, L"$OFFLINE$SOFTWARE");
  v21 = 1;
  WinDir = winreGetWinDir(a1, FileName);
  v6 = WinDir;
  if ( WinDir )
  {
    UnattendLogW(1, L"Failed to get WinDir from target OS Guid. Error: 0x%08X", WinDir);
    goto LABEL_41;
  }
  if ( a1 )
  {
    memset_0(&Buffer, 0, 0x25Cu);
    if ( !GetSystemWindowsDirectoryW(&Buffer, 0x12Eu) )
    {
      LastError = GetLastError();
      v8 = L"Failed to System Windows Directory. Error: 0x%08X";
      goto LABEL_39;
    }
    if ( !(unsigned int)winreArePathsEqual(FileName, &Buffer) )
    {
      LastError = GetLastError();
      v8 = L"Failed to compare Windows Directories. Error: 0x%08X";
      goto LABEL_39;
    }
    wcscpy(v30, L"Microsoft\\Windows NT\\CurrentVersion");
    wcscpy(Value, L"InstallationType");
    memset_0(String1, 0, 0x25Cu);
    pcbData[0] = 604;
    if ( !(unsigned int)Utils::EnablePrivilege(0x11u, &v20) )
    {
      UnattendLogW(1, L"Failed to enable backup privilege");
LABEL_10:
      v6 = 1314;
      goto LABEL_41;
    }
    if ( !(unsigned int)Utils::EnablePrivilege(0x12u, &v21) )
    {
      UnattendLogW(1, L"Failed to enable restore privilege");
      goto LABEL_10;
    }
    Buffer = 0;
    memset_0(v32, 0, 0x25Au);
    v22 = 0;
    v6 = StringCchLengthW(FileName, 0x7FFFFFFFu, &v22);
    if ( v6 >= 0 )
    {
      if ( !v22 || (v11 = L"%s\\%s", *(_WORD *)&v32[2 * v22 + 604] == 92) )
        v11 = L"%s%s";
      v6 = StringCchPrintfW(&Buffer, 0x12Eu, v11, FileName, L"System32\\config\\Software");
      if ( v6 >= 0 )
      {
LABEL_27:
        v12 = RegLoadKeyW(HKEY_LOCAL_MACHINE, SubKey, &Buffer);
        v6 = v12;
        if ( v12 )
        {
          UnattendLogW(0, L"RegLoadKey %s failed. Error: 0x%x.", SubKey, v12);
          goto LABEL_41;
        }
        v4 = 1;
        v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
        v6 = v13;
        if ( v13 || (v13 = RegOpenKeyExW(hKey, v30, 0, 0x20019u, &hkey), (v6 = v13) != 0) )
        {
          UnattendLogW(0, L"RegOpenKeyEx failed. Error: 0x%x.", v13);
          goto LABEL_41;
        }
        ValueW = RegGetValueW(hkey, 0, Value, 2u, 0, String1, pcbData);
        v6 = ValueW;
        if ( ValueW )
        {
          UnattendLogW(0, L"RegGetValue failed. Error: 0x%x.", ValueW);
          goto LABEL_41;
        }
        v15 = wcscmp_0(String1, L"Client");
        v16 = 0;
        v17 = v15 == 0;
        goto LABEL_37;
      }
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v10 = 15;
        goto LABEL_24;
      }
    }
    else
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v10 = 14;
LABEL_24:
        WPP_SF_d(v9[2], v10, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, (unsigned int)v6);
      }
    }
    v6 = (unsigned __int16)v6;
    if ( (_WORD)v6 )
    {
      UnattendLogW(1, L"AppendPath failed. Error: 0x%x.", (unsigned __int16)v6);
      goto LABEL_41;
    }
    goto LABEL_27;
  }
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( !GetVersionExW(&VersionInformation) )
  {
    LastError = GetLastError();
    v8 = L"Failed to get online OS version info. Error: 0x%08X";
LABEL_39:
    v6 = LastError;
    UnattendLogW(1, v8, LastError);
    v16 = 0;
    if ( v6 )
      goto LABEL_41;
    goto LABEL_40;
  }
  v16 = 0;
  v17 = v27 == 1;
LABEL_37:
  LOBYTE(v16) = v17;
LABEL_40:
  *a2 = v16;
LABEL_41:
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
  if ( v4 )
  {
    KeyW = RegUnLoadKeyW(HKEY_LOCAL_MACHINE, SubKey);
    if ( KeyW )
      UnattendLogW(2, L"RegUnloadKey [%s] failed. Error: 0x%x.", SubKey, KeyW);
  }
  Utils::DisablePrivilege(0x11u, &v20);
  Utils::DisablePrivilege(0x12u, &v21);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180037780  mov     [rsp-8+arg_10], rbx
0x180037785  push    rbp
0x180037786  push    rsi
0x180037787  push    rdi
0x180037788  push    r12
0x18003778a  push    r14
0x18003778c  lea     rbp, [rsp-860h]
0x180037794  sub     rsp, 960h
0x18003779b  mov     rax, cs:__security_cookie
0x1800377a2  xor     rax, rsp
0x1800377a5  mov     [rbp+880h+var_30], rax
0x1800377ac  mov     r14, rdx
0x1800377af  mov     [rsp+980h+var_920], 0
0x1800377b7  mov     rdi, rcx
0x1800377ba  xor     esi, esi
0x1800377bc  xor     edx, edx; Val
0x1800377be  mov     [rsp+980h+hKey], rsi
0x1800377c3  lea     rcx, [rsp+980h+VersionInformation]; void *
0x1800377c8  mov     [rsp+980h+hkey], rsi
0x1800377cd  mov     r8d, 11Ch; Size
0x1800377d3  call    memset_0
0x1800377d8  xor     edx, edx; Val
0x1800377da  lea     rcx, [rbp+880h+FileName]; void *
0x1800377e1  mov     r8d, 25Ch; Size
0x1800377e7  call    memset_0
0x1800377ec  movups  xmm0, xmmword ptr cs:aOfflineSoftwar; "$OFFLINE$SOFTWARE"
0x1800377f3  mov     eax, dword ptr cs:aOfflineSoftwar+20h; "E"
0x1800377f9  lea     r12d, [rsi+1]
0x1800377fd  movups  xmm1, xmmword ptr cs:aOfflineSoftwar+10h; "$SOFTWARE"
0x180037804  lea     rdx, [rbp+880h+FileName]
0x18003780b  mov     [rbp+880h+var_7D0], eax
0x180037811  mov     rcx, rdi
0x180037814  mov     [rsp+980h+var_940], r12d
0x180037819  movups  xmmword ptr [rbp+880h+SubKey], xmm0
0x180037820  mov     [rsp+980h+var_93C], r12d
0x180037825  movups  [rbp+880h+var_7E0], xmm1
0x18003782c  call    winreGetWinDir
0x180037831  mov     ebx, eax
0x180037833  test    eax, eax
0x180037835  jz      short loc_18003784E
0x180037837  mov     r8d, eax
0x18003783a  lea     rdx, aFailedToGetWin_12; "Failed to get WinDir from target OS Gui"...
0x180037841  mov     ecx, r12d
0x180037844  call    UnattendLogW
0x180037849  jmp     loc_180037C00
0x18003784e  test    rdi, rdi
0x180037851  jz      loc_180037BA6
0x180037857  xor     edx, edx; Val
0x180037859  lea     rcx, [rbp+880h+Buffer]; void *
0x180037860  mov     r8d, 25Ch; Size
0x180037866  call    memset_0
0x18003786b  mov     edi, 12Eh
0x180037870  lea     rcx, [rbp+880h+Buffer]; lpBuffer
0x180037877  mov     edx, edi; uSize
0x180037879  call    cs:__imp_GetSystemWindowsDirectoryW
0x18003787f  test    eax, eax
0x180037881  jnz     short loc_180037895
0x180037883  call    cs:__imp_GetLastError
0x180037889  lea     rdx, aFailedToSystem; "Failed to System Windows Directory. Err"...
0x180037890  jmp     loc_180037BEA
0x180037895  lea     r8, [rsp+980h+var_920]
0x18003789a  lea     rdx, [rbp+880h+Buffer]; LPCWSTR
0x1800378a1  lea     rcx, [rbp+880h+FileName]; lpFileName
0x1800378a8  call    winreArePathsEqual
0x1800378ad  test    eax, eax
0x1800378af  jnz     short loc_1800378C3
0x1800378b1  call    cs:__imp_GetLastError
0x1800378b7  lea     rdx, aFailedToCompar; "Failed to compare Windows Directories. "...
0x1800378be  jmp     loc_180037BEA
0x1800378c3  cmp     [rsp+980h+var_920], esi
0x1800378c7  jnz     loc_180037BA6
0x1800378cd  movaps  xmm0, xmmword ptr cs:aMicrosoftWindo_2; "Microsoft\\Windows NT\\CurrentVersion"
0x1800378d4  lea     rcx, [rbp+880h+String1]; void *
0x1800378db  movaps  xmm1, xmmword ptr cs:aMicrosoftWindo_2+10h; "t\\Windows NT\\CurrentVersion"
0x1800378e2  mov     ebx, 25Ch
0x1800378e7  movzx   eax, word ptr cs:aInstallationty+20h; ""
0x1800378ee  mov     r8d, ebx; Size
0x1800378f1  movaps  xmmword ptr [rbp+880h+var_7A0], xmm0
0x1800378f8  xor     edx, edx; Val
0x1800378fa  movaps  xmm0, xmmword ptr cs:aMicrosoftWindo_2+20h; "s NT\\CurrentVersion"
0x180037901  movaps  [rbp+880h+var_780], xmm0
0x180037908  movsd   xmm0, qword ptr cs:aMicrosoftWindo_2+40h; "ion"
0x180037910  movaps  xmmword ptr [rbp+0F0h], xmm1
0x180037917  movaps  xmm1, xmmword ptr cs:aMicrosoftWindo_2+30h; "rentVersion"
0x18003791e  movsd   [rbp+880h+var_760], xmm0
0x180037926  movups  xmm0, xmmword ptr cs:aInstallationty+10h; "tionType"
0x18003792d  mov     [rbp+880h+var_7A8], ax
0x180037934  movaps  [rbp+880h+var_770], xmm1
0x18003793b  movups  xmm1, xmmword ptr cs:aInstallationty; "InstallationType"
0x180037942  movups  [rbp+880h+var_7B8], xmm0
0x180037949  movups  xmmword ptr [rbp+880h+Value], xmm1
0x180037950  call    memset_0
0x180037955  lea     rdx, [rsp+980h+var_940]; int *
0x18003795a  mov     [rsp+980h+var_920], ebx
0x18003795e  mov     ecx, 11h; unsigned int
0x180037963  call    ?EnablePrivilege@Utils@@SAHKPEAH@Z; Utils::EnablePrivilege(ulong,int *)
0x180037968  test    eax, eax
0x18003796a  jnz     short loc_180037985
0x18003796c  lea     rdx, aFailedToEnable_0; "Failed to enable backup privilege"
0x180037973  mov     ecx, r12d
0x180037976  call    UnattendLogW
0x18003797b  mov     ebx, 522h
0x180037980  jmp     loc_180037C00
0x180037985  lea     rdx, [rsp+980h+var_93C]; int *
0x18003798a  mov     ecx, 12h; unsigned int
0x18003798f  call    ?EnablePrivilege@Utils@@SAHKPEAH@Z; Utils::EnablePrivilege(ulong,int *)
0x180037994  test    eax, eax
0x180037996  jnz     short loc_1800379A1
0x180037998  lea     rdx, aFailedToEnable; "Failed to enable restore privilege"
0x18003799f  jmp     short loc_180037973
0x1800379a1  xor     eax, eax
0x1800379a3  lea     rcx, [rbp+880h+var_74E]; void *
0x1800379aa  xor     edx, edx; Val
0x1800379ac  mov     [rbp+880h+Buffer], ax
0x1800379b3  mov     r8d, 25Ah; Size
0x1800379b9  call    memset_0
0x1800379be  lea     r8, [rsp+980h+var_938]; unsigned __int64 *
0x1800379c3  mov     [rsp+980h+var_938], rsi
0x1800379c8  mov     edx, 7FFFFFFFh; unsigned __int64
0x1800379cd  lea     rcx, [rbp+880h+FileName]; unsigned __int16 *
0x1800379d4  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800379d9  mov     ebx, eax
0x1800379db  test    eax, eax
0x1800379dd  jns     short loc_180037A07
0x1800379df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800379e6  lea     rax, WPP_GLOBAL_Control
0x1800379ed  cmp     rcx, rax
0x1800379f0  jz      loc_180037A83
0x1800379f6  test    byte ptr [rcx+1Ch], 2
0x1800379fa  jz      loc_180037A83
0x180037a00  mov     edx, 0Eh
0x180037a05  jmp     short loc_180037A70
0x180037a07  mov     rax, [rsp+980h+var_938]
0x180037a0c  test    rax, rax
0x180037a0f  jz      short loc_180037A23
0x180037a11  cmp     [rbp+rax*2+880h+var_4F2], 5Ch ; '\'
0x180037a1a  lea     r8, aSS_1; "%s\\%s"
0x180037a21  jnz     short loc_180037A2A
0x180037a23  lea     r8, aSS_2; "%s%s"
0x180037a2a  lea     rax, aSystem32Config_3; "System32\\config\\Software"
0x180037a31  mov     rdx, rdi; unsigned __int64
0x180037a34  lea     r9, [rbp+880h+FileName]
0x180037a3b  mov     [rsp+980h+phkResult], rax
0x180037a40  lea     rcx, [rbp+880h+Buffer]; unsigned __int16 *
0x180037a47  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037a4c  mov     ebx, eax
0x180037a4e  test    eax, eax
0x180037a50  jns     short loc_180037A99
0x180037a52  mov     rcx, cs:WPP_GLOBAL_Control
0x180037a59  lea     rax, WPP_GLOBAL_Control
0x180037a60  cmp     rcx, rax
0x180037a63  jz      short loc_180037A83
0x180037a65  test    byte ptr [rcx+1Ch], 2
0x180037a69  jz      short loc_180037A83
0x180037a6b  mov     edx, 0Fh
0x180037a70  mov     rcx, [rcx+10h]
0x180037a74  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x180037a7b  mov     r9d, ebx
0x180037a7e  call    WPP_SF_d
0x180037a83  movzx   ebx, bx
0x180037a86  test    ebx, ebx
0x180037a88  jz      short loc_180037A99
0x180037a8a  mov     r8d, ebx
0x180037a8d  lea     rdx, aAppendpathFail_0; "AppendPath failed. Error: 0x%x."
0x180037a94  jmp     loc_180037841
0x180037a99  lea     r8, [rbp+880h+Buffer]; lpFile
0x180037aa0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037aa7  lea     rdx, [rbp+880h+SubKey]; lpSubKey
0x180037aae  call    cs:__imp_RegLoadKeyW
0x180037ab4  mov     ebx, eax
0x180037ab6  test    eax, eax
0x180037ab8  jz      short loc_180037AD7
0x180037aba  mov     r9d, eax
0x180037abd  lea     r8, [rbp+880h+SubKey]
0x180037ac4  lea     rdx, aRegloadkeySFai; "RegLoadKey %s failed. Error: 0x%x."
0x180037acb  xor     ecx, ecx
0x180037acd  call    UnattendLogW
0x180037ad2  jmp     loc_180037C00
0x180037ad7  lea     rax, [rsp+980h+hKey]
0x180037adc  mov     edi, 20019h
0x180037ae1  mov     r9d, edi; samDesired
0x180037ae4  mov     [rsp+980h+phkResult], rax; phkResult
0x180037ae9  xor     r8d, r8d; ulOptions
0x180037aec  lea     rdx, [rbp+880h+SubKey]; lpSubKey
0x180037af3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037afa  mov     esi, r12d
0x180037afd  call    cs:__imp_RegOpenKeyExW
0x180037b03  mov     ebx, eax
0x180037b05  test    eax, eax
0x180037b07  jz      short loc_180037B1F
0x180037b09  lea     rdx, aRegopenkeyexFa; "RegOpenKeyEx failed. Error: 0x%x."
0x180037b10  mov     r8d, eax
0x180037b13  xor     ecx, ecx
0x180037b15  call    UnattendLogW
0x180037b1a  jmp     loc_180037C00
0x180037b1f  mov     rcx, [rsp+980h+hKey]; hKey
0x180037b24  lea     rax, [rsp+980h+hkey]
0x180037b29  mov     r9d, edi; samDesired
0x180037b2c  mov     [rsp+980h+phkResult], rax; phkResult
0x180037b31  xor     r8d, r8d; ulOptions
0x180037b34  lea     rdx, [rbp+880h+var_7A0]; lpSubKey
0x180037b3b  call    cs:__imp_RegOpenKeyExW
0x180037b41  mov     ebx, eax
0x180037b43  test    eax, eax
0x180037b45  jnz     short loc_180037B09
0x180037b47  mov     rcx, [rsp+980h+hkey]; hkey
0x180037b4c  lea     rax, [rsp+980h+var_920]
0x180037b51  mov     [rsp+980h+pcbData], rax; pcbData
0x180037b56  lea     r9d, [rbx+2]; dwFlags
0x180037b5a  lea     rax, [rbp+880h+String1]
0x180037b61  xor     edx, edx; lpSubKey
0x180037b63  mov     [rsp+980h+pvData], rax; pvData
0x180037b68  lea     r8, [rbp+880h+Value]; lpValue
0x180037b6f  mov     [rsp+980h+phkResult], 0; pdwType
0x180037b78  call    cs:__imp_RegGetValueW
0x180037b7e  mov     ebx, eax
0x180037b80  test    eax, eax
0x180037b82  jz      short loc_180037B8D
0x180037b84  lea     rdx, aReggetvalueFai; "RegGetValue failed. Error: 0x%x."
0x180037b8b  jmp     short loc_180037B10
0x180037b8d  lea     rdx, aClient; "Client"
0x180037b94  lea     rcx, [rbp+880h+String1]; String1
0x180037b9b  call    wcscmp_0
0x180037ba0  xor     ecx, ecx
0x180037ba2  test    eax, eax
0x180037ba4  jmp     short loc_180037BD8
0x180037ba6  xor     edx, edx; Val
0x180037ba8  lea     rcx, [rsp+980h+VersionInformation.dwMajorVersion]; void *
0x180037bad  mov     r8d, 118h; Size
0x180037bb3  call    memset_0
0x180037bb8  lea     rcx, [rsp+980h+VersionInformation]; lpVersionInformation
0x180037bbd  mov     [rsp+980h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180037bc5  call    cs:__imp_GetVersionExW
0x180037bcb  test    eax, eax
0x180037bcd  jz      short loc_180037BDD
0x180037bcf  xor     ecx, ecx
0x180037bd1  cmp     [rbp+880h+var_7F6], r12b
0x180037bd8  setz    cl
0x180037bdb  jmp     short loc_180037BFD
0x180037bdd  call    cs:__imp_GetLastError
0x180037be3  lea     rdx, aFailedToGetOnl; "Failed to get online OS version info. E"...
0x180037bea  mov     r8d, eax
0x180037bed  mov     ecx, r12d
0x180037bf0  mov     ebx, eax
0x180037bf2  call    UnattendLogW
0x180037bf7  xor     ecx, ecx
0x180037bf9  test    ebx, ebx
0x180037bfb  jnz     short loc_180037C00
0x180037bfd  mov     [r14], ecx
0x180037c00  mov     rcx, [rsp+980h+hkey]; hKey
0x180037c05  test    rcx, rcx
0x180037c08  jz      short loc_180037C19
0x180037c0a  call    cs:__imp_RegCloseKey
0x180037c10  mov     [rsp+980h+hkey], 0
0x180037c19  mov     rcx, [rsp+980h+hKey]; hKey
0x180037c1e  test    rcx, rcx
0x180037c21  jz      short loc_180037C32
0x180037c23  call    cs:__imp_RegCloseKey
0x180037c29  mov     [rsp+980h+hKey], 0
0x180037c32  test    esi, esi
0x180037c34  jz      short loc_180037C69
0x180037c36  lea     rdx, [rbp+880h+SubKey]; lpSubKey
0x180037c3d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037c44  call    cs:__imp_RegUnLoadKeyW
0x180037c4a  test    eax, eax
0x180037c4c  jz      short loc_180037C69
0x180037c4e  mov     r9d, eax
0x180037c51  lea     r8, [rbp+880h+SubKey]
0x180037c58  lea     rdx, aRegunloadkeySF; "RegUnloadKey [%s] failed. Error: 0x%x."
0x180037c5f  mov     ecx, 2
0x180037c64  call    UnattendLogW
0x180037c69  lea     rdx, [rsp+980h+var_940]; int *
0x180037c6e  mov     ecx, 11h; unsigned int
0x180037c73  call    ?DisablePrivilege@Utils@@SAHKPEAH@Z; Utils::DisablePrivilege(ulong,int *)
0x180037c78  lea     rdx, [rsp+980h+var_93C]; int *
0x180037c7d  mov     ecx, 12h; unsigned int
0x180037c82  call    ?DisablePrivilege@Utils@@SAHKPEAH@Z; Utils::DisablePrivilege(ulong,int *)
0x180037c87  mov     eax, ebx
0x180037c89  mov     rcx, [rbp+880h+var_30]
0x180037c90  xor     rcx, rsp; StackCookie
0x180037c93  call    __security_check_cookie
0x180037c98  mov     rbx, [rsp+980h+arg_10]
0x180037ca0  add     rsp, 960h
0x180037ca7  pop     r14
0x180037ca9  pop     r12
0x180037cab  pop     rdi
0x180037cac  pop     rsi
0x180037cad  pop     rbp
0x180037cae  retn
```
