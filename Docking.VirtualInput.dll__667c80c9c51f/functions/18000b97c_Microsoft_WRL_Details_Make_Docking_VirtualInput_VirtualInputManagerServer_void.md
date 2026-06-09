# Microsoft::WRL::Details::Make<Docking::VirtualInput::VirtualInputManagerServer,>(void)

- ea: `0x18000b97c`
- end: `0x18000ba46`
- name: `??$Make@VVirtualInputManagerServer@VirtualInput@Docking@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VVirtualInputManagerServer@VirtualInput@Docking@@@12@XZ`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180012850`

## callees

- `0x18000b97c`
- `0x18000bf4c`
- `0x18000c668`
- `0x18000c928`
- `0x18000ccf0`
- `0x18000d1f0`
- `0x18000d2a4`
- `0x18000daf0`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::Make<Docking::VirtualInput::VirtualInputManagerServer,>(_QWORD *a1)
{
  Docking::VirtualInput::VirtualInputManagerServer *v2; // [rsp+28h] [rbp-40h]
  __int64 v3; // [rsp+30h] [rbp-38h] BYREF
  void *v4; // [rsp+38h] [rbp-30h]
  __int64 v5; // [rsp+40h] [rbp-28h]
  __int64 v6; // [rsp+48h] [rbp-20h]
  _QWORD *v7; // [rsp+50h] [rbp-18h]

  v7 = Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(a1);
  Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(&v3);
  v4 = (void *)Microsoft::WRL::Details::MakeAllocator<Docking::VirtualInput::VirtualInputManagerServer>::Allocate(&v3);
  if ( v4 )
  {
    v2 = (Docking::VirtualInput::VirtualInputManagerServer *)Microsoft::WRL::Details::DontUseNewUseMake::operator new(
                                                               0x40u,
                                                               v4);
    if ( v2 )
    {
      memset(v2, 0, 0x40u);
      v5 = Docking::VirtualInput::VirtualInputManagerServer::VirtualInputManagerServer(v2);
    }
    else
    {
      v5 = 0;
    }
    v6 = v5;
    Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualInputManagerServer>::Attach(a1, v5);
    Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::Detach(&v3);
  }
  Microsoft::WRL::Details::MakeAllocator<DockingInputManager>::~MakeAllocator<DockingInputManager>(&v3);
  return a1;
}

```

## disassembly

```asm
0x18000b97c  mov     [rsp+arg_0], rcx
0x18000b981  push    rdi
0x18000b982  sub     rsp, 60h
0x18000b986  mov     [rsp+68h+var_48], 0
0x18000b98e  mov     rcx, [rsp+68h+arg_0]
0x18000b993  call    ??0?$ComPtr@VDockingInputManager@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(void)
0x18000b998  mov     [rsp+68h+var_18], rax
0x18000b99d  mov     eax, [rsp+68h+var_48]
0x18000b9a1  or      eax, 1
0x18000b9a4  mov     [rsp+68h+var_48], eax
0x18000b9a8  lea     rcx, [rsp+68h+var_38]
0x18000b9ad  call    ??0?$ComPtr@VDockingInputManager@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(void)
0x18000b9b2  lea     rcx, [rsp+68h+var_38]
0x18000b9b7  call    ?Allocate@?$MakeAllocator@VVirtualInputManagerServer@VirtualInput@Docking@@@Details@WRL@Microsoft@@QEAAPEAXXZ; Microsoft::WRL::Details::MakeAllocator<Docking::VirtualInput::VirtualInputManagerServer>::Allocate(void)
0x18000b9bc  mov     [rsp+68h+var_30], rax
0x18000b9c1  cmp     [rsp+68h+var_30], 0
0x18000b9c7  jz      short loc_18000BA31
0x18000b9c9  mov     rdx, [rsp+68h+var_30]; void *
0x18000b9ce  mov     ecx, 40h ; '@'; unsigned __int64
0x18000b9d3  call    ??2DontUseNewUseMake@Details@WRL@Microsoft@@SAPEAX_KPEAX@Z; Microsoft::WRL::Details::DontUseNewUseMake::operator new(unsigned __int64,void *)
0x18000b9d8  mov     [rsp+68h+var_40], rax
0x18000b9dd  cmp     [rsp+68h+var_40], 0
0x18000b9e3  jz      short loc_18000BA04
0x18000b9e5  mov     rdi, [rsp+68h+var_40]
0x18000b9ea  xor     eax, eax
0x18000b9ec  mov     ecx, 40h ; '@'
0x18000b9f1  rep stosb
0x18000b9f3  mov     rcx, [rsp+68h+var_40]; this
0x18000b9f8  call    ??0VirtualInputManagerServer@VirtualInput@Docking@@QEAA@XZ; Docking::VirtualInput::VirtualInputManagerServer::VirtualInputManagerServer(void)
0x18000b9fd  mov     [rsp+68h+var_28], rax
0x18000ba02  jmp     short loc_18000BA0D
0x18000ba04  mov     [rsp+68h+var_28], 0
0x18000ba0d  mov     rax, [rsp+68h+var_28]
0x18000ba12  mov     [rsp+68h+var_20], rax
0x18000ba17  mov     rdx, [rsp+68h+var_20]
0x18000ba1c  mov     rcx, [rsp+68h+arg_0]
0x18000ba21  call    ?Attach@?$ComPtr@VVirtualInputManagerServer@VirtualInput@Docking@@@WRL@Microsoft@@QEAAXPEAVVirtualInputManagerServer@VirtualInput@Docking@@@Z; Microsoft::WRL::ComPtr<Docking::VirtualInput::VirtualInputManagerServer>::Attach(Docking::VirtualInput::VirtualInputManagerServer *)
0x18000ba26  lea     rcx, [rsp+68h+var_38]
0x18000ba2b  call    ?Detach@?$MakeAllocator@VWeakReferenceImpl@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::Detach(void)
0x18000ba30  nop
0x18000ba31  lea     rcx, [rsp+68h+var_38]
0x18000ba36  call    ??1?$MakeAllocator@VDockingInputManager@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<DockingInputManager>::~MakeAllocator<DockingInputManager>(void)
0x18000ba3b  mov     rax, [rsp+68h+arg_0]
0x18000ba40  add     rsp, 60h
0x18000ba44  pop     rdi
0x18000ba45  retn
```
