# ServiceBase::GetServiceType(void)

- ea: `0x180003040`
- end: `0x180003046`
- name: `?GetServiceType@ServiceBase@@UEAAKXZ`
- size: `6`
- prototype: `__int64 __fastcall(ServiceBase *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
__int64 __fastcall ServiceBase::GetServiceType(ServiceBase *this)
{
  return 32;
}

```

## disassembly

```asm
0x180003040  mov     eax, 20h ; ' '
0x180003045  retn
```
