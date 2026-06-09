# wil::critical_section::~critical_section(void)

- ea: `0x18004c6b0`
- end: `0x18004c6c7`
- name: `??1critical_section@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(wil::critical_section *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180096110`
- `0x180096129`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004c6b4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004c6b4`

## pseudocode

```c
void __fastcall wil::critical_section::~critical_section(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x18004c6b0  sub     rsp, 28h
0x18004c6b4  call    cs:__imp_DeleteCriticalSection
0x18004c6bb  nop     dword ptr [rax+rax+00h]
0x18004c6c0  nop
0x18004c6c1  add     rsp, 28h
0x18004c6c5  retn
```
