# [thunk]:CServiceProvider::Unassociate`adjustor{8}' (ushort const *)

- ea: `0x180008880`
- end: `0x180008889`
- name: `?Unassociate@CServiceProvider@@W7EAAJPEBG@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000b5c0`

## pseudocode

```c
__int64 __fastcall CServiceProvider::Unassociate(__int64 a1, const unsigned __int16 *a2)
{
  return CServiceProvider::Unassociate((CServiceProvider *)(a1 - 8), a2);
}

```

## disassembly

```asm
0x180008880  sub     rcx, 8; this
0x180008884  jmp     ?Unassociate@CServiceProvider@@UEAAJPEBG@Z; CServiceProvider::Unassociate(ushort const *)
```
