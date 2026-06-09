# _ServiceBase::ServiceMain_::_1_::dtor$2

- ea: `0x180011149`
- end: `0x180011155`
- name: `_ServiceBase::ServiceMain_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000ddd4`

## pseudocode

```c
__int64 __fastcall ServiceBase::ServiceMain_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return wil::details::ScopeExitFn__lambda_537ed9c35ac0bc8f39ba3504d4808e79___::_ScopeExitFn__lambda_537ed9c35ac0bc8f39ba3504d4808e79___(a2 + 64);
}

```

## disassembly

```asm
0x180011149  lea     rcx, [rdx+40h]
0x180011150  jmp     wil__details__ScopeExitFn__lambda_537ed9c35ac0bc8f39ba3504d4808e79______ScopeExitFn__lambda_537ed9c35ac0bc8f39ba3504d4808e79___
```
