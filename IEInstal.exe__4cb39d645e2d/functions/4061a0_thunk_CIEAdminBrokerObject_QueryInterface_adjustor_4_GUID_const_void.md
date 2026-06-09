# [thunk]:CIEAdminBrokerObject::QueryInterface`adjustor{4}' (_GUID const &,void * *)

- ea: `0x4061a0`
- end: `0x4061aa`
- name: `?QueryInterface@CIEAdminBrokerObject@@W3AGJABU_GUID@@PAPAX@Z`
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
  return CIEAdminBrokerObject::QueryInterface((CIEAdminBrokerObject *)(a1 - 4), a2, a3);
}

```

## disassembly

```asm
0x4061a0  sub     [esp+arg_0], 4
0x4061a5  jmp     ?QueryInterface@CIEAdminBrokerObject@@UAGJABU_GUID@@PAPAX@Z; CIEAdminBrokerObject::QueryInterface(_GUID const &,void * *)
```
