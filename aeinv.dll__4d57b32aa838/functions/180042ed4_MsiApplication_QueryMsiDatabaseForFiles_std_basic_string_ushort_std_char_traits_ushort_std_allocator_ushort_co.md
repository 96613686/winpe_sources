# MsiApplication::QueryMsiDatabaseForFiles(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180042ed4`
- end: `0x180043592`
- name: `?QueryMsiDatabaseForFiles@MsiApplication@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@3@@Z`
- size: `1726`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `26`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003b364`

## callees

- `0x18000d834`
- `0x18000e780`
- `0x1800114a4`
- `0x1800118d0`
- `0x1800172bc`
- `0x1800175b0`
- `0x180018450`
- `0x180018a60`
- `0x1800197d4`
- `0x18001becc`
- `0x18001e0d0`
- `0x1800289a4`
- `0x18002ed54`
- `0x18002fdb4`
- `0x18003e070`
- `0x180040254`
- `0x1800404c4`
- `0x180041ef8`
- `0x180042ed4`
- `0x180043598`
- `0x180044c88`
- `0x18004662c`
- `0x1800512b4`
- `0x180059920`
- `0x18005a8bc`
- `0x180100418`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x18004328e`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x18004328e`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180042fb2`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x180042fb2`
- `msi!__imp_MsiOpenDatabaseW` at `0x180042f57`
- `msi!__imp_MsiOpenDatabaseW` at `0x180042f57`
- `msi!__imp_MsiRecordGetStringW` at `0x180043083`
- `msi!__imp_MsiRecordGetStringW` at `0x18004312c`
- `msi!__imp_MsiRecordGetStringW` at `0x180043083`
- `msi!__imp_MsiRecordGetStringW` at `0x18004312c`
- `msi!__imp_MsiViewExecute` at `0x180042fde`
- `msi!__imp_MsiViewExecute` at `0x180042fde`
- `msi!__imp_MsiViewFetch` at `0x18004301a`
- `msi!__imp_MsiViewFetch` at `0x18004338e`
- `msi!__imp_MsiViewFetch` at `0x18004301a`
- `msi!__imp_MsiViewFetch` at `0x18004338e`
- `msi!__imp_MsiGetComponentPathExW` at `0x180043187`
- `msi!__imp_MsiGetComponentPathExW` at `0x180043187`

## string_xrefs

- `0x18004325e`: `MsiApplication::QueryMsiDatabaseForFiles`
- `0x180043454`: `MsiApplication::QueryMsiDatabaseForFiles`
- `0x180043251`: `ProductCode: %ws ComponentID: %ws ComponentPath: %ws FileName: %ws InstallState: %d`
- `0x180042f7d`: `SELECT `FileName`,`ComponentId` FROM `File`,`Component` WHERE `File`.`Component_`=`Component`.`Component``
- `0x180042f6b`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x180042fc6`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x180042ff2`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x18004303d`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x18004348c`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x1800434a8`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x1800434c4`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x180043447`: `Msi custom action installed file: %ws`

## pseudocode

