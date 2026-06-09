# _Microsoft::WRL::Details::Make_MapsBrokerAsyncOperation_long_(__cdecl_)(_RPC_ASYNC_STATE__)__::_1_::dtor$1

- ea: `0x180011285`
- end: `0x180011291`
- name: `_Microsoft::WRL::Details::Make_MapsBrokerAsyncOperation_long_(__cdecl_)(_RPC_ASYNC_STATE__)__::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180008fd8`

## pseudocode

```c
void __fastcall Microsoft::WRL::Details::Make_MapsBrokerAsyncOperation_long____cdecl____RPC_ASYNC_STATE_____::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  std::unique_ptr<_RPC_ASYNC_STATE>::~unique_ptr<_RPC_ASYNC_STATE>((void **)(a2 + 80));
}

```

## disassembly

```asm
0x180011285  lea     rcx, [rdx+50h]
0x18001128c  jmp     ??1?$unique_ptr@U_RPC_ASYNC_STATE@@U?$default_delete@U_RPC_ASYNC_STATE@@@std@@@std@@QEAA@XZ; std::unique_ptr<_RPC_ASYNC_STATE>::~unique_ptr<_RPC_ASYNC_STATE>(void)
```
