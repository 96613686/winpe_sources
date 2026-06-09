# CRTFRead::ReadRtf(void)

- ea: `0x180002044`
- end: `0x1800026b2`
- name: `?ReadRtf@CRTFRead@@QEAAJXZ`
- size: `1646`
- prototype: `__int64 __fastcall(CRTFRead *__hidden this)`
- caller_count: `1`
- callee_count: `39`
- tags: `file_ops, installer_update`

## callers

- `0x18001ebcc`

## callees

- `0x180001490`
- `0x1800014e0`
- `0x180001598`
- `0x180001630`
- `0x180001c50`
- `0x180002044`
- `0x1800026c0`
- `0x1800165c0`
- `0x180017860`
- `0x180017ef0`
- `0x180018ea8`
- `0x18001d0b8`
- `0x1800202a0`
- `0x180020740`
- `0x180022780`
- `0x180023010`
- `0x180023ba8`
- `0x180024910`
- `0x180031974`
- `0x180032c68`
- `0x18003b9a4`
- `0x18003dfc0`
- `0x18003eba8`
- `0x180045358`
- `0x1800455c4`
- `0x180045f54`
- `0x180046378`
- `0x180048e00`
- `0x180048eac`
- `0x18004a0c8`
- `0x18004b528`
- `0x18004d1ac`
- `0x18007204c`
- `0x180074954`
- `0x180076900`
- `0x180084114`
- `0x180084140`
- `0x1800841c0`
- `0x180092010`

## pseudocode

