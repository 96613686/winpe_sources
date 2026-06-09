# std::_Func_impl<std::_Callable_fun<int (*const)(void *),0>,std::allocator<std::_Func_class<int,void *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,int,void *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::_Move(void *)

- ea: `0x1400119d0`
- end: `0x140011a0f`
- name: `?_Move@?$_Func_impl@U?$_Callable_fun@Q6AHPEAX@Z$0A@@std@@V?$allocator@V?$_Func_class@HPEAXU_Nil@std@@U12@U12@U12@U12@U12@@std@@@2@HPEAXU_Nil@2@U42@U42@U42@U42@U42@@std@@UEAAPEAV?$_Func_base@HPEAXU_Nil@std@@U12@U12@U12@U12@U12@@2@PEAX@Z`
- size: `63`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400014fc`
- `0x140001758`
- `0x1400119d0`

## pseudocode

```c
_QWORD *__fastcall std::_Func_impl<std::_Callable_fun<int (*const)(void *),0>,std::allocator<std::_Func_class<int,void *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,int,void *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::_Move(
        __int64 a1,
        _QWORD *a2)
{
  if ( !a2 )
  {
    a2 = operator new(0x18u);
    if ( !a2 )
      std::_Xbad_alloc();
  }
  *a2 = &std::_Func_impl<std::_Callable_fun<int (*const)(void *),0>,std::allocator<std::_Func_class<int,void *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,int,void *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable';
  a2[1] = *(_QWORD *)(a1 + 8);
  return a2;
}

```

## disassembly

```asm
0x1400119d0  push    rbx
0x1400119d2  sub     rsp, 20h
0x1400119d6  mov     rbx, rcx
0x1400119d9  test    rdx, rdx
0x1400119dc  jnz     short loc_1400119EE
0x1400119de  lea     ecx, [rdx+18h]; Size
0x1400119e1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400119e6  mov     rdx, rax
0x1400119e9  test    rax, rax
0x1400119ec  jz      short loc_140011A09
0x1400119ee  lea     rax, ??_7?$_Func_impl@U?$_Callable_fun@Q6AHPEAX@Z$0A@@std@@V?$allocator@V?$_Func_class@HPEAXU_Nil@std@@U12@U12@U12@U12@U12@@std@@@2@HPEAXU_Nil@2@U42@U42@U42@U42@U42@@std@@6B@; const std::_Func_impl<std::_Callable_fun<int (*const)(void *),0>,std::allocator<std::_Func_class<int,void *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,int,void *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable'
0x1400119f5  mov     [rdx], rax
0x1400119f8  mov     rax, [rbx+8]
0x1400119fc  mov     [rdx+8], rax
0x140011a00  mov     rax, rdx
0x140011a03  add     rsp, 20h
0x140011a07  pop     rbx
0x140011a08  retn
0x140011a09  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
