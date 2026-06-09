# SemanticsUM::SchemaEngine::Initialize(void)

- ea: `0x180026b00`
- end: `0x1800273d4`
- name: `?Initialize@SchemaEngine@SemanticsUM@@QEAAJXZ`
- size: `2260`
- prototype: `__int64 __fastcall(SemanticsUM::SchemaEngine *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800279ec`

## callees

- `0x180026b00`
- `0x1800273dc`
- `0x18005db64`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026b9b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026c0a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026c79`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026ce8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026d57`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026dc6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026e35`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026ea4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026f13`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026f82`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026ff1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180027060`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800270cf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002713e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800271ae`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002721e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002728e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026b9b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026c0a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026c79`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026ce8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026d57`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026dc6`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026e35`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026ea4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026f13`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026f82`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180026ff1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180027060`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800270cf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002713e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800271ae`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002721e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002728e`

## string_xrefs

- `0x1800270c3`: `System.StructuredQueryType.FilePath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SemanticsUM::SchemaEngine::Initialize(const struct SemanticsUM::SchemaBinary **this)
{
  SemanticsUM::CultureState *v2; // rax
  const struct SemanticsUM::SchemaBinary *v3; // rax
  __int64 v4; // r12
  const struct SemanticsUM::SchemaBinary *v5; // rdi
  unsigned int v6; // esi
  unsigned int v7; // r14d
  __int64 v8; // rbp
  const WCHAR *lpString2; // rax
  int v10; // eax
  const struct SemanticsUM::SchemaBinary *v11; // rax
  __int64 v12; // r12
  const struct SemanticsUM::SchemaBinary *v13; // rdi
  unsigned int v14; // esi
  unsigned int v15; // r14d
  __int64 v16; // rbp
  const WCHAR *v17; // rax
  int v18; // eax
  const struct SemanticsUM::SchemaBinary *v19; // rax
  __int64 v20; // r12
  const struct SemanticsUM::SchemaBinary *v21; // rdi
  unsigned int v22; // esi
  unsigned int v23; // r14d
  __int64 v24; // rbp
  const WCHAR *v25; // rax
  int v26; // eax
  const struct SemanticsUM::SchemaBinary *v27; // rax
  __int64 v28; // r12
  const struct SemanticsUM::SchemaBinary *v29; // rdi
  unsigned int v30; // esi
  unsigned int v31; // r14d
  __int64 v32; // rbp
  const WCHAR *v33; // rax
  int v34; // eax
  const struct SemanticsUM::SchemaBinary *v35; // rax
  __int64 v36; // r12
  const struct SemanticsUM::SchemaBinary *v37; // rdi
  unsigned int v38; // esi
  unsigned int v39; // r14d
  __int64 v40; // rbp
  const WCHAR *v41; // rax
  int v42; // eax
  const struct SemanticsUM::SchemaBinary *v43; // rax
  __int64 v44; // r12
  const struct SemanticsUM::SchemaBinary *v45; // rdi
  unsigned int v46; // esi
  unsigned int v47; // r14d
  __int64 v48; // rbp
  const WCHAR *v49; // rax
  int v50; // eax
  const struct SemanticsUM::SchemaBinary *v51; // rax
  __int64 v52; // r12
  const struct SemanticsUM::SchemaBinary *v53; // rdi
  unsigned int v54; // esi
  unsigned int v55; // r14d
  __int64 v56; // rbp
  const WCHAR *v57; // rax
  int v58; // eax
  const struct SemanticsUM::SchemaBinary *v59; // rax
  __int64 v60; // r12
  const struct SemanticsUM::SchemaBinary *v61; // rdi
  unsigned int v62; // esi
  unsigned int v63; // r14d
  __int64 v64; // rbp
  const WCHAR *v65; // rax
  int v66; // eax
  const struct SemanticsUM::SchemaBinary *v67; // rax
  __int64 v68; // r12
  const struct SemanticsUM::SchemaBinary *v69; // rdi
  unsigned int v70; // esi
  unsigned int v71; // r14d
  __int64 v72; // rbp
  const WCHAR *v73; // rax
  int v74; // eax
  const struct SemanticsUM::SchemaBinary *v75; // rax
  __int64 v76; // r12
  const struct SemanticsUM::SchemaBinary *v77; // rdi
  unsigned int v78; // esi
  unsigned int v79; // r14d
  __int64 v80; // rbp
  const WCHAR *v81; // rax
  int v82; // eax
  const struct SemanticsUM::SchemaBinary *v83; // rax
  __int64 v84; // r12
  const struct SemanticsUM::SchemaBinary *v85; // rdi
  unsigned int v86; // esi
  unsigned int v87; // r14d
  __int64 v88; // rbp
  const WCHAR *v89; // rax
  int v90; // eax
  const struct SemanticsUM::SchemaBinary *v91; // rax
  __int64 v92; // r12
  const struct SemanticsUM::SchemaBinary *v93; // rdi
  unsigned int v94; // esi
  unsigned int v95; // r14d
  __int64 v96; // rbp
  const WCHAR *v97; // rax
  int v98; // eax
  const struct SemanticsUM::SchemaBinary *v99; // rax
  __int64 v100; // r12
  const struct SemanticsUM::SchemaBinary *v101; // rdi
  unsigned int v102; // esi
  unsigned int v103; // r14d
  __int64 v104; // rbp
  const WCHAR *v105; // rax
  int v106; // eax
  const struct SemanticsUM::SchemaBinary *v107; // rax
  __int64 v108; // r12
  const struct SemanticsUM::SchemaBinary *v109; // rdi
  unsigned int v110; // esi
  unsigned int v111; // r14d
  __int64 v112; // rbp
  const WCHAR *v113; // rax
  int v114; // eax
  const struct SemanticsUM::SchemaBinary *v115; // rax
  __int64 v116; // r12
  const struct SemanticsUM::SchemaBinary *v117; // rdi
  unsigned int v118; // ebp
  unsigned int v119; // r14d
  int v120; // eax
  const struct SemanticsUM::SchemaBinary *v121; // rax
  __int64 v122; // r12
  const struct SemanticsUM::SchemaBinary *v123; // rdi
  unsigned int v124; // ebp
  unsigned int v125; // r14d
  int v126; // eax
  const struct SemanticsUM::SchemaBinary *v127; // rax
  __int64 v128; // r12
  const struct SemanticsUM::SchemaBinary *v129; // rdi
  unsigned int v130; // ebp
  unsigned int v131; // r14d
  int v132; // eax

  v2 = (SemanticsUM::CultureState *)operator new(4u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v2 )
    v2 = SemanticsUM::CultureState::CultureState(v2, this[1]);
  this[2] = v2;
  if ( !v2 )
    return 2147942414LL;
  v3 = this[1];
  v4 = *((_QWORD *)v3 + 5);
  v5 = 0;
  v6 = 0;
  v7 = *((_DWORD *)v3 + 8);
  do
  {
    if ( v6 >= v7 )
      break;
    v8 = (v7 + v6) >> 1;
    lpString2 = (const WCHAR *)(**(__int64 (__fastcall ***)(__int64))(v4 + 112 * v8))(v4 + 112 * v8);
    v10 = CompareStringW(0x7Fu, 0, L"System.StructuredQueryType.Entity", -1, lpString2, -1);
    if ( v10 == 2 )
    {
      v5 = (const struct SemanticsUM::SchemaBinary *)(v4 + 112 * v8);
    }
    else if ( v10 == 1 )
    {
      v7 = (v7 + v6) >> 1;
    }
    else
    {
      v6 = v8 + 1;
    }
  }
  while ( !v5 );
  this[3] = v5;
  v11 = this[1];
  v12 = *((_QWORD *)v11 + 5);
  v13 = 0;
  v14 = 0;
  v15 = *((_DWORD *)v11 + 8);
  do
  {
    if ( v14 >= v15 )
      break;
    v16 = (v15 + v14) >> 1;
    v17 = (const WCHAR *)(**(__int64 (__fastcall ***)(__int64))(v12 + 112 * v16))(v12 + 112 * v16);
    v18 = CompareStringW(0x7Fu, 0, L"System.StructuredQueryType.Object", -1, v17, -1);
    if ( v18 == 2 )
    {
      v13 = (const struct SemanticsUM::SchemaBinary *)(v12 + 112 * v16);
    }
    else if ( v18 == 1 )
    {
      v15 = (v15 + v14) >> 1;
    }
    else
    {
      v14 = v16 + 1;
    }
  }
  while ( !v13 );
  this[4] = v13;
  v19 = this[1];
  v20 = *((_QWORD *)v19 + 5);
  v21 = 0;
  v22 = 0;
  v23 = *((_DWORD *)v19 + 8);
  do
  {
    if ( v22 >= v23 )
      break;
    v24 = (v23 + v22) >> 1;
    v25 = (const WCHAR *)(**(__int64 (__fastcall ***)(__int64))(v20 + 112 * v24))(v20 + 112 * v24);
    v26 = CompareStringW(0x7Fu, 0, L"System.StructuredQueryType.Action", -1, v25, -1);
    if ( v26 == 2 )
    {
      v21 = (const struct SemanticsUM::SchemaBinary *)(v20 + 112 * v24);
    }
    else if ( v26 == 1 )
    {
      v23 = (v23 + v22) >> 1;
    }
    else
    {
      v22 = v24 + 1;
    }
  }
  while ( !v21 );
  this[5] = v21;
  v27 = this[1];
  v28 = *((_QWORD *)v27 + 5);
  v29 = 0;
  v30 = 0;
  v31 = *((_DWORD *)v27 + 8);
  do
  {
    if ( v30 >= v31 )
      break;
    v32 = (v31 + v30) >> 1;
    v33 = (const WCHAR *)(**(__int64 (__fastcall ***)(__int64))(v28 + 112 * v32))(v28 + 112 * v32);
    v34 = CompareStringW(0x7Fu, 0, L"System.StructuredQueryType.Value", -1, v33, -1);
    if ( v34 == 2 )
    {
      v29 = (const struct SemanticsUM::SchemaBinary *)(v28 + 112 * v32);
    }
    else if ( v34 == 1 )
    {
      v31 = (v31 + v30) >> 1;
    }
    else
    {
      v30 = v32 + 1;
    }
  }
  while ( !v29 );
  this[6] = v29;
  v35 = this[1];
  v36 = *((_QWORD *)v35 + 5);
  v37 = 0;
  v38 = 0;
  v39 = *((_DWORD *)v35 + 8);
  do
  {
    if ( v38 >= v39 )
      break;
    v40 = (v39 + v38) >> 1;
    v41 = (const WCHAR *)(**(__int64 (__fastcall ***)(__int64))(v36 + 112 * v40))(v36 + 112 * v40);
    v42 = CompareStringW(0x7Fu, 0, L"System.StructuredQueryType.Number", -1, v41, -1);
    if ( v42 == 2 )
    {
      v37 = (const struct SemanticsUM::SchemaBinary *)(v36 + 112 * v40);
    }
    else if ( v42 == 1 )
    {
      v39 = (v39 + v38) >> 1;
    }
    else
    {
      v38 = v40 + 1;
    }
  }
  while ( !v37 );
  this[7] = v37;
  v43 = this[1];
  v44 = *((_QWORD *)v43 + 5);
  v45 = 0;
  v46 = 0;
  v47 = *((_DWORD *)v43 + 8);
  do
  {
    if ( v46 >= v47 )
      break;
    v48 = (v47 + v46) >> 1;
    v49 = (const WCHAR *)(**(__int64 (__fastcall ***)(__int64))(v44 + 112 * v48))(v44 + 112 * v48);
    v50 = CompareStringW(0x7Fu, 0, L"System.StructuredQueryType.Integer", -1, v49, -1);
    if ( v50 == 2 )
    {
      v45 = (const struct SemanticsUM::SchemaBinary *)(v44 + 112 * v48);
    }
    else if ( v50 == 1 )
    {
      v47 = (v47 + v46) >> 1;
    }
    else
    {
      v46 = v48 + 1;
    }
  }
  while ( !v45 );
  this[8] = v45;
  v51 = this[1];
  v52 = *((_QWORD *)v51 + 5);
  v53 = 0;
  v54 = 0;
  v55 = *((_DWORD *)v51 + 8);
  do
  {
    if ( v54 >= v55 )
      break;
    v56 = (v55 + v54) >> 1;
    v57 = (const WCHAR *)(**(__int64 (__fastcall ***)(__int64))(v52 + 112 * v56))(v52 + 112 * v56);
    v58 = CompareStringW(0x7Fu, 0, L"System.StructuredQueryType.FloatingPoint", -1, v57, -1);
    if ( v58 == 2 )
    {
      v53 = (const struct SemanticsUM::SchemaBinary *)(v52 + 112 * v56);
    }
    else if ( v58 == 1 )
    {
      v55 = (v55 + v54) >> 1;
    }
    else
    {
      v54 = v56 + 1;
    }
  }
  while ( !v53 );
  this[9] = v53;
  v59 = this[1];
  v60 = *((_QWORD *)v59 + 5);
  v61 = 0;
  v62 = 0;
  v63 = *((_DWORD *)v59 + 8);
  do
  {
    if ( v62 >= v63 )
      break;
    v64 = (v63 + v62) >> 1;
    v65 = (const WCHAR *)(**(__int64 (__fastcall ***)(__int64))(v60 + 112 * v64))(v60 + 112 * v64);
    v66 = CompareStringW(0x7Fu, 0, L"System.StructuredQueryType.String", -1, v65, -1);
    if ( v66 == 2 )
    {
      v61 = (const struct SemanticsUM::SchemaBinary *)(v60 + 112 * v64);
    }
    else if ( v66 == 1 )
    {
      v63 = (v63 + v62) >> 1;
    }
    else
    {
      v62 = v64 + 1;
    }
  }
  while ( !v61 );
  this[10] = v61;
  v67 = this[1];
  v68 = *((_QWORD *)v67 + 5);
  v69 = 0;
  v70 = 0;
  v71 = *((_DWORD *)v67 + 8);
  do
  {
    if ( v70 >= v71 )
      break;
    v72 = (v71 + v70) >> 1;
    v73 = (const WCHAR *)(**(__int64 (__fastcall ***)(__int64))(v68 + 112 * v72))(v68 + 112 * v72);
    v74 = CompareStringW(0x7Fu, 0, L"System.StructuredQueryType.Boolean", -1, v73, -1);
    if ( v74 == 2 )
    {
      v69 = (const struct SemanticsUM::SchemaBinary *)(v68 + 112 * v72);
    }
    else if ( v74 == 1 )
    {
      v71 = (v71 + v70) >> 1;
    }
    else
    {
      v70 = v72 + 1;
    }
  }
  while ( !v69 );
  this[11] = v69;
  v75 = this[1];
  v76 = *((_QWORD *)v75 + 5);
  v77 = 0;
  v78 = 0;
  v79 = *((_DWORD *)v75 + 8);
  do
  {
    if ( v78 >= v79 )
      break;
    v80 = (v79 + v78) >> 1;
    v81 = (const WCHAR *)(**(__int64 (__fastcall ***)(__int64))(v76 + 112 * v80))(v76 + 112 * v80);
    v82 = CompareStringW(0x7Fu, 0, L"System.StructuredQueryType.DateTime", -1, v81, -1);
    if ( v82 == 2 )
    {
      v77 = (const struct SemanticsUM::SchemaBinary *)(v76 + 112 * v80);
    }
    else if ( v82 == 1 )
    {
      v79 = (v79 + v78) >> 1;
    }
    else
    {
      v78 = v80 + 1;
    }
  }
  while ( !v77 );
  this[12] = v77;
  v83 = this[1];
  v84 = *((_QWORD *)v83 + 5);
  v85 = 0;
  v86 = 0;
  v87 = *((_DWORD *)v83 + 8);
  do
  {
    if ( v86 >= v87 )
      break;
    v88 = (v87 + v86) >> 1;
    v89 = (const WCHAR *)(**(__int64 (__fastcall ***)(__int64))(v84 + 112 * v88))(v84 + 112 * v88);
    v90 = CompareStringW(0x7Fu, 0, L"System.StructuredQueryType.Blurb", -1, v89, -1);
    if ( v90 == 2 )
    {
      v85 = (const struct SemanticsUM::SchemaBinary *)(v84 + 112 * v88);
    }
    else if ( v90 == 1 )
    {
      v87 = (v87 + v86) >> 1;
    }
    else
    {
      v86 = v88 + 1;
    }
  }
  while ( !v85 );
  this[13] = v85;
  v91 = this[1];
  v92 = *((_QWORD *)v91 + 5);
  v93 = 0;
  v94 = 0;
  v95 = *((_DWORD *)v91 + 8);
  do
  {
    if ( v94 >= v95 )
      break;
    v96 = (v95 + v94) >> 1;
    v97 = (const WCHAR *)(**(__int64 (__fastcall ***)(__int64))(v92 + 112 * v96))(v92 + 112 * v96);
    v98 = CompareStringW(0x7Fu, 0, L"System.StructuredQueryType.NaturalLanguageText", -1, v97, -1);
    if ( v98 == 2 )
    {
      v93 = (const struct SemanticsUM::SchemaBinary *)(v92 + 112 * v96);
    }
    else if ( v98 == 1 )
    {
      v95 = (v95 + v94) >> 1;
    }
    else
    {
      v94 = v96 + 1;
    }
  }
  while ( !v93 );
  this[14] = v93;
  v99 = this[1];
  v100 = *((_QWORD *)v99 + 5);
  v101 = 0;
  v102 = 0;
  v103 = *((_DWORD *)v99 + 8);
  do
  {
    if ( v102 >= v103 )
      break;
    v104 = (v103 + v102) >> 1;
    v105 = (const WCHAR *)(**(__int64 (__fastcall ***)(__int64))(v100 + 112 * v104))(v100 + 112 * v104);
    v106 = CompareStringW(0x7Fu, 0, L"System.StructuredQueryType.FilePath", -1, v105, -1);
    if ( v106 == 2 )
    {
      v101 = (const struct SemanticsUM::SchemaBinary *)(v100 + 112 * v104);
    }
    else if ( v106 == 1 )
    {
      v103 = (v103 + v102) >> 1;
    }
    else
    {
      v102 = v104 + 1;
    }
  }
  while ( !v101 );
  this[15] = v101;
  v107 = this[1];
  v108 = *((_QWORD *)v107 + 5);
  v109 = 0;
  v110 = 0;
  v111 = *((_DWORD *)v107 + 8);
  do
  {
    if ( v110 >= v111 )
      break;
    v112 = (v111 + v110) >> 1;
    v113 = (const WCHAR *)(**(__int64 (__fastcall ***)(__int64))(v108 + 112 * v112))(v108 + 112 * v112);
    v114 = CompareStringW(0x7Fu, 0, L"System.StructuredQueryType.Null", -1, v113, -1);
    if ( v114 == 2 )
    {
      v109 = (const struct SemanticsUM::SchemaBinary *)(v108 + 112 * v112);
    }
    else if ( v114 == 1 )
    {
      v111 = (v111 + v110) >> 1;
    }
    else
    {
      v110 = v112 + 1;
    }
  }
  while ( !v109 );
  this[16] = v109;
  v115 = this[1];
  v116 = *((_QWORD *)v115 + 22);
  v117 = 0;
  v118 = 0;
  v119 = *((_DWORD *)v115 + 42);
  do
  {
    if ( v118 >= v119 )
      break;
    v120 = CompareStringW(0x7Fu, 0, L"and", -1, *(PCNZWCH *)(v116 + 24LL * ((v119 + v118) >> 1)), -1);
    if ( v120 == 2 )
    {
      v117 = (const struct SemanticsUM::SchemaBinary *)(v116 + 24LL * ((v119 + v118) >> 1));
    }
    else if ( v120 == 1 )
    {
      v119 = (v119 + v118) >> 1;
    }
    else
    {
      v118 = ((v119 + v118) >> 1) + 1;
    }
  }
  while ( !v117 );
  this[17] = v117;
  v121 = this[1];
  v122 = *((_QWORD *)v121 + 22);
  v123 = 0;
  v124 = 0;
  v125 = *((_DWORD *)v121 + 42);
  do
  {
    if ( v124 >= v125 )
      break;
    v126 = CompareStringW(0x7Fu, 0, L"or", -1, *(PCNZWCH *)(v122 + 24LL * ((v125 + v124) >> 1)), -1);
    if ( v126 == 2 )
    {
      v123 = (const struct SemanticsUM::SchemaBinary *)(v122 + 24LL * ((v125 + v124) >> 1));
    }
    else if ( v126 == 1 )
    {
      v125 = (v125 + v124) >> 1;
    }
    else
    {
      v124 = ((v125 + v124) >> 1) + 1;
    }
  }
  while ( !v123 );
  this[18] = v123;
  v127 = this[1];
  v128 = *((_QWORD *)v127 + 22);
  v129 = 0;
  v130 = 0;
  v131 = *((_DWORD *)v127 + 42);
  do
  {
    if ( v130 >= v131 )
      break;
    v132 = CompareStringW(0x7Fu, 0, L"not", -1, *(PCNZWCH *)(v128 + 24LL * ((v131 + v130) >> 1)), -1);
    if ( v132 == 2 )
    {
      v129 = (const struct SemanticsUM::SchemaBinary *)(v128 + 24LL * ((v131 + v130) >> 1));
    }
    else if ( v132 == 1 )
    {
      v131 = (v131 + v130) >> 1;
    }
    else
    {
      v130 = ((v131 + v130) >> 1) + 1;
    }
  }
  while ( !v129 );
  this[19] = v129;
  return 0;
}

```

