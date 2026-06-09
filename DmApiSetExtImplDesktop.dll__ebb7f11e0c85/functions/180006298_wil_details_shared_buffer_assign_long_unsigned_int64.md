# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x180006298`
- end: `0x1800062d5`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `61`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this, int *, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002cc8`
- `0x180002d3c`
- `0x180004fb8`
- `0x180006600`

## callees

- `0x180006298`
- `0x180006598`

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
0x180006298  mov     [rsp+arg_0], rbx
0x18000629d  mov     [rsp+arg_8], rsi
0x1800062a2  push    rdi
0x1800062a3  sub     rsp, 20h
0x1800062a7  mov     rsi, r8
0x1800062aa  mov     rbx, rdx
0x1800062ad  mov     rdi, rcx
0x1800062b0  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x1800062b5  test    rbx, rbx
0x1800062b8  jz      short loc_1800062C4
0x1800062ba  mov     [rdi], rbx
0x1800062bd  mov     [rdi+8], rsi
0x1800062c1  lock inc dword ptr [rbx]
0x1800062c4  mov     rbx, [rsp+28h+arg_0]
0x1800062c9  mov     rsi, [rsp+28h+arg_8]
0x1800062ce  add     rsp, 20h
0x1800062d2  pop     rdi
0x1800062d3  retn
```
