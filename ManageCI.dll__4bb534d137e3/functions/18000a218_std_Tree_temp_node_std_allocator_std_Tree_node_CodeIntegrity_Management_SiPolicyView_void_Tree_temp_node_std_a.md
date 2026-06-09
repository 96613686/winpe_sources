# std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyView,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyView,void *>>>(void)

- ea: `0x18000a218`
- end: `0x18000a242`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@VSiPolicyView@Management@CodeIntegrity@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `42`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009c40`
- `0x18000dca4`
- `0x18002a287`
- `0x18002a4a9`

## callees

- `0x18000589c`
- `0x18000a1c4`
- `0x18000a218`

## pseudocode

```c
__int64 __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyView,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyView,void *>>>(
        __int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
    CodeIntegrity::Management::SiPolicyView::`scalar deleting destructor'(
      (CodeIntegrity::Management::SiPolicyView *)(v2 + 32),
      0);
  return std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyView,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyView,void *>>>(a1);
}

```

## disassembly

```asm
0x18000a218  push    rbx
0x18000a21a  sub     rsp, 20h
0x18000a21e  mov     rbx, rcx
0x18000a221  mov     rcx, [rcx+8]
0x18000a225  test    rcx, rcx
0x18000a228  jz      short loc_18000A235
0x18000a22a  add     rcx, 20h ; ' '; this
0x18000a22e  xor     edx, edx; unsigned int
0x18000a230  call    ??_GSiPolicyView@Management@CodeIntegrity@@QEAAPEAXI@Z; CodeIntegrity::Management::SiPolicyView::`scalar deleting destructor'(uint)
0x18000a235  mov     rcx, rbx
0x18000a238  add     rsp, 20h
0x18000a23c  pop     rbx
0x18000a23d  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@VSiPolicyView@Management@CodeIntegrity@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyView,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<CodeIntegrity::Management::SiPolicyView,void *>>>(void)
```
