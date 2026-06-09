# BLTTER::S_Init(void)

- ea: `0x180286e08`
- end: `0x180286f58`
- name: `?S_Init@BLTTER@@SAJXZ`
- size: `336`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180285c50`

## callees

- `0x180286e08`

## import_xrefs

- `USER32!GetDC` at `0x180286e46`
- `USER32!GetDC` at `0x180286e46`
- `GDI32!CreateCompatibleBitmap` at `0x180286e81`
- `GDI32!CreateCompatibleBitmap` at `0x180286e81`
- `GDI32!CreateCompatibleDC` at `0x180286e1b`
- `GDI32!CreateCompatibleDC` at `0x180286e1b`
- `GDI32!DeleteDC` at `0x180286f14`
- `GDI32!DeleteDC` at `0x180286f3d`
- `GDI32!DeleteDC` at `0x180286f14`
- `GDI32!DeleteDC` at `0x180286f3d`
- `GDI32!SelectObject` at `0x180286eac`
- `GDI32!SelectObject` at `0x180286eeb`
- `GDI32!SelectObject` at `0x180286eac`
- `GDI32!SelectObject` at `0x180286eeb`
- `GDI32!DeleteObject` at `0x180286ef6`
- `GDI32!DeleteObject` at `0x180286ef6`

## pseudocode

```c
__int64 BLTTER::S_Init(void)
{
  int v1; // [rsp+20h] [rbp-10h]
  HBITMAP h; // [rsp+28h] [rbp-8h]

  v1 = 0;
  BLTTER::s_hdc = CreateCompatibleDC(0);
  if ( BLTTER::s_hdc )
  {
    BLTTER::s_hdcScreen = GetDC(0);
    if ( BLTTER::s_hdcScreen )
    {
      h = CreateCompatibleBitmap(BLTTER::s_hdc, 1, 1);
      if ( h )
      {
        BLTTER::s_hbmpCurrent = (HBITMAP)SelectObject(BLTTER::s_hdc, h);
        BLTTER::s_hbmpOriginal = BLTTER::s_hbmpCurrent;
        if ( BLTTER::s_hbmpCurrent )
        {
          SelectObject(BLTTER::s_hdc, BLTTER::s_hbmpOriginal);
          DeleteObject(h);
        }
        else
        {
          v1 = -2147024882;
        }
      }
      else
      {
        v1 = -2147024882;
      }
    }
    else
    {
      v1 = -2147024882;
    }
  }
  else
  {
    v1 = -2147024882;
  }
  if ( v1 < 0 && BLTTER::s_hdc )
  {
    DeleteDC(BLTTER::s_hdc);
    BLTTER::s_hdc = 0;
  }
  if ( v1 < 0 && BLTTER::s_hdcScreen )
  {
    DeleteDC(BLTTER::s_hdcScreen);
    BLTTER::s_hdcScreen = 0;
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180286e08  push    rbp
0x180286e0a  mov     rbp, rsp
0x180286e0d  sub     rsp, 30h
0x180286e11  mov     [rsp+30h+var_10], 0
0x180286e19  xor     ecx, ecx; hdc
0x180286e1b  call    cs:__imp_CreateCompatibleDC
0x180286e21  mov     cs:?s_hdc@BLTTER@@2PEAUHDC__@@EA, rax; HDC__ * BLTTER::s_hdc
0x180286e28  cmp     cs:?s_hdc@BLTTER@@2PEAUHDC__@@EA, 0; HDC__ * BLTTER::s_hdc
0x180286e30  jnz     short loc_180286E44
0x180286e32  mov     [rsp+30h+var_10], 8007000Eh
0x180286e3a  jmp     loc_180286EFC
0x180286e3f  jmp     loc_180286EFC
0x180286e44  xor     ecx, ecx; hWnd
0x180286e46  call    cs:__imp_GetDC
0x180286e4c  mov     cs:?s_hdcScreen@BLTTER@@2PEAUHDC__@@EA, rax; HDC__ * BLTTER::s_hdcScreen
0x180286e53  cmp     cs:?s_hdcScreen@BLTTER@@2PEAUHDC__@@EA, 0; HDC__ * BLTTER::s_hdcScreen
0x180286e5b  jnz     short loc_180286E6F
0x180286e5d  mov     [rsp+30h+var_10], 8007000Eh
0x180286e65  jmp     loc_180286EFC
0x180286e6a  jmp     loc_180286EFC
0x180286e6f  mov     r8d, 1; cy
0x180286e75  mov     edx, 1; cx
0x180286e7a  mov     rcx, cs:?s_hdc@BLTTER@@2PEAUHDC__@@EA; hdc
0x180286e81  call    cs:__imp_CreateCompatibleBitmap
0x180286e87  mov     [rsp+30h+h], rax
0x180286e8c  cmp     [rsp+30h+h], 0
0x180286e92  jnz     short loc_180286EA0
0x180286e94  mov     [rsp+30h+var_10], 8007000Eh
0x180286e9c  jmp     short loc_180286EFC
0x180286e9e  jmp     short loc_180286EFC
0x180286ea0  mov     rdx, [rsp+30h+h]; h
0x180286ea5  mov     rcx, cs:?s_hdc@BLTTER@@2PEAUHDC__@@EA; hdc
0x180286eac  call    cs:__imp_SelectObject
0x180286eb2  mov     cs:?s_hbmpCurrent@BLTTER@@2PEAUHBITMAP__@@EA, rax; HBITMAP__ * BLTTER::s_hbmpCurrent
0x180286eb9  mov     rax, cs:?s_hbmpCurrent@BLTTER@@2PEAUHBITMAP__@@EA; HBITMAP__ * BLTTER::s_hbmpCurrent
0x180286ec0  mov     cs:?s_hbmpOriginal@BLTTER@@2PEAUHBITMAP__@@EA, rax; HBITMAP__ * BLTTER::s_hbmpOriginal
0x180286ec7  cmp     cs:?s_hbmpOriginal@BLTTER@@2PEAUHBITMAP__@@EA, 0; HBITMAP__ * BLTTER::s_hbmpOriginal
0x180286ecf  jnz     short loc_180286EDD
0x180286ed1  mov     [rsp+30h+var_10], 8007000Eh
0x180286ed9  jmp     short loc_180286EFC
0x180286edb  jmp     short loc_180286EFC
0x180286edd  mov     rdx, cs:?s_hbmpOriginal@BLTTER@@2PEAUHBITMAP__@@EA; h
0x180286ee4  mov     rcx, cs:?s_hdc@BLTTER@@2PEAUHDC__@@EA; hdc
0x180286eeb  call    cs:__imp_SelectObject
0x180286ef1  mov     rcx, [rsp+30h+h]; ho
0x180286ef6  call    cs:__imp_DeleteObject
0x180286efc  cmp     [rsp+30h+var_10], 0
0x180286f01  jge     short loc_180286F25
0x180286f03  cmp     cs:?s_hdc@BLTTER@@2PEAUHDC__@@EA, 0; HDC__ * BLTTER::s_hdc
0x180286f0b  jz      short loc_180286F25
0x180286f0d  mov     rcx, cs:?s_hdc@BLTTER@@2PEAUHDC__@@EA; hdc
0x180286f14  call    cs:__imp_DeleteDC
0x180286f1a  mov     cs:?s_hdc@BLTTER@@2PEAUHDC__@@EA, 0; HDC__ * BLTTER::s_hdc
0x180286f25  cmp     [rsp+30h+var_10], 0
0x180286f2a  jge     short loc_180286F4E
0x180286f2c  cmp     cs:?s_hdcScreen@BLTTER@@2PEAUHDC__@@EA, 0; HDC__ * BLTTER::s_hdcScreen
0x180286f34  jz      short loc_180286F4E
0x180286f36  mov     rcx, cs:?s_hdcScreen@BLTTER@@2PEAUHDC__@@EA; hdc
0x180286f3d  call    cs:__imp_DeleteDC
0x180286f43  mov     cs:?s_hdcScreen@BLTTER@@2PEAUHDC__@@EA, 0; HDC__ * BLTTER::s_hdcScreen
0x180286f4e  mov     eax, [rsp+30h+var_10]
0x180286f52  add     rsp, 30h
0x180286f56  pop     rbp
0x180286f57  retn
```
