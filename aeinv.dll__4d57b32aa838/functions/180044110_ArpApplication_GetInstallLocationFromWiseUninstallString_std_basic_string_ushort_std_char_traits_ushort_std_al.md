# ArpApplication::GetInstallLocationFromWiseUninstallString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180044110`
- end: `0x18004468c`
- name: `?GetInstallLocationFromWiseUninstallString@ArpApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z`
- size: `1404`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x18003d33c`

## callees

- `0x18000da54`
- `0x1800114a4`
- `0x1800118d0`
- `0x1800150ac`
- `0x1800172bc`
- `0x1800175b0`
- `0x180018300`
- `0x1800183e0`
- `0x180018450`
- `0x180018a60`
- `0x180018ad0`
- `0x180018ff4`
- `0x1800197d4`
- `0x18001e0d0`
- `0x1800404c4`
- `0x180044110`
- `0x180044c88`
- `0x180044d04`
- `0x180046c3c`
- `0x1800515d8`
- `0x180059920`
- `0x180125400`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x180044307`
- `KERNEL32!GetFileAttributesW` at `0x1800444ff`
- `KERNEL32!GetFileAttributesW` at `0x180044307`
- `KERNEL32!GetFileAttributesW` at `0x1800444ff`
- `SHLWAPI!PathFileExistsW` at `0x1800442df`
- `SHLWAPI!PathFileExistsW` at `0x1800442df`
- `SHLWAPI!PathIsNetworkPathW` at `0x180044334`
- `SHLWAPI!PathIsNetworkPathW` at `0x180044334`

## string_xrefs

- `0x1800442a0`: `\install.log`
- `0x1800441ab`: `ArpApplication::GetInstallLocationFromWiseUninstallString`
- `0x180044430`: `ArpApplication::GetInstallLocationFromWiseUninstallString`
- `0x18004419e`: `Wise uninstall string: %ws`
- `0x180044423`: `Kept Install Directory: %ws`

## pseudocode

