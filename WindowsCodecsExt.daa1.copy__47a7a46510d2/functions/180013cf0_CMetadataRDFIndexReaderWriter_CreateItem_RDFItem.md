# CMetadataRDFIndexReaderWriter::CreateItem(RDFItem * *)

- ea: `0x180013cf0`
- end: `0x180013d5e`
- name: `?CreateItem@CMetadataRDFIndexReaderWriter@@MEBAJPEAPEAVRDFItem@@@Z`
- size: `110`
- prototype: `__int64 __fastcall(CMetadataRDFIndexReaderWriter *__hidden this, struct RDFItem **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180013cf0`
- `0x1800171c4`
- `0x1800215e8`

## pseudocode

```c
__int64 __fastcall CMetadataRDFIndexReaderWriter::CreateItem(CMetadataRDFIndexReaderWriter *this, struct RDFItem **a2)
{
  struct RDFItem *v3; // rax
  unsigned int v4; // ebx
  bool v6; // zf

  v3 = (struct RDFItem *)operator new(0x50u);
  if ( v3 )
  {
    *((_QWORD *)v3 + 1) = 0;
    *(_QWORD *)v3 = &IndexItem::`vftable';
    *((_QWORD *)v3 + 4) = 0;
    *((_QWORD *)v3 + 2) = 0;
    *((_QWORD *)v3 + 3) = 0;
    *((_QWORD *)v3 + 5) = 0;
    *((_QWORD *)v3 + 6) = 0;
    *((_QWORD *)v3 + 7) = 0;
    *((_QWORD *)v3 + 8) = 0;
    *((_QWORD *)v3 + 9) = 0;
    *a2 = v3;
    return 0;
  }
  else
  {
    v6 = g_doStackCaptures == 0;
    *a2 = 0;
    v4 = -2147024882;
    if ( !v6 )
      DoStackCapture(-2147024882);
  }
  return v4;
}

```

## disassembly

```asm
0x180013cf0  push    rbx
0x180013cf2  sub     rsp, 20h
0x180013cf6  mov     ecx, 50h ; 'P'; Size
0x180013cfb  mov     rbx, rdx
0x180013cfe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013d03  xor     edx, edx
0x180013d05  test    rax, rax
0x180013d08  jz      short loc_180013D45
0x180013d0a  lea     rcx, ??_7IndexItem@@6B@; const IndexItem::`vftable'
0x180013d11  mov     [rax+8], rdx
0x180013d15  mov     [rax], rcx
0x180013d18  mov     [rax+20h], rdx
0x180013d1c  mov     [rax+10h], rdx
0x180013d20  mov     [rax+18h], rdx
0x180013d24  mov     [rax+28h], rdx
0x180013d28  mov     [rax+30h], rdx
0x180013d2c  mov     [rax+38h], rdx
0x180013d30  mov     [rax+40h], rdx
0x180013d34  mov     [rax+48h], rdx
0x180013d38  mov     [rbx], rax
0x180013d3b  mov     ebx, edx
0x180013d3d  mov     eax, ebx
0x180013d3f  add     rsp, 20h
0x180013d43  pop     rbx
0x180013d44  retn
0x180013d45  cmp     cs:?g_doStackCaptures@@3HA, edx; int g_doStackCaptures
0x180013d4b  mov     [rbx], rdx
0x180013d4e  mov     ebx, 8007000Eh
0x180013d53  jz      short loc_180013D3D
0x180013d55  mov     ecx, ebx; int
0x180013d57  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180013d5c  jmp     short loc_180013D3D
```
