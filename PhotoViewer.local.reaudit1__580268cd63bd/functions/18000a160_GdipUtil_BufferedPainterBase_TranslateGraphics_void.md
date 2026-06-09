# GdipUtil::BufferedPainterBase::TranslateGraphics(void)

- ea: `0x18000a160`
- end: `0x18000a27e`
- name: `?TranslateGraphics@BufferedPainterBase@GdipUtil@@IEAAXXZ`
- size: `286`
- prototype: `void __fastcall(GdipUtil::BufferedPainterBase *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800095dc`
- `0x180009920`
- `0x180009ee0`

## callees

- `0x18000a160`
- `0x18002586c`

## import_xrefs

- `gdiplus!GdipTranslateWorldTransform` at `0x18000a1a1`
- `gdiplus!GdipTranslateWorldTransform` at `0x18000a1a1`
- `gdiplus!GdipSetRenderingOrigin` at `0x18000a1c7`
- `gdiplus!GdipSetRenderingOrigin` at `0x18000a1c7`
- `gdiplus!GdipSetClipHrgn` at `0x18000a25b`
- `gdiplus!GdipSetClipHrgn` at `0x18000a25b`
- `GDI32!GetClipRgn` at `0x18000a1f5`
- `GDI32!GetClipRgn` at `0x18000a1f5`
- `GDI32!OffsetRgn` at `0x18000a245`
- `GDI32!OffsetRgn` at `0x18000a245`
- `GDI32!CreateRectRgnIndirect` at `0x18000a1d7`
- `GDI32!CreateRectRgnIndirect` at `0x18000a1d7`
- `GDI32!DeleteObject` at `0x18000a26b`
- `GDI32!DeleteObject` at `0x18000a26b`
- `GDI32!GetLayout` at `0x18000a204`
- `GDI32!GetLayout` at `0x18000a204`

## pseudocode

```c
void __fastcall GdipUtil::BufferedPainterBase::TranslateGraphics(
        GdipUtil::BufferedPainterBase *this,
        __int64 a2,
        __int64 a3)
{
  _QWORD **v4; // rsi
  __int64 v5; // rdi
  const RECT *v6; // rbx
  int v7; // eax
  _QWORD *v8; // rdi
  _DWORD *v9; // r15
  int v10; // eax
  HRGN RectRgnIndirect; // rax
  HRGN v12; // rdi
  _QWORD *v13; // rbx
  int v14; // eax
  _BYTE v15[56]; // [rsp+20h] [rbp-38h] BYREF
  HRGN v16; // [rsp+60h] [rbp+8h] BYREF
  char *v17; // [rsp+68h] [rbp+10h]
  const RECT *v18; // [rsp+70h] [rbp+18h]
  char *v19; // [rsp+78h] [rbp+20h]

  v4 = (_QWORD **)((char *)this + 40);
  v17 = (char *)this + 40;
  v5 = *((_QWORD *)this + 5);
  v6 = (const RECT *)((char *)this + 16);
  v18 = (const RECT *)((char *)this + 16);
  v7 = GdipTranslateWorldTransform(*(_QWORD *)v5, a2, a3, 0);
  if ( v7 )
    *(_DWORD *)(v5 + 8) = v7;
  v8 = *v4;
  v9 = (_DWORD *)((char *)this + 20);
  v19 = (char *)this + 20;
  v10 = GdipSetRenderingOrigin(*v8, (unsigned int)-v6->left, (unsigned int)-*((_DWORD *)this + 5));
  if ( v10 )
    *((_DWORD *)v8 + 2) = v10;
  RectRgnIndirect = CreateRectRgnIndirect(v6);
  v12 = RectRgnIndirect;
  v16 = RectRgnIndirect;
  if ( RectRgnIndirect )
  {
    if ( GetClipRgn(*((HDC *)this + 1), RectRgnIndirect) != -1 )
    {
      if ( (GetLayout(*((HDC *)this + 1)) & 1) != 0 )
      {
        try
        {
          GdipUtil::BufferedPainterBase::MirrorRegion(*((HDC *)this + 1), &v16);
        }
        catch ( Base::Exception v15 )
        {
          if ( v16 )
          {
            DeleteObject(v16);
            v16 = 0;
          }
          Base::Exception::~Exception((Base::Exception *)v15);
          v4 = (_QWORD **)v17;
          v6 = v18;
          v9 = v19;
        }
        v12 = v16;
      }
      if ( v12 )
      {
        if ( OffsetRgn(v12, -v6->left, -*v9) )
        {
          v13 = *v4;
          v14 = GdipSetClipHrgn(**v4, v12, 0);
          if ( v14 )
            *((_DWORD *)v13 + 2) = v14;
        }
      }
    }
    DeleteObject(v12);
  }
}

```

## disassembly

