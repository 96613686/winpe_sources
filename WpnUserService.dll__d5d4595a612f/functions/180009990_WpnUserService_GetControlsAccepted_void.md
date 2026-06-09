# WpnUserService::GetControlsAccepted(void)

- ea: `0x180009990`
- end: `0x180009996`
- name: `?GetControlsAccepted@WpnUserService@@UEAAKXZ`
- size: `6`
- prototype: `__int64 __fastcall(WpnUserService *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
__int64 __fastcall WpnUserService::GetControlsAccepted(WpnUserService *this)
{
  return 256;
}

```

## disassembly

```asm
0x180009990  mov     eax, 100h
0x180009995  retn
```
