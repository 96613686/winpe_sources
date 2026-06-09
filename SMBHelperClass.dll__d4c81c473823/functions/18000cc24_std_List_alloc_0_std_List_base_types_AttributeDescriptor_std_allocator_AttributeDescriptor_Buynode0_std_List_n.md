# std::_List_alloc<0,std::_List_base_types<AttributeDescriptor,std::allocator<AttributeDescriptor>>>::_Buynode0(std::_List_node<AttributeDescriptor,void *> *,std::_List_node<AttributeDescriptor,void *> *)

- ea: `0x18000cc24`
- end: `0x18000cc70`
- name: `?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UAttributeDescriptor@@V?$allocator@UAttributeDescriptor@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UAttributeDescriptor@@PEAX@2@PEAU32@0@Z`
- size: `76`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180002974`
- `0x18000cb80`

## callees

- `0x18000123c`
- `0x180001578`
- `0x18000cc24`

## pseudocode

```c
_QWORD *__fastcall std::_List_alloc<0,std::_List_base_types<AttributeDescriptor>>::_Buynode0(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *result; // rax

  result = operator new(0x20u);
  if ( !result )
    std::_Xbad_alloc();
  if ( !a2 )
  {
    a2 = result;
    a3 = result;
  }
  *result = a2;
  result[1] = a3;
  return result;
}

```

## disassembly

```asm
0x18000cc24  mov     [rsp+arg_8], rbx
0x18000cc29  mov     [rsp+arg_0], rcx
0x18000cc2e  push    rdi
0x18000cc2f  sub     rsp, 20h
0x18000cc33  mov     rdi, r8
0x18000cc36  mov     rbx, rdx
0x18000cc39  mov     ecx, 20h ; ' '; Size
0x18000cc3e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000cc43  mov     [rsp+28h+arg_0], rax
0x18000cc48  test    rax, rax
0x18000cc4b  jz      short loc_18000CC6A
0x18000cc4d  test    rbx, rbx
0x18000cc50  jnz     short loc_18000CC58
0x18000cc52  mov     rbx, rax
0x18000cc55  mov     rdi, rax
0x18000cc58  mov     [rax], rbx
0x18000cc5b  mov     [rax+8], rdi
0x18000cc5f  mov     rbx, [rsp+28h+arg_8]
0x18000cc64  add     rsp, 20h
0x18000cc68  pop     rdi
0x18000cc69  retn
0x18000cc6a  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
