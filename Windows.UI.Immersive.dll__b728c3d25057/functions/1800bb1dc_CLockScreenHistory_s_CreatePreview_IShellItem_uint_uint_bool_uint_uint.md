# CLockScreenHistory::_s_CreatePreview(IShellItem *,uint,uint,bool,uint,uint)

- ea: `0x1800bb1dc`
- end: `0x1800bb2c7`
- name: `?_s_CreatePreview@CLockScreenHistory@@KAPEAUHBITMAP__@@PEAUIShellItem@@II_NII@Z`
- size: `235`
- prototype: `HBITMAP __fastcall(struct IShellItem *, unsigned int, unsigned int, bool, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800b96cc`

## callees

- `0x1800af8ec`
- `0x1800b0824`
- `0x1800bb1dc`
- `0x1800bb2d0`

## import_xrefs

- `GDI32!CreateCompatibleDC` at `0x1800bb202`
- `GDI32!CreateCompatibleDC` at `0x1800bb202`
- `GDI32!DeleteDC` at `0x1800bb2af`
- `GDI32!DeleteDC` at `0x1800bb2af`
- `GDI32!SelectObject` at `0x1800bb273`
- `GDI32!SelectObject` at `0x1800bb29c`
- `GDI32!SelectObject` at `0x1800bb273`
- `GDI32!SelectObject` at `0x1800bb29c`
- `GDI32!DeleteObject` at `0x1800bb2a6`
- `GDI32!DeleteObject` at `0x1800bb2a6`

## pseudocode

```c
HGDIOBJ __fastcall CLockScreenHistory::_s_CreatePreview(
        struct IShellItem *a1,
        unsigned int a2,
        unsigned int a3,
        bool a4,
        unsigned int a5,
        unsigned int a6)
{
  HGDIOBJ v7; // rsi
  HDC CompatibleDC; // rdi
  int v12; // eax
  HGDIOBJ v13; // rbx
  HGDIOBJ ho; // [rsp+40h] [rbp-20h] BYREF
  struct tagSIZE v16; // [rsp+48h] [rbp-18h] BYREF
  HGDIOBJ h; // [rsp+50h] [rbp-10h] BYREF
  void *v18; // [rsp+58h] [rbp-8h] BYREF

  v7 = 0;
  h = 0;
  CompatibleDC = CreateCompatibleDC(0);
  if ( CompatibleDC )
  {
    ho = 0;
    GetBitmapFromShellItem(a1, a2, a3, a5, a6, 1, (HBITMAP *)&ho);
    if ( ho )
    {
      v16.cx = a2;
      v16.cy = a3;
      v18 = 0;
      v12 = Create32BitHBITMAP(CompatibleDC, &v16, &v18, (HBITMAP *)&h);
      v7 = h;
      if ( v12 >= 0 )
      {
        v13 = SelectObject(CompatibleDC, h);
        CLockScreenHistory::_s_DrawImage(CompatibleDC, a2, a3, a4, (HBITMAP)ho);
        SelectObject(CompatibleDC, v13);
      }
      DeleteObject(ho);
    }
    DeleteDC(CompatibleDC);
  }
  return v7;
}

```

## disassembly

