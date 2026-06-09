# Gdiplus::Graphics::`scalar deleting destructor'(uint)

- ea: `0x1800250f8`
- end: `0x18002511c`
- name: `??_GGraphics@Gdiplus@@QEAAPEAXI@Z`
- size: `36`
- prototype: `void *__fastcall(Gdiplus::Graphics *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180024c50`
- `0x1800277e0`

## import_xrefs

- `gdiplus!GdipDeleteGraphics` at `0x180025104`
- `gdiplus!GdipDeleteGraphics` at `0x180025104`
- `gdiplus!GdipFree` at `0x18002510d`
- `gdiplus!GdipFree` at `0x18002510d`

## pseudocode

```c
Gdiplus::Graphics *__fastcall Gdiplus::Graphics::`scalar deleting destructor'(Gdiplus::Graphics *this)
{
  GdipDeleteGraphics(*(_QWORD *)this);
  GdipFree(this);
  return this;
}

```

## disassembly

```asm
0x1800250f8  push    rbx
0x1800250fa  sub     rsp, 20h
0x1800250fe  mov     rbx, rcx
0x180025101  mov     rcx, [rcx]
0x180025104  call    cs:__imp_GdipDeleteGraphics
0x18002510a  mov     rcx, rbx
0x18002510d  call    cs:__imp_GdipFree
0x180025113  mov     rax, rbx
0x180025116  add     rsp, 20h
0x18002511a  pop     rbx
0x18002511b  retn
```
