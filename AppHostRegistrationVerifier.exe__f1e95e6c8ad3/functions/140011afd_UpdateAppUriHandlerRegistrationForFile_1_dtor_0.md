# _UpdateAppUriHandlerRegistrationForFile_::_1_::dtor$0

- ea: `0x140011afd`
- end: `0x140011b09`
- name: `_UpdateAppUriHandlerRegistrationForFile_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x14000a41c`

## pseudocode

```c
void __fastcall UpdateAppUriHandlerRegistrationForFile_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  HostNameVerifierProvider::VerifyFromFile::~VerifyFromFile((HostNameVerifierProvider::VerifyFromFile *)(a2 + 176));
}

```

## disassembly

```asm
0x140011afd  lea     rcx, [rdx+0B0h]; this
0x140011b04  jmp     ??1VerifyFromFile@HostNameVerifierProvider@@QEAA@XZ; HostNameVerifierProvider::VerifyFromFile::~VerifyFromFile(void)
```
