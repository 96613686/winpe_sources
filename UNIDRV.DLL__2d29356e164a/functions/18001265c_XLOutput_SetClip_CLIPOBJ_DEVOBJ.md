# XLOutput::SetClip(_CLIPOBJ *,_DEVOBJ *)

- ea: `0x18001265c`
- end: `0x1800128b9`
- name: `?SetClip@XLOutput@@QEAAJPEAU_CLIPOBJ@@PEAU_DEVOBJ@@@Z`
- size: `605`
- prototype: `__int64 __fastcall(XLOutput *__hidden this, struct _CLIPOBJ *, struct _DEVOBJ *)`
- caller_count: `6`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000edc0`
- `0x18000fde0`
- `0x1800128c0`
- `0x180015380`
- `0x1800427a0`
- `0x18006d070`

## callees

- `0x180011fc0`
- `0x18001265c`
- `0x180013e00`
- `0x1800373c0`
- `0x18003bf7c`
- `0x18003c708`
- `0x18003d590`
- `0x1800452d0`

## import_xrefs

- `GDI32!CLIPOBJ_ppoGetPath` at `0x180012807`
- `GDI32!CLIPOBJ_ppoGetPath` at `0x180012807`
- `GDI32!EngDeletePath` at `0x18001284b`
- `GDI32!EngDeletePath` at `0x18001284b`

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
      XLWrite::WriteByte(this, 0x69u);
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
        if ( XLClipRgn::Compare((XLClipRgn *)v20, a2) )
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
    XLWrite::WriteByte(this, 0x85u);
    XLOutput::RectanglePath(this, &a2->rclBounds);
    XLOutput::SetClipRegion(this);
    XLWrite::WriteByte(this, 0x62u);
    XLClip::SetClip((XLClip *)v3, a2);
    goto LABEL_20;
  }
  if ( a2->iDComplexity != 3 )
  {
LABEL_47:
    XLWrite::WriteByte(this, 0x69u);
    v21 = (__int64)this + 148;
    if ( !this )
      v21 = 116;
    *(_DWORD *)v21 = 0;
    goto LABEL_20;
  }
  Path = CLIPOBJ_ppoGetPath(a2);
  if ( !Path )
  {
    XLWrite::WriteByte(this, 0x69u);
    *(_DWORD *)(v3 + 4) = 0;
    goto LABEL_21;
  }
  XLOutput::SetClipMode(this);
  XLOutput::Path(this, Path, a3);
  XLOutput::SetClipRegion(this);
  XLWrite::WriteByte(this, 0x62u);
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
0x18001265c  push    rbx
0x18001265e  push    rbp
0x18001265f  push    rsi
0x180012660  push    rdi
0x180012661  push    r14
0x180012663  push    r15
0x180012665  sub     rsp, 28h
0x180012669  test    rcx, rcx
0x18001266c  lea     rbp, [rcx+90h]
0x180012673  mov     eax, 70h ; 'p'
0x180012678  mov     r15, r8
0x18001267b  cmovz   rbp, rax
0x18001267f  mov     rdi, rdx
0x180012682  mov     rbx, rcx
0x180012685  test    rdx, rdx
0x180012688  jz      short loc_1800126A3
0x18001268a  movzx   ecx, byte ptr [rdi+14h]
0x18001268e  lea     r14d, [rax-6Fh]
0x180012692  mov     edx, [rbp+4]
0x180012695  test    ecx, ecx
0x180012697  jnz     loc_180012751
0x18001269d  test    edx, edx
0x18001269f  jnz     short loc_1800126EB
0x1800126a1  jmp     short loc_1800126AD
0x1800126a3  cmp     dword ptr [rbp+4], 0
0x1800126a7  jnz     loc_1800127D6
0x1800126ad  xor     eax, eax
0x1800126af  add     rsp, 28h
0x1800126b3  pop     r15
0x1800126b5  pop     r14
0x1800126b7  pop     rdi
0x1800126b8  pop     rsi
0x1800126b9  pop     rbp
0x1800126ba  pop     rbx
0x1800126bb  retn
0x1800126bc  cmp     ecx, 2
0x1800126bf  jnz     short loc_18001269D
0x1800126c1  cmp     edx, ecx
0x1800126c3  jnz     short loc_1800126EB
0x1800126c5  test    rbx, rbx
0x1800126c8  lea     rax, [rbx+0ACh]
0x1800126cf  mov     ecx, 8Ch
0x1800126d4  cmovz   rax, rcx
0x1800126d8  mov     ecx, [rax]
0x1800126da  test    ecx, ecx
0x1800126dc  jz      short loc_1800126EB
0x1800126de  cmp     dword ptr [rdi], 0
0x1800126e1  jz      short loc_1800126EB
0x1800126e3  cmp     ecx, [rdi]
0x1800126e5  jz      loc_180012856
0x1800126eb  movzx   ecx, byte ptr [rdi+14h]
0x1800126ef  test    ecx, ecx
0x1800126f1  jz      loc_180012891
0x1800126f7  sub     ecx, r14d
0x1800126fa  jnz     loc_1800127FB
0x180012700  mov     rcx, rbx
0x180012703  call    ?SetClipMode@XLOutput@@QEAAJW4ClipMode@@@Z; XLOutput::SetClipMode(ClipMode)
0x180012708  mov     dl, 85h; unsigned __int8
0x18001270a  mov     rcx, rbx; this
0x18001270d  call    ?WriteByte@XLWrite@@QEAAJE@Z; XLWrite::WriteByte(uchar)
0x180012712  lea     rdx, [rdi+4]; struct _RECTL *
0x180012716  mov     rcx, rbx; this
0x180012719  call    ?RectanglePath@XLOutput@@QEAAJPEBU_RECTL@@@Z; XLOutput::RectanglePath(_RECTL const *)
0x18001271e  mov     rcx, rbx
0x180012721  call    ?SetClipRegion@XLOutput@@QEAAJW4ClipRegion@@@Z; XLOutput::SetClipRegion(ClipRegion)
0x180012726  mov     dl, 62h ; 'b'; unsigned __int8
0x180012728  mov     rcx, rbx; this
0x18001272b  call    ?WriteByte@XLWrite@@QEAAJE@Z; XLWrite::WriteByte(uchar)
0x180012730  mov     rdx, rdi; struct _CLIPOBJ *
0x180012733  mov     rcx, rbp; this
0x180012736  call    ?SetClip@XLClip@@QEAAJPEBU_CLIPOBJ@@@Z; XLClip::SetClip(_CLIPOBJ const *)
0x18001273b  xor     r14d, r14d
0x18001273e  mov     rcx, [r15+1050h]
0x180012745  mov     eax, r14d
0x180012748  mov     [r15+8], rcx
0x18001274c  jmp     loc_1800126AF
0x180012751  sub     ecx, r14d
0x180012754  jnz     loc_1800126BC
0x18001275a  cmp     edx, r14d
0x18001275d  jnz     short loc_1800126EB
0x18001275f  test    rbx, rbx
0x180012762  lea     rcx, [rbx+9Ch]
0x180012769  mov     eax, 7Ch ; '|'
0x18001276e  cmovz   rcx, rax
0x180012772  mov     eax, [rdi+4]
0x180012775  cmp     [rcx], eax
0x180012777  jnz     loc_1800126EB
0x18001277d  test    rbx, rbx
0x180012780  lea     rcx, [rbx+0A4h]
0x180012787  mov     eax, 84h
0x18001278c  cmovz   rcx, rax
0x180012790  mov     eax, [rdi+0Ch]
0x180012793  cmp     [rcx], eax
0x180012795  jnz     loc_1800126EB
0x18001279b  test    rbx, rbx
0x18001279e  lea     rcx, [rbx+0A0h]
0x1800127a5  mov     eax, 80h
0x1800127aa  cmovz   rcx, rax
0x1800127ae  mov     eax, [rdi+8]
0x1800127b1  cmp     [rcx], eax
0x1800127b3  jnz     loc_1800126EB
0x1800127b9  test    rbx, rbx
0x1800127bc  lea     rcx, [rbx+0A8h]
0x1800127c3  mov     eax, 88h
0x1800127c8  cmovz   rcx, rax; this
0x1800127cc  mov     eax, [rdi+10h]
0x1800127cf  cmp     [rcx], eax
0x1800127d1  jmp     loc_18001269F
0x1800127d6  mov     dl, 69h ; 'i'; unsigned __int8
0x1800127d8  call    ?WriteByte@XLWrite@@QEAAJE@Z; XLWrite::WriteByte(uchar)
0x1800127dd  test    rbx, rbx
0x1800127e0  lea     rax, [rbx+94h]
0x1800127e7  mov     ecx, 74h ; 't'
0x1800127ec  cmovz   rax, rcx
0x1800127f0  mov     dword ptr [rax], 0
0x1800127f6  jmp     loc_1800126AD
0x1800127fb  cmp     ecx, 2
0x1800127fe  jnz     loc_180012891
0x180012804  mov     rcx, rdi; pco
0x180012807  call    cs:__imp_CLIPOBJ_ppoGetPath
0x18001280d  mov     rsi, rax
0x180012810  mov     rcx, rbx; this
0x180012813  test    rax, rax
0x180012816  jz      short loc_18001287E
0x180012818  call    ?SetClipMode@XLOutput@@QEAAJW4ClipMode@@@Z; XLOutput::SetClipMode(ClipMode)
0x18001281d  mov     r8, r15; struct _DEVOBJ *
0x180012820  mov     rdx, rsi; ppo
0x180012823  mov     rcx, rbx; this
0x180012826  call    ?Path@XLOutput@@QEAAJPEAU_PATHOBJ@@PEAU_DEVOBJ@@@Z; XLOutput::Path(_PATHOBJ *,_DEVOBJ *)
0x18001282b  mov     rcx, rbx
0x18001282e  call    ?SetClipRegion@XLOutput@@QEAAJW4ClipRegion@@@Z; XLOutput::SetClipRegion(ClipRegion)
0x180012833  mov     dl, 62h ; 'b'; unsigned __int8
0x180012835  mov     rcx, rbx; this
0x180012838  call    ?WriteByte@XLWrite@@QEAAJE@Z; XLWrite::WriteByte(uchar)
0x18001283d  mov     rdx, rdi; struct _CLIPOBJ *
0x180012840  mov     rcx, rbp; this
0x180012843  call    ?SetClip@XLClip@@QEAAJPEBU_CLIPOBJ@@@Z; XLClip::SetClip(_CLIPOBJ const *)
0x180012848  mov     rcx, rsi; ppo
0x18001284b  call    cs:__imp_EngDeletePath
0x180012851  jmp     loc_18001273B
0x180012856  mov     eax, 90h
0x18001285b  lea     rcx, [rbx+0B0h]
0x180012862  test    rbx, rbx
0x180012865  mov     rdx, rdi; struct _CLIPOBJ *
0x180012868  cmovz   rcx, rax; this
0x18001286c  call    ?Compare@XLClipRgn@@AEBAHPEBU_CLIPOBJ@@@Z; XLClipRgn::Compare(_CLIPOBJ const *)
0x180012871  test    eax, eax
0x180012873  jnz     loc_1800126AD
0x180012879  jmp     loc_1800126EB
0x18001287e  mov     dl, 69h ; 'i'; unsigned __int8
0x180012880  call    ?WriteByte@XLWrite@@QEAAJE@Z; XLWrite::WriteByte(uchar)
0x180012885  mov     dword ptr [rbp+4], 0
0x18001288c  jmp     loc_18001273E
0x180012891  mov     dl, 69h ; 'i'; unsigned __int8
0x180012893  mov     rcx, rbx; this
0x180012896  call    ?WriteByte@XLWrite@@QEAAJE@Z; XLWrite::WriteByte(uchar)
0x18001289b  test    rbx, rbx
0x18001289e  lea     rax, [rbx+94h]
0x1800128a5  mov     ecx, 74h ; 't'
0x1800128aa  cmovz   rax, rcx
0x1800128ae  mov     dword ptr [rax], 0
0x1800128b4  jmp     loc_18001273B
```
