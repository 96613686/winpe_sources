# _dynamic_atexit_destructor_for__kDeviceFamily__

- ea: `0x1800420b0`
- end: `0x1800420e2`
- name: `_dynamic_atexit_destructor_for__kDeviceFamily__`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180018724`
- `0x1800420b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800420db`

## pseudocode

```c
void dynamic_atexit_destructor_for__kDeviceFamily__()
{
  if ( byte_18007B81C )
  {
    Core::Optional<_EVENT_DESCRIPTOR>::getValuePtr(&dword_18007B818);
    byte_18007B81C = 0;
  }
  DeleteCriticalSection(&stru_18007B7F0);
}

```

## disassembly

```asm
0x1800420b0  sub     rsp, 28h
0x1800420b4  cmp     cs:byte_18007B81C, 0
0x1800420bb  jz      short loc_1800420D0
0x1800420bd  lea     rcx, dword_18007B818
0x1800420c4  call    ?getValuePtr@?$Optional@U_EVENT_DESCRIPTOR@@@Core@@AEAAPEAU_EVENT_DESCRIPTOR@@XZ; Core::Optional<_EVENT_DESCRIPTOR>::getValuePtr(void)
0x1800420c9  mov     cs:byte_18007B81C, 0
0x1800420d0  lea     rcx, stru_18007B7F0
0x1800420d7  add     rsp, 28h
0x1800420db  jmp     cs:__imp_DeleteCriticalSection
```
