# MessagingService::GetControlsAccepted(void)

- ea: `0x180003030`
- end: `0x180003036`
- name: `?GetControlsAccepted@MessagingService@@UEAAKXZ`
- size: `6`
- prototype: `__int64 __fastcall(MessagingService *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
__int64 __fastcall MessagingService::GetControlsAccepted(MessagingService *this)
{
  return 4;
}

```

## disassembly

```asm
0x180003030  mov     eax, 4
0x180003035  retn
```
