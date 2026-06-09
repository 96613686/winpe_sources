# ProcessNotification

- ea: `0x14000adf0`
- end: `0x14000ae46`
- name: `ProcessNotification`
- size: `86`
- prototype: `void __fastcall(PEPROCESS Process, __int64 ProcessId, __int64 CreateInfo)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x140001118`
- `0x14000aca0`
- `0x14000adf0`
- `0x14000b418`

## pseudocode

```c
void __fastcall ProcessNotification(PEPROCESS Process, __int64 ProcessId, __int64 CreateInfo)
{
  DbgTrace(2, "UevFilter.ProcessNotification: Entry\n");
  if ( CreateInfo )
  {
    ProcessCreateNotification(ProcessId, CreateInfo);
    SendProcessEventMessage(ProcessId);
  }
  DbgTrace(2, "UevFilter.ProcessNotification: Exit\n");
}

```

## disassembly

```asm
0x14000adf0  mov     [rsp+arg_0], rbx
0x14000adf5  push    rdi
0x14000adf6  sub     rsp, 20h
0x14000adfa  mov     rbx, rdx
0x14000adfd  mov     ecx, 2
0x14000ae02  lea     rdx, aUevfilterProce_6; "UevFilter.ProcessNotification: Entry\n"
0x14000ae09  mov     rdi, r8
0x14000ae0c  call    DbgTrace
0x14000ae11  test    rdi, rdi
0x14000ae14  jz      short loc_14000AE29
0x14000ae16  mov     rdx, rdi
0x14000ae19  mov     rcx, rbx
0x14000ae1c  call    ProcessCreateNotification
0x14000ae21  mov     rcx, rbx
0x14000ae24  call    SendProcessEventMessage
0x14000ae29  lea     rdx, aUevfilterProce_7; "UevFilter.ProcessNotification: Exit\n"
0x14000ae30  mov     ecx, 2
0x14000ae35  call    DbgTrace
0x14000ae3a  mov     rbx, [rsp+28h+arg_0]
0x14000ae3f  add     rsp, 20h
0x14000ae43  pop     rdi
0x14000ae44  retn
```
