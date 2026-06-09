# wil::details::shared_buffer::assign(long *,unsigned __int64)

- ea: `0x1400077d4`
- end: `0x140007810`
- name: `?assign@shared_buffer@details@wil@@AEAAXPEAJ_K@Z`
- size: `60`
- prototype: `void __fastcall(wil::details::shared_buffer *this, int *, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400050ac`
- `0x140005118`
- `0x140006dc8`
- `0x140007990`

## callees

- `0x1400077d4`
- `0x14000792c`

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
0x1400077d4  mov     [rsp+arg_0], rbx
0x1400077d9  mov     [rsp+arg_8], rsi
0x1400077de  push    rdi
0x1400077df  sub     rsp, 20h
0x1400077e3  mov     rsi, r8
0x1400077e6  mov     rbx, rdx
0x1400077e9  mov     rdi, rcx
0x1400077ec  call    ?reset@shared_buffer@details@wil@@QEAAXXZ; wil::details::shared_buffer::reset(void)
0x1400077f1  test    rbx, rbx
0x1400077f4  jz      short loc_140007800
0x1400077f6  mov     [rdi], rbx
0x1400077f9  mov     [rdi+8], rsi
0x1400077fd  lock inc dword ptr [rbx]
0x140007800  mov     rbx, [rsp+28h+arg_0]
0x140007805  mov     rsi, [rsp+28h+arg_8]
0x14000780a  add     rsp, 20h
0x14000780e  pop     rdi
0x14000780f  retn
```
