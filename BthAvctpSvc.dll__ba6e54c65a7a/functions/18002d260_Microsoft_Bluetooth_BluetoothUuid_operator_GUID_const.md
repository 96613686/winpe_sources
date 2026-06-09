# Microsoft::Bluetooth::BluetoothUuid::operator==(_GUID const &)

- ea: `0x18002d260`
- end: `0x18002d28b`
- name: `??8BluetoothUuid@Bluetooth@Microsoft@@UEBA_NAEBU_GUID@@@Z`
- size: `43`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002d260`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x18002d274`
- `ntdll!RtlCompareMemory` at `0x18002d274`

## pseudocode

```c
bool __fastcall Microsoft::Bluetooth::BluetoothUuid::operator==(__int64 a1, const void *a2)
{
  return !*(_BYTE *)(a1 + 32) && RtlCompareMemory((const void *)(a1 + 16), a2, 0x10u) == 16;
}

```

## disassembly

```asm
0x18002d260  sub     rsp, 28h
0x18002d264  cmp     byte ptr [rcx+20h], 0
0x18002d268  jnz     short loc_18002D284
0x18002d26a  add     rcx, 10h; Source1
0x18002d26e  mov     r8d, 10h; Length
0x18002d274  call    cs:__imp_RtlCompareMemory
0x18002d27a  cmp     rax, 10h
0x18002d27e  jnz     short loc_18002D284
0x18002d280  mov     al, 1
0x18002d282  jmp     short loc_18002D286
0x18002d284  xor     al, al
0x18002d286  add     rsp, 28h
0x18002d28a  retn
```
