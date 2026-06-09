# kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)

- ea: `0x180005430`
- end: `0x1800054aa`
- name: `??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z`
- size: `122`
- prototype: `volatile signed __int32 **__fastcall(volatile signed __int32 **, volatile signed __int32 **)`
- caller_count: `22`
- callee_count: `2`
- tags: ``

## callers

- `0x180001c98`
- `0x180001f78`
- `0x1800030f4`
- `0x1800048d8`
- `0x180004a90`
- `0x18000566c`
- `0x180007840`
- `0x180007b88`
- `0x180007e10`
- `0x180008048`
- `0x18000c694`
- `0x18000c768`
- `0x18000c8cc`
- `0x18000c9a8`
- `0x18000e960`
- `0x18000ef74`
- `0x180015828`
- `0x1800178ec`
- `0x180017c7c`
- `0x180018848`
- `0x180019624`
- `0x18001a79c`

## callees

- `0x180005430`
- `0x18001bb30`

## pseudocode

```c
volatile signed __int32 **__fastcall kernel_std::detail::shared_count::operator=(
        volatile signed __int32 **a1,
        volatile signed __int32 **a2)
{
  volatile signed __int32 *v2; // rdi
  volatile signed __int32 *v4; // rbx

  v2 = *a2;
  if ( *a2 != *a1 )
  {
    if ( v2 )
      _InterlockedIncrement(v2 + 2);
    v4 = *a1;
    if ( *a1 )
    {
      if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
        if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 16LL))(v4);
      }
    }
    *a1 = v2;
  }
  return a1;
}

```

## disassembly

```asm
0x180005430  mov     [rsp+arg_0], rbx
0x180005435  mov     [rsp+arg_8], rsi
0x18000543a  push    rdi
0x18000543b  sub     rsp, 20h
0x18000543f  mov     rdi, [rdx]
0x180005442  mov     rsi, rcx
0x180005445  cmp     rdi, [rcx]
0x180005448  jz      short loc_180005496
0x18000544a  test    rdi, rdi
0x18000544d  jz      short loc_180005453
0x18000544f  lock inc dword ptr [rdi+8]
0x180005453  mov     rbx, [rcx]
0x180005456  test    rbx, rbx
0x180005459  jz      short loc_180005493
0x18000545b  or      eax, 0FFFFFFFFh
0x18000545e  lock xadd [rbx+8], eax
0x180005463  cmp     eax, 1
0x180005466  jnz     short loc_180005493
0x180005468  mov     rax, [rbx]
0x18000546b  mov     rcx, rbx
0x18000546e  mov     rax, [rax+8]
0x180005472  call    _guard_dispatch_icall
0x180005477  or      eax, 0FFFFFFFFh
0x18000547a  lock xadd [rbx+0Ch], eax
0x18000547f  cmp     eax, 1
0x180005482  jnz     short loc_180005493
0x180005484  mov     rax, [rbx]
0x180005487  mov     rcx, rbx
0x18000548a  mov     rax, [rax+10h]
0x18000548e  call    _guard_dispatch_icall
0x180005493  mov     [rsi], rdi
0x180005496  mov     rbx, [rsp+28h+arg_0]
0x18000549b  mov     rax, rsi
0x18000549e  mov     rsi, [rsp+28h+arg_8]
0x1800054a3  add     rsp, 20h
0x1800054a7  pop     rdi
0x1800054a8  retn
```
