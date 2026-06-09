# CReadWriteSpinLock::CReadWriteSpinLock(char const *)

- ea: `0x140005288`
- end: `0x140005293`
- name: `??0CReadWriteSpinLock@@QEAA@PEBD@Z`
- size: `11`
- prototype: `CReadWriteSpinLock *__fastcall(CReadWriteSpinLock *__hidden this, const char *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001040`
- `0x140002244`
- `0x14000355c`

## pseudocode

```c
CReadWriteSpinLock *__fastcall CReadWriteSpinLock::CReadWriteSpinLock(CReadWriteSpinLock *this, const char *a2)
{
  CReadWriteSpinLock *result; // rax

  *(_DWORD *)this = 0;
  result = this;
  *((_DWORD *)this + 1) = 0;
  return result;
}

```

## disassembly

```asm
0x140005288  and     dword ptr [rcx], 0
0x14000528b  mov     rax, rcx
0x14000528e  and     dword ptr [rcx+4], 0
0x140005292  retn
```
