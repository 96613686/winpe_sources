# _MdmCommandParser::HandlePushNotification_::_1_::dtor$0

- ea: `0x18001d772`
- end: `0x18001d77e`
- name: `_MdmCommandParser::HandlePushNotification_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180019c60`

## pseudocode

```c
void __fastcall MdmCommandParser::HandlePushNotification_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  MdmBase64Coder::~MdmBase64Coder((MdmBase64Coder *)(a2 + 128));
}

```

## disassembly

```asm
0x18001d772  lea     rcx, [rdx+80h]; this
0x18001d779  jmp     ??1MdmBase64Coder@@QEAA@XZ; MdmBase64Coder::~MdmBase64Coder(void)
```
