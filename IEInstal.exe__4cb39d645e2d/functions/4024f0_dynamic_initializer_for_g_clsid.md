# _dynamic_initializer_for__g_clsid__

- ea: `0x4024f0`
- end: `0x402505`
- name: `_dynamic_initializer_for__g_clsid__`
- size: `21`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## pseudocode

```c
void dynamic_initializer_for__g_clsid__()
{
  g_clsid = GUID_NULL;
}

```

## disassembly

```asm
0x4024f0  mov     edi, edi
0x4024f2  push    esi
0x4024f3  push    edi
0x4024f4  mov     esi, offset _GUID_NULL
0x4024f9  mov     edi, offset ?g_clsid@@3U_GUID@@A; _GUID g_clsid
0x4024fe  movsd
0x4024ff  movsd
0x402500  movsd
0x402501  movsd
0x402502  pop     edi
0x402503  pop     esi
0x402504  retn
```
