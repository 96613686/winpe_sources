# CRchTxtPtr::ReplaceRange(long,long,ushort const *,IUndoBuilder *,long,long *,ulong)

- ea: `0x180018390`
- end: `0x180018c95`
- name: `?ReplaceRange@CRchTxtPtr@@QEAAJJJPEBGPEAVIUndoBuilder@@JPEAJK@Z`
- size: `2309`
- prototype: `__int64 __usercall@<rax>(CRchTxtPtr *__hidden this@<rcx>, int@<edx>, int@<r8d>, const unsigned __int16 *@<r9>, struct IUndoBuilder *, int, int *, unsigned int)`
- caller_count: `10`
- callee_count: `33`
- tags: `loader_planting`

## callers

- `0x1800175d0`
- `0x18004cf20`
- `0x180052be8`
- `0x18005361c`
- `0x180054c10`
- `0x18005eb2c`
- `0x18006f360`
- `0x18007147c`
- `0x180071980`
- `0x18007468c`

## callees

- `0x1800062e0`
- `0x1800064d0`
- `0x180006610`
- `0x180009860`
- `0x180010510`
- `0x1800114d0`
- `0x1800165c0`
- `0x180018390`
- `0x180019470`
- `0x1800194c0`
- `0x18001d0b8`
- `0x18001d7a8`
- `0x18001d8b0`
- `0x18001dfd0`
- `0x1800202a0`
- `0x180022780`
- `0x180022c50`
- `0x1800235f0`
- `0x180023ba8`
- `0x180024910`
- `0x180026e20`
- `0x180027f70`
- `0x180037080`
- `0x180037468`
- `0x180038530`
- `0x180039560`
- `0x18003c0bc`
- `0x18003f6c0`
- `0x180041b1c`
- `0x18005bb98`
- `0x18006fec8`
- `0x1800910fe`
- `0x180092010`

## pseudocode

