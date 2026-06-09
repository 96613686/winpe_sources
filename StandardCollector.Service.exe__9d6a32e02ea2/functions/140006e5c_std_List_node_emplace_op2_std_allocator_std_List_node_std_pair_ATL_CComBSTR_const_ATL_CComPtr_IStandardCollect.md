# std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>,void *>>>(void)

- ea: `0x140006e5c`
- end: `0x140006eb2`
- name: `??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBVCComBSTR@ATL@@V?$CComPtr@UIStandardCollectorService@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `86`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140015078`

## callees

- `0x140006e5c`
- `0x14001382c`
- `0x140014c70`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140006e8d`
- `OLEAUT32!__imp_SysFreeString` at `0x140006e8d`

## pseudocode

```c
void __fastcall std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<ATL::CComBSTR const,ATL::CComPtr<IStandardCollectorService>>,void *>>>(
        __int64 a1)
{
  __int64 v2; // rbx
  __int64 v3; // rcx
  void *v4; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
  {
    v3 = *(_QWORD *)(v2 + 24);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    SysFreeString(*(BSTR *)(v2 + 16));
  }
  v4 = *(void **)(a1 + 8);
  if ( v4 )
    operator delete(v4);
}

```

## disassembly

```asm
0x140006e5c  mov     [rsp+arg_8], rbx
0x140006e61  push    rdi
0x140006e62  sub     rsp, 20h
0x140006e66  mov     rdi, rcx
0x140006e69  mov     rbx, [rcx+8]
0x140006e6d  test    rbx, rbx
0x140006e70  jz      short loc_140006E93
0x140006e72  mov     rcx, [rbx+18h]
0x140006e76  test    rcx, rcx
0x140006e79  jz      short loc_140006E89
0x140006e7b  mov     rax, [rcx]
0x140006e7e  mov     rax, [rax+10h]
0x140006e82  call    cs:__guard_dispatch_icall_fptr
0x140006e88  nop
0x140006e89  mov     rcx, [rbx+10h]; bstrString
0x140006e8d  call    cs:__imp_SysFreeString
0x140006e93  mov     rcx, [rdi+8]; Block
0x140006e97  test    rcx, rcx
0x140006e9a  jz      short loc_140006EA7
0x140006e9c  mov     edx, 20h ; ' '
0x140006ea1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140006ea6  nop
0x140006ea7  mov     rbx, [rsp+28h+arg_8]
0x140006eac  add     rsp, 20h
0x140006eb0  pop     rdi
0x140006eb1  retn
```
