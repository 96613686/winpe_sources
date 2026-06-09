# Gdiplus::SolidBrush::~SolidBrush(void)

- ea: `0x18001d608`
- end: `0x18001d61d`
- name: `??1SolidBrush@Gdiplus@@UEAA@XZ`
- size: `21`
- prototype: `void __fastcall(Gdiplus::SolidBrush *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180031b22`
- `0x180031b34`
- `0x180031b46`

## import_xrefs

- `gdiplus!GdipDeleteBrush` at `0x18001d616`

## pseudocode

```c
void __fastcall Gdiplus::SolidBrush::~SolidBrush(Gdiplus::SolidBrush *this)
{
  *(_QWORD *)this = &Gdiplus::SolidBrush::`vftable';
  GdipDeleteBrush(*((_QWORD *)this + 1));
}

```

## disassembly

```asm
0x18001d608  lea     rax, ??_7SolidBrush@Gdiplus@@6B@; const Gdiplus::SolidBrush::`vftable'
0x18001d60f  mov     [rcx], rax
0x18001d612  mov     rcx, [rcx+8]
0x18001d616  jmp     cs:__imp_GdipDeleteBrush
```
