# GpFont::GpFont(HDC__ *,tagLOGFONTA *)

- ea: `0x180036748`
- end: `0x1800367da`
- name: `??0GpFont@@QEAA@PEAUHDC__@@PEAUtagLOGFONTA@@@Z`
- size: `146`
- prototype: `GpFont *__fastcall(GpFont *__hidden this, HDC, LOGFONTA *lplf)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800365f0`

## callees

- `0x180036748`
- `0x180036d58`

## import_xrefs

- `GDI32!CreateFontIndirectA` at `0x180036799`
- `GDI32!CreateFontIndirectA` at `0x180036799`
- `GDI32!SelectObject` at `0x1800367aa`
- `GDI32!SelectObject` at `0x1800367c9`
- `GDI32!SelectObject` at `0x1800367aa`
- `GDI32!SelectObject` at `0x1800367c9`
- `GDI32!DeleteObject` at `0x1800367d2`
- `GDI32!DeleteObject` at `0x1800367d2`

## pseudocode

```c
GpFont *__fastcall GpFont::GpFont(GpFont *this, HDC a2, LOGFONTA *lplf)
{
  HFONT FontIndirectA; // rax
  HGDIOBJ v7; // rsi
  HGDIOBJ v8; // rax

  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &GpFont::`vftable';
  *((_DWORD *)this + 2) = 1953383985;
  *((_QWORD *)this + 3) = 0;
  if ( a2 )
  {
    FontIndirectA = CreateFontIndirectA(lplf);
    if ( FontIndirectA )
    {
      v7 = SelectObject(a2, FontIndirectA);
      GpFont::InitializeFromDc(this, a2);
      if ( v7 )
      {
        v8 = SelectObject(a2, v7);
        DeleteObject(v8);
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x180036748  mov     [rsp+arg_0], rbx
0x18003674d  mov     [rsp+arg_8], rsi
0x180036752  push    rdi
0x180036753  sub     rsp, 20h
0x180036757  mov     qword ptr [rcx+10h], 0
0x18003675f  lea     rax, ??_7GpFont@@6B@; const GpFont::`vftable'
0x180036766  mov     [rcx], rax
0x180036769  mov     rdi, rdx
0x18003676c  mov     dword ptr [rcx+8], 746E4631h
0x180036773  mov     rbx, rcx
0x180036776  mov     qword ptr [rcx+18h], 0
0x18003677e  test    rdx, rdx
0x180036781  jnz     short loc_180036796
0x180036783  mov     rsi, [rsp+28h+arg_8]
0x180036788  mov     rax, rbx
0x18003678b  mov     rbx, [rsp+28h+arg_0]
0x180036790  add     rsp, 20h
0x180036794  pop     rdi
0x180036795  retn
0x180036796  mov     rcx, r8; lplf
0x180036799  call    cs:__imp_CreateFontIndirectA
0x18003679f  test    rax, rax
0x1800367a2  jz      short loc_180036783
0x1800367a4  mov     rdx, rax; h
0x1800367a7  mov     rcx, rdi; hdc
0x1800367aa  call    cs:__imp_SelectObject
0x1800367b0  mov     rdx, rdi; HDC
0x1800367b3  mov     rcx, rbx; this
0x1800367b6  mov     rsi, rax
0x1800367b9  call    ?InitializeFromDc@GpFont@@AEAAXPEAUHDC__@@@Z; GpFont::InitializeFromDc(HDC__ *)
0x1800367be  test    rsi, rsi
0x1800367c1  jz      short loc_180036783
0x1800367c3  mov     rdx, rsi; h
0x1800367c6  mov     rcx, rdi; hdc
0x1800367c9  call    cs:__imp_SelectObject
0x1800367cf  mov     rcx, rax; ho
0x1800367d2  call    cs:__imp_DeleteObject
0x1800367d8  jmp     short loc_180036783
```
