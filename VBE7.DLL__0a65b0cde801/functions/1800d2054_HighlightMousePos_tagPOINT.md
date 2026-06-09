# HighlightMousePos(tagPOINT)

- ea: `0x1800d2054`
- end: `0x1800d2305`
- name: `?HighlightMousePos@@YAXUtagPOINT@@@Z`
- size: `689`
- prototype: `void __fastcall(struct tagPOINT)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800cffc0`

## callees

- `0x180001180`
- `0x1800cec7c`
- `0x1800ced2c`
- `0x1800d1a94`
- `0x1800d1bb0`
- `0x1800d1d64`
- `0x1800d1f54`
- `0x1800d1fb0`
- `0x1800d2054`
- `0x180379380`
- `0x180379520`

## import_xrefs

- `USER32!InvalidateRect` at `0x1800d210f`
- `USER32!InvalidateRect` at `0x1800d22b9`
- `USER32!InvalidateRect` at `0x1800d210f`
- `USER32!InvalidateRect` at `0x1800d22b9`
- `USER32!InflateRect` at `0x1800d2284`
- `USER32!InflateRect` at `0x1800d2284`
- `GDI32!CreateCompatibleDC` at `0x1800d2095`
- `GDI32!CreateCompatibleDC` at `0x1800d2095`
- `GDI32!DeleteDC` at `0x1800d22de`
- `GDI32!DeleteDC` at `0x1800d22de`
- `GDI32!PatBlt` at `0x1800d21b4`
- `GDI32!PatBlt` at `0x1800d21da`
- `GDI32!PatBlt` at `0x1800d2215`
- `GDI32!PatBlt` at `0x1800d223b`
- `GDI32!PatBlt` at `0x1800d21b4`
- `GDI32!PatBlt` at `0x1800d21da`
- `GDI32!PatBlt` at `0x1800d2215`
- `GDI32!PatBlt` at `0x1800d223b`
- `GDI32!IntersectClipRect` at `0x1800d2170`
- `GDI32!IntersectClipRect` at `0x1800d2170`
- `GDI32!SelectObject` at `0x1800d20b1`
- `GDI32!SelectObject` at `0x1800d2186`
- `GDI32!SelectObject` at `0x1800d21f0`
- `GDI32!SelectObject` at `0x1800d22d0`
- `GDI32!SelectObject` at `0x1800d20b1`
- `GDI32!SelectObject` at `0x1800d2186`
- `GDI32!SelectObject` at `0x1800d21f0`
- `GDI32!SelectObject` at `0x1800d22d0`

## pseudocode

```c
void __fastcall HighlightMousePos(struct tagPOINT a1)
{
  unsigned int v1; // ebx
  HDC CompatibleDC; // rax
  HDC v3; // rdi
  HGDIOBJ v4; // rsi
  HBRUSH v5; // rax
  HBRUSH v6; // rax
  struct tagPALCTL *v7; // r14
  HBITMAP HbmpOfIctl; // rbx
  RECT Rect; // [rsp+30h] [rbp-20h] BYREF

  v1 = ToolAtPoint(a1);
  if ( v1 != dword_1803F393C )
  {
    CompatibleDC = CreateCompatibleDC(0);
    v3 = CompatibleDC;
    if ( CompatibleDC )
    {
      v4 = SelectObject(CompatibleDC, qword_1803F38A0);
      if ( !v4 )
      {
LABEL_19:
        if ( v3 )
          DeleteDC(v3);
        return;
      }
      if ( dword_1803F393C != -1 )
      {
        _DrawOneControl(
          v3,
          0,
          (struct tagPALCTL *)((char *)qword_1803F38E8 + 16 * dword_1803F393C - 16),
          dword_1803F393C);
        ToolRectOfTool(dword_1803F393C, &Rect);
        InvalidateRect(hwnd, &Rect, 0);
        dword_1803F393C = -1;
      }
      if ( !(unsigned int)_ToolFCanSet(v1) )
        v1 = -1;
      dword_1803F393C = v1;
      if ( v1 != -1 )
      {
        ToolRectOfTool(v1, &Rect);
        if ( v1 == dword_1803F3890 )
        {
          if ( v1 )
            v7 = (struct tagPALCTL *)((char *)qword_1803F38E8 + 16 * v1 - 16);
          else
            v7 = 0;
          HbmpOfIctl = _GetHbmpOfIctl(0, v7, v1, 0);
          InflateRect(&Rect, -1, -1);
          _PalDrawBitmap(v3, &Rect, HbmpOfIctl);
          _ReleaseHbmpOfIctl(HbmpOfIctl, v7, dword_1803F393C);
        }
        else
        {
          IntersectClipRect(v3, left.left, left.top, left.right, left.bottom);
          v5 = BrHbrushCreate(0x80000014);
          SelectObject(v3, v5);
          PatBlt(v3, Rect.left, Rect.top, Rect.right - Rect.left - 1, 1, 0xF00021u);
          PatBlt(v3, Rect.left, Rect.top, 1, Rect.bottom - Rect.top - 1, 0xF00021u);
          v6 = BrHbrushCreate(0x80000010);
          SelectObject(v3, v6);
          PatBlt(v3, Rect.right - 1, Rect.top, 1, Rect.bottom - Rect.top, 0xF00021u);
          PatBlt(v3, Rect.left, Rect.bottom - 1, Rect.right - Rect.left - 1, 1, 0xF00021u);
        }
        InvalidateRect(hwnd, &Rect, 0);
      }
    }
    else
    {
      v4 = *(HGDIOBJ *)&Rect.left;
    }
    if ( v4 )
      SelectObject(v3, v4);
    goto LABEL_19;
  }
}

```

