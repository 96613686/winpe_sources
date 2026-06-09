# GpFont::GpFont(HDC__ *,tagLOGFONTW *)

- ea: `0x180014048`
- end: `0x1800140da`
- name: `??0GpFont@@QEAA@PEAUHDC__@@PEAUtagLOGFONTW@@@Z`
- size: `146`
- prototype: `GpFont *__fastcall(GpFont *__hidden this, HDC, LOGFONTW *lplf)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180013dbc`
- `0x180013ef0`

## callees

- `0x180014048`
- `0x180036d58`

## import_xrefs

- `GDI32!CreateFontIndirectW` at `0x180014099`
- `GDI32!CreateFontIndirectW` at `0x180014099`
- `GDI32!SelectObject` at `0x1800140aa`
- `GDI32!SelectObject` at `0x1800140c9`
- `GDI32!SelectObject` at `0x1800140aa`
- `GDI32!SelectObject` at `0x1800140c9`
- `GDI32!DeleteObject` at `0x1800140d2`
- `GDI32!DeleteObject` at `0x1800140d2`

## pseudocode

```c
GpFont *__fastcall GpFont::GpFont(GpFont *this, HDC a2, LOGFONTW *lplf)
{
  HFONT FontIndirectW; // rax
  HGDIOBJ v7; // rsi
  HGDIOBJ v8; // rax

  *((_QWORD *)this + 2) = 0;
  *(_QWORD *)this = &GpFont::`vftable';
  *((_DWORD *)this + 2) = 1953383985;
  *((_QWORD *)this + 3) = 0;
  if ( a2 )
  {
    FontIndirectW = CreateFontIndirectW(lplf);
    if ( FontIndirectW )
    {
      v7 = SelectObject(a2, FontIndirectW);
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
0x180014048  mov     [rsp+arg_0], rbx
0x18001404d  mov     [rsp+arg_8], rsi
0x180014052  push    rdi
0x180014053  sub     rsp, 20h
0x180014057  mov     qword ptr [rcx+10h], 0
0x18001405f  lea     rax, ??_7GpFont@@6B@; const GpFont::`vftable'
0x180014066  mov     [rcx], rax
0x180014069  mov     rdi, rdx
0x18001406c  mov     dword ptr [rcx+8], 746E4631h
0x180014073  mov     rbx, rcx
0x180014076  mov     qword ptr [rcx+18h], 0
0x18001407e  test    rdx, rdx
0x180014081  jnz     short loc_180014096
0x180014083  mov     rsi, [rsp+28h+arg_8]
0x180014088  mov     rax, rbx
0x18001408b  mov     rbx, [rsp+28h+arg_0]
0x180014090  add     rsp, 20h
0x180014094  pop     rdi
0x180014095  retn
0x180014096  mov     rcx, r8; lplf
0x180014099  call    cs:__imp_CreateFontIndirectW
0x18001409f  test    rax, rax
0x1800140a2  jz      short loc_180014083
0x1800140a4  mov     rdx, rax; h
0x1800140a7  mov     rcx, rdi; hdc
0x1800140aa  call    cs:__imp_SelectObject
0x1800140b0  mov     rdx, rdi; HDC
0x1800140b3  mov     rcx, rbx; this
0x1800140b6  mov     rsi, rax
0x1800140b9  call    ?InitializeFromDc@GpFont@@AEAAXPEAUHDC__@@@Z; GpFont::InitializeFromDc(HDC__ *)
0x1800140be  test    rsi, rsi
0x1800140c1  jz      short loc_180014083
0x1800140c3  mov     rdx, rsi; h
0x1800140c6  mov     rcx, rdi; hdc
0x1800140c9  call    cs:__imp_SelectObject
0x1800140cf  mov     rcx, rax; ho
0x1800140d2  call    cs:__imp_DeleteObject
0x1800140d8  jmp     short loc_180014083
```
