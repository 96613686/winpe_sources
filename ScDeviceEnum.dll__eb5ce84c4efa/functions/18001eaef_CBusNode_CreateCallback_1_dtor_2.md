# _CBusNode::_CreateCallback_::_1_::dtor$2

- ea: `0x18001eaef`
- end: `0x18001eafb`
- name: `_CBusNode::_CreateCallback_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008440`

## pseudocode

```c
__int64 __fastcall CBusNode::_CreateCallback_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return wil::details::ScopeExitFnGuard__lambda_38e447e8f5eb8d94fc2cf5f8ab8fe563___::_ScopeExitFnGuard__lambda_38e447e8f5eb8d94fc2cf5f8ab8fe563___(a2 + 80);
}

```

## disassembly

```asm
0x18001eaef  lea     rcx, [rdx+50h]
0x18001eaf6  jmp     wil__details__ScopeExitFnGuard__lambda_38e447e8f5eb8d94fc2cf5f8ab8fe563______ScopeExitFnGuard__lambda_38e447e8f5eb8d94fc2cf5f8ab8fe563___
```
