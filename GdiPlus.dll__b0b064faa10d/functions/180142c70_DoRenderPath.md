# DoRenderPath

- ea: `0x180142c70`
- end: `0x1801430a4`
- name: `DoRenderPath`
- size: `1076`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: ``

## callers

- `0x1800c4564`
- `0x18013f470`
- `0x180140390`
- `0x1801403b0`
- `0x18014296c`

## callees

- `0x1800af12c`
- `0x1800c4204`
- `0x1800c42f4`
- `0x1800f0e88`
- `0x18013e940`
- `0x180142b2c`
- `0x180142c70`
- `0x180143464`
- `0x18014358c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180142d3a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180142daf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180142d3a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180142daf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180143066`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180143074`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180143083`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180143066`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180143074`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180143083`
- `GDI32!GetPath` at `0x180142d04`
- `GDI32!GetPath` at `0x180142d68`
- `GDI32!GetPath` at `0x180142d04`
- `GDI32!GetPath` at `0x180142d68`
- `GDI32!AbortPath` at `0x180143058`
- `GDI32!AbortPath` at `0x180143058`
- `GDI32!FlattenPath` at `0x180142cea`
- `GDI32!FlattenPath` at `0x180142cea`
- `GDI32!SetROP2` at `0x180142f39`
- `GDI32!SetROP2` at `0x180142f8b`
- `GDI32!SetROP2` at `0x180142f39`
- `GDI32!SetROP2` at `0x180142f8b`

## pseudocode

```c
__int64 __fastcall DoRenderPath(__int64 a1, int a2, int a3)
{
  struct tagPOINT *v3; // r13
  unsigned int v4; // r15d
  _QWORD *v6; // r14
  __int64 v7; // rdi
  int Path; // eax
  struct tagPOINT *v9; // rax
  HDC v10; // rcx
  ULONGLONG v11; // rsi
  char *v12; // rax
  _QWORD *v13; // r9
  char *v14; // rdx
  char *v15; // rax
  unsigned int v16; // esi
  __int64 v17; // r8
  int v18; // r12d
  unsigned int v19; // r10d
  unsigned int v20; // r11d
  ULONGLONG v21; // r15
  char *v22; // r10
  __int64 v23; // rdx
  __int64 v24; // rcx
  char v25; // al
  unsigned int v26; // ecx
  ULONGLONG v27; // rax
  int v28; // edi
  int v29; // eax
  unsigned int v30; // edi
  __int64 v31; // r8
  __int64 v32; // r9
  int v34; // [rsp+30h] [rbp-30h]
  char *v35; // [rsp+38h] [rbp-28h]
  ULONGLONG uBytes; // [rsp+40h] [rbp-20h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-18h] BYREF
  _QWORD *v38; // [rsp+50h] [rbp-10h]
  char *v39; // [rsp+58h] [rbp-8h]
  ULONGLONG pullResult; // [rsp+B8h] [rbp+58h] BYREF

  v3 = 0;
  v4 = 0;
  hMem = 0;
  LODWORD(pullResult) = 0;
  v6 = 0;
  if ( (unsigned int)GdipFlattenGdiPath(a1, &hMem, &pullResult) )
  {
    LODWORD(v7) = pullResult;
    if ( !(_DWORD)pullResult )
    {
LABEL_3:
      v4 = 1;
      goto LABEL_49;
    }
    v38 = hMem;
    v34 = 0;
    pullResult = (ULONGLONG)hMem + 8 * (int)pullResult;
  }
  else
  {
    if ( !FlattenPath(*(HDC *)(a1 + 40)) )
      goto LABEL_49;
    Path = GetPath(*(HDC *)(a1 + 40), 0, 0, 0);
    v7 = Path;
    if ( Path < 0 )
      goto LABEL_49;
    if ( !Path )
      goto LABEL_3;
    pullResult = 0;
    if ( ULongLongMult(9u, Path, &pullResult) < 0
      || (v9 = (struct tagPOINT *)LocalAlloc(0, pullResult), (v3 = v9) == 0)
      || (v10 = *(HDC *)(a1 + 40),
          pullResult = (ULONGLONG)&v9[v7],
          GetPath(v10, v9, (LPBYTE)pullResult, v7) != (_DWORD)v7) )
    {
LABEL_49:
      if ( !a3 )
        goto LABEL_50;
      goto LABEL_51;
    }
    v34 = 1;
    v38 = v3;
  }
  uBytes = 0;
  v11 = (int)v7 + (int)v7 / 2;
  if ( ULongLongMult(0xDu, v11, &uBytes) < 0 )
    goto LABEL_49;
  v12 = (char *)LocalAlloc(0, uBytes);
  v6 = v12;
  if ( !v12 )
    goto LABEL_49;
  v13 = v38;
  v14 = &v12[8 * v11];
  v15 = &v14[4 * v11];
  v35 = v14;
  v16 = 0;
  v39 = v15;
  v17 = 0;
  v18 = 0;
  while ( (int)v17 < (int)v7 )
  {
    v19 = v16;
    v20 = v16;
    uBytes = (int)v16;
    v39[v16] = *(_BYTE *)((int)v17 + pullResult);
    v4 = 0;
    v6[v16] = v13[(int)v17];
    LODWORD(v14) = (_DWORD)v35;
    v17 = (unsigned int)(v17 + 1);
    ++v16;
    if ( (int)v17 >= (int)v7 )
    {
      v16 = v19;
      break;
    }
    v21 = pullResult;
    v22 = v39;
    do
    {
      if ( (int)v17 >= (int)v7 )
        break;
      v23 = (int)v16;
      v22[v16] = *(_BYTE *)((int)v17 + v21);
      v6[v16] = v13[(int)v17];
      v17 = (unsigned int)(v17 + 1);
      ++v16;
    }
    while ( v22[v23] == 2 );
    v4 = 0;
    LODWORD(v14) = (_DWORD)v35;
    v24 = (int)v16;
    v25 = v22[v16 - 1];
    switch ( v25 )
    {
      case 6:
        --v16;
        v17 = (unsigned int)(v17 - 1);
        v26 = v16 - v20;
        if ( v16 - v20 != 1 )
          goto LABEL_26;
        v16 = v20;
        break;
      case 2:
        *(_DWORD *)&v35[4 * v18++] = v16 - v20;
        goto LABEL_29;
      case 3:
        v27 = uBytes;
        ++v16;
        *(_WORD *)&v22[v24 - 1] = 514;
        v6[v24] = v6[v27];
        v26 = v16 - v20;
LABEL_26:
        *(_DWORD *)&v35[4 * v18++] = v26;
        break;
    }
  }
LABEL_29:
  if ( !v16 )
  {
    v4 = 1;
    goto LABEL_49;
  }
  if ( a2 == 64 && !a3 )
  {
    v4 = DoPolyPolyline(a1, (_DWORD)v6, (_DWORD)v14, v18, v34);
    goto LABEL_50;
  }
  if ( *(_DWORD *)(a1 + 484) != 3 && !a3 )
  {
LABEL_41:
    v30 = 0;
    if ( a2 != 62 || (v30 = *(_DWORD *)(a1 + 436), (unsigned int)DoSelectObject(a1, 2147483656LL, v17, v13)) )
    {
      v4 = DoPolyPolygon(a1, v6, v35, v16, v18, v34);
      if ( a2 == 62 )
        DoSelectObject(a1, v30, v31, v32);
      v29 = a3;
      goto LABEL_46;
    }
    goto LABEL_49;
  }
  v28 = SetROP2(*(HDC *)(a1 + 40), 11);
  if ( !(unsigned int)bW16Emit1(a1, 260, 11) )
    goto LABEL_49;
  v4 = ConvertPolyPolygonToPolygons(a1, v6, v35, v16, v18, v34);
  if ( !v4 )
    goto LABEL_49;
  SetROP2(*(HDC *)(a1 + 40), v28);
  if ( !(unsigned int)bW16Emit1(a1, 260, (unsigned __int16)v28) )
    goto LABEL_49;
  LOWORD(pullResult) = 1;
  if ( !(unsigned int)bEmitWin16Escape(a1, 38, 2, &pullResult) )
    goto LABEL_49;
  v29 = a3;
  if ( !a3 )
    goto LABEL_41;
LABEL_46:
  if ( *(_DWORD *)(a1 + 484) == 3 || v29 )
  {
    LOWORD(pullResult) = 0;
    bEmitWin16Escape(a1, 38, 2, &pullResult);
    goto LABEL_49;
  }
LABEL_50:
  AbortPath(*(HDC *)(a1 + 40));
LABEL_51:
  if ( v6 )
    LocalFree(v6);
  if ( v3 )
    LocalFree(v3);
  if ( hMem )
    LocalFree(hMem);
  return v4;
}

