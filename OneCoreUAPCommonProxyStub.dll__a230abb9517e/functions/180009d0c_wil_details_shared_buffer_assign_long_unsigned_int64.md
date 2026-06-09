# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x180009d0c`
- end: `0x180009d48`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this, int *, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007084`
- `0x1800070f0`
- `0x180009378`
- `0x180009f40`

## callees

- `0x180009d0c`
- `0x180009ee8`

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
0x180009d0c  mov     [rsp+arg_0], rbx
0x180009d11  mov     [rsp+arg_8], rsi
0x180009d16  push    rdi
0x180009d17  sub     rsp, 20h
0x180009d1b  mov     rsi, r8
0x180009d1e  mov     rbx, rdx
0x180009d21  mov     rdi, rcx
0x180009d24  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x180009d29  test    rbx, rbx
0x180009d2c  jz      short loc_180009D38
0x180009d2e  mov     [rdi], rbx
0x180009d31  mov     [rdi+8], rsi
0x180009d35  lock inc dword ptr [rbx]
0x180009d38  mov     rbx, [rsp+28h+arg_0]
0x180009d3d  mov     rsi, [rsp+28h+arg_8]
0x180009d42  add     rsp, 20h
0x180009d46  pop     rdi
0x180009d47  retn
```
