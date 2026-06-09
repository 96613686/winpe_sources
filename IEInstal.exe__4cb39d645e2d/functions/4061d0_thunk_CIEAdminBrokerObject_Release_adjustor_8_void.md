# [thunk]:CIEAdminBrokerObject::Release`adjustor{8}' (void)

- ea: `0x4061d0`
- end: `0x4061da`
- name: `?Release@CIEAdminBrokerObject@@W7AGKXZ`
- size: `10`
- prototype: `int __stdcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x405ba0`

## pseudocode

```c
int __stdcall CIEAdminBrokerObject::Release(int a1)
{
  return CIEAdminBrokerObject::Release((CIEAdminBrokerObject *)(a1 - 8));
}

```

## disassembly

```asm
0x4061d0  sub     [esp+arg_0], 8
0x4061d5  jmp     ?Release@CIEAdminBrokerObject@@UAGKXZ; CIEAdminBrokerObject::Release(void)
```
