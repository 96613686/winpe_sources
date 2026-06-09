# IncomingTextMessageHandler::Start(void)

- ea: `0x18000740c`
- end: `0x180007493`
- name: `?Start@IncomingTextMessageHandler@@QEAAJXZ`
- size: `135`
- prototype: `__int64 __fastcall(IncomingTextMessageHandler *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006d00`

## callees

- `0x18000108c`
- `0x180007248`
- `0x18000740c`
- `0x180007930`
- `0x18000aa50`

## pseudocode

```c
__int64 __fastcall IncomingTextMessageHandler::Start(IncomingTextMessageHandler *this)
{
  int v2; // eax
  __int64 v3; // r8
  unsigned int v4; // ebx
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+30h] [rbp-38h] BYREF

  if ( (unsigned int)dword_180013018 > 4 )
    tlgWriteTransfer_EventWriteTransfer((int)&dword_180013018, (int)&unk_180010440, 0, 0, 2u, &v6);
  v2 = IncomingTextMessageHandler::_RegisterForTextMessages(this);
  v4 = v2;
  if ( v2 >= 0 )
    return 0;
  Log_HREvent_3((unsigned int)v2, 1, v3, 134);
  return v4;
}

```

## disassembly

```asm
0x18000740c  push    rbx
0x18000740e  sub     rsp, 60h
0x180007412  mov     rax, cs:__security_cookie
0x180007419  xor     rax, rsp
0x18000741c  mov     [rsp+68h+var_18], rax
0x180007421  mov     eax, cs:dword_180013018
0x180007427  mov     rbx, rcx
0x18000742a  cmp     eax, 4
0x18000742d  jbe     short loc_18000745A
0x18000742f  lea     rax, [rsp+68h+var_38]
0x180007434  xor     r9d, r9d; int
0x180007437  mov     [rsp+68h+var_40], rax; PEVENT_DATA_DESCRIPTOR
0x18000743c  lea     rdx, unk_180010440; int
0x180007443  xor     r8d, r8d; int
0x180007446  mov     [rsp+68h+var_48], 2; ULONG
0x18000744e  lea     rcx, dword_180013018; int
0x180007455  call    _tlgWriteTransfer_EventWriteTransfer
0x18000745a  mov     rcx, rbx; this
0x18000745d  call    ?_RegisterForTextMessages@IncomingTextMessageHandler@@AEAAJXZ; IncomingTextMessageHandler::_RegisterForTextMessages(void)
0x180007462  mov     ebx, eax
0x180007464  test    eax, eax
0x180007466  jns     short loc_18000747E
0x180007468  mov     edx, 1
0x18000746d  mov     r9d, 86h
0x180007473  mov     ecx, eax
0x180007475  call    Log_HREvent_3
0x18000747a  mov     eax, ebx
0x18000747c  jmp     short loc_180007480
0x18000747e  xor     eax, eax
0x180007480  mov     rcx, [rsp+68h+var_18]
0x180007485  xor     rcx, rsp; StackCookie
0x180007488  call    __security_check_cookie
0x18000748d  add     rsp, 60h
0x180007491  pop     rbx
0x180007492  retn
```
