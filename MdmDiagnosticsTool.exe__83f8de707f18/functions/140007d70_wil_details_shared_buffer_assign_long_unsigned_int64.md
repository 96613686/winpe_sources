# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x140007d70`
- end: `0x140007dad`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `61`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this, int *, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140003074`
- `0x1400030e8`
- `0x1400067c8`
- `0x140008480`

## callees

- `0x140007d70`
- `0x140008344`

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
0x140007d70  mov     [rsp+arg_0], rbx
0x140007d75  mov     [rsp+arg_8], rsi
0x140007d7a  push    rdi
0x140007d7b  sub     rsp, 20h
0x140007d7f  mov     rsi, r8
0x140007d82  mov     rbx, rdx
0x140007d85  mov     rdi, rcx
0x140007d88  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x140007d8d  test    rbx, rbx
0x140007d90  jz      short loc_140007D9C
0x140007d92  mov     [rdi], rbx
0x140007d95  mov     [rdi+8], rsi
0x140007d99  lock inc dword ptr [rbx]
0x140007d9c  mov     rbx, [rsp+28h+arg_0]
0x140007da1  mov     rsi, [rsp+28h+arg_8]
0x140007da6  add     rsp, 20h
0x140007daa  pop     rdi
0x140007dab  retn
```
