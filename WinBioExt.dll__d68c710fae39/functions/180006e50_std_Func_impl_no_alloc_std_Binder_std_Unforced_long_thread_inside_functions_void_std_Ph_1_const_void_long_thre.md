# std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (*&)(thread_inside_functions &,void *),std::_Ph<1> const &,void * &>,long,thread_inside_functions &>::_Do_call(thread_inside_functions &)

- ea: `0x180006e50`
- end: `0x180006e63`
- name: `?_Do_call@?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@AEAP6AJAEAVthread_inside_functions@@PEAX@ZAEBU?$_Ph@$00@2@AEAPEAX@std@@JAEAVthread_inside_functions@@@std@@EEAAJAEAVthread_inside_functions@@@Z`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x18000b010`

## pseudocode

```c
__int64 __fastcall std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (*&)(thread_inside_functions &,void *),std::_Ph<1> const &,void * &>,long,thread_inside_functions &>::_Do_call(
        __int64 a1,
        __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64, _QWORD))(a1 + 8))(a2, *(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x180006e50  mov     rax, [rcx+8]
0x180006e54  mov     r8, rdx
0x180006e57  mov     rdx, [rcx+10h]
0x180006e5b  mov     rcx, r8
0x180006e5e  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
