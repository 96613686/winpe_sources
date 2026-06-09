# CCompDBList::LoadCompDBs(LoadCompDBFlags,DeviceType,wchar_t const * const)

- ea: `0x1800f5334`
- end: `0x1800f5c85`
- name: `?LoadCompDBs@CCompDBList@@QEAAJW4LoadCompDBFlags@@W4DeviceType@@QEB_W@Z`
- size: `2385`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800f5198`

## callees

- `0x1800031d0`
- `0x180004c70`
- `0x1800062b8`
- `0x18000694a`
- `0x18000ba40`
- `0x18000ccb8`
- `0x18000f614`
- `0x18000f874`
- `0x18000fb10`
- `0x18001268c`
- `0x18001a810`
- `0x18001ba4c`
- `0x18002aa74`
- `0x18002c7e8`
- `0x18003ddc8`
- `0x18003e9cc`
- `0x18004d970`
- `0x1800f2214`
- `0x1800f24c8`
- `0x1800f30f8`
- `0x1800f36b4`
- `0x1800f3aa0`
- `0x1800f5334`
- `0x1800f6b20`
- `0x180182d08`
- `0x1801832a4`
- `0x180183350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800f5913`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800f5913`

## string_xrefs

- `0x1800f5c72`: `onecore\internal\sdk\inc\wil\opensource\wil\stl.h`
- `0x1800f53cb`: `onecore\base\servicing\compositiondatabase\lib\ccompdblist.cpp`
- `0x1800f5420`: `onecore\base\servicing\compositiondatabase\lib\ccompdblist.cpp`
- `0x1800f54df`: `onecore\base\servicing\compositiondatabase\lib\ccompdblist.cpp`
- `0x1800f558e`: `onecore\base\servicing\compositiondatabase\lib\ccompdblist.cpp`
- `0x1800f580e`: `onecore\base\servicing\compositiondatabase\lib\ccompdblist.cpp`
- `0x1800f58bf`: `onecore\base\servicing\compositiondatabase\lib\ccompdblist.cpp`
- `0x1800f597f`: `onecore\base\servicing\compositiondatabase\lib\ccompdblist.cpp`
- `0x1800f5a3f`: `onecore\base\servicing\compositiondatabase\lib\ccompdblist.cpp`
- `0x1800f539c`: `arbiter: Verifying and loading CompDBs from: {0}`
- `0x1800f5667`: `Failed while trying to find compDBs in sandbox: {0}`
- `0x1800f55d1`: `*db*.xml`
- `0x1800f548f`: `Failed to delete uncabbed DB files.`
- `0x1800f57be`: `Failed to parse compDB file: {0}`
- `0x1800f5b8b`: `Ignoring CompDB: {0}, revision: {1} since is not newer than CompDB: {2}, revision: {3}`
- `0x1800f5af4`: `Using CompDB: {0}, revision: {1} to replace CompDB: {2}, revision: {3}`
- `0x1800f5927`: `Excluding Apps CompDB: {0}`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CCompDBList::LoadCompDBs(__int64 a1, int a2, int a3, __int64 a4)
{
  int v5; // eax
  unsigned int v6; // ebx
  const char *v7; // r9
  __int64 result; // rax
  int v9; // eax
  CCompDBList *v10; // rcx
  unsigned int v11; // ebx
  wchar_t *v12; // rdi
  int v13; // eax
  unsigned int v14; // r14d
  __int64 v15; // rdx
  int DBFiles; // eax
  unsigned int v17; // r14d
  __int64 v18; // rdx
  __int16 *trivial_2; // rax
  const char *v20; // r9
  __int64 v21; // rax
  __int64 v22; // rcx
  int AllFilesAndDirectories; // eax
  unsigned int v24; // r14d
  __int64 v25; // rdx
  wchar_t *v26; // r13
  wchar_t *v27; // r14
  wchar_t *v28; // rcx
  int v29; // eax
  unsigned int v30; // r15d
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rcx
  int v34; // eax
  unsigned int v35; // ebx
  const wchar_t *v36; // rdx
  __int128 v37; // kr10_16
  __int64 v38; // r8
  int v39; // eax
  unsigned int v40; // ebx
  const wchar_t *v41; // rcx
  const wchar_t **i; // rbx
  __int64 v43; // r8
  const wchar_t **v44; // rdx
  __int64 v45; // rdx
  __int64 v46; // rcx
  int *v47; // [rsp+20h] [rbp-108h]
  int *v48; // [rsp+20h] [rbp-108h]
  wchar_t *v49; // [rsp+40h] [rbp-E8h] BYREF
  __int128 v50; // [rsp+48h] [rbp-E0h] BYREF
  __int64 v51; // [rsp+58h] [rbp-D0h]
  int v52[2]; // [rsp+60h] [rbp-C8h] BYREF
  __int64 v53; // [rsp+68h] [rbp-C0h]
  __int64 v54; // [rsp+70h] [rbp-B8h]
  int v55[2]; // [rsp+78h] [rbp-B0h] BYREF
  __int64 v56; // [rsp+80h] [rbp-A8h]
  __int64 v57; // [rsp+88h] [rbp-A0h] BYREF
  wchar_t *v58[2]; // [rsp+90h] [rbp-98h] BYREF
  int v59[4]; // [rsp+A0h] [rbp-88h] BYREF
  __int128 v60; // [rsp+B0h] [rbp-78h]
  __int64 v61; // [rsp+C0h] [rbp-68h]
  wchar_t *Str; // [rsp+C8h] [rbp-60h] BYREF
  wchar_t *v63[3]; // [rsp+D0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v54 = -2;
  v57 = a4;
  v49 = 0;
  memset(v63, 0, sizeof(v63));
  *(_DWORD *)(a1 + 72) = a2;
  *(_DWORD *)(a1 + 76) = a3;
  try
  {
    LogAdapter::TraceInfo<wchar_t const *>("arbiter: Verifying and loading CompDBs from: {0}", &v57);
    v5 = SczAllocFromSz(&v49);
    v6 = v5;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14E,
        (unsigned int)"onecore\\base\\servicing\\compositiondatabase\\lib\\ccompdblist.cpp",
        (const char *)(unsigned int)v5,
        (int)v47);
      std::vector<std::wstring>::_Tidy(v63);
      if ( v49 )
        operator delete(v49 - 4);
      return v6;
    }
    v9 = SczEnsureBackslashTerminated(&v49);
    v11 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14F,
        (unsigned int)"onecore\\base\\servicing\\compositiondatabase\\lib\\ccompdblist.cpp",
        (const char *)(unsigned int)v9,
        (int)v47);
      std::vector<std::wstring>::_Tidy(v63);
      if ( v49 )
        operator delete(v49 - 4);
      return v11;
    }
    v12 = v49;
    if ( (*(_BYTE *)(a1 + 72) & 2) == 0 )
    {
      v13 = CCompDBList::DeleteUncabbedDBFilesFromSandbox(v10, v49);
      v14 = v13;
      if ( v13 < 0 )
      {
        LODWORD(Str) = v13;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed to delete uncabbed DB files.");
          *(_QWORD *)v55 = &Str;
          v47 = v55;
          LOBYTE(v15) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v15,
            3,
            ": {}");
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x157,
          (unsigned int)"onecore\\base\\servicing\\compositiondatabase\\lib\\ccompdblist.cpp",
          (const char *)v14,
          (int)v47);
        std::vector<std::wstring>::_Tidy(v63);
        if ( v12 )
          operator delete(v12 - 4);
        return v14;
      }
    }
    DBFiles = CCompDBList::ExtractDBFiles((CCompDBList *)a1, v12);
    v17 = DBFiles;
    if ( DBFiles < 0 )
    {
      LODWORD(Str) = DBFiles;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to extract DB files");
        *(_QWORD *)v55 = &Str;
        v47 = v55;
        LOBYTE(v18) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v18,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15A,
        (unsigned int)"onecore\\base\\servicing\\compositiondatabase\\lib\\ccompdblist.cpp",
        (const char *)v17,
        (int)v47);
      std::vector<std::wstring>::_Tidy(v63);
      if ( v12 )
        operator delete(v12 - 4);
      return v17;
    }
    trivial_2 = (__int16 *)_std_find_trivial_2(L"*db*.xml", word_1801ED6A2, 0);
    if ( trivial_2 == word_1801ED6A2 || (v21 = ((char *)trivial_2 - (char *)L"*db*.xml") >> 1, v22 = -1, v21 == -1) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xEB,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\stl.h",
        v20);
    *(_QWORD *)v52 = L"*db*.xml";
    v53 = v21;
    *(_QWORD *)v55 = v12;
    do
      ++v22;
    while ( v12[v22] );
    v56 = v22;
    AllFilesAndDirectories = GetAllFilesAndDirectories((unsigned int)v55, (unsigned int)v52, 0, (unsigned int)v63, 0);
    v24 = AllFilesAndDirectories;
    if ( AllFilesAndDirectories < 0 )
    {
      LODWORD(Str) = AllFilesAndDirectories;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed while trying to find compDBs in sandbox: {0}",
          &v57);
        *(_QWORD *)v55 = &Str;
        LOBYTE(v25) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v25,
          3,
          ": {}");
      }
      std::vector<std::wstring>::_Tidy(v63);
      if ( v12 )
        operator delete(v12 - 4);
      return v24;
    }
    v26 = v63[1];
    v27 = v63[0];
    if ( v63[0] == v63[1] )
    {
      LogAdapter::TraceInfo<wchar_t const *>("No DBs found in the sandbox: {0}", &v57);
      std::vector<std::wstring>::_Tidy(v63);
      if ( v12 )
        operator delete(v12 - 4);
      return 0;
    }
    while ( 1 )
    {
      v50 = 0;
      v51 = 0;
      *(_QWORD *)v55 = 0;
      v58[0] = 0;
      LODWORD(v58[1]) = 0;
      *(_OWORD *)v59 = 0;
      v60 = 0;
      v61 = 0;
      LogAdapter::TraceInfo<std::wstring>("Loading database: {0}", v27);
      if ( *((_QWORD *)v27 + 3) <= 7u )
        v28 = v27;
      else
        v28 = *(wchar_t **)v27;
      v29 = CompositionDatabaseParser::ReadCompositionDatabase(v28, a1 + 24, v55, &v50);
      v30 = v29;
      if ( v29 < 0 )
      {
        LODWORD(Str) = v29;
        if ( *(_QWORD *)&LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<std::wstring>(
            *(_QWORD *)&LogAdapter::g_Logger,
            0,
            3,
            "Failed to parse compDB file: {0}",
            v27);
          *(_QWORD *)v52 = &Str;
          v48 = v52;
          LOBYTE(v31) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            *(_QWORD *)&LogAdapter::g_Logger,
            v31,
            3,
            ": {}");
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x177,
          (unsigned int)"onecore\\base\\servicing\\compositiondatabase\\lib\\ccompdblist.cpp",
          (const char *)v30,
          (int)v48);
        if ( v51 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v51);
        std::vector<std::wstring>::_Tidy(v63);
        if ( v12 )
          operator delete(v12 - 4);
        return v30;
      }
      v32 = *(_QWORD *)v55;
      if ( *(_BYTE *)(*(_QWORD *)v55 + 104LL) == 8 && (*(_BYTE *)(a1 + 72) & 0x20) == 0 )
      {
        LogAdapter::TraceInfo<std::wstring>("Excluding Supplemental database: {0}", v27);
        v33 = v51;
        goto LABEL_91;
      }
      if ( (*(_BYTE *)(a1 + 72) & 0x40) == 0 )
        goto LABEL_62;
      Str = 0;
      v34 = DuplicateParserString(
              (struct Windows::Rtl::IPoolAllocator *)(a1 + 24),
              (const struct _LUTF8_STRING *)(*(_QWORD *)v55 + 400LL),
              &Str);
      v35 = v34;
      if ( v34 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x183,
          (unsigned int)"onecore\\base\\servicing\\compositiondatabase\\lib\\ccompdblist.cpp",
          (const char *)(unsigned int)v34,
          (int)v48);
        if ( v51 )
          anonymous_namespace_::OurRtlFreeStringRoutine(v51);
        std::vector<std::wstring>::_Tidy(v63);
        if ( v12 )
          operator delete(v12 - 4);
        return v35;
      }
      if ( !wcsstr(Str, L"Desktop_Apps") )
        break;
      LogAdapter::TraceInfo<std::wstring>("Excluding Apps CompDB: {0}", v27);
      v33 = v51;
