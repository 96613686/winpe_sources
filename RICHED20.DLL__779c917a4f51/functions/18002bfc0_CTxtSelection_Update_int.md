# CTxtSelection::Update(int)

- ea: `0x18002bfc0`
- end: `0x18002c572`
- name: `?Update@CTxtSelection@@UEAAHH@Z`
- size: `1458`
- prototype: `__int64 __fastcall(CTxtSelection *__hidden this, int)`
- caller_count: `0`
- callee_count: `30`
- tags: `installer_update`

## callees

- `0x1800064d0`
- `0x180009860`
- `0x18000c070`
- `0x18000d670`
- `0x180010510`
- `0x1800110b0`
- `0x1800165c0`
- `0x180017860`
- `0x180017ef0`
- `0x18001aa50`
- `0x180026e20`
- `0x180027d38`
- `0x18002bfc0`
- `0x18002c578`
- `0x18002c604`
- `0x18002c890`
- `0x180039560`
- `0x18003c4f4`
- `0x180043f80`
- `0x180044094`
- `0x180047d6c`
- `0x180049cf4`
- `0x18004a070`
- `0x18004a0c8`
- `0x18005fb54`
- `0x18005fc48`
- `0x18005fc94`
- `0x18005fd44`
- `0x180072018`
- `0x180092010`

## pseudocode

