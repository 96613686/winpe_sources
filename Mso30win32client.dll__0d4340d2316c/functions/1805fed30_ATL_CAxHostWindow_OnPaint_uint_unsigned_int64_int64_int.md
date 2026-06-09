# ATL::CAxHostWindow::OnPaint(uint,unsigned __int64,__int64,int &)

- ea: `0x1805fed30`
- end: `0x1805fef6a`
- name: `?OnPaint@CAxHostWindow@ATL@@QEAA_JI_K_JAEAH@Z`
- size: `570`
- prototype: `__int64 __fastcall(ATL::CAxHostWindow *__hidden this, unsigned int, unsigned __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1805f0020`

## callees

- `0x180192520`
- `0x180192560`
- `0x1805fed30`

## import_xrefs

- `GDI32!BitBlt` at `0x1805feeb0`
- `GDI32!BitBlt` at `0x1805feeb0`
- `GDI32!SelectObject` at `0x1805fede4`
- `GDI32!SelectObject` at `0x1805feebc`
- `GDI32!SelectObject` at `0x1805fede4`
- `GDI32!SelectObject` at `0x1805feebc`
- `GDI32!DeleteDC` at `0x1805feec5`
- `GDI32!DeleteDC` at `0x1805feec5`
- `GDI32!DeleteObject` at `0x1805fee21`
- `GDI32!DeleteObject` at `0x1805fef4b`
- `GDI32!DeleteObject` at `0x1805fee21`
- `GDI32!DeleteObject` at `0x1805fef4b`
- `GDI32!CreateSolidBrush` at `0x1805fedfc`
- `GDI32!CreateSolidBrush` at `0x1805fef2a`
- `GDI32!CreateSolidBrush` at `0x1805fedfc`
- `GDI32!CreateSolidBrush` at `0x1805fef2a`
- `GDI32!CreateCompatibleDC` at `0x1805fedcc`
- `GDI32!CreateCompatibleDC` at `0x1805fedcc`
- `GDI32!CreateCompatibleBitmap` at `0x1805fedb7`
- `GDI32!CreateCompatibleBitmap` at `0x1805fedb7`
- `USER32!GetClientRect` at `0x1805feda0`
- `USER32!GetClientRect` at `0x1805fef1e`
- `USER32!GetClientRect` at `0x1805feda0`
- `USER32!GetClientRect` at `0x1805fef1e`
- `USER32!FillRect` at `0x1805fee18`
- `USER32!FillRect` at `0x1805fef42`
- `USER32!FillRect` at `0x1805fee18`
- `USER32!FillRect` at `0x1805fef42`
- `USER32!EndPaint` at `0x1805fef59`
- `USER32!EndPaint` at `0x1805fef59`
- `USER32!BeginPaint` at `0x1805fed86`
- `USER32!BeginPaint` at `0x1805fef08`
- `USER32!BeginPaint` at `0x1805fed86`
- `USER32!BeginPaint` at `0x1805fef08`

## pseudocode

```c
__int64 __fastcall ATL::CAxHostWindow::OnPaint(ATL::CAxHostWindow *this, __int64 a2, __int64 a3, __int64 a4, int *a5)
{
  HDC v6; // rsi
  HBITMAP CompatibleBitmap; // r14
  HDC CompatibleDC; // rax
  HDC hdcSrc; // rdi
  HGDIOBJ v10; // r15
  HBRUSH SolidBrush; // rax
  HBRUSH v12; // r12
  HBITMAP v13; // rcx
  HDC v15; // rsi
  HBRUSH v16; // rax
  HBRUSH v17; // rdi
  struct tagRECT Rect; // [rsp+60h] [rbp-41h] BYREF
  tagPAINTSTRUCT Paint; // [rsp+70h] [rbp-31h] BYREF

  if ( *((_QWORD *)this + 28) )
  {
    if ( (*((_BYTE *)this + 280) & 8) != 0 )
    {
      v6 = BeginPaint(*((HWND *)this + 1), &Paint);
      if ( v6 )
      {
        GetClientRect(*((HWND *)this + 1), &Rect);
        CompatibleBitmap = CreateCompatibleBitmap(v6, Rect.right - Rect.left, Rect.bottom - Rect.top);
        if ( CompatibleBitmap )
        {
          CompatibleDC = CreateCompatibleDC(v6);
          hdcSrc = CompatibleDC;
          if ( CompatibleDC )
          {
            v10 = SelectObject(CompatibleDC, CompatibleBitmap);
            if ( v10 )
            {
              SolidBrush = CreateSolidBrush(*((_DWORD *)this + 85));
              v12 = SolidBrush;
              if ( SolidBrush )
              {
                FillRect(hdcSrc, &Rect, SolidBrush);
                DeleteObject(v12);
                (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 28) + 24LL))(
                  *((_QWORD *)this + 28),
                  1,
                  0xFFFFFFFFLL);
                BitBlt(v6, 0, 0, Rect.right, Rect.bottom, hdcSrc, 0, 0, 0xCC0020u);
              }
              SelectObject(hdcSrc, v10);
            }
            DeleteDC(hdcSrc);
          }
          v13 = CompatibleBitmap;
          goto LABEL_17;
        }
        goto LABEL_18;
      }
    }
    else
    {
      *a5 = 0;
    }
    return 0;
  }
  v15 = BeginPaint(*((HWND *)this + 1), &Paint);
  if ( !v15 )
    return 0;
  GetClientRect(*((HWND *)this + 1), &Rect);
  v16 = CreateSolidBrush(*((_DWORD *)this + 85));
  v17 = v16;
  if ( v16 )
  {
    FillRect(v15, &Rect, v16);
    v13 = (HBITMAP)v17;
LABEL_17:
    DeleteObject(v13);
  }
LABEL_18:
  EndPaint(*((HWND *)this + 1), &Paint);
  return 1;
}

```

