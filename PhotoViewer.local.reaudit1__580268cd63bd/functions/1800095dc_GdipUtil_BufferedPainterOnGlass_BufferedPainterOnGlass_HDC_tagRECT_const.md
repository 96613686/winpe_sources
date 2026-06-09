# GdipUtil::BufferedPainterOnGlass::BufferedPainterOnGlass(HDC__ *,tagRECT const &)

- ea: `0x1800095dc`
- end: `0x180009863`
- name: `??0BufferedPainterOnGlass@GdipUtil@@QEAA@PEAUHDC__@@AEBUtagRECT@@@Z`
- size: `647`
- prototype: `__int64 __fastcall(GdipUtil::BufferedPainterOnGlass *__hidden this, HDC, const struct tagRECT *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180009588`

## callees

- `0x180001f30`
- `0x180001f6c`
- `0x1800095dc`
- `0x18000a160`
- `0x1800270f4`
- `0x180080010`

## import_xrefs

- `gdiplus!GdipGetImageGraphicsContext` at `0x1800097ee`
- `gdiplus!GdipGetImageGraphicsContext` at `0x1800097ee`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x180009740`
- `gdiplus!GdipCreateBitmapFromScan0` at `0x180009740`
- `gdiplus!GdipAlloc` at `0x1800096fa`
- `gdiplus!GdipAlloc` at `0x1800097cb`
- `gdiplus!GdipAlloc` at `0x1800096fa`
- `gdiplus!GdipAlloc` at `0x1800097cb`

## pseudocode

```c
GdipUtil::BufferedPainterOnGlass *__fastcall GdipUtil::BufferedPainterOnGlass::BufferedPainterOnGlass(
        GdipUtil::BufferedPainterOnGlass *this,
        HDC a2,
        const struct tagRECT *a3)
{
  __int128 v4; // xmm0
  int v5; // ebp
  int v6; // eax
  unsigned int v7; // r15d
  unsigned int v8; // ebp
  unsigned int i; // esi
  __int64 v10; // r14
  unsigned int Width; // ebx
  unsigned int Height; // eax
  int v13; // ebp
  void (__fastcall ***v14)(_QWORD, __int64); // rbx
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rbx
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // eax
  __int64 v23; // [rsp+60h] [rbp+8h] BYREF

  *((_QWORD *)this + 1) = a2;
  *(_QWORD *)this = &GdipUtil::BufferedPainterBase::`vftable';
  v4 = (__int128)*a3;
  *((_DWORD *)this + 8) = 0;
  *((_OWORD *)this + 1) = v4;
  *((_QWORD *)this + 5) = 0;
  v5 = *((_DWORD *)this + 6);
  *((_BYTE *)this + 48) = 0;
  if ( v5 <= *((_DWORD *)this + 4) || *((_DWORD *)this + 7) <= *((_DWORD *)this + 5) )
  {
    v6 = 2;
    *((_DWORD *)this + 8) = 2;
  }
  else
  {
    v6 = 0;
  }
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 16) = -1;
  *(_QWORD *)this = &GdipUtil::BufferedPainterOnGlass::`vftable';
  if ( v6 )
    return this;
  v7 = *((_DWORD *)this + 7) - *((_DWORD *)this + 5);
  v8 = v5 - *((_DWORD *)this + 4);
  if ( GdipUtilPrivate::g_theBitmapCache > 0 )
  {
    for ( i = 0; i < 0xA; ++i )
    {
      if ( v8 <= dword_18008DAE0[i] )
      {
        if ( byte_1800A3EF0[16 * i] )
          break;
        v8 = dword_18008DAE0[i];
        byte_1800A3EF0[16 * i] = 1;
        _mm_lfence();
        v10 = qword_1800A3EE8[2 * i];
        if ( v10 )
        {
          Width = Gdiplus::Image::GetWidth((Gdiplus::Image *)qword_1800A3EE8[2 * i]);
          Height = Gdiplus::Image::GetHeight((Gdiplus::Image *)v10);
          if ( v8 <= Width && v7 <= Height )
          {
            v13 = 0;
            goto LABEL_27;
          }
        }
        v14 = (void (__fastcall ***)(_QWORD, __int64))v10;
        goto LABEL_18;
      }
    }
  }
  i = -1;
  v14 = 0;
LABEL_18:
  v15 = GdipAlloc(24);
  v10 = v15;
  if ( v15 )
  {
    v23 = 0;
    *(_QWORD *)v15 = &Gdiplus::Image::`vftable';
    *(_DWORD *)(v15 + 16) = GdipCreateBitmapFromScan0(v8, v7, 0, 925707, 0, &v23);
    *(_QWORD *)(v10 + 8) = v23;
    v13 = *(_DWORD *)(v10 + 16);
    *(_DWORD *)(v10 + 16) = 0;
    if ( !v13 )
    {
      if ( (i & 0x80000000) == 0 )
      {
        if ( v14 )
          (**v14)(v14, 1);
        qword_1800A3EE8[2 * (int)i] = v10;
      }
      goto LABEL_27;
    }
    (**(void (__fastcall ***)(__int64, __int64))v10)(v10, 1);
  }
  else
  {
    v13 = 3;
  }
  i = -1;
  v10 = 0;
LABEL_27:
  *((_DWORD *)this + 16) = i;
  *((_QWORD *)this + 7) = v10;
  *((_DWORD *)this + 8) = v13;
  if ( !v13 )
  {
    v17 = GdipAlloc(16);
    if ( v17 )
    {
      v19 = 0;
      v23 = 0;
      if ( v10 )
      {
        *(_DWORD *)(v17 + 8) = GdipGetImageGraphicsContext(*(_QWORD *)(v10 + 8), &v23);
        v19 = v23;
      }
      *(_QWORD *)v17 = v19;
    }
    else
    {
      v17 = 0;
    }
    v20 = *((_QWORD *)this + 5);
    if ( v20 == v17 )
    {
      v17 = *((_QWORD *)this + 5);
    }
    else
    {
      if ( v20 )
        Gdiplus::Graphics::`scalar deleting destructor'(*((Gdiplus::Graphics **)this + 5), v16);
      *((_QWORD *)this + 5) = v17;
    }
    if ( v17 )
    {
      v21 = *(_DWORD *)(v17 + 8);
      *(_DWORD *)(v17 + 8) = 0;
      *((_DWORD *)this + 8) = v21;
      if ( !v21 )
        GdipUtil::BufferedPainterBase::TranslateGraphics(this, v16, v18);
    }
    else
    {
      *((_DWORD *)this + 8) = 3;
    }
  }
  return this;
}

