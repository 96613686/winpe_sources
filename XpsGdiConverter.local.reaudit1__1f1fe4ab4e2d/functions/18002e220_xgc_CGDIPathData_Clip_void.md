# xgc::CGDIPathData::Clip(void)

- ea: `0x18002e220`
- end: `0x18002e433`
- name: `?Clip@CGDIPathData@xgc@@QEBAXXZ`
- size: `531`
- prototype: `void(xgc::CGDIPathData *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180027ed4`
- `0x18002e684`
- `0x18002f6e8`

## callees

- `0x18002ccb4`
- `0x18002e220`
- `0x180037278`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002e290`
- `KERNEL32!GetLastError` at `0x18002e2dc`
- `KERNEL32!GetLastError` at `0x18002e31a`
- `KERNEL32!GetLastError` at `0x18002e351`
- `KERNEL32!GetLastError` at `0x18002e397`
- `KERNEL32!GetLastError` at `0x18002e3ce`
- `KERNEL32!GetLastError` at `0x18002e40e`
- `KERNEL32!GetLastError` at `0x18002e290`
- `KERNEL32!GetLastError` at `0x18002e2dc`
- `KERNEL32!GetLastError` at `0x18002e31a`
- `KERNEL32!GetLastError` at `0x18002e351`
- `KERNEL32!GetLastError` at `0x18002e397`
- `KERNEL32!GetLastError` at `0x18002e3ce`
- `KERNEL32!GetLastError` at `0x18002e40e`
- `GDI32!DeleteObject` at `0x18002e2bd`
- `GDI32!DeleteObject` at `0x18002e2bd`
- `GDI32!GetPolyFillMode` at `0x18002e2d2`
- `GDI32!GetPolyFillMode` at `0x18002e2d2`
- `GDI32!BeginPath` at `0x18002e347`
- `GDI32!BeginPath` at `0x18002e347`
- `GDI32!PolyDraw` at `0x18002e38d`
- `GDI32!PolyDraw` at `0x18002e38d`
- `GDI32!SelectClipPath` at `0x18002e400`
- `GDI32!SelectClipPath` at `0x18002e400`
- `GDI32!SetPolyFillMode` at `0x18002e310`
- `GDI32!SetPolyFillMode` at `0x18002e310`
- `GDI32!CreateRectRgn` at `0x18002e26d`
- `GDI32!CreateRectRgn` at `0x18002e26d`
- `GDI32!EndPath` at `0x18002e3c4`
- `GDI32!EndPath` at `0x18002e3c4`
- `GDI32!SelectClipRgn` at `0x18002e286`
- `GDI32!SelectClipRgn` at `0x18002e286`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall xgc::CGDIPathData::Clip(
        xgc::CGDIPathData *this,
        const struct D2D_MATRIX_3X2_F *a2,
        __int64 a3,
        float a4)
{
  __int64 v5; // rcx
  struct tagPOINT v6; // rax
  HRGN RectRgn; // rbx
  signed int v8; // eax
  int v9; // edx
  const char *v10; // r8
  int v11; // r9d
  __int64 v12; // rcx
  int PolyFillMode; // eax
  signed int LastError; // eax
  int v15; // edx
  const char *v16; // r8
  int v17; // r9d
  __int64 v18; // rcx
  int v19; // edx
  signed int v20; // eax
  int v21; // edx
  const char *v22; // r8
  int v23; // r9d
  __int64 v24; // rcx
  signed int v25; // eax
  int v26; // edx
  const char *v27; // r8
  int v28; // r9d
  __int64 v29; // rcx
  signed int v30; // eax
  int v31; // edx
  const char *v32; // r8
  int v33; // r9d
  __int64 v34; // rcx
  signed int v35; // eax
  int v36; // edx
  const char *v37; // r8
  int v38; // r9d
  __int64 v39; // rcx
  signed int v40; // eax
  int v41; // edx
  const char *v42; // r8
  int v43; // r9d
  __int64 v44; // rcx
  bool v45; // [rsp+20h] [rbp-8h]

  v5 = *((_QWORD *)this + 2);
  if ( (unsigned __int64)((__int64)(*((_QWORD *)this + 6) - *((_QWORD *)this + 5)) >> 3) >= 2 )
  {
    PolyFillMode = GetPolyFillMode(*(HDC *)(v5 + 32));
    if ( !PolyFillMode )
    {
      LastError = GetLastError();
      v18 = (unsigned int)LastError;
      if ( LastError > 0 )
        v18 = (unsigned __int16)LastError | 0x80070000;
      if ( (int)v18 >= 0 )
        v18 = 2147500037LL;
      xpsrdr::ThrowHRException((xpsrdr *)v18, v15, v16, v17);
    }
    v19 = *((_DWORD *)this + 24);
    if ( PolyFillMode != v19 && !SetPolyFillMode(*(HDC *)(*((_QWORD *)this + 2) + 32LL), v19) )
    {
      v20 = GetLastError();
      v24 = (unsigned int)v20;
      if ( v20 > 0 )
        v24 = (unsigned __int16)v20 | 0x80070000;
      if ( (int)v24 >= 0 )
        v24 = 2147500037LL;
      xpsrdr::ThrowHRException((xpsrdr *)v24, v21, v22, v23);
    }
    if ( !BeginPath(*(HDC *)(*((_QWORD *)this + 2) + 32LL)) )
    {
      v25 = GetLastError();
      v29 = (unsigned int)v25;
      if ( v25 > 0 )
        v29 = (unsigned __int16)v25 | 0x80070000;
      if ( (int)v29 >= 0 )
        v29 = 2147500037LL;
      xpsrdr::ThrowHRException((xpsrdr *)v29, v26, v27, v28);
    }
    if ( !PolyDraw(
            *(HDC *)(*((_QWORD *)this + 2) + 32LL),
            *((const POINT **)this + 5),
            *((const BYTE **)this + 8),
            *((_DWORD *)this + 18) - *((_QWORD *)this + 8)) )
    {
      v30 = GetLastError();
      v34 = (unsigned int)v30;
      if ( v30 > 0 )
        v34 = (unsigned __int16)v30 | 0x80070000;
      if ( (int)v34 >= 0 )
        v34 = 2147500037LL;
      xpsrdr::ThrowHRException((xpsrdr *)v34, v31, v32, v33);
    }
    if ( !EndPath(*(HDC *)(*((_QWORD *)this + 2) + 32LL)) )
    {
      v35 = GetLastError();
      v39 = (unsigned int)v35;
      if ( v35 > 0 )
        v39 = (unsigned __int16)v35 | 0x80070000;
      if ( (int)v39 >= 0 )
        v39 = 2147500037LL;
      xpsrdr::ThrowHRException((xpsrdr *)v39, v36, v37, v38);
    }
    if ( !SelectClipPath(*(HDC *)(*((_QWORD *)this + 2) + 32LL), 1) )
    {
      v40 = GetLastError();
      v44 = (unsigned int)v40;
      if ( v40 > 0 )
        v44 = (unsigned __int16)v40 | 0x80070000;
      if ( (int)v44 >= 0 )
        v44 = 2147500037LL;
      xpsrdr::ThrowHRException((xpsrdr *)v44, v41, v42, v43);
    }
  }
  else
  {
    v6 = xgc::TransformPoints((xgc *)(v5 + 40), a2, -1.0, a4, v45);
    RectRgn = CreateRectRgn(v6.x, v6.y, v6.x, v6.y);
    if ( !SelectClipRgn(*(HDC *)(*((_QWORD *)this + 2) + 32LL), RectRgn) )
    {
      v8 = GetLastError();
      v12 = (unsigned int)v8;
      if ( v8 > 0 )
        v12 = (unsigned __int16)v8 | 0x80070000;
      if ( (int)v12 >= 0 )
        v12 = 2147500037LL;
      xpsrdr::ThrowHRException((xpsrdr *)v12, v9, v10, v11);
    }
    if ( RectRgn )
      DeleteObject(RectRgn);
  }
}

```

