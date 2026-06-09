# PCLXLFillPath

- ea: `0x180012f00`
- end: `0x1800136a1`
- name: `PCLXLFillPath`
- size: `1953`
- prototype: `__int64(__int64, PATHOBJ *, const struct _CLIPOBJ *, struct _BRUSHOBJ *, int, ...)`
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x180011ed0`
- `0x180012160`
- `0x180012f00`
- `0x1800136a8`
- `0x180013b70`
- `0x180014040`
- `0x180015540`
- `0x18001cc14`
- `0x18001cc70`
- `0x180037e04`
- `0x18003cd38`
- `0x18003d4e8`
- `0x18003e350`
- `0x180045c00`
- `0x1800461b4`
- `0x180046654`
- `0x18006eb70`
- `0x180076660`

## import_xrefs

- `GDI32!CLIPOBJ_ppoGetPath` at `0x180013501`
- `GDI32!CLIPOBJ_ppoGetPath` at `0x180013501`
- `GDI32!EngDeletePath` at `0x180013554`
- `GDI32!EngDeletePath` at `0x180013554`

## pseudocode

```c
__int64 PCLXLFillPath(__int64 a1, PATHOBJ *a2, struct _CLIPOBJ *a3, struct _BRUSHOBJ *a4, int a5, ...)
{
  unsigned int v5; // ebp
  unsigned int v6; // esi
  __int64 v7; // rdi
  int v8; // r12d
  __int64 v9; // rbx
  char v10; // r15
  __int64 v11; // r14
  __int64 v12; // r11
  __int64 v13; // r10
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 v16; // r13
  __int64 v17; // r8
  int iDComplexity; // eax
  int v19; // ecx
  __int64 v20; // r14
  __int64 v21; // rbp
  __int64 v22; // rbp
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // rdx
  const struct _POINTL *v28; // r8
  __int64 v29; // r8
  void *v30; // r14
  int v31; // eax
  size_t v32; // rbp
  __int64 v33; // rax
  __int64 v34; // rax
  bool v36; // zf
  CLIPOBJ *v37; // rcx
  PATHOBJ *Path; // r13
  __int64 v39; // [rsp+20h] [rbp-58h]
  __int64 v43; // [rsp+A8h] [rbp+30h] BYREF
  va_list va; // [rsp+A8h] [rbp+30h]
  __int64 v45; // [rsp+B0h] [rbp+38h]
  va_list va1; // [rsp+B8h] [rbp+40h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v43 = va_arg(va1, _QWORD);
  v45 = va_arg(va1, _QWORD);
  v5 = *((_BYTE *)qword_180080778 + (v43 & 0xF)) & 0xF
     | *((_BYTE *)qword_180080778 + (((unsigned int)v43 >> 8) & 0xF)) & 0xF0;
  if ( v5 != 170 )
  {
    v6 = 1;
    v7 = *(_QWORD *)(a1 + 16);
    v8 = v5 >> 4 == (v5 & 0xF);
    v9 = *(_QWORD *)(*(_QWORD *)(v7 + 8) + 160LL);
    if ( (_DWORD)v45 == 1 )
    {
      v10 = 1;
    }
    else
    {
      v10 = 0;
      if ( (_DWORD)v45 == 2 )
        v10 = 0;
    }
    if ( v9 )
    {
      v39 = v9 + 148;
      v11 = v9 + 144;
      v12 = v9 + 168;
      v13 = v9 + 160;
      v14 = v9 + 164;
      v15 = v9 + 156;
      v16 = v9 + 176;
      v17 = v9 + 172;
    }
    else
    {
      v39 = 116;
      v15 = 124;
      v11 = 112;
      v12 = 136;
      v13 = 128;
      v14 = 132;
      v16 = 144;
      v17 = 140;
    }
    if ( !a3 )
    {
      if ( *(_DWORD *)(v11 + 4) )
      {
        XLWrite::WriteByte((XLWrite *)v9, 105);
        *(_DWORD *)v39 = 0;
      }
      goto LABEL_9;
    }
    iDComplexity = a3->iDComplexity;
    v19 = *(_DWORD *)(v11 + 4);
    LODWORD(v43) = iDComplexity;
    if ( !iDComplexity )
    {
      if ( !v19 )
        goto LABEL_9;
      goto LABEL_98;
    }
    LOBYTE(iDComplexity) = v43;
    if ( (_DWORD)v43 == 1 )
    {
      v36 = v19 == 1;
      v37 = a3;
      if ( v36 )
      {
        if ( *(_DWORD *)v15 == a3->rclBounds.left
          && *(_DWORD *)v14 == a3->rclBounds.right
          && *(_DWORD *)v13 == a3->rclBounds.top
          && *(_DWORD *)v12 == a3->rclBounds.bottom )
        {
          goto LABEL_9;
        }
        LOBYTE(iDComplexity) = v43;
      }
    }
    else
    {
      if ( (_DWORD)v43 != 3 )
      {
        if ( !v19 )
          goto LABEL_9;
LABEL_98:
        v37 = a3;
        goto LABEL_71;
      }
      v36 = v19 == 2;
      v37 = a3;
      if ( v36 && *(_DWORD *)v17 && a3->iUniq && *(_DWORD *)v17 == a3->iUniq )
      {
        if ( (unsigned int)XLClipRgn::Compare((XLClipRgn *)v16, a3) )
          goto LABEL_9;
        v37 = a3;
        LOBYTE(iDComplexity) = a3->iDComplexity;
      }
    }
LABEL_71:
    if ( (_BYTE)iDComplexity == 1 )
    {
      XLOutput::SetClipMode((XLWrite *)v9);
      XLWrite::WriteByte((XLWrite *)v9, 133);
      XLOutput::RectanglePath((XLOutput *)v9, &a3->rclBounds);
      XLOutput::SetClipRegion((XLWrite *)v9);
      XLWrite::WriteByte((XLWrite *)v9, 98);
      XLClip::SetClip((XLClip *)v11, a3);
    }
    else
    {
      if ( (_BYTE)iDComplexity == 3 )
      {
        Path = CLIPOBJ_ppoGetPath(v37);
        if ( !Path )
        {
          XLWrite::WriteByte((XLWrite *)v9, 105);
          *(_DWORD *)(v11 + 4) = 0;
          *(_QWORD *)(v7 + 8) = *(_QWORD *)(v7 + 4176);
          goto LABEL_55;
        }
        XLOutput::SetClipMode((XLWrite *)v9);
        XLOutput::Path((XLOutput *)v9, Path, (struct _DEVOBJ *)v7);
        XLOutput::SetClipRegion((XLWrite *)v9);
        XLWrite::WriteByte((XLWrite *)v9, 98);
        XLClip::SetClip((XLClip *)v11, a3);
        EngDeletePath(Path);
        *(_QWORD *)(v7 + 8) = *(_QWORD *)(v7 + 4176);
LABEL_9:
        v20 = v9 + 204;
        if ( !v9 )
          v20 = 172;
        if ( v5 != *(_DWORD *)v20 )
        {
          if ( (unsigned int)XLOutput::Send_ubyte((XLOutput *)v9, v5) || (unsigned int)XLOutput::Send_attr_ubyte(v9, 44) )
            goto LABEL_55;
          XLWrite::WriteByte((XLWrite *)v9, 123);
          *(_DWORD *)v20 = v5;
        }
        v21 = v9 + 32;
        if ( !v9 )
          v21 = 0;
        if ( v8 != *(_DWORD *)(v21 + 228) )
        {
          if ( (unsigned int)XLOutput::SetTxMode((XLWrite *)v9, v8) )
            goto LABEL_55;
          XLWrite::WriteByte((XLWrite *)v9, 120);
          *(_DWORD *)(v21 + 228) = v8;
        }
        v22 = 0;
        if ( v9 )
          v22 = v9 + 32;
        if ( v8 != *(_DWORD *)(v22 + 224) )
        {
          if ( (unsigned int)XLOutput::SetTxMode((XLWrite *)v9, v8) )
            goto LABEL_55;
          XLWrite::WriteByte((XLWrite *)v9, 124);
          *(_DWORD *)(v22 + 224) = v8;
        }
        v23 = *(unsigned int *)(v9 + 28);
        if ( (int)v23 + 1 >= (unsigned int)v23
          && (*(unsigned int *)(v9 + 24) >= (unsigned __int64)(v23 + 8)
           || !(unsigned int)XLWrite::IncreaseBuffer((XLWrite *)v9, 8))
          && *(_QWORD *)(v9 + 8) )
        {
          *(_BYTE *)(*(_QWORD *)(v9 + 16))++ = -64;
          ++*(_DWORD *)(v9 + 28);
        }
        v24 = *(unsigned int *)(v9 + 28);
        if ( (int)v24 + 1 >= (unsigned int)v24
          && (*(unsigned int *)(v9 + 24) >= (unsigned __int64)(v24 + 8)
           || !(unsigned int)XLWrite::IncreaseBuffer((XLWrite *)v9, 8))
          && *(_QWORD *)(v9 + 8) )
        {
          *(_BYTE *)(*(_QWORD *)(v9 + 16))++ = v10;
          ++*(_DWORD *)(v9 + 28);
        }
        v25 = *(unsigned int *)(v9 + 28);
        if ( (int)v25 + 1 >= (unsigned int)v25
          && (*(unsigned int *)(v9 + 24) >= (unsigned __int64)(v25 + 8)
           || !(unsigned int)XLWrite::IncreaseBuffer((XLWrite *)v9, 8))
          && *(_QWORD *)(v9 + 8) )
        {
          *(_BYTE *)(*(_QWORD *)(v9 + 16))++ = -8;
          ++*(_DWORD *)(v9 + 28);
        }
        v26 = *(unsigned int *)(v9 + 28);
        if ( (int)v26 + 1 >= (unsigned int)v26
          && (*(unsigned int *)(v9 + 24) >= (unsigned __int64)(v26 + 8)
           || !(unsigned int)XLWrite::IncreaseBuffer((XLWrite *)v9, 8))
          && *(_QWORD *)(v9 + 8) )
        {
          *(_BYTE *)(*(_QWORD *)(v9 + 16))++ = 70;
          ++*(_DWORD *)(v9 + 28);
        }
        v27 = *(unsigned int *)(v9 + 28);
        if ( (int)v27 + 1 >= (unsigned int)v27
          && (*(unsigned int *)(v9 + 24) >= (unsigned __int64)(v27 + 8)
           || !(unsigned int)XLWrite::IncreaseBuffer((XLWrite *)v9, 8))
          && *(_QWORD *)(v9 + 8) )
        {
          *(_BYTE *)(*(_QWORD *)(v9 + 16))++ = 110;
          ++*(_DWORD *)(v9 + 28);
        }
        if ( !(unsigned int)XLOutput::SetPenColor((XLOutput *)v9, 0, (struct _POINTL *)v17, (struct _DEVOBJ *)v7)
          && !(unsigned int)XLOutput::SetBrush((XLOutput *)v9, a4, v28, (struct _DEVOBJ *)v7)
          && !(unsigned int)XLOutput::Path((XLOutput *)v9, a2, (struct _DEVOBJ *)v7) )
        {
          v29 = *(unsigned int *)(v9 + 28);
          if ( (int)v29 + 1 >= (unsigned int)v29
            && (*(unsigned int *)(v9 + 24) >= (unsigned __int64)(v29 + 8)
             || !(unsigned int)XLWrite::IncreaseBuffer((XLWrite *)v9, 8))
            && *(_QWORD *)(v9 + 8) )
          {
            *(_BYTE *)(*(_QWORD *)(v9 + 16))++ = -122;
            ++*(_DWORD *)(v9 + 28);
          }
          v30 = *(void **)(v9 + 8);
          if ( v30 )
          {
            if ( v7 )
            {
              LODWORD(v43) = 0;
              if ( (*(_BYTE *)(v7 + 112) & 1) == 0 )
              {
                v31 = *(_DWORD *)(v7 + 4104);
                v32 = *(int *)(v9 + 28);
                if ( v31 && (int)v32 + v31 > 4096 && !(unsigned int)FlushSpoolBuf(v7) )
                {
                  WriteAbortBuf(v7, *(char **)(v7 + 4112), *(_DWORD *)(v7 + 4104), 0);
                  *(_DWORD *)(v7 + 4104) = 0;
                  *(_QWORD *)(v9 + 16) = *(_QWORD *)(v9 + 8);
                  *(_DWORD *)(v9 + 28) = 0;
                  return v6;
                }
                if ( (int)v32 >= 4096 )
                {
                  if ( !(unsigned int)BUniWritePrinter(v7, v30, v32, (DWORD *)va) )
                  {
                    *(_DWORD *)(v7 + 112) |= 1u;
                    *(_DWORD *)(v7 + 4104) = 0;
                  }
                }
                else
                {
                  v33 = *(_QWORD *)(v7 + 4112);
                  if ( v33 )
                  {
                    memcpy_0((void *)(v33 + *(int *)(v7 + 4104)), v30, v32);
                    *(_DWORD *)(v7 + 4104) += v32;
                  }
                }
              }
              *(_QWORD *)(v9 + 16) = *(_QWORD *)(v9 + 8);
              *(_DWORD *)(v9 + 28) = 0;
              return v6;
            }
          }
        }
LABEL_55:
        v34 = *(_QWORD *)(v9 + 8);
        if ( v34 )
        {
          *(_DWORD *)(v9 + 28) = 0;
          *(_QWORD *)(v9 + 16) = v34;
        }
        return 0;
      }
      XLWrite::WriteByte((XLWrite *)v9, 105);
      *(_DWORD *)v39 = 0;
    }
    *(_QWORD *)(v7 + 8) = *(_QWORD *)(v7 + 4176);
    goto LABEL_9;
  }
  return 1;
}

