# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x180006838`
- end: `0x180006874`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this, int *, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003da4`
- `0x180003e10`
- `0x18000629c`
- `0x1800069a0`

## callees

- `0x180006838`
- `0x18000693c`

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
0x180006838  mov     [rsp+arg_0], rbx
0x18000683d  mov     [rsp+arg_8], rsi
0x180006842  push    rdi
0x180006843  sub     rsp, 20h
0x180006847  mov     rsi, r8
0x18000684a  mov     rbx, rdx
0x18000684d  mov     rdi, rcx
0x180006850  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x180006855  test    rbx, rbx
0x180006858  jz      short loc_180006864
0x18000685a  mov     [rdi], rbx
0x18000685d  mov     [rdi+8], rsi
0x180006861  lock inc dword ptr [rbx]
0x180006864  mov     rbx, [rsp+28h+arg_0]
0x180006869  mov     rsi, [rsp+28h+arg_8]
0x18000686e  add     rsp, 20h
0x180006872  pop     rdi
0x180006873  retn
```
