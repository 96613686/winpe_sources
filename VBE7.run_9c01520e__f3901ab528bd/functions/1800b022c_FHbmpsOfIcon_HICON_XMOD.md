# _FHbmpsOfIcon(HICON__ *,XMOD *)

- ea: `0x1800b022c`
- end: `0x1800b0613`
- name: `?_FHbmpsOfIcon@@YAHPEAUHICON__@@PEAUXMOD@@@Z`
- size: `999`
- prototype: `__int64 __fastcall(HICON, struct XMOD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800b061c`
- `0x1800b0fa8`

## callees

- `0x180029b14`
- `0x1800b022c`
- `0x180379380`

## import_xrefs

- `USER32!DrawIcon` at `0x1800b0396`
- `USER32!DrawIcon` at `0x1800b04f2`
- `USER32!DrawIcon` at `0x1800b0396`
- `USER32!DrawIcon` at `0x1800b04f2`
- `USER32!GetDC` at `0x1800b02ba`
- `USER32!GetDC` at `0x1800b02ba`
- `USER32!ReleaseDC` at `0x1800b0580`
- `USER32!ReleaseDC` at `0x1800b0580`
- `GDI32!CreateCompatibleBitmap` at `0x1800b02f0`
- `GDI32!CreateCompatibleBitmap` at `0x1800b03a6`
- `GDI32!CreateCompatibleBitmap` at `0x1800b0502`
- `GDI32!CreateCompatibleBitmap` at `0x1800b02f0`
- `GDI32!CreateCompatibleBitmap` at `0x1800b03a6`
- `GDI32!CreateCompatibleBitmap` at `0x1800b0502`
- `GDI32!CreateCompatibleDC` at `0x1800b02cf`
- `GDI32!CreateCompatibleDC` at `0x1800b02cf`
- `GDI32!StretchBlt` at `0x1800b0367`
- `GDI32!StretchBlt` at `0x1800b040c`
- `GDI32!StretchBlt` at `0x1800b04bc`
- `GDI32!StretchBlt` at `0x1800b0560`
- `GDI32!StretchBlt` at `0x1800b0367`
- `GDI32!StretchBlt` at `0x1800b040c`
- `GDI32!StretchBlt` at `0x1800b04bc`
- `GDI32!StretchBlt` at `0x1800b0560`
- `GDI32!SetStretchBltMode` at `0x1800b0321`
- `GDI32!SetStretchBltMode` at `0x1800b0321`
- `GDI32!DeleteDC` at `0x1800b05bc`
- `GDI32!DeleteDC` at `0x1800b05bc`
- `GDI32!GetObjectA` at `0x1800b028d`
- `GDI32!GetObjectA` at `0x1800b028d`
- `GDI32!SelectObject` at `0x1800b02a5`
- `GDI32!SelectObject` at `0x1800b0308`
- `GDI32!SelectObject` at `0x1800b03c2`
- `GDI32!SelectObject` at `0x1800b0470`
- `GDI32!SelectObject` at `0x1800b051a`
- `GDI32!SelectObject` at `0x1800b0599`
- `GDI32!SelectObject` at `0x1800b05b3`
- `GDI32!SelectObject` at `0x1800b02a5`
- `GDI32!SelectObject` at `0x1800b0308`
- `GDI32!SelectObject` at `0x1800b03c2`
- `GDI32!SelectObject` at `0x1800b0470`
- `GDI32!SelectObject` at `0x1800b051a`
- `GDI32!SelectObject` at `0x1800b0599`
- `GDI32!SelectObject` at `0x1800b05b3`
- `GDI32!DeleteObject` at `0x1800b041e`
- `GDI32!DeleteObject` at `0x1800b0430`
- `GDI32!DeleteObject` at `0x1800b0443`
- `GDI32!DeleteObject` at `0x1800b05ca`
- `GDI32!DeleteObject` at `0x1800b05d8`
- `GDI32!DeleteObject` at `0x1800b05e6`
- `GDI32!DeleteObject` at `0x1800b041e`
- `GDI32!DeleteObject` at `0x1800b0430`
- `GDI32!DeleteObject` at `0x1800b0443`
- `GDI32!DeleteObject` at `0x1800b05ca`
- `GDI32!DeleteObject` at `0x1800b05d8`
- `GDI32!DeleteObject` at `0x1800b05e6`

