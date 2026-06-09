# Microsoft::WRL::Wrappers::CriticalSection::~CriticalSection(void)

- ea: `0x18000c8ec`
- end: `0x18000c8f3`
- name: `??1CriticalSection@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180011824`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c8ec`

## pseudocode

```c
// attributes: thunk
void __stdcall Microsoft::WRL::Wrappers::CriticalSection::~CriticalSection(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18000c8ec  jmp     cs:__imp_DeleteCriticalSection
```