## disassembly

```asm
0x18002e220  mov     [rsp+arg_8], rbx
0x18002e225  push    rdi; bool
0x18002e226  sub     rsp, 20h
0x18002e22a  mov     rdi, rcx
0x18002e22d  mov     rcx, [rcx+10h]
0x18002e231  mov     rax, [rdi+30h]
0x18002e235  sub     rax, [rdi+28h]
0x18002e239  sar     rax, 3
0x18002e23d  cmp     rax, 2
0x18002e241  jnb     loc_18002E2CE
0x18002e247  add     rcx, 28h ; '('; this
0x18002e24b  xor     r9d, r9d
0x18002e24e  movss   xmm1, cs:__real@bf800000
0x18002e256  movaps  xmm2, xmm1; float
0x18002e259  call    ?TransformPoints@xgc@@YA?AUtagPOINT@@AEBUD2D_MATRIX_3X2_F@@MM_N@Z; xgc::TransformPoints(D2D_MATRIX_3X2_F const &,float,float,bool)
0x18002e25e  mov     rdx, rax
0x18002e261  shr     rdx, 20h; y1
0x18002e265  mov     r9d, edx; y2
0x18002e268  mov     r8d, eax; x2
0x18002e26b  mov     ecx, eax; x1
0x18002e26d  call    cs:__imp_CreateRectRgn
0x18002e273  mov     rbx, rax
0x18002e276  mov     [rsp+28h+arg_0], rax
0x18002e27b  mov     rcx, [rdi+10h]
0x18002e27f  mov     rdx, rax; hrgn
0x18002e282  mov     rcx, [rcx+20h]; hdc
0x18002e286  call    cs:__imp_SelectClipRgn
0x18002e28c  test    eax, eax
0x18002e28e  jnz     short loc_18002E2B5
0x18002e290  call    cs:__imp_GetLastError
0x18002e296  mov     ecx, eax
0x18002e298  test    eax, eax
0x18002e29a  jle     short loc_18002E2A5
0x18002e29c  movzx   ecx, ax
0x18002e29f  or      ecx, 80070000h
0x18002e2a5  mov     eax, 80004005h
0x18002e2aa  test    ecx, ecx
0x18002e2ac  cmovns  ecx, eax; this
0x18002e2af  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002e2b5  test    rbx, rbx
0x18002e2b8  jz      short loc_18002E2C3
0x18002e2ba  mov     rcx, rbx; ho
0x18002e2bd  call    cs:__imp_DeleteObject
0x18002e2c3  mov     rbx, [rsp+28h+arg_8]
0x18002e2c8  add     rsp, 20h
0x18002e2cc  pop     rdi
0x18002e2cd  retn
0x18002e2ce  mov     rcx, [rcx+20h]; hdc
0x18002e2d2  call    cs:__imp_GetPolyFillMode
0x18002e2d8  test    eax, eax
0x18002e2da  jnz     short loc_18002E301
0x18002e2dc  call    cs:__imp_GetLastError
0x18002e2e2  mov     ecx, eax
0x18002e2e4  test    eax, eax
0x18002e2e6  jle     short loc_18002E2F1
0x18002e2e8  movzx   ecx, ax
0x18002e2eb  or      ecx, 80070000h
0x18002e2f1  mov     eax, 80004005h
0x18002e2f6  test    ecx, ecx
0x18002e2f8  cmovns  ecx, eax; this
0x18002e2fb  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002e301  mov     edx, [rdi+60h]; mode
0x18002e304  cmp     eax, edx
0x18002e306  jz      short loc_18002E33F
0x18002e308  mov     rcx, [rdi+10h]
0x18002e30c  mov     rcx, [rcx+20h]; hdc
0x18002e310  call    cs:__imp_SetPolyFillMode
0x18002e316  test    eax, eax
0x18002e318  jnz     short loc_18002E33F
0x18002e31a  call    cs:__imp_GetLastError
0x18002e320  mov     ecx, eax
0x18002e322  test    eax, eax
0x18002e324  jle     short loc_18002E32F
0x18002e326  movzx   ecx, ax
0x18002e329  or      ecx, 80070000h
0x18002e32f  mov     eax, 80004005h
0x18002e334  test    ecx, ecx
0x18002e336  cmovns  ecx, eax; this
0x18002e339  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002e33f  mov     rcx, [rdi+10h]
0x18002e343  mov     rcx, [rcx+20h]; hdc
0x18002e347  call    cs:__imp_BeginPath
0x18002e34d  test    eax, eax
0x18002e34f  jnz     short loc_18002E376
0x18002e351  call    cs:__imp_GetLastError
0x18002e357  mov     ecx, eax
0x18002e359  test    eax, eax
0x18002e35b  jle     short loc_18002E366
0x18002e35d  movzx   ecx, ax
0x18002e360  or      ecx, 80070000h
0x18002e366  mov     eax, 80004005h
0x18002e36b  test    ecx, ecx
0x18002e36d  cmovns  ecx, eax; this
0x18002e370  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002e376  mov     r8, [rdi+40h]; aj
0x18002e37a  mov     r9d, [rdi+48h]
0x18002e37e  sub     r9d, r8d; cpt
0x18002e381  mov     rcx, [rdi+10h]
0x18002e385  mov     rdx, [rdi+28h]; apt
0x18002e389  mov     rcx, [rcx+20h]; hdc
0x18002e38d  call    cs:__imp_PolyDraw
0x18002e393  test    eax, eax
0x18002e395  jnz     short loc_18002E3BC
0x18002e397  call    cs:__imp_GetLastError
0x18002e39d  mov     ecx, eax
0x18002e39f  test    eax, eax
0x18002e3a1  jle     short loc_18002E3AC
0x18002e3a3  movzx   ecx, ax
0x18002e3a6  or      ecx, 80070000h
0x18002e3ac  mov     eax, 80004005h
0x18002e3b1  test    ecx, ecx
0x18002e3b3  cmovns  ecx, eax; this
0x18002e3b6  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002e3bc  mov     rcx, [rdi+10h]
0x18002e3c0  mov     rcx, [rcx+20h]; hdc
0x18002e3c4  call    cs:__imp_EndPath
0x18002e3ca  test    eax, eax
0x18002e3cc  jnz     short loc_18002E3F3
0x18002e3ce  call    cs:__imp_GetLastError
0x18002e3d4  mov     ecx, eax
0x18002e3d6  test    eax, eax
0x18002e3d8  jle     short loc_18002E3E3
0x18002e3da  movzx   ecx, ax
0x18002e3dd  or      ecx, 80070000h
0x18002e3e3  mov     eax, 80004005h
0x18002e3e8  test    ecx, ecx
0x18002e3ea  cmovns  ecx, eax; this
0x18002e3ed  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
0x18002e3f3  mov     rcx, [rdi+10h]
0x18002e3f7  mov     edx, 1; mode
0x18002e3fc  mov     rcx, [rcx+20h]; hdc
0x18002e400  call    cs:__imp_SelectClipPath
0x18002e406  test    eax, eax
0x18002e408  jnz     loc_18002E2C3
0x18002e40e  call    cs:__imp_GetLastError
0x18002e414  mov     ecx, eax
0x18002e416  test    eax, eax
0x18002e418  jle     short loc_18002E423
0x18002e41a  movzx   ecx, ax
0x18002e41d  or      ecx, 80070000h
0x18002e423  mov     eax, 80004005h
0x18002e428  test    ecx, ecx
0x18002e42a  cmovns  ecx, eax; this
0x18002e42d  call    ?ThrowHRException@xpsrdr@@YAXJPEBDH@Z; xpsrdr::ThrowHRException(long,char const *,int)
```
