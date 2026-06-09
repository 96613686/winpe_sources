# Microsoft::WRL::Wrappers::CriticalSection::~CriticalSection(void)

- ea: `0x180023ecc`
- end: `0x180023ed3`
- name: `??1CriticalSection@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `6`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800349a4`
- `0x180034c70`
- `0x1800359e5`
- `0x180035b32`
- `0x180035f8c`
- `0x180035fc6`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180023ecc`

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
0x180023ecc  jmp     cs:__imp_DeleteCriticalSection
```
