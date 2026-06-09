# HIDPI_StretchBitmaps(HBITMAP__ * *,int,int,int,int)

- ea: `0x18030ab1c`
- end: `0x18030add1`
- name: `?HIDPI_StretchBitmaps@@YAHPEAPEAUHBITMAP__@@HHHH@Z`
- size: `693`
- prototype: `__int64 __fastcall(HBITMAP *, int, int, int, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180308720`
- `0x180308d2c`

## callees

- `0x18030ab1c`

## import_xrefs

- `KERNEL32!MulDiv` at `0x18030abe3`
- `KERNEL32!MulDiv` at `0x18030ac00`
- `KERNEL32!MulDiv` at `0x18030abe3`
- `KERNEL32!MulDiv` at `0x18030ac00`
- `USER32!GetDC` at `0x18030ac23`
- `USER32!GetDC` at `0x18030ac23`
- `USER32!ReleaseDC` at `0x18030ac7b`
- `USER32!ReleaseDC` at `0x18030ac7b`
- `GDI32!CreateCompatibleBitmap` at `0x18030ac59`
- `GDI32!CreateCompatibleBitmap` at `0x18030ac59`
- `GDI32!CreateCompatibleDC` at `0x18030ac0b`
- `GDI32!CreateCompatibleDC` at `0x18030ac17`
- `GDI32!CreateCompatibleDC` at `0x18030ac0b`
- `GDI32!CreateCompatibleDC` at `0x18030ac17`
- `GDI32!StretchBlt` at `0x18030ad66`
- `GDI32!StretchBlt` at `0x18030ad66`
- `GDI32!DeleteDC` at `0x18030ad96`
- `GDI32!DeleteDC` at `0x18030ada0`
- `GDI32!DeleteDC` at `0x18030ad96`
- `GDI32!DeleteDC` at `0x18030ada0`
- `GDI32!GetObjectA` at `0x18030ab84`
- `GDI32!GetObjectA` at `0x18030ab84`
- `GDI32!SelectObject` at `0x18030ac38`
- `GDI32!SelectObject` at `0x18030ac6b`
- `GDI32!SelectObject` at `0x18030ad7e`
- `GDI32!SelectObject` at `0x18030ad8c`
- `GDI32!SelectObject` at `0x18030ac38`
- `GDI32!SelectObject` at `0x18030ac6b`
- `GDI32!SelectObject` at `0x18030ad7e`
- `GDI32!SelectObject` at `0x18030ad8c`
- `GDI32!DeleteObject` at `0x18030adad`
- `GDI32!DeleteObject` at `0x18030adad`

## pseudocode

```c
__int64 __fastcall HIDPI_StretchBitmaps(HBITMAP *a1, int a2, int a3, int a4, int a5)
{
  int nDenominator; // [rsp+60h] [rbp-80h]
  int nNumerator; // [rsp+64h] [rbp-7Ch]
  int xDest; // [rsp+68h] [rbp-78h]
  int xSrc; // [rsp+6Ch] [rbp-74h]
  int yDest; // [rsp+70h] [rbp-70h]
  int ySrc; // [rsp+74h] [rbp-6Ch]
  int v12; // [rsp+78h] [rbp-68h]
  int v13; // [rsp+7Ch] [rbp-64h]
  unsigned int v14; // [rsp+80h] [rbp-60h]
  HDC hdc; // [rsp+88h] [rbp-58h]
  HDC hdcDest; // [rsp+90h] [rbp-50h]
  HBITMAP h; // [rsp+98h] [rbp-48h]
  HDC hDC; // [rsp+A0h] [rbp-40h]
  HGDIOBJ v19; // [rsp+A8h] [rbp-38h]
  HGDIOBJ v20; // [rsp+B0h] [rbp-30h]
  _BYTE pv[4]; // [rsp+B8h] [rbp-28h] BYREF
  int v22; // [rsp+BCh] [rbp-24h]
  int v23; // [rsp+C0h] [rbp-20h]
  int wDest; // [rsp+F8h] [rbp+18h]
  int nNumber; // [rsp+100h] [rbp+20h]

  nNumber = a3;
  wDest = a2;
  v14 = 0;
  if ( a1 && *a1 && (a2 || a3) && a4 && a5 && GetObjectA(*a1, 32, pv) )
  {
    nNumerator = v22 / a4;
    nDenominator = v23 / a5;
    if ( v22 / a4 == wDest && nDenominator == nNumber )
    {
      return 1;
    }
    else
    {
      if ( wDest )
      {
        if ( !nNumber )
          nNumber = MulDiv(wDest, nDenominator, nNumerator);
      }
      else
      {
        wDest = MulDiv(nNumber, nNumerator, nDenominator);
      }
      hdc = CreateCompatibleDC(0);
      hdcDest = CreateCompatibleDC(0);
      hDC = GetDC(0);
      v19 = SelectObject(hdc, *a1);
      h = CreateCompatibleBitmap(hDC, a4 * wDest, a5 * nNumber);
      v20 = SelectObject(hdcDest, h);
      ReleaseDC(0, hDC);
      v12 = 0;
      yDest = 0;
      ySrc = 0;
      while ( v12 < a5 )
      {
        v13 = 0;
        xDest = 0;
        xSrc = 0;
        while ( v13 < a4 )
        {
          StretchBlt(hdcDest, xDest, yDest, wDest, nNumber, hdc, xSrc, ySrc, nNumerator, nDenominator, 0xCC0020u);
          ++v13;
          xDest += wDest;
          xSrc += nNumerator;
        }
        ++v12;
        yDest += nNumber;
        ySrc += nDenominator;
      }
      SelectObject(hdc, v19);
      SelectObject(hdcDest, v20);
      DeleteDC(hdc);
      DeleteDC(hdcDest);
      DeleteObject(*a1);
      *a1 = h;
      return 1;
    }
  }
  return v14;
}

```

