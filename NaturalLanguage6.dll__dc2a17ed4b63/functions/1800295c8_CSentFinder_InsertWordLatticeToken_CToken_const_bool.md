# CSentFinder::InsertWordLatticeToken(CToken const &,bool)

- ea: `0x1800295c8`
- end: `0x1800299fc`
- name: `?InsertWordLatticeToken@CSentFinder@@AEAAXAEBVCToken@@_N@Z`
- size: `1076`
- prototype: `void __fastcall(CSentFinder *__hidden this, const struct CToken *, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002924c`
- `0x1800295c8`

## callees

- `0x180008d70`
- `0x18000b1a0`
- `0x1800295c8`
- `0x18006055c`
- `0x180060860`
- `0x18009e2c2`
- `0x18009e300`
- `0x1800b0010`

## pseudocode

```c
void __fastcall CSentFinder::InsertWordLatticeToken(CSentFinder *this, const struct CToken *a2, char a3)
{
  int v3; // eax
  unsigned int v6; // esi
  bool v7; // r13
  __int64 v8; // r12
  unsigned int v9; // r14d
  __int64 v10; // r15
  __int64 v11; // rdx
  char v12; // si
  int v13; // edx
  int v14; // eax
  unsigned int v15; // ecx
  bool v16; // zf
  unsigned int v17; // ecx
  __int64 v18; // rcx
  __int64 v19; // rax
  CText *v20; // r15
  __int16 v21; // r12
  __int64 v22; // r13
  __int64 v23; // r14
  __int64 v24; // rdx
  int v25; // r14d
  int v26; // r15d
  unsigned __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rcx
  void (__fastcall *v30)(__int64, __int128 *, __int64 *); // rax
  __int64 v31; // rax
  int v32; // eax
  int v33; // edi
  struct CText::BufferedCommit *v34; // rbx
  __int64 v35; // rcx
  void (__fastcall *v36)(__int64, __int128 *, __int64 *); // rax
  unsigned int v37; // [rsp+60h] [rbp-29h]
  __int64 v38; // [rsp+70h] [rbp-19h] BYREF
  __int64 v39; // [rsp+78h] [rbp-11h]
  __int128 v40; // [rsp+80h] [rbp-9h] BYREF
  __int128 i; // [rsp+90h] [rbp+7h]

  v3 = *((_DWORD *)a2 + 2);
  *((_DWORD *)this + 74) = v3;
  v6 = *((_DWORD *)a2 + 4);
  v37 = v6;
  if ( a3 && v6 > 2 && ((unsigned int)(v3 - 5) <= 2 || (*((_BYTE *)a2 + 20) & 0x40) != 0) )
  {
    v7 = 1;
    v8 = *(_QWORD *)a2;
    v9 = 1;
    v10 = *((unsigned int *)a2 + 3);
    DWORD2(v40) = *((_DWORD *)a2 + 2);
    DWORD2(i) = *((_DWORD *)a2 + 6);
    v11 = v8 + 2 * v10;
    *(_QWORD *)&i = __PAIR64__(*((_DWORD *)a2 + 5) & 0xFFFFFFBF, v6);
    v12 = 0;
    *(_QWORD *)&v40 = v8;
    HIDWORD(v40) = v10;
    v38 = v11;
    do
    {
      if ( ((unsigned int)CMN_IsCharSpaceW(*(unsigned __int16 *)(v11 + 2LL * v9)) != 0) == v7 )
      {
        v13 = *((_DWORD *)a2 + 3) + v9 - v10;
        LODWORD(i) = v13;
        if ( v7 )
        {
          v14 = 3;
          v12 = 1;
          if ( *(_WORD *)(v8 + 2LL * (unsigned int)(v13 + v10 - 1)) == 46 )
            v14 = 5;
          DWORD2(v40) = v14;
        }
        else
        {
          DWORD2(v40) = 1;
        }
        CSentFinder::InsertWordLatticeToken(this, (const struct CToken *)&v40, 0);
        v8 = v40;
        LODWORD(v10) = v9 + *((_DWORD *)a2 + 3);
        HIDWORD(v40) = v10;
        v7 = !v7;
      }
      v15 = *((_DWORD *)a2 + 4);
      ++v9;
      v11 = v38;
    }
    while ( v9 < v15 );
    v16 = v12 == 0;
    v6 = v37;
    if ( !v16 )
    {
      v17 = *((_DWORD *)a2 + 3) + v15;
      LODWORD(i) = v17 - v10;
      v18 = *(unsigned __int16 *)(v8 + 2LL * (v17 - 1));
      if ( (_WORD)v18 == 46 )
        DWORD2(v40) = 5;
      else
        DWORD2(v40) = (unsigned int)CMN_IsCharSpaceW(v18) != 0 ? 1 : 3;
      CSentFinder::InsertWordLatticeToken(this, (const struct CToken *)&v40, 0);
      return;
    }
  }
  v19 = *((_QWORD *)this + 96);
  if ( !v19 )
    return;
  v20 = *(CText **)(v19 + 168);
  v21 = *(_WORD *)(v19 + 176);
  v22 = (unsigned int)(*((_DWORD *)a2 + 3) + *(_DWORD *)(v19 + 8));
  v23 = *((_QWORD *)v20 + 15);
  if ( *(_BYTE *)((*(__int64 (__fastcall **)(CText *))(*(_QWORD *)v20 + 152LL))(v20) + 279) )
  {
    if ( v6 > 1 )
    {
      v24 = (unsigned int)(*((_DWORD *)a2 + 4) - 1 + *((_DWORD *)a2 + 3));
      if ( *(_WORD *)(*(_QWORD *)a2 + 2 * v24) == 173 || *(_WORD *)(*(_QWORD *)a2 + 2 * v24) == 8209 )
      {
        v25 = v6 - 1;
        v26 = 0;
        v40 = 0;
        for ( i = 0; v25 >= 0; --v25 )
        {
          v27 = (unsigned int)v25 + (unsigned __int64)*((unsigned int *)a2 + 3);
          if ( *(_WORD *)(*(_QWORD *)a2 + 2 * v27) != 173 && *(_WORD *)(*(_QWORD *)a2 + 2 * v27) != 8209 )
            break;
          v28 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 96) + 168LL) + 288LL))(*(_QWORD *)(*((_QWORD *)this + 96) + 168LL));
          v29 = *((_QWORD *)this + 98);
          v38 = v28;
          v30 = *(void (__fastcall **)(__int64, __int128 *, __int64 *))(*(_QWORD *)v29 + 32LL);
          v39 = (unsigned int)(v25 + v22);
          v30(v29, &v40, &v38);
          ++v26;
        }
        v31 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 96) + 168LL) + 288LL))(*(_QWORD *)(*((_QWORD *)this + 96) + 168LL));
        goto LABEL_39;
      }
    }
  }
  if ( (v21 & 0x3FF) != 9 || !v23 || !*(_BYTE *)(*((_QWORD *)this + 96) + 45LL) )
  {
    v31 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*((_QWORD *)this + 96) + 168LL) + 288LL))(*(_QWORD *)(*((_QWORD *)this + 96) + 168LL));
    v40 = 0;
    i = 0;
LABEL_39:
    v35 = *((_QWORD *)this + 98);
    v38 = v31;
    v36 = *(void (__fastcall **)(__int64, __int128 *, __int64 *))(*(_QWORD *)v35 + 32LL);
    v39 = (unsigned int)v22;
    v36(v35, &v40, &v38);
    return;
  }
  if ( v6 )
  {
    v32 = *((_DWORD *)this + 74);
    if ( v32 != 1 && v32 != 16 )
    {
      v33 = **(_DWORD **)(v23 + 16);
      if ( CText::get_IsFlushNeeded(v20) )
        (**(void (__fastcall ***)(__int64))v23)(v23);
      v34 = CText::NewBufferedCommit(v20);
      memset_0(v34, 0, 0x40u);
      *((_DWORD *)v34 + 2) = v6;
      *((_DWORD *)v34 + 1) = v33 + v22;
      *((_QWORD *)v34 + 3) = &CText::GetText(v20)[v22];
    }
  }
}

```

