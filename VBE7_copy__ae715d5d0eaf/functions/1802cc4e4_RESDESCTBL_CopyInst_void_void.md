# RESDESCTBL::CopyInst(void *,void *)

- ea: `0x1802cc4e4`
- end: `0x1802cc9f4`
- name: `?CopyInst@RESDESCTBL@@QEAAJPEAX0@Z`
- size: `1296`
- prototype: `__int64 __fastcall(RESDESCTBL *__hidden this, void *, void *)`
- caller_count: `3`
- callee_count: `17`
- tags: ``

## callers

- `0x1802cc4e4`
- `0x1802cd2bc`
- `0x18030f67c`

## callees

- `0x18011db78`
- `0x180172b48`
- `0x180191848`
- `0x180213c74`
- `0x180289f00`
- `0x1802cbe38`
- `0x1802cbf10`
- `0x1802cbf34`
- `0x1802cbf48`
- `0x1802cbf5c`
- `0x1802cc150`
- `0x1802cc4e4`
- `0x1802cd324`
- `0x1802cd6dc`
- `0x1802cd6e8`
- `0x18030eb60`
- `0x18030f67c`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x1802cc655`
- `OLEAUT32!__imp_VariantCopy` at `0x1802cc655`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1802cc6dd`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1802cc6dd`
- `OLEAUT32!__imp_SafeArrayAllocDescriptor` at `0x1802cc76d`
- `OLEAUT32!__imp_SafeArrayAllocDescriptor` at `0x1802cc792`
- `OLEAUT32!__imp_SafeArrayAllocDescriptor` at `0x1802cc76d`
- `OLEAUT32!__imp_SafeArrayAllocDescriptor` at `0x1802cc792`
- `OLEAUT32!__imp_SafeArrayDestroyDescriptor` at `0x1802cc7a9`
- `OLEAUT32!__imp_SafeArrayDestroyDescriptor` at `0x1802cc944`
- `OLEAUT32!__imp_SafeArrayDestroyDescriptor` at `0x1802cc953`
- `OLEAUT32!__imp_SafeArrayDestroyDescriptor` at `0x1802cc7a9`
- `OLEAUT32!__imp_SafeArrayDestroyDescriptor` at `0x1802cc944`
- `OLEAUT32!__imp_SafeArrayDestroyDescriptor` at `0x1802cc953`

## pseudocode

```c
__int64 __fastcall RESDESCTBL::CopyInst(RESDESCTBL *this, char *a2, char *a3)
{
  int v4; // eax
  HRESULT v5; // [rsp+30h] [rbp-90h]
  HRESULT v6; // [rsp+30h] [rbp-90h]
  char v7[4]; // [rsp+34h] [rbp-8Ch] BYREF
  SAFEARRAY *ppsaOut; // [rsp+38h] [rbp-88h] BYREF
  SAFEARRAY *psa; // [rsp+40h] [rbp-80h] BYREF
  int v10; // [rsp+48h] [rbp-78h]
  EXFRAME *v11; // [rsp+50h] [rbp-70h]
  VARIANTARG *pvargDest; // [rsp+58h] [rbp-68h]
  UINT cDims; // [rsp+60h] [rbp-60h]
  VARIANTARG *pvargSrc; // [rsp+68h] [rbp-58h]
  unsigned int i; // [rsp+70h] [rbp-50h]
  struct tagSAFEARRAY *v16; // [rsp+78h] [rbp-48h]
  RESDESCTBL *OldRefLibIdRel; // [rsp+80h] [rbp-40h]
  _BYTE v18[8]; // [rsp+88h] [rbp-38h] BYREF
  __int64 v19; // [rsp+90h] [rbp-30h]
  _BYTE v20[8]; // [rsp+98h] [rbp-28h] BYREF
  unsigned __int64 v21; // [rsp+A0h] [rbp-20h]

  RESDESCFLAGS::RESDESCFLAGS((RESDESCFLAGS *)v7);
  ppsaOut = 0;
  OldRefLibIdRel = 0;
  if ( a2 == a3 )
    return 0;
  qmemcpy(a2, a3, *((unsigned int *)this + 1));
  v11 = RESDESCTBL::PresdescFirst(this);
  for ( i = 0; ; ++i )
  {
    if ( i >= *((unsigned __int16 *)this + 5) )
      return 0;
    pvargSrc = (VARIANTARG *)&a3[(unsigned int)MEMBER_DEFN::MemId(v11)];
    pvargDest = (VARIANTARG *)&a2[(unsigned int)MEMBER_DEFN::MemId(v11)];
    *(_WORD *)v7 = *(_WORD *)RESDESC::Rdflags(v11, v20);
    v10 = RESDESCFLAGS::Rdkind(v7);
    switch ( v10 )
    {
      case 1:
LABEL_12:
        v5 = CopyBstr(pvargDest, *(_QWORD *)&pvargSrc->vt);
        if ( v5 < 0 )
          goto LABEL_51;
        goto LABEL_49;
      case 2:
        if ( pvargDest->vt >= 8u )
        {
          pvargDest->vt = 0;
          v5 = VariantCopy(pvargDest, pvargSrc);
          if ( v5 < 0 )
            goto LABEL_51;
        }
        goto LABEL_49;
      case 3:
        v19 = *(_QWORD *)&pvargSrc->vt;
        if ( v19 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
        goto LABEL_49;
      case 4:
        goto LABEL_12;
    }
    if ( v10 != 5 )
    {
      if ( v10 == 9 && (v7[0] & 0x20) != 0 )
      {
        OldRefLibIdRel = (RESDESCTBL *)COldRefLibIdNode::GetOldRefLibIdRel(v11);
        v5 = RESDESCTBL::CopyInst(OldRefLibIdRel, pvargDest, pvargSrc);
        if ( v5 < 0 )
          goto LABEL_51;
      }
      goto LABEL_49;
    }
    if ( (v7[1] & 1) != 0 )
    {
      psa = *(SAFEARRAY **)&pvargSrc->vt;
      if ( psa )
      {
        if ( (psa->fFeatures & 0xE0) != 0 )
        {
          v6 = SafeArrayCopy(psa, (SAFEARRAY **)pvargDest);
          if ( v6 < 0 )
            return (unsigned int)v6;
          goto LABEL_49;
        }
        if ( (int)AllocArrayFromSrc(&ppsaOut, psa) < 0 )
        {
          v5 = -2147024882;
          goto LABEL_51;
        }
        *(_QWORD *)&pvargDest->vt = ppsaOut;
      }
      goto LABEL_39;
    }
    v16 = RESDESC::Psa(v11);
    cDims = v16->cDims;
    if ( v7[0] < 0 )
      break;
    ppsaOut = (SAFEARRAY *)pvargDest;
    psa = (SAFEARRAY *)pvargSrc;
LABEL_39:
    if ( (*(_BYTE *)RESDESC::RdflagsElem(v11, v18) & 0x20) != 0 )
      OldRefLibIdRel = EXFRAME::Prtmi(v11);
    else
      OldRefLibIdRel = 0;
    if ( psa )
    {
      v5 = rtCopyArray(ppsaOut, psa, OldRefLibIdRel);
      if ( v5 < 0 )
        goto LABEL_51;
    }
    if ( v7[0] < 0 )
    {
      ppsaOut->pvData = 0;
      psa->pvData = 0;
      psa->fFeatures &= ~0x10u;
      ppsaOut->fFeatures &= ~0x10u;
      SafeArrayDestroyDescriptor(ppsaOut);
      SafeArrayDestroyDescriptor(psa);
    }
LABEL_49:
    v11 = RESDESCTBL::PresdescNext(this, v11);
  }
  if ( SafeArrayAllocDescriptor(cDims, &ppsaOut) < 0 )
  {
    v5 = -2147024882;
    goto LABEL_51;
  }
  if ( SafeArrayAllocDescriptor(cDims, &psa) >= 0 )
  {
    qmemcpy(ppsaOut, v16, (unsigned int)CbSizeOldArrayDesc(cDims));
    qmemcpy(psa, v16, (unsigned int)CbSizeOldArrayDesc(cDims));
    psa->fFeatures &= 0xFF1Fu;
    ppsaOut->fFeatures &= 0xFF1Fu;
    ppsaOut->pvData = pvargDest;
    if ( (ppsaOut->fFeatures & 0xF20) != 0 )
    {
      v4 = SafeArrayElemCount(v16);
      v21 = v16->cbElements * v4;
      memset(ppsaOut->pvData, 0, v21);
    }
    psa->pvData = pvargSrc;
    goto LABEL_39;
  }
  v5 = -2147024882;
  SafeArrayDestroyDescriptor(ppsaOut);
LABEL_51:
  RESDESCTBL::DestructModInst(this, a2, 0, (_DWORD)v11 - (_DWORD)this, 0);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1802cc4e4  mov     [rsp-8+arg_10], r8
0x1802cc4e9  mov     [rsp-8+arg_8], rdx
0x1802cc4ee  mov     [rsp-8+arg_0], rcx
0x1802cc4f3  push    rbp
0x1802cc4f4  mov     rbp, rsp
0x1802cc4f7  push    rsi
0x1802cc4f8  push    rdi
0x1802cc4f9  sub     rsp, 0B0h
0x1802cc500  lea     rcx, [rsp+0C0h+var_8C]; this
0x1802cc505  call    ??0RESDESCFLAGS@@QEAA@XZ; RESDESCFLAGS::RESDESCFLAGS(void)
0x1802cc50a  mov     [rsp+0C0h+ppsaOut], 0
0x1802cc513  mov     [rbp+var_40], 0
0x1802cc51b  mov     rax, [rbp+arg_10]
0x1802cc51f  cmp     [rbp+arg_8], rax
0x1802cc523  jnz     short loc_1802CC52C
0x1802cc525  xor     eax, eax
0x1802cc527  jmp     loc_1802CC9E9
0x1802cc52c  mov     rax, [rbp+arg_0]
0x1802cc530  mov     eax, [rax+4]
0x1802cc533  mov     rdi, [rbp+arg_8]
0x1802cc537  mov     rsi, [rbp+arg_10]
0x1802cc53b  mov     ecx, eax
0x1802cc53d  rep movsb
0x1802cc53f  mov     rcx, [rbp+arg_0]; this
0x1802cc543  call    ?PresdescFirst@RESDESCTBL@@AEBAPEAVRESDESC@@XZ; RESDESCTBL::PresdescFirst(void)
0x1802cc548  mov     [rsp+0C0h+var_70], rax
0x1802cc54d  mov     [rsp+0C0h+var_50], 0
0x1802cc555  jmp     short loc_1802CC561
0x1802cc557  mov     eax, [rsp+0C0h+var_50]
0x1802cc55b  inc     eax
0x1802cc55d  mov     [rsp+0C0h+var_50], eax
0x1802cc561  mov     rax, [rbp+arg_0]
0x1802cc565  movzx   eax, word ptr [rax+0Ah]
0x1802cc569  cmp     [rsp+0C0h+var_50], eax
0x1802cc56d  jnb     loc_1802CC9B7
0x1802cc573  mov     rcx, [rsp+0C0h+var_70]; this
0x1802cc578  call    ?MemId@MEMBER_DEFN@@QEBAJXZ; MEMBER_DEFN::MemId(void)
0x1802cc57d  mov     eax, eax
0x1802cc57f  mov     rcx, [rbp+arg_10]
0x1802cc583  add     rcx, rax
0x1802cc586  mov     rax, rcx
0x1802cc589  mov     [rsp+0C0h+pvargSrc], rax
0x1802cc58e  mov     rcx, [rsp+0C0h+var_70]; this
0x1802cc593  call    ?MemId@MEMBER_DEFN@@QEBAJXZ; MEMBER_DEFN::MemId(void)
0x1802cc598  mov     eax, eax
0x1802cc59a  mov     rcx, [rbp+arg_8]
0x1802cc59e  add     rcx, rax
0x1802cc5a1  mov     rax, rcx
0x1802cc5a4  mov     [rsp+0C0h+pvargDest], rax
0x1802cc5a9  lea     rdx, [rbp+var_28]
0x1802cc5ad  mov     rcx, [rsp+0C0h+var_70]
0x1802cc5b2  call    ?Rdflags@RESDESC@@QEBA?AURESDESCFLAGS@@XZ; RESDESC::Rdflags(void)
0x1802cc5b7  movzx   eax, word ptr [rax]
0x1802cc5ba  mov     word ptr [rsp+0C0h+var_8C], ax
0x1802cc5bf  lea     rcx, [rsp+0C0h+var_8C]
0x1802cc5c4  call    ?Rdkind@RESDESCFLAGS@@QEBA?AW4RDKIND@@XZ; RESDESCFLAGS::Rdkind(void)
0x1802cc5c9  mov     [rsp+0C0h+var_78], eax
0x1802cc5cd  cmp     [rsp+0C0h+var_78], 1
0x1802cc5d2  jz      short loc_1802CC608
0x1802cc5d4  cmp     [rsp+0C0h+var_78], 2
0x1802cc5d9  jz      short loc_1802CC634
0x1802cc5db  cmp     [rsp+0C0h+var_78], 3
0x1802cc5e0  jz      loc_1802CC675
0x1802cc5e6  cmp     [rsp+0C0h+var_78], 4
0x1802cc5eb  jz      short loc_1802CC608
0x1802cc5ed  cmp     [rsp+0C0h+var_78], 5
0x1802cc5f2  jz      loc_1802CC69B
0x1802cc5f8  cmp     [rsp+0C0h+var_78], 9
0x1802cc5fd  jz      loc_1802CC95F
0x1802cc603  jmp     loc_1802CC99F
0x1802cc608  mov     rax, [rsp+0C0h+pvargSrc]
0x1802cc60d  mov     rdx, [rax]
0x1802cc610  mov     rcx, [rsp+0C0h+pvargDest]
0x1802cc615  call    CopyBstr
0x1802cc61a  mov     [rsp+0C0h+var_90], eax
0x1802cc61e  cmp     [rsp+0C0h+var_90], 0
0x1802cc623  jge     short loc_1802CC62F
0x1802cc625  jmp     loc_1802CC9BB
0x1802cc62a  jmp     loc_1802CC9BB
0x1802cc62f  jmp     loc_1802CC99F
0x1802cc634  mov     rax, [rsp+0C0h+pvargDest]
0x1802cc639  movzx   eax, word ptr [rax]
0x1802cc63c  cmp     eax, 8
0x1802cc63f  jl      short loc_1802CC670
0x1802cc641  xor     eax, eax
0x1802cc643  mov     rcx, [rsp+0C0h+pvargDest]
0x1802cc648  mov     [rcx], ax
0x1802cc64b  mov     rdx, [rsp+0C0h+pvargSrc]; pvargSrc
0x1802cc650  mov     rcx, [rsp+0C0h+pvargDest]; pvargDest
0x1802cc655  call    cs:__imp_VariantCopy
0x1802cc65b  mov     [rsp+0C0h+var_90], eax
0x1802cc65f  cmp     [rsp+0C0h+var_90], 0
0x1802cc664  jge     short loc_1802CC670
0x1802cc666  jmp     loc_1802CC9BB
0x1802cc66b  jmp     loc_1802CC9BB
0x1802cc670  jmp     loc_1802CC99F
0x1802cc675  mov     rax, [rsp+0C0h+pvargSrc]
0x1802cc67a  mov     rax, [rax]
0x1802cc67d  mov     [rbp+var_30], rax
0x1802cc681  cmp     [rbp+var_30], 0
0x1802cc686  jz      short loc_1802CC696
0x1802cc688  mov     rax, [rbp+var_30]
0x1802cc68c  mov     rax, [rax]
0x1802cc68f  mov     rcx, [rbp+var_30]
0x1802cc693  call    qword ptr [rax+8]
0x1802cc696  jmp     loc_1802CC99F
0x1802cc69b  mov     al, [rsp+0C0h+var_8C+1]
0x1802cc69f  and     al, 1
0x1802cc6a1  movzx   eax, al
0x1802cc6a4  test    eax, eax
0x1802cc6a6  jz      loc_1802CC735
0x1802cc6ac  mov     rax, [rsp+0C0h+pvargSrc]
0x1802cc6b1  mov     rax, [rax]
0x1802cc6b4  mov     [rsp+0C0h+psa], rax
0x1802cc6b9  cmp     [rsp+0C0h+psa], 0
0x1802cc6bf  jz      short loc_1802CC730
0x1802cc6c1  mov     rax, [rsp+0C0h+psa]
0x1802cc6c6  movzx   eax, word ptr [rax+2]
0x1802cc6ca  and     eax, 0E0h
0x1802cc6cf  test    eax, eax
0x1802cc6d1  jz      short loc_1802CC6FE
0x1802cc6d3  mov     rdx, [rsp+0C0h+pvargDest]; ppsaOut
0x1802cc6d8  mov     rcx, [rsp+0C0h+psa]; psa
0x1802cc6dd  call    cs:__imp_SafeArrayCopy
0x1802cc6e3  mov     [rsp+0C0h+var_90], eax
0x1802cc6e7  cmp     [rsp+0C0h+var_90], 0
0x1802cc6ec  jge     short loc_1802CC6F7
0x1802cc6ee  mov     eax, [rsp+0C0h+var_90]
0x1802cc6f2  jmp     loc_1802CC9E9
0x1802cc6f7  jmp     loc_1802CC99F
0x1802cc6fc  jmp     short loc_1802CC730
0x1802cc6fe  mov     rdx, [rsp+0C0h+psa]; Src
0x1802cc703  lea     rcx, [rsp+0C0h+ppsaOut]; ppsaOut
0x1802cc708  call    AllocArrayFromSrc
0x1802cc70d  test    eax, eax
0x1802cc70f  jge     short loc_1802CC723
0x1802cc711  mov     [rsp+0C0h+var_90], 8007000Eh
0x1802cc719  jmp     loc_1802CC9BB
0x1802cc71e  jmp     loc_1802CC9BB
0x1802cc723  mov     rax, [rsp+0C0h+pvargDest]
0x1802cc728  mov     rcx, [rsp+0C0h+ppsaOut]
0x1802cc72d  mov     [rax], rcx
0x1802cc730  jmp     loc_1802CC887
0x1802cc735  mov     rcx, [rsp+0C0h+var_70]; this
0x1802cc73a  call    ?Psa@RESDESC@@QEAAPEAUtagSAFEARRAY@@XZ; RESDESC::Psa(void)
0x1802cc73f  mov     [rsp+0C0h+var_48], rax
0x1802cc744  mov     rax, [rsp+0C0h+var_48]
0x1802cc749  movzx   eax, word ptr [rax]
0x1802cc74c  mov     [rsp+0C0h+cDims], eax
0x1802cc750  mov     al, [rsp+0C0h+var_8C]
0x1802cc754  shr     al, 7
0x1802cc757  and     al, 1
0x1802cc759  movzx   eax, al
0x1802cc75c  test    eax, eax
0x1802cc75e  jz      loc_1802CC873
0x1802cc764  lea     rdx, [rsp+0C0h+ppsaOut]; ppsaOut
0x1802cc769  mov     ecx, [rsp+0C0h+cDims]; cDims
0x1802cc76d  call    cs:__imp_SafeArrayAllocDescriptor
0x1802cc773  test    eax, eax
0x1802cc775  jge     short loc_1802CC789
0x1802cc777  mov     [rsp+0C0h+var_90], 8007000Eh
0x1802cc77f  jmp     loc_1802CC9BB
0x1802cc784  jmp     loc_1802CC9BB
0x1802cc789  lea     rdx, [rsp+0C0h+psa]; ppsaOut
0x1802cc78e  mov     ecx, [rsp+0C0h+cDims]; cDims
0x1802cc792  call    cs:__imp_SafeArrayAllocDescriptor
0x1802cc798  test    eax, eax
0x1802cc79a  jge     short loc_1802CC7B9
0x1802cc79c  mov     [rsp+0C0h+var_90], 8007000Eh
0x1802cc7a4  mov     rcx, [rsp+0C0h+ppsaOut]; psa
0x1802cc7a9  call    cs:__imp_SafeArrayDestroyDescriptor
0x1802cc7af  jmp     loc_1802CC9BB
0x1802cc7b4  jmp     loc_1802CC9BB
0x1802cc7b9  mov     ecx, [rsp+0C0h+cDims]
0x1802cc7bd  call    CbSizeOldArrayDesc
0x1802cc7c2  mov     eax, eax
0x1802cc7c4  mov     rdi, [rsp+0C0h+ppsaOut]
0x1802cc7c9  mov     rsi, [rsp+0C0h+var_48]
0x1802cc7ce  mov     ecx, eax
0x1802cc7d0  rep movsb
0x1802cc7d2  mov     ecx, [rsp+0C0h+cDims]
0x1802cc7d6  call    CbSizeOldArrayDesc
0x1802cc7db  mov     eax, eax
0x1802cc7dd  mov     rdi, [rsp+0C0h+psa]
0x1802cc7e2  mov     rsi, [rsp+0C0h+var_48]
0x1802cc7e7  mov     ecx, eax
0x1802cc7e9  rep movsb
0x1802cc7eb  mov     rax, [rsp+0C0h+psa]
0x1802cc7f0  movzx   eax, word ptr [rax+2]
0x1802cc7f4  and     eax, 0FFFFFF1Fh
0x1802cc7f9  mov     rcx, [rsp+0C0h+psa]
0x1802cc7fe  mov     [rcx+2], ax
0x1802cc802  mov     rax, [rsp+0C0h+ppsaOut]
0x1802cc807  movzx   eax, word ptr [rax+2]
0x1802cc80b  and     eax, 0FFFFFF1Fh
0x1802cc810  mov     rcx, [rsp+0C0h+ppsaOut]
0x1802cc815  mov     [rcx+2], ax
0x1802cc819  mov     rax, [rsp+0C0h+ppsaOut]
0x1802cc81e  mov     rcx, [rsp+0C0h+pvargDest]
0x1802cc823  mov     [rax+10h], rcx
0x1802cc827  mov     rax, [rsp+0C0h+ppsaOut]
0x1802cc82c  movzx   eax, word ptr [rax+2]
0x1802cc830  and     eax, 0F20h
0x1802cc835  test    eax, eax
0x1802cc837  jz      short loc_1802CC863
0x1802cc839  mov     rcx, [rsp+0C0h+var_48]
0x1802cc83e  call    SafeArrayElemCount
0x1802cc843  mov     rcx, [rsp+0C0h+var_48]
0x1802cc848  imul    eax, [rcx+4]
0x1802cc84c  mov     eax, eax
0x1802cc84e  mov     [rbp+var_20], rax
0x1802cc852  mov     rcx, [rsp+0C0h+ppsaOut]
0x1802cc857  mov     rdi, [rcx+10h]
0x1802cc85b  xor     eax, eax
0x1802cc85d  mov     rcx, [rbp+var_20]
0x1802cc861  rep stosb
0x1802cc863  mov     rax, [rsp+0C0h+psa]
0x1802cc868  mov     rcx, [rsp+0C0h+pvargSrc]
0x1802cc86d  mov     [rax+10h], rcx
0x1802cc871  jmp     short loc_1802CC887
0x1802cc873  mov     rax, [rsp+0C0h+pvargDest]
0x1802cc878  mov     [rsp+0C0h+ppsaOut], rax
0x1802cc87d  mov     rax, [rsp+0C0h+pvargSrc]
0x1802cc882  mov     [rsp+0C0h+psa], rax
0x1802cc887  lea     rdx, [rbp+var_38]
0x1802cc88b  mov     rcx, [rsp+0C0h+var_70]
0x1802cc890  call    ?RdflagsElem@RESDESC@@QEBA?AURESDESCFLAGS@@XZ; RESDESC::RdflagsElem(void)
0x1802cc895  mov     al, [rax]
0x1802cc897  shr     al, 5
0x1802cc89a  and     al, 1
0x1802cc89c  movzx   eax, al
0x1802cc89f  test    eax, eax
0x1802cc8a1  jz      short loc_1802CC8B3
0x1802cc8a3  mov     rcx, [rsp+0C0h+var_70]; this
0x1802cc8a8  call    ?Prtmi@EXFRAME@@QEAAPEAURTMI@@XZ; EXFRAME::Prtmi(void)
0x1802cc8ad  mov     [rbp+var_40], rax
0x1802cc8b1  jmp     short loc_1802CC8BB
0x1802cc8b3  mov     [rbp+var_40], 0
0x1802cc8bb  cmp     [rsp+0C0h+psa], 0
0x1802cc8c1  jz      short loc_1802CC8EB
0x1802cc8c3  mov     r8, [rbp+var_40]
0x1802cc8c7  mov     rdx, [rsp+0C0h+psa]
0x1802cc8cc  mov     rcx, [rsp+0C0h+ppsaOut]
0x1802cc8d1  call    rtCopyArray
0x1802cc8d6  mov     [rsp+0C0h+var_90], eax
0x1802cc8da  cmp     [rsp+0C0h+var_90], 0
0x1802cc8df  jge     short loc_1802CC8EB
0x1802cc8e1  jmp     loc_1802CC9BB
0x1802cc8e6  jmp     loc_1802CC9BB
0x1802cc8eb  mov     al, [rsp+0C0h+var_8C]
0x1802cc8ef  shr     al, 7
0x1802cc8f2  and     al, 1
0x1802cc8f4  movzx   eax, al
0x1802cc8f7  test    eax, eax
0x1802cc8f9  jz      short loc_1802CC95D
0x1802cc8fb  mov     rax, [rsp+0C0h+ppsaOut]
0x1802cc900  mov     qword ptr [rax+10h], 0
0x1802cc908  mov     rax, [rsp+0C0h+psa]
0x1802cc90d  mov     qword ptr [rax+10h], 0
0x1802cc915  mov     rax, [rsp+0C0h+psa]
0x1802cc91a  movzx   eax, word ptr [rax+2]
0x1802cc91e  and     eax, 0FFFFFFEFh
0x1802cc921  mov     rcx, [rsp+0C0h+psa]
0x1802cc926  mov     [rcx+2], ax
0x1802cc92a  mov     rax, [rsp+0C0h+ppsaOut]
0x1802cc92f  movzx   eax, word ptr [rax+2]
0x1802cc933  and     eax, 0FFFFFFEFh
0x1802cc936  mov     rcx, [rsp+0C0h+ppsaOut]
0x1802cc93b  mov     [rcx+2], ax
0x1802cc93f  mov     rcx, [rsp+0C0h+ppsaOut]; psa
0x1802cc944  call    cs:__imp_SafeArrayDestroyDescriptor
0x1802cc94a  mov     [rsp+0C0h+var_90], eax
0x1802cc94e  mov     rcx, [rsp+0C0h+psa]; psa
0x1802cc953  call    cs:__imp_SafeArrayDestroyDescriptor
0x1802cc959  mov     [rsp+0C0h+var_90], eax
0x1802cc95d  jmp     short loc_1802CC99F
0x1802cc95f  mov     al, [rsp+0C0h+var_8C]
0x1802cc963  shr     al, 5
0x1802cc966  and     al, 1
0x1802cc968  movzx   eax, al
0x1802cc96b  test    eax, eax
0x1802cc96d  jz      short loc_1802CC99F
0x1802cc96f  mov     rcx, [rsp+0C0h+var_70]; this
0x1802cc974  call    ?GetOldRefLibIdRel@COldRefLibIdNode@@QEAAPEA_WXZ; COldRefLibIdNode::GetOldRefLibIdRel(void)
0x1802cc979  mov     [rbp+var_40], rax
0x1802cc97d  mov     r8, [rsp+0C0h+pvargSrc]; void *
0x1802cc982  mov     rdx, [rsp+0C0h+pvargDest]; void *
0x1802cc987  mov     rcx, [rbp+var_40]; this
0x1802cc98b  call    ?CopyInst@RESDESCTBL@@QEAAJPEAX0@Z; RESDESCTBL::CopyInst(void *,void *)
0x1802cc990  mov     [rsp+0C0h+var_90], eax
0x1802cc994  cmp     [rsp+0C0h+var_90], 0
0x1802cc999  jge     short loc_1802CC99F
0x1802cc99b  jmp     short loc_1802CC9BB
0x1802cc99d  jmp     short loc_1802CC9BB
0x1802cc99f  mov     rdx, [rsp+0C0h+var_70]; struct RESDESC *
0x1802cc9a4  mov     rcx, [rbp+arg_0]; this
0x1802cc9a8  call    ?PresdescNext@RESDESCTBL@@AEBAPEAVRESDESC@@PEAV2@@Z; RESDESCTBL::PresdescNext(RESDESC *)
0x1802cc9ad  mov     [rsp+0C0h+var_70], rax
0x1802cc9b2  jmp     loc_1802CC557
0x1802cc9b7  xor     eax, eax
  ... truncated ...
```
