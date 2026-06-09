# Microsoft::WRL::ComPtr<Microsoft::WRL::Details::WeakReferenceImpl>::Attach(Microsoft::WRL::Details::WeakReferenceImpl *)

- ea: `0x18000d344`
- end: `0x18000d380`
- name: `?Attach@?$ComPtr@VWeakReferenceImpl@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAXPEAVWeakReferenceImpl@Details@23@@Z`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ba4c`

## callees

- `0x18000d344`
- `0x180010760`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<Microsoft::WRL::Details::WeakReferenceImpl>::Attach(_QWORD *a1, __int64 a2)
{
  _QWORD *result; // rax

  if ( *a1 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(*a1);
  result = a1;
  *a1 = a2;
  return result;
}

```

## disassembly

```asm
0x18000d344  mov     [rsp+arg_8], rdx
0x18000d349  mov     [rsp+arg_0], rcx
0x18000d34e  sub     rsp, 38h
0x18000d352  mov     rax, [rsp+38h+arg_0]
0x18000d357  cmp     qword ptr [rax], 0
0x18000d35b  jz      short loc_18000D36E
0x18000d35d  mov     rax, [rsp+38h+arg_0]
0x18000d362  mov     rcx, [rax]
0x18000d365  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)
0x18000d36a  mov     [rsp+38h+var_18], eax
0x18000d36e  mov     rax, [rsp+38h+arg_0]
0x18000d373  mov     rcx, [rsp+38h+arg_8]
0x18000d378  mov     [rax], rcx
0x18000d37b  add     rsp, 38h
0x18000d37f  retn
```
