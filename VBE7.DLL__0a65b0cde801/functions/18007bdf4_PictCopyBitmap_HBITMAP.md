# _PictCopyBitmap(HBITMAP__ *)

- ea: `0x18007bdf4`
- end: `0x18007bf5e`
- name: `?_PictCopyBitmap@@YAPEAUHBITMAP__@@PEAU1@@Z`
- size: `362`
- prototype: `HBITMAP __fastcall(HBITMAP)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18007bd0c`

## callees

- `0x18007bdf4`
- `0x180379380`

## import_xrefs

- `USER32!GetDC` at `0x18007be38`
- `USER32!GetDC` at `0x18007be38`
- `USER32!ReleaseDC` at `0x18007bf1c`
- `USER32!ReleaseDC` at `0x18007bf1c`
- `GDI32!CreateCompatibleBitmap` at `0x18007be80`
- `GDI32!CreateCompatibleBitmap` at `0x18007be80`
- `GDI32!CreateCompatibleDC` at `0x18007be4d`
- `GDI32!CreateCompatibleDC` at `0x18007be62`
- `GDI32!CreateCompatibleDC` at `0x18007be4d`
- `GDI32!CreateCompatibleDC` at `0x18007be62`
- `GDI32!StretchBlt` at `0x18007bee5`
- `GDI32!StretchBlt` at `0x18007bee5`
- `GDI32!DeleteDC` at `0x18007bf2a`
- `GDI32!DeleteDC` at `0x18007bf38`
- `GDI32!DeleteDC` at `0x18007bf2a`
- `GDI32!DeleteDC` at `0x18007bf38`
- `GDI32!GetObjectA` at `0x18007be25`
- `GDI32!GetObjectA` at `0x18007be25`
- `GDI32!SelectObject` at `0x18007be98`
- `GDI32!SelectObject` at `0x18007bea7`
- `GDI32!SelectObject` at `0x18007bef3`
- `GDI32!SelectObject` at `0x18007beff`
- `GDI32!SelectObject` at `0x18007be98`
- `GDI32!SelectObject` at `0x18007bea7`
- `GDI32!SelectObject` at `0x18007bef3`
- `GDI32!SelectObject` at `0x18007beff`
- `GDI32!DeleteObject` at `0x18007bf0f`
- `GDI32!DeleteObject` at `0x18007bf0f`

## pseudocode

```c
HBITMAP __fastcall _PictCopyBitmap(HBITMAP a1)
{
  int v1; // eax
  HDC CompatibleDC; // r14
  HBITMAP CompatibleBitmap; // rdi
  HDC DC; // rax
  HDC v7; // rbp
  HDC hdcSrc; // r15
  HGDIOBJ v9; // rsi
  HGDIOBJ v10; // rdi
  BOOL v11; // ebx
  HBITMAP v12; // rax
  _BYTE pv[4]; // [rsp+60h] [rbp-38h] BYREF
  int wDest; // [rsp+64h] [rbp-34h]
  int cy; // [rsp+68h] [rbp-30h]

  CompatibleDC = 0;
  CompatibleBitmap = 0;
  if ( !GetObjectA(a1, v1 - 96, pv) )
    return 0;
  DC = GetDC(0);
  v7 = DC;
  if ( DC )
  {
    hdcSrc = CreateCompatibleDC(DC);
    if ( hdcSrc )
    {
      CompatibleDC = CreateCompatibleDC(v7);
      if ( CompatibleDC )
      {
        CompatibleBitmap = CreateCompatibleBitmap(v7, wDest, cy);
        if ( CompatibleBitmap )
        {
          v9 = SelectObject(hdcSrc, a1);
          v10 = SelectObject(CompatibleDC, CompatibleBitmap);
          v11 = StretchBlt(CompatibleDC, 0, 0, wDest, cy, hdcSrc, 0, 0, wDest, cy, 0xCC0020u);
          SelectObject(hdcSrc, v9);
          v12 = (HBITMAP)SelectObject(CompatibleDC, v10);
          CompatibleBitmap = v12;
          if ( !v11 )
          {
            DeleteObject(v12);
            CompatibleBitmap = 0;
          }
        }
      }
    }
    ReleaseDC(0, v7);
    if ( hdcSrc )
      DeleteDC(hdcSrc);
    if ( CompatibleDC )
      DeleteDC(CompatibleDC);
  }
  return CompatibleBitmap;
}

```

## disassembly

