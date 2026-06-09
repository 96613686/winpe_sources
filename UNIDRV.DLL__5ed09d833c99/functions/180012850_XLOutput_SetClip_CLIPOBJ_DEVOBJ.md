# XLOutput::SetClip(_CLIPOBJ *,_DEVOBJ *)

- ea: `0x180012850`
- end: `0x180012aba`
- name: `?SetClip@XLOutput@@QEAAJPEAU_CLIPOBJ@@PEAU_DEVOBJ@@@Z`
- size: `618`
- prototype: `__int64 __fastcall(XLOutput *__hidden this, struct _CLIPOBJ *, struct _DEVOBJ *)`
- caller_count: `6`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000ee10`
- `0x18000fe80`
- `0x180012ac0`
- `0x1800155e0`
- `0x180043980`
- `0x18006eec0`

## callees

- `0x180012160`
- `0x180012850`
- `0x180014040`
- `0x180037e04`
- `0x18003cd38`
- `0x18003d4e8`
- `0x18003e350`
- `0x180046654`

## import_xrefs

- `GDI32!CLIPOBJ_ppoGetPath` at `0x1800129fc`
- `GDI32!CLIPOBJ_ppoGetPath` at `0x1800129fc`
- `GDI32!EngDeletePath` at `0x180012a46`
- `GDI32!EngDeletePath` at `0x180012a46`

## pseudocode

```c
__int64 __fastcall XLOutput::SetClip(XLOutput *this, struct _CLIPOBJ *a2, struct _DEVOBJ *a3)
{
  __int64 v3; // rbp
  int iDComplexity; // ecx
  unsigned int v8; // r14d
  int v9; // edx
  bool v10; // zf
  __int64 result; // rax
  __int64 v12; // rax
  int v13; // ecx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rax
  PATHOBJ *Path; // rsi
  __int64 v20; // rcx
  __int64 v21; // rax

  v3 = (__int64)this + 144;
  if ( !this )
    v3 = 112;
  if ( !a2 )
  {
    if ( *(_DWORD *)(v3 + 4) )
    {
      XLWrite::WriteByte(this, 105);
      v18 = (__int64)this + 148;
      if ( !this )
        v18 = 116;
      *(_DWORD *)v18 = 0;
    }
    return 0;
  }
  iDComplexity = a2->iDComplexity;
  v8 = 1;
  v9 = *(_DWORD *)(v3 + 4);
  if ( !a2->iDComplexity )
    goto LABEL_5;
  v13 = iDComplexity - 1;
  if ( v13 )
  {
    if ( v13 != 2 )
    {
LABEL_5:
      v10 = v9 == 0;
      goto LABEL_6;
    }
    if ( v9 == 2 )
    {
      v12 = (__int64)this + 172;
      if ( !this )
        v12 = 140;
      if ( *(_DWORD *)v12 && a2->iUniq && *(_DWORD *)v12 == a2->iUniq )
      {
        v20 = (__int64)this + 176;
        if ( !this )
          v20 = 144;
        if ( (unsigned int)XLClipRgn::Compare((XLClipRgn *)v20, a2) )
          return 0;
      }
    }
  }
  else if ( v9 == 1 )
  {
    v14 = (__int64)this + 156;
    if ( !this )
      v14 = 124;
    if ( *(_DWORD *)v14 == a2->rclBounds.left )
    {
      v15 = (__int64)this + 164;
      if ( !this )
        v15 = 132;
      if ( *(_DWORD *)v15 == a2->rclBounds.right )
      {
        v16 = (__int64)this + 160;
        if ( !this )
          v16 = 128;
        if ( *(_DWORD *)v16 == a2->rclBounds.top )
        {
          v17 = (__int64)this + 168;
          if ( !this )
            v17 = 136;
          v10 = *(_DWORD *)v17 == a2->rclBounds.bottom;
LABEL_6:
          if ( v10 )
            return 0;
        }
      }
    }
  }
  if ( !a2->iDComplexity )
    goto LABEL_47;
  if ( a2->iDComplexity == 1 )
  {
    XLOutput::SetClipMode(this);
    XLWrite::WriteByte(this, 133);
    XLOutput::RectanglePath(this, &a2->rclBounds);
    XLOutput::SetClipRegion(this);
    XLWrite::WriteByte(this, 98);
    XLClip::SetClip((XLClip *)v3, a2);
    goto LABEL_20;
  }
  if ( a2->iDComplexity != 3 )
  {
LABEL_47:
    XLWrite::WriteByte(this, 105);
    v21 = (__int64)this + 148;
    if ( !this )
      v21 = 116;
    *(_DWORD *)v21 = 0;
    goto LABEL_20;
  }
  Path = CLIPOBJ_ppoGetPath(a2);
  if ( !Path )
  {
    XLWrite::WriteByte(this, 105);
    *(_DWORD *)(v3 + 4) = 0;
    goto LABEL_21;
  }
  XLOutput::SetClipMode(this);
  XLOutput::Path(this, Path, a3);
  XLOutput::SetClipRegion(this);
  XLWrite::WriteByte(this, 98);
  XLClip::SetClip((XLClip *)v3, a2);
  EngDeletePath(Path);
LABEL_20:
  v8 = 0;
LABEL_21:
  result = v8;
  *((_QWORD *)a3 + 1) = *((_QWORD *)a3 + 522);
  return result;
}

