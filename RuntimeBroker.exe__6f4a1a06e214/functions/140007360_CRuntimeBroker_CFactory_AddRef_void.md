# CRuntimeBroker::CFactory::AddRef(void)

- ea: `0x140007360`
- end: `0x140007366`
- name: `?AddRef@CFactory@CRuntimeBroker@@UEAAKXZ`
- size: `6`
- prototype: `unsigned int __fastcall(CRuntimeBroker::CFactory *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CRuntimeBroker::CFactory::AddRef(CRuntimeBroker::CFactory *this)
{
  return 2;
}

```

## disassembly

```asm
0x140007360  mov     eax, 2
0x140007365  retn
```
