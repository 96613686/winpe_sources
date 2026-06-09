# CReadWriteSpinLock::ReleaseReaderLock(void)

- ea: `0x140005370`
- end: `0x140005374`
- name: `?ReleaseReaderLock@CReadWriteSpinLock@@QEAAXXZ`
- size: `4`
- prototype: `void __fastcall(CReadWriteSpinLock *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140004ab8`
- `0x140004b0c`

## pseudocode

```c
void __fastcall CReadWriteSpinLock::ReleaseReaderLock(CReadWriteSpinLock *this)
{
  _InterlockedDecrement((volatile signed __int32 *)this);
}

```

## disassembly

```asm
0x140005370  lock dec dword ptr [rcx]
0x140005373  retn
```
