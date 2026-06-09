# SetSysPathsInReg(ulong)

- ea: `0x18000ef90`
- end: `0x18000f231`
- name: `?SetSysPathsInReg@@YAXK@Z`
- size: `673`
- prototype: `void __fastcall(int)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x18000a61c`

## callees

- `0x1800022bc`
- `0x18000279c`
- `0x180002c74`
- `0x180003ce0`
- `0x180003e20`
- `0x180007454`
- `0x18000ef90`
- `0x18001a688`
- `0x18001b294`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetWindowsDirectoryW` at `0x18000f0c3`
- `KERNEL32!GetWindowsDirectoryW` at `0x18000f0c3`
- `ADVAPI32!RegQueryValueExW` at `0x18000f036`
- `ADVAPI32!RegQueryValueExW` at `0x18000f15e`
- `ADVAPI32!RegQueryValueExW` at `0x18000f036`
- `ADVAPI32!RegQueryValueExW` at `0x18000f15e`
- `ADVAPI32!RegCloseKey` at `0x18000f200`
- `ADVAPI32!RegCloseKey` at `0x18000f200`
- `ADVAPI32!RegOpenKeyExW` at `0x18000eff3`
- `ADVAPI32!RegOpenKeyExW` at `0x18000eff3`
- `ADVAPI32!RegSetValueExW` at `0x18000f0b7`
- `ADVAPI32!RegSetValueExW` at `0x18000f1e9`
- `ADVAPI32!RegSetValueExW` at `0x18000f0b7`
- `ADVAPI32!RegSetValueExW` at `0x18000f1e9`

## string_xrefs

- `0x18000f010`: `ProgramFilesPath`
- `0x18000f0a4`: `ProgramFilesPath`
- `0x18000f113`: `SM_AccessoriesName`
- `0x18000f124`: `PF_AccessoriesName`
- `0x18000f0f8`: `Accessories`

## pseudocode

```c
void __fastcall SetSysPathsInReg(int a1)
{
  HKEY v1; // rbx
  int v2; // eax
  DWORD v3; // r9d
  __int64 v4; // rax
  int i; // edi
  const WCHAR *v6; // rbx
  const WCHAR *v7; // rsi
  __int64 v8; // rax
  ULONG phkResult; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  _WORD v12[104]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD Data[264]; // [rsp+110h] [rbp+10h] BYREF

  hKey = 0;
  cbData = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion", 0, a1 | 0x2001F, &hKey) )
  {
    cbData = 518;
    Data[259] = 0;
    if ( RegQueryValueExW(hKey, L"ProgramFilesPath", 0, 0, (LPBYTE)Data, &cbData)
      && (unsigned int)GetProgramFilesDir(Data, 0x104u) )
    {
      v1 = hKey;
      if ( ctx < 2u || (v2 = AddEnvInPath(Data, Data, 0x104u), v3 = 2, !v2) )
        v3 = 1;
      v4 = -1;
      do
        ++v4;
      while ( Data[v4] );
      RegSetValueExW(v1, L"ProgramFilesPath", 0, v3, (const BYTE *)Data, 2 * v4 + 2);
    }
    GetWindowsDirectoryW(Data, 0x104u);
    PathIsUnc2(L"inf\\wordpad.inf");
    PathCchCombineEx(Data, 0x104u, Data, L"inf\\wordpad.inf", phkResult);
    for ( i = 0; i < 2; ++i )
    {
      v6 = L"APPS_DESC";
      if ( i )
      {
        v7 = L"PF_AccessoriesName";
        if ( ctx < 2u )
          v6 = L"Accessories";
      }
      else
      {
        v7 = L"SM_AccessoriesName";
      }
      cbData = 200;
      v12[100] = 0;
      if ( RegQueryValueExW(hKey, v7, 0, 0, (LPBYTE)v12, &cbData) && (unsigned int)SaveGlobalContext() )
      {
        if ( (int)GetTranslatedString(Data, L"Strings", v6, v12, 0x65u, 0) < 0 )
          StringCchCopyW(v12, 0x65u, L"Accessories");
        v8 = -1;
        do
          ++v8;
        while ( v12[v8] );
        RegSetValueExW(hKey, v7, 0, 1u, (const BYTE *)v12, 2 * v8 + 2);
        RestoreGlobalContext();
      }
    }
    RegCloseKey(hKey);
  }
}

