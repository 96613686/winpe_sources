# av_dict_copy

- ea: `0x180035d20`
- end: `0x180035d98`
- name: `av_dict_copy`
- size: `120`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18003bfe0`
- `0x180046140`
- `0x180047b50`
- `0x180048c50`
- `0x180050880`

## callees

- `0x180035d20`
- `0x180036210`

## pseudocode

```c
__int64 __fastcall av_dict_copy(__int64 a1, __int64 a2, unsigned int a3)
{
  _QWORD *v6; // rbx
  int v7; // eax
  __int64 result; // rax

  v6 = 0;
  while ( 1 )
  {
    v7 = 0;
    if ( !a2 )
      break;
    if ( v6 )
      v7 = (((__int64)v6 - *(_QWORD *)(a2 + 8)) >> 4) + 1;
    if ( v7 >= *(_DWORD *)a2 )
      break;
    v6 = (_QWORD *)(*(_QWORD *)(a2 + 8) + 16LL * v7);
    if ( !v6 )
      break;
    result = av_dict_set(a1, *v6, v6[1], a3);
    if ( (int)result < 0 )
      return result;
  }
  return 0;
}

```

## disassembly

```asm
0x180035d20  mov     [rsp+arg_0], rbx
0x180035d25  mov     [rsp+arg_8], rbp
0x180035d2a  mov     [rsp+arg_10], rsi
0x180035d2f  push    rdi
0x180035d30  sub     rsp, 20h
0x180035d34  mov     esi, r8d
0x180035d37  mov     rdi, rdx
0x180035d3a  mov     rbp, rcx
0x180035d3d  xor     ebx, ebx
0x180035d3f  xor     eax, eax
0x180035d41  test    rdi, rdi
0x180035d44  jz      short loc_180035D81
0x180035d46  test    rbx, rbx
0x180035d49  jz      short loc_180035D58
0x180035d4b  sub     rbx, [rdi+8]
0x180035d4f  mov     rax, rbx
0x180035d52  sar     rax, 4
0x180035d56  inc     eax
0x180035d58  cmp     eax, [rdi]
0x180035d5a  jge     short loc_180035D81
0x180035d5c  movsxd  rbx, eax
0x180035d5f  shl     rbx, 4
0x180035d63  add     rbx, [rdi+8]
0x180035d67  jz      short loc_180035D81
0x180035d69  mov     r8, [rbx+8]
0x180035d6d  mov     r9d, esi
0x180035d70  mov     rdx, [rbx]
0x180035d73  mov     rcx, rbp
0x180035d76  call    av_dict_set
0x180035d7b  test    eax, eax
0x180035d7d  jns     short loc_180035D3F
0x180035d7f  jmp     short loc_180035D83
0x180035d81  xor     eax, eax
0x180035d83  mov     rbx, [rsp+28h+arg_0]
0x180035d88  mov     rbp, [rsp+28h+arg_8]
0x180035d8d  mov     rsi, [rsp+28h+arg_10]
0x180035d92  add     rsp, 20h
0x180035d96  pop     rdi
0x180035d97  retn
```
