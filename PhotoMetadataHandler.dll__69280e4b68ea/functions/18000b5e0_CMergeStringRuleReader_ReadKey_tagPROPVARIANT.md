# CMergeStringRuleReader::ReadKey(tagPROPVARIANT *)

- ea: `0x18000b5e0`
- end: `0x18000b905`
- name: `?ReadKey@CMergeStringRuleReader@@UEAAJPEAUtagPROPVARIANT@@@Z`
- size: `805`
- prototype: `__int64 __fastcall(CMergeStringRuleReader *__hidden this, struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x18000b5e0`
- `0x18000b90c`
- `0x18000bbe8`
- `0x18000bddc`
- `0x18000c048`
- `0x18000c1cc`
- `0x18000c458`
- `0x18000c49c`
- `0x1800147f8`
- `0x1800215a8`
- `0x180029010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b6e3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b83f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b8a0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b6e3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b83f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000b8a0`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000b87e`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000b87e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b76d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000b76d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMergeStringRuleReader::ReadKey(CMergeStringRuleReader *this, struct tagPROPVARIANT *a2, __int64 a3)
{
  VARTYPE vt; // ax
  char *v5; // r14
  unsigned __int64 v6; // r15
  unsigned int v7; // ebx
  char *v8; // rbx
  unsigned __int64 v9; // rdi
  unsigned __int64 v10; // r12
  LONG lVal; // esi
  LONG i; // r13d
  char v13; // r12
  int v14; // r13d
  int StringInStringArray; // eax
  int v16; // esi
  void *v17; // rbx
  __int64 v19; // r8
  unsigned __int64 v20; // rax
  __int64 v21; // [rsp+20h] [rbp-49h]
  PROPVARIANT pvar; // [rsp+28h] [rbp-41h] BYREF
  void *Block; // [rsp+40h] [rbp-29h] BYREF
  __int64 v24; // [rsp+48h] [rbp-21h]
  unsigned __int64 v25; // [rsp+50h] [rbp-19h]
  int v26; // [rsp+58h] [rbp-11h]
  char *v27; // [rsp+60h] [rbp-9h] BYREF
  unsigned __int64 v28; // [rsp+68h] [rbp-1h]
  __int64 v29; // [rsp+70h] [rbp+7h]
  int v30; // [rsp+78h] [rbp+Fh]
  void (__fastcall ***v31)(_QWORD, __int64); // [rsp+D0h] [rbp+67h] BYREF
  PROPVARIANT *pvarDest; // [rsp+D8h] [rbp+6Fh]
  __int64 v33; // [rsp+E0h] [rbp+77h] BYREF
  unsigned __int64 v34; // [rsp+E8h] [rbp+7Fh]

  pvarDest = a2;
  v31 = 0;
  *(_OWORD *)&a2->vt = 0;
  a2->bstrblobVal.pData = 0;
  memset(&pvar, 0, sizeof(pvar));
  vt = 4127;
  pvar.vt = 4127;
  v5 = 0;
  v27 = 0;
  v6 = 0;
  v28 = 0;
  v29 = 0;
  v30 = 0;
  v7 = 0;
  if ( !*((_DWORD *)this + 6) )
  {
LABEL_7:
    v8 = 0;
    Block = 0;
    v9 = 0;
    v24 = 0;
    v10 = 0;
    v25 = 0;
    v26 = 0;
    if ( vt == 4127 )
    {
      lVal = pvar.lVal;
      for ( i = 0; i < lVal; ++i )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v33,
          *(_QWORD *)&pvar.bstrblobVal.pData[8 * i],
          a3);
        v21 = v33;
        v20 = v9;
        v34 = v9;
        if ( v9 >= v10 )
        {
          if ( !(unsigned __int8)ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::GrowBuffer(
                                   &Block,
                                   v9 + 1) )
            ATL::AtlThrowImpl(-2147024882);
          v10 = v25;
          v9 = v24;
          v8 = (char *)Block;
          v20 = v34;
        }
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v8[8 * v20],
          v21,
          v19);
        v24 = ++v9;
        ATL::CStringData::Release((ATL::CStringData *)(v33 - 24));
      }
    }
    v13 = 0;
    v14 = 0;
    if ( (int)v6 > 0 )
    {
      do
      {
        if ( v14 >= v6 )
          ATL::AtlThrowImpl(-2147024809);
        StringInStringArray = FindStringInStringArray(&Block, &v5[8 * v14]);
        if ( StringInStringArray != -1 )
        {
          ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAt(
            &Block,
            StringInStringArray);
          v13 = 1;
        }
        ++v14;
      }
      while ( v14 < (int)v6 );
      if ( v13 )
      {
        v16 = ConvertStringArrayToPropVariantVector((__int64)&Block, &pvar);
        v17 = Block;
        if ( Block )
        {
          ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::CallDestructors(
            Block,
            v24);
          free(v17);
        }
        if ( v16 < 0 )
          goto LABEL_22;
LABEL_20:
        if ( pvar.lVal )
          v16 = PropVariantCopy(pvarDest, &pvar);
        else
          v16 = -2003292352;
        goto LABEL_22;
      }
      v9 = v24;
      v8 = (char *)Block;
    }
    if ( v8 )
    {
      ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::CallDestructors(
        v8,
        v9);
      free(v8);
    }
    goto LABEL_20;
  }
  while ( 1 )
  {
    if ( (*(int (__fastcall **)(CMergeStringRuleReader *, unsigned __int64, void (__fastcall ****)(_QWORD, __int64)))(*(_QWORD *)this + 48LL))(
           this,
           *((_QWORD *)this + 2) + ((unsigned __int64)v7 << 6),
           &v31) >= 0 )
    {
      v16 = CMergeStringRuleReader::MergeKeywords(v31 + 1, v31 + 4, &pvar, &v27);
      if ( v16 < 0 )
        break;
    }
    if ( v31 )
      (**v31)(v31, 1);
    v31 = 0;
    if ( ++v7 >= *((_DWORD *)this + 6) )
    {
      vt = pvar.vt;
      v6 = v28;
      v5 = v27;
      goto LABEL_7;
    }
  }
  v6 = v28;
  v5 = v27;
LABEL_22:
  if ( v31 )
    (**v31)(v31, 1);
  if ( v5 )
  {
    ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::CallDestructors(
      v5,
      v6);
    free(v5);
  }
  PropVariantClear(&pvar);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18000b5e0  mov     [rsp-8+pvarDest], rdx
0x18000b5e5  push    rbp
0x18000b5e6  push    rbx
0x18000b5e7  push    rsi
0x18000b5e8  push    rdi
0x18000b5e9  push    r12
0x18000b5eb  push    r13
0x18000b5ed  push    r14
0x18000b5ef  push    r15
0x18000b5f1  lea     rbp, [rsp-1Fh]
0x18000b5f6  sub     rsp, 88h
0x18000b5fd  mov     rdi, rcx
0x18000b600  xor     esi, esi
0x18000b602  mov     [rbp+57h+arg_0], rsi
0x18000b606  xorps   xmm0, xmm0
0x18000b609  xor     ecx, ecx
0x18000b60b  movups  xmmword ptr [rdx], xmm0
0x18000b60e  mov     [rdx+10h], rcx
0x18000b612  xor     eax, eax
0x18000b614  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x18000b618  mov     qword ptr [rbp+57h+pvar+10h], rax
0x18000b61c  mov     r13d, 101Fh
0x18000b622  movzx   eax, r13w
0x18000b626  mov     word ptr [rbp+57h+pvar], ax
0x18000b62a  mov     r14d, esi
0x18000b62d  mov     [rbp+57h+var_60], rsi
0x18000b631  mov     r15d, esi
0x18000b634  mov     [rbp+57h+var_58], rsi
0x18000b638  mov     [rbp+57h+var_50], rsi
0x18000b63c  mov     [rbp+57h+var_48], esi
0x18000b63f  mov     ebx, esi
0x18000b641  cmp     [rdi+18h], ebx
0x18000b644  jbe     short loc_18000B699
0x18000b646  nop     word ptr [rax+rax+00000000h]
0x18000b650  mov     rax, [rdi]
0x18000b653  mov     edx, ebx
0x18000b655  shl     rdx, 6
0x18000b659  add     rdx, [rdi+10h]
0x18000b65d  lea     r8, [rbp+57h+arg_0]
0x18000b661  mov     rcx, rdi
0x18000b664  mov     rax, [rax+30h]
0x18000b668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b66d  test    eax, eax
0x18000b66f  jns     loc_18000B7EC
0x18000b675  mov     rcx, [rbp+57h+arg_0]
0x18000b679  test    rcx, rcx
0x18000b67c  jnz     loc_18000B81C
0x18000b682  mov     [rbp+57h+arg_0], rsi
0x18000b686  inc     ebx
0x18000b688  cmp     ebx, [rdi+18h]
0x18000b68b  jb      short loc_18000B650
0x18000b68d  movzx   eax, word ptr [rbp+57h+pvar]
0x18000b691  mov     r15, [rbp+57h+var_58]
0x18000b695  mov     r14, [rbp+57h+var_60]
0x18000b699  mov     rbx, rsi
0x18000b69c  mov     [rbp+57h+Block], rbx
0x18000b6a0  mov     rdi, rsi
0x18000b6a3  mov     [rbp+57h+var_78], rsi
0x18000b6a7  mov     r12, rsi
0x18000b6aa  mov     [rbp+57h+var_70], rsi
0x18000b6ae  mov     [rbp+57h+var_68], esi
0x18000b6b1  cmp     ax, r13w
0x18000b6b5  jnz     short loc_18000B6C5
0x18000b6b7  mov     esi, dword ptr [rbp+57h+pvar+8]
0x18000b6ba  xor     r13d, r13d
0x18000b6bd  test    esi, esi
0x18000b6bf  jg      loc_18000B790
0x18000b6c5  xor     r12b, r12b
0x18000b6c8  xor     r13d, r13d
0x18000b6cb  test    r15d, r15d
0x18000b6ce  jg      short loc_18000B6F1
0x18000b6d0  test    rbx, rbx
0x18000b6d3  jz      short loc_18000B744
0x18000b6d5  mov     rdx, rdi
0x18000b6d8  mov     rcx, rbx
0x18000b6db  call    ?CallDestructors@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@CAXPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CallDestructors(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,unsigned __int64)
0x18000b6e0  mov     rcx, rbx; Block
0x18000b6e3  call    cs:__imp_free
0x18000b6ea  nop     dword ptr [rax+rax+00h]
0x18000b6ef  jmp     short loc_18000B744
0x18000b6f1  movsxd  rax, r13d
0x18000b6f4  cmp     rax, r15
0x18000b6f7  jnb     loc_18000B8E4
0x18000b6fd  lea     rdx, [r14+rax*8]
0x18000b701  lea     rcx, [rbp+57h+Block]
0x18000b705  call    ?FindStringInStringArray@@YAHAEBV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@@Z; FindStringInStringArray(ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000b70a  cmp     eax, 0FFFFFFFFh
0x18000b70d  jnz     loc_18000B8C3
0x18000b713  inc     r13d
0x18000b716  cmp     r13d, r15d
0x18000b719  jl      short loc_18000B6F1
0x18000b71b  test    r12b, r12b
0x18000b71e  jz      loc_18000B8D7
0x18000b724  lea     rdx, [rbp+57h+pvar]
0x18000b728  lea     rcx, [rbp+57h+Block]
0x18000b72c  call    ?ConvertStringArrayToPropVariantVector@@YAJAEBV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@PEAUtagPROPVARIANT@@@Z; ConvertStringArrayToPropVariantVector(ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,tagPROPVARIANT *)
0x18000b731  mov     esi, eax
0x18000b733  mov     rbx, [rbp+57h+Block]
0x18000b737  test    rbx, rbx
0x18000b73a  jnz     loc_18000B891
0x18000b740  test    esi, esi
0x18000b742  js      short loc_18000B753
0x18000b744  cmp     dword ptr [rbp+57h+pvar+8], 0
0x18000b748  ja      loc_18000B876
0x18000b74e  mov     esi, 88982F40h
0x18000b753  mov     rcx, [rbp+57h+arg_0]
0x18000b757  test    rcx, rcx
0x18000b75a  jnz     loc_18000B8EF
0x18000b760  test    r14, r14
0x18000b763  jnz     loc_18000B831
0x18000b769  lea     rcx, [rbp+57h+pvar]; pvar
0x18000b76d  call    cs:__imp_PropVariantClear
0x18000b774  nop     dword ptr [rax+rax+00h]
0x18000b779  mov     eax, esi
0x18000b77b  add     rsp, 88h
0x18000b782  pop     r15
0x18000b784  pop     r14
0x18000b786  pop     r13
0x18000b788  pop     r12
0x18000b78a  pop     rdi
0x18000b78b  pop     rsi
0x18000b78c  pop     rbx
0x18000b78d  pop     rbp
0x18000b78e  retn
0x18000b790  movsxd  rax, r13d
0x18000b793  mov     rdx, qword ptr [rbp+57h+pvar+10h]
0x18000b797  mov     rdx, [rdx+rax*8]
0x18000b79b  lea     rcx, [rbp+57h+arg_10]
0x18000b79f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000b7a4  nop
0x18000b7a5  mov     rax, [rbp+57h+arg_10]
0x18000b7a9  mov     [rbp+57h+var_A0], rax
0x18000b7ad  mov     rax, rdi
0x18000b7b0  mov     [rbp+57h+arg_18], rax
0x18000b7b4  cmp     rdi, r12
0x18000b7b7  jnb     loc_18000B850
0x18000b7bd  lea     rcx, [rbx+rax*8]
0x18000b7c1  mov     rdx, [rbp+57h+var_A0]
0x18000b7c5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000b7ca  inc     rdi
0x18000b7cd  mov     [rbp+57h+var_78], rdi
0x18000b7d1  mov     rcx, [rbp+57h+arg_10]
0x18000b7d5  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000b7d9  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000b7de  inc     r13d
0x18000b7e1  cmp     r13d, esi
0x18000b7e4  jge     loc_18000B6C5
0x18000b7ea  jmp     short loc_18000B790
0x18000b7ec  mov     rcx, [rbp+57h+arg_0]
0x18000b7f0  lea     rdx, [rcx+20h]
0x18000b7f4  add     rcx, 8
0x18000b7f8  lea     r9, [rbp+57h+var_60]
0x18000b7fc  lea     r8, [rbp+57h+pvar]
0x18000b800  call    ?MergeKeywords@CMergeStringRuleReader@@CAJAEBUtagPROPVARIANT@@0PEAU2@PEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; CMergeStringRuleReader::MergeKeywords(tagPROPVARIANT const &,tagPROPVARIANT const &,tagPROPVARIANT *,ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *)
0x18000b805  mov     esi, eax
0x18000b807  test    eax, eax
0x18000b809  jns     loc_18000B8B1
0x18000b80f  mov     r15, [rbp+57h+var_58]
0x18000b813  mov     r14, [rbp+57h+var_60]
0x18000b817  jmp     loc_18000B753
0x18000b81c  mov     rax, [rcx]
0x18000b81f  mov     edx, 1
0x18000b824  mov     rax, [rax]
0x18000b827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b82c  jmp     loc_18000B682
0x18000b831  mov     rdx, r15
0x18000b834  mov     rcx, r14
0x18000b837  call    ?CallDestructors@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@CAXPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CallDestructors(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,unsigned __int64)
0x18000b83c  mov     rcx, r14; Block
0x18000b83f  call    cs:__imp_free
0x18000b846  nop     dword ptr [rax+rax+00h]
0x18000b84b  jmp     loc_18000B769
0x18000b850  lea     rdx, [rdi+1]
0x18000b854  lea     rcx, [rbp+57h+Block]
0x18000b858  call    ?GrowBuffer@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::GrowBuffer(unsigned __int64)
0x18000b85d  test    al, al
0x18000b85f  jz      short loc_18000B8B8
0x18000b861  mov     r12, [rbp+57h+var_70]
0x18000b865  mov     rdi, [rbp+57h+var_78]
0x18000b869  mov     rbx, [rbp+57h+Block]
0x18000b86d  mov     rax, [rbp+57h+arg_18]
0x18000b871  jmp     loc_18000B7BD
0x18000b876  lea     rdx, [rbp+57h+pvar]; pvarSrc
0x18000b87a  mov     rcx, [rbp+57h+pvarDest]; pvarDest
0x18000b87e  call    cs:__imp_PropVariantCopy
0x18000b885  nop     dword ptr [rax+rax+00h]
0x18000b88a  mov     esi, eax
0x18000b88c  jmp     loc_18000B753
0x18000b891  mov     rdx, [rbp+57h+var_78]
0x18000b895  mov     rcx, rbx
0x18000b898  call    ?CallDestructors@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@CAXPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CallDestructors(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,unsigned __int64)
0x18000b89d  mov     rcx, rbx; Block
0x18000b8a0  call    cs:__imp_free
0x18000b8a7  nop     dword ptr [rax+rax+00h]
0x18000b8ac  jmp     loc_18000B740
0x18000b8b1  xor     esi, esi
0x18000b8b3  jmp     loc_18000B675
0x18000b8b8  mov     ecx, 8007000Eh; int
0x18000b8bd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000b8c3  movsxd  rdx, eax
0x18000b8c6  lea     rcx, [rbp+57h+Block]
0x18000b8ca  call    ?RemoveAt@?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAX_K0@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAt(unsigned __int64,unsigned __int64)
0x18000b8cf  mov     r12b, 1
0x18000b8d2  jmp     loc_18000B713
0x18000b8d7  mov     rdi, [rbp+57h+var_78]
0x18000b8db  mov     rbx, [rbp+57h+Block]
0x18000b8df  jmp     loc_18000B6D0
0x18000b8e4  mov     ecx, 80070057h; int
0x18000b8e9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000b8ef  mov     rax, [rcx]
0x18000b8f2  mov     edx, 1
0x18000b8f7  mov     rax, [rax]
0x18000b8fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8ff  jmp     loc_18000B760
```
