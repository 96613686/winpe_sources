# xpsrdr::RectEmpty(D2D_RECT_F const &)

- ea: `0x180034cac`
- end: `0x180034cc7`
- name: `?RectEmpty@xpsrdr@@YA_NAEBUD2D_RECT_F@@@Z`
- size: `27`
- prototype: `bool __fastcall(xpsrdr *__hidden this, const struct D2D_RECT_F *)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x18000eee0`
- `0x1800109e0`
- `0x180014568`
- `0x180017ea0`
- `0x1800185f0`
- `0x180018a70`
- `0x180018c90`
- `0x180019c1c`
- `0x180029334`
- `0x18002990c`
- `0x180033fb0`
- `0x18003426c`
- `0x180034d10`
- `0x1800384fc`
- `0x1800393b4`
- `0x180039cd4`
- `0x18003a18c`

## callees

- `0x180034cac`

## pseudocode

```c
bool __fastcall xpsrdr::RectEmpty(xpsrdr *this, const struct D2D_RECT_F *a2)
{
  return *(float *)this >= *((float *)this + 2) || *((float *)this + 1) >= *((float *)this + 3);
}

```

## disassembly

```asm
0x180034cac  movss   xmm0, dword ptr [rcx]
0x180034cb0  comiss  xmm0, dword ptr [rcx+8]
0x180034cb4  jnb     short loc_180034CC4
0x180034cb6  movss   xmm0, dword ptr [rcx+4]
0x180034cbb  comiss  xmm0, dword ptr [rcx+0Ch]
0x180034cbf  jnb     short loc_180034CC4
0x180034cc1  xor     al, al
0x180034cc3  retn
0x180034cc4  mov     al, 1
0x180034cc6  retn
```
