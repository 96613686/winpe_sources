# NPANE::DrawNPane(HDC__ *)

- ea: `0x180239cac`
- end: `0x180239ec3`
- name: `?DrawNPane@NPANE@@AEAAXPEAUHDC__@@@Z`
- size: `535`
- prototype: `void __fastcall(NPANE *__hidden this, HDC)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180236de0`

## callees

- `0x1800e6178`
- `0x180237c0c`
- `0x180239cac`
- `0x180379520`

## import_xrefs

- `USER32!FillRect` at `0x180239d87`
- `USER32!FillRect` at `0x180239d87`
- `USER32!CopyRect` at `0x180239dba`
- `USER32!CopyRect` at `0x180239dba`
- `USER32!GetSysColor` at `0x180239d28`
- `USER32!GetSysColor` at `0x180239dc5`
- `USER32!GetSysColor` at `0x180239d28`
- `USER32!GetSysColor` at `0x180239dc5`
- `GDI32!ExtTextOutA` at `0x180239e5a`
- `GDI32!ExtTextOutA` at `0x180239e5a`
- `GDI32!SetBkMode` at `0x180239d19`
- `GDI32!SetBkMode` at `0x180239e7d`
- `GDI32!SetBkMode` at `0x180239d19`
- `GDI32!SetBkMode` at `0x180239e7d`
- `GDI32!SelectObject` at `0x180239d56`
- `GDI32!SelectObject` at `0x180239e94`
- `GDI32!SelectObject` at `0x180239d56`
- `GDI32!SelectObject` at `0x180239e94`
- `GDI32!SetBkColor` at `0x180239dd1`
- `GDI32!SetBkColor` at `0x180239e68`
- `GDI32!SetBkColor` at `0x180239dd1`
- `GDI32!SetBkColor` at `0x180239e68`
- `GDI32!DeleteObject` at `0x180239ea7`
- `GDI32!DeleteObject` at `0x180239ea7`
- `GDI32!CreateSolidBrush` at `0x180239d30`
- `GDI32!CreateSolidBrush` at `0x180239d30`

## pseudocode

```c
void __fastcall NPANE::DrawNPane(RECT *this, HDC a2)
{
  COLORREF SysColor; // eax
  COLORREF v3; // eax
  int mode; // [rsp+40h] [rbp-40h]
  HBRUSH h; // [rsp+48h] [rbp-38h]
  int top; // [rsp+50h] [rbp-30h]
  LONG bottom; // [rsp+54h] [rbp-2Ch]
  HGDIOBJ v8; // [rsp+58h] [rbp-28h]
  COLORREF color; // [rsp+60h] [rbp-20h]
  struct tagRECT rcDst; // [rsp+68h] [rbp-18h] BYREF

  v8 = 0;
  NPANE::GetRequiredHeight((NPANE *)this);
  if ( (this[12].left & 1) != 0 )
  {
    mode = SetBkMode(a2, 1);
    SysColor = GetSysColor(15);
    h = CreateSolidBrush(SysColor);
    if ( h )
    {
      v8 = SelectObject(a2, h);
      if ( v8 )
      {
        FillRect(a2, this + 2, h);
        if ( ((*(_DWORD *)(*((_QWORD *)PebappCur() + 1) + 1072LL) >> 5) & 1) == 0 )
        {
          CopyRect(&rcDst, this + 2);
          v3 = GetSysColor(16);
          color = SetBkColor(a2, v3);
          if ( rcDst.top <= rcDst.bottom )
            bottom = rcDst.bottom;
          else
            bottom = rcDst.top;
          rcDst.bottom = bottom;
          if ( rcDst.top <= bottom - 1 )
            top = rcDst.bottom - 1;
          else
            top = rcDst.top;
          rcDst.top = top;
          ExtTextOutA(a2, 0, 0, 2u, &rcDst, 0, 0, 0);
          SetBkColor(a2, color);
        }
      }
    }
    if ( mode )
      SetBkMode(a2, mode);
    if ( v8 )
      SelectObject(a2, v8);
    if ( h )
      DeleteObject(h);
  }
}

```

## disassembly

