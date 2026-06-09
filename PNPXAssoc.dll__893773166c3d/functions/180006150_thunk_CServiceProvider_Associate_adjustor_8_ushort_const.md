# [thunk]:CServiceProvider::Associate`adjustor{8}' (ushort const *)

- ea: `0x180006150`
- end: `0x180006159`
- name: `?Associate@CServiceProvider@@W7EAAJPEBG@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180009c10`

## pseudocode

```c
__int64 __fastcall CServiceProvider::Associate(__int64 a1, const unsigned __int16 *a2)
{
  return CServiceProvider::Associate((CServiceProvider *)(a1 - 8), a2);
}

```

## disassembly

```asm
0x180006150  sub     rcx, 8; this
0x180006154  jmp     ?Associate@CServiceProvider@@UEAAJPEBG@Z; CServiceProvider::Associate(ushort const *)
```
