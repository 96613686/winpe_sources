# [thunk]:CIEAdminBrokerObject::Release`adjustor{4}' (void)

- ea: `0x4061c0`
- end: `0x4061ca`
- name: `?Release@CIEAdminBrokerObject@@W3AGKXZ`
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
  return CIEAdminBrokerObject::Release((CIEAdminBrokerObject *)(a1 - 4));
}

```

## disassembly

```asm
0x4061c0  sub     [esp+arg_0], 4
0x4061c5  jmp     ?Release@CIEAdminBrokerObject@@UAGKXZ; CIEAdminBrokerObject::Release(void)
```