```asm
0x18007bdf4  mov     [rsp+arg_0], rbx
0x18007bdf9  mov     [rsp+arg_8], rbp
0x18007bdfe  mov     [rsp+arg_10], rsi
0x18007be03  push    rdi
0x18007be04  push    r14
0x18007be06  push    r15
0x18007be08  mov     eax, 80h
0x18007be0d  call    _alloca_probe
0x18007be12  sub     rsp, rax
0x18007be15  lea     r8, [rsp+98h+pv]; pv
0x18007be1a  lea     edx, [rax-60h]; c
0x18007be1d  mov     rbx, rcx
0x18007be20  xor     r14d, r14d
0x18007be23  xor     edi, edi
0x18007be25  call    cs:__imp_GetObjectA
0x18007be2b  test    eax, eax
0x18007be2d  jnz     short loc_18007BE36
0x18007be2f  xor     eax, eax
0x18007be31  jmp     loc_18007BF41
0x18007be36  xor     ecx, ecx; hWnd
0x18007be38  call    cs:__imp_GetDC
0x18007be3e  mov     rbp, rax
0x18007be41  test    rax, rax
0x18007be44  jz      loc_18007BF3E
0x18007be4a  mov     rcx, rax; hdc
0x18007be4d  call    cs:__imp_CreateCompatibleDC
0x18007be53  mov     r15, rax
0x18007be56  test    rax, rax
0x18007be59  jz      loc_18007BF17
0x18007be5f  mov     rcx, rbp; hdc
0x18007be62  call    cs:__imp_CreateCompatibleDC
0x18007be68  mov     r14, rax
0x18007be6b  test    rax, rax
0x18007be6e  jz      loc_18007BF17
0x18007be74  mov     r8d, [rsp+98h+cy]; cy
0x18007be79  mov     edx, [rsp+98h+wDest]; cx
0x18007be7d  mov     rcx, rbp; hdc
0x18007be80  call    cs:__imp_CreateCompatibleBitmap
0x18007be86  mov     rdi, rax
0x18007be89  test    rax, rax
0x18007be8c  jz      loc_18007BF17
0x18007be92  mov     rdx, rbx; h
0x18007be95  mov     rcx, r15; hdc
0x18007be98  call    cs:__imp_SelectObject
0x18007be9e  mov     rdx, rdi; h
0x18007bea1  mov     rcx, r14; hdc
0x18007bea4  mov     rsi, rax
0x18007bea7  call    cs:__imp_SelectObject
0x18007bead  mov     ecx, [rsp+98h+cy]
0x18007beb1  mov     r9d, [rsp+98h+wDest]; wDest
0x18007beb6  mov     [rsp+98h+rop], 0CC0020h; rop
0x18007bebe  mov     [rsp+98h+hSrc], ecx; hSrc
0x18007bec2  mov     [rsp+98h+wSrc], r9d; wSrc
0x18007bec7  and     [rsp+98h+var_60], 0
0x18007becc  and     [rsp+98h+var_68], 0
0x18007bed1  mov     [rsp+98h+hdcSrc], r15; hdcSrc
0x18007bed6  mov     [rsp+98h+hDest], ecx; hDest
0x18007beda  xor     r8d, r8d; yDest
0x18007bedd  mov     rcx, r14; hdcDest
0x18007bee0  xor     edx, edx; xDest
0x18007bee2  mov     rdi, rax
0x18007bee5  call    cs:__imp_StretchBlt
0x18007beeb  mov     rdx, rsi; h
0x18007beee  mov     rcx, r15; hdc
0x18007bef1  mov     ebx, eax
0x18007bef3  call    cs:__imp_SelectObject
0x18007bef9  mov     rdx, rdi; h
0x18007befc  mov     rcx, r14; hdc
0x18007beff  call    cs:__imp_SelectObject
0x18007bf05  mov     rdi, rax
0x18007bf08  test    ebx, ebx
0x18007bf0a  jnz     short loc_18007BF17
0x18007bf0c  mov     rcx, rax; ho
0x18007bf0f  call    cs:__imp_DeleteObject
0x18007bf15  xor     edi, edi
0x18007bf17  mov     rdx, rbp; hDC
0x18007bf1a  xor     ecx, ecx; hWnd
0x18007bf1c  call    cs:__imp_ReleaseDC
0x18007bf22  test    r15, r15
0x18007bf25  jz      short loc_18007BF30
0x18007bf27  mov     rcx, r15; hdc
0x18007bf2a  call    cs:__imp_DeleteDC
0x18007bf30  test    r14, r14
0x18007bf33  jz      short loc_18007BF3E
0x18007bf35  mov     rcx, r14; hdc
0x18007bf38  call    cs:__imp_DeleteDC
0x18007bf3e  mov     rax, rdi
0x18007bf41  lea     r11, [rsp+98h+var_18]
0x18007bf49  mov     rbx, [r11+20h]
0x18007bf4d  mov     rbp, [r11+28h]
0x18007bf51  mov     rsi, [r11+30h]
0x18007bf55  mov     rsp, r11
0x18007bf58  pop     r15
0x18007bf5a  pop     r14
0x18007bf5c  pop     rdi
0x18007bf5d  retn
```
