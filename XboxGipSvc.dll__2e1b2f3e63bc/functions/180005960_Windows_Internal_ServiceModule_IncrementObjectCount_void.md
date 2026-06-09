# Windows::Internal::ServiceModule::IncrementObjectCount(void)

- ea: `0x180005960`
- end: `0x180005967`
- name: `?IncrementObjectCount@ServiceModule@Internal@Windows@@UEAAKXZ`
- size: `7`
- prototype: `ULONG __stdcall()`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005970`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoAddRefServerProcess` at `0x180005960`

## pseudocode

```c
// attributes: thunk
ULONG __stdcall Windows::Internal::ServiceModule::IncrementObjectCount()
{
  return CoAddRefServerProcess();
}

```

## disassembly

```asm
0x180005960  jmp     cs:__imp_CoAddRefServerProcess
```
