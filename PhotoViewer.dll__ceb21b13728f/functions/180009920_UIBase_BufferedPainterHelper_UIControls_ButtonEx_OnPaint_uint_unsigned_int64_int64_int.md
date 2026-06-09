# UIBase::BufferedPainterHelper<UIControls::ButtonEx>::OnPaint(uint,unsigned __int64,__int64,int &)

- ea: `0x180009920`
- end: `0x180009e8e`
- name: `?OnPaint@?$BufferedPainterHelper@VButtonEx@UIControls@@@UIBase@@QEAA_JI_K_JAEAH@Z`
- size: `1390`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x180008ac0`

## callees

- `0x180001800`
- `0x180001f30`
- `0x180001f6c`
- `0x1800035f8`
- `0x180009920`
- `0x180009e94`
- `0x180009ee0`
- `0x18000a160`
- `0x180026370`
- `0x18002a954`
- `0x18002abe0`
- `0x1800350f8`
- `0x18003f800`
- `0x180077e34`
- `0x180080010`

## import_xrefs

- `USER32!GetClientRect` at `0x180009974`
- `USER32!GetClientRect` at `0x180009974`
- `USER32!BeginPaint` at `0x1800099ba`
- `USER32!BeginPaint` at `0x180009d88`
- `USER32!BeginPaint` at `0x1800099ba`
- `USER32!BeginPaint` at `0x180009d88`
- `USER32!EndPaint` at `0x180009d65`
- `USER32!EndPaint` at `0x180009df2`
- `USER32!EndPaint` at `0x180009e41`
- `USER32!EndPaint` at `0x180009d65`
- `USER32!EndPaint` at `0x180009df2`
- `USER32!EndPaint` at `0x180009e41`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180009bfc`
- `gdiplus!GdipGetImageGraphicsContext` at `0x180009bfc`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x180009b4d`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x180009b4d`
- `gdiplus!GdipDeleteGraphics` at `0x180009c24`
- `gdiplus!GdipDeleteGraphics` at `0x180009cf5`
- `gdiplus!GdipDeleteGraphics` at `0x180009e2b`
- `gdiplus!GdipDeleteGraphics` at `0x180009c24`
- `gdiplus!GdipDeleteGraphics` at `0x180009cf5`
- `gdiplus!GdipDeleteGraphics` at `0x180009e2b`
- `gdiplus!GdipAlloc` at `0x180009b07`
- `gdiplus!GdipAlloc` at `0x180009bd7`
- `gdiplus!GdipAlloc` at `0x180009b07`
- `gdiplus!GdipAlloc` at `0x180009bd7`
- `gdiplus!GdipFree` at `0x180009c2d`
- `gdiplus!GdipFree` at `0x180009cfe`
- `gdiplus!GdipFree` at `0x180009c2d`
- `gdiplus!GdipFree` at `0x180009cfe`

## pseudocode

