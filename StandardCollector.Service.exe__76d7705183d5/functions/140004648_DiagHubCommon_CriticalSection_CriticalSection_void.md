# DiagHubCommon::CriticalSection::~CriticalSection(void)

- ea: `0x140004648`
- end: `0x14000464f`
- name: `??1CriticalSection@DiagHubCommon@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140014e02`
- `0x140014f7a`
- `0x1400151f2`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x140004648`

## pseudocode

```c
// attributes: thunk
void __stdcall DiagHubCommon::CriticalSection::~CriticalSection(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x140004648  jmp     cs:__imp_DeleteCriticalSection
```
