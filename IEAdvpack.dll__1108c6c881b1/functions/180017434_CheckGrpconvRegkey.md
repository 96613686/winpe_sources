# CheckGrpconvRegkey

- ea: `0x180017434`
- end: `0x18001771f`
- name: `CheckGrpconvRegkey`
- size: `747`
- prototype: `_BOOL8 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x180017728`

## callees

- `0x1800018d4`
- `0x180017434`
- `0x180017840`
- `0x1800198d0`
- `0x18001a688`
- `0x18001b294`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x180017675`
- `KERNEL32!GetFileAttributesW` at `0x180017675`
- `ADVAPI32!RegQueryValueExW` at `0x18001758e`
- `ADVAPI32!RegQueryValueExW` at `0x18001758e`
- `ADVAPI32!RegCloseKey` at `0x1800176d6`
- `ADVAPI32!RegCloseKey` at `0x1800176ec`
- `ADVAPI32!RegCloseKey` at `0x1800176d6`
- `ADVAPI32!RegCloseKey` at `0x1800176ec`
- `ADVAPI32!RegOpenKeyExW` at `0x180017506`
- `ADVAPI32!RegOpenKeyExW` at `0x18001755d`
- `ADVAPI32!RegOpenKeyExW` at `0x180017506`
- `ADVAPI32!RegOpenKeyExW` at `0x18001755d`
- `ADVAPI32!RegEnumValueW` at `0x1800175ed`
- `ADVAPI32!RegEnumValueW` at `0x1800175ed`
- `ADVAPI32!RegEnumKeyW` at `0x18001752a`
- `ADVAPI32!RegEnumKeyW` at `0x18001752a`
- `SHLWAPI!StrChrW` at `0x18001768e`
- `SHLWAPI!StrChrW` at `0x18001768e`

## pseudocode

```c
_BOOL8 __fastcall CheckGrpconvRegkey(unsigned __int16 *a1)
{
  BOOL v2; // edi
  DWORD v3; // r15d
  __int64 v4; // rsi
  DWORD i; // r14d
  WCHAR *v6; // rbx
  DWORD FileAttributesW; // ebx
  PWSTR v8; // rax
  ULONG phkResult; // [rsp+20h] [rbp-E0h]
  ULONG phkResulta; // [rsp+20h] [rbp-E0h]
  DWORD cchValueName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v13; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v15; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t pszDest[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Data[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR ValueName[264]; // [rsp+480h] [rbp+380h] BYREF
  WCHAR lpData[264]; // [rsp+690h] [rbp+590h] BYREF

  hKey = 0;
  v15 = 0;
  cbData = 0;
  v2 = 0;
  cchValueName = 0;
  v13 = 0;
  StringCchCopyW(pszDest, 0x104u, L"Software\\Microsoft\\Windows\\CurrentVersion");
  if ( a1 && !(unsigned int)PathIsUnc2(a1) && !IsExtendedLengthDosDevicePath(a1) )
  {
    while ( *a1 == 92 )
      ++a1;
  }
  PathCchCombineEx(pszDest, 0x104u, pszDest, a1, phkResult);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x20019u, &hKey) )
  {
    v3 = 0;
    do
    {
      if ( RegEnumKeyW(hKey, v3, pszDest, 0x104u) )
        break;
      cbData = 520;
      if ( !RegOpenKeyExW(hKey, pszDest, 0, 0x20019u, &v15) )
      {
        if ( !RegQueryValueExW(v15, 0, 0, 0, (LPBYTE)Data, &cbData) )
        {
          v4 = -1;
          do
            ++v4;
          while ( Data[v4] );
          for ( i = 0; ; ++i )
          {
            v13 = 520;
            cchValueName = 260;
            if ( v2 || RegEnumValueW(v15, i, ValueName, &cchValueName, 0, 0, (LPBYTE)lpData, &v13) )
              break;
            if ( cchValueName )
            {
              Data[v4] = 0;
              v6 = ValueName;
              if ( !(unsigned int)PathIsUnc2(ValueName)
                && !IsExtendedLengthDosDevicePath(ValueName)
                && ValueName[0] == 92 )
              {
                do
                  ++v6;
                while ( *v6 == 92 );
              }
              PathCchCombineEx(Data, 0x104u, Data, v6, phkResulta);
              FileAttributesW = GetFileAttributesW(Data);
              if ( FileAttributesW != -1 )
              {
                v8 = StrChrW(lpData, 0x2Cu);
                if ( v8 )
                {
                  *v8 = 0;
                  v2 = (wtol_0(v8 + 1) & FileAttributesW) == 0;
                }
                else
                {
                  v2 = 1;
                }
              }
            }
          }
        }
        RegCloseKey(v15);
      }
      ++v3;
    }
    while ( !v2 );
    RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x180017434  mov     [rsp-8+arg_8], rbx
0x180017439  mov     [rsp-8+arg_10], rsi
0x18001743e  push    rbp
0x18001743f  push    rdi
0x180017440  push    r12
0x180017442  push    r14
0x180017444  push    r15
0x180017446  lea     rbp, [rsp-7B0h]
0x18001744e  sub     rsp, 8B0h
0x180017455  mov     rax, cs:__security_cookie
0x18001745c  xor     rax, rsp
0x18001745f  mov     [rbp+7D0h+var_30], rax
0x180017466  xor     r12d, r12d
0x180017469  lea     r8, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180017470  mov     rbx, rcx
0x180017473  mov     [rsp+8D0h+hKey], r12
0x180017478  lea     rcx, [rsp+8D0h+pszDest]; pszDest
0x18001747d  mov     [rsp+8D0h+var_880], r12
0x180017482  mov     edx, 104h; cchDest
0x180017487  mov     [rsp+8D0h+cbData], r12d
0x18001748c  mov     edi, r12d
0x18001748f  mov     [rsp+8D0h+cchValueName], r12d
0x180017494  mov     [rsp+8D0h+var_88C], r12d
0x180017499  call    StringCchCopyW
0x18001749e  test    rbx, rbx
0x1800174a1  jz      short loc_1800174D0
0x1800174a3  lea     r8, IsBackslash
0x1800174aa  xor     edx, edx
0x1800174ac  mov     rcx, rbx; unsigned __int16 *
0x1800174af  call    PathIsUnc2
0x1800174b4  test    eax, eax
0x1800174b6  jnz     short loc_1800174D0
0x1800174b8  mov     rcx, rbx; unsigned __int16 *
0x1800174bb  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x1800174c0  test    al, al
0x1800174c2  jnz     short loc_1800174D0
0x1800174c4  jmp     short loc_1800174CA
0x1800174c6  add     rbx, 2
0x1800174ca  cmp     word ptr [rbx], 5Ch ; '\'
0x1800174ce  jz      short loc_1800174C6
0x1800174d0  mov     r9, rbx; pszMore
0x1800174d3  lea     r8, [rsp+8D0h+pszDest]; pszPathIn
0x1800174d8  mov     edx, 104h; cchPathOut
0x1800174dd  lea     rcx, [rsp+8D0h+pszDest]; pszPathOut
0x1800174e2  call    PathCchCombineEx
0x1800174e7  lea     rax, [rsp+8D0h+hKey]
0x1800174ec  mov     r9d, 20019h; samDesired
0x1800174f2  xor     r8d, r8d; ulOptions
0x1800174f5  mov     [rsp+8D0h+phkResult], rax; phkResult
0x1800174fa  lea     rdx, [rsp+8D0h+pszDest]; lpSubKey
0x1800174ff  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017506  call    cs:__imp_RegOpenKeyExW
0x18001750c  test    eax, eax
0x18001750e  jnz     loc_1800176F2
0x180017514  mov     r15d, r12d
0x180017517  mov     rcx, [rsp+8D0h+hKey]; hKey
0x18001751c  lea     r8, [rsp+8D0h+pszDest]; lpName
0x180017521  mov     r9d, 104h; cchName
0x180017527  mov     edx, r15d; dwIndex
0x18001752a  call    cs:__imp_RegEnumKeyW
0x180017530  test    eax, eax
0x180017532  jnz     loc_1800176E7
0x180017538  mov     rcx, [rsp+8D0h+hKey]; hKey
0x18001753d  lea     rax, [rsp+8D0h+var_880]
0x180017542  mov     r9d, 20019h; samDesired
0x180017548  mov     [rsp+8D0h+phkResult], rax; phkResult
0x18001754d  xor     r8d, r8d; ulOptions
0x180017550  mov     [rsp+8D0h+cbData], 208h
0x180017558  lea     rdx, [rsp+8D0h+pszDest]; lpSubKey
0x18001755d  call    cs:__imp_RegOpenKeyExW
0x180017563  test    eax, eax
0x180017565  jnz     loc_1800176DC
0x18001756b  mov     rcx, [rsp+8D0h+var_880]; hKey
0x180017570  lea     rax, [rsp+8D0h+cbData]
0x180017575  mov     [rsp+8D0h+lpcbData], rax; lpcbData
0x18001757a  xor     r9d, r9d; lpType
0x18001757d  lea     rax, [rbp+7D0h+Data]
0x180017584  xor     r8d, r8d; lpReserved
0x180017587  xor     edx, edx; lpValueName
0x180017589  mov     [rsp+8D0h+phkResult], rax; lpData
0x18001758e  call    cs:__imp_RegQueryValueExW
0x180017594  test    eax, eax
0x180017596  jnz     loc_1800176D1
0x18001759c  lea     rax, [rbp+7D0h+Data]
0x1800175a3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800175a7  inc     rsi
0x1800175aa  cmp     [rax+rsi*2], r12w
0x1800175af  jnz     short loc_1800175A7
0x1800175b1  mov     r14d, r12d
0x1800175b4  jmp     loc_1800176B9
0x1800175b9  mov     rcx, [rsp+8D0h+var_880]; hKey
0x1800175be  lea     rax, [rsp+8D0h+var_88C]
0x1800175c3  mov     [rsp+8D0h+var_898], rax; lpcbData
0x1800175c8  lea     r9, [rsp+8D0h+cchValueName]; lpcchValueName
0x1800175cd  lea     rax, [rbp+7D0h+var_240]
0x1800175d4  mov     edx, r14d; dwIndex
0x1800175d7  mov     [rsp+8D0h+lpData], rax; lpData
0x1800175dc  lea     r8, [rbp+7D0h+ValueName]; lpValueName
0x1800175e3  mov     [rsp+8D0h+lpcbData], r12; lpType
0x1800175e8  mov     [rsp+8D0h+phkResult], r12; dwFlags
0x1800175ed  call    cs:__imp_RegEnumValueW
0x1800175f3  test    eax, eax
0x1800175f5  jnz     loc_1800176D1
0x1800175fb  cmp     [rsp+8D0h+cchValueName], r12d
0x180017600  jz      loc_1800176B6
0x180017606  lea     r8, IsBackslash
0x18001760d  mov     [rbp+rsi*2+7D0h+Data], r12w
0x180017616  xor     edx, edx
0x180017618  lea     rcx, [rbp+7D0h+ValueName]; unsigned __int16 *
0x18001761f  lea     rbx, [rbp+7D0h+ValueName]
0x180017626  call    PathIsUnc2
0x18001762b  test    eax, eax
0x18001762d  jnz     short loc_180017653
0x18001762f  lea     rcx, [rbp+7D0h+ValueName]; unsigned __int16 *
0x180017636  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x18001763b  test    al, al
0x18001763d  jnz     short loc_180017653
0x18001763f  cmp     [rbp+7D0h+ValueName], 5Ch ; '\'
0x180017647  jnz     short loc_180017653
0x180017649  add     rbx, 2
0x18001764d  cmp     word ptr [rbx], 5Ch ; '\'
0x180017651  jz      short loc_180017649
0x180017653  mov     r9, rbx; pszMore
0x180017656  lea     r8, [rbp+7D0h+Data]; pszPathIn
0x18001765d  mov     edx, 104h; cchPathOut
0x180017662  lea     rcx, [rbp+7D0h+Data]; pszPathOut
0x180017669  call    PathCchCombineEx
0x18001766e  lea     rcx, [rbp+7D0h+Data]; lpFileName
0x180017675  call    cs:__imp_GetFileAttributesW
0x18001767b  mov     ebx, eax
0x18001767d  cmp     eax, 0FFFFFFFFh
0x180017680  jz      short loc_1800176B6
0x180017682  mov     edx, 2Ch ; ','; wMatch
0x180017687  lea     rcx, [rbp+7D0h+var_240]; pszStart
0x18001768e  call    cs:__imp_StrChrW
0x180017694  test    rax, rax
0x180017697  jz      short loc_1800176B1
0x180017699  lea     rcx, [rax+2]; String
0x18001769d  mov     [rax], r12w
0x1800176a1  call    _wtol_0
0x1800176a6  test    ebx, eax
0x1800176a8  mov     edi, r12d
0x1800176ab  setz    dil
0x1800176af  jmp     short loc_1800176B6
0x1800176b1  mov     edi, 1
0x1800176b6  inc     r14d
0x1800176b9  mov     [rsp+8D0h+var_88C], 208h
0x1800176c1  mov     [rsp+8D0h+cchValueName], 104h
0x1800176c9  test    edi, edi
0x1800176cb  jz      loc_1800175B9
0x1800176d1  mov     rcx, [rsp+8D0h+var_880]; hKey
0x1800176d6  call    cs:__imp_RegCloseKey
0x1800176dc  inc     r15d
0x1800176df  test    edi, edi
0x1800176e1  jz      loc_180017517
0x1800176e7  mov     rcx, [rsp+8D0h+hKey]; hKey
0x1800176ec  call    cs:__imp_RegCloseKey
0x1800176f2  mov     eax, edi
0x1800176f4  mov     rcx, [rbp+7D0h+var_30]
0x1800176fb  xor     rcx, rsp; StackCookie
0x1800176fe  call    __security_check_cookie
0x180017703  lea     r11, [rsp+8D0h+var_20]
0x18001770b  mov     rbx, [r11+38h]
0x18001770f  mov     rsi, [r11+40h]
0x180017713  mov     rsp, r11
0x180017716  pop     r15
0x180017718  pop     r14
0x18001771a  pop     r12
0x18001771c  pop     rdi
0x18001771d  pop     rbp
0x18001771e  retn
```