```c
__int64 __fastcall UIBase::BufferedPainterHelper<UIControls::ButtonEx>::OnPaint(_BYTE *a1)
{
  HWND *v2; // rdi
  unsigned int v3; // r14d
  bool v4; // al
  HWND v5; // rcx
  GdipUtilPrivate::BitmapCache *left; // rcx
  unsigned int v7; // r15d
  unsigned int v8; // esi
  int v9; // r13d
  Gdiplus::Image *v10; // r12
  unsigned int Width; // ebx
  unsigned int Height; // eax
  __int64 v13; // rax
  __int64 v14; // rbx
  int v15; // esi
  struct Gdiplus::Graphics *v16; // rbx
  __int64 v17; // rax
  struct Gdiplus::Graphics *v18; // rsi
  const struct tagRECT *v19; // r9
  struct Gdiplus::Graphics *v20; // rbx
  const struct tagRECT *v21; // r9
  const struct tagRECT *v22; // r9
  __int64 v24; // [rsp+30h] [rbp-188h] BYREF
  _BYTE v25[24]; // [rsp+38h] [rbp-180h] BYREF
  _QWORD v26[2]; // [rsp+50h] [rbp-168h] BYREF
  RECT rcPaint; // [rsp+60h] [rbp-158h]
  int v28; // [rsp+70h] [rbp-148h]
  struct Gdiplus::Graphics *v29; // [rsp+78h] [rbp-140h] BYREF
  char v30; // [rsp+80h] [rbp-138h]
  void (__fastcall ***v31)(_QWORD, __int64); // [rsp+88h] [rbp-130h]
  int v32; // [rsp+90h] [rbp-128h]
  HDC v33; // [rsp+98h] [rbp-120h]
  HWND hWnd; // [rsp+A0h] [rbp-118h]
  struct tagPAINTSTRUCT Paint; // [rsp+A8h] [rbp-110h] BYREF
  struct tagRECT Rect; // [rsp+100h] [rbp-B8h] BYREF
  _QWORD v37[2]; // [rsp+110h] [rbp-A8h] BYREF
  PAINTSTRUCT v38; // [rsp+120h] [rbp-98h] BYREF
  __int64 v39; // [rsp+170h] [rbp-48h] BYREF

  v2 = (HWND *)(a1 - 128);
  v3 = 0;
  if ( !a1 )
    v2 = 0;
  Rect = 0;
  GetClientRect(v2[1], &Rect);
  if ( a1[24] )
  {
    v4 = a1[16] && a1[17];
    v5 = v2[1];
    if ( v4 )
    {
      hWnd = v2[1];
      v33 = BeginPaint(v5, &Paint);
      v26[1] = Paint.hdc;
      left = (GdipUtilPrivate::BitmapCache *)(unsigned int)Paint.rcPaint.left;
      rcPaint = Paint.rcPaint;
      v28 = 0;
      v29 = 0;
      v30 = 0;
      if ( Paint.rcPaint.right <= Paint.rcPaint.left || Paint.rcPaint.bottom <= Paint.rcPaint.top )
      {
        v15 = 2;
      }
      else
      {
        v26[0] = &GdipUtil::BufferedPainterOnGlass::`vftable';
        v31 = 0;
        v32 = -1;
        v7 = Paint.rcPaint.bottom - Paint.rcPaint.top;
        v8 = Paint.rcPaint.right - Paint.rcPaint.left;
        v9 = -1;
        if ( GdipUtilPrivate::g_theBitmapCache > 0 )
        {
          while ( v3 < 0xA )
          {
            if ( v8 <= dword_18008DAE0[v3] )
            {
              if ( byte_1800A3EF0[16 * v3] )
                break;
              byte_1800A3EF0[16 * v3] = 1;
              v8 = dword_18008DAE0[v3];
              _mm_lfence();
              v10 = (Gdiplus::Image *)qword_1800A3EE8[2 * v3];
              if ( v10 )
              {
                Width = Gdiplus::Image::GetWidth((Gdiplus::Image *)qword_1800A3EE8[2 * v3]);
                Height = Gdiplus::Image::GetHeight(v10);
                if ( v8 <= Width && v7 <= Height )
                {
                  v32 = v3;
                  v31 = (void (__fastcall ***)(_QWORD, __int64))v10;
                  v28 = 0;
                  goto LABEL_30;
                }
              }
              v9 = v3;
              goto LABEL_22;
            }
            ++v3;
          }
        }
        v3 = -1;
        v10 = 0;
