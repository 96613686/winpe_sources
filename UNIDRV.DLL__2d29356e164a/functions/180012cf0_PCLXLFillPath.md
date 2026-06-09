# PCLXLFillPath

- ea: `0x180012cf0`
- end: `0x180013483`
- name: `PCLXLFillPath`
- size: `1939`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x180011dd0`
- `0x180011fc0`
- `0x180012cf0`
- `0x18001348c`
- `0x180013944`
- `0x180013e00`
- `0x1800152e0`
- `0x18001c884`
- `0x18001c8e0`
- `0x1800373c0`
- `0x18003bf7c`
- `0x18003c708`
- `0x18003d590`
- `0x180044930`
- `0x180044ec4`
- `0x1800452d0`
- `0x18006cd2c`
- `0x180074580`

## import_xrefs

- `GDI32!CLIPOBJ_ppoGetPath` at `0x1800132f0`
- `GDI32!CLIPOBJ_ppoGetPath` at `0x1800132f0`
- `GDI32!EngDeletePath` at `0x18001333d`
- `GDI32!EngDeletePath` at `0x18001333d`

## pseudocode

```c
__int64 PCLXLFillPath(__int64 a1, PATHOBJ *a2, const struct _CLIPOBJ *a3, struct _BRUSHOBJ *a4, int a5, ...)
{
  unsigned int v5; // ebp
  unsigned int v6; // esi
  __int64 v7; // rdi
  unsigned int v8; // r12d
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
  const void *v30; // r14
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
  v5 = *((_BYTE *)qword_18007E778 + (v43 & 0xF)) & 0xF
     | *((_BYTE *)qword_18007E778 + (((unsigned int)v43 >> 8) & 0xF)) & 0xF0;
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
        XLWrite::WriteByte((XLWrite *)v9, 0x69u);
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
      v37 = (CLIPOBJ *)a3;
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
        v37 = (CLIPOBJ *)a3;
        goto LABEL_71;
      }
      v36 = v19 == 2;
      v37 = (CLIPOBJ *)a3;
      if ( v36 && *(_DWORD *)v17 && a3->iUniq && *(_DWORD *)v17 == a3->iUniq )
      {
        if ( XLClipRgn::Compare((XLClipRgn *)v16, a3) )
          goto LABEL_9;
        v37 = (CLIPOBJ *)a3;
        LOBYTE(iDComplexity) = a3->iDComplexity;
      }
    }
