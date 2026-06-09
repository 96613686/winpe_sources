# _CSession::_HandleReaderAction_::_1_::dtor$1

- ea: `0x18001ee38`
- end: `0x18001ee44`
- name: `_CSession::_HandleReaderAction_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000c798`

## pseudocode

```c
__int64 __fastcall CSession::_HandleReaderAction_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wil::details::ScopeExitFnGuard__lambda_1f25a61b5ace30e9fc9ecb8c3af71889___::_ScopeExitFnGuard__lambda_1f25a61b5ace30e9fc9ecb8c3af71889___(a2 + 80);
}

```

## disassembly

```asm
0x18001ee38  lea     rcx, [rdx+50h]
0x18001ee3f  jmp     wil__details__ScopeExitFnGuard__lambda_1f25a61b5ace30e9fc9ecb8c3af71889______ScopeExitFnGuard__lambda_1f25a61b5ace30e9fc9ecb8c3af71889___
```
