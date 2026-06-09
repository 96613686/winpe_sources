# std::_Construct_in_place<PCLmWriter::ByteStreamFlateEncoder,std::shared_ptr<PCLmWriter::IByteStream> &>(PCLmWriter::ByteStreamFlateEncoder &,std::shared_ptr<PCLmWriter::IByteStream> &)

- ea: `0x1800109f4`
- end: `0x180010a47`
- name: `??$_Construct_in_place@VByteStreamFlateEncoder@PCLmWriter@@AEAV?$shared_ptr@VIByteStream@PCLmWriter@@@std@@@std@@YAXAEAVByteStreamFlateEncoder@PCLmWriter@@AEAV?$shared_ptr@VIByteStream@PCLmWriter@@@0@@Z`
- size: `83`
- prototype: `__int64 __fastcall(PCLmWriter::MemoryByteStream *this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800110b8`

## callees

- `0x18000e7c8`
- `0x1800101cc`
- `0x1800109f4`
- `0x180011678`

## pseudocode

```c
void __fastcall std::_Construct_in_place<PCLmWriter::ByteStreamFlateEncoder,std::shared_ptr<PCLmWriter::IByteStream> &>(
        PCLmWriter::MemoryByteStream *this,
        _QWORD *a2)
{
  _QWORD *v3; // r11
  __int64 v4; // r11
  std::_Ref_count_base *v5; // rcx
  _QWORD v6[3]; // [rsp+20h] [rbp-18h] BYREF

  std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(v6, a2);
  PCLmWriter::MemoryByteStream::MemoryByteStream(this);
  *(_QWORD *)this = &PCLmWriter::ByteStreamFlateEncoder::`vftable'{for `PCLmWriter::IByteStream'};
  *((_QWORD *)this + 1) = &PCLmWriter::ByteStreamFlateEncoder::`vftable'{for `PCLmWriter::IStreamBufferProvider'};
  std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>((_QWORD *)this + 10, v3);
  v5 = *(std::_Ref_count_base **)(v4 + 8);
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
}

```

## disassembly

```asm
0x1800109f4  push    rbx
0x1800109f6  sub     rsp, 30h
0x1800109fa  mov     rbx, rcx
0x1800109fd  lea     rcx, [rsp+38h+var_18]
0x180010a02  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180010a07  mov     rcx, rbx; this
0x180010a0a  mov     r11, rax
0x180010a0d  call    ??0MemoryByteStream@PCLmWriter@@QEAA@XZ; PCLmWriter::MemoryByteStream::MemoryByteStream(void)
0x180010a12  lea     rax, ??_7ByteStreamFlateEncoder@PCLmWriter@@6BIByteStream@1@@; const PCLmWriter::ByteStreamFlateEncoder::`vftable'{for `PCLmWriter::IByteStream'}
0x180010a19  mov     rdx, r11
0x180010a1c  mov     [rbx], rax
0x180010a1f  lea     rcx, [rbx+50h]
0x180010a23  lea     rax, ??_7ByteStreamFlateEncoder@PCLmWriter@@6BIStreamBufferProvider@1@@; const PCLmWriter::ByteStreamFlateEncoder::`vftable'{for `PCLmWriter::IStreamBufferProvider'}
0x180010a2a  mov     [rbx+8], rax
0x180010a2e  call    ??0?$shared_ptr@$$CBVIObject@PCLmWriter@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<PCLmWriter::IObject const>::shared_ptr<PCLmWriter::IObject const>(std::shared_ptr<PCLmWriter::IObject const> const &)
0x180010a33  mov     rcx, [r11+8]; this
0x180010a37  test    rcx, rcx
0x180010a3a  jz      short loc_180010A41
0x180010a3c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180010a41  add     rsp, 30h
0x180010a45  pop     rbx
0x180010a46  retn
```
