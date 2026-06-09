# MiscLoadBitmap3DImpl(HINSTANCE__ *,ushort,tagCOLORCONV *,int,HPALETTE__ * *)

- ea: `0x180029378`
- end: `0x18002961b`
- name: `?MiscLoadBitmap3DImpl@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@GPEAUtagCOLORCONV@@HPEAPEAUHPALETTE__@@@Z`
- size: `675`
- prototype: `HBITMAP __fastcall(HINSTANCE, unsigned __int16, struct tagCOLORCONV *, int, LPCSTR lpBitmapName)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180029b34`
- `0x180029ee8`
- `0x1800812d0`

## callees

- `0x180029378`
- `0x180379380`
- `0x1803796a6`

## import_xrefs

- `MSVCR100!free` at `0x1800295d0`
- `MSVCR100!free` at `0x1800295d0`
- `MSVCR100!malloc` at `0x180029495`
- `MSVCR100!malloc` at `0x180029495`
- `KERNEL32!GlobalAlloc` at `0x180029417`
- `KERNEL32!GlobalAlloc` at `0x180029417`
- `KERNEL32!GlobalFree` at `0x1800295b9`
- `KERNEL32!GlobalFree` at `0x1800295b9`
- `KERNEL32!FreeResource` at `0x1800295c2`
- `KERNEL32!FreeResource` at `0x1800295c2`
- `KERNEL32!LoadResource` at `0x1800293f9`
- `KERNEL32!LoadResource` at `0x1800293f9`
- `KERNEL32!SizeofResource` at `0x1800293eb`
- `KERNEL32!SizeofResource` at `0x1800293eb`
- `KERNEL32!FindResourceA` at `0x1800293d3`
- `KERNEL32!FindResourceA` at `0x1800293d3`
- `USER32!LoadBitmapA` at `0x1800295fd`
- `USER32!LoadBitmapA` at `0x1800295fd`
- `USER32!GetDC` at `0x180029474`
- `USER32!GetDC` at `0x180029474`
- `USER32!ReleaseDC` at `0x1800295e0`
- `USER32!ReleaseDC` at `0x1800295e0`
- `GDI32!CreateDIBitmap` at `0x1800295a6`
- `GDI32!CreateDIBitmap` at `0x1800295a6`
- `GDI32!CreatePalette` at `0x18002955f`
- `GDI32!CreatePalette` at `0x18002955f`
- `GDI32!SelectPalette` at `0x180029576`
- `GDI32!SelectPalette` at `0x180029576`
- `GDI32!RealizePalette` at `0x18002957f`
- `GDI32!RealizePalette` at `0x18002957f`

## pseudocode

