# CUtlProps::utlGetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *,CBidGenericBase const &)

- ea: `0x18002c3dc`
- end: `0x18002ca52`
- name: `?utlGetProperties@CUtlProps@@QEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@AEBVCBidGenericBase@@@Z`
- size: `1654`
- prototype: `__int64 __fastcall(CUtlProps *__hidden this, unsigned int, const struct tagDBPROPIDSET *const, unsigned int *, struct tagDBPROPSET **, const struct CBidGenericBase *)`
- caller_count: `4`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x180014390`
- `0x18001f850`
- `0x180020f40`
- `0x18002ae98`

## callees

- `0x1800022f8`
- `0x180002650`
- `0x18001a6c8`
- `0x18002a0c0`
- `0x18002a1b4`
- `0x18002ab58`
- `0x18002bad8`
- `0x18002bd24`
- `0x18002c3dc`
- `0x18002cd00`
- `0x18002cd54`
- `0x18002e02a`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002c5d1`
- `OLEAUT32!__imp_VariantInit` at `0x18002c5d1`
- `OLEAUT32!__imp_VariantCopy` at `0x18002c77c`
- `OLEAUT32!__imp_VariantCopy` at `0x18002c895`
- `OLEAUT32!__imp_VariantCopy` at `0x18002c77c`
- `OLEAUT32!__imp_VariantCopy` at `0x18002c895`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CUtlProps::utlGetProperties(
        CUtlProps *this,
        unsigned int a2,
        const struct tagDBPROPIDSET *const a3,
        unsigned int *a4,
        struct tagDBPROPSET **a5,
        const struct CBidGenericBase *a6)
{
  const struct tagDBPROPIDSET *v6; // r15
  unsigned int v7; // r14d
  CUtlProps *v8; // rsi
  unsigned int v9; // r12d
  unsigned int v10; // eax
  int v11; // edi
  __int64 v12; // rbx
  struct tagDBPROPSET *v13; // rdx
  struct tagDBPROP *v14; // rdi
  __int64 v15; // r14
  unsigned int cPropertyIDs; // r13d
  int v17; // r15d
  __int64 v18; // rcx
  unsigned int BidObjectID; // eax
  __int64 v20; // rbx
  __int64 v21; // rbx
  __int64 v22; // rsi
  unsigned int i; // r14d
  int v24; // edx
  __int64 v25; // r14
  struct tagDBPROPSET *v26; // rcx
  unsigned int j; // ecx
  __int64 v28; // rbx
  int v29; // eax
  __int64 v30; // rdx
  unsigned int v31; // eax
  __int64 v32; // r8
  unsigned int UPropValIndex; // eax
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int16 v36; // r11
  int v37; // eax
  HRESULT v38; // eax
  __int64 v39; // r8
  __int64 v40; // r10
  unsigned int v41; // eax
  __int64 v42; // r11
  int v43; // eax
  HRESULT v44; // eax
  unsigned int v45; // eax
  unsigned int v46; // eax
  unsigned int v47; // ebx
  unsigned int v48; // eax
  unsigned int v50; // eax
  unsigned int v51; // [rsp+38h] [rbp-49h] BYREF
  unsigned int v52; // [rsp+3Ch] [rbp-45h] BYREF
  unsigned int v53; // [rsp+40h] [rbp-41h]
  unsigned int v54; // [rsp+44h] [rbp-3Dh]
  unsigned int v55; // [rsp+48h] [rbp-39h] BYREF
  int v56; // [rsp+4Ch] [rbp-35h]
  __int64 v57; // [rsp+50h] [rbp-31h]
  unsigned int v58; // [rsp+58h] [rbp-29h] BYREF
  struct tagDBPROPSET *v59; // [rsp+60h] [rbp-21h] BYREF
  unsigned int v60; // [rsp+68h] [rbp-19h]
  struct tagDBPROP *v61; // [rsp+70h] [rbp-11h] BYREF
  struct tagDBPROPSET *v62; // [rsp+78h] [rbp-9h]

  v6 = a3;
  v7 = a2;
  v8 = this;
  v55 = 0;
  v9 = 0;
  v58 = 0;
  v59 = 0;
  v51 = 0;
  CUtlProps::AllocPropSets(this, a2, a3, &v58, &v59);
  v10 = v58;
  v60 = v58;
  if ( !v58 )
  {
    DBPROPSETOBJECT::ClearPropertySet((DBPROPSETOBJECT *)&v58);
    return 0;
  }
  v11 = 0;
  v56 = 0;
  v12 = 0;
  v13 = v59;
  v62 = v59;
  while ( 1 )
  {
    v53 = v12;
    if ( (unsigned int)v12 >= v10 )
      break;
    v14 = 0;
    v61 = 0;
    if ( v7 )
    {
      v15 = (unsigned int)v12;
      v57 = (unsigned int)v12;
      v18 = (unsigned int)v12;
      cPropertyIDs = v6[v18].cPropertyIDs;
      if ( cPropertyIDs )
      {
        if ( (*(unsigned int (__fastcall **)(CUtlProps *, GUID *, unsigned int *))(*(_QWORD *)v8 + 8LL))(
               v8,
               &v13[v18].guidPropertySet,
               &v51) )
        {
          v17 = 0;
        }
        else
        {
          v17 = 6;
          if ( (bidGblFlags & 2) != 0 && off_180048E98[0] )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID(a6);
            bidTraceW(off_180048220, 1316864, off_180048E98[0], BidObjectID, v12);
          }
        }
        goto LABEL_16;
      }
    }
    else if ( *((_DWORD *)v8 + 18) )
    {
      v15 = (unsigned int)v12;
      v57 = (unsigned int)v12;
      cPropertyIDs = *(_DWORD *)(*((_QWORD *)v8 + 2) + 40 * v12 + 8)
                   + CUtlProps::GetCountofColids(
                       (CUtlProps *)(3 * v12),
                       (struct tagUPROP *)(*((_QWORD *)v8 + 3) + 24 * v12));
      v17 = 1;
      v51 = v12;
      goto LABEL_16;
    }
    v15 = (unsigned int)v12;
    v57 = (unsigned int)v12;
    if ( !(*(unsigned int (__fastcall **)(CUtlProps *, GUID *, unsigned int *))(*(_QWORD *)v8 + 8LL))(
            v8,
            &v13[(unsigned int)v12].guidPropertySet,
            &v51) )
    {
      v17 = 5;
      if ( (bidGblFlags & 2) != 0 && off_180048EA8[0] )
      {
        v46 = CBidGenericBase::GetBidObjectID(a6);
        bidTraceW(off_180048220, 1300480, off_180048EA8[0], v46, v12);
      }
      goto LABEL_26;
    }
    v17 = 1;
    v20 = v51;
    cPropertyIDs = *(_DWORD *)(*((_QWORD *)v8 + 2) + 40 * v20 + 8)
                 + CUtlProps::GetCountofColids(
                     (CUtlProps *)(3LL * v51),
                     (struct tagUPROP *)(*((_QWORD *)v8 + 3) + 24LL * v51));
LABEL_16:
    v14 = (struct tagDBPROP *)TaskAlloc(72LL * cPropertyIDs);
    v61 = v14;
    memset_0(v14, 0, 72LL * cPropertyIDs);
    if ( cPropertyIDs )
    {
      v21 = 0;
      v22 = v53;
      for ( i = 0; i < cPropertyIDs; ++i )
      {
        VariantInit(&v14[v21].vValue);
        v24 = v17 & 2;
        if ( (v17 & 2) != 0 )
        {
          v14[v21].dwPropertyID = a3[v22].rgPropertyIDs[v21];
          v14[v21].dwStatus = 1;
        }
        ++v21;
      }
      v8 = this;
      v15 = v57;
    }
    else
    {
      v24 = v17 & 2;
    }
    if ( !v24 )
    {
      v9 = 0;
      v52 = 0;
      for ( j = 0; ; j = v54 + 1 )
      {
        v54 = j;
        if ( j >= cPropertyIDs )
          goto LABEL_25;
        v28 = v9;
        v14[v9].dwStatus = 0;
        if ( (v17 & 1) != 0 )
        {
          v29 = *(_DWORD *)(*((_QWORD *)v8 + 7) + 4 * (((unsigned __int64)j >> 5) + *((_DWORD *)v8 + 12) * v51));
          if ( !_bittest(&v29, j & 0x1F) )
            continue;
          v30 = *(_QWORD *)(*((_QWORD *)v8 + 2) + 40LL * v51 + 16);
          v31 = *(_DWORD *)(v30 + 24LL * j);
          v14[v9].dwPropertyID = v31;
          v14[v9].colid = DB_NULLID;
          if ( (*(_DWORD *)(v30 + 24LL * j + 8) & 0x400) != 0 || (*(_BYTE *)(v30 + 24LL * j + 12) & 1) != 0 )
          {
            UPropValIndex = CUtlProps::GetUPropValIndex(v8, v51, v31);
            v34 = 3LL * v51;
            v35 = *(_QWORD *)(*((_QWORD *)v8 + 3) + 24LL * v51 + 16) + 48LL * UPropValIndex;
            if ( (v36 & 0x100) != 0 && *(_QWORD *)(v35 + 8) )
              goto LABEL_36;
            v37 = 1;
            if ( *(_DWORD *)(v35 + 40) )
              v37 = *(_DWORD *)v35;
            v14[v9].dwOptions = v37;
            v38 = VariantCopy(&v14[v28].vValue, (const VARIANTARG *)(v35 + 16));
            if ( v38 < 0 )
              ThrowHR(v38);
            goto LABEL_51;
          }
          v32 = *(unsigned int *)(v30 + 24LL * j);
        }
        else
        {
          v39 = a3[v15].rgPropertyIDs[j];
          v14[v9].dwPropertyID = v39;
          v14[v9].colid = DB_NULLID;
          if ( !(*(unsigned int (__fastcall **)(CUtlProps *, _QWORD, __int64, unsigned int *))(*(_QWORD *)v8 + 16LL))(
                  v8,
                  v51,
                  v39,
                  &v55) )
          {
            v14[v9].dwStatus = 1;
            v17 |= 4u;
            if ( (bidGblFlags & 2) != 0 && off_180048E58[0] )
            {
              v45 = CBidGenericBase::GetBidObjectID(a6);
              bidTraceW(off_180048220, 1484800, off_180048E58[0], v45, v53);
            }
            goto LABEL_55;
          }
          v40 = *(_QWORD *)(*((_QWORD *)v8 + 2) + 40LL * v51 + 16);
          LODWORD(v57) = *(_DWORD *)(v40 + 24LL * v55 + 8);
          if ( (v57 & 0x400) != 0 || (*(_BYTE *)(v40 + 24LL * v55 + 12) & 1) != 0 )
          {
            v41 = CUtlProps::GetUPropValIndex(v8, v51, v14[v9].dwPropertyID);
            v34 = 3 * v42;
            v35 = *(_QWORD *)(*((_QWORD *)v8 + 3) + 24 * v42 + 16) + 48LL * v41;
            if ( (v57 & 0x100) != 0 && *(_QWORD *)(v35 + 8) )
            {
LABEL_36:
              CUtlProps::RetrieveColumnIdProps((CUtlProps *)v34, v14, (struct tagUPROPVAL *)v35, &v52);
              v9 = v52;
              continue;
            }
            v43 = 1;
            if ( *(_DWORD *)(v35 + 40) )
              v43 = *(_DWORD *)v35;
            v14[v9].dwOptions = v43;
            v44 = VariantCopy(&v14[v28].vValue, (const VARIANTARG *)(v35 + 16));
            if ( v44 < 0 )
              ThrowHR(v44);
            goto LABEL_51;
          }
          v32 = *(unsigned int *)(v40 + 24LL * v55);
        }
        (*(void (__fastcall **)(CUtlProps *, _QWORD, __int64, DBPROPOPTIONS *, VARIANT *))(*(_QWORD *)v8 + 40LL))(
          v8,
          v51,
          v32,
          &v14[v9].dwOptions,
          &v14[v28].vValue);
LABEL_51:
        v17 |= 8u;
LABEL_55:
        v52 = ++v9;
      }
    }
    v9 = cPropertyIDs;
LABEL_25:
    LODWORD(v12) = v53;
LABEL_26:
    v61 = 0;
    v25 = v15;
    v26 = v62;
    v62[v25].rgProperties = v14;
    v26[v25].cProperties = v14 != 0 ? v9 : 0;
    v11 = v17 | v56;
    v56 |= v17;
    CAutoP<_GUID>::~CAutoP<_GUID>(&v61);
    v12 = (unsigned int)(v12 + 1);
    v13 = v62;
    v10 = v60;
    v6 = a3;
    v7 = a2;
  }
  *a4 = v10;
  v58 = 0;
  *a5 = v13;
  v59 = 0;
  if ( (v11 & 4) == 0 )
  {
    DBPROPSETOBJECT::ClearPropertySet((DBPROPSETOBJECT *)&v58);
    return 0;
  }
  if ( (v11 & 8) != 0 )
  {
    v47 = 265946;
    if ( (bidGblFlags & 2) != 0 && off_180048E68[0] )
    {
      v48 = CBidGenericBase::GetBidObjectID(a6);
      bidTraceW(off_180048220, 1520640, off_180048E68[0], v48, v11);
    }
  }
  else
  {
    v47 = -2147217887;
    if ( (bidGblFlags & 2) != 0 && off_180048E50[0] )
    {
      v50 = CBidGenericBase::GetBidObjectID(a6);
      bidTraceW(off_180048220, 1525760, off_180048E50[0], v50, v11);
    }
  }
  DBPROPSETOBJECT::ClearPropertySet((DBPROPSETOBJECT *)&v58);
  return v47;
}

