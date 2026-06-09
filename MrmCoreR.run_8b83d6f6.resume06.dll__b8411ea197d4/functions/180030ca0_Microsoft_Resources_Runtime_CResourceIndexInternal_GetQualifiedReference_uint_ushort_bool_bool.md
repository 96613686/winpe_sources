# Microsoft::Resources::Runtime::CResourceIndexInternal::_GetQualifiedReference(uint,ushort * *,bool,bool)

- ea: `0x180030ca0`
- end: `0x180031dfd`
- name: `?_GetQualifiedReference@CResourceIndexInternal@Runtime@Resources@Microsoft@@AEBAJIPEAPEAG_N1@Z`
- size: `4445`
- prototype: `__int64 __fastcall(Microsoft::Resources::Runtime::CResourceIndexInternal *__hidden this, unsigned int, unsigned __int16 **, bool, bool)`
- caller_count: `5`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180030964`
- `0x180030b0c`
- `0x1800a7e6c`
- `0x1800a7fcc`
- `0x1800a84d0`

## callees

- `0x180017960`
- `0x180027c00`
- `0x180028ad0`
- `0x18002c8d0`
- `0x18002cfd0`
- `0x18002ec70`
- `0x180030ca0`
- `0x180032898`
- `0x18003295c`
- `0x180037130`
- `0x1800974f8`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003195a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031a7e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031b23`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031bd2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003195a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031a7e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031b23`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180031bd2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003101a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800312bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031329`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031363`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031542`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800317a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800318a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031949`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031a6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031b12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031bc1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003101a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800312bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031329`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031363`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031542`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800317a2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800318a9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031949`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031a6d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031b12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180031bc1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031028`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800312c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031337`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031371`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031550`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800317b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800318b7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031028`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800312c9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031337`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031371`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180031550`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800317b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800318b7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180031cc7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180031cc7`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::Runtime::CResourceIndexInternal::_GetQualifiedReference(
        Microsoft::Resources::Runtime::CResourceIndexInternal *this,
        int a2,
        unsigned __int16 **a3,
        char a4,
        bool a5)
{
  Microsoft::Resources::Runtime::CResourceIndexInternal *v6; // r8
  __int64 v7; // rax
  __int64 v8; // rax
  const unsigned __int16 *Ref; // rax
  __int64 v10; // rcx
  const WCHAR *v11; // rsi
  const WCHAR *v12; // rax
  int v13; // ebx
  unsigned __int64 v14; // rbx
  unsigned int v16; // eax
  __int64 v17; // rdx
  _WORD *v18; // rax
  __int64 j; // r15
  HRESULT v20; // ebx
  __int64 v21; // r15
  __int64 v22; // rdx
  const unsigned __int16 *v23; // rax
  const wchar_t *v24; // r10
  __int64 v25; // r9
  __int64 v26; // rdx
  const wchar_t *v27; // rcx
  __int64 v28; // r8
  unsigned __int64 v29; // rsi
  __int64 v30; // rdx
  Microsoft::Resources::StringResult *v31; // rcx
  int v32; // ecx
  unsigned int v33; // edi
  _WORD *v34; // rcx
  HANDLE v35; // rax
  _WORD *v36; // r8
  unsigned __int64 v37; // rdx
  const unsigned __int16 *v38; // r9
  __int64 v39; // rax
  _WORD *v40; // rcx
  _WORD *v41; // r10
  unsigned __int16 v42; // ax
  const unsigned __int16 *v43; // r13
  __int64 v44; // rdx
  const unsigned __int16 *v45; // rcx
  LPVOID *v46; // r15
  _WORD *v47; // rdx
  __int64 v48; // rcx
  _WORD *v49; // rax
  __int64 v50; // r12
  __int64 k; // r12
  __int64 v52; // rcx
  const unsigned __int16 *v53; // rax
  _WORD *v54; // rax
  __int64 v55; // rdx
  __int64 v56; // rcx
  __int64 v57; // r8
  wchar_t *v58; // r14
  __int64 v59; // rdx
  unsigned __int64 v60; // rdi
  void *v61; // rdi
  HANDLE v62; // rax
  size_t v63; // rdx
  const wchar_t *v64; // r8
  HANDLE v65; // rax
  _WORD *v66; // rcx
  HANDLE v67; // rax
  _WORD *v68; // r8
  unsigned __int64 v69; // rdx
  __int64 v70; // rcx
  _WORD *v71; // rcx
  LPVOID *v72; // rax
  unsigned __int16 *v73; // rdx
  int v74; // r8d
  __int64 v75; // rdx
  __int64 v76; // rax
  const struct Microsoft::Resources::ResourceMapSubtree *BaseSubtree; // rbx
  int updated; // eax
  unsigned int v79; // edi
  __int64 v80; // rdx
  int v81; // eax
  HANDLE v82; // rax
  __int64 v83; // rdx
  __int64 v84; // r9
  __int64 v85; // rcx
  unsigned int v86; // eax
  __int64 v87; // rcx
  _WORD *v88; // rax
  __int64 i; // r12
  __int64 v90; // r12
  const wchar_t *v91; // r14
  __int64 v92; // rcx
  const wchar_t *v93; // rax
  __int64 v94; // rdx
  __int64 v95; // rcx
  _WORD *v96; // rax
  __int64 v97; // r8
  __int64 v98; // rdx
  unsigned __int64 v99; // rsi
  _WORD *v100; // rcx
  HANDLE v101; // rax
  _WORD *v102; // r8
  unsigned __int64 v103; // rdx
  __int64 v104; // rax
  _WORD *v105; // rcx
  LPVOID *v106; // r14
  wchar_t *v107; // r13
  size_t v108; // r11
  LPVOID *v109; // rdi
  HANDLE v110; // rax
  _WORD *v111; // rcx
  __int64 v112; // r8
  SIZE_T v113; // rdi
  HANDLE ProcessHeap; // rax
  _WORD *v115; // rax
  _WORD *v116; // r8
  __int64 v117; // rdx
  __int64 v118; // rax
  _WORD *v119; // rcx
  LPVOID *v120; // r15
  wchar_t *v121; // r11
  unsigned __int64 v122; // r10
  wchar_t *v123; // r9
  SIZE_T v124; // rbx
  HANDLE v125; // rax
  _WORD *v126; // rax
  _WORD *v127; // rdi
  _WORD *v128; // rax
  __int64 v129; // rcx
  _WORD *v130; // r8
  unsigned __int64 v131; // rdx
  SIZE_T v132; // rbx
  HANDLE v133; // rax
  _WORD *v134; // rax
  _WORD *v135; // rdi
  _WORD *v136; // rax
  __int64 v137; // rcx
  _WORD *v138; // r8
  unsigned __int64 v139; // rdx
  SIZE_T v140; // rbx
  HANDLE v141; // rax
  _WORD *v142; // rax
  void *v143; // rsi
  _WORD *v144; // r8
  __int64 v145; // rcx
  unsigned __int64 v146; // rdx
  int v147; // eax
  int ResourceNameBySchemaIndex; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-61h]
  const unsigned __int16 *v150; // [rsp+30h] [rbp-51h]
  LPVOID *v151; // [rsp+38h] [rbp-49h]
  void *v152; // [rsp+38h] [rbp-49h]
  LPVOID *p_lpMem; // [rsp+48h] [rbp-39h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-31h] BYREF
  int v155; // [rsp+58h] [rbp-29h]
  LPVOID v156; // [rsp+60h] [rbp-21h]
  _BYTE *v157; // [rsp+68h] [rbp-19h] BYREF
  _BYTE v158[40]; // [rsp+70h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+57h]

  v6 = this;
  lpMem = 0;
  v155 = 0;
  v156 = 0;
  *a3 = 0;
  v7 = *((_QWORD *)this + 8);
  p_lpMem = &lpMem;
  if ( v7 )
  {
    v8 = *(_QWORD *)(v7 + 32);
    if ( v8 && (*(_QWORD *)v8 || !*(_DWORD *)(v8 + 8)) && (*(_DWORD *)(v8 + 8) || !*(_QWORD *)v8) )
      Ref = *(const unsigned __int16 **)(v8 + 16);
    else
      Ref = 0;
  }
  else
  {
    if ( !Microsoft::Resources::StringResult::GetRef((Microsoft::Resources::Runtime::CResourceIndexInternal *)((char *)this + 24)) )
      goto LABEL_46;
    Ref = Microsoft::Resources::StringResult::GetRef(v31);
  }
  v150 = Ref;
  if ( !Ref )
  {
LABEL_46:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7BE,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
      (const char *)0x80073B1FLL,
      bIgnoreCase);
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&p_lpMem);
    return 2147957535LL;
  }
  if ( a4 )
  {
    v32 = *((_DWORD *)v6 + 4);
    if ( (v32 & 4) != 0 )
    {
      if ( (v32 & 8) == 0 )
        goto LABEL_10;
      v33 = -2147009769;
    }
    else
    {
      v33 = -2147024875;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C1,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
      (const char *)v33,
      bIgnoreCase);
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&p_lpMem);
    return v33;
  }
