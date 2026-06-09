# CFileStream::~CFileStream(void)

- ea: `0x180020ba4`
- end: `0x180020bcc`
- name: `??1CFileStream@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(CFileStream *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180020b80`

## callees

- `0x180020d68`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x180020bc5`

## pseudocode

```c
void __fastcall CFileStream::~CFileStream(CFileStream *this)
{
  *(_QWORD *)this = &CFileStream::`vftable';
  CFileStream::Close(this);
  MPDeleteCriticalSection((char *)this + 16);
}

```

## disassembly

```asm
0x180020ba4  push    rbx
0x180020ba6  sub     rsp, 20h
0x180020baa  lea     rax, ??_7CFileStream@@6B@; const CFileStream::`vftable'
0x180020bb1  mov     rbx, rcx
0x180020bb4  mov     [rcx], rax
0x180020bb7  call    ?Close@CFileStream@@QEAAXXZ; CFileStream::Close(void)
0x180020bbc  lea     rcx, [rbx+10h]
0x180020bc0  add     rsp, 20h
0x180020bc4  pop     rbx
0x180020bc5  jmp     cs:__imp_MPDeleteCriticalSection
```
