# SetPerUserSecValuesW

- ea: `0x180010d50`
- end: `0x18001135e`
- name: `SetPerUserSecValuesW`
- size: `1550`
- prototype: `HRESULT __stdcall(PERUSERSECTIONW *pPerUser)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000dbec`
- `0x180010cd0`

## callees

- `0x1800022bc`
- `0x180003180`
- `0x1800035c8`
- `0x18000c574`
- `0x18000c8c8`
- `0x18000ed4c`
- `0x180010d50`
- `0x180017f14`
- `0x18001b980`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x180010e40`
- `ADVAPI32!RegCreateKeyExW` at `0x180010e9c`
- `ADVAPI32!RegCreateKeyExW` at `0x1800111fe`
- `ADVAPI32!RegCreateKeyExW` at `0x180010e40`
- `ADVAPI32!RegCreateKeyExW` at `0x180010e9c`
- `ADVAPI32!RegCreateKeyExW` at `0x1800111fe`
- `ADVAPI32!RegQueryValueExW` at `0x180010f0e`
- `ADVAPI32!RegQueryValueExW` at `0x180010f54`
- `ADVAPI32!RegQueryValueExW` at `0x1800110af`
- `ADVAPI32!RegQueryValueExW` at `0x180010f0e`
- `ADVAPI32!RegQueryValueExW` at `0x180010f54`
- `ADVAPI32!RegQueryValueExW` at `0x1800110af`
- `ADVAPI32!RegCloseKey` at `0x18001128e`
- `ADVAPI32!RegCloseKey` at `0x180011305`
- `ADVAPI32!RegCloseKey` at `0x180011315`
- `ADVAPI32!RegCloseKey` at `0x18001128e`
- `ADVAPI32!RegCloseKey` at `0x180011305`
- `ADVAPI32!RegCloseKey` at `0x180011315`
- `ADVAPI32!RegSetValueExW` at `0x18001107c`
- `ADVAPI32!RegSetValueExW` at `0x18001125a`
- `ADVAPI32!RegSetValueExW` at `0x18001107c`
- `ADVAPI32!RegSetValueExW` at `0x18001125a`
- `ADVAPI32!RegDeleteValueW` at `0x1800112a0`
- `ADVAPI32!RegDeleteValueW` at `0x1800112b2`
- `ADVAPI32!RegDeleteValueW` at `0x1800112c4`
- `ADVAPI32!RegDeleteValueW` at `0x1800112d6`
- `ADVAPI32!RegDeleteValueW` at `0x1800112e8`
- `ADVAPI32!RegDeleteValueW` at `0x1800112a0`
- `ADVAPI32!RegDeleteValueW` at `0x1800112b2`
- `ADVAPI32!RegDeleteValueW` at `0x1800112c4`
- `ADVAPI32!RegDeleteValueW` at `0x1800112d6`
- `ADVAPI32!RegDeleteValueW` at `0x1800112e8`
- `ADVAPI32!RegDeleteKeyW` at `0x1800110f6`
- `ADVAPI32!RegDeleteKeyW` at `0x1800110f6`

## string_xrefs

- `0x180010ef7`: `IsInstalled`
- `0x180010fff`: `StubPath`
- `0x180011066`: `StubPath`
- `0x18001116c`: `StubPath`
- `0x180011244`: `StubPath`
- `0x180010e51`: `Failure: Cannot open %1 key\n`
- `0x180010ea9`: `Failure: Cannot create %1 key\n`
- `0x180011265`: `DontAsk`
- `0x180011031`: `rundll32.exe advpack.dll,UserInstStubWrapper %s`
- `0x18001120f`: `rundll32.exe advpack.dll,UserUnInstStubWrapper %s`
- `0x180011022`: `RealStubPath`
- `0x180011099`: `RealStubPath`
- `0x18001118f`: `RealStubPath`
- `0x180011018`: `OldRealStubPath`
- `0x180011199`: `OldRealStubPath`
- `0x1800112e1`: `OldRealStubPath`
- `0x180010ff5`: `OldStubPath`
- `0x180011176`: `OldStubPath`
- `0x1800112cf`: `OldStubPath`
- `0x180010e13`: `software\microsoft\Active Setup\Installed Components`
- `0x180010e4a`: `software\microsoft\Active Setup\Installed Components`

## pseudocode

```c
HRESULT __stdcall SetPerUserSecValuesW(PERUSERSECTIONW *pPerUser)
{
  const char *v2; // rcx
  PERUSERSECTIONW *v3; // rdx
  const wchar_t *v4; // rcx
  unsigned int v5; // edi
  DWORD dwIsInstalled; // eax
  BOOL v7; // esi
  __int64 v8; // rax
  __int64 v9; // rax
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+5Ch] [rbp-A4h] BYREF
  HKEY v14; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 v16; // [rsp+70h] [rbp-90h]
  wchar_t Data[1024]; // [rsp+80h] [rbp-80h] BYREF

  hKey = 0;
  phkResult = 0;
  dwDisposition = 0;
  cbData = 0;
  AdvWriteToLog(L"SetPerUserSecValues:\r\n");
  if ( !pPerUser || !pPerUser->szGUID[0] )
  {
    AdvWriteToLog(L"SetPerUserSecValues: End Warning: No Data\r\n");
    return 0;
  }
  v2 = "1";
  if ( !pPerUser->dwIsInstalled )
    v2 = "0";
  AdvWriteToLog(
    L"Input params: %1,%2,%3,%4,%5,%6\r\n",
    pPerUser,
    pPerUser->szDispName,
    pPerUser->szLocale,
    pPerUser->szStub,
    pPerUser->szVersion,
    v2);
  if ( RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"software\\microsoft\\Active Setup\\Installed Components",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         &dwDisposition) )
  {
    v3 = (PERUSERSECTIONW *)L"software\\microsoft\\Active Setup\\Installed Components";
    v4 = L"Failure: Cannot open %1 key\r\n";
  }
  else
  {
    if ( !RegCreateKeyExW(hKey, pPerUser->szGUID, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition) )
    {
      dwIsInstalled = pPerUser->dwIsInstalled;
      v5 = 0;
      if ( dwIsInstalled == 1 )
      {
        v7 = 0;
        cbData = 4;
        if ( pPerUser->bRollback )
        {
          if ( !RegQueryValueExW(phkResult, L"IsInstalled", 0, 0, (LPBYTE)&dwDisposition, &cbData) && dwDisposition == 1 )
          {
            cbData = 2048;
            if ( !RegQueryValueExW(phkResult, L"Version", 0, 0, (LPBYTE)Data, &cbData) )
            {
              ConvertVersionString(Data);
              if ( pPerUser->szVersion[0] )
              {
                ConvertVersionString(pPerUser->szVersion);
                if ( v16 >= (unsigned __int16)v14 )
                {
                  cbData = 2048;
                  v7 = RegQueryValueExW(phkResult, L"RealStubPath", 0, 0, (LPBYTE)Data, &cbData) == 0;
                }
                else
                {
                  CopyRegValue(phkResult, phkResult, &word_18001DE6C, L"OldDisplayName");
                  CopyRegValue(phkResult, phkResult, L"Version", L"OldVersion");
                  CopyRegValue(phkResult, phkResult, L"Locale", L"OldLocale");
                  if ( (unsigned int)CopyRegValue(phkResult, phkResult, L"StubPath", L"OldStubPath") )
                  {
                    CopyRegValue(phkResult, phkResult, L"RealStubPath", L"OldRealStubPath");
                    StringCchPrintfW(Data, 0x400u, L"rundll32.exe advpack.dll,UserInstStubWrapper %s", pPerUser);
                    v8 = -1;
                    do
                      ++v8;
                    while ( Data[v8] );
                    RegSetValueExW(phkResult, L"StubPath", 0, 1u, (const BYTE *)Data, 2 * v8 + 2);
                    v7 = 1;
                  }
                }
              }
            }
          }
        }
        SetSecRegValues(phkResult, pPerUser, v7);
        StringCchCopyW(Data, 0x400u, (size_t *)pPerUser->szGUID);
        StringCchCatW(Data, 1024, L".Restore");
        RegDeleteKeyW(hKey, Data);
      }
      else if ( !dwIsInstalled )
      {
        if ( (unsigned int)CopyRegValue(phkResult, phkResult, L"OldVersion", L"Version") )
        {
          v14 = 0;
          CopyRegValue(phkResult, phkResult, L"OldDisplayName", &word_18001DE6C);
          CopyRegValue(phkResult, phkResult, L"OldLocale", L"Locale");
          if ( (unsigned int)CopyRegValue(phkResult, phkResult, L"OldStubPath", L"StubPath") )
          {
            CopyRegValue(phkResult, phkResult, L"OldRealStubPath", L"RealStubPath");
            StringCchCopyW(Data, 0x400u, (size_t *)pPerUser->szGUID);
            StringCchCatW(Data, 1024, L".Restore");
            if ( !RegCreateKeyExW(hKey, Data, 0, 0, 0, 0x2001Fu, 0, &v14, &dwDisposition) )
            {
              StringCchPrintfW(Data, 0x400u, L"rundll32.exe advpack.dll,UserUnInstStubWrapper %s", pPerUser);
              v9 = -1;
              do
                ++v9;
              while ( Data[v9] );
              RegSetValueExW(v14, L"StubPath", 0, 1u, (const BYTE *)Data, 2 * v9 + 2);
              CopyRegValue(phkResult, v14, L"DontAsk", L"DontAsk");
              SetSecRegValues(v14, pPerUser, 1);
              RegCloseKey(v14);
            }
          }
          RegDeleteValueW(phkResult, L"OldDisplayName");
          RegDeleteValueW(phkResult, L"OldLocale");
          RegDeleteValueW(phkResult, L"OldVersion");
          RegDeleteValueW(phkResult, L"OldStubPath");
          RegDeleteValueW(phkResult, L"OldRealStubPath");
        }
        else
        {
          SetSecRegValues(phkResult, pPerUser, 0);
        }
      }
      goto LABEL_32;
    }
    v3 = pPerUser;
    v4 = L"Failure: Cannot create %1 key\r\n";
  }
  v5 = -2147467259;
  AdvWriteToLog(v4, v3);
