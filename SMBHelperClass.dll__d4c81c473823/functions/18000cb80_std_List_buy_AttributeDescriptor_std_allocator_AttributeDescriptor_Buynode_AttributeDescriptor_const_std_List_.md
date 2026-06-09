# std::_List_buy<AttributeDescriptor,std::allocator<AttributeDescriptor>>::_Buynode<AttributeDescriptor const &>(std::_List_node<AttributeDescriptor,void *> *,std::_List_node<AttributeDescriptor,void *> *,AttributeDescriptor const &)

- ea: `0x18000cb80`
- end: `0x18000cba5`
- name: `??$_Buynode@AEBUAttributeDescriptor@@@?$_List_buy@UAttributeDescriptor@@V?$allocator@UAttributeDescriptor@@@std@@@std@@QEAAPEAU?$_List_node@UAttributeDescriptor@@PEAX@1@PEAU21@0AEBUAttributeDescriptor@@@Z`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002974`

## callees

- `0x18000cc24`

## pseudocode

```c
_QWORD *__fastcall std::_List_buy<AttributeDescriptor>::_Buynode<AttributeDescriptor const &>(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        _OWORD *a4)
{
  _QWORD *result; // rax

  result = std::_List_alloc<0,std::_List_base_types<AttributeDescriptor>>::_Buynode0(a1, a2, a3);
  *((_OWORD *)result + 1) = *a4;
  return result;
}

```

## disassembly

```asm
0x18000cb80  mov     [rsp+arg_0], rcx
0x18000cb85  push    rbx
0x18000cb86  sub     rsp, 20h
0x18000cb8a  mov     rbx, r9
0x18000cb8d  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UAttributeDescriptor@@V?$allocator@UAttributeDescriptor@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UAttributeDescriptor@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<AttributeDescriptor>>::_Buynode0(std::_List_node<AttributeDescriptor,void *> *,std::_List_node<AttributeDescriptor,void *> *)
0x18000cb92  mov     [rsp+28h+arg_0], rax
0x18000cb97  movups  xmm0, xmmword ptr [rbx]
0x18000cb9a  movdqu  xmmword ptr [rax+10h], xmm0
0x18000cb9f  add     rsp, 20h
0x18000cba3  pop     rbx
0x18000cba4  retn
```