```c
__int64 __fastcall CTxtSelection::Update(CTxtSelection *this, int a2)
{
  int v3; // ecx
  CTxtPtr *v4; // r14
  int v5; // esi
  __int64 v6; // rbx
  unsigned int v7; // r13d
  int v8; // r13d
  int v9; // edx
  __int16 Format; // ax
  __int64 v11; // rdx
  __int64 *v12; // rcx
  __int64 v13; // xmm0_8
  int v14; // eax
  int v15; // edx
  int v16; // ebx
  int v17; // r13d
  __int16 v18; // cx
  int v19; // esi
  int *v20; // r8
  int *v21; // r9
  int v22; // r14d
  int IsCollapsed; // r12d
  int v24; // esi
  int CchLeft; // eax
  int v26; // eax
  int v27; // edx
  int v28; // r12d
  int ExpandedBackward; // ebx
  int v30; // r14d
  int v31; // edx
  int v32; // ecx
  __int128 v33; // xmm0
  int v34; // esi
  int v35; // ebx
  int UnhiddenForward; // ebx
  int v37; // edx
  int v38; // ecx
  unsigned int v39; // ebx
  __int64 v40; // rax
  int v41; // ecx
  int v43; // [rsp+30h] [rbp-38h]
  int v44; // [rsp+34h] [rbp-34h]
  __int64 v45; // [rsp+38h] [rbp-30h]
  __int128 v46; // [rsp+40h] [rbp-28h] BYREF
  __int64 v47; // [rsp+50h] [rbp-18h]
  int v48; // [rsp+B0h] [rbp+48h] BYREF
  int v49; // [rsp+B8h] [rbp+50h]
  int v50; // [rsp+C0h] [rbp+58h]
  int v51; // [rsp+C8h] [rbp+60h] BYREF

  v49 = a2;
  v3 = *((_DWORD *)this + 22);
  v44 = v3;
  v4 = (CTxtSelection *)((char *)this + 24);
  if ( *((_QWORD *)this + 6) )
    v5 = *(_DWORD *)(*(_QWORD *)v4 + 24LL);
  else
    v5 = 0;
  v6 = *((_QWORD *)this + 6);
  v7 = *((unsigned __int16 *)this + 49);
  v45 = v6;
  v50 = v5;
  v51 = 0;
  v48 = 0;
  if ( !v3 )
    CTxtSelection::UpdateForAutoWord(this);
  if ( (*(_DWORD *)(v6 + 180) & 0x10008) != 8 )
    return 1;
  v8 = (v7 >> 6) & 1;
  v43 = v8;
  if ( *((_DWORD *)this + 22) )
  {
    if ( (*((_WORD *)this + 49) & 0x180) != 0 )
    {
      if ( (*((_WORD *)CTxtSelection::GetPF(this) + 1) & 0x4000) != 0
        || (v9 = -*((_DWORD *)this + 22),
            v46 = *(_OWORD *)((char *)this + 72),
            CRunPtrBase::AdvanceCp((CRunPtrBase *)&v46, v9),
            Format = CFormatRunPtr::GetFormat((CFormatRunPtr *)&v46),
            (*((_WORD *)CTxtArray::GetParaFormat((CTxtArray *)(v6 + 248), Format) + 1) & 0x4000) != 0) )
      {
        CTxtRange::Expander(this, (~(unsigned __int8)*((_WORD *)this + 49) & 0x80 | 0x40u) >> 4, 1, 0, &v51, &v48);
      }
    }
  }
  if ( (*(_WORD *)(*((_QWORD *)this + 6) + 184LL) & 0x2000) != 0
    && (*(_DWORD *)(v6 + 180) & 0x200) == 0
    && (unsigned int)CRunPtrBase::IsValid((CTxtSelection *)((char *)this + 72)) )
  {
    v13 = *v12;
    DWORD2(v46) = *((_DWORD *)v12 + 2);
    v14 = *((_DWORD *)v12 + 3);
    v47 = v11;
    *(_QWORD *)&v46 = v13;
    HIDWORD(v46) = v14;
    CTxtRange::GetRange(this, &v51, &v48);
    v15 = *((_DWORD *)this + 22);
    if ( !v15 )
    {
      v28 = v50;
      goto LABEL_44;
    }
    v16 = v51;
    v17 = v48;
    if ( !v51 && v48 >= v5 )
    {
      v28 = v50;
LABEL_43:
      v8 = v43;
LABEL_44:
      if ( !*((_DWORD *)this + 22) && (unsigned int)CPFRunPtr::IsCollapsed((CPFRunPtr *)&v46) )
      {
        if ( v8 )
          ExpandedBackward = CPFRunPtr::FindExpandedBackward((CPFRunPtr *)&v46);
        else
          ExpandedBackward = 0;
        if ( (unsigned int)CPFRunPtr::IsCollapsed((CPFRunPtr *)&v46) )
          ExpandedBackward = CPFRunPtr::FindExpanded((CPFRunPtr *)&v46);
        *((_WORD *)this + 49) &= ~1u;
        CTxtRange::Advance(this, ExpandedBackward);
        CRunPtrBase::AdjustForward((CRunPtrBase *)&v46);
        if ( ExpandedBackward <= 0
          && (unsigned int)CPFRunPtr::IsCollapsed((CPFRunPtr *)&v46)
          && (unsigned int)CTxtPtr::IsAfterEOP(v4) )
        {
          CTxtRange::BackupCRLF(this, 1);
        }
        *((_DWORD *)this + 34) &= ~1u;
      }
      goto LABEL_59;
    }
    v18 = *((_WORD *)this + 49);
    v19 = *((_DWORD *)this + 10);
    if ( (v18 & 0x80u) != 0 )
    {
      v20 = &v51;
      v21 = &v48;
      if ( ((v18 & 0x40) != 0) != v15 < 0 )
      {
        if ( (v18 & 0x40) != 0 )
          v21 = 0;
        else
          v20 = 0;
      }
      CTxtRange::Expander(this, 4, 1, 0, v20, v21);
      v16 = v51;
      v17 = v48;
    }
    v22 = v16;
    CRunPtrBase::AdvanceCp((CRunPtrBase *)&v46, v16 - v19);
    if ( (unsigned int)CPFRunPtr::IsCollapsed((CPFRunPtr *)&v46) )
      v16 += CPFRunPtr::FindExpandedBackward((CPFRunPtr *)&v46);
    CRunPtrBase::AdjustForward((CRunPtrBase *)&v46);
    IsCollapsed = CPFRunPtr::IsCollapsed((CPFRunPtr *)&v46);
    CRunPtrBase::AdvanceCp((CRunPtrBase *)&v46, v48 - v16);
    if ( (unsigned int)CPFRunPtr::IsCollapsed((CPFRunPtr *)&v46) )
    {
      v24 = 0;
      do
      {
        if ( !(unsigned int)CPFRunPtr::IsCollapsed((CPFRunPtr *)&v46) )
          break;
        CchLeft = CRunPtrBase::GetCchLeft((CRunPtrBase *)&v46);
        HIDWORD(v46) += CchLeft;
        v24 += CchLeft;
      }
      while ( (unsigned int)CRunPtrBase::NextRun((CRunPtrBase *)&v46) );
      v48 += v24;
    }
    if ( IsCollapsed )
    {
      v28 = v50;
    }
    else
    {
      v26 = CPFRunPtr::IsCollapsed((CPFRunPtr *)&v46);
      v27 = v48;
      v28 = v50;
      if ( !v26 || v48 >= v50 )
        goto LABEL_39;
    }
    if ( (unsigned int)CPFRunPtr::IsCollapsed((CPFRunPtr *)&v46) )
    {
      CRunPtrBase::AdvanceCp((CRunPtrBase *)&v46, v16 - v48);
      CRunPtrBase::AdjustForward((CRunPtrBase *)&v46);
      v27 = v16;
      v48 = v16;
    }
    else
    {
      v27 = v48;
      v16 = v48;
    }
LABEL_39:
    if ( v16 != v22 || v27 != v17 )
      CTxtRange::Set(this, v27, v27 - v16);
    v4 = (CTxtSelection *)((char *)this + 24);
    goto LABEL_43;
  }
  v28 = v50;
LABEL_59:
  v30 = *((_DWORD *)this + 10);
  v31 = v30;
  v32 = *((_DWORD *)this + 22);
  v33 = *(_OWORD *)((char *)this + 56);
  v47 = *((_QWORD *)this + 6);
  v34 = v30 - v32;
  v46 = v33;
  if ( v32 < 0 )
  {
    v31 = v30 - v32;
    v34 = v30;
  }
  v48 = v31;
  if ( v32 && (v34 || v31 < v28) )
  {
    CRunPtrBase::AdvanceCp((CRunPtrBase *)&v46, v34 - v30);
    v35 = CCFRunPtr::IsInHidden((CCFRunPtr *)&v46);
    CRunPtrBase::AdvanceCp((CRunPtrBase *)&v46, v48 - v34);
    if ( v35 || (unsigned int)CCFRunPtr::IsInHidden((CCFRunPtr *)&v46) && v48 < v28 )
      CTxtRange::Collapser(this, 0);
  }
  if ( !*((_DWORD *)this + 22) && v30 && (unsigned int)CCFRunPtr::IsInHidden((CCFRunPtr *)&v46) )
  {
    if ( !v8
      || (UnhiddenForward = CCFRunPtr::FindUnhiddenBackward((CCFRunPtr *)&v46),
          (unsigned int)CCFRunPtr::IsMask(&v46, 256)) )
    {
      UnhiddenForward = CCFRunPtr::FindUnhiddenForward((CCFRunPtr *)&v46);
      if ( (unsigned int)CCFRunPtr::IsMask(&v46, 256) )
        UnhiddenForward = CCFRunPtr::FindUnhiddenBackward((CCFRunPtr *)&v46);
    }
    *((_WORD *)this + 49) &= ~1u;
    CTxtRange::Advance(this, UnhiddenForward);
    *((_DWORD *)this + 34) &= ~1u;
  }
  v37 = *((_DWORD *)this + 22);
  if ( (v44 ^ v37) < 0 )
  {
    CRchTxtPtr::Advance((CTxtSelection *)((char *)this + 8), -v37);
    v37 = -*((_DWORD *)this + 22);
    *((_DWORD *)this + 22) = v37;
  }
  if ( !v37 && v44 )
  {
    CTxtRange::Update_iFormat(this, -1);
    *((_DWORD *)this + 34) &= ~1u;
  }
  if ( !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 13) + 264LL))(
          *((_QWORD *)this + 13),
          *((unsigned int *)this + 10),
          0xFFFFFFFFLL) )
    CTxtRange::Set(this, 0, 0);
  v38 = *(_DWORD *)(v45 + 180) >> 7;
  v39 = v38 & 1;
  if ( ((*((_DWORD *)this + 34) >> 3) & 1) != v39 )
  {
    v40 = *((_QWORD *)this + 6);
    v41 = *((_DWORD *)this + 34) ^ ((unsigned __int8)*((_DWORD *)this + 34) ^ (unsigned __int8)(8 * v38)) & 8;
    *((_DWORD *)this + 34) = v41;
    if ( (*(_DWORD *)(v40 + 180) & 0x8000080) != 0 )
    {
      if ( v39 )
      {
        if ( (v41 & 0x100) == 0 )
          CTxtSelection::CreateCaret(this);
      }
      (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(*((_QWORD *)this + 6) + 48LL) + 96LL))(
        *(_QWORD *)(*((_QWORD *)this + 6) + 48LL),
        v39);
    }
  }
  CTxtSelection::UpdateCaret(this, v49, 0);
  (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(v45 + 48) + 96LL))(*(_QWORD *)(v45 + 48), 0);
  CTxtSelection::UpdateSelection(this);
  (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v45 + 48) + 96LL))(*(_QWORD *)(v45 + 48), 1);
  return 1;
}

```

