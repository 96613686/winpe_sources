# PushToInstallCallback::CleanupInterfaces(bool)

- ea: `0x180016a40`
- end: `0x180016a58`
- name: `?CleanupInterfaces@PushToInstallCallback@@UEAAX_N@Z`
- size: `24`
- prototype: `void __fastcall(PushToInstallCallback *this)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180016a40`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180016a4d`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180016a4d`

## pseudocode

```c
void __fastcall PushToInstallCallback::CleanupInterfaces(PushToInstallCallback *this)
{
  if ( *((_QWORD *)this + 1) )
    RtlUnsubscribeWnfNotificationWaitForCompletion();
}

```

## disassembly

```asm
0x180016a40  sub     rsp, 28h
0x180016a44  mov     rcx, [rcx+8]
0x180016a48  test    rcx, rcx
0x180016a4b  jz      short loc_180016A53
0x180016a4d  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180016a53  add     rsp, 28h
0x180016a57  retn
```