## disassembly

```asm
0x1800295c8  mov     [rsp-8+arg_10], rbx
0x1800295cd  push    rbp
0x1800295ce  push    rsi
0x1800295cf  push    rdi
0x1800295d0  push    r12
0x1800295d2  push    r13
0x1800295d4  push    r14
0x1800295d6  push    r15
0x1800295d8  lea     rbp, [rsp-27h]
0x1800295dd  sub     rsp, 0B0h
0x1800295e4  mov     rax, cs:__security_cookie
0x1800295eb  xor     rax, rsp
0x1800295ee  mov     [rbp+57h+var_40], rax
0x1800295f2  mov     eax, [rdx+8]
0x1800295f5  mov     rbx, rdx
0x1800295f8  mov     [rcx+128h], eax
0x1800295fe  mov     rdi, rcx
0x180029601  mov     esi, [rdx+10h]
0x180029604  mov     [rbp+57h+var_80], esi
0x180029607  test    r8b, r8b
0x18002960a  jz      loc_180029740
0x180029610  cmp     esi, 2
0x180029613  jbe     loc_180029740
0x180029619  add     eax, 0FFFFFFFBh
0x18002961c  cmp     eax, 2
0x18002961f  jbe     short loc_18002962B
0x180029621  test    byte ptr [rdx+14h], 40h
0x180029625  jz      loc_180029740
0x18002962b  mov     eax, [rdx+8]
0x18002962e  mov     r13b, 1
0x180029631  mov     r12, [rdx]
0x180029634  mov     r14d, 1
0x18002963a  mov     r15d, [rdx+0Ch]
0x18002963e  mov     dword ptr [rbp+57h+var_60+8], eax
0x180029641  mov     eax, [rdx+18h]
0x180029644  mov     dword ptr [rbp+57h+var_50+8], eax
0x180029647  mov     eax, [rbx+14h]
0x18002964a  lea     rdx, [r12+r15*2]
0x18002964e  and     eax, 0FFFFFFBFh
0x180029651  mov     dword ptr [rbp+57h+var_50], esi
0x180029654  mov     dword ptr [rbp+57h+var_50+4], eax
0x180029657  xor     sil, sil
0x18002965a  mov     qword ptr [rbp+57h+var_60], r12
0x18002965e  mov     dword ptr [rbp+57h+var_60+0Ch], r15d
0x180029662  mov     [rbp+57h+var_70], rdx
0x180029666  mov     ecx, r14d
0x180029669  movzx   ecx, word ptr [rdx+rcx*2]
0x18002966d  call    CMN_IsCharSpaceW
0x180029672  xor     ecx, ecx
0x180029674  test    eax, eax
0x180029676  movzx   eax, r13b
0x18002967a  setnz   cl
0x18002967d  cmp     ecx, eax
0x18002967f  jnz     short loc_1800296DD
0x180029681  mov     edx, r14d
0x180029684  sub     edx, r15d
0x180029687  add     edx, [rbx+0Ch]
0x18002968a  mov     dword ptr [rbp+57h+var_50], edx
0x18002968d  test    r13b, r13b
0x180029690  jz      short loc_1800296B1
0x180029692  lea     ecx, [r15-1]
0x180029696  mov     eax, 3
0x18002969b  add     ecx, edx
0x18002969d  mov     sil, 1
0x1800296a0  cmp     word ptr [r12+rcx*2], 2Eh ; '.'
0x1800296a6  lea     ecx, [rax+2]
0x1800296a9  cmovz   eax, ecx
0x1800296ac  mov     dword ptr [rbp+57h+var_60+8], eax
0x1800296af  jmp     short loc_1800296B8
0x1800296b1  mov     dword ptr [rbp+57h+var_60+8], 1
0x1800296b8  xor     r8d, r8d; bool
0x1800296bb  lea     rdx, [rbp+57h+var_60]; struct CToken *
0x1800296bf  mov     rcx, rdi; this
0x1800296c2  call    ?InsertWordLatticeToken@CSentFinder@@AEAAXAEBVCToken@@_N@Z; CSentFinder::InsertWordLatticeToken(CToken const &,bool)
0x1800296c7  mov     r15d, [rbx+0Ch]
0x1800296cb  mov     r12, qword ptr [rbp+57h+var_60]
0x1800296cf  add     r15d, r14d
0x1800296d2  test    r13b, r13b
0x1800296d5  mov     dword ptr [rbp+57h+var_60+0Ch], r15d
0x1800296d9  setz    r13b
0x1800296dd  mov     ecx, [rbx+10h]
0x1800296e0  inc     r14d
0x1800296e3  mov     rdx, [rbp+57h+var_70]
0x1800296e7  cmp     r14d, ecx
0x1800296ea  jb      loc_180029666
0x1800296f0  test    sil, sil
0x1800296f3  mov     esi, [rbp+57h+var_80]
0x1800296f6  jz      short loc_180029740
0x1800296f8  add     ecx, [rbx+0Ch]
0x1800296fb  mov     eax, ecx
0x1800296fd  sub     eax, r15d
0x180029700  mov     dword ptr [rbp+57h+var_50], eax
0x180029703  lea     eax, [rcx-1]
0x180029706  movzx   ecx, word ptr [r12+rax*2]
0x18002970b  cmp     cx, 2Eh ; '.'
0x18002970f  jnz     short loc_18002971A
0x180029711  mov     dword ptr [rbp+57h+var_60+8], 5
0x180029718  jmp     short loc_18002972C
0x18002971a  call    CMN_IsCharSpaceW
0x18002971f  neg     eax
0x180029721  sbb     edx, edx
0x180029723  and     edx, 0FFFFFFFEh
0x180029726  add     edx, 3
0x180029729  mov     dword ptr [rbp+57h+var_60+8], edx
0x18002972c  xor     r8d, r8d; bool
0x18002972f  lea     rdx, [rbp+57h+var_60]; struct CToken *
0x180029733  mov     rcx, rdi; this
0x180029736  call    ?InsertWordLatticeToken@CSentFinder@@AEAAXAEBVCToken@@_N@Z; CSentFinder::InsertWordLatticeToken(CToken const &,bool)
0x18002973b  jmp     loc_1800299D5
0x180029740  mov     rax, [rdi+300h]
0x180029747  test    rax, rax
0x18002974a  jz      loc_1800299D5
0x180029750  mov     r15, [rax+0A8h]
0x180029757  mov     r13d, [rax+8]
0x18002975b  mov     rcx, r15
0x18002975e  movzx   r12d, word ptr [rax+0B0h]
0x180029766  add     r13d, [rbx+0Ch]
0x18002976a  mov     rax, [r15]
0x18002976d  mov     r14, [r15+78h]
0x180029771  mov     rax, [rax+98h]
0x180029778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002977d  cmp     byte ptr [rax+117h], 0
0x180029784  jz      loc_1800298AC
0x18002978a  cmp     esi, 1
0x18002978d  jbe     loc_1800298AC
0x180029793  mov     edx, [rbx+0Ch]
0x180029796  mov     r8d, 0ADh
0x18002979c  mov     ecx, [rbx+10h]
0x18002979f  mov     rax, [rbx]
0x1800297a2  dec     ecx
0x1800297a4  add     edx, ecx
0x1800297a6  mov     ecx, 2011h
0x1800297ab  cmp     [rax+rdx*2], r8w
0x1800297b0  jz      short loc_1800297BC
0x1800297b2  cmp     [rax+rdx*2], cx
0x1800297b6  jnz     loc_1800298AC
0x1800297bc  xorps   xmm0, xmm0
0x1800297bf  lea     r14d, [rsi-1]
0x1800297c3  xor     r15d, r15d
0x1800297c6  xor     r12d, r12d
0x1800297c9  movups  [rbp+57h+var_60], xmm0
0x1800297cd  movups  [rbp+57h+var_50], xmm0
0x1800297d1  test    r14d, r14d
0x1800297d4  js      loc_180029887
0x1800297da  mov     esi, ecx
0x1800297dc  mov     ecx, [rbx+0Ch]
0x1800297df  mov     eax, r14d
0x1800297e2  add     rcx, rax
0x1800297e5  mov     rax, [rbx]
0x1800297e8  cmp     [rax+rcx*2], r8w
0x1800297ed  jz      short loc_1800297F9
0x1800297ef  cmp     [rax+rcx*2], si
0x1800297f3  jnz     loc_180029884
0x1800297f9  mov     rax, [rdi+300h]
0x180029800  mov     rcx, [rax+0A8h]
0x180029807  mov     rax, [rcx]
0x18002980a  mov     rax, [rax+120h]
0x180029811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029816  cmp     [rdi+14h], r12d
0x18002981a  lea     r9d, [r14+r13]
0x18002981e  mov     rcx, [rdi+310h]
0x180029825  lea     r8, [rbp+57h+var_70]
0x180029829  setz    dl
0x18002982c  mov     [rbp+57h+var_70], rax
0x180029830  mov     [rsp+0E0h+var_90], dl
0x180029834  mov     edx, 1
0x180029839  mov     [rsp+0E0h+var_98], r12d
0x18002983e  mov     rax, [rcx]
0x180029841  mov     [rsp+0E0h+var_A0], 3
0x180029849  mov     [rsp+0E0h+var_A8], r12d
0x18002984e  mov     [rsp+0E0h+var_B0], 20h ; ' '
0x180029856  mov     rax, [rax+20h]
0x18002985a  mov     [rsp+0E0h+var_B8], rdx
0x18002985f  mov     [rsp+0E0h+var_C0], rdx
0x180029864  lea     rdx, [rbp+57h+var_60]
0x180029868  mov     [rbp+57h+var_68], r9
0x18002986c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029871  inc     r15d
0x180029874  mov     r8d, 0ADh
0x18002987a  sub     r14d, 1
0x18002987e  jns     loc_1800297DC
0x180029884  mov     esi, [rbp+57h+var_80]
0x180029887  mov     rax, [rdi+300h]
0x18002988e  mov     rcx, [rax+0A8h]
0x180029895  mov     rax, [rcx]
0x180029898  mov     rax, [rax+120h]
0x18002989f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298a4  sub     esi, r15d
0x1800298a7  jmp     loc_180029979
0x1800298ac  mov     eax, 3FFh
0x1800298b1  and     r12w, ax
0x1800298b5  cmp     r12w, 9
0x1800298ba  jnz     loc_18002994E
0x1800298c0  test    r14, r14
0x1800298c3  jz      loc_18002994E
0x1800298c9  mov     rax, [rdi+300h]
0x1800298d0  cmp     byte ptr [rax+2Dh], 0
0x1800298d4  jz      short loc_18002994E
0x1800298d6  test    esi, esi
0x1800298d8  jz      loc_1800299D5
0x1800298de  mov     eax, [rdi+128h]
0x1800298e4  cmp     eax, 1
0x1800298e7  jz      loc_1800299D5
0x1800298ed  cmp     eax, 10h
0x1800298f0  jz      loc_1800299D5
0x1800298f6  mov     rax, [r14+10h]
0x1800298fa  mov     rcx, r15; this
0x1800298fd  mov     edi, [rax]
0x1800298ff  call    ?get_IsFlushNeeded@CText@@QEBA_NXZ; CText::get_IsFlushNeeded(void)
0x180029904  test    al, al
0x180029906  jz      short loc_180029916
0x180029908  mov     rax, [r14]
0x18002990b  mov     rcx, r14
0x18002990e  mov     rax, [rax]
0x180029911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029916  mov     rcx, r15; this
0x180029919  call    ?NewBufferedCommit@CText@@QEAAPEAUBufferedCommit@1@XZ; CText::NewBufferedCommit(void)
0x18002991e  xor     edx, edx; Val
0x180029920  mov     rcx, rax; void *
0x180029923  mov     rbx, rax
0x180029926  lea     r8d, [rdx+40h]; Size
0x18002992a  call    memset_0
0x18002992f  lea     edx, [rdi+r13]
0x180029933  mov     [rbx+8], esi
0x180029936  mov     rcx, r15; this
0x180029939  mov     [rbx+4], edx
0x18002993c  call    ?GetText@CText@@QEAAPEBGXZ; CText::GetText(void)
0x180029941  lea     rdx, [rax+r13*2]
0x180029945  mov     [rbx+18h], rdx
0x180029949  jmp     loc_1800299D5
0x18002994e  mov     rax, [rdi+300h]
0x180029955  mov     rcx, [rax+0A8h]
0x18002995c  mov     rax, [rcx]
0x18002995f  mov     rax, [rax+120h]
0x180029966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002996b  xorps   xmm0, xmm0
0x18002996e  xor     r12d, r12d
0x180029971  movups  [rbp+57h+var_60], xmm0
0x180029975  movups  [rbp+57h+var_50], xmm0
0x180029979  cmp     [rdi+14h], r12d
0x18002997d  mov     rcx, [rdi+310h]
0x180029984  setz    dl
0x180029987  mov     [rbp+57h+var_70], rax
0x18002998b  mov     [rsp+0E0h+var_90], dl
0x18002998f  mov     edx, [rbx+14h]
0x180029992  mov     rax, [rcx]
0x180029995  mov     [rsp+0E0h+var_98], edx
0x180029999  mov     edx, [rdi+128h]
0x18002999f  mov     [rsp+0E0h+var_A0], 3
0x1800299a7  mov     rax, [rax+20h]
0x1800299ab  mov     [rsp+0E0h+var_A8], r12d
0x1800299b0  mov     [rsp+0E0h+var_B0], edx
0x1800299b4  lea     rdx, [rbp+57h+var_60]
0x1800299b8  mov     r8d, esi
0x1800299bb  mov     [rsp+0E0h+var_B8], r8
0x1800299c0  mov     [rsp+0E0h+var_C0], r8
0x1800299c5  lea     r8, [rbp+57h+var_70]
0x1800299c9  mov     r9d, r13d
0x1800299cc  mov     [rbp+57h+var_68], r9
0x1800299d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299d5  mov     rcx, [rbp+57h+var_40]
0x1800299d9  xor     rcx, rsp; StackCookie
0x1800299dc  call    __security_check_cookie
0x1800299e1  mov     rbx, [rsp+0E0h+arg_10]
0x1800299e9  add     rsp, 0B0h
0x1800299f0  pop     r15
0x1800299f2  pop     r14
0x1800299f4  pop     r13
0x1800299f6  pop     r12
0x1800299f8  pop     rdi
0x1800299f9  pop     rsi
0x1800299fa  pop     rbp
0x1800299fb  retn
```
