# CSelectionRect::_DrawWidget(HDC__ *,int,int,int)

- ea: `0x1800e54d0`
- end: `0x1800e55de`
- name: `?_DrawWidget@CSelectionRect@@AEAAXPEAUHDC__@@HHH@Z`
- size: `270`
- prototype: `void(CSelectionRect *__hidden this, HDC, int, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800e57d8`

## callees

- `0x1800e54d0`

## import_xrefs

- `USER32!LoadImageW` at `0x1800e550b`
- `USER32!LoadImageW` at `0x1800e550b`
- `GDI32!GetObjectW` at `0x1800e555b`
- `GDI32!GetObjectW` at `0x1800e555b`
- `GDI32!BitBlt` at `0x1800e55ad`
- `GDI32!BitBlt` at `0x1800e55ad`
- `GDI32!DeleteDC` at `0x1800e55c2`
- `GDI32!DeleteDC` at `0x1800e55c2`
- `GDI32!CreateCompatibleDC` at `0x1800e5520`
- `GDI32!CreateCompatibleDC` at `0x1800e5520`
- `GDI32!SelectObject` at `0x1800e5538`
- `GDI32!SelectObject` at `0x1800e55b9`
- `GDI32!SelectObject` at `0x1800e5538`
- `GDI32!SelectObject` at `0x1800e55b9`
- `GDI32!DeleteObject` at `0x1800e55cb`
- `GDI32!DeleteObject` at `0x1800e55cb`

## pseudocode

```c
void __fastcall CSelectionRect::_DrawWidget(CSelectionRect *this, HDC a2, int a3, int a4, unsigned __int16 a5)
{
  HANDLE ImageW; // rdi
  HDC CompatibleDC; // rax
  HDC v10; // rsi
  HGDIOBJ v11; // rbx
  _OWORD pv[5]; // [rsp+50h] [rbp-58h] BYREF

  ImageW = LoadImageW(hInst, (LPCWSTR)a5, 0, 0, 0, 0);
  if ( ImageW )
  {
    CompatibleDC = CreateCompatibleDC(a2);
    v10 = CompatibleDC;
    if ( CompatibleDC )
    {
      memset(pv, 0, 32);
      v11 = SelectObject(CompatibleDC, ImageW);
      GetObjectW(ImageW, 32, pv);
      BitBlt(a2, a3 - SDWORD1(pv[0]) / 2, a4 - SDWORD2(pv[0]) / 2, SDWORD1(pv[0]), SDWORD2(pv[0]), v10, 0, 0, 0xCC0020u);
      SelectObject(v10, v11);
      DeleteDC(v10);
    }
    DeleteObject(ImageW);
  }
}

```

## disassembly

```asm
0x1800e54d0  push    rbx
0x1800e54d2  push    rbp
0x1800e54d3  push    rsi
0x1800e54d4  push    rdi
0x1800e54d5  push    r14
0x1800e54d7  push    r15
0x1800e54d9  sub     rsp, 78h
0x1800e54dd  mov     rcx, cs:hInst; hInst
0x1800e54e4  mov     r14d, r9d
0x1800e54e7  mov     r15d, r8d
0x1800e54ea  mov     [rsp+0A8h+fuLoad], 0; fuLoad
0x1800e54f2  mov     rbp, rdx
0x1800e54f5  mov     [rsp+0A8h+cy], 0; cy
0x1800e54fd  movzx   edx, word ptr [rsp+0A8h+arg_20]; name
0x1800e5505  xor     r9d, r9d; cx
0x1800e5508  xor     r8d, r8d; type
0x1800e550b  call    cs:__imp_LoadImageW
0x1800e5511  mov     rdi, rax
0x1800e5514  test    rax, rax
0x1800e5517  jz      loc_1800E55D1
0x1800e551d  mov     rcx, rbp; hdc
0x1800e5520  call    cs:__imp_CreateCompatibleDC
0x1800e5526  mov     rsi, rax
0x1800e5529  test    rax, rax
0x1800e552c  jz      loc_1800E55C8
0x1800e5532  mov     rdx, rdi; h
0x1800e5535  mov     rcx, rax; hdc
0x1800e5538  call    cs:__imp_SelectObject
0x1800e553e  xorps   xmm0, xmm0
0x1800e5541  lea     r8, [rsp+0A8h+pv]; pv
0x1800e5546  mov     edx, 20h ; ' '; c
0x1800e554b  mov     rcx, rdi; h
0x1800e554e  movups  [rsp+0A8h+pv], xmm0
0x1800e5553  mov     rbx, rax
0x1800e5556  movups  [rsp+0A8h+var_48], xmm0
0x1800e555b  call    cs:__imp_GetObjectW
0x1800e5561  mov     ecx, dword ptr [rsp+0A8h+pv+8]
0x1800e5565  mov     r8d, 2
0x1800e556b  mov     r9d, dword ptr [rsp+0A8h+pv+4]; cx
0x1800e5570  mov     eax, ecx
0x1800e5572  cdq
0x1800e5573  mov     [rsp+0A8h+rop], 0CC0020h; rop
0x1800e557b  idiv    r8d
0x1800e557e  mov     [rsp+0A8h+y1], 0; y1
0x1800e5586  sub     r14d, eax
0x1800e5589  mov     [rsp+0A8h+x1], 0; x1
0x1800e5591  mov     eax, r9d
0x1800e5594  mov     qword ptr [rsp+0A8h+fuLoad], rsi; hdcSrc
0x1800e5599  cdq
0x1800e559a  mov     [rsp+0A8h+cy], ecx; cy
0x1800e559e  idiv    r8d
0x1800e55a1  mov     r8d, r14d; y
0x1800e55a4  mov     rcx, rbp; hdc
0x1800e55a7  sub     r15d, eax
0x1800e55aa  mov     edx, r15d; x
0x1800e55ad  call    cs:__imp_BitBlt
0x1800e55b3  mov     rdx, rbx; h
0x1800e55b6  mov     rcx, rsi; hdc
0x1800e55b9  call    cs:__imp_SelectObject
0x1800e55bf  mov     rcx, rsi; hdc
0x1800e55c2  call    cs:__imp_DeleteDC
0x1800e55c8  mov     rcx, rdi; ho
0x1800e55cb  call    cs:__imp_DeleteObject
0x1800e55d1  add     rsp, 78h
0x1800e55d5  pop     r15
0x1800e55d7  pop     r14
0x1800e55d9  pop     rdi
0x1800e55da  pop     rsi
0x1800e55db  pop     rbp
0x1800e55dc  pop     rbx
0x1800e55dd  retn
```
