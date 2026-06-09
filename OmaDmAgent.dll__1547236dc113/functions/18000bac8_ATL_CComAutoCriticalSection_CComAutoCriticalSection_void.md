# ATL::CComAutoCriticalSection::~CComAutoCriticalSection(void)

- ea: `0x18000bac8`
- end: `0x18000bacf`
- name: `??1CComAutoCriticalSection@ATL@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001ffd6`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000bac8`

## pseudocode

```c
// attributes: thunk
void __stdcall ATL::CComAutoCriticalSection::~CComAutoCriticalSection(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18000bac8  jmp     cs:__imp_DeleteCriticalSection
```
