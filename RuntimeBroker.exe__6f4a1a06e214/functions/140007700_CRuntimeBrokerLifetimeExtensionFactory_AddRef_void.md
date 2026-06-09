# CRuntimeBrokerLifetimeExtensionFactory::AddRef(void)

- ea: `0x140007700`
- end: `0x14000770d`
- name: `?AddRef@CRuntimeBrokerLifetimeExtensionFactory@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(CRuntimeBrokerLifetimeExtensionFactory *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000aee0`

## pseudocode

```c
__int64 __fastcall CRuntimeBrokerLifetimeExtensionFactory::AddRef(CRuntimeBrokerLifetimeExtensionFactory *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 4);
}

```

## disassembly

```asm
0x140007700  mov     eax, 1
0x140007705  lock xadd [rcx+10h], eax
0x14000770a  inc     eax
0x14000770c  retn
```
