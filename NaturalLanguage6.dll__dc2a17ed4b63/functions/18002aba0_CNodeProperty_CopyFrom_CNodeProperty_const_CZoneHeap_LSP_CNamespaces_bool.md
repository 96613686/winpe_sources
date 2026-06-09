# CNodeProperty::CopyFrom(CNodeProperty const *,CZoneHeap &,LSP::CNamespaces *,bool)

- ea: `0x18002aba0`
- end: `0x18002b243`
- name: `?CopyFrom@CNodeProperty@@QEAAXPEBV1@AEAVCZoneHeap@@PEAVCNamespaces@LSP@@_N@Z`
- size: `1699`
- prototype: `void __fastcall(CNodeProperty *__hidden this, const struct CNodeProperty *, struct CZoneHeap *, struct LSP::CNamespaces *, bool)`
- caller_count: `2`
- callee_count: `24`
- tags: ``

## callers

- `0x18002aa28`
- `0x18002aba0`

## callees

- `0x180003d38`
- `0x18000f380`
- `0x1800107c0`
- `0x1800268f0`
- `0x18002a880`
- `0x18002aba0`
- `0x18002b24c`
- `0x18002b2a0`
- `0x18002b380`
- `0x18002d8c4`
- `0x1800506ec`
- `0x18005257c`
- `0x1800525b4`
- `0x180054478`
- `0x180054f00`
- `0x18005dd90`
- `0x18005ddfc`
- `0x18005de3c`
- `0x18005dfa0`
- `0x18005dff4`
- `0x18005e060`
- `0x18005e09c`
- `0x18005e160`
- `0x1800b0010`

## pseudocode

