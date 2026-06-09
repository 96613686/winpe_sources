# Mso::SVG::StylableContext::SetFontFamily(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &&)

- ea: `0x180111134`
- end: `0x180111c78`
- name: `?SetFontFamily@StylableContext@SVG@Mso@@AEAAX$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `2884`
- prototype: ``
- caller_count: `2`
- callee_count: `22`
- tags: `broker_com_uri`

## callers

- `0x18006a98c`
- `0x1801167c4`

## callees

- `0x180004390`
- `0x180007360`
- `0x1800079f8`
- `0x1800081d0`
- `0x1800085e0`
- `0x180009068`
- `0x180009180`
- `0x1800091d0`
- `0x18000c5b0`
- `0x18000d260`
- `0x18001a0c0`
- `0x18001c888`
- `0x1800f89e8`
- `0x18010ee64`
- `0x180110dc8`
- `0x180111024`
- `0x180111134`
- `0x1801143e4`
- `0x180114428`
- `0x180114a24`
- `0x1801191a4`
- `0x18013d650`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180111c71`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180111c71`
- `MSVCP140!??1?$basic_iostream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x18011180f`
- `MSVCP140!??1?$basic_iostream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x180111851`
- `MSVCP140!??1?$basic_iostream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x18011180f`
- `MSVCP140!??1?$basic_iostream@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x180111851`
- `MSVCP140!??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x180111819`
- `MSVCP140!??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x18011185e`
- `MSVCP140!??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x180111819`
- `MSVCP140!??1?$basic_ios@_WU?$char_traits@_W@std@@@std@@UEAA@XZ` at `0x18011185e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801115ee`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180111934`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801115ee`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180111934`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180111a28`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180111bdf`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180111a28`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180111bdf`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1801111c8`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x180111221`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1801112b4`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x180111944`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1801111c8`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x180111221`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x1801112b4`
- `api-ms-win-crt-string-l1-1-0!iswspace` at `0x180111944`
- `api-ms-win-crt-string-l1-1-0!tolower` at `0x180111295`
- `api-ms-win-crt-string-l1-1-0!tolower` at `0x18011132c`
- `api-ms-win-crt-string-l1-1-0!tolower` at `0x180111295`
- `api-ms-win-crt-string-l1-1-0!tolower` at `0x18011132c`

## string_xrefs

- `0x180111775`: `Courier New`
- `0x18011164e`: `Comic Sans MS`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Mso::SVG::StylableContext::SetFontFamily(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // r14
  int v3; // r13d
  wint_t *v4; // rdi
  bool v5; // cc
  _QWORD *v6; // rcx
  const char *v7; // rbx
  char v8; // r12
  wint_t *v9; // rsi
  wint_t *v10; // r15
  __m128i si128; // xmm6
  wint_t *v12; // rsi
  int v13; // r8d
  int v14; // r9d
  int v15; // ecx
  unsigned int v16; // eax
  char v17; // si
  int v18; // ecx
  __int64 v19; // rdx
  unsigned int v20; // eax
  __int128 *v21; // rdx
  __int128 *v22; // rdx
  size_t v23; // r8
  const wchar_t *v24; // rcx
  wchar_t *v25; // rax
  size_t v26; // rdx
  __m128i *v27; // rdx
  wchar_t **v28; // rcx
  unsigned __int64 v29; // rax
  void *v30; // rcx
  wchar_t **v31; // rcx
  __m128i *v32; // rdx
  __int64 v33; // rdx
  size_t v34; // rax
  wchar_t *v35; // rcx
  Mso::SVG::Style *v36; // rcx
  struct Mso::SVG::Style *v37; // rbx
  __int64 v38; // rdi
  __int128 *v39; // rbx
  __int128 *v40; // rax
  __int64 v41; // rcx
  __m128i v42; // xmm0
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // rax
  __int128 v47; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v48; // [rsp+58h] [rbp-B0h]
  wint_t *v49; // [rsp+60h] [rbp-A8h] BYREF
  const char *v50; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v51; // [rsp+70h] [rbp-98h]
  _QWORD v52[2]; // [rsp+78h] [rbp-90h] BYREF
  char v53[8]; // [rsp+88h] [rbp-80h] BYREF
  char v54[8]; // [rsp+90h] [rbp-78h] BYREF
  char v55[120]; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v56[104]; // [rsp+110h] [rbp+8h] BYREF
  _QWORD v57[2]; // [rsp+178h] [rbp+70h] BYREF
  char v58[8]; // [rsp+188h] [rbp+80h] BYREF
  char v59[8]; // [rsp+190h] [rbp+88h] BYREF
  char v60[120]; // [rsp+198h] [rbp+90h] BYREF
  char v61[104]; // [rsp+210h] [rbp+108h] BYREF
  __int128 v62; // [rsp+278h] [rbp+170h] BYREF
  __m128i v63; // [rsp+288h] [rbp+180h]
  __int128 v64; // [rsp+298h] [rbp+190h]
  __m128i v65; // [rsp+2A8h] [rbp+1A0h]
  __int128 v66; // [rsp+2B8h] [rbp+1B0h] BYREF
  __m128i v67; // [rsp+2C8h] [rbp+1C0h]
  wchar_t *S1[2]; // [rsp+2D8h] [rbp+1D0h] BYREF
  size_t N[2]; // [rsp+2E8h] [rbp+1E0h]
  __int128 v70; // [rsp+2F8h] [rbp+1F0h]
  __m128i v71; // [rsp+308h] [rbp+200h]

  v2 = a2;
  v51 = a1;
  v3 = 0;
  LODWORD(v49) = 0;
  v47 = 0;
  v48 = 0;
  v4 = (wint_t *)a2;
  v5 = a2[3] <= 7u;
  if ( a2[3] > 7u )
    v4 = (wint_t *)*a2;
  v49 = v4;
  v6 = a2;
  if ( !v5 )
    v6 = (_QWORD *)*a2;
  v7 = (char *)v6 + 2 * a2[2];
  v50 = v7;
  v8 = 1;
  v9 = v4;
  if ( v4 != (wint_t *)v7 )
  {
    v10 = v4;
    do
    {
      if ( !iswspace(*v4) )
        break;
      v4 = v10 + 1;
      v9 = v4;
      v49 = ++v10;
    }
    while ( v4 != (wint_t *)v7 );
  }
  if ( v9 == (wint_t *)v7 )
  {
LABEL_91:
    if ( (_QWORD)v47 != *((_QWORD *)&v47 + 1) )
    {
      v36 = *(Mso::SVG::Style **)(v51 + 152);
      if ( !v36 )
      {
        CrashWithRecovery(0x1E3C3840u, 0);
        JUMPOUT(0x180111C77LL);
      }
      v37 = Mso::SVG::Style::EnsureWritable(v36);
      Mso::SVG::Style::EnsureWritable(v37);
      v38 = *((_QWORD *)v37 + 2);
      v39 = (__int128 *)(v38 + 768);
      if ( *(_BYTE *)(v38 + 792) )
      {
        if ( v39 != &v47 )
        {
          std::vector<std::wstring>::_Tidy(v38 + 768);
          *(_QWORD *)v39 = v47;
          *(_QWORD *)(v38 + 776) = *((_QWORD *)&v47 + 1);
          *(_QWORD *)(v38 + 784) = v48;
          v47 = 0;
          v48 = 0;
        }
      }
      else
      {
        v43 = v48;
        v48 = 0;
        v44 = *((_QWORD *)&v47 + 1);
        v45 = v47;
        v47 = 0u;
        *(_QWORD *)v39 = v45;
        *(_QWORD *)(v38 + 776) = v44;
        *(_QWORD *)(v38 + 784) = v43;
        *(_BYTE *)(v38 + 792) = 1;
      }
      *(_DWORD *)(v38 + 800) = 3;
    }
    return std::vector<std::wstring>::_Tidy(&v47);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    if ( !v8 )
    {
      if ( *v4 != 44 )
        return std::vector<std::wstring>::_Tidy(&v47);
      v49 = ++v4;
      if ( v4 != (wint_t *)v7 )
      {
        v12 = v4 + 1;
        do
        {
          if ( !iswspace(*v4) )
            break;
          v4 = v12;
          v49 = v12++;
        }
        while ( v4 != (wint_t *)v7 );
      }
    }
    if ( *v4 != 34 && *v4 != 39 )
      break;
    *(_OWORD *)S1 = 0;
    N[0] = 0;
    N[1] = 7;
    LOWORD(S1[0]) = 0;
    if ( !(unsigned __int8)sub_180111024(&v49, &v50, S1) )
    {
      std::wstring::~wstring(S1);
      return std::vector<std::wstring>::_Tidy(&v47);
    }
    if ( N[0] )
    {
      v33 = *((_QWORD *)&v47 + 1);
      if ( *((_QWORD *)&v47 + 1) != v48 )
      {
        **((_OWORD **)&v47 + 1) = *(_OWORD *)S1;
        *(_OWORD *)(v33 + 16) = *(_OWORD *)N;
        v34 = 7;
        LOWORD(S1[0]) = 0;
        *((_QWORD *)&v47 + 1) += 32LL;
        goto LABEL_82;
      }
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v47, *((_QWORD *)&v47 + 1), S1);
    }
    v34 = N[1];
LABEL_82:
    if ( v34 > 7 )
    {
      v35 = S1[0];
      if ( 2 * v34 + 2 >= 0x1000 )
      {
        v35 = (wchar_t *)*((_QWORD *)S1[0] - 1);
        if ( (unsigned __int64)((char *)S1[0] - (char *)v35 - 8) > 0x1F )
          _invoke_watson(0, 0, 0, 0, 0);
      }
      free(v35);
    }
    v4 = v49;
LABEL_89:
    while ( v4 != (wint_t *)v7 && iswspace(*v4) )
      v49 = ++v4;
    v8 = 0;
    if ( v4 == (wint_t *)v7 )
      goto LABEL_91;
  }
  if ( (unsigned __int8)sub_18010EE64(&v49, &v50) )
  {
    std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v57);
    std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v52);
    std::operator<<<wchar_t,std::char_traits<wchar_t>>(v53, *v4);
    v15 = *v4++;
    v49 = v4;
    v16 = tolower(v15);
    std::operator<<<wchar_t,std::char_traits<wchar_t>>(v58, v16);
    v17 = 0;
    while ( v4 != (wint_t *)v7 )
    {
      if ( iswspace(*v4) )
      {
        v17 = 1;
      }
      else
      {
        v18 = *v4;
        if ( (unsigned __int16)(v18 - 46) <= 0x32u
          && (v19 = 0x5E0000007F003LL, _bittest64(&v19, (unsigned int)(v18 - 46)))
          || (unsigned __int16)v18 <= 0x2Cu
          || (unsigned __int16)(v18 - 123) <= 0x25u )
        {
          if ( (__int64)((v7 - (const char *)v4) & 0xFFFFFFFFFFFFFFFEuLL) < 4 || *v4 != 92 || v4[1] == 10 )
            break;
          v66 = 0;
          v67 = si128;
          LOWORD(v66) = 0;
          if ( !(unsigned __int8)sub_180110DC8(&v49, &v50, &v66) )
          {
            std::wstring::~wstring(&v66);
            std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(v52);
            std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(v57);
            return std::vector<std::wstring>::_Tidy(&v47);
          }
          v21 = &v66;
          if ( v67.m128i_i64[1] > 7uLL )
            v21 = (__int128 *)v66;
          std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(v53, v21, v67.m128i_i64[0]);
          v22 = &v66;
          if ( v67.m128i_i64[1] > 7uLL )
            v22 = (__int128 *)v66;
          std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(v58, v22, v67.m128i_i64[0]);
          v4 = v49;
          std::wstring::~wstring(&v66);
          if ( v4 == (wint_t *)v7 )
            break;
        }
        else
        {
          if ( v17 )
          {
            std::operator<<<wchar_t,std::char_traits<wchar_t>>(v53, L" ");
            std::operator<<<wchar_t,std::char_traits<wchar_t>>(v58, L" ");
            v17 = 0;
          }
          std::operator<<<wchar_t,std::char_traits<wchar_t>>(v53, *v4);
          v20 = tolower(*v4);
          std::operator<<<wchar_t,std::char_traits<wchar_t>>(v58, v20);
        }
      }
      v49 = ++v4;
    }
    std::wstringbuf::str(v59, S1);
    v3 |= 1u;
    v23 = N[0];
    v24 = (const wchar_t *)S1;
    v25 = S1[0];
    v26 = N[1];
    if ( N[1] > 7 )
      v24 = S1[0];
    if ( N[0] == 5 )
    {
      if ( !wmemcmp(v24, L"serif", 5u) )
      {
        v62 = 0;
        v63 = 0;
        std::wstring::_Construct<1,wchar_t *>(&v62, L"Times New Roman", 15);
        v27 = (__m128i *)*((_QWORD *)&v47 + 1);
        if ( *((_QWORD *)&v47 + 1) == v48 )
        {
LABEL_54:
          std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v47, v27, &v62);
          v29 = v63.m128i_u64[1];
          goto LABEL_55;
        }
LABEL_53:
        **((_OWORD **)&v47 + 1) = v62;
        v27[1] = v63;
        v29 = 7;
        LOWORD(v62) = 0;
        *((_QWORD *)&v47 + 1) += 32LL;
LABEL_55:
        if ( v29 > 7 )
        {
          v30 = (void *)v62;
          if ( 2 * v29 + 2 >= 0x1000 )
          {
            v30 = *(void **)(v62 - 8);
            if ( (unsigned __int64)(v62 - (_QWORD)v30 - 8) > 0x1F )
              _invoke_watson(0, 0, 0, 0, 0);
          }
          free(v30);
        }
LABEL_75:
        std::wstring::~wstring(S1);
        *(_QWORD *)((char *)v52 + *(int *)(v52[0] + 4LL)) = &std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vftable';
        *(_DWORD *)((char *)&v51 + *(int *)(v52[0] + 4LL) + 4) = *(_DWORD *)(v52[0] + 4LL) - 152;
        std::wstringbuf::~wstringbuf(v54);
        std::wiostream::~basic_iostream<wchar_t,std::char_traits<wchar_t>>(v55);
        std::wios::~wios<wchar_t,std::char_traits<wchar_t>>(v56);
        *(_QWORD *)((char *)v57 + *(int *)(v57[0] + 4LL)) = &std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vftable';
        *(_DWORD *)&v56[*(int *)(v57[0] + 4LL) + 100] = *(_DWORD *)(v57[0] + 4LL) - 152;
        std::wstringbuf::~wstringbuf(v59);
        std::wiostream::~basic_iostream<wchar_t,std::char_traits<wchar_t>>(v60);
        std::wios::~wios<wchar_t,std::char_traits<wchar_t>>(v61);
        goto LABEL_89;
      }
      v26 = N[1];
      v23 = N[0];
      v25 = S1[0];
    }
    v28 = S1;
    if ( v26 > 7 )
      v28 = (wchar_t **)v25;
    if ( v23 == 10 )
    {
      if ( !wmemcmp((const wchar_t *)v28, L"sans-serif", 0xAu) )
      {
        v62 = 0;
        v63 = 0;
        std::wstring::_Construct<1,wchar_t *>(&v62, L"Arial", 5);
        v27 = (__m128i *)*((_QWORD *)&v47 + 1);
        if ( *((_QWORD *)&v47 + 1) == v48 )
          goto LABEL_54;
        goto LABEL_53;
      }
      v26 = N[1];
      v23 = N[0];
      v25 = S1[0];
    }
    v31 = S1;
    if ( v26 > 7 )
      v31 = (wchar_t **)v25;
    if ( v23 == 7 && !wmemcmp((const wchar_t *)v31, L"cursive", 7u) )
    {
      v62 = 0;
      v63 = 0;
      std::wstring::_Construct<1,wchar_t *>(&v62, L"Comic Sans MS", 13);
      v32 = (__m128i *)*((_QWORD *)&v47 + 1);
      if ( *((_QWORD *)&v47 + 1) != v48 )
        goto LABEL_65;
LABEL_66:
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v47, v32, &v62);
    }
    else if ( (unsigned __int8)std::operator==<wchar_t>(S1, L"fantasy") )
    {
      v62 = 0;
      v63 = 0;
      std::wstring::_Construct<1,wchar_t *>(&v62, L"Gabriola", 8);
      v32 = (__m128i *)*((_QWORD *)&v47 + 1);
      if ( *((_QWORD *)&v47 + 1) == v48 )
        goto LABEL_66;
LABEL_65:
      **((_OWORD **)&v47 + 1) = v62;
      v32[1] = v63;
      v63 = si128;
      LOWORD(v62) = 0;
      *((_QWORD *)&v47 + 1) += 32LL;
    }
    else
    {
      if ( (unsigned __int8)std::operator==<wchar_t>(S1, L"monospace") )
      {
        v62 = 0;
        v63 = 0;
        std::wstring::_Construct<1,wchar_t *>(&v62, L"Courier New", 11);
      }
      else
      {
        std::wstringbuf::str(v54, &v62);
        v3 |= 2u;
      }
      std::vector<std::wstring>::push_back(&v47, &v62);
    }
    std::wstring::~wstring(&v62);
    goto LABEL_75;
  }
  v66 = 0;
  v67 = 0;
  if ( v4 == (wint_t *)v7 )
  {
    v67 = si128;
    LOWORD(v66) = 0;
  }
  else
  {
    std::wstring::_Construct<1,wchar_t *>(&v66, v4, (v7 - (const char *)v4) >> 1);
  }
  v40 = &v66;
  if ( v67.m128i_i64[1] > 7uLL )
    v40 = (__int128 *)v66;
  S1[0] = (wchar_t *)&Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
  S1[1] = (wchar_t *)"fontFamily_it";
  N[0] = (size_t)v40;
  LOWORD(N[1]) = 16;
  v70 = 0;
  v71 = si128;
  LOWORD(v70) = 0;
  if ( v2[3] > 7u )
    v2 = (_QWORD *)*v2;
  *(_QWORD *)&v62 = &Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable';
  *((_QWORD *)&v62 + 1) = "fontFamily";
  v63.m128i_i64[0] = (__int64)v2;
  v63.m128i_i16[4] = 16;
  v64 = 0;
  v65 = si128;
  LOWORD(v64) = 0;
  v50 = "Unexpected character in SVG font family.";
  Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
    19174149,
    (unsigned int)&Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>::`vftable',
    v13,
    v14,
    (__int64)&v50,
    (__int64)&v62,
    (__int64)S1);
  if ( v65.m128i_i64[1] > 7uLL )
    std::wstring::_Deallocate_for_capacity(v41, v64);
  *(_QWORD *)&v64 = 19937;
  v42 = _mm_load_si128((const __m128i *)&_xmm);
  v65 = v42;
  if ( v71.m128i_i64[1] > 7uLL )
  {
    std::wstring::_Deallocate_for_capacity(v41, v70);
    v42 = _mm_load_si128((const __m128i *)&_xmm);
  }
  *(_QWORD *)&v70 = 19937;
  v71 = v42;
  if ( v67.m128i_i64[1] > 7uLL )
    std::wstring::_Deallocate_for_capacity(v41, v66);
  return std::vector<std::wstring>::_Tidy(&v47);
}

