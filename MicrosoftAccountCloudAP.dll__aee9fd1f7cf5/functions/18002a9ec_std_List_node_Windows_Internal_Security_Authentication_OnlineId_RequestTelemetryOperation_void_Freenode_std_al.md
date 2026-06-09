# std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>::_Freenode<std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>>>(std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>> &,std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *> *)

- ea: `0x18002a9ec`
- end: `0x18002aa22`
- name: `??$_Freenode@V?$allocator@U?$_List_node@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@PEAX@std@@@std@@@?$_List_node@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@PEAX@std@@@1@PEAU01@@Z`
- size: `54`
- prototype: `void __fastcall(__int64, HSTRING *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002a9b4`

## callees

- `0x180003530`
- `0x18002ad84`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002aa02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002aa02`

## pseudocode

```c
void __fastcall std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>::_Freenode<std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>>>(
        __int64 a1,
        HSTRING *a2)
{
  std::list<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation>::_Tidy(a2 + 6);
  WindowsDeleteString(a2[5]);
  a2[5] = 0;
  operator delete(a2);
}

```

## disassembly

```asm
0x18002a9ec  push    rbx
0x18002a9ee  sub     rsp, 20h
0x18002a9f2  lea     rcx, [rdx+30h]
0x18002a9f6  mov     rbx, rdx
0x18002a9f9  call    ?_Tidy@?$list@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@V?$allocator@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@AEAAXXZ; std::list<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation>::_Tidy(void)
0x18002a9fe  mov     rcx, [rbx+28h]; string
0x18002aa02  call    cs:__imp_WindowsDeleteString
0x18002aa08  mov     edx, 40h ; '@'
0x18002aa0d  mov     qword ptr [rbx+28h], 0
0x18002aa15  mov     rcx, rbx; Block
0x18002aa18  add     rsp, 20h
0x18002aa1c  pop     rbx
0x18002aa1d  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
