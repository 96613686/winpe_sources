# CGdiGraphicContext::`vector deleting destructor'(uint)

- ea: `0x1800d8f10`
- end: `0x1800d8f7e`
- name: `??_ECGdiGraphicContext@@UEAAPEAXI@Z`
- size: `110`
- prototype: `void *__fastcall(CGdiGraphicContext *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x1800d8f10`
- `0x18013bea0`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1800d8f76`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x1800d8f76`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1800d8f6c`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x1800d8f6c`

## pseudocode

```c
CGdiGraphicContext *__fastcall CGdiGraphicContext::`vector deleting destructor'(CGdiGraphicContext *this, char a2)
{
  HDC v4; // rcx

  *(_QWORD *)this = &CGdiGraphicContext::`vftable';
  v4 = (HDC)*((_QWORD *)this + 4);
  if ( v4 )
  {
    SelectObject(v4, *((HGDIOBJ *)this + 5));
    DeleteDC(*((HDC *)this + 4));
  }
  *(_QWORD *)this = &IGraphicContext::`vftable';
  *((_QWORD *)this + 1) = &IDpiAccessor::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this, 0x30u);
  return this;
}

```

## disassembly

```asm
0x1800d8f10  mov     [rsp+arg_0], rbx
0x1800d8f15  push    rdi
0x1800d8f16  sub     rsp, 20h
0x1800d8f1a  lea     rax, ??_7CGdiGraphicContext@@6B@; const CGdiGraphicContext::`vftable'
0x1800d8f21  mov     rbx, rcx
0x1800d8f24  mov     [rcx], rax
0x1800d8f27  mov     edi, edx
0x1800d8f29  mov     rcx, [rcx+20h]; hdc
0x1800d8f2d  test    rcx, rcx
0x1800d8f30  jnz     short loc_1800D8F68
0x1800d8f32  lea     rax, ??_7IGraphicContext@@6B@; const IGraphicContext::`vftable'
0x1800d8f39  mov     [rbx], rax
0x1800d8f3c  lea     rax, ??_7IDpiAccessor@@6B@; const IDpiAccessor::`vftable'
0x1800d8f43  mov     [rbx+8], rax
0x1800d8f47  test    dil, 1
0x1800d8f4b  jz      short loc_1800D8F5A
0x1800d8f4d  mov     edx, 30h ; '0'; unsigned __int64
0x1800d8f52  mov     rcx, rbx; void *
0x1800d8f55  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800d8f5a  mov     rax, rbx
0x1800d8f5d  mov     rbx, [rsp+28h+arg_0]
0x1800d8f62  add     rsp, 20h
0x1800d8f66  pop     rdi
0x1800d8f67  retn
0x1800d8f68  mov     rdx, [rbx+28h]; h
0x1800d8f6c  call    cs:__imp_SelectObject
0x1800d8f72  mov     rcx, [rbx+20h]; hdc
0x1800d8f76  call    cs:__imp_DeleteDC
0x1800d8f7c  jmp     short loc_1800D8F32
```
