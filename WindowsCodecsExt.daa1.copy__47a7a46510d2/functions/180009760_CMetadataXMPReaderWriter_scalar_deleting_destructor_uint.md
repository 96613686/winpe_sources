# CMetadataXMPReaderWriter::`scalar deleting destructor'(uint)

- ea: `0x180009760`
- end: `0x180009794`
- name: `??_GCMetadataXMPReaderWriter@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(CMetadataXMPReaderWriter *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800229a0`
- `0x1800229b0`

## callees

- `0x180009760`
- `0x18000979c`
- `0x180021a54`

## pseudocode

```c
CMetadataXMPReaderWriter *__fastcall CMetadataXMPReaderWriter::`scalar deleting destructor'(
        CMetadataXMPReaderWriter *this,
        char a2)
{
  CMetadataXMPReaderWriter::~CMetadataXMPReaderWriter(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180009760  mov     [rsp+arg_0], rbx
0x180009765  push    rdi
0x180009766  sub     rsp, 20h
0x18000976a  mov     ebx, edx
0x18000976c  mov     rdi, rcx
0x18000976f  call    ??1CMetadataXMPReaderWriter@@UEAA@XZ; CMetadataXMPReaderWriter::~CMetadataXMPReaderWriter(void)
0x180009774  test    bl, 1
0x180009777  jz      short loc_180009786
0x180009779  mov     edx, 128h
0x18000977e  mov     rcx, rdi; Block
0x180009781  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009786  mov     rbx, [rsp+28h+arg_0]
0x18000978b  mov     rax, rdi
0x18000978e  add     rsp, 20h
0x180009792  pop     rdi
0x180009793  retn
```