LABEL_32:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  AdvWriteToLog(L"SetPerUserSecValues: End hr=0x%1!x!\r\n", v5);
  return v5;
}

```

## disassembly

```asm
0x180010d50  push    rbp
0x180010d52  push    rbx
0x180010d53  push    rsi
0x180010d54  push    rdi
0x180010d55  push    r12
0x180010d57  push    r13
0x180010d59  push    r14
0x180010d5b  push    r15
0x180010d5d  lea     rbp, [rsp-798h]
0x180010d65  sub     rsp, 898h
0x180010d6c  mov     rax, cs:__security_cookie
0x180010d73  xor     rax, rsp
0x180010d76  mov     [rbp+7D0h+var_50], rax
0x180010d7d  xor     r12d, r12d
0x180010d80  mov     rbx, rcx
0x180010d83  lea     rcx, aSetperusersecv_2; "SetPerUserSecValues:\r\n"
0x180010d8a  mov     [rsp+8D0h+hKey], r12
0x180010d8f  mov     [rsp+8D0h+var_880], r12
0x180010d94  mov     [rsp+8D0h+dwDisposition], r12d
0x180010d99  mov     [rsp+8D0h+cbData], r12d
0x180010d9e  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x180010da3  test    rbx, rbx
0x180010da6  jz      loc_18001132D
0x180010dac  cmp     [rbx], r12w
0x180010db0  jz      loc_18001132D
0x180010db6  cmp     [rbx+0AECh], r12d
0x180010dbd  lea     rax, a0; "0"
0x180010dc4  lea     rcx, a1_1; "1"
0x180010dcb  mov     rdx, rbx
0x180010dce  cmovz   rcx, rax
0x180010dd2  lea     r15, [rbx+9AAh]
0x180010dd9  mov     [rsp+8D0h+lpSecurityAttributes], rcx
0x180010dde  lea     rax, [rbx+18Ah]
0x180010de5  mov     qword ptr [rsp+8D0h+samDesired], r15
0x180010dea  lea     rcx, aInputParams123; "Input params: %1,%2,%3,%4,%5,%6\r\n"
0x180010df1  lea     r9, [rbx+176h]
0x180010df8  mov     qword ptr [rsp+8D0h+dwOptions], rax
0x180010dfd  lea     r8, [rbx+76h]
0x180010e01  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x180010e06  lea     rax, [rsp+8D0h+dwDisposition]
0x180010e0b  xor     r9d, r9d; lpClass
0x180010e0e  mov     [rsp+8D0h+lpdwDisposition], rax; lpdwDisposition
0x180010e13  lea     rdx, aSoftwareMicros_3; "software\\microsoft\\Active Setup\\Inst"...
0x180010e1a  lea     rax, [rsp+8D0h+hKey]
0x180010e1f  xor     r8d, r8d; Reserved
0x180010e22  mov     [rsp+8D0h+phkResult], rax; phkResult
0x180010e27  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010e2e  mov     [rsp+8D0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180010e33  mov     [rsp+8D0h+samDesired], 20006h; samDesired
0x180010e3b  mov     [rsp+8D0h+dwOptions], r12d; dwOptions
0x180010e40  call    cs:__imp_RegCreateKeyExW
0x180010e46  test    eax, eax
0x180010e48  jz      short loc_180010E67
0x180010e4a  lea     rdx, aSoftwareMicros_3; "software\\microsoft\\Active Setup\\Inst"...
0x180010e51  lea     rcx, aFailureCannotO; "Failure: Cannot open %1 key\r\n"
0x180010e58  mov     edi, 80004005h
0x180010e5d  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x180010e62  jmp     loc_1800112FB
0x180010e67  mov     rcx, [rsp+8D0h+hKey]; hKey
0x180010e6c  lea     rax, [rsp+8D0h+dwDisposition]
0x180010e71  mov     [rsp+8D0h+lpdwDisposition], rax; lpdwDisposition
0x180010e76  mov     esi, 2001Fh
0x180010e7b  lea     rax, [rsp+8D0h+var_880]
0x180010e80  xor     r9d, r9d; lpClass
0x180010e83  mov     [rsp+8D0h+phkResult], rax; phkResult
0x180010e88  xor     r8d, r8d; Reserved
0x180010e8b  mov     [rsp+8D0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x180010e90  mov     rdx, rbx; lpSubKey
0x180010e93  mov     [rsp+8D0h+samDesired], esi; samDesired
0x180010e97  mov     [rsp+8D0h+dwOptions], r12d; dwOptions
0x180010e9c  call    cs:__imp_RegCreateKeyExW
0x180010ea2  test    eax, eax
0x180010ea4  jz      short loc_180010EB2
0x180010ea6  mov     rdx, rbx
0x180010ea9  lea     rcx, aFailureCannotC; "Failure: Cannot create %1 key\r\n"
0x180010eb0  jmp     short loc_180010E58
0x180010eb2  mov     eax, [rbx+0AECh]
0x180010eb8  mov     r13d, 1
0x180010ebe  mov     edi, r12d
0x180010ec1  cmp     eax, r13d
0x180010ec4  jnz     loc_180011101
0x180010eca  mov     esi, r12d
0x180010ecd  mov     [rsp+8D0h+cbData], 4
0x180010ed5  mov     r14d, 400h
0x180010edb  cmp     [rbx+0AF0h], r12d
0x180010ee2  jz      loc_1800110BB
0x180010ee8  mov     rcx, [rsp+8D0h+var_880]; hKey
0x180010eed  lea     rax, [rsp+8D0h+cbData]
0x180010ef2  mov     qword ptr [rsp+8D0h+samDesired], rax; lpcbData
0x180010ef7  lea     rdx, aIsinstalled; "IsInstalled"
0x180010efe  lea     rax, [rsp+8D0h+dwDisposition]
0x180010f03  xor     r9d, r9d; lpType
0x180010f06  xor     r8d, r8d; lpReserved
0x180010f09  mov     qword ptr [rsp+8D0h+dwOptions], rax; lpData
0x180010f0e  call    cs:__imp_RegQueryValueExW
0x180010f14  test    eax, eax
0x180010f16  jnz     loc_1800110BB
0x180010f1c  cmp     [rsp+8D0h+dwDisposition], r13d
0x180010f21  jnz     loc_1800110BB
0x180010f27  mov     rcx, [rsp+8D0h+var_880]; hKey
0x180010f2c  lea     rax, [rsp+8D0h+cbData]
0x180010f31  mov     qword ptr [rsp+8D0h+samDesired], rax; lpcbData
0x180010f36  lea     rdx, aVersion; "Version"
0x180010f3d  lea     rax, [rbp+7D0h+Data]
0x180010f41  mov     [rsp+8D0h+cbData], 800h
0x180010f49  xor     r9d, r9d; lpType
0x180010f4c  mov     qword ptr [rsp+8D0h+dwOptions], rax; lpData
0x180010f51  xor     r8d, r8d; lpReserved
0x180010f54  call    cs:__imp_RegQueryValueExW
0x180010f5a  test    eax, eax
0x180010f5c  jnz     loc_1800110BB
0x180010f62  lea     r8d, [r13+2Bh]
0x180010f66  lea     rdx, [rsp+8D0h+var_860]
0x180010f6b  lea     rcx, [rbp+7D0h+Data]; pszSrc
0x180010f6f  call    ConvertVersionString
0x180010f74  cmp     [r15], r12w
0x180010f78  jz      loc_1800110BB
0x180010f7e  lea     r8d, [r13+2Bh]
0x180010f82  mov     rcx, r15; pszSrc
0x180010f85  lea     rdx, [rsp+8D0h+var_870]
0x180010f8a  call    ConvertVersionString
0x180010f8f  movzx   eax, word ptr [rsp+8D0h+var_870]
0x180010f94  mov     rcx, [rsp+8D0h+var_880]; HKEY
0x180010f99  cmp     [rsp+8D0h+var_860], ax
0x180010f9e  jnb     loc_180011087
0x180010fa4  lea     r9, aOlddisplayname; "OldDisplayName"
0x180010fab  mov     rdx, rcx; HKEY
0x180010fae  lea     r8, word_18001DE6C; unsigned __int16 *
0x180010fb5  call    ?CopyRegValue@@YAHPEAUHKEY__@@0PEBG1@Z; CopyRegValue(HKEY__ *,HKEY__ *,ushort const *,ushort const *)
0x180010fba  mov     rcx, [rsp+8D0h+var_880]; HKEY
0x180010fbf  lea     r9, aOldversion; "OldVersion"
0x180010fc6  mov     rdx, rcx; HKEY
0x180010fc9  lea     r8, aVersion; "Version"
0x180010fd0  call    ?CopyRegValue@@YAHPEAUHKEY__@@0PEBG1@Z; CopyRegValue(HKEY__ *,HKEY__ *,ushort const *,ushort const *)
0x180010fd5  mov     rcx, [rsp+8D0h+var_880]; HKEY
0x180010fda  lea     r9, aOldlocale; "OldLocale"
0x180010fe1  mov     rdx, rcx; HKEY
0x180010fe4  lea     r8, aLocale; "Locale"
0x180010feb  call    ?CopyRegValue@@YAHPEAUHKEY__@@0PEBG1@Z; CopyRegValue(HKEY__ *,HKEY__ *,ushort const *,ushort const *)
0x180010ff0  mov     rcx, [rsp+8D0h+var_880]; HKEY
0x180010ff5  lea     r9, aOldstubpath; "OldStubPath"
0x180010ffc  mov     rdx, rcx; HKEY
0x180010fff  lea     r8, aStubpath; "StubPath"
0x180011006  call    ?CopyRegValue@@YAHPEAUHKEY__@@0PEBG1@Z; CopyRegValue(HKEY__ *,HKEY__ *,ushort const *,ushort const *)
0x18001100b  test    eax, eax
0x18001100d  jz      loc_1800110BB
0x180011013  mov     rcx, [rsp+8D0h+var_880]; HKEY
0x180011018  lea     r9, aOldrealstubpat; "OldRealStubPath"
0x18001101f  mov     rdx, rcx; HKEY
0x180011022  lea     r8, aRealstubpath; "RealStubPath"
0x180011029  call    ?CopyRegValue@@YAHPEAUHKEY__@@0PEBG1@Z; CopyRegValue(HKEY__ *,HKEY__ *,ushort const *,ushort const *)
0x18001102e  mov     r9, rbx
0x180011031  lea     r8, aRundll32ExeAdv_0; "rundll32.exe advpack.dll,UserInstStubWr"...
0x180011038  mov     edx, r14d; unsigned __int64
0x18001103b  lea     rcx, [rbp+7D0h+Data]; unsigned __int16 *
0x18001103f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011044  lea     rcx, [rbp+7D0h+Data]
0x180011048  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001104c  inc     rax
0x18001104f  cmp     [rcx+rax*2], r12w
0x180011054  jnz     short loc_18001104C
0x180011056  mov     rcx, [rsp+8D0h+var_880]; hKey
0x18001105b  lea     eax, ds:2[rax*2]
0x180011062  mov     [rsp+8D0h+samDesired], eax; cbData
0x180011066  lea     rdx, aStubpath; "StubPath"
0x18001106d  lea     rax, [rbp+7D0h+Data]
0x180011071  mov     r9d, r13d; dwType
0x180011074  xor     r8d, r8d; Reserved
0x180011077  mov     qword ptr [rsp+8D0h+dwOptions], rax; lpData
0x18001107c  call    cs:__imp_RegSetValueExW
0x180011082  mov     esi, r13d
0x180011085  jmp     short loc_1800110BB
0x180011087  lea     rax, [rsp+8D0h+cbData]
0x18001108c  mov     [rsp+8D0h+cbData], 800h
0x180011094  mov     qword ptr [rsp+8D0h+samDesired], rax; lpcbData
0x180011099  lea     rdx, aRealstubpath; "RealStubPath"
0x1800110a0  lea     rax, [rbp+7D0h+Data]
0x1800110a4  xor     r9d, r9d; lpType
0x1800110a7  xor     r8d, r8d; lpReserved
0x1800110aa  mov     qword ptr [rsp+8D0h+dwOptions], rax; lpData
0x1800110af  call    cs:__imp_RegQueryValueExW
0x1800110b5  test    eax, eax
0x1800110b7  cmovz   esi, r13d
0x1800110bb  mov     rcx, [rsp+8D0h+var_880]; hKey
0x1800110c0  mov     r8d, esi; int
0x1800110c3  mov     rdx, rbx; struct _PERUSERSECTIONW *
0x1800110c6  call    ?SetSecRegValues@@YAXPEAUHKEY__@@PEAU_PERUSERSECTIONW@@H@Z; SetSecRegValues(HKEY__ *,_PERUSERSECTIONW *,int)
0x1800110cb  mov     r8, rbx; unsigned __int16 *
0x1800110ce  lea     rcx, [rbp+7D0h+Data]; unsigned __int16 *
0x1800110d2  mov     rdx, r14; unsigned __int64
0x1800110d5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800110da  lea     r8, aRestore; ".Restore"
0x1800110e1  mov     rdx, r14; unsigned __int64
0x1800110e4  lea     rcx, [rbp+7D0h+Data]; unsigned __int16 *
0x1800110e8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800110ed  mov     rcx, [rsp+8D0h+hKey]; hKey
0x1800110f2  lea     rdx, [rbp+7D0h+Data]; lpSubKey
0x1800110f6  call    cs:__imp_RegDeleteKeyW
0x1800110fc  jmp     loc_1800112FB
0x180011101  test    eax, eax
0x180011103  jnz     loc_1800112FB
0x180011109  mov     rcx, [rsp+8D0h+var_880]; HKEY
0x18001110e  lea     r9, aVersion; "Version"
0x180011115  mov     rdx, rcx; HKEY
0x180011118  lea     r8, aOldversion; "OldVersion"
0x18001111f  call    ?CopyRegValue@@YAHPEAUHKEY__@@0PEBG1@Z; CopyRegValue(HKEY__ *,HKEY__ *,ushort const *,ushort const *)
0x180011124  mov     rcx, [rsp+8D0h+var_880]; hKey
0x180011129  test    eax, eax
0x18001112b  jz      loc_1800112F0
0x180011131  lea     r9, word_18001DE6C; unsigned __int16 *
0x180011138  mov     [rsp+8D0h+var_870], r12
0x18001113d  lea     r8, aOlddisplayname; "OldDisplayName"
0x180011144  mov     rdx, rcx; HKEY
0x180011147  call    ?CopyRegValue@@YAHPEAUHKEY__@@0PEBG1@Z; CopyRegValue(HKEY__ *,HKEY__ *,ushort const *,ushort const *)
0x18001114c  mov     rcx, [rsp+8D0h+var_880]; HKEY
0x180011151  lea     r9, aLocale; "Locale"
0x180011158  mov     rdx, rcx; HKEY
0x18001115b  lea     r8, aOldlocale; "OldLocale"
0x180011162  call    ?CopyRegValue@@YAHPEAUHKEY__@@0PEBG1@Z; CopyRegValue(HKEY__ *,HKEY__ *,ushort const *,ushort const *)
0x180011167  mov     rcx, [rsp+8D0h+var_880]; HKEY
0x18001116c  lea     r9, aStubpath; "StubPath"
0x180011173  mov     rdx, rcx; HKEY
0x180011176  lea     r8, aOldstubpath; "OldStubPath"
0x18001117d  call    ?CopyRegValue@@YAHPEAUHKEY__@@0PEBG1@Z; CopyRegValue(HKEY__ *,HKEY__ *,ushort const *,ushort const *)
0x180011182  test    eax, eax
0x180011184  jz      loc_180011294
0x18001118a  mov     rcx, [rsp+8D0h+var_880]; HKEY
0x18001118f  lea     r9, aRealstubpath; "RealStubPath"
0x180011196  mov     rdx, rcx; HKEY
0x180011199  lea     r8, aOldrealstubpat; "OldRealStubPath"
0x1800111a0  call    ?CopyRegValue@@YAHPEAUHKEY__@@0PEBG1@Z; CopyRegValue(HKEY__ *,HKEY__ *,ushort const *,ushort const *)
0x1800111a5  mov     r14d, 400h
0x1800111ab  lea     rcx, [rbp+7D0h+Data]; unsigned __int16 *
0x1800111af  mov     edx, r14d; unsigned __int64
0x1800111b2  mov     r8, rbx; unsigned __int16 *
0x1800111b5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800111ba  lea     r8, aRestore; ".Restore"
0x1800111c1  mov     edx, r14d; unsigned __int64
0x1800111c4  lea     rcx, [rbp+7D0h+Data]; unsigned __int16 *
0x1800111c8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800111cd  mov     rcx, [rsp+8D0h+hKey]; hKey
0x1800111d2  lea     rax, [rsp+8D0h+dwDisposition]
0x1800111d7  mov     [rsp+8D0h+lpdwDisposition], rax; lpdwDisposition
0x1800111dc  lea     rdx, [rbp+7D0h+Data]; lpSubKey
0x1800111e0  lea     rax, [rsp+8D0h+var_870]
0x1800111e5  xor     r9d, r9d; lpClass
0x1800111e8  mov     [rsp+8D0h+phkResult], rax; phkResult
0x1800111ed  xor     r8d, r8d; Reserved
0x1800111f0  mov     [rsp+8D0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800111f5  mov     [rsp+8D0h+samDesired], esi; samDesired
0x1800111f9  mov     [rsp+8D0h+dwOptions], r12d; dwOptions
0x1800111fe  call    cs:__imp_RegCreateKeyExW
0x180011204  test    eax, eax
0x180011206  jnz     loc_180011294
0x18001120c  mov     r9, rbx
0x18001120f  lea     r8, aRundll32ExeAdv_1; "rundll32.exe advpack.dll,UserUnInstStub"...
0x180011216  mov     edx, r14d; unsigned __int64
0x180011219  lea     rcx, [rbp+7D0h+Data]; unsigned __int16 *
0x18001121d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180011222  lea     rcx, [rbp+7D0h+Data]
0x180011226  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001122a  inc     rax
0x18001122d  cmp     [rcx+rax*2], r12w
0x180011232  jnz     short loc_18001122A
0x180011234  mov     rcx, [rsp+8D0h+var_870]; hKey
0x180011239  lea     eax, ds:2[rax*2]
0x180011240  mov     [rsp+8D0h+samDesired], eax; cbData
0x180011244  lea     rdx, aStubpath; "StubPath"
0x18001124b  lea     rax, [rbp+7D0h+Data]
0x18001124f  mov     r9d, r13d; dwType
0x180011252  xor     r8d, r8d; Reserved
0x180011255  mov     qword ptr [rsp+8D0h+dwOptions], rax; lpData
0x18001125a  call    cs:__imp_RegSetValueExW
0x180011260  mov     rdx, [rsp+8D0h+var_870]; HKEY
0x180011265  lea     r8, aDontask; "DontAsk"
0x18001126c  mov     rcx, [rsp+8D0h+var_880]; HKEY
0x180011271  mov     r9, r8; unsigned __int16 *
0x180011274  call    ?CopyRegValue@@YAHPEAUHKEY__@@0PEBG1@Z; CopyRegValue(HKEY__ *,HKEY__ *,ushort const *,ushort const *)
0x180011279  mov     rcx, [rsp+8D0h+var_870]; hKey
0x18001127e  mov     r8d, r13d; int
0x180011281  mov     rdx, rbx; struct _PERUSERSECTIONW *
0x180011284  call    ?SetSecRegValues@@YAXPEAUHKEY__@@PEAU_PERUSERSECTIONW@@H@Z; SetSecRegValues(HKEY__ *,_PERUSERSECTIONW *,int)
0x180011289  mov     rcx, [rsp+8D0h+var_870]; hKey
0x18001128e  call    cs:__imp_RegCloseKey
0x180011294  mov     rcx, [rsp+8D0h+var_880]; hKey
0x180011299  lea     rdx, aOlddisplayname; "OldDisplayName"
0x1800112a0  call    cs:__imp_RegDeleteValueW
0x1800112a6  mov     rcx, [rsp+8D0h+var_880]; hKey
0x1800112ab  lea     rdx, aOldlocale; "OldLocale"
0x1800112b2  call    cs:__imp_RegDeleteValueW
0x1800112b8  mov     rcx, [rsp+8D0h+var_880]; hKey
0x1800112bd  lea     rdx, aOldversion; "OldVersion"
0x1800112c4  call    cs:__imp_RegDeleteValueW
0x1800112ca  mov     rcx, [rsp+8D0h+var_880]; hKey
0x1800112cf  lea     rdx, aOldstubpath; "OldStubPath"
0x1800112d6  call    cs:__imp_RegDeleteValueW
0x1800112dc  mov     rcx, [rsp+8D0h+var_880]; hKey
0x1800112e1  lea     rdx, aOldrealstubpat; "OldRealStubPath"
0x1800112e8  call    cs:__imp_RegDeleteValueW
0x1800112ee  jmp     short loc_1800112FB
  ... truncated ...
```
