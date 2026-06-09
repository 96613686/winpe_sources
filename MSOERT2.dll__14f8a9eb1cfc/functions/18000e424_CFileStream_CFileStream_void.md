# CFileStream::CFileStream(void *)

- ea: `0x18000e424`
- end: `0x18000e43d`
- name: `??0CFileStream@@AEAA@PEAX@Z`
- size: `25`
- prototype: `CFileStream *__fastcall(CFileStream *__hidden this, void *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180001820`
- `0x180001980`
- `0x180001b60`

## pseudocode

```c
CFileStream *__fastcall CFileStream::CFileStream(CFileStream *this, void *a2)
{
  CFileStream *result; // rax

  *((_DWORD *)this + 2) = 1;
  *(_QWORD *)this = &CFileStream::`vftable';
  result = this;
  *((_QWORD *)this + 2) = a2;
  return result;
}

```

## disassembly

```asm
0x18000e424  lea     rax, ??_7CFileStream@@6B@; const CFileStream::`vftable'
0x18000e42b  mov     dword ptr [rcx+8], 1
0x18000e432  mov     [rcx], rax
0x18000e435  mov     rax, rcx
0x18000e438  mov     [rcx+10h], rdx
0x18000e43c  retn
```