## disassembly

```asm
0x18002bfc0  mov     [rsp-40h+arg_8], edx
0x18002bfc4  push    rbp
0x18002bfc5  push    rbx
0x18002bfc6  push    rsi
0x18002bfc7  push    rdi
0x18002bfc8  push    r12
0x18002bfca  push    r13
0x18002bfcc  push    r14
0x18002bfce  push    r15
0x18002bfd0  mov     rbp, rsp
0x18002bfd3  sub     rsp, 68h
0x18002bfd7  mov     rdi, rcx
0x18002bfda  xor     r12d, r12d
0x18002bfdd  mov     ecx, [rcx+58h]
0x18002bfe0  mov     [rbp+var_34], ecx
0x18002bfe3  lea     r14, [rdi+18h]
0x18002bfe7  cmp     [r14+18h], r12
0x18002bfeb  jz      short loc_18002BFF5
0x18002bfed  mov     rax, [r14]
0x18002bff0  mov     esi, [rax+18h]
0x18002bff3  jmp     short loc_18002BFF8
0x18002bff5  mov     esi, r12d
0x18002bff8  mov     rbx, [rdi+30h]
0x18002bffc  movzx   r13d, word ptr [rdi+62h]
0x18002c001  mov     [rbp+var_30], rbx
0x18002c005  mov     [rbp+arg_10], esi
0x18002c008  mov     [rbp+arg_18], r12d
0x18002c00c  mov     [rbp+arg_0], r12d
0x18002c010  test    ecx, ecx
0x18002c012  jnz     short loc_18002C01C
0x18002c014  mov     rcx, rdi; this
0x18002c017  call    ?UpdateForAutoWord@CTxtSelection@@IEAAXXZ; CTxtSelection::UpdateForAutoWord(void)
0x18002c01c  mov     eax, [rbx+0B4h]
0x18002c022  and     eax, 10008h
0x18002c027  cmp     eax, 8
0x18002c02a  jnz     loc_18002C55C
0x18002c030  shr     r13d, 6
0x18002c034  lea     r15d, [rax-7]
0x18002c038  and     r13d, r15d
0x18002c03b  mov     [rbp+var_38], r13d
0x18002c03f  cmp     [rdi+58h], r12d
0x18002c043  jz      loc_18002C0D8
0x18002c049  mov     eax, 180h
0x18002c04e  test    [rdi+62h], ax
0x18002c052  jz      loc_18002C0D8
0x18002c058  mov     rcx, rdi; this
0x18002c05b  call    ?GetPF@CTxtSelection@@QEAAPEBVCParaFormat@@XZ; CTxtSelection::GetPF(void)
0x18002c060  mov     ecx, 4000h
0x18002c065  test    [rax+2], cx
0x18002c069  jnz     short loc_18002C0A5
0x18002c06b  mov     edx, [rdi+58h]
0x18002c06e  lea     rcx, [rbp+var_28]; this
0x18002c072  movups  xmm0, xmmword ptr [rdi+48h]
0x18002c076  neg     edx; int
0x18002c078  movdqu  [rbp+var_28], xmm0
0x18002c07d  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x18002c082  lea     rcx, [rbp+var_28]; this
0x18002c086  call    ?GetFormat@CFormatRunPtr@@QEBAFXZ; CFormatRunPtr::GetFormat(void)
0x18002c08b  movsx   edx, ax; int
0x18002c08e  lea     rcx, [rbx+0F8h]; this
0x18002c095  call    ?GetParaFormat@CTxtArray@@QEAAPEBVCParaFormat@@J@Z; CTxtArray::GetParaFormat(long)
0x18002c09a  mov     ecx, 4000h
0x18002c09f  test    [rax+2], cx
0x18002c0a3  jz      short loc_18002C0D8
0x18002c0a5  movzx   edx, word ptr [rdi+62h]
0x18002c0a9  lea     rax, [rbp+arg_0]
0x18002c0ad  not     dx
0x18002c0b0  mov     [rsp+68h+var_40], rax; int *
0x18002c0b5  and     edx, 80h
0x18002c0bb  lea     rax, [rbp+arg_18]
0x18002c0bf  or      edx, 40h
0x18002c0c2  mov     [rsp+68h+var_48], rax; int *
0x18002c0c7  shr     edx, 4; int
0x18002c0ca  xor     r9d, r9d; int *
0x18002c0cd  mov     r8d, r15d; int
0x18002c0d0  mov     rcx, rdi; this
0x18002c0d3  call    ?Expander@CTxtRange@@QEAAJJHPEAJ00@Z; CTxtRange::Expander(long,int,long *,long *,long *)
0x18002c0d8  mov     rdx, [rdi+30h]
0x18002c0dc  mov     eax, 2000h
0x18002c0e1  test    [rdx+0B8h], ax
0x18002c0e8  jz      loc_18002C349
0x18002c0ee  test    dword ptr [rbx+0B4h], 200h
0x18002c0f8  jnz     loc_18002C349
0x18002c0fe  lea     rcx, [rdi+48h]; this
0x18002c102  call    ?IsValid@CRunPtrBase@@QEBAHXZ; CRunPtrBase::IsValid(void)
0x18002c107  test    eax, eax
0x18002c109  jz      loc_18002C349
0x18002c10f  mov     eax, [rcx+8]
0x18002c112  lea     r8, [rbp+arg_0]; int *
0x18002c116  movsd   xmm0, qword ptr [rcx]
0x18002c11a  mov     dword ptr [rbp+var_28+8], eax
0x18002c11d  mov     eax, [rcx+0Ch]
0x18002c120  mov     rcx, rdi; this
0x18002c123  mov     [rbp+var_18], rdx
0x18002c127  lea     rdx, [rbp+arg_18]; int *
0x18002c12b  movsd   qword ptr [rbp+var_28], xmm0
0x18002c130  mov     dword ptr [rbp+var_28+0Ch], eax
0x18002c133  call    ?GetRange@CTxtRange@@QEBAJAEAJ0@Z; CTxtRange::GetRange(long &,long &)
0x18002c138  mov     edx, [rdi+58h]
0x18002c13b  test    edx, edx
0x18002c13d  jz      loc_18002C2DC
0x18002c143  mov     ebx, [rbp+arg_18]
0x18002c146  mov     r13d, [rbp+arg_0]
0x18002c14a  test    ebx, ebx
0x18002c14c  jnz     short loc_18002C157
0x18002c14e  cmp     r13d, esi
0x18002c151  jge     loc_18002C2D6
0x18002c157  movzx   ecx, word ptr [rdi+62h]
0x18002c15b  mov     esi, [rdi+28h]
0x18002c15e  test    cl, cl
0x18002c160  jns     short loc_18002C1A9
0x18002c162  mov     eax, ecx
0x18002c164  shr     edx, 1Fh
0x18002c167  shr     eax, 6
0x18002c16a  lea     r8, [rbp+arg_18]
0x18002c16e  and     eax, r15d
0x18002c171  lea     r9, [rbp+arg_0]
0x18002c175  cmp     al, dl
0x18002c177  jz      short loc_18002C186
0x18002c179  test    cl, 40h
0x18002c17c  jz      short loc_18002C183
0x18002c17e  mov     r9, r12
0x18002c181  jmp     short loc_18002C186
0x18002c183  mov     r8, r12
0x18002c186  mov     [rsp+68h+var_40], r9; int *
0x18002c18b  mov     rcx, rdi; this
0x18002c18e  xor     r9d, r9d; int *
0x18002c191  mov     [rsp+68h+var_48], r8; int *
0x18002c196  mov     r8d, r15d; int
0x18002c199  lea     edx, [r9+4]; int
0x18002c19d  call    ?Expander@CTxtRange@@QEAAJJHPEAJ00@Z; CTxtRange::Expander(long,int,long *,long *,long *)
0x18002c1a2  mov     ebx, [rbp+arg_18]
0x18002c1a5  mov     r13d, [rbp+arg_0]
0x18002c1a9  mov     edx, ebx
0x18002c1ab  lea     rcx, [rbp+var_28]; this
0x18002c1af  sub     edx, esi; int
0x18002c1b1  mov     r14d, ebx
0x18002c1b4  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x18002c1b9  lea     rcx, [rbp+var_28]; this
0x18002c1bd  call    ?IsCollapsed@CPFRunPtr@@QEAAHXZ; CPFRunPtr::IsCollapsed(void)
0x18002c1c2  test    eax, eax
0x18002c1c4  jz      short loc_18002C1D5
0x18002c1c6  lea     rcx, [rbp+var_28]; this
0x18002c1ca  call    ?FindExpandedBackward@CPFRunPtr@@QEAAJXZ; CPFRunPtr::FindExpandedBackward(void)
0x18002c1cf  add     ebx, eax
0x18002c1d1  mov     esi, ebx
0x18002c1d3  jmp     short loc_18002C1D8
0x18002c1d5  mov     esi, r14d
0x18002c1d8  lea     rcx, [rbp+var_28]; this
0x18002c1dc  call    ?AdjustForward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustForward(void)
0x18002c1e1  lea     rcx, [rbp+var_28]; this
0x18002c1e5  call    ?IsCollapsed@CPFRunPtr@@QEAAHXZ; CPFRunPtr::IsCollapsed(void)
0x18002c1ea  mov     edx, [rbp+arg_0]
0x18002c1ed  lea     rcx, [rbp+var_28]; this
0x18002c1f1  sub     edx, esi; int
0x18002c1f3  mov     r12d, eax
0x18002c1f6  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x18002c1fb  lea     rcx, [rbp+var_28]; this
0x18002c1ff  call    ?IsCollapsed@CPFRunPtr@@QEAAHXZ; CPFRunPtr::IsCollapsed(void)
0x18002c204  test    eax, eax
0x18002c206  jz      short loc_18002C235
0x18002c208  xor     esi, esi
0x18002c20a  lea     rcx, [rbp+var_28]; this
0x18002c20e  call    ?IsCollapsed@CPFRunPtr@@QEAAHXZ; CPFRunPtr::IsCollapsed(void)
0x18002c213  test    eax, eax
0x18002c215  jz      short loc_18002C232
0x18002c217  lea     rcx, [rbp+var_28]; this
0x18002c21b  call    ?GetCchLeft@CRunPtrBase@@QEBAJXZ; CRunPtrBase::GetCchLeft(void)
0x18002c220  add     dword ptr [rbp+var_28+0Ch], eax
0x18002c223  lea     rcx, [rbp+var_28]; this
0x18002c227  add     esi, eax
0x18002c229  call    ?NextRun@CRunPtrBase@@QEAAHXZ; CRunPtrBase::NextRun(void)
0x18002c22e  test    eax, eax
0x18002c230  jnz     short loc_18002C20A
0x18002c232  add     [rbp+arg_0], esi
0x18002c235  test    r12d, r12d
0x18002c238  jnz     short loc_18002C255
0x18002c23a  lea     rcx, [rbp+var_28]; this
0x18002c23e  call    ?IsCollapsed@CPFRunPtr@@QEAAHXZ; CPFRunPtr::IsCollapsed(void)
0x18002c243  mov     edx, [rbp+arg_0]
0x18002c246  mov     r12d, [rbp+arg_10]
0x18002c24a  test    eax, eax
0x18002c24c  jz      short loc_18002C289
0x18002c24e  cmp     edx, r12d
0x18002c251  jl      short loc_18002C259
0x18002c253  jmp     short loc_18002C289
0x18002c255  mov     r12d, [rbp+arg_10]
0x18002c259  lea     rcx, [rbp+var_28]; this
0x18002c25d  call    ?IsCollapsed@CPFRunPtr@@QEAAHXZ; CPFRunPtr::IsCollapsed(void)
0x18002c262  test    eax, eax
0x18002c264  jz      short loc_18002C284
0x18002c266  mov     edx, ebx
0x18002c268  lea     rcx, [rbp+var_28]; this
0x18002c26c  sub     edx, [rbp+arg_0]; int
0x18002c26f  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x18002c274  lea     rcx, [rbp+var_28]; this
0x18002c278  call    ?AdjustForward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustForward(void)
0x18002c27d  mov     edx, ebx
0x18002c27f  mov     [rbp+arg_0], ebx
0x18002c282  jmp     short loc_18002C289
0x18002c284  mov     edx, [rbp+arg_0]; int
0x18002c287  mov     ebx, edx
0x18002c289  cmp     ebx, r14d
0x18002c28c  jnz     short loc_18002C293
0x18002c28e  cmp     edx, r13d
0x18002c291  jz      short loc_18002C2A1
0x18002c293  mov     r8d, edx
0x18002c296  mov     rcx, rdi; this
0x18002c299  sub     r8d, ebx; int
0x18002c29c  call    ?Set@CTxtRange@@QEAAHJJ@Z; CTxtRange::Set(long,long)
0x18002c2a1  lea     r14, [rdi+18h]
0x18002c2a5  mov     r13d, [rbp+var_38]
0x18002c2a9  cmp     dword ptr [rdi+58h], 0
0x18002c2ad  jnz     loc_18002C34D
0x18002c2b3  lea     rcx, [rbp+var_28]; this
0x18002c2b7  call    ?IsCollapsed@CPFRunPtr@@QEAAHXZ; CPFRunPtr::IsCollapsed(void)
0x18002c2bc  test    eax, eax
0x18002c2be  jz      loc_18002C34D
0x18002c2c4  test    r13d, r13d
0x18002c2c7  jz      short loc_18002C2E2
0x18002c2c9  lea     rcx, [rbp+var_28]; this
0x18002c2cd  call    ?FindExpandedBackward@CPFRunPtr@@QEAAJXZ; CPFRunPtr::FindExpandedBackward(void)
0x18002c2d2  mov     ebx, eax
0x18002c2d4  jmp     short loc_18002C2E4
0x18002c2d6  mov     r12d, [rbp+arg_10]
0x18002c2da  jmp     short loc_18002C2A5
0x18002c2dc  mov     r12d, [rbp+arg_10]
0x18002c2e0  jmp     short loc_18002C2A9
0x18002c2e2  xor     ebx, ebx
0x18002c2e4  lea     rcx, [rbp+var_28]; this
0x18002c2e8  call    ?IsCollapsed@CPFRunPtr@@QEAAHXZ; CPFRunPtr::IsCollapsed(void)
0x18002c2ed  test    eax, eax
0x18002c2ef  jz      short loc_18002C2FC
0x18002c2f1  lea     rcx, [rbp+var_28]; this
0x18002c2f5  call    ?FindExpanded@CPFRunPtr@@QEAAJXZ; CPFRunPtr::FindExpanded(void)
0x18002c2fa  mov     ebx, eax
0x18002c2fc  mov     eax, 0FFFEh
0x18002c301  mov     edx, ebx; int
0x18002c303  and     [rdi+62h], ax
0x18002c307  mov     rcx, rdi; this
0x18002c30a  call    ?Advance@CTxtRange@@QEAAJJ@Z; CTxtRange::Advance(long)
0x18002c30f  lea     rcx, [rbp+var_28]; this
0x18002c313  call    ?AdjustForward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustForward(void)
0x18002c318  test    ebx, ebx
0x18002c31a  jg      short loc_18002C340
0x18002c31c  lea     rcx, [rbp+var_28]; this
0x18002c320  call    ?IsCollapsed@CPFRunPtr@@QEAAHXZ; CPFRunPtr::IsCollapsed(void)
0x18002c325  test    eax, eax
0x18002c327  jz      short loc_18002C340
0x18002c329  mov     rcx, r14; this
0x18002c32c  call    ?IsAfterEOP@CTxtPtr@@QEAAHXZ; CTxtPtr::IsAfterEOP(void)
0x18002c331  test    eax, eax
0x18002c333  jz      short loc_18002C340
0x18002c335  mov     edx, r15d; int
0x18002c338  mov     rcx, rdi; this
0x18002c33b  call    ?BackupCRLF@CTxtRange@@QEAAJH@Z; CTxtRange::BackupCRLF(int)
0x18002c340  and     dword ptr [rdi+88h], 0FFFFFFFEh
0x18002c347  jmp     short loc_18002C34D
0x18002c349  mov     r12d, [rbp+arg_10]
0x18002c34d  mov     r14d, [rdi+28h]
0x18002c351  mov     edx, r14d
0x18002c354  mov     rax, [rdi+30h]
0x18002c358  mov     ecx, [rdi+58h]
0x18002c35b  movups  xmm0, xmmword ptr [rdi+38h]
0x18002c35f  mov     [rbp+var_18], rax
0x18002c363  mov     eax, r14d
0x18002c366  sub     eax, ecx
0x18002c368  test    ecx, ecx
0x18002c36a  mov     esi, eax
0x18002c36c  movdqu  [rbp+var_28], xmm0
0x18002c371  cmovs   edx, eax
0x18002c374  cmovs   esi, r14d
0x18002c378  mov     [rbp+arg_0], edx
0x18002c37b  jz      short loc_18002C3CE
0x18002c37d  test    esi, esi
0x18002c37f  jnz     short loc_18002C386
0x18002c381  cmp     edx, r12d
0x18002c384  jge     short loc_18002C3CE
0x18002c386  mov     edx, esi
0x18002c388  lea     rcx, [rbp+var_28]; this
0x18002c38c  sub     edx, r14d; int
0x18002c38f  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x18002c394  lea     rcx, [rbp+var_28]; this
0x18002c398  call    ?IsInHidden@CCFRunPtr@@QEAAHXZ; CCFRunPtr::IsInHidden(void)
0x18002c39d  mov     edx, [rbp+arg_0]
0x18002c3a0  lea     rcx, [rbp+var_28]; this
0x18002c3a4  sub     edx, esi; int
0x18002c3a6  mov     ebx, eax
0x18002c3a8  call    ?AdvanceCp@CRunPtrBase@@QEAAJJ@Z; CRunPtrBase::AdvanceCp(long)
0x18002c3ad  test    ebx, ebx
0x18002c3af  jnz     short loc_18002C3C4
0x18002c3b1  lea     rcx, [rbp+var_28]; this
0x18002c3b5  call    ?IsInHidden@CCFRunPtr@@QEAAHXZ; CCFRunPtr::IsInHidden(void)
0x18002c3ba  test    eax, eax
0x18002c3bc  jz      short loc_18002C3CE
0x18002c3be  cmp     [rbp+arg_0], r12d
0x18002c3c2  jge     short loc_18002C3CE
0x18002c3c4  xor     edx, edx; int
0x18002c3c6  mov     rcx, rdi; this
0x18002c3c9  call    ?Collapser@CTxtRange@@QEAAXJ@Z; CTxtRange::Collapser(long)
  ... truncated ...
```
