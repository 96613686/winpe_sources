# xpsrdr::CreateAndPushLayer(xpsrdr::RenderState &,std::shared_ptr<ID2D1RenderTarget> const &,D2D1_ANTIALIAS_MODE,D2D_RECT_F const &,std::shared_ptr<ID2D1Geometry> const &,float,std::shared_ptr<ID2D1Brush> const &)

- ea: `0x180037e18`
- end: `0x18003806f`
- name: `?CreateAndPushLayer@xpsrdr@@YA?AW4LAYER_CLIP_USE@1@AEAURenderState@1@AEBV?$shared_ptr@UID2D1RenderTarget@@@std@@W4D2D1_ANTIALIAS_MODE@@AEBUD2D_RECT_F@@AEBV?$shared_ptr@UID2D1Geometry@@@5@MAEBV?$shared_ptr@UID2D1Brush@@@5@@Z`
- size: `599`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x180039984`
- `0x180039cd4`
- `0x18003a18c`
- `0x18003ac3c`

## callees

- `0x180008830`
- `0x18000d7f8`
- `0x18000e990`
- `0x18000f89c`
- `0x1800152b8`
- `0x180027cac`
- `0x1800348a0`
- `0x180037e18`
- `0x18004a010`

## pseudocode

```c
char __fastcall xpsrdr::CreateAndPushLayer(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        xpsrdr *a4,
        _QWORD *a5,
        float a6,
        _QWORD *a7)
{
  __int64 v7; // rdi
  int v9; // r15d
  struct D2D_MATRIX_3X2_F *v11; // rax
  const struct D2D_MATRIX_3X2_F *v12; // r8
  struct D2D_MATRIX_3X2_F *v13; // rax
  __int64 v14; // xmm1_8
  struct D2D_RECT_F *v15; // r9
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v24; // rcx
  _BYTE v25[48]; // [rsp+38h] [rbp-D0h]
  _BYTE v26[24]; // [rsp+70h] [rbp-98h] BYREF
  struct D2D_MATRIX_3X2_F v27; // [rsp+88h] [rbp-80h] BYREF
  struct D2D_RECT_F v28; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v29; // [rsp+B0h] [rbp-58h]
  __int128 v30; // [rsp+B8h] [rbp-50h] BYREF
  _OWORD v31[4]; // [rsp+C8h] [rbp-40h] BYREF
  __int64 v32; // [rsp+108h] [rbp+0h]

  v7 = a1 + 488;
  v9 = a3;
  ++*(_DWORD *)(*(_QWORD *)(a1 + 544) + 132LL);
  *(_OWORD *)&v27.m11 = 0;
  v11 = (struct D2D_MATRIX_3X2_F *)std::stack<D2D_MATRIX_3X2_F>::top(a1 + 488, a2, a3, a4);
  v13 = xpsrdr::InverseMatrix((xpsrdr *)v26, v11, v12);
  v14 = *(_QWORD *)&v13->m[2][0];
  v28 = *(struct D2D_RECT_F *)&v13->m11;
  v29 = v14;
  xpsrdr::TransformRectF(a4, &v28, &v27, v15);
  v30 = 0;
  if ( a6 == 1.0
    && !(unsigned __int8)std::operator!=<ID3D11Device>(a7)
    && (v19 = std::stack<D2D_MATRIX_3X2_F>::top(v7, v16, v17, v18),
        (unsigned __int8)xpsrdr::IsRectGeometry(v19, a5, &v30)) )
  {
    v20 = *a2;
    v29 = 0;
    v28 = 0;
    (*(void (__fastcall **)(__int64, struct D2D_RECT_F *))(*(_QWORD *)v20 + 248LL))(v20, &v28);
    v21 = *a2;
    *(__m128i *)&v27.m11 = _mm_load_si128((const __m128i *)&_xmm);
    *(_QWORD *)&v27.m[2][0] = 0;
    (*(void (__fastcall **)(__int64, struct D2D_MATRIX_3X2_F *))(*(_QWORD *)v21 + 240LL))(v21, &v27);
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*a2 + 304LL))(*a2, 362854208, 65);
    v22 = std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>((__int64)a2);
    (*(void (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v22 + 360LL))(v22, &v30, 1);
    (*(void (__fastcall **)(_QWORD, struct D2D_RECT_F *))(*(_QWORD *)*a2 + 240LL))(*a2, &v28);
    return 1;
  }
  else
  {
    (*(void (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*a2 + 304LL))(*a2, 362854208, 85);
    v24 = *a2;
    *(_QWORD *)v25 = *a5;
    *(__m128i *)&v25[12] = _mm_load_si128((const __m128i *)&_xmm);
    *(_QWORD *)&v25[40] = *a7;
    v31[0] = *(_OWORD *)&v27.m11;
    *(_QWORD *)&v25[28] = 0;
    *(_DWORD *)&v25[8] = v9;
    v31[2] = *(_OWORD *)&v25[16];
    v31[1] = *(_OWORD *)v25;
    *(float *)&v25[36] = a6;
    v32 = 0;
    v31[3] = *(_OWORD *)&v25[32];
    (*(void (__fastcall **)(__int64, _OWORD *, _QWORD))(*(_QWORD *)v24 + 320LL))(v24, v31, 0);
    return 0;
  }
}

