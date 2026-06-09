# _std::_List_alloc_0_std::_List_base_types_Repair___std::allocator_Repair_______::_Buynode0_::_1_::catch$0

- ea: `0x180010dba`
- end: `0x180010dda`
- name: `_std::_List_alloc_0_std::_List_base_types_Repair___std::allocator_Repair_______::_Buynode0_::_1_::catch$0`
- size: `32`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18000257c`
- `0x1800090dc`

## pseudocode

```c
void __fastcall __noreturn std::_List_alloc_0_std::_List_base_types_Repair___std::allocator_Repair_______::_Buynode0_::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  std::_Tree_buy<std::pair<unsigned long const,RootCause *>>::_Freenode0(a1, *(_QWORD *)(a2 + 48));
  throw;
}

```

## disassembly

```asm
0x180010dba  mov     [rsp+arg_8], rdx
0x180010dbf  push    rbp
0x180010dc0  sub     rsp, 20h
0x180010dc4  mov     rbp, rdx
0x180010dc7  mov     rdx, [rbp+30h]
0x180010dcb  call    ?_Freenode0@?$_Tree_buy@U?$pair@$$CBKPEAVRootCause@@@std@@V?$allocator@U?$pair@$$CBKPEAVRootCause@@@std@@@2@@std@@QEAAXPEAU?$_Tree_node@U?$pair@$$CBKPEAVRootCause@@@std@@PEAX@2@@Z; std::_Tree_buy<std::pair<ulong const,RootCause *>>::_Freenode0(std::_Tree_node<std::pair<ulong const,RootCause *>,void *> *)
0x180010dd0  xor     edx, edx; pThrowInfo
0x180010dd2  xor     ecx, ecx; pExceptionObject
0x180010dd4  call    _CxxThrowException_0
```
