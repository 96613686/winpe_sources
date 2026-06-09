# _WiFiTaskPipeClient::IncomingMessage_::_1_::catch$1

- ea: `0x140010f61`
- end: `0x140010f89`
- name: `_WiFiTaskPipeClient::IncomingMessage_::_1_::catch$1`
- size: `40`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## pseudocode

```c
__int64 __fastcall WiFiTaskPipeClient::IncomingMessage_::_1_::catch_1(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 168) = -2147024882;
  return 0;
}

```

## disassembly

```asm
0x140010f61  mov     [rsp+arg_8], rdx
0x140010f66  push    rbp
0x140010f67  sub     rsp, 40h
0x140010f6b  mov     rbp, rdx
0x140010f6e  mov     dword ptr [rbp+0A8h], 8007000Eh
0x140010f78  mov     rax, 0
0x140010f82  add     rsp, 40h
0x140010f86  pop     rbp
0x140010f87  retn
```
