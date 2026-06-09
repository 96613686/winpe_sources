# CreateObjectServerTaskBase::Resume(void)

- ea: `0x140007ac0`
- end: `0x140007ac6`
- name: `?Resume@CreateObjectServerTaskBase@@UEAAJXZ`
- size: `6`
- prototype: `__int64 __fastcall(CreateObjectServerTaskBase *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
__int64 __fastcall CreateObjectServerTaskBase::Resume(CreateObjectServerTaskBase *this)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x140007ac0  mov     eax, 80004001h
0x140007ac5  retn
```