```c
__int64 __fastcall ArpApplication::GetInstallLocationFromWiseUninstallString(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // rax
  _QWORD *DirectoryFromPath; // rax
  __int64 v8; // rax
  const WCHAR *v9; // rcx
  const WCHAR *v10; // rcx
  DWORD FileAttributesW; // eax
  const WCHAR *v12; // rcx
  unsigned __int16 i; // di
  unsigned __int16 v14; // ax
  __int64 v15; // rax
  unsigned __int64 v16; // rsi
  unsigned __int64 v17; // rdi
  __int64 v18; // rax
  __int64 v19; // r8
  __int64 *v20; // rax
  __int64 *v21; // rax
  const WCHAR *v22; // rcx
  DWORD v23; // eax
  _QWORD v24[60]; // [rsp+60h] [rbp-12B8h] BYREF
  __int64 v25[3]; // [rsp+240h] [rbp-10D8h] BYREF
  unsigned __int64 v26; // [rsp+258h] [rbp-10C0h]
  LPCWSTR lpFileName[2]; // [rsp+260h] [rbp-10B8h] BYREF
  unsigned __int64 v28; // [rsp+270h] [rbp-10A8h]
  unsigned __int64 v29; // [rsp+278h] [rbp-10A0h]
  LPCWSTR pszPath[3]; // [rsp+280h] [rbp-1098h] BYREF
  unsigned __int64 v31; // [rsp+298h] [rbp-1080h]
  _BYTE Src[16]; // [rsp+2A0h] [rbp-1078h] BYREF
  __int64 v33; // [rsp+2B0h] [rbp-1068h]
  _QWORD v34[3]; // [rsp+2C0h] [rbp-1058h] BYREF
  _QWORD v35[3]; // [rsp+2E0h] [rbp-1038h] BYREF

  std::wstring::wstring(v25);
  std::wstring::wstring(v34);
  std::wstring::wstring(v35, v4);
  AslLogCallPrintf(
    3,
    (unsigned int)"ArpApplication::GetInstallLocationFromWiseUninstallString",
    1570,
    (unsigned int)"Wise uninstall string: %ws");
  ArpApplication::GetInstallLocationFromCommandString((__int64)Src);
  if ( !v33 )
  {
    v5 = Utility::VerifyAndNormalizeFilePath(lpFileName, a2);
    std::wstring::operator=(Src, v5);
    std::wstring::~wstring(lpFileName);
    if ( !v33 )
    {
      std::wstring::wstring(a1, &byte_1801389F0);
      std::wstring::~wstring(Src);
      std::wstring::~wstring(v35);
      std::wstring::~wstring(v34);
      std::wstring::~wstring(v25);
      return a1;
    }
    DirectoryFromPath = Utility::GetDirectoryFromPath(lpFileName, (__int64)Src);
    std::wstring::operator=(Src, DirectoryFromPath);
    std::wstring::~wstring(lpFileName);
  }
  v8 = std::wstring::_Append<unsigned short>(Src);
  std::wstring::wstring(pszPath, v8);
  v9 = (const WCHAR *)pszPath;
  if ( v31 > 7 )
    v9 = pszPath[0];
  if ( !PathFileExistsW(v9) )
    goto LABEL_43;
  v10 = (const WCHAR *)pszPath;
  if ( v31 > 7 )
    v10 = pszPath[0];
  FileAttributesW = GetFileAttributesW(v10);
  if ( FileAttributesW != -1 && (FileAttributesW & 0x10) != 0 )
    goto LABEL_43;
  v12 = (const WCHAR *)pszPath;
  if ( v31 > 7 )
    v12 = pszPath[0];
  if ( PathIsNetworkPathW(v12) )
  {
LABEL_43:
    std::wstring::wstring(a1, &byte_1801389F0);
    std::wstring::~wstring(pszPath);
    std::wstring::~wstring(Src);
    std::wstring::~wstring(v35);
    std::wstring::~wstring(v34);
    std::wstring::~wstring(v25);
    return a1;
  }
  else
  {
    std::basic_ifstream<unsigned short>::basic_ifstream<unsigned short>(v24, pszPath);
    if ( (*((_BYTE *)&v24[2] + *(int *)(v24[0] + 4LL)) & 4) != 0 || !v24[18] )
    {
      std::wstring::wstring(a1, &byte_1801389F0);
      std::basic_ifstream<unsigned short>::`vbase destructor'(v24);
      std::wstring::~wstring(pszPath);
      std::wstring::~wstring(Src);
      std::wstring::~wstring(v35);
      std::wstring::~wstring(v34);
      std::wstring::~wstring(v25);
      return a1;
    }
    else
    {
      for ( i = 0; ; std::wstring::append(v25, 1, i) )
      {
        v14 = std::basic_istream<unsigned short>::get(v24);
        if ( v14 != 0xFFFF )
          i = v14;
        if ( (*((_BYTE *)&v24[2] + *(int *)(v24[0] + 4LL)) & 6) != 0 )
          break;
      }
      std::basic_ifstream<unsigned short>::`vbase destructor'(v24);
      v15 = Utility::ToLower((__int64)lpFileName, v25);
      std::wstring::operator=(v25, v15);
      std::wstring::~wstring(lpFileName);
      v16 = 2600;
      v17 = 0;
      while ( 1 )
      {
        v18 = std::wstring::find(v25, L"made dir: ", v17);
        if ( v18 == -1 )
          break;
        v17 = v18 + 10;
        v19 = v18 + 10;
        while ( v17 < v25[2] )
        {
          v20 = v25;
          if ( v26 > 7 )
            v20 = (__int64 *)v25[0];
          if ( *((_WORD *)v20 + v17) == 10 )
            break;
          v21 = v25;
          if ( v26 > 7 )
            v21 = (__int64 *)v25[0];
          if ( *((_WORD *)v21 + v17) == 13 )
            break;
          ++v17;
        }
        std::wstring::substr(v25, lpFileName, v19, v17 - v19);
        v22 = (const WCHAR *)lpFileName;
        if ( v29 > 7 )
          v22 = lpFileName[0];
        v23 = GetFileAttributesW(v22);
        if ( v23 != -1 && (v23 & 0x10) != 0 && v28 > 3 && v28 < v16 )
        {
          std::wstring::operator=(v34, lpFileName);
          v16 = v28;
        }
        std::wstring::~wstring(lpFileName);
      }
      AslLogCallPrintf(
        3,
        (unsigned int)"ArpApplication::GetInstallLocationFromWiseUninstallString",
        1649,
        (unsigned int)"Kept Install Directory: %ws");
      std::wstring::~wstring(pszPath);
      std::wstring::~wstring(Src);
      std::wstring::~wstring(v35);
      std::wstring::wstring(a1, v34);
      std::wstring::~wstring(v34);
      std::wstring::~wstring(v25);
      return a1;
    }
  }
}

```

## disassembly

```asm
0x180044110  push    rdi
0x180044112  mov     eax, 1310h
0x180044117  call    _alloca_probe
0x18004411c  sub     rsp, rax
0x18004411f  mov     [rsp+1318h+var_12D8], 0FFFFFFFFFFFFFFFEh
0x180044128  mov     [rsp+1318h+arg_10], rbx
0x180044130  mov     [rsp+1318h+arg_18], rsi
0x180044138  mov     rax, cs:__security_cookie
0x18004413f  xor     rax, rsp
0x180044142  mov     [rsp+1318h+var_18], rax
0x18004414a  mov     rdi, rdx
0x18004414d  mov     rbx, rcx
0x180044150  mov     [rsp+1318h+var_12E8], rcx
0x180044155  lea     rcx, [rsp+1318h+var_10D8]
0x18004415d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180044162  nop
0x180044163  lea     rcx, [rsp+1318h+var_1058]
0x18004416b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180044170  nop
0x180044171  lea     rcx, [rsp+1318h+var_1038]
0x180044179  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004417e  nop
0x18004417f  lea     rax, [rsp+1318h+var_1038]
0x180044187  cmp     [rsp+1318h+var_1020], 7
0x180044190  cmova   rax, [rsp+1318h+var_1038]
0x180044199  mov     [rsp+1318h+var_12F8], rax
0x18004419e  lea     r9, aWiseUninstallS; "Wise uninstall string: %ws"
0x1800441a5  mov     r8d, 622h
0x1800441ab  lea     rdx, aArpapplication_3; "ArpApplication::GetInstallLocationFromW"...
0x1800441b2  mov     ecx, 3
0x1800441b7  call    AslLogCallPrintf
0x1800441bc  lea     rdx, [rsp+1318h+var_1038]
0x1800441c4  lea     rcx, [rsp+1318h+Src]
0x1800441cc  call    ?GetInstallLocationFromCommandString@ArpApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; ArpApplication::GetInstallLocationFromCommandString(std::wstring const &)
0x1800441d1  nop
0x1800441d2  cmp     [rsp+1318h+var_1068], 0
0x1800441db  jnz     loc_18004429A
0x1800441e1  mov     rdx, rdi
0x1800441e4  lea     rcx, [rsp+1318h+lpFileName]
0x1800441ec  call    ?VerifyAndNormalizeFilePath@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::VerifyAndNormalizeFilePath(std::wstring const &)
0x1800441f1  mov     rdx, rax
0x1800441f4  lea     rcx, [rsp+1318h+Src]
0x1800441fc  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180044201  lea     rcx, [rsp+1318h+lpFileName]
0x180044209  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004420e  cmp     [rsp+1318h+var_1068], 0
0x180044217  jnz     short loc_180044268
0x180044219  lea     rdx, byte_1801389F0
0x180044220  mov     rcx, rbx
0x180044223  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180044228  nop
0x180044229  lea     rcx, [rsp+1318h+Src]
0x180044231  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044236  nop
0x180044237  lea     rcx, [rsp+1318h+var_1038]
0x18004423f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044244  nop
0x180044245  lea     rcx, [rsp+1318h+var_1058]
0x18004424d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044252  nop
0x180044253  lea     rcx, [rsp+1318h+var_10D8]
0x18004425b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044260  mov     rax, rbx
0x180044263  jmp     loc_180044667
0x180044268  lea     rdx, [rsp+1318h+Src]
0x180044270  lea     rcx, [rsp+1318h+lpFileName]
0x180044278  call    ?GetDirectoryFromPath@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::GetDirectoryFromPath(std::wstring const &)
0x18004427d  mov     rdx, rax
0x180044280  lea     rcx, [rsp+1318h+Src]
0x180044288  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004428d  lea     rcx, [rsp+1318h+lpFileName]
0x180044295  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004429a  mov     r8d, 0Ch
0x1800442a0  lea     rdx, aInstallLog; "\\install.log"
0x1800442a7  lea     rcx, [rsp+1318h+Src]; Src
0x1800442af  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800442b4  mov     rdx, rax
0x1800442b7  lea     rcx, [rsp+1318h+pszPath]
0x1800442bf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800442c4  nop
0x1800442c5  lea     rcx, [rsp+1318h+pszPath]
0x1800442cd  cmp     [rsp+1318h+var_1080], 7
0x1800442d6  cmova   rcx, [rsp+1318h+pszPath]; pszPath
0x1800442df  call    cs:__imp_PathFileExistsW
0x1800442e5  test    eax, eax
0x1800442e7  jz      loc_1800445D5
0x1800442ed  lea     rcx, [rsp+1318h+pszPath]
0x1800442f5  cmp     [rsp+1318h+var_1080], 7
0x1800442fe  cmova   rcx, [rsp+1318h+pszPath]; lpFileName
0x180044307  call    cs:__imp_GetFileAttributesW
0x18004430d  cmp     eax, 0FFFFFFFFh
0x180044310  jz      short loc_18004431A
0x180044312  test    al, 10h
0x180044314  jnz     loc_1800445D5
0x18004431a  lea     rcx, [rsp+1318h+pszPath]
0x180044322  cmp     [rsp+1318h+var_1080], 7
0x18004432b  cmova   rcx, [rsp+1318h+pszPath]; pszPath
0x180044334  call    cs:__imp_PathIsNetworkPathW
0x18004433a  test    eax, eax
0x18004433c  jnz     loc_1800445D5
0x180044342  lea     rdx, [rsp+1318h+pszPath]
0x18004434a  lea     rcx, [rsp+1318h+var_12B8]
0x18004434f  call    ??0?$basic_ifstream@GU?$char_traits@G@std@@@std@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@HH@Z; std::basic_ifstream<ushort>::basic_ifstream<ushort>(std::wstring const &,int,int)
0x180044354  nop
0x180044355  mov     rax, [rsp+1318h+var_12B8]
0x18004435a  movsxd  rcx, dword ptr [rax+4]
0x18004435e  test    [rsp+rcx+1318h+var_12A8], 4
0x180044363  jnz     loc_18004456D
0x180044369  cmp     [rsp+1318h+var_1228], 0
0x180044372  jz      loc_18004456D
0x180044378  xor     edi, edi
0x18004437a  lea     rcx, [rsp+1318h+var_12B8]
0x18004437f  call    ?get@?$basic_istream@GU?$char_traits@G@std@@@std@@QEAAGXZ; std::basic_istream<ushort>::get(void)
0x180044384  mov     ecx, 0FFFFh
0x180044389  cmp     cx, ax
0x18004438c  cmovnz  di, ax
0x180044390  mov     rax, [rsp+1318h+var_12B8]
0x180044395  movsxd  rcx, dword ptr [rax+4]
0x180044399  test    [rsp+rcx+1318h+var_12A8], 6
0x18004439e  jz      loc_180044552
0x1800443a4  lea     rcx, [rsp+1318h+var_12B8]
0x1800443a9  call    ??_D?$basic_ifstream@GU?$char_traits@G@std@@@std@@QEAAXXZ; std::basic_ifstream<ushort>::`vbase destructor'(void)
0x1800443ae  lea     rdx, [rsp+1318h+var_10D8]
0x1800443b6  lea     rcx, [rsp+1318h+lpFileName]
0x1800443be  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800443c3  mov     rdx, rax
0x1800443c6  lea     rcx, [rsp+1318h+var_10D8]
0x1800443ce  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800443d3  lea     rcx, [rsp+1318h+lpFileName]
0x1800443db  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800443e0  mov     esi, 0A28h
0x1800443e5  xor     edi, edi
0x1800443e7  mov     r8, rdi
0x1800443ea  lea     rdx, aMadeDir; "made dir: "
0x1800443f1  lea     rcx, [rsp+1318h+var_10D8]
0x1800443f9  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x1800443fe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180044402  jnz     short loc_180044471
0x180044404  lea     rax, [rsp+1318h+var_1058]
0x18004440c  cmp     [rsp+1318h+var_1040], 7
0x180044415  cmova   rax, [rsp+1318h+var_1058]
0x18004441e  mov     [rsp+1318h+var_12F8], rax
0x180044423  lea     r9, aKeptInstallDir; "Kept Install Directory: %ws"
0x18004442a  mov     r8d, 671h
0x180044430  lea     rdx, aArpapplication_3; "ArpApplication::GetInstallLocationFromW"...
0x180044437  mov     ecx, 3
0x18004443c  call    AslLogCallPrintf
0x180044441  nop
0x180044442  lea     rcx, [rsp+1318h+pszPath]
0x18004444a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004444f  nop
0x180044450  lea     rcx, [rsp+1318h+Src]
0x180044458  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004445d  nop
0x18004445e  lea     rcx, [rsp+1318h+var_1038]
0x180044466  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004446b  nop
0x18004446c  jmp     loc_180044638
0x180044471  lea     rdi, [rax+0Ah]
0x180044475  mov     r8, rdi
0x180044478  jmp     short loc_1800444BF
0x18004447a  lea     rax, [rsp+1318h+var_10D8]
0x180044482  cmp     [rsp+1318h+var_10C0], 7
0x18004448b  cmova   rax, [rsp+1318h+var_10D8]
0x180044494  cmp     word ptr [rax+rdi*2], 0Ah
0x180044499  jz      short loc_1800444C9
0x18004449b  lea     rax, [rsp+1318h+var_10D8]
0x1800444a3  cmp     [rsp+1318h+var_10C0], 7
0x1800444ac  cmova   rax, [rsp+1318h+var_10D8]
0x1800444b5  cmp     word ptr [rax+rdi*2], 0Dh
0x1800444ba  jz      short loc_1800444C9
0x1800444bc  inc     rdi
0x1800444bf  cmp     rdi, [rsp+1318h+var_10C8]
0x1800444c7  jb      short loc_18004447A
0x1800444c9  mov     r9, rdi
0x1800444cc  sub     r9, r8
0x1800444cf  lea     rdx, [rsp+1318h+lpFileName]
0x1800444d7  lea     rcx, [rsp+1318h+var_10D8]
0x1800444df  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800444e4  nop
0x1800444e5  lea     rcx, [rsp+1318h+lpFileName]
0x1800444ed  cmp     [rsp+1318h+var_10A0], 7
0x1800444f6  cmova   rcx, [rsp+1318h+lpFileName]; lpFileName
0x1800444ff  call    cs:__imp_GetFileAttributesW
0x180044505  cmp     eax, 0FFFFFFFFh
0x180044508  jz      short loc_180044540
0x18004450a  test    al, 10h
0x18004450c  jz      short loc_180044540
0x18004450e  cmp     [rsp+1318h+var_10A8], 3
0x180044517  jbe     short loc_180044540
0x180044519  cmp     [rsp+1318h+var_10A8], rsi
0x180044521  jnb     short loc_180044540
0x180044523  lea     rdx, [rsp+1318h+lpFileName]
0x18004452b  lea     rcx, [rsp+1318h+var_1058]
0x180044533  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180044538  mov     rsi, [rsp+1318h+var_10A8]
0x180044540  lea     rcx, [rsp+1318h+lpFileName]
0x180044548  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004454d  jmp     loc_1800443E7
0x180044552  movzx   r8d, di
0x180044556  mov     edx, 1
0x18004455b  lea     rcx, [rsp+1318h+var_10D8]
0x180044563  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x180044568  jmp     loc_18004437A
0x18004456d  lea     rdx, byte_1801389F0
0x180044574  mov     rcx, rbx
0x180044577  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004457c  nop
0x18004457d  lea     rcx, [rsp+1318h+var_12B8]
0x180044582  call    ??_D?$basic_ifstream@GU?$char_traits@G@std@@@std@@QEAAXXZ; std::basic_ifstream<ushort>::`vbase destructor'(void)
0x180044587  nop
0x180044588  lea     rcx, [rsp+1318h+pszPath]
0x180044590  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044595  nop
0x180044596  lea     rcx, [rsp+1318h+Src]
0x18004459e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800445a3  nop
0x1800445a4  lea     rcx, [rsp+1318h+var_1038]
0x1800445ac  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800445b1  nop
0x1800445b2  lea     rcx, [rsp+1318h+var_1058]
0x1800445ba  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800445bf  nop
0x1800445c0  lea     rcx, [rsp+1318h+var_10D8]
0x1800445c8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800445cd  mov     rax, rbx
0x1800445d0  jmp     loc_180044667
0x1800445d5  lea     rdx, byte_1801389F0
0x1800445dc  mov     rcx, rbx
0x1800445df  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800445e4  nop
0x1800445e5  lea     rcx, [rsp+1318h+pszPath]
0x1800445ed  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800445f2  nop
0x1800445f3  lea     rcx, [rsp+1318h+Src]
0x1800445fb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044600  nop
0x180044601  lea     rcx, [rsp+1318h+var_1038]
0x180044609  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004460e  nop
0x18004460f  lea     rcx, [rsp+1318h+var_1058]
0x180044617  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004461c  nop
0x18004461d  lea     rcx, [rsp+1318h+var_10D8]
0x180044625  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004462a  mov     rax, rbx
0x18004462d  jmp     short loc_180044667
0x18004462f  jmp     short loc_180044633
0x180044631  jmp     short $+2
0x180044633  mov     rbx, [rsp+1318h+var_12E8]
0x180044638  lea     rdx, [rsp+1318h+var_1058]
0x180044640  mov     rcx, rbx
0x180044643  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180044648  nop
0x180044649  lea     rcx, [rsp+1318h+var_1058]
0x180044651  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044656  nop
0x180044657  lea     rcx, [rsp+1318h+var_10D8]
0x18004465f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044664  mov     rax, rbx
0x180044667  mov     rcx, [rsp+1318h+var_18]
0x18004466f  xor     rcx, rsp; StackCookie
0x180044672  call    __security_check_cookie
0x180044677  lea     r11, [rsp+1318h+var_8]
0x18004467f  mov     rbx, [r11+20h]
0x180044683  mov     rsi, [r11+28h]
0x180044687  mov     rsp, r11
0x18004468a  pop     rdi
0x18004468b  retn
```
