# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x180008f80`
- end: `0x180008fbc`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *__hidden this, int *, unsigned __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180005080`
- `0x180007450`
- `0x18000c4d8`

## callees

- `0x180005178`
- `0x180008f80`

## pseudocode

```c
void __fastcall wil::details::shared_buffer::assign(
        volatile signed __int32 **this,
        int *a2,
        volatile signed __int32 *a3)
{
  wil::details::shared_buffer::reset(this);
  if ( a2 )
  {
    *this = a2;
    this[1] = a3;
    _InterlockedIncrement(a2);
  }
}

```

## disassembly

```asm
0x180008f80  mov     [rsp+arg_0], rbx
0x180008f85  mov     [rsp+arg_8], rsi
0x180008f8a  push    rdi
0x180008f8b  sub     rsp, 20h
0x180008f8f  mov     rsi, r8
0x180008f92  mov     rbx, rdx
0x180008f95  mov     rdi, rcx
0x180008f98  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x180008f9d  test    rbx, rbx
0x180008fa0  jz      short loc_180008FAC
0x180008fa2  mov     [rdi], rbx
0x180008fa5  mov     [rdi+8], rsi
0x180008fa9  lock inc dword ptr [rbx]
0x180008fac  mov     rbx, [rsp+28h+arg_0]
0x180008fb1  mov     rsi, [rsp+28h+arg_8]
0x180008fb6  add     rsp, 20h
0x180008fba  pop     rdi
0x180008fbb  retn
```
