# WimFSFReleaseReadCbReadParameters

- ea: `0x140010758`
- end: `0x14001076b`
- name: `WimFSFReleaseReadCbReadParameters`
- size: `19`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002d6c8`
- `0x14003d320`

## callees

- `0x14000cfe0`

## pseudocode

```c
__int64 __fastcall WimFSFReleaseReadCbReadParameters(__int64 a1)
{
  return WimFSFReleaseReadCompletionContext((PVOID)(a1 - 24));
}

```

## disassembly

```asm
0x140010758  sub     rsp, 28h
0x14001075c  add     rcx, 0FFFFFFFFFFFFFFE8h; Entry
0x140010760  call    WimFSFReleaseReadCompletionContext
0x140010765  add     rsp, 28h
0x140010769  retn
```
