# MsiApplication::QueryMsiDatabaseInstallDirectory(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800284b8`
- end: `0x18002899b`
- name: `?QueryMsiDatabaseInstallDirectory@MsiApplication@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z`
- size: `1251`
- prototype: `__int64 __fastcall(_QWORD *, __int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003bfb0`

## callees

- `0x1800150ac`
- `0x1800175b0`
- `0x180018450`
- `0x180018a60`
- `0x180018ff4`
- `0x18001e0d0`
- `0x18001ea80`
- `0x1800260f4`
- `0x1800284b8`
- `0x1800289a4`
- `0x18002ed54`
- `0x1800404c4`
- `0x180044c88`
- `0x18004eab4`
- `0x1800512b4`
- `0x180059920`
- `0x18005a8bc`
- `0x1800fbe58`
- `0x180100418`

## import_xrefs

- `msi!__imp_MsiDatabaseOpenViewW` at `0x1800285d0`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x1800285d0`
- `msi!__imp_MsiOpenDatabaseW` at `0x180028572`
- `msi!__imp_MsiOpenDatabaseW` at `0x180028572`
- `msi!__imp_MsiRecordGetStringW` at `0x18002869f`
- `msi!__imp_MsiRecordGetStringW` at `0x1800286f2`
- `msi!__imp_MsiRecordGetStringW` at `0x18002869f`
- `msi!__imp_MsiRecordGetStringW` at `0x1800286f2`
- `msi!__imp_MsiViewExecute` at `0x1800285fc`
- `msi!__imp_MsiViewExecute` at `0x1800285fc`
- `msi!__imp_MsiViewFetch` at `0x18002863b`
- `msi!__imp_MsiViewFetch` at `0x180028883`
- `msi!__imp_MsiViewFetch` at `0x18002863b`
- `msi!__imp_MsiViewFetch` at `0x180028883`
- `SHLWAPI!PathFileExistsW` at `0x1800287cc`
- `SHLWAPI!PathFileExistsW` at `0x180028839`
- `SHLWAPI!PathFileExistsW` at `0x1800287cc`
- `SHLWAPI!PathFileExistsW` at `0x180028839`

## string_xrefs

- `0x180028598`: `SELECT `Directory`,`DefaultDir` FROM `Directory``
- `0x180028586`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x1800285e4`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x180028610`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x18002865a`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x1800288b0`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x1800288cc`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x18002892f`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`

## pseudocode