```asm
0x18000a160  push    rbx
0x18000a162  push    rsi
0x18000a163  push    rdi
0x18000a164  push    r14
0x18000a166  push    r15
0x18000a168  sub     rsp, 30h
0x18000a16c  mov     r14, rcx
0x18000a16f  lea     rsi, [rcx+28h]
0x18000a173  mov     [rsp+58h+arg_8], rsi
0x18000a178  mov     rdi, [rsi]
0x18000a17b  lea     rbx, [rcx+10h]
0x18000a17f  mov     [rsp+58h+arg_10], rbx
0x18000a184  mov     eax, [rbx+4]
0x18000a187  neg     eax
0x18000a189  movd    xmm2, eax
0x18000a18d  cvtdq2ps xmm2, xmm2
0x18000a190  mov     eax, [rbx]
0x18000a192  neg     eax
0x18000a194  movd    xmm1, eax
0x18000a198  cvtdq2ps xmm1, xmm1
0x18000a19b  xor     r9d, r9d
0x18000a19e  mov     rcx, [rdi]
0x18000a1a1  call    cs:__imp_GdipTranslateWorldTransform
0x18000a1a7  test    eax, eax
0x18000a1a9  jz      short loc_18000A1AE
0x18000a1ab  mov     [rdi+8], eax
0x18000a1ae  mov     rdi, [rsi]
0x18000a1b1  lea     r15, [r14+14h]
0x18000a1b5  mov     [rsp+58h+arg_18], r15
0x18000a1ba  mov     r8d, [r15]
0x18000a1bd  neg     r8d
0x18000a1c0  mov     edx, [rbx]
0x18000a1c2  neg     edx
0x18000a1c4  mov     rcx, [rdi]
0x18000a1c7  call    cs:__imp_GdipSetRenderingOrigin
0x18000a1cd  test    eax, eax
0x18000a1cf  jz      short loc_18000A1D4
0x18000a1d1  mov     [rdi+8], eax
0x18000a1d4  mov     rcx, rbx; lprect
0x18000a1d7  call    cs:__imp_CreateRectRgnIndirect
0x18000a1dd  mov     rdi, rax
0x18000a1e0  mov     [rsp+58h+arg_0], rax
0x18000a1e5  test    rax, rax
0x18000a1e8  jz      loc_18000A272
0x18000a1ee  mov     rdx, rax; hrgn
0x18000a1f1  mov     rcx, [r14+8]; hdc
0x18000a1f5  call    cs:__imp_GetClipRgn
0x18000a1fb  cmp     eax, 0FFFFFFFFh
0x18000a1fe  jz      short loc_18000A268
0x18000a200  mov     rcx, [r14+8]; hdc
0x18000a204  call    cs:__imp_GetLayout
0x18000a20a  test    al, 1
0x18000a20c  jz      short loc_18000A233
0x18000a20e  lea     rdx, [rsp+58h+arg_0]; HRGN *
0x18000a213  mov     rcx, [r14+8]; HDC
0x18000a217  call    ?MirrorRegion@BufferedPainterBase@GdipUtil@@KAXPEAUHDC__@@PEAPEAUHRGN__@@@Z; GdipUtil::BufferedPainterBase::MirrorRegion(HDC__ *,HRGN__ * *)
0x18000a21c  nop
0x18000a21d  jmp     short loc_18000A22E
0x18000a21f  mov     rsi, [rsp+58h+arg_8]
0x18000a224  mov     rbx, [rsp+58h+arg_10]
0x18000a229  mov     r15, [rsp+58h+arg_18]
0x18000a22e  mov     rdi, [rsp+58h+arg_0]
0x18000a233  test    rdi, rdi
0x18000a236  jz      short loc_18000A268
0x18000a238  mov     r8d, [r15]
0x18000a23b  neg     r8d; y
0x18000a23e  mov     edx, [rbx]
0x18000a240  neg     edx; x
0x18000a242  mov     rcx, rdi; hrgn
0x18000a245  call    cs:__imp_OffsetRgn
0x18000a24b  test    eax, eax
0x18000a24d  jz      short loc_18000A268
0x18000a24f  mov     rbx, [rsi]
0x18000a252  xor     r8d, r8d
0x18000a255  mov     rdx, rdi
0x18000a258  mov     rcx, [rbx]
0x18000a25b  call    cs:__imp_GdipSetClipHrgn
0x18000a261  test    eax, eax
0x18000a263  jz      short loc_18000A268
0x18000a265  mov     [rbx+8], eax
0x18000a268  mov     rcx, rdi; ho
0x18000a26b  call    cs:__imp_DeleteObject
0x18000a271  nop
0x18000a272  add     rsp, 30h
0x18000a276  pop     r15
0x18000a278  pop     r14
0x18000a27a  pop     rdi
0x18000a27b  pop     rsi
0x18000a27c  pop     rbx
0x18000a27d  retn
```
