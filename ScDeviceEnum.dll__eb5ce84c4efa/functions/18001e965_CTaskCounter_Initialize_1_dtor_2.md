# _CTaskCounter::Initialize_::_1_::dtor$2

- ea: `0x18001e965`
- end: `0x18001e971`
- name: `_CTaskCounter::Initialize_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180007620`

## pseudocode

```c
__int64 __fastcall CTaskCounter::Initialize_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return wil::details::ScopeExitFnGuard__lambda_9f007dc2373c375adaf9b2bd25c52df1___::_ScopeExitFnGuard__lambda_9f007dc2373c375adaf9b2bd25c52df1___(a2 + 32);
}

```

## disassembly

```asm
0x18001e965  lea     rcx, [rdx+20h]
0x18001e96c  jmp     wil__details__ScopeExitFnGuard__lambda_9f007dc2373c375adaf9b2bd25c52df1______ScopeExitFnGuard__lambda_9f007dc2373c375adaf9b2bd25c52df1___
```
