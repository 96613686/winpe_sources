# MODVWR::DrawSplitterBar(HDC__ *)

- ea: `0x1801ff7dc`
- end: `0x1801ffdfe`
- name: `?DrawSplitterBar@MODVWR@@AEAAXPEAUHDC__@@@Z`
- size: `1570`
- prototype: `void __fastcall(MODVWR *__hidden this, HDC)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1801fa2e8`

## callees

- `0x1801fdb00`
- `0x1801ff7dc`
- `0x180379520`

## import_xrefs

- `USER32!GetSysColor` at `0x1801ff849`
- `USER32!GetSysColor` at `0x1801ff873`
- `USER32!GetSysColor` at `0x1801ff89d`
- `USER32!GetSysColor` at `0x1801ff8c7`
- `USER32!GetSysColor` at `0x1801ff849`
- `USER32!GetSysColor` at `0x1801ff873`
- `USER32!GetSysColor` at `0x1801ff89d`
- `USER32!GetSysColor` at `0x1801ff8c7`
- `USER32!IntersectRect` at `0x1801ff915`
- `USER32!IntersectRect` at `0x1801ffaf0`
- `USER32!IntersectRect` at `0x1801ff915`
- `USER32!IntersectRect` at `0x1801ffaf0`
- `GDI32!GetClipBox` at `0x1801ff83e`
- `GDI32!GetClipBox` at `0x1801ff83e`
- `GDI32!PatBlt` at `0x1801ff97c`
- `GDI32!PatBlt` at `0x1801ff9b8`
- `GDI32!PatBlt` at `0x1801ffa0c`
- `GDI32!PatBlt` at `0x1801ffa63`
- `GDI32!PatBlt` at `0x1801ffabc`
- `GDI32!PatBlt` at `0x1801ffb50`
- `GDI32!PatBlt` at `0x1801ffb81`
- `GDI32!PatBlt` at `0x1801ffbd6`
- `GDI32!PatBlt` at `0x1801ffc2f`
- `GDI32!PatBlt` at `0x1801ffc69`
- `GDI32!PatBlt` at `0x1801ffcc2`
- `GDI32!PatBlt` at `0x1801ffcfd`
- `GDI32!PatBlt` at `0x1801ffd4b`
- `GDI32!PatBlt` at `0x1801ffd80`
- `GDI32!PatBlt` at `0x1801ff97c`
- `GDI32!PatBlt` at `0x1801ff9b8`
- `GDI32!PatBlt` at `0x1801ffa0c`
- `GDI32!PatBlt` at `0x1801ffa63`
- `GDI32!PatBlt` at `0x1801ffabc`
- `GDI32!PatBlt` at `0x1801ffb50`
- `GDI32!PatBlt` at `0x1801ffb81`
- `GDI32!PatBlt` at `0x1801ffbd6`
- `GDI32!PatBlt` at `0x1801ffc2f`
- `GDI32!PatBlt` at `0x1801ffc69`
- `GDI32!PatBlt` at `0x1801ffcc2`
- `GDI32!PatBlt` at `0x1801ffcfd`
- `GDI32!PatBlt` at `0x1801ffd4b`
- `GDI32!PatBlt` at `0x1801ffd80`
- `GDI32!SelectObject` at `0x1801ff92c`
- `GDI32!SelectObject` at `0x1801ff9c7`
- `GDI32!SelectObject` at `0x1801ffa1b`
- `GDI32!SelectObject` at `0x1801ffa72`
- `GDI32!SelectObject` at `0x1801ffb07`
- `GDI32!SelectObject` at `0x1801ffbe5`
- `GDI32!SelectObject` at `0x1801ffc78`
- `GDI32!SelectObject` at `0x1801ffd0c`
- `GDI32!SelectObject` at `0x1801ffd97`
- `GDI32!SelectObject` at `0x1801ff92c`
- `GDI32!SelectObject` at `0x1801ff9c7`
- `GDI32!SelectObject` at `0x1801ffa1b`
- `GDI32!SelectObject` at `0x1801ffa72`
- `GDI32!SelectObject` at `0x1801ffb07`
- `GDI32!SelectObject` at `0x1801ffbe5`
- `GDI32!SelectObject` at `0x1801ffc78`
- `GDI32!SelectObject` at `0x1801ffd0c`
- `GDI32!SelectObject` at `0x1801ffd97`
- `GDI32!DeleteObject` at `0x1801ffdaa`
- `GDI32!DeleteObject` at `0x1801ffdbd`
- `GDI32!DeleteObject` at `0x1801ffdd0`
- `GDI32!DeleteObject` at `0x1801ffde3`
- `GDI32!DeleteObject` at `0x1801ffdaa`
- `GDI32!DeleteObject` at `0x1801ffdbd`
- `GDI32!DeleteObject` at `0x1801ffdd0`
- `GDI32!DeleteObject` at `0x1801ffde3`
- `GDI32!CreateSolidBrush` at `0x1801ff851`
- `GDI32!CreateSolidBrush` at `0x1801ff87b`
- `GDI32!CreateSolidBrush` at `0x1801ff8a5`
- `GDI32!CreateSolidBrush` at `0x1801ff8cf`
- `GDI32!CreateSolidBrush` at `0x1801ff851`
- `GDI32!CreateSolidBrush` at `0x1801ff87b`
- `GDI32!CreateSolidBrush` at `0x1801ff8a5`
- `GDI32!CreateSolidBrush` at `0x1801ff8cf`

