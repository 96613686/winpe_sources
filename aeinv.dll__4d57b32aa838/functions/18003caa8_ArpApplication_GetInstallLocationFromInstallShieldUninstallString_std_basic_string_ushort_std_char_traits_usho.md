# ArpApplication::GetInstallLocationFromInstallShieldUninstallString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18003caa8`
- end: `0x18003d334`
- name: `?GetInstallLocationFromInstallShieldUninstallString@ArpApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@0@Z`
- size: `2188`
- prototype: `_OWORD *__fastcall(_OWORD *, __int64 *)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18003d33c`

## callees

- `0x18000d834`
- `0x18000da54`
- `0x1800118d0`
- `0x1800150ac`
- `0x180018300`
- `0x180018450`
- `0x180018a60`
- `0x1800197d4`
- `0x18001e0d0`
- `0x18002d40c`
- `0x18002fdb4`
- `0x18003caa8`
- `0x180040254`
- `0x1800404c4`
- `0x180043598`
- `0x180044c88`
- `0x180045480`
- `0x180047e68`
- `0x1800493b8`
- `0x18004967c`
- `0x18004e308`
- `0x18004f820`
- `0x180052f28`
- `0x180053b28`
- `0x180054fbc`
- `0x180059920`
- `0x180106e48`
- `0x180125400`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18003d05d`
- `api-ms-win-crt-private-l1-1-0!_o_iswalpha` at `0x18003d05d`
- `api-ms-win-crt-private-l1-1-0!_o_iswprint` at `0x18003d0cd`
- `api-ms-win-crt-private-l1-1-0!_o_iswprint` at `0x18003d0cd`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18003cd7f`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18003d06a`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18003cd7f`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18003d06a`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18003ccba`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18003ccba`
- `KERNEL32!GetFileAttributesW` at `0x18003cbe5`
- `KERNEL32!GetFileAttributesW` at `0x18003d12c`
- `KERNEL32!GetFileAttributesW` at `0x18003cbe5`
- `KERNEL32!GetFileAttributesW` at `0x18003d12c`
- `KERNEL32!GetLastError` at `0x18003cccb`
- `KERNEL32!GetLastError` at `0x18003cccb`
- `SHLWAPI!PathFileExistsW` at `0x18003cbbd`
- `SHLWAPI!PathFileExistsW` at `0x18003cbbd`
- `SHLWAPI!PathIsNetworkPathW` at `0x18003cc14`
- `SHLWAPI!PathIsNetworkPathW` at `0x18003cc14`

## string_xrefs

- `0x18003cf7f`: `InstallShield`
- `0x18003cb48`: `InstallShield uninstall string: %ws`
- `0x18003cb55`: `ArpApplication::GetInstallLocationFromInstallShieldUninstallString`
- `0x18003cce2`: `ArpApplication::GetInstallLocationFromInstallShieldUninstallString`
- `0x18003cf6e`: `ArpApplication::GetInstallLocationFromInstallShieldUninstallString`
- `0x18003cfea`: `ArpApplication::GetInstallLocationFromInstallShieldUninstallString`
- `0x18003ccb3`: `%programdata%\microsoft\windows\start menu\programs\`
- `0x18003cfdd`: `Added Install Directory: %ws`
- `0x18003cf61`: `Found Install Directory: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
_OWORD *__fastcall ArpApplication::GetInstallLocationFromInstallShieldUninstallString(_OWORD *a1, __int64 *a2)
{
  __int64 v3; // r8
  _QWORD *v4; // rax
  __int64 v5; // rax
  const WCHAR *v6; // rcx
  const WCHAR *v7; // rcx
  DWORD FileAttributesW; // eax
  const WCHAR *v9; // rcx
  LPCWSTR *v10; // rdx
  DWORD v11; // r12d
  bool v13; // zf
  DWORD v14; // r12d
  DWORD v15; // r14d
  unsigned int v16; // r13d
  char v17; // r15
  unsigned __int64 v18; // rbx
  char v19; // r14
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rbx
  __int64 v23; // r15
  char found; // r14
  __int64 v25; // rax
  __int64 v26; // r8
  unsigned __int64 v27; // rcx
  const WCHAR *v28; // rcx
  DWORD v29; // eax
  __int64 v30; // rax
  __int64 StringWithLeastDistance; // rax
  _QWORD *v32; // [rsp+20h] [rbp-13E8h]
  char v33; // [rsp+30h] [rbp-13D8h]
  __int16 v34; // [rsp+32h] [rbp-13D6h]
  _QWORD *v35; // [rsp+40h] [rbp-13C8h] BYREF
  unsigned __int64 v36; // [rsp+48h] [rbp-13C0h]
  int v37[6]; // [rsp+50h] [rbp-13B8h] BYREF
  __int64 *v38; // [rsp+68h] [rbp-13A0h]
  __int128 v39; // [rsp+70h] [rbp-1398h] BYREF
  __int64 v40; // [rsp+80h] [rbp-1388h]
  _QWORD v41[7]; // [rsp+88h] [rbp-1380h] BYREF
  _QWORD v42[60]; // [rsp+C0h] [rbp-1348h] BYREF
  LPCWSTR lpFileName[4]; // [rsp+2A0h] [rbp-1168h] BYREF
  LPCWSTR pszPath[3]; // [rsp+2C0h] [rbp-1148h] BYREF
  unsigned __int64 v45; // [rsp+2D8h] [rbp-1130h]
  __int128 v46; // [rsp+2E0h] [rbp-1128h] BYREF
  __m128i si128; // [rsp+2F0h] [rbp-1118h]
  _QWORD v48[4]; // [rsp+300h] [rbp-1108h] BYREF
  _BYTE v49[16]; // [rsp+320h] [rbp-10E8h] BYREF
  const WCHAR *v50; // [rsp+330h] [rbp-10D8h]
  _BYTE Src[32]; // [rsp+340h] [rbp-10C8h] BYREF
  _BYTE v52[32]; // [rsp+360h] [rbp-10A8h] BYREF
  _BYTE v53[32]; // [rsp+380h] [rbp-1088h] BYREF
  _BYTE v54[32]; // [rsp+3A0h] [rbp-1068h] BYREF
  WCHAR Dst[2048]; // [rsp+3C0h] [rbp-1048h] BYREF

  v41[3] = -2;
  v38 = a2;
  std::wstring::wstring(&v46);
  std::wstring::wstring(v52);
  std::wstring::wstring(v49);
  std::wstring::wstring(v48, v3);
  v4 = v48;
  if ( v48[3] > 7u )
    v4 = (_QWORD *)v48[0];
  v32 = v4;
  AslLogCallPrintf(
    3,
    (unsigned int)"ArpApplication::GetInstallLocationFromInstallShieldUninstallString",
    1341,
    (unsigned int)"InstallShield uninstall string: %ws");
  ArpApplication::GetInstallLocationFromCommandString((__int64)Src);
  v5 = std::wstring::_Append<unsigned short>(Src);
  std::wstring::wstring(pszPath, v5);
  v6 = (const WCHAR *)pszPath;
  if ( v45 > 7 )
    v6 = pszPath[0];
  if ( !PathFileExistsW(v6) )
    goto LABEL_66;
  v7 = (const WCHAR *)pszPath;
  if ( v45 > 7 )
    v7 = pszPath[0];
  FileAttributesW = GetFileAttributesW(v7);
  if ( FileAttributesW != -1 && (FileAttributesW & 0x10) != 0 )
    goto LABEL_66;
  v9 = (const WCHAR *)pszPath;
  if ( v45 > 7 )
    v9 = pszPath[0];
  if ( PathIsNetworkPathW(v9) )
  {
LABEL_66:
    std::wstring::wstring(a1, &byte_1801389F0);
    std::wstring::~wstring(pszPath);
    std::wstring::~wstring(Src);
    std::wstring::~wstring(v48);
    std::wstring::~wstring(v49);
    std::wstring::~wstring(v52);
    std::wstring::~wstring(&v46);
    return a1;
  }
  else
  {
    v10 = pszPath;
    if ( v45 > 7 )
      v10 = (LPCWSTR *)pszPath[0];
    std::ifstream::ifstream(v42, v10);
    *(_QWORD *)((char *)v42 + *(int *)(v42[0] + 4LL)) = &std::ifstream::`vftable';
    *(_DWORD *)((char *)&v41[6] + *(int *)(v42[0] + 4LL) + 4) = *(_DWORD *)(v42[0] + 4LL) - 176;
    if ( (*((_BYTE *)&v42[2] + *(int *)(v42[0] + 4LL)) & 4) == 0 && v42[18] )
    {
      v11 = ExpandEnvironmentStringsW(L"%programdata%\\microsoft\\windows\\start menu\\programs\\", Dst, 0x104u);
      if ( !v11 )
      {
        GetLastError();
        AslLogCallPrintf(
          1,
          (unsigned int)"ArpApplication::GetInstallLocationFromInstallShieldUninstallString",
          1361,
          (unsigned int)"ExpandEnvironmentStringsW failed [%d]");
        std::wstring::wstring(a1, &byte_1801389F0);
        std::ifstream::`vbase destructor'(v42);
        std::wstring::~wstring(pszPath);
        std::wstring::~wstring(Src);
        std::wstring::~wstring(v48);
        std::wstring::~wstring(v49);
        std::wstring::~wstring(v52);
        std::wstring::~wstring(&v46);
        return a1;
      }
      v13 = v11 == 1;
      v14 = v11 - 1;
      v15 = 0;
      if ( !v13 )
      {
        do
        {
          Dst[v15] = _o_towlower(Dst[v15]);
          ++v15;
        }
        while ( v15 < v14 );
      }
      v16 = 0;
      v33 = 0;
      v17 = 0;
      LOBYTE(v18) = 0;
      v34 = 0;
      v19 = 1;
      std::wstring::wstring(lpFileName);
      while ( 1 )
      {
        v20 = std::istream::get(v42);
        LODWORD(v18) = (unsigned __int8)v18;
        if ( v20 != -1 )
          LODWORD(v18) = (unsigned __int8)v20;
        v37[0] = v18;
        if ( (*((_BYTE *)&v42[2] + *(int *)(v42[0] + 4LL)) & 6) != 0 )
        {
          std::wstring::~wstring(lpFileName);
          break;
        }
        v18 = (unsigned __int8)v18;
        if ( v19 )
        {
          v34 = (unsigned __int8)v18;
          v19 ^= 1u;
          goto LABEL_35;
        }
        LOWORD(v18) = v34 | ((unsigned __int8)v18 << 8);
        if ( (unsigned int)_o_iswalpha((unsigned __int16)v18) )
          v18 = (unsigned __int16)_o_towlower((unsigned __int16)v18);
        if ( v33 )
        {
          if ( iswprint(v18) )
          {
            if ( (unsigned __int16)v18 > 0x3Fu || (v27 = 0xD400840400000000uLL, !_bittest64((const __int64 *)&v27, v18)) )
            {
              if ( (_WORD)v18 != 124 )
              {
                std::wstring::push_back(lpFileName, (unsigned __int16)v18);
                if ( (_WORD)v18 )
                  v17 = 1;
                goto LABEL_60;
              }
            }
          }
          if ( v17 )
          {
            v28 = (const WCHAR *)lpFileName;
            if ( lpFileName[3] > (LPCWSTR)7 )
              v28 = lpFileName[0];
            v29 = GetFileAttributesW(v28);
            if ( v29 != -1 && (v29 & 0x10) != 0 && lpFileName[2] > v50 )
              std::wstring::operator=(v49, lpFileName);
          }
          v33 = 0;
          v16 = 0;
        }
        else
        {
          v25 = v16++;
          if ( (_WORD)v18 != Dst[v25] )
            v16 = 0;
          if ( v16 != v14 )
            goto LABEL_60;
          v33 = 1;
          v26 = -1;
          do
            ++v26;
          while ( Dst[v26] );
          std::wstring::_Assign<unsigned short>(lpFileName, Dst);
        }
        v17 = 0;
LABEL_60:
        v19 = 1;
LABEL_35:
        LOBYTE(v18) = v37[0];
      }
    }
    std::ifstream::`vbase destructor'(v42);
    if ( v50 )
    {
      v39 = 0;
      v40 = 0;
      std::wstring::wstring(lpFileName, L".lnk");
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(&v39, lpFileName);
      std::wstring::~wstring(lpFileName);
      v21 = std::vector<std::wstring>::vector<std::wstring>(lpFileName, &v39);
      OrphanFileFinder::SearchForLooseAppFiles(v41, v49, v21, 9, v32);
      std::set<std::wstring>::set<std::wstring>(&v35);
      v22 = v41[0];
      v23 = v41[1];
      while ( v22 != v23 )
      {
        std::wstring::wstring(v54, v22);
        OrphanFileFinder::GetTargetDirectoryFromShortcut(lpFileName, v54);
        AslLogCallPrintf(
          3,
          (unsigned int)"ArpApplication::GetInstallLocationFromInstallShieldUninstallString",
          1480,
          (unsigned int)"Found Install Directory: %ws");
        std::wstring::wstring(v53, L"InstallShield");
        found = Utility::FoundSubstring(v53, lpFileName);
        std::wstring::~wstring(v53);
        if ( !found )
        {
          AslLogCallPrintf(
            3,
            (unsigned int)"ArpApplication::GetInstallLocationFromInstallShieldUninstallString",
            1485,
            (unsigned int)"Added Install Directory: %ws");
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring &>(
            &v35,
            v37,
            lpFileName);
        }
        std::wstring::~wstring(lpFileName);
        std::wstring::~wstring(v54);
        v22 += 32;
      }
      if ( v36 <= 1 )
      {
        if ( v36 == 1 )
          std::wstring::operator=(&v46, *v35 + 32LL);
      }
      else
      {
        v30 = Utility::ToLower((__int64)v53, v38);
        StringWithLeastDistance = Utility::FindStringWithLeastDistance(v54, v30, &v35);
        std::wstring::operator=(&v46, StringWithLeastDistance);
        std::wstring::~wstring(v54);
        std::wstring::~wstring(v53);
      }
      std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
        &v35,
        &v35);
      std::vector<std::wstring>::_Tidy(v41);
      std::vector<std::wstring>::_Tidy(&v39);
      std::wstring::~wstring(pszPath);
      std::wstring::~wstring(Src);
      std::wstring::~wstring(v48);
      std::wstring::~wstring(v49);
      std::wstring::~wstring(v52);
      *a1 = v46;
      a1[1] = si128;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v46) = 0;
      std::wstring::~wstring(&v46);
      return a1;
    }
    else
    {
      std::wstring::wstring(a1, &byte_1801389F0);
      std::wstring::~wstring(pszPath);
      std::wstring::~wstring(Src);
      std::wstring::~wstring(v48);
      std::wstring::~wstring(v49);
      std::wstring::~wstring(v52);
      std::wstring::~wstring(&v46);
      return a1;
    }
  }
}

```

