# WpnUserService::GetShutdownRegistryPath(void)

- ea: `0x180009a00`
- end: `0x180009a08`
- name: `?GetShutdownRegistryPath@WpnUserService@@UEAAPEBGXZ`
- size: `8`
- prototype: `const unsigned __int16 *__fastcall(WpnUserService *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x180009a00`: `SOFTWARE\Microsoft\Windows\CurrentVersion\PushNotifications\WpnUserServiceShutdown`

## pseudocode

```c
const unsigned __int16 *__fastcall WpnUserService::GetShutdownRegistryPath(WpnUserService *this)
{
  return L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\PushNotifications\\WpnUserServiceShutdown";
}

```

## disassembly

```asm
0x180009a00  lea     rax, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180009a07  retn
```
