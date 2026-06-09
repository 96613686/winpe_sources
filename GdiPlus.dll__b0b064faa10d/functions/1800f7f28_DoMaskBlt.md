# DoMaskBlt

- ea: `0x1800f7f28`
- end: `0x1800f8577`
- name: `DoMaskBlt`
- size: `1615`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int@<edx>, int cy, int, int x1, int y1, __int64, UINT, BITMAPINFO *, SIZE_T, void *, int, int, int, UINT, BITMAPINFO *, int, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800f7cf0`
- `0x1800f89e8`

## callees

- `0x1800c2ce4`
- `0x1800c3bb8`
- `0x1800f7f28`
- `0x1800fe680`
- `0x180140d28`
- `0x1801414e8`
- `0x1801417e0`

## import_xrefs

- `GDI32!BitBlt` at `0x1800f826e`
- `GDI32!BitBlt` at `0x1800f82fe`
- `GDI32!BitBlt` at `0x1800f83f4`
- `GDI32!BitBlt` at `0x1800f8488`
- `GDI32!BitBlt` at `0x1800f826e`
- `GDI32!BitBlt` at `0x1800f82fe`
- `GDI32!BitBlt` at `0x1800f83f4`
- `GDI32!BitBlt` at `0x1800f8488`
- `GDI32!CreateDIBitmap` at `0x1800f8219`
- `GDI32!CreateDIBitmap` at `0x1800f8219`
- `GDI32!StretchDIBits` at `0x1800f81c0`
- `GDI32!StretchDIBits` at `0x1800f81c0`
- `GDI32!SetWorldTransform` at `0x1800f81d5`
- `GDI32!SetWorldTransform` at `0x1800f81d5`
- `GDI32!SetGraphicsMode` at `0x1800f80a8`
- `GDI32!SetGraphicsMode` at `0x1800f80a8`
- `GDI32!SetDIBits` at `0x1800f83a7`
- `GDI32!SetDIBits` at `0x1800f83a7`
- `GDI32!CreateBitmap` at `0x1800f80c4`
- `GDI32!CreateBitmap` at `0x1800f80c4`
- `GDI32!PatBlt` at `0x1800f810c`
- `GDI32!PatBlt` at `0x1800f810c`
- `GDI32!DeleteDC` at `0x1800f8521`
- `GDI32!DeleteDC` at `0x1800f854e`
- `GDI32!DeleteDC` at `0x1800f8521`
- `GDI32!DeleteDC` at `0x1800f854e`
- `GDI32!SelectObject` at `0x1800f80dd`
- `GDI32!SelectObject` at `0x1800f8231`
- `GDI32!SelectObject` at `0x1800f836d`
- `GDI32!SelectObject` at `0x1800f83bb`
- `GDI32!SelectObject` at `0x1800f850e`
- `GDI32!SelectObject` at `0x1800f8532`
- `GDI32!SelectObject` at `0x1800f80dd`
- `GDI32!SelectObject` at `0x1800f8231`
- `GDI32!SelectObject` at `0x1800f836d`
- `GDI32!SelectObject` at `0x1800f83bb`
- `GDI32!SelectObject` at `0x1800f850e`
- `GDI32!SelectObject` at `0x1800f8532`
- `GDI32!CreateCompatibleDC` at `0x1800f8084`
- `GDI32!CreateCompatibleDC` at `0x1800f8084`
- `GDI32!DeleteObject` at `0x1800f8518`
- `GDI32!DeleteObject` at `0x1800f8540`
- `GDI32!DeleteObject` at `0x1800f8518`
- `GDI32!DeleteObject` at `0x1800f8540`

## pseudocode

```c
__int64 __fastcall DoMaskBlt(
        __int64 a1,
        int a2,
        int a3,
        int a4,
        int cy,
        unsigned int a6,
        int x1,
        int y1,
        XFORM *a9,
        UINT a10,
        BITMAPINFO *a11,
        SIZE_T a12,
        void *lpBits,
        int a14,
        int a15,
        int a16,
        UINT a17,
        BITMAPINFO *lpbmi,
        int a19,
        void *a20)
{
  HDC CompatibleDC; // rax
  HDC v23; // rsi
  HDC v24; // rbx
  void *v25; // r15
  HBITMAP v26; // r12
  HBITMAP Bitmap; // rax
  int v28; // edx
  int v29; // r8d
  HBITMAP DIBitmap; // rax
  int iUsage; // [rsp+58h] [rbp-A8h]
  SIZE_T v32; // [rsp+68h] [rbp-98h]
  HGDIOBJ h; // [rsp+80h] [rbp-80h]
  BOOL v36; // [rsp+90h] [rbp-70h]
  HGDIOBJ v38; // [rsp+D0h] [rbp-30h]
  HBITMAP ho; // [rsp+D8h] [rbp-28h]
  int v40; // [rsp+E0h] [rbp-20h] BYREF
  int v41; // [rsp+E4h] [rbp-1Ch]
  int v42; // [rsp+E8h] [rbp-18h]
  int v43; // [rsp+ECh] [rbp-14h]

  if ( !a19 )
  {
    LODWORD(v32) = a12;
    return DoStretchBlt(a1, cy, a6 & 0xFF0000, x1, y1, a4, cy, (__int64)a9, a10, a11, v32, lpBits, a14);
  }
  if ( ((a6 ^ (4 * a6)) & 0xCCCC0000) == 0 )
    return DoMaskBltNoSrc(a1, a2, a3, a4, cy, a6, (__int64)a9, a15, a16, a17, lpbmi, iUsage, a20);
  v36 = 0;
  CompatibleDC = CreateCompatibleDC(0);
  v23 = CompatibleDC;
  if ( CompatibleDC )
  {
    v24 = 0;
    v25 = 0;
    h = 0;
    v26 = 0;
    SetGraphicsMode(CompatibleDC, 2);
    Bitmap = CreateBitmap(a11->bmiHeader.biWidth, a11->bmiHeader.biHeight, 1u, 1u, 0);
    ho = Bitmap;
    if ( !Bitmap )
    {
LABEL_36:
      DeleteDC(v23);
      if ( v25 )
        SelectObject(v24, v25);
      if ( v26 )
        DeleteObject(v26);
      if ( v24 )
        DeleteDC(v24);
      return v36;
    }
    v38 = SelectObject(v23, Bitmap);
    if ( !v38 )
    {
LABEL_35:
      DeleteObject(ho);
      goto LABEL_36;
    }
    if ( PatBlt(v23, 0, 0, a11->bmiHeader.biWidth, a11->bmiHeader.biHeight, 0x42u) )
    {
      v40 = x1;
      v41 = y1;
      v42 = a4 + x1;
      v43 = y1 + cy;
      if ( !(unsigned int)bXformWorkhorse(&v40, 2, a9) )
        goto LABEL_33;
      v28 = v40;
      v29 = v41;
      if ( v40 > v42 )
        v28 = v42;
      if ( v41 > v43 )
        v29 = v43;
      if ( !StretchDIBits(
              v23,
              v28 - a15,
              v29 - a16,
              lpbmi->bmiHeader.biWidth,
              lpbmi->bmiHeader.biHeight,
              0,
              0,
              lpbmi->bmiHeader.biWidth,
              lpbmi->bmiHeader.biHeight,
              a20,
              lpbmi,
              a17,
              0xCC0020u)
        || !SetWorldTransform(v23, a9) )
      {
LABEL_33:
        v25 = 0;
        goto LABEL_34;
      }
      v24 = (HDC)hdcMakeCompatibleDC(a9);
      if ( !v24 )
      {
        v25 = 0;
        goto LABEL_34;
      }
      DIBitmap = CreateDIBitmap(*(HDC *)(a1 + 40), &a11->bmiHeader, 4u, lpBits, a11, a10);
      v26 = DIBitmap;
      if ( DIBitmap )
      {
        h = SelectObject(v24, DIBitmap);
        if ( !h )
        {
          v25 = 0;
          goto LABEL_34;
        }
        if ( BitBlt(v24, x1, y1, a4, cy, v23, x1, y1, 0x8800C6u)
          && (unsigned int)DoStretchBltAlt(
                             a1,
                             a2,
                             a3,
                             a4,
                             cy,
                             a6 & 0xCC0000 | 0x220000,
                             x1,
                             y1,
                             a4,
                             cy,
                             v24,
                             v26,
                             (__int64)a9)
          && BitBlt(v24, x1, y1, a4, cy, v23, x1, y1, 0xBB0226u)
          && (unsigned int)DoStretchBltAlt(
                             a1,
                             a2,
                             a3,
                             a4,
                             cy,
                             a6 & 0x330000 | 0x880000,
                             x1,
                             y1,
                             a4,
                             cy,
                             v24,
                             v26,
                             (__int64)a9)
          && SelectObject(v24, h)
          && SetDIBits(*(HDC *)(a1 + 40), v26, 0, a11->bmiHeader.biHeight, lpBits, a11, a10)
          && SelectObject(v24, v26)
          && BitBlt(v24, x1, y1, a4, cy, v23, x1, y1, 0x220326u)
          && (unsigned int)DoStretchBltAlt(
                             a1,
                             a2,
                             a3,
                             a4,
                             cy,
                             (a6 >> 8) & 0xCC0000 | 0x220000,
                             x1,
                             y1,
                             a4,
                             cy,
                             v24,
                             v26,
                             (__int64)a9)
          && BitBlt(v24, x1, y1, a4, cy, v23, x1, y1, 0xEE0086u) )
        {
          v36 = DoStretchBltAlt(
                  a1,
                  a2,
                  a3,
                  a4,
                  cy,
                  (a6 >> 8) & 0x330000 | 0x880000,
                  x1,
                  y1,
                  a4,
                  cy,
                  v24,
                  v26,
                  (__int64)a9) != 0;
        }
      }
      v25 = h;
    }
LABEL_34:
    SelectObject(v23, v38);
    goto LABEL_35;
  }
  return v36;
}

