# av_compare_ts

- ea: `0x180043d80`
- end: `0x180043e4c`
- name: `av_compare_ts`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180043d80`
- `0x180044120`

## pseudocode

```c
__int64 __fastcall av_compare_ts(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rbx
  __int64 v7; // rdi
  __int64 v8; // rcx
  __int64 v9; // rax

  v6 = (int)a2 * (__int64)SHIDWORD(a4);
  v7 = (int)a4 * (__int64)SHIDWORD(a2);
  v8 = -a1;
  if ( v8 < 0 )
    v8 = a1;
  v9 = -a3;
  if ( a3 > 0 )
    v9 = a3;
  _mm_lfence();
  if ( (v6 | v7 | v9 | (unsigned __int64)v8) <= 0x7FFFFFFF )
    return (a1 * v6 > a3 * v7) - (unsigned int)(a1 * v6 < a3 * v7);
  if ( av_rescale_rnd(a1, v6, v7, 2) < a3 )
    return 0xFFFFFFFFLL;
  _mm_lfence();
  return av_rescale_rnd(a3, v7, v6, 2) < a1;
}

```

## disassembly

```asm
0x180043d80  mov     [rsp+arg_0], rbx
0x180043d85  mov     [rsp+arg_8], rbp
0x180043d8a  mov     [rsp+arg_10], rsi
0x180043d8f  push    rdi
0x180043d90  sub     rsp, 20h
0x180043d94  mov     rbp, rcx
0x180043d97  mov     rax, r9
0x180043d9a  shr     rax, 20h
0x180043d9e  mov     rsi, r8
0x180043da1  movsxd  rbx, eax
0x180043da4  movsxd  rax, edx
0x180043da7  imul    rbx, rax
0x180043dab  shr     rdx, 20h
0x180043daf  movsxd  rax, r9d
0x180043db2  movsxd  rdi, edx
0x180043db5  imul    rdi, rax
0x180043db9  neg     rcx
0x180043dbc  mov     rax, r8
0x180043dbf  cmovs   rcx, rbp
0x180043dc3  neg     rax
0x180043dc6  cmovs   rax, r8
0x180043dca  or      rcx, rax
0x180043dcd  or      rcx, rdi
0x180043dd0  or      rcx, rbx
0x180043dd3  lfence
0x180043dd6  cmp     rcx, 7FFFFFFFh
0x180043ddd  ja      short loc_180043DF8
0x180043ddf  xor     ecx, ecx
0x180043de1  mov     eax, ecx
0x180043de3  imul    rbx, rbp
0x180043de7  imul    rdi, rsi
0x180043deb  cmp     rbx, rdi
0x180043dee  setnle  al
0x180043df1  setl    cl
0x180043df4  sub     eax, ecx
0x180043df6  jmp     short loc_180043E37
0x180043df8  mov     r9d, 2
0x180043dfe  mov     r8, rdi
0x180043e01  mov     rdx, rbx
0x180043e04  mov     rcx, rbp
0x180043e07  call    av_rescale_rnd
0x180043e0c  cmp     rax, rsi
0x180043e0f  jge     short loc_180043E16
0x180043e11  or      eax, 0FFFFFFFFh
0x180043e14  jmp     short loc_180043E37
0x180043e16  lfence
0x180043e19  mov     r9d, 2
0x180043e1f  mov     r8, rbx
0x180043e22  mov     rdx, rdi
0x180043e25  mov     rcx, rsi
0x180043e28  call    av_rescale_rnd
0x180043e2d  xor     ecx, ecx
0x180043e2f  cmp     rax, rbp
0x180043e32  setl    cl
0x180043e35  mov     eax, ecx
0x180043e37  mov     rbx, [rsp+28h+arg_0]
0x180043e3c  mov     rbp, [rsp+28h+arg_8]
0x180043e41  mov     rsi, [rsp+28h+arg_10]
0x180043e46  add     rsp, 20h
0x180043e4a  pop     rdi
0x180043e4b  retn
```