LABEL_10:
  v10 = 0x7FFFFFFF;
  v11 = L"ms-resource";
  v12 = L"ms-resource";
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v10;
  }
  while ( v10 );
  v13 = -2147024809;
  if ( !v10 )
    goto LABEL_18;
  v14 = 1;
  if ( v10 != 0x80000000LL )
    v14 = 0x80000000LL - v10;
  if ( !is_mul_ok(v14, 2u) || !(2 * v14) )
    goto LABEL_17;
  v113 = 2 * v14;
  if ( !is_mul_ok(v14, 2u) )
    v113 = 0;
  ProcessHeap = GetProcessHeap();
  v115 = HeapAlloc(ProcessHeap, 8u, v113);
  v116 = v115;
  if ( !v115 )
  {
LABEL_17:
    v13 = -2147024882;
    goto LABEL_18;
  }
  *v115 = 0;
  v117 = (unsigned int)v14;
  lpMem = v115;
  v155 = v14;
  v156 = v115;
  if ( (unsigned int)(v14 - 1) > 0x7FFFFFFE )
  {
    v13 = -2147024809;
    if ( v117 )
      *v115 = 0;
  }
  else
  {
    v118 = 2147483646;
    do
    {
      if ( !v118 )
        break;
      if ( !*v11 )
        break;
      *v116++ = *v11++;
      --v118;
      --v117;
    }
    while ( v117 );
    v119 = v116 - 1;
    v13 = -2147024774;
    if ( v117 )
    {
      v119 = v116;
      v13 = 0;
    }
    *v119 = 0;
    if ( v117 )
    {
      v156 = lpMem;
      goto LABEL_260;
    }
  }
  if ( v13 < 0 )
  {
LABEL_18:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C4,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
      (const char *)(unsigned int)v13,
      bIgnoreCase);
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&p_lpMem);
    return (unsigned int)v13;
  }
