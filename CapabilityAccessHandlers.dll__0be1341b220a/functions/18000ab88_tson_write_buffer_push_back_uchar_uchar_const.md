# tson::write_buffer::push_back<uchar>(uchar const &)

- ea: `0x18000ab88`
- end: `0x18000abd5`
- name: `??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z`
- size: `77`
- prototype: `bool __fastcall(tson::write_buffer *, _BYTE *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a64c`
- `0x18000b13c`
- `0x18000df0c`
- `0x18000f168`
- `0x18000f2a8`
- `0x18000f358`

## callees

- `0x18000ab88`
- `0x18000e20c`

## pseudocode

```c
bool __fastcall tson::write_buffer::push_back<unsigned char>(tson::write_buffer *a1, _BYTE *a2)
{
  bool result; // al

  if ( *((_QWORD *)a1 + 259) < *((_QWORD *)a1 + 260) || (result = tson::write_buffer::reserve(a1, 1u)) )
  {
    result = 1;
    *(_BYTE *)(*((_QWORD *)a1 + 259))++ = *a2;
  }
  return result;
}

```

## disassembly

```asm
0x18000ab88  mov     [rsp+arg_0], rbx
0x18000ab8d  push    rdi
0x18000ab8e  sub     rsp, 20h
0x18000ab92  mov     rax, [rcx+820h]
0x18000ab99  mov     rdi, rdx
0x18000ab9c  mov     rbx, rcx
0x18000ab9f  cmp     [rcx+818h], rax
0x18000aba6  jb      short loc_18000ABB6
0x18000aba8  mov     edx, 1; unsigned __int64
0x18000abad  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000abb2  test    al, al
0x18000abb4  jz      short loc_18000ABCA
0x18000abb6  mov     rdx, [rbx+818h]
0x18000abbd  mov     al, 1
0x18000abbf  mov     cl, [rdi]
0x18000abc1  mov     [rdx], cl
0x18000abc3  inc     qword ptr [rbx+818h]
0x18000abca  mov     rbx, [rsp+28h+arg_0]
0x18000abcf  add     rsp, 20h
0x18000abd3  pop     rdi
0x18000abd4  retn
```
