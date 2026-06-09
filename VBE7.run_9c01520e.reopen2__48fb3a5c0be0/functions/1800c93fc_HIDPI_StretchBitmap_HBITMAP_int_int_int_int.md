# HIDPI_StretchBitmap(HBITMAP__ * *,int,int,int,int)

- ea: `0x1800c93fc`
- end: `0x1800c9691`
- name: `?HIDPI_StretchBitmap@@YAHPEAPEAUHBITMAP__@@HHHH@Z`
- size: `661`
- prototype: `__int64 __fastcall(HBITMAP *, int, int, int, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800c64e0`
- `0x1800c9698`

## callees

- `0x1800c93fc`
- `0x180379380`

## import_xrefs

- `KERNEL32!MulDiv` at `0x1800c94ba`
- `KERNEL32!MulDiv` at `0x1800c94cf`
- `KERNEL32!MulDiv` at `0x1800c94ba`
- `KERNEL32!MulDiv` at `0x1800c94cf`
- `USER32!GetDC` at `0x1800c94f3`
- `USER32!GetDC` at `0x1800c94f3`
- `USER32!ReleaseDC` at `0x1800c9550`
- `USER32!ReleaseDC` at `0x1800c9550`
- `GDI32!CreateCompatibleBitmap` at `0x1800c9527`
- `GDI32!CreateCompatibleBitmap` at `0x1800c9527`
- `GDI32!CreateCompatibleDC` at `0x1800c94d9`
- `GDI32!CreateCompatibleDC` at `0x1800c94e6`
- `GDI32!CreateCompatibleDC` at `0x1800c94d9`
- `GDI32!CreateCompatibleDC` at `0x1800c94e6`
- `GDI32!StretchBlt` at `0x1800c95c8`
- `GDI32!StretchBlt` at `0x1800c95c8`
- `GDI32!DeleteDC` at `0x1800c964a`
- `GDI32!DeleteDC` at `0x1800c9653`
- `GDI32!DeleteDC` at `0x1800c964a`
- `GDI32!DeleteDC` at `0x1800c9653`
- `GDI32!GetObjectA` at `0x1800c9478`
- `GDI32!GetObjectA` at `0x1800c9478`
- `GDI32!SelectObject` at `0x1800c9505`
- `GDI32!SelectObject` at `0x1800c953d`
- `GDI32!SelectObject` at `0x1800c962b`
- `GDI32!SelectObject` at `0x1800c9641`
- `GDI32!SelectObject` at `0x1800c9505`
- `GDI32!SelectObject` at `0x1800c953d`
- `GDI32!SelectObject` at `0x1800c962b`
- `GDI32!SelectObject` at `0x1800c9641`
- `GDI32!DeleteObject` at `0x1800c965d`
- `GDI32!DeleteObject` at `0x1800c965d`

## pseudocode

