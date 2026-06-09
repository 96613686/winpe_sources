# MsiApplication::QueryMsiDatabaseForFiles2(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x18010f720`
- end: `0x18010feb2`
- name: `?QueryMsiDatabaseForFiles2@MsiApplication@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@3@AEAV43@@Z`
- size: `1938`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, __int64, __int64)`
- caller_count: `1`
- callee_count: `36`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18003b364`

## callees

- `0x18000d834`
- `0x18000e780`
- `0x1800114a4`
- `0x1800118d0`
- `0x1800150ac`
- `0x1800172bc`
- `0x1800175b0`
- `0x180018450`
- `0x180018a60`
- `0x1800197d4`
- `0x18001becc`
- `0x1800289a4`
- `0x18002ed54`
- `0x18002fdb4`
- `0x180040254`
- `0x1800404c4`
- `0x180041ef8`
- `0x180043598`
- `0x180044c88`
- `0x18004662c`
- `0x1800493b8`
- `0x1800512b4`
- `0x180059920`
- `0x18005a0ac`
- `0x18005a8bc`
- `0x1800677b0`
- `0x1800ffc38`
- `0x1800fffa8`
- `0x180100418`
- `0x18010e3cc`
- `0x18010e4d8`
- `0x18010e6a0`
- `0x18010eac4`
- `0x18010eb20`
- `0x18010f720`
- `0x18010feb8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x18010fb42`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x18010fb42`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x18010f839`
- `msi!__imp_MsiDatabaseOpenViewW` at `0x18010f839`
- `msi!__imp_MsiOpenDatabaseW` at `0x18010f7e4`
- `msi!__imp_MsiOpenDatabaseW` at `0x18010f7e4`
- `msi!__imp_MsiRecordGetStringW` at `0x18010f92a`
- `msi!__imp_MsiRecordGetStringW` at `0x18010fa53`
- `msi!__imp_MsiRecordGetStringW` at `0x18010f92a`
- `msi!__imp_MsiRecordGetStringW` at `0x18010fa53`
- `msi!__imp_MsiViewExecute` at `0x18010f854`
- `msi!__imp_MsiViewExecute` at `0x18010f854`
- `msi!__imp_MsiViewFetch` at `0x18010f87f`
- `msi!__imp_MsiViewFetch` at `0x18010fa04`
- `msi!__imp_MsiViewFetch` at `0x18010fc6d`
- `msi!__imp_MsiViewFetch` at `0x18010f87f`
- `msi!__imp_MsiViewFetch` at `0x18010fa04`
- `msi!__imp_MsiViewFetch` at `0x18010fc6d`
- `msi!__imp_MsiGetComponentPathExW` at `0x18010fb16`
- `msi!__imp_MsiGetComponentPathExW` at `0x18010fb16`

## string_xrefs

