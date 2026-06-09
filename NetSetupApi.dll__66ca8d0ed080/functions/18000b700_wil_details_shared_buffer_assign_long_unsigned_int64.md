# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x18000b700`
- end: `0x18000b73c`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *this, int *, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800047b8`
- `0x180009308`
- `0x180009374`
- `0x18000bb10`

## callees

- `0x18000b700`
- `0x18000bab4`

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
0x18000b700  mov     [rsp+arg_0], rbx
0x18000b705  mov     [rsp+arg_8], rsi
0x18000b70a  push    rdi
0x18000b70b  sub     rsp, 20h
0x18000b70f  mov     rsi, r8
0x18000b712  mov     rbx, rdx
0x18000b715  mov     rdi, rcx
0x18000b718  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x18000b71d  test    rbx, rbx
0x18000b720  jz      short loc_18000B72C
0x18000b722  mov     [rdi], rbx
0x18000b725  mov     [rdi+8], rsi
0x18000b729  lock inc dword ptr [rbx]
0x18000b72c  mov     rbx, [rsp+28h+arg_0]
0x18000b731  mov     rsi, [rsp+28h+arg_8]
0x18000b736  add     rsp, 20h
0x18000b73a  pop     rdi
0x18000b73b  retn
```
