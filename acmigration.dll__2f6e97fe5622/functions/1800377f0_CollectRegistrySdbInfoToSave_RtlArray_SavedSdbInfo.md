# CollectRegistrySdbInfoToSave(RtlArray<_SavedSdbInfo> &)

- ea: `0x1800377f0`
- end: `0x180037c5e`
- name: `?CollectRegistrySdbInfoToSave@@YAJAEAV?$RtlArray@U_SavedSdbInfo@@@@@Z`
- size: `1134`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800384a0`

## callees

- `0x180001cf0`
- `0x180002110`
- `0x18000a51c`
- `0x18000a654`
- `0x180037610`
- `0x180037760`
- `0x1800377f0`
- `0x18003862c`
- `0x1800543c0`
- `0x180054934`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180037ab4`
- `KERNEL32!GetLastError` at `0x180037ab4`
- `ADVAPI32!RegQueryValueExW` at `0x1800379a0`
- `ADVAPI32!RegQueryValueExW` at `0x1800379a0`
- `ADVAPI32!RegCloseKey` at `0x180037b2b`
- `ADVAPI32!RegCloseKey` at `0x180037b40`
- `ADVAPI32!RegCloseKey` at `0x180037c0f`
- `ADVAPI32!RegCloseKey` at `0x180037c24`
- `ADVAPI32!RegCloseKey` at `0x180037b2b`
- `ADVAPI32!RegCloseKey` at `0x180037b40`
- `ADVAPI32!RegCloseKey` at `0x180037c0f`
- `ADVAPI32!RegCloseKey` at `0x180037c24`
- `ADVAPI32!RegEnumKeyExW` at `0x180037925`
- `ADVAPI32!RegEnumKeyExW` at `0x180037b81`
- `ADVAPI32!RegEnumKeyExW` at `0x180037925`
- `ADVAPI32!RegEnumKeyExW` at `0x180037b81`
- `ADVAPI32!RegOpenKeyExW` at `0x1800378e1`
- `ADVAPI32!RegOpenKeyExW` at `0x180037957`
- `ADVAPI32!RegOpenKeyExW` at `0x180037a2b`
- `ADVAPI32!RegOpenKeyExW` at `0x1800378e1`
- `ADVAPI32!RegOpenKeyExW` at `0x180037957`
- `ADVAPI32!RegOpenKeyExW` at `0x180037a2b`

## string_xrefs

- `0x18003787d`: `CollectRegistrySdbInfoToSave`
- `0x180037ada`: `CollectRegistrySdbInfoToSave`
- `0x180037b03`: `CollectRegistrySdbInfoToSave`
- `0x180037898`: `\InstalledSDB`
- `0x180037be6`: `Failed to open installed sdb key: 0x%x`
- `0x180037bb9`: `Failed to open installed sdb subkey: 0x%x`
- `0x180037994`: `DatabasePath`
- `0x180037af4`: `Failed to query installed sdb value: 0x%x`
- `0x1800379f6`: `SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall\%ls.sdb`
- `0x180037ac9`: `Failed to open addremove key: 0x%x`
- `0x180037ba3`: `Failed to enumerate installed sdb subkey: 0x%x`

## pseudocode

