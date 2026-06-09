# WpnServiceModule::DecrementObjectCount(void)

- ea: `0x180018310`
- end: `0x18001831a`
- name: `?DecrementObjectCount@WpnServiceModule@@UEAAKXZ`
- size: `10`
- prototype: `__int64 __fastcall(WpnServiceModule *this)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `combase!__imp_CoReleaseSharedService` at `0x180018313`

## pseudocode

```c
__int64 __fastcall WpnServiceModule::DecrementObjectCount(WpnServiceModule *this)
{
  return CoReleaseSharedService(*((unsigned int *)this + 4));
}

```

## disassembly

```asm
0x180018310  mov     ecx, [rcx+10h]
0x180018313  jmp     cs:__imp_CoReleaseSharedService
```
