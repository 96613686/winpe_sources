# _CNgcNode::_DeviceCreateCallback_::_1_::dtor$1

- ea: `0x18001f2c1`
- end: `0x18001f2cd`
- name: `_CNgcNode::_DeviceCreateCallback_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800119b8`

## pseudocode

```c
__int64 __fastcall CNgcNode::_DeviceCreateCallback_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wil::details::ScopeExitFnGuard__lambda_3f584b9b580ddfa04b24e4edfdd7f979___::_ScopeExitFnGuard__lambda_3f584b9b580ddfa04b24e4edfdd7f979___(a2 + 56);
}

```

## disassembly

```asm
0x18001f2c1  lea     rcx, [rdx+38h]
0x18001f2c8  jmp     wil__details__ScopeExitFnGuard__lambda_3f584b9b580ddfa04b24e4edfdd7f979______ScopeExitFnGuard__lambda_3f584b9b580ddfa04b24e4edfdd7f979___
```
