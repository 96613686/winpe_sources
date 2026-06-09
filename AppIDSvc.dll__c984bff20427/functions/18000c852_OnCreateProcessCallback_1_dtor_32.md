# _OnCreateProcessCallback_::_1_::dtor$32

- ea: `0x18000c852`
- end: `0x18000c85e`
- name: `_OnCreateProcessCallback_::_1_::dtor$32`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800061f0`

## pseudocode

```c
void __fastcall OnCreateProcessCallback_::_1_::dtor_32(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HString::~HString((HSTRING *)(a2 + 128));
}

```

## disassembly

```asm
0x18000c852  lea     rcx, [rdx+80h]; this
0x18000c859  jmp     ??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HString::~HString(void)
```
