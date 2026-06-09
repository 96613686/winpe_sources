# std::_Func_impl_no_alloc<`ActionDialogManager::HandlePromptSync(void *)'::`2'::_lambda_1_,long,>::_Delete_this(bool)

- ea: `0x1400076a0`
- end: `0x1400076b7`
- name: `?_Delete_this@?$_Func_impl_no_alloc@V_lambda_1_@?1??HandlePromptSync@ActionDialogManager@@SAJPEAX@Z@J$$V@std@@EEAAX_N@Z`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x14000175c`
- `0x1400076a0`

## pseudocode

```c
void __fastcall std::J$$V::Z::_Func_impl_no_alloc<`ActionDialogManager::HandlePromptSync'::`2'::_lambda_1_,long near * const volatile,void *>::_Delete_this(
        void *a1,
        char a2)
{
  if ( a2 )
    operator delete(a1);
}

```

## disassembly

```asm
0x1400076a0  sub     rsp, 28h
0x1400076a4  test    dl, dl
0x1400076a6  jz      short loc_1400076B2
0x1400076a8  mov     edx, 10h
0x1400076ad  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400076b2  add     rsp, 28h
0x1400076b6  retn
```
