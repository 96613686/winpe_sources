# CFormattedDateTime::GatherKeywords(void)

- ea: `0x18001d250`
- end: `0x18001dcaf`
- name: `?GatherKeywords@CFormattedDateTime@@AEAAJXZ`
- size: `2655`
- prototype: `__int64 __fastcall(CFormattedDateTime *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, installer_update`

## callers

- `0x18001c274`

## callees

- `0x18001c6cc`
- `0x18001c7e0`
- `0x18001d250`
- `0x18001dcb8`
- `0x18001de80`
- `0x18001df98`
- `0x18003b1d8`
- `0x18003f818`
- `0x18003fd9c`
- `0x18003fde0`
- `0x180043c60`
- `0x180050bf0`
- `0x180059920`
- `0x18005daf0`
- `0x18005db14`
- `0x18005db64`
- `0x18005df6c`
- `0x18005df78`
- `0x18005e048`
- `0x18005e06c`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetCalendarInfoEx` at `0x18001d66e`
- `api-ms-win-core-localization-l1-2-0!GetCalendarInfoEx` at `0x18001d6d2`
- `api-ms-win-core-localization-l1-2-0!GetCalendarInfoEx` at `0x18001d66e`
- `api-ms-win-core-localization-l1-2-0!GetCalendarInfoEx` at `0x18001d6d2`
- `api-ms-win-core-calendar-l1-1-0!ConvertSystemTimeToCalDateTime` at `0x18001d7ca`
- `api-ms-win-core-calendar-l1-1-0!ConvertSystemTimeToCalDateTime` at `0x18001d7ca`
- `api-ms-win-core-calendar-l1-1-0!UpdateCalendarDayOfWeek` at `0x18001d7f4`
- `api-ms-win-core-calendar-l1-1-0!UpdateCalendarDayOfWeek` at `0x18001d7f4`
- `api-ms-win-core-calendar-l1-1-0!GetCalendarDateFormatEx` at `0x18001d825`
- `api-ms-win-core-calendar-l1-1-0!GetCalendarDateFormatEx` at `0x18001d825`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFormattedDateTime::GatherKeywords(CFormattedDateTime *this, unsigned int a2)
{
  int CalendarStrings; // edi
  const struct std::nothrow_t *v3; // rdx
  char *v4; // r15
  unsigned __int64 v5; // r14
  _QWORD *v6; // r12
  __int64 v7; // rax
  bool v8; // cf
  unsigned __int64 v9; // rax
  unsigned __int64 *v10; // rax
  void (__fastcall *v11)(KeywordBuilder *__hidden); // rcx
  struct KeywordBuilder *v12; // rsi
  unsigned __int64 v13; // rbx
  unsigned __int64 v14; // r12
  CFormattedDateTime *v15; // r13
  unsigned __int64 i; // rbx
  char *v17; // rdi
  __int64 v18; // r15
  unsigned int v19; // edx
  FormatNode *v20; // rcx
  _QWORD *v21; // rax
  char *v22; // rcx
  unsigned __int64 v23; // r15
  char *v24; // rdi
  __int64 v25; // r12
  unsigned int v26; // edx
  FormatNode *v27; // rcx
  _QWORD *v28; // rax
  char *v29; // rcx
  unsigned __int64 v30; // r12
  char *v31; // rdi
  __int64 v32; // r15
  unsigned int v33; // edx
  FormatNode *v34; // rcx
  _QWORD *v35; // rax
  char *v36; // rcx
  unsigned __int64 v37; // rax
  CFormattedDateTime *v38; // r15
  CALID *v39; // r13
  CALTYPE v40; // r12d
  int CalendarInfo; // eax
  unsigned __int64 cchData; // rdi
  unsigned __int64 v43; // rax
  WCHAR *lpCalData; // rax
  WCHAR *v45; // r15
  __int64 v46; // r12
  unsigned int v47; // edx
  FormatNode *v48; // rcx
  _QWORD *v49; // rax
  char *v50; // rcx
  unsigned __int64 v51; // r15
  wchar_t **v52; // r8
  unsigned __int64 v53; // rax
  unsigned __int64 v54; // rbx
  const struct std::nothrow_t *v56; // rdx
  int v57; // eax
  __int64 v58; // rcx
  char *v59; // rdi
  __int64 v60; // rax
  unsigned __int64 v61; // rax
  char **v62; // rax
  struct Keyword *v63; // rbx
  unsigned int v64; // edx
  __int64 v65; // rcx
  int Error; // [rsp+40h] [rbp-C0h]
  wchar_t v67[4]; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t **v68; // [rsp+50h] [rbp-B0h] BYREF
  CFormattedDateTime *v69; // [rsp+58h] [rbp-A8h] BYREF
  char *v70; // [rsp+60h] [rbp-A0h]
  void *v71; // [rsp+68h] [rbp-98h]
  _DWORD v72[4]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v73[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v74; // [rsp+A0h] [rbp-60h]
  _WORD v75[2]; // [rsp+B0h] [rbp-50h] BYREF
  char v76[156]; // [rsp+B4h] [rbp-4Ch] BYREF

  v69 = this;
  v68 = 0;
  *(_QWORD *)v67 = 0;
  CalendarStrings = CFormattedDateTime::GetCalendarStrings(this, a2, &v68, (unsigned __int64 *)v67);
  v3 = 0;
  if ( CalendarStrings < 0 )
    return (unsigned int)CalendarStrings;
  v4 = *(char **)v67;
  v70 = *(char **)v67;
  v5 = *(_QWORD *)v67 + 54LL;
  v6 = v68;
  v71 = v68;
  if ( (unsigned __int64)(*(_QWORD *)v67 + 54LL) < *(_QWORD *)v67 )
  {
    CalendarStrings = -2147024362;
LABEL_91:
    Error = CalendarStrings;
    goto LABEL_80;
  }
  v7 = 56 * v5;
  if ( !is_mul_ok(v5, 0x38u) )
    v7 = -1;
  v8 = __CFADD__(v7, 8);
  v9 = v7 + 8;
  if ( v8 )
    v9 = -1;
  v10 = (unsigned __int64 *)operator new[](v9, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)v67 = v10;
  v11 = KeywordBuilder::~KeywordBuilder;
  v3 = 0;
  if ( v10 )
  {
    *v10 = v5;
    v12 = (struct KeywordBuilder *)(v10 + 1);
    `eh vector constructor iterator'(
      v10 + 1,
      0x38u,
      v5,
      (void (*)(void *))KeywordBuilder::KeywordBuilder,
      (void (*)(void *))KeywordBuilder::~KeywordBuilder);
    v3 = 0;
  }
  else
  {
    v12 = 0;
  }
  if ( !v12 )
  {
    CalendarStrings = -2147024882;
    goto LABEL_91;
  }
  v68 = 0;
  v13 = 0;
  CalendarStrings = 0;
  do
  {
    if ( v13 >= (unsigned __int64)v4 )
      break;
    CalendarStrings = CFormattedDateTime::AddString(v11, v6[v13], 10, &v4[-v13], v12, v5, &v68);
    v6[v13++] = 0;
  }
  while ( CalendarStrings >= 0 );
  Error = CalendarStrings;
  v14 = 0;
  v15 = v69;
  for ( i = (unsigned __int64)v68; CalendarStrings >= 0; ++v14 )
  {
    if ( v14 >= 7 )
      break;
    *(_QWORD *)v67 = 0;
    CalendarStrings = CFormattedDateTime::ReadCalendarInfo(
                        v15,
                        *((_DWORD *)&CFormattedDateTime::s_aShortDayNameLocaleInfoTypes + v14),
                        (wchar_t **)v67);
    Error = CalendarStrings;
    if ( CalendarStrings >= 0 )
    {
      v17 = *(char **)v67;
      if ( i >= v5 )
      {
        operator delete(*(void **)v67, 0);
        CalendarStrings = -2147418113;
        Error = -2147418113;
      }
      else if ( **(_WORD **)v67 )
      {
        v18 = 56 * i;
        operator delete(*((void **)v12 + 7 * i + 2), 0);
        *((_QWORD *)v12 + 7 * i + 2) = v17;
        v20 = (FormatNode *)*((_QWORD *)v12 + 7 * i + 3);
        if ( v20 )
          FormatNode::`scalar deleting destructor'(v20, v19);
        v21 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v21 )
        {
          *(_DWORD *)v21 = 3;
          v21[1] = 0;
          *((_DWORD *)v21 + 4) = v14 + 1;
          v21[3] = 0;
          CalendarStrings = 0;
          Error = 0;
          v22 = (char *)(v21 + 3);
        }
        else
        {
          CalendarStrings = -2147024882;
          Error = -2147024882;
          v22 = 0;
          v21 = 0;
        }
        *(_QWORD *)((char *)v12 + v18 + 24) = v21;
        *(_QWORD *)((char *)v12 + v18 + 32) = v22;
        if ( CalendarStrings >= 0 )
          v68 = (wchar_t **)++i;
      }
      else
      {
        operator delete(*(void **)v67, 0);
        CalendarStrings = 0;
        Error = 0;
      }
    }
  }
  v23 = 0;
  if ( CalendarStrings >= 0 )
  {
    do
    {
      if ( v23 >= 7 )
        break;
      *(_QWORD *)v67 = 0;
      CalendarStrings = CFormattedDateTime::ReadCalendarInfo(
                          v15,
                          *((_DWORD *)&CFormattedDateTime::s_aLongDayNameLocaleInfoTypes + v23),
                          (wchar_t **)v67);
      if ( CalendarStrings >= 0 )
      {
        v24 = *(char **)v67;
        if ( i >= v5 )
        {
          operator delete(*(void **)v67, 0);
          CalendarStrings = -2147418113;
        }
        else if ( **(_WORD **)v67 )
        {
          v25 = 56 * i;
          operator delete(*((void **)v12 + 7 * i + 2), 0);
          *((_QWORD *)v12 + 7 * i + 2) = v24;
          v27 = (FormatNode *)*((_QWORD *)v12 + 7 * i + 3);
          if ( v27 )
            FormatNode::`scalar deleting destructor'(v27, v26);
          v28 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
          if ( v28 )
          {
            *(_DWORD *)v28 = 4;
            v28[1] = 0;
            *((_DWORD *)v28 + 4) = v23 + 1;
            v28[3] = 0;
            CalendarStrings = 0;
            v29 = (char *)(v28 + 3);
          }
          else
          {
            CalendarStrings = -2147024882;
            v29 = 0;
            v28 = 0;
          }
          *(_QWORD *)((char *)v12 + v25 + 24) = v28;
          *(_QWORD *)((char *)v12 + v25 + 32) = v29;
          if ( CalendarStrings >= 0 )
            v68 = (wchar_t **)++i;
        }
        else
        {
          operator delete(*(void **)v67, 0);
          CalendarStrings = 0;
        }
      }
      ++v23;
    }
    while ( CalendarStrings >= 0 );
    Error = CalendarStrings;
  }
  v30 = 0;
  if ( CalendarStrings >= 0 )
  {
    do
    {
      if ( v30 >= 0xD )
        break;
      *(_QWORD *)v67 = 0;
      CalendarStrings = CFormattedDateTime::ReadCalendarInfo(
                          v15,
                          *((_DWORD *)&CFormattedDateTime::s_aShortMonthNameLocaleInfoTypes + v30),
                          (wchar_t **)v67);
      if ( CalendarStrings >= 0 )
      {
        v31 = *(char **)v67;
        if ( i >= v5 )
        {
          operator delete(*(void **)v67, 0);
          CalendarStrings = -2147418113;
        }
        else if ( **(_WORD **)v67 )
        {
          v32 = 56 * i;
          operator delete(*((void **)v12 + 7 * i + 2), 0);
          *((_QWORD *)v12 + 7 * i + 2) = v31;
          v34 = (FormatNode *)*((_QWORD *)v12 + 7 * i + 3);
          if ( v34 )
            FormatNode::`scalar deleting destructor'(v34, v33);
          v35 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
          if ( v35 )
          {
            *(_DWORD *)v35 = 6;
            v35[1] = 0;
            *((_DWORD *)v35 + 4) = v30 + 1;
            v35[3] = 0;
            CalendarStrings = 0;
            v36 = (char *)(v35 + 3);
          }
          else
          {
            CalendarStrings = -2147024882;
            v36 = 0;
            v35 = 0;
          }
          *(_QWORD *)((char *)v12 + v32 + 24) = v35;
          *(_QWORD *)((char *)v12 + v32 + 32) = v36;
          if ( CalendarStrings >= 0 )
            v68 = (wchar_t **)++i;
        }
        else
        {
          operator delete(*(void **)v67, 0);
          CalendarStrings = 0;
        }
      }
      ++v30;
    }
    while ( CalendarStrings >= 0 );
    Error = CalendarStrings;
  }
  v37 = 0;
  *(_QWORD *)v67 = 0;
  if ( CalendarStrings < 0 )
    goto LABEL_79;
  v38 = v15;
  v39 = (CALID *)((char *)v15 + 184);
  while ( v37 < 0xD )
  {
    v40 = *((_DWORD *)&CFormattedDateTime::s_aLongMonthNameLocaleInfoTypes + v37);
    v39 = (CALID *)((char *)v38 + 184);
    CalendarInfo = GetCalendarInfoEx((LPCWSTR)v38 + 4, *((_DWORD *)v38 + 46), 0, v40, 0, 0, 0);
    cchData = CalendarInfo;
    if ( CalendarInfo <= 0 )
      goto LABEL_111;
    v43 = 2LL * CalendarInfo;
    if ( !is_mul_ok(cchData, 2u) )
      v43 = -1;
    lpCalData = (WCHAR *)operator new[](v43, (const struct std::nothrow_t *)&std::nothrow);
    v45 = lpCalData;
    if ( lpCalData )
    {
      if ( GetCalendarInfoEx((LPCWSTR)v69 + 4, *v39, 0, v40, lpCalData, cchData, 0) )
        goto LABEL_59;
      operator delete(v45, 0);
LABEL_111:
      v45 = 0;
      Error = ResultFromKnownLastError();
      CalendarStrings = Error;
      goto LABEL_112;
    }
    CalendarStrings = -2147024882;
    Error = -2147024882;
LABEL_112:
    if ( CalendarStrings < 0 )
    {
      v38 = v69;
      break;
    }
LABEL_59:
    if ( i >= v5 )
    {
      operator delete(v45, 0);
      CalendarStrings = -2147418113;
      Error = -2147418113;
    }
    else if ( *v45 )
    {
      v46 = 56 * i;
      operator delete(*((void **)v12 + 7 * i + 2), 0);
      *((_QWORD *)v12 + 7 * i + 2) = v45;
      v48 = (FormatNode *)*((_QWORD *)v12 + 7 * i + 3);
      if ( v48 )
        FormatNode::`scalar deleting destructor'(v48, v47);
      v49 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v49 )
      {
        *(_DWORD *)v49 = 7;
        v49[1] = 0;
        *((_DWORD *)v49 + 4) = *(_DWORD *)v67 + 1;
        v49[3] = 0;
        CalendarStrings = 0;
        Error = 0;
        v50 = (char *)(v49 + 3);
      }
      else
      {
        CalendarStrings = -2147024882;
        Error = -2147024882;
        v50 = 0;
        v49 = 0;
      }
      *(_QWORD *)((char *)v12 + v46 + 24) = v49;
      *(_QWORD *)((char *)v12 + v46 + 32) = v50;
      if ( CalendarStrings >= 0 )
        v68 = (wchar_t **)++i;
    }
    else
    {
      operator delete(v45, 0);
      CalendarStrings = 0;
      Error = 0;
    }
    v37 = ++*(_QWORD *)v67;
    v38 = v69;
    if ( CalendarStrings < 0 )
      break;
  }
  if ( CalendarStrings >= 0 )
  {
    v72[0] = 657366;
    v72[1] = 655362;
    v72[2] = 1900546;
    v72[3] = 23;
    memset(v73, 0, sizeof(v73));
    v74 = 0;
    if ( !(unsigned int)ConvertSystemTimeToCalDateTime(v72, *v39, v73) )
    {
      v57 = ResultFromKnownLastError();
      goto LABEL_97;
    }
    v51 = 0;
    while ( v51 < 0xC )
    {
      HIDWORD(v73[0]) = v51 + 1;
      if ( (unsigned int)UpdateCalendarDayOfWeek(v73) )
      {
        if ( (unsigned int)GetCalendarDateFormatEx((char *)v69 + 8, 0, v73, L"ddMMMM", v75, 80) )
        {
          v53 = -1;
          do
            ++v53;
          while ( v75[v53] );
          if ( v53 >= 2 )
          {
            *(_QWORD *)v67 = 0;
            CalendarStrings = StructuredQuery1::CopyStringToCppHeap((StructuredQuery1 *)v76, v67, v52);
            if ( CalendarStrings >= 0 )
            {
              if ( i >= v5 )
              {
                operator delete(*(void **)v67, v56);
                CalendarStrings = -2147418113;
              }
              else if ( **(_WORD **)v67 )
              {
                CalendarStrings = KeywordBuilder::Initialize(
                                    (char *)v12 + 56 * i,
                                    *(_QWORD *)v67,
                                    7,
                                    (unsigned int)(v51 + 1));
                if ( CalendarStrings >= 0 )
                  v68 = (wchar_t **)++i;
              }
              else
              {
                operator delete(*(void **)v67, v56);
                CalendarStrings = 0;
              }
            }
          }
        }
      }
      ++v51;
      if ( CalendarStrings < 0 )
        goto LABEL_78;
    }
    *(_QWORD *)v67 = 0;
    v38 = v69;
    CalendarStrings = CFormattedDateTime::ReadLocaleInfo(v69, 0x28u, (wchar_t **)v67);
    Error = CalendarStrings;
    if ( CalendarStrings >= 0 )
    {
      CalendarStrings = CFormattedDateTime::AddString(v65, *(_QWORD *)v67, 16, 1, v12, v5, &v68);
      Error = CalendarStrings;
      if ( CalendarStrings >= 0 )
      {
        *(_QWORD *)v67 = 0;
        CalendarStrings = CFormattedDateTime::ReadLocaleInfo(v38, 0x29u, (wchar_t **)v67);
        Error = CalendarStrings;
        if ( CalendarStrings >= 0 )
        {
          v57 = CFormattedDateTime::AddString(v58, *(_QWORD *)v67, 16, 2, v12, v5, &v68);
          i = (unsigned __int64)v68;
LABEL_97:
          CalendarStrings = v57;
          Error = v57;
          if ( v57 >= 0 )
          {
            CFormattedDateTime::MixedSort(v38, v12, i);
            if ( i )
            {
              *(_QWORD *)v67 = 0;
              CFormattedDateTime::OrganizeTrie(v38, v12, i, (unsigned __int64 *)v67);
              v59 = *(char **)v67;
              v60 = 32LL * *(_QWORD *)v67;
              if ( !is_mul_ok(*(unsigned __int64 *)v67, 0x20u) )
                v60 = -1;
              v8 = __CFADD__(v60, 8);
              v61 = v60 + 8;
              if ( v8 )
                v61 = -1;
              v62 = (char **)operator new[](v61, (const struct std::nothrow_t *)&std::nothrow);
              *(_QWORD *)v67 = v62;
              if ( v62 )
              {
                *v62 = v59;
                v63 = (struct Keyword *)(v62 + 1);
                `eh vector constructor iterator'(
                  v62 + 1,
                  0x20u,
                  (unsigned __int64)v59,
                  (void (*)(void *))Keyword::Keyword,
                  (void (*)(void *))Keyword::~Keyword);
              }
              else
              {
                v63 = 0;
              }
              if ( v63 )
              {
                *(_QWORD *)v67 = 0;
                CalendarStrings = CFormattedDateTime::CopyToFinalTrie(
                                    v38,
                                    v12,
                                    v63,
                                    (unsigned __int64)v59,
                                    (unsigned __int64 *)v67,
                                    (struct Keyword **)&v68,
                                    (unsigned __int64 *)&v69);
                Error = CalendarStrings;
                if ( CalendarStrings < 0 )
                {
                  Keyword::`vector deleting destructor'(v63, v64);
                }
                else
                {
                  *((_QWORD *)v38 + 40) = v63;
                  *((_QWORD *)v38 + 41) = *(_QWORD *)v67;
                }
              }
              else
              {
                CalendarStrings = -2147024882;
LABEL_78:
                Error = CalendarStrings;
              }
            }
          }
        }
      }
    }
  }
