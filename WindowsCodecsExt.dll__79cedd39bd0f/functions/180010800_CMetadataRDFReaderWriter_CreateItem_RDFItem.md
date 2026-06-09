# CMetadataRDFReaderWriter::CreateItem(RDFItem * *)

- ea: `0x180010800`
- end: `0x18001086d`
- name: `?CreateItem@CMetadataRDFReaderWriter@@MEBAJPEAPEAVRDFItem@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, struct RDFItem **)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180010800`
- `0x1800171c4`
- `0x1800215e8`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::CreateItem(CMetadataRDFReaderWriter *this, struct RDFItem **a2)
{
  _DWORD *v3; // rax
  unsigned int v4; // ebx
  bool v6; // zf

  v3 = operator new(0x50u);
  if ( v3 )
  {
    v3[2] = 0;
    *(_QWORD *)v3 = &RDFItem::`vftable';
    *((_QWORD *)v3 + 4) = 0;
    *((_QWORD *)v3 + 2) = 0;
    *((_QWORD *)v3 + 3) = 0;
    *((_QWORD *)v3 + 5) = 0;
    *((_QWORD *)v3 + 6) = 0;
    *((_QWORD *)v3 + 7) = 0;
    *((_QWORD *)v3 + 8) = 0;
    *((_QWORD *)v3 + 9) = 0;
    *a2 = (struct RDFItem *)v3;
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
0x180010800  push    rbx
0x180010802  sub     rsp, 20h
0x180010806  mov     ecx, 50h ; 'P'; Size
0x18001080b  mov     rbx, rdx
0x18001080e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010813  xor     edx, edx
0x180010815  test    rax, rax
0x180010818  jz      short loc_180010854
0x18001081a  lea     rcx, ??_7RDFItem@@6B@; const RDFItem::`vftable'
0x180010821  mov     [rax+8], edx
0x180010824  mov     [rax], rcx
0x180010827  mov     [rax+20h], rdx
0x18001082b  mov     [rax+10h], rdx
0x18001082f  mov     [rax+18h], rdx
0x180010833  mov     [rax+28h], rdx
0x180010837  mov     [rax+30h], rdx
0x18001083b  mov     [rax+38h], rdx
0x18001083f  mov     [rax+40h], rdx
0x180010843  mov     [rax+48h], rdx
0x180010847  mov     [rbx], rax
0x18001084a  mov     ebx, edx
0x18001084c  mov     eax, ebx
0x18001084e  add     rsp, 20h
0x180010852  pop     rbx
0x180010853  retn
0x180010854  cmp     cs:?g_doStackCaptures@@3HA, edx; int g_doStackCaptures
0x18001085a  mov     [rbx], rdx
0x18001085d  mov     ebx, 8007000Eh
0x180010862  jz      short loc_18001084C
0x180010864  mov     ecx, ebx; int
0x180010866  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001086b  jmp     short loc_18001084C
```