## pseudocode

```c
void __fastcall MODVWR::DrawSplitterBar(MODVWR *this, HDC a2)
{
  COLORREF SysColor; // eax
  COLORREF v3; // eax
  COLORREF v4; // eax
  COLORREF v5; // eax
  HBRUSH v6; // [rsp+30h] [rbp-70h]
  HBRUSH SolidBrush; // [rsp+38h] [rbp-68h]
  HGDIOBJ v8; // [rsp+40h] [rbp-60h]
  HBRUSH ho; // [rsp+48h] [rbp-58h]
  HBRUSH h; // [rsp+50h] [rbp-50h]
  RECT rcSrc1; // [rsp+68h] [rbp-38h] BYREF
  struct tagRECT rect; // [rsp+78h] [rbp-28h] BYREF
  struct tagRECT rcDst; // [rsp+88h] [rbp-18h] BYREF

  v8 = 0;
  ho = 0;
  h = 0;
  v6 = 0;
  GetClipBox(a2, &rect);
  SysColor = GetSysColor(20);
  SolidBrush = CreateSolidBrush(SysColor);
  if ( SolidBrush )
  {
    v3 = GetSysColor(15);
    h = CreateSolidBrush(v3);
    if ( h )
    {
      v4 = GetSysColor(16);
      v6 = CreateSolidBrush(v4);
      if ( v6 )
      {
        v5 = GetSysColor(6);
        ho = CreateSolidBrush(v5);
        if ( ho )
        {
          if ( (unsigned int)MODVWR::RectOfRectid(this, 5, &rcSrc1) )
          {
            if ( IntersectRect(&rcDst, &rcSrc1, &rect) )
            {
              v8 = SelectObject(a2, h);
              if ( v8 )
              {
                PatBlt(a2, rcSrc1.left + 1, rcSrc1.top, rcSrc1.right - rcSrc1.left - 2, 1, 0xF00021u);
                PatBlt(a2, rcSrc1.left, rcSrc1.top + 2, rcSrc1.right - rcSrc1.left, g_cySplitBar - 4, 0xF00021u);
                if ( SelectObject(a2, SolidBrush) )
                {
                  PatBlt(a2, rcSrc1.left, rcSrc1.top + 1, rcSrc1.right - rcSrc1.left, 1, 0xF00021u);
                  if ( SelectObject(a2, v6) )
                  {
                    PatBlt(a2, rcSrc1.left, rcSrc1.bottom - 2, rcSrc1.right - rcSrc1.left - 1, 1, 0xF00021u);
                    if ( SelectObject(a2, ho) )
                      PatBlt(a2, rcSrc1.left + 1, rcSrc1.bottom - 1, rcSrc1.right - rcSrc1.left - 3, 1, 0xF00021u);
                  }
                }
              }
            }
          }
          else if ( (unsigned int)MODVWR::RectOfRectid(this, 4, &rcSrc1) )
          {
            if ( IntersectRect(&rcDst, &rcSrc1, &rect) )
            {
              v8 = SelectObject(a2, h);
              if ( v8 )
              {
                PatBlt(a2, rcSrc1.left, rcSrc1.top, rcSrc1.right - rcSrc1.left, 1, 0xF00021u);
                PatBlt(a2, rcSrc1.left, rcSrc1.top, 1, rcSrc1.bottom - rcSrc1.top, 0xF00021u);
                PatBlt(
                  a2,
                  rcSrc1.left + 2,
                  rcSrc1.top + 2,
                  rcSrc1.right - rcSrc1.left - 4,
                  rcSrc1.bottom - rcSrc1.top - 4,
                  0xF00021u);
                if ( SelectObject(a2, SolidBrush) )
                {
                  PatBlt(a2, rcSrc1.left + 1, rcSrc1.top + 1, rcSrc1.right - rcSrc1.left - 3, 1, 0xF00021u);
                  PatBlt(a2, rcSrc1.left + 1, rcSrc1.top + 1, 1, rcSrc1.bottom - rcSrc1.top - 3, 0xF00021u);
                  if ( SelectObject(a2, v6) )
                  {
                    PatBlt(a2, rcSrc1.left + 1, rcSrc1.bottom - 2, rcSrc1.right - rcSrc1.left - 1, 1, 0xF00021u);
                    PatBlt(a2, rcSrc1.right - 2, rcSrc1.top + 1, 1, rcSrc1.bottom - rcSrc1.top - 2, 0xF00021u);
                    if ( SelectObject(a2, ho) )
                    {
                      PatBlt(a2, rcSrc1.left, rcSrc1.bottom - 1, rcSrc1.right - rcSrc1.left, 1, 0xF00021u);
                      PatBlt(a2, rcSrc1.right - 1, rcSrc1.top, 1, rcSrc1.bottom - rcSrc1.top, 0xF00021u);
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v8 )
    SelectObject(a2, v8);
  if ( ho )
    DeleteObject(ho);
  if ( h )
    DeleteObject(h);
  if ( v6 )
    DeleteObject(v6);
  if ( SolidBrush )
    DeleteObject(SolidBrush);
}

```