## disassembly

```asm
0x18030ab1c  mov     [rsp-8+arg_18], r9d
0x18030ab21  mov     [rsp-8+nNumber], r8d
0x18030ab26  mov     [rsp-8+wDest], edx
0x18030ab2a  mov     [rsp-8+arg_0], rcx
0x18030ab2f  push    rbp
0x18030ab30  mov     rbp, rsp
0x18030ab33  sub     rsp, 0E0h
0x18030ab3a  mov     [rbp+var_60], 0
0x18030ab41  cmp     [rbp+arg_0], 0
0x18030ab46  jz      short loc_18030AB6A
0x18030ab48  mov     rax, [rbp+arg_0]
0x18030ab4c  cmp     qword ptr [rax], 0
0x18030ab50  jz      short loc_18030AB6A
0x18030ab52  cmp     [rbp+wDest], 0
0x18030ab56  jnz     short loc_18030AB5E
0x18030ab58  cmp     [rbp+nNumber], 0
0x18030ab5c  jz      short loc_18030AB6A
0x18030ab5e  cmp     [rbp+arg_18], 0
0x18030ab62  jz      short loc_18030AB6A
0x18030ab64  cmp     [rbp+arg_20], 0
0x18030ab68  jnz     short loc_18030AB74
0x18030ab6a  jmp     loc_18030ADC5
0x18030ab6f  jmp     loc_18030ADC5
0x18030ab74  lea     r8, [rbp+pv]; pv
0x18030ab78  mov     edx, 20h ; ' '; c
0x18030ab7d  mov     rax, [rbp+arg_0]
0x18030ab81  mov     rcx, [rax]; h
0x18030ab84  call    cs:__imp_GetObjectA
0x18030ab8a  test    eax, eax
0x18030ab8c  jnz     short loc_18030AB98
0x18030ab8e  jmp     loc_18030ADC5
0x18030ab93  jmp     loc_18030ADC5
0x18030ab98  mov     eax, [rbp+var_24]
0x18030ab9b  cdq
0x18030ab9c  idiv    [rbp+arg_18]
0x18030ab9f  mov     [rsp+0E0h+nNumerator], eax
0x18030aba3  mov     eax, [rbp+var_20]
0x18030aba6  cdq
0x18030aba7  idiv    [rbp+arg_20]
0x18030abaa  mov     [rsp+0E0h+nDenominator], eax
0x18030abae  mov     eax, [rbp+wDest]
0x18030abb1  cmp     [rsp+0E0h+nNumerator], eax
0x18030abb5  jnz     short loc_18030ABD1
0x18030abb7  mov     eax, [rbp+nNumber]
0x18030abba  cmp     [rsp+0E0h+nDenominator], eax
0x18030abbe  jnz     short loc_18030ABD1
0x18030abc0  mov     [rbp+var_60], 1
0x18030abc7  jmp     loc_18030ADC5
0x18030abcc  jmp     loc_18030ADC5
0x18030abd1  cmp     [rbp+wDest], 0
0x18030abd5  jnz     short loc_18030ABEE
0x18030abd7  mov     r8d, [rsp+0E0h+nDenominator]; nDenominator
0x18030abdc  mov     edx, [rsp+0E0h+nNumerator]; nNumerator
0x18030abe0  mov     ecx, [rbp+nNumber]; nNumber
0x18030abe3  call    cs:__imp_MulDiv
0x18030abe9  mov     [rbp+wDest], eax
0x18030abec  jmp     short loc_18030AC09
0x18030abee  cmp     [rbp+nNumber], 0
0x18030abf2  jnz     short loc_18030AC09
0x18030abf4  mov     r8d, [rsp+0E0h+nNumerator]; nDenominator
0x18030abf9  mov     edx, [rsp+0E0h+nDenominator]; nNumerator
0x18030abfd  mov     ecx, [rbp+wDest]; nNumber
0x18030ac00  call    cs:__imp_MulDiv
0x18030ac06  mov     [rbp+nNumber], eax
0x18030ac09  xor     ecx, ecx; hdc
0x18030ac0b  call    cs:__imp_CreateCompatibleDC
0x18030ac11  mov     [rbp+hdc], rax
0x18030ac15  xor     ecx, ecx; hdc
0x18030ac17  call    cs:__imp_CreateCompatibleDC
0x18030ac1d  mov     [rbp+hdcDest], rax
0x18030ac21  xor     ecx, ecx; hWnd
0x18030ac23  call    cs:__imp_GetDC
0x18030ac29  mov     [rbp+hDC], rax
0x18030ac2d  mov     rax, [rbp+arg_0]
0x18030ac31  mov     rdx, [rax]; h
0x18030ac34  mov     rcx, [rbp+hdc]; hdc
0x18030ac38  call    cs:__imp_SelectObject
0x18030ac3e  mov     [rbp+var_38], rax
0x18030ac42  mov     eax, [rbp+nNumber]
0x18030ac45  imul    eax, [rbp+arg_20]
0x18030ac49  mov     ecx, [rbp+wDest]
0x18030ac4c  imul    ecx, [rbp+arg_18]
0x18030ac50  mov     r8d, eax; cy
0x18030ac53  mov     edx, ecx; cx
0x18030ac55  mov     rcx, [rbp+hDC]; hdc
0x18030ac59  call    cs:__imp_CreateCompatibleBitmap
0x18030ac5f  mov     [rbp+h], rax
0x18030ac63  mov     rdx, [rbp+h]; h
0x18030ac67  mov     rcx, [rbp+hdcDest]; hdc
0x18030ac6b  call    cs:__imp_SelectObject
0x18030ac71  mov     [rbp+var_30], rax
0x18030ac75  mov     rdx, [rbp+hDC]; hDC
0x18030ac79  xor     ecx, ecx; hWnd
0x18030ac7b  call    cs:__imp_ReleaseDC
0x18030ac81  mov     [rsp+0E0h+var_68], 0
0x18030ac89  mov     [rsp+0E0h+yDest], 0
0x18030ac91  mov     [rsp+0E0h+var_6C], 0
0x18030ac99  jmp     short loc_18030ACC4
0x18030ac9b  mov     eax, [rsp+0E0h+var_68]
0x18030ac9f  inc     eax
0x18030aca1  mov     [rsp+0E0h+var_68], eax
0x18030aca5  mov     eax, [rbp+nNumber]
0x18030aca8  mov     ecx, [rsp+0E0h+yDest]
0x18030acac  add     ecx, eax
0x18030acae  mov     eax, ecx
0x18030acb0  mov     [rsp+0E0h+yDest], eax
0x18030acb4  mov     eax, [rsp+0E0h+nDenominator]
0x18030acb8  mov     ecx, [rsp+0E0h+var_6C]
0x18030acbc  add     ecx, eax
0x18030acbe  mov     eax, ecx
0x18030acc0  mov     [rsp+0E0h+var_6C], eax
0x18030acc4  mov     eax, [rbp+arg_20]
0x18030acc7  cmp     [rsp+0E0h+var_68], eax
0x18030accb  jge     loc_18030AD76
0x18030acd1  mov     [rsp+0E0h+var_64], 0
0x18030acd9  mov     [rsp+0E0h+xDest], 0
0x18030ace1  mov     [rsp+0E0h+var_74], 0
0x18030ace9  jmp     short loc_18030AD14
0x18030aceb  mov     eax, [rsp+0E0h+var_64]
0x18030acef  inc     eax
0x18030acf1  mov     [rsp+0E0h+var_64], eax
0x18030acf5  mov     eax, [rbp+wDest]
0x18030acf8  mov     ecx, [rsp+0E0h+xDest]
0x18030acfc  add     ecx, eax
0x18030acfe  mov     eax, ecx
0x18030ad00  mov     [rsp+0E0h+xDest], eax
0x18030ad04  mov     eax, [rsp+0E0h+nNumerator]
0x18030ad08  mov     ecx, [rsp+0E0h+var_74]
0x18030ad0c  add     ecx, eax
0x18030ad0e  mov     eax, ecx
0x18030ad10  mov     [rsp+0E0h+var_74], eax
0x18030ad14  mov     eax, [rbp+arg_18]
0x18030ad17  cmp     [rsp+0E0h+var_64], eax
0x18030ad1b  jge     short loc_18030AD71
0x18030ad1d  mov     [rsp+0E0h+rop], 0CC0020h; rop
0x18030ad25  mov     eax, [rsp+0E0h+nDenominator]
0x18030ad29  mov     [rsp+0E0h+hSrc], eax; hSrc
0x18030ad2d  mov     eax, [rsp+0E0h+nNumerator]
0x18030ad31  mov     [rsp+0E0h+wSrc], eax; wSrc
0x18030ad35  mov     eax, [rsp+0E0h+var_6C]
0x18030ad39  mov     [rsp+0E0h+ySrc], eax; ySrc
0x18030ad3d  mov     eax, [rsp+0E0h+var_74]
0x18030ad41  mov     [rsp+0E0h+xSrc], eax; xSrc
0x18030ad45  mov     rax, [rbp+hdc]
0x18030ad49  mov     [rsp+0E0h+hdcSrc], rax; hdcSrc
0x18030ad4e  mov     eax, [rbp+nNumber]
0x18030ad51  mov     [rsp+0E0h+hDest], eax; hDest
0x18030ad55  mov     r9d, [rbp+wDest]; wDest
0x18030ad59  mov     r8d, [rsp+0E0h+yDest]; yDest
0x18030ad5e  mov     edx, [rsp+0E0h+xDest]; xDest
0x18030ad62  mov     rcx, [rbp+hdcDest]; hdcDest
0x18030ad66  call    cs:__imp_StretchBlt
0x18030ad6c  jmp     loc_18030ACEB
0x18030ad71  jmp     loc_18030AC9B
0x18030ad76  mov     rdx, [rbp+var_38]; h
0x18030ad7a  mov     rcx, [rbp+hdc]; hdc
0x18030ad7e  call    cs:__imp_SelectObject
0x18030ad84  mov     rdx, [rbp+var_30]; h
0x18030ad88  mov     rcx, [rbp+hdcDest]; hdc
0x18030ad8c  call    cs:__imp_SelectObject
0x18030ad92  mov     rcx, [rbp+hdc]; hdc
0x18030ad96  call    cs:__imp_DeleteDC
0x18030ad9c  mov     rcx, [rbp+hdcDest]; hdc
0x18030ada0  call    cs:__imp_DeleteDC
0x18030ada6  mov     rax, [rbp+arg_0]
0x18030adaa  mov     rcx, [rax]; ho
0x18030adad  call    cs:__imp_DeleteObject
0x18030adb3  mov     rax, [rbp+arg_0]
0x18030adb7  mov     rcx, [rbp+h]
0x18030adbb  mov     [rax], rcx
0x18030adbe  mov     [rbp+var_60], 1
0x18030adc5  mov     eax, [rbp+var_60]
0x18030adc8  add     rsp, 0E0h
0x18030adcf  pop     rbp
0x18030add0  retn
```
