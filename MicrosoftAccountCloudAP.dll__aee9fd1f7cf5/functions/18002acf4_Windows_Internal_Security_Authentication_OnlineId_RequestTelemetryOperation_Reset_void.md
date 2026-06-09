# Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation::Reset(void)

- ea: `0x18002acf4`
- end: `0x18002ad30`
- name: `?Reset@RequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@AEAAXXZ`
- size: `60`
- prototype: `void __fastcall(Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002abd0`

## callees

- `0x18002adb0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ad14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ad14`

## pseudocode

```c
void __fastcall Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation::Reset(
        Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation *this)
{
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_BYTE *)this + 16) = 0;
  WindowsDeleteString(*((HSTRING *)this + 3));
  *((_QWORD *)this + 3) = 0;
  std::list<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation>::clear((__int64 *)this + 4);
}

```

## disassembly

```asm
0x18002acf4  push    rbx
0x18002acf6  sub     rsp, 20h
0x18002acfa  mov     rbx, rcx
0x18002acfd  mov     qword ptr [rcx], 0
0x18002ad04  mov     qword ptr [rcx+8], 0
0x18002ad0c  mov     byte ptr [rcx+10h], 0
0x18002ad10  mov     rcx, [rcx+18h]; string
0x18002ad14  call    cs:__imp_WindowsDeleteString
0x18002ad1a  lea     rcx, [rbx+20h]
0x18002ad1e  mov     qword ptr [rbx+18h], 0
0x18002ad26  add     rsp, 20h
0x18002ad2a  pop     rbx
0x18002ad2b  jmp     ?clear@?$list@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@V?$allocator@VRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAAXXZ; std::list<Windows::Internal::Security::Authentication::OnlineId::RequestTelemetryOperation>::clear(void)
```