LABEL_71:
    if ( (_BYTE)iDComplexity == 1 )
    {
      XLOutput::SetClipMode(v9);
      XLWrite::WriteByte((XLWrite *)v9, 0x85u);
      XLOutput::RectanglePath((XLOutput *)v9, &a3->rclBounds);
      XLOutput::SetClipRegion(v9);
      XLWrite::WriteByte((XLWrite *)v9, 0x62u);
      XLClip::SetClip((XLClip *)v11, a3);
    }
    else
    {
      if ( (_BYTE)iDComplexity == 3 )
      {
        Path = CLIPOBJ_ppoGetPath(v37);
        if ( !Path )
        {
          XLWrite::WriteByte((XLWrite *)v9, 0x69u);
          *(_DWORD *)(v11 + 4) = 0;
          *(_QWORD *)(v7 + 8) = *(_QWORD *)(v7 + 4176);
          goto LABEL_55;
        }
        XLOutput::SetClipMode(v9);
        XLOutput::Path((XLOutput *)v9, Path, (struct _DEVOBJ *)v7);
        XLOutput::SetClipRegion(v9);
        XLWrite::WriteByte((XLWrite *)v9, 0x62u);
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
          XLWrite::WriteByte((XLWrite *)v9, 0x7Bu);
          *(_DWORD *)v20 = v5;
        }
        v21 = v9 + 32;
        if ( !v9 )
          v21 = 0;
        if ( v8 != *(_DWORD *)(v21 + 228) )
        {
          if ( (unsigned int)XLOutput::SetTxMode(v9, v8) )
            goto LABEL_55;
          XLWrite::WriteByte((XLWrite *)v9, 0x78u);
          *(_DWORD *)(v21 + 228) = v8;
        }
        v22 = 0;
        if ( v9 )
          v22 = v9 + 32;
        if ( v8 != *(_DWORD *)(v22 + 224) )
        {
          if ( (unsigned int)XLOutput::SetTxMode(v9, v8) )
            goto LABEL_55;
          XLWrite::WriteByte((XLWrite *)v9, 0x7Cu);
          *(_DWORD *)(v22 + 224) = v8;
        }
        v23 = *(unsigned int *)(v9 + 28);
        if ( (int)v23 + 1 >= (unsigned int)v23
          && (*(unsigned int *)(v9 + 24) >= (unsigned __int64)(v23 + 8)
           || !(unsigned int)XLWrite::IncreaseBuffer((XLWrite *)v9, 8u))
          && *(_QWORD *)(v9 + 8) )
        {
          *(_BYTE *)(*(_QWORD *)(v9 + 16))++ = -64;
          ++*(_DWORD *)(v9 + 28);
        }
        v24 = *(unsigned int *)(v9 + 28);
        if ( (int)v24 + 1 >= (unsigned int)v24
          && (*(unsigned int *)(v9 + 24) >= (unsigned __int64)(v24 + 8)
           || !(unsigned int)XLWrite::IncreaseBuffer((XLWrite *)v9, 8u))
          && *(_QWORD *)(v9 + 8) )
        {
          *(_BYTE *)(*(_QWORD *)(v9 + 16))++ = v10;
          ++*(_DWORD *)(v9 + 28);
        }
        v25 = *(unsigned int *)(v9 + 28);
        if ( (int)v25 + 1 >= (unsigned int)v25
          && (*(unsigned int *)(v9 + 24) >= (unsigned __int64)(v25 + 8)
           || !(unsigned int)XLWrite::IncreaseBuffer((XLWrite *)v9, 8u))
          && *(_QWORD *)(v9 + 8) )
        {
          *(_BYTE *)(*(_QWORD *)(v9 + 16))++ = -8;
          ++*(_DWORD *)(v9 + 28);
        }
        v26 = *(unsigned int *)(v9 + 28);
        if ( (int)v26 + 1 >= (unsigned int)v26
          && (*(unsigned int *)(v9 + 24) >= (unsigned __int64)(v26 + 8)
           || !(unsigned int)XLWrite::IncreaseBuffer((XLWrite *)v9, 8u))
          && *(_QWORD *)(v9 + 8) )
        {
          *(_BYTE *)(*(_QWORD *)(v9 + 16))++ = 70;
          ++*(_DWORD *)(v9 + 28);
        }
        v27 = *(unsigned int *)(v9 + 28);
        if ( (int)v27 + 1 >= (unsigned int)v27
          && (*(unsigned int *)(v9 + 24) >= (unsigned __int64)(v27 + 8)
           || !(unsigned int)XLWrite::IncreaseBuffer((XLWrite *)v9, 8u))
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
             || !(unsigned int)XLWrite::IncreaseBuffer((XLWrite *)v9, 8u))
            && *(_QWORD *)(v9 + 8) )
          {
            *(_BYTE *)(*(_QWORD *)(v9 + 16))++ = -122;
            ++*(_DWORD *)(v9 + 28);
          }
          v30 = *(const void **)(v9 + 8);
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
                  WriteAbortBuf(v7, *(_QWORD *)(v7 + 4112), *(unsigned int *)(v7 + 4104), 0);
                  *(_DWORD *)(v7 + 4104) = 0;
                  *(_QWORD *)(v9 + 16) = *(_QWORD *)(v9 + 8);
                  *(_DWORD *)(v9 + 28) = 0;
                  return v6;
                }
                if ( (int)v32 >= 4096 )
                {
                  if ( !(unsigned int)BUniWritePrinter(v7, v30, (unsigned int)v32, (__int64 *)va) )
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
      XLWrite::WriteByte((XLWrite *)v9, 0x69u);
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
0x180012cf0  mov     r11, rsp
0x180012cf3  mov     [r11+20h], r9
0x180012cf7  mov     [r11+18h], r8
0x180012cfb  mov     [r11+10h], rdx
0x180012cff  push    rbp
0x180012d00  push    rsi
0x180012d01  sub     rsp, 68h
0x180012d05  mov     r10d, dword ptr [rsp+78h+arg_28]
0x180012d0d  lea     rdx, qword_18007E778
0x180012d14  mov     eax, r10d
0x180012d17  and     r10d, 0Fh
0x180012d1b  shr     rax, 8
0x180012d1f  and     eax, 0Fh
0x180012d22  movzx   ebp, byte ptr [rax+rdx]
0x180012d26  movzx   eax, byte ptr [r10+rdx]
0x180012d2b  and     ebp, 0F0h
0x180012d31  and     eax, 0Fh
0x180012d34  or      ebp, eax
0x180012d36  cmp     ebp, 0AAh
0x180012d3c  jz      loc_180013353
0x180012d42  mov     [r11-18h], rbx
0x180012d46  mov     eax, ebp
0x180012d48  mov     [r11-20h], rdi
0x180012d4c  mov     esi, 1
0x180012d51  mov     rdi, [rcx+10h]
0x180012d55  mov     ecx, ebp
0x180012d57  mov     [r11-28h], r12
0x180012d5b  and     ecx, 0Fh
0x180012d5e  xor     r12d, r12d
0x180012d61  shr     eax, 4
0x180012d64  cmp     eax, ecx
0x180012d66  mov     [r11-40h], r15
0x180012d6a  mov     rbx, [rdi+8]
0x180012d6e  mov     ecx, dword ptr [rsp+78h+arg_30]
0x180012d75  setz    r12b
0x180012d79  mov     rbx, [rbx+0A0h]
0x180012d80  cmp     ecx, esi
0x180012d82  jnz     loc_1800130B2
0x180012d88  mov     r15d, esi
0x180012d8b  mov     [rsp+78h+var_30], r13
0x180012d90  mov     [rsp+78h+var_38], r14
0x180012d95  test    rbx, rbx
0x180012d98  jz      loc_180013070
0x180012d9e  lea     rcx, [rbx+94h]
0x180012da5  mov     [rsp+78h+var_58], rcx
0x180012daa  lea     r14, [rbx+90h]
0x180012db1  lea     r11, [rbx+0A8h]
0x180012db8  lea     r10, [rbx+0A0h]
0x180012dbf  lea     r9, [rbx+0A4h]
0x180012dc6  lea     rdx, [rbx+9Ch]
0x180012dcd  lea     r13, [rbx+0B0h]
0x180012dd4  lea     r8, [rbx+0ACh]; struct _POINTL *
0x180012ddb  mov     rax, [rsp+78h+pco]
0x180012de3  test    rax, rax
0x180012de6  jz      loc_1800130C3
0x180012dec  movzx   eax, byte ptr [rax+14h]
0x180012df0  mov     ecx, [r14+4]
0x180012df4  mov     dword ptr [rsp+78h+arg_28], eax
0x180012dfb  test    eax, eax
0x180012dfd  jnz     loc_180013108
0x180012e03  test    ecx, ecx
0x180012e05  jnz     loc_180013367
0x180012e0b  lea     r14, [rbx+0CCh]
0x180012e12  test    rbx, rbx
0x180012e15  jz      loc_1800130A7
0x180012e1b  cmp     ebp, [r14]
0x180012e1e  jnz     loc_180013026
0x180012e24  xor     eax, eax
0x180012e26  lea     r14, [rbx+20h]
0x180012e2a  test    rbx, rbx
0x180012e2d  mov     rbp, r14
0x180012e30  cmovz   rbp, rax
0x180012e34  cmp     r12d, [rbp+0E4h]
0x180012e3b  jnz     loc_180013421
0x180012e41  xor     ebp, ebp
0x180012e43  test    rbx, rbx
0x180012e46  cmovnz  rbp, r14
0x180012e4a  cmp     r12d, [rbp+0E0h]
0x180012e51  jnz     loc_18001344A
0x180012e57  mov     edx, [rbx+1Ch]
0x180012e5a  lea     eax, [rdx+1]
0x180012e5d  cmp     eax, edx
0x180012e5f  jb      short loc_180012E86
0x180012e61  mov     ecx, [rbx+18h]
0x180012e64  lea     rax, [rdx+8]
0x180012e68  cmp     rcx, rax
0x180012e6b  jb      loc_1800131FD
0x180012e71  cmp     qword ptr [rbx+8], 0
0x180012e76  jz      short loc_180012E86
0x180012e78  mov     rax, [rbx+10h]
0x180012e7c  mov     byte ptr [rax], 0C0h
0x180012e7f  inc     qword ptr [rbx+10h]
0x180012e83  inc     dword ptr [rbx+1Ch]
0x180012e86  mov     edx, [rbx+1Ch]
0x180012e89  lea     eax, [rdx+1]
0x180012e8c  cmp     eax, edx
0x180012e8e  jb      short loc_180012EB5
0x180012e90  mov     ecx, [rbx+18h]
0x180012e93  lea     rax, [rdx+8]
0x180012e97  cmp     rcx, rax
0x180012e9a  jb      loc_180013217
0x180012ea0  cmp     qword ptr [rbx+8], 0
0x180012ea5  jz      short loc_180012EB5
0x180012ea7  mov     rax, [rbx+10h]
0x180012eab  mov     [rax], r15b
0x180012eae  inc     qword ptr [rbx+10h]
0x180012eb2  inc     dword ptr [rbx+1Ch]
0x180012eb5  mov     edx, [rbx+1Ch]
0x180012eb8  lea     eax, [rdx+1]
0x180012ebb  cmp     eax, edx
0x180012ebd  jb      short loc_180012EE4
0x180012ebf  mov     ecx, [rbx+18h]
0x180012ec2  lea     rax, [rdx+8]
0x180012ec6  cmp     rcx, rax
0x180012ec9  jb      loc_180013231
0x180012ecf  cmp     qword ptr [rbx+8], 0
0x180012ed4  jz      short loc_180012EE4
0x180012ed6  mov     rax, [rbx+10h]
0x180012eda  mov     byte ptr [rax], 0F8h
0x180012edd  inc     qword ptr [rbx+10h]
0x180012ee1  inc     dword ptr [rbx+1Ch]
0x180012ee4  mov     edx, [rbx+1Ch]
0x180012ee7  lea     eax, [rdx+1]
0x180012eea  cmp     eax, edx
0x180012eec  jb      short loc_180012F13
0x180012eee  mov     ecx, [rbx+18h]
0x180012ef1  lea     rax, [rdx+8]
0x180012ef5  cmp     rcx, rax
0x180012ef8  jb      loc_18001324B
0x180012efe  cmp     qword ptr [rbx+8], 0
0x180012f03  jz      short loc_180012F13
0x180012f05  mov     rax, [rbx+10h]
0x180012f09  mov     byte ptr [rax], 46h ; 'F'
0x180012f0c  inc     qword ptr [rbx+10h]
0x180012f10  inc     dword ptr [rbx+1Ch]
0x180012f13  mov     edx, [rbx+1Ch]
0x180012f16  lea     eax, [rdx+1]
0x180012f19  cmp     eax, edx
0x180012f1b  jb      short loc_180012F42
0x180012f1d  mov     ecx, [rbx+18h]
0x180012f20  lea     rax, [rdx+8]
0x180012f24  cmp     rcx, rax
0x180012f27  jb      loc_180013265
0x180012f2d  cmp     qword ptr [rbx+8], 0
0x180012f32  jz      short loc_180012F42
0x180012f34  mov     rax, [rbx+10h]
0x180012f38  mov     byte ptr [rax], 6Eh ; 'n'
0x180012f3b  inc     qword ptr [rbx+10h]
0x180012f3f  inc     dword ptr [rbx+1Ch]
0x180012f42  mov     r9, rdi; struct _DEVOBJ *
0x180012f45  xor     edx, edx; struct _BRUSHOBJ *
0x180012f47  mov     rcx, rbx; this
0x180012f4a  call    ?SetPenColor@XLOutput@@QEAAJPEAU_BRUSHOBJ@@PEAU_POINTL@@PEAU_DEVOBJ@@@Z; XLOutput::SetPenColor(_BRUSHOBJ *,_POINTL *,_DEVOBJ *)
0x180012f4f  test    eax, eax
0x180012f51  jnz     loc_18001303A
0x180012f57  mov     rdx, [rsp+78h+arg_18]; struct _BRUSHOBJ *
0x180012f5f  mov     r9, rdi; struct _DEVOBJ *
0x180012f62  mov     rcx, rbx; this
0x180012f65  call    ?SetBrush@XLOutput@@QEAAJPEAU_BRUSHOBJ@@PEBU_POINTL@@PEAU_DEVOBJ@@@Z; XLOutput::SetBrush(_BRUSHOBJ *,_POINTL const *,_DEVOBJ *)
0x180012f6a  test    eax, eax
0x180012f6c  jnz     loc_18001303A
0x180012f72  mov     rdx, [rsp+78h+ppo]; ppo
0x180012f7a  mov     r8, rdi; struct _DEVOBJ *
0x180012f7d  mov     rcx, rbx; this
0x180012f80  call    ?Path@XLOutput@@QEAAJPEAU_PATHOBJ@@PEAU_DEVOBJ@@@Z; XLOutput::Path(_PATHOBJ *,_DEVOBJ *)
0x180012f85  test    eax, eax
0x180012f87  jnz     loc_18001303A
0x180012f8d  mov     r8d, [rbx+1Ch]
0x180012f91  lea     eax, [r8+1]
0x180012f95  cmp     eax, r8d
0x180012f98  jb      short loc_180012FBF
0x180012f9a  mov     ecx, [rbx+18h]
0x180012f9d  lea     rax, [r8+8]
0x180012fa1  cmp     rcx, rax
0x180012fa4  jb      loc_18001327F
0x180012faa  cmp     qword ptr [rbx+8], 0
0x180012faf  jz      short loc_180012FBF
0x180012fb1  mov     rax, [rbx+10h]
0x180012fb5  mov     byte ptr [rax], 86h
0x180012fb8  inc     qword ptr [rbx+10h]
0x180012fbc  inc     dword ptr [rbx+1Ch]
0x180012fbf  mov     r14, [rbx+8]
0x180012fc3  test    r14, r14
0x180012fc6  jz      short loc_18001303A
0x180012fc8  test    rdi, rdi
0x180012fcb  jz      short loc_18001303A
0x180012fcd  mov     dword ptr [rsp+78h+arg_28], 0
0x180012fd8  test    [rdi+70h], sil
0x180012fdc  jnz     short loc_180013015
0x180012fde  mov     eax, [rdi+1008h]
0x180012fe4  movsxd  rbp, dword ptr [rbx+1Ch]
0x180012fe8  test    eax, eax
0x180012fea  jz      short loc_180012FF9
0x180012fec  add     eax, ebp
0x180012fee  cmp     eax, 1000h
0x180012ff3  jg      loc_180013299
0x180012ff9  cmp     ebp, 1000h
0x180012fff  jge     loc_1800131D1
0x180013005  mov     rax, [rdi+1010h]
0x18001300c  test    rax, rax
0x18001300f  jnz     loc_1800130E8
0x180013015  mov     rax, [rbx+8]
0x180013019  mov     [rbx+10h], rax
0x18001301d  mov     dword ptr [rbx+1Ch], 0
0x180013024  jmp     short loc_180013049
0x180013026  movzx   edx, bpl; unsigned __int8
0x18001302a  mov     rcx, rbx; this
0x18001302d  call    ?Send_ubyte@XLOutput@@QEAAJE@Z; XLOutput::Send_ubyte(uchar)
0x180013032  test    eax, eax
0x180013034  jz      loc_1800133FA
0x18001303a  mov     rax, [rbx+8]
0x18001303e  test    rax, rax
0x180013041  jnz     loc_180013473
0x180013047  xor     esi, esi
0x180013049  mov     r15, [rsp+78h+var_40]
0x18001304e  mov     eax, esi
0x180013050  mov     r14, [rsp+78h+var_38]
0x180013055  mov     r13, [rsp+78h+var_30]
0x18001305a  mov     r12, [rsp+78h+var_28]
0x18001305f  mov     rdi, [rsp+78h+var_20]
0x180013064  mov     rbx, [rsp+78h+var_18]
0x180013069  add     rsp, 68h
0x18001306d  pop     rsi
0x18001306e  pop     rbp
0x18001306f  retn
0x180013070  mov     [rsp+78h+var_58], 74h ; 't'
0x180013079  mov     edx, 7Ch ; '|'
0x18001307e  mov     r14d, 70h ; 'p'
0x180013084  mov     r11d, 88h
0x18001308a  mov     r10d, 80h
0x180013090  mov     r9d, 84h
0x180013096  mov     r13d, 90h
0x18001309c  mov     r8d, 8Ch
0x1800130a2  jmp     loc_180012DDB
0x1800130a7  mov     r14d, 0ACh
0x1800130ad  jmp     loc_180012E1B
0x1800130b2  xor     r15d, r15d
0x1800130b5  xor     eax, eax
0x1800130b7  cmp     ecx, 2
0x1800130ba  cmovz   r15d, eax
0x1800130be  jmp     loc_180012D8B
0x1800130c3  cmp     dword ptr [r14+4], 0
0x1800130c8  jz      loc_180012E0B
0x1800130ce  mov     dl, 69h ; 'i'; unsigned __int8
0x1800130d0  mov     rcx, rbx; this
0x1800130d3  call    ?WriteByte@XLWrite@@QEAAJE@Z; XLWrite::WriteByte(uchar)
0x1800130d8  mov     rax, [rsp+78h+var_58]
0x1800130dd  mov     dword ptr [rax], 0
0x1800130e3  jmp     loc_180012E0B
0x1800130e8  movsxd  rcx, dword ptr [rdi+1008h]
0x1800130ef  mov     r8, rbp; Size
0x1800130f2  add     rcx, rax; void *
0x1800130f5  mov     rdx, r14; Src
0x1800130f8  call    memcpy_0
0x1800130fd  add     [rdi+1008h], ebp
0x180013103  jmp     loc_180013015
0x180013108  mov     eax, dword ptr [rsp+78h+arg_28]
0x18001310f  mov     [rsp+78h+arg_0], eax
0x180013116  sub     [rsp+78h+arg_0], esi
0x18001311d  jz      loc_1800131B1
0x180013123  sub     [rsp+78h+arg_0], 2
0x18001312b  jnz     loc_18001335F
0x180013131  cmp     ecx, 2
0x180013134  mov     rcx, [rsp+78h+pco]; pco
0x18001313c  jnz     short loc_180013155
0x18001313e  mov     r9d, [r8]
0x180013141  test    r9d, r9d
0x180013144  jz      short loc_180013155
0x180013146  mov     edx, [rcx]
0x180013148  test    edx, edx
0x18001314a  jz      short loc_180013155
0x18001314c  cmp     r9d, edx
0x18001314f  jz      loc_180013374
0x180013155  cmp     al, sil
0x180013158  jnz     loc_1800132E0
0x18001315e  mov     rcx, rbx
0x180013161  call    ?SetClipMode@XLOutput@@QEAAJW4ClipMode@@@Z; XLOutput::SetClipMode(ClipMode)
0x180013166  mov     dl, 85h; unsigned __int8
0x180013168  mov     rcx, rbx; this
0x18001316b  call    ?WriteByte@XLWrite@@QEAAJE@Z; XLWrite::WriteByte(uchar)
0x180013170  mov     r13, [rsp+78h+pco]
0x180013178  mov     rcx, rbx; this
0x18001317b  lea     rdx, [r13+4]; struct _RECTL *
0x18001317f  call    ?RectanglePath@XLOutput@@QEAAJPEBU_RECTL@@@Z; XLOutput::RectanglePath(_RECTL const *)
0x180013184  mov     rcx, rbx
0x180013187  call    ?SetClipRegion@XLOutput@@QEAAJW4ClipRegion@@@Z; XLOutput::SetClipRegion(ClipRegion)
0x18001318c  mov     dl, 62h ; 'b'; unsigned __int8
0x18001318e  mov     rcx, rbx; this
0x180013191  call    ?WriteByte@XLWrite@@QEAAJE@Z; XLWrite::WriteByte(uchar)
0x180013196  mov     rdx, r13; struct _CLIPOBJ *
0x180013199  mov     rcx, r14; this
0x18001319c  call    ?SetClip@XLClip@@QEAAJPEBU_CLIPOBJ@@@Z; XLClip::SetClip(_CLIPOBJ const *)
0x1800131a1  mov     rax, [rdi+1050h]
0x1800131a8  mov     [rdi+8], rax
0x1800131ac  jmp     loc_180012E0B
0x1800131b1  cmp     ecx, esi
0x1800131b3  mov     rcx, [rsp+78h+pco]
0x1800131bb  jnz     short loc_180013155
0x1800131bd  mov     eax, [rcx+4]
0x1800131c0  cmp     [rdx], eax
  ... truncated ...
```