LABEL_260:
  v120 = p_lpMem;
  if ( !p_lpMem )
    goto LABEL_270;
  v121 = (wchar_t *)*p_lpMem;
  v152 = *p_lpMem;
  if ( !*p_lpMem )
  {
    if ( *((_DWORD *)p_lpMem + 2) )
      goto LABEL_270;
  }
  v122 = *((unsigned int *)p_lpMem + 2);
  if ( !(_DWORD)v122 )
  {
    if ( v121 )
      goto LABEL_270;
  }
  v123 = (wchar_t *)p_lpMem[2];
  v90 = 0;
  if ( v123 && *v123 )
  {
    if ( v121 == v123 )
    {
      if ( (unsigned int)v122 > 0x7FFFFFFF )
      {
LABEL_270:
        v20 = -2147024809;
        goto LABEL_208;
      }
      v86 = *((_DWORD *)p_lpMem + 2);
    }
    else
    {
      v86 = 0x7FFFFFFF;
    }
    v87 = v86;
    v88 = p_lpMem[2];
    for ( i = (unsigned int)v87; v87; --v87 )
    {
      if ( !*v88 )
        break;
      ++v88;
    }
    v20 = -2147024809;
    if ( v87 )
    {
      v20 = 0;
      v90 = i - v87;
    }
    else
    {
      v90 = 0;
    }
    if ( !v87 )
      goto LABEL_208;
  }
  v91 = L"://";
  v92 = 0x7FFFFFFF;
  v93 = L"://";
  do
  {
    if ( !*v93 )
      break;
    ++v93;
    --v92;
  }
  while ( v92 );
  v20 = -2147024809;
  if ( !v92 )
    goto LABEL_208;
  v94 = 0x7FFFFFFF - v92;
  if ( v123 )
  {
    v95 = 0x7FFFFFFF;
    v96 = p_lpMem[2];
    do
    {
      if ( !*v96 )
        break;
      ++v96;
      --v95;
    }
    while ( v95 );
    v20 = -2147024809;
    if ( !v95 )
      goto LABEL_208;
    v97 = 0x7FFFFFFF - v95;
  }
  else
  {
    v97 = 0;
  }
  v98 = v90 + v94;
  if ( v98 + 1 >= (unsigned __int64)(v97 + 1) )
    v97 = v98;
  v99 = v97 + 1;
  if ( !v121 || v122 < v99 )
  {
    if ( !is_mul_ok(v99, 2u) || !(2 * v99) )
      goto LABEL_207;
    v124 = 2 * v99;
    if ( !is_mul_ok(v99, 2u) )
      v124 = 0;
    v125 = GetProcessHeap();
    v126 = HeapAlloc(v125, 8u, v124);
    v127 = v126;
    if ( !v126 )
    {
LABEL_207:
      v20 = -2147024882;
      goto LABEL_208;
    }
    *v126 = 0;
    v128 = v120[2];
    if ( v128 && *v128 )
    {
      if ( v99 - 1 > 0x7FFFFFFE )
      {
        v20 = -2147024809;
        goto LABEL_217;
      }
      v129 = 2147483646;
      v130 = v127;
      v131 = v99;
      do
      {
        if ( !v129 )
          break;
        if ( !*v128 )
          break;
        *v130++ = *v128++;
        --v129;
        --v131;
      }
      while ( v131 );
      v100 = v130 - 1;
      v20 = -2147024774;
      if ( v131 )
      {
        v100 = v130;
        v20 = 0;
      }
      *v100 = 0;
      if ( !v131 )
      {
LABEL_217:
        v101 = GetProcessHeap();
        HeapFree(v101, 0, v127);
        if ( v20 >= 0 )
          goto LABEL_218;
LABEL_208:
        v30 = 1989;
        goto LABEL_43;
      }
    }
    *v120 = v127;
    *((_DWORD *)v120 + 2) = v99;
    v120[2] = v127;
    if ( v152 )
    {
      v110 = GetProcessHeap();
      HeapFree(v110, 0, v152);
    }
    goto LABEL_218;
  }
  if ( v123 != v121 )
  {
    if ( v123 )
    {
      v20 = StringCchCopyW(v121, *((unsigned int *)p_lpMem + 2), (STRSAFE_LPCWSTR)p_lpMem[2]);
      if ( v20 < 0 )
        goto LABEL_208;
    }
    p_lpMem[2] = *p_lpMem;
  }
LABEL_218:
  v102 = (char *)*v120 + 2 * v90;
  v103 = *((unsigned int *)v120 + 2) - v90;
  if ( v103 )
  {
    if ( v103 > 0x7FFFFFFF )
    {
      v20 = -2147024809;
      *v102 = 0;
    }
    else
    {
      v104 = 2147483646;
      do
      {
        if ( !v104 )
          break;
        if ( !*v91 )
          break;
        *v102++ = *v91++;
        --v104;
        --v103;
      }
      while ( v103 );
      v105 = v102 - 1;
      v20 = -2147024774;
      if ( v103 )
      {
        v105 = v102;
        v20 = 0;
      }
      *v105 = 0;
      if ( v103 )
        goto LABEL_227;
    }
  }
  else
  {
    v20 = -2147024809;
  }
  if ( v20 < 0 )
    goto LABEL_208;