```c
__int64 __fastcall HIDPI_StretchBitmap(HBITMAP *a1, int a2, int a3, int a4, int a5)
{
  unsigned int v5; // edi
  int hDest; // esi
  int v8; // ebp
  HGDIOBJ *v9; // r12
  int wSrc; // r15d
  int v11; // eax
  int hSrc; // r14d
  HDC DC; // rbx
  int v14; // edx
  int ySrc; // r8d
  int v16; // eax
  __int64 v17; // rcx
  int v18; // ebx
  int xSrc; // r13d
  int v21; // [rsp+60h] [rbp-98h]
  int v22; // [rsp+64h] [rbp-94h]
  HDC hdc; // [rsp+68h] [rbp-90h]
  HDC hdcDest; // [rsp+70h] [rbp-88h]
  __int64 v25; // [rsp+78h] [rbp-80h]
  __int64 v26; // [rsp+80h] [rbp-78h]
  HGDIOBJ v27; // [rsp+88h] [rbp-70h]
  HBITMAP CompatibleBitmap; // [rsp+90h] [rbp-68h]
  HGDIOBJ h; // [rsp+98h] [rbp-60h]
  _BYTE pv[4]; // [rsp+A0h] [rbp-58h] BYREF
  int v31; // [rsp+A4h] [rbp-54h]
  int v32; // [rsp+A8h] [rbp-50h]

  v5 = 0;
  hDest = a3;
  v8 = a2;
  v9 = (HGDIOBJ *)a1;
  if ( a1 && *a1 && (a2 || a3) && a4 && a5 && GetObjectA(*a1, 32, pv) )
  {
    wSrc = v31 / a4;
    v11 = v32 / a5;
    hSrc = v32 / a5;
    if ( v31 / a4 != v8 || v11 != hDest )
    {
      if ( v8 )
      {
        if ( !hDest )
          hDest = MulDiv(v8, v11, wSrc);
      }
      else
      {
        v8 = MulDiv(hDest, wSrc, v11);
      }
      hdc = CreateCompatibleDC(0);
      hdcDest = CreateCompatibleDC(0);
      DC = GetDC(0);
      h = SelectObject(hdc, *v9);
      CompatibleBitmap = CreateCompatibleBitmap(DC, a4 * v8, a5 * hDest);
      v27 = SelectObject(hdcDest, CompatibleBitmap);
      ReleaseDC(0, DC);
      v14 = 0;
      v22 = 0;
      ySrc = 0;
      v21 = 0;
      if ( a5 > 0 )
      {
        v16 = a4;
        v17 = (unsigned int)a5;
        v26 = (unsigned int)a5;
        do
        {
          v18 = 0;
          xSrc = 0;
          if ( v16 > 0 )
          {
            v25 = (unsigned int)v16;
            do
            {
              StretchBlt(hdcDest, v18, v14, v8, hDest, hdc, xSrc, ySrc, wSrc, hSrc, 0xCC0020u);
              v14 = v22;
              ySrc = v21;
              v18 += v8;
              xSrc += wSrc;
              --v25;
            }
            while ( v25 );
            v16 = a4;
            v17 = v26;
          }
          v14 += hDest;
          ySrc += hSrc;
          v26 = --v17;
          v22 = v14;
          v21 = ySrc;
        }
        while ( v17 );
        v9 = (HGDIOBJ *)a1;
      }
      SelectObject(hdc, h);
      SelectObject(hdcDest, v27);
      DeleteDC(hdc);
      DeleteDC(hdcDest);
      DeleteObject(*v9);
      *v9 = CompatibleBitmap;
    }
    return 1;
  }
  return v5;
}

```

## disassembly

