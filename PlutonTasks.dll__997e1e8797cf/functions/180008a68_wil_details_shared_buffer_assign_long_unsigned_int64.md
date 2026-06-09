# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x180008a68`
- end: `0x180008aa4`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *this, int *, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003144`
- `0x1800031b0`
- `0x180007798`
- `0x180008ef0`

## callees

- `0x180008a68`
- `0x180008e90`

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
0x180008a68  mov     [rsp+arg_0], rbx
0x180008a6d  mov     [rsp+arg_8], rsi
0x180008a72  push    rdi
0x180008a73  sub     rsp, 20h
0x180008a77  mov     rsi, r8
0x180008a7a  mov     rbx, rdx
0x180008a7d  mov     rdi, rcx
0x180008a80  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x180008a85  test    rbx, rbx
0x180008a88  jz      short loc_180008A94
0x180008a8a  mov     [rdi], rbx
0x180008a8d  mov     [rdi+8], rsi
0x180008a91  lock inc dword ptr [rbx]
0x180008a94  mov     rbx, [rsp+28h+arg_0]
0x180008a99  mov     rsi, [rsp+28h+arg_8]
0x180008a9e  add     rsp, 20h
0x180008aa2  pop     rdi
0x180008aa3  retn
```
