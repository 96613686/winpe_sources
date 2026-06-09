# _CInformationNode::_CreateCallback_::_1_::dtor$1

- ea: `0x18001f1c3`
- end: `0x18001f1cf`
- name: `_CInformationNode::_CreateCallback_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180010064`

## pseudocode

```c
__int64 __fastcall CInformationNode::_CreateCallback_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wil::details::ScopeExitFnGuard__lambda_ab106416b255156e3aef6dee9bd62366___::_ScopeExitFnGuard__lambda_ab106416b255156e3aef6dee9bd62366___(a2 + 80);
}

```

## disassembly

```asm
0x18001f1c3  lea     rcx, [rdx+50h]
0x18001f1ca  jmp     wil__details__ScopeExitFnGuard__lambda_ab106416b255156e3aef6dee9bd62366______ScopeExitFnGuard__lambda_ab106416b255156e3aef6dee9bd62366___
```
