# ReceiveTextMessageTask::_CompleteTask(void)

- ea: `0x1800080c8`
- end: `0x180008161`
- name: `?_CompleteTask@ReceiveTextMessageTask@@AEAAJXZ`
- size: `153`
- prototype: `__int64 __fastcall(ReceiveTextMessageTask *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007b4c`

## callees

- `0x18000108c`
- `0x1800044dc`
- `0x1800080c8`
- `0x18000aa50`
- `0x18000c010`

## string_xrefs

- `0x180008135`: `onecoreuap\net\messaging\desktoptransport\texttransport\lib\receivetextmessagetask.cpp`

## pseudocode

```c
__int64 __fastcall ReceiveTextMessageTask::_CompleteTask(ReceiveTextMessageTask *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+30h] [rbp-38h] BYREF

  if ( (unsigned int)dword_180013018 > 4 )
    tlgWriteTransfer_EventWriteTransfer((int)&dword_180013018, (int)&byte_180010585, 0, 0, 2u, &v5);
  v2 = (*(__int64 (__fastcall **)(_QWORD, ReceiveTextMessageTask *))(**((_QWORD **)this + 4) + 24LL))(
         *((_QWORD *)this + 4),
         this);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  Log_HREvent_0(
    (unsigned int)v2,
    1,
    "onecoreuap\\net\\messaging\\desktoptransport\\texttransport\\lib\\receivetextmessagetask.cpp");
  return v3;
}

```

## disassembly

```asm
0x1800080c8  push    rbx
0x1800080ca  sub     rsp, 60h
0x1800080ce  mov     rax, cs:__security_cookie
0x1800080d5  xor     rax, rsp
0x1800080d8  mov     [rsp+68h+var_18], rax
0x1800080dd  mov     eax, cs:dword_180013018
0x1800080e3  mov     rbx, rcx
0x1800080e6  cmp     eax, 4
0x1800080e9  jbe     short loc_180008116
0x1800080eb  lea     rax, [rsp+68h+var_38]
0x1800080f0  xor     r9d, r9d; int
0x1800080f3  mov     [rsp+68h+var_40], rax; PEVENT_DATA_DESCRIPTOR
0x1800080f8  lea     rdx, byte_180010585; int
0x1800080ff  xor     r8d, r8d; int
0x180008102  mov     [rsp+68h+var_48], 2; ULONG
0x18000810a  lea     rcx, dword_180013018; int
0x180008111  call    _tlgWriteTransfer_EventWriteTransfer
0x180008116  mov     rcx, [rbx+20h]
0x18000811a  mov     rdx, rbx
0x18000811d  mov     rax, [rcx]
0x180008120  mov     rax, [rax+18h]
0x180008124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008129  mov     ebx, eax
0x18000812b  test    eax, eax
0x18000812d  jns     short loc_18000814C
0x18000812f  mov     r9d, 13Fh
0x180008135  lea     r8, aOnecoreuapNetM_3; "onecoreuap\\net\\messaging\\desktoptran"...
0x18000813c  mov     edx, 1
0x180008141  mov     ecx, eax
0x180008143  call    Log_HREvent_0
0x180008148  mov     eax, ebx
0x18000814a  jmp     short loc_18000814E
0x18000814c  xor     eax, eax
0x18000814e  mov     rcx, [rsp+68h+var_18]
0x180008153  xor     rcx, rsp; StackCookie
0x180008156  call    __security_check_cookie
0x18000815b  add     rsp, 60h
0x18000815f  pop     rbx
0x180008160  retn
```
