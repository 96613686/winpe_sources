# CFontPropPage::UpdateSampleFont(void)

- ea: `0x1800cd1d0`
- end: `0x1800cd2fd`
- name: `?UpdateSampleFont@CFontPropPage@@IEAAXXZ`
- size: `301`
- prototype: `void __fastcall(CFontPropPage *__hidden this)`
- caller_count: `8`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800cbc20`
- `0x1800cc580`
- `0x1800cc6f0`
- `0x1800ccad0`
- `0x1800ccb30`
- `0x1800ccb90`
- `0x1800ccbe0`
- `0x1800ccc50`

## callees

- `0x18000e170`
- `0x180020710`
- `0x18005e820`
- `0x1800cc030`
- `0x1800cc3b0`
- `0x1800d1fe0`

## import_xrefs

- `USER32!GetWindowRect` at `0x1800cd2ac`
- `USER32!GetWindowRect` at `0x1800cd2ac`
- `USER32!UpdateWindow` at `0x1800cd2d6`
- `USER32!UpdateWindow` at `0x1800cd2d6`
- `USER32!InvalidateRect` at `0x1800cd2cc`
- `USER32!InvalidateRect` at `0x1800cd2cc`

## pseudocode

```c
void __fastcall CFontPropPage::UpdateSampleFont(CFontPropPage *this)
{
  struct FONTITEM_PPG *FontItem; // rax
  LONG Height; // eax
  int v4; // edx
  struct tagRECT Rect; // [rsp+20h] [rbp-29h] BYREF
  LOGFONTW lf; // [rsp+30h] [rbp-19h] BYREF

  FontItem = CFontComboBox::GetFontItem((CFontPropPage *)((char *)this + 936), -1);
  *(_OWORD *)&lf.lfHeight = *(_OWORD *)((char *)FontItem + 4);
  *(_OWORD *)&lf.lfWeight = *(_OWORD *)((char *)FontItem + 20);
  *(_OWORD *)&lf.lfFaceName[2] = *(_OWORD *)((char *)FontItem + 36);
  *(_OWORD *)&lf.lfFaceName[10] = *(_OWORD *)((char *)FontItem + 52);
  *(_OWORD *)&lf.lfFaceName[18] = *(_OWORD *)((char *)FontItem + 68);
  *(_OWORD *)&lf.lfFaceName[24] = *((_OWORD *)FontItem + 5);
  Height = CSizeComboBox::GetHeight((CFontPropPage *)((char *)this + 808), -1);
  v4 = *((_DWORD *)this + 280);
  lf.lfHeight = Height;
  lf.lfWidth = 0;
  lf.lfStrikeOut = *((_BYTE *)this + 1132);
  lf.lfUnderline = *((_BYTE *)this + 1136);
  lf.lfWeight = (v4 & 0x20) != 0 ? 700 : 400;
  lf.lfItalic = v4 & 1;
  CGdiObject::DeleteObject((CFontPropPage *)((char *)this + 1104));
  CFont::CreateFontIndirectW((CFontPropPage *)((char *)this + 1104), &lf);
  GetWindowRect(*((HWND *)this + 77), &Rect);
  CWnd::ScreenToClient(this, &Rect);
  InvalidateRect(*((HWND *)this + 8), &Rect, 1);
  UpdateWindow(*((HWND *)this + 8));
}

