# _dynamic_atexit_destructor_for__s_cs__

- ea: `0x1800afb80`
- end: `0x1800afba6`
- name: `_dynamic_atexit_destructor_for__s_cs__`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800afb80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800afb94`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800afb94`

## pseudocode

```c
void dynamic_atexit_destructor_for__s_cs__()
{
  if ( byte_1800FB900 )
    DeleteCriticalSection(&stru_1800FB908);
  byte_1800FB900 = 0;
}

```

## disassembly

```asm
0x1800afb80  sub     rsp, 28h
0x1800afb84  cmp     cs:byte_1800FB900, 0
0x1800afb8b  jz      short loc_1800AFB9A
0x1800afb8d  lea     rcx, stru_1800FB908; lpCriticalSection
0x1800afb94  call    cs:__imp_DeleteCriticalSection
0x1800afb9a  mov     cs:byte_1800FB900, 0
0x1800afba1  add     rsp, 28h
0x1800afba5  retn
```
