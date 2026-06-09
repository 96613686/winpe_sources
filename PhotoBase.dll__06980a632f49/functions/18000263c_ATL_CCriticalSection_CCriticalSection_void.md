# ATL::CCriticalSection::~CCriticalSection(void)

- ea: `0x18000263c`
- end: `0x180002643`
- name: `??1CCriticalSection@ATL@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000766f`
- `0x180007718`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000263c`

## pseudocode

```c
// attributes: thunk
void __stdcall ATL::CCriticalSection::~CCriticalSection(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18000263c  jmp     cs:__imp_DeleteCriticalSection
```
