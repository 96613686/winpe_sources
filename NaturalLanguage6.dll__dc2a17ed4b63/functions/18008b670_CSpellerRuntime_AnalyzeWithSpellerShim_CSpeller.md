# CSpellerRuntime::AnalyzeWithSpellerShim(CSpeller *)

- ea: `0x18008b670`
- end: `0x18008c632`
- name: `?AnalyzeWithSpellerShim@CSpellerRuntime@@IEAAXPEAVCSpeller@@@Z`
- size: `4034`
- prototype: `void __fastcall(struct CSentence **this, struct CSpeller *)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18008b540`

## callees

- `0x1800088b0`
- `0x180008d70`
- `0x18000b1a0`
- `0x180026a2c`
- `0x18002a918`
- `0x18002aa94`
- `0x18002be20`
- `0x18002c0d0`
- `0x1800543d8`
- `0x180054478`
- `0x18005de3c`
- `0x18005dfa0`
- `0x180068928`
- `0x180068bd4`
- `0x180068d04`
- `0x180069e64`
- `0x180069f58`
- `0x18008b670`
- `0x18008cf64`
- `0x18008d14c`
- `0x18008d408`
- `0x18008ea50`
- `0x18009e300`
- `0x1800b0010`

## import_xrefs

- `msvcrt!wcschr` at `0x18008bb51`
- `msvcrt!wcschr` at `0x18008bb51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008ba3b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18008ba3b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008b9ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008b9ff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008ba30`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008ba30`

## pseudocode

```c
void __fastcall CSpellerRuntime::AnalyzeWithSpellerShim(struct CSentence **this, struct CSpeller *a2)
{
  CSpellerRuntime *v2; // r13
  __int64 v4; // rax
  __int64 v5; // rax
  struct ILspRuntime *LspRuntime; // rax
  struct CZoneHeap *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  int v10; // r9d
  __int64 v11; // rcx
  __int64 v12; // r15
  unsigned __int64 v13; // r12
  int v14; // ecx
  void *v15; // r8
  int v16; // edi
  int i; // esi
  struct INLTopLexicon *v18; // rdi
  __int16 v19; // bx
  __int64 v20; // rdx
  __int64 v21; // rax
  CSpellerRuntime *v22; // rcx
  unsigned int v23; // ebx
  int v24; // edx
  int v25; // ecx
  bool v26; // cf
  char v27; // al
  int v28; // edx
  void (__fastcall *v29)(_QWORD, _QWORD, _QWORD); // rax
  void (__fastcall *v30)(_QWORD, _QWORD, char *); // rax
  __int64 v31; // rcx
  __int64 v32; // rbx
  unsigned __int64 v33; // rsi
  const unsigned __int16 *v34; // rdx
  char v35; // bl
  HKEY v36; // rdi
  __int64 v37; // rcx
  wchar_t *v38; // rbx
  unsigned __int16 v39; // ax
  int v40; // eax
  struct CSentence *v41; // rcx
  unsigned __int64 v42; // rdx
  unsigned __int64 v43; // r13
  int v44; // edi
  unsigned __int64 v45; // rbx
  struct CWordNode *v46; // rax
  int v47; // edi
  int v48; // edi
  int v49; // edi
  int v50; // edi
  int v51; // edi
  int v52; // edi
  __int64 v53; // rcx
  int v54; // edi
  int v55; // edi
  __int64 v56; // rcx
  __int64 v57; // rcx
  _DWORD *v58; // roff
  struct CZoneHeap *v59; // rbx
  CNodeProperties *v60; // rsi
  __int64 v61; // rcx
  __int64 NextPropertyFor; // rax
  struct CNodeProperty *v63; // rbx
  __int64 v64; // rax
  _QWORD *v65; // rdi
  __int64 v66; // rax
  __int64 v67; // r8
  __int64 v68; // rcx
  __int64 v69; // rdx
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rcx
  __int64 v73; // rax
  struct CNodeProperty *v74; // rbx
  _QWORD *v75; // rdi
  __int64 v76; // r8
  __int64 v77; // rcx
  __int64 v78; // rdx
  __int64 v79; // rax
  __int64 v80; // rax
  __int64 v81; // rcx
  struct CWordNode *v82; // rsi
  unsigned __int16 v83; // r9
  int v84; // r9d
  int v85; // ecx
  __int64 v86; // rdx
  struct CZoneHeap *v87; // rbx
  CNodeProperties *v88; // r12
  __int64 v89; // rcx
  __int64 v90; // rax
  struct CNodeProperty *v91; // rbx
  __int64 v92; // rax
  _QWORD *v93; // r15
  __int64 v94; // rax
  __int64 v95; // r8
  __int64 v96; // rcx
  __int64 v97; // rdx
  __int64 v98; // rax
  __int64 v99; // rax
  __int64 v100; // rcx
  __int64 v101; // rax
  struct CNodeProperty *v102; // rbx
  _QWORD *v103; // r15
  __int64 v104; // r8
  __int64 v105; // rcx
  __int64 v106; // rdx
  __int64 v107; // rax
  __int64 v108; // rax
  unsigned int v109; // eax
  __int64 v110; // rdx
  unsigned int v111; // ecx
  int v112; // edi
  int v113; // edi
  int v114; // edi
  int v115; // edi
  int v116; // edi
  int v117; // edi
  int v118; // edi
  unsigned int v119; // ecx
  __int64 v120; // r12
  unsigned __int16 *v121; // rax
  int v122; // ecx
  int v123; // edx
  struct CZoneHeap *v124; // rbx
  CNodeProperties *v125; // r15
  __int64 v126; // rcx
  __int64 v127; // rax
  struct CNodeProperty *v128; // rbx
  __int64 v129; // rax
  _QWORD *v130; // rdi
  __int64 v131; // rax
  __int64 v132; // r8
  __int64 v133; // rcx
  __int64 v134; // rdx
  __int64 v135; // rax
  __int64 v136; // rax
  __int64 v137; // rcx
  __int64 v138; // rax
  struct CNodeProperty *v139; // rbx
  _QWORD *v140; // rdi
  __int64 v141; // r8
  __int64 v142; // rcx
  int v143; // ebx
  __int64 v144; // rdx
  __int64 v145; // rax
  __int64 v146; // rax
  __int64 v147; // rdx
  unsigned int v148; // ecx
  int v149; // edi
  int v150; // edi
  int v151; // edi
  int v152; // edi
  int v153; // edi
  int v154; // edi
  int v155; // edi
  unsigned int v156; // ecx
  int phkResult; // [rsp+20h] [rbp-E0h]
  char v158; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v160; // [rsp+40h] [rbp-C0h]
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct CZoneHeap *v162; // [rsp+50h] [rbp-B0h]
  __int16 v163; // [rsp+58h] [rbp-A8h]
  BOOL v164; // [rsp+5Ch] [rbp-A4h]
  BYTE Data[4]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v166; // [rsp+68h] [rbp-98h]
  unsigned __int64 v167; // [rsp+70h] [rbp-90h]
  __int128 v168; // [rsp+78h] [rbp-88h] BYREF
  __int16 v169; // [rsp+88h] [rbp-78h]
  __int64 v170; // [rsp+90h] [rbp-70h]
  unsigned __int64 v171; // [rsp+98h] [rbp-68h]
  __int128 v172; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v173; // [rsp+B0h] [rbp-50h]
  __int128 v174; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v175[72]; // [rsp+D0h] [rbp-30h] BYREF

  v2 = (CSpellerRuntime *)this;
  v4 = (*(__int64 (__fastcall **)(struct CSentence *))(*(_QWORD *)this[3] + 80LL))(this[3]);
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 24LL))(v4);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 88LL))(v5);
  LspRuntime = CSentence::GetLspRuntime(*((CSentence **)v2 + 3));
  v7 = (struct CZoneHeap *)(*(__int64 (__fastcall **)(struct ILspRuntime *))(*(_QWORD *)LspRuntime + 24LL))(LspRuntime);
  v8 = *((_QWORD *)v2 + 3);
  v162 = v7;
  v9 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v8 + 168) + 136LL))(*(_QWORD *)(v8 + 168));
  v11 = *((_QWORD *)v2 + 3);
  v12 = v9;
  v13 = 0;
  v166 = v9;
  v164 = *(_BYTE *)(v9 + 286) != 0;
  LOWORD(v9) = *(_WORD *)(v11 + 176) & 0x3FF;
  v14 = *(_DWORD *)(v12 + 424);
  v163 = v9;
  if ( *((_DWORD *)v2 + 9) != v14 )
  {
    *((_DWORD *)v2 + 9) = v14;
    v15 = (void *)*((_QWORD *)a2 + 6);
    if ( v15 )
      CProofAPI::CloseLex(*((CProofAPI **)a2 + 1), *((void **)a2 + 2), v15, v10);
    v16 = 0;
    for ( *((_QWORD *)a2 + 6) = 0; v16 < *((_DWORD *)a2 + 428); ++v16 )
      CProofAPI::CloseLex(
        *((CProofAPI **)a2 + 1),
        *((void **)a2 + 2),
        *(void **)(*((_QWORD *)a2 + 113) + 8LL * v16),
        v10);
    *((_DWORD *)a2 + 428) = 0;
    for ( i = *(unsigned __int16 *)(v12 + 428) - 1; i >= 0; --i )
    {
      *((_QWORD *)&v168 + 1) = 0x400000001LL;
      v169 = -1;
      *(_QWORD *)&v172 = 0;
      LODWORD(v173) = 0;
      v18 = CContext::LexAt((CContext *)v12, (unsigned int)i);
      v19 = *(_WORD *)(*((_QWORD *)v2 + 3) + 176LL);
      if ( (v19 == (*(unsigned __int16 (__fastcall **)(struct INLTopLexicon *))(*(_QWORD *)v18 + 40LL))(v18)
         || ((*(__int64 (__fastcall **)(struct INLTopLexicon *))(*(_QWORD *)v18 + 40LL))(v18) & 0x3FF) == 0)
        && (*(unsigned int (__fastcall **)(struct INLTopLexicon *))(*(_QWORD *)v18 + 72LL))(v18) == 3 )
      {
        HIDWORD(v168) = *(_DWORD *)(*((_QWORD *)v18 + 13) + 24LL);
        v20 = *((_QWORD *)v18 + 13) + 36LL;
        v21 = -1;
        do
          ++v21;
        while ( *(_WORD *)(v20 + 2 * v21) );
        DWORD2(v168) = 0;
        v169 = -1;
        v22 = (CSpellerRuntime *)(v20 & -(__int64)(v21 != 0));
        *(_QWORD *)&v168 = v22;
        v172 = 0;
        v173 = 0;
        if ( *(_BYTE *)(*((_QWORD *)v18 + 13) + 1660LL) )
        {
          CSpellerRuntime::SyncInternalLexOn(v22, a2, v18);
        }
        else if ( v22 )
        {
          CProof::OpenLex(a2, (struct PROOFLEXIN *)&v168, (struct PROOFLEXOUT *)&v172);
        }
      }
    }
  }
  v23 = (*(_BYTE *)(v12 + 293) != 0 ? 2 : 0)
      | (*(_BYTE *)(v12 + 297) != 0 ? 0x20000 : 0)
      | (*(_BYTE *)(v12 + 294) != 0 ? 4 : 0)
      | (*(_BYTE *)(v12 + 296) != 0 ? 0x40 : 0)
      | (1025 - (*(_BYTE *)(v12 + 292) != 0));
  switch ( *(_WORD *)(*((_QWORD *)v2 + 3) + 176LL) & 0x3FF )
  {
    case 1:
      v26 = *(_BYTE *)(v12 + 313) != 0;
      v27 = *(_BYTE *)(v12 + 312);
      goto LABEL_29;
    case 7:
      v23 |= *(_BYTE *)(v12 + 308) != 0 ? 0x10000000 : 0;
      break;
    case 12:
      v28 = *(_DWORD *)(v12 + 304);
      v26 = *(_BYTE *)(v12 + 300) != 0;
      hKey = 0;
      *(_DWORD *)Data = v28;
      v23 |= v26 ? 0x20000000 : 0;
      if ( v28 != *((_DWORD *)v2 + 17) )
      {
        *((_DWORD *)v2 + 17) = v28;
        if ( !RegOpenKeyExW(
                HKEY_CURRENT_USER,
                L"Software\\Microsoft\\Shared Tools\\Proofing Tools\\1.0",
                0,
                0x20006u,
                &hKey) )
        {
          RegSetValueExW(hKey, L"FrenchSpellingReform", 0, 4u, Data, 4u);
          RegCloseKey(hKey);
        }
      }
      break;
    case 13:
      v26 = *(_BYTE *)(v12 + 315) != 0;
      v27 = *(_BYTE *)(v12 + 314);
LABEL_29:
      v24 = v26 ? 0x20000000 : 0;
      v25 = -(v27 != 0);
      goto LABEL_30;
    case 18:
      v24 = (*(_BYTE *)(v12 + 310) == 0 ? 0x20000000 : 0) | (*(_BYTE *)(v12 + 311) == 0 ? 0x40000000 : 0);
      v25 = -(*(_BYTE *)(v12 + 309) == 0);
LABEL_30:
      v23 |= v25 & 0x10000000 | v24;
      break;
  }
  v29 = *(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(*((_QWORD *)a2 + 1) + 32LL);
  if ( v29 )
    v29(*((_QWORD *)a2 + 2), 0, v23);
  v30 = *(void (__fastcall **)(_QWORD, _QWORD, char *))(*((_QWORD *)a2 + 1) + 40LL);
  if ( v30 )
    v30(*((_QWORD *)a2 + 2), 0, (char *)a2 + 1824);
  v31 = *((_QWORD *)v2 + 3);
  v32 = *(_QWORD *)(v31 + 8);
  v33 = 0;
  v34 = &CText::GetText(*(CText **)(v31 + 168))[v32];
  v35 = 0;
  v36 = *(HKEY *)(*((_QWORD *)v2 + 3) + 16LL);
  hKey = v36;
  v160 = (unsigned __int16 *)v34;
  v158 = 0;
  while ( 1 )
  {
    v33 += v13;
    if ( v33 > (unsigned __int64)v36 || !v13 && v35 )
      break;
    v37 = *((_QWORD *)v2 + 3);
    if ( (*(_WORD *)(v37 + 176) & 0x3FF) == 0x11 )
    {
      if ( v35 )
      {
        if ( !*((_DWORD *)a2 + 450) )
          return;
        v33 = *((_DWORD *)a2 + 446) + *((_DWORD *)a2 + 447);
        v13 = *(_QWORD *)(v37 + 16) - v33;
LABEL_57:
        v39 = 1;
        v164 = 1;
        goto LABEL_60;
      }
      v13 = *(_QWORD *)(v37 + 16);
      v33 = 0;
    }
    else
    {
      v13 = 0;
      v38 = (wchar_t *)&v34[v33];
      if ( v33 < (unsigned __int64)v36 )
      {
        do
        {
          if ( (unsigned int)CMN_IsCharSpaceW(*v38) || wcschr(L"()[]{}", *v38) && v13 )
            break;
          ++v13;
          ++v38;
        }
        while ( v13 + v33 < (unsigned __int64)v36 );
        v12 = v166;
        v2 = (CSpellerRuntime *)this;
      }
      if ( v13 + v33 < (unsigned __int64)v36 )
      {
        do
        {
          if ( !(unsigned int)CMN_IsCharSpaceW(*v38) )
            break;
          ++v13;
          ++v38;
        }
        while ( v13 + v33 < (unsigned __int64)v36 );
        v2 = (CSpellerRuntime *)this;
      }
      if ( v158 )
        goto LABEL_57;
    }
    v39 = v164;
LABEL_60:
    if ( !v13 )
      return;
    v35 = 1;
    v158 = 1;
    *((_BYTE *)v2 + 32) = CSpeller::VerifyNoAR(a2, v160, (unsigned __int64)v36, v39, v33, v13) == 0;
    if ( *(_BYTE *)(v12 + 299)
      && OverlapsWithURL(*((struct CSentence **)v2 + 3), *((int *)a2 + 446), *((int *)a2 + 447)) )
    {
      goto LABEL_37;
    }
    if ( !*((_BYTE *)v2 + 32) )
      goto LABEL_37;
    if ( !*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)v2 + 3) + 168LL) + 136LL))(*(_QWORD *)(*((_QWORD *)v2 + 3) + 168LL))
                   + 280) )
    {
      v40 = *((_DWORD *)a2 + 450);
      if ( !v40 || v40 == 6 )
        goto LABEL_37;
    }
    v41 = (struct CSentence *)*((_QWORD *)v2 + 3);
    v42 = *((int *)a2 + 446);
    if ( (int)v42 >= *((_DWORD *)v41 + 4) )
      return;
    v43 = *((int *)a2 + 447);
    if ( (int)v42 + (int)v43 > *((_DWORD *)v41 + 4) )
      return;
    v44 = *((_DWORD *)a2 + 450);
    v13 = 0;
    v33 = *((int *)a2 + 446);
    v171 = 0;
    v45 = v43;
    v167 = v42;
    if ( *(_BYTE *)(v12 + 284) )
    {
      v46 = SpellerShimLatticeFixup(v41, v42, v43);
      v47 = v44 - 1;
      if ( !v47 )
        goto LABEL_107;
      v48 = v47 - 1;
      if ( v48 )
      {
        v49 = v48 - 1;
        if ( !v49 )
          goto LABEL_107;
        v50 = v49 - 1;
        if ( !v50 )
          goto LABEL_107;
        v51 = v50 - 1;
        if ( v51 )
        {
          v52 = v51 - 1;
          if ( v52 )
          {
            v2 = (CSpellerRuntime *)this;
            v53 = *(int *)(*((_QWORD *)v46 + 1) + 4LL);
            v54 = v52 - 5;
            if ( !v54 )
            {
              *(_DWORD *)((char *)v46 + v53 + 8) &= 0x7FFFFFFu;
              *(_DWORD *)((char *)v46 + v53 + 8) |= 0x98000000;
              goto LABEL_190;
            }
            v55 = v54 - 5;
            if ( v55 )
            {
              *(_DWORD *)((char *)v46 + v53 + 8) &= 0x7FFFFFFu;
              if ( v55 == 1 )
              {
                *(_DWORD *)((char *)v46 + v53 + 8) |= 0x90000000;
LABEL_190:
                v36 = hKey;
                v35 = 1;
                goto LABEL_37;
              }
            }
            else
            {
              *(_DWORD *)((char *)v46 + v53 + 8) &= 0x7FFFFFFu;
            }
            *(_DWORD *)((char *)v46 + v53 + 8) |= 0x10000000u;
            goto LABEL_190;
          }
LABEL_107:
          v81 = *(int *)(*((_QWORD *)v46 + 1) + 4LL);
          *(_DWORD *)((char *)v46 + v81 + 8) &= 0x7FFFFFFu;
          *(_DWORD *)((char *)v46 + v81 + 8) |= 0x10000000u;
        }
        else
        {
          v56 = *(int *)(*((_QWORD *)v46 + 1) + 4LL);
          *(_DWORD *)((char *)v46 + v56 + 8) &= 0x7FFFFFFu;
          *(_DWORD *)((char *)v46 + v56 + 8) |= 0x88000000;
        }
        v2 = (CSpellerRuntime *)this;
        goto LABEL_190;
      }
      v57 = *(int *)(*((_QWORD *)v46 + 1) + 4LL);
      *(_DWORD *)((char *)v46 + v57 + 8) &= 0x7FFFFFFu;
      *(_DWORD *)((char *)v46 + v57 + 8) |= 0x10000000u;
      v58 = (_DWORD *)((char *)v46 + *(int *)(*((_QWORD *)v46 + 1) + 4LL) + 36);
      *v58 |= 0x4000u;
      *((_BYTE *)v46 + *(int *)(*((_QWORD *)v46 + 1) + 4LL) + 9) = 18;
      if ( *((int *)a2 + 451) > 0 || (v2 = (CSpellerRuntime *)this, v36 = hKey, v35 = 1, v163 == 26) )
      {
        v59 = v162;
        v60 = CMorphNode::NewProperties(
                (struct CWordNode *)((char *)v46 + *(int *)(*((_QWORD *)v46 + 1) + 4LL) + 8),
                v162);
        NextPropertyFor = CNodeProperties::FindNextPropertyFor(v61, 245, *(_QWORD *)v60);
        if ( NextPropertyFor )
        {
          v65 = *(_QWORD **)(NextPropertyFor + 16);
        }
        else
        {
          v63 = CNodeProperties::NewProperty(v60, v59);
          v64 = CNodeProperty::NewNameArray(v63, v162);
          *((_QWORD *)v63 + 2) = v64;
          v65 = (_QWORD *)v64;
          *((_DWORD *)v63 + 2) = 33554677;
          v59 = v162;
        }
        v2 = (CSpellerRuntime *)this;
        v66 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this[3] + 21) + 272LL))(*((_QWORD *)this[3] + 21));
        (*(void (__fastcall **)(__int64, __int128 *, _QWORD, _QWORD))(*(_QWORD *)v66 + 24LL))(
          v66,
          &v174,
          *((_QWORD *)a2 + 221),
          0);
        v67 = v65[2];
        v68 = v65[1];
        if ( v68 >= v67 )
        {
          v69 = v68 + 1;
          v70 = v65[1];
          if ( v68 < 8 )
            v70 = 8;
          v71 = v67 + v70;
          if ( v69 < v71 )
            v69 = v71;
          if ( v69 > v67 )
          {
            CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::ReallocWorker(v65);
            v68 = v65[1];
          }
        }
        v72 = 2 * v68;
        *(_OWORD *)(*v65 + 8 * v72) = v174;
        ++v65[1];
        v73 = CNodeProperties::FindNextPropertyFor(v72, 255, *(_QWORD *)v60);
        if ( v73 )
        {
          v75 = *(_QWORD **)(v73 + 16);
        }
        else
        {
          v74 = CNodeProperties::NewProperty(v60, v59);
          v75 = (_QWORD *)CNodeProperty::NewIntArray(v74, v162);
          *((_QWORD *)v74 + 2) = v75;
          *((_DWORD *)v74 + 2) = 50331903;
        }
        v76 = v75[2];
        v77 = v75[1];
        if ( v77 >= v76 )
        {
          v78 = v77 + 1;
          v79 = v75[1];
          if ( v77 < 8 )
            v79 = 8;
          v80 = v76 + v79;
          if ( v78 < v80 )
            v78 = v80;
          if ( v78 > v76 )
          {
            CArray<int,CArrayAllocator_GC<CZoneHeap>>::ReallocWorker(v75);
            v77 = v75[1];
          }
        }
        *(_DWORD *)(*v75 + 4 * v77) = 0;
        ++v75[1];
