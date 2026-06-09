# ReceiveTextMessageTask::_Initialize(Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails *,ITransportTaskCallback *)

- ea: `0x180008d68`
- end: `0x180008e4c`
- name: `?_Initialize@ReceiveTextMessageTask@@AEAAJPEAUISmsMessageReceivedTriggerDetails@Sms@Devices@Windows@@PEAUITransportTaskCallback@@@Z`
- size: `228`
- prototype: `__int64 __fastcall(ReceiveTextMessageTask *__hidden this, struct Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails *, struct ITransportTaskCallback *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180007c48`

## callees

- `0x18000108c`
- `0x180008d68`
- `0x18000aa50`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ReceiveTextMessageTask::_Initialize(
        ReceiveTextMessageTask *this,
        struct Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails *a2,
        struct ITransportTaskCallback *a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+30h] [rbp-38h] BYREF

  if ( *((struct Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails **)this + 3) != a2 )
  {
    if ( a2 )
      (*(void (__fastcall **)(struct Windows::Devices::Sms::ISmsMessageReceivedTriggerDetails *))(*(_QWORD *)a2 + 8LL))(a2);
    v6 = *((_QWORD *)this + 3);
    *((_QWORD *)this + 3) = a2;
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  if ( *((struct ITransportTaskCallback **)this + 4) != a3 )
  {
    if ( a3 )
      (*(void (__fastcall **)(struct ITransportTaskCallback *))(*(_QWORD *)a3 + 8LL))(a3);
    v7 = *((_QWORD *)this + 4);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    *((_QWORD *)this + 4) = a3;
  }
  if ( (unsigned int)dword_180013018 > 4 )
    tlgWriteTransfer_EventWriteTransfer((int)&dword_180013018, (int)&word_1800107B2, 0, 0, 2u, &v9);
  return 0;
}

```

## disassembly

```asm
0x180008d68  mov     [rsp+arg_8], rbx
0x180008d6d  mov     [rsp+arg_18], rsi
0x180008d72  push    rdi
0x180008d73  sub     rsp, 60h
0x180008d77  mov     rax, cs:__security_cookie
0x180008d7e  xor     rax, rsp
0x180008d81  mov     [rsp+68h+var_18], rax
0x180008d86  mov     rdi, r8
0x180008d89  mov     rsi, rdx
0x180008d8c  mov     rbx, rcx
0x180008d8f  cmp     [rcx+18h], rdx
0x180008d93  jz      short loc_180008DC2
0x180008d95  test    rdx, rdx
0x180008d98  jz      short loc_180008DA9
0x180008d9a  mov     rax, [rdx]
0x180008d9d  mov     rcx, rdx
0x180008da0  mov     rax, [rax+8]
0x180008da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008da9  mov     rcx, [rbx+18h]
0x180008dad  mov     [rbx+18h], rsi
0x180008db1  test    rcx, rcx
0x180008db4  jz      short loc_180008DC2
0x180008db6  mov     rax, [rcx]
0x180008db9  mov     rax, [rax+10h]
0x180008dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dc2  cmp     [rbx+20h], rdi
0x180008dc6  jz      short loc_180008DF5
0x180008dc8  test    rdi, rdi
0x180008dcb  jz      short loc_180008DDC
0x180008dcd  mov     rax, [rdi]
0x180008dd0  mov     rcx, rdi
0x180008dd3  mov     rax, [rax+8]
0x180008dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ddc  mov     rcx, [rbx+20h]
0x180008de0  test    rcx, rcx
0x180008de3  jz      short loc_180008DF1
0x180008de5  mov     rax, [rcx]
0x180008de8  mov     rax, [rax+10h]
0x180008dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008df1  mov     [rbx+20h], rdi
0x180008df5  mov     eax, cs:dword_180013018
0x180008dfb  cmp     eax, 4
0x180008dfe  jbe     short loc_180008E2B
0x180008e00  lea     rax, [rsp+68h+var_38]
0x180008e05  xor     r9d, r9d; int
0x180008e08  mov     [rsp+68h+var_40], rax; PEVENT_DATA_DESCRIPTOR
0x180008e0d  lea     rdx, word_1800107B2; int
0x180008e14  xor     r8d, r8d; int
0x180008e17  mov     [rsp+68h+var_48], 2; ULONG
0x180008e1f  lea     rcx, dword_180013018; int
0x180008e26  call    _tlgWriteTransfer_EventWriteTransfer
0x180008e2b  xor     eax, eax
0x180008e2d  mov     rcx, [rsp+68h+var_18]
0x180008e32  xor     rcx, rsp; StackCookie
0x180008e35  call    __security_check_cookie
0x180008e3a  lea     r11, [rsp+68h+var_8]
0x180008e3f  mov     rbx, [r11+18h]
0x180008e43  mov     rsi, [r11+28h]
0x180008e47  mov     rsp, r11
0x180008e4a  pop     rdi
0x180008e4b  retn
```
