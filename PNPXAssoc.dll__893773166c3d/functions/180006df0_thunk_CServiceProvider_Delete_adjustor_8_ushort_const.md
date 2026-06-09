# [thunk]:CServiceProvider::Delete`adjustor{8}' (ushort const *)

- ea: `0x180006df0`
- end: `0x180006df9`
- name: `?Delete@CServiceProvider@@W7EAAJPEBG@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task`

## callees

- `0x18000a480`

## pseudocode

```c
__int64 __fastcall CServiceProvider::Delete(__int64 a1, const unsigned __int16 *a2)
{
  return CServiceProvider::Delete((CServiceProvider *)(a1 - 8), a2);
}

```

## disassembly

```asm
0x180006df0  sub     rcx, 8; this
0x180006df4  jmp     ?Delete@CServiceProvider@@UEAAJPEBG@Z; CServiceProvider::Delete(ushort const *)
```
