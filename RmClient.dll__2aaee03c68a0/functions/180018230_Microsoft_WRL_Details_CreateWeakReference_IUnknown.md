# Microsoft::WRL::Details::CreateWeakReference(IUnknown *)

- ea: `0x180018230`
- end: `0x180018274`
- name: `?CreateWeakReference@Details@WRL@Microsoft@@YAPEAVWeakReferenceImpl@123@PEAUIUnknown@@@Z`
- size: `68`
- prototype: `struct Microsoft::WRL::Details::WeakReferenceImpl *__fastcall(Microsoft::WRL::Details *__hidden this, struct IUnknown *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800185d0`
- `0x180018670`
- `0x180018710`

## callees

- `0x180017ecc`
- `0x180018230`
- `0x180018c00`

## pseudocode

```c
struct Microsoft::WRL::Details::WeakReferenceImpl *__fastcall Microsoft::WRL::Details::CreateWeakReference(
        Microsoft::WRL::Details *this,
        struct IUnknown *a2)
{
  __int64 *v2; // rax
  __int64 v3; // rbx
  Microsoft::WRL::Details *v5; // [rsp+30h] [rbp+8h] BYREF
  __int64 v6; // [rsp+38h] [rbp+10h] BYREF

  v5 = this;
  v2 = Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(&v6, (__int64 *)&v5);
  v3 = *v2;
  *v2 = 0;
  if ( v6 )
  {
    v6 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release();
  }
  return (struct Microsoft::WRL::Details::WeakReferenceImpl *)v3;
}

```

## disassembly

```asm
0x180018230  mov     [rsp+arg_0], rcx
0x180018235  push    rbx
0x180018236  sub     rsp, 20h
0x18001823a  lea     rdx, [rsp+28h+arg_0]
0x18001823f  lea     rcx, [rsp+28h+arg_8]
0x180018244  call    ??$Make@VWeakReferenceImpl@Details@WRL@Microsoft@@AEAPEAUIUnknown@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@12@AEAPEAUIUnknown@@@Z; Microsoft::WRL::Details::Make<Microsoft::WRL::Details::WeakReferenceImpl,IUnknown * &>(IUnknown * &)
0x180018249  mov     rbx, [rax]
0x18001824c  mov     qword ptr [rax], 0
0x180018253  mov     rcx, [rsp+28h+arg_8]
0x180018258  test    rcx, rcx
0x18001825b  jz      short loc_18001826B
0x18001825d  mov     [rsp+28h+arg_8], 0
0x180018266  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x18001826b  mov     rax, rbx
0x18001826e  add     rsp, 20h
0x180018272  pop     rbx
0x180018273  retn
```
