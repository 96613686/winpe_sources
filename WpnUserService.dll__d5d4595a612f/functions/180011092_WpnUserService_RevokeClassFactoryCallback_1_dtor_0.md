# _WpnUserService::RevokeClassFactoryCallback_::_1_::dtor$0

- ea: `0x180011092`
- end: `0x18001109e`
- name: `_WpnUserService::RevokeClassFactoryCallback_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000818c`

## pseudocode

```c
__int64 __fastcall WpnUserService::RevokeClassFactoryCallback_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return wil::details::ScopeExitFn__lambda_b5be9bbe31e520ef39e0cc2cd7ab50b8___::_ScopeExitFn__lambda_b5be9bbe31e520ef39e0cc2cd7ab50b8___(a2 + 48);
}

```

## disassembly

```asm
0x180011092  lea     rcx, [rdx+30h]
0x180011099  jmp     wil__details__ScopeExitFn__lambda_b5be9bbe31e520ef39e0cc2cd7ab50b8______ScopeExitFn__lambda_b5be9bbe31e520ef39e0cc2cd7ab50b8___
```
