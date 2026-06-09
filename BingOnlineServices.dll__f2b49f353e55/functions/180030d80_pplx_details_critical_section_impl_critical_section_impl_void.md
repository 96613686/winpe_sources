# pplx::details::critical_section_impl::~critical_section_impl(void)

- ea: `0x180030d80`
- end: `0x180030d87`
- name: `??1critical_section_impl@details@pplx@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180059aa6`
- `0x18005ab71`
- `0x18005ba22`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030d80`

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
0x180030d80  jmp     cs:__imp_DeleteCriticalSection
```