```c
__int64 __fastcall CRTFRead::ReadRtf(CRTFRead *this)
{
  __int64 v1; // r15
  CTxtEdit **v3; // rdi
  void *v4; // rax
  unsigned int v5; // eax
  int v6; // eax
  const struct CParaFormat *PF; // rax
  __int64 v8; // xmm1_8
  _OWORD *v9; // r14
  __int128 v10; // xmm1
  int v11; // r12d
  unsigned __int8 *v12; // rax
  unsigned __int8 v13; // dl
  __int64 v14; // rcx
  unsigned __int16 Keyword; // ax
  __int16 v16; // cx
  __int128 v17; // xmm1
  int EOP; // eax
  struct CDocInfo *DocInfo; // rsi
  int v20; // eax
  unsigned int v21; // esi
  unsigned int v22; // edx
  int v23; // edi
  __int128 v24; // xmm1
  int v25; // esi
  __int64 v26; // rdi
  __int64 v27; // rdi
  int v28; // r8d
  void **v29; // rsi
  int *v30; // r14
  CTxtEdit **v31; // rdi
  CTxtEdit *v32; // rax
  int v33; // ecx
  int v34; // esi
  _DWORD *v35; // rdx
  _DWORD *v36; // rcx
  __int64 v37; // rdx
  _BYTE v39[36]; // [rsp+30h] [rbp-38h] BYREF

  v1 = *((_QWORD *)this + 8);
  *((_DWORD *)this + 172) = *(_DWORD *)(v1 + 40);
  if ( !(unsigned int)CRTFRead::InitLex(this) )
    goto LABEL_78;
  v3 = (CTxtEdit **)((char *)this + 56);
  if ( (*((_DWORD *)this + 20) & 0x8000) == 0 )
    CTxtEdit::InitDocInfo(*v3);
  *(_WORD *)(v1 + 98) |= 8u;
  v4 = CW32System::PvAlloc(0x402u, 0x40u);
  *((_QWORD *)this + 84) = v4;
  if ( v4 )
  {
    v5 = *((_DWORD *)this + 20);
    *((_DWORD *)this + 170) = 513;
    if ( (v5 & 0x20) != 0 )
      v6 = HIWORD(v5);
    else
      v6 = -1;
    *((_DWORD *)this + 147) = v6;
    PF = CRchTxtPtr::GetPF((CRchTxtPtr *)(v1 + 8));
    *(_OWORD *)((char *)this + 244) = *(_OWORD *)PF;
    *(_OWORD *)((char *)this + 260) = *((_OWORD *)PF + 1);
    *(_OWORD *)((char *)this + 276) = *((_OWORD *)PF + 2);
    v8 = *((_QWORD *)PF + 6);
    *((_WORD *)this + 236) &= ~0x400u;
    *(_QWORD *)((char *)this + 292) = v8;
    LOWORD(PF) = (*((_WORD *)this + 123) >> 4) & 0x400;
    *((_DWORD *)this + 75) = -671089153;
    *((_WORD *)this + 236) |= (unsigned __int16)PF;
    *((_WORD *)this + 131) = -1;
    CRTFRead::GetChar(this);
    CRTFRead::UngetChar(this);
    if ( !(unsigned int)IsRTF(*((char **)this + 23)) )
    {
      if ( (*((_DWORD *)*v3 + 45) & 0x80000) == 0 )
      {
        *((_DWORD *)this + 12) = 16;
        goto LABEL_67;
      }
      *((_WORD *)this + 236) |= 0x200u;
    }
    v9 = (_OWORD *)(v1 + 24);
    *((_DWORD *)this + 58) = *((_DWORD *)this + 172);
    if ( !(unsigned int)CTxtPtr::IsAfterEOP((CTxtPtr *)(v1 + 24)) )
    {
      v10 = *(_OWORD *)(v1 + 40);
      *(_OWORD *)v39 = *v9;
      *(_OWORD *)&v39[16] = v10;
      CTxtPtr::FindEOP((CTxtPtr *)v39, -1073741823, 0);
      *((_DWORD *)this + 58) = *(_DWORD *)&v39[16];
    }
    v11 = *((_DWORD *)this + 58);
    do
    {
      *((_WORD *)this + 67) = *((_WORD *)this + 66);
      *((_WORD *)this + 66) = 260;
      while ( *((_QWORD *)this + 23) != *((_QWORD *)this + 24) || (unsigned int)CRTFRead::FillBuffer(this) )
      {
        v12 = (unsigned __int8 *)*((_QWORD *)this + 23);
        v13 = *v12;
        *((_QWORD *)this + 23) = v12 + 1;
        if ( !v13 )
          goto LABEL_27;
        if ( v13 != 10 && v13 != 13 )
        {
          if ( v13 != 92 )
          {
            if ( v13 == 123 )
            {
              *((_WORD *)this + 66) = 261;
              goto LABEL_38;
            }
            if ( v13 == 125 )
            {
              *((_WORD *)this + 66) = 262;
              goto LABEL_38;
            }
            goto LABEL_29;
          }
          Keyword = CRTFRead::TokenGetKeyword(this);
LABEL_34:
          *((_WORD *)this + 66) = Keyword;
          goto LABEL_38;
        }
      }
      *((_DWORD *)this + 12) = 15;
LABEL_27:
      if ( *((_DWORD *)this + 12) == 15 )
        continue;
      v13 = 32;
LABEL_29:
      v14 = *((_QWORD *)this + 27);
      if ( v14 )
      {
        v16 = *(_WORD *)(v14 + 10);
        if ( (unsigned __int16)(v16 - 7) > 1u )
        {
          Keyword = CRTFRead::TokenGetText(this, v13);
          goto LABEL_34;
        }
        *((_WORD *)this + 66) = v16 + 256;
        CRTFRead::UngetChar(this);
      }
      else if ( (*((_DWORD *)*v3 + 45) & 0x80000) != 0 )
      {
        *((_DWORD *)this + 12) = 16;
      }
LABEL_38:
      ;
    }
    while ( (unsigned __int16)(*((_WORD *)this + 66) - 259) > 1u
         && !(unsigned int)CRTFRead::HandleToken(this)
         && *((_QWORD *)this + 27) );
    if ( *((_DWORD *)this + 79) && *((_DWORD *)this + 12) == 18 )
    {
      v17 = *(_OWORD *)(v1 + 40);
      *(_OWORD *)v39 = *v9;
      *(_OWORD *)&v39[16] = v17;
      EOP = CTxtPtr::FindEOP((CTxtPtr *)v39, -1073741823, 0);
      CTxtRange::Set((CTxtRange *)v1, *(_DWORD *)(v1 + 40), -EOP);
      CTxtRange::Delete(v1, 0, 0);
    }
    *((_QWORD *)this + 39) = 0;
    *(_WORD *)(v1 + 98) &= ~8u;
    CTxtRange::Update_iFormat((CTxtRange *)v1, -1);
    if ( (*((_DWORD *)this + 20) & 0x8000) == 0 )
    {
      if ( *(_DWORD *)(v1 + 40) == (unsigned int)CTxtEdit::GetAdjustedTextLength(*v3) )
      {
        *((_DWORD *)this + 75) &= 0xFFFFE7FF;
        CRTFRead::Apply_PF(this);
        CRchTxtPtr::ExtendFormattingCRLF((CRchTxtPtr *)(v1 + 8));
      }
      DocInfo = CTxtEdit::GetDocInfo(*v3);
      if ( !DocInfo )
      {
        *((_DWORD *)this + 12) = 9;
        goto LABEL_67;
      }
      if ( !*((_DWORD *)this + 12) )
        CTxtRange::DeleteTerminatingEOP((CTxtRange *)v1, 0);
      v20 = *((_DWORD *)this + 147);
      if ( v20 == -1 )
        LOWORD(v20) = -1;
      *((_WORD *)DocInfo + 9) = v20;
      if ( (_WORD)v20 == 0xFDE9 )
        *((_WORD *)DocInfo + 9) = 1252;
      v21 = 65534;
      v22 = 65534;
      if ( *((_WORD *)this + 240) != 0xFFFF )
        v22 = *((unsigned __int16 *)this + 240);
      CTxtEdit::SetDefaultLCID(*v3, v22);
      if ( *((_WORD *)this + 241) != 0xFFFF )
        v21 = *((unsigned __int16 *)this + 241);
      CTxtEdit::SetDefaultLCIDFE(*v3, v21);
      (*(void (__fastcall **)(__int64))(*((_QWORD *)*v3 + 2) + 112LL))((__int64)*v3 + 16);
      CTxtEdit::SetDocumentType(*v3, *((unsigned __int8 *)this + 474));
    }
    if ( (*((_DWORD *)*v3 + 48) & 0x61086013) != 0 )
    {
      v23 = *(_DWORD *)(v1 + 40);
      if ( v23 > v11 )
      {
        if ( (unsigned int)CTxtPtr::IsAtEOP((CTxtPtr *)(v1 + 24)) )
        {
          v25 = v23;
        }
        else
        {
          v24 = *(_OWORD *)(v1 + 40);
          *(_OWORD *)v39 = *(_OWORD *)(v1 + 24);
          *(_OWORD *)&v39[16] = v24;
          CTxtPtr::FindEOP((CTxtPtr *)v39, 0x3FFFFFFF, 0);
          v25 = *(_DWORD *)&v39[16];
          CTxtRange::Advance((CTxtRange *)v1, *(_DWORD *)&v39[16] - v23);
        }
        CRchTxtPtr::ItemizeReplaceRange((CRchTxtPtr *)(v1 + 8), v25 - v11, 0, 0, 0);
        if ( v25 != v23 )
          CTxtRange::SetCp((CTxtRange *)v1, v23);
      }
    }
    goto LABEL_67;
  }
  CCallMgr::SetOutOfMemory(*((CCallMgr **)*v3 + 18));
  *((_DWORD *)this + 12) = 9;
LABEL_67:
  CRTFRead::FreeRtfObject(this);
  v26 = *((_QWORD *)this + 27);
  if ( v26 )
  {
    if ( !*((_DWORD *)this + 12) )
      *((_DWORD *)this + 12) = 12;
    while ( *(_QWORD *)(v26 + 40) )
    {
      v26 = *(_QWORD *)(v26 + 40);
      ReleaseFormats(*(__int16 *)(v26 + 2), -1);
    }
  }
  v27 = *((_QWORD *)this + 28);
  if ( v27 )
  {
    while ( *(_QWORD *)(v27 + 40) )
    {
      STATE::DeletePF((STATE *)v27);
      v27 = *(_QWORD *)(v27 + 40);
      CW32System::FreePv(*(void **)(v27 + 32));
    }
    STATE::DeletePF((STATE *)v27);
  }
  CW32System::FreePv((void *)v27);
  CW32System::FreePv(*((void **)this + 84));
  CW32System::FreePv(*((void **)this + 75));
  CW32System::FreePv(*((void **)this + 77));
LABEL_78:
  CRTFRead::DeinitLex(this);
  v29 = (void **)((char *)this + 696);
  v30 = (int *)*((_QWORD *)this + 87);
  v31 = (CTxtEdit **)((char *)this + 56);
  if ( v30 )
  {
    v32 = *v31;
    if ( (*((_DWORD *)*v31 + 44) & 0x2000000) != 0 )
    {
      v33 = *((_DWORD *)this + 177);
      if ( v33 > 0 )
      {
        memset(v39, 0, 24);
        *(_DWORD *)&v39[24] = v33;
        *(_QWORD *)&v39[28] = v30;
        if ( (*((_DWORD *)v32 + 45) & 0x80000) != 0 )
        {
          v34 = 0;
          do
          {
            *v30 = CTxtEdit::GetAcpFromCp(*v31, *v30, v28);
            ++v34;
            ++v30;
          }
          while ( v34 < *((_DWORD *)this + 177) );
          v31 = (CTxtEdit **)((char *)this + 56);
          v29 = (void **)((char *)this + 696);
        }
        CTxtEdit::TxNotify(*v31, 0x70Au, v39);
      }
    }
    CW32System::FreePv(*v29);
    *v29 = 0;
  }
  v35 = (_DWORD *)((char *)this + 48);
  if ( *((_DWORD *)this + 12) )
  {
    if ( *v35 == 18 )
    {
      CCallMgr::SetMaxText(*((CCallMgr **)*v31 + 18));
      v36 = (_DWORD *)((char *)this + 48);
      *(_DWORD *)(*((_QWORD *)this + 9) + 8LL) = -2147286928;
    }
    else
    {
      v36 = (_DWORD *)((char *)this + 48);
    }
    if ( *v35 == 15 )
      *(_DWORD *)(*((_QWORD *)this + 9) + 8LL) = -2147024858;
    else
      v36 = v35;
    v37 = *((_QWORD *)this + 9);
    if ( !*(_DWORD *)(v37 + 8) && *v36 != 21 )
      *(_DWORD *)(v37 + 8) = -*v36;
  }
  return (unsigned int)(*(_DWORD *)(v1 + 40) - *((_DWORD *)this + 172));
}

```

