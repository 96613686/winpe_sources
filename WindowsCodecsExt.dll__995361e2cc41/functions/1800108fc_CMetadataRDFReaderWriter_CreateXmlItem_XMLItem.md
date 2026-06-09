# CMetadataRDFReaderWriter::CreateXmlItem(XMLItem * *)

- ea: `0x1800108fc`
- end: `0x180010959`
- name: `?CreateXmlItem@CMetadataRDFReaderWriter@@IEBAJPEAPEAVXMLItem@@@Z`
- size: `93`
- prototype: `__int64 __fastcall(CMetadataRDFReaderWriter *__hidden this, struct XMLItem **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800151b0`
- `0x1800162c0`

## callees

- `0x1800108fc`
- `0x1800171c4`
- `0x1800215e8`

## pseudocode

```c
__int64 __fastcall CMetadataRDFReaderWriter::CreateXmlItem(CMetadataRDFReaderWriter *this, struct XMLItem **a2)
{
  struct XMLItem *v3; // rax
  unsigned int v4; // ebx
  bool v6; // zf

  v3 = (struct XMLItem *)operator new(0x30u);
  if ( v3 )
  {
    *a2 = v3;
    *(_QWORD *)v3 = &XMLItem::`vftable';
    v4 = 0;
    *((_DWORD *)v3 + 2) = 0;
    *((_QWORD *)v3 + 4) = 0;
    *((_QWORD *)v3 + 2) = 0;
    *((_QWORD *)v3 + 3) = 0;
    *((_QWORD *)v3 + 5) = 0;
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
0x1800108fc  push    rbx
0x1800108fe  sub     rsp, 20h
0x180010902  mov     ecx, 30h ; '0'; Size
0x180010907  mov     rbx, rdx
0x18001090a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001090f  xor     edx, edx
0x180010911  test    rax, rax
0x180010914  jz      short loc_180010940
0x180010916  lea     rcx, ??_7XMLItem@@6B@; const XMLItem::`vftable'
0x18001091d  mov     [rbx], rax
0x180010920  mov     [rax], rcx
0x180010923  mov     ebx, edx
0x180010925  mov     [rax+8], edx
0x180010928  mov     [rax+20h], rdx
0x18001092c  mov     [rax+10h], rdx
0x180010930  mov     [rax+18h], rdx
0x180010934  mov     [rax+28h], rdx
0x180010938  mov     eax, ebx
0x18001093a  add     rsp, 20h
0x18001093e  pop     rbx
0x18001093f  retn
0x180010940  cmp     cs:?g_doStackCaptures@@3HA, edx; int g_doStackCaptures
0x180010946  mov     [rbx], rdx
0x180010949  mov     ebx, 8007000Eh
0x18001094e  jz      short loc_180010938
0x180010950  mov     ecx, ebx; int
0x180010952  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180010957  jmp     short loc_180010938
```
