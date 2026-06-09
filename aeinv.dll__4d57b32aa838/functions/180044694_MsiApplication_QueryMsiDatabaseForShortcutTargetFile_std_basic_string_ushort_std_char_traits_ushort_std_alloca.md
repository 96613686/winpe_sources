# MsiApplication::QueryMsiDatabaseForShortcutTargetFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180044694`
- end: `0x180044c3c`
- name: `?QueryMsiDatabaseForShortcutTargetFile@MsiApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@0@Z`
- size: `1448`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000c490`

## callees

- `0x1800118d0`
- `0x1800150ac`
- `0x1800175b0`
- `0x180018450`
- `0x180018a60`
- `0x18001becc`
- `0x1800289a4`
- `0x18002ed54`
- `0x1800404c4`
- `0x180044694`
- `0x180044c88`
- `0x180045480`
- `0x1800512b4`
- `0x180059920`
- `0x18005a8bc`
- `0x180100418`
- `0x18010f0f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x180044b56`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x180044b56`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180044919`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180044919`
- `msi!__imp_MsiOpenDatabaseW` at `0x180044852`
- `msi!__imp_MsiOpenDatabaseW` at `0x180044852`
- `msi!__imp_MsiRecordGetStringW` at `0x1800449ed`
- `msi!__imp_MsiRecordGetStringW` at `0x180044abf`
- `msi!__imp_MsiRecordGetStringW` at `0x1800449ed`
- `msi!__imp_MsiRecordGetStringW` at `0x180044abf`
- `msi!__imp_MsiViewExecute` at `0x180044945`
- `msi!__imp_MsiViewExecute` at `0x180044945`
- `msi!__imp_MsiViewFetch` at `0x180044981`
- `msi!__imp_MsiViewFetch` at `0x180044b97`
- `msi!__imp_MsiViewFetch` at `0x180044981`
- `msi!__imp_MsiViewFetch` at `0x180044b97`
- `msi!__imp_MsiGetProductInfoExW` at `0x180044732`
- `msi!__imp_MsiGetProductInfoExW` at `0x1800447c8`
- `msi!__imp_MsiGetProductInfoExW` at `0x180044732`
- `msi!__imp_MsiGetProductInfoExW` at `0x1800447c8`
- `msi!__imp_MsiGetComponentPathExW` at `0x180044b41`
- `msi!__imp_MsiGetComponentPathExW` at `0x180044b41`

## string_xrefs

- `0x180044878`: `SELECT `FileName`,`ComponentId` FROM `File`,`Component`,`Shortcut` WHERE `
- `0x180044893`: ``File`.`Component_`=`Component`.`Component` AND `Shortcut`.`Component_`=`Component`.`Component` AND `Shortcut`.`Icon_`='`
- `0x1800447dd`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x180044867`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x18004492e`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x18004495a`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x1800449a1`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x180044a06`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x180044ad8`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x180044bb2`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`

## pseudocode

