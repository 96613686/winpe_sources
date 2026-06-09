# IncomingTextMessageHandler::_Initialize(ITransportTaskScheduler *,ITransportTaskCallback *)

- ea: `0x18000749c`
- end: `0x18000758b`
- name: `?_Initialize@IncomingTextMessageHandler@@AEAAJPEAUITransportTaskScheduler@@PEAUITransportTaskCallback@@@Z`
- size: `239`
- prototype: `__int64 __fastcall(IncomingTextMessageHandler *__hidden this, struct ITransportTaskScheduler *, struct ITransportTaskCallback *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180006df0`

## callees

- `0x18000108c`
- `0x18000749c`
- `0x18000aa50`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall IncomingTextMessageHandler::_Initialize(
        IncomingTextMessageHandler *this,
        struct ITransportTaskScheduler *a2,
        struct ITransportTaskCallback *a3)
{
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v9; // [rsp+30h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v10; // [rsp+38h] [rbp-50h] BYREF
  __int64 *v11; // [rsp+58h] [rbp-30h]
  __int64 v12; // [rsp+60h] [rbp-28h]

  if ( *((struct ITransportTaskScheduler **)this + 3) != a2 )
  {
    if ( a2 )
      (*(void (__fastcall **)(struct ITransportTaskScheduler *))(*(_QWORD *)a2 + 8LL))(a2);
    v6 = *((_QWORD *)this + 3);
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    *((_QWORD *)this + 3) = a2;
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
  {
    v9 = 2048;
    v11 = &v9;
    v12 = 8;
    tlgWriteTransfer_EventWriteTransfer((int)&dword_180013018, (int)&word_18001053E, 0, 0, 3u, &v10);
  }
  return 0;
}

```

## disassembly

```asm
0x18000749c  push    rbx
0x18000749e  push    rsi
0x18000749f  push    rdi
0x1800074a0  sub     rsp, 70h
0x1800074a4  mov     rax, cs:__security_cookie
0x1800074ab  xor     rax, rsp
0x1800074ae  mov     [rsp+88h+var_20], rax
0x1800074b3  mov     rdi, r8
0x1800074b6  mov     rsi, rdx
0x1800074b9  mov     rbx, rcx
0x1800074bc  cmp     [rcx+18h], rdx
0x1800074c0  jz      short loc_1800074EF
0x1800074c2  test    rdx, rdx
0x1800074c5  jz      short loc_1800074D6
0x1800074c7  mov     rax, [rdx]
0x1800074ca  mov     rcx, rdx
0x1800074cd  mov     rax, [rax+8]
0x1800074d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074d6  mov     rcx, [rbx+18h]
0x1800074da  test    rcx, rcx
0x1800074dd  jz      short loc_1800074EB
0x1800074df  mov     rax, [rcx]
0x1800074e2  mov     rax, [rax+10h]
0x1800074e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074eb  mov     [rbx+18h], rsi
0x1800074ef  cmp     [rbx+20h], rdi
0x1800074f3  jz      short loc_180007522
0x1800074f5  test    rdi, rdi
0x1800074f8  jz      short loc_180007509
0x1800074fa  mov     rax, [rdi]
0x1800074fd  mov     rcx, rdi
0x180007500  mov     rax, [rax+8]
0x180007504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007509  mov     rcx, [rbx+20h]
0x18000750d  test    rcx, rcx
0x180007510  jz      short loc_18000751E
0x180007512  mov     rax, [rcx]
0x180007515  mov     rax, [rax+10h]
0x180007519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000751e  mov     [rbx+20h], rdi
0x180007522  mov     eax, cs:dword_180013018
0x180007528  cmp     eax, 4
0x18000752b  jbe     short loc_180007574
0x18000752d  lea     rax, [rsp+88h+var_58]
0x180007532  mov     [rsp+88h+var_58], 800h
0x18000753b  mov     [rsp+88h+var_30], rax
0x180007540  lea     rdx, word_18001053E; int
0x180007547  lea     rax, [rsp+88h+var_50]
0x18000754c  mov     [rsp+88h+var_28], 8
0x180007555  mov     [rsp+88h+var_60], rax; PEVENT_DATA_DESCRIPTOR
0x18000755a  lea     rcx, dword_180013018; int
0x180007561  xor     r9d, r9d; int
0x180007564  mov     [rsp+88h+var_68], 3; ULONG
0x18000756c  xor     r8d, r8d; int
0x18000756f  call    _tlgWriteTransfer_EventWriteTransfer
0x180007574  xor     eax, eax
0x180007576  mov     rcx, [rsp+88h+var_20]
0x18000757b  xor     rcx, rsp; StackCookie
0x18000757e  call    __security_check_cookie
0x180007583  add     rsp, 70h
0x180007587  pop     rdi
0x180007588  pop     rsi
0x180007589  pop     rbx
0x18000758a  retn
```
