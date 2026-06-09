# CMetadataRDFReaderWriter::`scalar deleting destructor'(uint)

- ea: `0x180023430`
- end: `0x180023464`
- name: `??_GCMetadataRDFReaderWriter@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CMetadataRDFReaderWriter *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180023410`
- `0x180023420`

## callees

- `0x180009868`
- `0x180021a54`
- `0x180023430`

## pseudocode

```c
CMetadataRDFReaderWriter *__fastcall CMetadataRDFReaderWriter::`scalar deleting destructor'(
        CMetadataRDFReaderWriter *this,
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
0x180023430  mov     [rsp+arg_0], rbx
0x180023435  push    rdi
0x180023436  sub     rsp, 20h
0x18002343a  mov     ebx, edx
0x18002343c  mov     rdi, rcx
0x18002343f  call    ??1CMetadataRDFReaderWriter@@UEAA@XZ; CMetadataRDFReaderWriter::~CMetadataRDFReaderWriter(void)
0x180023444  test    bl, 1
0x180023447  jz      short loc_180023456
0x180023449  mov     edx, 0F8h
0x18002344e  mov     rcx, rdi; Block
0x180023451  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180023456  mov     rbx, [rsp+28h+arg_0]
0x18002345b  mov     rax, rdi
0x18002345e  add     rsp, 20h
0x180023462  pop     rdi
0x180023463  retn
```
