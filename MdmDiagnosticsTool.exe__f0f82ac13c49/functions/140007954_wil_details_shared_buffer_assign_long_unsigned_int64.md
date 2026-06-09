# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x140007954`
- end: `0x140007990`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *this, int *, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140002fe0`
- `0x14000304c`
- `0x140006408`
- `0x140007fa0`

## callees

- `0x140007954`
- `0x140007f0c`

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
0x140007954  mov     [rsp+arg_0], rbx
0x140007959  mov     [rsp+arg_8], rsi
0x14000795e  push    rdi
0x14000795f  sub     rsp, 20h
0x140007963  mov     rsi, r8
0x140007966  mov     rbx, rdx
0x140007969  mov     rdi, rcx
0x14000796c  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x140007971  test    rbx, rbx
0x140007974  jz      short loc_140007980
0x140007976  mov     [rdi], rbx
0x140007979  mov     [rdi+8], rsi
0x14000797d  lock inc dword ptr [rbx]
0x140007980  mov     rbx, [rsp+28h+arg_0]
0x140007985  mov     rsi, [rsp+28h+arg_8]
0x14000798a  add     rsp, 20h
0x14000798e  pop     rdi
0x14000798f  retn
```