```

## disassembly

```asm
0x18002c3dc  mov     rax, rsp
0x18002c3df  mov     [rax+20h], r9
0x18002c3e3  mov     [rax+18h], r8
0x18002c3e7  mov     [rax+10h], edx
0x18002c3ea  mov     [rax+8], rcx
0x18002c3ee  push    rbp
0x18002c3ef  push    rbx
0x18002c3f0  push    rsi
0x18002c3f1  push    rdi
0x18002c3f2  push    r12
0x18002c3f4  push    r13
0x18002c3f6  push    r14
0x18002c3f8  push    r15
0x18002c3fa  lea     rbp, [rax-4Fh]
0x18002c3fe  sub     rsp, 88h
0x18002c405  mov     r15, r8
0x18002c408  mov     r14d, edx
0x18002c40b  mov     rsi, rcx
0x18002c40e  mov     [rbp+47h+var_80], 0
0x18002c415  xor     r12d, r12d
0x18002c418  mov     [rbp+47h+var_70], r12d
0x18002c41c  mov     [rbp+47h+var_68], r12
0x18002c420  mov     [rbp+47h+var_90], r12d
0x18002c424  lea     rax, [rbp+47h+var_68]
0x18002c428  mov     [rsp+0C0h+var_A0], rax; struct tagDBPROPSET **
0x18002c42d  lea     r9, [rbp+47h+var_70]; unsigned int *
0x18002c431  call    ?AllocPropSets@CUtlProps@@AEAAXKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@@Z; CUtlProps::AllocPropSets(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *)
0x18002c436  mov     eax, [rbp+47h+var_70]
0x18002c439  mov     [rbp+47h+var_60], eax
0x18002c43c  test    eax, eax
0x18002c43e  jnz     short loc_18002C44F
0x18002c440  lea     rcx, [rbp+47h+var_70]; this
0x18002c444  call    ?ClearPropertySet@DBPROPSETOBJECT@@QEAAXXZ; DBPROPSETOBJECT::ClearPropertySet(void)
0x18002c449  nop
0x18002c44a  jmp     loc_18002CA3C
0x18002c44f  xor     edi, edi
0x18002c451  mov     [rbp+47h+var_7C], edi
0x18002c454  xor     ebx, ebx
0x18002c456  mov     rdx, [rbp+47h+var_68]
0x18002c45a  mov     [rbp+47h+var_50], rdx
0x18002c45e  mov     [rbp+47h+var_88], ebx
0x18002c461  cmp     ebx, eax
0x18002c463  jnb     loc_18002C95E
0x18002c469  xor     edi, edi
0x18002c46b  mov     [rbp+47h+var_58], rdi
0x18002c46f  test    r14d, r14d
0x18002c472  jnz     short loc_18002C4B2
0x18002c474  cmp     [rsi+48h], r14d
0x18002c478  jz      loc_18002C537
0x18002c47e  mov     r14d, ebx
0x18002c481  mov     [rbp+47h+var_78], r14
0x18002c485  lea     rcx, [rbx+rbx*2]; this
0x18002c489  mov     rax, [rsi+18h]
0x18002c48d  lea     rdx, [rax+rcx*8]; struct tagUPROP *
0x18002c491  call    ?GetCountofColids@CUtlProps@@AEAAKPEAUtagUPROP@@@Z; CUtlProps::GetCountofColids(tagUPROP *)
0x18002c496  mov     r13d, eax
0x18002c499  lea     rdx, [rbx+rbx*4]
0x18002c49d  mov     rcx, [rsi+10h]
0x18002c4a1  add     r13d, [rcx+rdx*8+8]
0x18002c4a6  lea     r15d, [rdi+1]
0x18002c4aa  mov     [rbp+47h+var_90], ebx
0x18002c4ad  jmp     loc_18002C590
0x18002c4b2  mov     r14d, ebx
0x18002c4b5  mov     [rbp+47h+var_78], r14
0x18002c4b9  mov     ecx, ebx
0x18002c4bb  shl     rcx, 5
0x18002c4bf  mov     r13d, [rcx+r15+8]
0x18002c4c4  test    r13d, r13d
0x18002c4c7  jz      short loc_18002C537
0x18002c4c9  mov     rax, [rsi]
0x18002c4cc  add     rcx, 0Ch
0x18002c4d0  add     rdx, rcx
0x18002c4d3  lea     r8, [rbp+47h+var_90]
0x18002c4d7  mov     rcx, rsi
0x18002c4da  mov     rax, [rax+8]
0x18002c4de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c4e3  test    eax, eax
0x18002c4e5  jnz     short loc_18002C532
0x18002c4e7  lea     r15d, [rax+6]
0x18002c4eb  test    byte ptr cs:_bidGblFlags, 2
0x18002c4f2  jz      loc_18002C590
0x18002c4f8  mov     rax, cs:off_180048E98; "<CUtlProps::utlGetProperties|ADO|ERR> %"...
0x18002c4ff  test    rax, rax
0x18002c502  jz      loc_18002C590
0x18002c508  mov     rcx, [rbp+47h+arg_28]; this
0x18002c50c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002c511  mov     r8, cs:off_180048E98; "<CUtlProps::utlGetProperties|ADO|ERR> %"...
0x18002c518  mov     rcx, cs:off_180048220; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002c51f  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x18002c523  mov     r9d, eax
0x18002c526  mov     edx, 141800h
0x18002c52b  call    _bidTraceW
0x18002c530  jmp     short loc_18002C590
0x18002c532  xor     r15d, r15d
0x18002c535  jmp     short loc_18002C590
0x18002c537  mov     r14d, ebx
0x18002c53a  mov     [rbp+47h+var_78], r14
0x18002c53e  mov     rcx, [rsi]
0x18002c541  mov     eax, ebx
0x18002c543  shl     rax, 5
0x18002c547  add     rax, 0Ch
0x18002c54b  add     rdx, rax
0x18002c54e  mov     rax, [rcx+8]
0x18002c552  lea     r8, [rbp+47h+var_90]
0x18002c556  mov     rcx, rsi
0x18002c559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c55e  test    eax, eax
0x18002c560  jz      loc_18002C906
0x18002c566  mov     r15d, 1
0x18002c56c  mov     ebx, [rbp+47h+var_90]
0x18002c56f  lea     rcx, [rbx+rbx*2]; this
0x18002c573  mov     rax, [rsi+18h]
0x18002c577  lea     rdx, [rax+rcx*8]; struct tagUPROP *
0x18002c57b  call    ?GetCountofColids@CUtlProps@@AEAAKPEAUtagUPROP@@@Z; CUtlProps::GetCountofColids(tagUPROP *)
0x18002c580  mov     r13d, eax
0x18002c583  lea     rcx, [rbx+rbx*4]
0x18002c587  mov     rax, [rsi+10h]
0x18002c58b  add     r13d, [rax+rcx*8+8]
0x18002c590  mov     eax, r13d
0x18002c593  lea     rbx, [rax+rax*8]
0x18002c597  shl     rbx, 3
0x18002c59b  mov     rcx, rbx; unsigned __int64
0x18002c59e  call    ?TaskAlloc@@YAPEAX_K@Z; TaskAlloc(unsigned __int64)
0x18002c5a3  mov     rdi, rax
0x18002c5a6  mov     [rbp+47h+var_58], rax
0x18002c5aa  mov     r8, rbx; Size
0x18002c5ad  xor     edx, edx; Val
0x18002c5af  mov     rcx, rax; void *
0x18002c5b2  call    memset_0
0x18002c5b7  test    r13d, r13d
0x18002c5ba  jz      short loc_18002C613
0x18002c5bc  xor     ebx, ebx
0x18002c5be  mov     esi, [rbp+47h+var_88]
0x18002c5c1  mov     r14d, ebx
0x18002c5c4  lea     r12, [rbx+rbx*8]
0x18002c5c8  lea     rcx, [r12+6]
0x18002c5cd  lea     rcx, [rdi+rcx*8]; pvarg
0x18002c5d1  call    cs:__imp_VariantInit
0x18002c5d7  mov     edx, r15d
0x18002c5da  and     edx, 2
0x18002c5dd  jz      short loc_18002C5FE
0x18002c5df  mov     rax, rsi
0x18002c5e2  shl     rax, 5
0x18002c5e6  mov     rcx, [rbp+47h+arg_10]
0x18002c5ea  mov     rax, [rax+rcx]
0x18002c5ee  mov     ecx, [rax+rbx*4]
0x18002c5f1  mov     [rdi+r12*8], ecx
0x18002c5f5  mov     dword ptr [rdi+r12*8+8], 1
0x18002c5fe  inc     r14d
0x18002c601  inc     rbx
0x18002c604  cmp     r14d, r13d
0x18002c607  jb      short loc_18002C5C4
0x18002c609  mov     rsi, [rbp+47h+arg_0]
0x18002c60d  mov     r14, [rbp+47h+var_78]
0x18002c611  jmp     short loc_18002C619
0x18002c613  mov     edx, r15d
0x18002c616  and     edx, 2
0x18002c619  test    edx, edx
0x18002c61b  jz      short loc_18002C66C
0x18002c61d  mov     r12d, r13d
0x18002c620  mov     ebx, [rbp+47h+var_88]
0x18002c623  mov     [rbp+47h+var_58], 0
0x18002c62b  shl     r14, 5
0x18002c62f  mov     rcx, [rbp+47h+var_50]
0x18002c633  mov     [r14+rcx], rdi
0x18002c637  neg     rdi
0x18002c63a  sbb     eax, eax
0x18002c63c  and     eax, r12d
0x18002c63f  mov     [r14+rcx+8], eax
0x18002c644  mov     edi, [rbp+47h+var_7C]
0x18002c647  or      edi, r15d
0x18002c64a  mov     [rbp+47h+var_7C], edi
0x18002c64d  lea     rcx, [rbp+47h+var_58]
0x18002c651  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x18002c656  inc     ebx
0x18002c658  mov     rdx, [rbp+47h+var_50]
0x18002c65c  mov     eax, [rbp+47h+var_60]
0x18002c65f  mov     r15, [rbp+47h+arg_10]
0x18002c663  mov     r14d, [rbp+47h+arg_8]
0x18002c667  jmp     loc_18002C45E
0x18002c66c  xor     r12d, r12d
0x18002c66f  mov     [rbp+47h+var_8C], r12d
0x18002c673  xor     ecx, ecx
0x18002c675  mov     [rbp+47h+var_84], ecx
0x18002c678  cmp     ecx, r13d
0x18002c67b  jnb     short loc_18002C620
0x18002c67d  mov     eax, r12d
0x18002c680  lea     rbx, [rax+rax*8]
0x18002c684  mov     dword ptr [rdi+rbx*8+8], 0
0x18002c68c  mov     r9d, ecx
0x18002c68f  test    r15b, 1
0x18002c693  jz      loc_18002C792
0x18002c699  mov     r8d, [rbp+47h+var_90]
0x18002c69d  imul    r8d, [rsi+30h]
0x18002c6a2  mov     eax, r9d
0x18002c6a5  shr     rax, 5
0x18002c6a9  add     r8, rax
0x18002c6ac  mov     rdx, [rsi+38h]
0x18002c6b0  and     ecx, 1Fh
0x18002c6b3  mov     eax, [rdx+r8*4]
0x18002c6b7  bt      eax, ecx
0x18002c6ba  jnb     loc_18002C8FC
0x18002c6c0  mov     eax, [rbp+47h+var_90]
0x18002c6c3  lea     rcx, [rax+rax*4]
0x18002c6c7  mov     rax, [rsi+10h]
0x18002c6cb  lea     r8, [r9+r9*2]
0x18002c6cf  mov     rdx, [rax+rcx*8+10h]
0x18002c6d4  mov     eax, [rdx+r8*8]
0x18002c6d8  mov     [rdi+rbx*8], eax
0x18002c6db  movups  xmm0, xmmword ptr cs:DB_NULLID.uGuid
0x18002c6e2  movups  xmmword ptr [rdi+rbx*8+10h], xmm0
0x18002c6e7  movups  xmm1, xmmword ptr cs:DB_NULLID.eKind
0x18002c6ee  movups  xmmword ptr [rdi+rbx*8+20h], xmm1
0x18002c6f3  mov     r11d, [rdx+r8*8+8]
0x18002c6f8  bt      r11d, 0Ah
0x18002c6fd  jb      short loc_18002C710
0x18002c6ff  test    byte ptr [rdx+r8*8+0Ch], 1
0x18002c705  jnz     short loc_18002C710
0x18002c707  mov     r8d, [rdx+r8*8]
0x18002c70b  jmp     loc_18002C811
0x18002c710  mov     r8d, eax; unsigned int
0x18002c713  mov     edx, [rbp+47h+var_90]; unsigned int
0x18002c716  mov     rcx, rsi; this
0x18002c719  call    ?GetUPropValIndex@CUtlProps@@QEAAKKK@Z; CUtlProps::GetUPropValIndex(ulong,ulong)
0x18002c71e  mov     r8d, eax
0x18002c721  lea     rdx, [r8+r8*2]
0x18002c725  shl     rdx, 4
0x18002c729  mov     eax, [rbp+47h+var_90]
0x18002c72c  lea     rcx, [rax+rax*2]; this
0x18002c730  mov     rax, [rsi+18h]
0x18002c734  add     rdx, [rax+rcx*8+10h]
0x18002c739  bt      r11d, 8
0x18002c73e  jnb     short loc_18002C75F
0x18002c740  cmp     qword ptr [rdx+8], 0
0x18002c745  jz      short loc_18002C75F
0x18002c747  lea     r9, [rbp+47h+var_8C]; unsigned int *
0x18002c74b  mov     r8, rdx; struct tagUPROPVAL *
0x18002c74e  mov     rdx, rdi; struct tagDBPROP *
0x18002c751  call    ?RetrieveColumnIdProps@CUtlProps@@AEAAXPEAUtagDBPROP@@PEAUtagUPROPVAL@@PEAK@Z; CUtlProps::RetrieveColumnIdProps(tagDBPROP *,tagUPROPVAL *,ulong *)
0x18002c756  mov     r12d, [rbp+47h+var_8C]
0x18002c75a  jmp     loc_18002C8FC
0x18002c75f  cmp     dword ptr [rdx+28h], 0
0x18002c763  mov     eax, 1
0x18002c768  jz      short loc_18002C76C
0x18002c76a  mov     eax, [rdx]
0x18002c76c  mov     [rdi+rbx*8+4], eax
0x18002c770  add     rdx, 10h; pvargSrc
0x18002c774  lea     rcx, [rbx+6]
0x18002c778  lea     rcx, [rdi+rcx*8]; pvargDest
0x18002c77c  call    cs:__imp_VariantCopy
0x18002c782  test    eax, eax
0x18002c784  jns     loc_18002C8A3
0x18002c78a  mov     ecx, eax; int
0x18002c78c  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002c792  mov     rax, r14
0x18002c795  shl     rax, 5
0x18002c799  mov     rcx, [rbp+47h+arg_10]
0x18002c79d  mov     rax, [rax+rcx]
0x18002c7a1  mov     r8d, [rax+r9*4]
0x18002c7a5  mov     [rdi+rbx*8], r8d
0x18002c7a9  movups  xmm0, xmmword ptr cs:DB_NULLID.uGuid
0x18002c7b0  movups  xmmword ptr [rdi+rbx*8+10h], xmm0
0x18002c7b5  movups  xmm1, xmmword ptr cs:DB_NULLID.eKind
0x18002c7bc  movups  xmmword ptr [rdi+rbx*8+20h], xmm1
0x18002c7c1  mov     rax, [rsi]
0x18002c7c4  lea     r9, [rbp+47h+var_80]
0x18002c7c8  mov     edx, [rbp+47h+var_90]
0x18002c7cb  mov     rcx, rsi
0x18002c7ce  mov     rax, [rax+10h]
0x18002c7d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7d7  test    eax, eax
0x18002c7d9  jz      loc_18002C8A9
0x18002c7df  mov     r11d, [rbp+47h+var_90]
0x18002c7e3  lea     rdx, [r11+r11*4]
0x18002c7e7  mov     rcx, [rsi+10h]
0x18002c7eb  mov     eax, [rbp+47h+var_80]
0x18002c7ee  lea     r8, [rax+rax*2]
0x18002c7f2  mov     r10, [rcx+rdx*8+10h]
0x18002c7f7  mov     eax, [r10+r8*8+8]
0x18002c7fc  mov     dword ptr [rbp+47h+var_78], eax
0x18002c7ff  bt      eax, 0Ah
0x18002c803  jb      short loc_18002C83D
0x18002c805  test    byte ptr [r10+r8*8+0Ch], 1
0x18002c80b  jnz     short loc_18002C83D
0x18002c80d  mov     r8d, [r10+r8*8]
0x18002c811  lea     rcx, [rbx+6]
0x18002c815  lea     rcx, [rdi+rcx*8]
0x18002c819  lea     r9, ds:4[rbx*8]
0x18002c821  mov     [rsp+0C0h+var_A0], rcx
0x18002c826  add     r9, rdi
0x18002c829  mov     rax, [rsi]
0x18002c82c  mov     edx, [rbp+47h+var_90]
0x18002c82f  mov     rcx, rsi
0x18002c832  mov     rax, [rax+28h]
0x18002c836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c83b  jmp     short loc_18002C8A3
0x18002c83d  mov     r8d, [rdi+rbx*8]; unsigned int
0x18002c841  mov     edx, [rbp+47h+var_90]; unsigned int
0x18002c844  mov     rcx, rsi; this
0x18002c847  call    ?GetUPropValIndex@CUtlProps@@QEAAKKK@Z; CUtlProps::GetUPropValIndex(ulong,ulong)
  ... truncated ...
```
