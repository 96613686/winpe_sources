# _dynamic_atexit_destructor_for__s_xGPRpcIdleStopCritSec__

- ea: `0x18002b200`
- end: `0x18002b21b`
- name: `_dynamic_atexit_destructor_for__s_xGPRpcIdleStopCritSec__`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18002b200`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002b210`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002b210`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_xGPRpcIdleStopCritSec__()
{
  if ( lpCriticalSection )
    DeleteCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18002b200  sub     rsp, 28h
0x18002b204  mov     rcx, cs:lpCriticalSection; lpCriticalSection
0x18002b20b  test    rcx, rcx
0x18002b20e  jz      short loc_18002B216
0x18002b210  call    cs:__imp_DeleteCriticalSection
0x18002b216  add     rsp, 28h
0x18002b21a  retn
```
