# GEL::VectorImageResource::VectorImageResource(HENHMETAFILE__ *,bool)

- ea: `0x18016e9ac`
- end: `0x18016eaa5`
- name: `??0VectorImageResource@GEL@@QEAA@PEAUHENHMETAFILE__@@_N@Z`
- size: `249`
- prototype: `__int64 __fastcall(GEL::VectorImageResource *__hidden this, HENHMETAFILE, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800be150`

## callees

- `0x1800e3da4`
- `0x1800e4040`
- `0x1800e4128`
- `0x18016e9ac`

## import_xrefs

- `gdiplus!GdipCreateMetafileFromEmf` at `0x18016ea25`
- `gdiplus!GdipCreateMetafileFromEmf` at `0x18016ea25`
- `gdiplus!GdipDisposeImage` at `0x18016ea44`
- `gdiplus!GdipDisposeImage` at `0x18016ea8e`
- `gdiplus!GdipDisposeImage` at `0x18016ea44`
- `gdiplus!GdipDisposeImage` at `0x18016ea8e`

## string_xrefs

- `0x18016ea6a`: `VectorImageResource: Created image from HENHMETAFILE`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
GEL::VectorImageResource *__fastcall GEL::VectorImageResource::VectorImageResource(
        GEL::VectorImageResource *this,
        HENHMETAFILE a2)
{
  int v3; // esi
  __int64 v4; // rdi
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF
  const char *v7; // [rsp+58h] [rbp+20h] BYREF

  *(_QWORD *)this = &GEL::VectorImageResource::`vftable';
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_WORD *)this + 20) = 1;
  *((_BYTE *)this + 42) = 1;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_BYTE *)this + 80) = 2;
  *((_DWORD *)this + 21) = -1;
  ++GEL::VectorResourceTally::s_activeVectors;
  *(_QWORD *)((char *)this + 92) = 0;
  *(_QWORD *)((char *)this + 100) = 0;
  *((_BYTE *)this + 108) = 0;
  *((_QWORD *)this + 3) = a2;
  v6 = 0;
  v3 = GdipCreateMetafileFromEmf(a2, 0, &v6);
  if ( !v3 )
  {
    v4 = v6;
    v6 = 0;
    if ( *((_QWORD *)this + 1) )
      GdipDisposeImage();
    *((_QWORD *)this + 1) = v4;
    *((_BYTE *)this + 80) = 1;
  }
  *((_BYTE *)this + 106) = v3 != 0;
  GEL::VectorImageResource::ProcessMetafile(this);
  GEL::VectorImageResource::StoreDPI(this);
  v7 = "VectorImageResource: Created image from HENHMETAFILE";
  GEL::VectorImageResource::SendImageLogging(this, &v7);
  if ( v6 )
    GdipDisposeImage();
  return this;
}

```

## disassembly

```asm
0x18016e9ac  mov     r11, rsp
0x18016e9af  mov     [r11+18h], rbx
0x18016e9b3  mov     [r11+8], rcx
0x18016e9b7  push    rbp
0x18016e9b8  push    rsi
0x18016e9b9  push    rdi
0x18016e9ba  sub     rsp, 20h
0x18016e9be  mov     rax, rdx
0x18016e9c1  mov     rbx, rcx
0x18016e9c4  lea     rcx, ??_7VectorImageResource@GEL@@6B@; const GEL::VectorImageResource::`vftable'
0x18016e9cb  mov     [rbx], rcx
0x18016e9ce  xor     ebp, ebp
0x18016e9d0  mov     [rbx+8], rbp
0x18016e9d4  mov     [rbx+10h], rbp
0x18016e9d8  mov     [rbx+20h], rbp
0x18016e9dc  mov     word ptr [rbx+28h], 1
0x18016e9e2  mov     byte ptr [rbx+2Ah], 1
0x18016e9e6  mov     [rbx+30h], rbp
0x18016e9ea  mov     [rbx+38h], rbp
0x18016e9ee  mov     [rbx+40h], rbp
0x18016e9f2  mov     [rbx+48h], rbp
0x18016e9f6  mov     byte ptr [rbx+50h], 2
0x18016e9fa  mov     dword ptr [rbx+54h], 0FFFFFFFFh
0x18016ea01  inc     cs:?s_activeVectors@VectorResourceTally@GEL@@0GA; ushort GEL::VectorResourceTally::s_activeVectors
0x18016ea08  mov     [rbx+5Ch], rbp
0x18016ea0c  mov     [rbx+64h], rbp
0x18016ea10  mov     [rbx+6Ch], bpl
0x18016ea14  mov     [rbx+18h], rdx
0x18016ea18  mov     [r11+10h], rbp
0x18016ea1c  lea     r8, [r11+10h]
0x18016ea20  xor     edx, edx
0x18016ea22  mov     rcx, rax
0x18016ea25  call    cs:__imp_GdipCreateMetafileFromEmf
0x18016ea2b  mov     esi, eax
0x18016ea2d  test    eax, eax
0x18016ea2f  jnz     short loc_18016EA52
0x18016ea31  mov     rdi, [rsp+38h+arg_8]
0x18016ea36  mov     [rsp+38h+arg_8], rbp
0x18016ea3b  mov     rcx, [rbx+8]
0x18016ea3f  test    rcx, rcx
0x18016ea42  jz      short loc_18016EA4A
0x18016ea44  call    cs:__imp_GdipDisposeImage
0x18016ea4a  mov     [rbx+8], rdi
0x18016ea4e  mov     byte ptr [rbx+50h], 1
0x18016ea52  test    esi, esi
0x18016ea54  setnz   al
0x18016ea57  mov     [rbx+6Ah], al
0x18016ea5a  mov     rcx, rbx; this
0x18016ea5d  call    ?ProcessMetafile@VectorImageResource@GEL@@AEAAXXZ; GEL::VectorImageResource::ProcessMetafile(void)
0x18016ea62  mov     rcx, rbx; this
0x18016ea65  call    ?StoreDPI@VectorImageResource@GEL@@AEAAXXZ; GEL::VectorImageResource::StoreDPI(void)
0x18016ea6a  lea     rax, aVectorimageres_1; "VectorImageResource: Created image from"...
0x18016ea71  mov     [rsp+38h+arg_18], rax
0x18016ea76  lea     rdx, [rsp+38h+arg_18]
0x18016ea7b  mov     rcx, rbx
0x18016ea7e  call    ?SendImageLogging@VectorImageResource@GEL@@AEAAXAEBV?$StringLiteral@D@StringLiterals@Mso@@@Z; GEL::VectorImageResource::SendImageLogging(Mso::StringLiterals::StringLiteral<char> const &)
0x18016ea83  nop
0x18016ea84  mov     rcx, [rsp+38h+arg_8]
0x18016ea89  test    rcx, rcx
0x18016ea8c  jz      short loc_18016EA95
0x18016ea8e  call    cs:__imp_GdipDisposeImage
0x18016ea94  nop
0x18016ea95  mov     rax, rbx
0x18016ea98  mov     rbx, [rsp+38h+arg_10]
0x18016ea9d  add     rsp, 20h
0x18016eaa1  pop     rdi
0x18016eaa2  pop     rsi
0x18016eaa3  pop     rbp
0x18016eaa4  retn
```