LABEL_227:
  v106 = p_lpMem;
  if ( !p_lpMem )
    goto LABEL_238;
  v107 = (wchar_t *)*p_lpMem;
  if ( !*p_lpMem )
  {
    if ( *((_DWORD *)p_lpMem + 2) )
      goto LABEL_238;
  }
  v108 = *((unsigned int *)p_lpMem + 2);
  if ( !(_DWORD)v108 )
  {
    if ( v107 )
      goto LABEL_238;
  }
  if ( *v150 )
  {
    v27 = (const wchar_t *)p_lpMem[2];
    v109 = p_lpMem + 2;
    v21 = 0;
    v151 = p_lpMem + 2;
    if ( v27 && *v27 )
    {
      if ( v107 == v27 )
      {
        if ( (unsigned int)v108 > 0x7FFFFFFF )
        {
LABEL_238:
          v20 = -2147024809;
          goto LABEL_42;
        }
        v16 = *((_DWORD *)p_lpMem + 2);
      }
      else
      {
        v16 = 0x7FFFFFFF;
      }
      v17 = v16;
      v18 = p_lpMem[2];
      for ( j = (unsigned int)v17; v17; --v17 )
      {
        if ( !*v18 )
          break;
        ++v18;
      }
      v20 = -2147024809;
      if ( v17 )
      {
        v20 = 0;
        v21 = j - v17;
      }
      else
      {
        v21 = 0;
      }
      if ( !v17 )
        goto LABEL_42;
    }
  }
  else
  {
    if ( p_lpMem[2] )
      goto LABEL_72;
    v27 = (const wchar_t *)p_lpMem[2];
    v109 = p_lpMem + 2;
    v151 = p_lpMem + 2;
    v21 = 0;
  }
  v22 = 0x7FFFFFFF;
  v23 = v150;
  do
  {
    if ( !*v23 )
      break;
    ++v23;
    --v22;
  }
  while ( v22 );
  v20 = -2147024809;
  if ( !v22 )
    goto LABEL_42;
  v24 = v27;
  v25 = 0x7FFFFFFF - v22;
  if ( v27 )
  {
    v26 = 0x7FFFFFFF;
    do
    {
      if ( !*v27 )
        break;
      ++v27;
      --v26;
    }
    while ( v26 );
    v20 = -2147024809;
    if ( !v26 )
      goto LABEL_42;
    v28 = 0x7FFFFFFF - v26;
  }
  else
  {
    v28 = 0;
    v151 = v109;
  }
  if ( v25 + v21 + 1 >= (unsigned __int64)(v28 + 1) )
    v28 = v25 + v21;
  v29 = v28 + 1;
  if ( !v107 || v108 < v29 )
  {
    if ( !is_mul_ok(v29, 2u) || !(2 * v29) )
      goto LABEL_41;
    v132 = 2 * v29;
    if ( !is_mul_ok(v29, 2u) )
      v132 = 0;
    v133 = GetProcessHeap();
    v134 = HeapAlloc(v133, 8u, v132);
    v135 = v134;
    if ( !v134 )
    {
LABEL_41:
      v20 = -2147024882;
      goto LABEL_42;
    }
    *v134 = 0;
    v136 = *v151;
    if ( *v151 && *v136 )
    {
      if ( v29 - 1 > 0x7FFFFFFE )
      {
        v20 = -2147024809;
        goto LABEL_62;
      }
      v137 = 2147483646;
      v138 = v135;
      v139 = v29;
      do
      {
        if ( !v137 )
          break;
        if ( !*v136 )
          break;
        *v138++ = *v136++;
        --v137;
        --v139;
      }
      while ( v139 );
      v34 = v138 - 1;
      v20 = -2147024774;
      if ( v139 )
      {
        v34 = v138;
        v20 = 0;
      }
      *v34 = 0;
      if ( !v139 )
      {
LABEL_62:
        v35 = GetProcessHeap();
        HeapFree(v35, 0, v135);
        if ( v20 >= 0 )
          goto LABEL_63;
LABEL_42:
        v30 = 1990;
LABEL_43:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
          (const char *)(unsigned int)v20,
          bIgnoreCase);
LABEL_44:
        Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&p_lpMem);
        return (unsigned int)v20;
      }
    }
    *v106 = v135;
    *((_DWORD *)v106 + 2) = v29;
    *v151 = v135;
    if ( v107 )
    {
      v65 = GetProcessHeap();
      HeapFree(v65, 0, v107);
    }
    goto LABEL_63;
  }
  if ( v24 != v107 )
  {
    if ( v24 )
    {
      v20 = StringCchCopyW(v107, v108, v24);
      if ( v20 < 0 )
        goto LABEL_42;
    }
    *v109 = *p_lpMem;
  }
LABEL_63:
  v36 = (char *)*v106 + 2 * v21;
  v37 = *((unsigned int *)v106 + 2) - v21;
  if ( v37 )
  {
    if ( v37 > 0x7FFFFFFF )
    {
      v20 = -2147024809;
      *v36 = 0;
    }
    else
    {
      v38 = v150;
      v39 = 2147483646;
      do
      {
        if ( !v39 )
          break;
        if ( !*v38 )
          break;
        *v36++ = *v38++;
        --v39;
        --v37;
      }
      while ( v37 );
      v40 = v36 - 1;
      v20 = -2147024774;
      if ( v37 )
      {
        v40 = v36;
        v20 = 0;
      }
      *v40 = 0;
      if ( v37 )
        goto LABEL_72;
    }
  }
  else
  {
    v20 = -2147024809;
  }
  if ( v20 < 0 )
    goto LABEL_42;
LABEL_72:
  if ( p_lpMem && (*p_lpMem || !*((_DWORD *)p_lpMem + 2)) && (*((_DWORD *)p_lpMem + 2) || !*p_lpMem) )
    v41 = p_lpMem[2];
  else
    v41 = 0;
  v42 = asc_1800DDC20[0];
  if ( !asc_1800DDC20[0] )
    goto LABEL_143;
  v43 = L"/";
  if ( v41 && *v41 )
  {
    v44 = 0x7FFFFFFF;
    v45 = L"/";
    while ( *v45 )
    {
      ++v45;
      if ( !--v44 )
        goto LABEL_84;
    }
    v112 = 0x7FFFFFFF;
    v111 = v41;
    while ( *v111 )
    {
      ++v111;
      if ( !--v112 )
        goto LABEL_84;
    }
    if ( 0x7FFFFFFF - v112 >= (unsigned __int64)(0x7FFFFFFF - v44) )
    {
      v147 = CompareStringOrdinal(L"/", -1, &v41[v44 - v112], -1, 1);
      if ( !(unsigned int)IntToComparison((unsigned int)(v147 - 2)) )
        goto LABEL_143;
      v42 = asc_1800DDC20[0];
    }
  }
