# Microsoft::WRL::Details::CreateWeakReference(IUnknown *)

- ea: `0x18000d950`
- end: `0x18000d990`
- name: `?CreateWeakReference@Details@WRL@Microsoft@@YAPEAVWeakReferenceImpl@123@PEAUIUnknown@@@Z`
- size: `64`
- prototype: `struct Microsoft::WRL::Details::WeakReferenceImpl *__fastcall(Microsoft::WRL::Details *__hidden this, struct IUnknown *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000e6d0`
- `0x18000e890`

## callees

- `0x18000ba4c`
- `0x18000c870`
- `0x18000dac0`

## pseudocode

```c
struct Microsoft::WRL::Details::WeakReferenceImpl *__fastcall Microsoft::WRL::Details::CreateWeakReference(
        Microsoft::WRL::Details *this,
        struct IUnknown *a2)
{
  _QWORD *v3; // [rsp+20h] [rbp-28h]
  __int64 v4; // [rsp+28h] [rbp-20h] BYREF
  __int64 v5; // [rsp+30h] [rbp-18h]
  Microsoft::WRL::Details *v6; // [rsp+50h] [rbp+8h] BYREF

  v6 = this;
  v3 = Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(&v4, (__int64)&v6);
  v5 = Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Detach(v3);
  Microsoft::WRL::ComPtr<Microsoft::WRL::Details::WeakReferenceImpl>::~ComPtr<Microsoft::WRL::Details::WeakReferenceImpl>(&v4);
  return (struct Microsoft::WRL::Details::WeakReferenceImpl *)v5;
}

```

## disassembly

```asm
0x18000d950  mov     [rsp+arg_0], rcx
0x18000d955  sub     rsp, 48h
0x18000d959  lea     rdx, [rsp+48h+arg_0]
0x18000d95e  lea     rcx, [rsp+48h+var_20]
0x18000d963  call    ??$Make@VWeakReferenceImpl@Details@WRL@Microsoft@@AEAPEAUIUnknown@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@12@AEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(IUnknown * &)
0x18000d968  mov     [rsp+48h+var_28], rax
0x18000d96d  mov     rcx, [rsp+48h+var_28]
0x18000d972  call    ?Detach@?$ComPtr@V?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@@WRL@Microsoft@@QEAAPEAV?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@XZ; Microsoft::WRL::ComPtr<SimpleClassFactoryWithAccessControl<DockingInputManager>>::Detach(void)
0x18000d977  mov     [rsp+48h+var_18], rax
0x18000d97c  lea     rcx, [rsp+48h+var_20]
0x18000d981  call    ??1?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::WeakReferenceImpl>::~ComPtr<Microsoft::WRL::Details::WeakReferenceImpl>(void)
0x18000d986  mov     rax, [rsp+48h+var_18]
0x18000d98b  add     rsp, 48h
0x18000d98f  retn
```
