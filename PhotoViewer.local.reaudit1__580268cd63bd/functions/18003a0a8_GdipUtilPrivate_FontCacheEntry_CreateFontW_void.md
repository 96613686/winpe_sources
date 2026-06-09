# GdipUtilPrivate::FontCacheEntry::CreateFontW(void)

- ea: `0x18003a0a8`
- end: `0x18003a2bf`
- name: `?CreateFontW@FontCacheEntry@GdipUtilPrivate@@AEAA_NXZ`
- size: `535`
- prototype: `bool __fastcall(GdipUtilPrivate::FontCacheEntry *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x180006144`
- `0x180025248`
- `0x18003496c`
- `0x180076cb0`

## callees

- `0x18003a0a8`
- `0x18003f800`
- `0x180077e98`
- `0x180077fb8`
- `0x180077fec`
- `0x180078020`
- `0x1800780ec`

## import_xrefs

- `USER32!GetDC` at `0x18003a101`
- `USER32!GetDC` at `0x18003a101`
- `USER32!ReleaseDC` at `0x18003a18d`
- `USER32!ReleaseDC` at `0x18003a1cc`
- `USER32!ReleaseDC` at `0x18003a224`
- `USER32!ReleaseDC` at `0x18003a27a`
- `USER32!ReleaseDC` at `0x18003a294`
- `USER32!ReleaseDC` at `0x18003a18d`
- `USER32!ReleaseDC` at `0x18003a1cc`
- `USER32!ReleaseDC` at `0x18003a224`
- `USER32!ReleaseDC` at `0x18003a27a`
- `USER32!ReleaseDC` at `0x18003a294`
- `gdiplus!GdipDeleteFontFamily` at `0x18003a17d`
- `gdiplus!GdipDeleteFontFamily` at `0x18003a1bc`
- `gdiplus!GdipDeleteFontFamily` at `0x18003a214`
- `gdiplus!GdipDeleteFontFamily` at `0x18003a26a`
- `gdiplus!GdipDeleteFontFamily` at `0x18003a284`
- `gdiplus!GdipDeleteFontFamily` at `0x18003a17d`
- `gdiplus!GdipDeleteFontFamily` at `0x18003a1bc`
- `gdiplus!GdipDeleteFontFamily` at `0x18003a214`
- `gdiplus!GdipDeleteFontFamily` at `0x18003a26a`
- `gdiplus!GdipDeleteFontFamily` at `0x18003a284`
- `gdiplus!GdipAlloc` at `0x18003a1e0`
- `gdiplus!GdipAlloc` at `0x18003a231`
- `gdiplus!GdipAlloc` at `0x18003a1e0`
- `gdiplus!GdipAlloc` at `0x18003a231`
- `GDI32!GetDeviceCaps` at `0x18003a124`
- `GDI32!GetDeviceCaps` at `0x18003a124`

## pseudocode