```

## disassembly

```asm
0x180012f00  mov     r11, rsp
0x180012f03  mov     [r11+20h], r9
0x180012f07  mov     [r11+18h], r8
0x180012f0b  mov     [r11+10h], rdx
0x180012f0f  push    rbp
0x180012f10  push    rsi
0x180012f11  sub     rsp, 68h
0x180012f15  mov     r10d, dword ptr [rsp+78h+arg_28]
0x180012f1d  lea     rdx, qword_180080778
0x180012f24  mov     eax, r10d
0x180012f27  and     r10d, 0Fh
0x180012f2b  shr     rax, 8
0x180012f2f  and     eax, 0Fh
0x180012f32  movzx   ebp, byte ptr [rax+rdx]
0x180012f36  movzx   eax, byte ptr [r10+rdx]
0x180012f3b  and     ebp, 0F0h
0x180012f41  and     eax, 0Fh
0x180012f44  or      ebp, eax
0x180012f46  cmp     ebp, 0AAh
0x180012f4c  jz      loc_180013570
0x180012f52  mov     [r11-18h], rbx
0x180012f56  mov     eax, ebp
0x180012f58  mov     [r11-20h], rdi
0x180012f5c  mov     esi, 1
0x180012f61  mov     rdi, [rcx+10h]
0x180012f65  mov     ecx, ebp
0x180012f67  mov     [r11-28h], r12
0x180012f6b  and     ecx, 0Fh
0x180012f6e  xor     r12d, r12d
0x180012f71  shr     eax, 4
0x180012f74  cmp     eax, ecx
0x180012f76  mov     [r11-40h], r15
0x180012f7a  mov     rbx, [rdi+8]
0x180012f7e  mov     ecx, dword ptr [rsp+78h+arg_30]
0x180012f85  setz    r12b
0x180012f89  mov     rbx, [rbx+0A0h]
0x180012f90  cmp     ecx, esi
0x180012f92  jnz     loc_1800132C3
0x180012f98  mov     r15d, esi
0x180012f9b  mov     [rsp+78h+var_30], r13
0x180012fa0  mov     [rsp+78h+var_38], r14
0x180012fa5  test    rbx, rbx
0x180012fa8  jz      loc_180013281
0x180012fae  lea     rcx, [rbx+94h]
0x180012fb5  mov     [rsp+78h+var_58], rcx
0x180012fba  lea     r14, [rbx+90h]
0x180012fc1  lea     r11, [rbx+0A8h]
0x180012fc8  lea     r10, [rbx+0A0h]
0x180012fcf  lea     r9, [rbx+0A4h]
0x180012fd6  lea     rdx, [rbx+9Ch]
0x180012fdd  lea     r13, [rbx+0B0h]
0x180012fe4  lea     r8, [rbx+0ACh]; struct _POINTL *
0x180012feb  mov     rax, [rsp+78h+pco]
0x180012ff3  test    rax, rax
0x180012ff6  jz      loc_1800132D4
0x180012ffc  movzx   eax, byte ptr [rax+14h]
0x180013000  mov     ecx, [r14+4]
0x180013004  mov     dword ptr [rsp+78h+arg_28], eax
0x18001300b  test    eax, eax
0x18001300d  jnz     loc_180013319
0x180013013  test    ecx, ecx
0x180013015  jnz     loc_180013585
0x18001301b  lea     r14, [rbx+0CCh]
0x180013022  test    rbx, rbx
0x180013025  jz      loc_1800132B8
0x18001302b  cmp     ebp, [r14]
0x18001302e  jnz     loc_180013236
0x180013034  xor     eax, eax
0x180013036  lea     r14, [rbx+20h]
0x18001303a  test    rbx, rbx
0x18001303d  mov     rbp, r14
0x180013040  cmovz   rbp, rax
0x180013044  cmp     r12d, [rbp+0E4h]
0x18001304b  jnz     loc_18001363F
0x180013051  xor     ebp, ebp
0x180013053  test    rbx, rbx
0x180013056  cmovnz  rbp, r14
0x18001305a  cmp     r12d, [rbp+0E0h]
0x180013061  jnz     loc_180013668
0x180013067  mov     edx, [rbx+1Ch]
0x18001306a  lea     eax, [rdx+1]
0x18001306d  cmp     eax, edx
0x18001306f  jb      short loc_180013096
0x180013071  mov     ecx, [rbx+18h]
0x180013074  lea     rax, [rdx+8]
0x180013078  cmp     rcx, rax
0x18001307b  jb      loc_18001340E
0x180013081  cmp     qword ptr [rbx+8], 0
0x180013086  jz      short loc_180013096
0x180013088  mov     rax, [rbx+10h]
0x18001308c  mov     byte ptr [rax], 0C0h
0x18001308f  inc     qword ptr [rbx+10h]
0x180013093  inc     dword ptr [rbx+1Ch]
0x180013096  mov     edx, [rbx+1Ch]
0x180013099  lea     eax, [rdx+1]
0x18001309c  cmp     eax, edx
0x18001309e  jb      short loc_1800130C5
0x1800130a0  mov     ecx, [rbx+18h]
0x1800130a3  lea     rax, [rdx+8]
0x1800130a7  cmp     rcx, rax
0x1800130aa  jb      loc_180013428
0x1800130b0  cmp     qword ptr [rbx+8], 0
0x1800130b5  jz      short loc_1800130C5
0x1800130b7  mov     rax, [rbx+10h]
0x1800130bb  mov     [rax], r15b
0x1800130be  inc     qword ptr [rbx+10h]
0x1800130c2  inc     dword ptr [rbx+1Ch]
0x1800130c5  mov     edx, [rbx+1Ch]
0x1800130c8  lea     eax, [rdx+1]
0x1800130cb  cmp     eax, edx
0x1800130cd  jb      short loc_1800130F4
0x1800130cf  mov     ecx, [rbx+18h]
0x1800130d2  lea     rax, [rdx+8]
0x1800130d6  cmp     rcx, rax
0x1800130d9  jb      loc_180013442
0x1800130df  cmp     qword ptr [rbx+8], 0
0x1800130e4  jz      short loc_1800130F4
0x1800130e6  mov     rax, [rbx+10h]
0x1800130ea  mov     byte ptr [rax], 0F8h
0x1800130ed  inc     qword ptr [rbx+10h]
0x1800130f1  inc     dword ptr [rbx+1Ch]
0x1800130f4  mov     edx, [rbx+1Ch]
0x1800130f7  lea     eax, [rdx+1]
0x1800130fa  cmp     eax, edx
0x1800130fc  jb      short loc_180013123
0x1800130fe  mov     ecx, [rbx+18h]
0x180013101  lea     rax, [rdx+8]
0x180013105  cmp     rcx, rax
0x180013108  jb      loc_18001345C
0x18001310e  cmp     qword ptr [rbx+8], 0
0x180013113  jz      short loc_180013123
0x180013115  mov     rax, [rbx+10h]
0x180013119  mov     byte ptr [rax], 46h ; 'F'
0x18001311c  inc     qword ptr [rbx+10h]
0x180013120  inc     dword ptr [rbx+1Ch]
0x180013123  mov     edx, [rbx+1Ch]
0x180013126  lea     eax, [rdx+1]
0x180013129  cmp     eax, edx
0x18001312b  jb      short loc_180013152
0x18001312d  mov     ecx, [rbx+18h]
0x180013130  lea     rax, [rdx+8]
0x180013134  cmp     rcx, rax
0x180013137  jb      loc_180013476
0x18001313d  cmp     qword ptr [rbx+8], 0
0x180013142  jz      short loc_180013152
0x180013144  mov     rax, [rbx+10h]
0x180013148  mov     byte ptr [rax], 6Eh ; 'n'
0x18001314b  inc     qword ptr [rbx+10h]
0x18001314f  inc     dword ptr [rbx+1Ch]
0x180013152  mov     r9, rdi; struct _DEVOBJ *
0x180013155  xor     edx, edx; struct _BRUSHOBJ *
0x180013157  mov     rcx, rbx; this
0x18001315a  call    ?SetPenColor@XLOutput@@QEAAJPEAU_BRUSHOBJ@@PEAU_POINTL@@PEAU_DEVOBJ@@@Z; XLOutput::SetPenColor(_BRUSHOBJ *,_POINTL *,_DEVOBJ *)
0x18001315f  test    eax, eax
0x180013161  jnz     loc_18001324A
0x180013167  mov     rdx, [rsp+78h+arg_18]; struct _BRUSHOBJ *
0x18001316f  mov     r9, rdi; struct _DEVOBJ *
0x180013172  mov     rcx, rbx; this
0x180013175  call    ?SetBrush@XLOutput@@QEAAJPEAU_BRUSHOBJ@@PEBU_POINTL@@PEAU_DEVOBJ@@@Z; XLOutput::SetBrush(_BRUSHOBJ *,_POINTL const *,_DEVOBJ *)
0x18001317a  test    eax, eax
0x18001317c  jnz     loc_18001324A
0x180013182  mov     rdx, [rsp+78h+ppo]; ppo
0x18001318a  mov     r8, rdi; struct _DEVOBJ *
0x18001318d  mov     rcx, rbx; this
0x180013190  call    ?Path@XLOutput@@QEAAJPEAU_PATHOBJ@@PEAU_DEVOBJ@@@Z; XLOutput::Path(_PATHOBJ *,_DEVOBJ *)
0x180013195  test    eax, eax
0x180013197  jnz     loc_18001324A
0x18001319d  mov     r8d, [rbx+1Ch]
0x1800131a1  lea     eax, [r8+1]
0x1800131a5  cmp     eax, r8d
0x1800131a8  jb      short loc_1800131CF
0x1800131aa  mov     ecx, [rbx+18h]
0x1800131ad  lea     rax, [r8+8]
0x1800131b1  cmp     rcx, rax
0x1800131b4  jb      loc_180013490
0x1800131ba  cmp     qword ptr [rbx+8], 0
0x1800131bf  jz      short loc_1800131CF
0x1800131c1  mov     rax, [rbx+10h]
0x1800131c5  mov     byte ptr [rax], 86h
0x1800131c8  inc     qword ptr [rbx+10h]
0x1800131cc  inc     dword ptr [rbx+1Ch]
0x1800131cf  mov     r14, [rbx+8]
0x1800131d3  test    r14, r14
0x1800131d6  jz      short loc_18001324A
0x1800131d8  test    rdi, rdi
0x1800131db  jz      short loc_18001324A
0x1800131dd  mov     dword ptr [rsp+78h+arg_28], 0
0x1800131e8  test    [rdi+70h], sil
0x1800131ec  jnz     short loc_180013225
0x1800131ee  mov     eax, [rdi+1008h]
0x1800131f4  movsxd  rbp, dword ptr [rbx+1Ch]
0x1800131f8  test    eax, eax
0x1800131fa  jz      short loc_180013209
0x1800131fc  add     eax, ebp
0x1800131fe  cmp     eax, 1000h
0x180013203  jg      loc_1800134AA
0x180013209  cmp     ebp, 1000h
0x18001320f  jge     loc_1800133E2
0x180013215  mov     rax, [rdi+1010h]
0x18001321c  test    rax, rax
0x18001321f  jnz     loc_1800132F9
0x180013225  mov     rax, [rbx+8]
0x180013229  mov     [rbx+10h], rax
0x18001322d  mov     dword ptr [rbx+1Ch], 0
0x180013234  jmp     short loc_180013259
0x180013236  movzx   edx, bpl; unsigned __int8
0x18001323a  mov     rcx, rbx; this
0x18001323d  call    ?Send_ubyte@XLOutput@@QEAAJE@Z; XLOutput::Send_ubyte(uchar)
0x180013242  test    eax, eax
0x180013244  jz      loc_180013618
0x18001324a  mov     rax, [rbx+8]
0x18001324e  test    rax, rax
0x180013251  jnz     loc_180013691
0x180013257  xor     esi, esi
0x180013259  mov     r15, [rsp+78h+var_40]
0x18001325e  mov     eax, esi
0x180013260  mov     r14, [rsp+78h+var_38]
0x180013265  mov     r13, [rsp+78h+var_30]
0x18001326a  mov     r12, [rsp+78h+var_28]
0x18001326f  mov     rdi, [rsp+78h+var_20]
0x180013274  mov     rbx, [rsp+78h+var_18]
0x180013279  add     rsp, 68h
0x18001327d  pop     rsi
0x18001327e  pop     rbp
0x18001327f  retn
0x180013281  mov     [rsp+78h+var_58], 74h ; 't'
0x18001328a  mov     edx, 7Ch ; '|'
0x18001328f  mov     r14d, 70h ; 'p'
0x180013295  mov     r11d, 88h
0x18001329b  mov     r10d, 80h
0x1800132a1  mov     r9d, 84h
0x1800132a7  mov     r13d, 90h
0x1800132ad  mov     r8d, 8Ch
0x1800132b3  jmp     loc_180012FEB
0x1800132b8  mov     r14d, 0ACh
0x1800132be  jmp     loc_18001302B
0x1800132c3  xor     r15d, r15d
0x1800132c6  xor     eax, eax
0x1800132c8  cmp     ecx, 2
0x1800132cb  cmovz   r15d, eax
0x1800132cf  jmp     loc_180012F9B
0x1800132d4  cmp     dword ptr [r14+4], 0
0x1800132d9  jz      loc_18001301B
0x1800132df  mov     dl, 69h ; 'i'; unsigned __int8
0x1800132e1  mov     rcx, rbx; this
0x1800132e4  call    ?WriteByte@XLWrite@@QEAAJE@Z; XLWrite::WriteByte(uchar)
0x1800132e9  mov     rax, [rsp+78h+var_58]
0x1800132ee  mov     dword ptr [rax], 0
0x1800132f4  jmp     loc_18001301B
0x1800132f9  movsxd  rcx, dword ptr [rdi+1008h]
0x180013300  mov     r8, rbp; Size
0x180013303  add     rcx, rax; void *
0x180013306  mov     rdx, r14; Src
0x180013309  call    memcpy_0
0x18001330e  add     [rdi+1008h], ebp
0x180013314  jmp     loc_180013225
0x180013319  mov     eax, dword ptr [rsp+78h+arg_28]
0x180013320  mov     [rsp+78h+arg_0], eax
0x180013327  sub     [rsp+78h+arg_0], esi
0x18001332e  jz      loc_1800133C2
0x180013334  sub     [rsp+78h+arg_0], 2
0x18001333c  jnz     loc_18001357D
0x180013342  cmp     ecx, 2
0x180013345  mov     rcx, [rsp+78h+pco]; pco
0x18001334d  jnz     short loc_180013366
0x18001334f  mov     r9d, [r8]
0x180013352  test    r9d, r9d
0x180013355  jz      short loc_180013366
0x180013357  mov     edx, [rcx]
0x180013359  test    edx, edx
0x18001335b  jz      short loc_180013366
0x18001335d  cmp     r9d, edx
0x180013360  jz      loc_180013592
0x180013366  cmp     al, sil
0x180013369  jnz     loc_1800134F1
0x18001336f  mov     rcx, rbx
0x180013372  call    ?SetClipMode@XLOutput@@QEAAJW4ClipMode@@@Z; XLOutput::SetClipMode(ClipMode)
0x180013377  mov     dl, 85h; unsigned __int8
0x180013379  mov     rcx, rbx; this
0x18001337c  call    ?WriteByte@XLWrite@@QEAAJE@Z; XLWrite::WriteByte(uchar)
0x180013381  mov     r13, [rsp+78h+pco]
0x180013389  mov     rcx, rbx; this
0x18001338c  lea     rdx, [r13+4]; struct _RECTL *
0x180013390  call    ?RectanglePath@XLOutput@@QEAAJPEBU_RECTL@@@Z; XLOutput::RectanglePath(_RECTL const *)
0x180013395  mov     rcx, rbx
0x180013398  call    ?SetClipRegion@XLOutput@@QEAAJW4ClipRegion@@@Z; XLOutput::SetClipRegion(ClipRegion)
0x18001339d  mov     dl, 62h ; 'b'; unsigned __int8
0x18001339f  mov     rcx, rbx; this
0x1800133a2  call    ?WriteByte@XLWrite@@QEAAJE@Z; XLWrite::WriteByte(uchar)
0x1800133a7  mov     rdx, r13; struct _CLIPOBJ *
0x1800133aa  mov     rcx, r14; this
0x1800133ad  call    ?SetClip@XLClip@@QEAAJPEBU_CLIPOBJ@@@Z; XLClip::SetClip(_CLIPOBJ const *)
0x1800133b2  mov     rax, [rdi+1050h]
0x1800133b9  mov     [rdi+8], rax
0x1800133bd  jmp     loc_18001301B
0x1800133c2  cmp     ecx, esi
0x1800133c4  mov     rcx, [rsp+78h+pco]
0x1800133cc  jnz     short loc_180013366
0x1800133ce  mov     eax, [rcx+4]
0x1800133d1  cmp     [rdx], eax
  ... truncated ...
```
