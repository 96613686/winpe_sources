# Lock::~Lock(void)

- ea: `0x18000a228`
- end: `0x18000a23d`
- name: `??1Lock@@QEAA@XZ`
- size: `21`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a27c`
- `0x18002d310`
- `0x18002d7b8`
- `0x180031c9c`

## callees

- `0x18000a228`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a232`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a232`

## pseudocode

```c
void __fastcall Lock::~Lock(struct _RTL_CRITICAL_SECTION *this)
{
  if ( LODWORD(this[1].DebugInfo) )
    DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x18000a228  sub     rsp, 28h
0x18000a22c  cmp     dword ptr [rcx+28h], 0
0x18000a230  jz      short loc_18000A238
0x18000a232  call    cs:__imp_DeleteCriticalSection
0x18000a238  add     rsp, 28h
0x18000a23c  retn
```
