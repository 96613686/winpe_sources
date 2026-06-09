# BitmapOfControl(CTL *,int)

- ea: `0x180054488`
- end: `0x18005459a`
- name: `?BitmapOfControl@@YAPEAUHBITMAP__@@PEAUCTL@@H@Z`
- size: `274`
- prototype: `HBITMAP __fastcall(struct CTL *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18002119c`

## callees

- `0x18000f5b0`
- `0x180028b30`
- `0x180054488`
- `0x180054690`
- `0x180054a64`
- `0x18007ad48`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `USER32!GetDC` at `0x1800544eb`
- `USER32!GetDC` at `0x1800544eb`
- `USER32!ReleaseDC` at `0x18005451a`
- `USER32!ReleaseDC` at `0x18005451a`
- `USER32!OffsetRect` at `0x1800544db`
- `USER32!OffsetRect` at `0x1800544db`
- `GDI32!CreateCompatibleBitmap` at `0x18005450c`
- `GDI32!CreateCompatibleBitmap` at `0x18005450c`
- `GDI32!CreateCompatibleDC` at `0x1800544f7`
- `GDI32!CreateCompatibleDC` at `0x1800544f7`
- `GDI32!DeleteDC` at `0x18005456a`
- `GDI32!DeleteDC` at `0x18005456a`
- `GDI32!SelectObject` at `0x18005452b`
- `GDI32!SelectObject` at `0x18005452b`

## pseudocode

```c
HBITMAP __fastcall BitmapOfControl(HWND *a1, int a2)
{
  HPALETTE v4; // r14
  HDC DC; // rbx
  HDC CompatibleDC; // rdi
  HBITMAP CompatibleBitmap; // rsi
  HBITMAP v8; // rax
  HWND v9; // rdx
  HBITMAP v10; // rbx
  struct tagRECT rc; // [rsp+30h] [rbp-38h] BYREF

  CtlGetRectInParent((struct CTL *)a1, &rc);
  OffsetRect(&rc, -rc.left, -rc.top);
  v4 = PicthPalRainbow();
  DC = GetDC(0);
  CompatibleDC = CreateCompatibleDC(DC);
  CompatibleBitmap = CreateCompatibleBitmap(DC, rc.right, rc.bottom);
  ReleaseDC(0, DC);
  if ( CompatibleBitmap )
  {
    v8 = (HBITMAP)SelectObject(CompatibleDC, CompatibleBitmap);
    v9 = a1[11];
    v10 = v8;
    if ( v9 )
      RenderWindow(CompatibleDC, v9, &rc, v4, a2);
    else
      RenderLiteCtl(CompatibleDC, (struct CTL *)a1, &rc, v4);
    RestoreBitmap(CompatibleDC, v10);
  }
  DeleteDC(CompatibleDC);
  return CompatibleBitmap;
}

```

## disassembly

```asm
0x180054488  mov     [rsp+arg_8], rbx
0x18005448d  mov     [rsp+arg_10], rbp
0x180054492  mov     [rsp+arg_18], rsi
0x180054497  push    rdi
0x180054498  push    r14
0x18005449a  push    r15
0x18005449c  mov     eax, 50h
0x1800544a1  call    _alloca_probe
0x1800544a6  sub     rsp, rax
0x1800544a9  mov     rax, cs:__security_cookie
0x1800544b0  xor     rax, rsp
0x1800544b3  mov     [rsp+68h+var_28], rax
0x1800544b8  mov     r15d, edx
0x1800544bb  lea     rdx, [rsp+68h+rc]; struct tagRECT *
0x1800544c0  mov     rbp, rcx
0x1800544c3  call    ?CtlGetRectInParent@@YAXPEAUCTL@@PEAUtagRECT@@@Z; CtlGetRectInParent(CTL *,tagRECT *)
0x1800544c8  mov     r8d, [rsp+68h+rc.top]
0x1800544cd  mov     edx, [rsp+68h+rc.left]
0x1800544d1  lea     rcx, [rsp+68h+rc]; lprc
0x1800544d6  neg     r8d; dy
0x1800544d9  neg     edx; dx
0x1800544db  call    cs:__imp_OffsetRect
0x1800544e1  call    ?PicthPalRainbow@@YAPEAUHPALETTE__@@XZ; PicthPalRainbow(void)
0x1800544e6  xor     ecx, ecx; hWnd
0x1800544e8  mov     r14, rax
0x1800544eb  call    cs:__imp_GetDC
0x1800544f1  mov     rcx, rax; hdc
0x1800544f4  mov     rbx, rax
0x1800544f7  call    cs:__imp_CreateCompatibleDC
0x1800544fd  mov     r8d, [rsp+68h+rc.bottom]; cy
0x180054502  mov     edx, [rsp+68h+rc.right]; cx
0x180054506  mov     rcx, rbx; hdc
0x180054509  mov     rdi, rax
0x18005450c  call    cs:__imp_CreateCompatibleBitmap
0x180054512  mov     rdx, rbx; hDC
0x180054515  xor     ecx, ecx; hWnd
0x180054517  mov     rsi, rax
0x18005451a  call    cs:__imp_ReleaseDC
0x180054520  test    rsi, rsi
0x180054523  jz      short loc_180054567
0x180054525  mov     rdx, rsi; h
0x180054528  mov     rcx, rdi; hdc
0x18005452b  call    cs:__imp_SelectObject
0x180054531  mov     rdx, [rbp+58h]; HWND
0x180054535  mov     r9, r14; HPALETTE
0x180054538  lea     r8, [rsp+68h+rc]; struct tagRECT *
0x18005453d  mov     rcx, rdi; HDC
0x180054540  mov     rbx, rax
0x180054543  test    rdx, rdx
0x180054546  jnz     short loc_180054552
0x180054548  mov     rdx, rbp; struct CTL *
0x18005454b  call    ?RenderLiteCtl@@YAXPEAUHDC__@@PEAUCTL@@PEAUtagRECT@@PEAUHPALETTE__@@@Z; RenderLiteCtl(HDC__ *,CTL *,tagRECT *,HPALETTE__ *)
0x180054550  jmp     short loc_18005455C
0x180054552  mov     [rsp+68h+var_48], r15d; int
0x180054557  call    ?RenderWindow@@YAXPEAUHDC__@@PEAUHWND__@@PEAUtagRECT@@PEAUHPALETTE__@@H@Z; RenderWindow(HDC__ *,HWND__ *,tagRECT *,HPALETTE__ *,int)
0x18005455c  mov     rdx, rbx; HBITMAP
0x18005455f  mov     rcx, rdi; HDC
0x180054562  call    ?RestoreBitmap@@YAXPEAUHDC__@@PEAUHBITMAP__@@@Z; RestoreBitmap(HDC__ *,HBITMAP__ *)
0x180054567  mov     rcx, rdi; hdc
0x18005456a  call    cs:__imp_DeleteDC
0x180054570  mov     rax, rsi
0x180054573  mov     rcx, [rsp+68h+var_28]
0x180054578  xor     rcx, rsp; StackCookie
0x18005457b  call    __security_check_cookie
0x180054580  lea     r11, [rsp+68h+var_18]
0x180054585  mov     rbx, [r11+28h]
0x180054589  mov     rbp, [r11+30h]
0x18005458d  mov     rsi, [r11+38h]
0x180054591  mov     rsp, r11
0x180054594  pop     r15
0x180054596  pop     r14
0x180054598  pop     rdi
0x180054599  retn
```
