# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x18000568c`
- end: `0x1800056c8`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this, int *, unsigned __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ebc`
- `0x180002f28`
- `0x180004d78`
- `0x1800057e0`

## callees

- `0x18000568c`
- `0x18000577c`

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
0x18000568c  mov     [rsp+arg_0], rbx
0x180005691  mov     [rsp+arg_8], rsi
0x180005696  push    rdi
0x180005697  sub     rsp, 20h
0x18000569b  mov     rsi, r8
0x18000569e  mov     rbx, rdx
0x1800056a1  mov     rdi, rcx
0x1800056a4  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x1800056a9  test    rbx, rbx
0x1800056ac  jz      short loc_1800056B8
0x1800056ae  mov     [rdi], rbx
0x1800056b1  mov     [rdi+8], rsi
0x1800056b5  lock inc dword ptr [rbx]
0x1800056b8  mov     rbx, [rsp+28h+arg_0]
0x1800056bd  mov     rsi, [rsp+28h+arg_8]
0x1800056c2  add     rsp, 20h
0x1800056c6  pop     rdi
0x1800056c7  retn
```
