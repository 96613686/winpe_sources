# _UpdateInstalledAppUriHandlerRegistrations_::_1_::dtor$6

- ea: `0x140011bb1`
- end: `0x140011bbd`
- name: `_UpdateInstalledAppUriHandlerRegistrations_::_1_::dtor$6`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x14000a448`

## pseudocode

```c
void __fastcall UpdateInstalledAppUriHandlerRegistrations_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  HostNameVerifierProvider::VerifyFromWeb::~VerifyFromWeb((HostNameVerifierProvider::VerifyFromWeb *)(a2 + 192));
}

```

## disassembly

```asm
0x140011bb1  lea     rcx, [rdx+0C0h]; this
0x140011bb8  jmp     ??1VerifyFromWeb@HostNameVerifierProvider@@QEAA@XZ; HostNameVerifierProvider::VerifyFromWeb::~VerifyFromWeb(void)
```