## disassembly

```asm
0x1800d2054  mov     [rsp-18h+arg_8], rbx
0x1800d2059  mov     [rsp-18h+arg_10], rsi
0x1800d205e  push    rbp
0x1800d205f  push    rdi
0x1800d2060  push    r14
0x1800d2062  mov     rbp, rsp
0x1800d2065  mov     eax, 50h
0x1800d206a  call    _alloca_probe
0x1800d206f  sub     rsp, rax
0x1800d2072  mov     rax, cs:__security_cookie
0x1800d2079  xor     rax, rsp
0x1800d207c  mov     [rbp+var_10], rax
0x1800d2080  call    ?ToolAtPoint@@YAIUtagPOINT@@@Z; ToolAtPoint(tagPOINT)
0x1800d2085  cmp     eax, cs:dword_1803F393C
0x1800d208b  mov     ebx, eax
0x1800d208d  jz      loc_1800D22E4
0x1800d2093  xor     ecx, ecx; hdc
0x1800d2095  call    cs:__imp_CreateCompatibleDC
0x1800d209b  mov     rdi, rax
0x1800d209e  test    rax, rax
0x1800d20a1  jz      loc_1800D22C1
0x1800d20a7  mov     rdx, cs:qword_1803F38A0; h
0x1800d20ae  mov     rcx, rax; hdc
0x1800d20b1  call    cs:__imp_SelectObject
0x1800d20b7  mov     rsi, rax
0x1800d20ba  test    rax, rax
0x1800d20bd  jz      loc_1800D22D6
0x1800d20c3  mov     r9d, cs:dword_1803F393C; unsigned int
0x1800d20ca  or      r14d, 0FFFFFFFFh
0x1800d20ce  cmp     r9d, r14d
0x1800d20d1  jz      short loc_1800D211C
0x1800d20d3  mov     r8, cs:qword_1803F38E8
0x1800d20da  mov     edx, r9d
0x1800d20dd  mov     rcx, rdi; HDC
0x1800d20e0  shl     rdx, 4
0x1800d20e4  add     r8, 0FFFFFFFFFFFFFFF0h
0x1800d20e8  add     r8, rdx; struct tagPALCTL *
0x1800d20eb  xor     edx, edx; int
0x1800d20ed  call    ?_DrawOneControl@@YAXPEAUHDC__@@HPEAUtagPALCTL@@I@Z; _DrawOneControl(HDC__ *,int,tagPALCTL *,uint)
0x1800d20f2  mov     ecx, cs:dword_1803F393C; unsigned int
0x1800d20f8  lea     rdx, [rbp+Rect]; struct tagRECT *
0x1800d20fc  call    ?ToolRectOfTool@@YAHIPEAUtagRECT@@@Z; ToolRectOfTool(uint,tagRECT *)
0x1800d2101  mov     rcx, cs:hwnd; hWnd
0x1800d2108  lea     rdx, [rbp+Rect]; lpRect
0x1800d210c  xor     r8d, r8d; bErase
0x1800d210f  call    cs:__imp_InvalidateRect
0x1800d2115  mov     cs:dword_1803F393C, r14d
0x1800d211c  mov     ecx, ebx; unsigned int
0x1800d211e  call    ?_ToolFCanSet@@YAHI@Z; _ToolFCanSet(uint)
0x1800d2123  test    eax, eax
0x1800d2125  cmovz   ebx, r14d
0x1800d2129  mov     cs:dword_1803F393C, ebx
0x1800d212f  cmp     ebx, r14d
0x1800d2132  jz      loc_1800D22C5
0x1800d2138  lea     rdx, [rbp+Rect]; struct tagRECT *
0x1800d213c  mov     ecx, ebx; unsigned int
0x1800d213e  call    ?ToolRectOfTool@@YAHIPEAUtagRECT@@@Z; ToolRectOfTool(uint,tagRECT *)
0x1800d2143  cmp     ebx, cs:dword_1803F3890
0x1800d2149  jz      loc_1800D2243
0x1800d214f  mov     eax, cs:left.bottom
0x1800d2155  mov     r9d, cs:left.right; right
0x1800d215c  mov     r8d, cs:left.top; top
0x1800d2163  mov     edx, cs:left.left; left
0x1800d2169  mov     rcx, rdi; hdc
0x1800d216c  mov     [rsp+50h+bottom], eax; bottom
0x1800d2170  call    cs:__imp_IntersectClipRect
0x1800d2176  mov     ecx, 80000014h; unsigned int
0x1800d217b  call    ?BrHbrushCreate@@YAPEAUHBRUSH__@@K@Z; BrHbrushCreate(ulong)
0x1800d2180  mov     rcx, rdi; hdc
0x1800d2183  mov     rdx, rax; h
0x1800d2186  call    cs:__imp_SelectObject
0x1800d218c  mov     r9d, [rbp+Rect.right]
0x1800d2190  mov     edx, [rbp+Rect.left]; x
0x1800d2193  mov     r8d, [rbp+Rect.top]; y
0x1800d2197  sub     r9d, edx
0x1800d219a  mov     r14d, 1
0x1800d21a0  mov     ebx, 0F00021h
0x1800d21a5  mov     rcx, rdi; hdc
0x1800d21a8  sub     r9d, r14d; w
0x1800d21ab  mov     [rsp+50h+rop], ebx; rop
0x1800d21af  mov     [rsp+50h+bottom], r14d; h
0x1800d21b4  call    cs:__imp_PatBlt
0x1800d21ba  mov     r11d, [rbp+Rect.bottom]
0x1800d21be  mov     r8d, [rbp+Rect.top]; y
0x1800d21c2  mov     edx, [rbp+Rect.left]; x
0x1800d21c5  sub     r11d, r8d
0x1800d21c8  mov     r9d, r14d; w
0x1800d21cb  mov     rcx, rdi; hdc
0x1800d21ce  sub     r11d, r14d
0x1800d21d1  mov     [rsp+50h+rop], ebx; rop
0x1800d21d5  mov     [rsp+50h+bottom], r11d; h
0x1800d21da  call    cs:__imp_PatBlt
0x1800d21e0  mov     ecx, 80000010h; unsigned int
0x1800d21e5  call    ?BrHbrushCreate@@YAPEAUHBRUSH__@@K@Z; BrHbrushCreate(ulong)
0x1800d21ea  mov     rcx, rdi; hdc
0x1800d21ed  mov     rdx, rax; h
0x1800d21f0  call    cs:__imp_SelectObject
0x1800d21f6  mov     r11d, [rbp+Rect.bottom]
0x1800d21fa  mov     r8d, [rbp+Rect.top]; y
0x1800d21fe  mov     edx, [rbp+Rect.right]
0x1800d2201  sub     r11d, r8d
0x1800d2204  mov     r9d, r14d; w
0x1800d2207  mov     rcx, rdi; hdc
0x1800d220a  dec     edx; x
0x1800d220c  mov     [rsp+50h+rop], ebx; rop
0x1800d2210  mov     [rsp+50h+bottom], r11d; h
0x1800d2215  call    cs:__imp_PatBlt
0x1800d221b  mov     r9d, [rbp+Rect.right]
0x1800d221f  mov     edx, [rbp+Rect.left]; x
0x1800d2222  mov     r8d, [rbp+Rect.bottom]
0x1800d2226  mov     rcx, rdi; hdc
0x1800d2229  sub     r9d, edx
0x1800d222c  mov     [rsp+50h+rop], ebx; rop
0x1800d2230  mov     [rsp+50h+bottom], r14d; h
0x1800d2235  sub     r9d, r14d; w
0x1800d2238  dec     r8d; y
0x1800d223b  call    cs:__imp_PatBlt
0x1800d2241  jmp     short loc_1800D22AB
0x1800d2243  mov     r14d, 1
0x1800d2249  cmp     ebx, r14d
0x1800d224c  jb      short loc_1800D2264
0x1800d224e  mov     r14, cs:qword_1803F38E8
0x1800d2255  mov     ecx, ebx
0x1800d2257  add     r14, 0FFFFFFFFFFFFFFF0h
0x1800d225b  shl     rcx, 4
0x1800d225f  add     r14, rcx
0x1800d2262  jmp     short loc_1800D2267
0x1800d2264  xor     r14d, r14d
0x1800d2267  xor     r9d, r9d; int
0x1800d226a  mov     r8d, ebx; unsigned int
0x1800d226d  mov     rdx, r14; struct tagPALCTL *
0x1800d2270  xor     ecx, ecx; int
0x1800d2272  call    ?_GetHbmpOfIctl@@YAPEAUHBITMAP__@@HPEAUtagPALCTL@@IH@Z; _GetHbmpOfIctl(int,tagPALCTL *,uint,int)
0x1800d2277  or      edx, 0FFFFFFFFh; dx
0x1800d227a  lea     rcx, [rbp+Rect]; lprc
0x1800d227e  mov     r8d, edx; dy
0x1800d2281  mov     rbx, rax
0x1800d2284  call    cs:__imp_InflateRect
0x1800d228a  lea     rdx, [rbp+Rect]; struct tagRECT *
0x1800d228e  mov     r8, rbx; HBITMAP
0x1800d2291  mov     rcx, rdi; HDC
0x1800d2294  call    ?_PalDrawBitmap@@YAXPEAUHDC__@@PEAUtagRECT@@PEAUHBITMAP__@@@Z; _PalDrawBitmap(HDC__ *,tagRECT *,HBITMAP__ *)
0x1800d2299  mov     r8d, cs:dword_1803F393C; unsigned int
0x1800d22a0  mov     rdx, r14; struct tagPALCTL *
0x1800d22a3  mov     rcx, rbx; HBITMAP
0x1800d22a6  call    ?_ReleaseHbmpOfIctl@@YAXPEAUHBITMAP__@@PEAUtagPALCTL@@I@Z; _ReleaseHbmpOfIctl(HBITMAP__ *,tagPALCTL *,uint)
0x1800d22ab  mov     rcx, cs:hwnd; hWnd
0x1800d22b2  lea     rdx, [rbp+Rect]; lpRect
0x1800d22b6  xor     r8d, r8d; bErase
0x1800d22b9  call    cs:__imp_InvalidateRect
0x1800d22bf  jmp     short loc_1800D22C5
0x1800d22c1  mov     rsi, qword ptr [rbp+Rect.left]
0x1800d22c5  test    rsi, rsi
0x1800d22c8  jz      short loc_1800D22D6
0x1800d22ca  mov     rdx, rsi; h
0x1800d22cd  mov     rcx, rdi; hdc
0x1800d22d0  call    cs:__imp_SelectObject
0x1800d22d6  test    rdi, rdi
0x1800d22d9  jz      short loc_1800D22E4
0x1800d22db  mov     rcx, rdi; hdc
0x1800d22de  call    cs:__imp_DeleteDC
0x1800d22e4  mov     rcx, [rbp+var_10]
0x1800d22e8  xor     rcx, rsp; StackCookie
0x1800d22eb  call    __security_check_cookie
0x1800d22f0  lea     r11, [rsp+50h+var_s0]
0x1800d22f5  mov     rbx, [r11+28h]
0x1800d22f9  mov     rsi, [r11+30h]
0x1800d22fd  mov     rsp, r11
0x1800d2300  pop     r14
0x1800d2302  pop     rdi
0x1800d2303  pop     rbp
0x1800d2304  retn
```
