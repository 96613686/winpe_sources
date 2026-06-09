# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x140005bec`
- end: `0x140005c28`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *this, int *, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140003030`
- `0x14000309c`
- `0x140004f18`
- `0x140006000`

## callees

- `0x140005bec`
- `0x140005fa8`

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
0x140005bec  mov     [rsp+arg_0], rbx
0x140005bf1  mov     [rsp+arg_8], rsi
0x140005bf6  push    rdi
0x140005bf7  sub     rsp, 20h
0x140005bfb  mov     rsi, r8
0x140005bfe  mov     rbx, rdx
0x140005c01  mov     rdi, rcx
0x140005c04  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x140005c09  test    rbx, rbx
0x140005c0c  jz      short loc_140005C18
0x140005c0e  mov     [rdi], rbx
0x140005c11  mov     [rdi+8], rsi
0x140005c15  lock inc dword ptr [rbx]
0x140005c18  mov     rbx, [rsp+28h+arg_0]
0x140005c1d  mov     rsi, [rsp+28h+arg_8]
0x140005c22  add     rsp, 20h
0x140005c26  pop     rdi
0x140005c27  retn
```