```c
__int64 __fastcall CollectRegistrySdbInfoToSave(
        __int64 a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  HRESULT PersistedLocation; // eax
  signed int v6; // ebx
  const char *v7; // r9
  __int64 v8; // r8
  LSTATUS v9; // eax
  DWORD v10; // r15d
  LSTATUS i; // eax
  int v12; // eax
  __int64 v13; // rdx
  DWORD v14; // eax
  unsigned __int64 v15; // rcx
  int LastError; // eax
  int v17; // ebx
  bool v18; // sf
  const char *v19; // r9
  __int64 v20; // r8
  bool v21; // sf
  int phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultb; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v30; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v31; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v32; // [rsp+68h] [rbp-98h] BYREF
  __int128 v33; // [rsp+78h] [rbp-88h] BYREF
  __int64 v34; // [rsp+88h] [rbp-78h]
  WCHAR Name[264]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t pszDest[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  BYTE Data[2]; // [rsp+4B0h] [rbp+3B0h] BYREF
  wchar_t SubKey[264]; // [rsp+6C0h] [rbp+5C0h] BYREF

  cchName = 0;
  cbData = 0;
  Type = 0;
  hKey = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v34 = 0;
  v33 = 0;
  PersistedLocation = Windows::Compat::Shared::Registry::GetPersistedLocation(pszDest, a2, a3, a4, phkResult);
  v6 = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v7 = "Failed to get persisted reg key location: 0x%x";
    v8 = 132;
LABEL_3:
    LODWORD(phkResulta) = PersistedLocation;
    goto LABEL_4;
  }
  PersistedLocation = StringCchCatW(pszDest, 0x104u, L"\\InstalledSDB");
  v6 = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    v7 = "Failed to concat string: 0x%x";
    v8 = 139;
    goto LABEL_3;
  }
  v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x20119u, &hKey);
  v6 = v9;
  if ( v9 )
  {
    if ( (unsigned int)(v9 - 2) <= 1 )
      goto LABEL_59;
    if ( v9 > 0 )
      v6 = (unsigned __int16)v9 | 0x80070000;
LABEL_55:
    v7 = "Failed to open installed sdb key: 0x%x";
    v21 = v6 < 0;
    v8 = 158;
    goto LABEL_56;
  }
  if ( !hKey )
    goto LABEL_55;
  v10 = 0;
  cchName = 260;
  for ( i = RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, 0); ; i = RegEnumKeyExW(
                                                                        hKey,
                                                                        v10,
                                                                        Name,
                                                                        &cchName,
                                                                        0,
                                                                        0,
                                                                        0,
                                                                        0) )
  {
    v6 = i;
    if ( i )
      break;
    v12 = RegOpenKeyExW(hKey, Name, 0, 0x20119u, &v30);
    if ( v12 )
    {
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
LABEL_51:
      v19 = "Failed to open installed sdb subkey: 0x%x";
      v20 = 185;
      goto LABEL_36;
    }
    if ( !v30 )
      goto LABEL_51;
    cbData = 520;
    v12 = RegQueryValueExW(v30, L"DatabasePath", 0, &Type, Data, &cbData);
    if ( v12 )
    {
      if ( v12 > 0 )
        v12 = (unsigned __int16)v12 | 0x80070000;
LABEL_35:
      v19 = "Failed to query installed sdb value: 0x%x";
      v20 = 203;
LABEL_36:
      if ( v12 >= 0 )
        v12 = -2147467259;
      LODWORD(phkResultb) = v12;
      AslLogCallPrintf(1, "CollectRegistrySdbInfoToSave", v20, v19, phkResultb);
      goto LABEL_39;
    }
    if ( Type != 1 )
      goto LABEL_35;
    v14 = cbData >> 1;
    if ( cbData >> 1 > 0x104 )
      v14 = 260;
    cbData = v14;
    v15 = 2LL * (v14 - 1);
    if ( v15 >= 0x208 )
      _report_rangecheckfailure(v15, v13);
    *(_WORD *)&Data[2 * v14 - 2] = 0;
    if ( StringCchPrintfW(SubKey, 0x104u, L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\%ls.sdb", Name) >= 0 )
    {
      LastError = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20119u, &v31);
      if ( LastError )
      {
        if ( (unsigned int)(LastError - 2) <= 1 )
        {
          v17 = 0;
LABEL_23:
          if ( !(unsigned int)AslStringDuplicate(&v32, Name) && !(unsigned int)AslStringDuplicate(&v33, Data) )
          {
            DWORD2(v32) = v17;
            if ( (int)RtlArray<_SavedSdbInfo>::Append(a1, &v32) >= 0 )
            {
              v32 = 0;
              v34 = 0;
              v33 = 0;
            }
          }
          goto LABEL_39;
        }
      }
      else
      {
        if ( v31 )
        {
          v17 = 1;
          goto LABEL_23;
        }
        LastError = GetLastError();
      }
      v18 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v18 = LastError < 0;
      }
      if ( !v18 )
        LastError = -2147467259;
      AslLogCallPrintf(1, "CollectRegistrySdbInfoToSave", 253, "Failed to open addremove key: 0x%x", LastError);
    }
LABEL_39:
    if ( v30 )
    {
      RegCloseKey(v30);
      v30 = 0;
    }
    if ( v31 )
    {
      RegCloseKey(v31);
      v31 = 0;
    }
    CleanupSavedSdbInfo((struct _SavedSdbInfo *)&v32);
    ++v10;
    cchName = 260;
  }
  if ( i == 259 )
  {
LABEL_59:
    v6 = 0;
    goto LABEL_60;
  }
  v21 = i < 0;
  if ( i > 0 )
  {
    v6 = (unsigned __int16)i | 0x80070000;
    v21 = 1;
  }
  v7 = "Failed to enumerate installed sdb subkey: 0x%x";
  v8 = 317;
LABEL_56:
  if ( !v21 )
    v6 = -2147467259;
  LODWORD(phkResulta) = v6;
LABEL_4:
  AslLogCallPrintf(1, "CollectRegistrySdbInfoToSave", v8, v7, phkResulta);
LABEL_60:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v30 )
    RegCloseKey(v30);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800377f0  mov     [rsp-8+arg_8], rbx
0x1800377f5  mov     [rsp-8+arg_10], rsi
0x1800377fa  push    rbp
0x1800377fb  push    r12
0x1800377fd  push    r13
0x1800377ff  push    r14
0x180037801  push    r15
0x180037803  lea     rbp, [rsp-7E0h]
0x18003780b  sub     rsp, 8E0h
0x180037812  mov     rax, cs:__security_cookie
0x180037819  xor     rax, rsp
0x18003781c  mov     [rbp+800h+var_30], rax
0x180037823  xor     r13d, r13d
0x180037826  xorps   xmm0, xmm0
0x180037829  mov     r12, rcx
0x18003782c  mov     [rsp+900h+cchName], r13d
0x180037831  xor     eax, eax
0x180037833  mov     [rsp+900h+cbData], r13d
0x180037838  lea     rcx, [rbp+800h+pszDest]; unsigned __int16 *
0x18003783f  mov     [rsp+900h+Type], r13d
0x180037844  mov     [rsp+900h+hKey], r13
0x180037849  mov     [rsp+900h+var_8A8], r13
0x18003784e  mov     [rsp+900h+var_8A0], r13
0x180037853  movups  [rsp+900h+var_898], xmm0
0x180037858  mov     [rbp+800h+var_878], rax
0x18003785c  movups  [rsp+900h+var_888], xmm0
0x180037861  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x180037866  mov     ebx, eax
0x180037868  test    eax, eax
0x18003786a  jns     short loc_180037893
0x18003786c  lea     r9, aFailedToGetPer; "Failed to get persisted reg key locatio"...
0x180037873  mov     r8d, 84h
0x180037879  mov     dword ptr [rsp+900h+phkResult], eax
0x18003787d  lea     rdx, aCollectregistr; "CollectRegistrySdbInfoToSave"
0x180037884  mov     ecx, 1
0x180037889  call    AslLogCallPrintf
0x18003788e  jmp     loc_180037C05
0x180037893  mov     esi, 104h
0x180037898  lea     r8, aInstalledsdb; "\\InstalledSDB"
0x18003789f  mov     edx, esi; cchDest
0x1800378a1  lea     rcx, [rbp+800h+pszDest]; pszDest
0x1800378a8  call    StringCchCatW
0x1800378ad  mov     ebx, eax
0x1800378af  test    eax, eax
0x1800378b1  jns     short loc_1800378C0
0x1800378b3  lea     r9, aFailedToConcat; "Failed to concat string: 0x%x"
0x1800378ba  lea     r8d, [rsi-79h]
0x1800378be  jmp     short loc_180037879
0x1800378c0  lea     rax, [rsp+900h+hKey]
0x1800378c5  mov     r9d, 20119h; samDesired
0x1800378cb  xor     r8d, r8d; ulOptions
0x1800378ce  mov     [rsp+900h+phkResult], rax; phkResult
0x1800378d3  lea     rdx, [rbp+800h+pszDest]; lpSubKey
0x1800378da  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800378e1  call    cs:__imp_RegOpenKeyExW
0x1800378e7  mov     ebx, eax
0x1800378e9  test    eax, eax
0x1800378eb  jnz     loc_180037BCB
0x1800378f1  mov     rcx, [rsp+900h+hKey]; hKey
0x1800378f6  test    rcx, rcx
0x1800378f9  jz      loc_180037BE0
0x1800378ff  mov     [rsp+900h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180037904  lea     r9, [rsp+900h+cchName]; lpcchName
0x180037909  mov     [rsp+900h+lpcchClass], r13; lpcchClass
0x18003790e  lea     r8, [rbp+800h+Name]; lpName
0x180037912  mov     [rsp+900h+lpClass], r13; lpClass
0x180037917  xor     edx, edx; dwIndex
0x180037919  mov     [rsp+900h+phkResult], r13; lpReserved
0x18003791e  mov     r15d, r13d
0x180037921  mov     [rsp+900h+cchName], esi
0x180037925  call    cs:__imp_RegEnumKeyExW
0x18003792b  mov     esi, 80070000h
0x180037930  mov     r14d, 80004005h
0x180037936  jmp     loc_180037B87
0x18003793b  mov     rcx, [rsp+900h+hKey]; hKey
0x180037940  lea     rax, [rsp+900h+var_8A8]
0x180037945  mov     r9d, 20119h; samDesired
0x18003794b  mov     [rsp+900h+phkResult], rax; phkResult
0x180037950  xor     r8d, r8d; ulOptions
0x180037953  lea     rdx, [rbp+800h+Name]; lpSubKey
0x180037957  call    cs:__imp_RegOpenKeyExW
0x18003795d  test    eax, eax
0x18003795f  jnz     loc_180037BB2
0x180037965  mov     rcx, [rsp+900h+var_8A8]; hKey
0x18003796a  test    rcx, rcx
0x18003796d  jz      loc_180037BB9
0x180037973  lea     rax, [rsp+900h+cbData]
0x180037978  mov     [rsp+900h+cbData], 208h
0x180037980  mov     [rsp+900h+lpClass], rax; lpcbData
0x180037985  lea     r9, [rsp+900h+Type]; lpType
0x18003798a  lea     rax, [rbp+800h+Data]
0x180037991  xor     r8d, r8d; lpReserved
0x180037994  lea     rdx, aDatabasepath; "DatabasePath"
0x18003799b  mov     [rsp+900h+phkResult], rax; lpData
0x1800379a0  call    cs:__imp_RegQueryValueExW
0x1800379a6  test    eax, eax
0x1800379a8  jnz     loc_180037AED
0x1800379ae  cmp     [rsp+900h+Type], 1
0x1800379b3  jnz     loc_180037AF4
0x1800379b9  mov     eax, [rsp+900h+cbData]
0x1800379bd  mov     ebx, 104h
0x1800379c2  shr     eax, 1
0x1800379c4  cmp     eax, ebx
0x1800379c6  cmova   eax, ebx
0x1800379c9  mov     [rsp+900h+cbData], eax
0x1800379cd  lea     ecx, [rax-1]
0x1800379d0  add     rcx, rcx
0x1800379d3  cmp     rcx, 208h
0x1800379da  jnb     loc_180037C58
0x1800379e0  mov     word ptr [rbp+rcx+800h+Data], r13w
0x1800379e9  lea     r9, [rbp+800h+Name]
0x1800379ed  lea     rcx, [rbp+800h+SubKey]; pszDest
0x1800379f4  mov     edx, ebx; cchDest
0x1800379f6  lea     r8, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800379fd  call    StringCchPrintfW
0x180037a02  test    eax, eax
0x180037a04  js      loc_180037B21
0x180037a0a  lea     rax, [rsp+900h+var_8A0]
0x180037a0f  mov     r9d, 20119h; samDesired
0x180037a15  xor     r8d, r8d; ulOptions
0x180037a18  mov     [rsp+900h+phkResult], rax; phkResult
0x180037a1d  lea     rdx, [rbp+800h+SubKey]; lpSubKey
0x180037a24  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180037a2b  call    cs:__imp_RegOpenKeyExW
0x180037a31  mov     edx, eax
0x180037a33  test    eax, eax
0x180037a35  jz      short loc_180037A46
0x180037a37  sub     edx, 2
0x180037a3a  jz      short loc_180037A41
0x180037a3c  cmp     edx, 1
0x180037a3f  jnz     short loc_180037ABA
0x180037a41  mov     ebx, r13d
0x180037a44  jmp     short loc_180037A52
0x180037a46  cmp     [rsp+900h+var_8A0], r13
0x180037a4b  jz      short loc_180037AB4
0x180037a4d  mov     ebx, 1
0x180037a52  lea     rdx, [rbp+800h+Name]
0x180037a56  lea     rcx, [rsp+900h+var_898]
0x180037a5b  call    AslStringDuplicate
0x180037a60  test    eax, eax
0x180037a62  jnz     loc_180037B1C
0x180037a68  lea     rdx, [rbp+800h+Data]
0x180037a6f  lea     rcx, [rsp+900h+var_888]
0x180037a74  call    AslStringDuplicate
0x180037a79  test    eax, eax
0x180037a7b  jnz     loc_180037B1C
0x180037a81  lea     rdx, [rsp+900h+var_898]
0x180037a86  mov     dword ptr [rsp+900h+var_898+8], ebx
0x180037a8a  mov     rcx, r12
0x180037a8d  call    ?Append@?$RtlArray@U_SavedSdbInfo@@@@QEAAJAEBU_SavedSdbInfo@@@Z; RtlArray<_SavedSdbInfo>::Append(_SavedSdbInfo const &)
0x180037a92  mov     ebx, 104h
0x180037a97  test    eax, eax
0x180037a99  js      loc_180037B21
0x180037a9f  xorps   xmm0, xmm0
0x180037aa2  xor     eax, eax
0x180037aa4  movups  [rsp+900h+var_898], xmm0
0x180037aa9  mov     [rbp+800h+var_878], rax
0x180037aad  movups  [rsp+900h+var_888], xmm0
0x180037ab2  jmp     short loc_180037B21
0x180037ab4  call    cs:__imp_GetLastError
0x180037aba  test    eax, eax
0x180037abc  jle     short loc_180037AC5
0x180037abe  movzx   eax, ax
0x180037ac1  or      eax, esi
0x180037ac3  test    eax, eax
0x180037ac5  cmovns  eax, r14d
0x180037ac9  lea     r9, aFailedToOpenAd; "Failed to open addremove key: 0x%x"
0x180037ad0  mov     r8d, 0FDh
0x180037ad6  mov     dword ptr [rsp+900h+phkResult], eax
0x180037ada  lea     rdx, aCollectregistr; "CollectRegistrySdbInfoToSave"
0x180037ae1  mov     ecx, 1
0x180037ae6  call    AslLogCallPrintf
0x180037aeb  jmp     short loc_180037B21
0x180037aed  jle     short loc_180037AF4
0x180037aef  movzx   eax, ax
0x180037af2  or      eax, esi
0x180037af4  lea     r9, aFailedToQueryI; "Failed to query installed sdb value: 0x"...
0x180037afb  mov     r8d, 0CBh
0x180037b01  test    eax, eax
0x180037b03  lea     rdx, aCollectregistr; "CollectRegistrySdbInfoToSave"
0x180037b0a  mov     ecx, 1
0x180037b0f  cmovns  eax, r14d
0x180037b13  mov     dword ptr [rsp+900h+phkResult], eax
0x180037b17  call    AslLogCallPrintf
0x180037b1c  mov     ebx, 104h
0x180037b21  mov     rcx, [rsp+900h+var_8A8]; hKey
0x180037b26  test    rcx, rcx
0x180037b29  jz      short loc_180037B36
0x180037b2b  call    cs:__imp_RegCloseKey
0x180037b31  mov     [rsp+900h+var_8A8], r13
0x180037b36  mov     rcx, [rsp+900h+var_8A0]; hKey
0x180037b3b  test    rcx, rcx
0x180037b3e  jz      short loc_180037B4B
0x180037b40  call    cs:__imp_RegCloseKey
0x180037b46  mov     [rsp+900h+var_8A0], r13
0x180037b4b  lea     rcx, [rsp+900h+var_898]; struct _SavedSdbInfo *
0x180037b50  call    ?CleanupSavedSdbInfo@@YAXPEAU_SavedSdbInfo@@@Z; CleanupSavedSdbInfo(_SavedSdbInfo *)
0x180037b55  mov     rcx, [rsp+900h+hKey]; hKey
0x180037b5a  lea     r9, [rsp+900h+cchName]; lpcchName
0x180037b5f  mov     [rsp+900h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180037b64  lea     r8, [rbp+800h+Name]; lpName
0x180037b68  inc     r15d
0x180037b6b  mov     [rsp+900h+lpcchClass], r13; lpcchClass
0x180037b70  mov     [rsp+900h+lpClass], r13; lpClass
0x180037b75  mov     edx, r15d; dwIndex
0x180037b78  mov     [rsp+900h+phkResult], r13; lpReserved
0x180037b7d  mov     [rsp+900h+cchName], ebx
0x180037b81  call    cs:__imp_RegEnumKeyExW
0x180037b87  mov     ebx, eax
0x180037b89  test    eax, eax
0x180037b8b  jz      loc_18003793B
0x180037b91  cmp     eax, 103h
0x180037b96  jz      short loc_180037C02
0x180037b98  test    eax, eax
0x180037b9a  jle     short loc_180037BA3
0x180037b9c  movzx   ebx, bx
0x180037b9f  or      ebx, esi
0x180037ba1  test    ebx, ebx
0x180037ba3  lea     r9, aFailedToEnumer; "Failed to enumerate installed sdb subke"...
0x180037baa  mov     r8d, 13Dh
0x180037bb0  jmp     short loc_180037BF5
0x180037bb2  jle     short loc_180037BB9
0x180037bb4  movzx   eax, ax
0x180037bb7  or      eax, esi
0x180037bb9  lea     r9, aFailedToOpenIn; "Failed to open installed sdb subkey: 0x"...
0x180037bc0  mov     r8d, 0B9h
0x180037bc6  jmp     loc_180037B01
0x180037bcb  add     eax, 0FFFFFFFEh
0x180037bce  cmp     eax, 1
0x180037bd1  jbe     short loc_180037C02
0x180037bd3  test    ebx, ebx
0x180037bd5  jle     short loc_180037BE0
0x180037bd7  movzx   ebx, bx
0x180037bda  or      ebx, 80070000h
0x180037be0  mov     r14d, 80004005h
0x180037be6  lea     r9, aFailedToOpenIn_0; "Failed to open installed sdb key: 0x%x"
0x180037bed  test    ebx, ebx
0x180037bef  mov     r8d, 9Eh
0x180037bf5  cmovns  ebx, r14d
0x180037bf9  mov     dword ptr [rsp+900h+phkResult], ebx
0x180037bfd  jmp     loc_18003787D
0x180037c02  mov     ebx, r13d
0x180037c05  mov     rcx, [rsp+900h+hKey]; hKey
0x180037c0a  test    rcx, rcx
0x180037c0d  jz      short loc_180037C1A
0x180037c0f  call    cs:__imp_RegCloseKey
0x180037c15  mov     [rsp+900h+hKey], r13
0x180037c1a  mov     rcx, [rsp+900h+var_8A8]; hKey
0x180037c1f  test    rcx, rcx
0x180037c22  jz      short loc_180037C2A
0x180037c24  call    cs:__imp_RegCloseKey
0x180037c2a  mov     eax, ebx
0x180037c2c  mov     rcx, [rbp+800h+var_30]
0x180037c33  xor     rcx, rsp; StackCookie
0x180037c36  call    __security_check_cookie
0x180037c3b  lea     r11, [rsp+900h+var_20]
0x180037c43  mov     rbx, [r11+38h]
0x180037c47  mov     rsi, [r11+40h]
0x180037c4b  mov     rsp, r11
0x180037c4e  pop     r15
0x180037c50  pop     r14
0x180037c52  pop     r13
0x180037c54  pop     r12
0x180037c56  pop     rbp
0x180037c57  retn
0x180037c58  call    __report_rangecheckfailure
```