```c
__int64 __fastcall MsiApplication::QueryMsiDatabaseForShortcutTargetFile(__int64 a1, __int64 a2, _QWORD *a3)
{
  __int64 v5; // r14
  const WCHAR *v6; // rcx
  const WCHAR *v7; // rdx
  const WCHAR *v8; // rcx
  UINT ProductInfo; // eax
  __int64 v10; // r8
  MSIHANDLE *v11; // rax
  const WCHAR *v12; // rcx
  UINT v13; // eax
  __int64 v14; // r8
  MSIHANDLE *v15; // rax
  const WCHAR *v16; // rdx
  UINT v17; // eax
  UINT v18; // eax
  MSIHANDLE *v19; // rax
  UINT v20; // eax
  UINT v21; // ebx
  UINT StringW; // eax
  __int64 v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rax
  UINT v26; // eax
  const WCHAR *v27; // rcx
  __int64 v28; // r8
  MSIHANDLE *v29; // rax
  UINT v30; // eax
  wil *v31; // rcx
  unsigned int szValue; // [rsp+20h] [rbp-788h]
  MSIHANDLE hRecord; // [rsp+30h] [rbp-778h] BYREF
  MSIHANDLE hView; // [rsp+34h] [rbp-774h] BYREF
  MSIINSTALLCONTEXT dwContext; // [rsp+38h] [rbp-770h] BYREF
  DWORD pcchValue; // [rsp+3Ch] [rbp-76Ch] BYREF
  MSIHANDLE hDatabase[2]; // [rsp+40h] [rbp-768h] BYREF
  DWORD pcchValueBuf; // [rsp+48h] [rbp-760h] BYREF
  DWORD pcchOutPathBuffer; // [rsp+4Ch] [rbp-75Ch] BYREF
  __int64 v41; // [rsp+50h] [rbp-758h]
  __int64 v42; // [rsp+58h] [rbp-750h]
  const std::exception *v43; // [rsp+60h] [rbp-748h] BYREF
  LPCWSTR szUserSid[4]; // [rsp+68h] [rbp-740h] BYREF
  LPCWSTR szQuery[4]; // [rsp+88h] [rbp-720h] BYREF
  LPCWSTR szDatabasePath[4]; // [rsp+A8h] [rbp-700h] BYREF
  _BYTE v47[40]; // [rsp+C8h] [rbp-6E0h] BYREF
  WCHAR szComponentCode[40]; // [rsp+F0h] [rbp-6B8h] BYREF
  WCHAR v49[264]; // [rsp+140h] [rbp-668h] BYREF
  WCHAR OutPathBuffer[264]; // [rsp+350h] [rbp-458h] BYREF
  WCHAR szValueBuf[264]; // [rsp+560h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+7A8h] [rbp+0h]

  v42 = -2;
  v5 = a1;
  v41 = a1;
  std::wstring::wstring(a1);
  hDatabase[1] = 1;
  memset_0(v49, 0, 0x208u);
  pcchValue = 260;
  if ( *(_QWORD *)(a2 + 24) <= 7u )
    v6 = (const WCHAR *)a2;
  else
    v6 = *(const WCHAR **)a2;
  MsiGetProductInfoExW(v6, 0, MSIINSTALLCONTEXT_MACHINE, L"LocalPackage", v49, &pcchValue);
  try
  {
    std::wstring::wstring(szDatabasePath, v49);
    if ( !szDatabasePath[2] )
    {
      pcchValue = 260;
      std::wstring::wstring(szUserSid);
      dwContext = MSIINSTALLCONTEXT_FIRSTVISIBLE;
      MsiApplication::GetMsiInstallContextAndUserSidStatic((LPCWSTR)a2);
      v7 = (const WCHAR *)szUserSid;
      if ( szUserSid[3] > (LPCWSTR)7 )
        v7 = szUserSid[0];
      if ( *(_QWORD *)(a2 + 24) <= 7u )
        v8 = (const WCHAR *)a2;
      else
        v8 = *(const WCHAR **)a2;
      ProductInfo = MsiGetProductInfoExW(v8, v7, dwContext, L"LocalPackage", v49, &pcchValue);
      if ( ProductInfo )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x403,
          (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
          (const char *)ProductInfo,
          szValue);
      v10 = -1;
      do
        ++v10;
      while ( v49[v10] );
      std::wstring::_Assign<unsigned short>(szDatabasePath, v49);
      std::wstring::~wstring(szUserSid);
    }
    hDatabase[0] = 0;
    v11 = (MSIHANDLE *)PMSIHANDLE::operator&(hDatabase);
    v12 = (const WCHAR *)szDatabasePath;
    if ( szDatabasePath[3] > (LPCWSTR)7 )
      v12 = szDatabasePath[0];
    v13 = MsiOpenDatabaseW(v12, 0, v11);
    if ( v13 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x408,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
        (const char *)v13,
        szValue);
    std::wstring::wstring(szQuery, L"SELECT `FileName`,`ComponentId` FROM `File`,`Component`,`Shortcut` WHERE ");
    std::wstring::_Append<unsigned short>(szQuery);
    if ( a3[3] > 7u )
      a3 = (_QWORD *)*a3;
    v14 = -1;
    do
      ++v14;
    while ( *((_WORD *)a3 + v14) );
    std::wstring::_Append<unsigned short>(szQuery);
    std::wstring::_Append<unsigned short>(szQuery);
    hView = 0;
    v15 = (MSIHANDLE *)PMSIHANDLE::operator&(&hView);
    v16 = (const WCHAR *)szQuery;
    if ( szQuery[3] > (LPCWSTR)7 )
      v16 = szQuery[0];
    v17 = MsiDatabaseOpenViewW(hDatabase[0], v16, v15);
    if ( v17 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x412,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
        (const char *)v17,
        szValue);
    v18 = MsiViewExecute(hView, 0);
    if ( v18 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x415,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
        (const char *)v18,
        szValue);
    hRecord = 0;
    v19 = (MSIHANDLE *)PMSIHANDLE::operator&(&hRecord);
    v20 = MsiViewFetch(hView, v19);
    v21 = v20;
    if ( v20 && v20 != 259 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x41C,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
        (const char *)v20,
        szValue);
    while ( v21 != 259 )
    {
      memset_0(szValueBuf, 0, 0x208u);
      dwContext = 260;
      StringW = MsiRecordGetStringW(hRecord, 1u, szValueBuf, (LPDWORD)&dwContext);
      if ( StringW && StringW != 259 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x428,
          (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
          (const char *)StringW,
          szValue);
      std::wstring::wstring(szUserSid, szValueBuf);
      v23 = std::wstring::find(szUserSid, 124);
      if ( v23 != -1 )
      {
        v24 = Utility::TrimSpace(szUserSid);
        std::wstring::operator=(szUserSid, v24);
        v25 = std::wstring::substr(szUserSid, v47, v23 + 1, szUserSid[2]);
        std::wstring::operator=(szUserSid, v25);
        std::wstring::~wstring(v47);
      }
      memset_0(szComponentCode, 0, 0x4Eu);
      pcchValueBuf = 39;
      v26 = MsiRecordGetStringW(hRecord, 2u, szComponentCode, &pcchValueBuf);
      if ( v26 && v26 != 259 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x43B,
          (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
          (const char *)v26,
          szValue);
      memset_0(OutPathBuffer, 0, 0x208u);
      pcchOutPathBuffer = 260;
      if ( *(_QWORD *)(a2 + 24) <= 7u )
        v27 = (const WCHAR *)a2;
      else
        v27 = *(const WCHAR **)a2;
      MsiGetComponentPathExW(v27, szComponentCode, L"s-1-1-0", MSIINSTALLCONTEXT_ALL, OutPathBuffer, &pcchOutPathBuffer);
      if ( OutPathBuffer[0] && !(unsigned int)_o_isdigit(OutPathBuffer[0]) )
      {
        v28 = -1;
        do
          ++v28;
        while ( OutPathBuffer[v28] );
        std::wstring::_Assign<unsigned short>(v5, OutPathBuffer);
      }
      v29 = (MSIHANDLE *)PMSIHANDLE::operator&(&hRecord);
      v30 = MsiViewFetch(hView, v29);
      v21 = v30;
      if ( v30 )
      {
        if ( v30 != 259 )
          wil::details::in1diag3::_Throw_Win32(
            retaddr,
            (void *)0x452,
            (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
            (const char *)v30,
            szValue);
      }
      std::wstring::~wstring(szUserSid);
    }
    PMSIHANDLE::~PMSIHANDLE((PMSIHANDLE *)&hRecord);
    PMSIHANDLE::~PMSIHANDLE((PMSIHANDLE *)&hView);
    std::wstring::~wstring(szQuery);
    PMSIHANDLE::~PMSIHANDLE((PMSIHANDLE *)hDatabase);
    std::wstring::~wstring(szDatabasePath);
  }
  catch ( const std::exception *v43 )
  {
    wil::ResultFromCaughtException(v31);
    (*(void (__fastcall **)(const std::exception *))(*(_QWORD *)v43 + 8LL))(v43);
    AslLogCallPrintf(
      1,
      (unsigned int)"MsiApplication::QueryMsiDatabaseForShortcutTargetFile",
      1113,
      (unsigned int)"Exception: 0x%08x %s");
    return v41;
  }
  catch ( ... )
  {
    wil::ResultFromCaughtException(v31);
    AslLogCallPrintf(
      1,
      (unsigned int)"MsiApplication::QueryMsiDatabaseForShortcutTargetFile",
      1118,
      (unsigned int)"Exception: [0x%08x]");
    return v41;
  }
  return v5;
}

```

