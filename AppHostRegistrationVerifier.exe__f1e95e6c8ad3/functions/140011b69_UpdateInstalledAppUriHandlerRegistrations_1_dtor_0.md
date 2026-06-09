# _UpdateInstalledAppUriHandlerRegistrations_::_1_::dtor$0

- ea: `0x140011b69`
- end: `0x140011b75`
- name: `_UpdateInstalledAppUriHandlerRegistrations_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x14000a3f0`

## pseudocode

```c
void __fastcall UpdateInstalledAppUriHandlerRegistrations_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  HostNameVerifierProvider::VerifyAllInstalled::~VerifyAllInstalled((HostNameVerifierProvider::VerifyAllInstalled *)(a2 + 528));
}

```

## disassembly

```asm
0x140011b69  lea     rcx, [rdx+210h]; this
0x140011b70  jmp     ??1VerifyAllInstalled@HostNameVerifierProvider@@QEAA@XZ; HostNameVerifierProvider::VerifyAllInstalled::~VerifyAllInstalled(void)
```