```

## disassembly

```asm
0x180012850  push    rbx
0x180012852  push    rbp
0x180012853  push    rsi
0x180012854  push    rdi
0x180012855  push    r14
0x180012857  push    r15
0x180012859  sub     rsp, 28h
0x18001285d  test    rcx, rcx
0x180012860  lea     rbp, [rcx+90h]
0x180012867  mov     eax, 70h ; 'p'
0x18001286c  mov     r15, r8
0x18001286f  cmovz   rbp, rax
0x180012873  mov     rdi, rdx
0x180012876  mov     rbx, rcx
0x180012879  test    rdx, rdx
0x18001287c  jz      short loc_180012897
0x18001287e  movzx   ecx, byte ptr [rdi+14h]
0x180012882  lea     r14d, [rax-6Fh]
0x180012886  mov     edx, [rbp+4]
0x180012889  test    ecx, ecx
0x18001288b  jnz     loc_180012946
0x180012891  test    edx, edx
0x180012893  jnz     short loc_1800128E0
0x180012895  jmp     short loc_1800128A1
0x180012897  cmp     dword ptr [rbp+4], 0
0x18001289b  jnz     loc_1800129CB
0x1800128a1  xor     eax, eax
0x1800128a3  add     rsp, 28h
0x1800128a7  pop     r15
0x1800128a9  pop     r14
0x1800128ab  pop     rdi
0x1800128ac  pop     rsi
0x1800128ad  pop     rbp
0x1800128ae  pop     rbx
0x1800128af  retn
0x1800128b1  cmp     ecx, 2
0x1800128b4  jnz     short loc_180012891
0x1800128b6  cmp     edx, ecx
0x1800128b8  jnz     short loc_1800128E0
0x1800128ba  test    rbx, rbx
0x1800128bd  lea     rax, [rbx+0ACh]
0x1800128c4  mov     ecx, 8Ch
0x1800128c9  cmovz   rax, rcx
0x1800128cd  mov     ecx, [rax]
0x1800128cf  test    ecx, ecx
0x1800128d1  jz      short loc_1800128E0
0x1800128d3  cmp     dword ptr [rdi], 0
0x1800128d6  jz      short loc_1800128E0
0x1800128d8  cmp     ecx, [rdi]
0x1800128da  jz      loc_180012A57
0x1800128e0  movzx   ecx, byte ptr [rdi+14h]
0x1800128e4  test    ecx, ecx
0x1800128e6  jz      loc_180012A92
0x1800128ec  sub     ecx, r14d
0x1800128ef  jnz     loc_1800129F0
0x1800128f5  mov     rcx, rbx
0x1800128f8  call    ?SetClipMode@XLOutput@@QEAAJW4ClipMode@@@Z; XLOutput::SetClipMode(ClipMode)
0x1800128fd  mov     dl, 85h; unsigned __int8
0x1800128ff  mov     rcx, rbx; this
0x180012902  call    ?WriteByte@XLWrite@@QEAAJE@Z; XLWrite::WriteByte(uchar)
0x180012907  lea     rdx, [rdi+4]; struct _RECTL *
0x18001290b  mov     rcx, rbx; this
0x18001290e  call    ?RectanglePath@XLOutput@@QEAAJPEBU_RECTL@@@Z; XLOutput::RectanglePath(_RECTL const *)
0x180012913  mov     rcx, rbx
0x180012916  call    ?SetClipRegion@XLOutput@@QEAAJW4ClipRegion@@@Z; XLOutput::SetClipRegion(ClipRegion)
0x18001291b  mov     dl, 62h ; 'b'; unsigned __int8
0x18001291d  mov     rcx, rbx; this
0x180012920  call    ?WriteByte@XLWrite@@QEAAJE@Z; XLWrite::WriteByte(uchar)
0x180012925  mov     rdx, rdi; struct _CLIPOBJ *
0x180012928  mov     rcx, rbp; this
0x18001292b  call    ?SetClip@XLClip@@QEAAJPEBU_CLIPOBJ@@@Z; XLClip::SetClip(_CLIPOBJ const *)
0x180012930  xor     r14d, r14d
0x180012933  mov     rcx, [r15+1050h]
0x18001293a  mov     eax, r14d
0x18001293d  mov     [r15+8], rcx
0x180012941  jmp     loc_1800128A3
0x180012946  sub     ecx, r14d
0x180012949  jnz     loc_1800128B1
0x18001294f  cmp     edx, r14d
0x180012952  jnz     short loc_1800128E0
0x180012954  test    rbx, rbx
0x180012957  lea     rcx, [rbx+9Ch]
0x18001295e  mov     eax, 7Ch ; '|'
0x180012963  cmovz   rcx, rax
0x180012967  mov     eax, [rdi+4]
0x18001296a  cmp     [rcx], eax
0x18001296c  jnz     loc_1800128E0
0x180012972  test    rbx, rbx
0x180012975  lea     rcx, [rbx+0A4h]
0x18001297c  mov     eax, 84h
0x180012981  cmovz   rcx, rax
0x180012985  mov     eax, [rdi+0Ch]
0x180012988  cmp     [rcx], eax
0x18001298a  jnz     loc_1800128E0
0x180012990  test    rbx, rbx
0x180012993  lea     rcx, [rbx+0A0h]
0x18001299a  mov     eax, 80h
0x18001299f  cmovz   rcx, rax
0x1800129a3  mov     eax, [rdi+8]
0x1800129a6  cmp     [rcx], eax
0x1800129a8  jnz     loc_1800128E0
0x1800129ae  test    rbx, rbx
0x1800129b1  lea     rcx, [rbx+0A8h]
0x1800129b8  mov     eax, 88h
0x1800129bd  cmovz   rcx, rax; this
0x1800129c1  mov     eax, [rdi+10h]
0x1800129c4  cmp     [rcx], eax
0x1800129c6  jmp     loc_180012893
0x1800129cb  mov     dl, 69h ; 'i'; unsigned __int8
0x1800129cd  call    ?WriteByte@XLWrite@@QEAAJE@Z; XLWrite::WriteByte(uchar)
0x1800129d2  test    rbx, rbx
0x1800129d5  lea     rax, [rbx+94h]
0x1800129dc  mov     ecx, 74h ; 't'
0x1800129e1  cmovz   rax, rcx
0x1800129e5  mov     dword ptr [rax], 0
0x1800129eb  jmp     loc_1800128A1
0x1800129f0  cmp     ecx, 2
0x1800129f3  jnz     loc_180012A92
0x1800129f9  mov     rcx, rdi; pco
0x1800129fc  call    cs:__imp_CLIPOBJ_ppoGetPath
0x180012a03  nop     dword ptr [rax+rax+00h]
0x180012a08  mov     rsi, rax
0x180012a0b  mov     rcx, rbx; this
0x180012a0e  test    rax, rax
0x180012a11  jz      short loc_180012A7F
0x180012a13  call    ?SetClipMode@XLOutput@@QEAAJW4ClipMode@@@Z; XLOutput::SetClipMode(ClipMode)
0x180012a18  mov     r8, r15; struct _DEVOBJ *
0x180012a1b  mov     rdx, rsi; ppo
0x180012a1e  mov     rcx, rbx; this
0x180012a21  call    ?Path@XLOutput@@QEAAJPEAU_PATHOBJ@@PEAU_DEVOBJ@@@Z; XLOutput::Path(_PATHOBJ *,_DEVOBJ *)
0x180012a26  mov     rcx, rbx
0x180012a29  call    ?SetClipRegion@XLOutput@@QEAAJW4ClipRegion@@@Z; XLOutput::SetClipRegion(ClipRegion)
0x180012a2e  mov     dl, 62h ; 'b'; unsigned __int8
0x180012a30  mov     rcx, rbx; this
0x180012a33  call    ?WriteByte@XLWrite@@QEAAJE@Z; XLWrite::WriteByte(uchar)
0x180012a38  mov     rdx, rdi; struct _CLIPOBJ *
0x180012a3b  mov     rcx, rbp; this
0x180012a3e  call    ?SetClip@XLClip@@QEAAJPEBU_CLIPOBJ@@@Z; XLClip::SetClip(_CLIPOBJ const *)
0x180012a43  mov     rcx, rsi; ppo
0x180012a46  call    cs:__imp_EngDeletePath
0x180012a4d  nop     dword ptr [rax+rax+00h]
0x180012a52  jmp     loc_180012930
0x180012a57  mov     eax, 90h
0x180012a5c  lea     rcx, [rbx+0B0h]
0x180012a63  test    rbx, rbx
0x180012a66  mov     rdx, rdi; struct _CLIPOBJ *
0x180012a69  cmovz   rcx, rax; this
0x180012a6d  call    ?Compare@XLClipRgn@@AEBAHPEBU_CLIPOBJ@@@Z; XLClipRgn::Compare(_CLIPOBJ const *)
0x180012a72  test    eax, eax
0x180012a74  jnz     loc_1800128A1
0x180012a7a  jmp     loc_1800128E0
0x180012a7f  mov     dl, 69h ; 'i'; unsigned __int8
0x180012a81  call    ?WriteByte@XLWrite@@QEAAJE@Z; XLWrite::WriteByte(uchar)
0x180012a86  mov     dword ptr [rbp+4], 0
0x180012a8d  jmp     loc_180012933
0x180012a92  mov     dl, 69h ; 'i'; unsigned __int8
0x180012a94  mov     rcx, rbx; this
0x180012a97  call    ?WriteByte@XLWrite@@QEAAJE@Z; XLWrite::WriteByte(uchar)
0x180012a9c  test    rbx, rbx
0x180012a9f  lea     rax, [rbx+94h]
0x180012aa6  mov     ecx, 74h ; 't'
0x180012aab  cmovz   rax, rcx
0x180012aaf  mov     dword ptr [rax], 0
0x180012ab5  jmp     loc_180012930
```
