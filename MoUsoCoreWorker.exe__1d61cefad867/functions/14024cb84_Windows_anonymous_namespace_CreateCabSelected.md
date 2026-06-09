# Windows::_anonymous_namespace_::CreateCabSelected

- ea: `0x14024cb84`
- end: `0x14024d4d2`
- name: `Windows::_anonymous_namespace_::CreateCabSelected`
- size: `2382`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, installer_update`

## callers

- `0x14024d4d8`

## callees

- `0x1400413a8`
- `0x140042d7c`
- `0x140043284`
- `0x1400447ac`
- `0x140044f20`
- `0x140045404`
- `0x140057a20`
- `0x1400b425c`
- `0x140249f30`
- `0x14024a9dc`
- `0x14024acec`
- `0x14024ca74`
- `0x14024cb84`
- `0x14024d718`
- `0x14024d880`
- `0x140378dc8`
- `0x140379070`
- `0x140380b50`
- `0x140380bd0`

## import_xrefs

- `Cabinet!__imp_FCICreate` at `0x14024cf92`
- `Cabinet!__imp_FCICreate` at `0x14024cf92`
- `Cabinet!__imp_FCIAddFile` at `0x14024d1f3`
- `Cabinet!__imp_FCIAddFile` at `0x14024d2b9`
- `Cabinet!__imp_FCIAddFile` at `0x14024d1f3`
- `Cabinet!__imp_FCIAddFile` at `0x14024d2b9`
- `Cabinet!__imp_FCIFlushFolder` at `0x14024d238`
- `Cabinet!__imp_FCIFlushFolder` at `0x14024d238`
- `Cabinet!__imp_FCIFlushCabinet` at `0x14024d346`
- `Cabinet!__imp_FCIFlushCabinet` at `0x14024d346`

## string_xrefs

- `0x14024d3e8`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Cabinet.cpp`
- `0x14024d3fd`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Cabinet.cpp`
- `0x14024d415`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Cabinet.cpp`
- `0x14024d42d`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Cabinet.cpp`
- `0x14024d445`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Cabinet.cpp`
- `0x14024d457`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Cabinet.cpp`
- `0x14024d469`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Cabinet.cpp`
- `0x14024d47b`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Cabinet.cpp`
- `0x14024d493`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Cabinet.cpp`
- `0x14024d4ab`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Cabinet.cpp`
- `0x14024d4c0`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Cabinet.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Windows::_anonymous_namespace_::CreateCabSelected(
        const wchar_t **a1,
        __int64 *a2,
        __int64 *a3,
        __int64 a4)
{
  int v7; // r13d
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  const wchar_t *v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rdx
  _QWORD *v14; // rax
  char *v15; // rax
  char *v16; // r8
  __int64 v17; // rbx
  __int64 v18; // rdx
  char *szCabPath; // rcx
  signed __int64 v20; // r8
  char v21; // al
  char *v22; // rax
  char *v23; // rax
  char *v24; // rdx
  char *szCab; // rcx
  signed __int64 v26; // rdx
  char v27; // al
  char *v28; // rax
  const wchar_t **v29; // r12
  HFCI v30; // rcx
  __int64 v31; // r9
  __int64 v32; // rbx
  __int64 v33; // r14
  __int64 v34; // r15
  int v35; // esi
  __m128i si128; // xmm6
  wchar_t **v37; // rdi
  __int64 v38; // rcx
  __int64 traits_2_unsigned_short; // rax
  __int64 v40; // r11
  __int64 v41; // rax
  __int64 v42; // rcx
  __int64 v43; // r8
  wchar_t **v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rdx
  wchar_t **v47; // rax
  wchar_t **v48; // rdx
  __int64 v49; // rdx
  const wchar_t *v50; // rdx
  CHAR *v51; // r8
  CHAR *v52; // rdx
  int v53; // edi
  const char *v54; // r9
  CHAR *v55; // r8
  CHAR *v56; // rdx
  const char *v57; // r9
  __int64 v58; // rdx
  __int64 v59; // rdx
  __int64 v60; // rdx
  __int64 v61; // rdx
  __int64 v62; // rdx
  __int64 v63; // rdx
  int pfnopen; // [rsp+28h] [rbp-E0h]
  int pfnopena; // [rsp+28h] [rbp-E0h]
  _QWORD v67[3]; // [rsp+70h] [rbp-98h] BYREF
  __m128i v68; // [rsp+88h] [rbp-80h]
  const wchar_t **v69; // [rsp+98h] [rbp-70h]
  _QWORD v70[7]; // [rsp+A8h] [rbp-60h] BYREF
  _QWORD *v71; // [rsp+E0h] [rbp-28h]
  HFCI hfci; // [rsp+E8h] [rbp-20h] BYREF
  wchar_t *String2[2]; // [rsp+F0h] [rbp-18h] BYREF
  __m128i v74; // [rsp+100h] [rbp-8h]
  ERF perf; // [rsp+110h] [rbp+8h] BYREF
  LPSTR pszSourceFile[2]; // [rsp+120h] [rbp+18h] BYREF
  __int128 v77; // [rsp+130h] [rbp+28h]
  LPSTR pszFileName[3]; // [rsp+140h] [rbp+38h] BYREF
  unsigned __int64 v79; // [rsp+158h] [rbp+50h]
  __int64 pv; // [rsp+168h] [rbp+60h] BYREF
  __int128 v81; // [rsp+170h] [rbp+68h] BYREF
  __int64 v82; // [rsp+180h] [rbp+78h]
  __int64 v83; // [rsp+188h] [rbp+80h]
  __int128 v84; // [rsp+190h] [rbp+88h] BYREF
  __int64 v85; // [rsp+1A0h] [rbp+98h]
  __int64 v86; // [rsp+1A8h] [rbp+A0h]
  __int128 v87; // [rsp+1B0h] [rbp+A8h] BYREF
  __int64 v88; // [rsp+1C0h] [rbp+B8h]
  __int64 v89; // [rsp+1C8h] [rbp+C0h]
  __int64 v90; // [rsp+1D0h] [rbp+C8h]
  _BYTE v91[32]; // [rsp+1D8h] [rbp+D0h] BYREF
  _QWORD v92[4]; // [rsp+1F8h] [rbp+F0h] BYREF
  _QWORD v93[10]; // [rsp+218h] [rbp+110h] BYREF
  CCAB pccab; // [rsp+268h] [rbp+160h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+600h] [rbp+4F8h]

  v69 = a1;
  v7 = 0;
  LODWORD(hfci) = 0;
  if ( !a1[1] )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x314,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Cabinet.cpp",
      (const char *)0x80070057LL,
      pfnopen);
  if ( !*(_QWORD *)(a4 + 8) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x315,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Cabinet.cpp",
      (const char *)0x80070057LL,
      pfnopen);
  if ( a2[1] - *a2 != a3[1] - *a3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x316,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Cabinet.cpp",
      (const char *)0x80070057LL,
      pfnopen);
  *(_QWORD *)&perf.erfOper = 0;
  perf.fError = 0;
  hfci = 0;
  memset(v93, 0, 0x48u);
  v70[0] = off_1403D5398;
  v71 = v70;
  v93[7] = 0;
  v93[7] = std::_Func_impl_no_alloc__Windows::_anonymous_namespace_::CreateCabSelected_::_2_::_lambda_1__void_void_____::_Move(
             v70,
             v93);
  if ( v71 )
  {
    LOBYTE(v8) = v71 != v70;
    (*(void (__fastcall **)(_QWORD *, __int64))(*v71 + 32LL))(v71, v8);
    v71 = 0;
  }
  v93[8] = &hfci;
  Windows::_anonymous_namespace_::ValidateFilePaths(a2, 0, 0);
  LOBYTE(v9) = 1;
  LOBYTE(v10) = 1;
  Windows::_anonymous_namespace_::ValidateFilePaths(a3, v10, v9);
  v11 = *a1;
  *(_OWORD *)pszSourceFile = 0;
  v77 = 0;
  v12 = -1;
  do
    ++v12;
  while ( v11[v12] );
  std::wstring::_Construct<1,wchar_t const *>(pszSourceFile, v11, v12);
  Windows::_anonymous_namespace_::GetPathAndFilename(v91, pszSourceFile);
  std::wstring::~wstring(pszSourceFile, v13);
  v14 = v92;
  if ( v92[3] > 7u )
    v14 = (_QWORD *)v92[0];
  v67[1] = v14;
  v67[2] = v92[2];
  Windows::_anonymous_namespace_::EnsureDirectoryExists(&v67[1]);
  memset(&pccab, 0, sizeof(pccab));
  pccab.setID = 555;
  *(_QWORD *)&pccab.iCab = 1;
  pccab.szDisk[0] = 0;
  pccab.cb = 0x7FFFFFFF;
  pccab.cbFolderThresh = 0x7FFFFFFF;
  v15 = (char *)UnicodeToMultiByte(pszFileName, v92);
  v16 = v15;
  if ( *((_QWORD *)v15 + 3) > 0xFu )
    v16 = *(char **)v15;
  v17 = 256;
  v18 = 256;
  szCabPath = pccab.szCabPath;
  v20 = v16 - pccab.szCabPath;
  do
  {
    if ( v18 == -2147483390 )
      break;
    v21 = szCabPath[v20];
    if ( !v21 )
      break;
    *szCabPath++ = v21;
    --v18;
  }
  while ( v18 );
  v22 = szCabPath - 1;
  if ( v18 )
    v22 = szCabPath;
  *v22 = 0;
  if ( !v18 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x32E,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Cabinet.cpp",
      (const char *)0x8007007ALL,
      pfnopen);
  std::string::_Tidy_deallocate(pszFileName);
  v23 = (char *)UnicodeToMultiByte(pszFileName, v91);
  v24 = v23;
  if ( *((_QWORD *)v23 + 3) > 0xFu )
    v24 = *(char **)v23;
  szCab = pccab.szCab;
  v26 = v24 - pccab.szCab;
  do
  {
    if ( v17 == -2147483390 )
      break;
    v27 = szCab[v26];
    if ( !v27 )
      break;
    *szCab++ = v27;
    --v17;
  }
  while ( v17 );
  v28 = szCab - 1;
  if ( v17 )
    v28 = szCab;
  *v28 = 0;
  v29 = v69;
  if ( !v17 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x32F,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Cabinet.cpp",
      v17 == 0 ? (const char *)0x8007007ALL : 0,
      pfnopen);
  std::string::_Tidy_deallocate(pszFileName);
  pv = 0;
  v81 = 0;
  v82 = 0;
  v83 = 7;
  LOWORD(v81) = 0;
  v84 = 0;
  v85 = 0;
  v86 = 7;
  LOWORD(v84) = 0;
  v87 = 0;
  v88 = 0;
  v89 = 7;
  LOWORD(v87) = 0;
  v90 = 0;
  std::wstring::operator=<wil::basic_zstring_view<wchar_t>,0>(&v87);
  LODWORD(pv) = 1;
  std::wstring::operator=<wil::basic_zstring_view<wchar_t>,0>(&v84);
  v30 = FCICreate(
          &perf,
          Update::RebootDowntimeSignal,
          Windows::_anonymous_namespace_::FdiCbAlloc,
          (PFNFCIFREE)Windows::_anonymous_namespace_::FdiCbFree,
          Windows::_anonymous_namespace_::FciCbFileOpen,
          Windows::_anonymous_namespace_::FciCbFileRead,
          Windows::_anonymous_namespace_::FciCbFileWrite,
          Windows::_anonymous_namespace_::FciCbFileClose,
          Windows::_anonymous_namespace_::FciCbFileSeek,
          Windows::_anonymous_namespace_::FciCbFileDelete,
          Windows::_anonymous_namespace_::FciCbGetTempFile,
          &pccab,
          &pv);
  hfci = v30;
  if ( (unsigned int)(perf.erfOper - 1) > 0xA )
    v31 = 2149090031LL;
  else
    v31 = (unsigned int)(perf.erfOper - 2145877280);
  if ( !v30 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x345,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Cabinet.cpp",
      (const char *)v31,
      pfnopena);
  v32 = *a3;
  v33 = *a2;
  v34 = a2[1];
  v35 = -2145877281;
  if ( *a2 != v34 )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    do
    {
      if ( *(_QWORD *)(v33 + 16) && *(_QWORD *)(v32 + 16) )
      {
        std::wstring::wstring(String2, v32);
        v37 = String2;
        if ( v74.m128i_i64[1] > 7uLL )
          v37 = (wchar_t **)String2[0];
        v38 = v74.m128i_i64[0];
        if ( v74.m128i_i64[0] )
        {
          traits_2_unsigned_short = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                      v37,
                                      (char *)v37 + 2 * v74.m128i_i64[0],
                                      58);
          if ( traits_2_unsigned_short != v40 )
          {
            v41 = (traits_2_unsigned_short - (__int64)v37) >> 1;
            if ( v41 != -1 )
            {
              v42 = v41 + 1;
              *(_OWORD *)&v67[1] = 0;
              v68 = 0;
              if ( v74.m128i_i64[0] < (unsigned __int64)(v41 + 1) )
                std::_String_val<std::_Simple_types<char>>::_Xran();
              v43 = -1;
              if ( v74.m128i_i64[0] - v42 != -1 )
                v43 = v74.m128i_i64[0] - v42;
              v44 = String2;
              if ( v74.m128i_i64[1] > 7uLL )
                v44 = (wchar_t **)String2[0];
              std::wstring::_Construct<1,wchar_t const *>(&v67[1], (char *)v44 + 2 * v42, v43);
              v7 |= 2u;
              std::wstring::~wstring(String2, v45);
              goto LABEL_55;
            }
          }
          v38 = v74.m128i_i64[0];
        }
        while ( v38 )
        {
          v47 = String2;
          if ( v74.m128i_i64[1] > 7uLL )
            v47 = (wchar_t **)String2[0];
          if ( *(_WORD *)v47 != 92 )
            break;
          *(_OWORD *)&v67[1] = 0;
          v68 = 0;
          v48 = String2;
          if ( v74.m128i_i64[1] > 7uLL )
            v48 = (wchar_t **)String2[0];
          std::wstring::_Construct<1,wchar_t const *>(&v67[1], (char *)v48 + 2, v38 - 1);
          v7 |= 1u;
          std::wstring::~wstring(String2, v49);
LABEL_55:
          *(_OWORD *)String2 = *(_OWORD *)&v67[1];
          v74 = v68;
          v68 = si128;
          LOWORD(v67[1]) = 0;
          std::wstring::~wstring(&v67[1], v46);
          v38 = v74.m128i_i64[0];
        }
        v50 = (const wchar_t *)String2;
        if ( v74.m128i_i64[1] > 7uLL )
          v50 = String2[0];
        if ( !wcsicmp(*v29, v50) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x35D,
            (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Cabinet.cpp",
            (const char *)0x80070057LL,
            pfnopena);
        UnicodeToMultiByte(pszSourceFile, v33);
        UnicodeToMultiByte(pszFileName, String2);
        v51 = (CHAR *)pszFileName;
        if ( v79 > 0xF )
          v51 = pszFileName[0];
        v52 = (CHAR *)pszSourceFile;
        if ( *((_QWORD *)&v77 + 1) > 0xFu )
          v52 = pszSourceFile[0];
        if ( !FCIAddFile(
                hfci,
                v52,
                v51,
                0,
                Windows::_anonymous_namespace_::FciCbGetNextCabinet,
                (PFNFCISTATUS)Update::RebootDowntimeSignal,
                Windows::_anonymous_namespace_::FciCbGetOpenInfo,
                1u) )
        {
          if ( (unsigned int)(perf.erfOper - 1) > 8 )
          {
            v53 = -2145877281;
          }
          else
          {
            v53 = perf.erfOper - 2145877296;
            if ( perf.erfOper == 9 )
            {
              v53 = 0;
              if ( !FCIFlushFolder(
                      hfci,
                      Windows::_anonymous_namespace_::FciCbGetNextCabinet,
                      (PFNFCISTATUS)Update::RebootDowntimeSignal) )
              {
                v54 = (unsigned int)(perf.erfOper - 1) > 8
                    ? (const char *)2149090015LL
                    : (const char *)(unsigned int)(perf.erfOper - 2145877296);
                if ( (int)v54 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x36D,
                    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Cabinet.cpp",
                    v54,
                    pfnopena);
              }
              v55 = (CHAR *)pszFileName;
              if ( v79 > 0xF )
                v55 = pszFileName[0];
              v56 = (CHAR *)pszSourceFile;
              if ( *((_QWORD *)&v77 + 1) > 0xFu )
                v56 = pszSourceFile[0];
              if ( !FCIAddFile(
                      hfci,
                      v56,
                      v55,
                      0,
                      Windows::_anonymous_namespace_::FciCbGetNextCabinet,
                      (PFNFCISTATUS)Update::RebootDowntimeSignal,
                      Windows::_anonymous_namespace_::FciCbGetOpenInfo,
                      1u) )
              {
                v57 = (unsigned int)(perf.erfOper - 1) > 8
                    ? (const char *)2149090015LL
                    : (const char *)(unsigned int)(perf.erfOper - 2145877296);
                if ( (int)v57 < 0 )
                  wil::details::in1diag3::Throw_Hr(
                    retaddr,
                    (void *)0x37A,
                    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Cabinet.cpp",
                    v57,
                    pfnopena);
              }
            }
          }
          if ( v53 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x37E,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Cabinet.cpp",
              (const char *)(unsigned int)v53,
              pfnopena);
        }
        std::string::_Tidy_deallocate(pszFileName);
        std::string::_Tidy_deallocate(pszSourceFile);
        std::wstring::~wstring(String2, v58);
        v30 = hfci;
      }
      v33 += 32;
      v32 += 32;
    }
    while ( v33 != v34 );
  }
  if ( !FCIFlushCabinet(
          v30,
          0,
          Windows::_anonymous_namespace_::FciCbGetNextCabinet,
          (PFNFCISTATUS)Update::RebootDowntimeSignal) )
  {
    if ( (unsigned int)(perf.erfOper - 1) <= 8 )
      v35 = perf.erfOper - 2145877296;
    if ( v35 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x386,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Cabinet.cpp",
        (const char *)(unsigned int)v35,
        pfnopena);
  }
  std::wstring::~wstring(&v87, v59);
  std::wstring::~wstring(&v84, v60);
  std::wstring::~wstring(&v81, v61);
  std::wstring::~wstring(v92, v62);
  std::wstring::~wstring(v91, v63);
  return std::unique_ptr<void *,std::function<void (void * *)>>::~unique_ptr<void *,std::function<void (void * *)>>(v93);
}

```