```asm
0x1800c93fc  mov     [rsp+arg_8], rbx
0x1800c9401  mov     [rsp+arg_18], r9d
0x1800c9406  mov     [rsp+arg_0], rcx
0x1800c940b  push    rbp
0x1800c940c  push    rsi
0x1800c940d  push    rdi
0x1800c940e  push    r12
0x1800c9410  push    r13
0x1800c9412  push    r14
0x1800c9414  push    r15
0x1800c9416  mov     eax, 0C0h
0x1800c941b  call    _alloca_probe
0x1800c9420  sub     rsp, rax
0x1800c9423  xor     edi, edi
0x1800c9425  mov     ebx, r9d
0x1800c9428  mov     esi, r8d
0x1800c942b  mov     ebp, edx
0x1800c942d  mov     r12, rcx
0x1800c9430  test    rcx, rcx
0x1800c9433  jz      loc_1800C9674
0x1800c9439  cmp     [rcx], rdi
0x1800c943c  jz      loc_1800C9674
0x1800c9442  test    edx, edx
0x1800c9444  jnz     short loc_1800C944F
0x1800c9446  test    r8d, r8d
0x1800c9449  jz      loc_1800C9674
0x1800c944f  test    ebx, ebx
0x1800c9451  jz      loc_1800C9674
0x1800c9457  mov     r13d, [rsp+0F8h+arg_20]
0x1800c945f  test    r13d, r13d
0x1800c9462  jz      loc_1800C9674
0x1800c9468  mov     rcx, [rcx]; h
0x1800c946b  lea     r8, [rsp+0F8h+pv]; pv
0x1800c9473  mov     edx, 20h ; ' '; c
0x1800c9478  call    cs:__imp_GetObjectA
0x1800c947e  test    eax, eax
0x1800c9480  jz      loc_1800C9674
0x1800c9486  mov     eax, [rsp+0F8h+var_54]
0x1800c948d  cdq
0x1800c948e  idiv    ebx
0x1800c9490  mov     r15d, eax
0x1800c9493  mov     eax, [rsp+0F8h+var_50]
0x1800c949a  cdq
0x1800c949b  idiv    r13d
0x1800c949e  mov     r14d, eax
0x1800c94a1  cmp     r15d, ebp
0x1800c94a4  jnz     short loc_1800C94AE
0x1800c94a6  cmp     eax, esi
0x1800c94a8  jz      loc_1800C966F
0x1800c94ae  test    ebp, ebp
0x1800c94b0  jnz     short loc_1800C94C4
0x1800c94b2  mov     r8d, eax; nDenominator
0x1800c94b5  mov     edx, r15d; nNumerator
0x1800c94b8  mov     ecx, esi; nNumber
0x1800c94ba  call    cs:__imp_MulDiv
0x1800c94c0  mov     ebp, eax
0x1800c94c2  jmp     short loc_1800C94D7
0x1800c94c4  test    esi, esi
0x1800c94c6  jnz     short loc_1800C94D7
0x1800c94c8  mov     r8d, r15d; nDenominator
0x1800c94cb  mov     edx, eax; nNumerator
0x1800c94cd  mov     ecx, ebp; nNumber
0x1800c94cf  call    cs:__imp_MulDiv
0x1800c94d5  mov     esi, eax
0x1800c94d7  xor     ecx, ecx; hdc
0x1800c94d9  call    cs:__imp_CreateCompatibleDC
0x1800c94df  xor     ecx, ecx; hdc
0x1800c94e1  mov     [rsp+0F8h+hdc], rax
0x1800c94e6  call    cs:__imp_CreateCompatibleDC
0x1800c94ec  xor     ecx, ecx; hWnd
0x1800c94ee  mov     [rsp+0F8h+hdcDest], rax
0x1800c94f3  call    cs:__imp_GetDC
0x1800c94f9  mov     rdx, [r12]; h
0x1800c94fd  mov     rcx, [rsp+0F8h+hdc]; hdc
0x1800c9502  mov     rbx, rax
0x1800c9505  call    cs:__imp_SelectObject
0x1800c950b  mov     edx, ebp
0x1800c950d  mov     r8d, esi
0x1800c9510  mov     rcx, rbx; hdc
0x1800c9513  mov     [rsp+0F8h+h], rax
0x1800c951b  imul    edx, [rsp+0F8h+arg_18]; cx
0x1800c9523  imul    r8d, r13d; cy
0x1800c9527  call    cs:__imp_CreateCompatibleBitmap
0x1800c952d  mov     rcx, [rsp+0F8h+hdcDest]; hdc
0x1800c9532  mov     rdx, rax; h
0x1800c9535  mov     [rsp+0F8h+var_68], rax
0x1800c953d  call    cs:__imp_SelectObject
0x1800c9543  mov     rdx, rbx; hDC
0x1800c9546  xor     ecx, ecx; hWnd
0x1800c9548  mov     [rsp+0F8h+var_70], rax
0x1800c9550  call    cs:__imp_ReleaseDC
0x1800c9556  mov     edx, edi
0x1800c9558  mov     [rsp+0F8h+var_94], edx
0x1800c955c  mov     r8d, edi
0x1800c955f  mov     [rsp+0F8h+var_98], edi
0x1800c9563  test    r13d, r13d
0x1800c9566  jle     loc_1800C961B
0x1800c956c  mov     eax, [rsp+0F8h+arg_18]
0x1800c9573  mov     r12, [rsp+0F8h+hdc]
0x1800c9578  mov     rcx, r13
0x1800c957b  mov     [rsp+0F8h+var_78], rcx
0x1800c9583  mov     ebx, edi
0x1800c9585  mov     r13d, edi
0x1800c9588  test    eax, eax
0x1800c958a  jle     short loc_1800C95F4
0x1800c958c  mov     rdi, [rsp+0F8h+hdcDest]
0x1800c9591  mov     ecx, eax
0x1800c9593  mov     [rsp+0F8h+var_80], rcx
0x1800c9598  mov     [rsp+0F8h+rop], 0CC0020h; rop
0x1800c95a0  mov     [rsp+0F8h+hSrc], r14d; hSrc
0x1800c95a5  mov     [rsp+0F8h+wSrc], r15d; wSrc
0x1800c95aa  mov     [rsp+0F8h+ySrc], r8d; ySrc
0x1800c95af  mov     r8d, edx; yDest
0x1800c95b2  mov     [rsp+0F8h+xSrc], r13d; xSrc
0x1800c95b7  mov     edx, ebx; xDest
0x1800c95b9  mov     r9d, ebp; wDest
0x1800c95bc  mov     rcx, rdi; hdcDest
0x1800c95bf  mov     [rsp+0F8h+hdcSrc], r12; hdcSrc
0x1800c95c4  mov     [rsp+0F8h+hDest], esi; hDest
0x1800c95c8  call    cs:__imp_StretchBlt
0x1800c95ce  mov     edx, [rsp+0F8h+var_94]
0x1800c95d2  mov     r8d, [rsp+0F8h+var_98]
0x1800c95d7  add     ebx, ebp
0x1800c95d9  add     r13d, r15d
0x1800c95dc  dec     [rsp+0F8h+var_80]
0x1800c95e1  jnz     short loc_1800C9598
0x1800c95e3  mov     eax, [rsp+0F8h+arg_18]
0x1800c95ea  mov     rcx, [rsp+0F8h+var_78]
0x1800c95f2  xor     edi, edi
0x1800c95f4  add     edx, esi
0x1800c95f6  add     r8d, r14d
0x1800c95f9  dec     rcx
0x1800c95fc  mov     [rsp+0F8h+var_78], rcx
0x1800c9604  mov     [rsp+0F8h+var_94], edx
0x1800c9608  mov     [rsp+0F8h+var_98], r8d
0x1800c960d  jnz     loc_1800C9583
0x1800c9613  mov     r12, [rsp+0F8h+arg_0]
0x1800c961b  mov     rbx, [rsp+0F8h+hdc]
0x1800c9620  mov     rdx, [rsp+0F8h+h]; h
0x1800c9628  mov     rcx, rbx; hdc
0x1800c962b  call    cs:__imp_SelectObject
0x1800c9631  mov     rdi, [rsp+0F8h+hdcDest]
0x1800c9636  mov     rdx, [rsp+0F8h+var_70]; h
0x1800c963e  mov     rcx, rdi; hdc
0x1800c9641  call    cs:__imp_SelectObject
0x1800c9647  mov     rcx, rbx; hdc
0x1800c964a  call    cs:__imp_DeleteDC
0x1800c9650  mov     rcx, rdi; hdc
0x1800c9653  call    cs:__imp_DeleteDC
0x1800c9659  mov     rcx, [r12]; ho
0x1800c965d  call    cs:__imp_DeleteObject
0x1800c9663  mov     r11, [rsp+0F8h+var_68]
0x1800c966b  mov     [r12], r11
0x1800c966f  mov     edi, 1
0x1800c9674  mov     eax, edi
0x1800c9676  mov     rbx, [rsp+0F8h+arg_8]
0x1800c967e  add     rsp, 0C0h
0x1800c9685  pop     r15
0x1800c9687  pop     r14
0x1800c9689  pop     r13
0x1800c968b  pop     r12
0x1800c968d  pop     rdi
0x1800c968e  pop     rsi
0x1800c968f  pop     rbp
0x1800c9690  retn
```
