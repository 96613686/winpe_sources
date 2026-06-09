# std::_Func_impl_no_alloc<`ActionDialogManager::HandlePromptSync(void *)'::`2'::_lambda_1_,long,>::_Copy(void *)

- ea: `0x140007680`
- end: `0x140007696`
- name: `?_Copy@?$_Func_impl_no_alloc@V_lambda_1_@?1??HandlePromptSync@ActionDialogManager@@SAJPEAX@Z@J$$V@std@@EEBAPEAV?$_Func_base@J$$V@2@PEAX@Z`
- size: `22`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
_QWORD *__fastcall std::J$$V::Z::_Func_impl_no_alloc<`ActionDialogManager::HandlePromptSync'::`2'::_lambda_1_,long near * const volatile,void *>::_Copy(
        __int64 a1,
        _QWORD *a2)
{
  *a2 = std::J$$V::Z::_Func_impl_no_alloc<`ActionDialogManager::HandlePromptSync'::`2'::_lambda_1_,long near * const volatile,void *>::`vftable';
  a2[1] = *(_QWORD *)(a1 + 8);
  return a2;
}

```

## disassembly

```asm
0x140007680  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?1??HandlePromptSync@ActionDialogManager@@SAJPEAX@Z@J$$V@std@@6B@; const std::_Func_impl_no_alloc<`ActionDialogManager::HandlePromptSync(void *)'::`2'::_lambda_1_,long,>::`vftable'
0x140007687  mov     [rdx], rax
0x14000768a  mov     rax, [rcx+8]
0x14000768e  mov     [rdx+8], rax
0x140007692  mov     rax, rdx
0x140007695  retn
```
