# pplx::details::critical_section_impl::~critical_section_impl(void)

- ea: `0x140023c28`
- end: `0x140023c2f`
- name: `??1critical_section_impl@details@pplx@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1400018d8`
- `0x140032e83`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140023c28`

## pseudocode

```c
// attributes: thunk
void __stdcall pplx::details::critical_section_impl::~critical_section_impl(LPCRITICAL_SECTION lpCriticalSection)
{
  DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x140023c28  jmp     cs:__imp_DeleteCriticalSection
```
