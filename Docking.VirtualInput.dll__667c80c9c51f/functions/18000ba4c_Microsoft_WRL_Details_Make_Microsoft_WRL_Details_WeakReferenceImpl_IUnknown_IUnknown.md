# Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(IUnknown * &)

- ea: `0x18000ba4c`
- end: `0x18000bb22`
- name: `??$Make@VWeakReferenceImpl@Details@WRL@Microsoft@@AEAPEAUIUnknown@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@12@AEAPEAUIUnknown@@@Z`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000d950`

## callees

- `0x18000b810`
- `0x18000ba4c`
- `0x18000bf4c`
- `0x18000c730`
- `0x18000c928`
- `0x18000ccf0`
- `0x18000d268`
- `0x18000d344`
- `0x18000daf0`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(
        _QWORD *a1,
        __int64 a2)
{
  __int64 v3; // [rsp+28h] [rbp-40h] BYREF
  void *v4; // [rsp+30h] [rbp-38h]
  Microsoft::WRL::Details::WeakReferenceImpl *v5; // [rsp+38h] [rbp-30h]
  __int64 v6; // [rsp+40h] [rbp-28h]
  struct IUnknown *v7; // [rsp+48h] [rbp-20h]
  __int64 v8; // [rsp+50h] [rbp-18h]
  _QWORD *v9; // [rsp+58h] [rbp-10h]

  v9 = Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(a1);
  Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(&v3);
  v4 = (void *)Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::Allocate(&v3);
  if ( v4 )
  {
    v5 = (Microsoft::WRL::Details::WeakReferenceImpl *)Microsoft::WRL::Details::DontUseNewUseMake::operator new(
                                                         0x20u,
                                                         v4);
    if ( v5 )
    {
      v7 = *(struct IUnknown **)Microsoft::WRL::Details::Forward<std::nullptr_t>(a2);
      v6 = Microsoft::WRL::Details::WeakReferenceImpl::WeakReferenceImpl(v5, v7);
    }
    else
    {
      v6 = 0;
    }
    v8 = v6;
    Microsoft::WRL::ComPtr<Microsoft::WRL::Details::WeakReferenceImpl>::Attach(a1, v6);
    Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::Detach(&v3);
  }
  Microsoft::WRL::Details::MakeAllocator<DockingInputManager>::~MakeAllocator<DockingInputManager>(&v3);
  return a1;
}

```

## disassembly

```asm
0x18000ba4c  mov     [rsp+arg_8], rdx
0x18000ba51  mov     [rsp+arg_0], rcx
0x18000ba56  sub     rsp, 68h
0x18000ba5a  mov     [rsp+68h+var_48], 0
0x18000ba62  mov     rcx, [rsp+68h+arg_0]
0x18000ba67  call    ??0?$ComPtr@VDockingInputManager@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(void)
0x18000ba6c  mov     [rsp+68h+var_10], rax
0x18000ba71  mov     eax, [rsp+68h+var_48]
0x18000ba75  or      eax, 1
0x18000ba78  mov     [rsp+68h+var_48], eax
0x18000ba7c  lea     rcx, [rsp+68h+var_40]
0x18000ba81  call    ??0?$ComPtr@VDockingInputManager@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<DockingInputManager>::ComPtr<DockingInputManager>(void)
0x18000ba86  lea     rcx, [rsp+68h+var_40]
0x18000ba8b  call    ?Allocate@?$MakeAllocator@VWeakReferenceImpl@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAXXZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::Allocate(void)
0x18000ba90  mov     [rsp+68h+var_38], rax
0x18000ba95  cmp     [rsp+68h+var_38], 0
0x18000ba9b  jz      short loc_18000BB0E
0x18000ba9d  mov     rdx, [rsp+68h+var_38]; void *
0x18000baa2  mov     ecx, 20h ; ' '; unsigned __int64
0x18000baa7  call    ??2DontUseNewUseMake@Details@WRL@Microsoft@@SAPEAX_KPEAX@Z; Microsoft::WRL::Details::DontUseNewUseMake::operator new(unsigned __int64,void *)
0x18000baac  mov     [rsp+68h+var_30], rax
0x18000bab1  cmp     [rsp+68h+var_30], 0
0x18000bab7  jz      short loc_18000BAE1
0x18000bab9  mov     rcx, [rsp+68h+arg_8]
0x18000babe  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x18000bac3  mov     rax, [rax]
0x18000bac6  mov     [rsp+68h+var_20], rax
0x18000bacb  mov     rdx, [rsp+68h+var_20]; struct IUnknown *
0x18000bad0  mov     rcx, [rsp+68h+var_30]; this
0x18000bad5  call    ??0WeakReferenceImpl@Details@WRL@Microsoft@@QEAA@PEAUIUnknown@@@Z; Microsoft::WRL::Details::WeakReferenceImpl::WeakReferenceImpl(IUnknown *)
0x18000bada  mov     [rsp+68h+var_28], rax
0x18000badf  jmp     short loc_18000BAEA
0x18000bae1  mov     [rsp+68h+var_28], 0
0x18000baea  mov     rax, [rsp+68h+var_28]
0x18000baef  mov     [rsp+68h+var_18], rax
0x18000baf4  mov     rdx, [rsp+68h+var_18]
0x18000baf9  mov     rcx, [rsp+68h+arg_0]
0x18000bafe  call    ?Attach@?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAXPEAVWeakReferenceImpl@Details@23@@Z; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::WeakReferenceImpl>::Attach(Microsoft::WRL::Details::WeakReferenceImpl *)
0x18000bb03  lea     rcx, [rsp+68h+var_40]
0x18000bb08  call    ?Detach@?$MakeAllocator@VWeakReferenceImpl@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::Detach(void)
0x18000bb0d  nop
0x18000bb0e  lea     rcx, [rsp+68h+var_40]
0x18000bb13  call    ??1?$MakeAllocator@VDockingInputManager@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<DockingInputManager>::~MakeAllocator<DockingInputManager>(void)
0x18000bb18  mov     rax, [rsp+68h+arg_0]
0x18000bb1d  add     rsp, 68h
0x18000bb21  retn
```
