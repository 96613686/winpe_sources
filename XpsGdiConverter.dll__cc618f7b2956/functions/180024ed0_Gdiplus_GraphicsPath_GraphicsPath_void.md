# Gdiplus::GraphicsPath::~GraphicsPath(void)

- ea: `0x180024ed0`
- end: `0x180024eda`
- name: `??1GraphicsPath@Gdiplus@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(Gdiplus::GraphicsPath *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180048471`

## import_xrefs

- `gdiplus!GdipDeletePath` at `0x180024ed3`

## pseudocode

```c
void __fastcall Gdiplus::GraphicsPath::~GraphicsPath(Gdiplus::GraphicsPath *this)
{
  GdipDeletePath(*(_QWORD *)this);
}

```

## disassembly

```asm
0x180024ed0  mov     rcx, [rcx]
0x180024ed3  jmp     cs:__imp_GdipDeletePath
```
