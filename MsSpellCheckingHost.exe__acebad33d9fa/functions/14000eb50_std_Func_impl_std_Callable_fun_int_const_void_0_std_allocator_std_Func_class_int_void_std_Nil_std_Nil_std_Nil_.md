# std::_Func_impl<std::_Callable_fun<int (*const)(void *),0>,std::allocator<std::_Func_class<int,void *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,int,void *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::_Delete_this(bool)

- ea: `0x14000eb50`
- end: `0x14000eb85`
- name: `?_Delete_this@?$_Func_impl@U?$_Callable_fun@Q6AHPEAX@Z$0A@@std@@V?$allocator@V?$_Func_class@HPEAXU_Nil@std@@U12@U12@U12@U12@U12@@std@@@2@HPEAXU_Nil@2@U42@U42@U42@U42@U42@@std@@EEAAX_N@Z`
- size: `53`
- prototype: `void __fastcall(void *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x14000eb50`
- `0x140013010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000eb74`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000eb74`

## pseudocode

```c
void __fastcall std::_Func_impl<std::_Callable_fun<int (*const)(void *),0>,std::allocator<std::_Func_class<int,void *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,int,void *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::_Delete_this(
        void *a1,
        char a2)
{
  (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, 0);
  if ( a2 )
    operator delete(a1);
}

```

## disassembly

```asm
0x14000eb50  mov     [rsp+arg_0], rbx
0x14000eb55  push    rdi
0x14000eb56  sub     rsp, 20h
0x14000eb5a  mov     rax, [rcx]
0x14000eb5d  mov     bl, dl
0x14000eb5f  xor     edx, edx
0x14000eb61  mov     rdi, rcx
0x14000eb64  mov     rax, [rax+28h]
0x14000eb68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eb6d  test    bl, bl
0x14000eb6f  jz      short loc_14000EB7A
0x14000eb71  mov     rcx, rdi
0x14000eb74  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000eb7a  mov     rbx, [rsp+28h+arg_0]
0x14000eb7f  add     rsp, 20h
0x14000eb83  pop     rdi
0x14000eb84  retn
```