LABEL_189:
        v33 = v167;
        goto LABEL_190;
      }
LABEL_37:
      v34 = v160;
    }
    else
    {
      StringCchCopyNW(v175, 0x41u, &v160[v42], v43);
      v82 = SpellerShimLatticeFixup(this[3], v33, *((int *)a2 + 447));
      if ( *((_DWORD *)a2 + 450) != 11 )
      {
        if ( CSpeller::Verify(a2, v175, v43, v83, phkResult, v43) || !*((_DWORD *)a2 + 447) )
        {
          *((_BYTE *)this + 33) = 0;
          CSpeller::VerifyNoAR(a2, v175, v43, 0, 0, v43);
        }
        else
        {
          v44 = *((_DWORD *)a2 + 450);
        }
      }
      if ( !*(_BYTE *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this[3] + 21) + 136LL))(*((_QWORD *)this[3] + 21))
                     + 280)
        && *((int *)a2 + 451) > 0 )
      {
        v85 = *((_DWORD *)a2 + 450);
        if ( v85 == 16 || v85 == 2 )
        {
          v86 = *(int *)(*((_QWORD *)v82 + 1) + 4LL);
          *(_DWORD *)((char *)v82 + v86 + 8) &= 0x7FFFFFFu;
          if ( v85 == 16 )
          {
            *(_DWORD *)((char *)v82 + v86 + 8) |= 0x18000000u;
          }
          else
          {
            *(_DWORD *)((char *)v82 + v86 + 8) |= 0x10000000u;
            *((_BYTE *)v82 + *(int *)(*((_QWORD *)v82 + 1) + 4LL) + 9) = 18;
            *(_DWORD *)((char *)v82 + *(int *)(*((_QWORD *)v82 + 1) + 4LL) + 36) |= 0x4000u;
          }
          v87 = v162;
          v88 = CMorphNode::NewProperties(
                  (struct CWordNode *)((char *)v82 + *(int *)(*((_QWORD *)v82 + 1) + 4LL) + 8),
                  v162);
          v90 = CNodeProperties::FindNextPropertyFor(v89, 245, *(_QWORD *)v88);
          if ( v90 )
          {
            v93 = *(_QWORD **)(v90 + 16);
          }
          else
          {
            v91 = CNodeProperties::NewProperty(v88, v87);
            v92 = CNodeProperty::NewNameArray(v91, v162);
            *((_QWORD *)v91 + 2) = v92;
            v93 = (_QWORD *)v92;
            *((_DWORD *)v91 + 2) = 33554677;
            v87 = v162;
          }
          v94 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this[3] + 21) + 272LL))(*((_QWORD *)this[3] + 21));
          (*(void (__fastcall **)(__int64, __int128 *, _QWORD, _QWORD))(*(_QWORD *)v94 + 24LL))(
            v94,
            &v172,
            *((_QWORD *)a2 + 221),
            0);
          v95 = v93[2];
          v96 = v93[1];
          if ( v96 >= v95 )
          {
            v97 = v96 + 1;
            v98 = v93[1];
            if ( v96 < 8 )
              v98 = 8;
            v99 = v95 + v98;
            if ( v97 < v99 )
              v97 = v99;
            if ( v97 > v95 )
            {
              CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::ReallocWorker(v93);
              v96 = v93[1];
            }
          }
          v100 = 2 * v96;
          *(_OWORD *)(*v93 + 8 * v100) = v172;
          ++v93[1];
          v101 = CNodeProperties::FindNextPropertyFor(v100, 255, *(_QWORD *)v88);
          if ( v101 )
          {
            v103 = *(_QWORD **)(v101 + 16);
          }
          else
          {
            v102 = CNodeProperties::NewProperty(v88, v87);
            v103 = (_QWORD *)CNodeProperty::NewIntArray(v102, v162);
            *((_QWORD *)v102 + 2) = v103;
            *((_DWORD *)v102 + 2) = 50331903;
          }
          v104 = v103[2];
          v105 = v103[1];
          if ( v105 >= v104 )
          {
            v84 = 8;
            v106 = v105 + 1;
            v107 = v103[1];
            if ( v105 < 8 )
              v107 = 8;
            v108 = v104 + v107;
            if ( v106 < v108 )
              v106 = v108;
            if ( v106 > v104 )
            {
              CArray<int,CArrayAllocator_GC<CZoneHeap>>::ReallocWorker(v103);
              v105 = v103[1];
            }
          }
          v45 = v43;
          v13 = v171;
          *(_DWORD *)(*v103 + 4 * v105) = 0;
          ++v103[1];
          v12 = v166;
        }
      }
      if ( *(_BYTE *)(v12 + 285) )
      {
        v147 = *(int *)(*((_QWORD *)v82 + 1) + 4LL);
        v148 = *(_DWORD *)((char *)v82 + v147 + 8);
        if ( (v148 >> 27) - 2 <= 1 )
          return;
        v149 = v44 - 1;
        if ( v149 )
        {
          v150 = v149 - 1;
          if ( !v150 )
          {
            *(_DWORD *)((char *)v82 + v147 + 8) = v148 & 0x7FFFFFF | 0x10000000;
            *((_BYTE *)v82 + *(int *)(*((_QWORD *)v82 + 1) + 4LL) + 9) = 18;
            *(_DWORD *)((char *)v82 + *(int *)(*((_QWORD *)v82 + 1) + 4LL) + 36) |= 0x4000u;
            return;
          }
          v151 = v150 - 3;
          if ( !v151 )
          {
            v156 = v148 & 0x7FFFFFF | 0x88000000;
            goto LABEL_206;
          }
          v152 = v151 - 3;
          if ( !v152 )
            return;
          v153 = v152 - 1;
          if ( v153 )
          {
            v154 = v153 - 2;
            if ( !v154 )
            {
              v156 = v148 & 0x7FFFFFF | 0x98000000;
              goto LABEL_206;
            }
            v155 = v154 - 5;
            if ( !v155 )
            {
              v156 = v148 & 0x7FFFFFF | 0x18000000;
              goto LABEL_206;
            }
            if ( v155 == 1 )
            {
              v156 = v148 & 0x7FFFFFF | 0x90000000;
LABEL_206:
              *(_DWORD *)((char *)v82 + v147 + 8) = v156;
              return;
            }
          }
        }
        v156 = v148 & 0x7FFFFFF | 0x10000000;
        goto LABEL_206;
      }
      v109 = CSpeller::Suggest(a2, v175, v45, v84, v43);
      v2 = (CSpellerRuntime *)this;
      v35 = 1;
      v34 = v160;
      *((_BYTE *)this + 32) = v109 == 0;
      if ( !v109 )
      {
        v110 = *(int *)(*((_QWORD *)v82 + 1) + 4LL);
        v111 = *(_DWORD *)((char *)v82 + v110 + 8);
        if ( (v111 >> 27) - 2 > 1 )
        {
          v112 = v44 - 1;
          if ( !v112 )
            goto LABEL_158;
          v113 = v112 - 1;
          if ( v113 )
          {
            v114 = v113 - 3;
            if ( !v114 )
            {
              v119 = v111 & 0x7FFFFFF | 0x88000000;
              goto LABEL_159;
            }
            v115 = v114 - 3;
            if ( v115 )
            {
              v116 = v115 - 1;
              if ( !v116 )
                goto LABEL_158;
              v117 = v116 - 2;
              if ( v117 )
              {
                v118 = v117 - 5;
                if ( v118 )
                {
                  if ( v118 == 1 )
                  {
                    v119 = v111 & 0x7FFFFFF | 0x90000000;
                    goto LABEL_159;
                  }
LABEL_158:
                  v119 = v111 & 0x7FFFFFF | 0x10000000;
                }
                else
                {
                  v119 = v111 & 0x7FFFFFF | 0x18000000;
                }
              }
              else
              {
                v119 = v111 & 0x7FFFFFF | 0x98000000;
              }
LABEL_159:
              *(_DWORD *)((char *)v82 + v110 + 8) = v119;
            }
          }
          else
          {
            *(_DWORD *)((char *)v82 + v110 + 8) = v111 & 0x7FFFFFF | 0x10000000;
            *((_BYTE *)v82 + *(int *)(*((_QWORD *)v82 + 1) + 4LL) + 9) = 18;
            *(_DWORD *)((char *)v82 + *(int *)(*((_QWORD *)v82 + 1) + 4LL) + 36) |= 0x4000u;
          }
        }
        v120 = 0;
        *(_DWORD *)Data = *((_DWORD *)a2 + 451);
        if ( *(int *)Data > 0 )
        {
          do
          {
            v121 = v175;
            v170 = *((_QWORD *)a2 + 222);
            do
            {
              v122 = *(unsigned __int16 *)((char *)v121 + *(_QWORD *)(v170 + 24 * v120) - (_QWORD)v175);
              v123 = *v121 - v122;
              if ( v123 )
                break;
              ++v121;
            }
            while ( v122 );
            if ( v123 )
            {
              v124 = v162;
              v125 = CMorphNode::NewProperties(
                       (struct CWordNode *)((char *)v82 + *(int *)(*((_QWORD *)v82 + 1) + 4LL) + 8),
                       v162);
              v127 = CNodeProperties::FindNextPropertyFor(v126, 245, *(_QWORD *)v125);
              if ( v127 )
              {
                v130 = *(_QWORD **)(v127 + 16);
              }
              else
              {
                v128 = CNodeProperties::NewProperty(v125, v124);
                v129 = CNodeProperty::NewNameArray(v128, v162);
                *((_QWORD *)v128 + 2) = v129;
                v130 = (_QWORD *)v129;
                *((_DWORD *)v128 + 2) = 33554677;
                v124 = v162;
              }
              v131 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this[3] + 21) + 272LL))(*((_QWORD *)this[3] + 21));
              (*(void (__fastcall **)(__int64, __int128 *, _QWORD, _QWORD))(*(_QWORD *)v131 + 24LL))(
                v131,
                &v168,
                *(_QWORD *)(v170 + 24 * v120),
                0);
              v132 = v130[2];
              v133 = v130[1];
              if ( v133 >= v132 )
              {
                v134 = v133 + 1;
                v135 = v130[1];
                if ( v133 < 8 )
                  v135 = 8;
                v136 = v132 + v135;
                if ( v134 < v136 )
                  v134 = v136;
                if ( v134 > v132 )
                {
                  CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::ReallocWorker(v130);
                  v133 = v130[1];
                }
              }
              v137 = 2 * v133;
              *(_OWORD *)(*v130 + 8 * v137) = v168;
              ++v130[1];
              v138 = CNodeProperties::FindNextPropertyFor(v137, 255, *(_QWORD *)v125);
              if ( v138 )
              {
                v140 = *(_QWORD **)(v138 + 16);
              }
              else
              {
                v139 = CNodeProperties::NewProperty(v125, v124);
                v140 = (_QWORD *)CNodeProperty::NewIntArray(v139, v162);
                *((_QWORD *)v139 + 2) = v140;
                *((_DWORD *)v139 + 2) = 50331903;
              }
              v141 = v140[2];
              v142 = v140[1];
              v143 = 255 - *(_DWORD *)(v170 + 24 * v120 + 16);
              if ( v142 >= v141 )
              {
                v144 = v142 + 1;
                v145 = v140[1];
                if ( v142 < 8 )
                  v145 = 8;
                v146 = v141 + v145;
                if ( v144 < v146 )
                  v144 = v146;
                if ( v144 > v141 )
                {
                  CArray<int,CArrayAllocator_GC<CZoneHeap>>::ReallocWorker(v140);
                  v142 = v140[1];
                }
              }
              *(_DWORD *)(*v140 + 4 * v142) = v143;
              ++v140[1];
            }
            v120 = (unsigned int)(v120 + 1);
          }
          while ( (int)v120 < *(int *)Data );
          v12 = v166;
          v2 = (CSpellerRuntime *)this;
        }
        Speller::CSpellerUtility::TrimDuplicateSuggestionsFor(v82, *(unsigned __int16 *)(*((_QWORD *)v2 + 3) + 176LL));
        v13 = v171;
        goto LABEL_189;
      }
      v33 = v167;
      v36 = hKey;
    }
  }
}

