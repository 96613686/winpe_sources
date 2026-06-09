# MicrosoftTelemetryAssertTriggeredNoArgsKM

- ea: `0x14000935c`
- end: `0x140009387`
- name: `MicrosoftTelemetryAssertTriggeredNoArgsKM`
- size: `43`
- prototype: ``
- caller_count: `22`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400018cc`
- `0x140002138`
- `0x14000225c`
- `0x1400023c0`
- `0x14000242c`
- `0x140002498`
- `0x14000294c`
- `0x1400029f4`
- `0x1400030dc`
- `0x140003f18`
- `0x140004330`
- `0x140004e54`
- `0x140005874`
- `0x140006010`
- `0x1400063e0`
- `0x14000664c`
- `0x140007280`
- `0x140008798`
- `0x140008878`
- `0x1400089c8`
- `0x140008ac4`
- `0x140009fb4`

## callees

- `0x140009390`

## pseudocode

```c
__int64 MicrosoftTelemetryAssertTriggeredNoArgsKM()
{
  void *retaddr; // [rsp+38h] [rbp+0h]

  return MicrosoftTelemetryAssertTriggeredWorker(retaddr, 0, 0);
}

```

## disassembly

```asm
0x14000935c  sub     rsp, 38h
0x140009360  mov     rcx, [rsp+38h]
0x140009365  or      r9d, 0FFFFFFFFh
0x140009369  mov     [rsp+38h+var_10], 0
0x140009372  xor     r8d, r8d
0x140009375  xor     edx, edx
0x140009377  mov     [rsp+38h+var_18], r9d
0x14000937c  call    MicrosoftTelemetryAssertTriggeredWorker
0x140009381  add     rsp, 38h
0x140009385  retn
```
