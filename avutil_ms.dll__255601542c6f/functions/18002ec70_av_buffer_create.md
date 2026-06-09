# av_buffer_create

- ea: `0x18002ec70`
- end: `0x18002ecef`
- name: `av_buffer_create`
- size: `127`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x18002ebe0`
- `0x18002f030`
- `0x180035c90`
- `0x18003f2d0`
- `0x1800778d0`
- `0x1800779d0`

## callees

- `0x18002ec70`
- `0x18002f22c`
- `0x1800449c0`
- `0x180044aa0`

## pseudocode

```c
__int64 __fastcall av_buffer_create(int a1, int a2, int a3, __int64 a4, int a5)
{
  void *v9; // rbx
  __int64 result; // rax

  v9 = av_mallocz(0x30u);
  if ( v9 )
  {
    result = sub_18002F22C((_DWORD)v9, a1, a2, a3, a4, a5);
    if ( result )
      return result;
    av_free(v9);
  }
  return 0;
}

```

## disassembly

```asm
0x18002ec70  mov     rax, rsp
0x18002ec73  mov     [rax+8], rbx
0x18002ec77  mov     [rax+10h], rbp
0x18002ec7b  mov     [rax+18h], rsi
0x18002ec7f  mov     [rax+20h], rdi
0x18002ec83  push    r14
0x18002ec85  sub     rsp, 30h
0x18002ec89  mov     r14, rcx
0x18002ec8c  mov     rdi, r9
0x18002ec8f  mov     ecx, 30h ; '0'
0x18002ec94  mov     rsi, r8
0x18002ec97  mov     rbp, rdx
0x18002ec9a  call    av_mallocz
0x18002ec9f  mov     rbx, rax
0x18002eca2  test    rax, rax
0x18002eca5  jz      short loc_18002ECD2
0x18002eca7  mov     eax, [rsp+38h+arg_20]
0x18002ecab  mov     r9, rsi
0x18002ecae  mov     [rsp+38h+var_10], eax
0x18002ecb2  mov     r8, rbp
0x18002ecb5  mov     rdx, r14
0x18002ecb8  mov     [rsp+38h+var_18], rdi
0x18002ecbd  mov     rcx, rbx
0x18002ecc0  call    sub_18002F22C
0x18002ecc5  test    rax, rax
0x18002ecc8  jnz     short loc_18002ECD4
0x18002ecca  mov     rcx, rbx; Block
0x18002eccd  call    av_free
0x18002ecd2  xor     eax, eax
0x18002ecd4  mov     rbx, [rsp+38h+arg_0]
0x18002ecd9  mov     rbp, [rsp+38h+arg_8]
0x18002ecde  mov     rsi, [rsp+38h+arg_10]
0x18002ece3  mov     rdi, [rsp+38h+arg_18]
0x18002ece8  add     rsp, 30h
0x18002ecec  pop     r14
0x18002ecee  retn
```
