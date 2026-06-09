# Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::Details::EventTargetArray *)

- ea: `0x18000a318`
- end: `0x18000a351`
- name: `??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@PEAVEventTargetArray@Details@12@@Z`
- size: `57`
- prototype: `__int64 *__fastcall(__int64 *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017c34`
- `0x180017d78`

## callees

- `0x18000a318`
- `0x18000a640`
- `0x18000a7ec`

## pseudocode

```c
__int64 *__fastcall Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(
        __int64 *a1,
        __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // r8
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  if ( *a1 != a2 )
  {
    v6 = a2;
    Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::InternalAddRef(&v6);
    v3 = *a1;
    *a1 = v4;
    if ( v3 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
  }
  return a1;
}

```

## disassembly

```asm
0x18000a318  push    rbx
0x18000a31a  sub     rsp, 20h
0x18000a31e  mov     r8, rdx
0x18000a321  mov     rbx, rcx
0x18000a324  cmp     [rcx], rdx
0x18000a327  jz      short loc_18000A348
0x18000a329  lea     rcx, [rsp+28h+arg_0]
0x18000a32e  mov     [rsp+28h+arg_0], rdx
0x18000a333  call    ?InternalAddRef@?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::InternalAddRef(void)
0x18000a338  mov     rcx, [rbx]
0x18000a33b  mov     [rbx], r8
0x18000a33e  test    rcx, rcx
0x18000a341  jz      short loc_18000A348
0x18000a343  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000a348  mov     rax, rbx
0x18000a34b  add     rsp, 20h
0x18000a34f  pop     rbx
0x18000a350  retn
```
