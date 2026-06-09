# Microsoft::Bluetooth::BluetoothUuid::operator==(Microsoft::Bluetooth::BluetoothUuid const &)

- ea: `0x18002d2a0`
- end: `0x18002d2dd`
- name: `??8BluetoothUuid@Bluetooth@Microsoft@@UEBA_NAEBV012@@Z`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18002d2a0`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x18002d2c6`
- `ntdll!RtlCompareMemory` at `0x18002d2c6`

## pseudocode

```c
bool __fastcall Microsoft::Bluetooth::BluetoothUuid::operator==(__int64 a1, __int64 a2)
{
  char v2; // al

  v2 = *(_BYTE *)(a1 + 32);
  return v2 == *(_BYTE *)(a2 + 32)
      && (v2
       || *(_DWORD *)(a1 + 12) == *(_DWORD *)(a2 + 12)
       && RtlCompareMemory((const void *)(a1 + 16), (const void *)(a2 + 16), 0x10u) == 16);
}

```

## disassembly

```asm
0x18002d2a0  sub     rsp, 28h
0x18002d2a4  mov     al, [rcx+20h]
0x18002d2a7  cmp     al, [rdx+20h]
0x18002d2aa  jnz     short loc_18002D2D6
0x18002d2ac  test    al, al
0x18002d2ae  jnz     short loc_18002D2D2
0x18002d2b0  mov     eax, [rdx+0Ch]
0x18002d2b3  cmp     [rcx+0Ch], eax
0x18002d2b6  jnz     short loc_18002D2D6
0x18002d2b8  add     rdx, 10h; Source2
0x18002d2bc  add     rcx, 10h; Source1
0x18002d2c0  mov     r8d, 10h; Length
0x18002d2c6  call    cs:__imp_RtlCompareMemory
0x18002d2cc  cmp     rax, 10h
0x18002d2d0  jnz     short loc_18002D2D6
0x18002d2d2  mov     al, 1
0x18002d2d4  jmp     short loc_18002D2D8
0x18002d2d6  xor     al, al
0x18002d2d8  add     rsp, 28h
0x18002d2dc  retn
```
