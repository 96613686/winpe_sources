# std::_List_alloc<0,std::_List_base_types<std::unique_ptr<CInformationNode,std::default_delete<CInformationNode>>,std::allocator<std::unique_ptr<CInformationNode,std::default_delete<CInformationNode>>>>>::_Buynode0(std::_List_node<std::unique_ptr<CInformationNode,std::default_delete<CInformationNode>>,void *> *,std::_List_node<std::unique_ptr<CInformationNode,std::default_delete<CInformationNode>>,void *> *)

- ea: `0x18000d9cc`
- end: `0x18000da18`
- name: `?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@V?$allocator@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@@2@@std@@@std@@QEAAPEAU?$_List_node@V?$unique_ptr@VCInformationNode@@U?$default_delete@VCInformationNode@@@std@@@std@@PEAX@2@PEAU32@0@Z`
- size: `76`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000c558`
- `0x18000c5d8`
- `0x18000db7c`

## callees

- `0x180001444`
- `0x1800015e8`
- `0x18000d9cc`

## pseudocode

```c
_QWORD *__fastcall std::_List_alloc<0,std::_List_base_types<std::unique_ptr<CInformationNode>>>::_Buynode0(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *result; // rax

  result = operator new(0x18u);
  if ( !result )
    std::_Xbad_alloc();
  if ( !a2 )
  {
    a2 = result;
    a3 = result;
  }
  try
  {
    *result = a2;
    result[1] = a3;
  }
  catch ( ... )
  {
    operator delete(result);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18000d9cc  mov     [rsp+arg_8], rbx
0x18000d9d1  mov     [rsp+arg_0], rcx
0x18000d9d6  push    rdi
0x18000d9d7  sub     rsp, 20h
0x18000d9db  mov     rdi, r8
0x18000d9de  mov     rbx, rdx
0x18000d9e1  mov     ecx, 18h; Size
0x18000d9e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d9eb  mov     [rsp+28h+arg_0], rax
0x18000d9f0  test    rax, rax
0x18000d9f3  jnz     short loc_18000D9FB
0x18000d9f5  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000d9fb  test    rbx, rbx
0x18000d9fe  jnz     short loc_18000DA06
0x18000da00  mov     rbx, rax
0x18000da03  mov     rdi, rax
0x18000da06  mov     [rax], rbx
0x18000da09  mov     [rax+8], rdi
0x18000da0d  mov     rbx, [rsp+28h+arg_8]
0x18000da12  add     rsp, 20h
0x18000da16  pop     rdi
0x18000da17  retn
```
