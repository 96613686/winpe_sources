# CFileStream::~CFileStream(void)

- ea: `0x180002014`
- end: `0x18000201f`
- name: `??1CFileStream@@QEAA@XZ`
- size: `11`
- prototype: `void __fastcall(CFileStream *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180002d4a`
- `0x180002d5c`

## pseudocode

```c
void __fastcall CFileStream::~CFileStream(CFileStream *this)
{
  *(_QWORD *)this = &CFileStream::`vftable';
}

```

## disassembly

```asm
0x180002014  lea     rax, ??_7CFileStream@@6B@; const CFileStream::`vftable'
0x18000201b  mov     [rcx], rax
0x18000201e  retn
```
