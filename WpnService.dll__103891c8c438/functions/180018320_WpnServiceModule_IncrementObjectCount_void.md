# WpnServiceModule::IncrementObjectCount(void)

- ea: `0x180018320`
- end: `0x18001832a`
- name: `?IncrementObjectCount@WpnServiceModule@@UEAAKXZ`
- size: `10`
- prototype: `unsigned int __fastcall(WpnServiceModule *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `combase!__imp_CoAddRefSharedService` at `0x180018323`

## pseudocode

```c
__int64 __fastcall WpnServiceModule::IncrementObjectCount(WpnServiceModule *this)
{
  return CoAddRefSharedService(*((unsigned int *)this + 4));
}

```

## disassembly

```asm
0x180018320  mov     ecx, [rcx+10h]
0x180018323  jmp     cs:__imp_CoAddRefSharedService
```
