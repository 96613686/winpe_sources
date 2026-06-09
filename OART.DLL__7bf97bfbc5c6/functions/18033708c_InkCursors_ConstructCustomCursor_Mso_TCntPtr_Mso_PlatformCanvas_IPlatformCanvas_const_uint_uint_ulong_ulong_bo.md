# InkCursors::ConstructCustomCursor(Mso::TCntPtr<Mso::PlatformCanvas::IPlatformCanvas> const &,uint,uint,ulong,ulong,bool,bool,bool)

- ea: `0x18033708c`
- end: `0x180337492`
- name: `?ConstructCustomCursor@InkCursors@@YAPEAUHICON__@@AEBV?$TCntPtr@UIPlatformCanvas@PlatformCanvas@Mso@@@Mso@@IIKK_N11@Z`
- size: `1030`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1802c006c`
- `0x18082d37c`

## callees

- `0x18001df54`
- `0x180071720`
- `0x18012737c`
- `0x18033708c`
- `0x180337494`
- `0x180337554`
- `0x1803375ac`
- `0x180a1b6bc`

## import_xrefs

- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x18033710a`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x18033710a`
- `GDI32!CreatePen` at `0x180337183`
- `GDI32!CreatePen` at `0x180337183`
- `GDI32!GetStockObject` at `0x180337200`
- `GDI32!GetStockObject` at `0x18033721e`
- `GDI32!GetStockObject` at `0x180337200`
- `GDI32!GetStockObject` at `0x18033721e`
- `GDI32!PatBlt` at `0x1803371f5`
- `GDI32!PatBlt` at `0x1803371f5`
- `GDI32!Rectangle` at `0x180337361`
- `GDI32!Rectangle` at `0x18033736c`
- `GDI32!Rectangle` at `0x180337361`
- `GDI32!Rectangle` at `0x18033736c`
- `GDI32!Ellipse` at `0x1803371bd`
- `GDI32!Ellipse` at `0x180337256`
- `GDI32!Ellipse` at `0x1803371bd`
- `GDI32!Ellipse` at `0x180337256`
- `GDI32!SelectObject` at `0x1803371d0`
- `GDI32!SelectObject` at `0x18033720e`
- `GDI32!SelectObject` at `0x18033722c`
- `GDI32!SelectObject` at `0x180337266`
- `GDI32!SelectObject` at `0x180337276`
- `GDI32!SelectObject` at `0x180337286`
- `GDI32!SelectObject` at `0x180337422`
- `GDI32!SelectObject` at `0x180337438`
- `GDI32!SelectObject` at `0x180337456`
- `GDI32!SelectObject` at `0x18033746f`
- `GDI32!SelectObject` at `0x1803371d0`
- `GDI32!SelectObject` at `0x18033720e`
- `GDI32!SelectObject` at `0x18033722c`
- `GDI32!SelectObject` at `0x180337266`
- `GDI32!SelectObject` at `0x180337276`
- `GDI32!SelectObject` at `0x180337286`
- `GDI32!SelectObject` at `0x180337422`
- `GDI32!SelectObject` at `0x180337438`
- `GDI32!SelectObject` at `0x180337456`
- `GDI32!SelectObject` at `0x18033746f`
- `GDI32!DeleteObject` at `0x180337334`
- `GDI32!DeleteObject` at `0x1803373a2`
- `GDI32!DeleteObject` at `0x180337443`
- `GDI32!DeleteObject` at `0x180337461`
- `GDI32!DeleteObject` at `0x180337334`
- `GDI32!DeleteObject` at `0x1803373a2`
- `GDI32!DeleteObject` at `0x180337443`
- `GDI32!DeleteObject` at `0x180337461`
- `GDI32!CreateCompatibleDC` at `0x180337152`
- `GDI32!CreateCompatibleDC` at `0x180337152`
- `GDI32!DeleteDC` at `0x18033737e`
- `GDI32!DeleteDC` at `0x180337397`
- `GDI32!DeleteDC` at `0x18033737e`
- `GDI32!DeleteDC` at `0x180337397`
- `USER32!GetDC` at `0x1803370ca`
- `USER32!GetDC` at `0x1803370ca`
- `USER32!ReleaseDC` at `0x180337346`
- `USER32!ReleaseDC` at `0x180337346`
- `USER32!CreateIconIndirect` at `0x1803372d1`
- `USER32!CreateIconIndirect` at `0x1803372d1`

## pseudocode

```c
HICON __fastcall InkCursors::ConstructCustomCursor(
        _QWORD *a1,
        int a2,
        int a3,
        unsigned int a4,
        int a5,
        __int64 a6,
        char a7)
{
  HDC v7; // r15
  HWND v10; // r13
  HDC DC; // rax
  HDC v12; // r12
  unsigned int v13; // esi
  unsigned int v14; // r14d
  HBITMAP CompatibleBitmap; // rax
  int v16; // r9d
  unsigned int v17; // r8d
  HPEN Pen; // rax
  HBITMAP v19; // rbx
  HGDIOBJ StockObject; // rax
  HGDIOBJ v21; // rax
  HGDIOBJ v22; // rsi
  HICON v23; // r14
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  HDC v28; // rcx
  const void *bottom; // [rsp+20h] [rbp-118h]
  HDC CompatibleDC; // [rsp+30h] [rbp-108h] BYREF
  HGDIOBJ h; // [rsp+38h] [rbp-100h] BYREF
  HGDIOBJ v32; // [rsp+40h] [rbp-F8h]
  HGDIOBJ v33; // [rsp+48h] [rbp-F0h]
  HWND v34; // [rsp+50h] [rbp-E8h]
  HGDIOBJ v35; // [rsp+58h] [rbp-E0h]
  HGDIOBJ ho; // [rsp+60h] [rbp-D8h]
  HGDIOBJ v37; // [rsp+68h] [rbp-D0h]
  HDC hdc[2]; // [rsp+70h] [rbp-C8h] BYREF
  ICONINFO piconinfo; // [rsp+80h] [rbp-B8h] BYREF
  HGDIOBJ v40[2]; // [rsp+A0h] [rbp-98h] BYREF
  HGDIOBJ v41; // [rsp+B0h] [rbp-88h]
  HDC v42; // [rsp+B8h] [rbp-80h]
  HWND v43; // [rsp+C0h] [rbp-78h]
  __int64 v44; // [rsp+C8h] [rbp-70h]

  v7 = (HDC)a4;
  v32 = 0;
  v10 = 0;
  v34 = 0;
  if ( *a1 )
  {
    v25 = ((__int64 (*)(void))Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->)();
    v26 = Mso::IObjectProxy::QueryObjectElseCrash<Mso::PlatformCanvas::IHWNDCanvas,0>(v25, &CompatibleDC);
    v27 = Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(v26);
    v10 = (HWND)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v27 + 40LL))(v27);
    v34 = v10;
    v28 = CompatibleDC;
    if ( CompatibleDC )
    {
      CompatibleDC = 0;
      (*(void (__fastcall **)(HDC))(*(_QWORD *)v28 + 8LL))(v28);
    }
  }
  DC = GetDC(v10);
  v12 = DC;
  v42 = DC;
  v43 = v10;
  v44 = 0;
  if ( !DC )
    return 0;
  v13 = a2 + 2;
  v14 = a3 + 2;
  CompatibleBitmap = MsoHbmpCreateCompatibleBitmap(DC, v13, v14, 0);
  ho = CompatibleBitmap;
  if ( !CompatibleBitmap )
  {
    Ofc::CLastErrorException::ThrowTag(0x13906CCu);
LABEL_34:
    if ( v7 )
      v33 = SelectObject(v7, Pen);
    goto LABEL_5;
  }
  *(_OWORD *)hdc = 0;
  Ofc::CCompatibleHDC::Create((Ofc::CCompatibleHDC *)hdc, v12, CompatibleBitmap);
  h = 0;
  Ofc::CHBitmap::Create((Ofc::CHBitmap *)&h, v13, v14, v16, bottom);
  CompatibleDC = CreateCompatibleDC(v12);
  v17 = (unsigned int)v7;
  v7 = hdc[0];
  Ofc::CHBrush::CHBrush((Ofc::CHBrush *)v40, hdc[0], v17);
  Pen = CreatePen(0, 1, a5 | 0x2000000u);
  v37 = Pen;
  v33 = 0;
  if ( Pen )
    goto LABEL_34;
