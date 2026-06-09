# sub_1809ABAA8

- ea: `0x1809abaa8`
- end: `0x1809abbd6`
- name: `sub_1809ABAA8`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180521700`

## callees

- `0x1806929d0`
- `0x1809abaa8`
- `0x1809aca0c`

## import_xrefs

- `GDI32!BitBlt` at `0x1809abb68`
- `GDI32!BitBlt` at `0x1809abb68`
- `GDI32!SelectObject` at `0x1809abb27`
- `GDI32!SelectObject` at `0x1809abb74`
- `GDI32!SelectObject` at `0x1809abb27`
- `GDI32!SelectObject` at `0x1809abb74`
- `GDI32!DeleteObject` at `0x1809abb8c`
- `GDI32!DeleteObject` at `0x1809abb8c`
- `GDI32!CreateCompatibleDC` at `0x1809abb06`
- `GDI32!CreateCompatibleDC` at `0x1809abb06`
- `GDI32!DeleteDC` at `0x1809abb95`
- `GDI32!DeleteDC` at `0x1809abb95`
- `GDI32!CreateCompatibleBitmap` at `0x1809abb18`
- `GDI32!CreateCompatibleBitmap` at `0x1809abb18`
- `USER32!GetDC` at `0x1809abafa`
- `USER32!GetDC` at `0x1809abafa`
- `USER32!ReleaseDC` at `0x1809abba0`
- `USER32!ReleaseDC` at `0x1809abba0`
- `USER32!ShowWindow` at `0x1809abbb6`
- `USER32!ShowWindow` at `0x1809abbb6`

## pseudocode

```c
int sub_1809ABAA8()
{
  int result; // eax
  int v1; // r15d
  int cy; // r14d
  HDC DC; // rbp
  HDC CompatibleDC; // rsi
  HBITMAP CompatibleBitmap; // rdi
  HGDIOBJ v6; // rbx

  result = sub_1806929D0();
  v1 = Rect.right - Rect.left;
  cy = Rect.bottom - Rect.top;
  byte_180E28C5A = 0;
  if ( Rect.right - Rect.left >= 5 || cy >= 5 )
  {
    DC = GetDC(0);
    CompatibleDC = CreateCompatibleDC(DC);
    CompatibleBitmap = CreateCompatibleBitmap(DC, v1, cy);
    v6 = SelectObject(CompatibleDC, CompatibleBitmap);
    BitBlt(CompatibleDC, 0, 0, v1, cy, hdcSrc, Rect.left, Rect.top, 0xCC0020u);
    SelectObject(CompatibleDC, v6);
    qword_180E2A9E0 = sub_1809ACA0C(CompatibleBitmap);
    DeleteObject(CompatibleBitmap);
    DeleteDC(CompatibleDC);
    ReleaseDC(0, DC);
    byte_180E1C9D8 = 0;
    return ShowWindow(hWnd, 0);
  }
  return result;
}

```

## disassembly

```asm
0x1809abaa8  mov     [rsp+arg_0], rbx
0x1809abaad  mov     [rsp+arg_8], rbp
0x1809abab2  mov     [rsp+arg_10], rsi
0x1809abab7  push    rdi
0x1809abab8  push    r14
0x1809ababa  push    r15
0x1809ababc  sub     rsp, 50h
0x1809abac0  call    sub_1806929D0
0x1809abac5  mov     r15d, cs:Rect.right
0x1809abacc  mov     r14d, cs:Rect.bottom
0x1809abad3  sub     r15d, cs:Rect.left
0x1809abada  sub     r14d, cs:Rect.top
0x1809abae1  mov     cs:byte_180E28C5A, 0
0x1809abae8  cmp     r15d, 5
0x1809abaec  jge     short loc_1809ABAF8
0x1809abaee  cmp     r14d, 5
0x1809abaf2  jl      loc_1809ABBBC
0x1809abaf8  xor     ecx, ecx; hWnd
0x1809abafa  call    cs:GetDC
0x1809abb00  mov     rcx, rax; hdc
0x1809abb03  mov     rbp, rax
0x1809abb06  call    cs:CreateCompatibleDC
0x1809abb0c  mov     r8d, r14d; cy
0x1809abb0f  mov     edx, r15d; cx
0x1809abb12  mov     rcx, rbp; hdc
0x1809abb15  mov     rsi, rax
0x1809abb18  call    cs:CreateCompatibleBitmap
0x1809abb1e  mov     rdx, rax; h
0x1809abb21  mov     rcx, rsi; hdc
0x1809abb24  mov     rdi, rax
0x1809abb27  call    cs:SelectObject
0x1809abb2d  mov     ecx, cs:Rect.top
0x1809abb33  mov     r9d, r15d; cx
0x1809abb36  mov     [rsp+68h+rop], 0CC0020h; rop
0x1809abb3e  xor     r8d, r8d; y
0x1809abb41  mov     [rsp+68h+y1], ecx; y1
0x1809abb45  xor     edx, edx; x
0x1809abb47  mov     ecx, cs:Rect.left
0x1809abb4d  mov     rbx, rax
0x1809abb50  mov     [rsp+68h+x1], ecx; x1
0x1809abb54  mov     rcx, cs:hdcSrc
0x1809abb5b  mov     [rsp+68h+hdcSrc], rcx; hdcSrc
0x1809abb60  mov     rcx, rsi; hdc
0x1809abb63  mov     [rsp+68h+cy], r14d; cy
0x1809abb68  call    cs:BitBlt
0x1809abb6e  mov     rdx, rbx; h
0x1809abb71  mov     rcx, rsi; hdc
0x1809abb74  call    cs:SelectObject
0x1809abb7a  mov     rcx, rdi
0x1809abb7d  call    sub_1809ACA0C
0x1809abb82  mov     rcx, rdi; ho
0x1809abb85  mov     cs:qword_180E2A9E0, rax
0x1809abb8c  call    cs:DeleteObject
0x1809abb92  mov     rcx, rsi; hdc
0x1809abb95  call    cs:DeleteDC
0x1809abb9b  mov     rdx, rbp; hDC
0x1809abb9e  xor     ecx, ecx; hWnd
0x1809abba0  call    cs:ReleaseDC
0x1809abba6  mov     rcx, cs:hWnd; hWnd
0x1809abbad  xor     edx, edx; nCmdShow
0x1809abbaf  mov     cs:byte_180E1C9D8, 0
0x1809abbb6  call    cs:ShowWindow
0x1809abbbc  lea     r11, [rsp+68h+var_18]
0x1809abbc1  mov     rbx, [r11+20h]
0x1809abbc5  mov     rbp, [r11+28h]
0x1809abbc9  mov     rsi, [r11+30h]
0x1809abbcd  mov     rsp, r11
0x1809abbd0  pop     r15
0x1809abbd2  pop     r14
0x1809abbd4  pop     rdi
0x1809abbd5  retn
```