LABEL_91:
      if ( v33 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v33);
LABEL_93:
      v27 += 16;
      if ( v27 == v26 )
      {
        ____Sort_unchecked_PEAUCompDBFile_CompDBList__P6A_NAEBU12_0__E_std__YAXPEAUCompDBFile_CompDBList__0_JP6A_NAEBU12_2__E_Z(
          *(_QWORD *)(a1 + 48),
          *(_QWORD *)(a1 + 56),
          0x6DB6DB6DB6DB6DB7LL * ((__int64)(*(_QWORD *)(a1 + 56) - *(_QWORD *)(a1 + 48)) >> 3),
          CmpCompDBFile);
        v46 = *(_QWORD *)(a1 + 48);
        if ( v46 != *(_QWORD *)(a1 + 56) )
        {
          *(_QWORD *)(a1 + 8) = v46;
          *(_DWORD *)(a1 + 16) = -1227133513 * ((*(_QWORD *)(a1 + 56) - v46) >> 3);
        }
        std::vector<std::wstring>::_Tidy(v63);
        if ( v12 )
          operator delete(v12 - 4);
        return 0;
      }
    }
    v32 = *(_QWORD *)v55;
LABEL_62:
    *(_QWORD *)&v59[2] = v32;
    if ( *((_QWORD *)v27 + 3) <= 7u )
      v36 = v27;
    else
      v36 = *(const wchar_t **)v27;
    *(_QWORD *)v59 = DuplicateNullTerminatedString((struct Windows::Rtl::IPoolAllocator *)(a1 + 24), v36);
    if ( !*(_QWORD *)v59 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x18F,
        (unsigned int)"onecore\\base\\servicing\\compositiondatabase\\lib\\ccompdblist.cpp",
        (const char *)0x8007000ELL,
        (int)v48);
      if ( v51 )
        anonymous_namespace_::OurRtlFreeStringRoutine(v51);
      std::vector<std::wstring>::_Tidy(v63);
      if ( v12 )
        operator delete(v12 - 4);
      return 2147942414LL;
    }
    v37 = v50;
    v38 = v51;
    v50 = 0;
    v51 = 0;
    v60 = v37;
    v61 = v38;
    LODWORD(v58[1]) = **(_DWORD **)v55;
    if ( !*(_BYTE *)(*(_QWORD *)v55 + 680LL)
      || (v39 = DuplicateParserString(
                  (struct Windows::Rtl::IPoolAllocator *)(a1 + 24),
                  (const struct _LUTF8_STRING *)(*(_QWORD *)v55 + 400LL),
                  v58),
          v40 = v39,
          v39 >= 0) )
    {
      v41 = v58[0];
      if ( v58[0] )
      {
        for ( i = *(const wchar_t ***)(a1 + 48); i != *(const wchar_t ***)(a1 + 56); i += 7 )
        {
          if ( !ComparePossiblyNullStringsCaseInvariant(v41, *i) )
          {
            v44 = i + 1;
            if ( LODWORD(v58[1]) > *((_DWORD *)i + 2) )
            {
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                v48 = v59;
                LogAdapter::Logger::LogNumObjects<wchar_t const *,unsigned int,wchar_t const *,unsigned int>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v44,
                  v43,
                  "Using CompDB: {0}, revision: {1} to replace CompDB: {2}, revision: {3}");
              }
              memmove_0(i, i + 7, *(_QWORD *)(a1 + 56) - (_QWORD)(i + 7));
              *(_QWORD *)(a1 + 56) -= 56LL;
              break;
            }
            if ( *(_QWORD *)&LogAdapter::g_Logger )
            {
              v48 = v59;
              LogAdapter::Logger::LogNumObjects<wchar_t const *,unsigned int,wchar_t const *,unsigned int>(
                *(_QWORD *)&LogAdapter::g_Logger,
                v44,
                v43,
                "Ignoring CompDB: {0}, revision: {1} since is not newer than CompDB: {2}, revision: {3}");
            }
            goto LABEL_93;
          }
          v41 = v58[0];
        }
      }
      v45 = *(_QWORD *)(a1 + 56);
      if ( v45 == *(_QWORD *)(a1 + 64) )
      {
        std::vector<CompDBList::CompDBFile>::_Emplace_reallocate<CompDBList::CompDBFile>(a1 + 48, v45, v58);
      }
      else
      {
        *(_OWORD *)v45 = *(_OWORD *)v58;
        *(_OWORD *)(v45 + 16) = *(_OWORD *)v59;
        *(_OWORD *)(v45 + 32) = v60;
        *(_QWORD *)(v45 + 48) = v61;
        *(_QWORD *)(a1 + 56) += 56LL;
      }
      goto LABEL_93;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x196,
      (unsigned int)"onecore\\base\\servicing\\compositiondatabase\\lib\\ccompdblist.cpp",
      (const char *)(unsigned int)v39,
      (int)v48);
    std::vector<std::wstring>::_Tidy(v63);
    if ( v12 )
      operator delete(v12 - 4);
    result = v40;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1CD,
                           (unsigned int)"onecore\\base\\servicing\\compositiondatabase\\lib\\ccompdblist.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x1800f5334  mov     r11, rsp