```c
__int64 __fastcall MsiApplication::QueryMsiDatabaseForFiles(__int64 a1, const WCHAR *a2, const WCHAR *a3, __int64 a4)
{
  MSIHANDLE v7; // edi
  MSIHANDLE *v8; // rax
  UINT v9; // eax
  MSIHANDLE *v10; // rax
  const WCHAR *v11; // rdx
  UINT v12; // eax
  UINT v13; // eax
  MSIHANDLE *v14; // rax
  UINT v15; // eax
  UINT StringW; // eax
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rax
  UINT v20; // eax
  const WCHAR *v21; // rcx
  char v22; // bl
  const WCHAR *v23; // rcx
  __int64 v24; // rax
  __int64 last_of; // rax
  MSIHANDLE *v26; // rax
  UINT v27; // eax
  UINT v28; // ebx
  __int64 v29; // rax
  __int64 v30; // rbx
  _QWORD *v31; // r9
  _QWORD *v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rax
  unsigned int lpOutPathBuffer; // [rsp+28h] [rbp-E0h]
  MSIHANDLE hRecord; // [rsp+58h] [rbp-B0h] BYREF
  MSIHANDLE hView; // [rsp+5Ch] [rbp-ACh] BYREF
  MSIHANDLE hDatabase[2]; // [rsp+60h] [rbp-A8h] BYREF
  DWORD v40[2]; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD *pcchOutPathBuffer; // [rsp+70h] [rbp-98h] BYREF
  DWORD pcchValueBuf[2]; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v43[2]; // [rsp+80h] [rbp-88h] BYREF
  _QWORD v44[3]; // [rsp+90h] [rbp-78h] BYREF
  char v45[16]; // [rsp+A8h] [rbp-60h] BYREF
  char v46[16]; // [rsp+B8h] [rbp-50h] BYREF
  _QWORD v47[2]; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v48; // [rsp+D8h] [rbp-30h]
  _BYTE Src[16]; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v50; // [rsp+F8h] [rbp-10h]
  _BYTE v51[32]; // [rsp+108h] [rbp+0h] BYREF
  _BYTE v52[32]; // [rsp+128h] [rbp+20h] BYREF
  LPCWSTR szQuery[4]; // [rsp+148h] [rbp+40h] BYREF
  WCHAR OutPathBuffer[264]; // [rsp+168h] [rbp+60h] BYREF
  WCHAR szComponentCode[264]; // [rsp+378h] [rbp+270h] BYREF
  WCHAR szValueBuf[264]; // [rsp+588h] [rbp+480h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+7E0h] [rbp+6D8h]

  v44[2] = -2;
  v7 = 0;
  hDatabase[1] = 0;
  std::set<std::wstring>::set<std::wstring>(v44);
  std::set<std::wstring>::set<std::wstring>(v43);
  hDatabase[0] = 0;
  v8 = (MSIHANDLE *)PMSIHANDLE::operator&(hDatabase);
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(const WCHAR **)a3;
  v9 = MsiOpenDatabaseW(a3, 0, v8);
  if ( v9 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x271,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
      (const char *)v9,
      lpOutPathBuffer);
  std::wstring::wstring(
    szQuery,
    L"SELECT `FileName`,`ComponentId` FROM `File`,`Component` WHERE `File`.`Component_`=`Component`.`Component`");
  hView = 0;
  v10 = (MSIHANDLE *)PMSIHANDLE::operator&(&hView);
  v11 = (const WCHAR *)szQuery;
  if ( szQuery[3] > (LPCWSTR)7 )
    v11 = szQuery[0];
  v12 = MsiDatabaseOpenViewW(hDatabase[0], v11, v10);
  if ( v12 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x278,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
      (const char *)v12,
      lpOutPathBuffer);
  v13 = MsiViewExecute(hView, 0);
  if ( v13 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x27B,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
      (const char *)v13,
      lpOutPathBuffer);
  hRecord = 0;
  v14 = (MSIHANDLE *)PMSIHANDLE::operator&(&hRecord);
  v15 = MsiViewFetch(hView, v14);
  if ( v15 )
  {
    if ( v15 != 259 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x282,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
        (const char *)v15,
        lpOutPathBuffer);
  }
  else
  {
    do
    {
      memset_0(szValueBuf, 0, 0x208u);
      pcchValueBuf[0] = 260;
      StringW = MsiRecordGetStringW(hRecord, 1u, szValueBuf, pcchValueBuf);
      if ( StringW && StringW != 259 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x291,
          (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
          (const char *)StringW,
          lpOutPathBuffer);
      std::wstring::wstring(v47, szValueBuf);
      v17 = std::wstring::find(v47, 124);
      if ( v17 != -1 )
      {
        v18 = Utility::TrimSpace(v47);
        std::wstring::operator=(v47, v18);
        v19 = std::wstring::substr(v47, v52, v17 + 1, v48);
        std::wstring::operator=(v47, v19);
        std::wstring::~wstring(v52);
      }
      memset_0(szComponentCode, 0, 0x208u);
      v40[0] = 260;
      v20 = MsiRecordGetStringW(hRecord, 2u, szComponentCode, v40);
      if ( v20 && v20 != 259 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x2A5,
          (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
          (const char *)v20,
          lpOutPathBuffer);
      memset_0(OutPathBuffer, 0, 0x208u);
      LODWORD(pcchOutPathBuffer) = 260;
      if ( *((_QWORD *)a2 + 3) <= 7u )
        v21 = a2;
      else
        v21 = *(const WCHAR **)a2;
      MsiGetComponentPathExW(
        v21,
        szComponentCode,
        L"s-1-1-0",
        MSIINSTALLCONTEXT_ALL,
        OutPathBuffer,
        (LPDWORD)&pcchOutPathBuffer);
      std::wstring::wstring(Src, L".exe");
      v7 |= 1u;
      hDatabase[1] = v7;
      if ( (unsigned __int8)Utility::FoundSubstring(Src, v47)
        || (std::wstring::wstring(v51, L".sys"),
            v7 |= 2u,
            hDatabase[1] = v7,
            v22 = 0,
            (unsigned __int8)Utility::FoundSubstring(v51, v47)) )
      {
        v22 = 1;
      }
      if ( (v7 & 2) != 0 )
      {
        v7 &= ~2u;
        std::wstring::~wstring(v51);
      }
      if ( (v7 & 1) != 0 )
      {
        v7 &= ~1u;
        std::wstring::~wstring(Src);
      }
      if ( v22 )
      {
        if ( *((_QWORD *)a2 + 3) <= 7u )
          LODWORD(v23) = (_DWORD)a2;
        else
          v23 = *(const WCHAR **)a2;
        lpOutPathBuffer = (unsigned int)v23;
        AslLogCallPrintf(
          3,
          (unsigned int)"MsiApplication::QueryMsiDatabaseForFiles",
          702,
          (unsigned int)"ProductCode: %ws ComponentID: %ws ComponentPath: %ws FileName: %ws InstallState: %d");
      }
      v24 = -1;
      do
        ++v24;
      while ( OutPathBuffer[v24] );
      if ( v24 )
      {
        if ( (unsigned int)_o_isdigit(OutPathBuffer[0]) )
        {
          std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring &>(
            v43,
            v45,
            v47);
        }
        else
        {
          std::wstring::wstring(v52, OutPathBuffer);
          Utility::GetDirectoryFromPath(Src, v52);
          std::wstring::~wstring(v52);
          if ( v50 && v48 )
          {
            last_of = std::wstring::find_last_of(Src, 92);
            if ( last_of != v50 && v50 )
            {
              std::wstring::_Append<unsigned short>(Src);
              std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring &>(
                v44,
                v46,
                Src);
            }
            std::operator+<unsigned short>(v51, Src, v47);
            if ( *(_QWORD *)(a4 + 8) == *(_QWORD *)(a4 + 16) )
            {
              std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a4, *(_QWORD *)(a4 + 8), v51);
            }
            else
            {
              std::wstring::wstring(*(_QWORD *)(a4 + 8), v51);
              *(_QWORD *)(a4 + 8) += 32LL;
            }
            std::wstring::~wstring(v51);
          }
          std::wstring::~wstring(Src);
        }
      }
      v26 = (MSIHANDLE *)PMSIHANDLE::operator&(&hRecord);
      v27 = MsiViewFetch(hView, v26);
      v28 = v27;
      if ( v27 && v27 != 259 )
        wil::details::in1diag3::_Throw_Win32(
          retaddr,
          (void *)0x2F1,
          (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
          (const char *)v27,
          lpOutPathBuffer);
      std::wstring::~wstring(v47);
    }
    while ( v28 != 259 );
  }
  v29 = v43[0];
  v30 = *(_QWORD *)v43[0];
  *(_QWORD *)v40 = *(_QWORD *)v43[0];
  v31 = (_QWORD *)v44[0];
  while ( v30 != v29 )
  {
    v32 = (_QWORD *)*v31;
    pcchOutPathBuffer = (_QWORD *)*v31;
    while ( v32 != v31 )
    {
      std::wstring::wstring(v47, v32 + 4);
      v33 = std::wstring::_Append<unsigned short>(v47);
      v34 = Utility::VerifyAndNormalizeFilePath(v52, v33);
      std::wstring::operator=(v47, v34);
      std::wstring::~wstring(v52);
      if ( v48 )
      {
        AslLogCallPrintf(
          3,
          (unsigned int)"MsiApplication::QueryMsiDatabaseForFiles",
          769,
          (unsigned int)"Msi custom action installed file: %ws");
        if ( *(_QWORD *)(a4 + 8) == *(_QWORD *)(a4 + 16) )
        {
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a4, *(_QWORD *)(a4 + 8), v47);
        }
        else
        {
          std::wstring::wstring(*(_QWORD *)(a4 + 8), v47);
          *(_QWORD *)(a4 + 8) += 32LL;
        }
      }
      std::wstring::~wstring(v47);
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<File>>,std::_Iterator_base0>::operator++(&pcchOutPathBuffer);
      v31 = (_QWORD *)v44[0];
      v32 = pcchOutPathBuffer;
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<File>>,std::_Iterator_base0>::operator++(v40);
    v29 = v43[0];
    v30 = *(_QWORD *)v40;
  }
  PMSIHANDLE::~PMSIHANDLE((PMSIHANDLE *)&hRecord);
  PMSIHANDLE::~PMSIHANDLE((PMSIHANDLE *)&hView);
  std::wstring::~wstring(szQuery);
  PMSIHANDLE::~PMSIHANDLE((PMSIHANDLE *)hDatabase);
  std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
    v43,
    v43);
  return std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
           v44,
           v44);
}

```