## pseudocode

```c
__int64 __fastcall _FHbmpsOfIcon(HICON a1, struct XMOD *a2)
{
  unsigned int v2; // ebx
  HDC hdcSrc; // rdi
  HBITMAP v5; // r12
  HBITMAP v6; // r14
  HBITMAP Bitmap3D; // rax
  HBITMAP v8; // rsi
  HDC DC; // rax
  HDC v10; // r15
  HBITMAP CompatibleBitmap; // rax
  HBITMAP v12; // rax
  void *v13; // rcx
  void *v14; // rcx
  HBITMAP v15; // rax
  HBITMAP v16; // rax
  _BYTE pv[4]; // [rsp+60h] [rbp-20h] BYREF
  int wDest; // [rsp+64h] [rbp-1Ch]
  int cy; // [rsp+68h] [rbp-18h]
  HDC h; // [rsp+C8h] [rbp+48h]
  HGDIOBJ v23; // [rsp+D0h] [rbp+50h]

  v2 = 0;
  hdcSrc = 0;
  v23 = 0;
  h = 0;
  v5 = 0;
  v6 = 0;
  Bitmap3D = LoadBitmap3D(Rby_hmodThun, 0x3DEu);
  v8 = Bitmap3D;
  if ( Bitmap3D && GetObjectA(Bitmap3D, 32, pv) && (h = (HDC)SelectObject(hdcDest, v8)) != 0 )
  {
    DC = GetDC(0);
    v10 = DC;
    if ( !DC )
      goto LABEL_22;
    hdcSrc = CreateCompatibleDC(DC);
    if ( hdcSrc )
    {
      CompatibleBitmap = CreateCompatibleBitmap(v10, 2 * wDest, 2 * cy);
      v5 = CompatibleBitmap;
      if ( CompatibleBitmap )
      {
        v23 = SelectObject(hdcSrc, CompatibleBitmap);
        if ( v23 )
        {
          SetStretchBltMode(hdcSrc, 3);
          StretchBlt(hdcSrc, 0, 0, 2 * wDest, 2 * cy, hdcDest, 0, 0, wDest, cy, 0xCC0020u);
          DrawIcon(hdcSrc, wDest - Sys_cxIcon / 2, cy - Sys_cyIcon / 2, a1);
          v12 = CreateCompatibleBitmap(v10, wDest, cy);
          v6 = v12;
          if ( v12 )
          {
            if ( SelectObject(hdcDest, v12) )
            {
              StretchBlt(hdcDest, 0, 0, wDest, cy, hdcSrc, 0, 0, 2 * wDest, 2 * cy, 0xCC0020u);
              v13 = (void *)*((_QWORD *)a2 + 50);
              if ( v13 )
                DeleteObject(v13);
              v14 = (void *)*((_QWORD *)a2 + 51);
              if ( v14 )
                DeleteObject(v14);
              *((_QWORD *)a2 + 50) = v6;
              v6 = 0;
              DeleteObject(v8);
              v15 = LoadBitmap3D(Rby_hmodThun, 0x3DFu);
              v8 = v15;
              if ( v15 )
              {
                if ( SelectObject(hdcDest, v15) )
                {
                  StretchBlt(hdcSrc, 0, 0, 2 * wDest, 2 * cy, hdcDest, 0, 0, wDest, cy, 0xCC0020u);
                  DrawIcon(hdcSrc, wDest - Sys_cxIcon / 2 + 2, cy - Sys_cyIcon / 2 + 2, a1);
                  v16 = CreateCompatibleBitmap(v10, wDest, cy);
                  v6 = v16;
                  if ( v16 )
                  {
                    if ( SelectObject(hdcDest, v16) )
                    {
                      StretchBlt(hdcDest, 0, 0, wDest, cy, hdcSrc, 0, 0, 2 * wDest, 2 * cy, 0xCC0020u);
                      *((_QWORD *)a2 + 51) = v6;
                      v6 = 0;
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
  else
  {
    v10 = h;
  }
  if ( v10 )
    ReleaseDC(0, v10);
LABEL_22:
  if ( h )
    SelectObject(hdcDest, h);
  if ( hdcSrc )
  {
    if ( v23 )
      SelectObject(hdcSrc, v23);
    DeleteDC(hdcSrc);
  }
  if ( v8 )
    DeleteObject(v8);
  if ( v6 )
    DeleteObject(v6);
  if ( v5 )
    DeleteObject(v5);
  LOBYTE(v2) = *((_QWORD *)a2 + 50) != 0;
  return v2;
}

```

