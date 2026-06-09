# avpriv_packet_list_put

- ea: `0x18001bae0`
- end: `0x18001bae6`
- name: `avpriv_packet_list_put`
- size: `6`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180006060`
- `0x180006390`
- `0x180009e98`
- `0x18000a378`
- `0x18000c7b0`

## import_xrefs

- `avcodec_ms!avpriv_packet_list_put` at `0x18001bae0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall avpriv_packet_list_put(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  return __imp_avpriv_packet_list_put(a1, a2, a3, a4);
}

```

## disassembly

```asm
0x18001bae0  jmp     cs:__imp_avpriv_packet_list_put
```