```

## disassembly

```asm
0x1800cd1d0  mov     [rsp-8+arg_8], rbx
0x1800cd1d5  mov     [rsp-8+arg_10], rdi
0x1800cd1da  push    rbp
0x1800cd1db  lea     rbp, [rsp-57h]
0x1800cd1e0  sub     rsp, 0A0h
0x1800cd1e7  mov     rax, cs:__security_cookie
0x1800cd1ee  xor     rax, rsp
0x1800cd1f1  mov     [rbp+57h+var_10], rax
0x1800cd1f5  mov     rdi, rcx
0x1800cd1f8  or      ebx, 0FFFFFFFFh
0x1800cd1fb  mov     edx, ebx; int
0x1800cd1fd  add     rcx, 3A8h; this
0x1800cd204  call    ?GetFontItem@CFontComboBox@@QEAAPEAUFONTITEM_PPG@@H@Z; CFontComboBox::GetFontItem(int)
0x1800cd209  lea     rcx, [rdi+328h]; this
0x1800cd210  mov     edx, ebx; int
0x1800cd212  movups  xmm0, xmmword ptr [rax+4]
0x1800cd216  movaps  xmmword ptr [rbp+57h+lf.lfHeight], xmm0
0x1800cd21a  movups  xmm1, xmmword ptr [rax+14h]
0x1800cd21e  movaps  xmmword ptr [rbp+57h+lf.lfWeight], xmm1
0x1800cd222  movups  xmm0, xmmword ptr [rax+24h]
0x1800cd226  movaps  xmmword ptr [rbp+57h+lf.lfFaceName+4], xmm0
0x1800cd22a  movups  xmm1, xmmword ptr [rax+34h]
0x1800cd22e  movaps  xmmword ptr [rbp+57h+lf.lfFaceName+14h], xmm1
0x1800cd232  movups  xmm0, xmmword ptr [rax+44h]
0x1800cd236  movaps  xmmword ptr [rbp+57h+lf.lfFaceName+24h], xmm0
0x1800cd23a  movups  xmm1, xmmword ptr [rax+50h]
0x1800cd23e  movups  xmmword ptr [rbp+57h+lf.lfFaceName+30h], xmm1
0x1800cd242  call    ?GetHeight@CSizeComboBox@@QEAAJH@Z; CSizeComboBox::GetHeight(int)
0x1800cd247  mov     edx, [rdi+460h]
0x1800cd24d  lea     rbx, [rdi+450h]
0x1800cd254  mov     [rbp+57h+lf.lfHeight], eax
0x1800cd257  mov     al, dl
0x1800cd259  and     al, 20h
0x1800cd25b  mov     [rbp+57h+lf.lfWidth], 0
0x1800cd262  neg     al
0x1800cd264  mov     al, [rdi+46Ch]
0x1800cd26a  sbb     ecx, ecx
0x1800cd26c  mov     [rbp+57h+lf.lfStrikeOut], al
0x1800cd26f  mov     al, [rdi+470h]
0x1800cd275  and     ecx, 12Ch
0x1800cd27b  add     ecx, 190h
0x1800cd281  mov     [rbp+57h+lf.lfUnderline], al
0x1800cd284  mov     [rbp+57h+lf.lfWeight], ecx
0x1800cd287  and     dl, 1
0x1800cd28a  mov     rcx, rbx; this
0x1800cd28d  mov     [rbp+57h+lf.lfItalic], dl
0x1800cd290  call    ?DeleteObject@CGdiObject@@QEAAHXZ; CGdiObject::DeleteObject(void)
0x1800cd295  lea     rdx, [rbp+57h+lf]; lplf
0x1800cd299  mov     rcx, rbx; this
0x1800cd29c  call    ?CreateFontIndirectW@CFont@@QEAAHPEBUtagLOGFONTW@@@Z; CFont::CreateFontIndirectW(tagLOGFONTW const *)
0x1800cd2a1  mov     rcx, [rdi+268h]; hWnd
0x1800cd2a8  lea     rdx, [rbp+57h+Rect]; lpRect
0x1800cd2ac  call    cs:__imp_GetWindowRect
0x1800cd2b2  lea     rdx, [rbp+57h+Rect]; struct tagRECT *
0x1800cd2b6  mov     rcx, rdi; this
0x1800cd2b9  call    ?ScreenToClient@CWnd@@QEBAXPEAUtagRECT@@@Z; CWnd::ScreenToClient(tagRECT *)
0x1800cd2be  mov     rcx, [rdi+40h]; hWnd
0x1800cd2c2  lea     rdx, [rbp+57h+Rect]; lpRect
0x1800cd2c6  mov     r8d, 1; bErase
0x1800cd2cc  call    cs:__imp_InvalidateRect
0x1800cd2d2  mov     rcx, [rdi+40h]; hWnd
0x1800cd2d6  call    cs:__imp_UpdateWindow
0x1800cd2dc  mov     rcx, [rbp+57h+var_10]
0x1800cd2e0  xor     rcx, rsp; StackCookie
0x1800cd2e3  call    __security_check_cookie
0x1800cd2e8  lea     r11, [rsp+0A0h+var_s0]
0x1800cd2f0  mov     rbx, [r11+18h]
0x1800cd2f4  mov     rdi, [r11+20h]
0x1800cd2f8  mov     rsp, r11
0x1800cd2fb  pop     rbp
0x1800cd2fc  retn
```