```

## disassembly

```asm
0x1800095dc  mov     [rsp+arg_8], rbx
0x1800095e1  mov     [rsp+arg_10], rbp
0x1800095e6  push    rsi
0x1800095e7  push    rdi
0x1800095e8  push    r13
0x1800095ea  push    r14
0x1800095ec  push    r15
0x1800095ee  sub     rsp, 30h
0x1800095f2  mov     [rcx+8], rdx
0x1800095f6  lea     rax, ??_7BufferedPainterBase@GdipUtil@@6B@; const GdipUtil::BufferedPainterBase::`vftable'
0x1800095fd  mov     [rcx], rax
0x180009600  mov     rdi, rcx
0x180009603  movups  xmm0, xmmword ptr [r8]
0x180009607  mov     dword ptr [rcx+20h], 0
0x18000960e  movdqu  xmmword ptr [rcx+10h], xmm0
0x180009613  mov     qword ptr [rcx+28h], 0
0x18000961b  mov     ebp, [rcx+18h]
0x18000961e  mov     byte ptr [rcx+30h], 0
0x180009622  cmp     ebp, [rcx+10h]
0x180009625  jle     short loc_180009633
0x180009627  mov     eax, [rcx+14h]
0x18000962a  cmp     [rcx+1Ch], eax
0x18000962d  jle     short loc_180009633
0x18000962f  xor     eax, eax
0x180009631  jmp     short loc_18000963B
0x180009633  mov     eax, 2
0x180009638  mov     [rcx+20h], eax
0x18000963b  or      r13d, 0FFFFFFFFh
0x18000963f  mov     qword ptr [rcx+38h], 0
0x180009647  mov     [rcx+40h], r13d
0x18000964b  lea     r8, ??_7BufferedPainterOnGlass@GdipUtil@@6B@; const GdipUtil::BufferedPainterOnGlass::`vftable'
0x180009652  mov     [rcx], r8
0x180009655  test    eax, eax
0x180009657  jnz     loc_180009849
0x18000965d  mov     r15d, [rcx+1Ch]
0x180009661  lea     rdx, __ImageBase
0x180009668  sub     r15d, [rcx+14h]
0x18000966c  sub     ebp, [rcx+10h]
0x18000966f  cmp     cs:?g_theBitmapCache@GdipUtilPrivate@@3VBitmapCache@1@A, eax; GdipUtilPrivate::BitmapCache GdipUtilPrivate::g_theBitmapCache
0x180009675  jle     short loc_1800096F0
0x180009677  xor     esi, esi
0x180009679  cmp     esi, 0Ah
0x18000967c  jnb     short loc_1800096F0
0x18000967e  movsxd  rax, esi
0x180009681  cmp     ebp, ds:rva dword_18008DAE0[rdx+rax*4]
0x180009688  jbe     short loc_18000968E
0x18000968a  inc     esi
0x18000968c  jmp     short loc_180009679
0x18000968e  test    esi, esi
0x180009690  js      short loc_1800096F3
0x180009692  movsxd  rcx, esi
0x180009695  mov     rax, rcx
0x180009698  add     rax, rax
0x18000969b  cmp     rva byte_1800A3EF0[rdx+rax*8], 0
0x1800096a3  jnz     short loc_1800096F0
0x1800096a5  mov     ebp, ds:rva dword_18008DAE0[rdx+rcx*4]
0x1800096ac  mov     rva byte_1800A3EF0[rdx+rax*8], 1
0x1800096b4  lfence
0x1800096b7  mov     eax, esi
0x1800096b9  add     rax, rax
0x1800096bc  mov     r14, rva qword_1800A3EE8[rdx+rax*8]
0x1800096c4  test    r14, r14
0x1800096c7  jz      short loc_1800096EB
0x1800096c9  mov     rcx, r14; this
0x1800096cc  call    ?GetWidth@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetWidth(void)
0x1800096d1  mov     rcx, r14; this
0x1800096d4  mov     ebx, eax
0x1800096d6  call    ?GetHeight@Image@Gdiplus@@QEAAIXZ; Gdiplus::Image::GetHeight(void)
0x1800096db  cmp     ebp, ebx
0x1800096dd  ja      short loc_1800096EB
0x1800096df  cmp     r15d, eax
0x1800096e2  ja      short loc_1800096EB
0x1800096e4  xor     ebp, ebp
0x1800096e6  jmp     loc_1800097B6
0x1800096eb  mov     rbx, r14
0x1800096ee  jmp     short loc_1800096F5
0x1800096f0  mov     esi, r13d
0x1800096f3  xor     ebx, ebx
0x1800096f5  mov     ecx, 18h
0x1800096fa  call    cs:__imp_GdipAlloc
0x180009700  mov     r14, rax
0x180009703  test    rax, rax
0x180009706  jz      loc_1800097AB
0x18000970c  lea     rax, ??_7Image@Gdiplus@@6B@; const Gdiplus::Image::`vftable'
0x180009713  mov     [rsp+58h+arg_0], 0
0x18000971c  mov     [r14], rax
0x18000971f  mov     r9d, 0E200Bh
0x180009725  lea     rax, [rsp+58h+arg_0]
0x18000972a  xor     r8d, r8d
0x18000972d  mov     [rsp+58h+var_30], rax
0x180009732  mov     edx, r15d
0x180009735  mov     ecx, ebp
0x180009737  mov     [rsp+58h+var_38], 0
0x180009740  call    cs:__imp_GdipCreateBitmapFromScan0
0x180009746  mov     [r14+10h], eax
0x18000974a  mov     rax, [rsp+58h+arg_0]
0x18000974f  mov     [r14+8], rax
0x180009753  mov     ebp, [r14+10h]
0x180009757  mov     dword ptr [r14+10h], 0
0x18000975f  test    ebp, ebp
0x180009761  jz      short loc_180009778
0x180009763  mov     rax, [r14]
0x180009766  mov     edx, 1
0x18000976b  mov     rcx, r14
0x18000976e  mov     rax, [rax]
0x180009771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009776  jmp     short loc_1800097B0
0x180009778  test    esi, esi
0x18000977a  js      short loc_1800097B6
0x18000977c  test    rbx, rbx
0x18000977f  jz      short loc_180009794
0x180009781  mov     rax, [rbx]
0x180009784  mov     edx, 1
0x180009789  mov     rcx, rbx
0x18000978c  mov     rax, [rax]
0x18000978f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009794  movsxd  rax, esi
0x180009797  lea     rcx, __ImageBase
0x18000979e  add     rax, rax
0x1800097a1  mov     rva qword_1800A3EE8[rcx+rax*8], r14
0x1800097a9  jmp     short loc_1800097B6
0x1800097ab  mov     ebp, 3
0x1800097b0  mov     esi, r13d
0x1800097b3  xor     r14d, r14d
0x1800097b6  mov     [rdi+40h], esi
0x1800097b9  mov     [rdi+38h], r14
0x1800097bd  mov     [rdi+20h], ebp
0x1800097c0  test    ebp, ebp
0x1800097c2  jnz     loc_180009849
0x1800097c8  lea     ecx, [rbp+10h]
0x1800097cb  call    cs:__imp_GdipAlloc
0x1800097d1  mov     rbx, rax
0x1800097d4  test    rax, rax
0x1800097d7  jz      short loc_180009801
0x1800097d9  xor     eax, eax
0x1800097db  mov     [rsp+58h+arg_0], rax
0x1800097e0  test    r14, r14
0x1800097e3  jz      short loc_1800097FC
0x1800097e5  mov     rcx, [r14+8]
0x1800097e9  lea     rdx, [rsp+58h+arg_0]
0x1800097ee  call    cs:__imp_GdipGetImageGraphicsContext
0x1800097f4  mov     [rbx+8], eax
0x1800097f7  mov     rax, [rsp+58h+arg_0]
0x1800097fc  mov     [rbx], rax
0x1800097ff  jmp     short loc_180009803
0x180009801  xor     ebx, ebx
0x180009803  mov     rax, [rdi+28h]
0x180009807  cmp     rax, rbx
0x18000980a  jz      short loc_18000981F
0x18000980c  test    rax, rax
0x18000980f  jz      short loc_180009819
0x180009811  mov     rcx, rax; this
0x180009814  call    ??_GGraphics@Gdiplus@@QEAAPEAXI@Z; Gdiplus::Graphics::`scalar deleting destructor'(uint)
0x180009819  mov     [rdi+28h], rbx
0x18000981d  jmp     short loc_180009822
0x18000981f  mov     rbx, rax
0x180009822  test    rbx, rbx
0x180009825  jnz     short loc_180009830
0x180009827  mov     dword ptr [rdi+20h], 3
0x18000982e  jmp     short loc_180009849
0x180009830  mov     eax, [rbx+8]
0x180009833  mov     dword ptr [rbx+8], 0
0x18000983a  mov     [rdi+20h], eax
0x18000983d  test    eax, eax
0x18000983f  jnz     short loc_180009849
0x180009841  mov     rcx, rdi; this
0x180009844  call    ?TranslateGraphics@BufferedPainterBase@GdipUtil@@IEAAXXZ; GdipUtil::BufferedPainterBase::TranslateGraphics(void)
0x180009849  mov     rbx, [rsp+58h+arg_8]
0x18000984e  mov     rax, rdi
0x180009851  mov     rbp, [rsp+58h+arg_10]
0x180009856  add     rsp, 30h
0x18000985a  pop     r15
0x18000985c  pop     r14
0x18000985e  pop     r13
0x180009860  pop     rdi
0x180009861  pop     rsi
0x180009862  retn
```
