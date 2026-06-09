# RESDESCTBL::ConvertInst(void *,void *,int)

- ea: `0x1802cc9fc`
- end: `0x1802cd2b3`
- name: `?ConvertInst@RESDESCTBL@@QEAAJPEAX0H@Z`
- size: `2231`
- prototype: `__int64 __fastcall(RESDESCTBL *__hidden this, void *, void *, int)`
- caller_count: `3`
- callee_count: `35`
- tags: ``

## callers

- `0x1802cbd34`
- `0x1802cbdb8`
- `0x1802cc9fc`

## callees

- `0x18011db78`
- `0x180134fe8`
- `0x180142bc0`
- `0x18014fae4`
- `0x180172b48`
- `0x180212dcc`
- `0x180212e34`
- `0x180212f08`
- `0x180212ffc`
- `0x180213114`
- `0x18021320c`
- `0x180213258`
- `0x180213c74`
- `0x180275e4c`
- `0x180289f00`
- `0x1802cbb54`
- `0x1802cbb64`
- `0x1802cbe38`
- `0x1802cbe48`
- `0x1802cbeac`
- `0x1802cbed4`
- `0x1802cbf10`
- `0x1802cbf1c`
- `0x1802cbf28`
- `0x1802cbf34`
- `0x1802cbf48`
- `0x1802cbf5c`
- `0x1802cc150`
- `0x1802cc484`
- `0x1802cc4a4`
- `0x1802cc9fc`
- `0x1802cd6dc`
- `0x1802cd6e8`
- `0x1802cfbd0`
- `0x18030f67c`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x1802ccbfb`
- `OLEAUT32!__imp_VariantCopy` at `0x1802ccbfb`
- `OLEAUT32!__imp_SafeArrayAllocDescriptor` at `0x1802ccd3f`
- `OLEAUT32!__imp_SafeArrayAllocDescriptor` at `0x1802ccd64`
- `OLEAUT32!__imp_SafeArrayAllocDescriptor` at `0x1802ccf25`
- `OLEAUT32!__imp_SafeArrayAllocDescriptor` at `0x1802ccd3f`
- `OLEAUT32!__imp_SafeArrayAllocDescriptor` at `0x1802ccd64`
- `OLEAUT32!__imp_SafeArrayAllocDescriptor` at `0x1802ccf25`
- `OLEAUT32!__imp_SafeArrayAllocData` at `0x1802cd08c`
- `OLEAUT32!__imp_SafeArrayAllocData` at `0x1802cd08c`
- `OLEAUT32!__imp_SafeArrayDestroyDescriptor` at `0x1802ccd7b`
- `OLEAUT32!__imp_SafeArrayDestroyDescriptor` at `0x1802cd1a8`
- `OLEAUT32!__imp_SafeArrayDestroyDescriptor` at `0x1802cd1b7`
- `OLEAUT32!__imp_SafeArrayDestroyDescriptor` at `0x1802ccd7b`
- `OLEAUT32!__imp_SafeArrayDestroyDescriptor` at `0x1802cd1a8`
- `OLEAUT32!__imp_SafeArrayDestroyDescriptor` at `0x1802cd1b7`

## pseudocode

```c
__int64 __fastcall RESDESCTBL::ConvertInst(RESDESCTBL *this, char *a2, char *a3, unsigned int a4)
{
  unsigned __int16 v4; // ax
  unsigned __int16 v5; // ax
  int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned __int16 v9; // ax
  int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned __int16 v13; // ax
  __int16 v15; // [rsp+20h] [rbp-B0h] BYREF
  SAFEARRAY *ppsaOut; // [rsp+28h] [rbp-A8h] BYREF
  HRESULT v17; // [rsp+30h] [rbp-A0h]
  char v18[4]; // [rsp+34h] [rbp-9Ch] BYREF
  EXFRAME *v19; // [rsp+38h] [rbp-98h]
  SAFEARRAY *psa; // [rsp+40h] [rbp-90h] BYREF
  VARIANTARG *pvargDest; // [rsp+48h] [rbp-88h]
  int v22; // [rsp+50h] [rbp-80h]
  UINT cDims; // [rsp+54h] [rbp-7Ch]
  int v24; // [rsp+58h] [rbp-78h]
  VARIANTARG *pvargSrc; // [rsp+60h] [rbp-70h]
  unsigned int i; // [rsp+68h] [rbp-68h]
  unsigned int v27; // [rsp+6Ch] [rbp-64h]
  struct tagSAFEARRAY *v28; // [rsp+70h] [rbp-60h]
  int v29; // [rsp+78h] [rbp-58h]
  RESDESCTBL *v30; // [rsp+80h] [rbp-50h]
  RESDESCTBL *OldRefLibIdRel; // [rsp+88h] [rbp-48h]
  MEMBER_DEFN *v32; // [rsp+90h] [rbp-40h]
  unsigned int v33; // [rsp+98h] [rbp-38h]
  _BYTE v34[4]; // [rsp+9Ch] [rbp-34h] BYREF
  unsigned int v35; // [rsp+A0h] [rbp-30h]
  unsigned int v36; // [rsp+A4h] [rbp-2Ch]
  unsigned int v37; // [rsp+A8h] [rbp-28h]
  _BYTE v38[4]; // [rsp+ACh] [rbp-24h] BYREF
  unsigned __int64 v39; // [rsp+B0h] [rbp-20h]
  unsigned __int64 v40; // [rsp+B8h] [rbp-18h]

  RESDESCFLAGS::RESDESCFLAGS((RESDESCFLAGS *)v18);
  RESDESCFLAGS::RESDESCFLAGS((RESDESCFLAGS *)&v15);
  qmemcpy(a2, a3, *((unsigned int *)this + 3));
  v22 = 0;
  v19 = RESDESCTBL::PresdescFirst(this);
  for ( i = 0; ; ++i )
  {
    if ( i >= *((unsigned __int16 *)this + 5) )
      return 0;
    *(_WORD *)v18 = *(_WORD *)RESDESC::Rdflags(v19, v38);
    if ( v22 )
    {
      if ( a4 )
      {
        pvargSrc = (VARIANTARG *)&a3[(unsigned int)MEMBER_DEFN::MemId(v19)];
        pvargDest = (VARIANTARG *)&a2[(unsigned int)VAR_DEFN::GetConstVal(v19)];
      }
      else
      {
        pvargSrc = (VARIANTARG *)&a3[(unsigned int)VAR_DEFN::GetConstVal(v19)];
        pvargDest = (VARIANTARG *)&a2[(unsigned int)MEMBER_DEFN::MemId(v19)];
      }
    }
    else
    {
      pvargSrc = (VARIANTARG *)&a3[(unsigned int)MEMBER_DEFN::MemId(v19)];
      pvargDest = (VARIANTARG *)&a2[(unsigned int)MEMBER_DEFN::MemId(v19)];
    }
    v24 = RESDESCFLAGS::Rdkind(v18);
    if ( v24 == 1 )
    {
      *(_QWORD *)&pvargDest->vt = 0;
      if ( a4 )
        _vbaStrToAnsi(pvargDest, *(_QWORD *)&pvargSrc->vt);
      else
        _vbaStrToUnicode(pvargDest, *(_QWORD *)&pvargSrc->vt);
      goto LABEL_87;
    }
    if ( v24 != 2 )
      break;
    if ( v22 || pvargDest->vt >= 8u )
    {
      pvargDest->vt = 0;
      v17 = VariantCopy(pvargDest, pvargSrc);
      if ( v17 < 0 )
        return (unsigned int)v17;
    }
LABEL_87:
    v19 = RESDESCTBL::PresdescNext(this, v19);
  }
  if ( v24 != 5 )
  {
    switch ( v24 )
    {
      case 9:
        if ( (v18[0] & 0x40) != 0 )
        {
          OldRefLibIdRel = (RESDESCTBL *)COldRefLibIdNode::GetOldRefLibIdRel(v19);
          v40 = *((unsigned int *)OldRefLibIdRel + 3);
          memset(pvargDest, 0, v40);
          v17 = RESDESCTBL::ConvertInst(OldRefLibIdRel, pvargDest, pvargSrc, a4);
          if ( v17 < 0 )
            return (unsigned int)v17;
          v22 = 1;
        }
        else if ( v22 )
        {
          if ( (v18[0] & 0x20) != 0 )
            v27 = *((_DWORD *)COldRefLibIdNode::GetOldRefLibIdRel(v19) + 1);
          else
            v27 = RESDESC::CIndir(v19);
          qmemcpy(pvargDest, pvargSrc, v27);
        }
        break;
      case 10:
        v4 = RESDESC::CchFxStr(v19);
        if ( a4 )
          ExFxStrToA(pvargDest, pvargSrc, v4);
        else
          ExFxStrToW(pvargDest, pvargSrc, v4);
        v22 = 1;
        break;
      case 11:
        v5 = RESDESC::CIndir(v19);
        qmemcpy(pvargDest, pvargSrc, v5);
        break;
    }
    goto LABEL_87;
  }
  v15 = *(_WORD *)RESDESC::RdflagsElem(v19, v34);
  if ( (v18[1] & 1) != 0 )
  {
    psa = *(SAFEARRAY **)&pvargSrc->vt;
    ppsaOut = 0;
    goto LABEL_48;
  }
  v28 = RESDESC::Psa(v19);
  cDims = v28->cDims;
  if ( !(unsigned int)RESDESCFLAGS::HasResource((RESDESCFLAGS *)&v15)
    && !(unsigned int)RESDESCFLAGS::IsFxStrInRec((RESDESCFLAGS *)&v15) )
  {
    if ( v22 )
    {
      v6 = SafeArrayElemCount(v28);
      qmemcpy(pvargDest, pvargSrc, v6 * v28->cbElements);
    }
    goto LABEL_87;
  }
  if ( SafeArrayAllocDescriptor(cDims, &ppsaOut) < 0 )
    return (unsigned int)-2147024882;
  if ( SafeArrayAllocDescriptor(cDims, &psa) < 0 )
  {
    v17 = -2147024882;
    SafeArrayDestroyDescriptor(ppsaOut);
    return (unsigned int)v17;
  }
  qmemcpy(ppsaOut, v28, (unsigned int)CbSizeOldArrayDesc(cDims));
  qmemcpy(psa, v28, (unsigned int)CbSizeOldArrayDesc(cDims));
  v29 = ppsaOut->fFeatures & 0xFF1F;
  ppsaOut->fFeatures = v29;
  psa->fFeatures = v29;
  ppsaOut->pvData = pvargDest;
  psa->pvData = pvargSrc;
  if ( (v15 & 0x40) != 0 )
  {
    v30 = EXFRAME::Prtmi(v19);
    if ( a4 )
    {
      v37 = RESDESCTBL::CbAlignRec(v30);
      v7 = RECTYPE_DEFN::Hmember(v30);
      ppsaOut->cbElements = RoundUp(v7, v37);
    }
    else
    {
      v33 = RESDESCTBL::CbAlignRec(v30);
      v8 = RECTYPE_DEFN::Hmember(v30);
      psa->cbElements = RoundUp(v8, v33);
    }
    v22 = RESDESCTBL::FSeenFxStrInRec(v30);
  }
  else if ( (unsigned int)RESDESCFLAGS::IsFxStrInRec((RESDESCFLAGS *)&v15) )
  {
    v9 = EXBIND::BindKind(v19);
    if ( a4 )
      ppsaOut->cbElements = v9;
    else
      psa->cbElements = v9;
  }
  v10 = SafeArrayElemCount(ppsaOut);
  v39 = v10 * ppsaOut->cbElements;
  memset(pvargDest, 0, v39);
LABEL_48:
  if ( !psa )
  {
LABEL_76:
    if ( v18[0] >= 0 )
    {
      *(_QWORD *)&pvargDest->vt = ppsaOut;
    }
    else
    {
      ppsaOut->pvData = 0;
      psa->pvData = 0;
      v17 = SafeArrayDestroyDescriptor(ppsaOut);
      v17 = SafeArrayDestroyDescriptor(psa);
    }
    goto LABEL_87;
  }
  if ( ppsaOut )
  {
LABEL_69:
    if ( (v15 & 0x40) != 0 )
    {
      OldRefLibIdRel = EXFRAME::Prtmi(v19);
      ExRecAryToAorW(&ppsaOut, psa, OldRefLibIdRel, a4);
    }
    else if ( (unsigned int)RESDESCFLAGS::IsString((RESDESCFLAGS *)&v15) )
    {
      ExStrAryToAorW(&ppsaOut, psa, a4);
    }
    else if ( (unsigned int)RESDESCFLAGS::IsFxStrInRec((RESDESCFLAGS *)&v15) )
    {
      v13 = EXBIND::BindKind(v19);
      ExFxStrInRecAryToAorW(&ppsaOut, psa, a4, v13);
    }
    else
    {
      v17 = rtCopyArray(ppsaOut, psa, 0);
      if ( v17 < 0 )
        return (unsigned int)v17;
    }
    goto LABEL_76;
  }
  cDims = psa->cDims;
  if ( SafeArrayAllocDescriptor(cDims, &ppsaOut) < 0 )
    return (unsigned int)-2147024882;
  qmemcpy(ppsaOut, psa, (unsigned int)CbSizeOldArrayDesc(cDims));
  if ( (psa->fFeatures & 0x20) != 0 )
  {
    SafeArraySetRecordInfoWrap(ppsaOut, *(_QWORD *)psa[-1].rgsabound);
  }
  else if ( (psa->fFeatures & 0x40) != 0 )
  {
    SafeArraySetIIDWrap(ppsaOut, &psa[-1].pvData);
  }
  else if ( (psa->fFeatures & 0x80) != 0 )
  {
    ppsaOut[-1].rgsabound[0].lLbound = psa[-1].rgsabound[0].lLbound;
  }
  if ( (*((_BYTE *)v19 + 16) & 0x40) != 0 )
  {
    v32 = EXFRAME::Prtmi(v19);
    if ( a4 )
    {
      v36 = RESDESCTBL::CbAlignRec(v32);
      v11 = RECTYPE_DEFN::Hmember(v32);
      ppsaOut->cbElements = RoundUp(v11, v36);
    }
    else
    {
      v35 = RESDESCTBL::CbAlignRec(v32);
      v12 = MEMBER_DEFN::DwHelpContext(v32);
      ppsaOut->cbElements = RoundUp(v12, v35);
    }
  }
  if ( !ppsaOut->pvData )
  {
LABEL_68:
    *(_QWORD *)&pvargDest->vt = ppsaOut;
    goto LABEL_69;
  }
  ppsaOut->cLocks = 0;
  if ( psa->cLocks )
    return (unsigned int)-2146828278;
  ppsaOut->pvData = 0;
  if ( SafeArrayAllocData(ppsaOut) >= 0 )
  {
    ppsaOut->cLocks = psa->cLocks;
    goto LABEL_68;
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x1802cc9fc  mov     [rsp-8+arg_18], r9d
0x1802cca01  mov     [rsp-8+arg_10], r8
0x1802cca06  mov     [rsp-8+arg_8], rdx
0x1802cca0b  mov     [rsp-8+arg_0], rcx
0x1802cca10  push    rbp
0x1802cca11  mov     rbp, rsp
0x1802cca14  push    rsi
0x1802cca15  push    rdi
0x1802cca16  sub     rsp, 0C0h
0x1802cca1d  lea     rcx, [rsp+0D0h+var_9C]; this
0x1802cca22  call    ??0RESDESCFLAGS@@QEAA@XZ; RESDESCFLAGS::RESDESCFLAGS(void)
0x1802cca27  lea     rcx, [rsp+0D0h+var_B0]; this
0x1802cca2c  call    ??0RESDESCFLAGS@@QEAA@XZ; RESDESCFLAGS::RESDESCFLAGS(void)
0x1802cca31  mov     rax, [rbp+arg_0]
0x1802cca35  mov     eax, [rax+0Ch]
0x1802cca38  mov     rdi, [rbp+arg_8]
0x1802cca3c  mov     rsi, [rbp+arg_10]
0x1802cca40  mov     ecx, eax
0x1802cca42  rep movsb
0x1802cca44  mov     [rsp+0D0h+var_80], 0
0x1802cca4c  mov     rcx, [rbp+arg_0]; this
0x1802cca50  call    ?PresdescFirst@RESDESCTBL@@AEBAPEAVRESDESC@@XZ; RESDESCTBL::PresdescFirst(void)
0x1802cca55  mov     [rsp+0D0h+var_98], rax
0x1802cca5a  mov     [rsp+0D0h+var_68], 0
0x1802cca62  jmp     short loc_1802CCA6E
0x1802cca64  mov     eax, [rsp+0D0h+var_68]
0x1802cca68  inc     eax
0x1802cca6a  mov     [rsp+0D0h+var_68], eax
0x1802cca6e  mov     rax, [rbp+arg_0]
0x1802cca72  movzx   eax, word ptr [rax+0Ah]
0x1802cca76  cmp     [rsp+0D0h+var_68], eax
0x1802cca7a  jnb     loc_1802CD2A0
0x1802cca80  lea     rdx, [rbp+var_24]
0x1802cca84  mov     rcx, [rsp+0D0h+var_98]
0x1802cca89  call    ?Rdflags@RESDESC@@QEBA?AURESDESCFLAGS@@XZ; RESDESC::Rdflags(void)
0x1802cca8e  movzx   eax, word ptr [rax]
0x1802cca91  mov     word ptr [rsp+0D0h+var_9C], ax
0x1802cca96  cmp     [rsp+0D0h+var_80], 0
0x1802cca9b  jz      short loc_1802CCB13
0x1802cca9d  cmp     [rbp+arg_18], 0
0x1802ccaa1  jz      short loc_1802CCADB
0x1802ccaa3  mov     rcx, [rsp+0D0h+var_98]; this
0x1802ccaa8  call    ?MemId@MEMBER_DEFN@@QEBAJXZ; MEMBER_DEFN::MemId(void)
0x1802ccaad  mov     eax, eax
0x1802ccaaf  mov     rcx, [rbp+arg_10]
0x1802ccab3  add     rcx, rax
0x1802ccab6  mov     rax, rcx
0x1802ccab9  mov     [rsp+0D0h+pvargSrc], rax
0x1802ccabe  mov     rcx, [rsp+0D0h+var_98]; this
0x1802ccac3  call    ?GetConstVal@VAR_DEFN@@QEBAJXZ; VAR_DEFN::GetConstVal(void)
0x1802ccac8  mov     eax, eax
0x1802ccaca  mov     rcx, [rbp+arg_8]
0x1802ccace  add     rcx, rax
0x1802ccad1  mov     rax, rcx
0x1802ccad4  mov     [rsp+0D0h+pvargDest], rax
0x1802ccad9  jmp     short loc_1802CCB11
0x1802ccadb  mov     rcx, [rsp+0D0h+var_98]; this
0x1802ccae0  call    ?GetConstVal@VAR_DEFN@@QEBAJXZ; VAR_DEFN::GetConstVal(void)
0x1802ccae5  mov     eax, eax
0x1802ccae7  mov     rcx, [rbp+arg_10]
0x1802ccaeb  add     rcx, rax
0x1802ccaee  mov     rax, rcx
0x1802ccaf1  mov     [rsp+0D0h+pvargSrc], rax
0x1802ccaf6  mov     rcx, [rsp+0D0h+var_98]; this
0x1802ccafb  call    ?MemId@MEMBER_DEFN@@QEBAJXZ; MEMBER_DEFN::MemId(void)
0x1802ccb00  mov     eax, eax
0x1802ccb02  mov     rcx, [rbp+arg_8]
0x1802ccb06  add     rcx, rax
0x1802ccb09  mov     rax, rcx
0x1802ccb0c  mov     [rsp+0D0h+pvargDest], rax
0x1802ccb11  jmp     short loc_1802CCB49
0x1802ccb13  mov     rcx, [rsp+0D0h+var_98]; this
0x1802ccb18  call    ?MemId@MEMBER_DEFN@@QEBAJXZ; MEMBER_DEFN::MemId(void)
0x1802ccb1d  mov     eax, eax
0x1802ccb1f  mov     rcx, [rbp+arg_10]
0x1802ccb23  add     rcx, rax
0x1802ccb26  mov     rax, rcx
0x1802ccb29  mov     [rsp+0D0h+pvargSrc], rax
0x1802ccb2e  mov     rcx, [rsp+0D0h+var_98]; this
0x1802ccb33  call    ?MemId@MEMBER_DEFN@@QEBAJXZ; MEMBER_DEFN::MemId(void)
0x1802ccb38  mov     eax, eax
0x1802ccb3a  mov     rcx, [rbp+arg_8]
0x1802ccb3e  add     rcx, rax
0x1802ccb41  mov     rax, rcx
0x1802ccb44  mov     [rsp+0D0h+pvargDest], rax
0x1802ccb49  lea     rcx, [rsp+0D0h+var_9C]
0x1802ccb4e  call    ?Rdkind@RESDESCFLAGS@@QEBA?AW4RDKIND@@XZ; RESDESCFLAGS::Rdkind(void)
0x1802ccb53  mov     [rsp+0D0h+var_78], eax
0x1802ccb57  cmp     [rsp+0D0h+var_78], 1
0x1802ccb5c  jz      short loc_1802CCB96
0x1802ccb5e  cmp     [rsp+0D0h+var_78], 2
0x1802ccb63  jz      short loc_1802CCBD3
0x1802ccb65  cmp     [rsp+0D0h+var_78], 5
0x1802ccb6a  jz      loc_1802CCC8E
0x1802ccb70  cmp     [rsp+0D0h+var_78], 9
0x1802ccb75  jz      loc_1802CD1D5
0x1802ccb7b  cmp     [rsp+0D0h+var_78], 0Ah
0x1802ccb80  jz      loc_1802CCC1B
0x1802ccb86  cmp     [rsp+0D0h+var_78], 0Bh
0x1802ccb8b  jz      loc_1802CCC6E
0x1802ccb91  jmp     loc_1802CD288
0x1802ccb96  mov     rax, [rsp+0D0h+pvargDest]
0x1802ccb9b  mov     qword ptr [rax], 0
0x1802ccba2  cmp     [rbp+arg_18], 0
0x1802ccba6  jz      short loc_1802CCBBC
0x1802ccba8  mov     rax, [rsp+0D0h+pvargSrc]
0x1802ccbad  mov     rdx, [rax]
0x1802ccbb0  mov     rcx, [rsp+0D0h+pvargDest]
0x1802ccbb5  call    __vbaStrToAnsi
0x1802ccbba  jmp     short loc_1802CCBCE
0x1802ccbbc  mov     rax, [rsp+0D0h+pvargSrc]
0x1802ccbc1  mov     rdx, [rax]
0x1802ccbc4  mov     rcx, [rsp+0D0h+pvargDest]
0x1802ccbc9  call    __vbaStrToUnicode
0x1802ccbce  jmp     loc_1802CD288
0x1802ccbd3  cmp     [rsp+0D0h+var_80], 0
0x1802ccbd8  jnz     short loc_1802CCBE7
0x1802ccbda  mov     rax, [rsp+0D0h+pvargDest]
0x1802ccbdf  movzx   eax, word ptr [rax]
0x1802ccbe2  cmp     eax, 8
0x1802ccbe5  jl      short loc_1802CCC16
0x1802ccbe7  xor     eax, eax
0x1802ccbe9  mov     rcx, [rsp+0D0h+pvargDest]
0x1802ccbee  mov     [rcx], ax
0x1802ccbf1  mov     rdx, [rsp+0D0h+pvargSrc]; pvargSrc
0x1802ccbf6  mov     rcx, [rsp+0D0h+pvargDest]; pvargDest
0x1802ccbfb  call    cs:__imp_VariantCopy
0x1802ccc01  mov     [rsp+0D0h+var_A0], eax
0x1802ccc05  cmp     [rsp+0D0h+var_A0], 0
0x1802ccc0a  jge     short loc_1802CCC16
0x1802ccc0c  jmp     loc_1802CD2A4
0x1802ccc11  jmp     loc_1802CD2A4
0x1802ccc16  jmp     loc_1802CD288
0x1802ccc1b  cmp     [rbp+arg_18], 0
0x1802ccc1f  jz      short loc_1802CCC42
0x1802ccc21  mov     rcx, [rsp+0D0h+var_98]; this
0x1802ccc26  call    ?CchFxStr@RESDESC@@QEBAGXZ; RESDESC::CchFxStr(void)
0x1802ccc2b  movzx   eax, ax
0x1802ccc2e  mov     r8d, eax
0x1802ccc31  mov     rdx, [rsp+0D0h+pvargSrc]
0x1802ccc36  mov     rcx, [rsp+0D0h+pvargDest]
0x1802ccc3b  call    ExFxStrToA
0x1802ccc40  jmp     short loc_1802CCC61
0x1802ccc42  mov     rcx, [rsp+0D0h+var_98]; this
0x1802ccc47  call    ?CchFxStr@RESDESC@@QEBAGXZ; RESDESC::CchFxStr(void)
0x1802ccc4c  movzx   eax, ax
0x1802ccc4f  mov     r8d, eax
0x1802ccc52  mov     rdx, [rsp+0D0h+pvargSrc]
0x1802ccc57  mov     rcx, [rsp+0D0h+pvargDest]
0x1802ccc5c  call    ExFxStrToW
0x1802ccc61  mov     [rsp+0D0h+var_80], 1
0x1802ccc69  jmp     loc_1802CD288
0x1802ccc6e  mov     rcx, [rsp+0D0h+var_98]; this
0x1802ccc73  call    ?CIndir@RESDESC@@QEBAGXZ; RESDESC::CIndir(void)
0x1802ccc78  movzx   eax, ax
0x1802ccc7b  mov     rdi, [rsp+0D0h+pvargDest]
0x1802ccc80  mov     rsi, [rsp+0D0h+pvargSrc]
0x1802ccc85  mov     ecx, eax
0x1802ccc87  rep movsb
0x1802ccc89  jmp     loc_1802CD288
0x1802ccc8e  lea     rdx, [rbp+var_34]
0x1802ccc92  mov     rcx, [rsp+0D0h+var_98]
0x1802ccc97  call    ?RdflagsElem@RESDESC@@QEBA?AURESDESCFLAGS@@XZ; RESDESC::RdflagsElem(void)
0x1802ccc9c  movzx   eax, word ptr [rax]
0x1802ccc9f  mov     [rsp+0D0h+var_B0], ax
0x1802ccca4  mov     al, [rsp+0D0h+var_9C+1]
0x1802ccca8  and     al, 1
0x1802cccaa  movzx   eax, al
0x1802cccad  test    eax, eax
0x1802cccaf  jz      short loc_1802CCCCC
0x1802cccb1  mov     rax, [rsp+0D0h+pvargSrc]
0x1802cccb6  mov     rax, [rax]
0x1802cccb9  mov     [rsp+0D0h+psa], rax
0x1802cccbe  mov     [rsp+0D0h+ppsaOut], 0
0x1802cccc7  jmp     loc_1802CCEF8
0x1802ccccc  mov     rcx, [rsp+0D0h+var_98]; this
0x1802cccd1  call    ?Psa@RESDESC@@QEAAPEAUtagSAFEARRAY@@XZ; RESDESC::Psa(void)
0x1802cccd6  mov     [rsp+0D0h+var_60], rax
0x1802cccdb  mov     rax, [rsp+0D0h+var_60]
0x1802ccce0  movzx   eax, word ptr [rax]
0x1802ccce3  mov     [rsp+0D0h+cDims], eax
0x1802ccce7  lea     rcx, [rsp+0D0h+var_B0]; this
0x1802cccec  call    ?HasResource@RESDESCFLAGS@@QEBAHXZ; RESDESCFLAGS::HasResource(void)
0x1802cccf1  test    eax, eax
0x1802cccf3  jnz     short loc_1802CCD36
0x1802cccf5  lea     rcx, [rsp+0D0h+var_B0]; this
0x1802cccfa  call    ?IsFxStrInRec@RESDESCFLAGS@@QEBAHXZ; RESDESCFLAGS::IsFxStrInRec(void)
0x1802cccff  test    eax, eax
0x1802ccd01  jnz     short loc_1802CCD36
0x1802ccd03  cmp     [rsp+0D0h+var_80], 0
0x1802ccd08  jz      short loc_1802CCD31
0x1802ccd0a  mov     rcx, [rsp+0D0h+var_60]
0x1802ccd0f  call    SafeArrayElemCount
0x1802ccd14  mov     rcx, [rsp+0D0h+var_60]
0x1802ccd19  mov     ecx, [rcx+4]
0x1802ccd1c  imul    ecx, eax
0x1802ccd1f  mov     eax, ecx
0x1802ccd21  mov     eax, eax
0x1802ccd23  mov     rdi, [rsp+0D0h+pvargDest]
0x1802ccd28  mov     rsi, [rsp+0D0h+pvargSrc]
0x1802ccd2d  mov     ecx, eax
0x1802ccd2f  rep movsb
0x1802ccd31  jmp     loc_1802CD288
0x1802ccd36  lea     rdx, [rsp+0D0h+ppsaOut]; ppsaOut
0x1802ccd3b  mov     ecx, [rsp+0D0h+cDims]; cDims
0x1802ccd3f  call    cs:__imp_SafeArrayAllocDescriptor
0x1802ccd45  test    eax, eax
0x1802ccd47  jge     short loc_1802CCD5B
0x1802ccd49  mov     [rsp+0D0h+var_A0], 8007000Eh
0x1802ccd51  jmp     loc_1802CD2A4
0x1802ccd56  jmp     loc_1802CD2A4
0x1802ccd5b  lea     rdx, [rsp+0D0h+psa]; ppsaOut
0x1802ccd60  mov     ecx, [rsp+0D0h+cDims]; cDims
0x1802ccd64  call    cs:__imp_SafeArrayAllocDescriptor
0x1802ccd6a  test    eax, eax
0x1802ccd6c  jge     short loc_1802CCD8B
0x1802ccd6e  mov     [rsp+0D0h+var_A0], 8007000Eh
0x1802ccd76  mov     rcx, [rsp+0D0h+ppsaOut]; psa
0x1802ccd7b  call    cs:__imp_SafeArrayDestroyDescriptor
0x1802ccd81  jmp     loc_1802CD2A4
0x1802ccd86  jmp     loc_1802CD2A4
0x1802ccd8b  mov     ecx, [rsp+0D0h+cDims]
0x1802ccd8f  call    CbSizeOldArrayDesc
0x1802ccd94  mov     eax, eax
0x1802ccd96  mov     rdi, [rsp+0D0h+ppsaOut]
0x1802ccd9b  mov     rsi, [rsp+0D0h+var_60]
0x1802ccda0  mov     ecx, eax
0x1802ccda2  rep movsb
0x1802ccda4  mov     ecx, [rsp+0D0h+cDims]
0x1802ccda8  call    CbSizeOldArrayDesc
0x1802ccdad  mov     eax, eax
0x1802ccdaf  mov     rdi, [rsp+0D0h+psa]
0x1802ccdb4  mov     rsi, [rsp+0D0h+var_60]
0x1802ccdb9  mov     ecx, eax
0x1802ccdbb  rep movsb
0x1802ccdbd  mov     rax, [rsp+0D0h+ppsaOut]
0x1802ccdc2  movzx   eax, word ptr [rax+2]
0x1802ccdc6  and     eax, 0FFFFFF1Fh
0x1802ccdcb  mov     [rsp+0D0h+var_58], eax
0x1802ccdcf  mov     rax, [rsp+0D0h+ppsaOut]
0x1802ccdd4  movzx   ecx, word ptr [rsp+0D0h+var_58]
0x1802ccdd9  mov     [rax+2], cx
0x1802ccddd  mov     rax, [rsp+0D0h+psa]
0x1802ccde2  movzx   ecx, word ptr [rsp+0D0h+var_58]
0x1802ccde7  mov     [rax+2], cx
0x1802ccdeb  mov     rax, [rsp+0D0h+ppsaOut]
0x1802ccdf0  mov     rcx, [rsp+0D0h+pvargDest]
0x1802ccdf5  mov     [rax+10h], rcx
0x1802ccdf9  mov     rax, [rsp+0D0h+psa]
0x1802ccdfe  mov     rcx, [rsp+0D0h+pvargSrc]
0x1802cce03  mov     [rax+10h], rcx
0x1802cce07  mov     al, byte ptr [rsp+0D0h+var_B0]
0x1802cce0b  shr     al, 6
0x1802cce0e  and     al, 1
0x1802cce10  movzx   eax, al
0x1802cce13  test    eax, eax
0x1802cce15  jz      short loc_1802CCE8E
0x1802cce17  mov     rcx, [rsp+0D0h+var_98]; this
0x1802cce1c  call    ?Prtmi@EXFRAME@@QEAAPEAURTMI@@XZ; EXFRAME::Prtmi(void)
0x1802cce21  mov     [rbp+var_50], rax
0x1802cce25  cmp     [rbp+arg_18], 0
0x1802cce29  jz      short loc_1802CCE56
0x1802cce2b  mov     rcx, [rbp+var_50]; this
0x1802cce2f  call    ?CbAlignRec@RESDESCTBL@@QEBAIXZ; RESDESCTBL::CbAlignRec(void)
0x1802cce34  mov     [rbp+var_28], eax
0x1802cce37  mov     rcx, [rbp+var_50]; this
0x1802cce3b  call    ?Hmember@RECTYPE_DEFN@@QEBAKXZ; RECTYPE_DEFN::Hmember(void)
0x1802cce40  mov     ecx, [rbp+var_28]
0x1802cce43  mov     edx, ecx; unsigned int
0x1802cce45  mov     ecx, eax; unsigned int
0x1802cce47  call    ?RoundUp@@YAIII@Z; RoundUp(uint,uint)
0x1802cce4c  mov     rcx, [rsp+0D0h+ppsaOut]
0x1802cce51  mov     [rcx+4], eax
0x1802cce54  jmp     short loc_1802CCE7F
0x1802cce56  mov     rcx, [rbp+var_50]; this
0x1802cce5a  call    ?CbAlignRec@RESDESCTBL@@QEBAIXZ; RESDESCTBL::CbAlignRec(void)
0x1802cce5f  mov     [rbp+var_38], eax
0x1802cce62  mov     rcx, [rbp+var_50]; this
0x1802cce66  call    ?Hmember@RECTYPE_DEFN@@QEBAKXZ; RECTYPE_DEFN::Hmember(void)
0x1802cce6b  mov     ecx, [rbp+var_38]
0x1802cce6e  mov     edx, ecx; unsigned int
0x1802cce70  mov     ecx, eax; unsigned int
0x1802cce72  call    ?RoundUp@@YAIII@Z; RoundUp(uint,uint)
0x1802cce77  mov     rcx, [rsp+0D0h+psa]
0x1802cce7c  mov     [rcx+4], eax
0x1802cce7f  mov     rcx, [rbp+var_50]; this
0x1802cce83  call    ?FSeenFxStrInRec@RESDESCTBL@@QEBAHXZ; RESDESCTBL::FSeenFxStrInRec(void)
0x1802cce88  mov     [rsp+0D0h+var_80], eax
0x1802cce8c  jmp     short loc_1802CCECE
0x1802cce8e  lea     rcx, [rsp+0D0h+var_B0]; this
0x1802cce93  call    ?IsFxStrInRec@RESDESCFLAGS@@QEBAHXZ; RESDESCFLAGS::IsFxStrInRec(void)
0x1802cce98  test    eax, eax
0x1802cce9a  jz      short loc_1802CCECE
0x1802cce9c  cmp     [rbp+arg_18], 0
0x1802ccea0  jz      short loc_1802CCEB9
0x1802ccea2  mov     rcx, [rsp+0D0h+var_98]
0x1802ccea7  call    ?BindKind@EXBIND@@QEBA?AW4BIND_KIND@@XZ; EXBIND::BindKind(void)
0x1802cceac  movzx   eax, ax
0x1802cceaf  mov     rcx, [rsp+0D0h+ppsaOut]
0x1802cceb4  mov     [rcx+4], eax
  ... truncated ...
```