## disassembly

```asm
0x180026b00  push    rbx
0x180026b02  push    rbp
0x180026b03  push    rsi
0x180026b04  push    rdi
0x180026b05  push    r12
0x180026b07  push    r13
0x180026b09  push    r14
0x180026b0b  push    r15
0x180026b0d  sub     rsp, 38h
0x180026b11  mov     rbx, rcx
0x180026b14  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026b1b  mov     ecx, 4; unsigned __int64
0x180026b20  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180026b25  mov     [rsp+78h+arg_0], rax
0x180026b2d  test    rax, rax
0x180026b30  jz      short loc_180026B3F
0x180026b32  mov     rdx, [rbx+8]; struct SemanticsUM::SchemaBinary *
0x180026b36  mov     rcx, rax; this
0x180026b39  call    ??0CultureState@SemanticsUM@@QEAA@PEBVSchemaBinary@1@@Z; SemanticsUM::CultureState::CultureState(SemanticsUM::SchemaBinary const *)
0x180026b3e  nop
0x180026b3f  mov     [rbx+10h], rax
0x180026b43  test    rax, rax
0x180026b46  jz      loc_1800273CA
0x180026b4c  mov     rax, [rbx+8]
0x180026b50  mov     r12, [rax+28h]
0x180026b54  xor     edi, edi
0x180026b56  xor     esi, esi
0x180026b58  mov     r14d, [rax+20h]
0x180026b5c  lea     r13d, [rdi+1]
0x180026b60  cmp     esi, r14d
0x180026b63  jnb     short loc_180026BBB
0x180026b65  lea     ebp, [r14+rsi]
0x180026b69  shr     ebp, 1
0x180026b6b  imul    r15, rbp, 70h ; 'p'
0x180026b6f  add     r15, r12
0x180026b72  mov     rax, [r15]
0x180026b75  mov     rcx, r15
0x180026b78  mov     rax, [rax]
0x180026b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b80  or      ecx, 0FFFFFFFFh
0x180026b83  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x180026b87  mov     [rsp+78h+lpString2], rax; lpString2
0x180026b8c  mov     r9d, ecx; cchCount1
0x180026b8f  lea     r8, String1; "System.StructuredQueryType.Entity"
0x180026b96  xor     edx, edx; dwCmpFlags
0x180026b98  lea     ecx, [rdx+7Fh]; Locale
0x180026b9b  call    cs:__imp_CompareStringW
0x180026ba1  cmp     eax, 2
0x180026ba4  jz      loc_1800272EA
0x180026baa  cmp     eax, r13d
0x180026bad  jnz     loc_18002735A
0x180026bb3  mov     r14d, ebp
0x180026bb6  test    rdi, rdi
0x180026bb9  jz      short loc_180026B60
0x180026bbb  mov     [rbx+18h], rdi
0x180026bbf  mov     rax, [rbx+8]
0x180026bc3  mov     r12, [rax+28h]
0x180026bc7  xor     edi, edi
0x180026bc9  xor     esi, esi
0x180026bcb  mov     r14d, [rax+20h]
0x180026bcf  cmp     esi, r14d
0x180026bd2  jnb     short loc_180026C2A
0x180026bd4  lea     ebp, [r14+rsi]
0x180026bd8  shr     ebp, 1
0x180026bda  imul    r15, rbp, 70h ; 'p'
0x180026bde  add     r15, r12
0x180026be1  mov     rax, [r15]
0x180026be4  mov     rcx, r15
0x180026be7  mov     rax, [rax]
0x180026bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026bef  or      ecx, 0FFFFFFFFh
0x180026bf2  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x180026bf6  mov     [rsp+78h+lpString2], rax; lpString2
0x180026bfb  mov     r9d, ecx; cchCount1
0x180026bfe  lea     r8, aSystemStructur_23; "System.StructuredQueryType.Object"
0x180026c05  xor     edx, edx; dwCmpFlags
0x180026c07  lea     ecx, [rdx+7Fh]; Locale
0x180026c0a  call    cs:__imp_CompareStringW
0x180026c10  cmp     eax, 2
0x180026c13  jz      loc_1800272F2
0x180026c19  cmp     eax, r13d
0x180026c1c  jnz     loc_180027362
0x180026c22  mov     r14d, ebp
0x180026c25  test    rdi, rdi
0x180026c28  jz      short loc_180026BCF
0x180026c2a  mov     [rbx+20h], rdi
0x180026c2e  mov     rax, [rbx+8]
0x180026c32  mov     r12, [rax+28h]
0x180026c36  xor     edi, edi
0x180026c38  xor     esi, esi
0x180026c3a  mov     r14d, [rax+20h]
0x180026c3e  cmp     esi, r14d
0x180026c41  jnb     short loc_180026C99
0x180026c43  lea     ebp, [r14+rsi]
0x180026c47  shr     ebp, 1
0x180026c49  imul    r15, rbp, 70h ; 'p'
0x180026c4d  add     r15, r12
0x180026c50  mov     rax, [r15]
0x180026c53  mov     rcx, r15
0x180026c56  mov     rax, [rax]
0x180026c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c5e  or      ecx, 0FFFFFFFFh
0x180026c61  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x180026c65  mov     [rsp+78h+lpString2], rax; lpString2
0x180026c6a  mov     r9d, ecx; cchCount1
0x180026c6d  lea     r8, aSystemStructur_1; "System.StructuredQueryType.Action"
0x180026c74  xor     edx, edx; dwCmpFlags
0x180026c76  lea     ecx, [rdx+7Fh]; Locale
0x180026c79  call    cs:__imp_CompareStringW
0x180026c7f  cmp     eax, 2
0x180026c82  jz      loc_1800272FA
0x180026c88  cmp     eax, r13d
0x180026c8b  jnz     loc_18002736A
0x180026c91  mov     r14d, ebp
0x180026c94  test    rdi, rdi
0x180026c97  jz      short loc_180026C3E
0x180026c99  mov     [rbx+28h], rdi
0x180026c9d  mov     rax, [rbx+8]
0x180026ca1  mov     r12, [rax+28h]
0x180026ca5  xor     edi, edi
0x180026ca7  xor     esi, esi
0x180026ca9  mov     r14d, [rax+20h]
0x180026cad  cmp     esi, r14d
0x180026cb0  jnb     short loc_180026D08
0x180026cb2  lea     ebp, [r14+rsi]
0x180026cb6  shr     ebp, 1
0x180026cb8  imul    r15, rbp, 70h ; 'p'
0x180026cbc  add     r15, r12
0x180026cbf  mov     rax, [r15]
0x180026cc2  mov     rcx, r15
0x180026cc5  mov     rax, [rax]
0x180026cc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ccd  or      ecx, 0FFFFFFFFh
0x180026cd0  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x180026cd4  mov     [rsp+78h+lpString2], rax; lpString2
0x180026cd9  mov     r9d, ecx; cchCount1
0x180026cdc  lea     r8, aSystemStructur_2; "System.StructuredQueryType.Value"
0x180026ce3  xor     edx, edx; dwCmpFlags
0x180026ce5  lea     ecx, [rdx+7Fh]; Locale
0x180026ce8  call    cs:__imp_CompareStringW
0x180026cee  cmp     eax, 2
0x180026cf1  jz      loc_180027302
0x180026cf7  cmp     eax, r13d
0x180026cfa  jnz     loc_180027372
0x180026d00  mov     r14d, ebp
0x180026d03  test    rdi, rdi
0x180026d06  jz      short loc_180026CAD
0x180026d08  mov     [rbx+30h], rdi
0x180026d0c  mov     rax, [rbx+8]
0x180026d10  mov     r12, [rax+28h]
0x180026d14  xor     edi, edi
0x180026d16  xor     esi, esi
0x180026d18  mov     r14d, [rax+20h]
0x180026d1c  cmp     esi, r14d
0x180026d1f  jnb     short loc_180026D77
0x180026d21  lea     ebp, [r14+rsi]
0x180026d25  shr     ebp, 1
0x180026d27  imul    r15, rbp, 70h ; 'p'
0x180026d2b  add     r15, r12
0x180026d2e  mov     rax, [r15]
0x180026d31  mov     rcx, r15
0x180026d34  mov     rax, [rax]
0x180026d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d3c  or      ecx, 0FFFFFFFFh
0x180026d3f  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x180026d43  mov     [rsp+78h+lpString2], rax; lpString2
0x180026d48  mov     r9d, ecx; cchCount1
0x180026d4b  lea     r8, aSystemStructur_15; "System.StructuredQueryType.Number"
0x180026d52  xor     edx, edx; dwCmpFlags
0x180026d54  lea     ecx, [rdx+7Fh]; Locale
0x180026d57  call    cs:__imp_CompareStringW
0x180026d5d  cmp     eax, 2
0x180026d60  jz      loc_18002730A
0x180026d66  cmp     eax, r13d
0x180026d69  jnz     loc_18002737A
0x180026d6f  mov     r14d, ebp
0x180026d72  test    rdi, rdi
0x180026d75  jz      short loc_180026D1C
0x180026d77  mov     [rbx+38h], rdi
0x180026d7b  mov     rax, [rbx+8]
0x180026d7f  mov     r12, [rax+28h]
0x180026d83  xor     edi, edi
0x180026d85  xor     esi, esi
0x180026d87  mov     r14d, [rax+20h]
0x180026d8b  cmp     esi, r14d
0x180026d8e  jnb     short loc_180026DE6
0x180026d90  lea     ebp, [r14+rsi]
0x180026d94  shr     ebp, 1
0x180026d96  imul    r15, rbp, 70h ; 'p'
0x180026d9a  add     r15, r12
0x180026d9d  mov     rax, [r15]
0x180026da0  mov     rcx, r15
0x180026da3  mov     rax, [rax]
0x180026da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026dab  or      ecx, 0FFFFFFFFh
0x180026dae  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x180026db2  mov     [rsp+78h+lpString2], rax; lpString2
0x180026db7  mov     r9d, ecx; cchCount1
0x180026dba  lea     r8, aSystemStructur_14; "System.StructuredQueryType.Integer"
0x180026dc1  xor     edx, edx; dwCmpFlags
0x180026dc3  lea     ecx, [rdx+7Fh]; Locale
0x180026dc6  call    cs:__imp_CompareStringW
0x180026dcc  cmp     eax, 2
0x180026dcf  jz      loc_180027312
0x180026dd5  cmp     eax, r13d
0x180026dd8  jnz     loc_180027382
0x180026dde  mov     r14d, ebp
0x180026de1  test    rdi, rdi
0x180026de4  jz      short loc_180026D8B
0x180026de6  mov     [rbx+40h], rdi
0x180026dea  mov     rax, [rbx+8]
0x180026dee  mov     r12, [rax+28h]
0x180026df2  xor     edi, edi
0x180026df4  xor     esi, esi
0x180026df6  mov     r14d, [rax+20h]
0x180026dfa  cmp     esi, r14d
0x180026dfd  jnb     short loc_180026E55
0x180026dff  lea     ebp, [r14+rsi]
0x180026e03  shr     ebp, 1
0x180026e05  imul    r15, rbp, 70h ; 'p'
0x180026e09  add     r15, r12
0x180026e0c  mov     rax, [r15]
0x180026e0f  mov     rcx, r15
0x180026e12  mov     rax, [rax]
0x180026e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e1a  or      ecx, 0FFFFFFFFh
0x180026e1d  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x180026e21  mov     [rsp+78h+lpString2], rax; lpString2
0x180026e26  mov     r9d, ecx; cchCount1
0x180026e29  lea     r8, aSystemStructur_29; "System.StructuredQueryType.FloatingPoin"...
0x180026e30  xor     edx, edx; dwCmpFlags
0x180026e32  lea     ecx, [rdx+7Fh]; Locale
0x180026e35  call    cs:__imp_CompareStringW
0x180026e3b  cmp     eax, 2
0x180026e3e  jz      loc_18002731A
0x180026e44  cmp     eax, r13d
0x180026e47  jnz     loc_18002738A
0x180026e4d  mov     r14d, ebp
0x180026e50  test    rdi, rdi
0x180026e53  jz      short loc_180026DFA
0x180026e55  mov     [rbx+48h], rdi
0x180026e59  mov     rax, [rbx+8]
0x180026e5d  mov     r12, [rax+28h]
0x180026e61  xor     edi, edi
0x180026e63  xor     esi, esi
0x180026e65  mov     r14d, [rax+20h]
0x180026e69  cmp     esi, r14d
0x180026e6c  jnb     short loc_180026EC4
0x180026e6e  lea     ebp, [r14+rsi]
0x180026e72  shr     ebp, 1
0x180026e74  imul    r15, rbp, 70h ; 'p'
0x180026e78  add     r15, r12
0x180026e7b  mov     rax, [r15]
0x180026e7e  mov     rcx, r15
0x180026e81  mov     rax, [rax]
0x180026e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e89  or      ecx, 0FFFFFFFFh
0x180026e8c  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x180026e90  mov     [rsp+78h+lpString2], rax; lpString2
0x180026e95  mov     r9d, ecx; cchCount1
0x180026e98  lea     r8, aSystemStructur_24; "System.StructuredQueryType.String"
0x180026e9f  xor     edx, edx; dwCmpFlags
0x180026ea1  lea     ecx, [rdx+7Fh]; Locale
0x180026ea4  call    cs:__imp_CompareStringW
0x180026eaa  cmp     eax, 2
0x180026ead  jz      loc_180027322
0x180026eb3  cmp     eax, r13d
0x180026eb6  jnz     loc_180027392
0x180026ebc  mov     r14d, ebp
0x180026ebf  test    rdi, rdi
0x180026ec2  jz      short loc_180026E69
0x180026ec4  mov     [rbx+50h], rdi
0x180026ec8  mov     rax, [rbx+8]
0x180026ecc  mov     r12, [rax+28h]
0x180026ed0  xor     edi, edi
0x180026ed2  xor     esi, esi
0x180026ed4  mov     r14d, [rax+20h]
0x180026ed8  cmp     esi, r14d
0x180026edb  jnb     short loc_180026F33
0x180026edd  lea     ebp, [r14+rsi]
0x180026ee1  shr     ebp, 1
0x180026ee3  imul    r15, rbp, 70h ; 'p'
0x180026ee7  add     r15, r12
0x180026eea  mov     rax, [r15]
0x180026eed  mov     rcx, r15
0x180026ef0  mov     rax, [rax]
0x180026ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ef8  or      ecx, 0FFFFFFFFh
0x180026efb  mov     [rsp+78h+cchCount2], ecx; cchCount2
0x180026eff  mov     [rsp+78h+lpString2], rax; lpString2
0x180026f04  mov     r9d, ecx; cchCount1
0x180026f07  lea     r8, aSystemStructur_13; "System.StructuredQueryType.Boolean"
0x180026f0e  xor     edx, edx; dwCmpFlags
0x180026f10  lea     ecx, [rdx+7Fh]; Locale
0x180026f13  call    cs:__imp_CompareStringW
0x180026f19  cmp     eax, 2
0x180026f1c  jz      loc_18002732A
0x180026f22  cmp     eax, r13d
0x180026f25  jnz     loc_18002739A
0x180026f2b  mov     r14d, ebp
  ... truncated ...
```
