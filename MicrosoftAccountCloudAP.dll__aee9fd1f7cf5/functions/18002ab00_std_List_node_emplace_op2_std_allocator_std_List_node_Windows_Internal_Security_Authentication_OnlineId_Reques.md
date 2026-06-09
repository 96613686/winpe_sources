# std::_List_node_emplace_op2<std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>>>(void)

- ea: `0x18002ab00`
- end: `0x18002ab43`
- name: `??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `67`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002ade4`

## callees

- `0x18002aadc`
- `0x18002ab00`
- `0x18002ad84`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ab23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ab23`

## pseudocode

```c
void __fastcall std::_List_node_emplace_op2<std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>>>(
        __int64 a1)
{
  __int64 v1; // rbx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    std::list<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation>::_Tidy(v1 + 48);
    WindowsDeleteString(*(HSTRING *)(v1 + 40));
    *(_QWORD *)(v1 + 40) = 0;
  }
  std::_Alloc_construct_ptr<std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>>>(a1);
}

```

## disassembly

```asm
0x18002ab00  mov     [rsp+arg_0], rbx
0x18002ab05  push    rdi
0x18002ab06  sub     rsp, 20h
0x18002ab0a  mov     rbx, [rcx+8]
0x18002ab0e  mov     rdi, rcx
0x18002ab11  test    rbx, rbx
0x18002ab14  jz      short loc_18002AB31
0x18002ab16  lea     rcx, [rbx+30h]
0x18002ab1a  call    ?_Tidy@?$list@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@V?$allocator@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@AEAAXXZ; std::list<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation>::_Tidy(void)
0x18002ab1f  mov     rcx, [rbx+28h]; string
0x18002ab23  call    cs:__imp_WindowsDeleteString
0x18002ab29  mov     qword ptr [rbx+28h], 0
0x18002ab31  mov     rcx, rdi
0x18002ab34  mov     rbx, [rsp+28h+arg_0]
0x18002ab39  add     rsp, 20h
0x18002ab3d  pop     rdi
0x18002ab3e  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>>>(void)
```
