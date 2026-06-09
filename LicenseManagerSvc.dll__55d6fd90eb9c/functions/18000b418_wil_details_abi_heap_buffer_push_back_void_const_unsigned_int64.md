# wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)

- ea: `0x18000b418`
- end: `0x18000b472`
- name: `?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z`
- size: `90`
- prototype: `bool(wil::details_abi::heap_buffer *__hidden this, const void *, unsigned __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x1800097e8`
- `0x1800098d4`
- `0x18000ab04`
- `0x18000acc0`

## callees

- `0x180007b30`
- `0x18000b3e8`
- `0x18000b418`

## pseudocode

```c
bool __fastcall wil::details_abi::heap_buffer::push_back(void **this, const void *a2, unsigned __int64 a3)
{
  bool result; // al

  result = wil::details_abi::heap_buffer::ensure((wil::details_abi::heap_buffer *)this, a3);
  if ( result )
  {
    memcpy_s(this[1], ((_BYTE *)this[2] - (_BYTE *)this[1]) & -(__int64)(this[1] < this[2]), a2, a3);
    this[1] = (char *)this[1] + a3;
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000b418  mov     [rsp+arg_0], rbx
0x18000b41d  mov     [rsp+arg_8], rsi
0x18000b422  push    rdi
0x18000b423  sub     rsp, 20h
0x18000b427  mov     rsi, rdx
0x18000b42a  mov     rdi, r8
0x18000b42d  mov     rdx, r8; unsigned __int64
0x18000b430  mov     rbx, rcx
0x18000b433  call    ?ensure@heap_buffer@details_abi@wil@@QEAA_N_K@Z; wil::details_abi::heap_buffer::ensure(unsigned __int64)
0x18000b438  test    al, al
0x18000b43a  jz      short loc_18000B462
0x18000b43c  mov     rcx, [rbx+8]; Destination
0x18000b440  mov     r9, rdi; SourceSize
0x18000b443  mov     rax, [rbx+10h]
0x18000b447  mov     r8, rsi; Source
0x18000b44a  sub     rax, rcx
0x18000b44d  cmp     rcx, [rbx+10h]
0x18000b451  sbb     rdx, rdx
0x18000b454  and     rdx, rax; DestinationSize
0x18000b457  call    memcpy_s
0x18000b45c  add     [rbx+8], rdi
0x18000b460  mov     al, 1
0x18000b462  mov     rbx, [rsp+28h+arg_0]
0x18000b467  mov     rsi, [rsp+28h+arg_8]
0x18000b46c  add     rsp, 20h
0x18000b470  pop     rdi
0x18000b471  retn
```
