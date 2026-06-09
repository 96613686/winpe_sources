# CRenderer::FillRectWithColor(tagRECT *,ulong)

- ea: `0x180073910`
- end: `0x1800739a5`
- name: `?FillRectWithColor@CRenderer@@QEAAXPEAUtagRECT@@K@Z`
- size: `149`
- prototype: `void(CRenderer *__hidden this, struct tagRECT *, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180073e74`
- `0x1800741d4`

## callees

- `0x180073910`

## import_xrefs

- `GDI32!DeleteObject` at `0x180073995`
- `GDI32!DeleteObject` at `0x180073995`
- `GDI32!SelectObject` at `0x18007394b`
- `GDI32!SelectObject` at `0x18007398c`
- `GDI32!SelectObject` at `0x18007394b`
- `GDI32!SelectObject` at `0x18007398c`
- `GDI32!PatBlt` at `0x18007397c`
- `GDI32!PatBlt` at `0x18007397c`
- `GDI32!CreateSolidBrush` at `0x180073933`
- `GDI32!CreateSolidBrush` at `0x180073933`

## pseudocode

```c
void __fastcall CRenderer::FillRectWithColor(CRenderer *this, struct tagRECT *a2, COLORREF a3)
{
  HBRUSH SolidBrush; // rax
  HBRUSH v6; // rsi
  HGDIOBJ v7; // rbx

  if ( (*((_BYTE *)this + 288) & 1) != 0 )
    a3 = *((_DWORD *)this + 57);
  SolidBrush = CreateSolidBrush(a3);
  v6 = SolidBrush;
  if ( SolidBrush )
  {
    v7 = SelectObject(*((HDC *)this + 35), SolidBrush);
    PatBlt(*((HDC *)this + 35), a2->left, a2->top, a2->right - a2->left, a2->bottom - a2->top, 0xF00021u);
    SelectObject(*((HDC *)this + 35), v7);
    DeleteObject(v6);
  }
}

```

## disassembly

```asm
0x180073910  push    rbx
0x180073912  push    rsi
0x180073913  push    rdi
0x180073914  push    r14
0x180073916  sub     rsp, 38h
0x18007391a  test    byte ptr [rcx+120h], 1
0x180073921  mov     r14, rdx
0x180073924  mov     rdi, rcx
0x180073927  jz      short loc_180073930
0x180073929  mov     r8d, [rcx+0E4h]
0x180073930  mov     ecx, r8d; color
0x180073933  call    cs:__imp_CreateSolidBrush
0x180073939  mov     rsi, rax
0x18007393c  test    rax, rax
0x18007393f  jz      short loc_18007399B
0x180073941  mov     rcx, [rdi+118h]; hdc
0x180073948  mov     rdx, rax; h
0x18007394b  call    cs:__imp_SelectObject
0x180073951  mov     ecx, [r14+0Ch]
0x180073955  mov     rbx, rax
0x180073958  mov     r8d, [r14+4]; y
0x18007395c  sub     ecx, r8d
0x18007395f  mov     r9d, [r14+8]
0x180073963  sub     r9d, [r14]; w
0x180073966  mov     edx, [r14]; x
0x180073969  mov     [rsp+58h+rop], 0F00021h; rop
0x180073971  mov     [rsp+58h+h], ecx; h
0x180073975  mov     rcx, [rdi+118h]; hdc
0x18007397c  call    cs:__imp_PatBlt
0x180073982  mov     rcx, [rdi+118h]; hdc
0x180073989  mov     rdx, rbx; h
0x18007398c  call    cs:__imp_SelectObject
0x180073992  mov     rcx, rsi; ho
0x180073995  call    cs:__imp_DeleteObject
0x18007399b  add     rsp, 38h
0x18007399f  pop     r14
0x1800739a1  pop     rdi
0x1800739a2  pop     rsi
0x1800739a3  pop     rbx
0x1800739a4  retn
```