```

## disassembly

```asm
0x180111134  mov     rax, rsp
0x180111137  mov     [rax+10h], rbx
0x18011113b  mov     [rax+18h], rsi
0x18011113f  mov     [rax+20h], rdi
0x180111143  push    rbp
0x180111144  push    r12
0x180111146  push    r13
0x180111148  push    r14
0x18011114a  push    r15
0x18011114c  lea     rbp, [rax-258h]
0x180111153  sub     rsp, 330h
0x18011115a  movaps  xmmword ptr [rax-38h], xmm6
0x18011115e  mov     rax, cs:__security_cookie
0x180111165  xor     rax, rsp
0x180111168  mov     [rbp+250h+var_40], rax
0x18011116f  mov     r14, rdx
0x180111172  mov     [rsp+350h+var_2E8], rcx
0x180111177  xor     r15d, r15d
0x18011117a  mov     r13d, r15d
0x18011117d  mov     dword ptr [rsp+350h+var_2F8], r15d
0x180111182  xorps   xmm0, xmm0
0x180111185  movdqu  [rsp+350h+var_318+8], xmm0
0x18011118b  mov     [rsp+350h+var_300], r15
0x180111190  mov     rdi, rdx
0x180111193  cmp     qword ptr [rdx+18h], 7
0x180111198  jbe     short loc_18011119D
0x18011119a  mov     rdi, [rdx]
0x18011119d  mov     [rsp+350h+var_2F8], rdi
0x1801111a2  mov     rcx, r14
0x1801111a5  jbe     short loc_1801111AA
0x1801111a7  mov     rcx, [rdx]
0x1801111aa  mov     rax, [rdx+10h]
0x1801111ae  lea     rbx, [rcx+rax*2]
0x1801111b2  mov     [rsp+350h+var_2F0], rbx
0x1801111b7  mov     r12b, 1
0x1801111ba  mov     rsi, rdi
0x1801111bd  cmp     rdi, rbx
0x1801111c0  jz      short loc_1801111E9
0x1801111c2  mov     r15, rdi
0x1801111c5  movzx   ecx, word ptr [rdi]; C
0x1801111c8  call    cs:__imp_iswspace
0x1801111ce  test    eax, eax
0x1801111d0  jz      short loc_1801111E6
0x1801111d2  lea     rdi, [r15+2]
0x1801111d6  mov     rsi, rdi
0x1801111d9  mov     [rsp+350h+var_2F8], rdi
0x1801111de  mov     r15, rdi
0x1801111e1  cmp     rdi, rbx
0x1801111e4  jnz     short loc_1801111C5
0x1801111e6  xor     r15d, r15d
0x1801111e9  cmp     rsi, rbx
0x1801111ec  jz      loc_180111968
0x1801111f2  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x1801111fa  test    r12b, r12b
0x1801111fd  jnz     short loc_18011123F
0x1801111ff  cmp     word ptr [rdi], 2Ch ; ','
0x180111203  jnz     loc_180111C2B
0x180111209  add     rdi, 2
0x18011120d  mov     [rsp+350h+var_2F8], rdi
0x180111212  cmp     rdi, rbx
0x180111215  jz      short loc_18011123F
0x180111217  lea     rsi, [rdi+2]
0x18011121b  mov     r15, rsi
0x18011121e  movzx   ecx, word ptr [rdi]; C
0x180111221  call    cs:__imp_iswspace
0x180111227  test    eax, eax
0x180111229  jz      short loc_18011123C
0x18011122b  mov     rdi, rsi
0x18011122e  mov     [rsp+350h+var_2F8], rsi
0x180111233  add     rsi, 2
0x180111237  cmp     rdi, rbx
0x18011123a  jnz     short loc_18011121B
0x18011123c  xor     r15d, r15d
0x18011123f  cmp     word ptr [rdi], 22h ; '"'
0x180111243  jz      loc_180111869
0x180111249  cmp     word ptr [rdi], 27h ; '''
0x18011124d  jz      loc_180111869
0x180111253  lea     rdx, [rsp+350h+var_2F0]
0x180111258  lea     rcx, [rsp+350h+var_2F8]
0x18011125d  call    sub_18010EE64
0x180111262  test    al, al
0x180111264  jz      loc_180111A2F
0x18011126a  lea     rcx, [rbp+250h+var_1E0]
0x18011126e  call    ??0?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x180111273  lea     rcx, [rsp+350h+var_2E0]
0x180111278  call    ??0?$basic_stringstream@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(void)
0x18011127d  movzx   edx, word ptr [rdi]
0x180111280  lea     rcx, [rbp+250h+var_2D0]
0x180111284  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t)
0x180111289  movzx   ecx, word ptr [rdi]; C
0x18011128c  add     rdi, 2
0x180111290  mov     [rsp+350h+var_2F8], rdi
0x180111295  call    cs:__imp_tolower
0x18011129b  mov     edx, eax
0x18011129d  lea     rcx, [rbp+250h+var_1D0]
0x1801112a4  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t)
0x1801112a9  mov     sil, r15b
0x1801112ac  jmp     loc_18011141A
0x1801112b1  movzx   ecx, word ptr [rdi]; C
0x1801112b4  call    cs:__imp_iswspace
0x1801112ba  test    eax, eax
0x1801112bc  jz      short loc_1801112C6
0x1801112be  mov     sil, 1
0x1801112c1  jmp     loc_180111411
0x1801112c6  movzx   ecx, word ptr [rdi]
0x1801112c9  lea     eax, [rcx-2Eh]
0x1801112cc  cmp     ax, 32h ; '2'
0x1801112d0  ja      short loc_1801112E2
0x1801112d2  mov     rdx, 5E0000007F003h
0x1801112dc  bt      rdx, rax
0x1801112e0  jb      short loc_180111345
0x1801112e2  cmp     cx, 2Ch ; ','
0x1801112e6  jbe     short loc_180111345
0x1801112e8  sub     cx, 7Bh ; '{'
0x1801112ec  cmp     cx, 25h ; '%'
0x1801112f0  jbe     short loc_180111345
0x1801112f2  test    sil, sil
0x1801112f5  jz      short loc_18011131D
0x1801112f7  lea     rdx, asc_18014DE9C; " "
0x1801112fe  lea     rcx, [rbp+250h+var_2D0]
0x180111302  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x180111307  lea     rdx, asc_18014DE9C; " "
0x18011130e  lea     rcx, [rbp+250h+var_1D0]
0x180111315  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18011131a  mov     sil, r15b
0x18011131d  movzx   edx, word ptr [rdi]
0x180111320  lea     rcx, [rbp+250h+var_2D0]
0x180111324  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t)
0x180111329  movzx   ecx, word ptr [rdi]; C
0x18011132c  call    cs:__imp_tolower
0x180111332  mov     edx, eax
0x180111334  lea     rcx, [rbp+250h+var_1D0]
0x18011133b  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t)
0x180111340  jmp     loc_180111411
0x180111345  mov     rax, rbx
0x180111348  sub     rax, rdi
0x18011134b  and     rax, 0FFFFFFFFFFFFFFFEh
0x18011134f  cmp     rax, 4
0x180111353  jl      loc_180111423
0x180111359  cmp     word ptr [rdi], 5Ch ; '\'
0x18011135d  jnz     loc_180111423
0x180111363  mov     eax, 0Ah
0x180111368  cmp     [rdi+2], ax
0x18011136c  jz      loc_180111423
0x180111372  xorps   xmm0, xmm0
0x180111375  movups  [rbp+250h+var_A0], xmm0
0x18011137c  movdqu  [rbp+250h+var_90], xmm6
0x180111384  mov     word ptr [rbp+250h+var_A0], r15w
0x18011138c  lea     r8, [rbp+250h+var_A0]
0x180111393  lea     rdx, [rsp+350h+var_2F0]
0x180111398  lea     rcx, [rsp+350h+var_2F8]
0x18011139d  call    sub_180110DC8
0x1801113a2  test    al, al
0x1801113a4  jz      loc_1801119F5
0x1801113aa  lea     rdx, [rbp+250h+var_A0]
0x1801113b1  cmp     qword ptr [rbp+250h+var_90+8], 7
0x1801113b9  cmova   rdx, qword ptr [rbp+250h+var_A0]
0x1801113c1  mov     r8, qword ptr [rbp+250h+var_90]
0x1801113c8  lea     rcx, [rbp+250h+var_2D0]
0x1801113cc  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x1801113d1  lea     rdx, [rbp+250h+var_A0]
0x1801113d8  cmp     qword ptr [rbp+250h+var_90+8], 7
0x1801113e0  cmova   rdx, qword ptr [rbp+250h+var_A0]
0x1801113e8  mov     r8, qword ptr [rbp+250h+var_90]
0x1801113ef  lea     rcx, [rbp+250h+var_1D0]
0x1801113f6  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x1801113fb  mov     rdi, [rsp+350h+var_2F8]
0x180111400  lea     rcx, [rbp+250h+var_A0]; void *
0x180111407  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18011140c  cmp     rdi, rbx
0x18011140f  jz      short loc_180111423
0x180111411  add     rdi, 2
0x180111415  mov     [rsp+350h+var_2F8], rdi
0x18011141a  cmp     rdi, rbx
0x18011141d  jnz     loc_1801112B1
0x180111423  lea     rdx, [rbp+250h+S1]
0x18011142a  lea     rcx, [rbp+250h+var_1C8]
0x180111431  call    ?str@?$basic_stringbuf@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEGBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@2@XZ; std::wstringbuf::str(void)
0x180111436  or      r13d, 1
0x18011143a  mov     r8, [rbp+250h+N]; N
0x180111441  lea     rcx, [rbp+250h+S1]
0x180111448  mov     rax, [rbp+250h+S1]
0x18011144f  mov     rdx, [rbp+250h+N+8]
0x180111456  mov     esi, 7
0x18011145b  cmp     rdx, rsi
0x18011145e  cmova   rcx, rax; S1
0x180111462  cmp     r8, 5
0x180111466  jnz     loc_18011150D
0x18011146c  lea     rdx, aSerif; "serif"
0x180111473  call    wmemcmp
0x180111478  test    eax, eax
0x18011147a  jnz     short loc_1801114F8
0x18011147c  xorps   xmm0, xmm0
0x18011147f  movups  [rbp+250h+var_E0], xmm0
0x180111486  xorps   xmm1, xmm1
0x180111489  movdqu  [rbp+250h+var_D0], xmm1
0x180111491  lea     r8d, [rsi+8]
0x180111495  lea     rdx, aTimesNewRoman; "Times New Roman"
0x18011149c  lea     rcx, [rbp+250h+var_E0]
0x1801114a3  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x1801114a8  mov     rdx, [rsp+350h+var_308]
0x1801114ad  cmp     rdx, [rsp+350h+var_300]
0x1801114b2  jz      short loc_1801114DB
0x1801114b4  movups  xmm0, [rbp+250h+var_E0]
0x1801114bb  movups  xmmword ptr [rdx], xmm0
0x1801114be  movups  xmm1, [rbp+250h+var_D0]
0x1801114c5  movups  xmmword ptr [rdx+10h], xmm1
0x1801114c9  mov     eax, esi
0x1801114cb  mov     word ptr [rbp+250h+var_E0], r15w
0x1801114d3  add     [rsp+350h+var_308], 20h ; ' '
0x1801114d9  jmp     short loc_1801114F3
0x1801114db  lea     r8, [rbp+250h+var_E0]
0x1801114e2  lea     rcx, [rsp+350h+var_318+8]
0x1801114e7  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1801114ec  mov     rax, qword ptr [rbp+250h+var_D0+8]
0x1801114f3  jmp     loc_1801115B6
0x1801114f8  mov     rdx, [rbp+250h+N+8]
0x1801114ff  mov     r8, [rbp+250h+N]; N
0x180111506  mov     rax, [rbp+250h+S1]
0x18011150d  lea     rcx, [rbp+250h+S1]
0x180111514  cmp     rdx, rsi
0x180111517  cmova   rcx, rax; S1
0x18011151b  mov     r9d, 0Ah
0x180111521  cmp     r8, r9
0x180111524  jnz     loc_18011160E
0x18011152a  lea     rdx, aSansSerif; "sans-serif"
0x180111531  call    wmemcmp
0x180111536  test    eax, eax
0x180111538  jnz     loc_1801115F9
0x18011153e  xorps   xmm0, xmm0
0x180111541  movups  [rbp+250h+var_E0], xmm0
0x180111548  xorps   xmm1, xmm1
0x18011154b  movdqu  [rbp+250h+var_D0], xmm1
0x180111553  lea     r8d, [rax+5]
0x180111557  lea     rdx, aArial; "Arial"
0x18011155e  lea     rcx, [rbp+250h+var_E0]
0x180111565  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x18011156a  mov     rdx, [rsp+350h+var_308]
0x18011156f  cmp     rdx, [rsp+350h+var_300]
0x180111574  jz      short loc_18011159E
0x180111576  movups  xmm0, [rbp+250h+var_E0]
0x18011157d  movups  xmmword ptr [rdx], xmm0
0x180111580  movups  xmm1, [rbp+250h+var_D0]
0x180111587  movups  xmmword ptr [rdx+10h], xmm1
0x18011158b  mov     rax, rsi
0x18011158e  mov     word ptr [rbp+250h+var_E0], r15w
0x180111596  add     [rsp+350h+var_308], 20h ; ' '
0x18011159c  jmp     short loc_1801115B6
0x18011159e  lea     r8, [rbp+250h+var_E0]
0x1801115a5  lea     rcx, [rsp+350h+var_318+8]
0x1801115aa  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1801115af  mov     rax, qword ptr [rbp+250h+var_D0+8]
0x1801115b6  cmp     rax, rsi
0x1801115b9  jbe     loc_1801117CE
0x1801115bf  lea     rax, ds:2[rax*2]
0x1801115c7  mov     rcx, qword ptr [rbp+250h+var_E0]
0x1801115ce  cmp     rax, 1000h
0x1801115d4  mov     rdx, rcx
0x1801115d7  jb      short loc_1801115EE
0x1801115d9  mov     rcx, [rcx-8]; Block
0x1801115dd  sub     rdx, rcx
0x1801115e0  lea     rax, [rdx-8]
0x1801115e4  cmp     rax, 1Fh
0x1801115e8  ja      loc_180111A19
0x1801115ee  call    cs:__imp_free
0x1801115f4  jmp     loc_1801117CE
0x1801115f9  mov     rdx, [rbp+250h+N+8]
0x180111600  mov     r8, [rbp+250h+N]; N
0x180111607  mov     rax, [rbp+250h+S1]
0x18011160e  lea     rcx, [rbp+250h+S1]
0x180111615  cmp     rdx, rsi
0x180111618  cmova   rcx, rax; S1
0x18011161c  cmp     r8, rsi
0x18011161f  jnz     loc_1801116B1
0x180111625  lea     rdx, aCursive; "cursive"
0x18011162c  call    wmemcmp
0x180111631  test    eax, eax
0x180111633  jnz     short loc_1801116B1
0x180111635  xorps   xmm0, xmm0
0x180111638  movups  [rbp+250h+var_E0], xmm0
0x18011163f  xorps   xmm1, xmm1
0x180111642  movdqu  [rbp+250h+var_D0], xmm1
0x18011164a  lea     r8d, [rax+0Dh]
0x18011164e  lea     rdx, aComicSansMs; "Comic Sans MS"
0x180111655  lea     rcx, [rbp+250h+var_E0]
0x18011165c  call    ??$_Construct@$00PEA_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEA_W_K@Z; std::wstring::_Construct<1,wchar_t *>(wchar_t * const,unsigned __int64)
0x180111661  mov     rdx, [rsp+350h+var_308]
0x180111666  cmp     rdx, [rsp+350h+var_300]
0x18011166b  jz      short loc_18011169A
0x18011166d  movups  xmm0, [rbp+250h+var_E0]
0x180111674  movups  xmmword ptr [rdx], xmm0
0x180111677  movups  xmm1, [rbp+250h+var_D0]
0x18011167e  movups  xmmword ptr [rdx+10h], xmm1
0x180111682  movdqu  [rbp+250h+var_D0], xmm6
0x18011168a  mov     word ptr [rbp+250h+var_E0], r15w
0x180111692  add     [rsp+350h+var_308], 20h ; ' '
0x180111698  jmp     short loc_1801116AC
0x18011169a  lea     r8, [rbp+250h+var_E0]
0x1801116a1  lea     rcx, [rsp+350h+var_318+8]
0x1801116a6  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
  ... truncated ...
```
