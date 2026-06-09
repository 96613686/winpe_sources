# wil::critical_section::~critical_section(void)

- ea: `0x180019f04`
- end: `0x180019f14`
- name: `??1critical_section@wil@@QEAA@XZ`
- size: `16`
- prototype: `void __fastcall(wil::critical_section *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18003114b`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019f08`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180019f08`

## pseudocode

```c
void __fastcall wil::critical_section::~critical_section(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180019f04  sub     rsp, 28h
0x180019f08  call    cs:__imp_DeleteCriticalSection
0x180019f0e  nop
0x180019f0f  add     rsp, 28h
0x180019f13  retn
```
