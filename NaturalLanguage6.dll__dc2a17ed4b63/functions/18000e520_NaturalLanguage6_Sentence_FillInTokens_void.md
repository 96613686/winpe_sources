# NaturalLanguage6::Sentence::FillInTokens(void)

- ea: `0x18000e520`
- end: `0x18000f36f`
- name: `?FillInTokens@Sentence@NaturalLanguage6@@IEAAXXZ`
- size: `3663`
- prototype: `void __fastcall(NaturalLanguage6::Sentence *__hidden this)`
- caller_count: `3`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18000e460`
- `0x18002b480`
- `0x18002cf40`

## callees

- `0x180002778`
- `0x180003664`
- `0x1800038a8`
- `0x180005160`
- `0x18000b07c`
- `0x18000e520`
- `0x18000f380`
- `0x1800107c0`
- `0x180010a2c`
- `0x18002a734`
- `0x18002a918`
- `0x18002aa94`
- `0x180035640`
- `0x18003dfcc`
- `0x18003ed6c`
- `0x1800b0010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall NaturalLanguage6::Sentence::FillInTokens(NaturalLanguage6::Sentence *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  char v4; // si
  char v5; // r13
  __int64 v6; // rbx
  __int64 v7; // rdi
  unsigned __int64 v8; // rcx
  __int64 v9; // r14
  __int64 *v10; // rsi
  __int64 *v11; // rdi
  __int64 v12; // r12
  _QWORD *v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  CZoneHeap *v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  const struct CWordNode *v20; // rbp
  int v21; // eax
  __int64 v22; // rdx
  unsigned int v23; // ecx
  __int64 **v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rcx
  int v28; // eax
  int v29; // eax
  char *v30; // rsi
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rax
  char *v35; // rax
  __int64 v36; // rcx
  unsigned int v37; // eax
  __int64 v38; // rdi
  CNodeProperties *v39; // rcx
  __int64 **v40; // rdx
  struct CNodeProperty *v41; // rdi
  unsigned __int8 *v42; // rax
  __int64 *v43; // rax
  __int64 v44; // rcx
  __int64 v45; // r8
  __int64 v46; // rcx
  __int64 v47; // rdx
  __int64 v48; // rax
  __int64 v49; // rax
  const struct CContext *v50; // r8
  __int64 v51; // rdx
  int v52; // edx
  int v53; // edx
  int v54; // edx
  int v55; // edx
  int v56; // edx
  struct CZoneHeap *v57; // rbx
  CNodeProperties *v58; // rax
  struct CNodeProperty *v59; // rdi
  unsigned __int8 *v60; // rax
  __int64 *v61; // rsi
  __int64 v62; // rbx
  char v63; // r14
  unsigned int v64; // edx
  __int64 v65; // rax
  unsigned __int64 v66; // r12
  __int64 v67; // rcx
  signed __int64 v68; // rdx
  unsigned __int8 (__fastcall ***v69)(_QWORD, _QWORD); // rdi
  struct CWordNode *v70; // r13
  __int64 v71; // rdi
  __int64 v72; // rsi
  unsigned int v73; // r14d
  unsigned __int8 (__fastcall ***v74)(_QWORD, _QWORD); // r12
  char *v75; // rdx
  __int64 v76; // r9
  __int64 v77; // rdi
  __int64 v78; // rsi
  __int64 v79; // rax
  __int64 *v80; // rax
  __int64 v81; // rcx
  __int64 v82; // rcx
  __int64 v83; // rcx
  __int64 v84; // rax
  __int64 v85; // rax
  __int64 v86; // r8
  __int64 v87; // rcx
  __int64 v88; // rdx
  __int64 v89; // rax
  __int64 v90; // rax
  int v91; // edx
  int v92; // edx
  int v93; // edx
  int v94; // edx
  int v95; // edx
  __int64 v96; // rbx
  char v97; // r14
  unsigned int v98; // esi
  __int64 v99; // rax
  unsigned __int64 v100; // r12
  __int64 v101; // rcx
  signed __int64 v102; // rdx
  unsigned __int8 (__fastcall ***v103)(_QWORD, _QWORD); // rdi
  struct CWordNode *v104; // r13
  __int64 v105; // rdi
  __int64 v106; // rsi
  unsigned int v107; // r14d
  unsigned __int8 (__fastcall ***v108)(_QWORD, _QWORD); // r12
  char *v109; // rdx
  __int64 v110; // r9
  __int64 v111; // rdi
  __int64 v112; // rsi
  __int64 v113; // rax
  __int64 *v114; // rax
  __int64 v115; // rcx
  __int64 v116; // rcx
  __int64 v117; // rcx
  __int64 v118; // r8
  __int64 v119; // rcx
  __int64 v120; // rdx
  __int64 v121; // rax
  __int64 v122; // rax
  NaturalLanguage6::BoundSegment *v123; // rax
  char v124; // [rsp+30h] [rbp-138h]
  char v125; // [rsp+31h] [rbp-137h]
  char *v126; // [rsp+38h] [rbp-130h] BYREF
  CZoneHeap *v127; // [rsp+40h] [rbp-128h]
  __int64 *v128; // [rsp+48h] [rbp-120h]
  unsigned int v129; // [rsp+50h] [rbp-118h]
  __int64 *v130; // [rsp+58h] [rbp-110h]
  unsigned int v131; // [rsp+60h] [rbp-108h]
  unsigned __int8 (__fastcall ***v132)(_QWORD, __int64); // [rsp+68h] [rbp-100h]
  __int64 v133; // [rsp+70h] [rbp-F8h]
  __int64 v134; // [rsp+78h] [rbp-F0h]
  __int64 v135; // [rsp+80h] [rbp-E8h]
  __int64 v136; // [rsp+88h] [rbp-E0h]
  __int64 v137; // [rsp+90h] [rbp-D8h] BYREF
  __int64 v138; // [rsp+98h] [rbp-D0h]
  __int64 v139; // [rsp+A0h] [rbp-C8h]
  __int64 v140; // [rsp+A8h] [rbp-C0h]
  char *v141; // [rsp+B0h] [rbp-B8h]
  char v142[16]; // [rsp+B8h] [rbp-B0h] BYREF
  char v143[16]; // [rsp+C8h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+D8h] [rbp-90h] BYREF
  const void *retaddr; // [rsp+168h] [rbp+0h]
  char v146; // [rsp+170h] [rbp+8h]
  char v147; // [rsp+170h] [rbp+8h]
  char v148; // [rsp+178h] [rbp+10h]
  unsigned int v149; // [rsp+178h] [rbp+10h]
  char v150; // [rsp+180h] [rbp+18h]
  char v151; // [rsp+188h] [rbp+20h]

  v140 = -2;
  v2 = *(_QWORD *)(*((_QWORD *)this + 3) + 216LL);
  if ( v2 && (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 136LL))(v2) )
  {
    v3 = *((_QWORD *)this + 3);
    v4 = *(_BYTE *)(*(_QWORD *)(v3 + 168) + 8LL);
    v125 = v4;
    v5 = *(_BYTE *)(v3 + 45);
    v150 = v5;
    v6 = 0;
    v133 = 0;
    v137 = 0;
    v7 = *((_QWORD *)this + 3);
    v131 = *(_DWORD *)(v7 + 176);
    v8 = *(_QWORD *)(v7 + 144);
    v135 = v8;
    if ( !v8 )
    {
      v50 = CSentence::Context((CSentence *)v7);
      v51 = *(unsigned int *)(v7 + 176);
      if ( (_DWORD)v51 == -1 )
        v51 = 9;
      v135 = (*(__int64 (__fastcall **)(const struct CContext *, __int64))(*(_QWORD *)v50 + 56LL))(v50, v51);
      *(_QWORD *)(v7 + 144) = v135;
    }
    v9 = *(_QWORD *)(*((_QWORD *)this + 3) + 112LL);
    v136 = v9;
    if ( v9 )
    {
      if ( !v4 )
      {
        v123 = (NaturalLanguage6::BoundSegment *)NaturalLanguage6::BoundSegment::operator new(v8);
        if ( v123 )
        {
          v6 = NaturalLanguage6::BoundSegment::BoundSegment(v123, this, 0);
          v133 = v6;
        }
        else
        {
          v6 = 0;
          v133 = 0;
        }
        _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(&v137);
        v137 = v6;
      }
      v10 = 0;
      v128 = 0;
      v11 = 0;
      v130 = 0;
      v12 = -1;
      v134 = -1;
      v13 = (_QWORD *)*((_QWORD *)this + 3);
      v138 = v13[1];
      v139 = v138 + v13[2];
      v14 = v13[21];
      if ( *(_BYTE *)(v14 + 24) )
      {
        v16 = (CZoneHeap *)(v14 + 528);
      }
      else
      {
        v15 = (*(__int64 (__fastcall **)(_QWORD *))(*v13 + 80LL))(v13);
        v16 = (CZoneHeap *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 32LL))(v15);
      }
      v127 = v16;
      v17 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 80LL))(*((_QWORD *)this + 3));
      v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v17 + 24LL))(v17);
      v132 = (unsigned __int8 (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 88LL))(v18);
      v151 = *(_BYTE *)((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 3) + 216LL) + 136LL))(*(_QWORD *)(*((_QWORD *)this + 3) + 216LL))
                      + 21);
      v124 = *(_BYTE *)((*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 3) + 216LL) + 136LL))(*(_QWORD *)(*((_QWORD *)this + 3) + 216LL))
                      + 19);
      while ( 1 )
      {
        if ( !v9 )
        {
          if ( v6 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
          return;
        }
        v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 32LL))(v9);
        v20 = (const struct CWordNode *)v19;
        if ( v19 )
        {
          if ( v5
            || (v25 = *(int *)(*(_QWORD *)(v19 + 8) + 4LL), v26 = *(_QWORD *)(v25 + v19 + 80), v26 > 0)
            && v138 + v26 + *((_QWORD *)v20 + 2) <= v139
            && ((*(_DWORD *)((_BYTE *)v20 + v25 + 12) & 0x3F0000) != 0x10000 || v151) )
          {
            if ( !v124
              || (v21 = *(_DWORD *)((_BYTE *)v20 + *(int *)(*((_QWORD *)v20 + 1) + 4LL) + 12) & 0x3F0000, v21 != 0x100000)
              && v21 != 1572864
              && v21 != 1769472
              && v21 != 786432
              && v21 != 1245184
              && v21 != 851968
              && v21 != 0x80000
              && v21 != 0x200000
              && v21 != 1703936
              && v21 != 917504
              && v21 != 2031616
              && v21 != 1638400
              && v21 != 655360
              && v21 != 720896
              && v21 != 589824 )
            {
              v22 = *(int *)(*((_QWORD *)v20 + 1) + 4LL);
              v23 = *(_DWORD *)((char *)v20 + v22 + 8);
              if ( v23 >> 27 == 10 )
              {
                *(_DWORD *)((char *)v20 + v22 + 8) = v23 & 0x7FFFFFF;
                goto LABEL_47;
              }
              if ( v23 >> 27 != 7 || (v23 & 0xF0) == 0x40 )
                goto LABEL_47;
              v148 = 0;
              if ( !v10 )
              {
                v24 = **(__int64 ****)((char *)v20 + v22 + 88);
                if ( v24 )
                {
                  while ( v24 )
                  {
                    if ( ((_DWORD)v24[1] & 0xFFFFFF) == 0x111B )
                    {
                      v10 = v24[2];
                      v128 = v10;
                      v36 = *(int *)(v10[1] + 4);
                      v37 = *(_DWORD *)((char *)v10 + v36 + 8);
                      if ( v37 < 0x8000000 )
                        *(_DWORD *)((char *)v10 + v36 + 8) = v37 & 0x7FFFFFF | 0x50000000;
                      break;
                    }
                    v24 = (__int64 **)*v24;
                  }
                }
                v148 = 1;
                if ( !v10 )
                {
                  CNLException::CNLException((CNLException *)pExceptionObject, 2147500037LL, retaddr);
                  throw (CNLException *)pExceptionObject;
                }
              }
              if ( !v11 )
              {
                v38 = *(int *)(v10[1] + 4);
                v39 = *(CNodeProperties **)((char *)v10 + v38 + 88);
                if ( !v39 )
                {
                  v39 = (CNodeProperties *)CZoneHeap::Alloc(v127, 8u, 8u);
                  if ( v39 )
                    *(_QWORD *)v39 = 0;
                  else
                    v39 = 0;
                  *(__int64 *)((char *)v10 + v38 + 88) = (__int64)v39;
                }
                v40 = *(__int64 ***)v39;
                if ( *(_QWORD *)v39 )
                {
                  while ( v40 )
                  {
                    if ( ((_DWORD)v40[1] & 0xFFFFFF) == 0xF7 )
                    {
                      v11 = v40[2];
                      v130 = v11;
                      goto LABEL_74;
                    }
                    v40 = (__int64 **)*v40;
                  }
                }
                v41 = CNodeProperties::NewProperty(v39, v127);
                *((_BYTE *)v41 + 11) = 1;
                v42 = CZoneHeap::Alloc(v127, 0x28u, 8u);
                *((_QWORD *)v41 + 2) = v42;
                *(_QWORD *)v42 = 0;
                *((_QWORD *)v42 + 1) = 0;
                *((_QWORD *)v42 + 2) = 0;
                v42[24] = 1;
                *((_QWORD *)v42 + 4) = v127;
                v130 = (__int64 *)*((_QWORD *)v41 + 2);
                v43 = v130;
                *((_DWORD *)v41 + 2) = 16777463;
                v11 = v43;
              }
LABEL_74:
              v44 = *(int *)(*((_QWORD *)v20 + 1) + 4LL);
              if ( (*(_DWORD *)((_BYTE *)v20 + v44 + 72) & 0xFFFFFFu) - 16777214 > 1
                && *(_DWORD *)((char *)v20 + v44 + 32)
                && (v91 = *(_DWORD *)((char *)v20 + v44 + 8) >> 27, v91 != 2)
                && (v92 = v91 - 3) != 0
                && (v93 = v92 - 14) != 0
                && (v94 = v93 - 1) != 0
                && (v95 = v94 - 1) != 0
                && v95 != 3 )
              {
                v96 = *((_QWORD *)v20 + 2);
                v97 = 1;
                v147 = 1;
                v98 = 0;
                v129 = 0;
                do
                {
                  if ( !v97 )
                    break;
                  v99 = *(int *)(*((_QWORD *)v20 + 1) + 4LL);
                  v100 = ((unsigned __int64)*(unsigned int *)((char *)v20 + v99 + 32) >> (5 * (unsigned __int8)v98))
                       & 0x1F;
                  v126 = (char *)v100;
                  v101 = *((_QWORD *)v20 + 2);
                  v102 = *(_QWORD *)((char *)v20 + v99 + 80);
                  if ( v96 + (unsigned int)v100 - v101 >= v102 || !v100 )
                  {
                    v100 = v101 + v102 - v96;
                    v126 = (char *)v100;
                    v97 = 0;
                    v147 = 0;
                  }
                  v103 = v132;
                  if ( !(**v132)(v132, v96) )
                    goto LABEL_145;
                  v104 = 0;
                  v105 = ((__int64 (__fastcall *)(unsigned __int8 (__fastcall ***)(_QWORD, _QWORD)))(*v103)[2])(v103);
                  if ( !v105 )
                    goto LABEL_145;
                  v106 = v135;
                  v107 = v131;
                  v108 = v132;
                  do
                  {
                    if ( (const struct CWordNode *)v105 != v20
                      && (*(_DWORD *)(*(int *)(*(_QWORD *)(v105 + 8) + 4LL) + v105 + 72) & 0xFFFFFFu) - 16777214 > 1 )
                    {
                      if ( (unsigned __int8)LSP::IsLengthMatch(v107, v106, v105, &v126) )
                      {
                        v104 = (struct CWordNode *)v105;
                        if ( (*(_DWORD *)(*(int *)(*(_QWORD *)(v105 + 8) + 4LL) + v105 + 8) & 0xF8000000) == 0x38000000 )
                          break;
                      }
                    }
                    v105 = ((__int64 (__fastcall *)(unsigned __int8 (__fastcall ***)(_QWORD, _QWORD)))(*v108)[4])(v108);
                  }
                  while ( v105 );
                  v98 = v129;
                  v97 = v147;
                  v100 = (unsigned __int64)v126;
                  if ( !v104 )
                  {
LABEL_145:
                    v104 = CWordNode::CloneOf(v20, v127);
                    v109 = (char *)v104 + 8;
                    v126 = (char *)v104 + 8;
                    if ( v98 )
                    {
                      v110 = *((_QWORD *)this + 3);
                      v111 = v96 + *(_QWORD *)(v110 + 8);
                      v112 = *(int *)(*(_QWORD *)v109 + 4LL);
                      v113 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v110 + 216) + 288LL))(*(_QWORD *)(v110 + 216));
                      v114 = (__int64 *)(*(__int64 (__fastcall **)(__int64, char *, __int64, unsigned __int64))(*(_QWORD *)v113 + 40LL))(
                                          v113,
                                          &v142,
                                          v111,
                                          v100);
                      v115 = *v114;
                      *(_QWORD *)((char *)v104 + v112 + 56) = v114[1];
                      *(_QWORD *)((char *)v104 + v112 + 48) = v115;
                      v109 = v126;
                      v98 = v129;
                    }
                    v116 = *(int *)(*(_QWORD *)v109 + 4LL);
                    *(_DWORD *)((char *)v104 + v116 + 8) &= 0x7FFFFFFu;
                    *(_DWORD *)((char *)v104 + v116 + 8) |= 0x38000000u;
                    *((_QWORD *)v104 + 2) = v96;
                    *(_QWORD *)((char *)v104 + *(int *)(*(_QWORD *)v109 + 4LL) + 64) = v100;
                    *(_QWORD *)((char *)v104 + *(int *)(*(_QWORD *)v109 + 4LL) + 80) = v100;
                    v117 = *(int *)(*(_QWORD *)v109 + 4LL);
                    *(_OWORD *)((char *)v104 + v117 + 16) = 0;
                    *(_QWORD *)((char *)v104 + v117 + 32) = 0;
                    *(_QWORD *)((char *)v104 + *(int *)(*(_QWORD *)v109 + 4LL) + 88) = 0;
                  }
                  v11 = v130;
                  v118 = v130[2];
                  v119 = v130[1];
                  if ( v119 >= v118 )
                  {
                    v120 = v119 + 1;
                    v121 = v130[1];
                    if ( v119 < 8 )
                      v121 = 8;
                    v122 = v118 + v121;
                    if ( v120 < v122 )
                      v120 = v122;
                    if ( v120 > v118 )
                    {
                      CArray<CWordNode *,CArrayAllocator_GC<CZoneHeap>>::ReallocWorker(v130);
                      v119 = v11[1];
                    }
                  }
                  *(_QWORD *)(*v11 + 8 * v119) = v104;
                  ++v11[1];
                  v96 += v100;
                  v129 = ++v98;
                }
                while ( v98 < 6 );
                v6 = v133;
                v9 = v136;
                v10 = v128;
                v12 = v134;
                v5 = v150;
              }
              else
              {
                v45 = v11[2];
                v46 = v11[1];
                if ( v46 >= v45 )
                {
                  v47 = v46 + 1;
                  v48 = v11[1];
                  if ( v46 < 8 )
                    v48 = 8;
                  v49 = v45 + v48;
                  if ( v47 < v49 )
                    v47 = v49;
                  if ( v47 > v45 )
                  {
                    CArray<CWordNode *,CArrayAllocator_GC<CZoneHeap>>::ReallocWorker(v11);
                    v46 = v11[1];
                  }
                }
                *(_QWORD *)(*v11 + 8 * v46) = v20;
                ++v11[1];
              }
              if ( v148 )
              {
                if ( v125 )
                {
                  if ( v12 < v10[2] )
                    goto LABEL_86;
LABEL_58:
                  v10 = 0;
                  v11 = 0;
                  v128 = 0;
                  v130 = 0;
                  goto LABEL_14;
                }
                if ( *((_QWORD *)v20 + 2) + *(_QWORD *)((char *)v20 + *(int *)(*((_QWORD *)v20 + 1) + 4LL) + 80) < v10[2] + *(__int64 *)((char *)v10 + *(int *)(v10[1] + 4) + 80) )
                  goto LABEL_58;
LABEL_86:
                v20 = (const struct CWordNode *)v10;
LABEL_47:
                v27 = *(int *)(*((_QWORD *)v20 + 1) + 4LL);
                if ( (*(_DWORD *)((_BYTE *)v20 + v27 + 72) & 0xFFFFFFu) - 16777214 > 1 )
                {
                  if ( *(_DWORD *)((char *)v20 + v27 + 32) )
                  {
                    v52 = *(_DWORD *)((char *)v20 + v27 + 8) >> 27;
                    if ( v52 != 2 )
                    {
                      v53 = v52 - 3;
                      if ( v53 )
                      {
                        v54 = v53 - 14;
                        if ( v54 )
                        {
                          v55 = v54 - 1;
                          if ( v55 )
                          {
                            v56 = v55 - 1;
                            if ( v56 )
                            {
                              if ( v56 != 3 )
                              {
                                *(_DWORD *)((char *)v20 + v27 + 8) = *(_DWORD *)((_BYTE *)v20 + v27 + 8) & 0x7FFFFFF
                                                                   | 0x50000000;
                                v57 = v127;
                                v58 = CMorphNode::NewProperties(
                                        (const struct CWordNode *)((char *)v20 + *(int *)(*((_QWORD *)v20 + 1) + 4LL)
                                                                               + 8),
                                        v127);
                                v59 = CNodeProperties::NewProperty(v58, v57);
                                *((_BYTE *)v59 + 11) = 1;
                                v60 = CZoneHeap::Alloc(v57, 0x28u, 8u);
                                *((_QWORD *)v59 + 2) = v60;
                                *(_QWORD *)v60 = 0;
                                *((_QWORD *)v60 + 1) = 0;
                                *((_QWORD *)v60 + 2) = 0;
                                v60[24] = 1;
                                *((_QWORD *)v60 + 4) = v57;
                                v61 = (__int64 *)*((_QWORD *)v59 + 2);
                                v128 = v61;
                                *((_DWORD *)v59 + 2) = 16777463;
                                v62 = *((_QWORD *)v20 + 2);
                                v63 = 1;
                                v146 = 1;
                                LOBYTE(v64) = 0;
                                v149 = 0;
                                do
                                {
                                  if ( !v63 )
                                    break;
                                  v65 = *(int *)(*((_QWORD *)v20 + 1) + 4LL);
                                  v66 = ((unsigned __int64)*(unsigned int *)((char *)v20 + v65 + 32) >> (5 * (unsigned __int8)v64))
                                      & 0x1F;
                                  v126 = (char *)v66;
                                  v67 = *((_QWORD *)v20 + 2);
                                  v68 = *(_QWORD *)((char *)v20 + v65 + 80);
                                  if ( v62 + (unsigned int)v66 - v67 >= v68 || !v66 )
                                  {
                                    v66 = v67 + v68 - v62;
                                    v126 = (char *)v66;
                                    v63 = 0;
                                    v146 = 0;
                                  }
                                  v69 = v132;
                                  if ( !(**v132)(v132, v62) )
                                    goto LABEL_113;
                                  v70 = 0;
                                  v71 = ((__int64 (__fastcall *)(unsigned __int8 (__fastcall ***)(_QWORD, _QWORD)))(*v69)[2])(v69);
                                  if ( !v71 )
                                    goto LABEL_113;
                                  v72 = v135;
                                  v73 = v131;
                                  v74 = v132;
                                  do
                                  {
                                    if ( (const struct CWordNode *)v71 != v20
                                      && (*(_DWORD *)(*(int *)(*(_QWORD *)(v71 + 8) + 4LL) + v71 + 72) & 0xFFFFFFu)
                                       - 16777214 > 1 )
                                    {
                                      if ( (unsigned __int8)LSP::IsLengthMatch(v73, v72, v71, &v126) )
                                      {
                                        v70 = (struct CWordNode *)v71;
                                        if ( (*(_DWORD *)(*(int *)(*(_QWORD *)(v71 + 8) + 4LL) + v71 + 8) & 0xF8000000) == 0x38000000 )
                                          break;
                                      }
                                    }
                                    v71 = ((__int64 (__fastcall *)(unsigned __int8 (__fastcall ***)(_QWORD, _QWORD)))(*v74)[4])(v74);
                                  }
                                  while ( v71 );
                                  v61 = v128;
                                  v63 = v146;
                                  v66 = (unsigned __int64)v126;
                                  if ( !v70 )
                                  {
LABEL_113:
                                    v70 = CWordNode::CloneOf(v20, v127);
                                    v75 = (char *)v70 + 8;
                                    v134 = (__int64)v70 + 8;
                                    if ( v149 )
                                    {
                                      v76 = *((_QWORD *)this + 3);
                                      v77 = v62 + *(_QWORD *)(v76 + 8);
                                      v78 = *(int *)(*(_QWORD *)v75 + 4LL);
                                      v79 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v76 + 216) + 288LL))(*(_QWORD *)(v76 + 216));
                                      v80 = (__int64 *)(*(__int64 (__fastcall **)(__int64, char *, __int64, unsigned __int64))(*(_QWORD *)v79 + 40LL))(
                                                         v79,
                                                         &v143,
                                                         v77,
                                                         v66);
                                      v81 = *v80;
                                      *(_QWORD *)((char *)v70 + v78 + 56) = v80[1];
                                      *(_QWORD *)((char *)v70 + v78 + 48) = v81;
                                      v61 = v128;
                                      v75 = (char *)v134;
                                    }
                                    *(_DWORD *)((char *)v70 + *(int *)(*(_QWORD *)v75 + 4LL) + 72) = -1;
                                    v82 = *(int *)(*(_QWORD *)v75 + 4LL);
                                    *(_DWORD *)((char *)v70 + v82 + 8) &= 0x7FFFFFFu;
                                    *(_DWORD *)((char *)v70 + v82 + 8) |= 0x38000000u;
                                    *((_QWORD *)v70 + 2) = v62;
                                    *(_QWORD *)((char *)v70 + *(int *)(*(_QWORD *)v75 + 4LL) + 64) = v66;
                                    *(_QWORD *)((char *)v70 + *(int *)(*(_QWORD *)v75 + 4LL) + 80) = v66;
                                    v83 = *(int *)(*(_QWORD *)v75 + 4LL);
                                    *(_OWORD *)((char *)v70 + v83 + 16) = 0;
                                    *(_QWORD *)((char *)v70 + v83 + 32) = 0;
                                    *(_QWORD *)((char *)v70 + *(int *)(*(_QWORD *)v75 + 4LL) + 88) = 0;
                                    v84 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 80LL))(*((_QWORD *)this + 3));
                                    v85 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v84 + 24LL))(v84);
                                    (*(void (__fastcall **)(__int64, struct CWordNode *))(*(_QWORD *)v85 + 96LL))(
                                      v85,
                                      v70);
                                  }
                                  v86 = v61[2];
                                  v87 = v61[1];
                                  if ( v87 >= v86 )
                                  {
                                    v88 = v87 + 1;
                                    v89 = v61[1];
                                    if ( v87 < 8 )
                                      v89 = 8;
                                    v90 = v86 + v89;
                                    if ( v88 < v90 )
                                      v88 = v90;
                                    if ( v88 > v86 )
                                    {
                                      CArray<CWordNode *,CArrayAllocator_GC<CZoneHeap>>::ReallocWorker(v61);
                                      v87 = v61[1];
                                    }
                                  }
                                  *(_QWORD *)(*v61 + 8 * v87) = v70;
                                  ++v61[1];
                                  v62 += v66;
                                  v64 = v149 + 1;
                                  v149 = v64;
                                }
                                while ( v64 < 6 );
                                v6 = v133;
                                v9 = v136;
                                v5 = v150;
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
                v28 = *((_DWORD *)this + 4112);
                if ( v28 )
                {
                  v29 = v28 - 1;
                  *((_DWORD *)this + 4112) = v29;
                  v30 = (char *)this + 64 * v29 + 64;
                }
                else
                {
                  v35 = (char *)operator new(0x40u);
                  v30 = v35;
                  if ( !v35 )
                  {
                    CNLException::CNLException((CNLException *)pExceptionObject, 2147942414LL, retaddr);
                    throw (CNLException *)pExceptionObject;
                  }
                  v141 = v35;
                  *(_QWORD *)v35 = &NaturalLanguage6::Segment::`vftable';
                  *((_DWORD *)v35 + 2) = 1;
                  *(_QWORD *)v35 = &NaturalLanguage6::BoundSegment::`vftable';
                  *((_QWORD *)v35 + 2) = this;
                  *((_QWORD *)v35 + 3) = 0;
                  *((_QWORD *)v35 + 4) = 0;
                  *((_QWORD *)v35 + 5) = 0;
                  *((_DWORD *)v35 + 12) = 2;
                  *((_QWORD *)v35 + 7) = 0;
                  *((_DWORD *)v35 + 2) = 1;
                }
                *((_QWORD *)v30 + 3) = 0;
                *((_QWORD *)v30 + 5) = v20;
                *((_DWORD *)v30 + 12) = 2;
                v31 = *((_QWORD *)this + 6);
                v32 = *((_QWORD *)this + 5);
                if ( v32 >= v31 )
                {
                  v33 = v32 + 1;
                  if ( v32 < 8 )
                    v32 = 8;
                  v34 = v31 + v32;
                  if ( v33 < v34 )
                    v33 = v34;
                  if ( v33 > v31 )
                    CArray<NLG::ITrieIter *,CArrayAllocator_malloc>::ReallocWorker((char *)this + 32);
                }
                *(_QWORD *)(*((_QWORD *)this + 4) + 8LL * (*((_QWORD *)this + 5))++) = v30;
                v12 = *((_QWORD *)v20 + 2);
                v134 = v12;
                goto LABEL_58;
              }
            }
          }
        }
