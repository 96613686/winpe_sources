# _dynamic_atexit_destructor_for__IncomingTextMessageHandler::sm_incomingTextMessageHandler__

- ea: `0x18000b120`
- end: `0x18000b141`
- name: `_dynamic_atexit_destructor_for__IncomingTextMessageHandler::sm_incomingTextMessageHandler__`
- size: `33`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b120`
- `0x18000c010`

## pseudocode

```c
__int64 dynamic_atexit_destructor_for__IncomingTextMessageHandler::sm_incomingTextMessageHandler__()
{
  __int64 result; // rax

  if ( IncomingTextMessageHandler::sm_incomingTextMessageHandler )
    return (*(__int64 (__fastcall **)(IncomingTextMessageHandler *))(*(_QWORD *)IncomingTextMessageHandler::sm_incomingTextMessageHandler
                                                                   + 8LL))(IncomingTextMessageHandler::sm_incomingTextMessageHandler);
  return result;
}

```

## disassembly

```asm
0x18000b120  sub     rsp, 28h
0x18000b124  mov     rcx, cs:?sm_incomingTextMessageHandler@IncomingTextMessageHandler@@0V?$CComPtr@VIncomingTextMessageHandler@@@ATL@@A; ATL::CComPtr<IncomingTextMessageHandler> IncomingTextMessageHandler::sm_incomingTextMessageHandler
0x18000b12b  test    rcx, rcx
0x18000b12e  jz      short loc_18000B13C
0x18000b130  mov     rax, [rcx]
0x18000b133  mov     rax, [rax+8]
0x18000b137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b13c  add     rsp, 28h
0x18000b140  retn
```