```c
HBITMAP __fastcall MiscLoadBitmap3DImpl(
        HINSTANCE a1,
        unsigned __int16 a2,
        struct tagCOLORCONV *a3,
        int a4,
        CHAR *lpBitmapName)
{
  LOGPALETTE *v6; // rdi
  HBITMAP DIBitmap; // r12
  HDC DC; // rbp
  __int64 v9; // r14
  HBITMAP result; // rax
  HRSRC v12; // rbx
  DWORD v13; // esi
  BITMAPINFO *Resource; // rax
  BITMAPINFO *v15; // r13
  BITMAPINFO *v16; // rax
  BITMAPINFO *pbmi; // rbx
  WORD biBitCount; // cx
  int biClrUsed; // esi
  RGBQUAD *bmiColors; // r8
  __int64 v21; // r11
  __int64 v22; // rdx
  HPALETTE Palette; // rax
  int v25; // [rsp+78h] [rbp+10h]
  const CHAR *lpBitmapNamea; // [rsp+90h] [rbp+28h]

  v6 = 0;
  DIBitmap = 0;
  v25 = 0;
  DC = 0;
  v9 = a4;
  if ( lpBitmapName )
    *(_QWORD *)lpBitmapName = 0;
  lpBitmapNamea = (const CHAR *)a2;
  result = (HBITMAP)FindResourceA(a1, (LPCSTR)a2, (LPCSTR)2);
  v12 = (HRSRC)result;
  if ( result )
  {
    v13 = SizeofResource(a1, (HRSRC)result);
    Resource = (BITMAPINFO *)LoadResource(a1, v12);
    v15 = Resource;
    if ( !Resource )
      return LoadBitmapA(a1, lpBitmapNamea);
    if ( (_DWORD)v9 )
    {
      v16 = (BITMAPINFO *)GlobalAlloc(0x40u, v13);
      v25 = 1;
      pbmi = v16;
      if ( !v16 )
        goto LABEL_35;
      memcpy_0(v16, v15, v13);
    }
    else
    {
      pbmi = Resource;
    }
    if ( !pbmi )
    {
LABEL_35:
      FreeResource(v15);
      if ( v6 )
        free(v6);
      if ( DC )
        ReleaseDC(0, DC);
      if ( DIBitmap )
        return DIBitmap;
      return LoadBitmapA(a1, lpBitmapNamea);
    }
    if ( pbmi->bmiHeader.biSize == 40 )
    {
      biBitCount = pbmi->bmiHeader.biBitCount;
      if ( biBitCount < 0x10u )
      {
        biClrUsed = pbmi->bmiHeader.biClrUsed;
        if ( !biClrUsed )
          biClrUsed = 1 << biBitCount;
        DC = GetDC(0);
        if ( !lpBitmapName || !Sys_ScrSizePalette )
          goto LABEL_18;
        v6 = (LOGPALETTE *)malloc(4LL * biClrUsed + 8);
        if ( v6 )
        {
          v6->palNumEntries = biClrUsed;
          v6->palVersion = 768;
LABEL_18:
          if ( biClrUsed > 0 )
          {
            bmiColors = pbmi->bmiColors;
            v21 = (unsigned int)biClrUsed;
            do
            {
              v22 = 0;
              if ( v9 > 0 )
              {
                while ( *bmiColors != (*((unsigned __int8 *)a3 + 8 * v22 + 2)
                                     | (*((unsigned __int8 *)a3 + 8 * v22) << 16)
                                     | (*((unsigned __int8 *)a3 + 8 * v22 + 1) << 8)) )
                {
                  if ( ++v22 >= v9 )
                    goto LABEL_25;
                }
                *bmiColors = (RGBQUAD)(*((unsigned __int8 *)a3 + 8 * v22 + 6)
                                     | (*((unsigned __int8 *)a3 + 8 * v22 + 4) << 16)
                                     | (*((unsigned __int8 *)a3 + 8 * v22 + 5) << 8));
              }
LABEL_25:
              if ( v6 )
                *(RGBQUAD *)((char *)&bmiColors[-9] + (char *)v6 - (char *)pbmi) = (RGBQUAD)((bmiColors->rgbBlue << 16)
                                                                                           | bmiColors->rgbRed
                                                                                           | (bmiColors->rgbGreen << 8));
              ++bmiColors;
              --v21;
            }
            while ( v21 );
          }
          if ( DC )
          {
            if ( v6 )
            {
              Palette = CreatePalette(v6);
              *(_QWORD *)lpBitmapName = Palette;
              if ( Palette )
              {
                SelectPalette(DC, Palette, 0);
                RealizePalette(DC);
              }
            }
            DIBitmap = CreateDIBitmap(DC, &pbmi->bmiHeader, 4u, &pbmi->bmiColors[biClrUsed], pbmi, 0);
          }
        }
      }
    }
    if ( v25 )
      GlobalFree(pbmi);
    goto LABEL_35;
  }
  return result;
}

```

## disassembly