## disassembly

```asm
0x180044694  push    rbx
0x180044696  push    rsi
0x180044697  push    rdi
0x180044698  push    r12
0x18004469a  push    r14
0x18004469c  sub     rsp, 780h
0x1800446a3  mov     [rsp+7A8h+var_750], 0FFFFFFFFFFFFFFFEh
0x1800446ac  mov     rax, cs:__security_cookie
0x1800446b3  xor     rax, rsp
0x1800446b6  mov     [rsp+7A8h+var_38], rax
0x1800446be  mov     rbx, r8
0x1800446c1  mov     rsi, rdx
0x1800446c4  mov     r14, rcx
0x1800446c7  mov     [rsp+7A8h+var_758], rcx
0x1800446cc  xor     r12d, r12d
0x1800446cf  mov     [rsp+7A8h+var_764], r12d
0x1800446d4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800446d9  mov     [rsp+7A8h+var_764], 1
0x1800446e1  xor     edx, edx; Val
0x1800446e3  mov     r8d, 208h; Size
0x1800446e9  lea     rcx, [rsp+7A8h+var_668]; void *
0x1800446f1  call    memset_0
0x1800446f6  mov     edi, 104h
0x1800446fb  mov     [rsp+7A8h+var_76C], edi
0x1800446ff  cmp     qword ptr [rsi+18h], 7
0x180044704  jbe     short loc_18004470B
0x180044706  mov     rcx, [rsi]
0x180044709  jmp     short loc_18004470E
0x18004470b  mov     rcx, rsi; szProductCode
0x18004470e  lea     rax, [rsp+7A8h+var_76C]
0x180044713  mov     [rsp+7A8h+pcchValue], rax; pcchValue
0x180044718  lea     rax, [rsp+7A8h+var_668]
0x180044720  mov     [rsp+7A8h+szValue], rax; szValue
0x180044725  lea     r9, szProperty; "LocalPackage"
0x18004472c  xor     edx, edx; szUserSid
0x18004472e  lea     r8d, [rdx+4]; dwContext
0x180044732  call    cs:__imp_MsiGetProductInfoExW
0x180044738  lea     rdx, [rsp+7A8h+var_668]
0x180044740  lea     rcx, [rsp+7A8h+szDatabasePath]
0x180044748  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004474d  nop
0x18004474e  cmp     [rsp+7A8h+var_6F0], r12
0x180044756  jnz     loc_180044824
0x18004475c  mov     [rsp+7A8h+var_76C], edi
0x180044760  lea     rcx, [rsp+7A8h+szUserSid]
0x180044765  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18004476a  nop
0x18004476b  mov     [rsp+7A8h+dwContext], r12d
0x180044770  lea     r8, [rsp+7A8h+dwContext]
0x180044775  lea     rdx, [rsp+7A8h+szUserSid]
0x18004477a  mov     rcx, rsi; szProductCode
0x18004477d  call    ?GetMsiInstallContextAndUserSidStatic@MsiApplication@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@AEAW4tagMSIINSTALLCONTEXT@@@Z; MsiApplication::GetMsiInstallContextAndUserSidStatic(std::wstring const &,std::wstring &,tagMSIINSTALLCONTEXT &)
0x180044782  lea     rdx, [rsp+7A8h+szUserSid]
0x180044787  cmp     [rsp+7A8h+var_728], 7
0x180044790  cmova   rdx, [rsp+7A8h+szUserSid]; szUserSid
0x180044796  cmp     qword ptr [rsi+18h], 7
0x18004479b  jbe     short loc_1800447A2
0x18004479d  mov     rcx, [rsi]
0x1800447a0  jmp     short loc_1800447A5
0x1800447a2  mov     rcx, rsi; szProductCode
0x1800447a5  lea     rax, [rsp+7A8h+var_76C]
0x1800447aa  mov     [rsp+7A8h+pcchValue], rax; pcchValue
0x1800447af  lea     rax, [rsp+7A8h+var_668]
0x1800447b7  mov     [rsp+7A8h+szValue], rax; unsigned int
0x1800447bc  lea     r9, szProperty; "LocalPackage"
0x1800447c3  mov     r8d, [rsp+7A8h+dwContext]; dwContext
0x1800447c8  call    cs:__imp_MsiGetProductInfoExW
0x1800447ce  mov     rcx, [rsp+7A8h]; this
0x1800447d6  test    eax, eax
0x1800447d8  jz      short loc_1800447EE
0x1800447da  mov     r9d, eax; char *
0x1800447dd  lea     r8, aBaseAppcompatI_6; "base\\appcompat\\inventory\\software\\i"...
0x1800447e4  mov     edx, 403h; void *
0x1800447e9  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800447ee  lea     rax, [rsp+7A8h+var_668]
0x1800447f6  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800447fa  inc     r8
0x1800447fd  cmp     [rax+r8*2], r12w
0x180044802  jnz     short loc_1800447FA
0x180044804  lea     rdx, [rsp+7A8h+var_668]
0x18004480c  lea     rcx, [rsp+7A8h+szDatabasePath]
0x180044814  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180044819  nop
0x18004481a  lea     rcx, [rsp+7A8h+szUserSid]
0x18004481f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044824  mov     [rsp+7A8h+hDatabase], r12d
0x180044829  lea     rcx, [rsp+7A8h+hDatabase]
0x18004482e  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x180044833  lea     rcx, [rsp+7A8h+szDatabasePath]
0x18004483b  cmp     [rsp+7A8h+var_6E8], 7
0x180044844  cmova   rcx, [rsp+7A8h+szDatabasePath]; szDatabasePath
0x18004484d  mov     r8, rax; phDatabase
0x180044850  xor     edx, edx; szPersist
0x180044852  call    cs:__imp_MsiOpenDatabaseW
0x180044858  mov     rcx, [rsp+7A8h]; this
0x180044860  test    eax, eax
0x180044862  jz      short loc_180044878
0x180044864  mov     r9d, eax; char *
0x180044867  lea     r8, aBaseAppcompatI_6; "base\\appcompat\\inventory\\software\\i"...
0x18004486e  mov     edx, 408h; void *
0x180044873  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180044878  lea     rdx, aSelectFilename_0; "SELECT `FileName`,`ComponentId` FROM `F"...
0x18004487f  lea     rcx, [rsp+7A8h+szQuery]
0x180044887  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004488c  nop
0x18004488d  mov     r8d, 78h ; 'x'
0x180044893  lea     rdx, aFileComponentC; "`File`.`Component_`=`Component`.`Compon"...
0x18004489a  lea     rcx, [rsp+7A8h+szQuery]; Src
0x1800448a2  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800448a7  cmp     qword ptr [rbx+18h], 7
0x1800448ac  jbe     short loc_1800448B1
0x1800448ae  mov     rbx, [rbx]
0x1800448b1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800448b5  inc     r8
0x1800448b8  cmp     [rbx+r8*2], r12w
0x1800448bd  jnz     short loc_1800448B5
0x1800448bf  mov     rdx, rbx
0x1800448c2  lea     rcx, [rsp+7A8h+szQuery]; Src
0x1800448ca  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800448cf  mov     r8d, 1
0x1800448d5  lea     rdx, asc_18013B000; "'"
0x1800448dc  lea     rcx, [rsp+7A8h+szQuery]; Src
0x1800448e4  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800448e9  mov     [rsp+7A8h+hView], r12d
0x1800448ee  lea     rcx, [rsp+7A8h+hView]
0x1800448f3  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x1800448f8  lea     rdx, [rsp+7A8h+szQuery]
0x180044900  cmp     [rsp+7A8h+var_708], 7
0x180044909  cmova   rdx, [rsp+7A8h+szQuery]; szQuery
0x180044912  mov     r8, rax; phView
0x180044915  mov     ecx, [rsp+7A8h+hDatabase]; hDatabase
0x180044919  call    cs:__imp_MsiDatabaseOpenViewW
0x18004491f  mov     rcx, [rsp+7A8h]; this
0x180044927  test    eax, eax
0x180044929  jz      short loc_18004493F
0x18004492b  mov     r9d, eax; char *
0x18004492e  lea     r8, aBaseAppcompatI_6; "base\\appcompat\\inventory\\software\\i"...
0x180044935  mov     edx, 412h; void *
0x18004493a  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18004493f  xor     edx, edx; hRecord
0x180044941  mov     ecx, [rsp+7A8h+hView]; hView
0x180044945  call    cs:__imp_MsiViewExecute
0x18004494b  mov     rcx, [rsp+7A8h]; this
0x180044953  test    eax, eax
0x180044955  jz      short loc_18004496B
0x180044957  mov     r9d, eax; char *
0x18004495a  lea     r8, aBaseAppcompatI_6; "base\\appcompat\\inventory\\software\\i"...
0x180044961  mov     edx, 415h; void *
0x180044966  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18004496b  mov     [rsp+7A8h+hRecord], r12d
0x180044970  lea     rcx, [rsp+7A8h+hRecord]
0x180044975  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x18004497a  mov     rdx, rax; phRecord
0x18004497d  mov     ecx, [rsp+7A8h+hView]; hView
0x180044981  call    cs:__imp_MsiViewFetch
0x180044987  mov     ebx, eax
0x180044989  mov     edi, 103h
0x18004498e  test    eax, eax
0x180044990  jz      short loc_1800449B2
0x180044992  cmp     eax, edi
0x180044994  jz      short loc_1800449B2
0x180044996  mov     rcx, [rsp+7A8h]; this
0x18004499e  mov     r9d, eax; char *
0x1800449a1  lea     r8, aBaseAppcompatI_6; "base\\appcompat\\inventory\\software\\i"...
0x1800449a8  mov     edx, 41Ch; void *
0x1800449ad  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800449b2  cmp     ebx, edi
0x1800449b4  jz      loc_180044BD3
0x1800449ba  xor     edx, edx; Val
0x1800449bc  mov     r8d, 208h; Size
0x1800449c2  lea     rcx, [rsp+7A8h+szValueBuf]; void *
0x1800449ca  call    memset_0
0x1800449cf  mov     [rsp+7A8h+dwContext], 104h
0x1800449d7  lea     r9, [rsp+7A8h+dwContext]; pcchValueBuf
0x1800449dc  lea     r8, [rsp+7A8h+szValueBuf]; szValueBuf
0x1800449e4  mov     edx, 1; iField
0x1800449e9  mov     ecx, [rsp+7A8h+hRecord]; hRecord
0x1800449ed  call    cs:__imp_MsiRecordGetStringW
0x1800449f3  test    eax, eax
0x1800449f5  jz      short loc_180044A17
0x1800449f7  cmp     eax, edi
0x1800449f9  jz      short loc_180044A17
0x1800449fb  mov     rcx, [rsp+7A8h]; this
0x180044a03  mov     r9d, eax; char *
0x180044a06  lea     r8, aBaseAppcompatI_6; "base\\appcompat\\inventory\\software\\i"...
0x180044a0d  mov     edx, 428h; void *
0x180044a12  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180044a17  lea     rdx, [rsp+7A8h+szValueBuf]
0x180044a1f  lea     rcx, [rsp+7A8h+szUserSid]
0x180044a24  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180044a29  nop
0x180044a2a  mov     edx, 7Ch ; '|'
0x180044a2f  lea     rcx, [rsp+7A8h+szUserSid]
0x180044a34  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find(ushort,unsigned __int64)
0x180044a39  mov     rbx, rax
0x180044a3c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180044a40  jz      short loc_180044A8E
0x180044a42  lea     rcx, [rsp+7A8h+szUserSid]
0x180044a47  call    ?TrimSpace@Utility@@SAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; Utility::TrimSpace(std::wstring &)
0x180044a4c  mov     rdx, rax
0x180044a4f  lea     rcx, [rsp+7A8h+szUserSid]
0x180044a54  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180044a59  lea     r8, [rbx+1]
0x180044a5d  mov     r9, [rsp+7A8h+var_730]
0x180044a62  lea     rdx, [rsp+7A8h+var_6E0]
0x180044a6a  lea     rcx, [rsp+7A8h+szUserSid]
0x180044a6f  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180044a74  mov     rdx, rax
0x180044a77  lea     rcx, [rsp+7A8h+szUserSid]
0x180044a7c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180044a81  lea     rcx, [rsp+7A8h+var_6E0]
0x180044a89  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044a8e  xor     edx, edx; Val
0x180044a90  lea     r8d, [rdx+4Eh]; Size
0x180044a94  lea     rcx, [rsp+7A8h+szComponentCode]; void *
0x180044a9c  call    memset_0
0x180044aa1  mov     [rsp+7A8h+pcchValueBuf], 27h ; '''
0x180044aa9  lea     r9, [rsp+7A8h+pcchValueBuf]; pcchValueBuf
0x180044aae  lea     r8, [rsp+7A8h+szComponentCode]; szValueBuf
0x180044ab6  mov     edx, 2; iField
0x180044abb  mov     ecx, [rsp+7A8h+hRecord]; hRecord
0x180044abf  call    cs:__imp_MsiRecordGetStringW
0x180044ac5  test    eax, eax
0x180044ac7  jz      short loc_180044AE9
0x180044ac9  cmp     eax, edi
0x180044acb  jz      short loc_180044AE9
0x180044acd  mov     rcx, [rsp+7A8h]; this
0x180044ad5  mov     r9d, eax; char *
0x180044ad8  lea     r8, aBaseAppcompatI_6; "base\\appcompat\\inventory\\software\\i"...
0x180044adf  mov     edx, 43Bh; void *
0x180044ae4  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180044ae9  xor     edx, edx; Val
0x180044aeb  mov     r8d, 208h; Size
0x180044af1  lea     rcx, [rsp+7A8h+OutPathBuffer]; void *
0x180044af9  call    memset_0
0x180044afe  mov     [rsp+7A8h+pcchOutPathBuffer], 104h
0x180044b06  cmp     qword ptr [rsi+18h], 7
0x180044b0b  jbe     short loc_180044B12
0x180044b0d  mov     rcx, [rsi]
0x180044b10  jmp     short loc_180044B15
0x180044b12  mov     rcx, rsi; szProductCode
0x180044b15  lea     rax, [rsp+7A8h+pcchOutPathBuffer]
0x180044b1a  mov     [rsp+7A8h+pcchValue], rax; pcchOutPathBuffer
0x180044b1f  lea     rax, [rsp+7A8h+OutPathBuffer]
0x180044b27  mov     [rsp+7A8h+szValue], rax; unsigned int
0x180044b2c  mov     r9d, 7; dwContext
0x180044b32  lea     r8, szUserSid; "s-1-1-0"
0x180044b39  lea     rdx, [rsp+7A8h+szComponentCode]; szComponentCode
0x180044b41  call    cs:__imp_MsiGetComponentPathExW
0x180044b47  movzx   eax, [rsp+7A8h+OutPathBuffer]
0x180044b4f  test    ax, ax
0x180044b52  jz      short loc_180044B86
0x180044b54  mov     ecx, eax
0x180044b56  call    cs:__imp__o_isdigit
0x180044b5c  test    eax, eax
0x180044b5e  jnz     short loc_180044B86
0x180044b60  lea     rax, [rsp+7A8h+OutPathBuffer]
0x180044b68  or      r8, 0FFFFFFFFFFFFFFFFh
0x180044b6c  inc     r8
0x180044b6f  cmp     [rax+r8*2], r12w
0x180044b74  jnz     short loc_180044B6C
0x180044b76  lea     rdx, [rsp+7A8h+OutPathBuffer]
0x180044b7e  mov     rcx, r14
0x180044b81  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180044b86  lea     rcx, [rsp+7A8h+hRecord]
0x180044b8b  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x180044b90  mov     rdx, rax; phRecord
0x180044b93  mov     ecx, [rsp+7A8h+hView]; hView
0x180044b97  call    cs:__imp_MsiViewFetch
0x180044b9d  mov     ebx, eax
0x180044b9f  test    eax, eax
0x180044ba1  jz      short loc_180044BC4
0x180044ba3  cmp     eax, edi
0x180044ba5  jz      short loc_180044BC4
0x180044ba7  mov     rcx, [rsp+7A8h]; this
0x180044baf  mov     r9d, eax; char *
0x180044bb2  lea     r8, aBaseAppcompatI_6; "base\\appcompat\\inventory\\software\\i"...
0x180044bb9  mov     edx, 452h; void *
0x180044bbe  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180044bc4  lea     rcx, [rsp+7A8h+szUserSid]
0x180044bc9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044bce  jmp     loc_1800449B2
0x180044bd3  lea     rcx, [rsp+7A8h+hRecord]; this
0x180044bd8  call    ??1PMSIHANDLE@@QEAA@XZ; PMSIHANDLE::~PMSIHANDLE(void)
0x180044bdd  nop
0x180044bde  lea     rcx, [rsp+7A8h+hView]; this
0x180044be3  call    ??1PMSIHANDLE@@QEAA@XZ; PMSIHANDLE::~PMSIHANDLE(void)
0x180044be8  nop
0x180044be9  lea     rcx, [rsp+7A8h+szQuery]
0x180044bf1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044bf6  nop
0x180044bf7  lea     rcx, [rsp+7A8h+hDatabase]; this
0x180044bfc  call    ??1PMSIHANDLE@@QEAA@XZ; PMSIHANDLE::~PMSIHANDLE(void)
0x180044c01  nop
0x180044c02  lea     rcx, [rsp+7A8h+szDatabasePath]
0x180044c0a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180044c0f  nop
0x180044c10  jmp     short loc_180044C19
0x180044c12  jmp     short $+2
0x180044c14  mov     r14, [rsp+7A8h+var_758]
  ... truncated ...
```
