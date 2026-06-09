# TextMessageTransport::_Initialize(ITransportTaskScheduler *,ITransportTaskCallback *)

- ea: `0x180006df0`
- end: `0x180006fd5`
- name: `?_Initialize@TextMessageTransport@@AEAAJPEAUITransportTaskScheduler@@PEAUITransportTaskCallback@@@Z`
- size: `485`
- prototype: `__int64 __fastcall(TextMessageTransport *this, struct ITransportTaskScheduler *, struct ITransportTaskCallback *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180004c48`

## callees

- `0x180001730`
- `0x180006be8`
- `0x180006df0`
- `0x180007248`
- `0x18000749c`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall TextMessageTransport::_Initialize(
        TextMessageTransport *this,
        struct ITransportTaskScheduler *a2,
        struct ITransportTaskCallback *a3)
{
  char *v6; // rax
  __int64 v7; // r8
  IncomingTextMessageHandler *v8; // rbx
  struct ATL::CAtlModule *v9; // rcx
  unsigned int v10; // ebp
  void (__fastcall **v11)(IncomingTextMessageHandler *); // rax
  __int64 v12; // r8
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v16; // r8

  v6 = (char *)operator new(0x30u);
  v8 = (IncomingTextMessageHandler *)v6;
  if ( !v6 )
  {
    v10 = -2147024882;
    goto LABEL_20;
  }
  *(_QWORD *)(v6 + 12) = 0;
  *((_DWORD *)v6 + 5) = 0;
  v9 = ATL::_pAtlModule;
  *((_DWORD *)v6 + 2) = 0;
  *((_QWORD *)v6 + 3) = 0;
  *((_QWORD *)v6 + 4) = 0;
  *((_QWORD *)v6 + 5) = 0;
  *(_QWORD *)v6 = &ATL::CComObject<IncomingTextMessageHandler>::`vftable';
  (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)v9 + 8LL))(v9);
  (**(void (__fastcall ***)(IncomingTextMessageHandler *))v8)(v8);
  v10 = IncomingTextMessageHandler::_Initialize(v8, a2, a3);
  v11 = *(void (__fastcall ***)(IncomingTextMessageHandler *))v8;
  if ( (v10 & 0x80000000) != 0 )
  {
    v11[1](v8);
LABEL_20:
    Log_HREvent_3(v10, 1, v7, 21);
    Log_HREvent_2(v10, 1, v16, 35);
    return v10;
  }
  (*v11)(v8);
  (*(void (__fastcall **)(IncomingTextMessageHandler *))(*(_QWORD *)v8 + 8LL))(v8);
  IncomingTextMessageHandler::sm_incomingTextMessageHandler = v8;
  (**(void (__fastcall ***)(IncomingTextMessageHandler *))v8)(v8);
  (**(void (__fastcall ***)(IncomingTextMessageHandler *))v8)(v8);
  (*(void (__fastcall **)(IncomingTextMessageHandler *))(*(_QWORD *)v8 + 8LL))(v8);
  if ( this == (TextMessageTransport *)-24LL )
  {
    Log_HREvent_2(2147500035LL, 1, v12, 37);
    (*(void (__fastcall **)(IncomingTextMessageHandler *))(*(_QWORD *)v8 + 8LL))(v8);
    return 2147500035LL;
  }
  else
  {
    *((_QWORD *)this + 3) = v8;
    (**(void (__fastcall ***)(IncomingTextMessageHandler *))v8)(v8);
    if ( *((struct ITransportTaskScheduler **)this + 4) != a2 )
    {
      if ( a2 )
        (*(void (__fastcall **)(struct ITransportTaskScheduler *))(*(_QWORD *)a2 + 8LL))(a2);
      v13 = *((_QWORD *)this + 4);
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      *((_QWORD *)this + 4) = a2;
    }
    if ( *((struct ITransportTaskCallback **)this + 5) != a3 )
    {
      if ( a3 )
        (*(void (__fastcall **)(struct ITransportTaskCallback *))(*(_QWORD *)a3 + 8LL))(a3);
      v14 = *((_QWORD *)this + 5);
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      *((_QWORD *)this + 5) = a3;
    }
    (*(void (__fastcall **)(IncomingTextMessageHandler *))(*(_QWORD *)v8 + 8LL))(v8);
    return 0;
  }
}

```

## disassembly

```asm
0x180006df0  push    rbx
0x180006df2  push    rbp
0x180006df3  push    rsi
0x180006df4  push    rdi
0x180006df5  push    r14
0x180006df7  sub     rsp, 30h
0x180006dfb  mov     rdi, rcx
0x180006dfe  mov     rsi, r8
0x180006e01  mov     ecx, 30h ; '0'; Size
0x180006e06  mov     r14, rdx
0x180006e09  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006e0e  mov     rbx, rax
0x180006e11  test    rax, rax
0x180006e14  jz      loc_180006FA3
0x180006e1a  mov     qword ptr [rax+0Ch], 0
0x180006e22  mov     dword ptr [rax+14h], 0
0x180006e29  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180006e30  mov     dword ptr [rax+8], 0
0x180006e37  mov     qword ptr [rax+18h], 0
0x180006e3f  mov     qword ptr [rax+20h], 0
0x180006e47  mov     qword ptr [rax+28h], 0
0x180006e4f  lea     rax, ??_7?$CComObject@VIncomingTextMessageHandler@@@ATL@@6B@; const ATL::CComObject<IncomingTextMessageHandler>::`vftable'
0x180006e56  mov     [rbx], rax
0x180006e59  mov     rax, [rcx]
0x180006e5c  mov     rax, [rax+8]
0x180006e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e65  mov     rax, [rbx]
0x180006e68  mov     rcx, rbx
0x180006e6b  mov     rax, [rax]
0x180006e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e73  mov     r8, rsi; struct ITransportTaskCallback *
0x180006e76  mov     rdx, r14; struct ITransportTaskScheduler *
0x180006e79  mov     rcx, rbx; this
0x180006e7c  call    ?_Initialize@IncomingTextMessageHandler@@AEAAJPEAUITransportTaskScheduler@@PEAUITransportTaskCallback@@@Z; IncomingTextMessageHandler::_Initialize(ITransportTaskScheduler *,ITransportTaskCallback *)
0x180006e81  mov     ebp, eax
0x180006e83  test    eax, eax
0x180006e85  mov     rax, [rbx]
0x180006e88  mov     rcx, rbx
0x180006e8b  jns     short loc_180006E9B
0x180006e8d  mov     rax, [rax+8]
0x180006e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e96  jmp     loc_180006FA8
0x180006e9b  mov     rax, [rax]
0x180006e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ea3  mov     rax, [rbx]
0x180006ea6  mov     rcx, rbx
0x180006ea9  mov     rax, [rax+8]
0x180006ead  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006eb2  mov     cs:?sm_incomingTextMessageHandler@IncomingTextMessageHandler@@0V?$CComPtr@VIncomingTextMessageHandler@@@ATL@@A, rbx; ATL::CComPtr<IncomingTextMessageHandler> IncomingTextMessageHandler::sm_incomingTextMessageHandler
0x180006eb9  mov     rcx, rbx
0x180006ebc  mov     rax, [rbx]
0x180006ebf  mov     rax, [rax]
0x180006ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ec7  mov     rax, [rbx]
0x180006eca  mov     rcx, rbx
0x180006ecd  mov     rax, [rax]
0x180006ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ed5  mov     rax, [rbx]
0x180006ed8  mov     rcx, rbx
0x180006edb  mov     rax, [rax+8]
0x180006edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ee4  lea     rax, [rdi+18h]
0x180006ee8  test    rax, rax
0x180006eeb  jz      loc_180006F7B
0x180006ef1  mov     [rax], rbx
0x180006ef4  mov     rcx, rbx
0x180006ef7  mov     rax, [rbx]
0x180006efa  mov     rax, [rax]
0x180006efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f02  cmp     [rdi+20h], r14
0x180006f06  jz      short loc_180006F35
0x180006f08  test    r14, r14
0x180006f0b  jz      short loc_180006F1C
0x180006f0d  mov     rax, [r14]
0x180006f10  mov     rcx, r14
0x180006f13  mov     rax, [rax+8]
0x180006f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f1c  mov     rcx, [rdi+20h]
0x180006f20  test    rcx, rcx
0x180006f23  jz      short loc_180006F31
0x180006f25  mov     rax, [rcx]
0x180006f28  mov     rax, [rax+10h]
0x180006f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f31  mov     [rdi+20h], r14
0x180006f35  cmp     [rdi+28h], rsi
0x180006f39  jz      short loc_180006F68
0x180006f3b  test    rsi, rsi
0x180006f3e  jz      short loc_180006F4F
0x180006f40  mov     rax, [rsi]
0x180006f43  mov     rcx, rsi
0x180006f46  mov     rax, [rax+8]
0x180006f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f4f  mov     rcx, [rdi+28h]
0x180006f53  test    rcx, rcx
0x180006f56  jz      short loc_180006F64
0x180006f58  mov     rax, [rcx]
0x180006f5b  mov     rax, [rax+10h]
0x180006f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f64  mov     [rdi+28h], rsi
0x180006f68  mov     rax, [rbx]
0x180006f6b  mov     rcx, rbx
0x180006f6e  mov     rax, [rax+8]
0x180006f72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f77  xor     eax, eax
0x180006f79  jmp     short loc_180006FCA
0x180006f7b  mov     edx, 1
0x180006f80  mov     edi, 80004003h
0x180006f85  mov     ecx, edi
0x180006f87  lea     r9d, [rdx+24h]
0x180006f8b  call    Log_HREvent_2
0x180006f90  mov     rcx, [rbx]
0x180006f93  mov     rax, [rcx+8]
0x180006f97  mov     rcx, rbx
0x180006f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f9f  mov     eax, edi
0x180006fa1  jmp     short loc_180006FCA
0x180006fa3  mov     ebp, 8007000Eh
0x180006fa8  mov     edx, 1
0x180006fad  mov     ecx, ebp
0x180006faf  lea     r9d, [rdx+14h]
0x180006fb3  call    Log_HREvent_3
0x180006fb8  mov     edx, 1
0x180006fbd  mov     ecx, ebp
0x180006fbf  lea     r9d, [rdx+22h]
0x180006fc3  call    Log_HREvent_2
0x180006fc8  mov     eax, ebp
0x180006fca  add     rsp, 30h
0x180006fce  pop     r14
0x180006fd0  pop     rdi
0x180006fd1  pop     rsi
0x180006fd2  pop     rbp
0x180006fd3  pop     rbx
0x180006fd4  retn
```