```asm
0x180029378  mov     [rsp+arg_18], rbx
0x18002937d  mov     [rsp+arg_10], r8
0x180029382  mov     [rsp+hInstance], rcx
0x180029387  push    rbp
0x180029388  push    rsi
0x180029389  push    rdi
0x18002938a  push    r12
0x18002938c  push    r13
0x18002938e  push    r14
0x180029390  push    r15
0x180029392  mov     eax, 30h
0x180029397  call    _alloca_probe
0x18002939c  sub     rsp, rax
0x18002939f  mov     r15, [rsp+68h+lpBitmapName]
0x1800293a7  xor     edi, edi
0x1800293a9  xor     r12d, r12d
0x1800293ac  and     [rsp+68h+arg_8], edi
0x1800293b0  xor     ebp, ebp
0x1800293b2  movsxd  r14, r9d
0x1800293b5  mov     r13, rcx
0x1800293b8  test    r15, r15
0x1800293bb  jz      short loc_1800293C0
0x1800293bd  and     [r15], rdi
0x1800293c0  movzx   eax, dx
0x1800293c3  mov     r8d, 2; lpType
0x1800293c9  mov     edx, eax; lpName
0x1800293cb  mov     [rsp+68h+lpBitmapName], rax
0x1800293d3  call    cs:__imp_FindResourceA
0x1800293d9  mov     rbx, rax
0x1800293dc  test    rax, rax
0x1800293df  jz      loc_180029603
0x1800293e5  mov     rdx, rax; hResInfo
0x1800293e8  mov     rcx, r13; hModule
0x1800293eb  call    cs:__imp_SizeofResource
0x1800293f1  mov     rdx, rbx; hResInfo
0x1800293f4  mov     rcx, r13; hModule
0x1800293f7  mov     esi, eax
0x1800293f9  call    cs:__imp_LoadResource
0x1800293ff  mov     r13, rax
0x180029402  test    rax, rax
0x180029405  jz      loc_1800295F0
0x18002940b  test    r14d, r14d
0x18002940e  jz      short loc_180029441
0x180029410  mov     edx, esi; dwBytes
0x180029412  mov     ecx, 40h ; '@'; uFlags
0x180029417  call    cs:__imp_GlobalAlloc
0x18002941d  mov     [rsp+68h+arg_8], 1
0x180029425  mov     rbx, rax
0x180029428  test    rax, rax
0x18002942b  jz      loc_1800295BF
0x180029431  mov     r8d, esi; Size
0x180029434  mov     rdx, r13; Src
0x180029437  mov     rcx, rax; void *
0x18002943a  call    memcpy_0
0x18002943f  jmp     short loc_180029444
0x180029441  mov     rbx, rax
0x180029444  test    rbx, rbx
0x180029447  jz      loc_1800295BF
0x18002944d  cmp     dword ptr [rbx], 28h ; '('
0x180029450  jnz     loc_1800295AF
0x180029456  movzx   ecx, word ptr [rbx+0Eh]
0x18002945a  cmp     cx, 10h
0x18002945e  jnb     loc_1800295AF
0x180029464  mov     esi, [rbx+20h]
0x180029467  test    esi, esi
0x180029469  jnz     short loc_180029472
0x18002946b  mov     esi, 1
0x180029470  shl     esi, cl
0x180029472  xor     ecx, ecx; hWnd
0x180029474  call    cs:__imp_GetDC
0x18002947a  mov     rbp, rax
0x18002947d  test    r15, r15
0x180029480  jz      short loc_1800294B3
0x180029482  cmp     cs:?Sys_ScrSizePalette@@3IA, edi; uint Sys_ScrSizePalette
0x180029488  jz      short loc_1800294B3
0x18002948a  movsxd  rcx, esi
0x18002948d  lea     rcx, ds:8[rcx*4]; Size
0x180029495  call    cs:__imp_malloc
0x18002949b  mov     rdi, rax
0x18002949e  test    rax, rax
0x1800294a1  jz      loc_1800295AF
0x1800294a7  mov     eax, 300h
0x1800294ac  mov     [rdi+2], si
0x1800294b0  mov     [rdi], ax
0x1800294b3  mov     r10, r14
0x1800294b6  test    esi, esi
0x1800294b8  jle     loc_180029552
0x1800294be  mov     r9, rdi
0x1800294c1  lea     r8, [rbx+28h]
0x1800294c5  mov     r11d, esi
0x1800294c8  sub     r9, rbx
0x1800294cb  xor     edx, edx
0x1800294cd  test    r10, r10
0x1800294d0  jle     short loc_180029523
0x1800294d2  mov     r14, [rsp+68h+arg_10]
0x1800294da  movzx   ecx, byte ptr [r14+rdx*8+1]
0x1800294e0  movzx   eax, byte ptr [r14+rdx*8]
0x1800294e5  shl     ecx, 8
0x1800294e8  shl     eax, 10h
0x1800294eb  or      ecx, eax
0x1800294ed  movzx   eax, byte ptr [r14+rdx*8+2]
0x1800294f3  or      ecx, eax
0x1800294f5  cmp     [r8], ecx
0x1800294f8  jz      short loc_180029504
0x1800294fa  inc     rdx
0x1800294fd  cmp     rdx, r10
0x180029500  jl      short loc_1800294DA
0x180029502  jmp     short loc_180029523
0x180029504  movzx   ecx, byte ptr [r14+rdx*8+5]
0x18002950a  movzx   eax, byte ptr [r14+rdx*8+4]
0x180029510  shl     eax, 10h
0x180029513  shl     ecx, 8
0x180029516  or      ecx, eax
0x180029518  movzx   eax, byte ptr [r14+rdx*8+6]
0x18002951e  or      ecx, eax
0x180029520  mov     [r8], ecx
0x180029523  test    rdi, rdi
0x180029526  jz      short loc_180029545
0x180029528  movzx   eax, byte ptr [r8+2]
0x18002952d  movzx   ecx, byte ptr [r8+1]
0x180029532  shl     ecx, 8
0x180029535  or      ecx, eax
0x180029537  movzx   eax, byte ptr [r8]
0x18002953b  shl     eax, 10h
0x18002953e  or      ecx, eax
0x180029540  mov     [r9+r8-24h], ecx
0x180029545  add     r8, 4
0x180029549  dec     r11
0x18002954c  jnz     loc_1800294CB
0x180029552  test    rbp, rbp
0x180029555  jz      short loc_1800295AF
0x180029557  test    rdi, rdi
0x18002955a  jz      short loc_180029585
0x18002955c  mov     rcx, rdi; plpal
0x18002955f  call    cs:__imp_CreatePalette
0x180029565  mov     [r15], rax
0x180029568  test    rax, rax
0x18002956b  jz      short loc_180029585
0x18002956d  xor     r8d, r8d; bForceBkgd
0x180029570  mov     rdx, rax; hPal
0x180029573  mov     rcx, rbp; hdc
0x180029576  call    cs:__imp_SelectPalette
0x18002957c  mov     rcx, rbp; hdc
0x18002957f  call    cs:__imp_RealizePalette
0x180029585  and     [rsp+68h+var_40], r12d
0x18002958a  movsxd  rax, esi
0x18002958d  mov     r8d, 4; flInit
0x180029593  add     rax, 0Ah
0x180029597  mov     rdx, rbx; pbmih
0x18002959a  mov     rcx, rbp; hdc
0x18002959d  lea     r9, [rbx+rax*4]; pjBits
0x1800295a1  mov     [rsp+68h+pbmi], rbx; pbmi
0x1800295a6  call    cs:__imp_CreateDIBitmap
0x1800295ac  mov     r12, rax
0x1800295af  cmp     [rsp+68h+arg_8], 0
0x1800295b4  jz      short loc_1800295BF
0x1800295b6  mov     rcx, rbx; hMem
0x1800295b9  call    cs:__imp_GlobalFree
0x1800295bf  mov     rcx, r13; hResData
0x1800295c2  call    cs:__imp_FreeResource
0x1800295c8  test    rdi, rdi
0x1800295cb  jz      short loc_1800295D6
0x1800295cd  mov     rcx, rdi; Block
0x1800295d0  call    cs:__imp_free
0x1800295d6  test    rbp, rbp
0x1800295d9  jz      short loc_1800295E6
0x1800295db  mov     rdx, rbp; hDC
0x1800295de  xor     ecx, ecx; hWnd
0x1800295e0  call    cs:__imp_ReleaseDC
0x1800295e6  test    r12, r12
0x1800295e9  jz      short loc_1800295F0
0x1800295eb  mov     rax, r12
0x1800295ee  jmp     short loc_180029603
0x1800295f0  mov     rdx, [rsp+68h+lpBitmapName]; lpBitmapName
0x1800295f8  mov     rcx, [rsp+68h+hInstance]; hInstance
0x1800295fd  call    cs:__imp_LoadBitmapA
0x180029603  mov     rbx, [rsp+68h+arg_18]
0x18002960b  add     rsp, 30h
0x18002960f  pop     r15
0x180029611  pop     r14
0x180029613  pop     r13
0x180029615  pop     r12
0x180029617  pop     rdi
0x180029618  pop     rsi
0x180029619  pop     rbp
0x18002961a  retn
```