## disassembly

```asm
0x18003caa8  push    rbx
0x18003caaa  push    rsi
0x18003caab  push    rdi
0x18003caac  push    r12
0x18003caae  push    r13
0x18003cab0  push    r14
0x18003cab2  push    r15
0x18003cab4  mov     eax, 13D0h
0x18003cab9  call    _alloca_probe
0x18003cabe  sub     rsp, rax
0x18003cac1  mov     [rsp+1408h+var_1368], 0FFFFFFFFFFFFFFFEh
0x18003cacd  mov     rax, cs:__security_cookie
0x18003cad4  xor     rax, rsp
0x18003cad7  mov     [rsp+1408h+var_48], rax
0x18003cadf  mov     [rsp+1408h+var_13A0], rdx
0x18003cae4  mov     rsi, rcx
0x18003cae7  mov     [rsp+1408h+var_13D0], rcx
0x18003caec  xor     edi, edi
0x18003caee  lea     rcx, [rsp+1408h+var_1128]
0x18003caf6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003cafb  nop
0x18003cafc  lea     rcx, [rsp+1408h+var_10A8]
0x18003cb04  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003cb09  nop
0x18003cb0a  lea     rcx, [rsp+1408h+var_10E8]
0x18003cb12  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003cb17  nop
0x18003cb18  mov     rdx, r8
0x18003cb1b  lea     rcx, [rsp+1408h+var_1108]
0x18003cb23  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003cb28  nop
0x18003cb29  lea     rax, [rsp+1408h+var_1108]
0x18003cb31  cmp     [rsp+1408h+var_10F0], 7
0x18003cb3a  cmova   rax, [rsp+1408h+var_1108]
0x18003cb43  mov     [rsp+1408h+var_13E8], rax
0x18003cb48  lea     r9, aInstallshieldU; "InstallShield uninstall string: %ws"
0x18003cb4f  mov     r8d, 53Dh
0x18003cb55  lea     rdx, aArpapplication_2; "ArpApplication::GetInstallLocationFromI"...
0x18003cb5c  lea     ecx, [rdi+3]
0x18003cb5f  call    AslLogCallPrintf
0x18003cb64  lea     rdx, [rsp+1408h+var_1108]
0x18003cb6c  lea     rcx, [rsp+1408h+Src]
0x18003cb74  call    ?GetInstallLocationFromCommandString@ArpApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; ArpApplication::GetInstallLocationFromCommandString(std::wstring const &)
0x18003cb79  nop
0x18003cb7a  lea     r8d, [rdi+0Ah]
0x18003cb7e  lea     rdx, aSetupIlg; "\\setup.ilg"
0x18003cb85  lea     rcx, [rsp+1408h+Src]; Src
0x18003cb8d  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003cb92  mov     rdx, rax
0x18003cb95  lea     rcx, [rsp+1408h+pszPath]
0x18003cb9d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003cba2  nop
0x18003cba3  lea     rcx, [rsp+1408h+pszPath]
0x18003cbab  cmp     [rsp+1408h+var_1130], 7
0x18003cbb4  cmova   rcx, [rsp+1408h+pszPath]; pszPath
0x18003cbbd  call    cs:__imp_PathFileExistsW
0x18003cbc3  test    eax, eax
0x18003cbc5  jz      loc_18003D25F
0x18003cbcb  lea     rcx, [rsp+1408h+pszPath]
0x18003cbd3  cmp     [rsp+1408h+var_1130], 7
0x18003cbdc  cmova   rcx, [rsp+1408h+pszPath]; lpFileName
0x18003cbe5  call    cs:__imp_GetFileAttributesW
0x18003cbeb  or      ebx, 0FFFFFFFFh
0x18003cbee  cmp     eax, ebx
0x18003cbf0  jz      short loc_18003CBFA
0x18003cbf2  test    al, 10h
0x18003cbf4  jnz     loc_18003D25F
0x18003cbfa  lea     rcx, [rsp+1408h+pszPath]
0x18003cc02  cmp     [rsp+1408h+var_1130], 7
0x18003cc0b  cmova   rcx, [rsp+1408h+pszPath]; pszPath
0x18003cc14  call    cs:__imp_PathIsNetworkPathW
0x18003cc1a  test    eax, eax
0x18003cc1c  jnz     loc_18003D25F
0x18003cc22  lea     rdx, [rsp+1408h+pszPath]
0x18003cc2a  cmp     [rsp+1408h+var_1130], 7
0x18003cc33  cmova   rdx, [rsp+1408h+pszPath]
0x18003cc3c  lea     rcx, [rsp+1408h+var_1348]
0x18003cc44  call    ??0?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAA@PEBGHH@Z; std::ifstream::ifstream(ushort const *,int,int)
0x18003cc49  mov     rax, [rsp+1408h+var_1348]
0x18003cc51  movsxd  rcx, dword ptr [rax+4]
0x18003cc55  lea     rax, ??_7?$basic_ifstream@DU?$char_traits@D@std@@@std@@6B@; const std::ifstream::`vftable'
0x18003cc5c  mov     [rsp+rcx+1408h+var_1348], rax
0x18003cc64  mov     rax, [rsp+1408h+var_1348]
0x18003cc6c  movsxd  rcx, dword ptr [rax+4]
0x18003cc70  lea     edx, [rcx-0B0h]
0x18003cc76  mov     [rsp+rcx+1408h+var_134C], edx
0x18003cc7d  mov     rax, [rsp+1408h+var_1348]
0x18003cc85  movsxd  rcx, dword ptr [rax+4]
0x18003cc89  test    [rsp+rcx+1408h+var_1338], 4
0x18003cc91  jnz     loc_18003CDFE
0x18003cc97  cmp     [rsp+1408h+var_12B8], rdi
0x18003cc9f  jz      loc_18003CDFE
0x18003cca5  mov     r8d, 104h; nSize
0x18003ccab  lea     rdx, [rsp+1408h+Dst]; lpDst
0x18003ccb3  lea     rcx, aProgramdataMic; "%programdata%\\microsoft\\windows\\star"...
0x18003ccba  call    cs:__imp_ExpandEnvironmentStringsW
0x18003ccc0  mov     r12d, eax
0x18003ccc3  test    eax, eax
0x18003ccc5  jnz     loc_18003CD6C
0x18003cccb  call    cs:__imp_GetLastError
0x18003ccd1  mov     dword ptr [rsp+1408h+var_13E8], eax
0x18003ccd5  lea     r9, aExpandenvironm; "ExpandEnvironmentStringsW failed [%d]"
0x18003ccdc  mov     r8d, 551h
0x18003cce2  lea     rdx, aArpapplication_2; "ArpApplication::GetInstallLocationFromI"...
0x18003cce9  lea     ecx, [r12+1]
0x18003ccee  call    AslLogCallPrintf
0x18003ccf3  lea     rdx, byte_1801389F0
0x18003ccfa  mov     rcx, rsi
0x18003ccfd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003cd02  nop
0x18003cd03  lea     rcx, [rsp+1408h+var_1348]
0x18003cd0b  call    ??_D?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAAXXZ; std::ifstream::`vbase destructor'(void)
0x18003cd10  nop
0x18003cd11  lea     rcx, [rsp+1408h+pszPath]
0x18003cd19  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003cd1e  nop
0x18003cd1f  lea     rcx, [rsp+1408h+Src]
0x18003cd27  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003cd2c  nop
0x18003cd2d  lea     rcx, [rsp+1408h+var_1108]
0x18003cd35  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003cd3a  nop
0x18003cd3b  lea     rcx, [rsp+1408h+var_10E8]
0x18003cd43  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003cd48  nop
0x18003cd49  lea     rcx, [rsp+1408h+var_10A8]
0x18003cd51  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003cd56  nop
0x18003cd57  lea     rcx, [rsp+1408h+var_1128]
0x18003cd5f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003cd64  mov     rax, rsi
0x18003cd67  jmp     loc_18003D30E
0x18003cd6c  add     r12d, ebx
0x18003cd6f  mov     r14d, edi
0x18003cd72  jz      short loc_18003CD95
0x18003cd74  mov     ebx, r14d
0x18003cd77  movzx   ecx, [rsp+rbx*2+1408h+Dst]
0x18003cd7f  call    cs:__imp__o_towlower
0x18003cd85  mov     [rsp+rbx*2+1408h+Dst], ax
0x18003cd8d  inc     r14d
0x18003cd90  cmp     r14d, r12d
0x18003cd93  jb      short loc_18003CD74
0x18003cd95  mov     r13d, edi
0x18003cd98  mov     [rsp+1408h+var_13D8], dil
0x18003cd9d  mov     r15b, dil
0x18003cda0  mov     bl, dil
0x18003cda3  mov     [rsp+1408h+var_13D6], di
0x18003cda8  mov     r14b, 1
0x18003cdab  lea     rcx, [rsp+1408h+lpFileName]
0x18003cdb3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18003cdb8  nop
0x18003cdb9  lea     rcx, [rsp+1408h+var_1348]
0x18003cdc1  call    ?get@?$basic_istream@DU?$char_traits@D@std@@@std@@QEAAHXZ; std::istream::get(void)
0x18003cdc6  movzx   ecx, al
0x18003cdc9  movzx   ebx, bl
0x18003cdcc  cmp     eax, 0FFFFFFFFh
0x18003cdcf  cmovnz  ebx, ecx
0x18003cdd2  mov     [rsp+1408h+var_13B8], ebx
0x18003cdd6  mov     rax, [rsp+1408h+var_1348]
0x18003cdde  movsxd  rcx, dword ptr [rax+4]
0x18003cde2  test    [rsp+rcx+1408h+var_1338], 6
0x18003cdea  jz      loc_18003D037
0x18003cdf0  lea     rcx, [rsp+1408h+lpFileName]
0x18003cdf8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003cdfd  nop
0x18003cdfe  lea     rcx, [rsp+1408h+var_1348]
0x18003ce06  call    ??_D?$basic_ifstream@DU?$char_traits@D@std@@@std@@QEAAXXZ; std::ifstream::`vbase destructor'(void)
0x18003ce0b  cmp     [rsp+1408h+var_10D8], rdi
0x18003ce13  jnz     short loc_18003CE80
0x18003ce15  lea     rdx, byte_1801389F0
0x18003ce1c  mov     rcx, rsi
0x18003ce1f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003ce24  nop
0x18003ce25  lea     rcx, [rsp+1408h+pszPath]
0x18003ce2d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003ce32  nop
0x18003ce33  lea     rcx, [rsp+1408h+Src]
0x18003ce3b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003ce40  nop
0x18003ce41  lea     rcx, [rsp+1408h+var_1108]
0x18003ce49  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003ce4e  nop
0x18003ce4f  lea     rcx, [rsp+1408h+var_10E8]
0x18003ce57  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003ce5c  nop
0x18003ce5d  lea     rcx, [rsp+1408h+var_10A8]
0x18003ce65  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003ce6a  nop
0x18003ce6b  lea     rcx, [rsp+1408h+var_1128]
0x18003ce73  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003ce78  mov     rax, rsi
0x18003ce7b  jmp     loc_18003D30E
0x18003ce80  xorps   xmm0, xmm0
0x18003ce83  movdqu  [rsp+1408h+var_1398], xmm0
0x18003ce89  mov     [rsp+1408h+var_1388], rdi
0x18003ce91  lea     rdx, aLnk; ".lnk"
0x18003ce98  lea     rcx, [rsp+1408h+lpFileName]
0x18003cea0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003cea5  nop
0x18003cea6  lea     rdx, [rsp+1408h+lpFileName]
0x18003ceae  lea     rcx, [rsp+1408h+var_1398]
0x18003ceb3  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x18003ceb8  nop
0x18003ceb9  lea     rcx, [rsp+1408h+lpFileName]
0x18003cec1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003cec6  lea     rdx, [rsp+1408h+var_1398]
0x18003cecb  lea     rcx, [rsp+1408h+lpFileName]
0x18003ced3  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x18003ced8  mov     r9d, 9
0x18003cede  mov     r8, rax
0x18003cee1  lea     rdx, [rsp+1408h+var_10E8]
0x18003cee9  lea     rcx, [rsp+1408h+var_1380]
0x18003cef1  call    ?SearchForLooseAppFiles@OrphanFileFinder@@SA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@V23@K@Z; OrphanFileFinder::SearchForLooseAppFiles(std::wstring const &,std::vector<std::wstring>,ulong)
0x18003cef6  nop
0x18003cef7  lea     rcx, [rsp+1408h+var_13C8]
0x18003cefc  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x18003cf01  nop
0x18003cf02  mov     rbx, [rsp+1408h+var_1380]
0x18003cf0a  mov     r15, [rsp+1408h+var_1378]
0x18003cf12  cmp     rbx, r15
0x18003cf15  jz      loc_18003D175
0x18003cf1b  mov     rdx, rbx
0x18003cf1e  lea     rcx, [rsp+1408h+var_1068]
0x18003cf26  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003cf2b  nop
0x18003cf2c  lea     rdx, [rsp+1408h+var_1068]
0x18003cf34  lea     rcx, [rsp+1408h+lpFileName]
0x18003cf3c  call    ?GetTargetDirectoryFromShortcut@OrphanFileFinder@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; OrphanFileFinder::GetTargetDirectoryFromShortcut(std::wstring const &)
0x18003cf41  nop
0x18003cf42  lea     rax, [rsp+1408h+lpFileName]
0x18003cf4a  cmp     [rsp+1408h+var_1150], 7
0x18003cf53  cmova   rax, [rsp+1408h+lpFileName]
0x18003cf5c  mov     [rsp+1408h+var_13E8], rax
0x18003cf61  lea     r9, aFoundInstallDi; "Found Install Directory: %ws"
0x18003cf68  mov     r8d, 5C8h
0x18003cf6e  lea     rdx, aArpapplication_2; "ArpApplication::GetInstallLocationFromI"...
0x18003cf75  mov     ecx, 3
0x18003cf7a  call    AslLogCallPrintf
0x18003cf7f  lea     rdx, aInstallshield_0; "InstallShield"
0x18003cf86  lea     rcx, [rsp+1408h+var_1088]
0x18003cf8e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003cf93  nop
0x18003cf94  lea     rdx, [rsp+1408h+lpFileName]
0x18003cf9c  lea     rcx, [rsp+1408h+var_1088]
0x18003cfa4  call    ?FoundSubstring@Utility@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Utility::FoundSubstring(std::wstring const &,std::wstring const &)
0x18003cfa9  mov     r14b, al
0x18003cfac  lea     rcx, [rsp+1408h+var_1088]
0x18003cfb4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003cfb9  test    r14b, r14b
0x18003cfbc  jnz     short loc_18003D013
0x18003cfbe  lea     rax, [rsp+1408h+lpFileName]
0x18003cfc6  cmp     [rsp+1408h+var_1150], 7
0x18003cfcf  cmova   rax, [rsp+1408h+lpFileName]
0x18003cfd8  mov     [rsp+1408h+var_13E8], rax
0x18003cfdd  lea     r9, aAddedInstallDi; "Added Install Directory: %ws"
0x18003cfe4  mov     r8d, 5CDh
0x18003cfea  lea     rdx, aArpapplication_2; "ArpApplication::GetInstallLocationFromI"...
0x18003cff1  mov     ecx, 3
0x18003cff6  call    AslLogCallPrintf
0x18003cffb  lea     r8, [rsp+1408h+lpFileName]
0x18003d003  lea     rdx, [rsp+1408h+var_13B8]
0x18003d008  lea     rcx, [rsp+1408h+var_13C8]
0x18003d00d  call    ??$emplace@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring &>(std::wstring &)
0x18003d012  nop
0x18003d013  lea     rcx, [rsp+1408h+lpFileName]
0x18003d01b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d020  nop
0x18003d021  lea     rcx, [rsp+1408h+var_1068]
0x18003d029  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003d02e  add     rbx, 20h ; ' '
0x18003d032  jmp     loc_18003CF12
0x18003d037  movzx   ebx, bl
0x18003d03a  test    r14b, r14b
0x18003d03d  jz      short loc_18003D051
0x18003d03f  mov     [rsp+1408h+var_13D6], bx
0x18003d044  xor     r14b, 1
0x18003d048  mov     ebx, [rsp+1408h+var_13B8]
0x18003d04c  jmp     loc_18003CDB9
0x18003d051  shl     bx, 8
0x18003d055  or      bx, [rsp+1408h+var_13D6]
0x18003d05a  movzx   ecx, bx
0x18003d05d  call    cs:__imp__o_iswalpha
0x18003d063  test    eax, eax
0x18003d065  jz      short loc_18003D073
0x18003d067  movzx   ecx, bx
0x18003d06a  call    cs:__imp__o_towlower
0x18003d070  movzx   ebx, ax
0x18003d073  cmp     [rsp+1408h+var_13D8], dil
0x18003d078  jnz     short loc_18003D0CA
0x18003d07a  mov     eax, r13d
0x18003d07d  inc     r13d
0x18003d080  cmp     bx, [rsp+rax*2+1408h+Dst]
0x18003d088  cmovnz  r13d, edi
0x18003d08c  cmp     r13d, r12d
0x18003d08f  jnz     loc_18003D16D
0x18003d095  mov     [rsp+1408h+var_13D8], 1
0x18003d09a  lea     rax, [rsp+1408h+Dst]
0x18003d0a2  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003d0a6  inc     r8
0x18003d0a9  cmp     [rax+r8*2], di
  ... truncated ...
```
