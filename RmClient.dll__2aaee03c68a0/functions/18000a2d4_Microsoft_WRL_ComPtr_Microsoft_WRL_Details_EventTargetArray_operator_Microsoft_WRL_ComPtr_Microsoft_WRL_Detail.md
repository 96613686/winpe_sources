# Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray> const &)

- ea: `0x18000a2d4`
- end: `0x18000a30f`
- name: `??4?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z`
- size: `59`
- prototype: `__int64 *__fastcall(__int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180017b94`

## callees

- `0x18000a2d4`
- `0x18000a640`
- `0x18000a7ec`

## pseudocode

```c
__int64 *__fastcall Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::operator=(
        __int64 *a1,
        __int64 *a2)
{
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // [rsp+30h] [rbp+8h] BYREF

  if ( *a1 != *a2 )
  {
    v6 = *a2;
    Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::InternalAddRef(&v6);
    v4 = *a1;
    *a1 = v5;
    if ( v4 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release();
  }
  return a1;
}

```

## disassembly

```asm
0x18000a2d4  push    rbx
0x18000a2d6  sub     rsp, 20h
0x18000a2da  mov     r8, [rdx]
0x18000a2dd  mov     rbx, rcx
0x18000a2e0  cmp     [rcx], r8
0x18000a2e3  jnz     short loc_18000A2EE
0x18000a2e5  mov     rax, rbx
0x18000a2e8  add     rsp, 20h
0x18000a2ec  pop     rbx
0x18000a2ed  retn
0x18000a2ee  lea     rcx, [rsp+28h+arg_0]
0x18000a2f3  mov     [rsp+28h+arg_0], r8
0x18000a2f8  call    ?InternalAddRef@?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::InternalAddRef(void)
0x18000a2fd  mov     rcx, [rbx]
0x18000a300  mov     [rbx], r8
0x18000a303  test    rcx, rcx
0x18000a306  jz      short loc_18000A2E5
0x18000a308  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000a30d  jmp     short loc_18000A2E5
```