```asm
0x180239cac  mov     [rsp-8+hdc], rdx
0x180239cb1  mov     [rsp-8+arg_0], rcx
0x180239cb6  push    rbp
0x180239cb7  mov     rbp, rsp
0x180239cba  sub     rsp, 80h
0x180239cc1  mov     rax, cs:__security_cookie
0x180239cc8  xor     rax, rsp
0x180239ccb  mov     [rsp+80h+var_8], rax
0x180239cd0  mov     [rsp+80h+h], 0
0x180239cd9  mov     [rsp+80h+var_28], 0
0x180239ce2  mov     [rsp+80h+mode], 0
0x180239cea  mov     rcx, [rbp+arg_0]; this
0x180239cee  call    ?GetRequiredHeight@NPANE@@QEAAHXZ; NPANE::GetRequiredHeight(void)
0x180239cf3  mov     [rsp+80h+var_1C], eax
0x180239cf7  mov     rax, [rbp+arg_0]
0x180239cfb  mov     eax, [rax+0C0h]
0x180239d01  shl     eax, 1Fh
0x180239d04  sar     eax, 1Fh
0x180239d07  test    eax, eax
0x180239d09  jnz     short loc_180239D10
0x180239d0b  jmp     loc_180239EAD
0x180239d10  mov     edx, 1; mode
0x180239d15  mov     rcx, [rbp+hdc]; hdc
0x180239d19  call    cs:__imp_SetBkMode
0x180239d1f  mov     [rsp+80h+mode], eax
0x180239d23  mov     ecx, 0Fh; nIndex
0x180239d28  call    cs:__imp_GetSysColor
0x180239d2e  mov     ecx, eax; color
0x180239d30  call    cs:__imp_CreateSolidBrush
0x180239d36  mov     [rsp+80h+h], rax
0x180239d3b  cmp     [rsp+80h+h], 0
0x180239d41  jnz     short loc_180239D4D
0x180239d43  jmp     loc_180239E6E
0x180239d48  jmp     loc_180239E6E
0x180239d4d  mov     rdx, [rsp+80h+h]; h
0x180239d52  mov     rcx, [rbp+hdc]; hdc
0x180239d56  call    cs:__imp_SelectObject
0x180239d5c  mov     [rsp+80h+var_28], rax
0x180239d61  cmp     [rsp+80h+var_28], 0
0x180239d67  jnz     short loc_180239D73
0x180239d69  jmp     loc_180239E6E
0x180239d6e  jmp     loc_180239E6E
0x180239d73  mov     rax, [rbp+arg_0]
0x180239d77  add     rax, 20h ; ' '
0x180239d7b  mov     r8, [rsp+80h+h]; hbr
0x180239d80  mov     rdx, rax; lprc
0x180239d83  mov     rcx, [rbp+hdc]; hDC
0x180239d87  call    cs:__imp_FillRect
0x180239d8d  call    ?PebappCur@@YAPEAVEBAPP@@XZ; PebappCur(void)
0x180239d92  mov     rax, [rax+8]
0x180239d96  mov     eax, [rax+430h]
0x180239d9c  shr     eax, 5
0x180239d9f  and     eax, 1
0x180239da2  test    eax, eax
0x180239da4  jnz     loc_180239E6E
0x180239daa  mov     rax, [rbp+arg_0]
0x180239dae  add     rax, 20h ; ' '
0x180239db2  mov     rdx, rax; lprcSrc
0x180239db5  lea     rcx, [rsp+80h+rcDst]; lprcDst
0x180239dba  call    cs:__imp_CopyRect
0x180239dc0  mov     ecx, 10h; nIndex
0x180239dc5  call    cs:__imp_GetSysColor
0x180239dcb  mov     edx, eax; color
0x180239dcd  mov     rcx, [rbp+hdc]; hdc
0x180239dd1  call    cs:__imp_SetBkColor
0x180239dd7  mov     [rsp+80h+color], eax
0x180239ddb  mov     eax, [rsp+80h+rcDst.bottom]
0x180239ddf  cmp     [rsp+80h+rcDst.top], eax
0x180239de3  jle     short loc_180239DEF
0x180239de5  mov     eax, [rsp+80h+rcDst.top]
0x180239de9  mov     [rsp+80h+var_2C], eax
0x180239ded  jmp     short loc_180239DF7
0x180239def  mov     eax, [rsp+80h+rcDst.bottom]
0x180239df3  mov     [rsp+80h+var_2C], eax
0x180239df7  mov     eax, [rsp+80h+var_2C]
0x180239dfb  mov     [rsp+80h+rcDst.bottom], eax
0x180239dff  mov     eax, [rsp+80h+rcDst.bottom]
0x180239e03  dec     eax
0x180239e05  cmp     [rsp+80h+rcDst.top], eax
0x180239e09  jle     short loc_180239E15
0x180239e0b  mov     eax, [rsp+80h+rcDst.top]
0x180239e0f  mov     [rsp+80h+var_30], eax
0x180239e13  jmp     short loc_180239E1F
0x180239e15  mov     eax, [rsp+80h+rcDst.bottom]
0x180239e19  dec     eax
0x180239e1b  mov     [rsp+80h+var_30], eax
0x180239e1f  mov     eax, [rsp+80h+var_30]
0x180239e23  mov     [rsp+80h+rcDst.top], eax
0x180239e27  mov     [rsp+80h+lpDx], 0; lpDx
0x180239e30  mov     [rsp+80h+c], 0; c
0x180239e38  mov     [rsp+80h+lpString], 0; lpString
0x180239e41  lea     rax, [rsp+80h+rcDst]
0x180239e46  mov     [rsp+80h+lprect], rax; lprect
0x180239e4b  mov     r9d, 2; options
0x180239e51  xor     r8d, r8d; y
0x180239e54  xor     edx, edx; x
0x180239e56  mov     rcx, [rbp+hdc]; hdc
0x180239e5a  call    cs:__imp_ExtTextOutA
0x180239e60  mov     edx, [rsp+80h+color]; color
0x180239e64  mov     rcx, [rbp+hdc]; hdc
0x180239e68  call    cs:__imp_SetBkColor
0x180239e6e  cmp     [rsp+80h+mode], 0
0x180239e73  jz      short loc_180239E83
0x180239e75  mov     edx, [rsp+80h+mode]; mode
0x180239e79  mov     rcx, [rbp+hdc]; hdc
0x180239e7d  call    cs:__imp_SetBkMode
0x180239e83  cmp     [rsp+80h+var_28], 0
0x180239e89  jz      short loc_180239E9A
0x180239e8b  mov     rdx, [rsp+80h+var_28]; h
0x180239e90  mov     rcx, [rbp+hdc]; hdc
0x180239e94  call    cs:__imp_SelectObject
0x180239e9a  cmp     [rsp+80h+h], 0
0x180239ea0  jz      short loc_180239EAD
0x180239ea2  mov     rcx, [rsp+80h+h]; ho
0x180239ea7  call    cs:__imp_DeleteObject
0x180239ead  mov     rcx, [rsp+80h+var_8]
0x180239eb2  xor     rcx, rsp; StackCookie
0x180239eb5  call    __security_check_cookie
0x180239eba  add     rsp, 80h
0x180239ec1  pop     rbp
0x180239ec2  retn
```
