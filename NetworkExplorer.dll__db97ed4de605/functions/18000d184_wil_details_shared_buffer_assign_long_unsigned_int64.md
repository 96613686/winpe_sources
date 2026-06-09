# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x18000d184`
- end: `0x18000d1c0`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this, int *, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800088a8`
- `0x180008914`
- `0x18000b508`
- `0x18000d980`

## callees

- `0x18000d184`
- `0x18000d64c`

## pseudocode

```c
void __fastcall wil::details::shared_buffer::assign(wil::details::shared_buffer *this, int *a2, __int64 a3)
{
  wil::details::shared_buffer::reset(this);
  if ( a2 )
  {
    *(_QWORD *)this = a2;
    *((_QWORD *)this + 1) = a3;
    _InterlockedIncrement(a2);
  }
}

```

## disassembly

```asm
0x18000d184  mov     [rsp+arg_0], rbx
0x18000d189  mov     [rsp+arg_8], rsi
0x18000d18e  push    rdi
0x18000d18f  sub     rsp, 20h
0x18000d193  mov     rsi, r8
0x18000d196  mov     rbx, rdx
0x18000d199  mov     rdi, rcx
0x18000d19c  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x18000d1a1  test    rbx, rbx
0x18000d1a4  jz      short loc_18000D1B0
0x18000d1a6  mov     [rdi], rbx
0x18000d1a9  mov     [rdi+8], rsi
0x18000d1ad  lock inc dword ptr [rbx]
0x18000d1b0  mov     rbx, [rsp+28h+arg_0]
0x18000d1b5  mov     rsi, [rsp+28h+arg_8]
0x18000d1ba  add     rsp, 20h
0x18000d1be  pop     rdi
0x18000d1bf  retn
```
