# tson::write_buffer::push_back<uchar>(uchar const &)

- ea: `0x18000ae94`
- end: `0x18000aee1`
- name: `??$push_back@E@write_buffer@tson@@QEAA_NAEBE@Z`
- size: `77`
- prototype: `bool __fastcall(tson::write_buffer *, _BYTE *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a730`
- `0x18000b3b0`
- `0x18000da94`
- `0x18000e734`
- `0x18000e874`
- `0x18000e924`

## callees

- `0x18000ae94`
- `0x18000dca8`

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
0x18000ae94  mov     [rsp+arg_0], rbx
0x18000ae99  push    rdi
0x18000ae9a  sub     rsp, 20h
0x18000ae9e  mov     rax, [rcx+820h]
0x18000aea5  mov     rdi, rdx
0x18000aea8  mov     rbx, rcx
0x18000aeab  cmp     [rcx+818h], rax
0x18000aeb2  jb      short loc_18000AEC2
0x18000aeb4  mov     edx, 1; unsigned __int64
0x18000aeb9  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000aebe  test    al, al
0x18000aec0  jz      short loc_18000AED6
0x18000aec2  mov     rdx, [rbx+818h]
0x18000aec9  mov     al, 1
0x18000aecb  mov     cl, [rdi]
0x18000aecd  mov     [rdx], cl
0x18000aecf  inc     qword ptr [rbx+818h]
0x18000aed6  mov     rbx, [rsp+28h+arg_0]
0x18000aedb  add     rsp, 20h
0x18000aedf  pop     rdi
0x18000aee0  retn
```