LABEL_84:
  v46 = p_lpMem;
  if ( !p_lpMem )
    goto LABEL_169;
  v47 = *p_lpMem;
  if ( !*p_lpMem )
  {
    if ( *((_DWORD *)p_lpMem + 2) )
      goto LABEL_169;
  }
  v48 = *((unsigned int *)p_lpMem + 2);
  if ( !(_DWORD)v48 )
  {
    if ( v47 )
      goto LABEL_169;
  }
  if ( v42 )
  {
    v49 = p_lpMem[2];
    v50 = 0;
    if ( v49 && *v49 )
    {
      if ( v47 == v49 )
      {
        if ( (unsigned int)v48 > 0x7FFFFFFF )
        {
LABEL_169:
          v20 = -2147024809;
          goto LABEL_116;
        }
      }
      else
      {
        v48 = 0x7FFFFFFF;
      }
      for ( k = v48; v48; --v48 )
      {
        if ( !*v49 )
          break;
        ++v49;
      }
      v20 = -2147024809;
      if ( v48 )
      {
        v20 = 0;
        v50 = k - v48;
      }
      else
      {
        v50 = 0;
      }
      if ( !v48 )
        goto LABEL_116;
    }
  }
  else
  {
    if ( p_lpMem[2] )
      goto LABEL_143;
    v50 = 0;
  }
  v52 = 0x7FFFFFFF;
  v53 = L"/";
  do
  {
    if ( !*v53 )
      break;
    ++v53;
    --v52;
  }
  while ( v52 );
  v20 = -2147024809;
  if ( !v52 )
  {
LABEL_116:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7CA,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
      (const char *)(unsigned int)v20,
      bIgnoreCase);
    v61 = lpMem;
    if ( (lpMem || !v155) && (v155 || !lpMem) )
    {
      v156 = 0;
      if ( lpMem )
      {
        v62 = GetProcessHeap();
        HeapFree(v62, 0, v61);
      }
    }
    return (unsigned int)v20;
  }
  v54 = p_lpMem[2];
  v55 = 0x7FFFFFFF - v52;
  if ( v54 )
  {
    v56 = 0x7FFFFFFF;
    do
    {
      if ( !*v54 )
        break;
      ++v54;
      --v56;
    }
    while ( v56 );
    v20 = -2147024809;
    if ( !v56 )
      goto LABEL_116;
    v57 = 0x7FFFFFFF - v56;
  }
  else
  {
    v57 = 0;
  }
  v58 = (wchar_t *)*p_lpMem;
  v59 = v50 + v55;
  if ( v59 + 1 >= (unsigned __int64)(v57 + 1) )
    v57 = v59;
  v60 = v57 + 1;
  if ( !v58 || (v63 = *((unsigned int *)p_lpMem + 2), v63 < v60) )
  {
    if ( !is_mul_ok(v60, 2u) || !(2 * v60) )
      goto LABEL_112;
    v140 = 2 * v60;
    if ( !is_mul_ok(v60, 2u) )
      v140 = 0;
    v141 = GetProcessHeap();
    v142 = HeapAlloc(v141, 8u, v140);
    v143 = v142;
    if ( !v142 )
    {
LABEL_112:
      v20 = -2147024882;
      goto LABEL_116;
    }
    *v142 = 0;
    v144 = v46[2];
    if ( v144 && *v144 )
    {
      if ( v60 - 1 > 0x7FFFFFFE )
      {
        v20 = -2147024809;
        goto LABEL_133;
      }
      v145 = 2147483646;
      v146 = v60;
      do
      {
        if ( !v145 )
          break;
        if ( !*v144 )
          break;
        *v142++ = *v144++;
        --v145;
        --v146;
      }
      while ( v146 );
      v66 = v142 - 1;
      v20 = -2147024774;
      if ( v146 )
      {
        v66 = v142;
        v20 = 0;
      }
      *v66 = 0;
      if ( !v146 )
      {
LABEL_133:
        v67 = GetProcessHeap();
        HeapFree(v67, 0, v143);
        if ( v20 < 0 )
          goto LABEL_116;
        goto LABEL_134;
      }
    }
    *v46 = v143;
    *((_DWORD *)v46 + 2) = v60;
    v46[2] = v143;
    if ( v58 )
    {
      v82 = GetProcessHeap();
      HeapFree(v82, 0, v58);
    }
    goto LABEL_134;
  }
  v64 = (const wchar_t *)p_lpMem[2];
  if ( v64 != v58 )
  {
    if ( v64 )
    {
      v20 = StringCchCopyW((STRSAFE_LPWSTR)*p_lpMem, v63, v64);
      if ( v20 < 0 )
        goto LABEL_116;
    }
    p_lpMem[2] = *p_lpMem;
  }
LABEL_134:
  v68 = (char *)*v46 + 2 * v50;
  v69 = *((unsigned int *)v46 + 2) - v50;
  if ( !v69 )
  {
    v20 = -2147024809;
    goto LABEL_115;
  }
  if ( v69 > 0x7FFFFFFF )
  {
    v20 = -2147024809;
    *v68 = 0;
    goto LABEL_115;
  }
  v70 = 2147483646;
  do
  {
    if ( !v70 )
      break;
    if ( !*v43 )
      break;
    *v68++ = *v43++;
    --v70;
    --v69;
  }
  while ( v69 );
  v71 = v68 - 1;
  v20 = -2147024774;
  if ( v69 )
  {
    v71 = v68;
    v20 = 0;
  }
  *v71 = 0;
  if ( !v69 )
  {
LABEL_115:
    if ( v20 >= 0 )
      goto LABEL_143;
    goto LABEL_116;
  }
