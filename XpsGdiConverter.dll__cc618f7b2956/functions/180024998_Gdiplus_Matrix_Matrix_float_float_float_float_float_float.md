# Gdiplus::Matrix::Matrix(float,float,float,float,float,float)

- ea: `0x180024998`
- end: `0x180024a19`
- name: `??0Matrix@Gdiplus@@QEAA@MMMMMM@Z`
- size: `129`
- prototype: `__int64 __fastcall(Gdiplus::Matrix *__hidden this, float, float, float, float, float, float)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180025f30`
- `0x180026438`

## import_xrefs

- `gdiplus!GdipCreateMatrix2` at `0x1800249f5`
- `gdiplus!GdipCreateMatrix2` at `0x1800249f5`

## pseudocode

```c
Gdiplus::Matrix *__fastcall Gdiplus::Matrix::Matrix(Gdiplus::Matrix *this, float a2, float a3, float a4)
{
  __int64 v4; // rdx
  __int64 v5; // r8

  *((_DWORD *)this + 2) = GdipCreateMatrix2(this, v4, v5);
  *(_QWORD *)this = 0;
  return this;
}

```

## disassembly

```asm
0x180024998  mov     rax, rsp
0x18002499b  push    rbx
0x18002499c  sub     rsp, 60h
0x1800249a0  movss   xmm0, [rsp+68h+arg_30]
0x1800249a9  movaps  xmm5, xmm3
0x1800249ac  movss   xmm4, [rsp+68h+arg_28]
0x1800249b5  mov     rbx, rcx
0x1800249b8  movss   xmm3, [rsp+68h+arg_20]
0x1800249c1  movaps  xmmword ptr [rax-18h], xmm6
0x1800249c5  movaps  xmm6, xmm2
0x1800249c8  movaps  xmmword ptr [rax-28h], xmm7
0x1800249cc  movaps  xmm7, xmm1
0x1800249cf  mov     qword ptr [rax+8], 0
0x1800249d7  lea     rax, [rax+8]
0x1800249db  mov     [rsp+68h+var_38], rax
0x1800249e0  movaps  xmm2, xmm5
0x1800249e3  movss   [rsp+68h+var_40], xmm0
0x1800249e9  movaps  xmm1, xmm6
0x1800249ec  movaps  xmm0, xmm7
0x1800249ef  movss   [rsp+68h+var_48], xmm4
0x1800249f5  call    cs:__imp_GdipCreateMatrix2
0x1800249fb  movaps  xmm6, [rsp+68h+var_18]
0x180024a00  movaps  xmm7, [rsp+68h+var_28]
0x180024a05  mov     [rbx+8], eax
0x180024a08  mov     rax, [rsp+68h+arg_0]
0x180024a0d  mov     [rbx], rax
0x180024a10  mov     rax, rbx
0x180024a13  add     rsp, 60h
0x180024a17  pop     rbx
0x180024a18  retn
```
