# DataStoreReader::LoadMostRecentResultsGetStateGetDoc(WinSATData &,__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 &,IXMLDOMDocument2 * *)

- ea: `0x180003970`
- end: `0x18000401a`
- name: `?LoadMostRecentResultsGetStateGetDoc@DataStoreReader@@KAJAEAUWinSATData@@AEAW4__MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002@@PEAPEAUIXMLDOMDocument2@@@Z`
- size: `1706`
- prototype: `__int64 __fastcall(struct WinSATData *, enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180002690`

## callees

- `0x1800035cc`
- `0x180003640`
- `0x1800038ec`
- `0x180003970`
- `0x180004020`
- `0x180004048`
- `0x180004198`
- `0x1800043f0`
- `0x180004538`
- `0x180004990`
- `0x180004c60`
- `0x180007128`
- `0x180008490`
- `0x18000ba00`
- `0x18000d07c`
- `0x18000e490`
- `0x180011e70`
- `0x180011ee0`
- `0x180011fc0`
- `0x180012bf3`
- `0x180013e69`
- `0x18001ba74`
- `0x18001c41c`
- `0x18001f2e4`
- `0x18002c3e4`
- `0x18002fb50`
- `0x180033010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003d3a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003d49`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003d72`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003e25`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003ed5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003f36`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003f8f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003fb9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003fc8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003d3a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003d49`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003d72`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003e25`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003ed5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003f36`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003f8f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003fb9`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003fc8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003c28`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003ccc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003cfa`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003c28`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003ccc`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180003cfa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003bed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003c37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003bed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003c37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003c16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d0f`
- `SHELL32!SHGetFolderPathW` at `0x180003ab5`
- `SHELL32!SHGetFolderPathW` at `0x180003ab5`
- `KERNEL32!GetCurrentDirectoryW` at `0x180003c06`
- `KERNEL32!GetCurrentDirectoryW` at `0x180003c06`

## string_xrefs

- `0x180003b78`: `.WinSAT.xml`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall DataStoreReader::LoadMostRecentResultsGetStateGetDoc(
        struct WinSATData *a1,
        enum __MIDL___MIDL_itf_winsatcominterfacei_0000_0000_0002 *a2,
        struct IXMLDOMDocument2 **a3)
{
  struct IXMLDOMDocument2 *v5; // rax
  __int64 v6; // rbx
  struct IXMLDOMDocument2 *v7; // rax
  struct IXMLDOMDocument2 *v8; // rax
  _WORD *v9; // rax
  HRESULT v10; // ebx
  __int64 v12; // rbx
  __int64 v13; // rax
  struct IXMLDOMDocument2 *v14; // rax
  __int64 v15; // rax
  const wchar_t *i; // rax
  _QWORD *v17; // rbx
  __int64 v18; // r15
  _QWORD *v19; // rdi
  WCHAR *v20; // rdx
  WCHAR *v21; // rsi
  WCHAR *v22; // rax
  DWORD LastError; // r15d
  signed int v24; // eax
  __int64 v25; // rcx
  signed int v26; // esi
  bool v27; // zf
  void *v28; // rcx
  __int64 v29; // r8
  __int64 v30; // rcx
  __int64 v31; // rdx
  const unsigned __int16 *v32; // rcx
  int v33; // ebx
  __int64 v34; // rcx
  __int64 v35; // rcx
  int HistoryVersion; // esi
  struct IXMLDOMDocument2 *v37; // rbx
  void *v38; // rcx
  _QWORD *v39; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v40; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v41; // [rsp+48h] [rbp-B8h]
  unsigned int v42[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct IXMLDOMDocument2 *v43; // [rsp+58h] [rbp-A8h] BYREF
  char pExceptionObject; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v45; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v46; // [rsp+68h] [rbp-98h]
  void **v47; // [rsp+70h] [rbp-90h] BYREF
  __int16 v48; // [rsp+78h] [rbp-88h]
  __int64 v49; // [rsp+280h] [rbp+180h]
  __int64 v50; // [rsp+288h] [rbp+188h]
  __int64 v51; // [rsp+290h] [rbp+190h]
  __int64 v52; // [rsp+298h] [rbp+198h]
  __int64 v53; // [rsp+2A0h] [rbp+1A0h]
  void **v54; // [rsp+2A8h] [rbp+1A8h]
  __int128 v55; // [rsp+2B0h] [rbp+1B0h]
  __int128 v56; // [rsp+2C0h] [rbp+1C0h]
  __int128 *v57; // [rsp+2D0h] [rbp+1D0h]

  v46 = -2;
  if ( !a1 || !a2 )
    return 2147942487LL;
  memset_0(a1, 0, 0x1A0u);
  *a2 = WINSAT_ASSESSMENT_STATE_MIN;
  v5 = (struct IXMLDOMDocument2 *)operator new(0x28u);
  if ( !v5 )
    std::_Xbad_alloc();
  v43 = v5;
  v39 = (_QWORD *)mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
                    v5,
                    260);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::cow(&v39);
  v6 = (__int64)v39;
  if ( v39[1] < 0x104u )
  {
    v7 = (struct IXMLDOMDocument2 *)mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::operator new();
    v43 = v7;
    if ( v7 )
      v6 = mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
             v7,
             *(_QWORD *)(v6 + 24),
             *(_QWORD *)v6,
             260);
    else
      v6 = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v39);
    v39 = (_QWORD *)v6;
  }
  if ( *(_QWORD *)(v6 + 16) <= 1u )
  {
    v9 = *(_WORD **)(v6 + 24);
    if ( v9 )
    {
      *(_QWORD *)v6 = 0;
      *v9 = 0;
    }
  }
  else
  {
    v8 = (struct IXMLDOMDocument2 *)mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::operator new();
    v43 = v8;
    if ( v8 )
      v6 = mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(v8);
    else
      v6 = 0;
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v39);
    v39 = (_QWORD *)v6;
  }
  v10 = SHGetFolderPathW(0, 36, 0, 0, *(LPWSTR *)(v6 + 24));
  if ( v10 < 0 )
  {
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::clear(&v39);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v39);
    return (unsigned int)v10;
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::resize(&v39);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::ensure_trailing_slash(&v39);
  v12 = 0x10000;
  v13 = mlib::m_traits<unsigned short>::CStrlen(L"Performance\\WinSAT\\DataStore", 0x10000);
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::munge(
    &v39,
    0,
    *v39,
    L"Performance\\WinSAT\\DataStore",
    v13);
  v40 = 0;
  v41 = 0;
  v14 = (struct IXMLDOMDocument2 *)mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::operator new();
  v43 = v14;
  if ( v14 )
    v15 = mlib::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::mstring_buf<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
            v14,
            260);
  else
    v15 = 0;
  *(_QWORD *)v42 = v15;
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spf(
    v42,
    L"*%s.Assessment (%s)",
    L"Formal",
    L"*");
  for ( i = L".WinSAT.xml"; ; ++i )
  {
    if ( !v12 )
      throw (mlib::CStringTooBig *)&pExceptionObject;
    if ( !*i )
      break;
    --v12;
  }
  mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::munge(
    v42,
    0,
    **(_QWORD **)v42,
    L".WinSAT.xml",
    i - L".WinSAT.xml");
  v17 = *(_QWORD **)v42;
  v18 = *(_QWORD *)(*(_QWORD *)v42 + 24LL);
  v19 = v39;
  v20 = (WCHAR *)v39[3];
  v21 = 0;
  if ( !v20 || !*v20 )
  {
    v22 = (WCHAR *)operator new[](0x208u);
    v21 = v22;
    if ( !v22 )
    {
      SetLastError(8u);
      goto LABEL_37;
    }
    if ( !GetCurrentDirectoryW(0x104u, v22) )
    {
      LastError = GetLastError();
      operator delete[](v21);
      SetLastError(LastError);
      goto LABEL_36;
    }
    v20 = v21;
  }
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = -1;
  v53 = 0;
  v54 = &mlib::FSpecList<unsigned short>::`vftable';
  v55 = 0;
  v56 = 0;
  v48 = 0;
  v47 = &mlib::FileFinder<unsigned short>::`vftable';
  v57 = &v40;
  LastError = mlib::TraverseDirT<unsigned short>::traverse_dir(&v47, v20, v18);
  if ( v21 )
    operator delete[](v21);
  v47 = &mlib::TraverseDirT<unsigned short>::`vftable';
  v54 = &mlib::FSpecList<unsigned short>::`vftable';
  operator delete[](*((void **)&v56 + 1));
LABEL_36:
  if ( !LastError )
  {
    std::_Sort<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> *,__int64,bool (*)(mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const &,mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>> const &)>(
      v40,
      *((_QWORD *)&v40 + 1),
      (__int64)(*((_QWORD *)&v40 + 1) - v40) >> 3);
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v42);
    goto LABEL_48;
  }
LABEL_37:
  v24 = GetLastError();
  v26 = v24;
  if ( v24 > 0 )
    v26 = (unsigned __int16)v24 | 0x80070000;
  v27 = v17[2]-- == 1;
  if ( v27 )
  {
    v28 = (void *)v17[3];
    if ( v28 )
      operator delete(v28);
    operator delete(v17);
  }
  if ( v26 < 0 )
  {
    if ( (_QWORD)v40 )
    {
      std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
        v25,
        v40,
        *((_QWORD *)&v40 + 1));
      operator delete((void *)v40);
      v40 = 0;
      v41 = 0;
    }
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v39);
    return (unsigned int)v26;
  }
LABEL_48:
  v29 = *((_QWORD *)&v40 + 1);
  v30 = v40;
  if ( *((_QWORD *)&v40 + 1) == (_QWORD)v40 )
  {
    *a2 = WINSAT_ASSESSMENT_STATE_NOT_AVAILABLE;
    if ( v30 )
    {
      v31 = v30;
LABEL_60:
      std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
        v30,
        v31,
        v29);
      operator delete((void *)v40);
      v41 = 0;
      v40 = 0;
      goto LABEL_66;
    }
    goto LABEL_66;
  }
  v43 = 0;
  v33 = DataStoreReader::LoadRecentResultsFromFile(v40, a1, &v43);
  if ( v33 >= 0 )
  {
    v42[0] = 0;
    v45 = 0;
    HistoryVersion = DataStoreReader::GetHistoryVersion(v32, v42);
    v37 = v43;
    if ( HistoryVersion >= 0 )
    {
      HistoryVersion = DataStoreReader::GetHistoryValueFromDocument(v43, &v45);
      if ( HistoryVersion >= 0 )
      {
        if ( v42[0] == v45 )
        {
          *a2 = WINSAT_ASSESSMENT_STATE_VALID;
          if ( v37 )
            ((void (__fastcall *)(struct IXMLDOMDocument2 *))v37->lpVtbl->Release)(v37);
          if ( (_QWORD)v40 )
          {
            std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
              v35,
              v40,
              *((_QWORD *)&v40 + 1));
            operator delete((void *)v40);
            v40 = 0;
            v41 = 0;
          }
          goto LABEL_66;
        }
        memset_0(a1, 0, 0x1A0u);
        *a2 = WINSAT_ASSESSMENT_STATE_NOT_AVAILABLE;
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
        v31 = v40;
        if ( (_QWORD)v40 )
        {
          v29 = *((_QWORD *)&v40 + 1);
          goto LABEL_60;
        }
LABEL_66:
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v39);
        return 0;
      }
    }
    if ( v37 )
      ((void (__fastcall *)(struct IXMLDOMDocument2 *))v37->lpVtbl->Release)(v37);
    if ( (_QWORD)v40 )
    {
      std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
        v35,
        v40,
        *((_QWORD *)&v40 + 1));
      operator delete((void *)v40);
      v40 = 0;
      v41 = 0;
    }
    v27 = v19[2]-- == 1;
    if ( v27 )
    {
      v38 = (void *)v19[3];
      if ( v38 )
        operator delete(v38);
      operator delete(v19);
    }
    return (unsigned int)HistoryVersion;
  }
  else
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
    if ( (_QWORD)v40 )
    {
      std::vector<mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>>::_Destroy(
        v34,
        v40,
        *((_QWORD *)&v40 + 1));
      operator delete((void *)v40);
      v40 = 0;
      v41 = 0;
    }
    mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v39);
    return (unsigned int)v33;
  }
}

```

