# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x1800075f8`
- end: `0x180007634`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this, int *, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180004ecc`
- `0x180004f38`
- `0x180006e7c`
- `0x180007740`

## callees

- `0x1800075f8`
- `0x1800076e8`

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
0x1800075f8  mov     [rsp+arg_0], rbx
0x1800075fd  mov     [rsp+arg_8], rsi
0x180007602  push    rdi
0x180007603  sub     rsp, 20h
0x180007607  mov     rsi, r8
0x18000760a  mov     rbx, rdx
0x18000760d  mov     rdi, rcx
0x180007610  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x180007615  test    rbx, rbx
0x180007618  jz      short loc_180007624
0x18000761a  mov     [rdi], rbx
0x18000761d  mov     [rdi+8], rsi
0x180007621  lock inc dword ptr [rbx]
0x180007624  mov     rbx, [rsp+28h+arg_0]
0x180007629  mov     rsi, [rsp+28h+arg_8]
0x18000762e  add     rsp, 20h
0x180007632  pop     rdi
0x180007633  retn
```
