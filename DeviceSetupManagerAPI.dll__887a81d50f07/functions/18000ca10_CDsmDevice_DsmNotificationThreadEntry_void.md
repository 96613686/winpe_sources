# CDsmDevice::_DsmNotificationThreadEntry(void *)

- ea: `0x18000ca10`
- end: `0x18000ca15`
- name: `?_DsmNotificationThreadEntry@CDsmDevice@@CAKPEAX@Z`
- size: `5`
- prototype: `__int64 __fastcall(CDsmDevice *Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c3b0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall CDsmDevice::_DsmNotificationThreadEntry(CDsmDevice *Parameter)
{
  return CDsmDevice::_DsmNotificationThread(Parameter);
}

```

## disassembly

```asm
0x18000ca10  jmp     ?_DsmNotificationThread@CDsmDevice@@AEAAKXZ; CDsmDevice::_DsmNotificationThread(void)
```
