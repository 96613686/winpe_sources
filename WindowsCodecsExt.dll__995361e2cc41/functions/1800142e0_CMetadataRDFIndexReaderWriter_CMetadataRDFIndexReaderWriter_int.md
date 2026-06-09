# CMetadataRDFIndexReaderWriter::CMetadataRDFIndexReaderWriter(int)

- ea: `0x1800142e0`
- end: `0x18001432d`
- name: `??0CMetadataRDFIndexReaderWriter@@QEAA@H@Z`
- size: `77`
- prototype: `CMetadataRDFIndexReaderWriter *__fastcall(CMetadataRDFIndexReaderWriter *__hidden this, int)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180014258`
- `0x180023200`

## callees

- `0x1800093c0`

## pseudocode

```c
CMetadataRDFIndexReaderWriter *__fastcall CMetadataRDFIndexReaderWriter::CMetadataRDFIndexReaderWriter(
        CMetadataRDFIndexReaderWriter *this,
        int a2)
{
  CMetadataRDFReaderWriter::CMetadataRDFReaderWriter(this, a2);
  *(_QWORD *)this = &CMetadataRDFIndexReaderWriter::`vftable'{for `IWICMetadataWriter'};
  *((_QWORD *)this + 1) = &CMetadataXMPBagReaderWriter::`vftable'{for `IWICPersistStream'};
  *((_QWORD *)this + 2) = &CMetadataRDFReaderWriter::`vftable'{for `IWICStreamProvider'};
  *((_QWORD *)this + 3) = &CMetadataXMPBagReaderWriter::`vftable'{for `CMILCOMBase'};
  *((_QWORD *)this + 5) = &CMetadataRDFIndexReaderWriter::`vftable'{for `CMTALock'};
  return this;
}

```

## disassembly

```asm
0x1800142e0  push    rbx
0x1800142e2  sub     rsp, 20h
0x1800142e6  mov     rbx, rcx
0x1800142e9  call    ??0CMetadataRDFReaderWriter@@QEAA@H@Z
0x1800142ee  lea     rax, ??_7CMetadataRDFIndexReaderWriter@@6BIWICMetadataWriter@@@
0x1800142f5  mov     [rbx], rax
0x1800142f8  lea     rax, ??_7CMetadataXMPBagReaderWriter@@6BIWICPersistStream@@@
0x1800142ff  mov     [rbx+8], rax
0x180014303  lea     rax, ??_7CMetadataRDFReaderWriter@@6BIWICStreamProvider@@@
0x18001430a  mov     [rbx+10h], rax
0x18001430e  lea     rax, ??_7CMetadataXMPBagReaderWriter@@6BCMILCOMBase@@@
0x180014315  mov     [rbx+18h], rax
0x180014319  lea     rax, ??_7CMetadataRDFIndexReaderWriter@@6BCMTALock@@@
0x180014320  mov     [rbx+28h], rax
0x180014324  mov     rax, rbx
0x180014327  add     rsp, 20h
0x18001432b  pop     rbx
0x18001432c  retn
```
