# _ScDeviceEnumServiceMain_::_1_::dtor$1

- ea: `0x18001e864`
- end: `0x18001e870`
- name: `_ScDeviceEnumServiceMain_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180005e40`

## pseudocode

```c
__int64 __fastcall ScDeviceEnumServiceMain_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wil::details::ScopeExitFnGuard__lambda_d495ed0969d7a4df03df3ad00c2006cb___::_ScopeExitFnGuard__lambda_d495ed0969d7a4df03df3ad00c2006cb___(a2 + 72);
}

```

## disassembly

```asm
0x18001e864  lea     rcx, [rdx+48h]
0x18001e86b  jmp     wil__details__ScopeExitFnGuard__lambda_d495ed0969d7a4df03df3ad00c2006cb______ScopeExitFnGuard__lambda_d495ed0969d7a4df03df3ad00c2006cb___
```
