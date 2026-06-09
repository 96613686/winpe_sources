# Pal::Mutex::~Mutex(void)

- ea: `0x18000caec`
- end: `0x18000caf3`
- name: `??1Mutex@Pal@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x18003c2cc`
- `0x18003c3b3`
- `0x18003c56c`
- `0x18003c598`
- `0x18003cd40`
- `0x18003cd6b`
- `0x18003d01d`
- `0x18003d0a7`
- `0x18003f7fa`
- `0x18004133f`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000caec`

## pseudocode

```c
// attributes: thunk
void __stdcall Pal::Mutex::~Mutex(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18000caec  jmp     cs:__imp_DeleteCriticalSection
```
