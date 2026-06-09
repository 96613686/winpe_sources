# UninitializeService(long)

- ea: `0x180003b00`
- end: `0x180003b3c`
- name: `?UninitializeService@@YAXJ@Z`
- size: `60`
- prototype: `void __fastcall(int)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180003860`
- `0x1800039f0`

## callees

- `0x180001cf0`
- `0x18000a108`
- `0x18000b3b8`

## pseudocode

```c
void __fastcall UninitializeService(int a1)
{
  SvcLogEventFromServiceEngine(2, a1);
  UnRegisterForWNFs();
  wil::details::g_pfnLoggingCallback = 0;
  TraceLoggingUnregister_EventUnregister();
  SvcLogEventFromServiceEngine(3, a1);
}

```

## disassembly

```asm
0x180003b00  push    rbx
0x180003b02  sub     rsp, 20h
0x180003b06  mov     ebx, ecx
0x180003b08  mov     edx, ecx
0x180003b0a  mov     ecx, 2
0x180003b0f  call    ?SvcLogEventFromServiceEngine@@YAXW4SvcLogPoint@@J@Z; SvcLogEventFromServiceEngine(SvcLogPoint,long)
0x180003b14  call    ?UnRegisterForWNFs@@YAXXZ; UnRegisterForWNFs(void)
0x180003b19  nop
0x180003b1a  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, 0
0x180003b25  call    TraceLoggingUnregister_EventUnregister
0x180003b2a  nop
0x180003b2b  mov     edx, ebx
0x180003b2d  mov     ecx, 3
0x180003b32  add     rsp, 20h
0x180003b36  pop     rbx
0x180003b37  jmp     ?SvcLogEventFromServiceEngine@@YAXW4SvcLogPoint@@J@Z; SvcLogEventFromServiceEngine(SvcLogPoint,long)
```