```asm
0x1800bb1dc  push    rbp
0x1800bb1de  push    rbx
0x1800bb1df  push    rsi
0x1800bb1e0  push    rdi
0x1800bb1e1  push    r12
0x1800bb1e3  push    r14
0x1800bb1e5  push    r15
0x1800bb1e7  mov     rbp, rsp
0x1800bb1ea  sub     rsp, 60h
0x1800bb1ee  mov     rbx, rcx
0x1800bb1f1  xor     esi, esi
0x1800bb1f3  xor     ecx, ecx; hdc
0x1800bb1f5  mov     [rbp+h], rsi
0x1800bb1f9  mov     r12b, r9b
0x1800bb1fc  mov     r14d, r8d
0x1800bb1ff  mov     r15d, edx
0x1800bb202  call    cs:__imp_CreateCompatibleDC
0x1800bb208  mov     rdi, rax
0x1800bb20b  test    rax, rax
0x1800bb20e  jz      loc_1800BB2B5
0x1800bb214  mov     r9d, [rbp+arg_20]; unsigned int
0x1800bb218  lea     rax, [rbp+ho]
0x1800bb21c  mov     [rsp+60h+var_30], rax; HBITMAP *
0x1800bb221  mov     r8d, r14d; unsigned int
0x1800bb224  mov     eax, [rbp+arg_28]
0x1800bb227  mov     edx, r15d; unsigned int
0x1800bb22a  mov     [rsp+60h+var_38], 1; bool
0x1800bb22f  mov     rcx, rbx; struct IShellItem *
0x1800bb232  mov     dword ptr [rsp+60h+var_40], eax; unsigned int
0x1800bb236  mov     [rbp+ho], rsi
0x1800bb23a  call    ?GetBitmapFromShellItem@@YAXPEAUIShellItem@@IIII_NPEAPEAUHBITMAP__@@@Z; GetBitmapFromShellItem(IShellItem *,uint,uint,uint,uint,bool,HBITMAP__ * *)
0x1800bb23f  cmp     [rbp+ho], rsi
0x1800bb243  jz      short loc_1800BB2AC
0x1800bb245  lea     r9, [rbp+h]; HBITMAP *
0x1800bb249  mov     [rbp+var_18.cx], r15d
0x1800bb24d  lea     r8, [rbp+var_8]; void **
0x1800bb251  mov     [rbp+var_18.cy], r14d
0x1800bb255  lea     rdx, [rbp+var_18]; struct tagSIZE *
0x1800bb259  mov     [rbp+var_8], rsi
0x1800bb25d  mov     rcx, rdi; hDC
0x1800bb260  call    ?Create32BitHBITMAP@@YAJPEAUHDC__@@PEBUtagSIZE@@PEAPEAXPEAPEAUHBITMAP__@@@Z; Create32BitHBITMAP(HDC__ *,tagSIZE const *,void * *,HBITMAP__ * *)
0x1800bb265  mov     rsi, [rbp+h]
0x1800bb269  test    eax, eax
0x1800bb26b  js      short loc_1800BB2A2
0x1800bb26d  mov     rdx, rsi; h
0x1800bb270  mov     rcx, rdi; hdc
0x1800bb273  call    cs:__imp_SelectObject
0x1800bb279  mov     r9b, r12b; bool
0x1800bb27c  mov     r8d, r14d; hSrc
0x1800bb27f  mov     rbx, rax
0x1800bb282  mov     edx, r15d; wDest
0x1800bb285  mov     rax, [rbp+ho]
0x1800bb289  mov     rcx, rdi; hdcDest
0x1800bb28c  mov     [rsp+60h+var_40], rax; HBITMAP
0x1800bb291  call    ?_s_DrawImage@CLockScreenHistory@@KAXPEAUHDC__@@II_NPEAUHBITMAP__@@@Z; CLockScreenHistory::_s_DrawImage(HDC__ *,uint,uint,bool,HBITMAP__ *)
0x1800bb296  mov     rdx, rbx; h
0x1800bb299  mov     rcx, rdi; hdc
0x1800bb29c  call    cs:__imp_SelectObject
0x1800bb2a2  mov     rcx, [rbp+ho]; ho
0x1800bb2a6  call    cs:__imp_DeleteObject
0x1800bb2ac  mov     rcx, rdi; hdc
0x1800bb2af  call    cs:__imp_DeleteDC
0x1800bb2b5  mov     rax, rsi
0x1800bb2b8  add     rsp, 60h
0x1800bb2bc  pop     r15
0x1800bb2be  pop     r14
0x1800bb2c0  pop     r12
0x1800bb2c2  pop     rdi
0x1800bb2c3  pop     rsi
0x1800bb2c4  pop     rbx
0x1800bb2c5  pop     rbp
0x1800bb2c6  retn
```