```c
__int64 __fastcall MsiApplication::QueryMsiDatabaseInstallDirectory(_QWORD *a1, __int64 a2, const WCHAR *a3)
{
  _QWORD *v5; // r14
  _QWORD *v6; // rdx
  bool v7; // bl
  MSIHANDLE *v8; // rax
  UINT v9; // eax
  MSIHANDLE *v10; // rax
  const WCHAR *v11; // rdx
  UINT v12; // eax
  UINT v13; // eax
  MSIHANDLE *v14; // rax
  UINT v15; // eax
  UINT v16; // ebx
  UINT StringW; // eax
  WCHAR *v18; // r8
  UINT v19; // eax
  __int64 v20; // rax
  __int64 v21; // rax
  const WCHAR *v22; // rcx
  const WCHAR *v23; // rcx
  MSIHANDLE *v24; // rax
  UINT v25; // eax
  MSIHANDLE hRecord; // [rsp+20h] [rbp-E0h] BYREF
  MSIHANDLE hView; // [rsp+24h] [rbp-DCh] BYREF
  MSIHANDLE hDatabase; // [rsp+28h] [rbp-D8h] BYREF
  DWORD pcchValueBuf; // [rsp+2Ch] [rbp-D4h] BYREF
  DWORD v31[4]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v32; // [rsp+40h] [rbp-C0h]
  LPWSTR v33[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v34; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v35; // [rsp+60h] [rbp-A0h]
  LPCWSTR pszPath[4]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v37; // [rsp+88h] [rbp-78h] BYREF
  __int128 v38; // [rsp+98h] [rbp-68h]
  LPCWSTR Src[4]; // [rsp+A8h] [rbp-58h] BYREF
  LPCWSTR szQuery[4]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v41[40]; // [rsp+E8h] [rbp-18h] BYREF
  WCHAR szValueBuf[264]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  v32 = -2;
  *(_QWORD *)v31 = a2;
  v5 = a1 + 126;
  v37 = 0;
  v38 = 0;
  if ( a1[129] <= 7u )
    v6 = a1 + 126;
  else
    v6 = (_QWORD *)*v5;
  std::wstring::_Construct<2,unsigned short const *>(&v37, v6, a1[128]);
  v7 = (_QWORD)v38 == 0;
  std::wstring::~wstring(&v37);
  if ( v7 )
  {
    std::wstring::wstring(a2, &byte_1801389F0);
  }
  else
  {
    hDatabase = 0;
    v8 = (MSIHANDLE *)PMSIHANDLE::operator&(&hDatabase);
    if ( *((_QWORD *)a3 + 3) > 7u )
      a3 = *(const WCHAR **)a3;
    v9 = MsiOpenDatabaseW(a3, 0, v8);
    if ( v9 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x1FA,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
        (const char *)v9,
        hRecord);
    std::wstring::wstring(szQuery, L"SELECT `Directory`,`DefaultDir` FROM `Directory`");
    hView = 0;
    v10 = (MSIHANDLE *)PMSIHANDLE::operator&(&hView);
    v11 = (const WCHAR *)szQuery;
    if ( szQuery[3] > (LPCWSTR)7 )
      v11 = szQuery[0];
    v12 = MsiDatabaseOpenViewW(hDatabase, v11, v10);
    if ( v12 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x201,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
        (const char *)v12,
        hRecord);
    v13 = MsiViewExecute(hView, 0);
    if ( v13 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x204,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
        (const char *)v13,
        hRecord);
    hRecord = 0;
    v14 = (MSIHANDLE *)PMSIHANDLE::operator&(&hRecord);
    v15 = MsiViewFetch(hView, v14);
    v16 = v15;
    if ( v15 && v15 != 259 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x20B,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
        (const char *)v15,
        hRecord);
    while ( v16 != 259 )
    {
      memset_0(szValueBuf, 0, 0x208u);
      pcchValueBuf = 260;
      StringW = MsiRecordGetStringW(hRecord, 1u, szValueBuf, &pcchValueBuf);
      if ( StringW && StringW != 259 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x21A,
          (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
          (const char *)StringW,
          hRecord);
      std::wstring::wstring(v33);
      std::wstring::resize(v33, 260);
      v31[0] = v34;
      v18 = (WCHAR *)v33;
      if ( v35 > 7 )
        v18 = v33[0];
      v19 = MsiRecordGetStringW(hRecord, 2u, v18, v31);
      if ( v19 && v19 != 259 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x224,
          (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
          (const char *)v19,
          hRecord);
      if ( v34 )
      {
        v20 = std::wstring::find(v33, 124);
        if ( v20 != -1 )
        {
          v21 = std::wstring::substr(v33, v41, v20 + 1, v34);
          std::wstring::operator=(v33, v21);
          std::wstring::~wstring(v41);
        }
        std::wstring::wstring(v41, v5);
        Utility::GetLocalAppDataPathFromUserSid(&v37, v41);
        std::wstring::~wstring(v41);
        std::wstring::wstring(pszPath, &v37);
        std::wstring::_Append<unsigned short>(pszPath);
        std::wstring::_Append<unsigned short>(pszPath);
        v22 = (const WCHAR *)pszPath;
        if ( pszPath[3] > (LPCWSTR)7 )
          v22 = pszPath[0];
        if ( PathFileExistsW(v22) && (unsigned __int8)Utility::ShouldScanInstallDirectoryForFiles(pszPath) )
        {
          std::wstring::wstring(a2, pszPath);
LABEL_44:
          std::wstring::~wstring(pszPath);
          std::wstring::~wstring(&v37);
          std::wstring::~wstring(v33);
          goto LABEL_48;
        }
        std::wstring::wstring(Src, &v37);
        std::wstring::_Append<unsigned short>(Src);
        std::wstring::_Append<unsigned short>(Src);
        v23 = (const WCHAR *)Src;
        if ( Src[3] > (LPCWSTR)7 )
          v23 = Src[0];
        if ( PathFileExistsW(v23) && (unsigned __int8)Utility::ShouldScanInstallDirectoryForFiles(Src) )
        {
          std::wstring::wstring(a2, Src);
          std::wstring::~wstring(Src);
          goto LABEL_44;
        }
        std::wstring::~wstring(Src);
        std::wstring::~wstring(pszPath);
        std::wstring::~wstring(&v37);
      }
      v24 = (MSIHANDLE *)PMSIHANDLE::operator&(&hRecord);
      v25 = MsiViewFetch(hView, v24);
      v16 = v25;
      if ( v25 && v25 != 259 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x24E,
          (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
          (const char *)v25,
          hRecord);
      std::wstring::~wstring(v33);
    }
    std::wstring::wstring(a2, &byte_1801389F0);
LABEL_48:
    PMSIHANDLE::~PMSIHANDLE((PMSIHANDLE *)&hRecord);
    PMSIHANDLE::~PMSIHANDLE((PMSIHANDLE *)&hView);
    std::wstring::~wstring(szQuery);
    PMSIHANDLE::~PMSIHANDLE((PMSIHANDLE *)&hDatabase);
  }
  return a2;
}

```

