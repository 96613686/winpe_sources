# _ipx::mtf::CMtfSuggestionClient::RepairServerConnection_::_1_::dtor$4

- ea: `0x18002d569`
- end: `0x18002d575`
- name: `_ipx::mtf::CMtfSuggestionClient::RepairServerConnection_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800105e0`

## pseudocode

```c
void __fastcall ipx::mtf::CMtfSuggestionClient::RepairServerConnection_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  ipx::mtf::RefPtrMtfPropertyBag::~RefPtrMtfPropertyBag((ipx::mtf::RefPtrMtfPropertyBag *)(a2 + 128));
}

```

## disassembly

```asm
0x18002d569  lea     rcx, [rdx+80h]; this
0x18002d570  jmp     ??1RefPtrMtfPropertyBag@mtf@ipx@@QEAA@XZ; ipx::mtf::RefPtrMtfPropertyBag::~RefPtrMtfPropertyBag(void)
```
