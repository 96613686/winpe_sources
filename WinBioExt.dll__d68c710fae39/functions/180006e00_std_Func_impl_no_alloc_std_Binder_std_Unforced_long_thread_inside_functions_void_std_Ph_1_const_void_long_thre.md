# std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (*&)(thread_inside_functions &,void *),std::_Ph<1> const &,void * &>,long,thread_inside_functions &>::_Copy(void *)

- ea: `0x180006e00`
- end: `0x180006e24`
- name: `?_Copy@?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@AEAP6AJAEAVthread_inside_functions@@PEAX@ZAEBU?$_Ph@$00@2@AEAPEAX@std@@JAEAVthread_inside_functions@@@std@@EEBAPEAV?$_Func_base@JAEAVthread_inside_functions@@@2@PEAX@Z`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## pseudocode

```c
__int64 __fastcall std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (*&)(thread_inside_functions &,void *),std::_Ph<1> const &,void * &>,long,thread_inside_functions &>::_Copy(
        __int64 a1,
        __int64 a2)
{
  *(_QWORD *)a2 = &std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (*&)(thread_inside_functions &,void *),std::_Ph<1> const &,void * &>,long,thread_inside_functions &>::`vftable';
  *(_QWORD *)(a2 + 8) = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(a2 + 16) = *(_QWORD *)(a1 + 16);
  *(_BYTE *)(a2 + 24) = *(_BYTE *)(a1 + 24);
  return a2;
}

```

## disassembly

```asm
0x180006e00  lea     rax, ??_7?$_Func_impl_no_alloc@V?$_Binder@U_Unforced@std@@AEAP6AJAEAVthread_inside_functions@@PEAX@ZAEBU?$_Ph@$00@2@AEAPEAX@std@@JAEAVthread_inside_functions@@@std@@6B@; const std::_Func_impl_no_alloc<std::_Binder<std::_Unforced,long (*&)(thread_inside_functions &,void *),std::_Ph<1> const &,void * &>,long,thread_inside_functions &>::`vftable'
0x180006e07  mov     [rdx], rax
0x180006e0a  mov     rax, [rcx+8]
0x180006e0e  mov     [rdx+8], rax
0x180006e12  mov     rax, [rcx+10h]
0x180006e16  mov     [rdx+10h], rax
0x180006e1a  mov     al, [rcx+18h]
0x180006e1d  mov     [rdx+18h], al
0x180006e20  mov     rax, rdx
0x180006e23  retn
```