0x1800f5337  push    rdi
0x1800f5338  push    r12
0x1800f533a  push    r13
0x1800f533c  push    r14
0x1800f533e  push    r15
0x1800f5340  sub     rsp, 100h
0x1800f5347  mov     [rsp+128h+var_B8], 0FFFFFFFFFFFFFFFEh
0x1800f5350  mov     [r11+10h], rbx
0x1800f5354  mov     [r11+18h], rsi
0x1800f5358  movaps  xmmword ptr [r11-38h], xmm6
0x1800f535d  mov     rax, cs:__security_cookie
0x1800f5364  xor     rax, rsp
0x1800f5367  mov     [rsp+128h+var_40], rax
0x1800f536f  mov     rsi, rcx
0x1800f5372  mov     [r11-0A0h], r9
0x1800f5379  xor     r15d, r15d
0x1800f537c  mov     [rsp+128h+var_E8], r15
0x1800f5381  xorps   xmm0, xmm0
0x1800f5384  movdqu  xmmword ptr [r11-58h], xmm0
0x1800f538a  mov     [r11-48h], r15
0x1800f538e  mov     [rcx+48h], edx
0x1800f5391  mov     [rcx+4Ch], r8d
0x1800f5395  lea     rdx, [r11-0A0h]
0x1800f539c  lea     rcx, aArbiterVerifyi; "arbiter: Verifying and loading CompDBs "...
0x1800f53a3  call    ??$TraceInfo@PEB_W@LogAdapter@@YAXQEBDAEBQEB_W@Z; LogAdapter::TraceInfo<wchar_t const *>(char const * const,wchar_t const * const &)
0x1800f53a8  mov     rdx, [rsp+128h+var_A0]
0x1800f53b0  lea     rcx, [rsp+128h+var_E8]
0x1800f53b5  call    SczAllocFromSz
0x1800f53ba  mov     ebx, eax
0x1800f53bc  test    eax, eax
0x1800f53be  jns     short loc_1800F5405
0x1800f53c0  mov     rcx, [rsp+128h]; this
0x1800f53c8  mov     r9d, eax; char *
0x1800f53cb  lea     r8, aOnecoreBaseSer_12; "onecore\\base\\servicing\\compositionda"...
0x1800f53d2  mov     edx, 14Eh; void *
0x1800f53d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f53dc  nop
0x1800f53dd  lea     rcx, [rsp+128h+var_58]
0x1800f53e5  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800f53ea  nop
0x1800f53eb  mov     rcx, [rsp+128h+var_E8]
0x1800f53f0  test    rcx, rcx
0x1800f53f3  jz      short loc_1800F53FE
0x1800f53f5  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800f53f9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f53fe  mov     eax, ebx
0x1800f5400  jmp     loc_1800F5C37
0x1800f5405  lea     rcx, [rsp+128h+var_E8]
0x1800f540a  call    SczEnsureBackslashTerminated
0x1800f540f  mov     ebx, eax
0x1800f5411  test    eax, eax
0x1800f5413  jns     short loc_1800F545A
0x1800f5415  mov     rcx, [rsp+128h]; this
0x1800f541d  mov     r9d, eax; char *
0x1800f5420  lea     r8, aOnecoreBaseSer_12; "onecore\\base\\servicing\\compositionda"...
0x1800f5427  mov     edx, 14Fh; void *
0x1800f542c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f5431  nop
0x1800f5432  lea     rcx, [rsp+128h+var_58]
0x1800f543a  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800f543f  nop
0x1800f5440  mov     rcx, [rsp+128h+var_E8]
0x1800f5445  test    rcx, rcx
0x1800f5448  jz      short loc_1800F5453
0x1800f544a  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800f544e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f5453  mov     eax, ebx
0x1800f5455  jmp     loc_1800F5C37
0x1800f545a  mov     rdi, [rsp+128h+var_E8]
0x1800f545f  test    byte ptr [rsi+48h], 2
0x1800f5463  jnz     loc_1800F5515
0x1800f5469  mov     rdx, rdi; wchar_t *
0x1800f546c  call    ?DeleteUncabbedDBFilesFromSandbox@CCompDBList@@AEAAJQEB_W@Z; CCompDBList::DeleteUncabbedDBFilesFromSandbox(wchar_t const * const)
0x1800f5471  mov     r14d, eax
0x1800f5474  test    eax, eax
0x1800f5476  jns     loc_1800F5515
0x1800f547c  mov     dword ptr [rsp+128h+Str], eax
0x1800f5483  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f548a  test    rcx, rcx
0x1800f548d  jz      short loc_1800F54D4
0x1800f548f  lea     r9, aFailedToDelete_0; "Failed to delete uncabbed DB files."
0x1800f5496  mov     ebx, 3
0x1800f549b  mov     r8d, ebx
0x1800f549e  xor     edx, edx
0x1800f54a0  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f54a5  lea     rax, [rsp+128h+Str]
0x1800f54ad  mov     qword ptr [rsp+128h+var_B0], rax
0x1800f54b2  lea     rax, [rsp+128h+var_B0]
0x1800f54b7  mov     qword ptr [rsp+128h+var_108], rax; int
0x1800f54bc  lea     r9, asc_1801CAFB4; ": {}"
0x1800f54c3  mov     r8d, ebx
0x1800f54c6  mov     dl, 1
0x1800f54c8  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f54cf  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f54d4  mov     rcx, [rsp+128h]; this
0x1800f54dc  mov     r9d, r14d; char *
0x1800f54df  lea     r8, aOnecoreBaseSer_12; "onecore\\base\\servicing\\compositionda"...
0x1800f54e6  mov     edx, 157h; void *
0x1800f54eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f54f0  nop
0x1800f54f1  lea     rcx, [rsp+128h+var_58]
0x1800f54f9  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800f54fe  nop
0x1800f54ff  test    rdi, rdi
0x1800f5502  jz      short loc_1800F550D
0x1800f5504  lea     rcx, [rdi-8]; Block
0x1800f5508  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f550d  mov     eax, r14d
0x1800f5510  jmp     loc_1800F5C37
0x1800f5515  mov     rdx, rdi; wchar_t *
0x1800f5518  mov     rcx, rsi; this
0x1800f551b  call    ?ExtractDBFiles@CCompDBList@@AEAAJQEB_W@Z; CCompDBList::ExtractDBFiles(wchar_t const * const)
0x1800f5520  mov     r14d, eax
0x1800f5523  test    eax, eax
0x1800f5525  jns     loc_1800F55C4
0x1800f552b  mov     dword ptr [rsp+128h+Str], eax
0x1800f5532  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f5539  test    rcx, rcx
0x1800f553c  jz      short loc_1800F5583
0x1800f553e  lea     r9, aFailedToExtrac_7; "Failed to extract DB files"
0x1800f5545  mov     ebx, 3
0x1800f554a  mov     r8d, ebx
0x1800f554d  xor     edx, edx
0x1800f554f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800f5554  lea     rax, [rsp+128h+Str]
0x1800f555c  mov     qword ptr [rsp+128h+var_B0], rax
0x1800f5561  lea     rax, [rsp+128h+var_B0]
0x1800f5566  mov     qword ptr [rsp+128h+var_108], rax; int
0x1800f556b  lea     r9, asc_1801CAFB4; ": {}"
0x1800f5572  mov     r8d, ebx
0x1800f5575  mov     dl, 1
0x1800f5577  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f557e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f5583  mov     rcx, [rsp+128h]; this
0x1800f558b  mov     r9d, r14d; char *
0x1800f558e  lea     r8, aOnecoreBaseSer_12; "onecore\\base\\servicing\\compositionda"...
0x1800f5595  mov     edx, 15Ah; void *
0x1800f559a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f559f  nop
0x1800f55a0  lea     rcx, [rsp+128h+var_58]
0x1800f55a8  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800f55ad  nop
0x1800f55ae  test    rdi, rdi
0x1800f55b1  jz      short loc_1800F55BC
0x1800f55b3  lea     rcx, [rdi-8]; Block
0x1800f55b7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f55bc  mov     eax, r14d
0x1800f55bf  jmp     loc_1800F5C37
0x1800f55c4  xor     r8d, r8d
0x1800f55c7  lea     rbx, word_1801ED6A2
0x1800f55ce  mov     rdx, rbx
0x1800f55d1  lea     r14, aDbXml_0; "*db*.xml"
0x1800f55d8  mov     rcx, r14
0x1800f55db  call    __std_find_trivial_2
0x1800f55e0  cmp     rax, rbx
0x1800f55e3  jz      loc_1800F5C6A
0x1800f55e9  sub     rax, r14
0x1800f55ec  sar     rax, 1
0x1800f55ef  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800f55f3  cmp     rax, rcx
0x1800f55f6  jz      loc_1800F5C6A
0x1800f55fc  mov     qword ptr [rsp+128h+var_C8], r14
0x1800f5601  mov     [rsp+128h+var_C0], rax
0x1800f5606  mov     qword ptr [rsp+128h+var_B0], rdi
0x1800f560b  inc     rcx
0x1800f560e  cmp     [rdi+rcx*2], r15w
0x1800f5613  jnz     short loc_1800F560B
0x1800f5615  mov     [rsp+128h+var_A8], rcx
0x1800f561d  mov     qword ptr [rsp+128h+var_108], r15
0x1800f5622  lea     r9, [rsp+128h+var_58]
0x1800f562a  xor     r8d, r8d
0x1800f562d  lea     rdx, [rsp+128h+var_C8]
0x1800f5632  lea     rcx, [rsp+128h+var_B0]
0x1800f5637  call    ?GetAllFilesAndDirectories@@YAJAEBV?$basic_zstring_view@_W@wil@@0HPEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@1@Z; GetAllFilesAndDirectories(wil::basic_zstring_view<wchar_t> const &,wil::basic_zstring_view<wchar_t> const &,int,std::vector<std::wstring> *,std::vector<std::wstring> *)
0x1800f563c  mov     r14d, eax
0x1800f563f  test    eax, eax
0x1800f5641  jns     loc_1800F56D1
0x1800f5647  mov     dword ptr [rsp+128h+Str], eax
0x1800f564e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f5655  test    rcx, rcx
0x1800f5658  jz      short loc_1800F56AD
0x1800f565a  lea     rax, [rsp+128h+var_A0]
0x1800f5662  mov     qword ptr [rsp+128h+var_108], rax
0x1800f5667  lea     r9, aFailedWhileTry_1; "Failed while trying to find compDBs in "...
0x1800f566e  mov     ebx, 3
0x1800f5673  mov     r8d, ebx
0x1800f5676  xor     edx, edx
0x1800f5678  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x1800f567d  lea     rax, [rsp+128h+Str]
0x1800f5685  mov     qword ptr [rsp+128h+var_B0], rax
0x1800f568a  lea     rax, [rsp+128h+var_B0]
0x1800f568f  mov     qword ptr [rsp+128h+var_108], rax
0x1800f5694  lea     r9, asc_1801CAFB4; ": {}"
0x1800f569b  mov     r8d, ebx
0x1800f569e  mov     dl, 1
0x1800f56a0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f56a7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f56ac  nop
0x1800f56ad  lea     rcx, [rsp+128h+var_58]
0x1800f56b5  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800f56ba  nop
0x1800f56bb  test    rdi, rdi
0x1800f56be  jz      short loc_1800F56C9
0x1800f56c0  lea     rcx, [rdi-8]; Block
0x1800f56c4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f56c9  mov     eax, r14d
0x1800f56cc  jmp     loc_1800F5C37
0x1800f56d1  mov     r13, [rsp+128h+var_50]
0x1800f56d9  mov     r14, [rsp+128h+var_58]
0x1800f56e1  cmp     r14, r13
0x1800f56e4  jnz     short loc_1800F5727
0x1800f56e6  lea     rdx, [rsp+128h+var_A0]
0x1800f56ee  lea     rcx, aNoDbsFoundInTh; "No DBs found in the sandbox: {0}"
0x1800f56f5  call    ??$TraceInfo@PEB_W@LogAdapter@@YAXQEBDAEBQEB_W@Z; LogAdapter::TraceInfo<wchar_t const *>(char const * const,wchar_t const * const &)
0x1800f56fa  nop
0x1800f56fb  lea     rcx, [rsp+128h+var_58]
0x1800f5703  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800f5708  nop
0x1800f5709  test    rdi, rdi
0x1800f570c  jz      short loc_1800F5717
0x1800f570e  lea     rcx, [rdi-8]; Block
0x1800f5712  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f5717  xor     eax, eax
0x1800f5719  jmp     loc_1800F5C37
0x1800f571e  cmp     r14, r13
0x1800f5721  jz      loc_1800F5BC4
0x1800f5727  xorps   xmm0, xmm0
0x1800f572a  xor     eax, eax
0x1800f572c  movups  [rsp+128h+var_E0], xmm0
0x1800f5731  mov     [rsp+128h+var_D0], rax
0x1800f5736  mov     qword ptr [rsp+128h+var_B0], r15
0x1800f573b  mov     [rsp+128h+var_98], r15
0x1800f5743  mov     dword ptr [rsp+128h+var_98+8], r15d
0x1800f574b  movdqu  xmmword ptr [rsp+128h+var_88], xmm0
0x1800f5754  xorps   xmm1, xmm1
0x1800f5757  movups  [rsp+128h+var_78], xmm1
0x1800f575f  mov     [rsp+128h+var_68], rax
0x1800f5767  mov     rdx, r14
0x1800f576a  lea     rcx, aLoadingDatabas; "Loading database: {0}"
0x1800f5771  call    ??$TraceInfo@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@LogAdapter@@YAXQEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; LogAdapter::TraceInfo<std::wstring>(char const * const,std::wstring const &)
0x1800f5776  cmp     qword ptr [r14+18h], 7
0x1800f577b  jbe     short loc_1800F5782
0x1800f577d  mov     rcx, [r14]
0x1800f5780  jmp     short loc_1800F5785
0x1800f5782  mov     rcx, r14
0x1800f5785  lea     r12, [rsi+18h]
0x1800f5789  lea     r9, [rsp+128h+var_E0]
0x1800f578e  lea     r8, [rsp+128h+var_B0]
0x1800f5793  mov     rdx, r12
0x1800f5796  call    ?ReadCompositionDatabase@CompositionDatabaseParser@@YAJQEB_WAEAVIPoolAllocator@Rtl@Windows@@PEAPEAUCompositionDatabaseDocument@1@PEAV?$Auto@U_LBLOB@@@4@@Z; CompositionDatabaseParser::ReadCompositionDatabase(wchar_t const * const,Windows::Rtl::IPoolAllocator &,CompositionDatabaseParser::CompositionDatabaseDocument * *,Windows::Auto<_LBLOB> *)
0x1800f579b  mov     r15d, eax
0x1800f579e  test    eax, eax
0x1800f57a0  jns     loc_1800F5854
0x1800f57a6  mov     dword ptr [rsp+128h+Str], eax
0x1800f57ad  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f57b4  test    rcx, rcx
0x1800f57b7  jz      short loc_1800F5803
0x1800f57b9  mov     qword ptr [rsp+128h+var_108], r14
0x1800f57be  lea     r9, aFailedToParseC; "Failed to parse compDB file: {0}"
0x1800f57c5  mov     ebx, 3
0x1800f57ca  mov     r8d, ebx
0x1800f57cd  xor     edx, edx
0x1800f57cf  call    ??$LogNumObjects@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; LogAdapter::Logger::LogNumObjects<std::wstring>(bool,LogAdapter::LogLevel,char const * const,std::wstring const &)
0x1800f57d4  lea     rax, [rsp+128h+Str]
0x1800f57dc  mov     qword ptr [rsp+128h+var_C8], rax
0x1800f57e1  lea     rax, [rsp+128h+var_C8]
0x1800f57e6  mov     qword ptr [rsp+128h+var_108], rax; int
0x1800f57eb  lea     r9, asc_1801CAFB4; ": {}"
0x1800f57f2  mov     r8d, ebx
0x1800f57f5  mov     dl, 1
0x1800f57f7  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800f57fe  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800f5803  mov     rcx, [rsp+128h]; this
0x1800f580b  mov     r9d, r15d; char *
0x1800f580e  lea     r8, aOnecoreBaseSer_12; "onecore\\base\\servicing\\compositionda"...
0x1800f5815  mov     edx, 177h; void *
0x1800f581a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f581f  nop
0x1800f5820  mov     rcx, [rsp+128h+var_D0]
0x1800f5825  test    rcx, rcx
0x1800f5828  jz      short loc_1800F5830
0x1800f582a  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x1800f582f  nop
0x1800f5830  lea     rcx, [rsp+128h+var_58]
0x1800f5838  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800f583d  nop
0x1800f583e  test    rdi, rdi
0x1800f5841  jz      short loc_1800F584C
0x1800f5843  lea     rcx, [rdi-8]; Block
0x1800f5847  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f584c  mov     eax, r15d
0x1800f584f  jmp     loc_1800F5C37
0x1800f5854  mov     rax, qword ptr [rsp+128h+var_B0]
0x1800f5859  cmp     byte ptr [rax+68h], 8
0x1800f585d  jnz     short loc_1800F5882
0x1800f585f  test    byte ptr [rsi+48h], 20h
0x1800f5863  jnz     short loc_1800F5882
0x1800f5865  mov     rdx, r14
0x1800f5868  lea     rcx, aExcludingSuppl; "Excluding Supplemental database: {0}"
  ... truncated ...
```
