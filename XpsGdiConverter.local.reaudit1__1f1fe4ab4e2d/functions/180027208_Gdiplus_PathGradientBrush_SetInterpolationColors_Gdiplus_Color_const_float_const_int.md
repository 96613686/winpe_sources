# Gdiplus::PathGradientBrush::SetInterpolationColors(Gdiplus::Color const *,float const *,int)

- ea: `0x180027208`
- end: `0x180027299`
- name: `?SetInterpolationColors@PathGradientBrush@Gdiplus@@QEAA?AW4Status@2@PEBVColor@2@PEBMH@Z`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180026438`

## callees

- `0x180008c44`
- `0x180008c7c`
- `0x180027208`

## import_xrefs

- `gdiplus!GdipSetPathGradientPresetBlend` at `0x180027267`
- `gdiplus!GdipSetPathGradientPresetBlend` at `0x180027267`

## pseudocode

```c
__int64 __fastcall Gdiplus::PathGradientBrush::SetInterpolationColors(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  void *v8; // rax
  void *v9; // rsi
  __int64 v10; // r8
  unsigned int v11; // eax
  unsigned __int64 v12; // rdx
  unsigned int v13; // ebx
  __int64 result; // rax

  if ( a4 > 0 && a2 )
  {
    v8 = operator new[](saturated_mul(a4, 4u));
    v9 = v8;
    v10 = 0;
    do
    {
      *((_DWORD *)v8 + v10) = *(_DWORD *)(a2 + 4 * v10);
      v10 = (unsigned int)(v10 + 1);
    }
    while ( (int)v10 < a4 );
    v11 = GdipSetPathGradientPresetBlend(*(_QWORD *)(a1 + 8), v8, a3, (unsigned int)a4);
    v13 = v11;
    if ( v11 )
      *(_DWORD *)(a1 + 16) = v11;
    else
      v13 = 0;
    operator delete(v9, v12);
    return v13;
  }
  else
  {
    result = 2;
    *(_DWORD *)(a1 + 16) = 2;
  }
  return result;
}

```

## disassembly

```asm
0x180027208  push    rbx
0x18002720a  push    rbp
0x18002720b  push    rsi
0x18002720c  push    rdi
0x18002720d  push    r14
0x18002720f  sub     rsp, 20h
0x180027213  movsxd  rbx, r9d
0x180027216  mov     rbp, r8
0x180027219  mov     r14, rdx
0x18002721c  mov     rdi, rcx
0x18002721f  test    r9d, r9d
0x180027222  jle     short loc_180027286
0x180027224  test    rdx, rdx
0x180027227  jz      short loc_180027286
0x180027229  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180027230  mov     eax, 4
0x180027235  mul     rbx
0x180027238  cmovb   rax, rcx
0x18002723c  mov     rcx, rax; unsigned __int64
0x18002723f  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180027244  mov     rsi, rax
0x180027247  xor     r8d, r8d
0x18002724a  mov     ecx, [r14+r8*4]
0x18002724e  mov     [rax+r8*4], ecx
0x180027252  inc     r8d
0x180027255  cmp     r8d, ebx
0x180027258  jl      short loc_18002724A
0x18002725a  mov     rcx, [rdi+8]
0x18002725e  mov     r9d, ebx
0x180027261  mov     r8, rbp
0x180027264  mov     rdx, rsi
0x180027267  call    cs:__imp_GdipSetPathGradientPresetBlend
0x18002726d  mov     ebx, eax
0x18002726f  test    eax, eax
0x180027271  jz      short loc_180027278
0x180027273  mov     [rdi+10h], eax
0x180027276  jmp     short loc_18002727A
0x180027278  xor     ebx, ebx
0x18002727a  mov     rcx, rsi; void *
0x18002727d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180027282  mov     eax, ebx
0x180027284  jmp     short loc_18002728E
0x180027286  mov     eax, 2
0x18002728b  mov     [rcx+10h], eax
0x18002728e  add     rsp, 20h
0x180027292  pop     r14
0x180027294  pop     rdi
0x180027295  pop     rsi
0x180027296  pop     rbp
0x180027297  pop     rbx
0x180027298  retn
```
