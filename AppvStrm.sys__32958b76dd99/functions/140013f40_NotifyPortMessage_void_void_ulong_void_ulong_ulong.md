# NotifyPortMessage(void *,void *,ulong,void *,ulong,ulong *)

- ea: `0x140013f40`
- end: `0x140013f61`
- name: `?NotifyPortMessage@@YAJPEAX0K0KPEAK@Z`
- size: `33`
- prototype: `NTSTATUS __fastcall(Streaming::Messaging::UserCommunication *PortCookie, PVOID InputBuffer, ULONG InputBufferLength, PVOID OutputBuffer, ULONG OutputBufferLength, PULONG ReturnOutputBufferLength)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140013f68`

## pseudocode

```c
NTSTATUS __fastcall NotifyPortMessage(
        Streaming::Messaging::UserCommunication *PortCookie,
        PVOID InputBuffer,
        ULONG InputBufferLength,
        PVOID OutputBuffer,
        ULONG OutputBufferLength,
        PULONG ReturnOutputBufferLength)
{
  return Streaming::Messaging::UserCommunication::ProcessMessage(
           PortCookie,
           InputBuffer,
           InputBufferLength,
           OutputBuffer,
           OutputBufferLength,
           ReturnOutputBufferLength);
}

```

## disassembly

```asm
0x140013f40  sub     rsp, 38h
0x140013f44  mov     rax, [rsp+38h+ReturnOutputBufferLength]
0x140013f49  mov     [rsp+38h+var_10], rax; unsigned int *
0x140013f4e  mov     eax, [rsp+38h+OutputBufferLength]
0x140013f52  mov     [rsp+38h+var_18], eax; unsigned int
0x140013f56  call    ?ProcessMessage@UserCommunication@Messaging@Streaming@@QEAAJPEAXK0KPEAK@Z; Streaming::Messaging::UserCommunication::ProcessMessage(void *,ulong,void *,ulong,ulong *)
0x140013f5b  add     rsp, 38h
0x140013f5f  retn
```
