# Gdiplus::SolidBrush::`scalar deleting destructor'(uint)

- ea: `0x18001d750`
- end: `0x18001d79c`
- name: `??_GSolidBrush@Gdiplus@@UEAAPEAXI@Z`
- size: `76`
- prototype: `void *__fastcall(Gdiplus::SolidBrush *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001d750`

## import_xrefs

- `gdiplus!GdipDeleteBrush` at `0x18001d76d`
- `gdiplus!GdipDeleteBrush` at `0x18001d76d`
- `gdiplus!GdipFree` at `0x18001d781`
- `gdiplus!GdipFree` at `0x18001d781`

## pseudocode

```c
Gdiplus::SolidBrush *__fastcall Gdiplus::SolidBrush::`scalar deleting destructor'(Gdiplus::SolidBrush *this, char a2)
{
  *(_QWORD *)this = &Gdiplus::SolidBrush::`vftable';
  GdipDeleteBrush(*((_QWORD *)this + 1));
  if ( (a2 & 1) != 0 )
    GdipFree(this);
  return this;
}

```

## disassembly

```asm
0x18001d750  mov     [rsp+arg_0], rbx
0x18001d755  push    rdi
0x18001d756  sub     rsp, 20h
0x18001d75a  lea     rax, ??_7SolidBrush@Gdiplus@@6B@; const Gdiplus::SolidBrush::`vftable'
0x18001d761  mov     rdi, rcx
0x18001d764  mov     [rcx], rax
0x18001d767  mov     ebx, edx
0x18001d769  mov     rcx, [rcx+8]
0x18001d76d  call    cs:__imp_GdipDeleteBrush
0x18001d774  nop     dword ptr [rax+rax+00h]
0x18001d779  test    bl, 1
0x18001d77c  jz      short loc_18001D78D
0x18001d77e  mov     rcx, rdi
0x18001d781  call    cs:__imp_GdipFree
0x18001d788  nop     dword ptr [rax+rax+00h]
0x18001d78d  mov     rbx, [rsp+28h+arg_0]
0x18001d792  mov     rax, rdi
0x18001d795  add     rsp, 20h
0x18001d799  pop     rdi
0x18001d79a  retn
```
