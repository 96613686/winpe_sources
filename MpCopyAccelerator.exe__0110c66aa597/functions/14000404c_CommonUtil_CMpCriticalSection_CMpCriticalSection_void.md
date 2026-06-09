# CommonUtil::CMpCriticalSection::~CMpCriticalSection(void)

- ea: `0x14000404c`
- end: `0x140004053`
- name: `??1CMpCriticalSection@CommonUtil@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140002bdc`
- `0x14001cd20`
- `0x14001ce0c`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x14000404c`

## pseudocode

```c
// attributes: thunk
void __stdcall CommonUtil::CMpCriticalSection::~CMpCriticalSection(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x14000404c  jmp     cs:__imp_DeleteCriticalSection
```
