# _GetJsonFromUrl_::_1_::dtor$7

- ea: `0x140011927`
- end: `0x140011933`
- name: `_GetJsonFromUrl_::_1_::dtor$7`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000a374`

## pseudocode

```c
void __fastcall GetJsonFromUrl_::_1_::dtor_7(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 32));
}

```

## disassembly

```asm
0x140011927  lea     rcx, [rdx+20h]; this
0x14001192e  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
