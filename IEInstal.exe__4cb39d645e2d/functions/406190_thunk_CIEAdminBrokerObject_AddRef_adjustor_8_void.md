# [thunk]:CIEAdminBrokerObject::AddRef`adjustor{8}' (void)

- ea: `0x406190`
- end: `0x40619a`
- name: `?AddRef@CIEAdminBrokerObject@@W7AGKXZ`
- size: `10`
- prototype: `unsigned int __stdcall(int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x405b80`

## pseudocode

```c
unsigned int __stdcall CIEAdminBrokerObject::AddRef(int a1)
{
  return CIEAdminBrokerObject::AddRef((CIEAdminBrokerObject *)(a1 - 8));
}

```

## disassembly

```asm
0x406190  sub     [esp+arg_0], 8
0x406195  jmp     ?AddRef@CIEAdminBrokerObject@@UAGKXZ; CIEAdminBrokerObject::AddRef(void)
```
