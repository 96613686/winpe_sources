# _CTaskCounter::Initialize_::_1_::dtor$1

- ea: `0x18001e953`
- end: `0x18001e95f`
- name: `_CTaskCounter::Initialize_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180007614`

## pseudocode

```c
__int64 __fastcall CTaskCounter::Initialize_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wil::details::ScopeExitFnGuard__lambda_349182dd85bd6507f6866e4526050a91___::_ScopeExitFnGuard__lambda_349182dd85bd6507f6866e4526050a91___(a2 + 36);
}

```

## disassembly

```asm
0x18001e953  lea     rcx, [rdx+24h]
0x18001e95a  jmp     wil__details__ScopeExitFnGuard__lambda_349182dd85bd6507f6866e4526050a91______ScopeExitFnGuard__lambda_349182dd85bd6507f6866e4526050a91___
```