## disassembly

```asm
0x1800284b8  push    rbp
0x1800284ba  push    rbx
0x1800284bb  push    rsi
0x1800284bc  push    rdi
0x1800284bd  push    r14
0x1800284bf  lea     rbp, [rsp-230h]
0x1800284c7  sub     rsp, 330h
0x1800284ce  mov     [rsp+350h+var_310], 0FFFFFFFFFFFFFFFEh
0x1800284d7  mov     rax, cs:__security_cookie
0x1800284de  xor     rax, rsp
0x1800284e1  mov     [rbp+250h+var_30], rax
0x1800284e8  mov     rsi, r8
0x1800284eb  mov     rdi, rdx
0x1800284ee  mov     qword ptr [rsp+350h+var_320], rdx
0x1800284f3  lea     r14, [rcx+3F0h]
0x1800284fa  xorps   xmm0, xmm0
0x1800284fd  movups  [rbp+250h+var_2C8], xmm0
0x180028501  xorps   xmm1, xmm1
0x180028504  movdqu  [rbp+250h+var_2B8], xmm1
0x180028509  cmp     qword ptr [r14+18h], 7
0x18002850e  jbe     short loc_180028515
0x180028510  mov     rdx, [r14]
0x180028513  jmp     short loc_180028518
0x180028515  mov     rdx, r14
0x180028518  mov     r8, [r14+10h]
0x18002851c  lea     rcx, [rbp+250h+var_2C8]
0x180028520  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x180028525  cmp     qword ptr [rbp+250h+var_2B8], 0
0x18002852a  setz    bl
0x18002852d  lea     rcx, [rbp+250h+var_2C8]
0x180028531  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028536  test    bl, bl
0x180028538  jz      short loc_18002854E
0x18002853a  lea     rdx, byte_1801389F0
0x180028541  mov     rcx, rdi
0x180028544  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180028549  jmp     loc_18002897B
0x18002854e  mov     [rsp+350h+hDatabase], 0
0x180028556  lea     rcx, [rsp+350h+hDatabase]
0x18002855b  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x180028560  cmp     qword ptr [rsi+18h], 7
0x180028565  jbe     short loc_18002856A
0x180028567  mov     rsi, [rsi]
0x18002856a  mov     r8, rax; phDatabase
0x18002856d  xor     edx, edx; szPersist
0x18002856f  mov     rcx, rsi; szDatabasePath
0x180028572  call    cs:__imp_MsiOpenDatabaseW
0x180028578  mov     rcx, [rbp+258h]; this
0x18002857f  test    eax, eax
0x180028581  jz      short loc_180028598
0x180028583  mov     r9d, eax; char *
0x180028586  lea     r8, aBaseAppcompatI_6; "base\\appcompat\\inventory\\software\\i"...
0x18002858d  mov     edx, 1FAh; void *
0x180028592  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180028598  lea     rdx, aSelectDirector; "SELECT `Directory`,`DefaultDir` FROM `D"...
0x18002859f  lea     rcx, [rbp+250h+szQuery]
0x1800285a3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800285a8  nop
0x1800285a9  mov     [rsp+350h+hView], 0
0x1800285b1  lea     rcx, [rsp+350h+hView]
0x1800285b6  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x1800285bb  lea     rdx, [rbp+250h+szQuery]
0x1800285bf  cmp     [rbp+250h+var_270], 7
0x1800285c4  cmova   rdx, [rbp+250h+szQuery]; szQuery
0x1800285c9  mov     r8, rax; phView
0x1800285cc  mov     ecx, [rsp+350h+hDatabase]; hDatabase
0x1800285d0  call    cs:__imp_MsiDatabaseOpenViewW
0x1800285d6  mov     rcx, [rbp+258h]; this
0x1800285dd  test    eax, eax
0x1800285df  jz      short loc_1800285F6
0x1800285e1  mov     r9d, eax; char *
0x1800285e4  lea     r8, aBaseAppcompatI_6; "base\\appcompat\\inventory\\software\\i"...
0x1800285eb  mov     edx, 201h; void *
0x1800285f0  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800285f6  xor     edx, edx; hRecord
0x1800285f8  mov     ecx, [rsp+350h+hView]; hView
0x1800285fc  call    cs:__imp_MsiViewExecute
0x180028602  mov     rcx, [rbp+258h]; this
0x180028609  test    eax, eax
0x18002860b  jz      short loc_180028622
0x18002860d  mov     r9d, eax; char *
0x180028610  lea     r8, aBaseAppcompatI_6; "base\\appcompat\\inventory\\software\\i"...
0x180028617  mov     edx, 204h; void *
0x18002861c  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180028622  mov     [rsp+350h+hRecord], 0; unsigned int
0x18002862a  lea     rcx, [rsp+350h+hRecord]
0x18002862f  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x180028634  mov     rdx, rax; phRecord
0x180028637  mov     ecx, [rsp+350h+hView]; hView
0x18002863b  call    cs:__imp_MsiViewFetch
0x180028641  mov     ebx, eax
0x180028643  mov     esi, 103h
0x180028648  test    eax, eax
0x18002864a  jz      short loc_18002866C
0x18002864c  cmp     eax, esi
0x18002864e  jz      short loc_18002866C
0x180028650  mov     rcx, [rbp+258h]; this
0x180028657  mov     r9d, eax; char *
0x18002865a  lea     r8, aBaseAppcompatI_6; "base\\appcompat\\inventory\\software\\i"...
0x180028661  mov     edx, 20Bh; void *
0x180028666  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18002866c  cmp     ebx, esi
0x18002866e  jz      loc_180028941
0x180028674  xor     edx, edx; Val
0x180028676  mov     r8d, 208h; Size
0x18002867c  lea     rcx, [rbp+250h+szValueBuf]; void *
0x180028680  call    memset_0
0x180028685  mov     [rsp+350h+pcchValueBuf], 104h
0x18002868d  lea     r9, [rsp+350h+pcchValueBuf]; pcchValueBuf
0x180028692  lea     r8, [rbp+250h+szValueBuf]; szValueBuf
0x180028696  mov     edx, 1; iField
0x18002869b  mov     ecx, [rsp+350h+hRecord]; hRecord
0x18002869f  call    cs:__imp_MsiRecordGetStringW
0x1800286a5  test    eax, eax
0x1800286a7  jz      short loc_1800286B1
0x1800286a9  cmp     eax, esi
0x1800286ab  jnz     loc_1800288A6
0x1800286b1  lea     rcx, [rsp+350h+var_308]
0x1800286b6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800286bb  nop
0x1800286bc  mov     edx, 104h
0x1800286c1  lea     rcx, [rsp+350h+var_308]
0x1800286c6  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800286cb  mov     eax, dword ptr [rsp+350h+var_2F8]
0x1800286cf  mov     [rsp+350h+var_320], eax
0x1800286d3  lea     r8, [rsp+350h+var_308]
0x1800286d8  cmp     [rsp+350h+var_2F0], 7
0x1800286de  cmova   r8, [rsp+350h+var_308]; szValueBuf
0x1800286e4  lea     r9, [rsp+350h+var_320]; pcchValueBuf
0x1800286e9  mov     edx, 2; iField
0x1800286ee  mov     ecx, [rsp+350h+hRecord]; hRecord
0x1800286f2  call    cs:__imp_MsiRecordGetStringW
0x1800286f8  test    eax, eax
0x1800286fa  jz      short loc_180028704
0x1800286fc  cmp     eax, esi
0x1800286fe  jnz     loc_1800288C2
0x180028704  cmp     [rsp+350h+var_2F8], 0
0x18002870a  jbe     loc_180028872
0x180028710  mov     edx, 7Ch ; '|'
0x180028715  lea     rcx, [rsp+350h+var_308]
0x18002871a  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find(ushort,unsigned __int64)
0x18002871f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180028723  jz      short loc_180028752
0x180028725  lea     r8, [rax+1]
0x180028729  mov     r9, [rsp+350h+var_2F8]
0x18002872e  lea     rdx, [rbp+250h+var_268]
0x180028732  lea     rcx, [rsp+350h+var_308]
0x180028737  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18002873c  mov     rdx, rax
0x18002873f  lea     rcx, [rsp+350h+var_308]
0x180028744  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180028749  lea     rcx, [rbp+250h+var_268]
0x18002874d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028752  mov     rdx, r14
0x180028755  lea     rcx, [rbp+250h+var_268]
0x180028759  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002875e  nop
0x18002875f  lea     rdx, [rbp+250h+var_268]
0x180028763  lea     rcx, [rbp+250h+var_2C8]
0x180028767  call    ?GetLocalAppDataPathFromUserSid@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::GetLocalAppDataPathFromUserSid(std::wstring const &)
0x18002876c  nop
0x18002876d  lea     rcx, [rbp+250h+var_268]
0x180028771  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028776  lea     rdx, [rbp+250h+var_2C8]
0x18002877a  lea     rcx, [rsp+350h+pszPath]
0x18002877f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180028784  nop
0x180028785  mov     r8d, 1
0x18002878b  lea     rdx, SubBlock; "\\"
0x180028792  lea     rcx, [rsp+350h+pszPath]; Src
0x180028797  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002879c  lea     rdx, [rsp+350h+var_308]
0x1800287a1  cmp     [rsp+350h+var_2F0], 7
0x1800287a7  cmova   rdx, [rsp+350h+var_308]
0x1800287ad  mov     r8, [rsp+350h+var_2F8]
0x1800287b2  lea     rcx, [rsp+350h+pszPath]; Src
0x1800287b7  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800287bc  lea     rcx, [rsp+350h+pszPath]
0x1800287c1  cmp     [rbp+250h+var_2D0], 7
0x1800287c6  cmova   rcx, [rsp+350h+pszPath]; pszPath
0x1800287cc  call    cs:__imp_PathFileExistsW
0x1800287d2  test    eax, eax
0x1800287d4  jz      short loc_1800287E8
0x1800287d6  lea     rcx, [rsp+350h+pszPath]
0x1800287db  call    ?ShouldScanInstallDirectoryForFiles@Utility@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Utility::ShouldScanInstallDirectoryForFiles(std::wstring const &)
0x1800287e0  test    al, al
0x1800287e2  jnz     loc_1800288DE
0x1800287e8  lea     rdx, [rbp+250h+var_2C8]
0x1800287ec  lea     rcx, [rbp+250h+Src]
0x1800287f0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800287f5  nop
0x1800287f6  mov     r8d, 0Bh
0x1800287fc  lea     rdx, aMicrosoft_0; "\\Microsoft\\"
0x180028803  lea     rcx, [rbp+250h+Src]; Src
0x180028807  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002880c  lea     rdx, [rsp+350h+var_308]
0x180028811  cmp     [rsp+350h+var_2F0], 7
0x180028817  cmova   rdx, [rsp+350h+var_308]
0x18002881d  mov     r8, [rsp+350h+var_2F8]
0x180028822  lea     rcx, [rbp+250h+Src]; Src
0x180028826  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002882b  lea     rcx, [rbp+250h+Src]
0x18002882f  cmp     [rbp+250h+var_290], 7
0x180028834  cmova   rcx, [rbp+250h+Src]; pszPath
0x180028839  call    cs:__imp_PathFileExistsW
0x18002883f  test    eax, eax
0x180028841  jz      short loc_180028854
0x180028843  lea     rcx, [rbp+250h+Src]
0x180028847  call    ?ShouldScanInstallDirectoryForFiles@Utility@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Utility::ShouldScanInstallDirectoryForFiles(std::wstring const &)
0x18002884c  test    al, al
0x18002884e  jnz     loc_18002890D
0x180028854  lea     rcx, [rbp+250h+Src]
0x180028858  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002885d  nop
0x18002885e  lea     rcx, [rsp+350h+pszPath]
0x180028863  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028868  nop
0x180028869  lea     rcx, [rbp+250h+var_2C8]
0x18002886d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028872  lea     rcx, [rsp+350h+hRecord]
0x180028877  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x18002887c  mov     rdx, rax; phRecord
0x18002887f  mov     ecx, [rsp+350h+hView]; hView
0x180028883  call    cs:__imp_MsiViewFetch
0x180028889  mov     ebx, eax
0x18002888b  test    eax, eax
0x18002888d  jz      short loc_180028897
0x18002888f  cmp     eax, esi
0x180028891  jnz     loc_180028925
0x180028897  lea     rcx, [rsp+350h+var_308]
0x18002889c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800288a1  jmp     loc_18002866C
0x1800288a6  mov     rcx, [rbp+258h]; this
0x1800288ad  mov     r9d, eax; char *
0x1800288b0  lea     r8, aBaseAppcompatI_6; "base\\appcompat\\inventory\\software\\i"...
0x1800288b7  mov     edx, 21Ah; void *
0x1800288bc  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800288c2  mov     rcx, [rbp+258h]; this
0x1800288c9  mov     r9d, eax; char *
0x1800288cc  lea     r8, aBaseAppcompatI_6; "base\\appcompat\\inventory\\software\\i"...
0x1800288d3  mov     edx, 224h; void *
0x1800288d8  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800288de  lea     rdx, [rsp+350h+pszPath]
0x1800288e3  mov     rcx, rdi
0x1800288e6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800288eb  nop
0x1800288ec  lea     rcx, [rsp+350h+pszPath]
0x1800288f1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800288f6  nop
0x1800288f7  lea     rcx, [rbp+250h+var_2C8]
0x1800288fb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028900  nop
0x180028901  lea     rcx, [rsp+350h+var_308]
0x180028906  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002890b  jmp     short loc_180028951
0x18002890d  lea     rdx, [rbp+250h+Src]
0x180028911  mov     rcx, rdi
0x180028914  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180028919  nop
0x18002891a  lea     rcx, [rbp+250h+Src]
0x18002891e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028923  jmp     short loc_1800288EC
0x180028925  mov     rcx, [rbp+258h]; this
0x18002892c  mov     r9d, eax; char *
0x18002892f  lea     r8, aBaseAppcompatI_6; "base\\appcompat\\inventory\\software\\i"...
0x180028936  mov     edx, 24Eh; void *
0x18002893b  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180028941  lea     rdx, byte_1801389F0
0x180028948  mov     rcx, rdi
0x18002894b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180028950  nop
0x180028951  lea     rcx, [rsp+350h+hRecord]; this
0x180028956  call    ??1PMSIHANDLE@@QEAA@XZ; PMSIHANDLE::~PMSIHANDLE(void)
0x18002895b  nop
0x18002895c  lea     rcx, [rsp+350h+hView]; this
0x180028961  call    ??1PMSIHANDLE@@QEAA@XZ; PMSIHANDLE::~PMSIHANDLE(void)
0x180028966  nop
0x180028967  lea     rcx, [rbp+250h+szQuery]
0x18002896b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028970  nop
0x180028971  lea     rcx, [rsp+350h+hDatabase]; this
0x180028976  call    ??1PMSIHANDLE@@QEAA@XZ; PMSIHANDLE::~PMSIHANDLE(void)
0x18002897b  mov     rax, rdi
0x18002897e  mov     rcx, [rbp+250h+var_30]
0x180028985  xor     rcx, rsp; StackCookie
0x180028988  call    __security_check_cookie
0x18002898d  add     rsp, 330h
0x180028994  pop     r14
0x180028996  pop     rdi
0x180028997  pop     rsi
0x180028998  pop     rbx
0x180028999  pop     rbp
0x18002899a  retn
```
