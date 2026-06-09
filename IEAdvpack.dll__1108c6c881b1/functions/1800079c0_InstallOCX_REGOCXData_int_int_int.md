# InstallOCX(_REGOCXData *,int,int,int)

- ea: `0x1800079c0`
- end: `0x1800080c2`
- name: `?InstallOCX@@YAHPEAU_REGOCXData@@HHH@Z`
- size: `1794`
- prototype: `_BOOL8 __fastcall(struct _REGOCXData *, int, unsigned int, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800096f0`
- `0x180009928`

## callees

- `0x1800022bc`
- `0x180003180`
- `0x1800035c8`
- `0x180005d10`
- `0x180005d70`
- `0x1800068ac`
- `0x180006928`
- `0x1800079c0`
- `0x180008644`
- `0x180008a6c`
- `0x18000ae68`
- `0x18000c574`
- `0x18001b980`

## import_xrefs

- `USER32!CharNextW` at `0x180007e63`
- `USER32!CharNextW` at `0x180007e7d`
- `USER32!CharNextW` at `0x180007e63`
- `USER32!CharNextW` at `0x180007e7d`
- `USER32!CharUpperW` at `0x180007a49`
- `USER32!CharUpperW` at `0x180007a6f`
- `USER32!CharUpperW` at `0x180007a49`
- `USER32!CharUpperW` at `0x180007a6f`
- `KERNEL32!LocalFree` at `0x180007bff`
- `KERNEL32!LocalFree` at `0x180007c0d`
- `KERNEL32!LocalFree` at `0x180007bff`
- `KERNEL32!LocalFree` at `0x180007c0d`
- `KERNEL32!LocalAlloc` at `0x180007aa1`
- `KERNEL32!LocalAlloc` at `0x180007ab2`
- `KERNEL32!LocalAlloc` at `0x180007aa1`
- `KERNEL32!LocalAlloc` at `0x180007ab2`
- `KERNEL32!CompareStringW` at `0x180007b20`
- `KERNEL32!CompareStringW` at `0x180007b20`
- `KERNEL32!FreeLibrary` at `0x180007d0e`
- `KERNEL32!FreeLibrary` at `0x180007d0e`
- `KERNEL32!LoadLibraryExW` at `0x180007bbe`
- `KERNEL32!LoadLibraryExW` at `0x180007bbe`
- `ADVAPI32!RegCreateKeyExW` at `0x180007da5`
- `ADVAPI32!RegCreateKeyExW` at `0x180007e46`
- `ADVAPI32!RegCreateKeyExW` at `0x180007da5`
- `ADVAPI32!RegCreateKeyExW` at `0x180007e46`
- `ADVAPI32!RegCloseKey` at `0x180007be1`
- `ADVAPI32!RegCloseKey` at `0x180007bf1`
- `ADVAPI32!RegCloseKey` at `0x180007be1`
- `ADVAPI32!RegCloseKey` at `0x180007bf1`
- `ADVAPI32!RegSetValueExW` at `0x180008056`
- `ADVAPI32!RegSetValueExW` at `0x180008056`
- `ADVAPI32!RegSetValueW` at `0x180007e99`
- `ADVAPI32!RegSetValueW` at `0x180007e99`
- `SHLWAPI!StrChrW` at `0x180007a55`
- `SHLWAPI!StrChrW` at `0x180007a7b`
- `SHLWAPI!StrChrW` at `0x180007a55`
- `SHLWAPI!StrChrW` at `0x180007a7b`

## string_xrefs

- `0x180007a28`: `InstallOCX: %1 %2\n`
- `0x180007b7f`: `InstallOCX: %1 Failed\n`
- `0x180007ba9`: `LoadLibrary %1\n`
- `0x180007c75`: `Register: DoDllReg: %1\n`
- `0x180007ca7`: `Register: DoDllInstall: %1\n`
- `0x180007cc7`: `UnRegister: DoDllReg: %1\n`
- `0x180007cf4`: `UnRegister: DoDllInstall: %1\n`
- `0x180007ef9`: `DllRegisterServer`
- `0x180007f0a`: `DllUnregisterServer`
- `0x180007f44`: `DllInstall`
- `0x180007fcb`: `rundll32.exe advpack.dll,RegisterOCX %s,%s,%s`
- `0x180007c16`: `InstallOCX: End %1\n`

