# CRuntimeBroker::CFactory::Release(void)

- ea: `0x140007650`
- end: `0x140007656`
- name: `?Release@CFactory@CRuntimeBroker@@UEAAKXZ`
- size: `6`
- prototype: `unsigned int __fastcall(CRuntimeBroker::CFactory *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400089e0`

## pseudocode

```c
__int64 __fastcall CRuntimeBroker::CFactory::Release(CRuntimeBroker::CFactory *this)
{
  return 1;
}

```

## disassembly

```asm
0x140007650  mov     eax, 1
0x140007655  retn
```
