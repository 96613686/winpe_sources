# GEL::CreateMetafileFromRecord(Gdiplus::GpMetafile * *,uint,uchar const *)

- ea: `0x180105010`
- end: `0x18010509e`
- name: `?CreateMetafileFromRecord@GEL@@YAXPEAPEAVGpMetafile@Gdiplus@@IPEBE@Z`
- size: `142`
- prototype: `void __fastcall(GEL *__hidden this, struct Gdiplus::GpMetafile **, unsigned int, const unsigned __int8 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180104bf0`
- `0x180105f78`

## callees

- `0x180105010`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180105082`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180105082`
- `GDI32!SetEnhMetaFileBits` at `0x180105036`
- `GDI32!SetEnhMetaFileBits` at `0x180105036`
- `GDI32!SetMetaFileBitsEx` at `0x18010505b`
- `GDI32!SetMetaFileBitsEx` at `0x18010505b`
- `gdiplus!GdipCreateMetafileFromEmf` at `0x180105095`
- `gdiplus!GdipCreateMetafileFromEmf` at `0x180105095`
- `gdiplus!GdipCreateMetafileFromWmf` at `0x180105075`
- `gdiplus!GdipCreateMetafileFromWmf` at `0x180105075`

## pseudocode

```c
void __fastcall GEL::CreateMetafileFromRecord(
        GEL *this,
        struct Gdiplus::GpMetafile **a2,
        __int64 a3,
        const unsigned __int8 *a4)
{
  unsigned int v4; // edx
  UINT v7; // ecx
  HENHMETAFILE v8; // rax
  HMETAFILE v9; // rax

  v4 = (_DWORD)a2 - 16;
  v7 = *(_DWORD *)(a3 + 12);
  if ( *(_DWORD *)(a3 + 8) == 2 )
  {
    if ( v7 + 24 < v7 )
    {
      MsoShipAssertTagProc(2929246);
    }
    else if ( v4 >= v7 + 24 )
    {
      v9 = SetMetaFileBitsEx(v7, (const BYTE *)(a3 + 40));
      if ( v9 )
        GdipCreateMetafileFromWmf(v9, 1, a3 + 16, this);
    }
  }
  else if ( v4 >= v7 )
  {
    v8 = SetEnhMetaFileBits(v7, (const BYTE *)(a3 + 16));
    if ( v8 )
      GdipCreateMetafileFromEmf(v8, 1, this);
  }
}

```

## disassembly

```asm
0x180105010  mov     [rsp+arg_0], rbx
0x180105015  push    rdi
0x180105016  sub     rsp, 20h
0x18010501a  add     edx, 0FFFFFFF0h
0x18010501d  mov     rdi, rcx
0x180105020  cmp     dword ptr [r8+8], 2
0x180105025  mov     rbx, r8
0x180105028  mov     ecx, [r8+0Ch]; cbBuffer
0x18010502c  jz      short loc_18010504C
0x18010502e  cmp     edx, ecx
0x180105030  jb      short loc_180105041
0x180105032  lea     rdx, [r8+10h]; pb
0x180105036  call    cs:__imp_SetEnhMetaFileBits
0x18010503c  test    rax, rax
0x18010503f  jnz     short loc_18010508A
0x180105041  mov     rbx, [rsp+28h+arg_0]
0x180105046  add     rsp, 20h
0x18010504a  pop     rdi
0x18010504b  retn
0x18010504c  lea     eax, [rcx+18h]
0x18010504f  cmp     eax, ecx
0x180105051  jb      short loc_18010507D
0x180105053  cmp     edx, eax
0x180105055  jb      short loc_180105041
0x180105057  lea     rdx, [r8+28h]; lpData
0x18010505b  call    cs:__imp_SetMetaFileBitsEx
0x180105061  test    rax, rax
0x180105064  jz      short loc_180105041
0x180105066  mov     r9, rdi
0x180105069  lea     r8, [rbx+10h]
0x18010506d  mov     edx, 1
0x180105072  mov     rcx, rax
0x180105075  call    cs:__imp_GdipCreateMetafileFromWmf
0x18010507b  jmp     short loc_180105041
0x18010507d  mov     ecx, 2CB25Eh
0x180105082  call    cs:__imp_MsoShipAssertTagProc
0x180105088  jmp     short loc_180105041
0x18010508a  mov     r8, rdi
0x18010508d  mov     edx, 1
0x180105092  mov     rcx, rax
0x180105095  call    cs:__imp_GdipCreateMetafileFromEmf
0x18010509b  jmp     short loc_180105041
```
