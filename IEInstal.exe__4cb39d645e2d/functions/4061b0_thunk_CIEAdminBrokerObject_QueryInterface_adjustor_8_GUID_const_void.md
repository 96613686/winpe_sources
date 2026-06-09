# [thunk]:CIEAdminBrokerObject::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x4061b0`
- end: `0x4061ba`
- name: `?QueryInterface@CIEAdminBrokerObject@@W7AGJABU_GUID@@PAPAX@Z`
- size: `10`
- prototype: `int __stdcall(int, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x405a60`

## pseudocode

```c
int __stdcall CIEAdminBrokerObject::QueryInterface(int a1, const struct _GUID *a2, void **a3)
{
  return CIEAdminBrokerObject::QueryInterface((CIEAdminBrokerObject *)(a1 - 8), a2, a3);
}

```

## disassembly

```asm
0x4061b0  sub     [esp+arg_0], 8
0x4061b5  jmp     ?QueryInterface@CIEAdminBrokerObject@@UAGJABU_GUID@@PAPAX@Z; CIEAdminBrokerObject::QueryInterface(_GUID const &,void * *)
```