```

## disassembly

```asm
0x18008b670  mov     [rsp-8+arg_10], rbx
0x18008b675  push    rbp
0x18008b676  push    rsi
0x18008b677  push    rdi
0x18008b678  push    r12
0x18008b67a  push    r13
0x18008b67c  push    r14
0x18008b67e  push    r15
0x18008b680  lea     rbp, [rsp-70h]
0x18008b685  sub     rsp, 170h
0x18008b68c  mov     rax, cs:__security_cookie
0x18008b693  xor     rax, rsp
0x18008b696  mov     [rbp+0A0h+var_40], rax
0x18008b69a  mov     r13, rcx
0x18008b69d  mov     [rsp+1A0h+var_168], rcx
0x18008b6a2  mov     rcx, [rcx+18h]
0x18008b6a6  mov     r14, rdx
0x18008b6a9  mov     rax, [rcx]
0x18008b6ac  mov     rax, [rax+50h]
0x18008b6b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b6b5  mov     rdx, rax
0x18008b6b8  mov     rcx, [rax]
0x18008b6bb  mov     rax, [rcx+18h]
0x18008b6bf  mov     rcx, rdx
0x18008b6c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b6c7  mov     rdx, rax
0x18008b6ca  mov     rcx, [rax]
0x18008b6cd  mov     rax, [rcx+58h]
0x18008b6d1  mov     rcx, rdx
0x18008b6d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b6d9  mov     rcx, [r13+18h]; this
0x18008b6dd  call    ?GetLspRuntime@CSentence@@QEAAPEAUILspRuntime@@XZ; CSentence::GetLspRuntime(void)
0x18008b6e2  mov     rdx, rax
0x18008b6e5  mov     rcx, [rax]
0x18008b6e8  mov     rax, [rcx+18h]
0x18008b6ec  mov     rcx, rdx
0x18008b6ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b6f4  mov     rcx, [r13+18h]
0x18008b6f8  mov     [rsp+1A0h+var_150], rax
0x18008b6fd  mov     rcx, [rcx+0A8h]
0x18008b704  mov     rdx, [rcx]
0x18008b707  mov     rax, [rdx+88h]
0x18008b70e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b713  mov     rcx, [r13+18h]
0x18008b717  mov     r15, rax
0x18008b71a  xor     r12d, r12d
0x18008b71d  mov     [rsp+1A0h+var_138], rax
0x18008b722  mov     eax, r12d
0x18008b725  cmp     [r15+11Eh], r12b
0x18008b72c  lea     edx, [r12+1]
0x18008b731  setnz   al
0x18008b734  mov     [rsp+1A0h+var_144], eax
0x18008b738  movzx   eax, word ptr [rcx+0B0h]
0x18008b73f  mov     ecx, 3FFh
0x18008b744  and     ax, cx
0x18008b747  mov     ecx, [r15+1A8h]
0x18008b74e  mov     [rsp+1A0h+var_148], ax
0x18008b753  cmp     [r13+24h], ecx
0x18008b757  jz      loc_18008B8CE
0x18008b75d  mov     [r13+24h], ecx
0x18008b761  mov     r8, [r14+30h]; void *
0x18008b765  test    r8, r8
0x18008b768  jz      short loc_18008B77C
0x18008b76a  mov     rdx, [r14+10h]; void *
0x18008b76e  mov     rcx, [r14+8]; this
0x18008b772  call    ?CloseLex@CProofAPI@@QEAAKPEAX0H@Z; CProofAPI::CloseLex(void *,void *,int)
0x18008b777  lea     edx, [r12+1]
0x18008b77c  mov     edi, r12d
0x18008b77f  mov     [r14+30h], r12
0x18008b783  cmp     [r14+6B0h], r12d
0x18008b78a  jle     short loc_18008B7B7
0x18008b78c  mov     r8, [r14+388h]
0x18008b793  mov     rdx, [r14+10h]; void *
0x18008b797  mov     rcx, [r14+8]; this
0x18008b79b  movsxd  rax, edi
0x18008b79e  mov     r8, [r8+rax*8]; void *
0x18008b7a2  call    ?CloseLex@CProofAPI@@QEAAKPEAX0H@Z; CProofAPI::CloseLex(void *,void *,int)
0x18008b7a7  inc     edi
0x18008b7a9  cmp     edi, [r14+6B0h]
0x18008b7b0  jl      short loc_18008B78C
0x18008b7b2  mov     edx, 1
0x18008b7b7  mov     [r14+6B0h], r12d
0x18008b7be  movzx   esi, word ptr [r15+1ACh]
0x18008b7c6  sub     esi, edx
0x18008b7c8  js      loc_18008B8CE
0x18008b7ce  mov     eax, 0FFFFh
0x18008b7d3  mov     dword ptr [rbp+0A0h+var_128+8], edx
0x18008b7d6  mov     rcx, r15; this
0x18008b7d9  mov     edx, esi; __int64
0x18008b7db  mov     dword ptr [rbp+0A0h+var_128+0Ch], 4
0x18008b7e2  mov     [rbp+0A0h+var_118], ax
0x18008b7e6  mov     qword ptr [rbp+0A0h+var_100], r12
0x18008b7ea  mov     dword ptr [rbp+0A0h+var_F0], r12d
0x18008b7ee  call    ?LexAt@CContext@@QEBAPEAVINLTopLexicon@@_J@Z; CContext::LexAt(__int64)
0x18008b7f3  mov     rcx, [r13+18h]
0x18008b7f7  mov     rdi, rax
0x18008b7fa  movzx   ebx, word ptr [rcx+0B0h]
0x18008b801  mov     rcx, [rax]
0x18008b804  mov     rax, [rcx+28h]
0x18008b808  mov     rcx, rdi
0x18008b80b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b810  cmp     bx, ax
0x18008b813  jz      short loc_18008B832
0x18008b815  mov     rcx, [rdi]
0x18008b818  mov     rax, [rcx+28h]
0x18008b81c  mov     rcx, rdi
0x18008b81f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b824  mov     ecx, 3FFh
0x18008b829  test    cx, ax
0x18008b82c  jnz     loc_18008B8BC
0x18008b832  mov     rax, [rdi]
0x18008b835  mov     rcx, rdi
0x18008b838  mov     rax, [rax+48h]
0x18008b83c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008b841  cmp     eax, 3
0x18008b844  jnz     short loc_18008B8BC
0x18008b846  mov     rax, [rdi+68h]
0x18008b84a  mov     ecx, [rax+18h]
0x18008b84d  mov     dword ptr [rbp+0A0h+var_128+0Ch], ecx
0x18008b850  mov     rdx, [rdi+68h]
0x18008b854  add     rdx, 24h ; '$'
0x18008b858  or      rax, 0FFFFFFFFFFFFFFFFh
0x18008b85c  inc     rax
0x18008b85f  cmp     [rdx+rax*2], r12w
0x18008b864  jnz     short loc_18008B85C
0x18008b866  neg     rax
0x18008b869  mov     dword ptr [rbp+0A0h+var_128+8], r12d
0x18008b86d  mov     eax, 0FFFFh
0x18008b872  xorps   xmm0, xmm0
0x18008b875  sbb     rcx, rcx
0x18008b878  mov     [rbp+0A0h+var_118], ax
0x18008b87c  and     rcx, rdx; this
0x18008b87f  mov     qword ptr [rsp+1A0h+var_128], rcx
0x18008b884  movups  [rbp+0A0h+var_100], xmm0
0x18008b888  movups  [rbp+0A0h+var_F0], xmm0
0x18008b88c  mov     rax, [rdi+68h]
0x18008b890  cmp     [rax+67Ch], r12b
0x18008b897  jz      short loc_18008B8A6
0x18008b899  mov     r8, rdi; struct UserDictionary *
0x18008b89c  mov     rdx, r14; struct CSpeller *
0x18008b89f  call    ?SyncInternalLexOn@CSpellerRuntime@@IEAAXPEAVCSpeller@@PEAVUserDictionary@@@Z; CSpellerRuntime::SyncInternalLexOn(CSpeller *,UserDictionary *)
0x18008b8a4  jmp     short loc_18008B8BC
0x18008b8a6  test    rcx, rcx
0x18008b8a9  jz      short loc_18008B8BC
0x18008b8ab  lea     r8, [rbp+0A0h+var_100]; struct PROOFLEXOUT *
0x18008b8af  mov     rcx, r14; this
0x18008b8b2  lea     rdx, [rsp+1A0h+var_128]; struct PROOFLEXIN *
0x18008b8b7  call    ?OpenLex@CProof@@QEAAKAEAUPROOFLEXIN@@AEAUPROOFLEXOUT@@@Z; CProof::OpenLex(PROOFLEXIN &,PROOFLEXOUT &)
0x18008b8bc  mov     edx, 1
0x18008b8c1  mov     eax, 0FFFFh
0x18008b8c6  sub     esi, edx
0x18008b8c8  jns     loc_18008B7D3
0x18008b8ce  mov     al, [r15+124h]
0x18008b8d5  mov     r8d, 10000000h
0x18008b8db  neg     al
0x18008b8dd  mov     al, [r15+128h]
0x18008b8e4  sbb     ebx, ebx
0x18008b8e6  add     ebx, 401h
0x18008b8ec  neg     al
0x18008b8ee  mov     al, [r15+126h]
0x18008b8f5  sbb     ecx, ecx
0x18008b8f7  and     ecx, 40h
0x18008b8fa  or      ebx, ecx
0x18008b8fc  neg     al
0x18008b8fe  mov     al, [r15+129h]
0x18008b905  sbb     ecx, ecx
0x18008b907  and     ecx, 4
0x18008b90a  or      ebx, ecx
0x18008b90c  neg     al
0x18008b90e  mov     al, [r15+125h]
0x18008b915  sbb     ecx, ecx
0x18008b917  and     ecx, 20000h
0x18008b91d  or      ebx, ecx
0x18008b91f  neg     al
0x18008b921  mov     rax, [r13+18h]
0x18008b925  sbb     ecx, ecx
0x18008b927  and     ecx, 2
0x18008b92a  or      ebx, ecx
0x18008b92c  movzx   ecx, word ptr [rax+0B0h]
0x18008b933  and     ecx, 3FFh
0x18008b939  sub     ecx, 1
0x18008b93c  jz      loc_18008BA55
0x18008b942  sub     ecx, 6
0x18008b945  jz      loc_18008BA43
0x18008b94b  sub     ecx, 5
0x18008b94e  jz      short loc_18008B9AD
0x18008b950  sub     ecx, 1
0x18008b953  jz      short loc_18008B998
0x18008b955  cmp     ecx, 5
0x18008b958  jnz     loc_18008BA78
0x18008b95e  mov     al, [r15+137h]
0x18008b965  neg     al
0x18008b967  mov     al, [r15+136h]
0x18008b96e  sbb     edx, edx
0x18008b970  not     edx
0x18008b972  and     edx, 40000000h
0x18008b978  neg     al
0x18008b97a  mov     al, [r15+135h]
0x18008b981  sbb     ecx, ecx
0x18008b983  not     ecx
0x18008b985  and     ecx, 20000000h
0x18008b98b  or      edx, ecx
0x18008b98d  neg     al
0x18008b98f  sbb     ecx, ecx
0x18008b991  not     ecx
0x18008b993  jmp     loc_18008BA71
0x18008b998  mov     al, [r15+13Bh]
0x18008b99f  neg     al
0x18008b9a1  mov     al, [r15+13Ah]
0x18008b9a8  jmp     loc_18008BA65
0x18008b9ad  mov     edx, [r15+130h]
0x18008b9b4  mov     al, [r15+12Ch]
0x18008b9bb  neg     al
0x18008b9bd  mov     [rsp+1A0h+hKey], r12
0x18008b9c2  mov     dword ptr [rsp+1A0h+Data], edx
0x18008b9c6  sbb     ecx, ecx
0x18008b9c8  and     ecx, 20000000h
0x18008b9ce  or      ebx, ecx
0x18008b9d0  cmp     edx, [r13+44h]
0x18008b9d4  jz      loc_18008BA78
0x18008b9da  mov     [r13+44h], edx
0x18008b9de  lea     rax, [rsp+1A0h+hKey]
0x18008b9e3  lea     rdx, SubKey; "Software\\Microsoft\\Shared Tools\\Proo"...
0x18008b9ea  mov     [rsp+1A0h+phkResult], rax; phkResult
0x18008b9ef  mov     r9d, 20006h; samDesired
0x18008b9f5  xor     r8d, r8d; ulOptions
0x18008b9f8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18008b9ff  call    cs:__imp_RegOpenKeyExW
0x18008ba05  test    eax, eax
0x18008ba07  jnz     short loc_18008BA78
0x18008ba09  mov     rcx, [rsp+1A0h+hKey]; hKey
0x18008ba0e  lea     rax, [rsp+1A0h+Data]
0x18008ba13  mov     [rsp+1A0h+cbData], 4; cbData
0x18008ba1b  lea     rdx, ValueName; "FrenchSpellingReform"
0x18008ba22  mov     r9d, 4; dwType
0x18008ba28  mov     [rsp+1A0h+phkResult], rax; lpData
0x18008ba2d  xor     r8d, r8d; Reserved
0x18008ba30  call    cs:__imp_RegSetValueExW
0x18008ba36  mov     rcx, [rsp+1A0h+hKey]; hKey
0x18008ba3b  call    cs:__imp_RegCloseKey
0x18008ba41  jmp     short loc_18008BA78
0x18008ba43  mov     al, [r15+134h]
0x18008ba4a  neg     al
0x18008ba4c  sbb     ecx, ecx
0x18008ba4e  and     ecx, r8d
0x18008ba51  or      ebx, ecx
0x18008ba53  jmp     short loc_18008BA78
0x18008ba55  mov     al, [r15+139h]
0x18008ba5c  neg     al
0x18008ba5e  mov     al, [r15+138h]
0x18008ba65  sbb     edx, edx
0x18008ba67  and     edx, 20000000h
0x18008ba6d  neg     al
0x18008ba6f  sbb     ecx, ecx
0x18008ba71  and     ecx, r8d
0x18008ba74  or      edx, ecx
0x18008ba76  or      ebx, edx
0x18008ba78  mov     rax, [r14+8]
0x18008ba7c  mov     rax, [rax+20h]
0x18008ba80  test    rax, rax
0x18008ba83  jz      short loc_18008BA93
0x18008ba85  mov     rcx, [r14+10h]
0x18008ba89  mov     r8d, ebx
0x18008ba8c  xor     edx, edx
0x18008ba8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ba93  mov     rax, [r14+8]
0x18008ba97  mov     rax, [rax+28h]
0x18008ba9b  test    rax, rax
0x18008ba9e  jz      short loc_18008BAB2
0x18008baa0  mov     rcx, [r14+10h]
0x18008baa4  lea     r8, [r14+720h]
0x18008baab  xor     edx, edx
0x18008baad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008bab2  mov     rcx, [r13+18h]
0x18008bab6  mov     rbx, [rcx+8]
0x18008baba  mov     rcx, [rcx+0A8h]; this
0x18008bac1  add     rbx, rbx
0x18008bac4  call    ?GetText@CText@@QEAAPEBGXZ; CText::GetText(void)
0x18008bac9  mov     rcx, [r13+18h]
0x18008bacd  mov     rsi, r12
0x18008bad0  lea     rdx, [rbx+rax]
0x18008bad4  xor     bl, bl
0x18008bad6  mov     rdi, [rcx+10h]
0x18008bada  mov     [rsp+1A0h+hKey], rdi
0x18008badf  mov     [rsp+1A0h+var_160], rdx
0x18008bae4  mov     [rsp+1A0h+var_170], bl
0x18008bae8  jmp     short loc_18008BAFB
0x18008baea  mov     rsi, [rsp+1A0h+var_130]
0x18008baef  mov     rdi, [rsp+1A0h+hKey]
0x18008baf4  jmp     short loc_18008BAFB
0x18008baf6  mov     rdx, [rsp+1A0h+var_160]
0x18008bafb  add     rsi, r12
0x18008bafe  cmp     rsi, rdi
0x18008bb01  ja      loc_18008C60B
0x18008bb07  test    r12, r12
0x18008bb0a  jnz     short loc_18008BB14
0x18008bb0c  test    bl, bl
0x18008bb0e  jnz     loc_18008C60B
0x18008bb14  mov     rcx, [r13+18h]
0x18008bb18  mov     r8d, 3FFh
  ... truncated ...
```