## disassembly

```asm
0x180002044  push    rbp
0x180002046  push    rbx
0x180002047  push    rsi
0x180002048  push    rdi
0x180002049  push    r12
0x18000204b  push    r13
0x18000204d  push    r14
0x18000204f  push    r15
0x180002051  mov     rbp, rsp
0x180002054  sub     rsp, 68h
0x180002058  mov     r15, [rcx+40h]
0x18000205c  mov     rbx, rcx
0x18000205f  mov     eax, [r15+28h]
0x180002063  mov     [rcx+2B0h], eax
0x180002069  call    ?InitLex@CRTFRead@@AEAAHXZ; CRTFRead::InitLex(void)
0x18000206e  mov     r12d, 1
0x180002074  test    eax, eax
0x180002076  jz      loc_18000259E
0x18000207c  test    dword ptr [rbx+50h], 8000h
0x180002083  lea     rdi, [rbx+38h]
0x180002087  jnz     short loc_180002091
0x180002089  mov     rcx, [rdi]; this
0x18000208c  call    ?InitDocInfo@CTxtEdit@@QEAAJXZ; CTxtEdit::InitDocInfo(void)
0x180002091  or      word ptr [r15+62h], 8
0x180002097  mov     edx, 40h ; '@'; unsigned int
0x18000209c  mov     ecx, 402h; unsigned int
0x1800020a1  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x1800020a6  or      esi, 0FFFFFFFFh
0x1800020a9  mov     [rbx+2A0h], rax
0x1800020b0  test    rax, rax
0x1800020b3  jnz     short loc_1800020D0
0x1800020b5  mov     rcx, [rdi]
0x1800020b8  mov     rcx, [rcx+90h]; this
0x1800020bf  call    ?SetOutOfMemory@CCallMgr@@QEAAXXZ; CCallMgr::SetOutOfMemory(void)
0x1800020c4  mov     dword ptr [rbx+30h], 9
0x1800020cb  jmp     loc_180002506
0x1800020d0  mov     eax, [rbx+50h]
0x1800020d3  mov     dword ptr [rbx+2A8h], 201h
0x1800020dd  test    al, 20h
0x1800020df  jz      short loc_1800020E6
0x1800020e1  shr     eax, 10h
0x1800020e4  jmp     short loc_1800020E9
0x1800020e6  or      eax, 0FFFFFFFFh
0x1800020e9  lea     rcx, [r15+8]; this
0x1800020ed  mov     [rbx+24Ch], eax
0x1800020f3  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x1800020f8  mov     ecx, 400h
0x1800020fd  movups  xmm0, xmmword ptr [rax]
0x180002100  movups  xmmword ptr [rbx+0F4h], xmm0
0x180002107  movups  xmm1, xmmword ptr [rax+10h]
0x18000210b  movups  xmmword ptr [rbx+104h], xmm1
0x180002112  movups  xmm0, xmmword ptr [rax+20h]
0x180002116  movups  xmmword ptr [rbx+114h], xmm0
0x18000211d  movsd   xmm1, qword ptr [rax+30h]
0x180002122  mov     eax, 0FBFFh
0x180002127  and     [rbx+1D8h], ax
0x18000212e  movsd   qword ptr [rbx+124h], xmm1
0x180002136  movzx   eax, word ptr [rbx+0F6h]
0x18000213d  shr     ax, 4
0x180002141  and     ax, cx
0x180002144  mov     dword ptr [rbx+12Ch], 0D7FFFDFFh
0x18000214e  or      [rbx+1D8h], ax
0x180002155  mov     rcx, rbx; this
0x180002158  mov     [rbx+106h], si
0x18000215f  call    ?GetChar@CRTFRead@@AEAAEXZ; CRTFRead::GetChar(void)
0x180002164  mov     rcx, rbx; this
0x180002167  call    ?UngetChar@CRTFRead@@AEAAHXZ; CRTFRead::UngetChar(void)
0x18000216c  mov     rcx, [rbx+0B8h]; char *
0x180002173  call    ?IsRTF@@YAHPEAD@Z; IsRTF(char *)
0x180002178  test    eax, eax
0x18000217a  jnz     short loc_18000219B
0x18000217c  mov     rax, [rdi]
0x18000217f  test    dword ptr [rax+0B4h], 80000h
0x180002189  jz      loc_180002260
0x18000218f  mov     eax, 200h
0x180002194  or      [rbx+1D8h], ax
0x18000219b  mov     eax, [rbx+2B0h]
0x1800021a1  lea     r14, [r15+18h]
0x1800021a5  mov     rcx, r14; this
0x1800021a8  mov     [rbx+0E8h], eax
0x1800021ae  call    ?IsAfterEOP@CTxtPtr@@QEAAHXZ; CTxtPtr::IsAfterEOP(void)
0x1800021b3  test    eax, eax
0x1800021b5  jnz     short loc_1800021E2
0x1800021b7  movups  xmm0, xmmword ptr [r14]
0x1800021bb  xor     r8d, r8d; int *
0x1800021be  mov     edx, 0C0000001h; int
0x1800021c3  movups  xmm1, xmmword ptr [r14+10h]
0x1800021c8  lea     rcx, [rbp+var_38]; this
0x1800021cc  movups  [rbp+var_38], xmm0
0x1800021d0  movups  [rbp+var_28], xmm1
0x1800021d4  call    ?FindEOP@CTxtPtr@@QEAAJJPEAJ@Z; CTxtPtr::FindEOP(long,long *)
0x1800021d9  mov     eax, dword ptr [rbp+var_28]
0x1800021dc  mov     [rbx+0E8h], eax
0x1800021e2  mov     r12d, [rbx+0E8h]
0x1800021e9  mov     r13d, 1
0x1800021ef  movzx   eax, word ptr [rbx+84h]
0x1800021f6  mov     [rbx+86h], ax
0x1800021fd  mov     word ptr [rbx+84h], 104h
0x180002206  mov     rax, [rbx+0C0h]
0x18000220d  cmp     [rbx+0B8h], rax
0x180002214  jnz     short loc_180002222
0x180002216  mov     rcx, rbx; this
0x180002219  call    ?FillBuffer@CRTFRead@@AEAAJXZ; CRTFRead::FillBuffer(void)
0x18000221e  test    eax, eax
0x180002220  jz      short loc_18000226C
0x180002222  mov     rax, [rbx+0B8h]
0x180002229  mov     dl, [rax]
0x18000222b  inc     rax
0x18000222e  mov     [rbx+0B8h], rax
0x180002235  test    dl, dl
0x180002237  jz      short loc_180002273
0x180002239  cmp     dl, 0Ah
0x18000223c  jz      short loc_180002206
0x18000223e  cmp     dl, 0Dh
0x180002241  jz      short loc_180002206
0x180002243  cmp     dl, 5Ch ; '\'
0x180002246  jz      short loc_1800022AA
0x180002248  cmp     dl, 7Bh ; '{'
0x18000224b  jz      short loc_18000229F
0x18000224d  cmp     dl, 7Dh ; '}'
0x180002250  jnz     short loc_18000227B
0x180002252  mov     word ptr [rbx+84h], 106h
0x18000225b  jmp     loc_1800022E9
0x180002260  mov     dword ptr [rbx+30h], 10h
0x180002267  jmp     loc_180002506
0x18000226c  mov     dword ptr [rbx+30h], 0Fh
0x180002273  cmp     dword ptr [rbx+30h], 0Fh
0x180002277  jz      short loc_1800022E9
0x180002279  mov     dl, 20h ; ' '; unsigned __int8
0x18000227b  mov     rcx, [rbx+0D8h]
0x180002282  test    rcx, rcx
0x180002285  jnz     short loc_1800022BB
0x180002287  mov     rax, [rdi]
0x18000228a  test    dword ptr [rax+0B4h], 80000h
0x180002294  jz      short loc_1800022E9
0x180002296  mov     dword ptr [rbx+30h], 10h
0x18000229d  jmp     short loc_1800022E9
0x18000229f  mov     word ptr [rbx+84h], 105h
0x1800022a8  jmp     short loc_1800022E9
0x1800022aa  mov     rcx, rbx; this
0x1800022ad  call    ?TokenGetKeyword@CRTFRead@@AEAAGXZ; CRTFRead::TokenGetKeyword(void)
0x1800022b2  mov     [rbx+84h], ax
0x1800022b9  jmp     short loc_1800022E9
0x1800022bb  movzx   ecx, word ptr [rcx+0Ah]
0x1800022bf  lea     eax, [rcx-7]
0x1800022c2  cmp     ax, r13w
0x1800022c6  jbe     short loc_1800022D2
0x1800022c8  mov     rcx, rbx; this
0x1800022cb  call    ?TokenGetText@CRTFRead@@AEAAGE@Z; CRTFRead::TokenGetText(uchar)
0x1800022d0  jmp     short loc_1800022B2
0x1800022d2  mov     eax, 100h
0x1800022d7  add     cx, ax
0x1800022da  mov     [rbx+84h], cx
0x1800022e1  mov     rcx, rbx; this
0x1800022e4  call    ?UngetChar@CRTFRead@@AEAAHXZ; CRTFRead::UngetChar(void)
0x1800022e9  movzx   eax, word ptr [rbx+84h]
0x1800022f0  mov     ecx, 103h
0x1800022f5  sub     ax, cx
0x1800022f8  cmp     ax, r13w
0x1800022fc  jbe     short loc_180002318
0x1800022fe  mov     rcx, rbx; this
0x180002301  call    ?HandleToken@CRTFRead@@AEAAHXZ; CRTFRead::HandleToken(void)
0x180002306  test    eax, eax
0x180002308  jnz     short loc_180002318
0x18000230a  cmp     qword ptr [rbx+0D8h], 0
0x180002312  jnz     loc_1800021EF
0x180002318  cmp     dword ptr [rbx+13Ch], 0
0x18000231f  jz      short loc_180002367
0x180002321  cmp     dword ptr [rbx+30h], 12h
0x180002325  jnz     short loc_180002367
0x180002327  movups  xmm0, xmmword ptr [r14]
0x18000232b  xor     r8d, r8d; int *
0x18000232e  mov     edx, 0C0000001h; int
0x180002333  movups  xmm1, xmmword ptr [r14+10h]
0x180002338  lea     rcx, [rbp+var_38]; this
0x18000233c  movups  [rbp+var_38], xmm0
0x180002340  movups  [rbp+var_28], xmm1
0x180002344  call    ?FindEOP@CTxtPtr@@QEAAJJPEAJ@Z; CTxtPtr::FindEOP(long,long *)
0x180002349  mov     edx, [r15+28h]; int
0x18000234d  neg     eax
0x18000234f  mov     r8d, eax; int
0x180002352  mov     rcx, r15; this
0x180002355  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x18000235a  xor     r8d, r8d
0x18000235d  xor     edx, edx
0x18000235f  mov     rcx, r15
0x180002362  call    ?Delete@CTxtRange@@QEAAXPEAVIUndoBuilder@@W4SELRR@@@Z; CTxtRange::Delete(IUndoBuilder *,SELRR)
0x180002367  mov     eax, 0FFF7h
0x18000236c  mov     qword ptr [rbx+138h], 0
0x180002377  and     [r15+62h], ax
0x18000237c  mov     edx, esi; int
0x18000237e  mov     rcx, r15; this
0x180002381  call    ?Update_iFormat@CTxtRange@@QEAAXJ@Z; CTxtRange::Update_iFormat(long)
0x180002386  test    dword ptr [rbx+50h], 8000h
0x18000238d  jnz     loc_18000247F
0x180002393  mov     rcx, [rdi]; this
0x180002396  call    ?GetAdjustedTextLength@CTxtEdit@@QEAAJXZ; CTxtEdit::GetAdjustedTextLength(void)
0x18000239b  cmp     [r15+28h], eax
0x18000239f  jnz     short loc_1800023BC
0x1800023a1  and     dword ptr [rbx+12Ch], 0FFFFE7FFh
0x1800023ab  mov     rcx, rbx; this
0x1800023ae  call    ?Apply_PF@CRTFRead@@AEAAXXZ; CRTFRead::Apply_PF(void)
0x1800023b3  lea     rcx, [r15+8]; this
0x1800023b7  call    ?ExtendFormattingCRLF@CRchTxtPtr@@QEAAXXZ; CRchTxtPtr::ExtendFormattingCRLF(void)
0x1800023bc  mov     rcx, [rdi]; this
0x1800023bf  call    ?GetDocInfo@CTxtEdit@@QEAAPEAVCDocInfo@@XZ; CTxtEdit::GetDocInfo(void)
0x1800023c4  mov     rsi, rax
0x1800023c7  test    rax, rax
0x1800023ca  jnz     short loc_1800023D8
0x1800023cc  mov     dword ptr [rbx+30h], 9
0x1800023d3  jmp     loc_180002503
0x1800023d8  cmp     dword ptr [rbx+30h], 0
0x1800023dc  jnz     short loc_1800023E8
0x1800023de  xor     edx, edx; struct IUndoBuilder *
0x1800023e0  mov     rcx, r15; this
0x1800023e3  call    ?DeleteTerminatingEOP@CTxtRange@@QEAAXPEAVIUndoBuilder@@@Z; CTxtRange::DeleteTerminatingEOP(IUndoBuilder *)
0x1800023e8  mov     eax, [rbx+24Ch]
0x1800023ee  or      edx, 0FFFFFFFFh
0x1800023f1  cmp     eax, edx
0x1800023f3  mov     ecx, 0FFFFh
0x1800023f8  cmovz   eax, ecx
0x1800023fb  mov     ecx, 0FDE9h
0x180002400  mov     [rsi+12h], ax
0x180002404  cmp     ax, cx
0x180002407  jnz     short loc_18000240F
0x180002409  mov     word ptr [rsi+12h], 4E4h
0x18000240f  movzx   eax, word ptr [rbx+1E0h]
0x180002416  mov     esi, 0FFFEh
0x18000241b  cmp     ax, dx
0x18000241e  mov     edx, esi
0x180002420  jz      short loc_180002424
0x180002422  mov     edx, eax; unsigned int
0x180002424  mov     rcx, [rdi]; this
0x180002427  call    ?SetDefaultLCID@CTxtEdit@@QEAAJK@Z; CTxtEdit::SetDefaultLCID(ulong)
0x18000242c  movzx   eax, word ptr [rbx+1E2h]
0x180002433  or      ecx, 0FFFFFFFFh
0x180002436  cmp     ax, cx
0x180002439  jz      short loc_18000243D
0x18000243b  mov     esi, eax
0x18000243d  mov     rcx, [rdi]; this
0x180002440  mov     edx, esi; unsigned int
0x180002442  call    ?SetDefaultLCIDFE@CTxtEdit@@QEAAJK@Z; CTxtEdit::SetDefaultLCIDFE(ulong)
0x180002447  movsx   eax, word ptr [rbx+1E4h]
0x18000244e  mov     rcx, [rdi]
0x180002451  add     rcx, 10h
0x180002455  movd    xmm1, eax
0x180002459  cvtdq2ps xmm1, xmm1
0x18000245c  mov     rdx, [rcx]
0x18000245f  mov     rax, [rdx+70h]
0x180002463  mulss   xmm1, cs:__real@3d4ccccd
0x18000246b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002470  movzx   edx, byte ptr [rbx+1DAh]; int
0x180002477  mov     rcx, [rdi]; this
0x18000247a  call    ?SetDocumentType@CTxtEdit@@QEAAJJ@Z; CTxtEdit::SetDocumentType(long)
0x18000247f  mov     rax, [rdi]
0x180002482  test    dword ptr [rax+0C0h], 61086013h
0x18000248c  jz      short loc_180002503
0x18000248e  mov     edi, [r15+28h]
0x180002492  cmp     edi, r12d
0x180002495  jle     short loc_180002503
0x180002497  mov     rcx, r14; this
0x18000249a  call    ?IsAtEOP@CTxtPtr@@QEAAHXZ; CTxtPtr::IsAtEOP(void)
0x18000249f  test    eax, eax
0x1800024a1  jnz     short loc_1800024D7
0x1800024a3  movups  xmm0, xmmword ptr [r15+18h]
0x1800024a8  xor     r8d, r8d; int *
0x1800024ab  mov     edx, 3FFFFFFFh; int
0x1800024b0  movups  xmm1, xmmword ptr [r15+28h]
0x1800024b5  lea     rcx, [rbp+var_38]; this
0x1800024b9  movups  [rbp+var_38], xmm0
0x1800024bd  movups  [rbp+var_28], xmm1
0x1800024c1  call    ?FindEOP@CTxtPtr@@QEAAJJPEAJ@Z; CTxtPtr::FindEOP(long,long *)
0x1800024c6  mov     esi, dword ptr [rbp+var_28]
0x1800024c9  mov     rcx, r15; this
0x1800024cc  mov     edx, esi
0x1800024ce  sub     edx, edi; int
0x1800024d0  call    ?Advance@CTxtRange@@QEAAJJ@Z; CTxtRange::Advance(long)
0x1800024d5  jmp     short loc_1800024D9
0x1800024d7  mov     esi, edi
0x1800024d9  mov     edx, esi
0x1800024db  mov     [rsp+68h+var_48], 0; int
0x1800024e3  sub     edx, r12d; int
0x1800024e6  lea     rcx, [r15+8]; this
0x1800024ea  xor     r9d, r9d; struct IUndoBuilder *
0x1800024ed  xor     r8d, r8d; int
0x1800024f0  call    ?ItemizeReplaceRange@CRchTxtPtr@@QEAAHJJPEAVIUndoBuilder@@H@Z; CRchTxtPtr::ItemizeReplaceRange(long,long,IUndoBuilder *,int)
0x1800024f5  cmp     esi, edi
0x1800024f7  jz      short loc_180002503
0x1800024f9  mov     edx, edi; int
0x1800024fb  mov     rcx, r15; this
0x1800024fe  call    ?SetCp@CTxtRange@@QEAAJJ@Z; CTxtRange::SetCp(long)
0x180002503  mov     r12d, r13d
0x180002506  mov     rcx, rbx; this
0x180002509  call    ?FreeRtfObject@CRTFRead@@AEAAXXZ; CRTFRead::FreeRtfObject(void)
0x18000250e  mov     rdi, [rbx+0D8h]
0x180002515  xor     r13d, r13d
0x180002518  test    rdi, rdi
0x18000251b  jz      short loc_180002542
0x18000251d  cmp     [rbx+30h], r13d
0x180002521  jnz     short loc_18000253C
  ... truncated ...
```
