# kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)

- ea: `0x140003bd8`
- end: `0x140003c52`
- name: `??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z`
- size: `122`
- prototype: `volatile signed __int32 **__fastcall(volatile signed __int32 **, volatile signed __int32 **)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x140001f40`
- `0x140003c58`
- `0x1400044a0`
- `0x1400048a8`
- `0x140004ef0`
- `0x140006c08`
- `0x140006fe0`
- `0x1400073b8`
- `0x140009b58`
- `0x14000cf74`
- `0x14000e7f8`
- `0x14000ebd0`
- `0x140010270`
- `0x1400105d8`
- `0x1400115cc`
- `0x140011ec4`

## callees

- `0x140003bd8`
- `0x140015b30`

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
0x140003bd8  mov     [rsp+arg_0], rbx
0x140003bdd  mov     [rsp+arg_8], rsi
0x140003be2  push    rdi
0x140003be3  sub     rsp, 20h
0x140003be7  mov     rdi, [rdx]
0x140003bea  mov     rsi, rcx
0x140003bed  cmp     rdi, [rcx]
0x140003bf0  jz      short loc_140003C3E
0x140003bf2  test    rdi, rdi
0x140003bf5  jz      short loc_140003BFB
0x140003bf7  lock inc dword ptr [rdi+8]
0x140003bfb  mov     rbx, [rcx]
0x140003bfe  test    rbx, rbx
0x140003c01  jz      short loc_140003C3B
0x140003c03  or      eax, 0FFFFFFFFh
0x140003c06  lock xadd [rbx+8], eax
0x140003c0b  cmp     eax, 1
0x140003c0e  jnz     short loc_140003C3B
0x140003c10  mov     rax, [rbx]
0x140003c13  mov     rcx, rbx
0x140003c16  mov     rax, [rax+8]
0x140003c1a  call    _guard_dispatch_icall
0x140003c1f  or      eax, 0FFFFFFFFh
0x140003c22  lock xadd [rbx+0Ch], eax
0x140003c27  cmp     eax, 1
0x140003c2a  jnz     short loc_140003C3B
0x140003c2c  mov     rax, [rbx]
0x140003c2f  mov     rcx, rbx
0x140003c32  mov     rax, [rax+10h]
0x140003c36  call    _guard_dispatch_icall
0x140003c3b  mov     [rsi], rdi
0x140003c3e  mov     rbx, [rsp+28h+arg_0]
0x140003c43  mov     rax, rsi
0x140003c46  mov     rsi, [rsp+28h+arg_8]
0x140003c4b  add     rsp, 20h
0x140003c4f  pop     rdi
0x140003c50  retn
```
