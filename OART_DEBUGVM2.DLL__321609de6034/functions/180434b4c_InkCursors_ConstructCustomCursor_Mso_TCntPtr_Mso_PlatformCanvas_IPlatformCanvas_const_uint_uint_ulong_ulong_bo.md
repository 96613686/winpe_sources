# InkCursors::ConstructCustomCursor(Mso::TCntPtr<Mso::PlatformCanvas::IPlatformCanvas> const &,uint,uint,ulong,ulong,bool,bool,bool)

- ea: `0x180434b4c`
- end: `0x180434f59`
- name: `?ConstructCustomCursor@InkCursors@@YAPEAUHICON__@@AEBV?$TCntPtr@UIPlatformCanvas@PlatformCanvas@Mso@@@Mso@@IIKK_N11@Z`
- size: `1037`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18039d308`
- `0x18083a03c`

## callees

- `0x18000e858`
- `0x1801e4320`
- `0x180279050`
- `0x180434b4c`
- `0x180434f5c`
- `0x180434fb8`
- `0x180435010`
- `0x180a2473c`

## import_xrefs

- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x180434bca`
- `mso40uiWin32Client!__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z` at `0x180434bca`
- `GDI32!CreatePen` at `0x180434c43`
- `GDI32!CreatePen` at `0x180434c43`
- `GDI32!GetStockObject` at `0x180434cc0`
- `GDI32!GetStockObject` at `0x180434cde`
- `GDI32!GetStockObject` at `0x180434cc0`
- `GDI32!GetStockObject` at `0x180434cde`
- `GDI32!PatBlt` at `0x180434cb5`
- `GDI32!PatBlt` at `0x180434cb5`
- `GDI32!Rectangle` at `0x180434e1d`
- `GDI32!Rectangle` at `0x180434e2c`
- `GDI32!Rectangle` at `0x180434e1d`
- `GDI32!Rectangle` at `0x180434e2c`
- `GDI32!Ellipse` at `0x180434c7d`
- `GDI32!Ellipse` at `0x180434d16`
- `GDI32!Ellipse` at `0x180434c7d`
- `GDI32!Ellipse` at `0x180434d16`
- `GDI32!SelectObject` at `0x180434c90`
- `GDI32!SelectObject` at `0x180434cce`
- `GDI32!SelectObject` at `0x180434cec`
- `GDI32!SelectObject` at `0x180434d26`
- `GDI32!SelectObject` at `0x180434d36`
- `GDI32!SelectObject` at `0x180434d46`
- `GDI32!SelectObject` at `0x180434ec8`
- `GDI32!SelectObject` at `0x180434ede`
- `GDI32!SelectObject` at `0x180434efc`
- `GDI32!SelectObject` at `0x180434f2d`
- `GDI32!SelectObject` at `0x180434c90`
- `GDI32!SelectObject` at `0x180434cce`
- `GDI32!SelectObject` at `0x180434cec`
- `GDI32!SelectObject` at `0x180434d26`
- `GDI32!SelectObject` at `0x180434d36`
- `GDI32!SelectObject` at `0x180434d46`
- `GDI32!SelectObject` at `0x180434ec8`
- `GDI32!SelectObject` at `0x180434ede`
- `GDI32!SelectObject` at `0x180434efc`
- `GDI32!SelectObject` at `0x180434f2d`
- `GDI32!DeleteObject` at `0x180434dfc`
- `GDI32!DeleteObject` at `0x180434e48`
- `GDI32!DeleteObject` at `0x180434ee9`
- `GDI32!DeleteObject` at `0x180434f07`
- `GDI32!DeleteObject` at `0x180434dfc`
- `GDI32!DeleteObject` at `0x180434e48`
- `GDI32!DeleteObject` at `0x180434ee9`
- `GDI32!DeleteObject` at `0x180434f07`
- `GDI32!CreateCompatibleDC` at `0x180434c12`
- `GDI32!CreateCompatibleDC` at `0x180434c12`
- `GDI32!DeleteDC` at `0x180434f15`
- `GDI32!DeleteDC` at `0x180434f36`
- `GDI32!DeleteDC` at `0x180434f15`
- `GDI32!DeleteDC` at `0x180434f36`
- `USER32!GetDC` at `0x180434b8a`
- `USER32!GetDC` at `0x180434b8a`
- `USER32!ReleaseDC` at `0x180434e3d`
- `USER32!ReleaseDC` at `0x180434e3d`
- `USER32!CreateIconIndirect` at `0x180434d91`
- `USER32!CreateIconIndirect` at `0x180434d91`

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
LABEL_31:
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
    goto LABEL_31;
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
0x180434b4c  push    rbx
0x180434b4e  push    rsi
0x180434b4f  push    r12
0x180434b51  push    r13
0x180434b53  push    r14
0x180434b55  push    r15
0x180434b57  sub     rsp, 108h
0x180434b5e  mov     r15d, r9d
0x180434b61  mov     r14d, r8d
0x180434b64  mov     esi, edx
0x180434b66  mov     ebx, [rsp+138h+arg_20]
0x180434b6d  mov     [rsp+138h+var_F8], 0
0x180434b76  xor     r13d, r13d
0x180434b79  mov     [rsp+138h+var_E8], r13
0x180434b7e  cmp     [rcx], r13
0x180434b81  jnz     loc_180434E50
0x180434b87  mov     rcx, r13; hWnd
0x180434b8a  call    cs:__imp_GetDC
0x180434b90  mov     r12, rax
0x180434b93  mov     [rsp+138h+var_80], rax
0x180434b9b  mov     [rsp+138h+var_78], r13
0x180434ba3  mov     [rsp+138h+var_70], 0
0x180434baf  test    rax, rax
0x180434bb2  jz      loc_180434E28
0x180434bb8  add     esi, 2
0x180434bbb  add     r14d, 2
0x180434bbf  xor     r9d, r9d
0x180434bc2  mov     r8d, r14d
0x180434bc5  mov     edx, esi
0x180434bc7  mov     rcx, rax
0x180434bca  call    cs:__imp_?MsoHbmpCreateCompatibleBitmap@@YAPEAUHBITMAP__@@PEAUHDC__@@HHPEAX@Z; MsoHbmpCreateCompatibleBitmap(HDC__ *,int,int,void *)
0x180434bd0  mov     [rsp+138h+ho], rax
0x180434bd5  test    rax, rax
0x180434bd8  jz      loc_180434EAB
0x180434bde  xorps   xmm0, xmm0
0x180434be1  movdqu  xmmword ptr [rsp+138h+hdc], xmm0
0x180434be7  mov     r8, rax; HBITMAP
0x180434bea  mov     rdx, r12; HDC
0x180434bed  lea     rcx, [rsp+138h+hdc]; this
0x180434bf2  call    ?Create@CCompatibleHDC@Ofc@@QEAAXPEAUHDC__@@PEAUHBITMAP__@@@Z; Ofc::CCompatibleHDC::Create(HDC__ *,HBITMAP__ *)
0x180434bf7  mov     [rsp+138h+h], 0
0x180434c00  mov     r8d, r14d; nHeight
0x180434c03  mov     edx, esi; nWidth
0x180434c05  lea     rcx, [rsp+138h+h]; this
0x180434c0a  call    ?Create@CHBitmap@Ofc@@QEAAXHHHPEBX@Z; Ofc::CHBitmap::Create(int,int,int,void const *)
0x180434c0f  mov     rcx, r12; hdc
0x180434c12  call    cs:__imp_CreateCompatibleDC
0x180434c18  mov     [rsp+138h+var_108], rax
0x180434c1d  mov     r8d, r15d; unsigned int
0x180434c20  mov     r15, [rsp+138h+hdc]
0x180434c25  mov     rdx, r15; HDC
0x180434c28  lea     rcx, [rsp+138h+var_98]; this
0x180434c30  call    ??0CHBrush@Ofc@@QEAA@PEAUHDC__@@K@Z; Ofc::CHBrush::CHBrush(HDC__ *,ulong)
0x180434c35  bts     ebx, 19h
0x180434c39  mov     r8d, ebx; color
0x180434c3c  mov     edx, 1; cWidth
0x180434c41  xor     ecx, ecx; iStyle
0x180434c43  call    cs:__imp_CreatePen
0x180434c49  mov     [rsp+138h+var_D0], rax
0x180434c4e  mov     [rsp+138h+var_F0], 0
0x180434c57  test    rax, rax
0x180434c5a  jnz     loc_180434EB9
0x180434c60  mov     dword ptr [rsp+138h+bottom], r14d; bottom
0x180434c65  mov     r9d, esi; right
0x180434c68  xor     r8d, r8d; top
0x180434c6b  xor     edx, edx; left
0x180434c6d  mov     rcx, r15; hdc
0x180434c70  cmp     [rsp+138h+arg_30], dl
0x180434c77  jz      loc_180434E2C
0x180434c7d  call    cs:__imp_Ellipse
0x180434c83  mov     rbx, [rsp+138h+h]
0x180434c88  mov     rdx, rbx; h
0x180434c8b  mov     rcx, [rsp+138h+var_108]; hdc
0x180434c90  call    cs:__imp_SelectObject
0x180434c96  mov     [rsp+138h+var_E0], rax
0x180434c9b  mov     [rsp+138h+rop], 0FF0062h; rop
0x180434ca3  mov     dword ptr [rsp+138h+bottom], r14d; h
0x180434ca8  mov     r9d, esi; w
0x180434cab  xor     r8d, r8d; y
0x180434cae  xor     edx, edx; x
0x180434cb0  mov     rcx, [rsp+138h+var_108]; hdc
0x180434cb5  call    cs:__imp_PatBlt
0x180434cbb  mov     ecx, 4; i
0x180434cc0  call    cs:__imp_GetStockObject
0x180434cc6  mov     rdx, rax; h
0x180434cc9  mov     rcx, [rsp+138h+var_108]; hdc
0x180434cce  call    cs:__imp_SelectObject
0x180434cd4  mov     [rsp+138h+h], rax
0x180434cd9  mov     ecx, 7; i
0x180434cde  call    cs:__imp_GetStockObject
0x180434ce4  mov     rdx, rax; h
0x180434ce7  mov     rcx, [rsp+138h+var_108]; hdc
0x180434cec  call    cs:__imp_SelectObject
0x180434cf2  mov     [rsp+138h+var_F8], rax
0x180434cf7  mov     dword ptr [rsp+138h+bottom], r14d; bottom
0x180434cfc  mov     r9d, esi; right
0x180434cff  xor     r8d, r8d; top
0x180434d02  xor     edx, edx; left
0x180434d04  mov     rcx, [rsp+138h+var_108]; hdc
0x180434d09  cmp     [rsp+138h+arg_30], dl
0x180434d10  jz      loc_180434E1D
0x180434d16  call    cs:__imp_Ellipse
0x180434d1c  mov     rdx, [rsp+138h+var_F8]; h
0x180434d21  mov     rcx, [rsp+138h+var_108]; hdc
0x180434d26  call    cs:__imp_SelectObject
0x180434d2c  mov     rdx, [rsp+138h+h]; h
0x180434d31  mov     rcx, [rsp+138h+var_108]; hdc
0x180434d36  call    cs:__imp_SelectObject
0x180434d3c  mov     rdx, [rsp+138h+var_E0]; h
0x180434d41  mov     rcx, [rsp+138h+var_108]; hdc
0x180434d46  call    cs:__imp_SelectObject
0x180434d4c  shr     esi, 1
0x180434d4e  shr     r14d, 1
0x180434d51  mov     [rsp+138h+piconinfo.fIcon], 0
0x180434d5c  mov     [rsp+138h+piconinfo.xHotspot], esi
0x180434d63  mov     [rsp+138h+piconinfo.yHotspot], r14d
0x180434d6b  xor     eax, eax
0x180434d6d  mov     dword ptr [rsp+138h+piconinfo+0Ch], eax
0x180434d74  mov     [rsp+138h+piconinfo.hbmMask], rbx
0x180434d7c  mov     rsi, [rsp+138h+ho]
0x180434d81  mov     [rsp+138h+piconinfo.hbmColor], rsi
0x180434d89  lea     rcx, [rsp+138h+piconinfo]; piconinfo
0x180434d91  call    cs:__imp_CreateIconIndirect
0x180434d97  mov     r14, rax
0x180434d9a  mov     [rsp+138h+var_F8], rax
0x180434d9f  mov     rax, [rsp+138h+var_F0]
0x180434da4  test    rax, rax
0x180434da7  jnz     loc_180434ED8
0x180434dad  mov     rcx, [rsp+138h+var_D0]; ho
0x180434db2  test    rcx, rcx
0x180434db5  jnz     loc_180434EE9
0x180434dbb  mov     rdx, [rsp+138h+var_88]; h
0x180434dc3  test    rdx, rdx
0x180434dc6  jnz     loc_180434EF4
0x180434dcc  mov     rcx, [rsp+138h+var_98]; ho
0x180434dd4  test    rcx, rcx
0x180434dd7  jnz     loc_180434F07
0x180434ddd  mov     rax, [rsp+138h+var_108]
0x180434de2  test    rax, rax
0x180434de5  jnz     loc_180434F12
0x180434deb  test    rbx, rbx
0x180434dee  jnz     short loc_180434E45
0x180434df0  test    r15, r15
0x180434df3  jnz     loc_180434F20
0x180434df9  mov     rcx, rsi; ho
0x180434dfc  call    cs:__imp_DeleteObject
0x180434e02  nop
0x180434e03  test    r12, r12
0x180434e06  jnz     short loc_180434E37
0x180434e08  mov     rax, r14
0x180434e0b  add     rsp, 108h
0x180434e12  pop     r15
0x180434e14  pop     r14
0x180434e16  pop     r13
0x180434e18  pop     r12
0x180434e1a  pop     rsi
0x180434e1b  pop     rbx
0x180434e1c  retn
0x180434e1d  call    cs:__imp_Rectangle
0x180434e23  jmp     loc_180434D1C
0x180434e28  xor     eax, eax
0x180434e2a  jmp     short loc_180434E0B
0x180434e2c  call    cs:__imp_Rectangle
0x180434e32  jmp     loc_180434C83
0x180434e37  mov     rdx, r12; hDC
0x180434e3a  mov     rcx, r13; hWnd
0x180434e3d  call    cs:__imp_ReleaseDC
0x180434e43  jmp     short loc_180434E08
0x180434e45  mov     rcx, rbx; ho
0x180434e48  call    cs:__imp_DeleteObject
0x180434e4e  jmp     short loc_180434DF0
0x180434e50  call    ??C?$TCntPtr@VAppAugmentationStatefulRuntime@AugLoop@Art@@@Mso@@QEBAPEAVAppAugmentationStatefulRuntime@AugLoop@Art@@XZ; Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(void)
0x180434e55  lea     rdx, [rsp+138h+var_108]
0x180434e5a  mov     rcx, rax
0x180434e5d  call    ??$QueryObjectElseCrash@UIHWNDCanvas@PlatformCanvas@Mso@@$0A@@IObjectProxy@Mso@@QEAA?AV?$TCntPtr@UIHWNDCanvas@PlatformCanvas@Mso@@@1@XZ; Mso::IObjectProxy::QueryObjectElseCrash<Mso::PlatformCanvas::IHWNDCanvas,0>(void)
0x180434e62  mov     rcx, rax
0x180434e65  call    ??C?$TCntPtr@VAppAugmentationStatefulRuntime@AugLoop@Art@@@Mso@@QEBAPEAVAppAugmentationStatefulRuntime@AugLoop@Art@@XZ; Mso::TCntPtr<Art::AugLoop::AppAugmentationStatefulRuntime>::operator->(void)
0x180434e6a  mov     rcx, rax
0x180434e6d  mov     rax, [rax]
0x180434e70  mov     rax, [rax+28h]
0x180434e74  call    cs:__guard_dispatch_icall_fptr
0x180434e7a  mov     r13, rax
0x180434e7d  mov     [rsp+138h+var_E8], rax
0x180434e82  mov     rcx, [rsp+138h+var_108]
0x180434e87  test    rcx, rcx
0x180434e8a  jz      loc_180434B87
0x180434e90  mov     [rsp+138h+var_108], 0
0x180434e99  mov     rdx, [rcx]
0x180434e9c  mov     rax, [rdx+8]
0x180434ea0  call    cs:__guard_dispatch_icall_fptr
0x180434ea6  jmp     loc_180434B87
0x180434eab  mov     ecx, 13906CCh; unsigned int
0x180434eb0  call    ?ThrowTag@CLastErrorException@Ofc@@SAXK@Z; Ofc::CLastErrorException::ThrowTag(ulong)
0x180434eb5  nop
0x180434eb6  jmp     short $+2
0x180434eb8  nop
0x180434eb9  test    r15, r15
0x180434ebc  jz      loc_180434C60
0x180434ec2  mov     rdx, rax; h
0x180434ec5  mov     rcx, r15; hdc
0x180434ec8  call    cs:__imp_SelectObject
0x180434ece  mov     [rsp+138h+var_F0], rax
0x180434ed3  jmp     loc_180434C60
0x180434ed8  mov     rdx, rax; h
0x180434edb  mov     rcx, r15; hdc
0x180434ede  call    cs:__imp_SelectObject
0x180434ee4  jmp     loc_180434DAD
0x180434ee9  call    cs:__imp_DeleteObject
0x180434eef  jmp     loc_180434DBB
0x180434ef4  mov     rcx, [rsp+138h+var_90]; hdc
0x180434efc  call    cs:__imp_SelectObject
0x180434f02  jmp     loc_180434DCC
0x180434f07  call    cs:__imp_DeleteObject
0x180434f0d  jmp     loc_180434DDD
0x180434f12  mov     rcx, rax; hdc
0x180434f15  call    cs:__imp_DeleteDC
0x180434f1b  jmp     loc_180434DEB
0x180434f20  mov     rdx, [rsp+138h+hdc+8]; h
0x180434f25  test    rdx, rdx
0x180434f28  jz      short loc_180434F33
0x180434f2a  mov     rcx, r15; hdc
0x180434f2d  call    cs:__imp_SelectObject
0x180434f33  mov     rcx, r15; hdc
0x180434f36  call    cs:__imp_DeleteDC
0x180434f3c  jmp     loc_180434DF9
0x180434f41  mov     r14, [rsp+138h+var_F8]
0x180434f46  mov     r13, [rsp+138h+var_E8]
0x180434f4b  mov     r12, [rsp+138h+var_80]
0x180434f53  jmp     loc_180434E03
```
