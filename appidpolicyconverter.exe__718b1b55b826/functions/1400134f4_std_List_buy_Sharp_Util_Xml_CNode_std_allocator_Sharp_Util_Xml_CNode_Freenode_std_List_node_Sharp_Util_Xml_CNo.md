# std::_List_buy<Sharp::Util::Xml::CNode,std::allocator<Sharp::Util::Xml::CNode>>::_Freenode(std::_List_node<Sharp::Util::Xml::CNode,void *> *)

- ea: `0x1400134f4`
- end: `0x14001351b`
- name: `?_Freenode@?$_List_buy@VCNode@Xml@Util@Sharp@@V?$allocator@VCNode@Xml@Util@Sharp@@@std@@@std@@QEAAXPEAU?$_List_node@VCNode@Xml@Util@Sharp@@PEAX@2@@Z`
- size: `39`
- prototype: `void __fastcall(__int64, void (__fastcall ***)(_QWORD, _QWORD))`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x1400120e0`

## callees

- `0x14000157c`
- `0x140016010`

## pseudocode

```c
void __fastcall std::_List_buy<Sharp::Util::Xml::CNode>::_Freenode(__int64 a1, void (__fastcall ***a2)(_QWORD, _QWORD))
{
  (*a2[2])(a2 + 2, 0);
  operator delete(a2);
}

```

## disassembly

```asm
0x1400134f4  push    rbx
0x1400134f6  sub     rsp, 20h
0x1400134fa  lea     rcx, [rdx+10h]
0x1400134fe  mov     rbx, rdx
0x140013501  mov     rax, [rcx]
0x140013504  xor     edx, edx
0x140013506  mov     rax, [rax]
0x140013509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001350e  mov     rcx, rbx; Block
0x140013511  add     rsp, 20h
0x140013515  pop     rbx
0x140013516  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