LABEL_5:
  if ( a7 )
    Ellipse(v7, 0, 0, v13, v14);
  else
    Rectangle(v7, 0, 0, v13, v14);
  v19 = (HBITMAP)h;
  v35 = SelectObject(CompatibleDC, h);
  PatBlt(CompatibleDC, 0, 0, v13, v14, 0xFF0062u);
  StockObject = GetStockObject(4);
  h = SelectObject(CompatibleDC, StockObject);
  v21 = GetStockObject(7);
  v32 = SelectObject(CompatibleDC, v21);
  if ( a7 )
    Ellipse(CompatibleDC, 0, 0, v13, v14);
  else
    Rectangle(CompatibleDC, 0, 0, v13, v14);
  SelectObject(CompatibleDC, v32);
  SelectObject(CompatibleDC, h);
  SelectObject(CompatibleDC, v35);
  piconinfo.fIcon = 0;
  piconinfo.xHotspot = v13 >> 1;
  piconinfo.yHotspot = v14 >> 1;
  *(&piconinfo.yHotspot + 1) = 0;
  piconinfo.hbmMask = v19;
  v22 = ho;
  piconinfo.hbmColor = (HBITMAP)ho;
  v23 = CreateIconIndirect(&piconinfo);
  v32 = v23;
  if ( v33 )
    SelectObject(v7, v33);
  if ( v37 )
    DeleteObject(v37);
  if ( v41 )
    SelectObject((HDC)v40[1], v41);
  if ( v40[0] )
    DeleteObject(v40[0]);
  if ( CompatibleDC )
    DeleteDC(CompatibleDC);
  if ( v19 )
    DeleteObject(v19);
  if ( v7 )
  {
    if ( hdc[1] )
      SelectObject(v7, hdc[1]);
    DeleteDC(v7);
  }
  DeleteObject(v22);
  if ( v12 )
    ReleaseDC(v10, v12);
  return v23;
}

