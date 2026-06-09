# _UpdateAppUriHandlerRegistrationForFile_::_1_::dtor$2

- ea: `0x140011b21`
- end: `0x140011b2d`
- name: `_UpdateAppUriHandlerRegistrationForFile_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140009e70`

## pseudocode

```c
__int64 __fastcall UpdateAppUriHandlerRegistrationForFile_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return wil::details::ScopeExitFn__lambda_81c4fc374f9dfcee604b97dcc0beb5f1___::_ScopeExitFn__lambda_81c4fc374f9dfcee604b97dcc0beb5f1___(a2 + 96);
}

```

## disassembly

```asm
0x140011b21  lea     rcx, [rdx+60h]
0x140011b28  jmp     wil__details__ScopeExitFn__lambda_81c4fc374f9dfcee604b97dcc0beb5f1______ScopeExitFn__lambda_81c4fc374f9dfcee604b97dcc0beb5f1___
```
