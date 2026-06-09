# Microsoft::WRL::ComPtr<DefaultHumanProvider>::~ComPtr<DefaultHumanProvider>(void)

- ea: `0x18000a67c`
- end: `0x18000a69c`
- name: `??1?$ComPtr@VDefaultHumanProvider@@@WRL@Microsoft@@QEAA@XZ`
- size: `32`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f79b`

## callees

- `0x18000a67c`
- `0x18000b2c0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ComPtr<DefaultHumanProvider>::~ComPtr<DefaultHumanProvider>(__int64 *a1)
{
  __int64 result; // rax

  result = *a1;
  if ( *a1 )
  {
    *a1 = 0;
    return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHrtfAnthropometricsProvider>::Release(result);
  }
  return result;
}

```

## disassembly

```asm
0x18000a67c  sub     rsp, 28h
0x18000a680  mov     rax, [rcx]
0x18000a683  test    rax, rax
0x18000a686  jz      short loc_18000A697
0x18000a688  mov     qword ptr [rcx], 0
0x18000a68f  mov     rcx, rax
0x18000a692  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIHrtfAnthropometricsProvider@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHrtfAnthropometricsProvider>::Release(void)
0x18000a697  add     rsp, 28h
0x18000a69b  retn
```