## disassembly

```asm
0x1805fed30  mov     [rsp-8+arg_8], rbx
0x1805fed35  mov     [rsp-8+arg_10], rsi
0x1805fed3a  push    rbp
0x1805fed3b  push    rdi
0x1805fed3c  push    r12
0x1805fed3e  push    r14
0x1805fed40  push    r15
0x1805fed42  lea     rbp, [rsp-2Fh]
0x1805fed47  sub     rsp, 0D0h
0x1805fed4e  mov     rax, cs:__security_cookie
0x1805fed55  xor     rax, rsp
0x1805fed58  mov     [rbp+4Fh+var_30], rax
0x1805fed5c  cmp     qword ptr [rcx+0E0h], 0
0x1805fed64  mov     rbx, rcx
0x1805fed67  mov     rax, [rbp+4Fh+arg_20]
0x1805fed6b  jz      loc_1805FEF00
0x1805fed71  test    byte ptr [rcx+118h], 8
0x1805fed78  jz      loc_1805FEED0
0x1805fed7e  mov     rcx, [rcx+8]; hWnd
0x1805fed82  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x1805fed86  call    cs:__imp_BeginPaint
0x1805fed8c  mov     rsi, rax
0x1805fed8f  test    rax, rax
0x1805fed92  jz      loc_1805FEED6
0x1805fed98  mov     rcx, [rbx+8]; hWnd
0x1805fed9c  lea     rdx, [rbp+4Fh+Rect]; lpRect
0x1805feda0  call    cs:__imp_GetClientRect
0x1805feda6  mov     r8d, [rbp+4Fh+Rect.bottom]
0x1805fedaa  mov     rcx, rsi; hdc
0x1805fedad  mov     edx, [rbp+4Fh+Rect.right]
0x1805fedb0  sub     r8d, [rbp+4Fh+Rect.top]; cy
0x1805fedb4  sub     edx, [rbp+4Fh+Rect.left]; cx
0x1805fedb7  call    cs:__imp_CreateCompatibleBitmap
0x1805fedbd  mov     r14, rax
0x1805fedc0  test    rax, rax
0x1805fedc3  jz      loc_1805FEF51
0x1805fedc9  mov     rcx, rsi; hdc
0x1805fedcc  call    cs:__imp_CreateCompatibleDC
0x1805fedd2  mov     rdi, rax
0x1805fedd5  test    rax, rax
0x1805fedd8  jz      loc_1805FEECB
0x1805fedde  mov     rdx, r14; h
0x1805fede1  mov     rcx, rax; hdc
0x1805fede4  call    cs:__imp_SelectObject
0x1805fedea  mov     r15, rax
0x1805feded  test    rax, rax
0x1805fedf0  jz      loc_1805FEEC2
0x1805fedf6  mov     ecx, [rbx+154h]; color
0x1805fedfc  call    cs:__imp_CreateSolidBrush
0x1805fee02  mov     r12, rax
0x1805fee05  test    rax, rax
0x1805fee08  jz      loc_1805FEEB6
0x1805fee0e  mov     r8, rax; hbr
0x1805fee11  lea     rdx, [rbp+4Fh+Rect]; lprc
0x1805fee15  mov     rcx, rdi; hDC
0x1805fee18  call    cs:__imp_FillRect
0x1805fee1e  mov     rcx, r12; ho
0x1805fee21  call    cs:__imp_DeleteObject
0x1805fee27  mov     rcx, [rbx+0E0h]
0x1805fee2e  lea     rdx, [rbx+134h]
0x1805fee35  mov     [rsp+0F0h+var_A0], 0
0x1805fee3e  xor     r9d, r9d
0x1805fee41  mov     [rsp+0F0h+var_A8], 0
0x1805fee4a  or      r8d, 0FFFFFFFFh
0x1805fee4e  mov     qword ptr [rsp+0F0h+rop], rdx
0x1805fee53  mov     rax, [rcx]
0x1805fee56  mov     qword ptr [rsp+0F0h+y1], rdx
0x1805fee5b  lea     edx, [r9+1]
0x1805fee5f  mov     qword ptr [rsp+0F0h+x1], rdi
0x1805fee64  mov     [rsp+0F0h+hdcSrc], 0
0x1805fee6d  mov     rax, [rax+18h]
0x1805fee71  mov     qword ptr [rsp+0F0h+cy], 0
0x1805fee7a  call    cs:__guard_dispatch_icall_fptr
0x1805fee80  mov     eax, [rbp+4Fh+Rect.bottom]
0x1805fee83  xor     r8d, r8d; y
0x1805fee86  mov     r9d, [rbp+4Fh+Rect.right]; cx
0x1805fee8a  xor     edx, edx; x
0x1805fee8c  mov     [rsp+0F0h+rop], 0CC0020h; rop
0x1805fee94  mov     rcx, rsi; hdc
0x1805fee97  mov     [rsp+0F0h+y1], 0; y1
0x1805fee9f  mov     [rsp+0F0h+x1], 0; x1
0x1805feea7  mov     [rsp+0F0h+hdcSrc], rdi; hdcSrc
0x1805feeac  mov     [rsp+0F0h+cy], eax; cy
0x1805feeb0  call    cs:__imp_BitBlt
0x1805feeb6  mov     rdx, r15; h
0x1805feeb9  mov     rcx, rdi; hdc
0x1805feebc  call    cs:__imp_SelectObject
0x1805feec2  mov     rcx, rdi; hdc
0x1805feec5  call    cs:__imp_DeleteDC
0x1805feecb  mov     rcx, r14
0x1805feece  jmp     short loc_1805FEF4B
0x1805feed0  mov     dword ptr [rax], 0
0x1805feed6  xor     eax, eax
0x1805feed8  mov     rcx, [rbp+4Fh+var_30]
0x1805feedc  xor     rcx, rsp; StackCookie
0x1805feedf  call    __security_check_cookie
0x1805feee4  lea     r11, [rsp+0F0h+var_20]
0x1805feeec  mov     rbx, [r11+38h]
0x1805feef0  mov     rsi, [r11+40h]
0x1805feef4  mov     rsp, r11
0x1805feef7  pop     r15
0x1805feef9  pop     r14
0x1805feefb  pop     r12
0x1805feefd  pop     rdi
0x1805feefe  pop     rbp
0x1805feeff  retn
0x1805fef00  mov     rcx, [rcx+8]; hWnd
0x1805fef04  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x1805fef08  call    cs:__imp_BeginPaint
0x1805fef0e  mov     rsi, rax
0x1805fef11  test    rax, rax
0x1805fef14  jz      short loc_1805FEED6
0x1805fef16  mov     rcx, [rbx+8]; hWnd
0x1805fef1a  lea     rdx, [rbp+4Fh+Rect]; lpRect
0x1805fef1e  call    cs:__imp_GetClientRect
0x1805fef24  mov     ecx, [rbx+154h]; color
0x1805fef2a  call    cs:__imp_CreateSolidBrush
0x1805fef30  mov     rdi, rax
0x1805fef33  test    rax, rax
0x1805fef36  jz      short loc_1805FEF51
0x1805fef38  mov     r8, rax; hbr
0x1805fef3b  lea     rdx, [rbp+4Fh+Rect]; lprc
0x1805fef3f  mov     rcx, rsi; hDC
0x1805fef42  call    cs:__imp_FillRect
0x1805fef48  mov     rcx, rdi; ho
0x1805fef4b  call    cs:__imp_DeleteObject
0x1805fef51  mov     rcx, [rbx+8]; hWnd
0x1805fef55  lea     rdx, [rbp+4Fh+Paint]; lpPaint
0x1805fef59  call    cs:__imp_EndPaint
0x1805fef5f  mov     eax, 1
0x1805fef64  jmp     loc_1805FEED8
```
