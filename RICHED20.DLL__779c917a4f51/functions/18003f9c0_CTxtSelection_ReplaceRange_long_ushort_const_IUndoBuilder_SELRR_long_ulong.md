# CTxtSelection::ReplaceRange(long,ushort const *,IUndoBuilder *,SELRR,long *,ulong)

- ea: `0x18003f9c0`
- end: `0x18003fd4d`
- name: `?ReplaceRange@CTxtSelection@@UEAAJJPEBGPEAVIUndoBuilder@@W4SELRR@@PEAJK@Z`
- size: `909`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `installer_update`

## callees

- `0x18000c070`
- `0x1800110b0`
- `0x1800114d0`
- `0x1800175d0`
- `0x180017ef0`
- `0x18001db20`
- `0x1800202a0`
- `0x180038d20`
- `0x1800391f0`
- `0x18003e0c4`
- `0x18003f9c0`
- `0x1800411d4`
- `0x180042de8`
- `0x180043f80`
- `0x180045120`
- `0x1800490f0`
- `0x1800491d8`
- `0x1800734d4`
- `0x18007fc58`
- `0x180080d68`
- `0x180092010`

## pseudocode

```c
__int64 __fastcall CTxtSelection::ReplaceRange(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int a7)
{
  const unsigned __int16 *v9; // r8
  CTxtPtr *v10; // r11
  int v11; // edx
  int v12; // ecx
  unsigned int v14; // ebp
  CTxtPtr *v15; // r11
  int v16; // eax
  int v17; // ecx
  unsigned int v18; // r12d
  unsigned int v19; // r15d
  bool v20; // sf
  int v21; // eax
  int v22; // edx
  __int64 v23; // rax
  unsigned int v24; // edi
  int v25; // r13d
  int v26; // r14d
  unsigned int v27; // ebp
  __int64 v28; // r8
  __int64 v29; // r9
  int v30; // edx
  int v31; // ecx
  __int64 v32; // rax
  __int64 v33; // rcx
  int v34; // eax
  _BYTE v35[32]; // [rsp+40h] [rbp-78h] BYREF
  __int16 v36; // [rsp+60h] [rbp-58h]
  int TextLength; // [rsp+C8h] [rbp+10h]

  TextLength = CTxtPtr::GetTextLength((CTxtPtr *)(a1 + 24));
  *(_DWORD *)(a1 + 140) = 0;
  if ( v11 < 0 )
    a2 = CW32System::wcslen(v9);
  v12 = *(_DWORD *)(a1 + 88);
  if ( !v12 && !a2 )
    return 0;
  v14 = *(_DWORD *)(a1 + 136);
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 48) + 180LL) & 0x10000) == 0
    && (!v12
     && *v9 != 13
     && CTxtPtr::GetChar(v10) == 13
     && CTxtPtr::GetPrevChar(v15) == 9
     && (*((_WORD *)CTxtSelection::GetPF((CTxtSelection *)a1) + 1) & 0x4000) != 0
     || *(_DWORD *)(a1 + 88) != TextLength
     && ((*(_WORD *)(*(_QWORD *)(a1 + 48) + 184LL) & 0x2000) != 0
      && (*((_WORD *)CRchTxtPtr::GetPF((CRchTxtPtr *)(a1 + 8)) + 1) & 0x100) != 0
      || (unsigned int)CRchTxtPtr::IsHidden((CRchTxtPtr *)(a1 + 8)) && (a7 & 0x10) == 0)) )
  {
    CTxtEdit::Beep(*(CTxtEdit **)(a1 + 48));
    return 0;
  }
  CCallMgr::SetSelectionChanged(*(CCallMgr **)(*(_QWORD *)(a1 + 48) + 144LL));
  CTxtSelection::CheckTableSelection((CTxtSelection *)a1);
  v16 = *(_DWORD *)(a1 + 88);
  v17 = *(_DWORD *)(a1 + 112);
  v18 = *(_DWORD *)(a1 + 40);
  v19 = v18 - v16;
  v20 = v16 < 0;
  v21 = v17;
  if ( v20 )
  {
    v18 = v19;
    v19 = *(_DWORD *)(a1 + 40);
  }
  v22 = v17 + *(_DWORD *)(a1 + 116);
  if ( v17 >= v22 )
    v21 = v17 + *(_DWORD *)(a1 + 116);
  if ( (int)v19 > v21 )
    goto LABEL_26;
  if ( v17 <= v22 )
    v17 += *(_DWORD *)(a1 + 116);
  if ( (int)v18 < v17 )
  {
LABEL_26:
    CTxtSelection::ShowSelection((CTxtSelection *)a1, 0);
    *(_DWORD *)(a1 + 136) |= 8u;
  }
  v23 = *(_QWORD *)(a1 + 48);
  *(_DWORD *)(a1 + 136) &= 0xFFFFFFEE;
  if ( (*(_DWORD *)(v23 + 180) & 0x10000) != 0
    || (*(unsigned int (__fastcall **)(_QWORD, _QWORD, __int64))(**(_QWORD **)(a1 + 104) + 264LL))(
         *(_QWORD *)(a1 + 104),
         v19,
         0xFFFFFFFFLL) )
  {
    v25 = 0;
    v26 = 0;
    v27 = v14 >> 4;
    if ( a4 )
    {
      if ( a5 == 1 )
      {
        v28 = *(unsigned int *)(a1 + 40);
        v29 = *(unsigned int *)(a1 + 88);
      }
      else
      {
        v29 = 0;
        v28 = v19;
        if ( a5 == 3 )
          v28 = v18;
      }
      HandleSelectionAEInfo(*(_QWORD *)(a1 + 48), a4, v28, v29, v19 + a2, 0, 1);
    }
    v30 = *(_DWORD *)(a1 + 88);
    if ( v30 == TextLength && !a2 )
    {
      v25 = 1;
      CRchTxtPtr::Advance((CRchTxtPtr *)(a1 + 8), -v30);
      *(_DWORD *)(a1 + 88) = -*(_DWORD *)(a1 + 88);
      if ( (*(_WORD *)(*(_QWORD *)(a1 + 48) + 184LL) & 0x2000) != 0
        && *((__int16 *)CTxtSelection::GetPF((CTxtSelection *)a1) + 16) <= -2
        && *((__int16 *)CTxtSelection::GetPF((CTxtSelection *)a1) + 16) >= -10 )
      {
        v26 = 1;
      }
    }
    v24 = CTxtRange::ReplaceRange(a1, a2, a3, a4, 0, a6, a7);
    *(_DWORD *)(a1 + 112) = *(_DWORD *)(a1 + 40);
    v31 = *(_DWORD *)(a1 + 136);
    *(_DWORD *)(a1 + 116) = 0;
    *(_DWORD *)(a1 + 136) = v31 ^ ((unsigned __int8)v31 ^ (unsigned __int8)(16 * v27)) & 0x10;
    if ( v24 == a2 )
    {
      if ( v25 )
      {
        v36 = -2;
        if ( !v26 )
          v36 = -1;
        CTxtRange::SetParaStyle((CTxtRange *)a1, (const struct CParaFormat *)v35, 0, 0x400u);
        v32 = *(_QWORD *)(a1 + 48);
        if ( (*(_BYTE *)(v32 + 192) & 1) != 0 )
        {
          if ( *(char *)(v32 + 180) < 0 && (*(_WORD *)(v32 + 184) & 0x4000) == 0 )
          {
            CTxtSelection::MatchKeyboardToPara((CTxtSelection *)a1);
            CTxtSelection::CheckSynchCharSet((CTxtSelection *)a1, 0);
          }
        }
        else
        {
          CTxtRange::Update_iFormat((CTxtRange *)a1, -1);
        }
      }
      v33 = *(_QWORD *)(a1 + 48);
      v34 = *(_DWORD *)(v33 + 180);
      if ( (v34 & 8) != 0 )
        CTxtSelection::UpdateCaret((CTxtSelection *)a1, v27 & 1, 0);
      else
        *(_DWORD *)(v33 + 180) = v34 | 0x8000;
    }
  }
  else
  {
    return 0;
  }
  return v24;
}

```

