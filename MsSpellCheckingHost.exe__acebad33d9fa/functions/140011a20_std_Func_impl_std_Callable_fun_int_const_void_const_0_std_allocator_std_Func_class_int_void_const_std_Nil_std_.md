# std::_Func_impl<std::_Callable_fun<int (*const)(void const *),0>,std::allocator<std::_Func_class<int,void const *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,int,void const *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::_Move(void *)

- ea: `0x140011a20`
- end: `0x140011a5f`
- name: `?_Move@?$_Func_impl@U?$_Callable_fun@Q6AHPEBX@Z$0A@@std@@V?$allocator@V?$_Func_class@HPEBXU_Nil@std@@U12@U12@U12@U12@U12@@std@@@2@HPEBXU_Nil@2@U42@U42@U42@U42@U42@@std@@UEAAPEAV?$_Func_base@HPEBXU_Nil@std@@U12@U12@U12@U12@U12@@2@PEAX@Z`
- size: `63`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400014fc`
- `0x140001758`
- `0x140011a20`

## pseudocode

```c
_QWORD *__fastcall std::_Func_impl<std::_Callable_fun<int (*const)(void const *),0>,std::allocator<std::_Func_class<int,void const *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,int,void const *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::_Move(
        __int64 a1,
        _QWORD *a2)
{
  if ( !a2 )
  {
    a2 = operator new(0x18u);
    if ( !a2 )
      std::_Xbad_alloc();
  }
  *a2 = &std::_Func_impl<std::_Callable_fun<int (*const)(void const *),0>,std::allocator<std::_Func_class<int,void const *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,int,void const *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable';
  a2[1] = *(_QWORD *)(a1 + 8);
  return a2;
}

```

## disassembly

```asm
0x140011a20  push    rbx
0x140011a22  sub     rsp, 20h
0x140011a26  mov     rbx, rcx
0x140011a29  test    rdx, rdx
0x140011a2c  jnz     short loc_140011A3E
0x140011a2e  lea     ecx, [rdx+18h]; Size
0x140011a31  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140011a36  mov     rdx, rax
0x140011a39  test    rax, rax
0x140011a3c  jz      short loc_140011A59
0x140011a3e  lea     rax, ??_7?$_Func_impl@U?$_Callable_fun@Q6AHPEBX@Z$0A@@std@@V?$allocator@V?$_Func_class@HPEBXU_Nil@std@@U12@U12@U12@U12@U12@@std@@@2@HPEBXU_Nil@2@U42@U42@U42@U42@U42@@std@@6B@; const std::_Func_impl<std::_Callable_fun<int (*const)(void const *),0>,std::allocator<std::_Func_class<int,void const *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>>,int,void const *,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil,std::_Nil>::`vftable'
0x140011a45  mov     [rdx], rax
0x140011a48  mov     rax, [rbx+8]
0x140011a4c  mov     [rdx+8], rax
0x140011a50  mov     rax, rdx
0x140011a53  add     rsp, 20h
0x140011a57  pop     rbx
0x140011a58  retn
0x140011a59  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
