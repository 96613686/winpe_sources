# BufferWriter::CBufferWriter::~CBufferWriter(void)

- ea: `0x180013124`
- end: `0x180013162`
- name: `??1CBufferWriter@BufferWriter@@MEAA@XZ`
- size: `62`
- prototype: `void __fastcall(BufferWriter::CBufferWriter *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180013500`

## callees

- `0x180013068`
- `0x180013124`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180013144`
- `KERNEL32!CloseHandle` at `0x180013144`

## pseudocode

```c
void __fastcall BufferWriter::CBufferWriter::~CBufferWriter(BufferWriter::CBufferWriter *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &BufferWriter::CBufferWriter::`vftable';
  v2 = (void *)*((_QWORD *)this + 16);
  if ( v2 != (void *)-1LL )
  {
    CloseHandle(v2);
    *((_QWORD *)this + 16) = -1;
  }
  BufferWriter::CAsyncIO::~CAsyncIO(this);
}

```

## disassembly

```asm
0x180013124  push    rbx
0x180013126  sub     rsp, 20h
0x18001312a  lea     rax, ??_7CBufferWriter@BufferWriter@@6B@; const BufferWriter::CBufferWriter::`vftable'
0x180013131  mov     rbx, rcx
0x180013134  mov     [rcx], rax
0x180013137  mov     rcx, [rcx+80h]; hObject
0x18001313e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180013142  jz      short loc_180013155
0x180013144  call    cs:__imp_CloseHandle
0x18001314a  mov     qword ptr [rbx+80h], 0FFFFFFFFFFFFFFFFh
0x180013155  mov     rcx, rbx; this
0x180013158  add     rsp, 20h
0x18001315c  pop     rbx
0x18001315d  jmp     ??1CAsyncIO@BufferWriter@@UEAA@XZ; BufferWriter::CAsyncIO::~CAsyncIO(void)
```
