# ATL::CAxHostWindow::GetDC(tagRECT const *,ulong,HDC__ * *)

- ea: `0x18000d2a0`
- end: `0x18000d3d3`
- name: `?GetDC@CAxHostWindow@ATL@@UEAAJPEBUtagRECT@@KPEAPEAUHDC__@@@Z`
- size: `307`
- prototype: `__int64 __fastcall(HWND *this, const struct tagRECT *, char, HDC *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001800`
- `0x18000d2a0`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x18000d327`
- `GDI32!CreateCompatibleDC` at `0x18000d327`
- `GDI32!CreateCompatibleBitmap` at `0x18000d34a`
- `GDI32!CreateCompatibleBitmap` at `0x18000d34a`
- `GDI32!SelectObject` at `0x18000d35e`
- `GDI32!SelectObject` at `0x18000d35e`
- `GDI32!DeleteObject` at `0x18000d36c`
- `GDI32!DeleteObject` at `0x18000d380`
- `GDI32!DeleteObject` at `0x18000d36c`
- `GDI32!DeleteObject` at `0x18000d380`
- `GDI32!DeleteDC` at `0x18000d375`
- `GDI32!DeleteDC` at `0x18000d375`
- `USER32!GetDC` at `0x18000d2e7`
- `USER32!GetDC` at `0x18000d2e7`
- `USER32!GetClientRect` at `0x18000d318`
- `USER32!GetClientRect` at `0x18000d318`
- `USER32!FillRect` at `0x18000d3a4`
- `USER32!FillRect` at `0x18000d3a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall ATL::CAxHostWindow::GetDC(HWND *this, const struct tagRECT *a2, char a3, HDC *a4)
{
  HDC DC; // rax
  HWND v9; // rcx
  HDC CompatibleDC; // rdi
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v12; // r14
  HDC v13; // rcx
  HGDIOBJ v14; // rax
  tagRECT Rect; // [rsp+20h] [rbp-38h] BYREF

  if ( !a4 )
    return 2147500035LL;
  if ( *((_BYTE *)this + 96) )
  {
    DC = GetDC(*(this - 10));
    *a4 = DC;
    if ( DC )
    {
      *((_BYTE *)this + 96) = 0;
      if ( (a3 & 1) != 0 )
        return 0;
      v9 = *(this - 10);
      Rect = 0;
      GetClientRect(v9, &Rect);
      if ( (a3 & 4) != 0 )
      {
        CompatibleDC = CreateCompatibleDC(*a4);
        if ( CompatibleDC )
        {
          CompatibleBitmap = CreateCompatibleBitmap(*a4, Rect.right - Rect.left, Rect.bottom - Rect.top);
          v12 = CompatibleBitmap;
          v13 = CompatibleDC;
          if ( !CompatibleBitmap )
          {
LABEL_11:
            DeleteDC(v13);
            goto LABEL_13;
          }
          v14 = SelectObject(CompatibleDC, CompatibleBitmap);
          if ( !v14 )
          {
            DeleteObject(v12);
            v13 = CompatibleDC;
            goto LABEL_11;
          }
          DeleteObject(v14);
          this[11] = (HWND)*a4;
          *a4 = CompatibleDC;
        }
      }
LABEL_13:
      if ( (a3 & 2) != 0 )
        FillRect(*a4, &Rect, (HBRUSH)6);
      return 0;
    }
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18000d2a0  mov     [rsp+arg_8], rbx
0x18000d2a5  mov     [rsp+arg_10], rbp
0x18000d2aa  push    rsi
0x18000d2ab  push    rdi
0x18000d2ac  push    r14
0x18000d2ae  sub     rsp, 40h
0x18000d2b2  mov     rax, cs:__security_cookie
0x18000d2b9  xor     rax, rsp
0x18000d2bc  mov     [rsp+58h+var_28], rax
0x18000d2c1  mov     rbx, r9
0x18000d2c4  mov     ebp, r8d
0x18000d2c7  mov     rsi, rcx
0x18000d2ca  test    r9, r9
0x18000d2cd  jnz     short loc_18000D2D9
0x18000d2cf  mov     eax, 80004003h
0x18000d2d4  jmp     loc_18000D3B3
0x18000d2d9  cmp     byte ptr [rcx+60h], 0
0x18000d2dd  jz      loc_18000D3AE
0x18000d2e3  mov     rcx, [rcx-50h]; hWnd
0x18000d2e7  call    cs:__imp_GetDC
0x18000d2ed  mov     [rbx], rax
0x18000d2f0  test    rax, rax
0x18000d2f3  jz      loc_18000D3AE
0x18000d2f9  mov     byte ptr [rsi+60h], 0
0x18000d2fd  test    bpl, 1
0x18000d301  jnz     loc_18000D3AA
0x18000d307  mov     rcx, [rsi-50h]; hWnd
0x18000d30b  lea     rdx, [rsp+58h+Rect]; lpRect
0x18000d310  xorps   xmm0, xmm0
0x18000d313  movups  xmmword ptr [rsp+58h+Rect.left], xmm0
0x18000d318  call    cs:__imp_GetClientRect
0x18000d31e  test    bpl, 4
0x18000d322  jz      short loc_18000D390
0x18000d324  mov     rcx, [rbx]; hdc
0x18000d327  call    cs:__imp_CreateCompatibleDC
0x18000d32d  mov     rdi, rax
0x18000d330  test    rax, rax
0x18000d333  jz      short loc_18000D390
0x18000d335  mov     r8d, [rsp+58h+Rect.bottom]
0x18000d33a  mov     edx, [rsp+58h+Rect.right]
0x18000d33e  sub     r8d, [rsp+58h+Rect.top]; cy
0x18000d343  sub     edx, [rsp+58h+Rect.left]; cx
0x18000d347  mov     rcx, [rbx]; hdc
0x18000d34a  call    cs:__imp_CreateCompatibleBitmap
0x18000d350  mov     r14, rax
0x18000d353  mov     rcx, rdi; hdc
0x18000d356  test    rax, rax
0x18000d359  jz      short loc_18000D375
0x18000d35b  mov     rdx, rax; h
0x18000d35e  call    cs:__imp_SelectObject
0x18000d364  test    rax, rax
0x18000d367  jnz     short loc_18000D37D
0x18000d369  mov     rcx, r14; ho
0x18000d36c  call    cs:__imp_DeleteObject
0x18000d372  mov     rcx, rdi; hdc
0x18000d375  call    cs:__imp_DeleteDC
0x18000d37b  jmp     short loc_18000D390
0x18000d37d  mov     rcx, rax; ho
0x18000d380  call    cs:__imp_DeleteObject
0x18000d386  mov     rax, [rbx]
0x18000d389  mov     [rsi+58h], rax
0x18000d38d  mov     [rbx], rdi
0x18000d390  test    bpl, 2
0x18000d394  jz      short loc_18000D3AA
0x18000d396  mov     rcx, [rbx]; hDC
0x18000d399  lea     rdx, [rsp+58h+Rect]; lprc
0x18000d39e  mov     r8d, 6; hbr
0x18000d3a4  call    cs:__imp_FillRect
0x18000d3aa  xor     eax, eax
0x18000d3ac  jmp     short loc_18000D3B3
0x18000d3ae  mov     eax, 80004005h
0x18000d3b3  mov     rcx, [rsp+58h+var_28]
0x18000d3b8  xor     rcx, rsp; StackCookie
0x18000d3bb  call    __security_check_cookie
0x18000d3c0  mov     rbx, [rsp+58h+arg_8]
0x18000d3c5  mov     rbp, [rsp+58h+arg_10]
0x18000d3ca  add     rsp, 40h
0x18000d3ce  pop     r14
0x18000d3d0  pop     rdi
0x18000d3d1  pop     rsi
0x18000d3d2  retn
```
