# CCritSec::~CCritSec(void)

- ea: `0x180010ea0`
- end: `0x180010eb0`
- name: `??1CCritSec@@QEAA@XZ`
- size: `16`
- prototype: `void __fastcall(CCritSec *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18001e13b`
- `0x18001e74b`
- `0x18001e779`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010ea4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010ea4`

## pseudocode

```c
void __fastcall CCritSec::~CCritSec(struct _RTL_CRITICAL_SECTION *this)
{
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180010ea0  sub     rsp, 28h
0x180010ea4  call    cs:__imp_DeleteCriticalSection
0x180010eaa  nop
0x180010eab  add     rsp, 28h
0x180010eaf  retn
```
