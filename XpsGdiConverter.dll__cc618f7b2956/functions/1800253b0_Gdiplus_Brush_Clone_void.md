# Gdiplus::Brush::Clone(void)

- ea: `0x1800253b0`
- end: `0x180025417`
- name: `?Clone@Brush@Gdiplus@@UEBAPEAV12@XZ`
- size: `103`
- prototype: `struct Gdiplus::Brush *__fastcall(Gdiplus::Brush *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800253b0`

## import_xrefs

- `gdiplus!GdipCloneBrush` at `0x1800253cb`
- `gdiplus!GdipCloneBrush` at `0x1800253cb`
- `gdiplus!GdipAlloc` at `0x1800253dd`
- `gdiplus!GdipAlloc` at `0x1800253dd`
- `gdiplus!GdipDeleteBrush` at `0x180025406`
- `gdiplus!GdipDeleteBrush` at `0x180025406`

## pseudocode

```c
struct Gdiplus::Brush *__fastcall Gdiplus::Brush::Clone(Gdiplus::Brush *this)
{
  int v2; // eax
  __int64 v3; // rax
  __int64 v4; // rcx
  __int64 v5; // rdx
  int v6; // eax
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF

  v8 = 0;
  v2 = GdipCloneBrush(*((_QWORD *)this + 1), &v8);
  if ( v2 )
    *((_DWORD *)this + 4) = v2;
  v3 = GdipAlloc(24);
  v4 = v8;
  v5 = v3;
  if ( v3 )
  {
    v6 = *((_DWORD *)this + 4);
    *(_QWORD *)v5 = &Gdiplus::LinearGradientBrush::`vftable';
    *(_DWORD *)(v5 + 16) = v6;
    *(_QWORD *)(v5 + 8) = v4;
  }
  else
  {
    GdipDeleteBrush(v8);
    return 0;
  }
  return (struct Gdiplus::Brush *)v5;
}

```

## disassembly

```asm
0x1800253b0  push    rbx
0x1800253b2  sub     rsp, 20h
0x1800253b6  mov     rbx, rcx
0x1800253b9  mov     [rsp+28h+arg_0], 0
0x1800253c2  mov     rcx, [rcx+8]
0x1800253c6  lea     rdx, [rsp+28h+arg_0]
0x1800253cb  call    cs:__imp_GdipCloneBrush
0x1800253d1  test    eax, eax
0x1800253d3  jz      short loc_1800253D8
0x1800253d5  mov     [rbx+10h], eax
0x1800253d8  mov     ecx, 18h
0x1800253dd  call    cs:__imp_GdipAlloc
0x1800253e3  mov     rcx, [rsp+28h+arg_0]
0x1800253e8  mov     rdx, rax
0x1800253eb  test    rax, rax
0x1800253ee  jz      short loc_180025406
0x1800253f0  mov     eax, [rbx+10h]
0x1800253f3  lea     r8, ??_7LinearGradientBrush@Gdiplus@@6B@; const Gdiplus::LinearGradientBrush::`vftable'
0x1800253fa  mov     [rdx], r8
0x1800253fd  mov     [rdx+10h], eax
0x180025400  mov     [rdx+8], rcx
0x180025404  jmp     short loc_18002540E
0x180025406  call    cs:__imp_GdipDeleteBrush
0x18002540c  xor     edx, edx
0x18002540e  mov     rax, rdx
0x180025411  add     rsp, 20h
0x180025415  pop     rbx
0x180025416  retn
```
