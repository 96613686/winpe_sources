# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x140009628`
- end: `0x140009664`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this, int *, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140004b38`
- `0x140004ba4`
- `0x140008608`
- `0x1400099c0`

## callees

- `0x140009628`
- `0x140009960`

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
0x140009628  mov     [rsp+arg_0], rbx
0x14000962d  mov     [rsp+arg_8], rsi
0x140009632  push    rdi
0x140009633  sub     rsp, 20h
0x140009637  mov     rsi, r8
0x14000963a  mov     rbx, rdx
0x14000963d  mov     rdi, rcx
0x140009640  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x140009645  test    rbx, rbx
0x140009648  jz      short loc_140009654
0x14000964a  mov     [rdi], rbx
0x14000964d  mov     [rdi+8], rsi
0x140009651  lock inc dword ptr [rbx]
0x140009654  mov     rbx, [rsp+28h+arg_0]
0x140009659  mov     rsi, [rsp+28h+arg_8]
0x14000965e  add     rsp, 20h
0x140009662  pop     rdi
0x140009663  retn
```
