# CriticalSection::~CriticalSection(void)

- ea: `0x18000adf4`
- end: `0x18000ae09`
- name: `??1CriticalSection@@QEAA@XZ`
- size: `21`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ae10`
- `0x18000eab0`
- `0x18003b574`
- `0x18003e4a0`
- `0x18003e4c0`

## callees

- `0x18000adf4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000adfe`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000adfe`

## pseudocode

```c
void __fastcall CriticalSection::~CriticalSection(struct _RTL_CRITICAL_SECTION *this)
{
  if ( !LOBYTE(this[1].DebugInfo) )
    DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x18000adf4  sub     rsp, 28h
0x18000adf8  cmp     byte ptr [rcx+28h], 0
0x18000adfc  jnz     short loc_18000AE04
0x18000adfe  call    cs:__imp_DeleteCriticalSection
0x18000ae04  add     rsp, 28h
0x18000ae08  retn
```