## disassembly

```asm
0x1800b022c  mov     [rsp-38h+arg_18], rbx
0x1800b0231  mov     [rsp-38h+hIcon], rcx
0x1800b0236  push    rbp
0x1800b0237  push    rsi
0x1800b0238  push    rdi
0x1800b0239  push    r12
0x1800b023b  push    r13
0x1800b023d  push    r14
0x1800b023f  push    r15
0x1800b0241  mov     rbp, rsp
0x1800b0244  mov     eax, 80h
0x1800b0249  call    _alloca_probe
0x1800b024e  sub     rsp, rax
0x1800b0251  mov     rcx, cs:?Rby_hmodThun@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x1800b0258  xor     ebx, ebx
0x1800b025a  mov     r13, rdx
0x1800b025d  mov     edx, 3DEh; unsigned __int16
0x1800b0262  mov     edi, ebx
0x1800b0264  mov     [rbp+arg_10], rbx
0x1800b0268  mov     [rbp+h], rbx
0x1800b026c  mov     r12d, ebx
0x1800b026f  mov     r14d, ebx
0x1800b0272  call    ?LoadBitmap3D@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@G@Z; LoadBitmap3D(HINSTANCE__ *,ushort)
0x1800b0277  mov     rsi, rax
0x1800b027a  test    rax, rax
0x1800b027d  jz      loc_1800B0572
0x1800b0283  lea     r8, [rbp+pv]; pv
0x1800b0287  lea     edx, [rbx+20h]; c
0x1800b028a  mov     rcx, rax; h
0x1800b028d  call    cs:__imp_GetObjectA
0x1800b0293  test    eax, eax
0x1800b0295  jz      loc_1800B0572
0x1800b029b  mov     rcx, cs:hdcDest; hdc
0x1800b02a2  mov     rdx, rsi; h
0x1800b02a5  call    cs:__imp_SelectObject
0x1800b02ab  mov     [rbp+h], rax
0x1800b02af  test    rax, rax
0x1800b02b2  jz      loc_1800B0572
0x1800b02b8  xor     ecx, ecx; hWnd
0x1800b02ba  call    cs:__imp_GetDC
0x1800b02c0  mov     r15, rax
0x1800b02c3  test    rax, rax
0x1800b02c6  jz      loc_1800B0586
0x1800b02cc  mov     rcx, rax; hdc
0x1800b02cf  call    cs:__imp_CreateCompatibleDC
0x1800b02d5  mov     rdi, rax
0x1800b02d8  test    rax, rax
0x1800b02db  jz      loc_1800B0576
0x1800b02e1  mov     r8d, [rbp+cy]
0x1800b02e5  mov     edx, [rbp+wDest]
0x1800b02e8  mov     rcx, r15; hdc
0x1800b02eb  add     r8d, r8d; cy
0x1800b02ee  add     edx, edx; cx
0x1800b02f0  call    cs:__imp_CreateCompatibleBitmap
0x1800b02f6  mov     r12, rax
0x1800b02f9  test    rax, rax
0x1800b02fc  jz      loc_1800B0576
0x1800b0302  mov     rdx, rax; h
0x1800b0305  mov     rcx, rdi; hdc
0x1800b0308  call    cs:__imp_SelectObject
0x1800b030e  mov     [rbp+arg_10], rax
0x1800b0312  test    rax, rax
0x1800b0315  jz      loc_1800B0576
0x1800b031b  lea     edx, [rbx+3]; mode
0x1800b031e  mov     rcx, rdi; hdc
0x1800b0321  call    cs:__imp_SetStretchBltMode
0x1800b0327  mov     eax, [rbp+wDest]
0x1800b032a  mov     r11d, [rbp+cy]
0x1800b032e  mov     [rsp+80h+rop], 0CC0020h; rop
0x1800b0336  mov     [rsp+80h+hSrc], r11d; hSrc
0x1800b033b  mov     [rsp+80h+wSrc], eax; wSrc
0x1800b033f  lea     ecx, [r11+r11]
0x1800b0343  mov     [rsp+80h+ySrc], ebx; ySrc
0x1800b0347  lea     r9d, [rax+rax]; wDest
0x1800b034b  mov     rax, cs:hdcDest
0x1800b0352  mov     [rsp+80h+xSrc], ebx; xSrc
0x1800b0356  xor     r8d, r8d; yDest
0x1800b0359  mov     [rsp+80h+hdcSrc], rax; hdcSrc
0x1800b035e  mov     [rsp+80h+hDest], ecx; hDest
0x1800b0362  mov     rcx, rdi; hdcDest
0x1800b0365  xor     edx, edx; xDest
0x1800b0367  call    cs:__imp_StretchBlt
0x1800b036d  mov     eax, cs:?Sys_cyIcon@@3HA; int Sys_cyIcon
0x1800b0373  mov     r8d, [rbp+cy]
0x1800b0377  mov     r9, [rbp+hIcon]; hIcon
0x1800b037b  cdq
0x1800b037c  mov     rcx, rdi; hDC
0x1800b037f  sub     eax, edx
0x1800b0381  sar     eax, 1
0x1800b0383  sub     r8d, eax; Y
0x1800b0386  mov     eax, cs:?Sys_cxIcon@@3HA; int Sys_cxIcon
0x1800b038c  cdq
0x1800b038d  sub     eax, edx
0x1800b038f  mov     edx, [rbp+wDest]
0x1800b0392  sar     eax, 1
0x1800b0394  sub     edx, eax; X
0x1800b0396  call    cs:__imp_DrawIcon
0x1800b039c  mov     r8d, [rbp+cy]; cy
0x1800b03a0  mov     edx, [rbp+wDest]; cx
0x1800b03a3  mov     rcx, r15; hdc
0x1800b03a6  call    cs:__imp_CreateCompatibleBitmap
0x1800b03ac  mov     r14, rax
0x1800b03af  test    rax, rax
0x1800b03b2  jz      loc_1800B0576
0x1800b03b8  mov     rcx, cs:hdcDest; hdc
0x1800b03bf  mov     rdx, rax; h
0x1800b03c2  call    cs:__imp_SelectObject
0x1800b03c8  test    rax, rax
0x1800b03cb  jz      loc_1800B0576
0x1800b03d1  mov     edx, [rbp+cy]
0x1800b03d4  mov     r9d, [rbp+wDest]; wDest
0x1800b03d8  mov     [rsp+80h+rop], 0CC0020h; rop
0x1800b03e0  lea     ecx, [rdx+rdx]
0x1800b03e3  lea     eax, [r9+r9]
0x1800b03e7  xor     r8d, r8d; yDest
0x1800b03ea  mov     [rsp+80h+hSrc], ecx; hSrc
0x1800b03ee  mov     rcx, cs:hdcDest; hdcDest
0x1800b03f5  mov     [rsp+80h+wSrc], eax; wSrc
0x1800b03f9  mov     [rsp+80h+ySrc], ebx; ySrc
0x1800b03fd  mov     [rsp+80h+xSrc], ebx; xSrc
0x1800b0401  mov     [rsp+80h+hdcSrc], rdi; hdcSrc
0x1800b0406  mov     [rsp+80h+hDest], edx; hDest
0x1800b040a  xor     edx, edx; xDest
0x1800b040c  call    cs:__imp_StretchBlt
0x1800b0412  mov     rcx, [r13+190h]; ho
0x1800b0419  test    rcx, rcx
0x1800b041c  jz      short loc_1800B0424
0x1800b041e  call    cs:__imp_DeleteObject
0x1800b0424  mov     rcx, [r13+198h]; ho
0x1800b042b  test    rcx, rcx
0x1800b042e  jz      short loc_1800B0436
0x1800b0430  call    cs:__imp_DeleteObject
0x1800b0436  mov     [r13+190h], r14
0x1800b043d  mov     rcx, rsi; ho
0x1800b0440  mov     r14, rbx
0x1800b0443  call    cs:__imp_DeleteObject
0x1800b0449  mov     rcx, cs:?Rby_hmodThun@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x1800b0450  mov     edx, 3DFh; unsigned __int16
0x1800b0455  call    ?LoadBitmap3D@@YAPEAUHBITMAP__@@PEAUHINSTANCE__@@G@Z; LoadBitmap3D(HINSTANCE__ *,ushort)
0x1800b045a  mov     rsi, rax
0x1800b045d  test    rax, rax
0x1800b0460  jz      loc_1800B0576
0x1800b0466  mov     rcx, cs:hdcDest; hdc
0x1800b046d  mov     rdx, rax; h
0x1800b0470  call    cs:__imp_SelectObject
0x1800b0476  test    rax, rax
0x1800b0479  jz      loc_1800B0576
0x1800b047f  mov     ecx, [rbp+cy]
0x1800b0482  mov     eax, [rbp+wDest]
0x1800b0485  mov     [rsp+80h+rop], 0CC0020h; rop
0x1800b048d  mov     [rsp+80h+hSrc], ecx; hSrc
0x1800b0491  mov     [rsp+80h+wSrc], eax; wSrc
0x1800b0495  lea     edx, [rcx+rcx]
0x1800b0498  mov     [rsp+80h+ySrc], ebx; ySrc
0x1800b049c  lea     r9d, [rax+rax]; wDest
0x1800b04a0  mov     rax, cs:hdcDest
0x1800b04a7  mov     [rsp+80h+xSrc], ebx; xSrc
0x1800b04ab  mov     [rsp+80h+hdcSrc], rax; hdcSrc
0x1800b04b0  mov     [rsp+80h+hDest], edx; hDest
0x1800b04b4  xor     edx, edx; xDest
0x1800b04b6  xor     r8d, r8d; yDest
0x1800b04b9  mov     rcx, rdi; hdcDest
0x1800b04bc  call    cs:__imp_StretchBlt
0x1800b04c2  mov     eax, cs:?Sys_cyIcon@@3HA; int Sys_cyIcon
0x1800b04c8  mov     r8d, [rbp+cy]
0x1800b04cc  mov     r9, [rbp+hIcon]; hIcon
0x1800b04d0  cdq
0x1800b04d1  mov     rcx, rdi; hDC
0x1800b04d4  sub     eax, edx
0x1800b04d6  sar     eax, 1
0x1800b04d8  sub     r8d, eax
0x1800b04db  mov     eax, cs:?Sys_cxIcon@@3HA; int Sys_cxIcon
0x1800b04e1  cdq
0x1800b04e2  add     r8d, 2; Y
0x1800b04e6  sub     eax, edx
0x1800b04e8  mov     edx, [rbp+wDest]
0x1800b04eb  sar     eax, 1
0x1800b04ed  sub     edx, eax
0x1800b04ef  add     edx, 2; X
0x1800b04f2  call    cs:__imp_DrawIcon
0x1800b04f8  mov     r8d, [rbp+cy]; cy
0x1800b04fc  mov     edx, [rbp+wDest]; cx
0x1800b04ff  mov     rcx, r15; hdc
0x1800b0502  call    cs:__imp_CreateCompatibleBitmap
0x1800b0508  mov     r14, rax
0x1800b050b  test    rax, rax
0x1800b050e  jz      short loc_1800B0576
0x1800b0510  mov     rcx, cs:hdcDest; hdc
0x1800b0517  mov     rdx, rax; h
0x1800b051a  call    cs:__imp_SelectObject
0x1800b0520  test    rax, rax
0x1800b0523  jz      short loc_1800B0576
0x1800b0525  mov     edx, [rbp+cy]
0x1800b0528  mov     r9d, [rbp+wDest]; wDest
0x1800b052c  mov     [rsp+80h+rop], 0CC0020h; rop
0x1800b0534  lea     ecx, [rdx+rdx]
0x1800b0537  lea     eax, [r9+r9]
0x1800b053b  xor     r8d, r8d; yDest
0x1800b053e  mov     [rsp+80h+hSrc], ecx; hSrc
0x1800b0542  mov     rcx, cs:hdcDest; hdcDest
0x1800b0549  mov     [rsp+80h+wSrc], eax; wSrc
0x1800b054d  mov     [rsp+80h+ySrc], ebx; ySrc
0x1800b0551  mov     [rsp+80h+xSrc], ebx; xSrc
0x1800b0555  mov     [rsp+80h+hdcSrc], rdi; hdcSrc
0x1800b055a  mov     [rsp+80h+hDest], edx; hDest
0x1800b055e  xor     edx, edx; xDest
0x1800b0560  call    cs:__imp_StretchBlt
0x1800b0566  mov     [r13+198h], r14
0x1800b056d  mov     r14, rbx
0x1800b0570  jmp     short loc_1800B0576
0x1800b0572  mov     r15, [rbp+h]
0x1800b0576  test    r15, r15
0x1800b0579  jz      short loc_1800B0586
0x1800b057b  mov     rdx, r15; hDC
0x1800b057e  xor     ecx, ecx; hWnd
0x1800b0580  call    cs:__imp_ReleaseDC
0x1800b0586  mov     rax, [rbp+h]
0x1800b058a  test    rax, rax
0x1800b058d  jz      short loc_1800B059F
0x1800b058f  mov     rcx, cs:hdcDest; hdc
0x1800b0596  mov     rdx, rax; h
0x1800b0599  call    cs:__imp_SelectObject
0x1800b059f  test    rdi, rdi
0x1800b05a2  jz      short loc_1800B05C2
0x1800b05a4  mov     rax, [rbp+arg_10]
0x1800b05a8  test    rax, rax
0x1800b05ab  jz      short loc_1800B05B9
0x1800b05ad  mov     rdx, rax; h
0x1800b05b0  mov     rcx, rdi; hdc
0x1800b05b3  call    cs:__imp_SelectObject
0x1800b05b9  mov     rcx, rdi; hdc
0x1800b05bc  call    cs:__imp_DeleteDC
0x1800b05c2  test    rsi, rsi
0x1800b05c5  jz      short loc_1800B05D0
0x1800b05c7  mov     rcx, rsi; ho
0x1800b05ca  call    cs:__imp_DeleteObject
0x1800b05d0  test    r14, r14
0x1800b05d3  jz      short loc_1800B05DE
0x1800b05d5  mov     rcx, r14; ho
0x1800b05d8  call    cs:__imp_DeleteObject
0x1800b05de  test    r12, r12
0x1800b05e1  jz      short loc_1800B05EC
0x1800b05e3  mov     rcx, r12; ho
0x1800b05e6  call    cs:__imp_DeleteObject
0x1800b05ec  cmp     [r13+190h], rbx
0x1800b05f3  setnz   bl
0x1800b05f6  mov     eax, ebx
0x1800b05f8  mov     rbx, [rsp+80h+arg_18]
0x1800b0600  add     rsp, 80h
0x1800b0607  pop     r15
0x1800b0609  pop     r14
0x1800b060b  pop     r13
0x1800b060d  pop     r12
0x1800b060f  pop     rdi
0x1800b0610  pop     rsi
0x1800b0611  pop     rbp
0x1800b0612  retn
```