## disassembly

```asm
0x14024cb84  mov     rax, rsp
0x14024cb87  push    rbp
0x14024cb88  push    rbx
0x14024cb89  push    rsi
0x14024cb8a  push    rdi
0x14024cb8b  push    r12
0x14024cb8d  push    r13
0x14024cb8f  push    r14
0x14024cb91  push    r15
0x14024cb93  lea     rbp, [rax-4F8h]
0x14024cb9a  sub     rsp, 5B8h
0x14024cba1  movaps  xmmword ptr [rax-58h], xmm6
0x14024cba5  mov     rax, cs:__security_cookie
0x14024cbac  xor     rax, rsp
0x14024cbaf  mov     [rbp+4F0h+var_60], rax
0x14024cbb6  mov     r14, r9
0x14024cbb9  mov     rsi, r8
0x14024cbbc  mov     rdi, rdx
0x14024cbbf  mov     r12, rcx
0x14024cbc2  mov     [rbp+4F0h+var_560], rcx
0x14024cbc6  xor     r15d, r15d
0x14024cbc9  mov     r13d, r15d
0x14024cbcc  mov     dword ptr [rbp+4F0h+hfci], r15d
0x14024cbd0  mov     rcx, [rbp+4F8h]; this
0x14024cbd7  cmp     [r12+8], r15
0x14024cbdc  jz      loc_14024D40F
0x14024cbe2  mov     rcx, [rbp+4F8h]; this
0x14024cbe9  cmp     [r9+8], r15
0x14024cbed  jz      loc_14024D427
0x14024cbf3  mov     rcx, [rbp+4F8h]; this
0x14024cbfa  mov     rdx, [r8+8]
0x14024cbfe  sub     rdx, [r8]
0x14024cc01  mov     rax, [rdi+8]
0x14024cc05  sub     rax, [rdi]
0x14024cc08  cmp     rax, rdx
0x14024cc0b  jnz     loc_14024D43F
0x14024cc11  xor     eax, eax
0x14024cc13  mov     qword ptr [rbp+4F0h+perf.erfOper], rax
0x14024cc17  mov     [rbp+4F0h+perf.fError], eax
0x14024cc1a  mov     [rbp+4F0h+hfci], r15
0x14024cc1e  xor     edx, edx; Val
0x14024cc20  lea     r8d, [r15+48h]; Size
0x14024cc24  lea     rcx, [rbp+4F0h+var_3E0]; void *
0x14024cc2b  call    memset
0x14024cc30  lea     rax, off_1403D5398
0x14024cc37  mov     [rbp+4F0h+var_550], rax
0x14024cc3b  lea     rax, [rbp+4F0h+var_550]
0x14024cc3f  mov     [rbp+4F0h+var_518], rax
0x14024cc43  mov     [rbp+4F0h+var_3A8], r15
0x14024cc4a  lea     rdx, [rbp+4F0h+var_3E0]
0x14024cc51  lea     rcx, [rbp+4F0h+var_550]
0x14024cc55  call    std___Func_impl_no_alloc__Windows___anonymous_namespace___CreateCabSelected____2____lambda_1__void_void________Move
0x14024cc5a  mov     [rbp+4F0h+var_3A8], rax
0x14024cc61  mov     rcx, [rbp+4F0h+var_518]
0x14024cc65  test    rcx, rcx
0x14024cc68  jz      short loc_14024CC84
0x14024cc6a  lea     rax, [rbp+4F0h+var_550]
0x14024cc6e  cmp     rcx, rax
0x14024cc71  setnz   dl
0x14024cc74  mov     rax, [rcx]
0x14024cc77  mov     rax, [rax+20h]
0x14024cc7b  call    _guard_dispatch_icall
0x14024cc80  mov     [rbp+4F0h+var_518], r15
0x14024cc84  lea     rax, [rbp+4F0h+hfci]
0x14024cc88  mov     [rbp+4F0h+var_3A0], rax
0x14024cc8f  xor     r8d, r8d
0x14024cc92  xor     edx, edx
0x14024cc94  mov     rcx, rdi
0x14024cc97  call    Windows___anonymous_namespace___ValidateFilePaths
0x14024cc9c  mov     ebx, 1
0x14024cca1  mov     r8b, bl
0x14024cca4  mov     dl, bl
0x14024cca6  mov     rcx, rsi
0x14024cca9  call    Windows___anonymous_namespace___ValidateFilePaths
0x14024ccae  mov     rdx, [r12]
0x14024ccb2  xorps   xmm0, xmm0
0x14024ccb5  movups  xmmword ptr [rbp+4F0h+pszSourceFile], xmm0
0x14024ccb9  xorps   xmm1, xmm1
0x14024ccbc  movdqu  [rbp+4F0h+var_4C8], xmm1
0x14024ccc1  or      r8, 0FFFFFFFFFFFFFFFFh
0x14024ccc5  inc     r8
0x14024ccc8  cmp     [rdx+r8*2], r15w
0x14024cccd  jnz     short loc_14024CCC5
0x14024cccf  lea     rcx, [rbp+4F0h+pszSourceFile]
0x14024ccd3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14024ccd8  nop
0x14024ccd9  lea     rdx, [rbp+4F0h+pszSourceFile]
0x14024ccdd  lea     rcx, [rbp+4F0h+var_420]
0x14024cce4  call    Windows___anonymous_namespace___GetPathAndFilename
0x14024cce9  nop
0x14024ccea  lea     rcx, [rbp+4F0h+pszSourceFile]
0x14024ccee  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024ccf3  lea     rax, [rbp+4F0h+var_400]
0x14024ccfa  cmp     [rbp+4F0h+var_3E8], 7
0x14024cd02  cmova   rax, [rbp+4F0h+var_400]
0x14024cd0a  mov     qword ptr [rsp+5F0h+var_588+8], rax
0x14024cd0f  mov     rax, [rbp+4F0h+var_3F0]
0x14024cd16  mov     qword ptr [rsp+5F0h+var_588+10h], rax
0x14024cd1b  lea     rcx, [rsp+5F0h+var_588+8]
0x14024cd20  call    Windows___anonymous_namespace___EnsureDirectoryExists
0x14024cd25  xor     edx, edx; Val
0x14024cd27  mov     r8d, 324h; Size
0x14024cd2d  lea     rcx, [rbp+4F0h+var_390]; void *
0x14024cd34  call    memset
0x14024cd39  mov     eax, 22Bh
0x14024cd3e  mov     [rbp+4F0h+var_390.setID], ax
0x14024cd45  mov     qword ptr [rbp+4F0h+var_390.iCab], 1
0x14024cd50  mov     [rbp+4F0h+var_390.szDisk], r15b
0x14024cd57  mov     eax, 7FFFFFFFh
0x14024cd5c  mov     [rbp+4F0h+var_390.cb], eax
0x14024cd62  mov     [rbp+4F0h+var_390.cbFolderThresh], eax
0x14024cd68  lea     rdx, [rbp+4F0h+var_400]
0x14024cd6f  lea     rcx, [rbp+4F0h+pszFileName]
0x14024cd73  call    UnicodeToMultiByte
0x14024cd78  mov     r8, rax
0x14024cd7b  cmp     qword ptr [rax+18h], 0Fh
0x14024cd80  jbe     short loc_14024CD85
0x14024cd82  mov     r8, [rax]
0x14024cd85  mov     ebx, 100h
0x14024cd8a  mov     edx, ebx
0x14024cd8c  lea     rcx, [rbp+4F0h+var_390.szCabPath]
0x14024cd93  lea     rax, [rbp+4F0h+var_390.szCabPath]
0x14024cd9a  sub     r8, rax
0x14024cd9d  mov     r12d, 1
0x14024cda3  lea     rax, [rdx+7FFFFEFEh]
0x14024cdaa  test    rax, rax
0x14024cdad  jz      short loc_14024CDC1
0x14024cdaf  mov     al, [r8+rcx]
0x14024cdb3  test    al, al
0x14024cdb5  jz      short loc_14024CDC1
0x14024cdb7  mov     [rcx], al
0x14024cdb9  add     rcx, r12
0x14024cdbc  sub     rdx, r12
0x14024cdbf  jnz     short loc_14024CDA3
0x14024cdc1  lea     rax, [rcx-1]
0x14024cdc5  test    rdx, rdx
0x14024cdc8  cmovnz  rax, rcx
0x14024cdcc  mov     [rax], r15b
0x14024cdcf  mov     rax, rdx
0x14024cdd2  neg     rax
0x14024cdd5  sbb     r9d, r9d
0x14024cdd8  not     r9d
0x14024cddb  and     r9d, 8007007Ah; char *
0x14024cde2  mov     rcx, [rbp+4F8h]; this
0x14024cde9  test    rdx, rdx
0x14024cdec  jz      loc_14024D457
0x14024cdf2  lea     rcx, [rbp+4F0h+pszFileName]
0x14024cdf6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14024cdfb  lea     rdx, [rbp+4F0h+var_420]
0x14024ce02  lea     rcx, [rbp+4F0h+pszFileName]
0x14024ce06  call    UnicodeToMultiByte
0x14024ce0b  mov     rdx, rax
0x14024ce0e  cmp     qword ptr [rax+18h], 0Fh
0x14024ce13  jbe     short loc_14024CE18
0x14024ce15  mov     rdx, [rax]
0x14024ce18  lea     rcx, [rbp+4F0h+var_390.szCab]
0x14024ce1f  lea     rax, [rbp+4F0h+var_390.szCab]
0x14024ce26  sub     rdx, rax
0x14024ce29  mov     r12d, 1
0x14024ce2f  lea     rax, [rbx+7FFFFEFEh]
0x14024ce36  test    rax, rax
0x14024ce39  jz      short loc_14024CE4C
0x14024ce3b  mov     al, [rcx+rdx]
0x14024ce3e  test    al, al
0x14024ce40  jz      short loc_14024CE4C
0x14024ce42  mov     [rcx], al
0x14024ce44  add     rcx, r12
0x14024ce47  sub     rbx, r12
0x14024ce4a  jnz     short loc_14024CE2F
0x14024ce4c  lea     rax, [rcx-1]
0x14024ce50  test    rbx, rbx
0x14024ce53  cmovnz  rax, rcx
0x14024ce57  mov     [rax], r15b
0x14024ce5a  mov     rax, rbx
0x14024ce5d  neg     rax
0x14024ce60  sbb     r9d, r9d
0x14024ce63  not     r9d
0x14024ce66  and     r9d, 8007007Ah; char *
0x14024ce6d  mov     rcx, [rbp+4F8h]; this
0x14024ce74  test    rbx, rbx
0x14024ce77  mov     r12, [rbp+4F0h+var_560]
0x14024ce7b  jz      loc_14024D469
0x14024ce81  lea     rcx, [rbp+4F0h+pszFileName]
0x14024ce85  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x14024ce8a  mov     [rbp+4F0h+pv], r15
0x14024ce8e  xorps   xmm0, xmm0
0x14024ce91  movups  [rbp+4F0h+var_488], xmm0
0x14024ce95  mov     [rbp+4F0h+var_478], r15
0x14024ce99  mov     eax, 7
0x14024ce9e  mov     [rbp+4F0h+var_470], rax
0x14024cea5  mov     word ptr [rbp+4F0h+var_488], r15w
0x14024ceaa  movups  [rbp+4F0h+var_468], xmm0
0x14024ceb1  mov     [rbp+4F0h+var_458], r15
0x14024ceb8  mov     [rbp+4F0h+var_450], rax
0x14024cebf  mov     word ptr [rbp+4F0h+var_468], r15w
0x14024cec7  movups  [rbp+4F0h+var_448], xmm0
0x14024cece  mov     [rbp+4F0h+var_438], r15
0x14024ced5  mov     [rbp+4F0h+var_430], rax
0x14024cedc  mov     word ptr [rbp+4F0h+var_448], r15w
0x14024cee4  mov     [rbp+4F0h+var_428], r15
0x14024ceeb  mov     rdx, r12
0x14024ceee  lea     rcx, [rbp+4F0h+var_448]; void *
0x14024cef5  call    ??$?4V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV?$basic_zstring_view@_W@wil@@@Z; std::wstring::operator=<wil::basic_zstring_view<wchar_t>,0>(wil::basic_zstring_view<wchar_t> const &)
0x14024cefa  mov     dword ptr [rbp+4F0h+pv], 1
0x14024cf01  mov     rdx, r14
0x14024cf04  lea     rcx, [rbp+4F0h+var_468]; void *
0x14024cf0b  call    ??$?4V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV?$basic_zstring_view@_W@wil@@@Z; std::wstring::operator=<wil::basic_zstring_view<wchar_t>,0>(wil::basic_zstring_view<wchar_t> const &)
0x14024cf10  lea     rax, [rbp+4F0h+pv]
0x14024cf14  mov     [rsp+60h], rax; pv
0x14024cf19  lea     rax, [rbp+4F0h+var_390]
0x14024cf20  mov     [rsp+5F0h+pccab], rax; pccab
0x14024cf25  lea     rax, Windows___anonymous_namespace___FciCbGetTempFile
0x14024cf2c  mov     [rsp+5F0h+pfnfcigtf], rax; pfnfcigtf
0x14024cf31  lea     rax, Windows___anonymous_namespace___FciCbFileDelete
0x14024cf38  mov     [rsp+5F0h+pfndelete], rax; pfndelete
0x14024cf3d  lea     rax, Windows___anonymous_namespace___FciCbFileSeek
0x14024cf44  mov     [rsp+5F0h+pfnseek], rax; pfnseek
0x14024cf49  lea     rax, Windows___anonymous_namespace___FciCbFileClose
0x14024cf50  mov     [rsp+5F0h+pfnclose], rax; pfnclose
0x14024cf55  lea     rax, Windows___anonymous_namespace___FciCbFileWrite
0x14024cf5c  mov     [rsp+5F0h+pfnwrite], rax; pfnwrite
0x14024cf61  lea     rax, Windows___anonymous_namespace___FciCbFileRead
0x14024cf68  mov     [rsp+5F0h+pfnread], rax; pfnread
0x14024cf6d  lea     rax, Windows___anonymous_namespace___FciCbFileOpen
0x14024cf74  mov     [rsp+5F0h+pfnopen], rax; int
0x14024cf79  lea     r9, Windows___anonymous_namespace___FdiCbFree; pfnf
0x14024cf80  lea     r8, Windows___anonymous_namespace___FdiCbAlloc; pfna
0x14024cf87  lea     rdx, ?RebootDowntimeSignal@Update@@UEAA_JXZ; pfnfcifp
0x14024cf8e  lea     rcx, [rbp+4F0h+perf]; perf
0x14024cf92  call    cs:__imp_FCICreate
0x14024cf98  mov     rcx, rax
0x14024cf9b  mov     [rbp+4F0h+hfci], rax
0x14024cf9f  mov     r9d, [rbp+4F0h+perf.erfOper]
0x14024cfa3  lea     eax, [r9-1]
0x14024cfa7  cmp     eax, 0Ah
0x14024cfaa  ja      short loc_14024CFB5
0x14024cfac  add     r9d, 801882E0h
0x14024cfb3  jmp     short loc_14024CFBB
0x14024cfb5  mov     r9d, 801882EFh; char *
0x14024cfbb  mov     rax, [rbp+4F8h]
0x14024cfc2  test    rcx, rcx
0x14024cfc5  jz      loc_14024D47B
0x14024cfcb  mov     rbx, [rsi]
0x14024cfce  mov     r14, [rdi]
0x14024cfd1  mov     r15, [rdi+8]
0x14024cfd5  lea     rdx, ?RebootDowntimeSignal@Update@@UEAA_JXZ; Update::RebootDowntimeSignal(void)
0x14024cfdc  lea     r8, Windows___anonymous_namespace___FciCbGetNextCabinet
0x14024cfe3  mov     esi, 801882DFh
0x14024cfe8  cmp     r14, r15
0x14024cfeb  jz      loc_14024D341
0x14024cff1  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x14024cff9  xor     eax, eax
0x14024cffb  cmp     [r14+10h], rax
0x14024cfff  jz      loc_14024D322
0x14024d005  cmp     [rbx+10h], rax
0x14024d009  jz      loc_14024D322
0x14024d00f  mov     rdx, rbx
0x14024d012  lea     rcx, [rbp+4F0h+String2]
0x14024d016  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x14024d01b  nop
0x14024d01c  lea     rdi, [rbp+4F0h+String2]
0x14024d020  cmp     qword ptr [rbp+4F0h+var_4F8+8], 7
0x14024d025  cmova   rdi, [rbp+4F0h+String2]
0x14024d02a  mov     rcx, qword ptr [rbp+4F0h+var_4F8]
0x14024d02e  test    rcx, rcx
0x14024d031  jz      loc_14024D0BD
0x14024d037  lea     r11, [rdi+rcx*2]
0x14024d03b  mov     r8d, 3Ah ; ':'
0x14024d041  mov     rdx, r11
0x14024d044  mov     rcx, rdi
0x14024d047  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x14024d04c  cmp     rax, r11
0x14024d04f  jz      short loc_14024D0B9
0x14024d051  sub     rax, rdi
0x14024d054  sar     rax, 1
0x14024d057  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14024d05b  jz      short loc_14024D0B9
0x14024d05d  lea     rcx, [rax+1]
0x14024d061  xorps   xmm0, xmm0
0x14024d064  movups  xmmword ptr [rsp+5F0h+var_588+8], xmm0
0x14024d069  xorps   xmm1, xmm1
0x14024d06c  movdqu  [rbp+4F0h+var_570], xmm1
0x14024d071  mov     rax, qword ptr [rbp+4F0h+var_4F8]
0x14024d075  cmp     rax, rcx
0x14024d078  jb      loc_14024D4A5
0x14024d07e  sub     rax, rcx
0x14024d081  or      r8, 0FFFFFFFFFFFFFFFFh
0x14024d085  cmp     rax, r8
0x14024d088  cmovb   r8, rax
0x14024d08c  lea     rax, [rbp+4F0h+String2]
0x14024d090  cmp     qword ptr [rbp+4F0h+var_4F8+8], 7
0x14024d095  cmova   rax, [rbp+4F0h+String2]
0x14024d09a  lea     rdx, [rax+rcx*2]
0x14024d09e  lea     rcx, [rsp+5F0h+var_588+8]
0x14024d0a3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14024d0a8  or      r13d, 2
0x14024d0ac  lea     rcx, [rbp+4F0h+String2]
0x14024d0b0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14024d0b5  xor     edi, edi
0x14024d0b7  jmp     short loc_14024D132
  ... truncated ...
```