LABEL_22:
        v13 = GdipAlloc(24);
        v14 = v13;
        if ( v13 )
        {
          *(_QWORD *)v13 = &Gdiplus::Image::`vftable';
          v24 = 0;
          *(_DWORD *)(v13 + 16) = GdipCreateBitmapFromScan0(v8, v7, 0, 925707, 0, &v24);
          *(_QWORD *)(v14 + 8) = v24;
          v15 = *(_DWORD *)(v14 + 16);
          *(_DWORD *)(v14 + 16) = 0;
          if ( !v15 )
          {
            if ( v9 >= 0 )
            {
              if ( v10 )
                (**(void (__fastcall ***)(Gdiplus::Image *, __int64))v10)(v10, 1);
              qword_1800A3EE8[2 * v9] = v14;
            }
            v10 = (Gdiplus::Image *)v14;
            v32 = v3;
            v31 = (void (__fastcall ***)(_QWORD, __int64))v14;
            v28 = 0;
LABEL_30:
            v16 = (struct Gdiplus::Graphics *)GdipAlloc(16);
            if ( v16 )
            {
              v17 = 0;
              v24 = 0;
              if ( v10 )
              {
                *((_DWORD *)v16 + 2) = GdipGetImageGraphicsContext(*((_QWORD *)v10 + 1), &v24);
                v17 = v24;
              }
              *(_QWORD *)v16 = v17;
            }
            else
            {
              v16 = 0;
            }
            v18 = v29;
            if ( v29 == v16 )
            {
              v16 = v29;
            }
            else
            {
              if ( v29 )
              {
                GdipDeleteGraphics(*(_QWORD *)v29);
                GdipFree(v18);
              }
              v29 = v16;
            }
            if ( !v16 )
            {
              v28 = 3;
LABEL_49:
              v26[0] = &GdipUtil::BufferedPainterOnGlass::`vftable';
              if ( !v30 )
                GdipUtil::BufferedPainterOnGlass::RenderToScreen((GdipUtil::BufferedPainterOnGlass *)v26);
              v20 = v29;
              if ( v29 )
              {
                GdipDeleteGraphics(*(_QWORD *)v29);
                GdipFree(v20);
                v29 = 0;
              }
              if ( v31 )
              {
                if ( v32 < 0 )
                  (**v31)(v31, 1);
                else
                  GdipUtilPrivate::BitmapCache::ReleaseCacheBitmap(left, v32);
                v31 = 0;
              }
              Base::Ptr<Gdiplus::Graphics>::Release(&v29);
              EndPaint(hWnd, &Paint);
              return 0;
            }
            v15 = *((_DWORD *)v16 + 2);
            *((_DWORD *)v16 + 2) = 0;
            v28 = v15;
            if ( !v15 )
            {
              GdipUtil::BufferedPainterBase::TranslateGraphics((GdipUtil::BufferedPainterBase *)v26);
              v15 = v28;
            }