```

## disassembly

```asm
0x18000ef90  mov     [rsp-8+arg_8], rbx
0x18000ef95  mov     [rsp-8+arg_10], rsi
0x18000ef9a  push    rbp
0x18000ef9b  push    rdi
0x18000ef9c  push    r13
0x18000ef9e  push    r14
0x18000efa0  push    r15
0x18000efa2  lea     rbp, [rsp-230h]
0x18000efaa  sub     rsp, 330h
0x18000efb1  mov     rax, cs:__security_cookie
0x18000efb8  xor     rax, rsp
0x18000efbb  mov     [rbp+250h+var_30], rax
0x18000efc2  or      ecx, 2001Fh
0x18000efc8  lea     rax, [rsp+350h+hKey]
0x18000efcd  mov     r9d, ecx; samDesired
0x18000efd0  mov     [rsp+350h+phkResult], rax; phkResult
0x18000efd5  xor     r14d, r14d
0x18000efd8  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000efdf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000efe6  mov     [rsp+350h+hKey], r14
0x18000efeb  xor     r8d, r8d; ulOptions
0x18000efee  mov     [rsp+350h+cbData], r14d
0x18000eff3  call    cs:__imp_RegOpenKeyExW
0x18000eff9  test    eax, eax
0x18000effb  jnz     loc_18000F206
0x18000f001  mov     rcx, [rsp+350h+hKey]; hKey
0x18000f006  lea     rax, [rsp+350h+cbData]
0x18000f00b  mov     [rsp+350h+lpcbData], rax; lpcbData
0x18000f010  lea     rdx, aProgramfilespa; "ProgramFilesPath"
0x18000f017  lea     rax, [rbp+250h+Data]
0x18000f01b  mov     [rsp+350h+cbData], 206h
0x18000f023  xor     r9d, r9d; lpType
0x18000f026  mov     [rsp+350h+phkResult], rax; lpData
0x18000f02b  xor     r8d, r8d; lpReserved
0x18000f02e  mov     [rbp+250h+var_3A], r14w
0x18000f036  call    cs:__imp_RegQueryValueExW
0x18000f03c  mov     edi, 104h
0x18000f041  lea     r15d, [r14+2]
0x18000f045  test    eax, eax
0x18000f047  jz      short loc_18000F0BD
0x18000f049  mov     edx, edi; unsigned int
0x18000f04b  lea     rcx, [rbp+250h+Data]; unsigned __int16 *
0x18000f04f  call    ?GetProgramFilesDir@@YAHPEAGK@Z; GetProgramFilesDir(ushort *,ulong)
0x18000f054  test    eax, eax
0x18000f056  jz      short loc_18000F0BD
0x18000f058  cmp     cs:?ctx@@3UADVCONTEXTW@@A, r15w; ADVCONTEXTW ctx
0x18000f060  mov     rbx, [rsp+350h+hKey]
0x18000f065  jb      short loc_18000F07E
0x18000f067  mov     r8d, edi; unsigned int
0x18000f06a  lea     rdx, [rbp+250h+Data]; unsigned __int16 *
0x18000f06e  lea     rcx, [rbp+250h+Data]; unsigned __int16 *
0x18000f072  call    ?AddEnvInPath@@YAHPEBGPEAGK@Z; AddEnvInPath(ushort const *,ushort *,ulong)
0x18000f077  mov     r9d, r15d
0x18000f07a  test    eax, eax
0x18000f07c  jnz     short loc_18000F084
0x18000f07e  mov     r9d, 1; dwType
0x18000f084  lea     rcx, [rbp+250h+Data]
0x18000f088  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f08c  inc     rax
0x18000f08f  cmp     [rcx+rax*2], r14w
0x18000f094  jnz     short loc_18000F08C
0x18000f096  lea     eax, ds:2[rax*2]
0x18000f09d  xor     r8d, r8d; Reserved
0x18000f0a0  mov     dword ptr [rsp+350h+lpcbData], eax; cbData
0x18000f0a4  lea     rdx, aProgramfilespa; "ProgramFilesPath"
0x18000f0ab  lea     rax, [rbp+250h+Data]
0x18000f0af  mov     rcx, rbx; hKey
0x18000f0b2  mov     [rsp+350h+phkResult], rax; dwFlags
0x18000f0b7  call    cs:__imp_RegSetValueExW
0x18000f0bd  mov     edx, edi; uSize
0x18000f0bf  lea     rcx, [rbp+250h+Data]; lpBuffer
0x18000f0c3  call    cs:__imp_GetWindowsDirectoryW
0x18000f0c9  lea     r8, IsBackslash
0x18000f0d0  xor     edx, edx
0x18000f0d2  lea     rcx, aInfWordpadInf; "inf\\wordpad.inf"
0x18000f0d9  call    PathIsUnc2
0x18000f0de  lea     r9, aInfWordpadInf; "inf\\wordpad.inf"
0x18000f0e5  mov     rdx, rdi; cchPathOut
0x18000f0e8  lea     r8, [rbp+250h+Data]; pszPathIn
0x18000f0ec  lea     rcx, [rbp+250h+Data]; pszPathOut
0x18000f0f0  call    PathCchCombineEx
0x18000f0f5  mov     edi, r14d
0x18000f0f8  lea     r13, aAccessories; "Accessories"
0x18000f0ff  cmp     edi, r15d
0x18000f102  jge     loc_18000F1FB
0x18000f108  lea     rbx, aAppsDesc; "APPS_DESC"
0x18000f10f  test    edi, edi
0x18000f111  jnz     short loc_18000F11C
0x18000f113  lea     rsi, aSmAccessoriesn; "SM_AccessoriesName"
0x18000f11a  jmp     short loc_18000F12F
0x18000f11c  cmp     cs:?ctx@@3UADVCONTEXTW@@A, r15w; ADVCONTEXTW ctx
0x18000f124  lea     rsi, aPfAccessoriesn; "PF_AccessoriesName"
0x18000f12b  cmovb   rbx, r13
0x18000f12f  mov     rcx, [rsp+350h+hKey]; hKey
0x18000f134  lea     rax, [rsp+350h+cbData]
0x18000f139  mov     [rsp+350h+lpcbData], rax; lpcbData
0x18000f13e  xor     r9d, r9d; lpType
0x18000f141  lea     rax, [rsp+350h+var_310]
0x18000f146  mov     [rsp+350h+cbData], 0C8h
0x18000f14e  xor     r8d, r8d; lpReserved
0x18000f151  mov     [rsp+350h+phkResult], rax; lpData
0x18000f156  mov     rdx, rsi; lpValueName
0x18000f159  mov     [rbp+250h+var_248], r14w
0x18000f15e  call    cs:__imp_RegQueryValueExW
0x18000f164  test    eax, eax
0x18000f166  jz      loc_18000F1F4
0x18000f16c  call    ?SaveGlobalContext@@YAHXZ; SaveGlobalContext(void)
0x18000f171  test    eax, eax
0x18000f173  jz      short loc_18000F1F4
0x18000f175  mov     [rsp+350h+lpcbData], r14; unsigned int *
0x18000f17a  lea     r9, [rsp+350h+var_310]; unsigned __int16 *
0x18000f17f  mov     r8, rbx; lpKeyName
0x18000f182  mov     dword ptr [rsp+350h+phkResult], 65h ; 'e'; unsigned int
0x18000f18a  lea     rdx, AppName; "Strings"
0x18000f191  lea     rcx, [rbp+250h+Data]; unsigned __int16 *
0x18000f195  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x18000f19a  test    eax, eax
0x18000f19c  jns     short loc_18000F1B0
0x18000f19e  mov     r8, r13; unsigned __int16 *
0x18000f1a1  lea     rcx, [rsp+350h+var_310]; unsigned __int16 *
0x18000f1a6  mov     edx, 65h ; 'e'; unsigned __int64
0x18000f1ab  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f1b0  lea     rcx, [rsp+350h+var_310]
0x18000f1b5  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f1b9  inc     rax
0x18000f1bc  cmp     [rcx+rax*2], r14w
0x18000f1c1  jnz     short loc_18000F1B9
0x18000f1c3  mov     rcx, [rsp+350h+hKey]; hKey
0x18000f1c8  lea     eax, ds:2[rax*2]
0x18000f1cf  mov     dword ptr [rsp+350h+lpcbData], eax; cbData
0x18000f1d3  mov     r9d, 1; dwType
0x18000f1d9  lea     rax, [rsp+350h+var_310]
0x18000f1de  xor     r8d, r8d; Reserved
0x18000f1e1  mov     rdx, rsi; lpValueName
0x18000f1e4  mov     [rsp+350h+phkResult], rax; lpData
0x18000f1e9  call    cs:__imp_RegSetValueExW
0x18000f1ef  call    ?RestoreGlobalContext@@YAHXZ; RestoreGlobalContext(void)
0x18000f1f4  inc     edi
0x18000f1f6  jmp     loc_18000F0FF
0x18000f1fb  mov     rcx, [rsp+350h+hKey]; hKey
0x18000f200  call    cs:__imp_RegCloseKey
0x18000f206  mov     rcx, [rbp+250h+var_30]
0x18000f20d  xor     rcx, rsp; StackCookie
0x18000f210  call    __security_check_cookie
0x18000f215  lea     r11, [rsp+350h+var_20]
0x18000f21d  mov     rbx, [r11+38h]
0x18000f221  mov     rsi, [r11+40h]
0x18000f225  mov     rsp, r11
0x18000f228  pop     r15
0x18000f22a  pop     r14
0x18000f22c  pop     r13
0x18000f22e  pop     rdi
0x18000f22f  pop     rbp
0x18000f230  retn
```
