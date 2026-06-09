# std::_List_buy<Repair *,std::allocator<Repair *>>::_Buynode<Repair * const &>(std::_List_node<Repair *,void *> *,std::_List_node<Repair *,void *> *,Repair * const &)

- ea: `0x18000a960`
- end: `0x18000a984`
- name: `??$_Buynode@AEBQEAVRepair@@@?$_List_buy@PEAVRepair@@V?$allocator@PEAVRepair@@@std@@@std@@QEAAPEAU?$_List_node@PEAVRepair@@PEAX@1@PEAU21@0AEBQEAVRepair@@@Z`
- size: `36`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000ab58`
- `0x18000f7dc`

## callees

- `0x18000aa18`

## pseudocode

```c
_QWORD *__fastcall std::_List_buy<Repair *>::_Buynode<Repair * const &>(__int64 a1, _QWORD *a2, _QWORD *a3, _QWORD *a4)
{
  _QWORD *result; // rax

  result = std::_List_alloc<0,std::_List_base_types<Repair *>>::_Buynode0(a1, a2, a3);
  result[2] = *a4;
  return result;
}

```

## disassembly

```asm
0x18000a960  mov     [rsp+arg_0], rcx
0x18000a965  push    rbx
0x18000a966  sub     rsp, 20h
0x18000a96a  mov     rbx, r9
0x18000a96d  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@PEAVRepair@@V?$allocator@PEAVRepair@@@std@@@std@@@std@@QEAAPEAU?$_List_node@PEAVRepair@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<Repair *>>::_Buynode0(std::_List_node<Repair *,void *> *,std::_List_node<Repair *,void *> *)
0x18000a972  mov     [rsp+28h+arg_0], rax
0x18000a977  mov     rcx, [rbx]
0x18000a97a  mov     [rax+10h], rcx
0x18000a97e  add     rsp, 20h
0x18000a982  pop     rbx
0x18000a983  retn
```
