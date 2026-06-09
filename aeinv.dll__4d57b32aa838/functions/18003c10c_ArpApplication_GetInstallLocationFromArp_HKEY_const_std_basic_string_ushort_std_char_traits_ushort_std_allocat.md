# ArpApplication::GetInstallLocationFromArp(HKEY__ * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18003c10c`
- end: `0x18003caa0`
- name: `?GetInstallLocationFromArp@ArpApplication@@QEAAXQEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@@Z`
- size: `2452`
- prototype: `__int64 __fastcall(__int64, HKEY, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, installer_update`

## callers

- `0x180007824`

## callees

- `0x18000deb4`
- `0x1800118d0`
- `0x1800172bc`
- `0x1800175b0`
- `0x180017724`
- `0x180018300`
- `0x180018450`
- `0x180018a60`
- `0x18001becc`
- `0x18001ccfc`
- `0x18001e0d0`
- `0x180022500`
- `0x1800260f4`
- `0x180027c48`
- `0x18002e8f8`
- `0x18003c10c`
- `0x18003d33c`
- `0x1800404c4`
- `0x180046c3c`
- `0x180052f28`
- `0x180059920`
- `0x1800f7e8c`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x18003c1f9`
- `KERNEL32!GetFileAttributesW` at `0x18003c338`
- `KERNEL32!GetFileAttributesW` at `0x18003c46b`
- `KERNEL32!GetFileAttributesW` at `0x18003c59e`
- `KERNEL32!GetFileAttributesW` at `0x18003c6b8`
- `KERNEL32!GetFileAttributesW` at `0x18003c7a2`
- `KERNEL32!GetFileAttributesW` at `0x18003c89d`
- `KERNEL32!GetFileAttributesW` at `0x18003ca22`
- `KERNEL32!GetFileAttributesW` at `0x18003c1f9`
- `KERNEL32!GetFileAttributesW` at `0x18003c338`
- `KERNEL32!GetFileAttributesW` at `0x18003c46b`
- `KERNEL32!GetFileAttributesW` at `0x18003c59e`
- `KERNEL32!GetFileAttributesW` at `0x18003c6b8`
- `KERNEL32!GetFileAttributesW` at `0x18003c7a2`
- `KERNEL32!GetFileAttributesW` at `0x18003c89d`
- `KERNEL32!GetFileAttributesW` at `0x18003ca22`
- `SHLWAPI!PathIsNetworkPathW` at `0x18003c216`
- `SHLWAPI!PathIsNetworkPathW` at `0x18003c355`
- `SHLWAPI!PathIsNetworkPathW` at `0x18003c488`
- `SHLWAPI!PathIsNetworkPathW` at `0x18003c5bb`
- `SHLWAPI!PathIsNetworkPathW` at `0x18003c6d6`
- `SHLWAPI!PathIsNetworkPathW` at `0x18003c7c0`
- `SHLWAPI!PathIsNetworkPathW` at `0x18003c8bb`
- `SHLWAPI!PathIsNetworkPathW` at `0x18003ca3e`
- `SHLWAPI!PathIsNetworkPathW` at `0x18003c216`
- `SHLWAPI!PathIsNetworkPathW` at `0x18003c355`
- `SHLWAPI!PathIsNetworkPathW` at `0x18003c488`
- `SHLWAPI!PathIsNetworkPathW` at `0x18003c5bb`
- `SHLWAPI!PathIsNetworkPathW` at `0x18003c6d6`
- `SHLWAPI!PathIsNetworkPathW` at `0x18003c7c0`
- `SHLWAPI!PathIsNetworkPathW` at `0x18003c8bb`
- `SHLWAPI!PathIsNetworkPathW` at `0x18003ca3e`

## string_xrefs

- `0x18003c148`: `InstallLocation`
- `0x18003c24c`: `InstallSource`
- `0x18003c4be`: `InstallPath`
- `0x18003c702`: `system32`
- `0x18003c8e0`: `Readme`

## pseudocode

```c
__int64 __fastcall ArpApplication::GetInstallLocationFromArp(__int64 a1, HKEY a2, const WCHAR *a3, __int64 a4)
{
  __int64 v8; // rdx
  __int64 v9; // rax
  LPCWSTR v10; // rbx
  const WCHAR *v11; // rsi
  const WCHAR *v12; // rcx
  DWORD v13; // eax
  const WCHAR *v14; // rcx
  __int64 RegValueString; // rax
  __int64 v16; // rdx
  __int64 v17; // rax
  LPCWSTR v18; // rbx
  const WCHAR *v19; // rsi
  const WCHAR *v20; // rcx
  DWORD FileAttributesW; // eax
  const WCHAR *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rax
  LPCWSTR v26; // rbx
  const WCHAR *v27; // rsi
  const WCHAR *v28; // rcx
  DWORD v29; // eax
  const WCHAR *v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rax
  LPCWSTR v34; // rbx
  const WCHAR *v35; // rsi
  const WCHAR *v36; // rcx
  DWORD v37; // eax
  const WCHAR *v38; // rcx
  LPCWSTR *v39; // rcx
  __int64 v40; // rcx
  LPCWSTR *v41; // rdx
  LPCWSTR *v42; // rcx
  __int64 InstallLocationFromUninstallString; // rax
  const WCHAR *v44; // rcx
  DWORD v45; // eax
  const WCHAR *v46; // rcx
  LPCWSTR *v47; // r9
  __int64 v48; // rdx
  __int64 v49; // rax
  const WCHAR *v50; // rcx
  DWORD v51; // eax
  const WCHAR *v52; // rcx
  __int64 v53; // rax
  __int64 v54; // rdx
  __int64 v55; // rax
  const WCHAR *v56; // rcx
  DWORD v57; // eax
  const WCHAR *v58; // rcx
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // rax
  __int64 LongPath; // rax
  const WCHAR *p_Src; // rcx
  DWORD v65; // eax
  const WCHAR *v66; // rcx
  LPCWSTR pszPath[2]; // [rsp+38h] [rbp-91h] BYREF
  unsigned __int64 v69; // [rsp+48h] [rbp-81h]
  unsigned __int64 v70; // [rsp+50h] [rbp-79h]
  LPCWSTR lpFileName[3]; // [rsp+58h] [rbp-71h] BYREF
  unsigned __int64 v72; // [rsp+70h] [rbp-59h]
  LPCWSTR Src; // [rsp+78h] [rbp-51h] BYREF
  const WCHAR *v74; // [rsp+80h] [rbp-49h]
  __int64 v75; // [rsp+88h] [rbp-41h]
  unsigned __int64 v76; // [rsp+90h] [rbp-39h]
  _BYTE v77[32]; // [rsp+98h] [rbp-31h] BYREF
  WCHAR v78[16]; // [rsp+B8h] [rbp-11h] BYREF

  std::wstring::wstring(v78, L"InstallLocation");
  Utility::GetRegValueString((__int64)pszPath, a2, a3, v78);
  std::wstring::~wstring(v78);
  v8 = Utility::TrimSpace(pszPath);
  std::wstring::operator=(pszPath, v8);
  v9 = Utility::ReplaceForwardSlashes(lpFileName, pszPath);
  std::wstring::operator=(pszPath, v9);
  std::wstring::~wstring(lpFileName);
  if ( !v69 )
  {
LABEL_14:
    std::wstring::wstring(lpFileName, L"InstallSource");
    RegValueString = Utility::GetRegValueString((__int64)&Src, a2, a3, (const WCHAR *)lpFileName);
    std::wstring::operator=(pszPath, RegValueString);
    std::wstring::~wstring(&Src);
    std::wstring::~wstring(lpFileName);
    v16 = Utility::TrimSpace(pszPath);
    std::wstring::operator=(pszPath, v16);
    v17 = Utility::ReplaceForwardSlashes(lpFileName, pszPath);
    std::wstring::operator=(pszPath, v17);
    std::wstring::~wstring(lpFileName);
    if ( v69 )
    {
      Utility::Split(&Src, pszPath, 34);
      v18 = Src;
      v19 = v74;
      while ( v18 != v19 )
      {
        std::wstring::wstring(lpFileName, v18);
        v20 = (const WCHAR *)lpFileName;
        if ( v72 > 7 )
          v20 = lpFileName[0];
        FileAttributesW = GetFileAttributesW(v20);
        if ( FileAttributesW != -1 && (FileAttributesW & 0x10) != 0 )
        {
          v22 = (const WCHAR *)lpFileName;
          if ( v72 > 7 )
            v22 = lpFileName[0];
          if ( !PathIsNetworkPathW(v22) && (unsigned __int8)Utility::ShouldScanInstallDirectoryForFiles(lpFileName) )
            goto LABEL_16;
        }
        std::wstring::~wstring(lpFileName);
        v18 += 16;
      }
      std::vector<std::wstring>::_Tidy(&Src);
    }
    std::wstring::wstring(lpFileName, L"LocationRoot");
    v23 = Utility::GetRegValueString((__int64)&Src, a2, a3, (const WCHAR *)lpFileName);
    std::wstring::operator=(pszPath, v23);
    std::wstring::~wstring(&Src);
    std::wstring::~wstring(lpFileName);
    v24 = Utility::TrimSpace(pszPath);
    std::wstring::operator=(pszPath, v24);
    v25 = Utility::ReplaceForwardSlashes(lpFileName, pszPath);
    std::wstring::operator=(pszPath, v25);
    std::wstring::~wstring(lpFileName);
    if ( v69 )
    {
      Utility::Split(&Src, pszPath, 34);
      v26 = Src;
      v27 = v74;
      while ( v26 != v27 )
      {
        std::wstring::wstring(lpFileName, v26);
        v28 = (const WCHAR *)lpFileName;
        if ( v72 > 7 )
          v28 = lpFileName[0];
        v29 = GetFileAttributesW(v28);
        if ( v29 != -1 && (v29 & 0x10) != 0 )
        {
          v30 = (const WCHAR *)lpFileName;
          if ( v72 > 7 )
            v30 = lpFileName[0];
          if ( !PathIsNetworkPathW(v30) && (unsigned __int8)Utility::ShouldScanInstallDirectoryForFiles(lpFileName) )
            goto LABEL_16;
        }
        std::wstring::~wstring(lpFileName);
        v26 += 16;
      }
      std::vector<std::wstring>::_Tidy(&Src);
    }
    std::wstring::wstring(lpFileName, L"InstallPath");
    v31 = Utility::GetRegValueString((__int64)&Src, a2, a3, (const WCHAR *)lpFileName);
    std::wstring::operator=(pszPath, v31);
    std::wstring::~wstring(&Src);
    std::wstring::~wstring(lpFileName);
    v32 = Utility::TrimSpace(pszPath);
    std::wstring::operator=(pszPath, v32);
    v33 = Utility::ReplaceForwardSlashes(lpFileName, pszPath);
    std::wstring::operator=(pszPath, v33);
    std::wstring::~wstring(lpFileName);
    if ( v69 )
    {
      Utility::Split(&Src, pszPath, 34);
      v34 = Src;
      v35 = v74;
      while ( v34 != v35 )
      {
        std::wstring::wstring(lpFileName, v34);
        v36 = (const WCHAR *)lpFileName;
        if ( v72 > 7 )
          v36 = lpFileName[0];
        v37 = GetFileAttributesW(v36);
        if ( v37 != -1 && (v37 & 0x10) != 0 )
        {
          v38 = (const WCHAR *)lpFileName;
          if ( v72 > 7 )
            v38 = lpFileName[0];
          if ( !PathIsNetworkPathW(v38) && (unsigned __int8)Utility::ShouldScanInstallDirectoryForFiles(lpFileName) )
            goto LABEL_16;
        }
        std::wstring::~wstring(lpFileName);
        v34 += 16;
      }
      std::vector<std::wstring>::_Tidy(&Src);
    }
    v69 = 0;
    v39 = pszPath;
    if ( v70 > 7 )
      v39 = (LPCWSTR *)pszPath[0];
    *(_WORD *)v39 = 0;
    ArpApplication::GetClickOnceInstallLocationFromArp(a2);
    if ( v69 )
    {
      std::wstring::operator=(a4, pszPath);
      v40 = a1 + 336;
      v41 = (LPCWSTR *)Application::ApplicationSourceClickOnce;
LABEL_60:
      std::wstring::operator=(v40, v41);
      return std::wstring::~wstring(pszPath);
    }
    v69 = 0;
    v42 = pszPath;
    if ( v70 > 7 )
      v42 = (LPCWSTR *)pszPath[0];
    *(_WORD *)v42 = 0;
    InstallLocationFromUninstallString = ArpApplication::GetInstallLocationFromUninstallString(a1, lpFileName, a2, a3);
    std::wstring::operator=(pszPath, InstallLocationFromUninstallString);
    std::wstring::~wstring(lpFileName);
    if ( !v69 )
      goto LABEL_73;
    v44 = (const WCHAR *)pszPath;
    if ( v70 > 7 )
      v44 = pszPath[0];
    v45 = GetFileAttributesW(v44);
    if ( v45 == -1 || (v45 & 0x10) == 0 )
      goto LABEL_73;
    v46 = (const WCHAR *)pszPath;
    if ( v70 > 7 )
      v46 = pszPath[0];
    if ( PathIsNetworkPathW(v46) || !(unsigned __int8)Utility::ShouldScanInstallDirectoryForFiles(pszPath) )
    {
LABEL_73:
      Utility::ToLower(&Src, a3);
      if ( std::wstring::find(&Src, L"system32", 0) != -1 )
      {
        std::wstring::wstring(lpFileName, L"syswow64");
        v47 = lpFileName;
        if ( v72 > 7 )
          v47 = (LPCWSTR *)lpFileName[0];
        v48 = -1;
        do
          ++v48;
        while ( *((_WORD *)v47 + v48) );
        std::wstring::_Replace<unsigned short>(&Src, v48);
        v49 = ArpApplication::GetInstallLocationFromUninstallString(a1, v77, a2, &Src);
        std::wstring::operator=(pszPath, v49);
        std::wstring::~wstring(v77);
        if ( v69 )
        {
          v50 = (const WCHAR *)pszPath;
          if ( v70 > 7 )
            v50 = pszPath[0];
          v51 = GetFileAttributesW(v50);
          if ( v51 != -1 && (v51 & 0x10) != 0 )
          {
            v52 = (const WCHAR *)pszPath;
            if ( v70 > 7 )
              v52 = pszPath[0];
            if ( !PathIsNetworkPathW(v52) && (unsigned __int8)Utility::ShouldScanInstallDirectoryForFiles(pszPath) )
            {
              std::wstring::operator=(a4, pszPath);
              std::wstring::~wstring(lpFileName);
              goto LABEL_113;
            }
          }
        }
        std::wstring::~wstring(lpFileName);
      }
      std::wstring::~wstring(&Src);
      std::wstring::wstring(lpFileName, L"ProductHome");
      v53 = Utility::GetRegValueString((__int64)v77, a2, a3, (const WCHAR *)lpFileName);
      std::wstring::operator=(pszPath, v53);
      std::wstring::~wstring(v77);
      std::wstring::~wstring(lpFileName);
      v54 = Utility::TrimSpace(pszPath);
      std::wstring::operator=(pszPath, v54);
      v55 = Utility::ReplaceForwardSlashes(v77, pszPath);
      std::wstring::operator=(pszPath, v55);
      std::wstring::~wstring(v77);
      if ( !v69 )
        goto LABEL_99;
      v56 = (const WCHAR *)pszPath;
      if ( v70 > 7 )
        v56 = pszPath[0];
      v57 = GetFileAttributesW(v56);
      if ( v57 == -1 || (v57 & 0x10) == 0 )
        goto LABEL_99;
      v58 = (const WCHAR *)pszPath;
      if ( v70 > 7 )
        v58 = pszPath[0];
      if ( PathIsNetworkPathW(v58) || !(unsigned __int8)Utility::ShouldScanInstallDirectoryForFiles(pszPath) )
      {
LABEL_99:
        std::wstring::wstring(lpFileName, L"Readme");
        v59 = Utility::GetRegValueString((__int64)v77, a2, a3, (const WCHAR *)lpFileName);
        std::wstring::operator=(pszPath, v59);
        std::wstring::~wstring(v77);
        std::wstring::~wstring(lpFileName);
        v60 = Utility::TrimSpace(pszPath);
        std::wstring::operator=(pszPath, v60);
        v61 = Utility::ReplaceForwardSlashes(v77, pszPath);
        std::wstring::operator=(pszPath, v61);
        std::wstring::~wstring(v77);
        if ( v69 <= 3 || !std::wstring::find(pszPath, L"http://", 0) )
          return std::wstring::~wstring(pszPath);
        Utility::GetDirectoryFromPath(&Src, pszPath);
        if ( v75 )
        {
          std::wstring::wstring(lpFileName, L"file://");
          if ( !std::wstring::find(pszPath, lpFileName) )
          {
            v62 = std::wstring::substr(&Src, v77, lpFileName[2], -1);
            std::wstring::operator=(&Src, v62);
            std::wstring::~wstring(v77);
            LongPath = Utility::GetLongPath(v77, &Src);
            std::wstring::operator=(&Src, LongPath);
            std::wstring::~wstring(v77);
            p_Src = (const WCHAR *)&Src;
            if ( v76 > 7 )
              p_Src = Src;
            v65 = GetFileAttributesW(p_Src);
            if ( v65 != -1 && (v65 & 0x10) != 0 )
            {
              v66 = (const WCHAR *)&Src;
              if ( v76 > 7 )
                v66 = Src;
              if ( !PathIsNetworkPathW(v66) && (unsigned __int8)Utility::ShouldScanInstallDirectoryForFiles(&Src) )
                std::wstring::operator=(a4, &Src);
            }
          }
          std::wstring::~wstring(lpFileName);
        }
LABEL_113:
        std::wstring::~wstring(&Src);
        return std::wstring::~wstring(pszPath);
      }
    }
    v41 = pszPath;
    v40 = a4;
    goto LABEL_60;
  }
  Utility::Split(&Src, pszPath, 34);
  v10 = Src;
  v11 = v74;
  while ( 1 )
  {
    if ( v10 == v11 )
    {
      std::vector<std::wstring>::_Tidy(&Src);
      goto LABEL_14;
    }
    std::wstring::wstring(lpFileName, v10);
    v12 = (const WCHAR *)lpFileName;
    if ( v72 > 7 )
      v12 = lpFileName[0];
    v13 = GetFileAttributesW(v12);
    if ( v13 != -1 && (v13 & 0x10) != 0 )
    {
      v14 = (const WCHAR *)lpFileName;
      if ( v72 > 7 )
        v14 = lpFileName[0];
      if ( !PathIsNetworkPathW(v14) && (unsigned __int8)Utility::ShouldScanInstallDirectoryForFiles(lpFileName) )
        break;
    }
    std::wstring::~wstring(lpFileName);
    v10 += 16;
  }
LABEL_16:
  std::wstring::operator=(a4, lpFileName);
  std::wstring::~wstring(lpFileName);
  std::vector<std::wstring>::_Tidy(&Src);
  return std::wstring::~wstring(pszPath);
}