LABEL_47:
            v26[0] = &GdipUtil::BufferedPainterOnGlass::`vftable';
            if ( !v15 )
            {
              GdipUtil::BufferedPainterOnGlass::Clear((GdipUtil::BufferedPainterOnGlass *)v26);
              UIControls::ButtonEx::PaintClient((UIControls::ButtonEx *)v2, v29, &Rect, v19);
            }
            goto LABEL_49;
          }
          (**(void (__fastcall ***)(__int64, __int64))v14)(v14, 1);
        }
        else
        {
          v15 = 3;
        }
      }
      v32 = -1;
      v31 = 0;
      v28 = v15;
      goto LABEL_47;
    }
    Paint.hdc = (HDC)v2[1];
    hWnd = (HWND)BeginPaint(v5, (LPPAINTSTRUCT)&Paint.fErase);
    GdipUtil::BufferedPainter::BufferedPainter(
      (GdipUtil::BufferedPainter *)v26,
      *(HDC *)&Paint.fErase,
      (const struct tagRECT *)&Paint.rcPaint.right);
    v26[0] = &GdipUtil::WmPaintBufferedPainter<GdipUtil::BufferedPainter>::`vftable';
    if ( !v28 )
      UIControls::ButtonEx::PaintClient((UIControls::ButtonEx *)v2, v29, &Rect, v21);
    GdipUtil::BufferedPainter::~BufferedPainter((GdipUtil::BufferedPainter *)v26);
    EndPaint((HWND)Paint.hdc, (const PAINTSTRUCT *)&Paint.fErase);
  }
  else
  {
    try
    {
      GdipUtil::WmPaintGraphics::WmPaintGraphics((GdipUtil::WmPaintGraphics *)v37, v2[1]);
      UIControls::ButtonEx::PaintClient((UIControls::ButtonEx *)v2, (struct Gdiplus::Graphics *)&v39, &Rect, v22);
      GdipDeleteGraphics(v39);
      EndPaint((HWND)v37[1], &v38);
      v37[0] = 0;
      WTL::CDCT<1>::~CDCT<1>(v37);
    }
    catch ( Base::Exception v25 )
    {
      Base::Exception::~Exception((Base::Exception *)v25);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180009920  mov     [rsp+arg_8], rbx
0x180009925  mov     [rsp+arg_10], rsi
0x18000992a  push    rdi
0x18000992b  push    r12
0x18000992d  push    r13
0x18000992f  push    r14
0x180009931  push    r15
0x180009933  sub     rsp, 190h
0x18000993a  mov     rax, cs:__security_cookie
0x180009941  xor     rax, rsp
0x180009944  mov     [rsp+1B8h+var_38], rax
0x18000994c  mov     rbx, rcx
0x18000994f  lea     rdi, [rcx-80h]
0x180009953  xor     r14d, r14d
0x180009956  test    rcx, rcx
0x180009959  cmovz   rdi, r14
0x18000995d  xorps   xmm0, xmm0
0x180009960  movups  xmmword ptr [rsp+1B8h+Rect.left], xmm0
0x180009968  lea     rdx, [rsp+1B8h+Rect]; lpRect
0x180009970  mov     rcx, [rdi+8]; hWnd
0x180009974  call    cs:__imp_GetClientRect
0x18000997a  cmp     [rbx+18h], r14b
0x18000997e  jz      loc_180009DFA
0x180009984  cmp     [rbx+10h], r14b
0x180009988  jz      short loc_180009994
0x18000998a  cmp     [rbx+11h], r14b
0x18000998e  jz      short loc_180009994
0x180009990  mov     al, 1
0x180009992  jmp     short loc_180009996
0x180009994  xor     al, al
0x180009996  mov     rcx, [rdi+8]; hWnd
0x18000999a  test    al, al
0x18000999c  jz      loc_180009D70
0x1800099a2  mov     [rsp+1B8h+var_120], r14
0x1800099aa  mov     [rsp+1B8h+hWnd], rcx
0x1800099b2  lea     rdx, [rsp+1B8h+Paint]; lpPaint
0x1800099ba  call    cs:__imp_BeginPaint
0x1800099c0  mov     [rsp+1B8h+var_120], rax
0x1800099c8  mov     rax, [rsp+1B8h+Paint.hdc]
0x1800099d0  mov     [rsp+1B8h+var_160], rax
0x1800099d5  mov     ecx, [rsp+1B8h+Paint.rcPaint.left]
0x1800099dc  mov     dword ptr [rsp+1B8h+var_158], ecx
0x1800099e0  mov     eax, [rsp+1B8h+Paint.rcPaint.top]
0x1800099e7  mov     dword ptr [rsp+1B8h+var_158+4], eax
0x1800099eb  mov     esi, [rsp+1B8h+Paint.rcPaint.right]
0x1800099f2  mov     dword ptr [rsp+1B8h+var_150], esi
0x1800099f6  mov     r15d, [rsp+1B8h+Paint.rcPaint.bottom]
0x1800099fe  mov     dword ptr [rsp+1B8h+var_150+4], r15d
0x180009a03  mov     [rsp+1B8h+var_148], r14d
0x180009a08  mov     [rsp+1B8h+var_140], r14
0x180009a0d  mov     [rsp+1B8h+var_138], r14b
0x180009a15  cmp     esi, ecx
0x180009a17  jle     loc_180009C7D
0x180009a1d  cmp     r15d, eax
0x180009a20  jle     loc_180009C7D
0x180009a26  lea     rdx, ??_7BufferedPainterOnGlass@GdipUtil@@6B@; const GdipUtil::BufferedPainterOnGlass::`vftable'
0x180009a2d  mov     [rsp+1B8h+var_168], rdx
0x180009a32  mov     [rsp+1B8h+var_130], r14
0x180009a3a  mov     [rsp+1B8h+var_128], 0FFFFFFFFh
0x180009a45  sub     r15d, eax
0x180009a48  sub     esi, ecx
0x180009a4a  mov     r13d, 0FFFFFFFFh
0x180009a50  cmp     cs:?g_theBitmapCache@GdipUtilPrivate@@3VBitmapCache@1@A, r14d; GdipUtilPrivate::BitmapCache GdipUtilPrivate::g_theBitmapCache
0x180009a57  jle     loc_180009AFC
0x180009a5d  lea     rcx, __ImageBase
0x180009a64  cmp     r14d, 0Ah
0x180009a68  jnb     loc_180009AFC
0x180009a6e  movsxd  rax, r14d
0x180009a71  cmp     esi, ds:rva dword_18008DAE0[rcx+rax*4]
0x180009a78  jbe     short loc_180009A7F
0x180009a7a  inc     r14d
0x180009a7d  jmp     short loc_180009A64
0x180009a7f  test    r14d, r14d
0x180009a82  js      short loc_180009AF9
0x180009a84  movsxd  rdx, r14d
0x180009a87  mov     rax, rdx
0x180009a8a  add     rax, rax
0x180009a8d  cmp     rva byte_1800A3EF0[rcx+rax*8], 0
0x180009a95  jnz     short loc_180009AFC
0x180009a97  mov     rva byte_1800A3EF0[rcx+rax*8], 1
0x180009a9f  mov     esi, ds:rva dword_18008DAE0[rcx+rdx*4]
0x180009aa6  lfence
0x180009aa9  mov     eax, r14d
0x180009aac  add     rax, rax
0x180009aaf  mov     r12, rva qword_1800A3EE8[rcx+rax*8]
0x180009ab7  test    r12, r12
0x180009aba  jz      short loc_180009AF4
0x180009abc  mov     rcx, r12; this
0x180009abf  call    ?GetWidth@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetWidth(void)
0x180009ac4  mov     ebx, eax
0x180009ac6  mov     rcx, r12; this
0x180009ac9  call    ?GetHeight@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetHeight(void)
0x180009ace  cmp     esi, ebx
0x180009ad0  ja      short loc_180009AF4
0x180009ad2  cmp     r15d, eax
0x180009ad5  ja      short loc_180009AF4
0x180009ad7  mov     [rsp+1B8h+var_128], r14d
0x180009adf  mov     [rsp+1B8h+var_130], r12
0x180009ae7  xor     r14d, r14d
0x180009aea  mov     [rsp+1B8h+var_148], r14d
0x180009aef  jmp     loc_180009BD2
0x180009af4  mov     r13d, r14d
0x180009af7  jmp     short loc_180009B02
0x180009af9  mov     r13d, r14d
0x180009afc  mov     r14d, r13d
0x180009aff  xor     r12d, r12d
0x180009b02  mov     ecx, 18h
0x180009b07  call    cs:__imp_GdipAlloc
0x180009b0d  mov     rbx, rax
0x180009b10  test    rax, rax
0x180009b13  jz      loc_180009C73
0x180009b19  lea     rax, ??_7Image@Gdiplus@@6B@; const Gdiplus::Image::`vftable'
0x180009b20  mov     [rbx], rax
0x180009b23  mov     [rsp+1B8h+var_188], 0
0x180009b2c  lea     rax, [rsp+1B8h+var_188]
0x180009b31  mov     [rsp+1B8h+var_190], rax
0x180009b36  mov     [rsp+1B8h+var_198], 0
0x180009b3f  mov     r9d, 0E200Bh
0x180009b45  xor     r8d, r8d
0x180009b48  mov     edx, r15d
0x180009b4b  mov     ecx, esi
0x180009b4d  call    cs:__imp_GdipCreateBitmapFromScan0
0x180009b53  mov     [rbx+10h], eax
0x180009b56  mov     rax, [rsp+1B8h+var_188]
0x180009b5b  mov     [rbx+8], rax
0x180009b5f  mov     esi, [rbx+10h]
0x180009b62  mov     dword ptr [rbx+10h], 0
0x180009b69  test    esi, esi
0x180009b6b  jz      short loc_180009B85
0x180009b6d  mov     rax, [rbx]
0x180009b70  mov     edx, 1
0x180009b75  mov     rcx, rbx
0x180009b78  mov     rax, [rax]
0x180009b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b80  jmp     loc_180009C78
0x180009b85  test    r13d, r13d
0x180009b88  js      short loc_180009BB8
0x180009b8a  test    r12, r12
0x180009b8d  jz      short loc_180009BA3
0x180009b8f  mov     rax, [r12]
0x180009b93  mov     edx, 1
0x180009b98  mov     rcx, r12
0x180009b9b  mov     rax, [rax]
0x180009b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ba3  movsxd  rax, r13d
0x180009ba6  add     rax, rax
0x180009ba9  lea     rcx, __ImageBase
0x180009bb0  mov     rva qword_1800A3EE8[rcx+rax*8], rbx
0x180009bb8  mov     r12, rbx
0x180009bbb  mov     [rsp+1B8h+var_128], r14d
0x180009bc3  mov     [rsp+1B8h+var_130], rbx
0x180009bcb  mov     [rsp+1B8h+var_148], esi
0x180009bcf  xor     r14d, r14d
0x180009bd2  mov     ecx, 10h
0x180009bd7  call    cs:__imp_GdipAlloc
0x180009bdd  mov     rbx, rax
0x180009be0  test    rax, rax
0x180009be3  jz      short loc_180009C0F
0x180009be5  mov     rax, r14
0x180009be8  mov     [rsp+1B8h+var_188], rax
0x180009bed  test    r12, r12
0x180009bf0  jz      short loc_180009C0A
0x180009bf2  lea     rdx, [rsp+1B8h+var_188]
0x180009bf7  mov     rcx, [r12+8]
0x180009bfc  call    cs:__imp_GdipGetImageGraphicsContext
0x180009c02  mov     [rbx+8], eax
0x180009c05  mov     rax, [rsp+1B8h+var_188]
0x180009c0a  mov     [rbx], rax
0x180009c0d  jmp     short loc_180009C12
0x180009c0f  mov     rbx, r14
0x180009c12  mov     rsi, [rsp+1B8h+var_140]
0x180009c17  cmp     rsi, rbx
0x180009c1a  jz      short loc_180009C3A
0x180009c1c  test    rsi, rsi
0x180009c1f  jz      short loc_180009C33
0x180009c21  mov     rcx, [rsi]
0x180009c24  call    cs:__imp_GdipDeleteGraphics
0x180009c2a  mov     rcx, rsi
0x180009c2d  call    cs:__imp_GdipFree
0x180009c33  mov     [rsp+1B8h+var_140], rbx
0x180009c38  jmp     short loc_180009C3D
0x180009c3a  mov     rbx, rsi
0x180009c3d  test    rbx, rbx
0x180009c40  jnz     short loc_180009C54
0x180009c42  mov     esi, 3
0x180009c47  mov     [rsp+1B8h+var_148], esi
0x180009c4b  lea     rbx, ??_7BufferedPainterOnGlass@GdipUtil@@6B@; const GdipUtil::BufferedPainterOnGlass::`vftable'
0x180009c52  jmp     short loc_180009CCF
0x180009c54  mov     esi, [rbx+8]
0x180009c57  mov     [rbx+8], r14d
0x180009c5b  mov     [rsp+1B8h+var_148], esi
0x180009c5f  test    esi, esi
0x180009c61  jnz     short loc_180009C99
0x180009c63  lea     rcx, [rsp+1B8h+var_168]; this
0x180009c68  call    ?TranslateGraphics@BufferedPainterBase@GdipUtil@@IEAAXXZ; GdipUtil::BufferedPainterBase::TranslateGraphics(void)
0x180009c6d  mov     esi, [rsp+1B8h+var_148]
0x180009c71  jmp     short loc_180009C99
0x180009c73  mov     esi, 3
0x180009c78  xor     r14d, r14d
0x180009c7b  jmp     short loc_180009C82
0x180009c7d  mov     esi, 2
0x180009c82  mov     [rsp+1B8h+var_128], 0FFFFFFFFh
0x180009c8d  mov     [rsp+1B8h+var_130], r14
0x180009c95  mov     [rsp+1B8h+var_148], esi
0x180009c99  lea     rbx, ??_7BufferedPainterOnGlass@GdipUtil@@6B@; const GdipUtil::BufferedPainterOnGlass::`vftable'
0x180009ca0  lea     rax, ??_7BufferedPainterOnGlass@GdipUtil@@6B@; const GdipUtil::BufferedPainterOnGlass::`vftable'
0x180009ca7  mov     [rsp+1B8h+var_168], rax
0x180009cac  test    esi, esi
0x180009cae  jnz     short loc_180009CCF
0x180009cb0  lea     rcx, [rsp+1B8h+var_168]; this
0x180009cb5  call    ?Clear@BufferedPainterOnGlass@GdipUtil@@QEAAXXZ; GdipUtil::BufferedPainterOnGlass::Clear(void)
0x180009cba  lea     r8, [rsp+1B8h+Rect]; struct tagRECT *
0x180009cc2  mov     rdx, [rsp+1B8h+var_140]; struct Gdiplus::Graphics *
0x180009cc7  mov     rcx, rdi; this
0x180009cca  call    ?PaintClient@ButtonEx@UIControls@@QEAAXPEAVGraphics@Gdiplus@@AEBUtagRECT@@1@Z; UIControls::ButtonEx::PaintClient(Gdiplus::Graphics *,tagRECT const &,tagRECT const &)
0x180009ccf  mov     [rsp+1B8h+var_168], rbx
0x180009cd4  cmp     [rsp+1B8h+var_138], 0
0x180009cdc  jnz     short loc_180009CE8
0x180009cde  lea     rcx, [rsp+1B8h+var_168]; this
0x180009ce3  call    ?RenderToScreen@BufferedPainterOnGlass@GdipUtil@@UEAAXXZ; GdipUtil::BufferedPainterOnGlass::RenderToScreen(void)
0x180009ce8  mov     rbx, [rsp+1B8h+var_140]
0x180009ced  test    rbx, rbx
0x180009cf0  jz      short loc_180009D09
0x180009cf2  mov     rcx, [rbx]
0x180009cf5  call    cs:__imp_GdipDeleteGraphics
0x180009cfb  mov     rcx, rbx
0x180009cfe  call    cs:__imp_GdipFree
0x180009d04  mov     [rsp+1B8h+var_140], r14
0x180009d09  cmp     [rsp+1B8h+var_130], 0
0x180009d12  jz      short loc_180009D4B
0x180009d14  mov     edx, [rsp+1B8h+var_128]; int
0x180009d1b  test    edx, edx
0x180009d1d  js      short loc_180009D26
0x180009d1f  call    ?ReleaseCacheBitmap@BitmapCache@GdipUtilPrivate@@QEAAXH@Z; GdipUtilPrivate::BitmapCache::ReleaseCacheBitmap(int)
0x180009d24  jmp     short loc_180009D43
0x180009d26  mov     rcx, [rsp+1B8h+var_130]
0x180009d2e  test    rcx, rcx
0x180009d31  jz      short loc_180009D43
0x180009d33  mov     rax, [rcx]
0x180009d36  mov     edx, 1
0x180009d3b  mov     rax, [rax]
0x180009d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d43  mov     [rsp+1B8h+var_130], r14
0x180009d4b  lea     rcx, [rsp+1B8h+var_140]
0x180009d50  call    ?Release@?$Ptr@VGraphics@Gdiplus@@@Base@@QEAAXXZ; Base::Ptr<Gdiplus::Graphics>::Release(void)
0x180009d55  lea     rdx, [rsp+1B8h+Paint]; lpPaint
0x180009d5d  mov     rcx, [rsp+1B8h+hWnd]; hWnd
0x180009d65  call    cs:__imp_EndPaint
0x180009d6b  jmp     loc_180009E5D
0x180009d70  mov     [rsp+1B8h+hWnd], r14
0x180009d78  mov     [rsp+1B8h+Paint.hdc], rcx
0x180009d80  lea     rdx, [rsp+1B8h+Paint.fErase]; lpPaint
0x180009d88  call    cs:__imp_BeginPaint
0x180009d8e  mov     [rsp+1B8h+hWnd], rax
0x180009d96  lea     r8, [rsp+1B8h+Paint.rcPaint.right]; struct tagRECT *
0x180009d9e  mov     rdx, qword ptr [rsp+1B8h+Paint.fErase]; HDC
0x180009da6  lea     rcx, [rsp+1B8h+var_168]; this
0x180009dab  call    ??0BufferedPainter@GdipUtil@@QEAA@PEAUHDC__@@AEBUtagRECT@@@Z; GdipUtil::BufferedPainter::BufferedPainter(HDC__ *,tagRECT const &)
0x180009db0  lea     rax, ??_7?$WmPaintBufferedPainter@VBufferedPainter@GdipUtil@@@GdipUtil@@6B@; const GdipUtil::WmPaintBufferedPainter<GdipUtil::BufferedPainter>::`vftable'
0x180009db7  mov     [rsp+1B8h+var_168], rax
0x180009dbc  cmp     [rsp+1B8h+var_148], r14d
0x180009dc1  jnz     short loc_180009DD8
0x180009dc3  lea     r8, [rsp+1B8h+Rect]; struct tagRECT *
0x180009dcb  mov     rdx, [rsp+1B8h+var_140]; struct Gdiplus::Graphics *
0x180009dd0  mov     rcx, rdi; this
0x180009dd3  call    ?PaintClient@ButtonEx@UIControls@@QEAAXPEAVGraphics@Gdiplus@@AEBUtagRECT@@1@Z; UIControls::ButtonEx::PaintClient(Gdiplus::Graphics *,tagRECT const &,tagRECT const &)
0x180009dd8  lea     rcx, [rsp+1B8h+var_168]; this
0x180009ddd  call    ??1BufferedPainter@GdipUtil@@QEAA@XZ; GdipUtil::BufferedPainter::~BufferedPainter(void)
0x180009de2  lea     rdx, [rsp+1B8h+Paint.fErase]; lpPaint
0x180009dea  mov     rcx, [rsp+1B8h+Paint.hdc]; hWnd
0x180009df2  call    cs:__imp_EndPaint
0x180009df8  jmp     short loc_180009E5D
0x180009dfa  mov     rdx, [rdi+8]; HWND
0x180009dfe  lea     rcx, [rsp+1B8h+var_A8]; this
0x180009e06  call    ??0WmPaintGraphics@GdipUtil@@QEAA@PEAUHWND__@@@Z; GdipUtil::WmPaintGraphics::WmPaintGraphics(HWND__ *)
0x180009e0b  lea     r8, [rsp+1B8h+Rect]; struct tagRECT *
0x180009e13  lea     rdx, [rsp+1B8h+var_48]; struct Gdiplus::Graphics *
0x180009e1b  mov     rcx, rdi; this
0x180009e1e  call    ?PaintClient@ButtonEx@UIControls@@QEAAXPEAVGraphics@Gdiplus@@AEBUtagRECT@@1@Z; UIControls::ButtonEx::PaintClient(Gdiplus::Graphics *,tagRECT const &,tagRECT const &)
0x180009e23  mov     rcx, [rsp+1B8h+var_48]
0x180009e2b  call    cs:__imp_GdipDeleteGraphics
0x180009e31  lea     rdx, [rsp+1B8h+var_98]; lpPaint
0x180009e39  mov     rcx, [rsp+1B8h+var_A0]; hWnd
0x180009e41  call    cs:__imp_EndPaint
0x180009e47  mov     [rsp+1B8h+var_A8], r14
0x180009e4f  lea     rcx, [rsp+1B8h+var_A8]
0x180009e57  call    ??1?$CDCT@$00@WTL@@QEAA@XZ; WTL::CDCT<1>::~CDCT<1>(void)
0x180009e5c  nop
0x180009e5d  jmp     short $+2
0x180009e5f  xor     eax, eax
0x180009e61  mov     rcx, [rsp+1B8h+var_38]
0x180009e69  xor     rcx, rsp; StackCookie
0x180009e6c  call    __security_check_cookie
0x180009e71  lea     r11, [rsp+1B8h+var_28]
0x180009e79  mov     rbx, [r11+38h]
0x180009e7d  mov     rsi, [r11+40h]
0x180009e81  mov     rsp, r11
0x180009e84  pop     r15
0x180009e86  pop     r14
0x180009e88  pop     r13
  ... truncated ...
```
