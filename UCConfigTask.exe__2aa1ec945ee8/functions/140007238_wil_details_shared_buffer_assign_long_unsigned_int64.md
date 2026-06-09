# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x140007238`
- end: `0x140007274`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *this, int *, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140002b28`
- `0x140002b94`
- `0x14000629c`
- `0x140007610`

## callees

- `0x140007238`
- `0x1400075b0`

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
0x140007238  mov     [rsp+arg_0], rbx
0x14000723d  mov     [rsp+arg_8], rsi
0x140007242  push    rdi
0x140007243  sub     rsp, 20h
0x140007247  mov     rsi, r8
0x14000724a  mov     rbx, rdx
0x14000724d  mov     rdi, rcx
0x140007250  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x140007255  test    rbx, rbx
0x140007258  jz      short loc_140007264
0x14000725a  mov     [rdi], rbx
0x14000725d  mov     [rdi+8], rsi
0x140007261  lock inc dword ptr [rbx]
0x140007264  mov     rbx, [rsp+28h+arg_0]
0x140007269  mov     rsi, [rsp+28h+arg_8]
0x14000726e  add     rsp, 20h
0x140007272  pop     rdi
0x140007273  retn
```