## pseudocode

```c
_BOOL8 __fastcall InstallOCX(struct _REGOCXData *a1, int a2, unsigned int a3, int a4)
{
  unsigned __int16 *v4; // rdi
  __int64 v7; // rdx
  BOOL v8; // ebx
  bool v10; // zf
  const wchar_t *v11; // r8
  DWORD v12; // r12d
  WCHAR *v13; // rcx
  const WCHAR *v14; // rax
  PWSTR v15; // rax
  __int64 v16; // r8
  WCHAR *v17; // rcx
  const WCHAR *v18; // rax
  unsigned __int16 *v19; // rax
  unsigned __int16 *v20; // r15
  __int64 v21; // rcx
  __int64 v22; // rax
  const unsigned __int16 *v23; // r8
  HMODULE Library; // rax
  HMODULE v25; // r15
  const wchar_t *v27; // rsi
  int v28; // eax
  const wchar_t *v29; // rdx
  int v30; // eax
  const wchar_t *v31; // rcx
  int v32; // eax
  const wchar_t *v33; // rdx
  int v34; // eax
  int v35; // eax
  const WCHAR *v36; // rdx
  LSTATUS v37; // eax
  int v38; // esi
  LSTATUS v39; // eax
  LPWSTR v40; // rax
  __int64 v41; // rsi
  const WCHAR *v42; // rax
  LSTATUS v43; // eax
  const unsigned __int16 *v44; // r8
  const WCHAR *v45; // r12
  HKEY v46; // r13
  const WCHAR *v47; // rcx
  const WCHAR *v48; // rax
  int i; // r15d
  const BYTE *v50; // r12
  __int64 v51; // rax
  LSTATUS v52; // eax
  int cchCount2[2]; // [rsp+28h] [rbp-D8h]
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  int v55; // [rsp+58h] [rbp-A8h]
  int v56; // [rsp+60h] [rbp-A0h]
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v58; // [rsp+70h] [rbp-90h]
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  BYTE *lpData; // [rsp+80h] [rbp-80h]
  const WCHAR *v61; // [rsp+88h] [rbp-78h]
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF

  v4 = 0;
  v56 = a4;
  phkResult = 0;
  hKey = 0;
  v7 = *(_QWORD *)a1;
  v8 = 1;
  v55 = 0;
  dwDisposition = 1;
  v10 = a3 == 0;
  v11 = L"Register";
  v12 = 1;
  if ( v10 )
    v11 = L"UnRegister";
  AdvWriteToLog(L"InstallOCX: %1 %2\r\n", v7, v11);
  v13 = (WCHAR *)*((_QWORD *)a1 + 1);
  if ( v13 && *v13 )
  {
    v14 = CharUpperW(v13);
    v15 = StrChrW(v14, 0x49u);
    v16 = 0;
    if ( !v15 )
    {
      v20 = 0;
      goto LABEL_20;
    }
    v17 = (WCHAR *)*((_QWORD *)a1 + 1);
    v55 = 1;
    v18 = CharUpperW(v17);
    v12 = StrChrW(v18, 0x4Eu) == 0;
    dwDisposition = v12;
  }
  v4 = (unsigned __int16 *)LocalAlloc(0x40u, 0x800u);
  v19 = (unsigned __int16 *)LocalAlloc(0x40u, 0x800u);
  v16 = 0;
  v58 = v19;
  v20 = v19;
  if ( !v4 || !v19 )
  {
    MsgBox2Param(hWnd, 0x44Eu, 0, 0, 0x10u, 0);
    goto LABEL_18;
  }
  if ( !a2 )
  {
    dwDisposition = 0;
    if ( dword_1800322F8 || (v34 = UseRunOnceEx(), v16 = 0, !v34) )
    {
      v35 = dword_1800322F4;
    }
    else
    {
      dword_1800322F8 = 799;
      v35 = 1;
      dword_1800322F4 = 1;
    }
    if ( v35 )
    {
      v36 = L"Software\\Microsoft\\Windows\\CurrentVersion\\RunOnceEx";
    }
    else
    {
      if ( **(_WORD **)a1 == 64 )
        goto LABEL_25;
      v36 = L"Software\\Microsoft\\Windows\\CurrentVersion\\RunOnce";
    }
    v37 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v36, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
    v16 = 0;
    if ( v37 )
      goto LABEL_20;
    v38 = v56;
    if ( !dword_1800322F4 )
      goto LABEL_81;
    if ( v56 )
      StringCchPrintfW(SubKey, 0x104u, L"%d", (unsigned int)dword_1800322F8);
    else
      GetNextRunOnceExSubKey(phkResult, SubKey, 0x104u, &dword_1800322F8);
    if ( dword_1800322F4 )
    {
      v39 = RegCreateKeyExW(phkResult, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
      v16 = 0;
      if ( v39 )
        goto LABEL_20;
      if ( **(_WORD **)a1 == 64 )
      {
        v40 = CharNextW(*(LPCWSTR *)a1);
        v41 = -1;
        do
          ++v41;
        while ( v40[v41] );
        v42 = CharNextW(*(LPCWSTR *)a1);
        v43 = RegSetValueW(phkResult, SubKey, 1u, v42, v41 + 1);
        v16 = 0;
        v8 = v43 == 0;
        goto LABEL_25;
      }
      GetNextRunOnceValName(hKey, L"%03d", SubKey, 0x104u, v38);
      v16 = 0;
      if ( v12 )
      {
        StringCchCopyW(v4, 0x400u, *(const unsigned __int16 **)a1);
        StringCchCatW(v4, 0x400u, L"|");
        v44 = L"DllRegisterServer";
        if ( !a3 )
          v44 = L"DllUnregisterServer";
        StringCchCatW(v4, 0x400u, v44);
        v16 = 0;
      }
      if ( v55 )
      {
        v45 = &word_18001DE6C;
        if ( *((_QWORD *)a1 + 2) )
          v45 = (const WCHAR *)*((_QWORD *)a1 + 2);
        cchCount2[0] = a3 != 0 ? 105 : 117;
        StringCchPrintfW(v20, 0x400u, L"%s|%s|%c,%s", *(_QWORD *)a1, L"DllInstall", *(_QWORD *)cchCount2, v45);
        v16 = 0;
      }
      v10 = a3 == 0;
      v46 = hKey;
      if ( v10 )
      {
        v61 = v4;
        lpData = (BYTE *)v20;
        goto LABEL_87;
      }
      v61 = v20;
    }
    else
    {
LABEL_81:
      GetNextRunOnceValName(phkResult, L"IExpressRegOCX%d", SubKey, 0x104u, v38);
      v47 = &word_18001DE6C;
      v48 = &word_18001DE6C;
      if ( *((_QWORD *)a1 + 2) )
        v47 = (const WCHAR *)*((_QWORD *)a1 + 2);
      if ( *((_QWORD *)a1 + 1) )
        v48 = (const WCHAR *)*((_QWORD *)a1 + 1);
      StringCchPrintfW(v4, 0x400u, L"rundll32.exe advpack.dll,RegisterOCX %s,%s,%s", *(_QWORD *)a1, v48, v47);
      v46 = phkResult;
      v16 = 0;
      v61 = &word_18001DE6C;
    }
    lpData = (BYTE *)v4;
LABEL_87:
    for ( i = 0; i < 2; ++i )
    {
      v50 = (&lpData)[i];
      if ( *(_WORD *)v50 )
      {
        AdvWriteToLog(L"Delay Register: Value=%1  Data=%2\r\n", SubKey, (&lpData)[i]);
        v51 = -1;
        do
          ++v51;
        while ( *(_WORD *)&v50[2 * v51] );
        v52 = RegSetValueExW(v46, SubKey, 0, 1u, v50, 2 * v51 + 2);
        v16 = 0;
        if ( v52 )
          goto LABEL_23;
        if ( dword_1800322F4 )
        {
          GetNextRunOnceValName(v46, L"%03d", SubKey, 0x104u, v56);
          v16 = 0;
        }
      }
    }
    goto LABEL_24;
  }
  v21 = *(_QWORD *)a1;
  if ( **(_WORD **)a1 == 64 )
    goto LABEL_25;
  v22 = -1;
  do
    ++v22;
  while ( *(_WORD *)(v21 + 2 * v22) );
  if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)(v21 + 2 * (v22 - 3)), -1, L"EXE", -1) != 2 )
  {
    AdvWriteToLog(L"LoadLibrary %1\r\n", *(_QWORD *)a1);
    Library = LoadLibraryExW(*(LPCWSTR *)a1, 0, 8u);
    v16 = 0;
    v25 = Library;
    if ( !Library )
    {
LABEL_23:
      v8 = 0;
LABEL_24:
      v20 = v58;
      goto LABEL_25;
    }
    v27 = L"Succeeded";
    if ( a3 )
    {
      if ( dwDisposition )
      {
        v28 = DoDllReg(Library, a3);
        v29 = L"Succeeded";
        v8 = v28;
        if ( !v28 )
          v29 = L"Failed";
        AdvWriteToLog(L"Register: DoDllReg: %1\r\n", v29);
        if ( !v8 )
          goto LABEL_50;
      }
      if ( !v55 )
        goto LABEL_50;
      v30 = DoDllInst(v25, a3, *((const unsigned __int16 **)a1 + 2));
      v31 = L"Register: DoDllInstall: %1\r\n";
    }
    else
    {
      if ( v55 )
      {
        v32 = DoDllInst(Library, 0, *((const unsigned __int16 **)a1 + 2));
        v33 = L"Succeeded";
        v8 = v32;
        if ( !v32 )
          v33 = L"Failed";
        AdvWriteToLog(L"UnRegister: DoDllReg: %1\r\n", v33);
        if ( !v8 )
          goto LABEL_50;
      }
      if ( !dwDisposition )
        goto LABEL_50;
      v30 = DoDllReg(v25, 0);
      v31 = L"UnRegister: DoDllInstall: %1\r\n";
    }
    v8 = v30;
    if ( !v30 )
      v27 = L"Failed";
    AdvWriteToLog(v31, v27);
LABEL_50:
    FreeLibrary(v25);
    goto LABEL_24;
  }
  StringCchCopyW(v4, 0x400u, *(const unsigned __int16 **)a1);
  v23 = L" /RegServer";
  if ( !a3 )
    v23 = L" /UnRegServer";
  StringCchCatW(v4, 0x400u, v23);
  if ( (unsigned int)LaunchAndWait(v4, 0, 0, 0xFFFFFFFF, 0) == -2147467259 )
  {
    AdvWriteToLog(L"InstallOCX: %1 Failed\r\n", v4);
LABEL_18:
    v16 = 0;
LABEL_20:
    v8 = 0;
    goto LABEL_25;
  }
  AdvWriteToLog(L"%1 : Succeeded.\r\n", v4);
LABEL_25:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v4 )
    LocalFree(v4);
  if ( v20 )
    LocalFree(v20);
  AdvWriteToLog(L"InstallOCX: End %1\r\n", *(_QWORD *)a1, v16);
  return v8;
}

```

