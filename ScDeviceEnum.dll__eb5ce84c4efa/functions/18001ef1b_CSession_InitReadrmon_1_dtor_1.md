# _CSession::_InitReadrmon_::_1_::dtor$1

- ea: `0x18001ef1b`
- end: `0x18001ef27`
- name: `_CSession::_InitReadrmon_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c7a4`

## pseudocode

```c
__int64 __fastcall CSession::_InitReadrmon_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wil::details::ScopeExitFnGuard__lambda_50cef3df7a2899e4d80253e7bc680178___::_ScopeExitFnGuard__lambda_50cef3df7a2899e4d80253e7bc680178___(a2 + 52);
}

```

## disassembly

```asm
0x18001ef1b  lea     rcx, [rdx+34h]
0x18001ef22  jmp     wil__details__ScopeExitFnGuard__lambda_50cef3df7a2899e4d80253e7bc680178______ScopeExitFnGuard__lambda_50cef3df7a2899e4d80253e7bc680178___
```