```

## disassembly

```asm
0x1800f7f28  push    rbp
0x1800f7f2a  push    rbx
0x1800f7f2b  push    rsi
0x1800f7f2c  push    rdi
0x1800f7f2d  push    r12
0x1800f7f2f  push    r13
0x1800f7f31  push    r14
0x1800f7f33  push    r15
0x1800f7f35  lea     rbp, [rsp-8]
0x1800f7f3a  sub     rsp, 108h
0x1800f7f41  mov     rax, cs:__security_cookie
0x1800f7f48  xor     rax, rsp
0x1800f7f4b  mov     [rbp+40h+var_50], rax
0x1800f7f4f  mov     r13d, [rbp+40h+arg_28]
0x1800f7f53  mov     ebx, edx
0x1800f7f55  mov     r14, [rbp+40h+arg_50]
0x1800f7f5c  mov     edi, r9d
0x1800f7f5f  mov     r15, [rbp+40h+arg_60]
0x1800f7f66  mov     r11, rcx
0x1800f7f69  mov     r9, [rbp+40h+arg_88]
0x1800f7f70  mov     r10, [rbp+40h+arg_98]
0x1800f7f77  mov     esi, [rbp+40h+arg_48]
0x1800f7f7d  mov     [rbp+40h+var_B4], edx
0x1800f7f80  mov     edx, r13d
0x1800f7f83  and     edx, 0FF0000h
0x1800f7f89  mov     qword ptr [rbp+40h+var_A0], rcx
0x1800f7f8d  cmp     [rbp+40h+arg_90], 0
0x1800f7f94  mov     rcx, [rbp+40h+arg_40]
0x1800f7f9b  mov     [rbp+40h+var_B8], r8d
0x1800f7f9f  mov     [rbp+40h+lpxf], rcx
0x1800f7fa3  mov     [rbp+40h+ColorUse], esi
0x1800f7fa6  mov     [rbp+40h+pbmi], r14
0x1800f7faa  mov     [rbp+40h+pjBits], r15
0x1800f7fae  mov     [rbp+40h+var_80], r9
0x1800f7fb2  mov     [rbp+40h+var_78], r10
0x1800f7fb6  mov     [rbp+40h+var_98], edx
0x1800f7fb9  jnz     short loc_1800F801E
0x1800f7fbb  mov     eax, [rbp+40h+arg_68]
0x1800f7fc1  mov     r9d, edi
0x1800f7fc4  mov     r10d, [rbp+40h+cy]
0x1800f7fc8  mov     [rsp+140h+var_C8], eax; int
0x1800f7fcc  mov     eax, dword ptr [rbp+40h+arg_58]
0x1800f7fd2  mov     [rsp+140h+var_D0], r15; pjBits
0x1800f7fd7  mov     dword ptr [rsp+140h+var_D8], eax; SIZE_T
0x1800f7fdb  mov     eax, [rbp+40h+y1]
0x1800f7fe1  mov     qword ptr [rsp+140h+var_E0], r14; BITMAPINFO *
0x1800f7fe6  mov     [rsp+140h+iUsage], esi; UINT
0x1800f7fea  mov     [rsp+140h+lpbmi], rcx; __int64
0x1800f7fef  mov     rcx, r11; int
0x1800f7ff2  mov     [rsp+140h+var_F8], r10d; int
0x1800f7ff7  mov     [rsp+140h+SrcHeight], edi; int
0x1800f7ffb  mov     [rsp+140h+SrcWidth], eax; int
0x1800f7fff  mov     eax, [rbp+40h+x1]
0x1800f8005  mov     [rsp+140h+ySrc], eax; int
0x1800f8009  mov     [rsp+140h+rop], edx; int
0x1800f800d  mov     edx, ebx
0x1800f800f  mov     dword ptr [rsp+140h+lpBits], r10d; hDest
0x1800f8014  call    DoStretchBlt
0x1800f8019  jmp     loc_1800F8557
0x1800f801e  lea     eax, ds:0[r13*4]
0x1800f8026  xor     eax, r13d
0x1800f8029  test    eax, 0CCCC0000h
0x1800f802e  jnz     short loc_1800F807B
0x1800f8030  mov     eax, [rbp+40h+arg_80]
0x1800f8036  mov     edx, ebx; int
0x1800f8038  mov     qword ptr [rsp+140h+var_E0], r10; lpBits
0x1800f803d  mov     [rsp+140h+lpbmi], r9; lpbmi
0x1800f8042  mov     r9d, edi; int
0x1800f8045  mov     [rsp+140h+var_F8], eax; ColorUse
0x1800f8049  mov     eax, [rbp+40h+arg_78]
0x1800f804f  mov     [rsp+140h+SrcHeight], eax; int
0x1800f8053  mov     eax, [rbp+40h+arg_70]
0x1800f8059  mov     [rsp+140h+SrcWidth], eax; int
0x1800f805d  mov     eax, [rbp+40h+cy]
0x1800f8060  mov     qword ptr [rsp+140h+ySrc], rcx; __int64
0x1800f8065  mov     rcx, r11; int
0x1800f8068  mov     [rsp+140h+rop], r13d; int
0x1800f806d  mov     dword ptr [rsp+140h+lpBits], eax; int
0x1800f8071  call    DoMaskBltNoSrc
0x1800f8076  jmp     loc_1800F8557
0x1800f807b  xor     ecx, ecx; hdc
0x1800f807d  mov     [rbp+40h+var_B0], 0
0x1800f8084  call    cs:__imp_CreateCompatibleDC
0x1800f808a  mov     rsi, rax
0x1800f808d  test    rax, rax
0x1800f8090  jz      loc_1800F8554
0x1800f8096  xor     ebx, ebx
0x1800f8098  xor     r15d, r15d
0x1800f809b  mov     rcx, rax; hdc
0x1800f809e  mov     [rbp+40h+h], r15
0x1800f80a2  xor     r12d, r12d
0x1800f80a5  lea     edx, [rbx+2]; iMode
0x1800f80a8  call    cs:__imp_SetGraphicsMode
0x1800f80ae  mov     edx, [r14+8]; nHeight
0x1800f80b2  lea     eax, [rbx+1]
0x1800f80b5  mov     ecx, [r14+4]; nWidth
0x1800f80b9  mov     r9d, eax; nBitCount
0x1800f80bc  mov     r8d, eax; nPlanes
0x1800f80bf  mov     [rsp+140h+lpBits], rbx; lpBits
0x1800f80c4  call    cs:__imp_CreateBitmap
0x1800f80ca  mov     [rbp+40h+ho], rax
0x1800f80ce  test    rax, rax
0x1800f80d1  jz      loc_1800F851E
0x1800f80d7  mov     rdx, rax; h
0x1800f80da  mov     rcx, rsi; hdc
0x1800f80dd  call    cs:__imp_SelectObject
0x1800f80e3  mov     [rbp+40h+var_70], rax
0x1800f80e7  test    rax, rax
0x1800f80ea  jz      loc_1800F8514
0x1800f80f0  mov     ecx, [r14+8]
0x1800f80f4  xor     r8d, r8d; y
0x1800f80f7  mov     r9d, [r14+4]; w
0x1800f80fb  xor     edx, edx; x
0x1800f80fd  mov     [rsp+140h+rop], 42h ; 'B'; rop
0x1800f8105  mov     dword ptr [rsp+140h+lpBits], ecx; h
0x1800f8109  mov     rcx, rsi; hdc
0x1800f810c  call    cs:__imp_PatBlt
0x1800f8112  test    eax, eax
0x1800f8114  jz      loc_1800F8507
0x1800f811a  mov     r14d, [rbp+40h+x1]
0x1800f8121  lea     edx, [rbx+2]
0x1800f8124  mov     r15d, [rbp+40h+y1]
0x1800f812b  lea     rcx, [rbp+40h+var_60]
0x1800f812f  mov     r8, [rbp+40h+lpxf]
0x1800f8133  mov     [rbp+40h+var_60], r14d
0x1800f8137  lea     eax, [rdi+r14]
0x1800f813b  mov     [rbp+40h+var_5C], r15d
0x1800f813f  mov     [rbp+40h+var_58], eax
0x1800f8142  mov     eax, [rbp+40h+cy]
0x1800f8145  add     eax, r15d
0x1800f8148  mov     [rbp+40h+var_54], eax
0x1800f814b  call    bXformWorkhorse
0x1800f8150  test    eax, eax
0x1800f8152  jz      loc_1800F8504
0x1800f8158  mov     r10, [rbp+40h+var_80]
0x1800f815c  mov     edx, [rbp+40h+var_60]
0x1800f815f  cmp     edx, [rbp+40h+var_58]
0x1800f8162  mov     r8d, [rbp+40h+var_5C]
0x1800f8166  mov     ecx, [r10+8]
0x1800f816a  cmovg   edx, [rbp+40h+var_58]
0x1800f816e  cmp     r8d, [rbp+40h+var_54]
0x1800f8172  mov     eax, [rbp+40h+arg_80]
0x1800f8178  cmovg   r8d, [rbp+40h+var_54]
0x1800f817d  mov     r9d, [r10+4]; DestWidth
0x1800f8181  sub     r8d, [rbp+40h+arg_78]; yDest
0x1800f8188  sub     edx, [rbp+40h+arg_70]; xDest
0x1800f818e  mov     [rsp+140h+var_E0], 0CC0020h; rop
0x1800f8196  mov     [rsp+140h+iUsage], eax; iUsage
0x1800f819a  mov     rax, [rbp+40h+var_78]
0x1800f819e  mov     [rsp+140h+lpbmi], r10; lpbmi
0x1800f81a3  mov     qword ptr [rsp+140h+var_F8], rax; lpBits
0x1800f81a8  mov     [rsp+140h+SrcHeight], ecx; SrcHeight
0x1800f81ac  mov     [rsp+140h+SrcWidth], r9d; SrcWidth
0x1800f81b1  mov     [rsp+140h+ySrc], ebx; ySrc
0x1800f81b5  mov     [rsp+140h+rop], ebx; xSrc
0x1800f81b9  mov     dword ptr [rsp+140h+lpBits], ecx; DestHeight
0x1800f81bd  mov     rcx, rsi; hdc
0x1800f81c0  call    cs:__imp_StretchDIBits
0x1800f81c6  test    eax, eax
0x1800f81c8  jz      loc_1800F8504
0x1800f81ce  mov     rdx, [rbp+40h+lpxf]; lpxf
0x1800f81d2  mov     rcx, rsi; hdc
0x1800f81d5  call    cs:__imp_SetWorldTransform
0x1800f81db  test    eax, eax
0x1800f81dd  jz      loc_1800F8504
0x1800f81e3  mov     rcx, [rbp+40h+lpxf]; lpxf
0x1800f81e7  call    hdcMakeCompatibleDC
0x1800f81ec  mov     rbx, rax
0x1800f81ef  test    rax, rax
0x1800f81f2  jz      loc_1800F84FF
0x1800f81f8  mov     eax, [rbp+40h+ColorUse]
0x1800f81fb  lea     r8d, [r12+4]; flInit
0x1800f8200  mov     rdx, [rbp+40h+pbmi]; pbmih
0x1800f8204  mov     rcx, qword ptr [rbp+40h+var_A0]
0x1800f8208  mov     r9, [rbp+40h+pjBits]; pjBits
0x1800f820c  mov     [rsp+140h+rop], eax; iUsage
0x1800f8210  mov     [rsp+140h+lpBits], rdx; pbmi
0x1800f8215  mov     rcx, [rcx+28h]; hdc
0x1800f8219  call    cs:__imp_CreateDIBitmap
0x1800f821f  mov     r12, rax
0x1800f8222  test    rax, rax
0x1800f8225  jz      loc_1800F84F4
0x1800f822b  mov     rdx, rax; h
0x1800f822e  mov     rcx, rbx; hdc
0x1800f8231  call    cs:__imp_SelectObject
0x1800f8237  mov     [rbp+40h+h], rax
0x1800f823b  test    rax, rax
0x1800f823e  jz      loc_1800F84FA
0x1800f8244  mov     eax, [rbp+40h+cy]
0x1800f8247  mov     r9d, edi; cx
0x1800f824a  mov     [rsp+140h+SrcHeight], 8800C6h; rop
0x1800f8252  mov     r8d, r15d; y
0x1800f8255  mov     [rsp+140h+SrcWidth], r15d; y1
0x1800f825a  mov     edx, r14d; x
0x1800f825d  mov     [rsp+140h+ySrc], r14d; x1
0x1800f8262  mov     rcx, rbx; hdc
0x1800f8265  mov     qword ptr [rsp+140h+rop], rsi; hdcSrc
0x1800f826a  mov     dword ptr [rsp+140h+lpBits], eax; cy
0x1800f826e  call    cs:__imp_BitBlt
0x1800f8274  test    eax, eax
0x1800f8276  jz      loc_1800F84F4
0x1800f827c  mov     rcx, [rbp+40h+lpxf]
0x1800f8280  mov     r9d, edi; int
0x1800f8283  mov     eax, [rbp+40h+var_98]
0x1800f8286  mov     r8d, [rbp+40h+var_B8]; int
0x1800f828a  and     eax, 0CC0000h
0x1800f828f  mov     edx, [rbp+40h+var_B4]; int
0x1800f8292  or      eax, 220000h
0x1800f8297  mov     qword ptr [rsp+140h+var_E0], rcx; __int64
0x1800f829c  mov     ecx, [rbp+40h+cy]
0x1800f829f  mov     qword ptr [rsp+140h+iUsage], r12; hbm
0x1800f82a4  mov     [rsp+140h+lpbmi], rbx; hdc
0x1800f82a9  mov     [rsp+140h+var_F8], ecx; int
0x1800f82ad  mov     [rsp+140h+SrcHeight], edi; int
0x1800f82b1  mov     [rsp+140h+SrcWidth], r15d; int
0x1800f82b6  mov     [rsp+140h+ySrc], r14d; int
0x1800f82bb  mov     [rsp+140h+rop], eax; int
0x1800f82bf  mov     dword ptr [rsp+140h+lpBits], ecx; hDest
0x1800f82c3  mov     rcx, qword ptr [rbp+40h+var_A0]; int
0x1800f82c7  call    DoStretchBltAlt
0x1800f82cc  test    eax, eax
0x1800f82ce  jz      loc_1800F84F4
0x1800f82d4  mov     eax, [rbp+40h+cy]
0x1800f82d7  mov     r9d, edi; cx
0x1800f82da  mov     [rsp+140h+SrcHeight], 0BB0226h; rop
0x1800f82e2  mov     r8d, r15d; y
0x1800f82e5  mov     [rsp+140h+SrcWidth], r15d; y1
0x1800f82ea  mov     edx, r14d; x
0x1800f82ed  mov     [rsp+140h+ySrc], r14d; x1
0x1800f82f2  mov     rcx, rbx; hdc
0x1800f82f5  mov     qword ptr [rsp+140h+rop], rsi; hdcSrc
0x1800f82fa  mov     dword ptr [rsp+140h+lpBits], eax; cy
0x1800f82fe  call    cs:__imp_BitBlt
0x1800f8304  test    eax, eax
0x1800f8306  jz      loc_1800F84F4
0x1800f830c  mov     rax, [rbp+40h+lpxf]
0x1800f8310  mov     r9d, edi; int
0x1800f8313  mov     ecx, [rbp+40h+var_98]
0x1800f8316  mov     r8d, [rbp+40h+var_B8]; int
0x1800f831a  and     ecx, 330000h
0x1800f8320  mov     edx, [rbp+40h+var_B4]; int
0x1800f8323  or      ecx, 880000h
0x1800f8329  mov     qword ptr [rsp+140h+var_E0], rax; __int64
0x1800f832e  mov     eax, [rbp+40h+cy]
0x1800f8331  mov     qword ptr [rsp+140h+iUsage], r12; hbm
0x1800f8336  mov     [rsp+140h+lpbmi], rbx; hdc
0x1800f833b  mov     [rsp+140h+var_F8], eax; int
0x1800f833f  mov     [rsp+140h+SrcHeight], edi; int
0x1800f8343  mov     [rsp+140h+SrcWidth], r15d; int
0x1800f8348  mov     [rsp+140h+ySrc], r14d; int
0x1800f834d  mov     [rsp+140h+rop], ecx; int
0x1800f8351  mov     rcx, qword ptr [rbp+40h+var_A0]; int
0x1800f8355  mov     dword ptr [rsp+140h+lpBits], eax; hDest
0x1800f8359  call    DoStretchBltAlt
0x1800f835e  test    eax, eax
0x1800f8360  jz      loc_1800F84F4
0x1800f8366  mov     rdx, [rbp+40h+h]; h
0x1800f836a  mov     rcx, rbx; hdc
0x1800f836d  call    cs:__imp_SelectObject
0x1800f8373  test    rax, rax
0x1800f8376  jz      loc_1800F84F4
0x1800f837c  mov     eax, [rbp+40h+ColorUse]
0x1800f837f  xor     r8d, r8d; start
0x1800f8382  mov     rcx, [rbp+40h+pjBits]
0x1800f8386  mov     rdx, r12; hbm
0x1800f8389  mov     [rsp+140h+ySrc], eax; ColorUse
0x1800f838d  mov     rax, [rbp+40h+pbmi]
0x1800f8391  mov     qword ptr [rsp+140h+rop], rax; lpbmi
0x1800f8396  mov     [rsp+140h+lpBits], rcx; lpBits
0x1800f839b  mov     r9d, [rax+8]; cLines
0x1800f839f  mov     rax, qword ptr [rbp+40h+var_A0]
0x1800f83a3  mov     rcx, [rax+28h]; hdc
0x1800f83a7  call    cs:__imp_SetDIBits
0x1800f83ad  test    eax, eax
0x1800f83af  jz      loc_1800F84F4
0x1800f83b5  mov     rdx, r12; h
0x1800f83b8  mov     rcx, rbx; hdc
0x1800f83bb  call    cs:__imp_SelectObject
0x1800f83c1  test    rax, rax
0x1800f83c4  jz      loc_1800F84F4
0x1800f83ca  mov     eax, [rbp+40h+cy]
0x1800f83cd  mov     r9d, edi; cx
0x1800f83d0  mov     [rsp+140h+SrcHeight], 220326h; rop
0x1800f83d8  mov     r8d, r15d; y
0x1800f83db  mov     [rsp+140h+SrcWidth], r15d; y1
0x1800f83e0  mov     edx, r14d; x
0x1800f83e3  mov     [rsp+140h+ySrc], r14d; x1
0x1800f83e8  mov     rcx, rbx; hdc
0x1800f83eb  mov     qword ptr [rsp+140h+rop], rsi; hdcSrc
0x1800f83f0  mov     dword ptr [rsp+140h+lpBits], eax; cy
0x1800f83f4  call    cs:__imp_BitBlt
0x1800f83fa  test    eax, eax
0x1800f83fc  jz      loc_1800F84F4
0x1800f8402  mov     rcx, [rbp+40h+lpxf]
0x1800f8406  mov     r9d, edi; int
0x1800f8409  mov     r8d, [rbp+40h+var_B8]; int
0x1800f840d  mov     edx, [rbp+40h+var_B4]; int
0x1800f8410  mov     qword ptr [rsp+140h+var_E0], rcx; __int64
0x1800f8415  mov     ecx, [rbp+40h+cy]
0x1800f8418  mov     qword ptr [rsp+140h+iUsage], r12; hbm
  ... truncated ...
```
