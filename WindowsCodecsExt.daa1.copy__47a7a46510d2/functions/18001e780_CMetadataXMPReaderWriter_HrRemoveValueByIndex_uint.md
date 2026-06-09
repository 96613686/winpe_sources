# CMetadataXMPReaderWriter::HrRemoveValueByIndex(uint)

- ea: `0x18001e780`
- end: `0x18001e7b8`
- name: `?HrRemoveValueByIndex@CMetadataXMPReaderWriter@@UEAAJI@Z`
- size: `56`
- prototype: `__int64 __fastcall(CMetadataXMPReaderWriter *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800171c4`
- `0x18001e780`
- `0x18001e824`
- `0x18001ea50`

## pseudocode

```c
__int64 __fastcall CMetadataXMPReaderWriter::HrRemoveValueByIndex(CMetadataXMPReaderWriter *this, int a2)
{
  int v2; // eax
  unsigned int v3; // ebx

  if ( a2 == *((_DWORD *)this + 43) )
    v2 = CMetadataXMPReaderWriter::RemovePaddingTag(this);
  else
    v2 = CMetadataRDFReaderWriter::HrRemoveValueByIndex(this, a2);
  v3 = v2;
  if ( v2 < 0 && g_doStackCaptures )
    DoStackCapture(v2);
  return v3;
}

```

## disassembly

```asm
0x18001e780  push    rbx
0x18001e782  sub     rsp, 20h
0x18001e786  cmp     edx, [rcx+0ACh]
0x18001e78c  jnz     short loc_18001E795
0x18001e78e  call    ?RemovePaddingTag@CMetadataXMPReaderWriter@@IEAAJXZ; CMetadataXMPReaderWriter::RemovePaddingTag(void)
0x18001e793  jmp     short loc_18001E79A
0x18001e795  call    ?HrRemoveValueByIndex@CMetadataRDFReaderWriter@@MEAAJI@Z; CMetadataRDFReaderWriter::HrRemoveValueByIndex(uint)
0x18001e79a  mov     ebx, eax
0x18001e79c  test    eax, eax
0x18001e79e  jns     short loc_18001E7B0
0x18001e7a0  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001e7a7  jz      short loc_18001E7B0
0x18001e7a9  mov     ecx, eax; int
0x18001e7ab  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001e7b0  mov     eax, ebx
0x18001e7b2  add     rsp, 20h
0x18001e7b6  pop     rbx
0x18001e7b7  retn
```
