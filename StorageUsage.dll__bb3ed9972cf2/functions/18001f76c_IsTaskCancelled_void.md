# IsTaskCancelled(void *)

- ea: `0x18001f76c`
- end: `0x18001f782`
- name: `?IsTaskCancelled@@YA_NPEAX@Z`
- size: `22`
- prototype: `bool __fastcall(void *)`
- caller_count: `5`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x180012340`
- `0x180018a10`
- `0x18001cb04`
- `0x18001d020`
- `0x18001d1b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f772`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001f772`

## pseudocode

```c
bool __fastcall IsTaskCancelled(void *a1)
{
  return WaitForSingleObject(a1, 0) == 0;
}

```

## disassembly

```asm
0x18001f76c  sub     rsp, 28h
0x18001f770  xor     edx, edx; dwMilliseconds
0x18001f772  call    cs:__imp_WaitForSingleObject
0x18001f778  test    eax, eax
0x18001f77a  setz    al
0x18001f77d  add     rsp, 28h
0x18001f781  retn
```
