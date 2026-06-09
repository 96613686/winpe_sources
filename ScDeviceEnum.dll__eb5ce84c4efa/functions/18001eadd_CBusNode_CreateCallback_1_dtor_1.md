# _CBusNode::_CreateCallback_::_1_::dtor$1

- ea: `0x18001eadd`
- end: `0x18001eae9`
- name: `_CBusNode::_CreateCallback_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008434`

## pseudocode

```c
__int64 __fastcall CBusNode::_CreateCallback_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wil::details::ScopeExitFnGuard__lambda_2e5668b3dd55b38550ad49610b4ed3d9___::_ScopeExitFnGuard__lambda_2e5668b3dd55b38550ad49610b4ed3d9___(a2 + 104);
}

```

## disassembly

```asm
0x18001eadd  lea     rcx, [rdx+68h]
0x18001eae4  jmp     wil__details__ScopeExitFnGuard__lambda_2e5668b3dd55b38550ad49610b4ed3d9______ScopeExitFnGuard__lambda_2e5668b3dd55b38550ad49610b4ed3d9___
```
