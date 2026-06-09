# PCLmWriter::IStreamByteStream::IStreamByteStream(Microsoft::WRL::ComPtr<IStream>)

- ea: `0x18001a17c`
- end: `0x18001a213`
- name: `??0IStreamByteStream@PCLmWriter@@QEAA@V?$ComPtr@UIStream@@@WRL@Microsoft@@@Z`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180010a9c`

## callees

- `0x18000df0c`
- `0x1800183d8`
- `0x18001a17c`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
PCLmWriter::CByteStream *__fastcall PCLmWriter::IStreamByteStream::IStreamByteStream(
        PCLmWriter::CByteStream *a1,
        __int64 *a2)
{
  __int64 v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF

  PCLmWriter::CByteStream::CByteStream(a1);
  *(_QWORD *)a1 = &PCLmWriter::IStreamByteStream::`vftable'{for `PCLmWriter::IByteStream'};
  *((_QWORD *)a1 + 1) = &PCLmWriter::IStreamByteStream::`vftable'{for `PCLmWriter::IStreamBufferProvider'};
  *((_QWORD *)a1 + 9) = 0;
  v4 = *a2;
  if ( *a2 )
  {
    v8 = *a2;
    Microsoft::WRL::ComPtr<IXpsOMPage>::InternalAddRef(&v8);
    v5 = *((_QWORD *)a1 + 9);
    *((_QWORD *)a1 + 9) = v4;
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  v6 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return a1;
}

```

## disassembly

```asm
0x18001a17c  mov     [rsp+arg_8], rbx
0x18001a181  mov     [rsp+arg_10], rsi
0x18001a186  push    rdi
0x18001a187  sub     rsp, 20h
0x18001a18b  mov     rsi, rdx
0x18001a18e  mov     rbx, rcx
0x18001a191  call    ??0CByteStream@PCLmWriter@@QEAA@XZ; PCLmWriter::CByteStream::CByteStream(void)
0x18001a196  lea     r9, ??_7IStreamByteStream@PCLmWriter@@6BIByteStream@1@@; const PCLmWriter::IStreamByteStream::`vftable'{for `PCLmWriter::IByteStream'}
0x18001a19d  mov     [rbx], r9
0x18001a1a0  lea     rax, ??_7IStreamByteStream@PCLmWriter@@6BIStreamBufferProvider@1@@; const PCLmWriter::IStreamByteStream::`vftable'{for `PCLmWriter::IStreamBufferProvider'}
0x18001a1a7  mov     [rbx+8], rax
0x18001a1ab  mov     qword ptr [rbx+48h], 0
0x18001a1b3  mov     rdi, [rsi]
0x18001a1b6  test    rdi, rdi
0x18001a1b9  jz      short loc_18001A1E4
0x18001a1bb  mov     [rsp+28h+arg_0], rdi
0x18001a1c0  lea     rcx, [rsp+28h+arg_0]
0x18001a1c5  call    ?InternalAddRef@?$ComPtr@UIXpsOMPage@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IXpsOMPage>::InternalAddRef(void)
0x18001a1ca  mov     rcx, [rbx+48h]
0x18001a1ce  mov     [rbx+48h], rdi
0x18001a1d2  test    rcx, rcx
0x18001a1d5  jz      short loc_18001A1E4
0x18001a1d7  mov     rax, [rcx]
0x18001a1da  mov     rax, [rax+10h]
0x18001a1de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1e3  nop
0x18001a1e4  mov     rcx, [rsi]
0x18001a1e7  test    rcx, rcx
0x18001a1ea  jz      short loc_18001A200
0x18001a1ec  mov     qword ptr [rsi], 0
0x18001a1f3  mov     rax, [rcx]
0x18001a1f6  mov     rax, [rax+10h]
0x18001a1fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a1ff  nop
0x18001a200  mov     rax, rbx
0x18001a203  mov     rbx, [rsp+28h+arg_8]
0x18001a208  mov     rsi, [rsp+28h+arg_10]
0x18001a20d  add     rsp, 20h
0x18001a211  pop     rdi
0x18001a212  retn
```