LABEL_143:
  if ( a4 )
  {
    BaseSubtree = Microsoft::Resources::Runtime::CResourceIndexInternal::GetBaseSubtree(this);
    DefStringResult_InitBuf(v158);
    v157 = v158;
    if ( a5 )
    {
      ResourceNameBySchemaIndex = Microsoft::Resources::ResourceMapSubtree::GetResourceNameBySchemaIndex(
                                    BaseSubtree,
                                    a2,
                                    (struct Microsoft::Resources::StringResult *)&v157);
      v20 = ResourceNameBySchemaIndex;
      if ( ResourceNameBySchemaIndex < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7D5,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
          (const char *)(unsigned int)ResourceNameBySchemaIndex,
          bIgnoreCase);
        Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v157);
        goto LABEL_44;
      }
      goto LABEL_156;
    }
    updated = Microsoft::Resources::ResourceMapSubtree::GetOrUpdateDescendents(BaseSubtree);
    v79 = updated;
    if ( updated < 0 )
    {
      v84 = (unsigned int)updated;
      v83 = 1175;
    }
    else
    {
      if ( a2 >= 0 && a2 <= *((_DWORD *)BaseSubtree + 16) - 1 )
      {
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD, _QWORD, _BYTE **))(**((_QWORD **)BaseSubtree + 2) + 144LL))(
               *((_QWORD *)BaseSubtree + 2),
               *((unsigned int *)BaseSubtree + 6),
               *(unsigned int *)(*((_QWORD *)BaseSubtree + 9) + 4LL * a2),
               &v157) )
        {
LABEL_156:
          if ( v157 && (*(_QWORD *)v157 || !*((_DWORD *)v157 + 2)) && (*((_DWORD *)v157 + 2) || !*(_QWORD *)v157) )
            v80 = *((_QWORD *)v157 + 2);
          else
            v80 = 0;
          v81 = DefStringResult_Concat(p_lpMem, v80);
          v20 = v81;
          if ( v81 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x7DC,
              (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
              (const char *)(unsigned int)v81,
              bIgnoreCase);
            Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v157);
            goto LABEL_44;
          }
          Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v157);
          goto LABEL_144;
        }
        v79 = -2147009769;
LABEL_167:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7D9,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
          (const char *)v79,
          bIgnoreCase);
        Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v157);
        Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&p_lpMem);
        return v79;
      }
      v79 = -2147024252;
      v83 = 1177;
      v84 = 2147943044LL;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v83,
      (unsigned int)"minkernel\\mrt\\mrm\\mrmmin\\resourcemap.cpp",
      (const char *)v84,
      bIgnoreCase);
    goto LABEL_167;
  }
