# CInkOverlay::_WindowInputRectangleToClippableRegion(HDC__ *,tagRECT *)

- ea: `0x1800e328c`
- end: `0x1800e334e`
- name: `?_WindowInputRectangleToClippableRegion@CInkOverlay@@AEAAXPEAUHDC__@@PEAUtagRECT@@@Z`
- size: `194`
- prototype: `void(CInkOverlay *__hidden this, HDC, struct tagRECT *)`
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1800d7fd0`
- `0x1800d9b90`
- `0x1800dc0ec`
- `0x1800dc860`
- `0x1800e0efc`
- `0x1800e20b0`
- `0x1800e2340`

## callees

- `0x1800365f8`
- `0x180036824`
- `0x1800e328c`

## import_xrefs

- `USER32!IsRectEmpty` at `0x1800e32ba`
- `USER32!IsRectEmpty` at `0x1800e32ba`
- `GDI32!IntersectClipRect` at `0x1800e331a`
- `GDI32!IntersectClipRect` at `0x1800e331a`
- `GDI32!SelectClipRgn` at `0x1800e332b`
- `GDI32!SelectClipRgn` at `0x1800e332b`
- `GDI32!CreateRectRgn` at `0x1800e32d6`
- `GDI32!CreateRectRgn` at `0x1800e32f8`
- `GDI32!CreateRectRgn` at `0x1800e32d6`
- `GDI32!CreateRectRgn` at `0x1800e32f8`
- `GDI32!DeleteObject` at `0x1800e3334`
- `GDI32!DeleteObject` at `0x1800e3334`

## pseudocode

```c
void __fastcall CInkOverlay::_WindowInputRectangleToClippableRegion(CInkOverlay *this, HDC a2, struct tagRECT *a3)
{
  HRGN RectRgn; // rdi
  _BYTE v7[56]; // [rsp+30h] [rbp-38h] BYREF

  CInkAutoDataLock::CInkAutoDataLock((CInkAutoDataLock *)v7, (struct _RTL_CRITICAL_SECTION *)((char *)this + 272));
  if ( IsRectEmpty((const RECT *)this + 21) )
  {
    if ( !a3 )
      goto LABEL_8;
    RectRgn = CreateRectRgn(a3->left, a3->top, a3->right, a3->bottom);
  }
  else
  {
    RectRgn = CreateRectRgn(
                *((_DWORD *)this + 84),
                *((_DWORD *)this + 85),
                *((_DWORD *)this + 86),
                *((_DWORD *)this + 87));
    if ( a3 )
      IntersectClipRect(a2, a3->left, a3->top, a3->right, a3->bottom);
  }
  if ( RectRgn )
  {
    SelectClipRgn(a2, RectRgn);
    DeleteObject(RectRgn);
  }
LABEL_8:
  CInkAutoDataLock::~CInkAutoDataLock((CInkAutoDataLock *)v7);
}

```

## disassembly

```asm
0x1800e328c  push    rbx
0x1800e328e  push    rsi
0x1800e328f  push    rdi
0x1800e3290  push    r14
0x1800e3292  sub     rsp, 48h
0x1800e3296  mov     rsi, rdx
0x1800e3299  mov     rdi, rcx
0x1800e329c  lea     rdx, [rcx+110h]; struct _RTL_CRITICAL_SECTION *
0x1800e32a3  mov     rbx, r8
0x1800e32a6  lea     rcx, [rsp+68h+var_38]; this
0x1800e32ab  call    ??0CInkAutoDataLock@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInkAutoDataLock::CInkAutoDataLock(_RTL_CRITICAL_SECTION *)
0x1800e32b0  lea     r14, [rdi+150h]
0x1800e32b7  mov     rcx, r14; lprc
0x1800e32ba  call    cs:__imp_IsRectEmpty
0x1800e32c0  test    eax, eax
0x1800e32c2  jz      short loc_1800E32E1
0x1800e32c4  test    rbx, rbx
0x1800e32c7  jz      short loc_1800E333A
0x1800e32c9  mov     r9d, [rbx+0Ch]; y2
0x1800e32cd  mov     r8d, [rbx+8]; x2
0x1800e32d1  mov     edx, [rbx+4]; y1
0x1800e32d4  mov     ecx, [rbx]; x1
0x1800e32d6  call    cs:__imp_CreateRectRgn
0x1800e32dc  mov     rdi, rax
0x1800e32df  jmp     short loc_1800E3320
0x1800e32e1  mov     r9d, [rdi+15Ch]; y2
0x1800e32e8  mov     r8d, [rdi+158h]; x2
0x1800e32ef  mov     edx, [rdi+154h]; y1
0x1800e32f5  mov     ecx, [r14]; x1
0x1800e32f8  call    cs:__imp_CreateRectRgn
0x1800e32fe  mov     rdi, rax
0x1800e3301  test    rbx, rbx
0x1800e3304  jz      short loc_1800E3320
0x1800e3306  mov     eax, [rbx+0Ch]
0x1800e3309  mov     rcx, rsi; hdc
0x1800e330c  mov     r9d, [rbx+8]; right
0x1800e3310  mov     r8d, [rbx+4]; top
0x1800e3314  mov     edx, [rbx]; left
0x1800e3316  mov     [rsp+68h+bottom], eax; bottom
0x1800e331a  call    cs:__imp_IntersectClipRect
0x1800e3320  test    rdi, rdi
0x1800e3323  jz      short loc_1800E333A
0x1800e3325  mov     rdx, rdi; hrgn
0x1800e3328  mov     rcx, rsi; hdc
0x1800e332b  call    cs:__imp_SelectClipRgn
0x1800e3331  mov     rcx, rdi; ho
0x1800e3334  call    cs:__imp_DeleteObject
0x1800e333a  lea     rcx, [rsp+68h+var_38]; this
0x1800e333f  call    ??1CInkAutoDataLock@@QEAA@XZ; CInkAutoDataLock::~CInkAutoDataLock(void)
0x1800e3344  add     rsp, 48h
0x1800e3348  pop     r14
0x1800e334a  pop     rdi
0x1800e334b  pop     rsi
0x1800e334c  pop     rbx
0x1800e334d  retn
```
