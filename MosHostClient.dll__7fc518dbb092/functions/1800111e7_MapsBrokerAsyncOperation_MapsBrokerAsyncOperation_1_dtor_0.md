# _MapsBrokerAsyncOperation::MapsBrokerAsyncOperation_::_1_::dtor$0

- ea: `0x1800111e7`
- end: `0x1800111f3`
- name: `_MapsBrokerAsyncOperation::MapsBrokerAsyncOperation_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007928`

## pseudocode

```c
void __fastcall MapsBrokerAsyncOperation::MapsBrokerAsyncOperation_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMapsBrokerAsyncOperation>::~RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMapsBrokerAsyncOperation>(*(_QWORD *)(a2 + 64));
}

```

## disassembly

```asm
0x1800111e7  mov     rcx, [rdx+40h]
0x1800111ee  jmp     ??1?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIMapsBrokerAsyncOperation@@@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMapsBrokerAsyncOperation>::~RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IMapsBrokerAsyncOperation>(void)
```
