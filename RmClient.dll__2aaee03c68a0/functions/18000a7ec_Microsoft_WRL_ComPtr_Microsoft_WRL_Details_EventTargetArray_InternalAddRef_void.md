# Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::InternalAddRef(void)

- ea: `0x18000a7ec`
- end: `0x18000a806`
- name: `?InternalAddRef@?$ComPtr@VEventTargetArray@Details@WRL@Microsoft@@@WRL@Microsoft@@IEBAXXZ`
- size: `26`
- prototype: `unsigned int __fastcall(__int64 *, volatile int *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a2d4`
- `0x18000a318`
- `0x18000f684`
- `0x180013594`

## callees

- `0x18000a7ec`
- `0x18000acd0`

## pseudocode

```c
unsigned int __fastcall Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::InternalAddRef(
        __int64 *a1,
        volatile int *a2)
{
  __int64 v2; // rcx
  unsigned int result; // eax

  v2 = *a1;
  if ( v2 )
    return Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(v2 + 12), a2);
  return result;
}

```

## disassembly

```asm
0x18000a7ec  sub     rsp, 28h
0x18000a7f0  mov     rcx, [rcx]
0x18000a7f3  test    rcx, rcx
0x18000a7f6  jz      short loc_18000A801
0x18000a7f8  add     rcx, 0Ch; this
0x18000a7fc  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x18000a801  add     rsp, 28h
0x18000a805  retn
```
