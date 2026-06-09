# std::_Tree<std::_Tmap_traits<_GUID,PDC_ENTRY *,guidcomp,std::allocator<std::pair<_GUID const,PDC_ENTRY *>>,0>>::clear(void)

- ea: `0x18000eeb0`
- end: `0x18000eee7`
- name: `?clear@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVPDC_ENTRY@@Uguidcomp@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVPDC_ENTRY@@@std@@@std@@$0A@@std@@@std@@QEAAXXZ`
- size: `55`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007df0`
- `0x180008020`
- `0x180008d00`
- `0x180015544`
- `0x18001939c`
- `0x180020530`

## callees

- `0x180002084`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<_GUID,PDC_ENTRY *,guidcomp,std::allocator<std::pair<_GUID const,PDC_ENTRY *>>,0>>::clear(
        _QWORD *a1)
{
  __int64 result; // rax

  std::_Tree<std::_Tmap_traits<unsigned __int64,_EVENT_SUBSCRIPTION *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>,0>>::_Erase(
    a1,
    *(_QWORD *)(*a1 + 8LL));
  *(_QWORD *)(*a1 + 8LL) = *a1;
  *(_QWORD *)*a1 = *a1;
  result = *a1;
  *(_QWORD *)(*a1 + 16LL) = *a1;
  a1[1] = 0;
  return result;
}

```

## disassembly

```asm
0x18000eeb0  push    rbx
0x18000eeb2  sub     rsp, 20h
0x18000eeb6  mov     rbx, rcx
0x18000eeb9  mov     rdx, [rcx]
0x18000eebc  mov     rdx, [rdx+8]
0x18000eec0  call    ?_Erase@?$_Tree@V?$_Tmap_traits@_KPEAU_EVENT_SUBSCRIPTION@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@@3@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CB_KPEAU_EVENT_SUBSCRIPTION@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,_EVENT_SUBSCRIPTION *,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>>,0>>::_Erase(std::_Tree_node<std::pair<unsigned __int64 const,_EVENT_SUBSCRIPTION *>,void *> *)
0x18000eec5  mov     rax, [rbx]
0x18000eec8  mov     [rax+8], rax
0x18000eecc  mov     rax, [rbx]
0x18000eecf  mov     [rax], rax
0x18000eed2  mov     rax, [rbx]
0x18000eed5  mov     [rax+10h], rax
0x18000eed9  mov     qword ptr [rbx+8], 0
0x18000eee1  add     rsp, 20h
0x18000eee5  pop     rbx
0x18000eee6  retn
```
