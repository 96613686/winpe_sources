# _AfxGetDropDownWidth(void)

- ea: `0x1800033c8`
- end: `0x1800034b0`
- name: `?_AfxGetDropDownWidth@@YAHXZ`
- size: `232`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002c40`

## callees

- `0x1800033c8`

## import_xrefs

- `USER32!GetSystemMetrics` at `0x1800033f6`
- `USER32!GetSystemMetrics` at `0x1800033f6`
- `USER32!ReleaseDC` at `0x180003492`
- `USER32!ReleaseDC` at `0x180003492`
- `USER32!GetDC` at `0x1800033e8`
- `USER32!GetDC` at `0x1800033e8`
- `GDI32!DeleteObject` at `0x180003487`
- `GDI32!DeleteObject` at `0x180003487`
- `GDI32!GetCharWidthW` at `0x18000346d`
- `GDI32!GetCharWidthW` at `0x18000346d`
- `GDI32!CreateFontW` at `0x18000343e`
- `GDI32!CreateFontW` at `0x18000343e`
- `GDI32!SelectObject` at `0x180003452`
- `GDI32!SelectObject` at `0x18000347e`
- `GDI32!SelectObject` at `0x180003452`
- `GDI32!SelectObject` at `0x18000347e`

## pseudocode

```c
__int64 _AfxGetDropDownWidth(void)
{
  __int64 result; // rax
  HGDIOBJ v1; // rsi
  HDC DC; // rbx
  int SystemMetrics; // eax
  HFONT FontW; // rax
  HFONT v5; // rdi

  result = (unsigned int)_afxDropDownWidth;
  if ( _afxDropDownWidth == -1 )
  {
    v1 = 0;
    DC = GetDC(0);
    SystemMetrics = GetSystemMetrics(72);
    FontW = CreateFontW(SystemMetrics, 0, 0, 0, 400, 0, 0, 0, 2u, 0, 0, 0, 0, L"Marlett");
    v5 = FontW;
    if ( FontW )
      v1 = SelectObject(DC, FontW);
    GetCharWidthW(DC, 0x36u, 0x36u, &_afxDropDownWidth);
    if ( v5 )
    {
      SelectObject(DC, v1);
      DeleteObject(v5);
    }
    ReleaseDC(0, DC);
    return (unsigned int)_afxDropDownWidth;
  }
  return result;
}

```

## disassembly

```asm
0x1800033c8  mov     [rsp+arg_0], rbx
0x1800033cd  mov     [rsp+arg_8], rsi
0x1800033d2  push    rdi
0x1800033d3  sub     rsp, 70h
0x1800033d7  mov     eax, cs:?_afxDropDownWidth@@3HA; int _afxDropDownWidth
0x1800033dd  cmp     eax, 0FFFFFFFFh
0x1800033e0  jnz     loc_18000349E
0x1800033e6  xor     ecx, ecx; hWnd
0x1800033e8  call    cs:__imp_GetDC
0x1800033ee  xor     esi, esi
0x1800033f0  mov     rbx, rax
0x1800033f3  lea     ecx, [rsi+48h]; nIndex
0x1800033f6  call    cs:__imp_GetSystemMetrics
0x1800033fc  xor     r9d, r9d; cOrientation
0x1800033ff  xor     r8d, r8d; cEscapement
0x180003402  mov     ecx, eax; cHeight
0x180003404  xor     edx, edx; cWidth
0x180003406  lea     rax, pszFaceName; "Marlett"
0x18000340d  mov     [rsp+78h+pszFaceName], rax; pszFaceName
0x180003412  mov     [rsp+78h+iPitchAndFamily], esi; iPitchAndFamily
0x180003416  mov     [rsp+78h+iQuality], esi; iQuality
0x18000341a  mov     [rsp+78h+iClipPrecision], esi; iClipPrecision
0x18000341e  mov     [rsp+78h+iOutPrecision], esi; iOutPrecision
0x180003422  mov     [rsp+78h+iCharSet], 2; iCharSet
0x18000342a  mov     [rsp+78h+bStrikeOut], esi; bStrikeOut
0x18000342e  mov     [rsp+78h+bUnderline], esi; bUnderline
0x180003432  mov     [rsp+78h+bItalic], esi; bItalic
0x180003436  mov     [rsp+78h+cWeight], 190h; cWeight
0x18000343e  call    cs:__imp_CreateFontW
0x180003444  mov     rdi, rax
0x180003447  test    rax, rax
0x18000344a  jz      short loc_18000345B
0x18000344c  mov     rdx, rax; h
0x18000344f  mov     rcx, rbx; hdc
0x180003452  call    cs:__imp_SelectObject
0x180003458  mov     rsi, rax
0x18000345b  mov     edx, 36h ; '6'; iFirst
0x180003460  lea     r9, ?_afxDropDownWidth@@3HA; lpBuffer
0x180003467  mov     r8d, edx; iLast
0x18000346a  mov     rcx, rbx; hdc
0x18000346d  call    cs:__imp_GetCharWidthW
0x180003473  test    rdi, rdi
0x180003476  jz      short loc_18000348D
0x180003478  mov     rdx, rsi; h
0x18000347b  mov     rcx, rbx; hdc
0x18000347e  call    cs:__imp_SelectObject
0x180003484  mov     rcx, rdi; ho
0x180003487  call    cs:__imp_DeleteObject
0x18000348d  mov     rdx, rbx; hDC
0x180003490  xor     ecx, ecx; hWnd
0x180003492  call    cs:__imp_ReleaseDC
0x180003498  mov     eax, cs:?_afxDropDownWidth@@3HA; int _afxDropDownWidth
0x18000349e  lea     r11, [rsp+78h+var_8]
0x1800034a3  mov     rbx, [r11+10h]
0x1800034a7  mov     rsi, [r11+18h]
0x1800034ab  mov     rsp, r11
0x1800034ae  pop     rdi
0x1800034af  retn
```
