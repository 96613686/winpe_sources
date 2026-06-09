# CRuntimeBroker::AddRef(void)

- ea: `0x140006d10`
- end: `0x140006d1d`
- name: `?AddRef@CRuntimeBroker@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(CRuntimeBroker *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CRuntimeBroker::AddRef(CRuntimeBroker *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 2);
}

```

## disassembly

```asm
0x140006d10  mov     eax, 1
0x140006d15  lock xadd [rcx+8], eax
0x140006d1a  inc     eax
0x140006d1c  retn
```