```c
void __fastcall CNodeProperty::CopyFrom(
        CNodeProperty *this,
        const struct CNodeProperty *a2,
        struct CZoneHeap *a3,
        struct LSP::CNamespaces *a4,
        bool a5)
{
  int v7; // edx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned __int64 v18; // rax
  int v19; // edx
  int v20; // xmm0_4
  __int64 v21; // rcx
  int v22; // eax
  void *v23; // rdx
  __int64 v24; // r8
  const struct CWordNode *v25; // rsi
  CWordNode *v26; // rax
  CWordNode *v27; // rbx
  __int64 v28; // rbx
  __int64 v29; // rax
  _QWORD *v30; // rbx
  __int64 v31; // rax
  _QWORD *v32; // rdi
  int i; // esi
  CWordNode *v34; // rax
  CWordNode *v35; // r12
  const struct CWordNode **v36; // rax
  __int64 v37; // r9
  __int64 v38; // r8
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 j; // rdx
  const unsigned __int16 *v42; // r8
  unsigned __int64 v43; // r9
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  unsigned int v48; // ecx
  unsigned int v49; // ecx
  CNodeProperty *v50; // rbx
  CNodeProperty *v51; // rbx
  __int64 *v52; // r14
  __int64 *v53; // rsi
  int k; // ebp
  LSP::CName *v55; // rax
  __int64 v56; // rax
  __int64 v57; // r9
  __int64 v58; // r8
  __int64 v59; // rbx
  __int64 v60; // rdi
  __int64 v61; // rdx
  __int64 v62; // rdx
  __int64 v63; // rax
  __int64 v64; // r8
  __int64 v65; // rdi
  __int64 (__fastcall *v66)(__int64, char *, const unsigned __int16 *, _QWORD); // rbx
  LSP::CName *v67; // rax
  const unsigned __int16 *v68; // rax
  __int64 v69; // rax
  __int64 v70; // r10
  _OWORD *v71; // rbx
  __int64 v72; // r9
  __int64 v73; // rdx
  __int64 v74; // rdx
  __int64 v75; // rax
  __int64 *v76; // rbx
  __int64 m; // r9
  __int64 v78; // rdx
  __int64 v79; // rcx
  __int64 v80; // r8
  __int64 v81; // rbx
  _OWORD *v82; // rcx
  __int64 v83; // rdx
  __int128 v84; // xmm1
  __int128 v85; // xmm0
  __int128 v86; // xmm1
  __int128 v87; // xmm0
  __int128 v88; // xmm1
  __int128 v89; // xmm0
  __int128 v90; // xmm1
  struct CHyphenationPoints *v91; // rcx
  _OWORD *v92; // rax
  __int128 v93; // xmm1
  __int128 v94; // xmm0
  __int128 v95; // xmm1
  __int128 v96; // xmm0
  __int128 v97; // xmm1
  __int128 v98; // xmm0
  __int128 v99; // xmm1
  int v100; // [rsp+20h] [rbp-288h]
  __int16 v101; // [rsp+30h] [rbp-278h] BYREF
  char v102[32]; // [rsp+38h] [rbp-270h] BYREF
  _BYTE v103[592]; // [rsp+58h] [rbp-250h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  *((_QWORD *)this + 2) = 0;
  v7 = *((_DWORD *)a2 + 2);
  *((_DWORD *)this + 2) = v7;
  v10 = (unsigned __int8)HIBYTE(*((_DWORD *)a2 + 2));
  if ( v10 <= 0xA )
  {
    if ( v10 == 10 )
    {
      v42 = (const unsigned __int16 *)*((_QWORD *)a2 + 2);
      if ( v42 )
      {
        v43 = -1;
        do
          ++v43;
        while ( v42[v43] );
        CNodeProperty::NewString(this, a3, v42, v43);
      }
      return;
    }
    v11 = v10 - 1;
    if ( !v11 )
    {
      v30 = (_QWORD *)*((_QWORD *)a2 + 2);
      if ( v30 )
      {
        v31 = CNodeProperty::NewTokenArray(this, a3);
        v32 = (_QWORD *)v31;
        if ( a5 )
        {
          for ( i = 0; i < v30[1]; ++v32[1] )
          {
            v34 = (CWordNode *)CZoneHeap::Alloc(a3, 0x78u, 8u);
            v35 = CWordNode::CWordNode(v34);
            v36 = (const struct CWordNode **)CArray<NLG::CTrieWalker *,CArrayAllocator_malloc>::ElementAt(v30, i);
            CWordNode::CopyFrom(v35, *v36, a3, a4, a5);
            v37 = v32[2];
            v38 = v32[1];
            if ( v38 >= v37 )
            {
              v39 = v32[1];
              if ( v38 < 8 )
                v39 = 8;
              v40 = v37 + v39;
              if ( v38 + 1 >= v40 )
                v40 = v38 + 1;
              if ( v40 > v37 )
              {
                CArray<CWordNode *,CArrayAllocator_GC<CZoneHeap>>::ReallocWorker(v32);
                v38 = v32[1];
              }
            }
            ++i;
            *(_QWORD *)(*v32 + 8 * v38) = v35;
          }
        }
        else if ( (_QWORD *)v31 != v30 )
        {
          CArray<CWordNode *,CArrayAllocator_GC<CZoneHeap>>::SetArraySize(v31, v30[1]);
          for ( j = 0; j < v32[1]; ++j )
            *(_QWORD *)(*v32 + 8 * j) = *(_QWORD *)(*v30 + 8 * j);
        }
      }
      return;
    }
    v12 = v11 - 1;
    if ( v12 )
    {
      v13 = v12 - 1;
      if ( v13 )
      {
        v14 = v13 - 1;
        if ( v14 )
        {
          v15 = v14 - 2;
          if ( v15 )
          {
            v16 = v15 - 1;
            if ( !v16 )
            {
              v21 = *((_QWORD *)a2 + 2);
              v101 = 0;
              v22 = LongLongToShort(v21, &v101);
              if ( v22 < 0 )
                wil::details::in1diag3::_FailFast_Hr(retaddr, v23, v24, (const char *)(unsigned int)v22, v100);
              v18 = v101;
              *((_BYTE *)this + 11) = 7;
              goto LABEL_94;
            }
            v17 = v16 - 1;
            if ( !v17 )
            {
              v20 = *((_DWORD *)a2 + 4);
              *((_DWORD *)this + 2) = v7 & 0xFFFFFF | 0x8000000;
              *((_DWORD *)this + 4) = v20;
              return;
            }
            if ( v17 != 1 )
              return;
            v18 = *((_QWORD *)a2 + 2) != 0;
            v19 = v7 & 0xFFFFFF | 0x9000000;
          }
          else
          {
            v18 = *((int *)a2 + 4);
            v19 = v7 & 0xFFFFFF | 0x6000000;
          }
LABEL_12:
          *((_DWORD *)this + 2) = v19;
LABEL_94:
          *((_QWORD *)this + 2) = v18;
          return;
        }
        v25 = (const struct CWordNode *)*((_QWORD *)a2 + 2);
        if ( a5 )
        {
          v26 = (CWordNode *)CZoneHeap::Alloc(a3, 0x78u, 8u);
          v27 = CWordNode::CWordNode(v26);
          CWordNode::CopyFrom(v27, v25, a3, a4, a5);
          v7 = *((_DWORD *)this + 2);
        }
        else
        {
          v27 = v25;
        }
        *((_DWORD *)this + 2) = v7 & 0xFFFFFF | 0x4000000;
        *((_QWORD *)this + 2) = v27;
      }
      else
      {
        v28 = *((_QWORD *)a2 + 2);
        if ( v28 )
        {
          v29 = CNodeProperty::NewIntArray(this, a3);
          CArray<int,CArrayAllocator_GC<CZoneHeap>>::CopyArray(v29, v28);
        }
      }
      return;
    }
LABEL_57:
    v52 = (__int64 *)*((_QWORD *)a2 + 2);
    if ( v52 )
    {
      if ( a5 && a4 )
      {
        v53 = (__int64 *)CNodeProperty::NewNameArray(this, a3);
        for ( k = 0; k < v52[1]; ++k )
        {
          v55 = (LSP::CName *)CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::ElementAt(v52, k);
          if ( LSP::CName::IsFixedNamespace(v55) )
          {
            v56 = CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::ElementAt(v52, k);
            v57 = v53[2];
            v58 = v53[1];
            v59 = *((_QWORD *)a4 + 1);
            v60 = *(_QWORD *)(v56 + 8);
            if ( v58 >= v57 )
            {
              v61 = v53[1];
              if ( v58 < 8 )
                v61 = 8;
              v62 = v57 + v61;
              if ( v58 + 1 >= v62 )
                v62 = v58 + 1;
              if ( v62 > v57 )
              {
                CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::ReallocWorker(v53);
                v58 = v53[1];
              }
            }
            v63 = *v53;
            v64 = 2 * v58;
            *(_QWORD *)(v63 + 8 * v64) = v59;
            *(_QWORD *)(v63 + 8 * v64 + 8) = v60;
          }
          else
          {
            v65 = *(_QWORD *)a4;
            v66 = *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)a4 + 24LL);
            v67 = (LSP::CName *)CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::ElementAt(v52, k);
            v68 = LSP::CName::ToString(v67);
            v69 = v66(v65, v102, v68, 0);
            v70 = v53[2];
            v71 = (_OWORD *)v69;
            v72 = v53[1];
            if ( v72 >= v70 )
            {
              v73 = v53[1];
              if ( v72 < 8 )
                v73 = 8;
              v74 = v70 + v73;
              if ( v72 + 1 >= v74 )
                v74 = v72 + 1;
              if ( v74 > v70 )
              {
                CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::ReallocWorker(v53);
                v72 = v53[1];
              }
            }
            *(_OWORD *)(*v53 + 16 * v72) = *v71;
          }
          ++v53[1];
        }
      }
      else
      {
        v75 = CNodeProperty::NewNameArray(this, a3);
        v76 = (__int64 *)v75;
        if ( (__int64 *)v75 != v52 )
        {
          CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::SetArraySize(v75, v52[1]);
          for ( m = 0; m < v76[1]; *(_QWORD *)(v79 + 8 * v80) = *(_QWORD *)(v78 + 8 * v80) )
          {
            v78 = *v52;
            v79 = *v76;
            v80 = 2 * m++;
            *(_QWORD *)(v79 + 8 * v80 + 8) = *(_QWORD *)(*v52 + 8 * v80 + 8);
          }
        }
      }
    }
    return;
  }
  v44 = v10 - 11;
  if ( !v44 )
  {
    v18 = *((_QWORD *)a2 + 2);
    if ( !v18 )
      return;
    goto LABEL_94;
  }
  v45 = v44 - 1;
  if ( !v45 )
  {
    if ( *((_QWORD *)a2 + 2) )
      *(_QWORD *)CNodeProperty::NewSimpleTimeRepresentation(this, a3) = **((_QWORD **)a2 + 2);
    return;
  }
  v46 = v45 - 1;
  if ( !v46 )
  {
    v18 = *((_QWORD *)a2 + 2);
    if ( !v18 )
      return;
    if ( !a5 )
      goto LABEL_94;
    v81 = 4;
    v82 = v103;
    v83 = 4;
    do
    {
      v84 = *(_OWORD *)(v18 + 16);
      *v82 = *(_OWORD *)v18;
      v85 = *(_OWORD *)(v18 + 32);
      v82[1] = v84;
      v86 = *(_OWORD *)(v18 + 48);
      v82[2] = v85;
      v87 = *(_OWORD *)(v18 + 64);
      v82[3] = v86;
      v88 = *(_OWORD *)(v18 + 80);
      v82[4] = v87;
      v89 = *(_OWORD *)(v18 + 96);
      v82[5] = v88;
      v90 = *(_OWORD *)(v18 + 112);
      v18 += 128LL;
      v82[6] = v89;
      v82[7] = v90;
      v82 += 8;
      --v83;
    }
    while ( v83 );
    *(_DWORD *)v82 = *(_DWORD *)v18;
    v91 = CNodeProperty::NewHyphenationPoints(this, a3);
    v92 = v103;
    do
    {
      v93 = v92[1];
      *(_OWORD *)v91 = *v92;
      v94 = v92[2];
      *((_OWORD *)v91 + 1) = v93;
      v95 = v92[3];
      *((_OWORD *)v91 + 2) = v94;
      v96 = v92[4];
      *((_OWORD *)v91 + 3) = v95;
      v97 = v92[5];
      *((_OWORD *)v91 + 4) = v96;
      v98 = v92[6];
      *((_OWORD *)v91 + 5) = v97;
      v99 = v92[7];
      v92 += 8;
      *((_OWORD *)v91 + 6) = v98;
      *((_OWORD *)v91 + 7) = v99;
      v91 = (struct CHyphenationPoints *)((char *)v91 + 128);
      --v81;
    }
    while ( v81 );
    *(_DWORD *)v91 = *(_DWORD *)v92;
    return;
  }
  v47 = v46 - 1;
  if ( !v47 )
    goto LABEL_57;
  v48 = v47 - 1;
  if ( v48 )
  {
    v49 = v48 - 1;
    if ( v49 )
    {
      if ( v49 == 1 )
      {
        v18 = *((_QWORD *)a2 + 2);
        if ( v18 )
        {
          v19 = v7 & 0xFFFFFF | 0x11000000;
          goto LABEL_12;
        }
      }
    }
    else if ( *((_QWORD *)a2 + 2) )
    {
      v50 = (CNodeProperty *)CZoneHeap::Alloc(a3, 0x18u, 8u);
      *(_QWORD *)v50 = 0;
      CNodeProperty::CopyFrom(v50, *(const struct CNodeProperty **)(*((_QWORD *)a2 + 2) + 8LL), a3, a4, a5);
      CNodeProperty::NewGuidValue(this, a3, **((_QWORD **)a2 + 2), v50);
    }
  }
  else if ( *((_QWORD *)a2 + 2) )
  {
    v51 = (CNodeProperty *)CZoneHeap::Alloc(a3, 0x18u, 8u);
    *(_QWORD *)v51 = 0;
    CNodeProperty::CopyFrom(v51, *(const struct CNodeProperty **)(*((_QWORD *)a2 + 2) + 8LL), a3, a4, a5);
    CNodeProperty::NewNameValue(this, a3, **((_QWORD **)a2 + 2), v51);
  }
}

```

