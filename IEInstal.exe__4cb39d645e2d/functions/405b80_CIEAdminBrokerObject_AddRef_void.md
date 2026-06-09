# CIEAdminBrokerObject::AddRef(void)

- ea: `0x405b80`
- end: `0x405b94`
- name: `?AddRef@CIEAdminBrokerObject@@UAGKXZ`
- size: `20`
- prototype: `unsigned int __stdcall(CIEAdminBrokerObject *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x406190`
- `0x4061e0`

## pseudocode

```c
unsigned int __stdcall CIEAdminBrokerObject::AddRef(CIEAdminBrokerObject *this)
{
  _InterlockedIncrement((volatile signed __int32 *)this + 3);
  return *((_DWORD *)this + 3);
}

```

## disassembly

```asm
0x405b80  mov     edi, edi
0x405b82  push    ebp
0x405b83  mov     ebp, esp
0x405b85  mov     eax, [ebp+this]
0x405b88  add     eax, 0Ch
0x405b8b  lock inc dword ptr [eax]
0x405b8e  mov     eax, [eax]
0x405b90  pop     ebp
0x405b91  retn    4
```
