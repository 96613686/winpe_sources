# std::_List_node_emplace_op2<std::allocator<std::_List_node<ATL::CComBSTR,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<ATL::CComBSTR,void *>>>(void)

- ea: `0x1400104b8`
- end: `0x1400104ed`
- name: `??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@VCComBSTR@ATL@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `53`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400159a0`

## callees

- `0x1400104b8`
- `0x14001382c`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400104ce`
- `OLEAUT32!__imp_SysFreeString` at `0x1400104ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_List_node_emplace_op2<std::allocator<std::_List_node<ATL::CComBSTR,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<ATL::CComBSTR,void *>>>(
        __int64 a1)
{
  __int64 v2; // rcx
  void *v3; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
    SysFreeString(*(BSTR *)(v2 + 16));
  v3 = *(void **)(a1 + 8);
  if ( v3 )
    operator delete(v3);
}

```

## disassembly

```asm
0x1400104b8  push    rbx
0x1400104ba  sub     rsp, 20h
0x1400104be  mov     rbx, rcx
0x1400104c1  mov     rcx, [rcx+8]
0x1400104c5  test    rcx, rcx
0x1400104c8  jz      short loc_1400104D4
0x1400104ca  mov     rcx, [rcx+10h]; bstrString
0x1400104ce  call    cs:__imp_SysFreeString
0x1400104d4  mov     rcx, [rbx+8]; Block
0x1400104d8  test    rcx, rcx
0x1400104db  jz      short loc_1400104E7
0x1400104dd  mov     edx, 18h
0x1400104e2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400104e7  add     rsp, 20h
0x1400104eb  pop     rbx
0x1400104ec  retn
```