```

## disassembly

```asm
0x18033708c  push    rbx
0x18033708e  push    rsi
0x18033708f  push    r12
0x180337091  push    r13
0x180337093  push    r14
0x180337095  push    r15
0x180337097  sub     rsp, 108h
0x18033709e  mov     r15d, r9d
0x1803370a1  mov     r14d, r8d
0x1803370a4  mov     esi, edx
0x1803370a6  mov     ebx, [rsp+138h+arg_20]
0x1803370ad  mov     [rsp+138h+var_F8], 0
0x1803370b6  xor     r13d, r13d
0x1803370b9  mov     [rsp+138h+var_E8], r13
0x1803370be  cmp     [rcx], r13
0x1803370c1  jnz     loc_1803373AA
0x1803370c7  mov     rcx, r13; hWnd
0x1803370ca  call    cs:__imp_GetDC
0x1803370d0  mov     r12, rax
0x1803370d3  mov     [rsp+138h+var_80], rax
0x1803370db  mov     [rsp+138h+var_78], r13
0x1803370e3  mov     [rsp+138h+var_70], 0
0x1803370ef  test    rax, rax
0x1803370f2  jz      loc_180337377
0x1803370f8  add     esi, 2
0x1803370fb  add     r14d, 2
0x1803370ff  xor     r9d, r9d
0x180337102  mov     r8d, r14d
0x180337105  mov     edx, esi
0x180337107  mov     rcx, rax
0x18033710a  call    cs:__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z; MsoHbmpCreateCompatibleBitmap(HDC__ *,int,int,void *)
0x180337110  mov     [rsp+138h+ho], rax
0x180337115  test    rax, rax
0x180337118  jz      loc_180337405
0x18033711e  xorps   xmm0, xmm0
0x180337121  movdqu  xmmword ptr [rsp+138h+hdc], xmm0
0x180337127  mov     r8, rax; HBITMAP
0x18033712a  mov     rdx, r12; HDC
0x18033712d  lea     rcx, [rsp+138h+hdc]; this
0x180337132  call    ?Create@CCompatibleHDC@Ofc@@QEAAXPEAUHDC__@@PEAUHBITMAP__@@@Z; Ofc::CCompatibleHDC::Create(HDC__ *,HBITMAP__ *)
0x180337137  mov     [rsp+138h+h], 0
0x180337140  mov     r8d, r14d; nHeight
0x180337143  mov     edx, esi; nWidth
0x180337145  lea     rcx, [rsp+138h+h]; this
0x18033714a  call    ?Create@CHBitmap@Ofc@@QEAAXHHHPEBX@Z; Ofc::CHBitmap::Create(int,int,int,void const *)
0x18033714f  mov     rcx, r12; hdc
0x180337152  call    cs:__imp_CreateCompatibleDC
0x180337158  mov     [rsp+138h+var_108], rax
0x18033715d  mov     r8d, r15d; unsigned int
0x180337160  mov     r15, [rsp+138h+hdc]
0x180337165  mov     rdx, r15; HDC
0x180337168  lea     rcx, [rsp+138h+var_98]; this
0x180337170  call    ??0CHBrush@Ofc@@QEAA@PEAUHDC__@@K@Z; Ofc::CHBrush::CHBrush(HDC__ *,ulong)
0x180337175  bts     ebx, 19h
0x180337179  mov     r8d, ebx; color
0x18033717c  mov     edx, 1; cWidth
0x180337181  xor     ecx, ecx; iStyle
0x180337183  call    cs:__imp_CreatePen
0x180337189  mov     [rsp+138h+var_D0], rax
0x18033718e  mov     [rsp+138h+var_F0], 0
0x180337197  test    rax, rax
0x18033719a  jnz     loc_180337413
0x1803371a0  mov     dword ptr [rsp+138h+bottom], r14d; bottom
0x1803371a5  mov     r9d, esi; right
0x1803371a8  xor     r8d, r8d; top
0x1803371ab  xor     edx, edx; left
0x1803371ad  mov     rcx, r15; hdc
0x1803371b0  cmp     [rsp+138h+arg_30], dl
0x1803371b7  jz      loc_18033736C
0x1803371bd  call    cs:__imp_Ellipse
0x1803371c3  mov     rbx, [rsp+138h+h]
0x1803371c8  mov     rdx, rbx; h
0x1803371cb  mov     rcx, [rsp+138h+var_108]; hdc
0x1803371d0  call    cs:__imp_SelectObject
0x1803371d6  mov     [rsp+138h+var_E0], rax
0x1803371db  mov     [rsp+138h+rop], 0FF0062h; rop
0x1803371e3  mov     dword ptr [rsp+138h+bottom], r14d; h
0x1803371e8  mov     r9d, esi; w
0x1803371eb  xor     r8d, r8d; y
0x1803371ee  xor     edx, edx; x
0x1803371f0  mov     rcx, [rsp+138h+var_108]; hdc
0x1803371f5  call    cs:__imp_PatBlt
0x1803371fb  mov     ecx, 4; i
0x180337200  call    cs:__imp_GetStockObject
0x180337206  mov     rdx, rax; h
0x180337209  mov     rcx, [rsp+138h+var_108]; hdc
0x18033720e  call    cs:__imp_SelectObject
0x180337214  mov     [rsp+138h+h], rax
0x180337219  mov     ecx, 7; i
0x18033721e  call    cs:__imp_GetStockObject
0x180337224  mov     rdx, rax; h
0x180337227  mov     rcx, [rsp+138h+var_108]; hdc
0x18033722c  call    cs:__imp_SelectObject
0x180337232  mov     [rsp+138h+var_F8], rax
0x180337237  mov     dword ptr [rsp+138h+bottom], r14d; bottom
0x18033723c  mov     r9d, esi; right
0x18033723f  xor     r8d, r8d; top
0x180337242  xor     edx, edx; left
0x180337244  mov     rcx, [rsp+138h+var_108]; hdc
0x180337249  cmp     [rsp+138h+arg_30], dl
0x180337250  jz      loc_180337361
0x180337256  call    cs:__imp_Ellipse
0x18033725c  mov     rdx, [rsp+138h+var_F8]; h
0x180337261  mov     rcx, [rsp+138h+var_108]; hdc
0x180337266  call    cs:__imp_SelectObject
0x18033726c  mov     rdx, [rsp+138h+h]; h
0x180337271  mov     rcx, [rsp+138h+var_108]; hdc
0x180337276  call    cs:__imp_SelectObject
0x18033727c  mov     rdx, [rsp+138h+var_E0]; h
0x180337281  mov     rcx, [rsp+138h+var_108]; hdc
0x180337286  call    cs:__imp_SelectObject
0x18033728c  shr     esi, 1
0x18033728e  shr     r14d, 1
0x180337291  mov     [rsp+138h+piconinfo.fIcon], 0
0x18033729c  mov     [rsp+138h+piconinfo.xHotspot], esi
0x1803372a3  mov     [rsp+138h+piconinfo.yHotspot], r14d
0x1803372ab  xor     eax, eax
0x1803372ad  mov     dword ptr [rsp+138h+piconinfo+0Ch], eax
0x1803372b4  mov     [rsp+138h+piconinfo.hbmMask], rbx
0x1803372bc  mov     rsi, [rsp+138h+ho]
0x1803372c1  mov     [rsp+138h+piconinfo.hbmColor], rsi
0x1803372c9  lea     rcx, [rsp+138h+piconinfo]; piconinfo
0x1803372d1  call    cs:__imp_CreateIconIndirect
0x1803372d7  mov     r14, rax
0x1803372da  mov     [rsp+138h+var_F8], rax
0x1803372df  mov     rax, [rsp+138h+var_F0]
0x1803372e4  test    rax, rax
0x1803372e7  jnz     loc_180337432
0x1803372ed  mov     rcx, [rsp+138h+var_D0]; ho
0x1803372f2  test    rcx, rcx
0x1803372f5  jnz     loc_180337443
0x1803372fb  mov     rdx, [rsp+138h+var_88]; h
0x180337303  test    rdx, rdx
0x180337306  jnz     loc_18033744E
0x18033730c  mov     rcx, [rsp+138h+var_98]; ho
0x180337314  test    rcx, rcx
0x180337317  jnz     loc_180337461
0x18033731d  mov     rax, [rsp+138h+var_108]
0x180337322  test    rax, rax
0x180337325  jnz     short loc_18033737B
0x180337327  test    rbx, rbx
0x18033732a  jnz     short loc_18033739F
0x18033732c  test    r15, r15
0x18033732f  jnz     short loc_180337386
0x180337331  mov     rcx, rsi; ho
0x180337334  call    cs:__imp_DeleteObject
0x18033733a  nop
0x18033733b  test    r12, r12
0x18033733e  jz      short loc_18033734C
0x180337340  mov     rdx, r12; hDC
0x180337343  mov     rcx, r13; hWnd
0x180337346  call    cs:__imp_ReleaseDC
0x18033734c  mov     rax, r14
0x18033734f  add     rsp, 108h
0x180337356  pop     r15
0x180337358  pop     r14
0x18033735a  pop     r13
0x18033735c  pop     r12
0x18033735e  pop     rsi
0x18033735f  pop     rbx
0x180337360  retn
0x180337361  call    cs:__imp_Rectangle
0x180337367  jmp     loc_18033725C
0x18033736c  call    cs:__imp_Rectangle
0x180337372  jmp     loc_1803371C3
0x180337377  xor     eax, eax
0x180337379  jmp     short loc_18033734F
0x18033737b  mov     rcx, rax; hdc
0x18033737e  call    cs:__imp_DeleteDC
0x180337384  jmp     short loc_180337327
0x180337386  mov     rdx, [rsp+138h+hdc+8]; h
0x18033738b  test    rdx, rdx
0x18033738e  jnz     loc_18033746C
0x180337394  mov     rcx, r15; hdc
0x180337397  call    cs:__imp_DeleteDC
0x18033739d  jmp     short loc_180337331
0x18033739f  mov     rcx, rbx; ho
0x1803373a2  call    cs:__imp_DeleteObject
0x1803373a8  jmp     short loc_18033732C
0x1803373aa  call    ??C?$TCntPtr@VAppAugmentationStatefulRuntime@AugLoop@Art@@@Mso@@QEBAPEAVAppAugmentationStatefulRuntime@AugLoop@Art@@XZ; Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(void)
0x1803373af  lea     rdx, [rsp+138h+var_108]
0x1803373b4  mov     rcx, rax
0x1803373b7  call    ??$QueryObjectElseCrash@UIHWNDCanvas@PlatformCanvas@Mso@@$0A@@IObjectProxy@Mso@@QEAA?AV?$TCntPtr@UIHWNDCanvas@PlatformCanvas@Mso@@@1@XZ; Mso::IObjectProxy::QueryObjectElseCrash<Mso::PlatformCanvas::IHWNDCanvas,0>(void)
0x1803373bc  mov     rcx, rax
0x1803373bf  call    ??C?$TCntPtr@VAppAugmentationStatefulRuntime@AugLoop@Art@@@Mso@@QEBAPEAVAppAugmentationStatefulRuntime@AugLoop@Art@@XZ; Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(void)
0x1803373c4  mov     rcx, rax
0x1803373c7  mov     rax, [rax]
0x1803373ca  mov     rax, [rax+28h]
0x1803373ce  call    cs:__guard_dispatch_icall_fptr
0x1803373d4  mov     r13, rax
0x1803373d7  mov     [rsp+138h+var_E8], rax
0x1803373dc  mov     rcx, [rsp+138h+var_108]
0x1803373e1  test    rcx, rcx
0x1803373e4  jz      loc_1803370C7
0x1803373ea  mov     [rsp+138h+var_108], 0
0x1803373f3  mov     rdx, [rcx]
0x1803373f6  mov     rax, [rdx+8]
0x1803373fa  call    cs:__guard_dispatch_icall_fptr
0x180337400  jmp     loc_1803370C7
0x180337405  mov     ecx, 13906CCh; unsigned int
0x18033740a  call    ?ThrowTag@CLastErrorException@Ofc@@SAXK@Z; Ofc::CLastErrorException::ThrowTag(ulong)
0x18033740f  nop
0x180337410  jmp     short $+2
0x180337412  nop
0x180337413  test    r15, r15
0x180337416  jz      loc_1803371A0
0x18033741c  mov     rdx, rax; h
0x18033741f  mov     rcx, r15; hdc
0x180337422  call    cs:__imp_SelectObject
0x180337428  mov     [rsp+138h+var_F0], rax
0x18033742d  jmp     loc_1803371A0
0x180337432  mov     rdx, rax; h
0x180337435  mov     rcx, r15; hdc
0x180337438  call    cs:__imp_SelectObject
0x18033743e  jmp     loc_1803372ED
0x180337443  call    cs:__imp_DeleteObject
0x180337449  jmp     loc_1803372FB
0x18033744e  mov     rcx, [rsp+138h+var_90]; hdc
0x180337456  call    cs:__imp_SelectObject
0x18033745c  jmp     loc_18033730C
0x180337461  call    cs:__imp_DeleteObject
0x180337467  jmp     loc_18033731D
0x18033746c  mov     rcx, r15; hdc
0x18033746f  call    cs:__imp_SelectObject
0x180337475  jmp     loc_180337394
0x18033747a  mov     r14, [rsp+138h+var_F8]
0x18033747f  mov     r13, [rsp+138h+var_E8]
0x180337484  mov     r12, [rsp+138h+var_80]
0x18033748c  jmp     loc_18033733B
```
