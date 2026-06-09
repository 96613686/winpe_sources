# GEL::CreateMetafileFromRecord(Gdiplus::GpMetafile * *,uint,uchar const *)

- ea: `0x180110be0`
- end: `0x180110c6e`
- name: `?CreateMetafileFromRecord@GEL@@YAXPEAPEAVGpMetafile@Gdiplus@@IPEBE@Z`
- size: `142`
- prototype: `void __fastcall(GEL *__hidden this, struct Gdiplus::GpMetafile **, unsigned int, const unsigned __int8 *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800a7618`
- `0x1801107c0`

## callees

- `0x180110be0`

## import_xrefs

- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180110c52`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x180110c52`
- `GDI32!SetEnhMetaFileBits` at `0x180110c06`
- `GDI32!SetEnhMetaFileBits` at `0x180110c06`
- `GDI32!SetMetaFileBitsEx` at `0x180110c2b`
- `GDI32!SetMetaFileBitsEx` at `0x180110c2b`
- `gdiplus!GdipCreateMetafileFromEmf` at `0x180110c65`
- `gdiplus!GdipCreateMetafileFromEmf` at `0x180110c65`
- `gdiplus!GdipCreateMetafileFromWmf` at `0x180110c45`
- `gdiplus!GdipCreateMetafileFromWmf` at `0x180110c45`

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
0x180110be0  mov     [rsp+arg_0], rbx
0x180110be5  push    rdi
0x180110be6  sub     rsp, 20h
0x180110bea  add     edx, 0FFFFFFF0h
0x180110bed  mov     rdi, rcx
0x180110bf0  cmp     dword ptr [r8+8], 2
0x180110bf5  mov     rbx, r8
0x180110bf8  mov     ecx, [r8+0Ch]; cbBuffer
0x180110bfc  jz      short loc_180110C1C
0x180110bfe  cmp     edx, ecx
0x180110c00  jb      short loc_180110C11
0x180110c02  lea     rdx, [r8+10h]; pb
0x180110c06  call    cs:__imp_SetEnhMetaFileBits
0x180110c0c  test    rax, rax
0x180110c0f  jnz     short loc_180110C5A
0x180110c11  mov     rbx, [rsp+28h+arg_0]
0x180110c16  add     rsp, 20h
0x180110c1a  pop     rdi
0x180110c1b  retn
0x180110c1c  lea     eax, [rcx+18h]
0x180110c1f  cmp     eax, ecx
0x180110c21  jb      short loc_180110C4D
0x180110c23  cmp     edx, eax
0x180110c25  jb      short loc_180110C11
0x180110c27  lea     rdx, [r8+28h]; lpData
0x180110c2b  call    cs:__imp_SetMetaFileBitsEx
0x180110c31  test    rax, rax
0x180110c34  jz      short loc_180110C11
0x180110c36  mov     r9, rdi
0x180110c39  lea     r8, [rbx+10h]
0x180110c3d  mov     edx, 1
0x180110c42  mov     rcx, rax
0x180110c45  call    cs:__imp_GdipCreateMetafileFromWmf
0x180110c4b  jmp     short loc_180110C11
0x180110c4d  mov     ecx, 2CB25Eh
0x180110c52  call    cs:__imp_MsoShipAssertTagProc
0x180110c58  jmp     short loc_180110C11
0x180110c5a  mov     r8, rdi
0x180110c5d  mov     edx, 1
0x180110c62  mov     rcx, rax
0x180110c65  call    cs:__imp_GdipCreateMetafileFromEmf
0x180110c6b  jmp     short loc_180110C11
```