```c
char __fastcall GdipUtilPrivate::FontCacheEntry::CreateFontW(GdipUtilPrivate::FontCacheEntry *this)
{
  __int64 v2; // rbx
  __int16 v3; // r14
  HDC DC; // rax
  HDC v5; // rdi
  int *v6; // rcx
  int v7; // edx
  float v8; // xmm6_4
  int DeviceCaps; // eax
  const struct Gdiplus::FontCollection *v10; // r8
  __int64 v11; // rdx
  int v13; // ebx
  const struct Gdiplus::FontFamily *v14; // rax
  struct Gdiplus::Font *v15; // rax
  struct Gdiplus::Font *v16; // rax
  _QWORD v17[2]; // [rsp+30h] [rbp-68h] BYREF
  struct Gdiplus::Font *v18; // [rsp+40h] [rbp-58h]
  __int64 v19; // [rsp+48h] [rbp-50h] BYREF
  int v20; // [rsp+50h] [rbp-48h]
  wchar_t v21; // [rsp+54h] [rbp-44h]

  v19 = *(_QWORD *)L"Tahoma";
  v20 = *(_DWORD *)L"ma";
  v21 = aTahoma[6];
  v2 = *((_QWORD *)this + 2);
  if ( !v2 )
    return 0;
  v3 = *(_WORD *)(v2 + 28);
  DC = GetDC(0);
  v5 = DC;
  v6 = (int *)*((_QWORD *)this + 2);
  v7 = -*v6;
  if ( *v6 > 0 )
    v7 = *v6;
  v8 = (float)v7;
  DeviceCaps = GetDeviceCaps(DC, 90);
  if ( DeviceCaps > 0 )
    v8 = (float)(v8 * 72.0) / (float)DeviceCaps;
  v11 = 28;
  if ( v3 == 64 )
    v11 = 30;
  Gdiplus::FontFamily::FontFamily((Gdiplus::FontFamily *)v17, (const unsigned __int16 *)(v2 + v11), v10);
  if ( GdipUtilPrivate::FontCacheEntry::CreateFontFromFamily(
         this,
         (const struct Gdiplus::FontFamily *)v17,
         *((_DWORD *)this + 6),
         v8) )
  {
    GdipDeleteFontFamily(v17[0]);
    if ( v5 )
      ReleaseDC(0, v5);
    return 1;
  }
  else
  {
    v13 = *((_DWORD *)this + 6);
    v14 = Gdiplus::FontFamily::GenericSansSerif();
    if ( GdipUtilPrivate::FontCacheEntry::CreateFontFromFamily(this, v14, v13, v8) )
    {
      GdipDeleteFontFamily(v17[0]);
      if ( v5 )
        ReleaseDC(0, v5);
      return 1;
    }
    else
    {
      v15 = (struct Gdiplus::Font *)GdipAlloc(16);
      v18 = v15;
      if ( v15 )
        v15 = (struct Gdiplus::Font *)Gdiplus::Font::Font(v15, &v19);
      if ( GdipUtilPrivate::FontCacheEntry::CheckFontAndAttachOrDelete(this, v15) )
      {
        GdipDeleteFontFamily(v17[0]);
        if ( v5 )
          ReleaseDC(0, v5);
        return 1;
      }
      else
      {
        v16 = (struct Gdiplus::Font *)GdipAlloc(16);
        v18 = v16;
        if ( v16 )
          v16 = (struct Gdiplus::Font *)Gdiplus::Font::Font(v16, &v19);
        if ( GdipUtilPrivate::FontCacheEntry::CheckFontAndAttachOrDelete(this, v16) )
        {
          GdipDeleteFontFamily(v17[0]);
          if ( v5 )
            ReleaseDC(0, v5);
          return 1;
        }
        else
        {
          GdipDeleteFontFamily(v17[0]);
          if ( v5 )
            ReleaseDC(0, v5);
          return 0;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18003a0a8  push    rbx
0x18003a0aa  push    rsi
0x18003a0ab  push    rdi
0x18003a0ac  push    r14
0x18003a0ae  sub     rsp, 78h
0x18003a0b2  movaps  [rsp+98h+var_38], xmm6
0x18003a0b7  mov     rax, cs:__security_cookie
0x18003a0be  xor     rax, rsp
0x18003a0c1  mov     [rsp+98h+var_40], rax
0x18003a0c6  mov     rsi, rcx
0x18003a0c9  movsd   xmm0, qword ptr cs:aTahoma; "Tahoma"
0x18003a0d1  movsd   [rsp+98h+var_50], xmm0
0x18003a0d7  mov     eax, dword ptr cs:aTahoma+8; "ma"
0x18003a0dd  mov     [rsp+98h+var_48], eax
0x18003a0e1  movzx   eax, word ptr cs:aTahoma+0Ch; ""
0x18003a0e8  mov     [rsp+98h+var_44], ax
0x18003a0ed  mov     rbx, [rcx+10h]
0x18003a0f1  test    rbx, rbx
0x18003a0f4  jz      loc_18003A29D
0x18003a0fa  movzx   r14d, word ptr [rbx+1Ch]
0x18003a0ff  xor     ecx, ecx; hWnd
0x18003a101  call    cs:__imp_GetDC
0x18003a107  mov     rdi, rax
0x18003a10a  mov     rcx, [rsi+10h]
0x18003a10e  mov     edx, [rcx]
0x18003a110  neg     edx
0x18003a112  cmovs   edx, [rcx]
0x18003a115  movd    xmm6, edx
0x18003a119  cvtdq2ps xmm6, xmm6
0x18003a11c  mov     edx, 5Ah ; 'Z'; index
0x18003a121  mov     rcx, rax; hdc
0x18003a124  call    cs:__imp_GetDeviceCaps
0x18003a12a  test    eax, eax
0x18003a12c  jle     short loc_18003A141
0x18003a12e  mulss   xmm6, cs:__real@42900000
0x18003a136  movd    xmm0, eax
0x18003a13a  cvtdq2ps xmm0, xmm0
0x18003a13d  divss   xmm6, xmm0
0x18003a141  mov     ecx, 40h ; '@'
0x18003a146  lea     edx, [rcx-24h]
0x18003a149  lea     eax, [rcx-22h]
0x18003a14c  cmp     cx, r14w
0x18003a150  cmovz   edx, eax
0x18003a153  add     rdx, rbx; unsigned __int16 *
0x18003a156  lea     rcx, [rsp+98h+var_68]; this
0x18003a15b  call    ??0FontFamily@Gdiplus@@QEAA@PEBGPEBVFontCollection@1@@Z; Gdiplus::FontFamily::FontFamily(ushort const *,Gdiplus::FontCollection const *)
0x18003a160  movaps  xmm3, xmm6; float
0x18003a163  mov     r8d, [rsi+18h]; int
0x18003a167  lea     rdx, [rsp+98h+var_68]; struct Gdiplus::FontFamily *
0x18003a16c  mov     rcx, rsi; this
0x18003a16f  call    ?CreateFontFromFamily@FontCacheEntry@GdipUtilPrivate@@AEAA_NPEBVFontFamily@Gdiplus@@HM@Z; GdipUtilPrivate::FontCacheEntry::CreateFontFromFamily(Gdiplus::FontFamily const *,int,float)
0x18003a174  test    al, al
0x18003a176  jz      short loc_18003A19A
0x18003a178  mov     rcx, [rsp+98h+var_68]
0x18003a17d  call    cs:__imp_GdipDeleteFontFamily
0x18003a183  test    rdi, rdi
0x18003a186  jz      short loc_18003A193
0x18003a188  mov     rdx, rdi; hDC
0x18003a18b  xor     ecx, ecx; hWnd
0x18003a18d  call    cs:__imp_ReleaseDC
0x18003a193  mov     al, 1
0x18003a195  jmp     loc_18003A2A3
0x18003a19a  mov     ebx, [rsi+18h]
0x18003a19d  call    ?GenericSansSerif@FontFamily@Gdiplus@@SAPEBV12@XZ; Gdiplus::FontFamily::GenericSansSerif(void)
0x18003a1a2  movaps  xmm3, xmm6; float
0x18003a1a5  mov     r8d, ebx; int
0x18003a1a8  mov     rdx, rax; struct Gdiplus::FontFamily *
0x18003a1ab  mov     rcx, rsi; this
0x18003a1ae  call    ?CreateFontFromFamily@FontCacheEntry@GdipUtilPrivate@@AEAA_NPEBVFontFamily@Gdiplus@@HM@Z; GdipUtilPrivate::FontCacheEntry::CreateFontFromFamily(Gdiplus::FontFamily const *,int,float)
0x18003a1b3  test    al, al
0x18003a1b5  jz      short loc_18003A1D9
0x18003a1b7  mov     rcx, [rsp+98h+var_68]
0x18003a1bc  call    cs:__imp_GdipDeleteFontFamily
0x18003a1c2  test    rdi, rdi
0x18003a1c5  jz      short loc_18003A1D2
0x18003a1c7  mov     rdx, rdi; hDC
0x18003a1ca  xor     ecx, ecx; hWnd
0x18003a1cc  call    cs:__imp_ReleaseDC
0x18003a1d2  mov     al, 1
0x18003a1d4  jmp     loc_18003A2A3
0x18003a1d9  mov     ebx, 10h
0x18003a1de  mov     ecx, ebx
0x18003a1e0  call    cs:__imp_GdipAlloc
0x18003a1e6  mov     [rsp+98h+var_58], rax
0x18003a1eb  test    rax, rax
0x18003a1ee  jz      short loc_18003A200
0x18003a1f0  movaps  xmm2, xmm6
0x18003a1f3  lea     rdx, [rsp+98h+var_50]
0x18003a1f8  mov     rcx, rax
0x18003a1fb  call    ??0Font@Gdiplus@@QEAA@PEBGMHW4Unit@1@PEBVFontCollection@1@@Z; Gdiplus::Font::Font(ushort const *,float,int,Gdiplus::Unit,Gdiplus::FontCollection const *)
0x18003a200  mov     rdx, rax; struct Gdiplus::Font *
0x18003a203  mov     rcx, rsi; this
0x18003a206  call    ?CheckFontAndAttachOrDelete@FontCacheEntry@GdipUtilPrivate@@AEAA_NPEAVFont@Gdiplus@@@Z; GdipUtilPrivate::FontCacheEntry::CheckFontAndAttachOrDelete(Gdiplus::Font *)
0x18003a20b  test    al, al
0x18003a20d  jz      short loc_18003A22E
0x18003a20f  mov     rcx, [rsp+98h+var_68]
0x18003a214  call    cs:__imp_GdipDeleteFontFamily
0x18003a21a  test    rdi, rdi
0x18003a21d  jz      short loc_18003A22A
0x18003a21f  mov     rdx, rdi; hDC
0x18003a222  xor     ecx, ecx; hWnd
0x18003a224  call    cs:__imp_ReleaseDC
0x18003a22a  mov     al, 1
0x18003a22c  jmp     short loc_18003A2A3
0x18003a22e  mov     rcx, rbx
0x18003a231  call    cs:__imp_GdipAlloc
0x18003a237  mov     [rsp+98h+var_58], rax
0x18003a23c  test    rax, rax
0x18003a23f  jz      short loc_18003A256
0x18003a241  movss   xmm2, cs:__real@41100000
0x18003a249  lea     rdx, [rsp+98h+var_50]
0x18003a24e  mov     rcx, rax
0x18003a251  call    ??0Font@Gdiplus@@QEAA@PEBGMHW4Unit@1@PEBVFontCollection@1@@Z; Gdiplus::Font::Font(ushort const *,float,int,Gdiplus::Unit,Gdiplus::FontCollection const *)
0x18003a256  mov     rdx, rax; struct Gdiplus::Font *
0x18003a259  mov     rcx, rsi; this
0x18003a25c  call    ?CheckFontAndAttachOrDelete@FontCacheEntry@GdipUtilPrivate@@AEAA_NPEAVFont@Gdiplus@@@Z; GdipUtilPrivate::FontCacheEntry::CheckFontAndAttachOrDelete(Gdiplus::Font *)
0x18003a261  mov     rcx, [rsp+98h+var_68]
0x18003a266  test    al, al
0x18003a268  jz      short loc_18003A284
0x18003a26a  call    cs:__imp_GdipDeleteFontFamily
0x18003a270  test    rdi, rdi
0x18003a273  jz      short loc_18003A280
0x18003a275  mov     rdx, rdi; hDC
0x18003a278  xor     ecx, ecx; hWnd
0x18003a27a  call    cs:__imp_ReleaseDC
0x18003a280  mov     al, 1
0x18003a282  jmp     short loc_18003A2A3
0x18003a284  call    cs:__imp_GdipDeleteFontFamily
0x18003a28a  test    rdi, rdi
0x18003a28d  jz      short loc_18003A29B
0x18003a28f  mov     rdx, rdi; hDC
0x18003a292  xor     ecx, ecx; hWnd
0x18003a294  call    cs:__imp_ReleaseDC
0x18003a29a  nop
0x18003a29b  jmp     short loc_18003A2A1
0x18003a29d  xor     al, al
0x18003a29f  jmp     short loc_18003A2A3
0x18003a2a1  xor     al, al
0x18003a2a3  mov     rcx, [rsp+98h+var_40]
0x18003a2a8  xor     rcx, rsp; StackCookie
0x18003a2ab  call    __security_check_cookie
0x18003a2b0  movaps  xmm6, [rsp+98h+var_38]
0x18003a2b5  add     rsp, 78h
0x18003a2b9  pop     r14
0x18003a2bb  pop     rdi
0x18003a2bc  pop     rsi
0x18003a2bd  pop     rbx
0x18003a2be  retn
```