```c
__int64 __fastcall CRchTxtPtr::ReplaceRange(
        CRchTxtPtr *this,
        int a2,
        unsigned int a3,
        unsigned __int16 *a4,
        struct IUndoBuilder *a5,
        int a6,
        int *a7,
        char a8)
{
  unsigned int v8; // r13d
  int v9; // r11d
  __int64 v10; // r15
  int v11; // esi
  unsigned int v13; // edi
  _DWORD *v14; // rax
  __int64 v15; // rdx
  int v16; // ecx
  int v17; // ecx
  __int64 v18; // rax
  CNotifyMgr *v19; // r12
  CRchTxtPtr *v20; // rbx
  unsigned int v21; // r12d
  int v22; // ecx
  int v23; // eax
  int v24; // edi
  int v25; // ebx
  unsigned int v26; // edi
  unsigned __int16 *v27; // r9
  int *v28; // r10
  int v29; // ebx
  int v30; // r11d
  CRchTxtPtr *v31; // rbx
  unsigned int v32; // r12d
  unsigned int v33; // r15d
  int v34; // edx
  int v35; // eax
  int v37; // edx
  int v38; // edx
  CRunPtrBase *v39; // rcx
  int v40; // r8d
  __int64 Format; // rdx
  void *v42; // r11
  __int64 *v43; // rax
  int IsValid; // ebx
  CRunPtrBase *v45; // rcx
  int v46; // edx
  _DWORD *v47; // rax
  struct IAntiEvent *v48; // rax
  struct IAntiEvent *v49; // r9
  int v50; // ecx
  int v51; // eax
  int v52; // ecx
  int v53; // ebx
  __int64 v54; // rcx
  struct IAntiEvent *v55; // rax
  char *v56; // r9
  __int64 v57; // rax
  int v58; // edx
  const struct CParaFormat *PF; // rax
  __int128 v60; // xmm1
  __int128 v61; // xmm0
  int v62; // ebx
  __int16 v63; // ax
  unsigned __int16 v64; // di
  __int16 v65; // ax
  unsigned int v66; // eax
  int v67; // r8d
  int v68; // r9d
  __int16 v69; // di
  const struct CParaFormat *ParaFormat; // rax
  bool v71; // zf
  CObjectMgr *ObjectMgr; // rax
  int TextLength; // eax
  int v74; // r8d
  int v75; // [rsp+60h] [rbp-89h]
  void *Src; // [rsp+68h] [rbp-81h] BYREF
  int v77; // [rsp+70h] [rbp-79h]
  int v78; // [rsp+74h] [rbp-75h] BYREF
  unsigned int v79; // [rsp+78h] [rbp-71h]
  int v80; // [rsp+7Ch] [rbp-6Dh]
  unsigned int v81; // [rsp+80h] [rbp-69h]
  struct IAntiEvent *v82; // [rsp+88h] [rbp-61h] BYREF
  CDisplay *v83; // [rsp+90h] [rbp-59h]
  __int128 v84; // [rsp+98h] [rbp-51h] BYREF
  __int128 v85; // [rsp+A8h] [rbp-41h]
  struct IAntiEvent *v86; // [rsp+B8h] [rbp-31h] BYREF
  __int64 v87; // [rsp+C0h] [rbp-29h]
  _OWORD v88[2]; // [rsp+C8h] [rbp-21h] BYREF
  int v89; // [rsp+130h] [rbp+47h]
  unsigned int v90; // [rsp+130h] [rbp+47h]
  int v91; // [rsp+138h] [rbp+4Fh]
  int v92; // [rsp+138h] [rbp+4Fh]
  int EOP; // [rsp+138h] [rbp+4Fh]

  v8 = *((_DWORD *)this + 8);
  v9 = 0;
  v10 = *((_QWORD *)this + 5);
  v11 = a2;
  v78 = 0;
  v75 = 0;
  v13 = v8;
  v91 = a2;
  v83 = *(CDisplay **)(v10 + 64);
  v77 = 0;
  v79 = v8;
  v14 = (_DWORD *)*((_QWORD *)v83 + 6);
  v81 = v8;
  v80 = 0;
  v87 = v10;
  v82 = 0;
  v86 = 0;
  if ( v14 )
  {
    ++*v14;
  }
  else
  {
    v47 = CW32System::PvAlloc(0x14u, 0x40u);
    if ( v47 )
    {
      v47[4] &= ~1u;
      v9 = 0;
      *v47 = 1;
      v47[1] = 0x3FFFFFFF;
    }
    else
    {
      v9 = 0;
      v47 = 0;
    }
    *((_QWORD *)v83 + 6) = v47;
  }
  v15 = *((_QWORD *)this + 5);
  if ( v15 )
    v16 = *(_DWORD *)(*((_QWORD *)this + 2) + 24LL);
  else
    v16 = 0;
  v17 = v16 - *((_DWORD *)this + 8);
  if ( v11 < 0 || v11 > v17 )
    v11 = v17;
  if ( (*(_BYTE *)(v15 + 180) & 1) != 0 && v11 == v17 )
  {
    v37 = ((*(_DWORD *)(v10 + 180) & 0x80000) != 0) + 1;
    v89 = v37;
    if ( v37 <= v11 )
      v11 -= v37;
    if ( (unsigned int)CRunPtrBase::IsValid((CRchTxtPtr *)((char *)this + 64)) )
    {
      CRunPtrBase::AdjustBackward(v39);
      PF = CRchTxtPtr::GetPF(this);
      v9 = 0;
      if ( (*((_WORD *)PF + 1) & 0x4000) != 0 )
        v89 = 0;
    }
    else
    {
      v89 = v38;
    }
    goto LABEL_10;
  }
  v18 = *((_QWORD *)this + 8);
  v89 = 0;
  if ( !v18 || !*(_DWORD *)(v18 + 8) )
    goto LABEL_10;
  CRunPtrBase::AdjustForward((CRchTxtPtr *)((char *)this + 64));
  if ( !v11 )
  {
    Format = (unsigned int)CFormatRunPtr::GetFormat((CRchTxtPtr *)((char *)this + 64));
    Src = v42;
    if ( (int)Format < 0 )
      Format = (unsigned int)*(__int16 *)(v10 + 278);
    if ( (*(int (__fastcall **)(struct IFormatCache *, __int64, void **))(*(_QWORD *)qword_1800A41E8 + 32LL))(
           qword_1800A41E8,
           Format,
           &Src) >= 0 )
    {
      v43 = (__int64 *)Src;
    }
    else
    {
      v43 = g_defaultPF;
      Src = g_defaultPF;
    }
    if ( (*((_WORD *)v43 + 1) & 0x4000) != 0
      && (unsigned int)CTxtPtr::IsAtEOP((CRchTxtPtr *)((char *)this + 16))
      && (a8 & 8) == 0 )
    {
      goto LABEL_71;
    }
LABEL_68:
    v9 = 0;
    goto LABEL_10;
  }
  v60 = *((_OWORD *)this + 1);
  v88[0] = *((_OWORD *)this + 4);
  v61 = *((_OWORD *)this + 2);
  v84 = v60;
  v85 = v61;
  CTxtPtr::AdvanceCp((CTxtPtr *)&v84, v11);
  CRunPtrBase::AdvanceCp((CRunPtrBase *)v88, v11);
  LODWORD(Src) = 0;
  if ( (unsigned int)CTxtPtr::IsAfterEOP((CTxtPtr *)&v84) )
  {
    LODWORD(Src) = -(int)CTxtPtr::BackupCpCRLF((CTxtPtr *)&v84, 1);
    CTxtPtr::AdvanceCp((CTxtPtr *)&v84, (int)Src);
  }
  EOP = CTxtPtr::FindEOP((CTxtPtr *)&v84, 0x3FFFFFFF, 0);
  if ( !*((_DWORD *)this + 8) || (unsigned int)CTxtPtr::IsAfterEOP((CRchTxtPtr *)((char *)this + 16)) )
  {
    v62 = 1;
    CTxtPtr::AdvanceCp((CTxtPtr *)&v84, *((_DWORD *)this + 8) - v85);
    v91 = v11 + EOP;
  }
  else
  {
    v62 = 0;
    if ( (_DWORD)Src != v11 )
      goto LABEL_114;
    if ( (a8 & 8) == 0 )
    {
      v63 = CFormatRunPtr::GetFormat((CFormatRunPtr *)v88);
      v64 = *((_WORD *)CTxtArray::GetParaFormat((CTxtArray *)(v10 + 248), v63) + 1);
      v65 = CFormatRunPtr::GetFormat((CRchTxtPtr *)((char *)this + 64));
      if ( ((*((_WORD *)CTxtArray::GetParaFormat((CTxtArray *)(v10 + 248), v65) + 1) | v64) & 0x4000) != 0 )
      {
LABEL_71:
        CDisplay::Thaw(v83);
        return 0;
      }
      v13 = v8;
    }
    if ( HIDWORD(v88[0]) )
    {
LABEL_114:
      v91 = v11 + EOP;
    }
    else
    {
      v75 = EOP;
      v66 = EOP + v8;
      v91 = v11 + EOP;
      v81 = v66;
    }
    CTxtPtr::AdvanceCp((CTxtPtr *)&v84, *((_DWORD *)this + 8) - v85);
    v77 = CTxtPtr::FindEOP((CTxtPtr *)&v84, -1073741823, 0);
  }
  CFormatRunPtr::GetFormat((CFormatRunPtr *)v88);
  LODWORD(Src) = CFormatRunPtr::GetFormat((CRchTxtPtr *)((char *)this + 64));
  if ( v67 == (_DWORD)Src )
    goto LABEL_68;
  if ( !v62 && !v75 )
  {
    v75 = v68;
    v79 = v68 + v8;
  }
  v69 = *((_WORD *)CTxtArray::GetParaFormat((CTxtArray *)(v10 + 248), v67) + 1);
  ParaFormat = CTxtArray::GetParaFormat((CTxtArray *)(v10 + 248), (int)Src);
  v9 = 0;
  v71 = ((*((_BYTE *)ParaFormat + 2) ^ (unsigned __int8)v69) & 1) == 0;
  v13 = v79;
  if ( !v71 )
    v80 = 1;
LABEL_10:
  if ( !(v11 + a3) )
  {
    if ( a7 )
      *a7 = v9;
    goto LABEL_71;
  }
  v19 = (CNotifyMgr *)(v10 + 128);
  if ( v10 != -128 )
  {
    v20 = *(CRchTxtPtr **)v19;
    if ( *(_QWORD *)v19 )
    {
      v21 = v81;
      do
      {
        if ( v20 != this )
          (**(void (__fastcall ***)(CRchTxtPtr *, _QWORD, _QWORD, _QWORD, unsigned int, int))v20)(
            v20,
            v8,
            (unsigned int)v11,
            a3,
            v13,
            v21 + v11);
        v20 = (CRchTxtPtr *)*((_QWORD *)v20 + 1);
      }
      while ( v20 );
      v10 = v87;
      v19 = (CNotifyMgr *)(v87 + 128);
    }
  }
  if ( a6 >= 0 )
    CRchTxtPtr::Check_rpCF(this);
  if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)this + 5) + 8LL) + 32LL))(*((_QWORD *)this + 5) + 8LL) )
  {
    ObjectMgr = CTxtEdit::GetObjectMgr((CTxtEdit *)v10);
    CObjectMgr::ReplaceRange(ObjectMgr, v8, v11, a5);
  }
  if ( (*(_BYTE *)(v10 + 192) & 1) != 0 )
  {
    v40 = 0;
    if ( v80 )
      v40 = v75;
    v24 = v11 + v89;
    v23 = CRchTxtPtr::ExpandRangeFormatting(this, v11 + v89, v40, &v78);
    v22 = v89;
  }
  else
  {
    v22 = v89;
    v23 = 0;
    v24 = v89 + v11;
  }
  v25 = CRchTxtPtr::ReplaceRangeFormatting(this, v24, v22 + a3, a6, a5, &v82, &v86, v75, v77, v91, v23, v78);
  if ( v89 )
  {
    CRunPtrBase::AdvanceCp((CRchTxtPtr *)((char *)this + 48), -v89);
    CRunPtrBase::AdvanceCp((CRchTxtPtr *)((char *)this + 64), -v89);
  }
  v26 = 0;
  if ( v25 >= 0 )
  {
    v27 = a4;
    v28 = (int *)((char *)this + 16);
    v29 = a3;
    Src = a4;
    v90 = a3;
    if ( v11 < 0 )
    {
      TextLength = CTxtPtr::GetTextLength((CRchTxtPtr *)((char *)this + 16));
      v30 = TextLength - v28[4];
      v92 = v30;
    }
    else
    {
      v30 = v11;
      v92 = v11;
    }
    if ( a5 )
    {
      CTxtPtr::HandleReplaceRangeUndo((CTxtPtr *)v28, v30, a3, a5, v82, v86);
      v30 = v92;
      v28 = (int *)((char *)this + 16);
      v27 = (unsigned __int16 *)Src;
    }
    if ( v30 <= 0 )
    {
LABEL_32:
      if ( v29 <= 0 )
      {
        if ( v30 > 0 )
LABEL_83:
          CTxtPtr::DeleteRange((CTxtPtr *)v28, v30);
      }
      else
      {
LABEL_33:
        v26 += CTxtPtr::InsertRange((CTxtPtr *)v28, v29, v27);
      }
      if ( v26 != a3 )
      {
        if ( v19 )
          CNotifyMgr::NotifyPreReplaceRange(v19, 0, -2, 0, 0, 0, 0);
        CTxtStory::DeleteFormatRuns((CTxtStory *)(v10 + 248));
      }
      goto LABEL_35;
    }
    while ( 1 )
    {
      if ( v29 <= 0 )
        goto LABEL_83;
      v48 = (struct IAntiEvent *)CArrayBase::Elem(*(CArrayBase **)v28, v28[2]);
      v82 = v48;
      if ( !v48 )
        goto LABEL_33;
      CTxtBlk::MoveGap(v48, v28[3]);
      v30 = v92;
      v28 = (int *)((char *)this + 16);
      v49 = v82;
      v50 = *(_DWORD *)v82 - *((_DWORD *)this + 7);
      if ( v92 < v50 )
        v50 = v92;
      if ( v50 > 0 )
      {
        v30 = v92 - v50;
        *(_DWORD *)v82 -= v50;
        v92 -= v50;
        *(_DWORD *)(*(_QWORD *)v28 + 24LL) -= v50;
      }
      v51 = *((_DWORD *)v49 + 5) / 2 - *(_DWORD *)v49;
      v52 = v51 - 128;
      if ( v51 <= 128 )
        v52 = *((_DWORD *)v49 + 5) / 2 - *(_DWORD *)v49;
      v78 = v52;
      if ( v52 > v29 )
        break;
      if ( v52 > 0 )
        goto LABEL_94;
      v27 = (unsigned __int16 *)Src;
LABEL_95:
      v58 = v28[2];
      if ( v58 < *(_DWORD *)(*(_QWORD *)v28 + 8LL) - 1 )
      {
        if ( v30 )
        {
          *((_QWORD *)v28 + 1) = (unsigned int)(v58 + 1);
          if ( v30 > 0 )
            continue;
        }
      }
      goto LABEL_32;
    }
    v52 = v29;
    v78 = v29;
LABEL_94:
    v53 = 2 * v52;
    memmove_0((void *)(*((_QWORD *)v49 + 1) + 2LL * *((int *)this + 7)), Src, 2 * v52);
    v54 = (unsigned int)v78;
    v28 = (int *)((char *)this + 16);
    v55 = v82;
    v26 += v78;
    *((_DWORD *)this + 8) += v78;
    *((_DWORD *)this + 7) += v54;
    v56 = (char *)Src;
    *((_DWORD *)v55 + 4) += v53;
    *(_DWORD *)v55 += v54;
    v90 -= v54;
    v57 = *((_QWORD *)this + 2);
    v27 = (unsigned __int16 *)&v56[2 * v54];
    v29 = v90;
    v30 = v92;
    Src = v27;
    *(_DWORD *)(v57 + 24) += v54;
    goto LABEL_95;
  }
LABEL_35:
  if ( (*(_BYTE *)(v10 + 192) & 1) != 0 && (signed int)v8 <= *(_DWORD *)(v10 + 220) && (v11 || v26) )
  {
    IsValid = CRunPtrBase::IsValid((CRchTxtPtr *)((char *)this + 48));
    CTxtEdit::SetContextDirection((CTxtEdit *)v10, 0);
    if ( !IsValid )
    {
      if ( (unsigned int)CRunPtrBase::IsValid((CRchTxtPtr *)((char *)this + 48)) )
      {
        v46 = *((_DWORD *)this + 8);
        *((_QWORD *)v45 + 1) = 0;
        CRunPtrBase::AdvanceCp(v45, v46);
      }
    }
  }
  if ( v19 )
  {
    v31 = *(CRchTxtPtr **)v19;
    if ( *(_QWORD *)v19 )
    {
      v32 = v79;
      v33 = v81;
      do
      {
        if ( v31 != this )
          (*(void (__fastcall **)(CRchTxtPtr *, _QWORD, _QWORD, _QWORD, unsigned int, unsigned int))(*(_QWORD *)v31 + 8LL))(
            v31,
            v8,
            (unsigned int)v11,
            v26,
            v32,
            v33 + v11);
        v31 = (CRchTxtPtr *)*((_QWORD *)v31 + 1);
      }
      while ( v31 );
      v10 = v87;
    }
  }
  CCallMgr::SetChangeEvent(*(_QWORD *)(v10 + 144), 1);
  v34 = v80;
  if ( a7 )
  {
    v35 = 0;
    if ( v80 )
      v35 = v75;
    *a7 = v35;
  }
  if ( (*(_DWORD *)(v10 + 192) & 0x61086013) != 0 )
  {
    if ( (a8 & 2) == 0 && ((*(_DWORD *)(v10 + 180) & 0x10000) == 0 || a4 && *a4 == 0xFFFC) )
    {
      v74 = 0;
      if ( v34 )
        v74 = v75;
      CRchTxtPtr::ItemizeReplaceRange(this, a3, v74, a5, 0);
    }
    else
    {
      *(_WORD *)(v10 + 188) |= 8u;
    }
  }
  CDisplay::Thaw(v83);
  return v26;
}

```