## disassembly

```asm
0x18003f9c0  mov     [rsp+arg_0], rbx
0x18003f9c5  mov     [rsp+arg_18], r9
0x18003f9ca  mov     [rsp+arg_10], r8
0x18003f9cf  push    rbp
0x18003f9d0  push    rsi
0x18003f9d1  push    rdi
0x18003f9d2  push    r12
0x18003f9d4  push    r13
0x18003f9d6  push    r14
0x18003f9d8  push    r15
0x18003f9da  sub     rsp, 80h
0x18003f9e1  lea     r11, [rcx+18h]
0x18003f9e5  mov     rbx, rcx
0x18003f9e8  mov     rcx, r11; this
0x18003f9eb  mov     esi, edx
0x18003f9ed  call    ?GetTextLength@CTxtPtr@@QEBAJXZ; CTxtPtr::GetTextLength(void)
0x18003f9f2  mov     [rsp+0B8h+arg_8], eax
0x18003f9f9  mov     r14d, eax
0x18003f9fc  mov     dword ptr [rbx+8Ch], 0
0x18003fa06  test    edx, edx
0x18003fa08  jns     short loc_18003FA15
0x18003fa0a  mov     rcx, r8; unsigned __int16 *
0x18003fa0d  call    ?wcslen@CW32System@@SA_KPEBG@Z; CW32System::wcslen(ushort const *)
0x18003fa12  mov     rsi, rax
0x18003fa15  mov     ecx, [rbx+58h]
0x18003fa18  test    ecx, ecx
0x18003fa1a  jnz     short loc_18003FA27
0x18003fa1c  test    esi, esi
0x18003fa1e  jnz     short loc_18003FA27
0x18003fa20  xor     eax, eax
0x18003fa22  jmp     loc_18003FD32
0x18003fa27  mov     ebp, [rbx+88h]
0x18003fa2d  lea     rdi, [rbx+8]
0x18003fa31  mov     rax, [rdi+28h]
0x18003fa35  mov     r13d, 10000h
0x18003fa3b  mov     edx, 2000h
0x18003fa40  mov     r15d, 4000h
0x18003fa46  test    [rax+0B4h], r13d
0x18003fa4d  jnz     loc_18003FAD8
0x18003fa53  test    ecx, ecx
0x18003fa55  jnz     short loc_18003FA8E
0x18003fa57  cmp     word ptr [r8], 0Dh
0x18003fa5c  jz      short loc_18003FA8E
0x18003fa5e  mov     rcx, r11; this
0x18003fa61  call    ?GetChar@CTxtPtr@@QEAAGXZ; CTxtPtr::GetChar(void)
0x18003fa66  cmp     ax, 0Dh
0x18003fa6a  jnz     short loc_18003FA89
0x18003fa6c  mov     rcx, r11; this
0x18003fa6f  call    ?GetPrevChar@CTxtPtr@@QEAAGXZ; CTxtPtr::GetPrevChar(void)
0x18003fa74  cmp     ax, 9
0x18003fa78  jnz     short loc_18003FA89
0x18003fa7a  mov     rcx, rbx; this
0x18003fa7d  call    ?GetPF@CTxtSelection@@QEAAPEBVCParaFormat@@XZ; CTxtSelection::GetPF(void)
0x18003fa82  test    [rax+2], r15w
0x18003fa87  jnz     short loc_18003FACA
0x18003fa89  mov     edx, 2000h
0x18003fa8e  cmp     [rbx+58h], r14d
0x18003fa92  jz      short loc_18003FAD8
0x18003fa94  mov     rax, [rbx+30h]
0x18003fa98  test    [rax+0B8h], dx
0x18003fa9f  jz      short loc_18003FAB4
0x18003faa1  mov     rcx, rdi; this
0x18003faa4  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x18003faa9  mov     ecx, 100h
0x18003faae  test    [rax+2], cx
0x18003fab2  jnz     short loc_18003FACA
0x18003fab4  mov     rcx, rdi; this
0x18003fab7  call    ?IsHidden@CRchTxtPtr@@QEBAHXZ; CRchTxtPtr::IsHidden(void)
0x18003fabc  test    eax, eax
0x18003fabe  jz      short loc_18003FAD8
0x18003fac0  test    byte ptr [rsp+0B8h+arg_30], 10h
0x18003fac8  jnz     short loc_18003FAD8
0x18003faca  mov     rcx, [rbx+30h]; this
0x18003face  call    ?Beep@CTxtEdit@@QEAAXXZ; CTxtEdit::Beep(void)
0x18003fad3  jmp     loc_18003FA20
0x18003fad8  mov     rcx, [rbx+30h]
0x18003fadc  mov     rcx, [rcx+90h]; this
0x18003fae3  call    ?SetSelectionChanged@CCallMgr@@QEAAXXZ; CCallMgr::SetSelectionChanged(void)
0x18003fae8  mov     rcx, rbx; this
0x18003faeb  call    ?CheckTableSelection@CTxtSelection@@QEAAXXZ; CTxtSelection::CheckTableSelection(void)
0x18003faf0  mov     eax, [rbx+58h]
0x18003faf3  mov     ecx, [rbx+70h]
0x18003faf6  mov     r15d, [rbx+28h]
0x18003fafa  mov     r12d, [rbx+28h]
0x18003fafe  sub     r15d, eax
0x18003fb01  mov     edx, [rbx+74h]
0x18003fb04  test    eax, eax
0x18003fb06  mov     eax, ecx
0x18003fb08  cmovs   r12d, r15d
0x18003fb0c  cmovs   r15d, [rbx+28h]
0x18003fb11  add     edx, ecx
0x18003fb13  cmp     ecx, edx
0x18003fb15  cmovge  eax, edx
0x18003fb18  cmp     r15d, eax
0x18003fb1b  jg      short loc_18003FB27
0x18003fb1d  cmp     ecx, edx
0x18003fb1f  cmovle  ecx, edx
0x18003fb22  cmp     r12d, ecx
0x18003fb25  jge     short loc_18003FB38
0x18003fb27  xor     edx, edx; int
0x18003fb29  mov     rcx, rbx; this
0x18003fb2c  call    ?ShowSelection@CTxtSelection@@QEAAHH@Z; CTxtSelection::ShowSelection(int)
0x18003fb31  or      dword ptr [rbx+88h], 8
0x18003fb38  mov     rax, [rbx+30h]
0x18003fb3c  and     dword ptr [rbx+88h], 0FFFFFFEEh
0x18003fb43  test    [rax+0B4h], r13d
0x18003fb4a  jnz     short loc_18003FB71
0x18003fb4c  mov     rcx, [rbx+68h]
0x18003fb50  or      r8d, 0FFFFFFFFh
0x18003fb54  mov     edx, r15d
0x18003fb57  mov     rax, [rcx]
0x18003fb5a  mov     rax, [rax+108h]
0x18003fb61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fb66  test    eax, eax
0x18003fb68  jnz     short loc_18003FB71
0x18003fb6a  xor     edi, edi
0x18003fb6c  jmp     loc_18003FD30
0x18003fb71  mov     rcx, [rsp+0B8h+arg_18]
0x18003fb79  xor     r13d, r13d
0x18003fb7c  xor     r14d, r14d
0x18003fb7f  shr     ebp, 4
0x18003fb82  test    rcx, rcx
0x18003fb85  jz      short loc_18003FBCE
0x18003fb87  cmp     [rsp+0B8h+arg_20], 1
0x18003fb8f  jnz     short loc_18003FB9B
0x18003fb91  mov     r8d, [rbx+28h]
0x18003fb95  mov     r9d, [rbx+58h]
0x18003fb99  jmp     short loc_18003FBAD
0x18003fb9b  xor     r9d, r9d
0x18003fb9e  mov     r8d, r15d
0x18003fba1  cmp     [rsp+0B8h+arg_20], 3
0x18003fba9  cmovz   r8d, r12d
0x18003fbad  lea     eax, [r15+rsi]
0x18003fbb1  mov     [rsp+0B8h+var_88], 1
0x18003fbb9  mov     rdx, rcx
0x18003fbbc  mov     dword ptr [rsp+0B8h+var_90], r13d
0x18003fbc1  mov     rcx, [rbx+30h]
0x18003fbc5  mov     [rsp+0B8h+var_98], eax
0x18003fbc9  call    ?HandleSelectionAEInfo@@YAJPEAVCTxtEdit@@PEAVIUndoBuilder@@JJJJW4SELAE@@@Z; HandleSelectionAEInfo(CTxtEdit *,IUndoBuilder *,long,long,long,long,SELAE)
0x18003fbce  mov     edx, [rbx+58h]
0x18003fbd1  mov     r15d, 0FFFFFFFEh
0x18003fbd7  cmp     edx, [rsp+0B8h+arg_8]
0x18003fbde  jnz     short loc_18003FC2D
0x18003fbe0  test    esi, esi
0x18003fbe2  jnz     short loc_18003FC2D
0x18003fbe4  neg     edx; int
0x18003fbe6  lea     r13d, [r15+3]
0x18003fbea  mov     rcx, rdi; this
0x18003fbed  call    ?Advance@CRchTxtPtr@@QEAAJJ@Z; CRchTxtPtr::Advance(long)
0x18003fbf2  mov     eax, [rbx+58h]
0x18003fbf5  mov     ecx, 2000h
0x18003fbfa  neg     eax
0x18003fbfc  mov     [rbx+58h], eax
0x18003fbff  mov     rax, [rbx+30h]
0x18003fc03  test    [rax+0B8h], cx
0x18003fc0a  jz      short loc_18003FC2D
0x18003fc0c  mov     rcx, rbx; this
0x18003fc0f  call    ?GetPF@CTxtSelection@@QEAAPEBVCParaFormat@@XZ; CTxtSelection::GetPF(void)
0x18003fc14  cmp     [rax+20h], r15w
0x18003fc19  jg      short loc_18003FC2D
0x18003fc1b  mov     rcx, rbx; this
0x18003fc1e  call    ?GetPF@CTxtSelection@@QEAAPEBVCParaFormat@@XZ; CTxtSelection::GetPF(void)
0x18003fc23  cmp     word ptr [rax+20h], 0FFF6h
0x18003fc28  jl      short loc_18003FC2D
0x18003fc2a  mov     r14d, r13d
0x18003fc2d  mov     eax, [rsp+0B8h+arg_30]
0x18003fc34  mov     edx, esi
0x18003fc36  mov     r9, [rsp+0B8h+arg_18]
0x18003fc3e  mov     rcx, rbx
0x18003fc41  mov     r8, [rsp+0B8h+arg_10]
0x18003fc49  mov     [rsp+0B8h+var_88], eax
0x18003fc4d  mov     rax, [rsp+0B8h+arg_28]
0x18003fc55  mov     [rsp+0B8h+var_90], rax
0x18003fc5a  mov     [rsp+0B8h+var_98], 0
0x18003fc62  call    ?ReplaceRange@CTxtRange@@UEAAJJPEBGPEAVIUndoBuilder@@W4SELRR@@PEAJK@Z; CTxtRange::ReplaceRange(long,ushort const *,IUndoBuilder *,SELRR,long *,ulong)
0x18003fc67  mov     ecx, [rbx+28h]
0x18003fc6a  mov     edx, ebp
0x18003fc6c  shl     edx, 4
0x18003fc6f  mov     edi, eax
0x18003fc71  mov     [rbx+70h], ecx
0x18003fc74  mov     ecx, [rbx+88h]
0x18003fc7a  xor     edx, ecx
0x18003fc7c  and     edx, 10h
0x18003fc7f  mov     dword ptr [rbx+74h], 0
0x18003fc86  xor     edx, ecx
0x18003fc88  mov     [rbx+88h], edx
0x18003fc8e  cmp     eax, esi
0x18003fc90  jnz     loc_18003FD30
0x18003fc96  test    r13d, r13d
0x18003fc99  jz      short loc_18003FD06
0x18003fc9b  or      esi, 0FFFFFFFFh
0x18003fc9e  mov     [rsp+0B8h+var_58], r15w
0x18003fca4  test    r14d, r14d
0x18003fca7  jnz     short loc_18003FCAE
0x18003fca9  mov     [rsp+0B8h+var_58], si
0x18003fcae  mov     r9d, 400h; unsigned int
0x18003fcb4  lea     rdx, [rsp+0B8h+var_78]; struct CParaFormat *
0x18003fcb9  xor     r8d, r8d; struct IUndoBuilder *
0x18003fcbc  mov     rcx, rbx; this
0x18003fcbf  call    ?SetParaStyle@CTxtRange@@QEAAJPEBVCParaFormat@@PEAVIUndoBuilder@@K@Z; CTxtRange::SetParaStyle(CParaFormat const *,IUndoBuilder *,ulong)
0x18003fcc4  mov     rax, [rbx+30h]
0x18003fcc8  test    byte ptr [rax+0C0h], 1
0x18003fccf  jz      short loc_18003FCFC
0x18003fcd1  test    byte ptr [rax+0B4h], 80h
0x18003fcd8  jz      short loc_18003FD06
0x18003fcda  mov     ecx, 4000h
0x18003fcdf  test    [rax+0B8h], cx
0x18003fce6  jnz     short loc_18003FD06
0x18003fce8  mov     rcx, rbx; this
0x18003fceb  call    ?MatchKeyboardToPara@CTxtSelection@@QEAAHXZ; CTxtSelection::MatchKeyboardToPara(void)
0x18003fcf0  xor     edx, edx; unsigned int
0x18003fcf2  mov     rcx, rbx; this
0x18003fcf5  call    ?CheckSynchCharSet@CTxtSelection@@QEAAIK@Z; CTxtSelection::CheckSynchCharSet(ulong)
0x18003fcfa  jmp     short loc_18003FD06
0x18003fcfc  mov     edx, esi; int
0x18003fcfe  mov     rcx, rbx; this
0x18003fd01  call    ?Update_iFormat@CTxtRange@@QEAAXJ@Z; CTxtRange::Update_iFormat(long)
0x18003fd06  mov     rcx, [rbx+30h]
0x18003fd0a  mov     eax, [rcx+0B4h]
0x18003fd10  test    al, 8
0x18003fd12  jz      short loc_18003FD26
0x18003fd14  and     ebp, 1
0x18003fd17  xor     r8d, r8d; int
0x18003fd1a  mov     edx, ebp; int
0x18003fd1c  mov     rcx, rbx; this
0x18003fd1f  call    ?UpdateCaret@CTxtSelection@@QEAAHHH@Z; CTxtSelection::UpdateCaret(int,int)
0x18003fd24  jmp     short loc_18003FD30
0x18003fd26  bts     eax, 0Fh
0x18003fd2a  mov     [rcx+0B4h], eax
0x18003fd30  mov     eax, edi
0x18003fd32  mov     rbx, [rsp+0B8h+arg_0]
0x18003fd3a  add     rsp, 80h
0x18003fd41  pop     r15
0x18003fd43  pop     r14
0x18003fd45  pop     r13
0x18003fd47  pop     r12
0x18003fd49  pop     rdi
0x18003fd4a  pop     rsi
0x18003fd4b  pop     rbp
0x18003fd4c  retn
```