## disassembly

```asm
0x1800079c0  mov     [rsp-8+arg_8], rbx
0x1800079c5  push    rbp
0x1800079c6  push    rsi
0x1800079c7  push    rdi
0x1800079c8  push    r12
0x1800079ca  push    r13
0x1800079cc  push    r14
0x1800079ce  push    r15
0x1800079d0  lea     rbp, [rsp-1B0h]
0x1800079d8  sub     rsp, 2B0h
0x1800079df  mov     rax, cs:__security_cookie
0x1800079e6  xor     rax, rsp
0x1800079e9  mov     [rbp+1E0h+var_40], rax
0x1800079f0  xor     edi, edi
0x1800079f2  mov     [rsp+2E0h+var_280], r9d
0x1800079f7  mov     r13d, r8d
0x1800079fa  mov     [rsp+2E0h+var_278], rdi
0x1800079ff  mov     esi, edx
0x180007a01  mov     [rsp+2E0h+hKey], rdi
0x180007a06  mov     rdx, [rcx]
0x180007a09  lea     rax, aUnregister; "UnRegister"
0x180007a10  lea     ebx, [rdi+1]
0x180007a13  mov     [rsp+2E0h+var_288], edi
0x180007a17  mov     r14, rcx
0x180007a1a  mov     [rsp+2E0h+dwDisposition], ebx
0x180007a1e  test    r13d, r13d
0x180007a21  lea     r8, aRegister; "Register"
0x180007a28  lea     rcx, aInstallocx12; "InstallOCX: %1 %2\r\n"
0x180007a2f  mov     r12d, ebx
0x180007a32  cmovz   r8, rax
0x180007a36  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x180007a3b  mov     rcx, [r14+8]; lpsz
0x180007a3f  test    rcx, rcx
0x180007a42  jz      short loc_180007A93
0x180007a44  cmp     [rcx], di
0x180007a47  jz      short loc_180007A93
0x180007a49  call    cs:__imp_CharUpperW
0x180007a4f  mov     rcx, rax; pszStart
0x180007a52  lea     edx, [rdi+49h]; wMatch
0x180007a55  call    cs:__imp_StrChrW
0x180007a5b  xor     r8d, r8d
0x180007a5e  test    rax, rax
0x180007a61  jz      loc_180007B90
0x180007a67  mov     rcx, [r14+8]; lpsz
0x180007a6b  mov     [rsp+2E0h+var_288], ebx
0x180007a6f  call    cs:__imp_CharUpperW
0x180007a75  mov     rcx, rax; pszStart
0x180007a78  lea     edx, [rdi+4Eh]; wMatch
0x180007a7b  call    cs:__imp_StrChrW
0x180007a81  xor     r8d, r8d
0x180007a84  mov     r12d, r8d
0x180007a87  test    rax, rax
0x180007a8a  setz    r12b
0x180007a8e  mov     [rsp+2E0h+dwDisposition], r12d
0x180007a93  mov     r15d, 800h
0x180007a99  mov     ecx, 40h ; '@'; uFlags
0x180007a9e  mov     edx, r15d; uBytes
0x180007aa1  call    cs:__imp_LocalAlloc
0x180007aa7  mov     edx, r15d; uBytes
0x180007aaa  mov     ecx, 40h ; '@'; uFlags
0x180007aaf  mov     rdi, rax
0x180007ab2  call    cs:__imp_LocalAlloc
0x180007ab8  xor     r8d, r8d; unsigned __int16 *
0x180007abb  mov     [rsp+2E0h+var_270], rax
0x180007ac0  mov     r15, rax
0x180007ac3  test    rdi, rdi
0x180007ac6  jz      loc_18000809C
0x180007acc  test    rax, rax
0x180007acf  jz      loc_18000809C
0x180007ad5  test    esi, esi
0x180007ad7  jz      loc_180007D19
0x180007add  mov     rcx, [r14]
0x180007ae0  lea     eax, [r8+40h]
0x180007ae4  cmp     [rcx], ax
0x180007ae7  jz      loc_180007BD7
0x180007aed  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180007af1  mov     rax, rsi
0x180007af4  inc     rax
0x180007af7  cmp     [rcx+rax*2], r8w
0x180007afc  jnz     short loc_180007AF4
0x180007afe  add     rax, 0FFFFFFFFFFFFFFFDh
0x180007b02  mov     [rsp+2E0h+cchCount2], esi; cchCount2
0x180007b06  mov     r9d, esi; cchCount1
0x180007b09  mov     edx, ebx; dwCmpFlags
0x180007b0b  lea     r8, [rcx+rax*2]; lpString1
0x180007b0f  mov     ecx, 7Fh; Locale
0x180007b14  lea     rax, aExe; "EXE"
0x180007b1b  mov     [rsp+2E0h+lpString2], rax; lpString2
0x180007b20  call    cs:__imp_CompareStringW
0x180007b26  xor     r12d, r12d
0x180007b29  add     eax, 0FFFFFFFEh
0x180007b2c  jnz     short loc_180007BA6
0x180007b2e  mov     r8, [r14]; unsigned __int16 *
0x180007b31  mov     esi, 400h
0x180007b36  mov     edx, esi; unsigned __int64
0x180007b38  mov     rcx, rdi; unsigned __int16 *
0x180007b3b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007b40  lea     rax, aUnregserver; " /UnRegServer"
0x180007b47  test    r13d, r13d
0x180007b4a  lea     r8, aRegserver; " /RegServer"
0x180007b51  mov     edx, esi; unsigned __int64
0x180007b53  cmovz   r8, rax; unsigned __int16 *
0x180007b57  mov     rcx, rdi; unsigned __int16 *
0x180007b5a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007b5f  or      r9d, 0FFFFFFFFh; unsigned int
0x180007b63  mov     dword ptr [rsp+2E0h+lpString2], r12d; unsigned int
0x180007b68  xor     r8d, r8d; void **
0x180007b6b  xor     edx, edx; lpCurrentDirectory
0x180007b6d  mov     rcx, rdi; unsigned __int16 *
0x180007b70  call    ?LaunchAndWait@@YAJPEBG0PEAPEAXKK@Z; LaunchAndWait(ushort const *,ushort const *,void * *,ulong,ulong)
0x180007b75  mov     rdx, rdi
0x180007b78  cmp     eax, 80004005h
0x180007b7d  jnz     short loc_180007B98
0x180007b7f  lea     rcx, aInstallocx1Fai; "InstallOCX: %1 Failed\r\n"
0x180007b86  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x180007b8b  xor     r8d, r8d
0x180007b8e  jmp     short loc_180007B93
0x180007b90  mov     r15, r8
0x180007b93  mov     ebx, r8d
0x180007b96  jmp     short loc_180007BD7
0x180007b98  lea     rcx, a1Succeeded; "%1 : Succeeded.\r\n"
0x180007b9f  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x180007ba4  jmp     short loc_180007BD7
0x180007ba6  mov     rdx, [r14]
0x180007ba9  lea     rcx, aLoadlibrary1; "LoadLibrary %1\r\n"
0x180007bb0  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x180007bb5  mov     rcx, [r14]; lpLibFileName
0x180007bb8  xor     edx, edx; hFile
0x180007bba  lea     r8d, [rdx+8]; dwFlags
0x180007bbe  call    cs:__imp_LoadLibraryExW
0x180007bc4  xor     r8d, r8d
0x180007bc7  mov     r15, rax
0x180007bca  test    rax, rax
0x180007bcd  jnz     short loc_180007C4E
0x180007bcf  mov     ebx, r8d
0x180007bd2  mov     r15, [rsp+2E0h+var_270]
0x180007bd7  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180007bdc  test    rcx, rcx
0x180007bdf  jz      short loc_180007BE7
0x180007be1  call    cs:__imp_RegCloseKey
0x180007be7  mov     rcx, [rsp+2E0h+var_278]; hKey
0x180007bec  test    rcx, rcx
0x180007bef  jz      short loc_180007BF7
0x180007bf1  call    cs:__imp_RegCloseKey
0x180007bf7  test    rdi, rdi
0x180007bfa  jz      short loc_180007C05
0x180007bfc  mov     rcx, rdi; hMem
0x180007bff  call    cs:__imp_LocalFree
0x180007c05  test    r15, r15
0x180007c08  jz      short loc_180007C13
0x180007c0a  mov     rcx, r15; hMem
0x180007c0d  call    cs:__imp_LocalFree
0x180007c13  mov     rdx, [r14]
0x180007c16  lea     rcx, aInstallocxEnd1; "InstallOCX: End %1\r\n"
0x180007c1d  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x180007c22  mov     eax, ebx
0x180007c24  mov     rcx, [rbp+1E0h+var_40]
0x180007c2b  xor     rcx, rsp; StackCookie
0x180007c2e  call    __security_check_cookie
0x180007c33  mov     rbx, [rsp+2E0h+arg_8]
0x180007c3b  add     rsp, 2B0h
0x180007c42  pop     r15
0x180007c44  pop     r14
0x180007c46  pop     r13
0x180007c48  pop     r12
0x180007c4a  pop     rdi
0x180007c4b  pop     rsi
0x180007c4c  pop     rbp
0x180007c4d  retn
0x180007c4e  lea     r12, aFailed; "Failed"
0x180007c55  lea     rsi, aSucceeded; "Succeeded"
0x180007c5c  test    r13d, r13d
0x180007c5f  jz      short loc_180007CB0
0x180007c61  cmp     [rsp+2E0h+dwDisposition], r8d
0x180007c66  jz      short loc_180007C91
0x180007c68  mov     edx, r13d; int
0x180007c6b  mov     rcx, r15; HINSTANCE
0x180007c6e  call    ?DoDllReg@@YAHPEAUHINSTANCE__@@H@Z; DoDllReg(HINSTANCE__ *,int)
0x180007c73  test    eax, eax
0x180007c75  lea     rcx, aRegisterDodllr; "Register: DoDllReg: %1\r\n"
0x180007c7c  mov     rdx, rsi
0x180007c7f  mov     ebx, eax
0x180007c81  cmovz   rdx, r12
0x180007c85  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x180007c8a  xor     r8d, r8d
0x180007c8d  test    ebx, ebx
0x180007c8f  jz      short loc_180007D0B
0x180007c91  cmp     [rsp+2E0h+var_288], r8d
0x180007c96  jz      short loc_180007D0B
0x180007c98  mov     r8, [r14+10h]; unsigned __int16 *
0x180007c9c  mov     edx, r13d; int
0x180007c9f  mov     rcx, r15; HINSTANCE
0x180007ca2  call    ?DoDllInst@@YAHPEAUHINSTANCE__@@HPEBG@Z; DoDllInst(HINSTANCE__ *,int,ushort const *)
0x180007ca7  lea     rcx, aRegisterDodlli; "Register: DoDllInstall: %1\r\n"
0x180007cae  jmp     short loc_180007CFB
0x180007cb0  cmp     [rsp+2E0h+var_288], r8d
0x180007cb5  jz      short loc_180007CE3
0x180007cb7  mov     r8, [r14+10h]; unsigned __int16 *
0x180007cbb  xor     edx, edx; int
0x180007cbd  mov     rcx, r15; HINSTANCE
0x180007cc0  call    ?DoDllInst@@YAHPEAUHINSTANCE__@@HPEBG@Z; DoDllInst(HINSTANCE__ *,int,ushort const *)
0x180007cc5  test    eax, eax
0x180007cc7  lea     rcx, aUnregisterDodl_0; "UnRegister: DoDllReg: %1\r\n"
0x180007cce  mov     rdx, rsi
0x180007cd1  mov     ebx, eax
0x180007cd3  cmovz   rdx, r12
0x180007cd7  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x180007cdc  xor     r8d, r8d
0x180007cdf  test    ebx, ebx
0x180007ce1  jz      short loc_180007D0B
0x180007ce3  cmp     [rsp+2E0h+dwDisposition], r8d
0x180007ce8  jz      short loc_180007D0B
0x180007cea  xor     edx, edx; int
0x180007cec  mov     rcx, r15; HINSTANCE
0x180007cef  call    ?DoDllReg@@YAHPEAUHINSTANCE__@@H@Z; DoDllReg(HINSTANCE__ *,int)
0x180007cf4  lea     rcx, aUnregisterDodl; "UnRegister: DoDllInstall: %1\r\n"
0x180007cfb  test    eax, eax
0x180007cfd  mov     ebx, eax
0x180007cff  cmovz   rsi, r12
0x180007d03  mov     rdx, rsi
0x180007d06  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x180007d0b  mov     rcx, r15; hLibModule
0x180007d0e  call    cs:__imp_FreeLibrary
0x180007d14  jmp     loc_180007BD2
0x180007d19  cmp     cs:dword_1800322F8, r8d
0x180007d20  mov     [rsp+2E0h+dwDisposition], r8d
0x180007d25  jnz     short loc_180007D47
0x180007d27  call    ?UseRunOnceEx@@YAHXZ; UseRunOnceEx(void)
0x180007d2c  xor     r8d, r8d
0x180007d2f  test    eax, eax
0x180007d31  jz      short loc_180007D47
0x180007d33  mov     cs:dword_1800322F8, 31Fh
0x180007d3d  mov     eax, ebx
0x180007d3f  mov     cs:dword_1800322F4, ebx
0x180007d45  jmp     short loc_180007D4D
0x180007d47  mov     eax, cs:dword_1800322F4
0x180007d4d  test    eax, eax
0x180007d4f  jnz     short loc_180007D6B
0x180007d51  mov     rax, [r14]
0x180007d54  mov     ecx, 40h ; '@'
0x180007d59  cmp     [rax], cx
0x180007d5c  jz      loc_180007BD7
0x180007d62  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180007d69  jmp     short loc_180007D72
0x180007d6b  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180007d72  lea     rax, [rsp+2E0h+dwDisposition]
0x180007d77  xor     r9d, r9d; lpClass
0x180007d7a  mov     [rsp+2E0h+lpdwDisposition], rax; lpdwDisposition
0x180007d7f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180007d86  lea     rax, [rsp+2E0h+var_278]
0x180007d8b  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180007d90  mov     [rsp+2E0h+lpSecurityAttributes], r8; lpSecurityAttributes
0x180007d95  mov     [rsp+2E0h+cchCount2], 2001Fh; samDesired
0x180007d9d  mov     dword ptr [rsp+2E0h+lpString2], r8d; dwOptions
0x180007da2  xor     r8d, r8d; Reserved
0x180007da5  call    cs:__imp_RegCreateKeyExW
0x180007dab  xor     r8d, r8d
0x180007dae  test    eax, eax
0x180007db0  jnz     loc_180007B93
0x180007db6  cmp     cs:dword_1800322F4, r8d
0x180007dbd  mov     esi, [rsp+2E0h+var_280]
0x180007dc1  jz      loc_180007F87
0x180007dc7  test    esi, esi
0x180007dc9  jnz     short loc_180007DE8
0x180007dcb  mov     rcx, [rsp+2E0h+var_278]; hKey
0x180007dd0  lea     r9, dword_1800322F8; int *
0x180007dd7  mov     r8d, 104h; unsigned int
0x180007ddd  lea     rdx, [rbp+1E0h+SubKey]; unsigned __int16 *
0x180007de1  call    ?GetNextRunOnceExSubKey@@YAXPEAUHKEY__@@PEAGKPEAH@Z; GetNextRunOnceExSubKey(HKEY__ *,ushort *,ulong,int *)
0x180007de6  jmp     short loc_180007E04
0x180007de8  mov     r9d, cs:dword_1800322F8
0x180007def  lea     r8, aD; "%d"
0x180007df6  mov     edx, 104h; unsigned __int64
0x180007dfb  lea     rcx, [rbp+1E0h+SubKey]; unsigned __int16 *
0x180007dff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007e04  xor     ecx, ecx
0x180007e06  cmp     cs:dword_1800322F4, ecx
0x180007e0c  jz      loc_180007F87
0x180007e12  lea     rax, [rsp+2E0h+dwDisposition]
0x180007e17  xor     r9d, r9d; lpClass
0x180007e1a  mov     [rsp+2E0h+lpdwDisposition], rax; lpdwDisposition
0x180007e1f  lea     rdx, [rbp+1E0h+SubKey]; lpSubKey
0x180007e23  lea     rax, [rsp+2E0h+hKey]
0x180007e28  xor     r8d, r8d; Reserved
0x180007e2b  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180007e30  mov     [rsp+2E0h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x180007e35  mov     [rsp+2E0h+cchCount2], 2001Fh; samDesired
0x180007e3d  mov     dword ptr [rsp+2E0h+lpString2], ecx; dwOptions
0x180007e41  mov     rcx, [rsp+2E0h+var_278]; hKey
0x180007e46  call    cs:__imp_RegCreateKeyExW
0x180007e4c  xor     r8d, r8d
0x180007e4f  test    eax, eax
0x180007e51  jnz     loc_180007B93
0x180007e57  mov     rcx, [r14]; lpsz
0x180007e5a  lea     eax, [r8+40h]
0x180007e5e  cmp     [rcx], ax
0x180007e61  jnz     short loc_180007EAF
0x180007e63  call    cs:__imp_CharNextW
0x180007e69  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180007e6d  xor     r8d, r8d
  ... truncated ...
```