## disassembly

```asm
0x18002aba0  push    rbx
0x18002aba2  push    rbp
0x18002aba3  push    rsi
0x18002aba4  push    rdi
0x18002aba5  push    r12
0x18002aba7  push    r13
0x18002aba9  push    r14
0x18002abab  push    r15
0x18002abad  sub     rsp, 268h
0x18002abb4  mov     rsi, rdx
0x18002abb7  xor     r12d, r12d
0x18002abba  mov     [rcx+10h], r12
0x18002abbe  mov     rdi, rcx
0x18002abc1  mov     edx, [rdx+8]
0x18002abc4  mov     r13, r9
0x18002abc7  mov     [rcx+8], edx
0x18002abca  mov     rbp, r8
0x18002abcd  mov     eax, [rsi+8]
0x18002abd0  shr     rax, 18h
0x18002abd4  movzx   ecx, al
0x18002abd7  cmp     ecx, 0Ah
0x18002abda  ja      loc_18002AE76
0x18002abe0  jz      loc_18002AE4B
0x18002abe6  sub     ecx, 1
0x18002abe9  jz      loc_18002AD38
0x18002abef  sub     ecx, 1
0x18002abf2  jz      loc_18002AF87
0x18002abf8  sub     ecx, 1
0x18002abfb  jz      loc_18002AD10
0x18002ac01  sub     ecx, 1
0x18002ac04  jz      loc_18002ACAA
0x18002ac0a  sub     ecx, 2
0x18002ac0d  jz      loc_18002AC98
0x18002ac13  sub     ecx, 1
0x18002ac16  jz      short loc_18002AC60
0x18002ac18  sub     ecx, 1
0x18002ac1b  jz      short loc_18002AC44
0x18002ac1d  cmp     ecx, 1
0x18002ac20  jnz     loc_18002B22F
0x18002ac26  cmp     [rsi+10h], r12
0x18002ac2a  mov     eax, r12d
0x18002ac2d  setnz   al
0x18002ac30  and     edx, 0FFFFFFh
0x18002ac36  or      edx, 9000000h
0x18002ac3c  mov     [rdi+8], edx
0x18002ac3f  jmp     loc_18002B22B
0x18002ac44  movss   xmm0, dword ptr [rsi+10h]
0x18002ac49  and     edx, 0FFFFFFh
0x18002ac4f  bts     edx, 1Bh
0x18002ac53  mov     [rdi+8], edx
0x18002ac56  movss   dword ptr [rdi+10h], xmm0
0x18002ac5b  jmp     loc_18002B22F
0x18002ac60  mov     rcx, [rsi+10h]; __int64
0x18002ac64  lea     rdx, [rsp+2A8h+var_278]; __int16 *
0x18002ac69  mov     [rsp+2A8h+var_278], r12w
0x18002ac6f  call    ?LongLongToShort@@YAJ_JPEAF@Z; LongLongToShort(__int64,short *)
0x18002ac74  test    eax, eax
0x18002ac76  jns     short loc_18002AC89
0x18002ac78  mov     rcx, [rsp+2A8h]; this
0x18002ac80  mov     r9d, eax; char *
0x18002ac83  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x18002ac89  movsx   rax, [rsp+2A8h+var_278]
0x18002ac8f  mov     byte ptr [rdi+0Bh], 7
0x18002ac93  jmp     loc_18002B22B
0x18002ac98  movsxd  rax, dword ptr [rsi+10h]
0x18002ac9c  and     edx, 0FFFFFFh
0x18002aca2  or      edx, 6000000h
0x18002aca8  jmp     short loc_18002AC3C
0x18002acaa  mov     r14b, [rsp+2A8h+arg_20]
0x18002acb2  mov     rsi, [rsi+10h]
0x18002acb6  test    r14b, r14b
0x18002acb9  jz      short loc_18002ACF7
0x18002acbb  mov     edx, 78h ; 'x'; unsigned __int64
0x18002acc0  mov     rcx, rbp; this
0x18002acc3  lea     r8d, [rdx-70h]; unsigned __int64
0x18002acc7  call    ?Alloc@CZoneHeap@@QEAAPEAE_K0@Z; CZoneHeap::Alloc(unsigned __int64,unsigned __int64)
0x18002accc  mov     edx, 1
0x18002acd1  mov     rcx, rax; this
0x18002acd4  call    ??0CWordNode@@QEAA@XZ; CWordNode::CWordNode(void)
0x18002acd9  mov     r8, rbp; struct CZoneHeap *
0x18002acdc  mov     byte ptr [rsp+2A8h+var_288], r14b; bool
0x18002ace1  mov     rcx, rax; this
0x18002ace4  mov     r9, r13; struct LSP::CNamespaces *
0x18002ace7  mov     rdx, rsi; struct CWordNode *
0x18002acea  mov     rbx, rax
0x18002aced  call    ?CopyFrom@CWordNode@@QEAAXPEBV1@AEAVCZoneHeap@@PEAVCNamespaces@LSP@@_N@Z; CWordNode::CopyFrom(CWordNode const *,CZoneHeap &,LSP::CNamespaces *,bool)
0x18002acf2  mov     edx, [rdi+8]
0x18002acf5  jmp     short loc_18002ACFA
0x18002acf7  mov     rbx, rsi
0x18002acfa  and     edx, 0FFFFFFh
0x18002ad00  bts     edx, 1Ah
0x18002ad04  mov     [rdi+8], edx
0x18002ad07  mov     [rdi+10h], rbx
0x18002ad0b  jmp     loc_18002B22F
0x18002ad10  mov     rbx, [rsi+10h]
0x18002ad14  test    rbx, rbx
0x18002ad17  jz      loc_18002B22F
0x18002ad1d  mov     rdx, rbp
0x18002ad20  mov     rcx, rdi
0x18002ad23  call    ?NewIntArray@CNodeProperty@@QEAAPEAV?$CArray@HV?$CArrayAllocator_GC@VCZoneHeap@@@@@@AEAVCZoneHeap@@@Z; CNodeProperty::NewIntArray(CZoneHeap &)
0x18002ad28  mov     rdx, rbx
0x18002ad2b  mov     rcx, rax
0x18002ad2e  call    ?CopyArray@?$CArray@HV?$CArrayAllocator_GC@VCZoneHeap@@@@@@QEAAXAEBV1@@Z; CArray<int,CArrayAllocator_GC<CZoneHeap>>::CopyArray(CArray<int,CArrayAllocator_GC<CZoneHeap>> const &)
0x18002ad33  jmp     loc_18002B22F
0x18002ad38  mov     rbx, [rsi+10h]
0x18002ad3c  test    rbx, rbx
0x18002ad3f  jz      loc_18002B22F
0x18002ad45  mov     r14b, [rsp+2A8h+arg_20]
0x18002ad4d  mov     rdx, rbp
0x18002ad50  mov     rcx, rdi
0x18002ad53  call    ?NewTokenArray@CNodeProperty@@QEAAPEAV?$CArray@PEAVCWordNode@@V?$CArrayAllocator_GC@VCZoneHeap@@@@@@AEAVCZoneHeap@@@Z; CNodeProperty::NewTokenArray(CZoneHeap &)
0x18002ad58  mov     rdi, rax
0x18002ad5b  test    r14b, r14b
0x18002ad5e  jz      loc_18002AE0D
0x18002ad64  mov     esi, r12d
0x18002ad67  cmp     [rbx+8], r12
0x18002ad6b  jle     loc_18002B22F
0x18002ad71  mov     r15d, 8
0x18002ad77  mov     r8, r15; unsigned __int64
0x18002ad7a  mov     edx, 78h ; 'x'; unsigned __int64
0x18002ad7f  mov     rcx, rbp; this
0x18002ad82  call    ?Alloc@CZoneHeap@@QEAAPEAE_K0@Z; CZoneHeap::Alloc(unsigned __int64,unsigned __int64)
0x18002ad87  mov     edx, 1
0x18002ad8c  mov     rcx, rax; this
0x18002ad8f  call    ??0CWordNode@@QEAA@XZ; CWordNode::CWordNode(void)
0x18002ad94  movsxd  rdx, esi
0x18002ad97  mov     rcx, rbx
0x18002ad9a  mov     r12, rax
0x18002ad9d  call    ?ElementAt@?$CArray@PEAVCTrieWalker@NLG@@VCArrayAllocator_malloc@@@@QEBAAEAPEAVCTrieWalker@NLG@@_J@Z; CArray<NLG::CTrieWalker *,CArrayAllocator_malloc>::ElementAt(__int64)
0x18002ada2  mov     r9, r13; struct LSP::CNamespaces *
0x18002ada5  mov     byte ptr [rsp+2A8h+var_288], r14b; bool
0x18002adaa  mov     r8, rbp; struct CZoneHeap *
0x18002adad  mov     rcx, r12; this
0x18002adb0  mov     rdx, [rax]; struct CWordNode *
0x18002adb3  call    ?CopyFrom@CWordNode@@QEAAXPEBV1@AEAVCZoneHeap@@PEAVCNamespaces@LSP@@_N@Z; CWordNode::CopyFrom(CWordNode const *,CZoneHeap &,LSP::CNamespaces *,bool)
0x18002adb8  mov     r9, [rdi+10h]
0x18002adbc  mov     r8, [rdi+8]
0x18002adc0  cmp     r8, r9
0x18002adc3  jl      short loc_18002ADEE
0x18002adc5  cmp     r8, r15
0x18002adc8  lea     rcx, [r8+1]
0x18002adcc  mov     rdx, r8
0x18002adcf  cmovl   rdx, r15
0x18002add3  add     rdx, r9
0x18002add6  cmp     rcx, rdx
0x18002add9  cmovge  rdx, rcx
0x18002addd  cmp     rdx, r9
0x18002ade0  jle     short loc_18002ADEE
0x18002ade2  mov     rcx, rdi
0x18002ade5  call    ?ReallocWorker@?$CArray@PEAVCWordNode@@V?$CArrayAllocator_GC@VCZoneHeap@@@@@@AEAAX_J@Z; CArray<CWordNode *,CArrayAllocator_GC<CZoneHeap>>::ReallocWorker(__int64)
0x18002adea  mov     r8, [rdi+8]
0x18002adee  mov     rax, [rdi]
0x18002adf1  inc     esi
0x18002adf3  mov     [rax+r8*8], r12
0x18002adf7  inc     qword ptr [rdi+8]
0x18002adfb  movsxd  rax, esi
0x18002adfe  cmp     rax, [rbx+8]
0x18002ae02  jl      loc_18002AD77
0x18002ae08  jmp     loc_18002B22F
0x18002ae0d  cmp     rax, rbx
0x18002ae10  jz      loc_18002B22F
0x18002ae16  mov     rdx, [rbx+8]
0x18002ae1a  mov     rcx, rdi
0x18002ae1d  call    ?SetArraySize@?$CArray@PEAVCWordNode@@V?$CArrayAllocator_GC@VCZoneHeap@@@@@@QEAAX_J@Z; CArray<CWordNode *,CArrayAllocator_GC<CZoneHeap>>::SetArraySize(__int64)
0x18002ae22  mov     rdx, r12
0x18002ae25  cmp     [rdi+8], r12
0x18002ae29  jle     loc_18002B22F
0x18002ae2f  mov     rax, [rbx]
0x18002ae32  mov     rcx, [rdi]
0x18002ae35  mov     rax, [rax+rdx*8]
0x18002ae39  mov     [rcx+rdx*8], rax
0x18002ae3d  inc     rdx
0x18002ae40  cmp     rdx, [rdi+8]
0x18002ae44  jl      short loc_18002AE2F
0x18002ae46  jmp     loc_18002B22F
0x18002ae4b  mov     r8, [rsi+10h]; unsigned __int16 *
0x18002ae4f  test    r8, r8
0x18002ae52  jz      loc_18002B22F
0x18002ae58  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002ae5c  inc     r9; unsigned __int64
0x18002ae5f  cmp     [r8+r9*2], r12w
0x18002ae64  jnz     short loc_18002AE5C
0x18002ae66  mov     rdx, rbp; struct CZoneHeap *
0x18002ae69  mov     rcx, rdi; this
0x18002ae6c  call    ?NewString@CNodeProperty@@QEAAPEBGAEAVCZoneHeap@@PEBG_K@Z; CNodeProperty::NewString(CZoneHeap &,ushort const *,unsigned __int64)
0x18002ae71  jmp     loc_18002B22F
0x18002ae76  sub     ecx, 0Bh
0x18002ae79  jz      loc_18002B222
0x18002ae7f  sub     ecx, 1
0x18002ae82  jz      loc_18002B205
0x18002ae88  sub     ecx, 1
0x18002ae8b  jz      loc_18002B12A
0x18002ae91  sub     ecx, 1
0x18002ae94  jz      loc_18002AF87
0x18002ae9a  sub     ecx, 1
0x18002ae9d  jz      loc_18002AF2B
0x18002aea3  sub     ecx, 1
0x18002aea6  jz      short loc_18002AECF
0x18002aea8  cmp     ecx, 1
0x18002aeab  jnz     loc_18002B22F
0x18002aeb1  mov     rax, [rsi+10h]
0x18002aeb5  test    rax, rax
0x18002aeb8  jz      loc_18002B22F
0x18002aebe  and     edx, 0FFFFFFh
0x18002aec4  or      edx, 11000000h
0x18002aeca  jmp     loc_18002AC3C
0x18002aecf  cmp     [rsi+10h], r12
0x18002aed3  jz      loc_18002B22F
0x18002aed9  mov     edx, 18h; unsigned __int64
0x18002aede  mov     rcx, rbp; this
0x18002aee1  lea     r8d, [rdx-10h]; unsigned __int64
0x18002aee5  call    ?Alloc@CZoneHeap@@QEAAPEAE_K0@Z; CZoneHeap::Alloc(unsigned __int64,unsigned __int64)
0x18002aeea  mov     cl, [rsp+2A8h+arg_20]
0x18002aef1  mov     r9, r13; struct LSP::CNamespaces *
0x18002aef4  mov     byte ptr [rsp+2A8h+var_288], cl; bool
0x18002aef8  mov     r8, rbp; struct CZoneHeap *
0x18002aefb  mov     rcx, rax; this
0x18002aefe  mov     rbx, rax
0x18002af01  mov     [rax], r12
0x18002af04  mov     rdx, [rsi+10h]
0x18002af08  mov     rdx, [rdx+8]; struct CNodeProperty *
0x18002af0c  call    ?CopyFrom@CNodeProperty@@QEAAXPEBV1@AEAVCZoneHeap@@PEAVCNamespaces@LSP@@_N@Z; CNodeProperty::CopyFrom(CNodeProperty const *,CZoneHeap &,LSP::CNamespaces *,bool)
0x18002af11  mov     r8, [rsi+10h]
0x18002af15  mov     r9, rbx
0x18002af18  mov     rdx, rbp
0x18002af1b  mov     rcx, rdi
0x18002af1e  mov     r8, [r8]
0x18002af21  call    ?NewGuidValue@CNodeProperty@@QEAAPEAV?$TNameValueProperty@U_GUID@@@@AEAVCZoneHeap@@PEBU_GUID@@PEBV1@@Z; CNodeProperty::NewGuidValue(CZoneHeap &,_GUID const *,CNodeProperty const *)
0x18002af26  jmp     loc_18002B22F
0x18002af2b  cmp     [rsi+10h], r12
0x18002af2f  jz      loc_18002B22F
0x18002af35  mov     edx, 18h; unsigned __int64
0x18002af3a  mov     rcx, rbp; this
0x18002af3d  lea     r8d, [rdx-10h]; unsigned __int64
0x18002af41  call    ?Alloc@CZoneHeap@@QEAAPEAE_K0@Z; CZoneHeap::Alloc(unsigned __int64,unsigned __int64)
0x18002af46  mov     cl, [rsp+2A8h+arg_20]
0x18002af4d  mov     r9, r13; struct LSP::CNamespaces *
0x18002af50  mov     byte ptr [rsp+2A8h+var_288], cl; bool
0x18002af54  mov     r8, rbp; struct CZoneHeap *
0x18002af57  mov     rcx, rax; this
0x18002af5a  mov     rbx, rax
0x18002af5d  mov     [rax], r12
0x18002af60  mov     rdx, [rsi+10h]
0x18002af64  mov     rdx, [rdx+8]; struct CNodeProperty *
0x18002af68  call    ?CopyFrom@CNodeProperty@@QEAAXPEBV1@AEAVCZoneHeap@@PEAVCNamespaces@LSP@@_N@Z; CNodeProperty::CopyFrom(CNodeProperty const *,CZoneHeap &,LSP::CNamespaces *,bool)
0x18002af6d  mov     r8, [rsi+10h]
0x18002af71  mov     r9, rbx
0x18002af74  mov     rdx, rbp
0x18002af77  mov     rcx, rdi
0x18002af7a  mov     r8, [r8]
0x18002af7d  call    ?NewNameValue@CNodeProperty@@QEAAPEAV?$TNameValueProperty@G@@AEAVCZoneHeap@@PEBGPEBV1@@Z; CNodeProperty::NewNameValue(CZoneHeap &,ushort const *,CNodeProperty const *)
0x18002af82  jmp     loc_18002B22F
0x18002af87  mov     r14, [rsi+10h]
0x18002af8b  test    r14, r14
0x18002af8e  jz      loc_18002B22F
0x18002af94  cmp     [rsp+2A8h+arg_20], r12b
0x18002af9c  jz      loc_18002B0CE
0x18002afa2  test    r13, r13
0x18002afa5  jz      loc_18002B0CE
0x18002afab  mov     rdx, rbp
0x18002afae  mov     rcx, rdi
0x18002afb1  call    ?NewNameArray@CNodeProperty@@QEAAPEAV?$CArray@VCName@LSP@@V?$CArrayAllocator_GC@VCZoneHeap@@@@@@AEAVCZoneHeap@@@Z; CNodeProperty::NewNameArray(CZoneHeap &)
0x18002afb6  mov     rsi, rax
0x18002afb9  mov     ebp, r12d
0x18002afbc  cmp     [r14+8], r12
0x18002afc0  jle     loc_18002B22F
0x18002afc6  mov     r15d, 8
0x18002afcc  movsxd  r12, ebp
0x18002afcf  mov     rcx, r14
0x18002afd2  mov     rdx, r12
0x18002afd5  call    ?ElementAt@?$CArray@VCName@LSP@@V?$CArrayAllocator_GC@VCZoneHeap@@@@@@QEBAAEAVCName@LSP@@_J@Z; CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::ElementAt(__int64)
0x18002afda  mov     rcx, rax; this
0x18002afdd  call    ?IsFixedNamespace@CName@LSP@@QEBA_NXZ; LSP::CName::IsFixedNamespace(void)
0x18002afe2  mov     rdx, r12
0x18002afe5  mov     rcx, r14
0x18002afe8  test    al, al
0x18002afea  jz      short loc_18002B040
0x18002afec  call    ?ElementAt@?$CArray@VCName@LSP@@V?$CArrayAllocator_GC@VCZoneHeap@@@@@@QEBAAEAVCName@LSP@@_J@Z; CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::ElementAt(__int64)
0x18002aff1  mov     r9, [rsi+10h]
0x18002aff5  mov     r8, [rsi+8]
0x18002aff9  mov     rbx, [r13+8]
0x18002affd  mov     rdi, [rax+8]
0x18002b001  cmp     r8, r9
0x18002b004  jl      short loc_18002B02F
0x18002b006  cmp     r8, r15
0x18002b009  lea     rcx, [r8+1]
0x18002b00d  mov     rdx, r8
0x18002b010  cmovl   rdx, r15
0x18002b014  add     rdx, r9
0x18002b017  cmp     rcx, rdx
0x18002b01a  cmovge  rdx, rcx
0x18002b01e  cmp     rdx, r9
0x18002b021  jle     short loc_18002B02F
0x18002b023  mov     rcx, rsi
0x18002b026  call    ?ReallocWorker@?$CArray@VCName@LSP@@V?$CArrayAllocator_GC@VCZoneHeap@@@@@@AEAAX_J@Z; CArray<LSP::CName,CArrayAllocator_GC<CZoneHeap>>::ReallocWorker(__int64)
0x18002b02b  mov     r8, [rsi+8]
0x18002b02f  mov     rax, [rsi]
0x18002b032  add     r8, r8
0x18002b035  mov     [rax+r8*8], rbx
0x18002b039  mov     [rax+r8*8+8], rdi
  ... truncated ...
```
