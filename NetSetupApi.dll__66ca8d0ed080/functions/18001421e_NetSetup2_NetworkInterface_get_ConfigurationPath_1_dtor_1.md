# _NetSetup2::NetworkInterface::get_ConfigurationPath_::_1_::dtor$1

- ea: `0x18001421e`
- end: `0x18001422a`
- name: `_NetSetup2::NetworkInterface::get_ConfigurationPath_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x18000d7f0`

## pseudocode

```c
void __fastcall NetSetup2::NetworkInterface::get_ConfigurationPath_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  NetSetup2::Property::~Property((NetSetup2::Property *)(a2 + 48));
}

```

## disassembly

```asm
0x18001421e  lea     rcx, [rdx+30h]; this
0x180014225  jmp     ??1Property@NetSetup2@@QEAA@XZ; NetSetup2::Property::~Property(void)
```