## disassembly

```asm
0x180042ed4  mov     rax, rsp
0x180042ed7  push    rbp
0x180042ed8  push    rsi
0x180042ed9  push    rdi
0x180042eda  push    r12
0x180042edc  push    r13
0x180042ede  push    r14
0x180042ee0  push    r15
0x180042ee2  lea     rbp, [rax-6D8h]
0x180042ee9  sub     rsp, 7A0h
0x180042ef0  mov     [rbp+6D0h+var_738], 0FFFFFFFFFFFFFFFEh
0x180042ef8  mov     [rax+8], rbx
0x180042efc  mov     rax, cs:__security_cookie
0x180042f03  xor     rax, rsp
0x180042f06  mov     [rbp+6D0h+var_40], rax
0x180042f0d  mov     rsi, r9
0x180042f10  mov     rbx, r8
0x180042f13  mov     r15, rdx
0x180042f16  xor     r13d, r13d
0x180042f19  mov     edi, r13d
0x180042f1c  mov     [rsp+7D0h+hDatabase+4], r13d
0x180042f21  lea     rcx, [rbp+6D0h+var_748]
0x180042f25  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x180042f2a  nop
0x180042f2b  lea     rcx, [rsp+78h]
0x180042f30  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x180042f35  nop
0x180042f36  mov     [rsp+7D0h+hDatabase], r13d
0x180042f3b  lea     rcx, [rsp+7D0h+hDatabase]
0x180042f40  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x180042f45  cmp     qword ptr [rbx+18h], 7
0x180042f4a  jbe     short loc_180042F4F
0x180042f4c  mov     rbx, [rbx]
0x180042f4f  mov     r8, rax; phDatabase
0x180042f52  xor     edx, edx; szPersist
0x180042f54  mov     rcx, rbx; szDatabasePath
0x180042f57  call    cs:__imp_MsiOpenDatabaseW
0x180042f5d  mov     rcx, [rbp+6D8h]; this
0x180042f64  test    eax, eax
0x180042f66  jz      short loc_180042F7D
0x180042f68  mov     r9d, eax; char *
0x180042f6b  lea     r8, aBaseAppcompatI_6; "base\\appcompat\\inventory\\software\\i"...
0x180042f72  mov     edx, 271h; void *
0x180042f77  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180042f7d  lea     rdx, aSelectFilename; "SELECT `FileName`,`ComponentId` FROM `F"...
0x180042f84  lea     rcx, [rbp+6D0h+szQuery]
0x180042f88  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180042f8d  nop
0x180042f8e  mov     [rsp+7D0h+hView], r13d
0x180042f93  lea     rcx, [rsp+7D0h+hView]
0x180042f98  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x180042f9d  lea     rdx, [rbp+6D0h+szQuery]
0x180042fa1  cmp     [rbp+6D0h+var_678], 7
0x180042fa6  cmova   rdx, [rbp+6D0h+szQuery]; szQuery
0x180042fab  mov     r8, rax; phView
0x180042fae  mov     ecx, [rsp+7D0h+hDatabase]; hDatabase
0x180042fb2  call    cs:__imp_MsiDatabaseOpenViewW
0x180042fb8  mov     rcx, [rbp+6D8h]; this
0x180042fbf  test    eax, eax
0x180042fc1  jz      short loc_180042FD8
0x180042fc3  mov     r9d, eax; char *
0x180042fc6  lea     r8, aBaseAppcompatI_6; "base\\appcompat\\inventory\\software\\i"...
0x180042fcd  mov     edx, 278h; void *
0x180042fd2  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180042fd8  xor     edx, edx; hRecord
0x180042fda  mov     ecx, [rsp+7D0h+hView]; hView
0x180042fde  call    cs:__imp_MsiViewExecute
0x180042fe4  mov     rcx, [rbp+6D8h]; this
0x180042feb  test    eax, eax
0x180042fed  jz      short loc_180043004
0x180042fef  mov     r9d, eax; char *
0x180042ff2  lea     r8, aBaseAppcompatI_6; "base\\appcompat\\inventory\\software\\i"...
0x180042ff9  mov     edx, 27Bh; void *
0x180042ffe  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180043004  mov     [rsp+7D0h+hRecord], r13d
0x180043009  lea     rcx, [rsp+7D0h+hRecord]
0x18004300e  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x180043013  mov     rdx, rax; phRecord
0x180043016  mov     ecx, [rsp+7D0h+hView]; hView
0x18004301a  call    cs:__imp_MsiViewFetch
0x180043020  mov     r14d, 103h
0x180043026  test    eax, eax
0x180043028  jz      short loc_18004304F
0x18004302a  cmp     eax, r14d
0x18004302d  jz      loc_1800433B5
0x180043033  mov     rcx, [rbp+6D8h]; this
0x18004303a  mov     r9d, eax; char *
0x18004303d  lea     r8, aBaseAppcompatI_6; "base\\appcompat\\inventory\\software\\i"...
0x180043044  mov     edx, 282h; void *
0x180043049  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x18004304f  mov     r12d, 208h
0x180043055  mov     r8d, r12d; Size
0x180043058  xor     edx, edx; Val
0x18004305a  lea     rcx, [rbp+6D0h+szValueBuf]; void *
0x180043061  call    memset_0
0x180043066  mov     [rsp+7D0h+pcchValueBuf], 104h
0x18004306e  lea     r9, [rsp+7D0h+pcchValueBuf]; pcchValueBuf
0x180043073  lea     r8, [rbp+6D0h+szValueBuf]; szValueBuf
0x18004307a  mov     edx, 1; iField
0x18004307f  mov     ecx, [rsp+7D0h+hRecord]; hRecord
0x180043083  call    cs:__imp_MsiRecordGetStringW
0x180043089  test    eax, eax
0x18004308b  jz      short loc_180043096
0x18004308d  cmp     eax, r14d
0x180043090  jnz     loc_180043482
0x180043096  lea     rdx, [rbp+6D0h+szValueBuf]
0x18004309d  lea     rcx, [rbp+6D0h+var_710]
0x1800430a1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800430a6  nop
0x1800430a7  mov     edx, 7Ch ; '|'
0x1800430ac  lea     rcx, [rbp+6D0h+var_710]
0x1800430b0  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find(ushort,unsigned __int64)
0x1800430b5  mov     rbx, rax
0x1800430b8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800430bc  jz      short loc_1800430FD
0x1800430be  lea     rcx, [rbp+6D0h+var_710]
0x1800430c2  call    ?TrimSpace@Utility@@SAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; Utility::TrimSpace(std::wstring &)
0x1800430c7  mov     rdx, rax
0x1800430ca  lea     rcx, [rbp+6D0h+var_710]
0x1800430ce  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800430d3  lea     r8, [rbx+1]
0x1800430d7  mov     r9, [rbp+6D0h+var_700]
0x1800430db  lea     rdx, [rbp+6D0h+var_6B0]
0x1800430df  lea     rcx, [rbp+6D0h+var_710]
0x1800430e3  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x1800430e8  mov     rdx, rax
0x1800430eb  lea     rcx, [rbp+6D0h+var_710]
0x1800430ef  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800430f4  lea     rcx, [rbp+6D0h+var_6B0]
0x1800430f8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800430fd  mov     r8, r12; Size
0x180043100  xor     edx, edx; Val
0x180043102  lea     rcx, [rbp+6D0h+szComponentCode]; void *
0x180043109  call    memset_0
0x18004310e  mov     ebx, 104h
0x180043113  mov     [rsp+7D0h+var_770], ebx
0x180043117  lea     r9, [rsp+7D0h+var_770]; pcchValueBuf
0x18004311c  lea     r8, [rbp+6D0h+szComponentCode]; szValueBuf
0x180043123  mov     edx, 2; iField
0x180043128  mov     ecx, [rsp+7D0h+hRecord]; hRecord
0x18004312c  call    cs:__imp_MsiRecordGetStringW
0x180043132  test    eax, eax
0x180043134  jz      short loc_18004313F
0x180043136  cmp     eax, r14d
0x180043139  jnz     loc_18004349E
0x18004313f  mov     r8, r12; Size
0x180043142  xor     edx, edx; Val
0x180043144  lea     rcx, [rbp+6D0h+OutPathBuffer]; void *
0x180043148  call    memset_0
0x18004314d  mov     dword ptr [rsp+7D0h+var_768], ebx
0x180043151  cmp     qword ptr [r15+18h], 7
0x180043156  jbe     short loc_18004315D
0x180043158  mov     rcx, [r15]
0x18004315b  jmp     short loc_180043160
0x18004315d  mov     rcx, r15; szProductCode
0x180043160  lea     rax, [rsp+7D0h+var_768]
0x180043165  mov     [rsp+7D0h+pcchOutPathBuffer], rax; pcchOutPathBuffer
0x18004316a  lea     rax, [rbp+6D0h+OutPathBuffer]
0x18004316e  mov     [rsp+7D0h+lpOutPathBuffer], rax; lpOutPathBuffer
0x180043173  mov     r9d, 7; dwContext
0x180043179  lea     r8, szUserSid; "s-1-1-0"
0x180043180  lea     rdx, [rbp+6D0h+szComponentCode]; szComponentCode
0x180043187  call    cs:__imp_MsiGetComponentPathExW
0x18004318d  mov     r12d, eax
0x180043190  lea     rdx, aExe; ".exe"
0x180043197  lea     rcx, [rbp+6D0h+Src]
0x18004319b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800431a0  nop
0x1800431a1  or      edi, 1
0x1800431a4  mov     [rsp+7D0h+hDatabase+4], edi
0x1800431a8  lea     rdx, [rbp+6D0h+var_710]
0x1800431ac  lea     rcx, [rbp+6D0h+Src]
0x1800431b0  call    ?FoundSubstring@Utility@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Utility::FoundSubstring(std::wstring const &,std::wstring const &)
0x1800431b5  test    al, al
0x1800431b7  jnz     short loc_1800431E5
0x1800431b9  lea     rdx, aSys; ".sys"
0x1800431c0  lea     rcx, [rbp+6D0h+var_6D0]
0x1800431c4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800431c9  nop
0x1800431ca  or      edi, 2
0x1800431cd  mov     [rsp+7D0h+hDatabase+4], edi
0x1800431d1  lea     rdx, [rbp+6D0h+var_710]
0x1800431d5  lea     rcx, [rbp+6D0h+var_6D0]
0x1800431d9  call    ?FoundSubstring@Utility@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Utility::FoundSubstring(std::wstring const &,std::wstring const &)
0x1800431de  test    al, al
0x1800431e0  mov     bl, r13b
0x1800431e3  jz      short loc_1800431E7
0x1800431e5  mov     bl, 1
0x1800431e7  test    dil, 2
0x1800431eb  jz      short loc_1800431FA
0x1800431ed  and     edi, 0FFFFFFFDh
0x1800431f0  lea     rcx, [rbp+6D0h+var_6D0]
0x1800431f4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800431f9  nop
0x1800431fa  test    dil, 1
0x1800431fe  jz      short loc_18004320C
0x180043200  and     edi, 0FFFFFFFEh
0x180043203  lea     rcx, [rbp+6D0h+Src]
0x180043207  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004320c  test    bl, bl
0x18004320e  jz      short loc_18004326F
0x180043210  lea     rax, [rbp+6D0h+var_710]
0x180043214  cmp     [rbp+6D0h+var_6F8], 7
0x180043219  cmova   rax, [rbp+6D0h+var_710]
0x18004321e  cmp     qword ptr [r15+18h], 7
0x180043223  jbe     short loc_18004322A
0x180043225  mov     rcx, [r15]
0x180043228  jmp     short loc_18004322D
0x18004322a  mov     rcx, r15
0x18004322d  mov     [rsp+40h], r12d
0x180043232  mov     qword ptr [rsp+7D0h+var_798], rax
0x180043237  lea     rax, [rbp+6D0h+OutPathBuffer]
0x18004323b  mov     [rsp+7D0h+var_7A0], rax
0x180043240  lea     rax, [rbp+6D0h+szComponentCode]
0x180043247  mov     [rsp+7D0h+pcchOutPathBuffer], rax
0x18004324c  mov     [rsp+7D0h+lpOutPathBuffer], rcx; unsigned int
0x180043251  lea     r9, aProductcodeWsC; "ProductCode: %ws ComponentID: %ws Compo"...
0x180043258  mov     r8d, 2BEh
0x18004325e  lea     rdx, aMsiapplication_2; "MsiApplication::QueryMsiDatabaseForFile"...
0x180043265  mov     ecx, 3
0x18004326a  call    AslLogCallPrintf
0x18004326f  lea     rcx, [rbp+6D0h+OutPathBuffer]
0x180043273  or      rax, 0FFFFFFFFFFFFFFFFh
0x180043277  inc     rax
0x18004327a  cmp     [rcx+rax*2], r13w
0x18004327f  jnz     short loc_180043277
0x180043281  test    rax, rax
0x180043284  jz      loc_18004337D
0x18004328a  movzx   ecx, [rbp+6D0h+OutPathBuffer]
0x18004328e  call    cs:__imp__o_isdigit
0x180043294  test    eax, eax
0x180043296  jz      short loc_1800432AF
0x180043298  lea     r8, [rbp+6D0h+var_710]
0x18004329c  lea     rdx, [rbp+6D0h+var_730]
0x1800432a0  lea     rcx, [rsp+78h]
0x1800432a5  call    ??$emplace@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring &>(std::wstring &)
0x1800432aa  jmp     loc_18004337D
0x1800432af  lea     rdx, [rbp+6D0h+OutPathBuffer]
0x1800432b3  lea     rcx, [rbp+6D0h+var_6B0]
0x1800432b7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800432bc  nop
0x1800432bd  lea     rdx, [rbp+6D0h+var_6B0]
0x1800432c1  lea     rcx, [rbp+6D0h+Src]
0x1800432c5  call    ?GetDirectoryFromPath@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::GetDirectoryFromPath(std::wstring const &)
0x1800432ca  nop
0x1800432cb  lea     rcx, [rbp+6D0h+var_6B0]
0x1800432cf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800432d4  cmp     [rbp+6D0h+var_6E0], r13
0x1800432d8  jbe     loc_180043374
0x1800432de  cmp     [rbp+6D0h+var_700], r13
0x1800432e2  jbe     loc_180043374
0x1800432e8  mov     edx, 5Ch ; '\'
0x1800432ed  lea     rcx, [rbp+6D0h+Src]
0x1800432f1  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find_last_of(ushort,unsigned __int64)
0x1800432f6  mov     rcx, [rbp+6D0h+var_6E0]
0x1800432fa  cmp     rax, rcx
0x1800432fd  jz      short loc_18004332B
0x1800432ff  test    rcx, rcx
0x180043302  jz      short loc_18004332B
0x180043304  mov     r8d, 1
0x18004330a  lea     rdx, SubBlock; "\\"
0x180043311  lea     rcx, [rbp+6D0h+Src]; Src
0x180043315  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004331a  lea     r8, [rbp+6D0h+Src]
0x18004331e  lea     rdx, [rbp+6D0h+var_720]
0x180043322  lea     rcx, [rbp+6D0h+var_748]
0x180043326  call    ??$emplace@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring &>(std::wstring &)
0x18004332b  lea     r8, [rbp+6D0h+var_710]
0x18004332f  lea     rdx, [rbp+6D0h+Src]
0x180043333  lea     rcx, [rbp+6D0h+var_6D0]
0x180043337  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@0@Z; std::operator+<ushort>(std::wstring const &,std::wstring const &)
0x18004333c  nop
0x18004333d  mov     rax, [rsi+8]
0x180043341  cmp     rax, [rsi+10h]
0x180043345  jz      short loc_18004335A
0x180043347  lea     rdx, [rbp+6D0h+var_6D0]
0x18004334b  mov     rcx, rax
0x18004334e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180043353  add     qword ptr [rsi+8], 20h ; ' '
0x180043358  jmp     short loc_18004336A
0x18004335a  lea     r8, [rbp+6D0h+var_6D0]
0x18004335e  mov     rdx, rax
0x180043361  mov     rcx, rsi
0x180043364  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180043369  nop
0x18004336a  lea     rcx, [rbp+6D0h+var_6D0]
0x18004336e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180043373  nop
0x180043374  lea     rcx, [rbp+6D0h+Src]
0x180043378  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004337d  lea     rcx, [rsp+7D0h+hRecord]
0x180043382  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x180043387  mov     rdx, rax; phRecord
0x18004338a  mov     ecx, [rsp+7D0h+hView]; hView
0x18004338e  call    cs:__imp_MsiViewFetch
0x180043394  mov     ebx, eax
0x180043396  test    eax, eax
0x180043398  jz      short loc_1800433A3
0x18004339a  cmp     eax, r14d
0x18004339d  jnz     loc_1800434BA
  ... truncated ...
```
