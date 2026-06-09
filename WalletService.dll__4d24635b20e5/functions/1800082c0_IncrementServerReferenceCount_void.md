# IncrementServerReferenceCount(void)

- ea: `0x1800082c0`
- end: `0x1800082db`
- name: `?IncrementServerReferenceCount@@YAJXZ`
- size: `27`
- prototype: `__int64(void)`
- caller_count: `23`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004520`
- `0x180004760`
- `0x180004860`
- `0x180008ca0`
- `0x180014294`
- `0x1800173d0`
- `0x180018720`
- `0x180018bd0`
- `0x18001da74`
- `0x18001ed70`
- `0x1800211b4`
- `0x1800251ac`
- `0x180025f00`
- `0x180025fb4`
- `0x18002a140`
- `0x18002a240`
- `0x18002c1d0`
- `0x18002c904`
- `0x18002cfe0`
- `0x180033350`
- `0x1800340d0`
- `0x18003548c`
- `0x1800360c0`

## callees

- `0x1800082c0`

## import_xrefs

- `combase!__imp_CoAddRefSharedService` at `0x1800082ce`
- `combase!__imp_CoAddRefSharedService` at `0x1800082ce`

## pseudocode

```c
__int64 IncrementServerReferenceCount(void)
{
  if ( RWService::g_ulServiceId )
    CoAddRefSharedService();
  return 0;
}

```

## disassembly

```asm
0x1800082c0  sub     rsp, 28h
0x1800082c4  mov     ecx, cs:?g_ulServiceId@RWService@@2KA; ulong RWService::g_ulServiceId
0x1800082ca  test    ecx, ecx
0x1800082cc  jz      short loc_1800082D4
0x1800082ce  call    cs:__imp_CoAddRefSharedService
0x1800082d4  xor     eax, eax
0x1800082d6  add     rsp, 28h
0x1800082da  retn
```