LABEL_79:
  `eh vector destructor iterator'(v12, 0x38u, *((_QWORD *)v12 - 1), (void (*)(void *))KeywordBuilder::~KeywordBuilder);
  operator delete[]((char *)v12 - 8, (const struct std::nothrow_t *)(56LL * *((_QWORD *)v12 - 1) + 8));
  v4 = v70;
  v6 = v71;
  v3 = 0;
LABEL_80:
  v54 = 0;
  if ( v4 )
  {
    do
      operator delete((void *)v6[v54++], (const struct std::nothrow_t *)2);
    while ( v54 < (unsigned __int64)v4 );
    CalendarStrings = Error;
  }
  operator delete(v6, v3);
  return (unsigned int)CalendarStrings;
}

```

## disassembly

```asm
0x18001d250  push    rbp
0x18001d252  push    rbx
0x18001d253  push    rsi
0x18001d254  push    rdi
0x18001d255  push    r12
0x18001d257  push    r13
0x18001d259  push    r14
0x18001d25b  push    r15
0x18001d25d  lea     rbp, [rsp-68h]
0x18001d262  sub     rsp, 168h
0x18001d269  mov     rax, cs:__security_cookie
0x18001d270  xor     rax, rsp
0x18001d273  mov     [rbp+0A0h+var_50], rax
0x18001d277  mov     [rsp+1A0h+var_148], rcx
0x18001d27c  xor     eax, eax
0x18001d27e  mov     [rsp+1A0h+var_150], rax
0x18001d283  mov     qword ptr [rsp+1A0h+var_158], rax
0x18001d288  lea     r9, [rsp+1A0h+var_158]; unsigned __int64 *
0x18001d28d  lea     r8, [rsp+1A0h+var_150]; wchar_t ***
0x18001d292  call    ?GetCalendarStrings@CFormattedDateTime@@AEAAJKPEAPEAPEA_WPEA_K@Z; CFormattedDateTime::GetCalendarStrings(ulong,wchar_t * * *,unsigned __int64 *)
0x18001d297  mov     edi, eax
0x18001d299  xor     edx, edx
0x18001d29b  test    eax, eax
0x18001d29d  js      loc_18001D8B8
0x18001d2a3  mov     r15, qword ptr [rsp+1A0h+var_158]
0x18001d2a8  mov     [rsp+1A0h+var_140], r15
0x18001d2ad  lea     r14, [r15+36h]
0x18001d2b1  mov     r12, [rsp+1A0h+var_150]
0x18001d2b6  mov     [rsp+1A0h+var_138], r12
0x18001d2bb  cmp     r14, r15
0x18001d2be  jb      loc_18001D93E
0x18001d2c4  lea     ebx, [rdx+38h]
0x18001d2c7  mov     eax, ebx
0x18001d2c9  mul     r14
0x18001d2cc  lea     rcx, [rbx-39h]
0x18001d2d0  cmovb   rax, rcx
0x18001d2d4  add     rax, 8
0x18001d2d8  cmovb   rax, rcx
0x18001d2dc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d2e3  mov     rcx, rax; unsigned __int64
0x18001d2e6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001d2eb  mov     qword ptr [rsp+1A0h+var_158], rax
0x18001d2f0  lea     rcx, ??1KeywordBuilder@@QEAA@XZ; KeywordBuilder::~KeywordBuilder(void)
0x18001d2f7  xor     edx, edx
0x18001d2f9  test    rax, rax
0x18001d2fc  jz      loc_18001DB39
0x18001d302  mov     [rax], r14
0x18001d305  lea     rsi, [rax+8]
0x18001d309  mov     [rsp+1A0h+lpCalData], rcx; void (*)(void *)
0x18001d30e  lea     r9, ??0KeywordBuilder@@QEAA@XZ; void (*)(void *)
0x18001d315  mov     r8, r14; unsigned __int64
0x18001d318  mov     edx, ebx; unsigned __int64
0x18001d31a  mov     rcx, rsi; void *
0x18001d31d  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18001d322  xor     edx, edx
0x18001d324  test    rsi, rsi
0x18001d327  jz      loc_18001DCA5
0x18001d32d  mov     [rsp+1A0h+var_150], rdx
0x18001d332  mov     rbx, rdx
0x18001d335  mov     edi, edx
0x18001d337  cmp     rbx, r15
0x18001d33a  jnb     short loc_18001D374
0x18001d33c  mov     r9, r15
0x18001d33f  sub     r9, rbx
0x18001d342  lea     rax, [rsp+1A0h+var_150]
0x18001d347  mov     [rsp+1A0h+lpValue], rax
0x18001d34c  mov     qword ptr [rsp+1A0h+cchData], r14
0x18001d351  mov     [rsp+1A0h+lpCalData], rsi
0x18001d356  mov     r8d, 0Ah
0x18001d35c  mov     rdx, [r12+rbx*8]
0x18001d360  call    ?AddString@CFormattedDateTime@@AEAAJPEA_WW4tagFORMAT_OPTION@@_KPEAVKeywordBuilder@@2AEA_K@Z; CFormattedDateTime::AddString(wchar_t *,tagFORMAT_OPTION,unsigned __int64,KeywordBuilder *,unsigned __int64,unsigned __int64 &)
0x18001d365  mov     edi, eax
0x18001d367  xor     edx, edx
0x18001d369  mov     [r12+rbx*8], rdx
0x18001d36d  inc     rbx
0x18001d370  test    eax, eax
0x18001d372  jns     short loc_18001D337
0x18001d374  mov     [rsp+1A0h+var_160], edi
0x18001d378  mov     r12, rdx
0x18001d37b  lea     rax, __ImageBase
0x18001d382  test    edi, edi
0x18001d384  mov     r13, [rsp+1A0h+var_148]
0x18001d389  mov     rbx, [rsp+1A0h+var_150]
0x18001d38e  js      loc_18001D46B
0x18001d394  cmp     r12, 7
0x18001d398  jnb     loc_18001D46B
0x18001d39e  mov     qword ptr [rsp+1A0h+var_158], rdx
0x18001d3a3  lea     r8, [rsp+1A0h+var_158]; wchar_t **
0x18001d3a8  mov     edx, ds:rva ?s_aShortDayNameLocaleInfoTypes@CFormattedDateTime@@0QBKB[rax+r12*4]; unsigned int
0x18001d3b0  mov     rcx, r13; this
0x18001d3b3  call    ?ReadCalendarInfo@CFormattedDateTime@@AEAAJKPEAPEA_W@Z; CFormattedDateTime::ReadCalendarInfo(ulong,wchar_t * *)
0x18001d3b8  mov     edi, eax
0x18001d3ba  mov     [rsp+1A0h+var_160], eax
0x18001d3be  xor     edx, edx; struct std::nothrow_t *
0x18001d3c0  test    eax, eax
0x18001d3c2  js      loc_18001D452
0x18001d3c8  mov     rdi, qword ptr [rsp+1A0h+var_158]
0x18001d3cd  cmp     rbx, r14
0x18001d3d0  jnb     loc_18001DC2D
0x18001d3d6  cmp     [rdi], dx
0x18001d3d9  jz      loc_18001DB14
0x18001d3df  imul    r15, rbx, 38h ; '8'
0x18001d3e3  mov     rcx, [r15+rsi+10h]; void *
0x18001d3e8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001d3ed  mov     [r15+rsi+10h], rdi
0x18001d3f2  mov     rcx, [r15+rsi+18h]; this
0x18001d3f7  test    rcx, rcx
0x18001d3fa  jnz     loc_18001DB9E
0x18001d400  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d407  mov     ecx, 20h ; ' '; unsigned __int64
0x18001d40c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001d411  xor     edx, edx
0x18001d413  test    rax, rax
0x18001d416  jz      loc_18001DB8A
0x18001d41c  mov     dword ptr [rax], 3
0x18001d422  mov     [rax+8], rdx
0x18001d426  lea     ecx, [r12+1]
0x18001d42b  mov     [rax+10h], ecx
0x18001d42e  mov     [rax+18h], rdx
0x18001d432  mov     edi, edx
0x18001d434  mov     [rsp+1A0h+var_160], edx
0x18001d438  lea     rcx, [rax+18h]
0x18001d43c  mov     [r15+rsi+18h], rax
0x18001d441  mov     [r15+rsi+20h], rcx
0x18001d446  test    edi, edi
0x18001d448  js      short loc_18001D452
0x18001d44a  inc     rbx
0x18001d44d  mov     [rsp+1A0h+var_150], rbx
0x18001d452  inc     r12
0x18001d455  test    edi, edi
0x18001d457  lea     rax, __ImageBase
0x18001d45e  jns     loc_18001D394
0x18001d464  lea     rax, __ImageBase
0x18001d46b  mov     r15, rdx
0x18001d46e  test    edi, edi
0x18001d470  js      loc_18001D541
0x18001d476  cmp     r15, 7
0x18001d47a  jnb     loc_18001D53D
0x18001d480  mov     qword ptr [rsp+1A0h+var_158], rdx
0x18001d485  lea     r8, [rsp+1A0h+var_158]; wchar_t **
0x18001d48a  mov     edx, ds:rva ?s_aLongDayNameLocaleInfoTypes@CFormattedDateTime@@0QBKB[rax+r15*4]; unsigned int
0x18001d492  mov     rcx, r13; this
0x18001d495  call    ?ReadCalendarInfo@CFormattedDateTime@@AEAAJKPEAPEA_W@Z; CFormattedDateTime::ReadCalendarInfo(ulong,wchar_t * *)
0x18001d49a  mov     edi, eax
0x18001d49c  xor     edx, edx; struct std::nothrow_t *
0x18001d49e  test    eax, eax
0x18001d4a0  js      loc_18001D52B
0x18001d4a6  mov     rdi, qword ptr [rsp+1A0h+var_158]
0x18001d4ab  cmp     rbx, r14
0x18001d4ae  jnb     loc_18001DC45
0x18001d4b4  cmp     [rdi], dx
0x18001d4b7  jz      loc_18001DAD7
0x18001d4bd  imul    r12, rbx, 38h ; '8'
0x18001d4c1  mov     rcx, [r12+rsi+10h]; void *
0x18001d4c6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001d4cb  mov     [r12+rsi+10h], rdi
0x18001d4d0  mov     rcx, [r12+rsi+18h]; this
0x18001d4d5  test    rcx, rcx
0x18001d4d8  jnz     loc_18001DBA8
0x18001d4de  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d4e5  mov     ecx, 20h ; ' '; unsigned __int64
0x18001d4ea  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001d4ef  xor     edx, edx
0x18001d4f1  test    rax, rax
0x18001d4f4  jz      loc_18001DB7A
0x18001d4fa  mov     dword ptr [rax], 4
0x18001d500  mov     [rax+8], rdx
0x18001d504  lea     ecx, [r15+1]
0x18001d508  mov     [rax+10h], ecx
0x18001d50b  mov     [rax+18h], rdx
0x18001d50f  mov     edi, edx
0x18001d511  lea     rcx, [rax+18h]
0x18001d515  mov     [r12+rsi+18h], rax
0x18001d51a  mov     [r12+rsi+20h], rcx
0x18001d51f  test    edi, edi
0x18001d521  js      short loc_18001D52B
0x18001d523  inc     rbx
0x18001d526  mov     [rsp+1A0h+var_150], rbx
0x18001d52b  inc     r15
0x18001d52e  test    edi, edi
0x18001d530  lea     rax, __ImageBase
0x18001d537  jns     loc_18001D476
0x18001d53d  mov     [rsp+1A0h+var_160], edi
0x18001d541  mov     r12, rdx
0x18001d544  test    edi, edi
0x18001d546  js      loc_18001D618
0x18001d54c  cmp     r12, 0Dh
0x18001d550  jnb     loc_18001D614
0x18001d556  mov     qword ptr [rsp+1A0h+var_158], rdx
0x18001d55b  lea     r8, [rsp+1A0h+var_158]; wchar_t **
0x18001d560  lea     rax, __ImageBase
0x18001d567  mov     edx, ds:rva ?s_aShortMonthNameLocaleInfoTypes@CFormattedDateTime@@0QBKB[rax+r12*4]; unsigned int
0x18001d56f  mov     rcx, r13; this
0x18001d572  call    ?ReadCalendarInfo@CFormattedDateTime@@AEAAJKPEAPEA_W@Z; CFormattedDateTime::ReadCalendarInfo(ulong,wchar_t * *)
0x18001d577  mov     edi, eax
0x18001d579  xor     edx, edx; struct std::nothrow_t *
0x18001d57b  test    eax, eax
0x18001d57d  js      loc_18001D609
0x18001d583  mov     rdi, qword ptr [rsp+1A0h+var_158]
0x18001d588  cmp     rbx, r14
0x18001d58b  jnb     loc_18001DC59
0x18001d591  cmp     [rdi], dx
0x18001d594  jz      loc_18001D961
0x18001d59a  imul    r15, rbx, 38h ; '8'
0x18001d59e  mov     rcx, [r15+rsi+10h]; void *
0x18001d5a3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001d5a8  mov     [r15+rsi+10h], rdi
0x18001d5ad  mov     rcx, [r15+rsi+18h]; this
0x18001d5b2  test    rcx, rcx
0x18001d5b5  jnz     loc_18001DBB2
0x18001d5bb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d5c2  mov     ecx, 20h ; ' '; unsigned __int64
0x18001d5c7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001d5cc  xor     edx, edx
0x18001d5ce  test    rax, rax
0x18001d5d1  jz      loc_18001DB5D
0x18001d5d7  mov     dword ptr [rax], 6
0x18001d5dd  mov     [rax+8], rdx
0x18001d5e1  lea     ecx, [r12+1]
0x18001d5e6  mov     [rax+10h], ecx
0x18001d5e9  mov     [rax+18h], rdx
0x18001d5ed  mov     edi, edx
0x18001d5ef  lea     rcx, [rax+18h]
0x18001d5f3  mov     [r15+rsi+18h], rax
0x18001d5f8  mov     [r15+rsi+20h], rcx
0x18001d5fd  test    edi, edi
0x18001d5ff  js      short loc_18001D609
0x18001d601  inc     rbx
0x18001d604  mov     [rsp+1A0h+var_150], rbx
0x18001d609  inc     r12
0x18001d60c  test    edi, edi
0x18001d60e  jns     loc_18001D54C
0x18001d614  mov     [rsp+1A0h+var_160], edi
0x18001d618  mov     rax, rdx
0x18001d61b  mov     qword ptr [rsp+1A0h+var_158], rdx
0x18001d620  test    edi, edi
0x18001d622  js      loc_18001D856
0x18001d628  mov     r15, r13
0x18001d62b  add     r13, 0B8h
0x18001d632  cmp     rax, 0Dh
0x18001d636  jnb     loc_18001D784
0x18001d63c  lea     rcx, __ImageBase
0x18001d643  mov     r12d, ds:rva ?s_aLongMonthNameLocaleInfoTypes@CFormattedDateTime@@0QBKB[rcx+rax*4]; ulong const near * const CFormattedDateTime::s_aLongMonthNameLocaleInfoTypes ...
0x18001d64b  lea     rcx, [r15+8]; lpLocaleName
0x18001d64f  lea     r13, [r15+0B8h]
0x18001d656  mov     [rsp+1A0h+lpValue], rdx; lpValue
0x18001d65b  mov     [rsp+1A0h+cchData], edx; cchData
0x18001d65f  mov     [rsp+1A0h+lpCalData], rdx; lpCalData
0x18001d664  mov     r9d, r12d; CalType
0x18001d667  xor     r8d, r8d; lpReserved
0x18001d66a  mov     edx, [r13+0]; Calendar
0x18001d66e  call    cs:__imp_GetCalendarInfoEx
0x18001d674  movsxd  rdi, eax
0x18001d677  xor     eax, eax
0x18001d679  test    edi, edi
0x18001d67b  jle     loc_18001DAF2
0x18001d681  mov     eax, 2
0x18001d686  mul     rdi
0x18001d689  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001d690  cmovb   rax, rcx
0x18001d694  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d69b  mov     rcx, rax; unsigned __int64
0x18001d69e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001d6a3  mov     r15, rax
0x18001d6a6  xor     edx, edx
0x18001d6a8  test    rax, rax
0x18001d6ab  jz      loc_18001DC6D
0x18001d6b1  mov     [rsp+1A0h+lpValue], rdx; lpValue
0x18001d6b6  mov     [rsp+1A0h+cchData], edi; cchData
0x18001d6ba  mov     [rsp+1A0h+lpCalData], rax; lpCalData
0x18001d6bf  mov     r9d, r12d; CalType
0x18001d6c2  xor     r8d, r8d; lpReserved
0x18001d6c5  mov     edx, [r13+0]; Calendar
0x18001d6c9  mov     rcx, [rsp+1A0h+var_148]
0x18001d6ce  add     rcx, 8; lpLocaleName
0x18001d6d2  call    cs:__imp_GetCalendarInfoEx
0x18001d6d8  xor     edx, edx; struct std::nothrow_t *
0x18001d6da  test    eax, eax
0x18001d6dc  jz      loc_18001DAE8
0x18001d6e2  cmp     rbx, r14
0x18001d6e5  jnb     loc_18001DC7B
0x18001d6eb  cmp     [r15], dx
0x18001d6ef  jz      loc_18001D94C
0x18001d6f5  imul    r12, rbx, 38h ; '8'
0x18001d6f9  mov     rcx, [r12+rsi+10h]; void *
0x18001d6fe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001d703  mov     [r12+rsi+10h], r15
0x18001d708  mov     rcx, [r12+rsi+18h]; this
0x18001d70d  test    rcx, rcx
0x18001d710  jnz     loc_18001DBBC
0x18001d716  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d71d  mov     ecx, 20h ; ' '; unsigned __int64
0x18001d722  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001d727  xor     edx, edx
0x18001d729  test    rax, rax
0x18001d72c  jz      loc_18001DB41
0x18001d732  mov     dword ptr [rax], 7
0x18001d738  mov     [rax+8], rdx
0x18001d73c  mov     rcx, qword ptr [rsp+1A0h+var_158]
0x18001d741  inc     ecx
  ... truncated ...
```