## disassembly

```asm
0x180003970  push    rbp
0x180003972  push    rsi
0x180003973  push    rdi
0x180003974  push    r12
0x180003976  push    r13
0x180003978  push    r14
0x18000397a  push    r15
0x18000397c  lea     rbp, [rsp-1F0h]
0x180003984  sub     rsp, 2F0h
0x18000398b  mov     [rsp+320h+var_2B8], 0FFFFFFFFFFFFFFFEh
0x180003994  mov     [rsp+320h+arg_10], rbx
0x18000399c  mov     rax, cs:__security_cookie
0x1800039a3  xor     rax, rsp
0x1800039a6  mov     [rbp+220h+var_40], rax
0x1800039ad  mov     r12, rdx
0x1800039b0  mov     r14, rcx
0x1800039b3  test    rcx, rcx
0x1800039b6  jz      loc_180003FEA
0x1800039bc  test    rdx, rdx
0x1800039bf  jz      loc_180003FEA
0x1800039c5  xor     edx, edx; Val
0x1800039c7  mov     r8d, 1A0h; Size
0x1800039cd  call    memset_0
0x1800039d2  xor     r13d, r13d
0x1800039d5  mov     [r12], r13d
0x1800039d9  lea     ecx, [r13+28h]; Size
0x1800039dd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800039e2  test    rax, rax
0x1800039e5  jnz     short loc_1800039ED
0x1800039e7  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800039ed  mov     [rsp+320h+var_2C8], rax
0x1800039f2  mov     edx, 104h
0x1800039f7  mov     rcx, rax
0x1800039fa  call    ??0?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAA@_KAEBV?$allocator@G@std@@@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64,std::allocator<ushort> const &)
0x1800039ff  nop
0x180003a00  mov     [rsp+320h+var_2F0], rax
0x180003a05  lea     rcx, [rsp+320h+var_2F0]
0x180003a0a  call    ?cow@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::cow(void)
0x180003a0f  mov     rbx, [rsp+320h+var_2F0]
0x180003a14  cmp     qword ptr [rbx+8], 104h
0x180003a1c  jnb     short loc_180003A59
0x180003a1e  call    ??2?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@CAPEAX_K@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::operator new(unsigned __int64)
0x180003a23  mov     [rsp+320h+var_2C8], rax
0x180003a28  test    rax, rax
0x180003a2b  jz      short loc_180003A47
0x180003a2d  mov     r9d, 104h
0x180003a33  mov     r8, [rbx]
0x180003a36  mov     rdx, [rbx+18h]
0x180003a3a  mov     rcx, rax
0x180003a3d  call    ??0?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAA@PEBG_K1AEBV?$allocator@G@std@@@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *,unsigned __int64,unsigned __int64,std::allocator<ushort> const &)
0x180003a42  mov     rbx, rax
0x180003a45  jmp     short loc_180003A4A
0x180003a47  mov     rbx, r13
0x180003a4a  lea     rcx, [rsp+320h+var_2F0]
0x180003a4f  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180003a54  mov     [rsp+320h+var_2F0], rbx
0x180003a59  cmp     qword ptr [rbx+10h], 1
0x180003a5e  jbe     short loc_180003A90
0x180003a60  call    ??2?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@CAPEAX_K@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::operator new(unsigned __int64)
0x180003a65  mov     [rsp+320h+var_2C8], rax
0x180003a6a  test    rax, rax
0x180003a6d  jz      short loc_180003A7C
0x180003a6f  mov     rcx, rax
0x180003a72  call    ??0?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAA@AEBV?$allocator@G@std@@@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(std::allocator<ushort> const &)
0x180003a77  mov     rbx, rax
0x180003a7a  jmp     short loc_180003A7F
0x180003a7c  mov     rbx, r13
0x180003a7f  lea     rcx, [rsp+320h+var_2F0]
0x180003a84  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180003a89  mov     [rsp+320h+var_2F0], rbx
0x180003a8e  jmp     short loc_180003AA0
0x180003a90  mov     rax, [rbx+18h]
0x180003a94  test    rax, rax
0x180003a97  jz      short loc_180003AA0
0x180003a99  mov     [rbx], r13
0x180003a9c  mov     [rax], r13w
0x180003aa0  mov     rax, [rbx+18h]
0x180003aa4  mov     [rsp+320h+pszPath], rax; pszPath
0x180003aa9  xor     r9d, r9d; dwFlags
0x180003aac  xor     r8d, r8d; hToken
0x180003aaf  lea     edx, [r9+24h]; csidl
0x180003ab3  xor     ecx, ecx; hwnd
0x180003ab5  call    cs:__imp_SHGetFolderPathW
0x180003abc  nop     dword ptr [rax+rax+00h]
0x180003ac1  mov     ebx, eax
0x180003ac3  lea     rcx, [rsp+320h+var_2F0]
0x180003ac8  test    eax, eax
0x180003aca  jns     short loc_180003AE3
0x180003acc  call    ?clear@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::clear(void)
0x180003ad1  nop
0x180003ad2  lea     rcx, [rsp+320h+var_2F0]
0x180003ad7  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180003adc  mov     eax, ebx
0x180003ade  jmp     loc_180003FEF
0x180003ae3  call    ?resize@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::resize(void)
0x180003ae8  lea     rcx, [rsp+320h+var_2F0]
0x180003aed  call    ?ensure_trailing_slash@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::ensure_trailing_slash(void)
0x180003af2  mov     ebx, 10000h
0x180003af7  mov     edx, ebx
0x180003af9  lea     rcx, aPerformanceWin; "Performance\\WinSAT\\DataStore"
0x180003b00  call    ?CStrlen@?$m_traits@G@mlib@@SA_KPEBG_K@Z; mlib::m_traits<ushort>::CStrlen(ushort const *,unsigned __int64)
0x180003b05  mov     rcx, [rsp+320h+var_2F0]
0x180003b0a  mov     [rsp+320h+pszPath], rax
0x180003b0f  lea     r9, aPerformanceWin; "Performance\\WinSAT\\DataStore"
0x180003b16  mov     r8, [rcx]
0x180003b19  xor     edx, edx
0x180003b1b  lea     rcx, [rsp+320h+var_2F0]
0x180003b20  call    ?munge@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAX_K0PEBG0@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::munge(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x180003b25  xorps   xmm0, xmm0
0x180003b28  movdqu  [rsp+320h+var_2E8], xmm0
0x180003b2e  mov     [rsp+320h+var_2D8], r13
0x180003b33  call    ??2?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@CAPEAX_K@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::operator new(unsigned __int64)
0x180003b38  mov     [rsp+320h+var_2C8], rax
0x180003b3d  test    rax, rax
0x180003b40  jz      short loc_180003B51
0x180003b42  mov     edx, 104h
0x180003b47  mov     rcx, rax
0x180003b4a  call    ??0?$mstring_buf@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAA@_KAEBV?$allocator@G@std@@@Z; mlib::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::mstring_buf<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64,std::allocator<ushort> const &)
0x180003b4f  jmp     short loc_180003B54
0x180003b51  mov     rax, r13
0x180003b54  mov     qword ptr [rsp+320h+var_2D0], rax
0x180003b59  lea     r9, asc_180037888; "*"
0x180003b60  lea     r8, aFormal; "Formal"
0x180003b67  lea     rdx, aSAssessmentS; "*%s.Assessment (%s)"
0x180003b6e  lea     rcx, [rsp+320h+var_2D0]
0x180003b73  call    ?spf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spf(ushort const *,...)
0x180003b78  lea     r9, aWinsatXml; ".WinSAT.xml"
0x180003b7f  mov     rax, r9
0x180003b82  test    rbx, rbx
0x180003b85  jz      loc_180003FD8
0x180003b8b  cmp     word ptr [rax], 0
0x180003b8f  jz      short loc_180003B9A
0x180003b91  add     rax, 2
0x180003b95  dec     rbx
0x180003b98  jmp     short loc_180003B82
0x180003b9a  sub     rax, r9
0x180003b9d  sar     rax, 1
0x180003ba0  mov     rcx, qword ptr [rsp+320h+var_2D0]
0x180003ba5  mov     [rsp+320h+pszPath], rax
0x180003baa  mov     r8, [rcx]
0x180003bad  xor     edx, edx
0x180003baf  lea     rcx, [rsp+320h+var_2D0]
0x180003bb4  call    ?munge@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAX_K0PEBG0@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::munge(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x180003bb9  mov     rbx, qword ptr [rsp+320h+var_2D0]
0x180003bbe  mov     r15, [rbx+18h]
0x180003bc2  mov     rdi, [rsp+320h+var_2F0]
0x180003bc7  mov     rdx, [rdi+18h]
0x180003bcb  mov     rsi, r13
0x180003bce  test    rdx, rdx
0x180003bd1  jz      short loc_180003BD8
0x180003bd3  cmp     [rdx], si
0x180003bd6  jnz     short loc_180003C4B
0x180003bd8  mov     ecx, 208h; unsigned __int64
0x180003bdd  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180003be2  mov     rsi, rax
0x180003be5  test    rax, rax
0x180003be8  jnz     short loc_180003BFE
0x180003bea  lea     ecx, [rax+8]; dwErrCode
0x180003bed  call    cs:__imp_SetLastError
0x180003bf4  nop     dword ptr [rax+rax+00h]
0x180003bf9  jmp     loc_180003D0F
0x180003bfe  mov     rdx, rsi; lpBuffer
0x180003c01  mov     ecx, 104h; nBufferLength
0x180003c06  call    cs:__imp_GetCurrentDirectoryW
0x180003c0d  nop     dword ptr [rax+rax+00h]
0x180003c12  test    eax, eax
0x180003c14  jnz     short loc_180003C48
0x180003c16  call    cs:__imp_GetLastError
0x180003c1d  nop     dword ptr [rax+rax+00h]
0x180003c22  mov     r15d, eax
0x180003c25  mov     rcx, rsi
0x180003c28  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003c2f  nop     dword ptr [rax+rax+00h]
0x180003c34  mov     ecx, r15d; dwErrCode
0x180003c37  call    cs:__imp_SetLastError
0x180003c3e  nop     dword ptr [rax+rax+00h]
0x180003c43  jmp     loc_180003D06
0x180003c48  mov     rdx, rsi
0x180003c4b  mov     [rbp+220h+var_A0], r13
0x180003c52  mov     [rbp+220h+var_98], r13
0x180003c59  mov     [rbp+220h+var_90], r13
0x180003c60  mov     [rbp+220h+var_88], 0FFFFFFFFFFFFFFFFh
0x180003c6b  mov     [rbp+220h+var_80], r13
0x180003c72  lea     rax, ??_7?$FSpecList@G@mlib@@6B@; const mlib::FSpecList<ushort>::`vftable'
0x180003c79  mov     [rbp+220h+var_78], rax
0x180003c80  xorps   xmm0, xmm0
0x180003c83  movdqa  [rbp+220h+var_70], xmm0
0x180003c8b  xorps   xmm1, xmm1
0x180003c8e  movdqa  [rbp+220h+var_60], xmm1
0x180003c96  mov     [rsp+320h+var_2A8], r13w
0x180003c9c  lea     rax, ??_7?$FileFinder@G@mlib@@6B@; const mlib::FileFinder<ushort>::`vftable'
0x180003ca3  mov     [rsp+320h+var_2B0], rax
0x180003ca8  lea     rax, [rsp+320h+var_2E8]
0x180003cad  mov     [rbp+220h+var_50], rax
0x180003cb4  mov     r8, r15
0x180003cb7  lea     rcx, [rsp+320h+var_2B0]
0x180003cbc  call    ?traverse_dir@?$TraverseDirT@G@mlib@@QEAAKPEBG0_K_N@Z; mlib::TraverseDirT<ushort>::traverse_dir(ushort const *,ushort const *,unsigned __int64,bool)
0x180003cc1  mov     r15d, eax
0x180003cc4  test    rsi, rsi
0x180003cc7  jz      short loc_180003CD9
0x180003cc9  mov     rcx, rsi
0x180003ccc  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003cd3  nop     dword ptr [rax+rax+00h]
0x180003cd8  nop
0x180003cd9  lea     rax, ??_7?$TraverseDirT@G@mlib@@6B@; const mlib::TraverseDirT<ushort>::`vftable'
0x180003ce0  mov     [rsp+320h+var_2B0], rax
0x180003ce5  lea     rax, ??_7?$FSpecList@G@mlib@@6B@; const mlib::FSpecList<ushort>::`vftable'
0x180003cec  mov     [rbp+220h+var_78], rax
0x180003cf3  mov     rcx, qword ptr [rbp+220h+var_60+8]
0x180003cfa  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180003d01  nop     dword ptr [rax+rax+00h]
0x180003d06  test    r15d, r15d
0x180003d09  jz      loc_180003D9D
0x180003d0f  call    cs:__imp_GetLastError
0x180003d16  nop     dword ptr [rax+rax+00h]
0x180003d1b  mov     esi, eax
0x180003d1d  test    eax, eax
0x180003d1f  jle     short loc_180003D2A
0x180003d21  movzx   esi, ax
0x180003d24  or      esi, 80070000h
0x180003d2a  sub     qword ptr [rbx+10h], 1
0x180003d2f  jnz     short loc_180003D55
0x180003d31  mov     rcx, [rbx+18h]
0x180003d35  test    rcx, rcx
0x180003d38  jz      short loc_180003D46
0x180003d3a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003d41  nop     dword ptr [rax+rax+00h]
0x180003d46  mov     rcx, rbx
0x180003d49  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003d50  nop     dword ptr [rax+rax+00h]
0x180003d55  test    esi, esi
0x180003d57  jns     short loc_180003DC1
0x180003d59  mov     rdx, qword ptr [rsp+320h+var_2E8]
0x180003d5e  test    rdx, rdx
0x180003d61  jz      short loc_180003D8C
0x180003d63  mov     r8, qword ptr [rsp+320h+var_2E8+8]
0x180003d68  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180003d6d  mov     rcx, qword ptr [rsp+320h+var_2E8]
0x180003d72  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003d79  nop     dword ptr [rax+rax+00h]
0x180003d7e  xorps   xmm0, xmm0
0x180003d81  movdqu  [rsp+320h+var_2E8], xmm0
0x180003d87  mov     [rsp+320h+var_2D8], r13
0x180003d8c  lea     rcx, [rsp+320h+var_2F0]
0x180003d91  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180003d96  mov     eax, esi
0x180003d98  jmp     loc_180003FEF
0x180003d9d  mov     rdx, qword ptr [rsp+320h+var_2E8+8]
0x180003da2  mov     r8, rdx
0x180003da5  mov     rcx, qword ptr [rsp+320h+var_2E8]
0x180003daa  sub     r8, rcx
0x180003dad  sar     r8, 3
0x180003db1  call    ??$_Sort@PEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@_JP6A_NAEBV12@0@Z@std@@YAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0_JP6A_NAEBV12@2@Z@Z; std::_Sort<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,__int64,bool (*)(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)>(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,__int64,bool (*)(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &))
0x180003db6  nop
0x180003db7  lea     rcx, [rsp+320h+var_2D0]
0x180003dbc  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180003dc1  mov     r8, qword ptr [rsp+320h+var_2E8+8]
0x180003dc6  mov     rcx, qword ptr [rsp+320h+var_2E8]
0x180003dcb  cmp     r8, rcx
0x180003dce  jnz     short loc_180003DE9
0x180003dd0  mov     dword ptr [r12], 3
0x180003dd8  test    rcx, rcx
0x180003ddb  jz      loc_180003EEF
0x180003de1  mov     rdx, rcx
0x180003de4  jmp     loc_180003ECB
0x180003de9  mov     [rsp+320h+var_2C8], r13
0x180003dee  lea     r8, [rsp+320h+var_2C8]
0x180003df3  mov     rdx, r14
0x180003df6  call    ?LoadRecentResultsFromFile@DataStoreReader@@KAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@AEAUWinSATData@@PEAPEAUIXMLDOMDocument2@@@Z; DataStoreReader::LoadRecentResultsFromFile(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &,WinSATData &,IXMLDOMDocument2 * *)
0x180003dfb  mov     ebx, eax
0x180003dfd  test    eax, eax
0x180003dff  jns     short loc_180003E50
0x180003e01  lea     rcx, [rsp+320h+var_2C8]
0x180003e06  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180003e0b  nop
0x180003e0c  mov     rdx, qword ptr [rsp+320h+var_2E8]
0x180003e11  test    rdx, rdx
0x180003e14  jz      short loc_180003E3F
0x180003e16  mov     r8, qword ptr [rsp+320h+var_2E8+8]
0x180003e1b  call    ?_Destroy@?$vector@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@V?$allocator@V?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@std@@@std@@IEAAXPEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@0@Z; std::vector<mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>>::_Destroy(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> *)
0x180003e20  mov     rcx, qword ptr [rsp+320h+var_2E8]
0x180003e25  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180003e2c  nop     dword ptr [rax+rax+00h]
0x180003e31  xorps   xmm0, xmm0
0x180003e34  movdqu  [rsp+320h+var_2E8], xmm0
0x180003e3a  mov     [rsp+320h+var_2D8], r13
0x180003e3f  lea     rcx, [rsp+320h+var_2F0]
0x180003e44  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x180003e49  mov     eax, ebx
0x180003e4b  jmp     loc_180003FEF
0x180003e50  mov     [rsp+320h+var_2D0], r13d
0x180003e55  mov     [rsp+320h+var_2BC], r13d
0x180003e5a  lea     rdx, [rsp+320h+var_2D0]; unsigned int *
0x180003e5f  call    ?GetHistoryVersion@DataStoreReader@@CAJPEBGAEAK@Z; DataStoreReader::GetHistoryVersion(ushort const *,ulong &)
0x180003e64  mov     esi, eax
0x180003e66  mov     rbx, [rsp+320h+var_2C8]
0x180003e6b  test    eax, eax
0x180003e6d  js      loc_180003F61
0x180003e73  lea     rdx, [rsp+320h+var_2BC]; unsigned int *
0x180003e78  mov     rcx, rbx; struct IXMLDOMDocument2 *
  ... truncated ...
```