## disassembly

```asm
0x1801ff7dc  mov     [rsp-8+hdc], rdx
0x1801ff7e1  mov     [rsp-8+arg_0], rcx
0x1801ff7e6  push    rbp
0x1801ff7e7  mov     rbp, rsp
0x1801ff7ea  sub     rsp, 0A0h
0x1801ff7f1  mov     rax, cs:__security_cookie
0x1801ff7f8  xor     rax, rsp
0x1801ff7fb  mov     [rbp+var_8], rax
0x1801ff7ff  mov     [rsp+0A0h+var_40], 0
0x1801ff808  mov     [rsp+0A0h+var_60], 0
0x1801ff811  mov     [rsp+0A0h+ho], 0
0x1801ff81a  mov     [rsp+0A0h+h], 0
0x1801ff823  mov     [rsp+0A0h+var_70], 0
0x1801ff82c  mov     [rsp+0A0h+var_68], 0
0x1801ff835  lea     rdx, [rsp+0A0h+rect]; lprect
0x1801ff83a  mov     rcx, [rbp+hdc]; hdc
0x1801ff83e  call    cs:__imp_GetClipBox
0x1801ff844  mov     ecx, 14h; nIndex
0x1801ff849  call    cs:__imp_GetSysColor
0x1801ff84f  mov     ecx, eax; color
0x1801ff851  call    cs:__imp_CreateSolidBrush
0x1801ff857  mov     [rsp+0A0h+var_68], rax
0x1801ff85c  cmp     [rsp+0A0h+var_68], 0
0x1801ff862  jnz     short loc_1801FF86E
0x1801ff864  jmp     loc_1801FFD86
0x1801ff869  jmp     loc_1801FFD86
0x1801ff86e  mov     ecx, 0Fh; nIndex
0x1801ff873  call    cs:__imp_GetSysColor
0x1801ff879  mov     ecx, eax; color
0x1801ff87b  call    cs:__imp_CreateSolidBrush
0x1801ff881  mov     [rsp+0A0h+h], rax
0x1801ff886  cmp     [rsp+0A0h+h], 0
0x1801ff88c  jnz     short loc_1801FF898
0x1801ff88e  jmp     loc_1801FFD86
0x1801ff893  jmp     loc_1801FFD86
0x1801ff898  mov     ecx, 10h; nIndex
0x1801ff89d  call    cs:__imp_GetSysColor
0x1801ff8a3  mov     ecx, eax; color
0x1801ff8a5  call    cs:__imp_CreateSolidBrush
0x1801ff8ab  mov     [rsp+0A0h+var_70], rax
0x1801ff8b0  cmp     [rsp+0A0h+var_70], 0
0x1801ff8b6  jnz     short loc_1801FF8C2
0x1801ff8b8  jmp     loc_1801FFD86
0x1801ff8bd  jmp     loc_1801FFD86
0x1801ff8c2  mov     ecx, 6; nIndex
0x1801ff8c7  call    cs:__imp_GetSysColor
0x1801ff8cd  mov     ecx, eax; color
0x1801ff8cf  call    cs:__imp_CreateSolidBrush
0x1801ff8d5  mov     [rsp+0A0h+ho], rax
0x1801ff8da  cmp     [rsp+0A0h+ho], 0
0x1801ff8e0  jnz     short loc_1801FF8EC
0x1801ff8e2  jmp     loc_1801FFD86
0x1801ff8e7  jmp     loc_1801FFD86
0x1801ff8ec  lea     r8, [rsp+0A0h+rcSrc1]
0x1801ff8f1  mov     edx, 5
0x1801ff8f6  mov     rcx, [rbp+arg_0]
0x1801ff8fa  call    ?RectOfRectid@MODVWR@@AEAAHW4RECTID@@PEAUtagRECT@@@Z; MODVWR::RectOfRectid(RECTID,tagRECT *)
0x1801ff8ff  test    eax, eax
0x1801ff901  jz      loc_1801FFAC7
0x1801ff907  lea     r8, [rsp+0A0h+rect]; lprcSrc2
0x1801ff90c  lea     rdx, [rsp+0A0h+rcSrc1]; lprcSrc1
0x1801ff911  lea     rcx, [rbp+rcDst]; lprcDst
0x1801ff915  call    cs:__imp_IntersectRect
0x1801ff91b  test    eax, eax
0x1801ff91d  jz      loc_1801FFAC2
0x1801ff923  mov     rdx, [rsp+0A0h+h]; h
0x1801ff928  mov     rcx, [rbp+hdc]; hdc
0x1801ff92c  call    cs:__imp_SelectObject
0x1801ff932  mov     [rsp+0A0h+var_60], rax
0x1801ff937  cmp     [rsp+0A0h+var_60], 0
0x1801ff93d  jnz     short loc_1801FF949
0x1801ff93f  jmp     loc_1801FFD86
0x1801ff944  jmp     loc_1801FFD86
0x1801ff949  mov     eax, [rsp+0A0h+rcSrc1.left]
0x1801ff94d  mov     ecx, [rsp+0A0h+rcSrc1.right]
0x1801ff951  sub     ecx, eax
0x1801ff953  mov     eax, ecx
0x1801ff955  sub     eax, 2
0x1801ff958  mov     ecx, [rsp+0A0h+rcSrc1.left]
0x1801ff95c  inc     ecx
0x1801ff95e  mov     [rsp+0A0h+rop], 0F00021h; rop
0x1801ff966  mov     [rsp+0A0h+var_80], 1; h
0x1801ff96e  mov     r9d, eax; w
0x1801ff971  mov     r8d, [rsp+0A0h+rcSrc1.top]; y
0x1801ff976  mov     edx, ecx; x
0x1801ff978  mov     rcx, [rbp+hdc]; hdc
0x1801ff97c  call    cs:__imp_PatBlt
0x1801ff982  mov     eax, cs:?g_cySplitBar@@3HA; int g_cySplitBar
0x1801ff988  sub     eax, 4
0x1801ff98b  mov     ecx, [rsp+0A0h+rcSrc1.left]
0x1801ff98f  mov     edx, [rsp+0A0h+rcSrc1.right]
0x1801ff993  sub     edx, ecx
0x1801ff995  mov     ecx, edx
0x1801ff997  mov     edx, [rsp+0A0h+rcSrc1.top]
0x1801ff99b  add     edx, 2
0x1801ff99e  mov     [rsp+0A0h+rop], 0F00021h; rop
0x1801ff9a6  mov     [rsp+0A0h+var_80], eax; h
0x1801ff9aa  mov     r9d, ecx; w
0x1801ff9ad  mov     r8d, edx; y
0x1801ff9b0  mov     edx, [rsp+0A0h+rcSrc1.left]; x
0x1801ff9b4  mov     rcx, [rbp+hdc]; hdc
0x1801ff9b8  call    cs:__imp_PatBlt
0x1801ff9be  mov     rdx, [rsp+0A0h+var_68]; h
0x1801ff9c3  mov     rcx, [rbp+hdc]; hdc
0x1801ff9c7  call    cs:__imp_SelectObject
0x1801ff9cd  test    rax, rax
0x1801ff9d0  jnz     short loc_1801FF9DC
0x1801ff9d2  jmp     loc_1801FFD86
0x1801ff9d7  jmp     loc_1801FFD86
0x1801ff9dc  mov     eax, [rsp+0A0h+rcSrc1.left]
0x1801ff9e0  mov     ecx, [rsp+0A0h+rcSrc1.right]
0x1801ff9e4  sub     ecx, eax
0x1801ff9e6  mov     eax, ecx
0x1801ff9e8  mov     ecx, [rsp+0A0h+rcSrc1.top]
0x1801ff9ec  inc     ecx
0x1801ff9ee  mov     [rsp+0A0h+rop], 0F00021h; rop
0x1801ff9f6  mov     [rsp+0A0h+var_80], 1; h
0x1801ff9fe  mov     r9d, eax; w
0x1801ffa01  mov     r8d, ecx; y
0x1801ffa04  mov     edx, [rsp+0A0h+rcSrc1.left]; x
0x1801ffa08  mov     rcx, [rbp+hdc]; hdc
0x1801ffa0c  call    cs:__imp_PatBlt
0x1801ffa12  mov     rdx, [rsp+0A0h+var_70]; h
0x1801ffa17  mov     rcx, [rbp+hdc]; hdc
0x1801ffa1b  call    cs:__imp_SelectObject
0x1801ffa21  test    rax, rax
0x1801ffa24  jnz     short loc_1801FFA30
0x1801ffa26  jmp     loc_1801FFD86
0x1801ffa2b  jmp     loc_1801FFD86
0x1801ffa30  mov     eax, [rsp+0A0h+rcSrc1.left]
0x1801ffa34  mov     ecx, [rsp+0A0h+rcSrc1.right]
0x1801ffa38  sub     ecx, eax
0x1801ffa3a  mov     eax, ecx
0x1801ffa3c  dec     eax
0x1801ffa3e  mov     ecx, [rsp+0A0h+rcSrc1.bottom]
0x1801ffa42  sub     ecx, 2
0x1801ffa45  mov     [rsp+0A0h+rop], 0F00021h; rop
0x1801ffa4d  mov     [rsp+0A0h+var_80], 1; h
0x1801ffa55  mov     r9d, eax; w
0x1801ffa58  mov     r8d, ecx; y
0x1801ffa5b  mov     edx, [rsp+0A0h+rcSrc1.left]; x
0x1801ffa5f  mov     rcx, [rbp+hdc]; hdc
0x1801ffa63  call    cs:__imp_PatBlt
0x1801ffa69  mov     rdx, [rsp+0A0h+ho]; h
0x1801ffa6e  mov     rcx, [rbp+hdc]; hdc
0x1801ffa72  call    cs:__imp_SelectObject
0x1801ffa78  test    rax, rax
0x1801ffa7b  jnz     short loc_1801FFA87
0x1801ffa7d  jmp     loc_1801FFD86
0x1801ffa82  jmp     loc_1801FFD86
0x1801ffa87  mov     eax, [rsp+0A0h+rcSrc1.left]
0x1801ffa8b  mov     ecx, [rsp+0A0h+rcSrc1.right]
0x1801ffa8f  sub     ecx, eax
0x1801ffa91  mov     eax, ecx
0x1801ffa93  sub     eax, 3
0x1801ffa96  mov     ecx, [rsp+0A0h+rcSrc1.bottom]
0x1801ffa9a  dec     ecx
0x1801ffa9c  mov     edx, [rsp+0A0h+rcSrc1.left]
0x1801ffaa0  inc     edx; x
0x1801ffaa2  mov     [rsp+0A0h+rop], 0F00021h; rop
0x1801ffaaa  mov     [rsp+0A0h+var_80], 1; h
0x1801ffab2  mov     r9d, eax; w
0x1801ffab5  mov     r8d, ecx; y
0x1801ffab8  mov     rcx, [rbp+hdc]; hdc
0x1801ffabc  call    cs:__imp_PatBlt
0x1801ffac2  jmp     loc_1801FFD86
0x1801ffac7  lea     r8, [rsp+0A0h+rcSrc1]
0x1801ffacc  mov     edx, 4
0x1801ffad1  mov     rcx, [rbp+arg_0]
0x1801ffad5  call    ?RectOfRectid@MODVWR@@AEAAHW4RECTID@@PEAUtagRECT@@@Z; MODVWR::RectOfRectid(RECTID,tagRECT *)
0x1801ffada  test    eax, eax
0x1801ffadc  jz      loc_1801FFD86
0x1801ffae2  lea     r8, [rsp+0A0h+rect]; lprcSrc2
0x1801ffae7  lea     rdx, [rsp+0A0h+rcSrc1]; lprcSrc1
0x1801ffaec  lea     rcx, [rbp+rcDst]; lprcDst
0x1801ffaf0  call    cs:__imp_IntersectRect
0x1801ffaf6  test    eax, eax
0x1801ffaf8  jz      loc_1801FFD86
0x1801ffafe  mov     rdx, [rsp+0A0h+h]; h
0x1801ffb03  mov     rcx, [rbp+hdc]; hdc
0x1801ffb07  call    cs:__imp_SelectObject
0x1801ffb0d  mov     [rsp+0A0h+var_60], rax
0x1801ffb12  cmp     [rsp+0A0h+var_60], 0
0x1801ffb18  jnz     short loc_1801FFB24
0x1801ffb1a  jmp     loc_1801FFD86
0x1801ffb1f  jmp     loc_1801FFD86
0x1801ffb24  mov     eax, [rsp+0A0h+rcSrc1.left]
0x1801ffb28  mov     ecx, [rsp+0A0h+rcSrc1.right]
0x1801ffb2c  sub     ecx, eax
0x1801ffb2e  mov     eax, ecx
0x1801ffb30  mov     [rsp+0A0h+rop], 0F00021h; rop
0x1801ffb38  mov     [rsp+0A0h+var_80], 1; h
0x1801ffb40  mov     r9d, eax; w
0x1801ffb43  mov     r8d, [rsp+0A0h+rcSrc1.top]; y
0x1801ffb48  mov     edx, [rsp+0A0h+rcSrc1.left]; x
0x1801ffb4c  mov     rcx, [rbp+hdc]; hdc
0x1801ffb50  call    cs:__imp_PatBlt
0x1801ffb56  mov     eax, [rsp+0A0h+rcSrc1.top]
0x1801ffb5a  mov     ecx, [rsp+0A0h+rcSrc1.bottom]
0x1801ffb5e  sub     ecx, eax
0x1801ffb60  mov     eax, ecx
0x1801ffb62  mov     [rsp+0A0h+rop], 0F00021h; rop
0x1801ffb6a  mov     [rsp+0A0h+var_80], eax; h
0x1801ffb6e  mov     r9d, 1; w
0x1801ffb74  mov     r8d, [rsp+0A0h+rcSrc1.top]; y
0x1801ffb79  mov     edx, [rsp+0A0h+rcSrc1.left]; x
0x1801ffb7d  mov     rcx, [rbp+hdc]; hdc
0x1801ffb81  call    cs:__imp_PatBlt
0x1801ffb87  mov     eax, [rsp+0A0h+rcSrc1.top]
0x1801ffb8b  mov     ecx, [rsp+0A0h+rcSrc1.bottom]
0x1801ffb8f  sub     ecx, eax
0x1801ffb91  mov     eax, ecx
0x1801ffb93  sub     eax, 4
0x1801ffb96  mov     ecx, [rsp+0A0h+rcSrc1.left]
0x1801ffb9a  mov     edx, [rsp+0A0h+rcSrc1.right]
0x1801ffb9e  sub     edx, ecx
0x1801ffba0  mov     ecx, edx
0x1801ffba2  sub     ecx, 4
0x1801ffba5  mov     edx, [rsp+0A0h+rcSrc1.top]
0x1801ffba9  add     edx, 2
0x1801ffbac  mov     r8d, [rsp+0A0h+rcSrc1.left]
0x1801ffbb1  add     r8d, 2
0x1801ffbb5  mov     [rsp+0A0h+x], r8d
0x1801ffbba  mov     [rsp+0A0h+rop], 0F00021h; rop
0x1801ffbc2  mov     [rsp+0A0h+var_80], eax; h
0x1801ffbc6  mov     r9d, ecx; w
0x1801ffbc9  mov     r8d, edx; y
0x1801ffbcc  mov     eax, [rsp+0A0h+x]
0x1801ffbd0  mov     edx, eax; x
0x1801ffbd2  mov     rcx, [rbp+hdc]; hdc
0x1801ffbd6  call    cs:__imp_PatBlt
0x1801ffbdc  mov     rdx, [rsp+0A0h+var_68]; h
0x1801ffbe1  mov     rcx, [rbp+hdc]; hdc
0x1801ffbe5  call    cs:__imp_SelectObject
0x1801ffbeb  test    rax, rax
0x1801ffbee  jnz     short loc_1801FFBFA
0x1801ffbf0  jmp     loc_1801FFD86
0x1801ffbf5  jmp     loc_1801FFD86
0x1801ffbfa  mov     eax, [rsp+0A0h+rcSrc1.left]
0x1801ffbfe  mov     ecx, [rsp+0A0h+rcSrc1.right]
0x1801ffc02  sub     ecx, eax
0x1801ffc04  mov     eax, ecx
0x1801ffc06  sub     eax, 3
0x1801ffc09  mov     ecx, [rsp+0A0h+rcSrc1.top]
0x1801ffc0d  inc     ecx
0x1801ffc0f  mov     edx, [rsp+0A0h+rcSrc1.left]
0x1801ffc13  inc     edx; x
0x1801ffc15  mov     [rsp+0A0h+rop], 0F00021h; rop
0x1801ffc1d  mov     [rsp+0A0h+var_80], 1; h
0x1801ffc25  mov     r9d, eax; w
0x1801ffc28  mov     r8d, ecx; y
0x1801ffc2b  mov     rcx, [rbp+hdc]; hdc
0x1801ffc2f  call    cs:__imp_PatBlt
0x1801ffc35  mov     eax, [rsp+0A0h+rcSrc1.top]
0x1801ffc39  mov     ecx, [rsp+0A0h+rcSrc1.bottom]
0x1801ffc3d  sub     ecx, eax
0x1801ffc3f  mov     eax, ecx
0x1801ffc41  sub     eax, 3
0x1801ffc44  mov     ecx, [rsp+0A0h+rcSrc1.top]
0x1801ffc48  inc     ecx
0x1801ffc4a  mov     edx, [rsp+0A0h+rcSrc1.left]
0x1801ffc4e  inc     edx; x
0x1801ffc50  mov     [rsp+0A0h+rop], 0F00021h; rop
0x1801ffc58  mov     [rsp+0A0h+var_80], eax; h
0x1801ffc5c  mov     r9d, 1; w
0x1801ffc62  mov     r8d, ecx; y
0x1801ffc65  mov     rcx, [rbp+hdc]; hdc
0x1801ffc69  call    cs:__imp_PatBlt
0x1801ffc6f  mov     rdx, [rsp+0A0h+var_70]; h
0x1801ffc74  mov     rcx, [rbp+hdc]; hdc
0x1801ffc78  call    cs:__imp_SelectObject
0x1801ffc7e  test    rax, rax
0x1801ffc81  jnz     short loc_1801FFC8D
0x1801ffc83  jmp     loc_1801FFD86
0x1801ffc88  jmp     loc_1801FFD86
0x1801ffc8d  mov     eax, [rsp+0A0h+rcSrc1.left]
0x1801ffc91  mov     ecx, [rsp+0A0h+rcSrc1.right]
0x1801ffc95  sub     ecx, eax
0x1801ffc97  mov     eax, ecx
0x1801ffc99  dec     eax
0x1801ffc9b  mov     ecx, [rsp+0A0h+rcSrc1.bottom]
0x1801ffc9f  sub     ecx, 2
0x1801ffca2  mov     edx, [rsp+0A0h+rcSrc1.left]
0x1801ffca6  inc     edx; x
0x1801ffca8  mov     [rsp+0A0h+rop], 0F00021h; rop
0x1801ffcb0  mov     [rsp+0A0h+var_80], 1; h
0x1801ffcb8  mov     r9d, eax; w
0x1801ffcbb  mov     r8d, ecx; y
0x1801ffcbe  mov     rcx, [rbp+hdc]; hdc
0x1801ffcc2  call    cs:__imp_PatBlt
0x1801ffcc8  mov     eax, [rsp+0A0h+rcSrc1.top]
0x1801ffccc  mov     ecx, [rsp+0A0h+rcSrc1.bottom]
0x1801ffcd0  sub     ecx, eax
0x1801ffcd2  mov     eax, ecx
0x1801ffcd4  sub     eax, 2
0x1801ffcd7  mov     ecx, [rsp+0A0h+rcSrc1.top]
0x1801ffcdb  inc     ecx
0x1801ffcdd  mov     edx, [rsp+0A0h+rcSrc1.right]
0x1801ffce1  sub     edx, 2; x
0x1801ffce4  mov     [rsp+0A0h+rop], 0F00021h; rop
  ... truncated ...
```
