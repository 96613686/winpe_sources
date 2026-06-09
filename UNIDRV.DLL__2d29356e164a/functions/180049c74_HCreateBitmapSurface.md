# HCreateBitmapSurface

- ea: `0x180049c74`
- end: `0x18004a103`
- name: `HCreateBitmapSurface`
- size: `1167`
- prototype: `HBITMAP __fastcall(__int64, ULONG)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x1800493a0`

## callees

- `0x18001c38c`
- `0x1800487e0`
- `0x180049c74`
- `0x18004a10c`
- `0x180075010`

## import_xrefs

- `GDI32!EngCreateBitmap` at `0x180049f1d`
- `GDI32!EngCreateBitmap` at `0x18004a0d0`
- `GDI32!EngCreateBitmap` at `0x180049f1d`
- `GDI32!EngCreateBitmap` at `0x18004a0d0`

## pseudocode

```c
HBITMAP __fastcall HCreateBitmapSurface(__int64 a1, ULONG a2)
{
  __int64 v2; // r10
  int v4; // r12d
  unsigned int v5; // edi
  LONG cx; // r11d
  LONG v7; // r15d
  void (__fastcall *v8)(__int64, __int64 *); // r10
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
  __int64 v19; // r8
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
  __int64 v36; // [rsp+50h] [rbp-20h] BYREF
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
  if ( (unsigned int)BConfigureOemDevObj(a1, 37) )
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
      (*(void (__fastcall **)(_QWORD, __int64, __int64 *))(*(_QWORD *)v10 + 144LL))(v9[9], a1, &v36);
    }
    else
    {
      v8(a1, &v36);
    }
    cx = sizl.cx;
  }
LABEL_18:
  v5 = 100 * (6291456 - (int)v36) / (unsigned int)(HIDWORD(v36) + 100);
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
  if ( !(unsigned int)BConfigureOemDevObj(a1, 47) )
    goto LABEL_33;
  v21 = HCreateBitmapSurfaceWithOemPlugin(a1, a2, v19, &v35, &v36, &v33);
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
    *(_QWORD *)(a1 + 1972) = v36;
    return Bitmap;
  }
  return 0;
}

```

## disassembly