## disassembly

```asm
0x180018390  mov     [rsp-8+arg_18], r9
0x180018395  mov     [rsp-8+arg_10], r8d
0x18001839a  push    rbp
0x18001839b  push    rbx
0x18001839c  push    rsi
0x18001839d  push    rdi
0x18001839e  push    r13
0x1800183a0  push    r14
0x1800183a2  push    r15
0x1800183a4  lea     rbp, [rsp-7]
0x1800183a9  sub     rsp, 0F0h
0x1800183b0  mov     r13d, [rcx+20h]
0x1800183b4  xor     r11d, r11d
0x1800183b7  mov     r15, [rcx+28h]
0x1800183bb  mov     esi, edx
0x1800183bd  mov     r14, rcx
0x1800183c0  mov     [rbp+37h+var_AC], r11d
0x1800183c4  mov     [rsp+120h+var_C0], r11d
0x1800183c9  mov     edi, r13d
0x1800183cc  mov     [rbp+37h+arg_8], edx
0x1800183cf  mov     rax, [r15+40h]
0x1800183d3  mov     [rbp+37h+var_90], rax
0x1800183d7  mov     [rbp+37h+var_B0], r11d
0x1800183db  mov     [rbp+37h+var_A8], r13d
0x1800183df  mov     rax, [rax+30h]
0x1800183e3  mov     [rbp+37h+var_A0], r13d
0x1800183e7  mov     [rbp+37h+var_A4], r11d
0x1800183eb  mov     [rbp+37h+var_60], r15
0x1800183ef  mov     [rbp+37h+var_98], r11
0x1800183f3  mov     [rbp+37h+var_68], r11
0x1800183f7  test    rax, rax
0x1800183fa  jz      loc_180018800
0x180018400  inc     dword ptr [rax]
0x180018402  mov     rdx, [r14+28h]
0x180018406  test    rdx, rdx
0x180018409  jz      loc_18001896A
0x18001840f  mov     rax, [r14+10h]
0x180018413  mov     ecx, [rax+18h]
0x180018416  sub     ecx, [r14+20h]
0x18001841a  test    esi, esi
0x18001841c  js      loc_18001899A
0x180018422  cmp     esi, ecx
0x180018424  jg      loc_18001899A
0x18001842a  test    byte ptr [rdx+0B4h], 1
0x180018431  mov     [rsp+120h+var_38], r12
0x180018439  jnz     loc_1800186AD
0x18001843f  mov     rax, [r14+40h]
0x180018443  mov     [rbp+37h+arg_0], r11d
0x180018447  test    rax, rax
0x18001844a  jz      short loc_180018456
0x18001844c  cmp     dword ptr [rax+8], 0
0x180018450  jnz     loc_180018712
0x180018456  mov     eax, [rbp+37h+arg_10]
0x180018459  add     eax, esi
0x18001845b  jz      loc_18001877F
0x180018461  lea     r12, [r15+80h]
0x180018468  test    r12, r12
0x18001846b  jz      short loc_1800184BC
0x18001846d  mov     rbx, [r12]
0x180018471  test    rbx, rbx
0x180018474  jz      short loc_1800184BC
0x180018476  mov     r12d, [rbp+37h+var_A0]
0x18001847a  mov     r15d, [rbp+37h+arg_10]
0x18001847e  xchg    ax, ax
0x180018480  cmp     rbx, r14
0x180018483  jz      short loc_1800184A8
0x180018485  mov     rax, [rbx]
0x180018488  lea     ecx, [r12+rsi]
0x18001848c  mov     dword ptr [rsp+120h+var_F8], ecx
0x180018490  mov     r9d, r15d
0x180018493  mov     r8d, esi
0x180018496  mov     dword ptr [rsp+120h+var_100], edi
0x18001849a  mov     edx, r13d
0x18001849d  mov     rcx, rbx
0x1800184a0  mov     rax, [rax]
0x1800184a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184a8  mov     rbx, [rbx+8]
0x1800184ac  test    rbx, rbx
0x1800184af  jnz     short loc_180018480
0x1800184b1  mov     r15, [rbp+37h+var_60]
0x1800184b5  lea     r12, [r15+80h]
0x1800184bc  mov     ebx, [rbp+37h+arg_28]
0x1800184bf  test    ebx, ebx
0x1800184c1  js      short loc_1800184CB
0x1800184c3  mov     rcx, r14; this
0x1800184c6  call    ?Check_rpCF@CRchTxtPtr@@QEAAHXZ; CRchTxtPtr::Check_rpCF(void)
0x1800184cb  mov     rcx, [r14+28h]
0x1800184cf  add     rcx, 8
0x1800184d3  mov     rax, [rcx]
0x1800184d6  mov     rax, [rax+20h]
0x1800184da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184df  test    eax, eax
0x1800184e1  jnz     loc_180018B93
0x1800184e7  test    byte ptr [r15+0C0h], 1
0x1800184ef  jnz     loc_1800186EA
0x1800184f5  mov     ecx, [rbp+37h+arg_0]
0x1800184f8  xor     eax, eax
0x1800184fa  lea     edi, [rcx+rsi]
0x1800184fd  mov     r8d, [rbp+37h+arg_10]
0x180018501  mov     r9d, ebx; int
0x180018504  add     r8d, ecx; int
0x180018507  mov     edx, edi; int
0x180018509  mov     ecx, [rbp+37h+var_AC]
0x18001850c  mov     [rsp+120h+var_C8], ecx; int
0x180018510  mov     rcx, r14; this
0x180018513  mov     [rsp+120h+var_D0], eax; int
0x180018517  mov     eax, [rbp+37h+arg_8]
0x18001851a  mov     [rsp+120h+var_D8], eax; int
0x18001851e  mov     eax, [rbp+37h+var_B0]
0x180018521  mov     [rsp+120h+var_E0], eax; int
0x180018525  mov     eax, [rsp+120h+var_C0]
0x180018529  mov     [rsp+120h+var_E8], eax; int
0x18001852d  lea     rax, [rbp+37h+var_68]
0x180018531  mov     [rsp+120h+var_F0], rax; struct IAntiEvent **
0x180018536  lea     rax, [rbp+37h+var_98]
0x18001853a  mov     [rsp+120h+var_F8], rax; struct IAntiEvent **
0x18001853f  mov     rax, [rbp+37h+arg_20]
0x180018543  mov     [rsp+120h+var_100], rax; struct IUndoBuilder *
0x180018548  call    ?ReplaceRangeFormatting@CRchTxtPtr@@AEAAJJJJPEAVIUndoBuilder@@PEAPEAVIAntiEvent@@1JJJJJ@Z; CRchTxtPtr::ReplaceRangeFormatting(long,long,long,IUndoBuilder *,IAntiEvent * *,IAntiEvent * *,long,long,long,long,long)
0x18001854d  mov     edi, [rbp+37h+arg_0]
0x180018550  mov     ebx, eax
0x180018552  test    edi, edi
0x180018554  jnz     loc_180018BB2
0x18001855a  xor     edi, edi
0x18001855c  test    ebx, ebx
0x18001855e  js      short loc_1800185B7
0x180018560  mov     r9, [rbp+37h+arg_18]
0x180018564  lea     r10, [r14+10h]
0x180018568  mov     ebx, [rbp+37h+arg_10]
0x18001856b  mov     [rsp+120h+Src], r9
0x180018570  mov     [rbp+37h+arg_0], ebx
0x180018573  test    esi, esi
0x180018575  js      loc_180018BCF
0x18001857b  mov     r11d, esi
0x18001857e  mov     [rbp+37h+arg_8], esi
0x180018581  mov     rcx, [rbp+37h+arg_20]
0x180018585  test    rcx, rcx
0x180018588  jnz     loc_180018BE7
0x18001858e  test    r11d, r11d
0x180018591  jg      loc_180018852
0x180018597  test    ebx, ebx
0x180018599  jle     loc_180018839
0x18001859f  mov     r8, r9; unsigned __int16 *
0x1800185a2  mov     edx, ebx; int
0x1800185a4  mov     rcx, r10; this
0x1800185a7  call    ?InsertRange@CTxtPtr@@AEAAJJPEBG@Z; CTxtPtr::InsertRange(long,ushort const *)
0x1800185ac  add     edi, eax
0x1800185ae  cmp     edi, [rbp+37h+arg_10]
0x1800185b1  jnz     loc_180018C2F
0x1800185b7  test    byte ptr [r15+0C0h], 1
0x1800185bf  jnz     loc_1800187A3
0x1800185c5  test    r12, r12
0x1800185c8  jz      short loc_180018617
0x1800185ca  mov     rbx, [r12]
0x1800185ce  test    rbx, rbx
0x1800185d1  jz      short loc_180018617
0x1800185d3  mov     r12d, [rbp+37h+var_A8]
0x1800185d7  mov     r15d, [rbp+37h+var_A0]
0x1800185db  nop     dword ptr [rax+rax+00h]
0x1800185e0  cmp     rbx, r14
0x1800185e3  jz      short loc_18001860A
0x1800185e5  mov     rax, [rbx]
0x1800185e8  lea     ecx, [r15+rsi]
0x1800185ec  mov     dword ptr [rsp+120h+var_F8], ecx
0x1800185f0  mov     r9d, edi
0x1800185f3  mov     r8d, esi
0x1800185f6  mov     dword ptr [rsp+120h+var_100], r12d
0x1800185fb  mov     edx, r13d
0x1800185fe  mov     rcx, rbx
0x180018601  mov     rax, [rax+8]
0x180018605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001860a  mov     rbx, [rbx+8]
0x18001860e  test    rbx, rbx
0x180018611  jnz     short loc_1800185E0
0x180018613  mov     r15, [rbp+37h+var_60]
0x180018617  mov     rcx, [r15+90h]
0x18001861e  mov     edx, 1
0x180018623  call    ?SetChangeEvent@CCallMgr@@QEAAXW4CHANGETYPE@@@Z; CCallMgr::SetChangeEvent(CHANGETYPE)
0x180018628  mov     r9, [rbp+37h+arg_30]
0x18001862c  mov     edx, [rbp+37h+var_A4]
0x18001862f  mov     ecx, [rsp+120h+var_C0]
0x180018633  test    r9, r9
0x180018636  jz      short loc_180018642
0x180018638  xor     eax, eax
0x18001863a  test    edx, edx
0x18001863c  cmovnz  eax, ecx
0x18001863f  mov     [r9], eax
0x180018642  test    dword ptr [r15+0C0h], 61086013h
0x18001864d  jz      short loc_180018688
0x18001864f  test    byte ptr [rbp+37h+arg_38], 2
0x180018653  jnz     short loc_18001867F
0x180018655  test    dword ptr [r15+0B4h], 10000h
0x180018660  jz      loc_180018C70
0x180018666  mov     rax, [rbp+37h+arg_18]
0x18001866a  test    rax, rax
0x18001866d  jz      short loc_18001867F
0x18001866f  mov     r8d, 0FFFCh
0x180018675  cmp     [rax], r8w
0x180018679  jz      loc_180018C70
0x18001867f  or      word ptr [r15+0BCh], 8
0x180018688  mov     rcx, [rbp+37h+var_90]; this
0x18001868c  call    ?Thaw@CDisplay@@QEAAXXZ; CDisplay::Thaw(void)
0x180018691  mov     eax, edi
0x180018693  mov     r12, [rsp+120h+var_38]
0x18001869b  add     rsp, 0F0h
0x1800186a2  pop     r15
0x1800186a4  pop     r14
0x1800186a6  pop     r13
0x1800186a8  pop     rdi
0x1800186a9  pop     rsi
0x1800186aa  pop     rbx
0x1800186ab  pop     rbp
0x1800186ac  retn
0x1800186ad  cmp     esi, ecx
0x1800186af  jnz     loc_18001843F
0x1800186b5  test    dword ptr [r15+0B4h], 80000h
0x1800186c0  mov     edx, r11d
0x1800186c3  setnz   dl
0x1800186c6  inc     edx
0x1800186c8  mov     [rbp+37h+arg_0], edx
0x1800186cb  cmp     edx, esi
0x1800186cd  jg      short loc_1800186D1
0x1800186cf  sub     esi, edx
0x1800186d1  lea     rcx, [r14+40h]; this
0x1800186d5  call    ?IsValid@CRunPtrBase@@QEBAHXZ; CRunPtrBase::IsValid(void)
0x1800186da  test    eax, eax
0x1800186dc  jnz     loc_180018972
0x1800186e2  mov     [rbp+37h+arg_0], edx
0x1800186e5  jmp     loc_180018456
0x1800186ea  mov     edi, [rbp+37h+arg_0]
0x1800186ed  lea     r9, [rbp+37h+var_AC]; int *
0x1800186f1  xor     r8d, r8d
0x1800186f4  mov     rcx, r14; this
0x1800186f7  cmp     [rbp+37h+var_A4], r8d
0x1800186fb  cmovnz  r8d, [rsp+120h+var_C0]; int
0x180018701  add     edi, esi
0x180018703  mov     edx, edi; int
0x180018705  call    ?ExpandRangeFormatting@CRchTxtPtr@@QEAAJJJAEAJ@Z; CRchTxtPtr::ExpandRangeFormatting(long,long,long &)
0x18001870a  mov     ecx, [rbp+37h+arg_0]
0x18001870d  jmp     loc_1800184FD
0x180018712  lea     rcx, [r14+40h]; this
0x180018716  call    ?AdjustForward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustForward(void)
0x18001871b  test    esi, esi
0x18001871d  jnz     loc_1800189A1
0x180018723  lea     rcx, [r14+40h]; this
0x180018727  call    ?GetFormat@CFormatRunPtr@@QEBAFXZ; CFormatRunPtr::GetFormat(void)
0x18001872c  movsx   edx, ax
0x18001872f  mov     [rsp+120h+Src], r11
0x180018734  test    edx, edx
0x180018736  jns     short loc_180018740
0x180018738  movsx   edx, word ptr [r15+116h]
0x180018740  mov     rcx, cs:qword_1800A41E8
0x180018747  lea     r8, [rsp+120h+Src]
0x18001874c  mov     rax, [rcx]
0x18001874f  mov     rax, [rax+20h]
0x180018753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018758  test    eax, eax
0x18001875a  jns     short loc_18001879C
0x18001875c  lea     rax, ?g_defaultPF@@3VCParaFormat@@A; CParaFormat g_defaultPF
0x180018763  mov     [rsp+120h+Src], rax
0x180018768  mov     ecx, 4000h
0x18001876d  test    [rax+2], cx
0x180018771  jnz     loc_180018B6B
0x180018777  xor     r11d, r11d
0x18001877a  jmp     loc_180018456
0x18001877f  mov     rax, [rbp+37h+arg_30]
0x180018783  test    rax, rax
0x180018786  jnz     loc_180018B8B
0x18001878c  mov     rcx, [rbp+37h+var_90]; this
0x180018790  call    ?Thaw@CDisplay@@QEAAXXZ; CDisplay::Thaw(void)
0x180018795  xor     eax, eax
0x180018797  jmp     loc_180018693
0x18001879c  mov     rax, [rsp+120h+Src]
0x1800187a1  jmp     short loc_180018768
0x1800187a3  cmp     r13d, [r15+0DCh]
0x1800187aa  jg      loc_1800185C5
0x1800187b0  test    esi, esi
0x1800187b2  jnz     short loc_1800187BC
0x1800187b4  test    edi, edi
0x1800187b6  jz      loc_1800185C5
0x1800187bc  lea     rcx, [r14+30h]; this
0x1800187c0  call    ?IsValid@CRunPtrBase@@QEBAHXZ; CRunPtrBase::IsValid(void)
0x1800187c5  xor     edx, edx; int
0x1800187c7  mov     rcx, r15; this
0x1800187ca  mov     ebx, eax
0x1800187cc  call    ?SetContextDirection@CTxtEdit@@QEAAXH@Z; CTxtEdit::SetContextDirection(int)
0x1800187d1  test    ebx, ebx
0x1800187d3  jnz     loc_1800185C5
0x1800187d9  lea     rcx, [r14+30h]; this
0x1800187dd  call    ?IsValid@CRunPtrBase@@QEBAHXZ; CRunPtrBase::IsValid(void)
0x1800187e2  test    eax, eax
0x1800187e4  jz      loc_1800185C5
0x1800187ea  mov     edx, [r14+20h]; int
0x1800187ee  mov     qword ptr [rcx+8], 0
0x1800187f6  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x1800187fb  jmp     loc_1800185C5
0x180018800  mov     edx, 40h ; '@'; unsigned int
0x180018805  mov     ecx, 14h; unsigned int
0x18001880a  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x18001880f  test    rax, rax
  ... truncated ...
```
