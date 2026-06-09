# MicrosoftTelemetryAssertTriggeredMsgKM

- ea: `0x14000c9fc`
- end: `0x14000ca26`
- name: `MicrosoftTelemetryAssertTriggeredMsgKM`
- size: `42`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002234`
- `0x1400025e4`
- `0x140002738`
- `0x14000a290`

## callees

- `0x14000ca2c`

## pseudocode

```c
void __fastcall MicrosoftTelemetryAssertTriggeredMsgKM(const char *a1)
{
  unsigned __int64 retaddr; // [rsp+38h] [rbp+0h]

  MicrosoftTelemetryAssertTriggeredWorker(retaddr, 0, 0, 0xFFFFFFFF, -1, a1);
}

```

## disassembly

```asm
0x14000c9fc  sub     rsp, 38h
0x14000ca00  mov     rax, rcx
0x14000ca03  or      r9d, 0FFFFFFFFh
0x14000ca07  mov     rcx, [rsp+38h]
0x14000ca0c  xor     r8d, r8d
0x14000ca0f  mov     [rsp+38h+var_10], rax
0x14000ca14  xor     edx, edx
0x14000ca16  mov     [rsp+38h+var_18], r9d
0x14000ca1b  call    MicrosoftTelemetryAssertTriggeredWorker
0x14000ca20  add     rsp, 38h
0x14000ca24  retn
```
