# _InstallPackage_::_1_::dtor$7

- ea: `0x18002087b`
- end: `0x180020887`
- name: `_InstallPackage_::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18001506c`

## pseudocode

```c
void __fastcall InstallPackage_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 144));
}

```

## disassembly

```asm
0x18002087b  lea     rcx, [rdx+90h]; this
0x180020882  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