```

## disassembly

```asm
0x180142c70  mov     [rsp-38h+arg_0], rbx
0x180142c75  mov     [rsp-38h+arg_10], r8d
0x180142c7a  mov     [rsp-38h+arg_8], edx
0x180142c7e  push    rbp
0x180142c7f  push    rsi
0x180142c80  push    rdi
0x180142c81  push    r12
0x180142c83  push    r13
0x180142c85  push    r14
0x180142c87  push    r15
0x180142c89  mov     rbp, rsp
0x180142c8c  sub     rsp, 60h
0x180142c90  xor     r13d, r13d
0x180142c93  lea     r8, [rbp+pullResult]
0x180142c97  xor     r15d, r15d
0x180142c9a  mov     [rbp+hMem], r13
0x180142c9e  lea     rdx, [rbp+hMem]
0x180142ca2  mov     dword ptr [rbp+pullResult], r13d
0x180142ca6  mov     [rbp+var_2C], r15d
0x180142caa  mov     rbx, rcx
0x180142cad  xor     r14d, r14d
0x180142cb0  call    GdipFlattenGdiPath
0x180142cb5  lea     esi, [r13+1]
0x180142cb9  test    eax, eax
0x180142cbb  jz      short loc_180142CE6
0x180142cbd  movsxd  rdi, dword ptr [rbp+pullResult]
0x180142cc1  test    edi, edi
0x180142cc3  jnz     short loc_180142CCD
0x180142cc5  mov     r15d, esi
0x180142cc8  jmp     loc_18014304E
0x180142ccd  mov     r9, [rbp+hMem]
0x180142cd1  mov     [rbp+var_10], r9
0x180142cd5  mov     [rbp+var_30], r13d
0x180142cd9  lea     rax, [r9+rdi*8]
0x180142cdd  mov     [rbp+pullResult], rax
0x180142ce1  jmp     loc_180142D7D
0x180142ce6  mov     rcx, [rbx+28h]; hdc
0x180142cea  call    cs:__imp_FlattenPath
0x180142cf0  test    eax, eax
0x180142cf2  jz      loc_18014304E
0x180142cf8  mov     rcx, [rbx+28h]; hdc
0x180142cfc  xor     r9d, r9d; cpt
0x180142cff  xor     r8d, r8d; aj
0x180142d02  xor     edx, edx; apt
0x180142d04  call    cs:__imp_GetPath
0x180142d0a  movsxd  rdi, eax
0x180142d0d  test    eax, eax
0x180142d0f  js      loc_18014304E
0x180142d15  jz      short loc_180142CC5
0x180142d17  lea     r8, [rbp+pullResult]; pullResult
0x180142d1b  mov     [rbp+pullResult], r13
0x180142d1f  mov     rdx, rdi; ullMultiplier
0x180142d22  mov     ecx, 9; ullMultiplicand
0x180142d27  call    ULongLongMult
0x180142d2c  test    eax, eax
0x180142d2e  js      loc_18014304E
0x180142d34  mov     rdx, [rbp+pullResult]; uBytes
0x180142d38  xor     ecx, ecx; uFlags
0x180142d3a  call    cs:__imp_LocalAlloc
0x180142d40  mov     r13, rax
0x180142d43  test    rax, rax
0x180142d46  jz      loc_18014304E
0x180142d4c  mov     rcx, [rbx+28h]; hdc
0x180142d50  lea     r12, ds:0[rdi*8]
0x180142d58  add     r12, rax
0x180142d5b  mov     r9d, edi; cpt
0x180142d5e  mov     r8, r12; aj
0x180142d61  mov     [rbp+pullResult], r12
0x180142d65  mov     rdx, rax; apt
0x180142d68  call    cs:__imp_GetPath
0x180142d6e  cmp     eax, edi
0x180142d70  jnz     loc_18014304E
0x180142d76  mov     [rbp+var_30], esi
0x180142d79  mov     [rbp+var_10], r13
0x180142d7d  mov     eax, edi
0x180142d7f  mov     [rbp+uBytes], r14
0x180142d83  cdq
0x180142d84  lea     r8, [rbp+uBytes]; pullResult
0x180142d88  mov     ecx, 2
0x180142d8d  idiv    ecx
0x180142d8f  mov     ecx, 0Dh; ullMultiplicand
0x180142d94  add     eax, edi
0x180142d96  movsxd  rsi, eax
0x180142d99  mov     rdx, rsi; ullMultiplier
0x180142d9c  call    ULongLongMult
0x180142da1  test    eax, eax
0x180142da3  js      loc_18014304E
0x180142da9  mov     rdx, [rbp+uBytes]; uBytes
0x180142dad  xor     ecx, ecx; uFlags
0x180142daf  call    cs:__imp_LocalAlloc
0x180142db5  mov     r14, rax
0x180142db8  test    rax, rax
0x180142dbb  jz      loc_18014304E
0x180142dc1  mov     r9, [rbp+var_10]
0x180142dc5  lea     rdx, [rax+rsi*8]
0x180142dc9  lea     rax, [rdx+rsi*4]
0x180142dcd  mov     [rbp+var_28], rdx
0x180142dd1  xor     esi, esi
0x180142dd3  mov     [rbp+var_8], rax
0x180142dd7  xor     r8d, r8d
0x180142dda  xor     r12d, r12d
0x180142ddd  mov     eax, 1
0x180142de2  cmp     r8d, edi
0x180142de5  jge     loc_180142EE6
0x180142deb  mov     r15, [rbp+var_8]
0x180142def  mov     r10d, esi
0x180142df2  movsxd  rax, esi
0x180142df5  mov     r11d, esi
0x180142df8  mov     [rbp+uBytes], rax
0x180142dfc  mov     rdx, [rbp+uBytes]
0x180142e00  mov     rax, [rbp+pullResult]
0x180142e04  movsxd  rcx, r8d
0x180142e07  mov     al, [rcx+rax]
0x180142e0a  mov     [rdx+r15], al
0x180142e0e  mov     rax, [r9+rcx*8]
0x180142e12  mov     r15d, [rbp+var_2C]
0x180142e16  mov     [r14+rdx*8], rax
0x180142e1a  mov     eax, 1
0x180142e1f  mov     rdx, [rbp+var_28]
0x180142e23  add     r8d, eax
0x180142e26  add     esi, eax
0x180142e28  cmp     r8d, edi
0x180142e2b  jge     loc_180142EE3
0x180142e31  mov     r15, [rbp+pullResult]
0x180142e35  mov     r10, [rbp+var_8]
0x180142e39  cmp     r8d, edi
0x180142e3c  jge     short loc_180142E65
0x180142e3e  movsxd  rdx, esi
0x180142e41  movsxd  rcx, r8d
0x180142e44  mov     al, [rcx+r15]
0x180142e48  mov     [rdx+r10], al
0x180142e4c  mov     rax, [r9+rcx*8]
0x180142e50  mov     [r14+rdx*8], rax
0x180142e54  mov     eax, 1
0x180142e59  add     r8d, eax
0x180142e5c  add     esi, eax
0x180142e5e  cmp     byte ptr [rdx+r10], 2
0x180142e63  jz      short loc_180142E39
0x180142e65  mov     r15d, [rbp+var_2C]
0x180142e69  mov     rdx, [rbp+var_28]
0x180142e6d  movsxd  rcx, esi
0x180142e70  mov     al, [rcx+r10-1]
0x180142e75  cmp     al, 6
0x180142e77  jnz     short loc_180142E94
0x180142e79  dec     esi
0x180142e7b  mov     eax, 1
0x180142e80  mov     ecx, esi
0x180142e82  sub     r8d, eax
0x180142e85  sub     ecx, r11d
0x180142e88  cmp     ecx, eax
0x180142e8a  jnz     short loc_180142EBB
0x180142e8c  mov     esi, r11d
0x180142e8f  jmp     loc_180142DE2
0x180142e94  cmp     al, 2
0x180142e96  jz      short loc_180142ECE
0x180142e98  cmp     al, 3
0x180142e9a  jnz     loc_180142DDD
0x180142ea0  mov     rax, [rbp+uBytes]
0x180142ea4  inc     esi
0x180142ea6  mov     word ptr [rcx+r10-1], 202h
0x180142eae  mov     rax, [r14+rax*8]
0x180142eb2  mov     [r14+rcx*8], rax
0x180142eb6  mov     ecx, esi
0x180142eb8  sub     ecx, r11d
0x180142ebb  movsxd  rax, r12d
0x180142ebe  mov     [rdx+rax*4], ecx
0x180142ec1  mov     eax, 1
0x180142ec6  add     r12d, eax
0x180142ec9  jmp     loc_180142DE2
0x180142ece  movsxd  rax, r12d
0x180142ed1  mov     ecx, esi
0x180142ed3  sub     ecx, r11d
0x180142ed6  mov     [rdx+rax*4], ecx
0x180142ed9  mov     eax, 1
0x180142ede  add     r12d, eax
0x180142ee1  jmp     short loc_180142EE6
0x180142ee3  mov     esi, r10d
0x180142ee6  test    esi, esi
0x180142ee8  jnz     short loc_180142EF2
0x180142eea  mov     r15d, eax
0x180142eed  jmp     loc_18014304E
0x180142ef2  cmp     [rbp+arg_8], 40h ; '@'
0x180142ef6  mov     eax, [rbp+arg_10]
0x180142ef9  jnz     short loc_180142F1F
0x180142efb  test    eax, eax
0x180142efd  jnz     short loc_180142F1F
0x180142eff  mov     eax, [rbp+var_30]
0x180142f02  mov     r8, rdx
0x180142f05  mov     rdx, r14
0x180142f08  mov     [rsp+60h+var_40], eax
0x180142f0c  mov     r9d, r12d
0x180142f0f  mov     rcx, rbx
0x180142f12  call    DoPolyPolyline
0x180142f17  mov     r15d, eax
0x180142f1a  jmp     loc_180143054
0x180142f1f  cmp     dword ptr [rbx+1E4h], 3
0x180142f26  jz      short loc_180142F30
0x180142f28  test    eax, eax
0x180142f2a  jz      loc_180142FD5
0x180142f30  mov     rcx, [rbx+28h]; hdc
0x180142f34  mov     edx, 0Bh; rop2
0x180142f39  call    cs:__imp_SetROP2
0x180142f3f  mov     edx, 104h
0x180142f44  mov     r8d, 0Bh
0x180142f4a  mov     rcx, rbx
0x180142f4d  mov     edi, eax
0x180142f4f  call    bW16Emit1
0x180142f54  test    eax, eax
0x180142f56  jz      loc_18014304E
0x180142f5c  mov     eax, [rbp+var_30]
0x180142f5f  mov     r9d, esi
0x180142f62  mov     r8, [rbp+var_28]
0x180142f66  mov     rdx, r14
0x180142f69  mov     [rsp+60h+var_38], eax
0x180142f6d  mov     rcx, rbx
0x180142f70  mov     [rsp+60h+var_40], r12d
0x180142f75  call    ConvertPolyPolygonToPolygons
0x180142f7a  mov     r15d, eax
0x180142f7d  test    eax, eax
0x180142f7f  jz      loc_18014304E
0x180142f85  mov     rcx, [rbx+28h]; hdc
0x180142f89  mov     edx, edi; rop2
0x180142f8b  call    cs:__imp_SetROP2
0x180142f91  movzx   r8d, di
0x180142f95  mov     edx, 104h
0x180142f9a  mov     rcx, rbx
0x180142f9d  call    bW16Emit1
0x180142fa2  test    eax, eax
0x180142fa4  jz      loc_18014304E
0x180142faa  mov     eax, 1
0x180142faf  lea     r9, [rbp+pullResult]
0x180142fb3  mov     rcx, rbx
0x180142fb6  mov     word ptr [rbp+pullResult], ax
0x180142fba  lea     edx, [rax+25h]
0x180142fbd  lea     r8d, [rax+1]
0x180142fc1  call    bEmitWin16Escape
0x180142fc6  test    eax, eax
0x180142fc8  jz      loc_18014304E
0x180142fce  mov     eax, [rbp+arg_10]
0x180142fd1  test    eax, eax
0x180142fd3  jnz     short loc_180143028
0x180142fd5  xor     edi, edi
0x180142fd7  cmp     [rbp+arg_8], 3Eh ; '>'
0x180142fdb  jnz     short loc_180142FF4
0x180142fdd  mov     edi, [rbx+1B4h]
0x180142fe3  mov     edx, 80000008h
0x180142fe8  mov     rcx, rbx
0x180142feb  call    DoSelectObject
0x180142ff0  test    eax, eax
0x180142ff2  jz      short loc_18014304E
0x180142ff4  mov     eax, [rbp+var_30]
0x180142ff7  mov     r9d, esi
0x180142ffa  mov     r8, [rbp+var_28]
0x180142ffe  mov     rdx, r14
0x180143001  mov     [rsp+60h+var_38], eax
0x180143005  mov     rcx, rbx
0x180143008  mov     [rsp+60h+var_40], r12d
0x18014300d  call    DoPolyPolygon
0x180143012  cmp     [rbp+arg_8], 3Eh ; '>'
0x180143016  mov     r15d, eax
0x180143019  jnz     short loc_180143025
0x18014301b  mov     edx, edi
0x18014301d  mov     rcx, rbx
0x180143020  call    DoSelectObject
0x180143025  mov     eax, [rbp+arg_10]
0x180143028  cmp     dword ptr [rbx+1E4h], 3
0x18014302f  jz      short loc_180143035
0x180143031  test    eax, eax
0x180143033  jz      short loc_180143054
0x180143035  xor     eax, eax
0x180143037  lea     r9, [rbp+pullResult]
0x18014303b  mov     rcx, rbx
0x18014303e  mov     word ptr [rbp+pullResult], ax
0x180143042  lea     edx, [rax+26h]
0x180143045  lea     r8d, [rax+2]
0x180143049  call    bEmitWin16Escape
0x18014304e  cmp     [rbp+arg_10], 0
0x180143052  jnz     short loc_18014305E
0x180143054  mov     rcx, [rbx+28h]; hdc
0x180143058  call    cs:__imp_AbortPath
0x18014305e  test    r14, r14
0x180143061  jz      short loc_18014306C
0x180143063  mov     rcx, r14; hMem
0x180143066  call    cs:__imp_LocalFree
0x18014306c  test    r13, r13
0x18014306f  jz      short loc_18014307A
0x180143071  mov     rcx, r13; hMem
0x180143074  call    cs:__imp_LocalFree
0x18014307a  mov     rcx, [rbp+hMem]; hMem
0x18014307e  test    rcx, rcx
0x180143081  jz      short loc_180143089
0x180143083  call    cs:__imp_LocalFree
0x180143089  mov     rbx, [rsp+60h+arg_0]
0x180143091  mov     eax, r15d
0x180143094  add     rsp, 60h
0x180143098  pop     r15
0x18014309a  pop     r14
0x18014309c  pop     r13
0x18014309e  pop     r12
0x1801430a0  pop     rdi
  ... truncated ...
```
