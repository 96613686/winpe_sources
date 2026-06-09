# _CNgcNode::Uninstall_::_1_::dtor$1

- ea: `0x18001f243`
- end: `0x18001f24f`
- name: `_CNgcNode::Uninstall_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800119ac`

## pseudocode

```c
__int64 __fastcall CNgcNode::Uninstall_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wil::details::ScopeExitFnGuard__lambda_07b0745ddc92eb413bee6b1b57a85b42___::_ScopeExitFnGuard__lambda_07b0745ddc92eb413bee6b1b57a85b42___(a2 + 104);
}

```

## disassembly

```asm
0x18001f243  lea     rcx, [rdx+68h]
0x18001f24a  jmp     wil__details__ScopeExitFnGuard__lambda_07b0745ddc92eb413bee6b1b57a85b42______ScopeExitFnGuard__lambda_07b0745ddc92eb413bee6b1b57a85b42___
```
