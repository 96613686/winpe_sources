# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x18000d8cc`
- end: `0x18000d908`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this, int *, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000b600`
- `0x18000b66c`
- `0x18000cff8`
- `0x18000daa0`

## callees

- `0x18000d8cc`
- `0x18000da3c`

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
0x18000d8cc  mov     [rsp+arg_0], rbx
0x18000d8d1  mov     [rsp+arg_8], rsi
0x18000d8d6  push    rdi
0x18000d8d7  sub     rsp, 20h
0x18000d8db  mov     rsi, r8
0x18000d8de  mov     rbx, rdx
0x18000d8e1  mov     rdi, rcx
0x18000d8e4  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x18000d8e9  test    rbx, rbx
0x18000d8ec  jz      short loc_18000D8F8
0x18000d8ee  mov     [rdi], rbx
0x18000d8f1  mov     [rdi+8], rsi
0x18000d8f5  lock inc dword ptr [rbx]
0x18000d8f8  mov     rbx, [rsp+28h+arg_0]
0x18000d8fd  mov     rsi, [rsp+28h+arg_8]
0x18000d902  add     rsp, 20h
0x18000d906  pop     rdi
0x18000d907  retn
```
