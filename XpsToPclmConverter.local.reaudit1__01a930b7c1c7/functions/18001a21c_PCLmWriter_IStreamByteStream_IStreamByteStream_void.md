# PCLmWriter::IStreamByteStream::~IStreamByteStream(void)

- ea: `0x18001a21c`
- end: `0x18001a250`
- name: `??1IStreamByteStream@PCLmWriter@@UEAA@XZ`
- size: `52`
- prototype: `void __fastcall(PCLmWriter::IStreamByteStream *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a270`

## callees

- `0x1800119bc`
- `0x18001a21c`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PCLmWriter::IStreamByteStream::~IStreamByteStream(PCLmWriter::IStreamByteStream *this)
{
  __int64 v2; // rcx

  v2 = *((_QWORD *)this + 9);
  if ( v2 )
  {
    *((_QWORD *)this + 9) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  PCLmWriter::CByteStream::~CByteStream(this);
}

```

## disassembly

```asm
0x18001a21c  push    rbx
0x18001a21e  sub     rsp, 20h
0x18001a222  mov     rbx, rcx
0x18001a225  mov     rcx, [rcx+48h]
0x18001a229  test    rcx, rcx
0x18001a22c  jz      short loc_18001A243
0x18001a22e  mov     qword ptr [rbx+48h], 0
0x18001a236  mov     rax, [rcx]
0x18001a239  mov     rax, [rax+10h]
0x18001a23d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a242  nop
0x18001a243  mov     rcx, rbx; this
0x18001a246  add     rsp, 20h
0x18001a24a  pop     rbx
0x18001a24b  jmp     ??1CByteStream@PCLmWriter@@UEAA@XZ; PCLmWriter::CByteStream::~CByteStream(void)
```