- `0x18010f7f9`: `SELECT `FileName`,`ComponentId` FROM `File`,`Component` WHERE `File`.`Component_`=`Component`.`Component``
- `0x18010fdf1`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x18010fe0d`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x18010fe22`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x18010fe37`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x18010fe4c`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x18010fe68`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x18010fe84`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x18010fea0`: `base\appcompat\inventory\software\inv2\lib\msiapplication.cpp`
- `0x18010fd23`: `Msi custom action installed file: %ws`
- `0x18010fd30`: `MsiApplication::QueryMsiDatabaseForFiles2`

## pseudocode

```c
__int64 __fastcall MsiApplication::QueryMsiDatabaseForFiles2(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5)
{
  MSIHANDLE *v8; // rax
  UINT v9; // eax
  MSIHANDLE *v10; // rax
  const WCHAR *v11; // rdx
  UINT v12; // eax
  UINT v13; // eax
  MSIHANDLE *v14; // rax
  UINT v15; // eax
  UINT v16; // ebx
  _QWORD *v17; // rax
  UINT StringW; // eax
  __int64 v19; // rbx
  __int64 v20; // rdx
  __int64 v21; // rax
  _QWORD *v22; // rsi
  _QWORD *v23; // rdi
  _QWORD *v24; // rdx
  char found; // bl
  MSIHANDLE *v26; // rax
  UINT v27; // eax
  UINT v28; // eax
  unsigned __int64 v29; // rcx
  const unsigned __int8 *v30; // rdx
  unsigned __int64 appended; // rax
  __int64 v32; // rax
  _QWORD *v33; // rbx
  const WCHAR *v34; // rcx
  __int64 last_of; // rax
  __int64 v36; // rax
  MSIHANDLE *v37; // rax
  UINT v38; // eax
  __int64 v39; // rax
  __int64 v40; // rsi
  _QWORD *v41; // rdi
  _QWORD *i; // rbx
  __int64 v43; // rdx
  unsigned int lpOutPathBuffer; // [rsp+28h] [rbp-E0h]
  MSIHANDLE hRecord; // [rsp+38h] [rbp-D0h] BYREF
  MSIHANDLE v47; // [rsp+3Ch] [rbp-CCh] BYREF
  MSIHANDLE hDatabase[2]; // [rsp+40h] [rbp-C8h] BYREF
  __int64 pcchOutPathBuffer; // [rsp+48h] [rbp-C0h] BYREF
  DWORD pcchValueBuf[2]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 *v51; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v52; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD *v53; // [rsp+70h] [rbp-98h]
  __int64 v54; // [rsp+78h] [rbp-90h]
  __int64 v55; // [rsp+80h] [rbp-88h] BYREF
  __int128 v56; // [rsp+88h] [rbp-80h]
  __int64 v57; // [rsp+98h] [rbp-70h]
  __int64 v58; // [rsp+A0h] [rbp-68h]
  int v59; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD v60[2]; // [rsp+B0h] [rbp-58h] BYREF
  __int64 v61; // [rsp+C0h] [rbp-48h] BYREF
  __int128 v62; // [rsp+C8h] [rbp-40h]
  __int64 v63; // [rsp+D8h] [rbp-30h]
  __int64 v64; // [rsp+E0h] [rbp-28h]
  __int64 v65; // [rsp+E8h] [rbp-20h]
  char v66[16]; // [rsp+F0h] [rbp-18h] BYREF
  char v67[16]; // [rsp+100h] [rbp-8h] BYREF
  char v68[16]; // [rsp+110h] [rbp+8h] BYREF
  char v69[16]; // [rsp+120h] [rbp+18h] BYREF
  unsigned __int8 *v70[2]; // [rsp+130h] [rbp+28h] BYREF
  __int64 v71; // [rsp+140h] [rbp+38h]
  unsigned __int64 v72; // [rsp+148h] [rbp+40h]
  _BYTE v73[16]; // [rsp+150h] [rbp+48h] BYREF
  __int64 v74; // [rsp+160h] [rbp+58h]
  _BYTE Src[16]; // [rsp+170h] [rbp+68h] BYREF
  __int64 v76; // [rsp+180h] [rbp+78h]
  _BYTE v77[32]; // [rsp+190h] [rbp+88h] BYREF
  LPCWSTR szQuery[4]; // [rsp+1B0h] [rbp+A8h] BYREF
  char v79[8]; // [rsp+1D0h] [rbp+C8h] BYREF
  _BYTE v80[32]; // [rsp+1D8h] [rbp+D0h] BYREF
  WCHAR szComponentCode[40]; // [rsp+1F8h] [rbp+F0h] BYREF
  WCHAR OutPathBuffer[264]; // [rsp+248h] [rbp+140h] BYREF
  WCHAR szValueBuf[264]; // [rsp+458h] [rbp+350h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6B0h] [rbp+5A8h]

  v65 = -2;
  v60[0] = 0;
  v60[1] = 0;
  std::list<std::wstring>::_Alloc_sentinel_and_proxy(v60);
  v61 = 0;
  v62 = 0;
  v63 = 7;
  v64 = 8;
  v59 = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(
    &v61,
    16,
    v60[0]);
  std::set<std::wstring>::set<std::wstring>(&v51);
  hDatabase[0] = 0;
  v8 = (MSIHANDLE *)PMSIHANDLE::operator&(hDatabase);
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(const WCHAR **)a3;
  v9 = MsiOpenDatabaseW(a3, 0, v8);
  if ( v9 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x328,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
      (const char *)v9,
      lpOutPathBuffer);
  std::wstring::wstring(
    szQuery,
    L"SELECT `FileName`,`ComponentId` FROM `File`,`Component` WHERE `File`.`Component_`=`Component`.`Component`");
  v47 = 0;
  v10 = (MSIHANDLE *)PMSIHANDLE::operator&(&v47);
  v11 = (const WCHAR *)szQuery;
  if ( szQuery[3] > (LPCWSTR)7 )
    v11 = szQuery[0];
  v12 = MsiDatabaseOpenViewW(hDatabase[0], v11, v10);
  if ( v12 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x32F,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
      (const char *)v12,
      lpOutPathBuffer);
  v13 = MsiViewExecute(v47, 0);
  if ( v13 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x332,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
      (const char *)v13,
      lpOutPathBuffer);
  hRecord = 0;
  v14 = (MSIHANDLE *)PMSIHANDLE::operator&(&hRecord);
  v15 = MsiViewFetch(v47, v14);
  v16 = v15;
  if ( v15 && v15 != 259 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x339,
      (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
      (const char *)v15,
      lpOutPathBuffer);
  LODWORD(v52) = 0;
  v53 = 0;
  v54 = 0;
  v17 = operator new(0x58u);
  *v17 = v17;
  v17[1] = v17;
  v53 = v17;
  v55 = 0;
  v56 = 0;
  v57 = 7;
  v58 = 8;
  LODWORD(v52) = 1065353216;
  std::_Hash_vec_std::allocator_std::_List_unchecked_iterator_std::_List_val_std::_List_simple_types_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___MsiApplication::QueryMsiDatabaseForFiles2_::_2_::CachedComponentResult___________::_Assign_grow(
    &v55,
    16,
    v17);
  while ( v16 != 259 )
  {
    memset_0(szValueBuf, 0, 0x208u);
    pcchValueBuf[0] = 260;
    StringW = MsiRecordGetStringW(hRecord, 1u, szValueBuf, pcchValueBuf);
    if ( StringW && StringW != 259 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x352,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
        (const char *)StringW,
        lpOutPathBuffer);
    std::wstring::wstring(v73, szValueBuf);
    v19 = std::wstring::find(v73, 124);
    if ( v19 != -1 )
    {
      v20 = Utility::TrimSpace(v73);
      std::wstring::operator=(v73, v20);
      v21 = std::wstring::substr(v73, v77, v19 + 1, v74);
      std::wstring::operator=(v73, v21);
      std::wstring::~wstring(v77);
    }
    v22 = *(_QWORD **)(a4 + 8);
    v23 = *(_QWORD **)a4;
    if ( *(_QWORD **)a4 != v22 )
    {
      while ( 1 )
      {
        v24 = v23[3] <= 7u ? v23 : (_QWORD *)*v23;
        std::wstring::wstring(Src, v24);
        found = Utility::FoundSubstring(Src, v73);
        std::wstring::~wstring(Src);
        if ( found )
          break;
        v23 += 4;
        if ( v23 == v22 )
        {
          v26 = (MSIHANDLE *)PMSIHANDLE::operator&(&hRecord);
          v27 = MsiViewFetch(v47, v26);
          v16 = v27;
          if ( v27 && v27 != 259 )
            wil::details::in1diag3::_Throw_Win32(
              retaddr,
              (void *)0x374,
              (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
              (const char *)v27,
              lpOutPathBuffer);
          goto LABEL_51;
        }
      }
    }
    memset_0(szComponentCode, 0, 0x4Eu);
    pcchValueBuf[1] = 39;
    v28 = MsiRecordGetStringW(hRecord, 2u, szComponentCode, &pcchValueBuf[1]);
    if ( v28 && v28 != 259 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x380,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
        (const char *)v28,
        lpOutPathBuffer);
    std::wstring::wstring(v70, szComponentCode);
    v30 = (const unsigned __int8 *)v70;
    if ( v72 > 7 )
      v30 = v70[0];
    appended = std::_Fnv1a_append_bytes(v29, v30, 2 * v71);
    v32 = std::_Hash_std::_Umap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____MsiApplication::QueryMsiDatabaseForFiles2_::_2_::CachedComponentResult_std::_Uhash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___MsiApplication::QueryMsiDatabaseForFiles2_::_2_::CachedComponentResult____0___::_Find_last_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____(
            &v52,
            v66,
            v70,
            appended);
    v33 = v53;
    if ( *(_QWORD *)(v32 + 8) )
      v33 = *(_QWORD **)(v32 + 8);
    if ( v33 == v53 )
    {
      memset_0(OutPathBuffer, 0, 0x208u);
      LODWORD(pcchOutPathBuffer) = 260;
      if ( *(_QWORD *)(a2 + 24) <= 7u )
        v34 = (const WCHAR *)a2;
      else
        v34 = *(const WCHAR **)a2;
      MsiGetComponentPathExW(
        v34,
        szComponentCode,
        L"s-1-1-0",
        MSIINSTALLCONTEXT_ALL,
        OutPathBuffer,
        (LPDWORD)&pcchOutPathBuffer);
      v79[0] = 0;
      std::wstring::wstring(v80);
      if ( OutPathBuffer[0] )
      {
        if ( (unsigned int)_o_isdigit(OutPathBuffer[0]) )
        {
          v79[0] = 1;
        }
        else
        {
          std::wstring::wstring(v77, OutPathBuffer);
          Utility::GetDirectoryFromPath(Src, v77);
          std::wstring::~wstring(v77);
          if ( v76 )
          {
            last_of = std::wstring::find_last_of(Src, 92);
            if ( last_of != v76 )
              std::wstring::_Append<unsigned short>(Src);
            std::wstring::operator=(v80, Src);
          }
          std::wstring::~wstring(Src);
        }
      }
      v33 = *(_QWORD **)std::_Hash_std::_Umap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____MsiApplication::QueryMsiDatabaseForFiles2_::_2_::CachedComponentResult_std::_Uhash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___MsiApplication::QueryMsiDatabaseForFiles2_::_2_::CachedComponentResult____0___::emplace_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____MsiApplication::QueryMsiDatabaseForFiles2_::_2_::CachedComponentResult_(
                          &v52,
                          v67,
                          v70,
                          v79);
      std::wstring::~wstring(v80);
    }
    if ( *((_BYTE *)v33 + 48) )
    {
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring &>(
        &v51,
        v68,
        v73);
    }
    else if ( v33[9] && v74 )
    {
      std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(
        &v59,
        v69,
        v33 + 7);
      v36 = std::operator+<unsigned short>(v77, v33 + 7, v73);
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(a5, v36);
      std::wstring::~wstring(v77);
    }
    v37 = (MSIHANDLE *)PMSIHANDLE::operator&(&hRecord);
    v38 = MsiViewFetch(v47, v37);
    v16 = v38;
    if ( v38 && v38 != 259 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x3C9,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\msiapplication.cpp",
        (const char *)v38,
        lpOutPathBuffer);
    std::wstring::~wstring(v70);
LABEL_51:
    std::wstring::~wstring(v73);
  }
  v39 = *v51;
  pcchOutPathBuffer = *v51;
  while ( !*(_BYTE *)(v39 + 25) )
  {
    v40 = v39 + 32;
    v41 = (_QWORD *)v60[0];
    for ( i = *(_QWORD **)v60[0]; i != v41; i = (_QWORD *)*i )
    {
      v43 = std::operator+<unsigned short>(v77, i + 2, v40);
      Utility::VerifyAndNormalizeFilePath(v70, v43);
      std::wstring::~wstring(v77);
      if ( v71 )
      {
        AslLogCallPrintf(
          3,
          (unsigned int)"MsiApplication::QueryMsiDatabaseForFiles2",
          982,
          (unsigned int)"Msi custom action installed file: %ws");
        std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(a5, v70);
        std::wstring::~wstring(v70);
        break;
      }
      std::wstring::~wstring(v70);
    }
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<File>>,std::_Iterator_base0>::operator++(&pcchOutPathBuffer);
    v39 = pcchOutPathBuffer;
  }
  std::_Hash_std::_Umap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____MsiApplication::QueryMsiDatabaseForFiles2_::_2_::CachedComponentResult_std::_Uhash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___MsiApplication::QueryMsiDatabaseForFiles2_::_2_::CachedComponentResult____0___::__Hash_std::_Umap_traits_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short_____MsiApplication::QueryMsiDatabaseForFiles2_::_2_::CachedComponentResult_std::_Uhash_compare_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____std::hash_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short______std::equal_to_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short________std::allocator_std::pair_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short____const___MsiApplication::QueryMsiDatabaseForFiles2_::_2_::CachedComponentResult____0___(&v52);
  PMSIHANDLE::~PMSIHANDLE((PMSIHANDLE *)&hRecord);
  PMSIHANDLE::~PMSIHANDLE((PMSIHANDLE *)&v47);
  std::wstring::~wstring(szQuery);
  PMSIHANDLE::~PMSIHANDLE((PMSIHANDLE *)hDatabase);
  std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_head<std::allocator<std::_Tree_node<std::wstring,void *>>>(
    &v51,
    &v51);
  return std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(&v59);
}

```

## disassembly

```asm
0x18010f720  mov     rax, rsp
0x18010f723  push    rbp
0x18010f724  push    rsi
0x18010f725  push    rdi
0x18010f726  push    r12
0x18010f728  push    r13
0x18010f72a  push    r14
0x18010f72c  push    r15
0x18010f72e  lea     rbp, [rax-5A8h]
0x18010f735  sub     rsp, 670h
0x18010f73c  mov     [rbp+5A0h+var_5C0], 0FFFFFFFFFFFFFFFEh
0x18010f744  mov     [rax+8], rbx
0x18010f748  mov     rax, cs:__security_cookie
0x18010f74f  xor     rax, rsp
0x18010f752  mov     [rbp+5A0h+var_40], rax
0x18010f759  mov     r15, r9
0x18010f75c  mov     rbx, r8
0x18010f75f  mov     r14, rdx
0x18010f762  mov     r12, [rbp+5A0h+arg_20]
0x18010f769  mov     [rbp+5A0h+var_600], 0
0x18010f770  xor     r13d, r13d
0x18010f773  mov     [rbp+5A0h+var_5F8], r13
0x18010f777  mov     [rbp+5A0h+var_5F0], r13
0x18010f77b  lea     rcx, [rbp+5A0h+var_5F8]
0x18010f77f  call    ?_Alloc_sentinel_and_proxy@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::list<std::wstring>::_Alloc_sentinel_and_proxy(void)
0x18010f784  nop
0x18010f785  mov     [rbp+5A0h+var_5E8], r13
0x18010f789  xorps   xmm0, xmm0
0x18010f78c  movdqa  [rbp+5A0h+var_5E0], xmm0
0x18010f791  lea     esi, [r13+7]
0x18010f795  mov     [rbp+5A0h+var_5D0], rsi
0x18010f799  mov     [rbp+5A0h+var_5C8], 8
0x18010f7a1  mov     [rbp+5A0h+var_600], 3F800000h
0x18010f7a8  mov     r8, [rbp+5A0h+var_5F8]
0x18010f7ac  lea     edx, [rsi+9]
0x18010f7af  lea     rcx, [rbp+5A0h+var_5E8]
0x18010f7b3  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>)
0x18010f7b8  nop
0x18010f7b9  lea     rcx, [rsp+6A0h+var_650]
0x18010f7be  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x18010f7c3  nop
0x18010f7c4  mov     [rsp+6A0h+hDatabase], r13d
0x18010f7c9  lea     rcx, [rsp+6A0h+hDatabase]
0x18010f7ce  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x18010f7d3  cmp     [rbx+18h], rsi
0x18010f7d7  jbe     short loc_18010F7DC
0x18010f7d9  mov     rbx, [rbx]
0x18010f7dc  mov     r8, rax; phDatabase
0x18010f7df  xor     edx, edx; szPersist
0x18010f7e1  mov     rcx, rbx; szDatabasePath
0x18010f7e4  call    cs:__imp_MsiOpenDatabaseW
0x18010f7ea  mov     rcx, [rbp+5A8h]; this
0x18010f7f1  test    eax, eax
0x18010f7f3  jnz     loc_18010FE1F
0x18010f7f9  lea     rdx, aSelectFilename; "SELECT `FileName`,`ComponentId` FROM `F"...
0x18010f800  lea     rcx, [rbp+5A0h+szQuery]
0x18010f807  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010f80c  nop
0x18010f80d  mov     [rsp+6A0h+var_66C], r13d
0x18010f812  lea     rcx, [rsp+6A0h+var_66C]
0x18010f817  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x18010f81c  lea     rdx, [rbp+5A0h+szQuery]
0x18010f823  cmp     [rbp+5A0h+var_4E0], rsi
0x18010f82a  cmova   rdx, [rbp+5A0h+szQuery]; szQuery
0x18010f832  mov     r8, rax; phView
0x18010f835  mov     ecx, [rsp+6A0h+hDatabase]; hDatabase
0x18010f839  call    cs:__imp_MsiDatabaseOpenViewW
0x18010f83f  mov     rcx, [rbp+5A8h]; this
0x18010f846  test    eax, eax
0x18010f848  jnz     loc_18010FE34
0x18010f84e  xor     edx, edx; hRecord
0x18010f850  mov     ecx, [rsp+6A0h+var_66C]; hView
0x18010f854  call    cs:__imp_MsiViewExecute
0x18010f85a  mov     rcx, [rbp+5A8h]; this
0x18010f861  test    eax, eax
0x18010f863  jnz     loc_18010FE49
0x18010f869  mov     [rsp+6A0h+hRecord], r13d
0x18010f86e  lea     rcx, [rsp+6A0h+hRecord]
0x18010f873  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x18010f878  mov     rdx, rax; phRecord
0x18010f87b  mov     ecx, [rsp+6A0h+var_66C]; hView
0x18010f87f  call    cs:__imp_MsiViewFetch
0x18010f885  mov     ebx, eax
0x18010f887  mov     edi, 103h
0x18010f88c  test    eax, eax
0x18010f88e  jz      short loc_18010F898
0x18010f890  cmp     eax, edi
0x18010f892  jnz     loc_18010FE5E
0x18010f898  mov     dword ptr [rsp+6A0h+var_640], 0
0x18010f8a0  mov     [rsp+6A0h+var_638], r13
0x18010f8a5  mov     [rsp+6A0h+var_630], r13
0x18010f8aa  mov     ecx, 58h ; 'X'; Size
0x18010f8af  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18010f8b4  mov     [rax], rax
0x18010f8b7  mov     [rax+8], rax
0x18010f8bb  mov     [rsp+6A0h+var_638], rax
0x18010f8c0  mov     [rsp+6A0h+var_628], r13
0x18010f8c5  xorps   xmm0, xmm0
0x18010f8c8  movdqa  [rbp+5A0h+var_620], xmm0
0x18010f8cd  mov     [rbp+5A0h+var_610], rsi
0x18010f8d1  mov     [rbp+5A0h+var_608], 8
0x18010f8d9  mov     dword ptr [rsp+6A0h+var_640], 3F800000h
0x18010f8e1  mov     r8, rax
0x18010f8e4  mov     edx, 10h
0x18010f8e9  lea     rcx, [rsp+6A0h+var_628]
0x18010f8ee  call    std___Hash_vec_std__allocator_std___List_unchecked_iterator_std___List_val_std___List_simple_types_std__pair_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____const___MsiApplication__QueryMsiDatabaseForFiles2____2___CachedComponentResult______________Assign_grow
0x18010f8f3  nop
0x18010f8f4  jmp     loc_18010FC9C
0x18010f8f9  xor     edx, edx; Val
0x18010f8fb  mov     r8d, 208h; Size
0x18010f901  lea     rcx, [rbp+5A0h+szValueBuf]; void *
0x18010f908  call    memset_0
0x18010f90d  mov     [rsp+6A0h+pcchValueBuf], 104h
0x18010f915  lea     r9, [rsp+6A0h+pcchValueBuf]; pcchValueBuf
0x18010f91a  lea     r8, [rbp+5A0h+szValueBuf]; szValueBuf
0x18010f921  mov     edx, 1; iField
0x18010f926  mov     ecx, [rsp+6A0h+hRecord]; hRecord
0x18010f92a  call    cs:__imp_MsiRecordGetStringW
0x18010f930  test    eax, eax
0x18010f932  jz      short loc_18010F93C
0x18010f934  cmp     eax, edi
0x18010f936  jnz     loc_18010FE7A
0x18010f93c  lea     rdx, [rbp+5A0h+szValueBuf]
0x18010f943  lea     rcx, [rbp+5A0h+var_558]
0x18010f947  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010f94c  nop
0x18010f94d  mov     edx, 7Ch ; '|'
0x18010f952  lea     rcx, [rbp+5A0h+var_558]
0x18010f956  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find(ushort,unsigned __int64)
0x18010f95b  mov     rbx, rax
0x18010f95e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18010f962  jz      short loc_18010F9A9
0x18010f964  lea     rcx, [rbp+5A0h+var_558]
0x18010f968  call    ?TrimSpace@Utility@@SAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; Utility::TrimSpace(std::wstring &)
0x18010f96d  mov     rdx, rax
0x18010f970  lea     rcx, [rbp+5A0h+var_558]
0x18010f974  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18010f979  lea     r8, [rbx+1]
0x18010f97d  mov     r9, [rbp+5A0h+var_548]
0x18010f981  lea     rdx, [rbp+5A0h+var_518]
0x18010f988  lea     rcx, [rbp+5A0h+var_558]
0x18010f98c  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18010f991  mov     rdx, rax
0x18010f994  lea     rcx, [rbp+5A0h+var_558]
0x18010f998  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18010f99d  lea     rcx, [rbp+5A0h+var_518]
0x18010f9a4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18010f9a9  mov     rsi, [r15+8]
0x18010f9ad  mov     rdi, [r15]
0x18010f9b0  cmp     rdi, rsi
0x18010f9b3  jz      short loc_18010FA24
0x18010f9b5  cmp     qword ptr [rdi+18h], 7
0x18010f9ba  jbe     short loc_18010F9C1
0x18010f9bc  mov     rdx, [rdi]
0x18010f9bf  jmp     short loc_18010F9C4
0x18010f9c1  mov     rdx, rdi
0x18010f9c4  lea     rcx, [rbp+5A0h+Src]
0x18010f9c8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010f9cd  nop
0x18010f9ce  lea     rdx, [rbp+5A0h+var_558]
0x18010f9d2  lea     rcx, [rbp+5A0h+Src]
0x18010f9d6  call    ?FoundSubstring@Utility@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Utility::FoundSubstring(std::wstring const &,std::wstring const &)
0x18010f9db  mov     bl, al
0x18010f9dd  lea     rcx, [rbp+5A0h+Src]
0x18010f9e1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18010f9e6  test    bl, bl
0x18010f9e8  jnz     short loc_18010FA24
0x18010f9ea  add     rdi, 20h ; ' '
0x18010f9ee  cmp     rdi, rsi
0x18010f9f1  jnz     short loc_18010F9B5
0x18010f9f3  lea     rcx, [rsp+6A0h+hRecord]
0x18010f9f8  call    ??IPMSIHANDLE@@QEAAPEAKXZ; PMSIHANDLE::operator&(void)
0x18010f9fd  mov     rdx, rax; phRecord
0x18010fa00  mov     ecx, [rsp+6A0h+var_66C]; hView
0x18010fa04  call    cs:__imp_MsiViewFetch
0x18010fa0a  mov     ebx, eax
0x18010fa0c  test    eax, eax
0x18010fa0e  jz      loc_18010FC8E
0x18010fa14  cmp     eax, 103h
0x18010fa19  jnz     loc_18010FE03
0x18010fa1f  jmp     loc_18010FC8E
0x18010fa24  xor     edx, edx; Val
0x18010fa26  lea     r8d, [rdx+4Eh]; Size
0x18010fa2a  lea     rcx, [rbp+5A0h+szComponentCode]; void *
0x18010fa31  call    memset_0
0x18010fa36  mov     [rsp+6A0h+pcchValueBuf+4], 27h ; '''
0x18010fa3e  lea     r9, [rsp+6A0h+pcchValueBuf+4]; pcchValueBuf
0x18010fa43  lea     r8, [rbp+5A0h+szComponentCode]; szValueBuf
0x18010fa4a  mov     edx, 2; iField
0x18010fa4f  mov     ecx, [rsp+6A0h+hRecord]; hRecord
0x18010fa53  call    cs:__imp_MsiRecordGetStringW
0x18010fa59  test    eax, eax
0x18010fa5b  jz      short loc_18010FA68
0x18010fa5d  cmp     eax, 103h
0x18010fa62  jnz     loc_18010FE96
0x18010fa68  lea     rdx, [rbp+5A0h+szComponentCode]
0x18010fa6f  lea     rcx, [rbp+5A0h+var_578]
0x18010fa73  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010fa78  nop
0x18010fa79  mov     r8, [rbp+5A0h+var_568]
0x18010fa7d  lea     rdx, [rbp+5A0h+var_578]
0x18010fa81  mov     esi, 7
0x18010fa86  cmp     [rbp+5A0h+var_560], rsi
0x18010fa8a  cmova   rdx, [rbp+5A0h+var_578]; unsigned __int8 *
0x18010fa8f  add     r8, r8; unsigned __int64
0x18010fa92  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x18010fa97  mov     r9, rax
0x18010fa9a  lea     r8, [rbp+5A0h+var_578]
0x18010fa9e  lea     rdx, [rbp+5A0h+var_5B8]
0x18010faa2  lea     rcx, [rsp+6A0h+var_640]
0x18010faa7  call    std___Hash_std___Umap_traits_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short_____MsiApplication__QueryMsiDatabaseForFiles2____2___CachedComponentResult_std___Uhash_compare_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____std__hash_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short______std__equal_to_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short________std__allocator_std__pair_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____const___MsiApplication__QueryMsiDatabaseForFiles2____2___CachedComponentResult____0______Find_last_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short_____
0x18010faac  mov     rbx, [rsp+6A0h+var_638]
0x18010fab1  cmp     [rax+8], r13
0x18010fab5  cmovnz  rbx, [rax+8]
0x18010faba  cmp     rbx, [rsp+6A0h+var_638]
0x18010fabf  jnz     loc_18010FBF8
0x18010fac5  xor     edx, edx; Val
0x18010fac7  mov     r8d, 208h; Size
0x18010facd  lea     rcx, [rbp+5A0h+OutPathBuffer]; void *
0x18010fad4  call    memset_0
0x18010fad9  mov     [rsp+6A0h+var_660], 104h
0x18010fae1  cmp     [r14+18h], rsi
0x18010fae5  jbe     short loc_18010FAEC
0x18010fae7  mov     rcx, [r14]
0x18010faea  jmp     short loc_18010FAEF
0x18010faec  mov     rcx, r14; szProductCode
0x18010faef  lea     rax, [rsp+6A0h+var_660]
0x18010faf4  mov     [rsp+6A0h+pcchOutPathBuffer], rax; pcchOutPathBuffer
0x18010faf9  lea     rax, [rbp+5A0h+OutPathBuffer]
0x18010fb00  mov     [rsp+6A0h+lpOutPathBuffer], rax; unsigned int
0x18010fb05  mov     r9d, esi; dwContext
0x18010fb08  lea     r8, szUserSid; "s-1-1-0"
0x18010fb0f  lea     rdx, [rbp+5A0h+szComponentCode]; szComponentCode
0x18010fb16  call    cs:__imp_MsiGetComponentPathExW
0x18010fb1c  mov     [rbp+5A0h+var_4D8], r13b
0x18010fb23  lea     rcx, [rbp+5A0h+var_4D0]
0x18010fb2a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18010fb2f  nop
0x18010fb30  movzx   eax, [rbp+5A0h+OutPathBuffer]
0x18010fb37  test    ax, ax
0x18010fb3a  jz      loc_18010FBD0
0x18010fb40  mov     ecx, eax
0x18010fb42  call    cs:__imp__o_isdigit
0x18010fb48  test    eax, eax
0x18010fb4a  jz      short loc_18010FB55
0x18010fb4c  mov     [rbp+5A0h+var_4D8], 1
0x18010fb53  jmp     short loc_18010FBD0
0x18010fb55  lea     rdx, [rbp+5A0h+OutPathBuffer]
0x18010fb5c  lea     rcx, [rbp+5A0h+var_518]
0x18010fb63  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18010fb68  nop
0x18010fb69  lea     rdx, [rbp+5A0h+var_518]
0x18010fb70  lea     rcx, [rbp+5A0h+Src]
0x18010fb74  call    ?GetDirectoryFromPath@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::GetDirectoryFromPath(std::wstring const &)
0x18010fb79  nop
0x18010fb7a  lea     rcx, [rbp+5A0h+var_518]
0x18010fb81  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18010fb86  cmp     [rbp+5A0h+var_528], r13
0x18010fb8a  jz      short loc_18010FBC7
0x18010fb8c  mov     edx, 5Ch ; '\'
0x18010fb91  lea     rcx, [rbp+5A0h+Src]
0x18010fb95  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find_last_of(ushort,unsigned __int64)
0x18010fb9a  cmp     rax, [rbp+5A0h+var_528]
0x18010fb9e  jz      short loc_18010FBB6
0x18010fba0  mov     r8d, 1
0x18010fba6  lea     rdx, SubBlock; "\\"
0x18010fbad  lea     rcx, [rbp+5A0h+Src]; Src
0x18010fbb1  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18010fbb6  lea     rdx, [rbp+5A0h+Src]
0x18010fbba  lea     rcx, [rbp+5A0h+var_4D0]
0x18010fbc1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18010fbc6  nop
0x18010fbc7  lea     rcx, [rbp+5A0h+Src]
0x18010fbcb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18010fbd0  lea     r9, [rbp+5A0h+var_4D8]
0x18010fbd7  lea     r8, [rbp+5A0h+var_578]
0x18010fbdb  lea     rdx, [rbp+5A0h+var_5A8]
0x18010fbdf  lea     rcx, [rsp+6A0h+var_640]
0x18010fbe4  call    std___Hash_std___Umap_traits_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short_____MsiApplication__QueryMsiDatabaseForFiles2____2___CachedComponentResult_std___Uhash_compare_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____std__hash_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short______std__equal_to_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short________std__allocator_std__pair_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short____const___MsiApplication__QueryMsiDatabaseForFiles2____2___CachedComponentResult____0_____emplace_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short_____MsiApplication__QueryMsiDatabaseForFiles2____2___CachedComponentResult_
0x18010fbe9  mov     rbx, [rax]
0x18010fbec  lea     rcx, [rbp+5A0h+var_4D0]
0x18010fbf3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18010fbf8  cmp     [rbx+30h], r13b
0x18010fbfc  jz      short loc_18010FC12
0x18010fbfe  lea     r8, [rbp+5A0h+var_558]
0x18010fc02  lea     rdx, [rbp+5A0h+var_598]
0x18010fc06  lea     rcx, [rsp+6A0h+var_650]
0x18010fc0b  call    ??$emplace@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::emplace<std::wstring &>(std::wstring &)
0x18010fc10  jmp     short loc_18010FC5C
0x18010fc12  cmp     [rbx+48h], r13
0x18010fc16  jz      short loc_18010FC5C
0x18010fc18  cmp     [rbp+5A0h+var_548], r13
0x18010fc1c  jz      short loc_18010FC5C
0x18010fc1e  lea     r8, [rbx+38h]
0x18010fc22  lea     rdx, [rbp+5A0h+var_588]
0x18010fc26  lea     rcx, [rbp+5A0h+var_600]
0x18010fc2a  call    ??$emplace@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring const &>(std::wstring const &)
0x18010fc2f  lea     r8, [rbp+5A0h+var_558]
0x18010fc33  lea     rdx, [rbx+38h]
0x18010fc37  lea     rcx, [rbp+5A0h+var_518]
  ... truncated ...
```
