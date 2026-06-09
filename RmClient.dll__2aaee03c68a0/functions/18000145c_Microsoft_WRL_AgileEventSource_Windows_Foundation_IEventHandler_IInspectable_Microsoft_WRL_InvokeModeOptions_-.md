# Microsoft::WRL::AgileEventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Add(Windows::Foundation::IEventHandler<IInspectable *> *,EventRegistrationToken *)

- ea: `0x18000145c`
- end: `0x1800014f9`
- name: `?Add@?$AgileEventSource@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAU?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@PEAUEventRegistrationToken@@@Z`
- size: `157`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001420`
- `0x180019070`

## callees

- `0x18000145c`
- `0x180001500`
- `0x18000166c`
- `0x1800018c4`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::AgileEventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::Add(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  int v6; // eax
  __int64 v7; // rdi
  unsigned int v8; // ebx
  __int64 v10; // [rsp+48h] [rbp+10h] BYREF

  if ( !a2 )
    return 2147942487LL;
  v10 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v10);
  v6 = Microsoft::WRL::Details::CreateAgileHelper<Windows::Foundation::IEventHandler<IInspectable *>>(a2, &v10);
  v7 = v10;
  v8 = v6;
  if ( v6 >= 0 )
  {
    if ( v10 )
      v8 = Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(
             a1,
             v10,
             *(_QWORD *)(*(_QWORD *)a2 + 24LL),
             a3);
    else
      v8 = -2147024809;
  }
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  return v8;
}

```

## disassembly

```asm
0x18000145c  mov     rax, rsp
0x18000145f  mov     [rax+8], rbx
0x180001463  mov     [rax+18h], rbp
0x180001467  push    rsi
0x180001468  push    rdi
0x180001469  push    r14
0x18000146b  sub     rsp, 20h
0x18000146f  mov     rbp, r8
0x180001472  mov     rsi, rdx
0x180001475  mov     r14, rcx
0x180001478  test    rdx, rdx
0x18000147b  jz      short loc_1800014EB
0x18000147d  lea     rcx, [rax+10h]
0x180001481  mov     qword ptr [rax+10h], 0
0x180001489  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000148e  lea     rdx, [rsp+38h+arg_8]
0x180001493  mov     rcx, rsi
0x180001496  call    ??$CreateAgileHelper@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@@Details@WRL@Microsoft@@YAJPEAU?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@PEAPEAU345@@Z; Microsoft::WRL::Details::CreateAgileHelper<Windows::Foundation::IEventHandler<IInspectable *>>(Windows::Foundation::IEventHandler<IInspectable *> *,Windows::Foundation::IEventHandler<IInspectable *> * *)
0x18000149b  mov     rdi, [rsp+38h+arg_8]
0x1800014a0  mov     ebx, eax
0x1800014a2  test    eax, eax
0x1800014a4  js      short loc_1800014C2
0x1800014a6  test    rdi, rdi
0x1800014a9  jz      short loc_1800014F2
0x1800014ab  mov     r8, [rsi]
0x1800014ae  mov     r9, rbp
0x1800014b1  mov     rdx, rdi
0x1800014b4  mov     rcx, r14
0x1800014b7  mov     r8, [r8+18h]
0x1800014bb  call    ?AddInternal@?$EventSource@U?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@AEAAJPEAU?$IEventHandler@PEAUIInspectable@@@Foundation@Windows@@PEAXPEAUEventRegistrationToken@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::IEventHandler<IInspectable *>,Microsoft::WRL::InvokeModeOptions<-2>>::AddInternal(Windows::Foundation::IEventHandler<IInspectable *> *,void *,EventRegistrationToken *)
0x1800014c0  mov     ebx, eax
0x1800014c2  test    rdi, rdi
0x1800014c5  jz      short loc_1800014D6
0x1800014c7  mov     rax, [rdi]
0x1800014ca  mov     rcx, rdi
0x1800014cd  mov     rax, [rax+10h]
0x1800014d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800014d6  mov     eax, ebx
0x1800014d8  mov     rbx, [rsp+38h+arg_0]
0x1800014dd  mov     rbp, [rsp+38h+arg_10]
0x1800014e2  add     rsp, 20h
0x1800014e6  pop     r14
0x1800014e8  pop     rdi
0x1800014e9  pop     rsi
0x1800014ea  retn
0x1800014eb  mov     eax, 80070057h
0x1800014f0  jmp     short loc_1800014D8
0x1800014f2  mov     ebx, 80070057h
0x1800014f7  jmp     short loc_1800014C2
```
