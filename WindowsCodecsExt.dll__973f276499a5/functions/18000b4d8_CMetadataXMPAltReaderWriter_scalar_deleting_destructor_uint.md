# CMetadataXMPAltReaderWriter::`scalar deleting destructor'(uint)

- ea: `0x18000b4d8`
- end: `0x18000b50c`
- name: `??_GCMetadataXMPAltReaderWriter@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CMetadataXMPAltReaderWriter *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180022db0`
- `0x180022dc0`

## callees

- `0x180009868`
- `0x18000b4d8`
- `0x180021a54`

## pseudocode

```c
CMetadataXMPAltReaderWriter *__fastcall CMetadataXMPAltReaderWriter::`scalar deleting destructor'(
        CMetadataXMPAltReaderWriter *this,
        char a2)
{
  CMetadataRDFReaderWriter::~CMetadataRDFReaderWriter(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000b4d8  mov     [rsp+arg_0], rbx
0x18000b4dd  push    rdi
0x18000b4de  sub     rsp, 20h
0x18000b4e2  mov     ebx, edx
0x18000b4e4  mov     rdi, rcx
0x18000b4e7  call    ??1CMetadataRDFReaderWriter@@UEAA@XZ; CMetadataRDFReaderWriter::~CMetadataRDFReaderWriter(void)
0x18000b4ec  test    bl, 1
0x18000b4ef  jz      short loc_18000B4FE
0x18000b4f1  mov     edx, 100h
0x18000b4f6  mov     rcx, rdi; Block
0x18000b4f9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000b4fe  mov     rbx, [rsp+28h+arg_0]
0x18000b503  mov     rax, rdi
0x18000b506  add     rsp, 20h
0x18000b50a  pop     rdi
0x18000b50b  retn
```
