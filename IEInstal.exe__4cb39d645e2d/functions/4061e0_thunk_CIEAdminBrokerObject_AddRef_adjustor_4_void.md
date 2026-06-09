# [thunk]:CIEAdminBrokerObject::AddRef`adjustor{4}' (void)

- ea: `0x4061e0`
- end: `0x4061ea`
- name: `?AddRef@CIEAdminBrokerObject@@W3AGKXZ`
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
  return CIEAdminBrokerObject::AddRef((CIEAdminBrokerObject *)(a1 - 4));
}

```

## disassembly

```asm
0x4061e0  sub     [esp+arg_0], 4
0x4061e5  jmp     ?AddRef@CIEAdminBrokerObject@@UAGKXZ; CIEAdminBrokerObject::AddRef(void)
```
