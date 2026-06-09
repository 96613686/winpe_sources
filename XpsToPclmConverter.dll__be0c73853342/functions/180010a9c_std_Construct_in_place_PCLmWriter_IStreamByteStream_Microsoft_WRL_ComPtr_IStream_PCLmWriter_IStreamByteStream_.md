# std::_Construct_in_place<PCLmWriter::IStreamByteStream,Microsoft::WRL::ComPtr<IStream> &>(PCLmWriter::IStreamByteStream &,Microsoft::WRL::ComPtr<IStream> &)

- ea: `0x180010a9c`
- end: `0x180010aca`
- name: `??$_Construct_in_place@VIStreamByteStream@PCLmWriter@@AEAV?$ComPtr@UIStream@@@WRL@Microsoft@@@std@@YAXAEAVIStreamByteStream@PCLmWriter@@AEAV?$ComPtr@UIStream@@@WRL@Microsoft@@@Z`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180011178`

## callees

- `0x18000df0c`
- `0x18001a17c`

## pseudocode

```c
PCLmWriter::CByteStream *__fastcall std::_Construct_in_place<PCLmWriter::IStreamByteStream,Microsoft::WRL::ComPtr<IStream> &>(
        PCLmWriter::CByteStream *a1,
        __int64 *a2)
{
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF

  v4 = *a2;
  Microsoft::WRL::ComPtr<IXpsOMPage>::InternalAddRef(&v4);
  return PCLmWriter::IStreamByteStream::IStreamByteStream(a1, &v4);
}

```

## disassembly

```asm
0x180010a9c  push    rbx
0x180010a9e  sub     rsp, 20h
0x180010aa2  mov     rax, [rdx]
0x180010aa5  mov     rbx, rcx
0x180010aa8  lea     rcx, [rsp+28h+arg_0]
0x180010aad  mov     [rsp+28h+arg_0], rax
0x180010ab2  call    ?InternalAddRef@?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXpsOMPage>::InternalAddRef(void)
0x180010ab7  lea     rdx, [rsp+28h+arg_0]
0x180010abc  mov     rcx, rbx
0x180010abf  call    ??0IStreamByteStream@PCLmWriter@@QEAA@V?$ComPtr@UIStream@@@WRL@Microsoft@@@Z; PCLmWriter::IStreamByteStream::IStreamByteStream(Microsoft::WRL::ComPtr<IStream>)
0x180010ac4  add     rsp, 20h
0x180010ac8  pop     rbx
0x180010ac9  retn
```