LABEL_14:
        v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
        v136 = v9;
      }
    }
  }
}

```

## disassembly

```asm
0x18000e520  push    rbx
0x18000e522  push    rbp
0x18000e523  push    rsi
0x18000e524  push    rdi
0x18000e525  push    r12
0x18000e527  push    r13
0x18000e529  push    r14
0x18000e52b  push    r15
0x18000e52d  sub     rsp, 128h
0x18000e534  mov     [rsp+168h+var_C0], 0FFFFFFFFFFFFFFFEh
0x18000e540  mov     r15, rcx
0x18000e543  mov     rax, [rcx+18h]
0x18000e547  mov     rcx, [rax+0D8h]
0x18000e54e  test    rcx, rcx
0x18000e551  jz      loc_18000E824
0x18000e557  mov     rax, [rcx]
0x18000e55a  mov     rax, [rax+88h]
0x18000e561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e566  test    rax, rax
0x18000e569  jz      loc_18000E824
0x18000e56f  mov     rcx, [r15+18h]
0x18000e573  mov     rax, [rcx+0A8h]
0x18000e57a  movzx   esi, byte ptr [rax+8]
0x18000e57e  mov     [rsp+168h+var_137], sil
0x18000e583  movzx   r13d, byte ptr [rcx+2Dh]
0x18000e588  mov     [rsp+168h+arg_10], r13b
0x18000e590  xor     ebx, ebx
0x18000e592  mov     [rsp+168h+var_F8], rbx
0x18000e597  mov     [rsp+168h+var_D8], rbx
0x18000e59f  mov     rdi, [r15+18h]
0x18000e5a3  mov     eax, [rdi+0B0h]
0x18000e5a9  mov     [rsp+168h+var_108], eax
0x18000e5ad  mov     rcx, [rdi+90h]; unsigned __int64
0x18000e5b4  mov     [rsp+168h+var_E8], rcx
0x18000e5bc  test    rcx, rcx
0x18000e5bf  jz      loc_18000EB93
0x18000e5c5  mov     rax, [r15+18h]
0x18000e5c9  mov     r14, [rax+70h]
0x18000e5cd  mov     [rsp+168h+var_E0], r14
0x18000e5d5  test    r14, r14
0x18000e5d8  jz      loc_18000E892
0x18000e5de  test    sil, sil
0x18000e5e1  jz      loc_18000F2C6
0x18000e5e7  xor     esi, esi
0x18000e5e9  mov     [rsp+168h+var_120], rsi
0x18000e5ee  xor     edi, edi
0x18000e5f0  mov     [rsp+168h+var_110], rdi
0x18000e5f5  mov     r12, 0FFFFFFFFFFFFFFFFh
0x18000e5fc  mov     [rsp+168h+var_F0], r12
0x18000e601  mov     rcx, [r15+18h]
0x18000e605  mov     rdx, [rcx+8]
0x18000e609  mov     [rsp+168h+var_D0], rdx
0x18000e611  mov     rax, [rcx+10h]
0x18000e615  add     rax, rdx
0x18000e618  mov     [rsp+168h+var_C8], rax
0x18000e620  mov     rax, [rcx+0A8h]
0x18000e627  cmp     [rax+18h], sil
0x18000e62b  jnz     loc_18000EBD2
0x18000e631  mov     rax, [rcx]
0x18000e634  mov     rax, [rax+50h]
0x18000e638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e63d  mov     rdx, rax
0x18000e640  mov     rcx, [rax]
0x18000e643  mov     rax, [rcx+20h]
0x18000e647  mov     rcx, rdx
0x18000e64a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e64f  mov     [rsp+168h+var_128], rax
0x18000e654  mov     rcx, [r15+18h]
0x18000e658  mov     rdx, [rcx]
0x18000e65b  mov     rax, [rdx+50h]
0x18000e65f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e664  mov     rdx, rax
0x18000e667  mov     rcx, [rax]
0x18000e66a  mov     rax, [rcx+18h]
0x18000e66e  mov     rcx, rdx
0x18000e671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e676  mov     rdx, rax
0x18000e679  mov     rcx, [rax]
0x18000e67c  mov     rax, [rcx+58h]
0x18000e680  mov     rcx, rdx
0x18000e683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e688  mov     [rsp+168h+var_100], rax
0x18000e68d  mov     rcx, [r15+18h]
0x18000e691  mov     rcx, [rcx+0D8h]
0x18000e698  mov     rdx, [rcx]
0x18000e69b  mov     rax, [rdx+88h]
0x18000e6a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6a7  movzx   eax, byte ptr [rax+15h]
0x18000e6ab  mov     [rsp+168h+arg_18], al
0x18000e6b2  mov     rcx, [r15+18h]
0x18000e6b6  mov     rcx, [rcx+0D8h]
0x18000e6bd  mov     rdx, [rcx]
0x18000e6c0  mov     rax, [rdx+88h]
0x18000e6c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6cc  movzx   eax, byte ptr [rax+13h]
0x18000e6d0  mov     [rsp+168h+var_138], al
0x18000e6d4  test    r14, r14
0x18000e6d7  jz      loc_18000E810
0x18000e6dd  mov     rax, [r14]
0x18000e6e0  mov     rcx, r14
0x18000e6e3  mov     rax, [rax+20h]
0x18000e6e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6ec  mov     rbp, rax
0x18000e6ef  test    rax, rax
0x18000e6f2  jz      short loc_18000E720
0x18000e6f4  test    r13b, r13b
0x18000e6f7  jz      loc_18000E838
0x18000e6fd  cmp     [rsp+168h+var_138], 0
0x18000e702  jz      loc_18000E79E
0x18000e708  mov     rax, [rbp+8]
0x18000e70c  movsxd  rax, dword ptr [rax+4]
0x18000e710  mov     eax, [rax+rbp+0Ch]
0x18000e714  and     eax, 3F0000h
0x18000e719  cmp     eax, 100000h
0x18000e71e  jnz     short loc_18000E73C
0x18000e720  mov     rax, [r14]
0x18000e723  mov     rcx, r14
0x18000e726  mov     rax, [rax+8]
0x18000e72a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e72f  mov     r14, rax
0x18000e732  mov     [rsp+168h+var_E0], rax
0x18000e73a  jmp     short loc_18000E6D4
0x18000e73c  cmp     eax, 180000h
0x18000e741  jz      short loc_18000E720
0x18000e743  cmp     eax, 1B0000h
0x18000e748  jz      short loc_18000E720
0x18000e74a  cmp     eax, 0C0000h
0x18000e74f  jz      short loc_18000E720
0x18000e751  cmp     eax, 130000h
0x18000e756  jz      short loc_18000E720
0x18000e758  cmp     eax, 0D0000h
0x18000e75d  jz      short loc_18000E720
0x18000e75f  cmp     eax, 80000h
0x18000e764  jz      short loc_18000E720
0x18000e766  cmp     eax, 200000h
0x18000e76b  jz      short loc_18000E720
0x18000e76d  cmp     eax, 1A0000h
0x18000e772  jz      short loc_18000E720
0x18000e774  cmp     eax, 0E0000h
0x18000e779  jz      short loc_18000E720
0x18000e77b  cmp     eax, 1F0000h
0x18000e780  jz      short loc_18000E720
0x18000e782  cmp     eax, 190000h
0x18000e787  jz      short loc_18000E720
0x18000e789  cmp     eax, 0A0000h
0x18000e78e  jz      short loc_18000E720
0x18000e790  cmp     eax, 0B0000h
0x18000e795  jz      short loc_18000E720
0x18000e797  cmp     eax, 90000h
0x18000e79c  jz      short loc_18000E720
0x18000e79e  mov     rax, [rbp+8]
0x18000e7a2  movsxd  rdx, dword ptr [rax+4]
0x18000e7a6  mov     ecx, [rdx+rbp+8]
0x18000e7aa  mov     eax, ecx
0x18000e7ac  shr     eax, 1Bh
0x18000e7af  cmp     eax, 0Ah
0x18000e7b2  jz      loc_18000E894
0x18000e7b8  cmp     eax, 7
0x18000e7bb  jnz     loc_18000E89E
0x18000e7c1  and     cl, 0F0h
0x18000e7c4  cmp     cl, 40h ; '@'
0x18000e7c7  jz      loc_18000E89E
0x18000e7cd  mov     byte ptr [rsp+168h+arg_8], 0
0x18000e7d5  test    rsi, rsi
0x18000e7d8  jnz     loc_18000EA03
0x18000e7de  mov     rax, [rdx+rbp+58h]
0x18000e7e3  mov     rcx, [rax]
0x18000e7e6  test    rcx, rcx
0x18000e7e9  jz      loc_18000E9F2
0x18000e7ef  test    rcx, rcx
0x18000e7f2  jz      loc_18000E9F2
0x18000e7f8  mov     eax, [rcx+8]
0x18000e7fb  and     eax, 0FFFFFFh
0x18000e800  cmp     eax, 111Bh
0x18000e805  jz      loc_18000E9C8
0x18000e80b  mov     rcx, [rcx]
0x18000e80e  jmp     short loc_18000E7EF
0x18000e810  test    rbx, rbx
0x18000e813  jz      short loc_18000E824
0x18000e815  mov     rax, [rbx]
0x18000e818  mov     rcx, rbx
0x18000e81b  mov     rax, [rax+10h]
0x18000e81f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e824  add     rsp, 128h
0x18000e82b  pop     r15
0x18000e82d  pop     r14
0x18000e82f  pop     r13
0x18000e831  pop     r12
0x18000e833  pop     rdi
0x18000e834  pop     rsi
0x18000e835  pop     rbp
0x18000e836  pop     rbx
0x18000e837  retn
0x18000e838  mov     rcx, [rax+8]
0x18000e83c  movsxd  rdx, dword ptr [rcx+4]
0x18000e840  mov     rax, [rdx+rax+50h]
0x18000e845  test    rax, rax
0x18000e848  jle     loc_18000E720
0x18000e84e  mov     rcx, [rbp+10h]
0x18000e852  add     rcx, rax
0x18000e855  add     rcx, [rsp+168h+var_D0]
0x18000e85d  cmp     rcx, [rsp+168h+var_C8]
0x18000e865  jg      loc_18000E720
0x18000e86b  mov     eax, [rdx+rbp+0Ch]
0x18000e86f  and     eax, 3F0000h
0x18000e874  cmp     eax, 10000h
0x18000e879  jnz     loc_18000E6FD
0x18000e87f  cmp     [rsp+168h+arg_18], 0
0x18000e887  jnz     loc_18000E6FD
0x18000e88d  jmp     loc_18000E720
0x18000e892  jmp     short loc_18000E824
0x18000e894  and     ecx, 7FFFFFFh
0x18000e89a  mov     [rdx+rbp+8], ecx
0x18000e89e  mov     rax, [rbp+8]
0x18000e8a2  movsxd  rcx, dword ptr [rax+4]
0x18000e8a6  mov     eax, [rcx+rbp+48h]
0x18000e8aa  and     eax, 0FFFFFFh
0x18000e8af  sub     eax, 0FFFFFEh
0x18000e8b4  cmp     eax, 1
0x18000e8b7  ja      loc_18000EBDD
0x18000e8bd  mov     eax, [r15+4040h]
0x18000e8c4  test    eax, eax
0x18000e8c6  jz      loc_18000E958
0x18000e8cc  dec     eax
0x18000e8ce  mov     [r15+4040h], eax
0x18000e8d5  movsxd  rsi, eax
0x18000e8d8  inc     rsi
0x18000e8db  shl     rsi, 6
0x18000e8df  add     rsi, r15
0x18000e8e2  mov     qword ptr [rsi+18h], 0
0x18000e8ea  mov     [rsi+28h], rbp
0x18000e8ee  mov     dword ptr [rsi+30h], 2
0x18000e8f5  mov     rcx, [r15+30h]
0x18000e8f9  mov     rax, [r15+28h]
0x18000e8fd  cmp     rax, rcx
0x18000e900  jl      short loc_18000E92C
0x18000e902  lea     rdx, [rax+1]
0x18000e906  cmp     rax, 8
0x18000e90a  mov     r8d, 8
0x18000e910  cmovl   rax, r8
0x18000e914  add     rax, rcx
0x18000e917  cmp     rdx, rax
0x18000e91a  cmovl   rdx, rax
0x18000e91e  cmp     rdx, rcx
0x18000e921  jle     short loc_18000E92C
0x18000e923  lea     rcx, [r15+20h]
0x18000e927  call    ?ReallocWorker@?$CArray@PEAVITrieIter@NLG@@VCArrayAllocator_malloc@@@@AEAAX_J@Z; CArray<NLG::ITrieIter *,CArrayAllocator_malloc>::ReallocWorker(__int64)
0x18000e92c  mov     rdx, [r15+28h]
0x18000e930  mov     rax, [r15+20h]
0x18000e934  mov     [rax+rdx*8], rsi
0x18000e938  inc     qword ptr [r15+28h]
0x18000e93c  mov     r12, [rbp+10h]
0x18000e940  mov     [rsp+168h+var_F0], r12
0x18000e945  xor     esi, esi
0x18000e947  xor     edi, edi
0x18000e949  mov     [rsp+168h+var_120], rsi
0x18000e94e  mov     [rsp+168h+var_110], rdi
0x18000e953  jmp     loc_18000E720
0x18000e958  mov     ecx, 40h ; '@'; Size
0x18000e95d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e962  mov     rsi, rax
0x18000e965  test    rax, rax
0x18000e968  jz      loc_18000F340
0x18000e96e  mov     [rsp+168h+var_B8], rax
0x18000e976  lea     rax, ??_7Segment@NaturalLanguage6@@6B@; const NaturalLanguage6::Segment::`vftable'
0x18000e97d  mov     [rsi], rax
0x18000e980  mov     dword ptr [rsi+8], 1
0x18000e987  lea     rax, ??_7BoundSegment@NaturalLanguage6@@6B@; const NaturalLanguage6::BoundSegment::`vftable'
0x18000e98e  mov     [rsi], rax
0x18000e991  mov     [rsi+10h], r15
0x18000e995  mov     qword ptr [rsi+18h], 0
0x18000e99d  mov     qword ptr [rsi+20h], 0
0x18000e9a5  mov     qword ptr [rsi+28h], 0
0x18000e9ad  mov     dword ptr [rsi+30h], 2
0x18000e9b4  mov     qword ptr [rsi+38h], 0
0x18000e9bc  mov     dword ptr [rsi+8], 1
0x18000e9c3  jmp     loc_18000E8E2
0x18000e9c8  mov     rsi, [rcx+10h]
0x18000e9cc  mov     [rsp+168h+var_120], rsi
0x18000e9d1  mov     rax, [rsi+8]
0x18000e9d5  movsxd  rcx, dword ptr [rax+4]
0x18000e9d9  mov     eax, [rcx+rsi+8]
0x18000e9dd  cmp     eax, 8000000h
0x18000e9e2  jnb     short loc_18000E9F2
0x18000e9e4  and     eax, 7FFFFFFh
0x18000e9e9  or      eax, 50000000h
0x18000e9ee  mov     [rcx+rsi+8], eax
0x18000e9f2  mov     byte ptr [rsp+168h+arg_8], 1
0x18000e9fa  test    rsi, rsi
0x18000e9fd  jz      loc_18000F311
0x18000ea03  test    rdi, rdi
0x18000ea06  jnz     loc_18000EAC4
0x18000ea0c  mov     rax, [rsi+8]
0x18000ea10  movsxd  rdi, dword ptr [rax+4]
0x18000ea14  mov     rcx, [rdi+rsi+58h]
0x18000ea19  test    rcx, rcx
0x18000ea1c  jnz     short loc_18000EA48
0x18000ea1e  mov     eax, 8
0x18000ea23  mov     r8d, eax; unsigned __int64
0x18000ea26  mov     edx, eax; unsigned __int64
  ... truncated ...
```
