# HCreateBitmapSurface

- ea: `0x18004b23c`
- end: `0x18004b6dc`
- name: `HCreateBitmapSurface`
- size: `1184`
- prototype: `HBITMAP __fastcall(__int64, ULONG)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18004a8f0`

## callees

- `0x18001c714`
- `0x180049d00`
- `0x18004b23c`
- `0x18004b6e4`
- `0x180077010`

## import_xrefs

- `GDI32!EngCreateBitmap` at `0x18004b4ea`
- `GDI32!EngCreateBitmap` at `0x18004b6a3`
- `GDI32!EngCreateBitmap` at `0x18004b4ea`
- `GDI32!EngCreateBitmap` at `0x18004b6a3`

## pseudocode

```c
HBITMAP __fastcall HCreateBitmapSurface(__int64 a1, ULONG a2)
{
  __int64 v2; // r10
  int v4; // r12d
  unsigned int v5; // edi
  LONG cx; // r11d
  LONG v7; // r15d
  void (__fastcall *v8)(__int64, SIZEL *); // r10
  _QWORD *v9; // rax
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // esi
  __int64 v15; // rcx
  LONG v16; // r13d
  unsigned int v17; // eax
  unsigned int v18; // r14d
  unsigned int v19; // r8d
  ULONG v20; // edi
  int v21; // eax
  HBITMAP Bitmap; // rcx
  __int64 v24; // rax
  int v25; // eax
  signed int v26; // edi
  int v27; // ecx
  int v28; // eax
  int v29; // eax
  int v30; // eax
  SIZEL sizl; // [rsp+30h] [rbp-40h]
  unsigned int v33; // [rsp+3Ch] [rbp-34h] BYREF
  int v34; // [rsp+40h] [rbp-30h]
  HBITMAP v35; // [rsp+48h] [rbp-28h] BYREF
  SIZEL v36; // [rsp+50h] [rbp-20h] BYREF
  int v37; // [rsp+58h] [rbp-18h]

  v2 = *(_QWORD *)(a1 + 1896);
  v4 = *(__int16 *)(a1 + 2600);
  v5 = 6291456;
  cx = *(_DWORD *)(a1 + 4076);
  v7 = *(_DWORD *)(a1 + 4080);
  v35 = 0;
  sizl = (SIZEL)__PAIR64__(v7, cx);
  v34 = v4;
  if ( !v2 || !*(_QWORD *)(v2 + 592) )
    goto LABEL_20;
  v36 = 0;
  v37 = 6291456;
  if ( (unsigned int)BConfigureOemDevObj((_QWORD *)a1, 0x25u) )
  {
    v9 = *(_QWORD **)(a1 + 1888);
    v10 = v9[9];
    if ( v10 )
    {
      v11 = v9[10] - *(_QWORD *)&IID_IPrintOemUni.Data1;
      if ( !v11 )
        v11 = v9[11] - *(_QWORD *)IID_IPrintOemUni.Data4;
      if ( v11 )
      {
        v12 = v9[10] - *(_QWORD *)&IID_IPrintOemUni2.Data1;
        if ( !v12 )
          v12 = v9[11] - *(_QWORD *)IID_IPrintOemUni2.Data4;
        if ( v12 )
        {
          v13 = v9[10] - *(_QWORD *)&IID_IPrintOemUni3.Data1;
          if ( !v13 )
            v13 = v9[11] - *(_QWORD *)IID_IPrintOemUni3.Data4;
          if ( v13 )
            goto LABEL_18;
        }
      }
      (*(void (__fastcall **)(_QWORD, __int64, SIZEL *))(*(_QWORD *)v10 + 144LL))(v9[9], a1, &v36);
    }
    else
    {
      v8(a1, &v36);
    }
    cx = sizl.cx;
  }
LABEL_18:
  v5 = 100 * (6291456 - v36.cx) / (unsigned int)(v36.cy + 100);
  if ( v5 < 0x100000 )
    v5 = 0x100000;
LABEL_20:
  v14 = 1;
  v15 = *(_QWORD *)(a1 + 1896);
  v16 = (int)((cx * v4 + 31) & 0xFFFFFFE0) / 8;
  v17 = v16 * v7 / v5;
  v18 = v17 + 1;
  if ( !v15 || !*(_QWORD *)(v15 + 752) )
  {
    v20 = a2;
    goto LABEL_33;
  }
  v36 = 0;
  v33 = v17 + 1;
  v20 = a2;
  if ( !(unsigned int)BConfigureOemDevObj((_QWORD *)a1, 0x2Fu) )
    goto LABEL_33;
  v21 = HCreateBitmapSurfaceWithOemPlugin(a1, a2, v19, &v35, &v36, (int *)&v33);
  if ( v21 < 0 )
  {
    if ( (unsigned int)(v21 + 2147467263) > 1 )
      return 0;
LABEL_33:
    if ( v18 > 1
      || (*(_DWORD *)(a1 + 112) & 0x1000) != 0
      || (*(_DWORD *)(*(_QWORD *)(a1 + 2024) + 140LL) & 0x6000) != 0
      || (Bitmap = EngCreateBitmap(sizl, v16, v20, 0xBu, 0)) == 0 )
    {
      if ( (_WORD)v4 == 1 && *(_DWORD *)(*(_QWORD *)(a1 + 3864) + 24LL) == 1 )
      {
        v24 = *(_QWORD *)(a1 + 3928);
        if ( !v24 || (v25 = *(_DWORD *)(v24 + 56), v25 == 255) )
        {
          v27 = *(_DWORD *)(a1 + 3948);
          if ( *(_DWORD *)(a1 + 3944) <= v27 )
            v27 = *(_DWORD *)(a1 + 3944);
          if ( v27 < 2400 )
          {
            if ( v27 < 1800 )
            {
              if ( v27 < 1200 )
              {
                v28 = 8;
                if ( v27 >= 800 )
                  v28 = 40;
                v26 = v28;
              }
              else
              {
                v26 = 24;
              }
            }
            else
            {
              v26 = 56;
            }
          }
          else
          {
            v26 = 16;
          }
        }
        else
        {
          switch ( v25 )
          {
            case 5:
            case 11:
              v26 = 24;
              break;
            case 9:
              v26 = 40;
              break;
            case 13:
              v26 = 56;
              break;
            default:
              v26 = 8;
              if ( v25 == 15 )
                v26 = 16;
              break;
          }
        }
      }
      else
      {
        v26 = (*(_DWORD *)(*(_QWORD *)(a1 + 3864) + 24LL) + 7) & 0xFFFFFFF8;
      }
      if ( v18 <= 1 )
        v18 = 2;
      while ( 1 )
      {
        if ( *(char *)(a1 + 112) >= 0 )
        {
          v30 = *(_DWORD *)(a1 + 4080) / v18;
          if ( v30 < v26 )
            return 0;
          v7 = v26 + v30 - v30 % v26;
          sizl.cy = v7;
        }
        else
        {
          v29 = *(_DWORD *)(a1 + 4076) / v18;
          if ( v29 < v26 )
            return 0;
          sizl.cx = v29 - v29 % v26 + v26;
          v16 = (int)((v34 * sizl.cx + 31) & 0xFFFFFFE0) / 8;
        }
        Bitmap = EngCreateBitmap(sizl, v16, a2, 0xBu, 0);
        if ( Bitmap )
          break;
        if ( ((v16 * v7) & 0xFFFFFFFE) < 0x100000 )
          return 0;
        v18 *= 2;
      }
    }
    else
    {
      v14 = 0;
      *(_DWORD *)(a1 + 1988) = *(_DWORD *)(a1 + 4076);
      *(_DWORD *)(a1 + 1992) = *(_DWORD *)(a1 + 4080);
      *(_QWORD *)(a1 + 1980) = 0;
    }
    *(_DWORD *)(a1 + 1960) = v14;
    *(_DWORD *)(a1 + 1972) = sizl.cx;
    *(_DWORD *)(a1 + 1976) = v7;
    return Bitmap;
  }
  Bitmap = v35;
  if ( v35 && v21 != 1 )
  {
    if ( v33 <= 1 )
    {
      v14 = 0;
      *(_DWORD *)(a1 + 1988) = *(_DWORD *)(a1 + 4076);
      *(_DWORD *)(a1 + 1992) = *(_DWORD *)(a1 + 4080);
      *(_QWORD *)(a1 + 1980) = 0;
    }
    *(_DWORD *)(a1 + 1960) = v14;
    *(SIZEL *)(a1 + 1972) = v36;
    return Bitmap;
  }
  return 0;
}

```

