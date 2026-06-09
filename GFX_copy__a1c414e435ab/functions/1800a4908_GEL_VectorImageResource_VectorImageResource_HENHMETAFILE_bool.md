# GEL::VectorImageResource::VectorImageResource(HENHMETAFILE__ *,bool)

- ea: `0x1800a4908`
- end: `0x1800a4a01`
- name: `??0VectorImageResource@GEL@@QEAA@PEAUHENHMETAFILE__@@_N@Z`
- size: `249`
- prototype: `__int64 __fastcall(GEL::VectorImageResource *__hidden this, HENHMETAFILE, bool)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800a4770`

## callees

- `0x1800a4908`
- `0x1800a4e54`
- `0x1800a50f4`
- `0x1800a51e0`

## import_xrefs

- `gdiplus!GdipCreateMetafileFromEmf` at `0x1800a4981`
- `gdiplus!GdipCreateMetafileFromEmf` at `0x1800a4981`
- `gdiplus!GdipDisposeImage` at `0x1800a49a0`
- `gdiplus!GdipDisposeImage` at `0x1800a49ea`
- `gdiplus!GdipDisposeImage` at `0x1800a49a0`
- `gdiplus!GdipDisposeImage` at `0x1800a49ea`

## string_xrefs

- `0x1800a49c6`: `VectorImageResource: Created image from HENHMETAFILE`

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
0x1800a4908  mov     r11, rsp
0x1800a490b  mov     [r11+18h], rbx
0x1800a490f  mov     [r11+8], rcx
0x1800a4913  push    rbp
0x1800a4914  push    rsi
0x1800a4915  push    rdi
0x1800a4916  sub     rsp, 20h
0x1800a491a  mov     rax, rdx
0x1800a491d  mov     rbx, rcx
0x1800a4920  lea     rcx, ??_7VectorImageResource@GEL@@6B@; const GEL::VectorImageResource::`vftable'
0x1800a4927  mov     [rbx], rcx
0x1800a492a  xor     ebp, ebp
0x1800a492c  mov     [rbx+8], rbp
0x1800a4930  mov     [rbx+10h], rbp
0x1800a4934  mov     [rbx+20h], rbp
0x1800a4938  mov     word ptr [rbx+28h], 1
0x1800a493e  mov     byte ptr [rbx+2Ah], 1
0x1800a4942  mov     [rbx+30h], rbp
0x1800a4946  mov     [rbx+38h], rbp
0x1800a494a  mov     [rbx+40h], rbp
0x1800a494e  mov     [rbx+48h], rbp
0x1800a4952  mov     byte ptr [rbx+50h], 2
0x1800a4956  mov     dword ptr [rbx+54h], 0FFFFFFFFh
0x1800a495d  inc     cs:?s_activeVectors@VectorResourceTally@GEL@@0GA; ushort GEL::VectorResourceTally::s_activeVectors
0x1800a4964  mov     [rbx+5Ch], rbp
0x1800a4968  mov     [rbx+64h], rbp
0x1800a496c  mov     [rbx+6Ch], bpl
0x1800a4970  mov     [rbx+18h], rdx
0x1800a4974  mov     [r11+10h], rbp
0x1800a4978  lea     r8, [r11+10h]
0x1800a497c  xor     edx, edx
0x1800a497e  mov     rcx, rax
0x1800a4981  call    cs:__imp_GdipCreateMetafileFromEmf
0x1800a4987  mov     esi, eax
0x1800a4989  test    eax, eax
0x1800a498b  jnz     short loc_1800A49AE
0x1800a498d  mov     rdi, [rsp+38h+arg_8]
0x1800a4992  mov     [rsp+38h+arg_8], rbp
0x1800a4997  mov     rcx, [rbx+8]
0x1800a499b  test    rcx, rcx
0x1800a499e  jz      short loc_1800A49A6
0x1800a49a0  call    cs:__imp_GdipDisposeImage
0x1800a49a6  mov     [rbx+8], rdi
0x1800a49aa  mov     byte ptr [rbx+50h], 1
0x1800a49ae  test    esi, esi
0x1800a49b0  setnz   al
0x1800a49b3  mov     [rbx+6Ah], al
0x1800a49b6  mov     rcx, rbx; this
0x1800a49b9  call    ?ProcessMetafile@VectorImageResource@GEL@@AEAAXXZ; GEL::VectorImageResource::ProcessMetafile(void)
0x1800a49be  mov     rcx, rbx; this
0x1800a49c1  call    ?StoreDPI@VectorImageResource@GEL@@AEAAXXZ; GEL::VectorImageResource::StoreDPI(void)
0x1800a49c6  lea     rax, aVectorimageres_1; "VectorImageResource: Created image from"...
0x1800a49cd  mov     [rsp+38h+arg_18], rax
0x1800a49d2  lea     rdx, [rsp+38h+arg_18]
0x1800a49d7  mov     rcx, rbx
0x1800a49da  call    ?SendImageLogging@VectorImageResource@GEL@@AEAAXAEBV?$StringLiteral@D@StringLiterals@Mso@@@Z; GEL::VectorImageResource::SendImageLogging(Mso::StringLiterals::StringLiteral<char> const &)
0x1800a49df  nop
0x1800a49e0  mov     rcx, [rsp+38h+arg_8]
0x1800a49e5  test    rcx, rcx
0x1800a49e8  jz      short loc_1800A49F1
0x1800a49ea  call    cs:__imp_GdipDisposeImage
0x1800a49f0  nop
0x1800a49f1  mov     rax, rbx
0x1800a49f4  mov     rbx, [rsp+38h+arg_10]
0x1800a49f9  add     rsp, 20h
0x1800a49fd  pop     rdi
0x1800a49fe  pop     rsi
0x1800a49ff  pop     rbp
0x1800a4a00  retn
```
