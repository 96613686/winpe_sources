# CMetadataXMPAltReaderWriter::CreateItem(RDFItem * *)

- ea: `0x180022fd0`
- end: `0x18002303e`
- name: `?CreateItem@CMetadataXMPAltReaderWriter@@MEBAJPEAPEAVRDFItem@@@Z`
- size: `110`
- prototype: `__int64 __fastcall(CMetadataXMPAltReaderWriter *__hidden this, struct RDFItem **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800171c4`
- `0x1800215e8`
- `0x180022fd0`

## pseudocode

```c
__int64 __fastcall CMetadataXMPAltReaderWriter::CreateItem(CMetadataXMPAltReaderWriter *this, struct RDFItem **a2)
{
  struct RDFItem *v3; // rax
  unsigned int v4; // ebx
  bool v5; // zf

  v3 = (struct RDFItem *)operator new(0x50u);
  if ( v3 )
  {
    *((_QWORD *)v3 + 1) = 0;
    *(_QWORD *)v3 = &AltItem::`vftable';
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
    v5 = g_doStackCaptures == 0;
    *a2 = 0;
    v4 = -2147024882;
    if ( !v5 )
      DoStackCapture(-2147024882);
  }
  return v4;
}

```

## disassembly

```asm
0x180022fd0  push    rbx
0x180022fd2  sub     rsp, 20h
0x180022fd6  mov     ecx, 50h ; 'P'; Size
0x180022fdb  mov     rbx, rdx
0x180022fde  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022fe3  xor     edx, edx
0x180022fe5  test    rax, rax
0x180022fe8  jz      short loc_18002301F
0x180022fea  lea     rcx, ??_7AltItem@@6B@; const AltItem::`vftable'
0x180022ff1  mov     [rax+8], rdx
0x180022ff5  mov     [rax], rcx
0x180022ff8  mov     [rax+20h], rdx
0x180022ffc  mov     [rax+10h], rdx
0x180023000  mov     [rax+18h], rdx
0x180023004  mov     [rax+28h], rdx
0x180023008  mov     [rax+30h], rdx
0x18002300c  mov     [rax+38h], rdx
0x180023010  mov     [rax+40h], rdx
0x180023014  mov     [rax+48h], rdx
0x180023018  mov     [rbx], rax
0x18002301b  mov     ebx, edx
0x18002301d  jmp     short loc_180023036
0x18002301f  cmp     cs:?g_doStackCaptures@@3HA, edx; int g_doStackCaptures
0x180023025  mov     [rbx], rdx
0x180023028  mov     ebx, 8007000Eh
0x18002302d  jz      short loc_180023036
0x18002302f  mov     ecx, ebx; int
0x180023031  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180023036  mov     eax, ebx
0x180023038  add     rsp, 20h
0x18002303c  pop     rbx
0x18002303d  retn
```
