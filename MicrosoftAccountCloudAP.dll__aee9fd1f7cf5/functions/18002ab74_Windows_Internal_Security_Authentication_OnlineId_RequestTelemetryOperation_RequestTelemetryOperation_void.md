# Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation::~RequestTelemetryOperation(void)

- ea: `0x18002ab74`
- end: `0x18002abac`
- name: `??1RequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002ac80`
- `0x1800314e4`

## callees

- `0x180003530`
- `0x18002a9b4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ab98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ab98`

## pseudocode

```c
void __fastcall Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation::~RequestTelemetryOperation(
        Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation *this)
{
  std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>::_Free_non_head<std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>>>(
    (__int64)this,
    *((_QWORD *)this + 4));
  operator delete(*((void **)this + 4));
  WindowsDeleteString(*((HSTRING *)this + 3));
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x18002ab74  push    rbx
0x18002ab76  sub     rsp, 20h
0x18002ab7a  mov     rdx, [rcx+20h]
0x18002ab7e  mov     rbx, rcx
0x18002ab81  call    ??$_Free_non_head@V?$allocator@U?$_List_node@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@PEAX@std@@@std@@@?$_List_node@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>::_Free_non_head<std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>>>(std::allocator<std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *>> &,std::_List_node<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation,void *> *)
0x18002ab86  mov     rcx, [rbx+20h]; Block
0x18002ab8a  mov     edx, 40h ; '@'
0x18002ab8f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002ab94  mov     rcx, [rbx+18h]; string
0x18002ab98  call    cs:__imp_WindowsDeleteString
0x18002ab9e  mov     qword ptr [rbx+18h], 0
0x18002aba6  add     rsp, 20h
0x18002abaa  pop     rbx
0x18002abab  retn
```