```

## disassembly

```asm
0x18003c10c  push    rbp
0x18003c10e  push    rbx
0x18003c10f  push    rsi
0x18003c110  push    rdi
0x18003c111  push    r12
0x18003c113  push    r13
0x18003c115  push    r14
0x18003c117  push    r15
0x18003c119  lea     rbp, [rsp-1Fh]
0x18003c11e  sub     rsp, 0E8h
0x18003c125  mov     [rsp+120h+var_F0], 0FFFFFFFFFFFFFFFEh
0x18003c12e  mov     rax, cs:__security_cookie
0x18003c135  xor     rax, rsp
0x18003c138  mov     [rbp+57h+var_48], rax
0x18003c13c  mov     rdi, r9
0x18003c13f  mov     r14, r8
0x18003c142  mov     r15, rdx
0x18003c145  mov     r13, rcx
0x18003c148  lea     rdx, aInstalllocatio; "InstallLocation"
0x18003c14f  lea     rcx, [rbp+57h+var_68]
0x18003c153  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003c158  nop
0x18003c159  lea     r9, [rbp+57h+var_68]
0x18003c15d  mov     r8, r14
0x18003c160  mov     rdx, r15
0x18003c163  lea     rcx, [rsp+120h+pszPath]
0x18003c168  call    ?GetRegValueString@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAUHKEY__@@AEBV23@1_N@Z; Utility::GetRegValueString(HKEY__ * const,std::wstring const &,std::wstring const &,bool)
0x18003c16d  nop
0x18003c16e  lea     rcx, [rbp+57h+var_68]
0x18003c172  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c177  lea     rcx, [rsp+120h+pszPath]
0x18003c17c  call    ?TrimSpace@Utility@@SAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; Utility::TrimSpace(std::wstring &)
0x18003c181  mov     rdx, rax
0x18003c184  lea     rcx, [rsp+120h+pszPath]
0x18003c189  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003c18e  lea     rdx, [rsp+120h+pszPath]
0x18003c193  lea     rcx, [rbp+57h+lpFileName]
0x18003c197  call    ?ReplaceForwardSlashes@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ReplaceForwardSlashes(std::wstring const &)
0x18003c19c  mov     rdx, rax
0x18003c19f  lea     rcx, [rsp+120h+pszPath]
0x18003c1a4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003c1a9  lea     rcx, [rbp+57h+lpFileName]
0x18003c1ad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c1b2  xor     r12d, r12d
0x18003c1b5  cmp     [rsp+120h+var_D8], r12
0x18003c1ba  jbe     loc_18003C24C
0x18003c1c0  lea     r8d, [r12+22h]
0x18003c1c5  lea     rdx, [rsp+120h+pszPath]
0x18003c1ca  lea     rcx, [rbp+57h+Src]
0x18003c1ce  call    ?Split@Utility@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@G@Z; Utility::Split(std::wstring &,ushort)
0x18003c1d3  nop
0x18003c1d4  mov     rbx, [rbp+57h+Src]
0x18003c1d8  mov     rsi, [rbp+57h+var_A0]
0x18003c1dc  jmp     short loc_18003C23E
0x18003c1de  mov     rdx, rbx
0x18003c1e1  lea     rcx, [rbp+57h+lpFileName]
0x18003c1e5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003c1ea  nop
0x18003c1eb  lea     rcx, [rbp+57h+lpFileName]
0x18003c1ef  cmp     [rbp+57h+var_B0], 7
0x18003c1f4  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18003c1f9  call    cs:__imp_GetFileAttributesW
0x18003c1ff  cmp     eax, 0FFFFFFFFh
0x18003c202  jz      short loc_18003C231
0x18003c204  test    al, 10h
0x18003c206  jz      short loc_18003C231
0x18003c208  lea     rcx, [rbp+57h+lpFileName]
0x18003c20c  cmp     [rbp+57h+var_B0], 7
0x18003c211  cmova   rcx, [rbp+57h+lpFileName]; pszPath
0x18003c216  call    cs:__imp_PathIsNetworkPathW
0x18003c21c  test    eax, eax
0x18003c21e  jnz     short loc_18003C231
0x18003c220  lea     rcx, [rbp+57h+lpFileName]
0x18003c224  call    ?ShouldScanInstallDirectoryForFiles@Utility@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Utility::ShouldScanInstallDirectoryForFiles(std::wstring const &)
0x18003c229  test    al, al
0x18003c22b  jnz     loc_18003C2F8
0x18003c231  lea     rcx, [rbp+57h+lpFileName]
0x18003c235  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c23a  add     rbx, 20h ; ' '
0x18003c23e  cmp     rbx, rsi
0x18003c241  jnz     short loc_18003C1DE
0x18003c243  lea     rcx, [rbp+57h+Src]
0x18003c247  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18003c24c  lea     rdx, aInstallsource; "InstallSource"
0x18003c253  lea     rcx, [rbp+57h+lpFileName]
0x18003c257  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003c25c  nop
0x18003c25d  lea     r9, [rbp+57h+lpFileName]
0x18003c261  mov     r8, r14
0x18003c264  mov     rdx, r15
0x18003c267  lea     rcx, [rbp+57h+Src]
0x18003c26b  call    ?GetRegValueString@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAUHKEY__@@AEBV23@1_N@Z; Utility::GetRegValueString(HKEY__ * const,std::wstring const &,std::wstring const &,bool)
0x18003c270  mov     rdx, rax
0x18003c273  lea     rcx, [rsp+120h+pszPath]
0x18003c278  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003c27d  lea     rcx, [rbp+57h+Src]
0x18003c281  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c286  nop
0x18003c287  lea     rcx, [rbp+57h+lpFileName]
0x18003c28b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c290  lea     rcx, [rsp+120h+pszPath]
0x18003c295  call    ?TrimSpace@Utility@@SAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; Utility::TrimSpace(std::wstring &)
0x18003c29a  mov     rdx, rax
0x18003c29d  lea     rcx, [rsp+120h+pszPath]
0x18003c2a2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003c2a7  lea     rdx, [rsp+120h+pszPath]
0x18003c2ac  lea     rcx, [rbp+57h+lpFileName]
0x18003c2b0  call    ?ReplaceForwardSlashes@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ReplaceForwardSlashes(std::wstring const &)
0x18003c2b5  mov     rdx, rax
0x18003c2b8  lea     rcx, [rsp+120h+pszPath]
0x18003c2bd  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003c2c2  lea     rcx, [rbp+57h+lpFileName]
0x18003c2c6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c2cb  cmp     [rsp+120h+var_D8], r12
0x18003c2d0  jbe     loc_18003C38B
0x18003c2d6  mov     r8d, 22h ; '"'
0x18003c2dc  lea     rdx, [rsp+120h+pszPath]
0x18003c2e1  lea     rcx, [rbp+57h+Src]
0x18003c2e5  call    ?Split@Utility@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@G@Z; Utility::Split(std::wstring &,ushort)
0x18003c2ea  nop
0x18003c2eb  mov     rbx, [rbp+57h+Src]
0x18003c2ef  mov     rsi, [rbp+57h+var_A0]
0x18003c2f3  jmp     loc_18003C37D
0x18003c2f8  lea     rdx, [rbp+57h+lpFileName]
0x18003c2fc  mov     rcx, rdi
0x18003c2ff  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003c304  nop
0x18003c305  lea     rcx, [rbp+57h+lpFileName]
0x18003c309  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c30e  nop
0x18003c30f  lea     rcx, [rbp+57h+Src]
0x18003c313  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18003c318  jmp     loc_18003CA76
0x18003c31d  mov     rdx, rbx
0x18003c320  lea     rcx, [rbp+57h+lpFileName]
0x18003c324  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003c329  nop
0x18003c32a  lea     rcx, [rbp+57h+lpFileName]
0x18003c32e  cmp     [rbp+57h+var_B0], 7
0x18003c333  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18003c338  call    cs:__imp_GetFileAttributesW
0x18003c33e  cmp     eax, 0FFFFFFFFh
0x18003c341  jz      short loc_18003C370
0x18003c343  test    al, 10h
0x18003c345  jz      short loc_18003C370
0x18003c347  lea     rcx, [rbp+57h+lpFileName]
0x18003c34b  cmp     [rbp+57h+var_B0], 7
0x18003c350  cmova   rcx, [rbp+57h+lpFileName]; pszPath
0x18003c355  call    cs:__imp_PathIsNetworkPathW
0x18003c35b  test    eax, eax
0x18003c35d  jnz     short loc_18003C370
0x18003c35f  lea     rcx, [rbp+57h+lpFileName]
0x18003c363  call    ?ShouldScanInstallDirectoryForFiles@Utility@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Utility::ShouldScanInstallDirectoryForFiles(std::wstring const &)
0x18003c368  test    al, al
0x18003c36a  jnz     loc_18003C434
0x18003c370  lea     rcx, [rbp+57h+lpFileName]
0x18003c374  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c379  add     rbx, 20h ; ' '
0x18003c37d  cmp     rbx, rsi
0x18003c380  jnz     short loc_18003C31D
0x18003c382  lea     rcx, [rbp+57h+Src]
0x18003c386  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18003c38b  lea     rdx, aLocationroot; "LocationRoot"
0x18003c392  lea     rcx, [rbp+57h+lpFileName]
0x18003c396  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003c39b  nop
0x18003c39c  lea     r9, [rbp+57h+lpFileName]
0x18003c3a0  mov     r8, r14
0x18003c3a3  mov     rdx, r15
0x18003c3a6  lea     rcx, [rbp+57h+Src]
0x18003c3aa  call    ?GetRegValueString@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAUHKEY__@@AEBV23@1_N@Z; Utility::GetRegValueString(HKEY__ * const,std::wstring const &,std::wstring const &,bool)
0x18003c3af  mov     rdx, rax
0x18003c3b2  lea     rcx, [rsp+120h+pszPath]
0x18003c3b7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003c3bc  lea     rcx, [rbp+57h+Src]
0x18003c3c0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c3c5  nop
0x18003c3c6  lea     rcx, [rbp+57h+lpFileName]
0x18003c3ca  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c3cf  lea     rcx, [rsp+120h+pszPath]
0x18003c3d4  call    ?TrimSpace@Utility@@SAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; Utility::TrimSpace(std::wstring &)
0x18003c3d9  mov     rdx, rax
0x18003c3dc  lea     rcx, [rsp+120h+pszPath]
0x18003c3e1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003c3e6  lea     rdx, [rsp+120h+pszPath]
0x18003c3eb  lea     rcx, [rbp+57h+lpFileName]
0x18003c3ef  call    ?ReplaceForwardSlashes@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ReplaceForwardSlashes(std::wstring const &)
0x18003c3f4  mov     rdx, rax
0x18003c3f7  lea     rcx, [rsp+120h+pszPath]
0x18003c3fc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003c401  lea     rcx, [rbp+57h+lpFileName]
0x18003c405  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c40a  cmp     [rsp+120h+var_D8], r12
0x18003c40f  jbe     loc_18003C4BE
0x18003c415  mov     r8d, 22h ; '"'
0x18003c41b  lea     rdx, [rsp+120h+pszPath]
0x18003c420  lea     rcx, [rbp+57h+Src]
0x18003c424  call    ?Split@Utility@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@G@Z; Utility::Split(std::wstring &,ushort)
0x18003c429  nop
0x18003c42a  mov     rbx, [rbp+57h+Src]
0x18003c42e  mov     rsi, [rbp+57h+var_A0]
0x18003c432  jmp     short loc_18003C4B0
0x18003c434  lea     rdx, [rbp+57h+lpFileName]
0x18003c438  mov     rcx, rdi
0x18003c43b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003c440  nop
0x18003c441  lea     rcx, [rbp+57h+lpFileName]
0x18003c445  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c44a  nop
0x18003c44b  jmp     loc_18003C30F
0x18003c450  mov     rdx, rbx
0x18003c453  lea     rcx, [rbp+57h+lpFileName]
0x18003c457  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003c45c  nop
0x18003c45d  lea     rcx, [rbp+57h+lpFileName]
0x18003c461  cmp     [rbp+57h+var_B0], 7
0x18003c466  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18003c46b  call    cs:__imp_GetFileAttributesW
0x18003c471  cmp     eax, 0FFFFFFFFh
0x18003c474  jz      short loc_18003C4A3
0x18003c476  test    al, 10h
0x18003c478  jz      short loc_18003C4A3
0x18003c47a  lea     rcx, [rbp+57h+lpFileName]
0x18003c47e  cmp     [rbp+57h+var_B0], 7
0x18003c483  cmova   rcx, [rbp+57h+lpFileName]; pszPath
0x18003c488  call    cs:__imp_PathIsNetworkPathW
0x18003c48e  test    eax, eax
0x18003c490  jnz     short loc_18003C4A3
0x18003c492  lea     rcx, [rbp+57h+lpFileName]
0x18003c496  call    ?ShouldScanInstallDirectoryForFiles@Utility@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Utility::ShouldScanInstallDirectoryForFiles(std::wstring const &)
0x18003c49b  test    al, al
0x18003c49d  jnz     loc_18003C567
0x18003c4a3  lea     rcx, [rbp+57h+lpFileName]
0x18003c4a7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c4ac  add     rbx, 20h ; ' '
0x18003c4b0  cmp     rbx, rsi
0x18003c4b3  jnz     short loc_18003C450
0x18003c4b5  lea     rcx, [rbp+57h+Src]
0x18003c4b9  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18003c4be  lea     rdx, aInstallpath; "InstallPath"
0x18003c4c5  lea     rcx, [rbp+57h+lpFileName]
0x18003c4c9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003c4ce  nop
0x18003c4cf  lea     r9, [rbp+57h+lpFileName]
0x18003c4d3  mov     r8, r14
0x18003c4d6  mov     rdx, r15
0x18003c4d9  lea     rcx, [rbp+57h+Src]
0x18003c4dd  call    ?GetRegValueString@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAUHKEY__@@AEBV23@1_N@Z; Utility::GetRegValueString(HKEY__ * const,std::wstring const &,std::wstring const &,bool)
0x18003c4e2  mov     rdx, rax
0x18003c4e5  lea     rcx, [rsp+120h+pszPath]
0x18003c4ea  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003c4ef  lea     rcx, [rbp+57h+Src]
0x18003c4f3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c4f8  nop
0x18003c4f9  lea     rcx, [rbp+57h+lpFileName]
0x18003c4fd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c502  lea     rcx, [rsp+120h+pszPath]
0x18003c507  call    ?TrimSpace@Utility@@SAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; Utility::TrimSpace(std::wstring &)
0x18003c50c  mov     rdx, rax
0x18003c50f  lea     rcx, [rsp+120h+pszPath]
0x18003c514  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003c519  lea     rdx, [rsp+120h+pszPath]
0x18003c51e  lea     rcx, [rbp+57h+lpFileName]
0x18003c522  call    ?ReplaceForwardSlashes@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ReplaceForwardSlashes(std::wstring const &)
0x18003c527  mov     rdx, rax
0x18003c52a  lea     rcx, [rsp+120h+pszPath]
0x18003c52f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003c534  lea     rcx, [rbp+57h+lpFileName]
0x18003c538  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c53d  cmp     [rsp+120h+var_D8], r12
0x18003c542  jbe     loc_18003C5ED
0x18003c548  mov     r8d, 22h ; '"'
0x18003c54e  lea     rdx, [rsp+120h+pszPath]
0x18003c553  lea     rcx, [rbp+57h+Src]
0x18003c557  call    ?Split@Utility@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@G@Z; Utility::Split(std::wstring &,ushort)
0x18003c55c  nop
0x18003c55d  mov     rbx, [rbp+57h+Src]
0x18003c561  mov     rsi, [rbp+57h+var_A0]
0x18003c565  jmp     short loc_18003C5DF
0x18003c567  lea     rdx, [rbp+57h+lpFileName]
0x18003c56b  mov     rcx, rdi
0x18003c56e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003c573  nop
0x18003c574  lea     rcx, [rbp+57h+lpFileName]
0x18003c578  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c57d  nop
0x18003c57e  jmp     loc_18003C30F
0x18003c583  mov     rdx, rbx
0x18003c586  lea     rcx, [rbp+57h+lpFileName]
0x18003c58a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003c58f  nop
0x18003c590  lea     rcx, [rbp+57h+lpFileName]
0x18003c594  cmp     [rbp+57h+var_B0], 7
0x18003c599  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18003c59e  call    cs:__imp_GetFileAttributesW
0x18003c5a4  cmp     eax, 0FFFFFFFFh
0x18003c5a7  jz      short loc_18003C5D2
0x18003c5a9  test    al, 10h
0x18003c5ab  jz      short loc_18003C5D2
0x18003c5ad  lea     rcx, [rbp+57h+lpFileName]
  ... truncated ...
```
