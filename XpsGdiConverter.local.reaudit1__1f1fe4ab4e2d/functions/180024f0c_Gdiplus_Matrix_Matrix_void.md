# Gdiplus::Matrix::~Matrix(void)

- ea: `0x180024f0c`
- end: `0x180024f16`
- name: `??1Matrix@Gdiplus@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(Gdiplus::Matrix *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180048483`

## import_xrefs

- `gdiplus!GdipDeleteMatrix` at `0x180024f0f`

## pseudocode

```c
void __fastcall Gdiplus::Matrix::~Matrix(Gdiplus::Matrix *this)
{
  GdipDeleteMatrix(*(_QWORD *)this);
}

```

## disassembly

```asm
0x180024f0c  mov     rcx, [rcx]
0x180024f0f  jmp     cs:__imp_GdipDeleteMatrix
```