LABEL_144:
  v72 = p_lpMem;
  if ( p_lpMem
    && ((v73 = (unsigned __int16 *)*p_lpMem) != 0 || !*((_DWORD *)p_lpMem + 2))
    && ((v74 = *((_DWORD *)p_lpMem + 2)) != 0 || !v73)
    && v73
    && v74 )
  {
    *a3 = v73;
    v75 = *((unsigned int *)v72 + 2);
    *((_DWORD *)v72 + 2) = 0;
    v72[2] = 0;
    *v72 = 0;
    v76 = (__int64)*a3;
    if ( *a3 )
    {
      v85 = v75 - 1;
      if ( v75 != 1 )
      {
        do
        {
          if ( *(_WORD *)(v76 + 2 * v85) == 92 )
          {
            *(_WORD *)(v76 + 2 * v85) = 47;
            v76 = (__int64)*a3;
          }
          --v85;
        }
        while ( v85 );
      }
    }
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&p_lpMem);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7DF,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\cresourceindexinternal.cpp",
      (const char *)0x80070057LL,
      bIgnoreCase);
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&p_lpMem);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180030ca0  mov     [rsp-8+arg_18], r9b
0x180030ca5  mov     [rsp-8+arg_10], r8
0x180030caa  mov     [rsp-8+arg_8], edx
0x180030cae  mov     [rsp-8+arg_0], rcx
0x180030cb3  push    rbp
0x180030cb4  push    r14
0x180030cb6  lea     rbp, [rsp-47h]
0x180030cbb  sub     rsp, 0C8h
0x180030cc2  xor     r14d, r14d
0x180030cc5  mov     rax, r8
0x180030cc8  mov     r8, rcx
0x180030ccb  mov     [rbp+4Fh+lpMem], r14
0x180030ccf  lea     rcx, [rbp+4Fh+lpMem]
0x180030cd3  mov     [rbp+4Fh+var_78], r14d
0x180030cd7  mov     [rbp+4Fh+var_70], r14
0x180030cdb  mov     [rax], r14
0x180030cde  mov     rax, [r8+40h]
0x180030ce2  mov     [rbp+4Fh+var_88], rcx
0x180030ce6  test    rax, rax
0x180030ce9  jz      loc_180030F50
0x180030cef  mov     rax, [rax+20h]
0x180030cf3  test    rax, rax
0x180030cf6  jz      loc_180030FF1
0x180030cfc  mov     rdx, [rax]
0x180030cff  test    rdx, rdx
0x180030d02  jnz     short loc_180030D0E
0x180030d04  cmp     [rax+8], r14d
0x180030d08  ja      loc_180030FF1
0x180030d0e  cmp     [rax+8], r14d
0x180030d12  jnz     short loc_180030D1D
0x180030d14  test    rdx, rdx
0x180030d17  jnz     loc_180030FF1
0x180030d1d  mov     rax, [rax+10h]
0x180030d21  mov     [rbp+4Fh+var_A0], rax
0x180030d25  test    rax, rax
0x180030d28  jz      loc_180030F1C
0x180030d2e  mov     [rsp+0D0h+var_20], rdi
0x180030d36  test    r9b, r9b
0x180030d39  jnz     loc_180030FA0
0x180030d3f  mov     [rsp+0D0h+var_10], rbx
0x180030d47  mov     ecx, 7FFFFFFFh
0x180030d4c  mov     [rsp+0D0h+var_18], rsi
0x180030d54  lea     rsi, aMsResource_0; "ms-resource"
0x180030d5b  mov     rax, rsi
0x180030d5e  xchg    ax, ax
0x180030d60  cmp     [rax], r14w
0x180030d64  jz      short loc_180030D70
0x180030d66  add     rax, 2
0x180030d6a  sub     rcx, 1
0x180030d6e  jnz     short loc_180030D60
0x180030d70  test    rcx, rcx
0x180030d73  mov     ebx, 80070057h
0x180030d78  cmovnz  ebx, r14d
0x180030d7c  jz      short loc_180030DAC
0x180030d7e  mov     ebx, 1
0x180030d83  mov     [rbp+4Fh+var_98], r14
0x180030d87  mov     eax, 80000000h
0x180030d8c  sub     rax, rcx
0x180030d8f  cmp     rax, rbx
0x180030d92  cmovnb  rbx, rax
0x180030d96  mov     eax, 2
0x180030d9b  mul     rbx
0x180030d9e  test    rdx, rdx
0x180030da1  jz      loc_180031929
0x180030da7  mov     ebx, 8007000Eh
0x180030dac  mov     rcx, [rbp+57h]; this
0x180030db0  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x180030db7  mov     r9d, ebx; char *
0x180030dba  mov     edx, 7C4h; void *
0x180030dbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030dc4  lea     rcx, [rbp+4Fh+var_88]; this
0x180030dc8  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x180030dcd  mov     eax, ebx
0x180030dcf  jmp     loc_180030EF9
0x180030dd4  cmp     r11d, 7FFFFFFFh
0x180030ddb  ja      loc_1800318CD
0x180030de1  mov     eax, r11d
0x180030de4  mov     edx, eax
0x180030de6  mov     rax, rcx
0x180030de9  mov     r15d, edx
0x180030dec  test    rdx, rdx
0x180030def  jz      short loc_180030E01
0x180030df1  cmp     word ptr [rax], 0
0x180030df5  jz      short loc_180030E01
0x180030df7  add     rax, 2
0x180030dfb  sub     rdx, 1
0x180030dff  jnz     short loc_180030DF1
0x180030e01  xor     eax, eax
0x180030e03  mov     ebx, 80070057h
0x180030e08  test    rdx, rdx
0x180030e0b  cmovnz  ebx, eax
0x180030e0e  jz      loc_180031618
0x180030e14  sub     r15, rdx
0x180030e17  test    rdx, rdx
0x180030e1a  jz      loc_180030EBE
0x180030e20  mov     edx, 7FFFFFFFh
0x180030e25  mov     rax, r8
0x180030e28  cmp     word ptr [rax], 0
0x180030e2c  jz      short loc_180030E38
0x180030e2e  add     rax, 2
0x180030e32  sub     rdx, 1
0x180030e36  jnz     short loc_180030E28
0x180030e38  xor     eax, eax
0x180030e3a  mov     ebx, 80070057h
0x180030e3f  test    rdx, rdx
0x180030e42  cmovnz  ebx, eax
0x180030e45  jz      short loc_180030EBE
0x180030e47  mov     r9d, 7FFFFFFFh
0x180030e4d  mov     r10, rcx
0x180030e50  sub     r9, rdx
0x180030e53  test    rcx, rcx
0x180030e56  jz      loc_180031D14
0x180030e5c  mov     edx, 7FFFFFFFh
0x180030e61  cmp     [rcx], ax
0x180030e64  jz      short loc_180030E70
0x180030e66  add     rcx, 2
0x180030e6a  sub     rdx, 1
0x180030e6e  jnz     short loc_180030E61
0x180030e70  test    rdx, rdx
0x180030e73  mov     ebx, 80070057h
0x180030e78  cmovnz  ebx, eax
0x180030e7b  jz      short loc_180030EBE
0x180030e7d  mov     r8d, 7FFFFFFFh
0x180030e83  sub     r8, rdx
0x180030e86  lea     rdx, [r9+r15]
0x180030e8a  lea     rax, [r8+1]
0x180030e8e  lea     rcx, [rdx+1]
0x180030e92  cmp     rcx, rax
0x180030e95  cmovnb  r8, rdx
0x180030e99  lea     rsi, [r8+1]
0x180030e9d  test    r13, r13
0x180030ea0  jnz     loc_180030F68
0x180030ea6  mov     eax, 2
0x180030eab  xor     ecx, ecx
0x180030ead  mul     rsi
0x180030eb0  test    rdx, rdx
0x180030eb3  jz      loc_180031AF6
0x180030eb9  mov     ebx, 8007000Eh
0x180030ebe  mov     edx, 7C6h; void *
0x180030ec3  mov     rcx, [rbp+57h]; this
0x180030ec7  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x180030ece  mov     r9d, ebx; char *
0x180030ed1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030ed6  lea     rcx, [rbp+4Fh+var_88]; this
0x180030eda  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x180030edf  mov     eax, ebx
0x180030ee1  mov     r13, [rsp+0D0h+var_30]
0x180030ee9  mov     r12, [rsp+0D0h+var_28]
0x180030ef1  mov     r15, [rsp+0D0h+var_38]
0x180030ef9  mov     rsi, [rsp+0D0h+var_18]
0x180030f01  mov     rbx, [rsp+0D0h+var_10]
0x180030f09  mov     rdi, [rsp+0D0h+var_20]
0x180030f11  add     rsp, 0C8h
0x180030f18  pop     r14
0x180030f1a  pop     rbp
0x180030f1b  retn
0x180030f1c  mov     rcx, [rbp+57h]; this
0x180030f20  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x180030f27  mov     r9d, 80073B1Fh; char *
0x180030f2d  mov     edx, 7BEh; void *
0x180030f32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030f37  lea     rcx, [rbp+4Fh+var_88]; this
0x180030f3b  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x180030f40  mov     eax, 80073B1Fh
0x180030f45  add     rsp, 0C8h
0x180030f4c  pop     r14
0x180030f4e  pop     rbp
0x180030f4f  retn
0x180030f50  lea     rcx, [r8+18h]; this
0x180030f54  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x180030f59  test    rax, rax
0x180030f5c  jz      short loc_180030F1C
0x180030f5e  call    ?GetRef@StringResult@Resources@Microsoft@@QEBAPEBGXZ; Microsoft::Resources::StringResult::GetRef(void)
0x180030f63  jmp     loc_180030D21
0x180030f68  mov     rdx, r11; cchDest
0x180030f6b  cmp     r11, rsi
0x180030f6e  jb      loc_180030EA6
0x180030f74  cmp     r10, r13
0x180030f77  jz      loc_180031036
0x180030f7d  test    r10, r10
0x180030f80  jz      loc_1800C1B00
0x180030f86  mov     r8, r10; pszSrc
0x180030f89  mov     rcx, r13; pszDest
0x180030f8c  call    StringCchCopyW
0x180030f91  mov     ebx, eax
0x180030f93  test    eax, eax
0x180030f95  js      loc_180030EBE
0x180030f9b  jmp     loc_1800C1B00
0x180030fa0  mov     ecx, [r8+10h]
0x180030fa4  test    cl, 4
0x180030fa7  jz      loc_180031CE8
0x180030fad  test    cl, 8
0x180030fb0  jz      loc_180030D3F
0x180030fb6  mov     edi, 80073B17h
0x180030fbb  mov     rcx, [rbp+57h]; this
0x180030fbf  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\mrt\\runtime\\src\\cr"...
0x180030fc6  mov     r9d, edi; char *
0x180030fc9  mov     edx, 7C1h; void *
0x180030fce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030fd3  lea     rcx, [rbp+4Fh+var_88]; this
0x180030fd7  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x180030fdc  mov     eax, edi
0x180030fde  mov     rdi, [rsp+0D0h+var_20]
0x180030fe6  add     rsp, 0C8h
0x180030fed  pop     r14
0x180030fef  pop     rbp
0x180030ff0  retn
0x180030ff1  mov     rax, r14
0x180030ff4  jmp     loc_180030D21
0x180030ff9  test    rdx, rdx
0x180030ffc  lea     rcx, [r8-2]
0x180031000  mov     ebx, 8007007Ah
0x180031005  cmovnz  rcx, r8
0x180031009  xor     eax, eax
0x18003100b  test    rdx, rdx
0x18003100e  cmovnz  ebx, eax
0x180031011  mov     [rcx], ax
0x180031014  jnz     loc_180031316
0x18003101a  call    cs:__imp_GetProcessHeap
0x180031020  mov     r8, rdi; lpMem
0x180031023  xor     edx, edx; dwFlags
0x180031025  mov     rcx, rax; hHeap
0x180031028  call    cs:__imp_HeapFree
0x18003102e  test    ebx, ebx
0x180031030  js      loc_180030EBE
0x180031036  mov     rax, [r14]
0x180031039  mov     edx, [r14+8]
0x18003103d  lea     r8, [rax+r15*2]
0x180031041  sub     rdx, r15
0x180031044  jz      loc_180031C68
0x18003104a  cmp     rdx, 7FFFFFFFh
0x180031051  ja      loc_180031D2A
0x180031057  mov     r9, [rbp+4Fh+var_A0]
0x18003105b  mov     eax, 7FFFFFFEh
0x180031060  test    rax, rax
0x180031063  jz      short loc_180031083
0x180031065  movzx   ecx, word ptr [r9]
0x180031069  test    cx, cx
0x18003106c  jz      short loc_180031083
0x18003106e  mov     [r8], cx
0x180031072  add     r9, 2
0x180031076  add     r8, 2
0x18003107a  dec     rax
0x18003107d  sub     rdx, 1
0x180031081  jnz     short loc_180031060
0x180031083  test    rdx, rdx
0x180031086  lea     rcx, [r8-2]
0x18003108a  mov     ebx, 8007007Ah
0x18003108f  cmovnz  rcx, r8
0x180031093  xor     eax, eax
0x180031095  test    rdx, rdx
0x180031098  cmovnz  ebx, eax
0x18003109b  mov     [rcx], ax
0x18003109e  jz      loc_180031C78
0x1800310a4  mov     rax, [rbp+4Fh+var_88]
0x1800310a8  test    rax, rax
0x1800310ab  jz      loc_18003130E
0x1800310b1  mov     rdx, [rax]
0x1800310b4  test    rdx, rdx
0x1800310b7  jnz     short loc_1800310C2
0x1800310b9  cmp     [rax+8], edx
0x1800310bc  ja      loc_18003130E
0x1800310c2  cmp     dword ptr [rax+8], 0
0x1800310c6  jnz     short loc_1800310D1
0x1800310c8  test    rdx, rdx
0x1800310cb  jnz     loc_18003130E
0x1800310d1  mov     r10, [rax+10h]
0x1800310d5  mov     eax, dword ptr cs:asc_1800DDC20; "/"
0x1800310db  test    ax, ax
0x1800310de  jz      loc_1800313EA
0x1800310e4  lea     r13, asc_1800DDC20; "/"
0x1800310eb  test    r10, r10
0x1800310ee  jz      short loc_180031114
0x1800310f0  cmp     word ptr [r10], 0
0x1800310f5  jz      short loc_180031114
0x1800310f7  mov     edx, 7FFFFFFFh
0x1800310fc  mov     rcx, r13
0x1800310ff  nop
0x180031100  cmp     word ptr [rcx], 0
0x180031104  jz      loc_180031D34
0x18003110a  add     rcx, 2
0x18003110e  sub     rdx, 1
0x180031112  jnz     short loc_180031100
0x180031114  mov     r15, [rbp+4Fh+var_88]
0x180031118  test    r15, r15
0x18003111b  jz      loc_18003159C
0x180031121  mov     rdx, [r15]
0x180031124  test    rdx, rdx
0x180031127  jz      loc_180031591
0x18003112d  mov     ecx, [r15+8]
0x180031131  test    ecx, ecx
0x180031133  jz      loc_1800315C5
0x180031139  test    ax, ax
0x18003113c  jz      loc_1800315FE
0x180031142  mov     rax, [r15+10h]
0x180031146  xor     r12d, r12d
0x180031149  test    rax, rax
0x18003114c  jz      short loc_1800311A0
0x18003114e  cmp     [rax], r12w
0x180031152  jz      short loc_1800311A0
  ... truncated ...
```
