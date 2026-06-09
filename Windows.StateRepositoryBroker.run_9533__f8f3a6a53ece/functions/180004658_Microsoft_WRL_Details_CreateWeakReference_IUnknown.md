# Microsoft::WRL::Details::CreateWeakReference(IUnknown *)

- ea: `0x180004658`
- end: `0x18000469c`
- name: `?CreateWeakReference@Details@WRL@Microsoft@@YAPEAVWeakReferenceImpl@123@PEAUIUnknown@@@Z`
- size: `68`
- prototype: `struct Microsoft::WRL::Details::WeakReferenceImpl *__fastcall(Microsoft::WRL::Details *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005090`

## callees

- `0x180003184`
- `0x180004658`
- `0x180005d70`

## pseudocode

```c
struct Microsoft::WRL::Details::WeakReferenceImpl *__fastcall Microsoft::WRL::Details::CreateWeakReference(
        Microsoft::WRL::Details *this,
        struct IUnknown *a2)
{
  __int64 *v2; // rax
  __int64 v3; // rbx
  __int64 v4; // rcx
  Microsoft::WRL::Details *v6; // [rsp+30h] [rbp+8h] BYREF
  __int64 v7; // [rsp+38h] [rbp+10h] BYREF

  v6 = this;
  v2 = Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(&v7, (__int64 *)&v6);
  v3 = *v2;
  *v2 = 0;
  v4 = v7;
  if ( v7 )
  {
    v7 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(v4);
  }
  return (struct Microsoft::WRL::Details::WeakReferenceImpl *)v3;
}

```

## disassembly

```asm
0x180004658  mov     [rsp+arg_0], rcx
0x18000465d  push    rbx
0x18000465e  sub     rsp, 20h
0x180004662  lea     rdx, [rsp+28h+arg_0]
0x180004667  lea     rcx, [rsp+28h+arg_8]
0x18000466c  call    ??$Make@VWeakReferenceImpl@Details@WRL@Microsoft@@AEAPEAUIUnknown@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@12@AEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(IUnknown * &)
0x180004671  mov     rbx, [rax]
0x180004674  mov     qword ptr [rax], 0
0x18000467b  mov     rcx, [rsp+28h+arg_8]
0x180004680  test    rcx, rcx
0x180004683  jz      short loc_180004693
0x180004685  mov     [rsp+28h+arg_8], 0
0x18000468e  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x180004693  mov     rax, rbx
0x180004696  add     rsp, 20h
0x18000469a  pop     rbx
0x18000469b  retn
```