```

## disassembly

```asm
0x180037e18  mov     rax, rsp
0x180037e1b  mov     [rax+18h], rbx
0x180037e1f  push    rbp
0x180037e20  push    rsi
0x180037e21  push    rdi
0x180037e22  push    r14
0x180037e24  push    r15
0x180037e26  lea     rbp, [rax-58h]
0x180037e2a  sub     rsp, 130h
0x180037e31  movaps  xmmword ptr [rax-38h], xmm6
0x180037e35  mov     rax, cs:__security_cookie
0x180037e3c  xor     rax, rsp
0x180037e3f  mov     [rbp+50h+var_40], rax
0x180037e43  mov     rax, [rcx+220h]
0x180037e4a  lea     rdi, [rcx+1E8h]
0x180037e51  mov     rsi, [rbp+50h+arg_20]
0x180037e58  xorps   xmm0, xmm0
0x180037e5b  mov     rcx, rdi
0x180037e5e  mov     rbx, r9
0x180037e61  mov     r15d, r8d
0x180037e64  mov     r14, rdx
0x180037e67  inc     dword ptr [rax+84h]
0x180037e6d  movups  xmmword ptr [rbp+50h+var_D0], xmm0
0x180037e71  call    ?top@?$stack@UD2D_MATRIX_3X2_F@@V?$deque@UD2D_MATRIX_3X2_F@@V?$allocator@UD2D_MATRIX_3X2_F@@@std@@@std@@@std@@QEAAAEAUD2D_MATRIX_3X2_F@@XZ; std::stack<D2D_MATRIX_3X2_F>::top(void)
0x180037e76  mov     rdx, rax; retstr
0x180037e79  lea     rcx, [rsp+150h+var_E8]; this
0x180037e7e  call    ?InverseMatrix@xpsrdr@@YA?AUD2D_MATRIX_3X2_F@@AEBU2@@Z; xpsrdr::InverseMatrix(D2D_MATRIX_3X2_F const &)
0x180037e83  lea     r8, [rbp+50h+var_D0]; struct D2D_MATRIX_3X2_F *
0x180037e87  mov     rcx, rbx; this
0x180037e8a  lea     rdx, [rbp+50h+var_B8]; struct D2D_RECT_F *
0x180037e8e  movups  xmm0, xmmword ptr [rax]
0x180037e91  movsd   xmm1, qword ptr [rax+10h]
0x180037e96  movups  xmmword ptr [rbp+50h+var_B8.left], xmm0
0x180037e9a  movsd   [rbp+50h+var_A8], xmm1
0x180037e9f  call    ?TransformRectF@xpsrdr@@YAXAEBUD2D_RECT_F@@AEBUD2D_MATRIX_3X2_F@@AEAU2@@Z; xpsrdr::TransformRectF(D2D_RECT_F const &,D2D_MATRIX_3X2_F const &,D2D_RECT_F &)
0x180037ea4  movss   xmm6, [rbp+50h+arg_28]
0x180037eac  xorps   xmm0, xmm0
0x180037eaf  ucomiss xmm6, cs:__real@3f800000
0x180037eb6  mov     rbx, [rbp+50h+arg_30]
0x180037ebd  movups  [rbp+50h+var_A0], xmm0
0x180037ec1  jp      loc_180037FA7
0x180037ec7  jnz     loc_180037FA7
0x180037ecd  mov     rcx, rbx
0x180037ed0  call    ??$?9UID3D11Device@@@std@@YA_NAEBV?$shared_ptr@UID3D11Device@@@0@$$T@Z; std::operator!=<ID3D11Device>(std::shared_ptr<ID3D11Device> const &,std::nullptr_t)
0x180037ed5  test    al, al
0x180037ed7  jnz     loc_180037FA7
0x180037edd  mov     rcx, rdi
0x180037ee0  call    ?top@?$stack@UD2D_MATRIX_3X2_F@@V?$deque@UD2D_MATRIX_3X2_F@@V?$allocator@UD2D_MATRIX_3X2_F@@@std@@@std@@@std@@QEAAAEAUD2D_MATRIX_3X2_F@@XZ; std::stack<D2D_MATRIX_3X2_F>::top(void)
0x180037ee5  mov     rcx, rax
0x180037ee8  lea     r8, [rbp+50h+var_A0]
0x180037eec  mov     rdx, rsi
0x180037eef  call    ?IsRectGeometry@xpsrdr@@YA_NAEBUD2D_MATRIX_3X2_F@@AEBV?$shared_ptr@UID2D1Geometry@@@std@@AEAUD2D_RECT_F@@@Z; xpsrdr::IsRectGeometry(D2D_MATRIX_3X2_F const &,std::shared_ptr<ID2D1Geometry> const &,D2D_RECT_F &)
0x180037ef4  test    al, al
0x180037ef6  jz      loc_180037FA7
0x180037efc  mov     rcx, [r14]
0x180037eff  lea     rdx, [rbp+50h+var_B8]
0x180037f03  xor     eax, eax
0x180037f05  xorps   xmm0, xmm0
0x180037f08  mov     [rbp+50h+var_A8], rax
0x180037f0c  movups  xmmword ptr [rbp+50h+var_B8.left], xmm0
0x180037f10  mov     rax, [rcx]
0x180037f13  mov     rax, [rax+0F8h]
0x180037f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f1f  mov     rcx, [r14]
0x180037f22  lea     rdx, [rbp+50h+var_D0]
0x180037f26  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x180037f2e  movups  xmmword ptr [rbp+50h+var_D0], xmm0
0x180037f32  mov     qword ptr [rbp+50h+var_D0+10h], 0
0x180037f3a  mov     rax, [rcx]
0x180037f3d  mov     rax, [rax+0F0h]
0x180037f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f49  mov     rcx, [r14]
0x180037f4c  mov     edx, 15A0B740h
0x180037f51  mov     r8d, 41h ; 'A'
0x180037f57  mov     rax, [rcx]
0x180037f5a  mov     rax, [rax+130h]
0x180037f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f66  mov     rcx, r14
0x180037f69  call    ??$?CUIDWriteFactory@@$0A@@?$shared_ptr@UIDWriteFactory@@@std@@QEBAPEAUIDWriteFactory@@XZ; std::shared_ptr<IDWriteFactory>::operator-><IDWriteFactory,0>(void)
0x180037f6e  mov     rcx, rax
0x180037f71  lea     rdx, [rbp+50h+var_A0]
0x180037f75  mov     r8d, 1
0x180037f7b  mov     rax, [rax]
0x180037f7e  mov     rax, [rax+168h]
0x180037f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037f8a  mov     rcx, [r14]
0x180037f8d  mov     rdx, [rcx]
0x180037f90  mov     rax, [rdx+0F0h]
0x180037f97  lea     rdx, [rbp+50h+var_B8]
0x180037f9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037fa0  mov     al, 1
0x180037fa2  jmp     loc_180038047
0x180037fa7  mov     rcx, [r14]
0x180037faa  mov     edx, 15A0B740h
0x180037faf  mov     r8d, 55h ; 'U'
0x180037fb5  mov     rax, [rcx]
0x180037fb8  mov     rax, [rax+130h]
0x180037fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037fc4  movups  xmm1, xmmword ptr [rbp+50h+var_D0]
0x180037fc8  mov     rax, [rsi]
0x180037fcb  lea     rdx, [rbp+50h+var_90]
0x180037fcf  movdqa  xmm0, cs:__xmm@3f80000000000000000000003f800000
0x180037fd7  xor     r8d, r8d
0x180037fda  mov     rcx, [r14]
0x180037fdd  mov     qword ptr [rsp+150h+var_128+8], rax
0x180037fe2  mov     rax, [rbx]
0x180037fe5  movups  xmmword ptr [rsp+3Ch], xmm0
0x180037fea  mov     [rsp+150h+var_F8], rax
0x180037fef  movaps  [rbp+50h+var_90], xmm1
0x180037ff3  mov     qword ptr [rsp+150h+var_10C+8], 0
0x180037ffc  movups  xmm1, xmmword ptr [rsp+40h]
0x180038001  mov     [rsp+150h+var_118], r15d
0x180038006  movups  xmm0, [rsp+150h+var_128+8]
0x18003800b  mov     qword ptr [rsp+150h+var_F0], 0
0x180038014  movaps  [rbp+50h+var_70], xmm1
0x180038018  movsd   xmm1, qword ptr [rsp+150h+var_F0]
0x18003801e  movaps  [rbp+50h+var_80], xmm0
0x180038022  movss   [rsp+150h+var_FC], xmm6
0x180038028  movups  xmm0, [rsp+150h+var_10C+0Ch]
0x18003802d  movsd   [rbp+50h+var_50], xmm1
0x180038032  movaps  [rbp+50h+var_60], xmm0
0x180038036  mov     rax, [rcx]
0x180038039  mov     rax, [rax+140h]
0x180038040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038045  xor     al, al
0x180038047  mov     rcx, [rbp+50h+var_40]
0x18003804b  xor     rcx, rsp; StackCookie
0x18003804e  call    __security_check_cookie
0x180038053  lea     r11, [rsp+150h+var_20]
0x18003805b  mov     rbx, [r11+40h]
0x18003805f  movaps  xmm6, xmmword ptr [r11-10h]
0x180038064  mov     rsp, r11
0x180038067  pop     r15
0x180038069  pop     r14
0x18003806b  pop     rdi
0x18003806c  pop     rsi
0x18003806d  pop     rbp
0x18003806e  retn
```