```asm
0x180049c74  mov     [rsp-38h+arg_10], rbx
0x180049c79  push    rbp
0x180049c7a  push    rsi
0x180049c7b  push    rdi
0x180049c7c  push    r12
0x180049c7e  push    r13
0x180049c80  push    r14
0x180049c82  push    r15
0x180049c84  mov     rbp, rsp
0x180049c87  sub     rsp, 70h
0x180049c8b  mov     rax, cs:__security_cookie
0x180049c92  xor     rax, rsp
0x180049c95  mov     [rbp+var_10], rax
0x180049c99  mov     r10, [rcx+768h]
0x180049ca0  mov     rbx, rcx
0x180049ca3  movsx   r12d, word ptr [rcx+0A28h]
0x180049cab  mov     edi, 600000h
0x180049cb0  mov     r11d, [rcx+0FECh]
0x180049cb7  mov     r14d, 100000h
0x180049cbd  mov     r15d, [rcx+0FF0h]
0x180049cc4  mov     qword ptr [rbp+sizl.cx], 0
0x180049ccc  mov     [rbp+iFormat], edx
0x180049ccf  mov     [rbp+var_28], 0
0x180049cd7  mov     [rbp+sizl.cx], r11d
0x180049cdb  mov     [rbp+sizl.cy], r15d
0x180049cdf  mov     [rbp+var_30], r12d
0x180049ce3  test    r10, r10
0x180049ce6  jz      loc_180049DC9
0x180049cec  mov     r10, [r10+250h]
0x180049cf3  test    r10, r10
0x180049cf6  jz      loc_180049DC9
0x180049cfc  mov     edx, 25h ; '%'
0x180049d01  mov     [rbp+var_20], 0
0x180049d09  mov     [rbp+var_18], edi
0x180049d0c  call    BConfigureOemDevObj
0x180049d11  test    eax, eax
0x180049d13  jz      loc_180049DB0
0x180049d19  mov     rax, [rbx+760h]
0x180049d20  mov     r9, [rax+48h]
0x180049d24  test    r9, r9
0x180049d27  jz      short loc_180049D9D
0x180049d29  mov     rcx, [rax+50h]
0x180049d2d  sub     rcx, qword ptr cs:IID_IPrintOemUni.Data1
0x180049d34  jnz     short loc_180049D41
0x180049d36  mov     rcx, [rax+58h]
0x180049d3a  sub     rcx, qword ptr cs:IID_IPrintOemUni.Data4
0x180049d41  test    rcx, rcx
0x180049d44  jnz     short loc_180049D61
0x180049d46  mov     rax, [r9]
0x180049d49  lea     r8, [rbp+var_20]
0x180049d4d  mov     rdx, rbx
0x180049d50  mov     rcx, r9
0x180049d53  mov     rax, [rax+90h]
0x180049d5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d5f  jmp     short loc_180049DAC
0x180049d61  mov     rcx, [rax+50h]
0x180049d65  sub     rcx, qword ptr cs:IID_IPrintOemUni2.Data1
0x180049d6c  jnz     short loc_180049D79
0x180049d6e  mov     rcx, [rax+58h]
0x180049d72  sub     rcx, qword ptr cs:IID_IPrintOemUni2.Data4
0x180049d79  test    rcx, rcx
0x180049d7c  jz      short loc_180049D46
0x180049d7e  mov     rcx, [rax+50h]
0x180049d82  sub     rcx, qword ptr cs:IID_IPrintOemUni3.Data1
0x180049d89  jnz     short loc_180049D96
0x180049d8b  mov     rcx, [rax+58h]
0x180049d8f  sub     rcx, qword ptr cs:IID_IPrintOemUni3.Data4
0x180049d96  test    rcx, rcx
0x180049d99  jnz     short loc_180049DB0
0x180049d9b  jmp     short loc_180049D46
0x180049d9d  lea     rdx, [rbp+var_20]
0x180049da1  mov     rcx, rbx
0x180049da4  mov     rax, r10
0x180049da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049dac  mov     r11d, [rbp+sizl.cx]
0x180049db0  sub     edi, dword ptr [rbp+var_20]
0x180049db3  xor     edx, edx
0x180049db5  mov     ecx, dword ptr [rbp+var_20+4]
0x180049db8  imul    eax, edi, 64h ; 'd'
0x180049dbb  add     ecx, 64h ; 'd'
0x180049dbe  div     ecx
0x180049dc0  cmp     eax, r14d
0x180049dc3  mov     edi, eax
0x180049dc5  cmovb   edi, r14d
0x180049dc9  mov     ecx, 8
0x180049dce  mov     eax, r12d
0x180049dd1  imul    eax, r11d
0x180049dd5  mov     esi, 1
0x180049dda  add     eax, 1Fh
0x180049ddd  and     eax, 0FFFFFFE0h
0x180049de0  cdq
0x180049de1  idiv    ecx
0x180049de3  mov     rcx, [rbx+768h]
0x180049dea  xor     edx, edx
0x180049dec  mov     r13d, eax
0x180049def  mov     eax, r15d
0x180049df2  imul    eax, r13d
0x180049df6  div     edi
0x180049df8  lea     r14d, [rax+1]
0x180049dfc  test    rcx, rcx
0x180049dff  jz      loc_180049EDC
0x180049e05  cmp     qword ptr [rcx+2F0h], 0
0x180049e0d  jz      loc_180049EDC
0x180049e13  lea     edx, [rsi+2Eh]
0x180049e16  mov     [rbp+var_20], 0
0x180049e1e  mov     rcx, rbx
0x180049e21  mov     [rbp+var_34], r14d
0x180049e25  call    BConfigureOemDevObj
0x180049e2a  mov     edi, [rbp+iFormat]
0x180049e2d  test    eax, eax
0x180049e2f  jz      loc_180049EDF
0x180049e35  lea     rax, [rbp+var_34]
0x180049e39  mov     edx, edi
0x180049e3b  mov     [rsp+70h+var_48], rax
0x180049e40  lea     r9, [rbp+var_28]
0x180049e44  lea     rax, [rbp+var_20]
0x180049e48  mov     rcx, rbx
0x180049e4b  mov     [rsp+70h+pvBits], rax
0x180049e50  call    HCreateBitmapSurfaceWithOemPlugin
0x180049e55  test    eax, eax
0x180049e57  js      short loc_180049EAD
0x180049e59  mov     rcx, [rbp+var_28]
0x180049e5d  test    rcx, rcx
0x180049e60  jz      short loc_180049EB6
0x180049e62  cmp     eax, esi
0x180049e64  jz      short loc_180049EB6
0x180049e66  cmp     [rbp+var_34], esi
0x180049e69  ja      short loc_180049E90
0x180049e6b  mov     eax, [rbx+0FECh]
0x180049e71  xor     esi, esi
0x180049e73  mov     [rbx+7C4h], eax
0x180049e79  mov     eax, [rbx+0FF0h]
0x180049e7f  mov     [rbx+7C8h], eax
0x180049e85  mov     qword ptr [rbx+7BCh], 0
0x180049e90  mov     [rbx+7A8h], esi
0x180049e96  mov     eax, dword ptr [rbp+var_20]
0x180049e99  mov     [rbx+7B4h], eax
0x180049e9f  mov     eax, dword ptr [rbp+var_20+4]
0x180049ea2  mov     [rbx+7B8h], eax
0x180049ea8  mov     rax, rcx
0x180049eab  jmp     short loc_180049EB8
0x180049ead  add     eax, 7FFFBFFFh
0x180049eb2  cmp     eax, esi
0x180049eb4  jbe     short loc_180049EDF
0x180049eb6  xor     eax, eax
0x180049eb8  mov     rcx, [rbp+var_10]
0x180049ebc  xor     rcx, rsp; StackCookie
0x180049ebf  call    __security_check_cookie
0x180049ec4  mov     rbx, [rsp+70h+arg_10]
0x180049ecc  add     rsp, 70h
0x180049ed0  pop     r15
0x180049ed2  pop     r14
0x180049ed4  pop     r13
0x180049ed6  pop     r12
0x180049ed8  pop     rdi
0x180049ed9  pop     rsi
0x180049eda  pop     rbp
0x180049edb  retn
0x180049edc  mov     edi, [rbp+iFormat]
0x180049edf  cmp     r14d, esi
0x180049ee2  ja      loc_180049F6B
0x180049ee8  test    dword ptr [rbx+70h], 1000h
0x180049eef  jnz     short loc_180049F6B
0x180049ef1  mov     rax, [rbx+7E8h]
0x180049ef8  test    dword ptr [rax+8Ch], 6000h
0x180049f02  jnz     short loc_180049F6B
0x180049f04  mov     rcx, qword ptr [rbp+sizl.cx]; sizl
0x180049f08  mov     r9d, 0Bh; fl
0x180049f0e  mov     r8d, edi; iFormat
0x180049f11  mov     [rsp+70h+pvBits], 0; pvBits
0x180049f1a  mov     edx, r13d; lWidth
0x180049f1d  call    cs:__imp_EngCreateBitmap
0x180049f23  mov     rcx, rax
0x180049f26  test    rax, rax
0x180049f29  jz      short loc_180049F6B
0x180049f2b  mov     eax, [rbx+0FECh]
0x180049f31  xor     esi, esi
0x180049f33  mov     [rbx+7C4h], eax
0x180049f39  mov     eax, [rbx+0FF0h]
0x180049f3f  mov     [rbx+7C8h], eax
0x180049f45  mov     qword ptr [rbx+7BCh], 0
0x180049f50  mov     eax, [rbp+sizl.cx]
0x180049f53  mov     [rbx+7A8h], esi
0x180049f59  mov     [rbx+7B4h], eax
0x180049f5f  mov     [rbx+7B8h], r15d
0x180049f66  jmp     loc_180049EA8
0x180049f6b  cmp     r12w, si
0x180049f6f  jnz     loc_18004A034
0x180049f75  mov     rax, [rbx+0F18h]
0x180049f7c  cmp     [rax+18h], esi
0x180049f7f  jnz     loc_18004A034
0x180049f85  mov     rax, [rbx+0F58h]
0x180049f8c  test    rax, rax
0x180049f8f  jz      short loc_180049FDC
0x180049f91  mov     eax, [rax+38h]
0x180049f94  cmp     eax, 0FFh
0x180049f99  jz      short loc_180049FDC
0x180049f9b  cmp     eax, 5
0x180049f9e  jz      short loc_180049FD5
0x180049fa0  cmp     eax, 0Bh
0x180049fa3  jz      short loc_180049FD5
0x180049fa5  cmp     eax, 9
0x180049fa8  jnz     short loc_180049FB2
0x180049faa  lea     edi, [rax+1Fh]
0x180049fad  jmp     loc_18004A044
0x180049fb2  mov     r8d, 8
0x180049fb8  cmp     eax, 0Dh
0x180049fbb  jnz     short loc_180049FC5
0x180049fbd  lea     edi, [rax+2Bh]
0x180049fc0  jmp     loc_18004A04A
0x180049fc5  cmp     eax, 0Fh
0x180049fc8  mov     edi, r8d
0x180049fcb  mov     ecx, 10h
0x180049fd0  cmovz   edi, ecx
0x180049fd3  jmp     short loc_18004A04A
0x180049fd5  mov     edi, 18h
0x180049fda  jmp     short loc_18004A044
0x180049fdc  mov     eax, [rbx+0F68h]
0x180049fe2  mov     ecx, [rbx+0F6Ch]
0x180049fe8  cmp     eax, ecx
0x180049fea  cmovle  ecx, eax
0x180049fed  cmp     ecx, 960h
0x180049ff3  jl      short loc_180049FFC
0x180049ff5  mov     edi, 10h
0x180049ffa  jmp     short loc_18004A044
0x180049ffc  cmp     ecx, 708h
0x18004a002  jl      short loc_18004A00B
0x18004a004  mov     edi, 38h ; '8'
0x18004a009  jmp     short loc_18004A044
0x18004a00b  mov     r8d, 8
0x18004a011  cmp     ecx, 4B0h
0x18004a017  jl      short loc_18004A01F
0x18004a019  lea     edi, [r8+10h]
0x18004a01d  jmp     short loc_18004A04A
0x18004a01f  mov     edi, 28h ; '('
0x18004a024  cmp     ecx, 320h
0x18004a02a  mov     eax, r8d
0x18004a02d  cmovge  eax, edi
0x18004a030  mov     edi, eax
0x18004a032  jmp     short loc_18004A04A
0x18004a034  mov     rax, [rbx+0F18h]
0x18004a03b  mov     edi, [rax+18h]
0x18004a03e  add     edi, 7
0x18004a041  and     edi, 0FFFFFFF8h
0x18004a044  mov     r8d, 8
0x18004a04a  mov     r12d, [rbp+iFormat]
0x18004a04e  cmp     r14d, esi
0x18004a051  mov     eax, 2
0x18004a056  cmovbe  r14d, eax
0x18004a05a  xor     edx, edx
0x18004a05c  test    byte ptr [rbx+70h], 80h
0x18004a060  jz      short loc_18004A096
0x18004a062  mov     eax, [rbx+0FECh]
0x18004a068  div     r14d
0x18004a06b  mov     [rbp+sizl.cx], eax
0x18004a06e  mov     ecx, eax
0x18004a070  cmp     eax, edi
0x18004a072  jl      loc_180049EB6
0x18004a078  cdq
0x18004a079  idiv    edi
0x18004a07b  sub     ecx, edx
0x18004a07d  lea     eax, [rcx+rdi]
0x18004a080  mov     [rbp+sizl.cx], eax
0x18004a083  imul    eax, [rbp+var_30]
0x18004a087  add     eax, 1Fh
0x18004a08a  and     eax, 0FFFFFFE0h
0x18004a08d  cdq
0x18004a08e  idiv    r8d
0x18004a091  mov     r13d, eax
0x18004a094  jmp     short loc_18004A0B7
0x18004a096  mov     eax, [rbx+0FF0h]
0x18004a09c  div     r14d
0x18004a09f  mov     r15d, eax
0x18004a0a2  cmp     eax, edi
0x18004a0a4  jl      loc_180049EB6
0x18004a0aa  cdq
0x18004a0ab  idiv    edi
0x18004a0ad  sub     r15d, edx
0x18004a0b0  add     r15d, edi
0x18004a0b3  mov     [rbp+sizl.cy], r15d
0x18004a0b7  mov     rcx, qword ptr [rbp+sizl.cx]; sizl
0x18004a0bb  mov     r9d, 0Bh; fl
0x18004a0c1  mov     r8d, r12d; iFormat
0x18004a0c4  mov     [rsp+70h+pvBits], 0; pvBits
0x18004a0cd  mov     edx, r13d; lWidth
0x18004a0d0  call    cs:__imp_EngCreateBitmap
0x18004a0d6  mov     rcx, rax
0x18004a0d9  test    rax, rax
0x18004a0dc  jnz     loc_180049F50
0x18004a0e2  mov     eax, r15d
0x18004a0e5  imul    eax, r13d
0x18004a0e9  and     eax, 0FFFFFFFEh
0x18004a0ec  cmp     eax, 100000h
0x18004a0f1  jb      loc_180049EB6
0x18004a0f7  add     r14d, r14d
0x18004a0fa  lea     r8d, [rcx+8]
0x18004a0fe  jmp     loc_18004A05A
```
