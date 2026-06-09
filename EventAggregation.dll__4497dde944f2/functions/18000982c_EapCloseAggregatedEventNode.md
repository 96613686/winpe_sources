# EapCloseAggregatedEventNode

- ea: `0x18000982c`
- end: `0x180009840`
- name: `EapCloseAggregatedEventNode`
- size: `20`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009070`
- `0x180009370`
- `0x1800095e0`
- `0x180009d38`
- `0x18000a414`
- `0x18000ace0`
- `0x18000ad20`
- `0x18000aec4`

## callees

- `0x18000982c`

## import_xrefs

- `ntdll!ZwClose` at `0x180009835`
- `ntdll!ZwClose` at `0x180009835`

## pseudocode

```c
NTSTATUS __fastcall EapCloseAggregatedEventNode(void *a1)
{
  NTSTATUS result; // eax

  if ( a1 )
    return ZwClose(a1);
  return result;
}

```

## disassembly

```asm
0x18000982c  sub     rsp, 28h
0x180009830  test    rcx, rcx
0x180009833  jz      short loc_18000983B
0x180009835  call    cs:__imp_ZwClose
0x18000983b  add     rsp, 28h
0x18000983f  retn
```