## disassembly

```asm
0x18004b23c  mov     [rsp-38h+arg_10], rbx
0x18004b241  push    rbp
0x18004b242  push    rsi
0x18004b243  push    rdi
0x18004b244  push    r12
0x18004b246  push    r13
0x18004b248  push    r14
0x18004b24a  push    r15
0x18004b24c  mov     rbp, rsp
0x18004b24f  sub     rsp, 70h
0x18004b253  mov     rax, cs:__security_cookie
0x18004b25a  xor     rax, rsp
0x18004b25d  mov     [rbp+var_10], rax
0x18004b261  mov     r10, [rcx+768h]
0x18004b268  mov     rbx, rcx
0x18004b26b  movsx   r12d, word ptr [rcx+0A28h]
0x18004b273  mov     edi, 600000h
0x18004b278  mov     r11d, [rcx+0FECh]
0x18004b27f  mov     r14d, 100000h
0x18004b285  mov     r15d, [rcx+0FF0h]
0x18004b28c  mov     qword ptr [rbp+sizl.cx], 0
0x18004b294  mov     [rbp+iFormat], edx
0x18004b297  mov     [rbp+var_28], 0
0x18004b29f  mov     [rbp+sizl.cx], r11d
0x18004b2a3  mov     [rbp+sizl.cy], r15d
0x18004b2a7  mov     [rbp+var_30], r12d
0x18004b2ab  test    r10, r10
0x18004b2ae  jz      loc_18004B391
0x18004b2b4  mov     r10, [r10+250h]
0x18004b2bb  test    r10, r10
0x18004b2be  jz      loc_18004B391
0x18004b2c4  mov     edx, 25h ; '%'
0x18004b2c9  mov     [rbp+var_20], 0
0x18004b2d1  mov     [rbp+var_18], edi
0x18004b2d4  call    BConfigureOemDevObj
0x18004b2d9  test    eax, eax
0x18004b2db  jz      loc_18004B378
0x18004b2e1  mov     rax, [rbx+760h]
0x18004b2e8  mov     r9, [rax+48h]
0x18004b2ec  test    r9, r9
0x18004b2ef  jz      short loc_18004B365
0x18004b2f1  mov     rcx, [rax+50h]
0x18004b2f5  sub     rcx, qword ptr cs:IID_IPrintOemUni.Data1
0x18004b2fc  jnz     short loc_18004B309
0x18004b2fe  mov     rcx, [rax+58h]
0x18004b302  sub     rcx, qword ptr cs:IID_IPrintOemUni.Data4
0x18004b309  test    rcx, rcx
0x18004b30c  jnz     short loc_18004B329
0x18004b30e  mov     rax, [r9]
0x18004b311  lea     r8, [rbp+var_20]
0x18004b315  mov     rdx, rbx
0x18004b318  mov     rcx, r9
0x18004b31b  mov     rax, [rax+90h]
0x18004b322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b327  jmp     short loc_18004B374
0x18004b329  mov     rcx, [rax+50h]
0x18004b32d  sub     rcx, qword ptr cs:IID_IPrintOemUni2.Data1
0x18004b334  jnz     short loc_18004B341
0x18004b336  mov     rcx, [rax+58h]
0x18004b33a  sub     rcx, qword ptr cs:IID_IPrintOemUni2.Data4
0x18004b341  test    rcx, rcx
0x18004b344  jz      short loc_18004B30E
0x18004b346  mov     rcx, [rax+50h]
0x18004b34a  sub     rcx, qword ptr cs:IID_IPrintOemUni3.Data1
0x18004b351  jnz     short loc_18004B35E
0x18004b353  mov     rcx, [rax+58h]
0x18004b357  sub     rcx, qword ptr cs:IID_IPrintOemUni3.Data4
0x18004b35e  test    rcx, rcx
0x18004b361  jnz     short loc_18004B378
0x18004b363  jmp     short loc_18004B30E
0x18004b365  lea     rdx, [rbp+var_20]
0x18004b369  mov     rcx, rbx
0x18004b36c  mov     rax, r10
0x18004b36f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b374  mov     r11d, [rbp+sizl.cx]
0x18004b378  sub     edi, dword ptr [rbp+var_20]
0x18004b37b  xor     edx, edx
0x18004b37d  mov     ecx, dword ptr [rbp+var_20+4]
0x18004b380  imul    eax, edi, 64h ; 'd'
0x18004b383  add     ecx, 64h ; 'd'
0x18004b386  div     ecx
0x18004b388  cmp     eax, r14d
0x18004b38b  mov     edi, eax
0x18004b38d  cmovb   edi, r14d
0x18004b391  mov     ecx, 8
0x18004b396  mov     eax, r12d
0x18004b399  imul    eax, r11d
0x18004b39d  mov     esi, 1
0x18004b3a2  add     eax, 1Fh
0x18004b3a5  and     eax, 0FFFFFFE0h
0x18004b3a8  cdq
0x18004b3a9  idiv    ecx
0x18004b3ab  mov     rcx, [rbx+768h]
0x18004b3b2  xor     edx, edx
0x18004b3b4  mov     r13d, eax
0x18004b3b7  mov     eax, r15d
0x18004b3ba  imul    eax, r13d
0x18004b3be  div     edi
0x18004b3c0  lea     r14d, [rax+1]
0x18004b3c4  test    rcx, rcx
0x18004b3c7  jz      loc_18004B4A5
0x18004b3cd  cmp     qword ptr [rcx+2F0h], 0
0x18004b3d5  jz      loc_18004B4A5
0x18004b3db  lea     edx, [rsi+2Eh]
0x18004b3de  mov     [rbp+var_20], 0
0x18004b3e6  mov     rcx, rbx
0x18004b3e9  mov     [rbp+var_34], r14d
0x18004b3ed  call    BConfigureOemDevObj
0x18004b3f2  mov     edi, [rbp+iFormat]
0x18004b3f5  test    eax, eax
0x18004b3f7  jz      loc_18004B4A8
0x18004b3fd  lea     rax, [rbp+var_34]
0x18004b401  mov     edx, edi
0x18004b403  mov     [rsp+70h+var_48], rax
0x18004b408  lea     r9, [rbp+var_28]
0x18004b40c  lea     rax, [rbp+var_20]
0x18004b410  mov     rcx, rbx
0x18004b413  mov     [rsp+70h+pvBits], rax
0x18004b418  call    HCreateBitmapSurfaceWithOemPlugin
0x18004b41d  test    eax, eax
0x18004b41f  js      short loc_18004B475
0x18004b421  mov     rcx, [rbp+var_28]
0x18004b425  test    rcx, rcx
0x18004b428  jz      short loc_18004B47E
0x18004b42a  cmp     eax, esi
0x18004b42c  jz      short loc_18004B47E
0x18004b42e  cmp     [rbp+var_34], esi
0x18004b431  ja      short loc_18004B458
0x18004b433  mov     eax, [rbx+0FECh]
0x18004b439  xor     esi, esi
0x18004b43b  mov     [rbx+7C4h], eax
0x18004b441  mov     eax, [rbx+0FF0h]
0x18004b447  mov     [rbx+7C8h], eax
0x18004b44d  mov     qword ptr [rbx+7BCh], 0
0x18004b458  mov     [rbx+7A8h], esi
0x18004b45e  mov     eax, dword ptr [rbp+var_20]
0x18004b461  mov     [rbx+7B4h], eax
0x18004b467  mov     eax, dword ptr [rbp+var_20+4]
0x18004b46a  mov     [rbx+7B8h], eax
0x18004b470  mov     rax, rcx
0x18004b473  jmp     short loc_18004B480
0x18004b475  add     eax, 7FFFBFFFh
0x18004b47a  cmp     eax, esi
0x18004b47c  jbe     short loc_18004B4A8
0x18004b47e  xor     eax, eax
0x18004b480  mov     rcx, [rbp+var_10]
0x18004b484  xor     rcx, rsp; StackCookie
0x18004b487  call    __security_check_cookie
0x18004b48c  mov     rbx, [rsp+70h+arg_10]
0x18004b494  add     rsp, 70h
0x18004b498  pop     r15
0x18004b49a  pop     r14
0x18004b49c  pop     r13
0x18004b49e  pop     r12
0x18004b4a0  pop     rdi
0x18004b4a1  pop     rsi
0x18004b4a2  pop     rbp
0x18004b4a3  retn
0x18004b4a5  mov     edi, [rbp+iFormat]
0x18004b4a8  cmp     r14d, esi
0x18004b4ab  ja      loc_18004B53E
0x18004b4b1  test    dword ptr [rbx+70h], 1000h
0x18004b4b8  jnz     loc_18004B53E
0x18004b4be  mov     rax, [rbx+7E8h]
0x18004b4c5  test    dword ptr [rax+8Ch], 6000h
0x18004b4cf  jnz     short loc_18004B53E
0x18004b4d1  mov     rcx, qword ptr [rbp+sizl.cx]; sizl
0x18004b4d5  mov     r9d, 0Bh; fl
0x18004b4db  mov     r8d, edi; iFormat
0x18004b4de  mov     [rsp+70h+pvBits], 0; pvBits
0x18004b4e7  mov     edx, r13d; lWidth
0x18004b4ea  call    cs:__imp_EngCreateBitmap
0x18004b4f1  nop     dword ptr [rax+rax+00h]
0x18004b4f6  mov     rcx, rax
0x18004b4f9  test    rax, rax
0x18004b4fc  jz      short loc_18004B53E
0x18004b4fe  mov     eax, [rbx+0FECh]
0x18004b504  xor     esi, esi
0x18004b506  mov     [rbx+7C4h], eax
0x18004b50c  mov     eax, [rbx+0FF0h]
0x18004b512  mov     [rbx+7C8h], eax
0x18004b518  mov     qword ptr [rbx+7BCh], 0
0x18004b523  mov     eax, [rbp+sizl.cx]
0x18004b526  mov     [rbx+7A8h], esi
0x18004b52c  mov     [rbx+7B4h], eax
0x18004b532  mov     [rbx+7B8h], r15d
0x18004b539  jmp     loc_18004B470
0x18004b53e  cmp     r12w, si
0x18004b542  jnz     loc_18004B607
0x18004b548  mov     rax, [rbx+0F18h]
0x18004b54f  cmp     [rax+18h], esi
0x18004b552  jnz     loc_18004B607
0x18004b558  mov     rax, [rbx+0F58h]
0x18004b55f  test    rax, rax
0x18004b562  jz      short loc_18004B5AF
0x18004b564  mov     eax, [rax+38h]
0x18004b567  cmp     eax, 0FFh
0x18004b56c  jz      short loc_18004B5AF
0x18004b56e  cmp     eax, 5
0x18004b571  jz      short loc_18004B5A8
0x18004b573  cmp     eax, 0Bh
0x18004b576  jz      short loc_18004B5A8
0x18004b578  cmp     eax, 9
0x18004b57b  jnz     short loc_18004B585
0x18004b57d  lea     edi, [rax+1Fh]
0x18004b580  jmp     loc_18004B617
0x18004b585  mov     r8d, 8
0x18004b58b  cmp     eax, 0Dh
0x18004b58e  jnz     short loc_18004B598
0x18004b590  lea     edi, [rax+2Bh]
0x18004b593  jmp     loc_18004B61D
0x18004b598  cmp     eax, 0Fh
0x18004b59b  mov     edi, r8d
0x18004b59e  mov     ecx, 10h
0x18004b5a3  cmovz   edi, ecx
0x18004b5a6  jmp     short loc_18004B61D
0x18004b5a8  mov     edi, 18h
0x18004b5ad  jmp     short loc_18004B617
0x18004b5af  mov     eax, [rbx+0F68h]
0x18004b5b5  mov     ecx, [rbx+0F6Ch]
0x18004b5bb  cmp     eax, ecx
0x18004b5bd  cmovle  ecx, eax
0x18004b5c0  cmp     ecx, 960h
0x18004b5c6  jl      short loc_18004B5CF
0x18004b5c8  mov     edi, 10h
0x18004b5cd  jmp     short loc_18004B617
0x18004b5cf  cmp     ecx, 708h
0x18004b5d5  jl      short loc_18004B5DE
0x18004b5d7  mov     edi, 38h ; '8'
0x18004b5dc  jmp     short loc_18004B617
0x18004b5de  mov     r8d, 8
0x18004b5e4  cmp     ecx, 4B0h
0x18004b5ea  jl      short loc_18004B5F2
0x18004b5ec  lea     edi, [r8+10h]
0x18004b5f0  jmp     short loc_18004B61D
0x18004b5f2  mov     edi, 28h ; '('
0x18004b5f7  cmp     ecx, 320h
0x18004b5fd  mov     eax, r8d
0x18004b600  cmovge  eax, edi
0x18004b603  mov     edi, eax
0x18004b605  jmp     short loc_18004B61D
0x18004b607  mov     rax, [rbx+0F18h]
0x18004b60e  mov     edi, [rax+18h]
0x18004b611  add     edi, 7
0x18004b614  and     edi, 0FFFFFFF8h
0x18004b617  mov     r8d, 8
0x18004b61d  mov     r12d, [rbp+iFormat]
0x18004b621  cmp     r14d, esi
0x18004b624  mov     eax, 2
0x18004b629  cmovbe  r14d, eax
0x18004b62d  xor     edx, edx
0x18004b62f  test    byte ptr [rbx+70h], 80h
0x18004b633  jz      short loc_18004B669
0x18004b635  mov     eax, [rbx+0FECh]
0x18004b63b  div     r14d
0x18004b63e  mov     [rbp+sizl.cx], eax
0x18004b641  mov     ecx, eax
0x18004b643  cmp     eax, edi
0x18004b645  jl      loc_18004B47E
0x18004b64b  cdq
0x18004b64c  idiv    edi
0x18004b64e  sub     ecx, edx
0x18004b650  lea     eax, [rcx+rdi]
0x18004b653  mov     [rbp+sizl.cx], eax
0x18004b656  imul    eax, [rbp+var_30]
0x18004b65a  add     eax, 1Fh
0x18004b65d  and     eax, 0FFFFFFE0h
0x18004b660  cdq
0x18004b661  idiv    r8d
0x18004b664  mov     r13d, eax
0x18004b667  jmp     short loc_18004B68A
0x18004b669  mov     eax, [rbx+0FF0h]
0x18004b66f  div     r14d
0x18004b672  mov     r15d, eax
0x18004b675  cmp     eax, edi
0x18004b677  jl      loc_18004B47E
0x18004b67d  cdq
0x18004b67e  idiv    edi
0x18004b680  sub     r15d, edx
0x18004b683  add     r15d, edi
0x18004b686  mov     [rbp+sizl.cy], r15d
0x18004b68a  mov     rcx, qword ptr [rbp+sizl.cx]; sizl
0x18004b68e  mov     r9d, 0Bh; fl
0x18004b694  mov     r8d, r12d; iFormat
0x18004b697  mov     [rsp+70h+pvBits], 0; pvBits
0x18004b6a0  mov     edx, r13d; lWidth
0x18004b6a3  call    cs:__imp_EngCreateBitmap
0x18004b6aa  nop     dword ptr [rax+rax+00h]
0x18004b6af  mov     rcx, rax
0x18004b6b2  test    rax, rax
0x18004b6b5  jnz     loc_18004B523
0x18004b6bb  mov     eax, r15d
0x18004b6be  imul    eax, r13d
0x18004b6c2  and     eax, 0FFFFFFFEh
0x18004b6c5  cmp     eax, 100000h
0x18004b6ca  jb      loc_18004B47E
0x18004b6d0  add     r14d, r14d
0x18004b6d3  lea     r8d, [rcx+8]
0x18004b6d7  jmp     loc_18004B62D
```
