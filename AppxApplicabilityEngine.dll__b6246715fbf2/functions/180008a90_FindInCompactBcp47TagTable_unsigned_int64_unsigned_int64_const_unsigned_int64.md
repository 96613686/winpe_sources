# FindInCompactBcp47TagTable(unsigned __int64,unsigned __int64 const *,unsigned __int64)

- ea: `0x180008a90`
- end: `0x180008bfc`
- name: `?FindInCompactBcp47TagTable@@YAPEB_K_KPEB_K0@Z`
- size: `364`
- prototype: `const unsigned __int64 *__fastcall(__int64, const unsigned __int64 *, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007650`

## callees

- `0x180008a90`
- `0x1800095e0`

## pseudocode

```c
const unsigned __int64 *__fastcall FindInCompactBcp47TagTable(__int64 a1, const unsigned __int64 *a2, __int64 a3)
{
  __int64 i; // rax
  __int64 v6; // rdx
  unsigned __int64 v7; // r8
  const unsigned __int64 *v8; // r10
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rbx
  const unsigned __int64 *v11; // r11
  const unsigned __int64 *v12; // r10
  unsigned __int64 v13; // rcx
  const unsigned __int64 *result; // rax
  __int64 v15; // [rsp+30h] [rbp+8h] BYREF
  __int64 *j; // [rsp+38h] [rbp+10h] BYREF

  v15 = a1;
  for ( i = (8 * a3) >> 3; ; i += -1 - v6 )
  {
    while ( 1 )
    {
      if ( i <= 0 )
      {
        v12 = a2;
        v11 = a2;
        goto LABEL_11;
      }
      v6 = i >> 1;
      v7 = a1 & 0x3FFF000000LL;
      v8 = &a2[i >> 1];
      v9 = *v8 & 0x3FFF000000LL;
      if ( v9 <= (a1 & 0x3FFF000000uLL) )
        break;
LABEL_7:
      i >>= 1;
    }
    if ( v9 >= (a1 & 0x3FFF000000uLL) )
      break;
    a2 = v8 + 1;
  }
  if ( v9 > (a1 & 0x3FFF000000uLL) )
    goto LABEL_7;
  v10 = (8 * v6) >> 3;
  v11 = a2;
  while ( (__int64)v10 > 0 )
  {
    if ( (v11[v10 >> 1] & 0x3FFF000000LL) >= v7 )
    {
      v10 >>= 1;
    }
    else
    {
      v11 += (v10 >> 1) + 1;
      v10 += -1LL - (v10 >> 1);
    }
  }
  v12 = v8 + 1;
  v13 = ((__int64)a2 + 8 * i - (__int64)v12) >> 3;
  while ( (__int64)v13 > 0 )
  {
    if ( v7 >= (v12[v13 >> 1] & 0x3FFF000000LL) )
    {
      v12 += (v13 >> 1) + 1;
      v13 += -1LL - (v13 >> 1);
    }
    else
    {
      v13 >>= 1;
    }
  }
  for ( j = &v15; v11 != v12; ++v11 )
  {
    if ( (unsigned __int8)lambda_a481841d582f381d2c5e66151ae159aa_::operator()(&j, *v11) )
      break;
  }
LABEL_11:
  result = 0;
  if ( v11 != v12 )
    return v11;
  return result;
}

```

## disassembly

```asm
0x180008a90  mov     [rsp+arg_0], rcx
0x180008a95  push    rsi
0x180008a96  sub     rsp, 20h
0x180008a9a  lea     rax, ds:0[r8*8]
0x180008aa2  mov     [rsp+28h+arg_10], rbx
0x180008aa7  sar     rax, 3
0x180008aab  mov     r9, rdx
0x180008aae  mov     r11, rcx
0x180008ab1  mov     rsi, 3FFF000000h
0x180008abb  test    rax, rax
0x180008abe  jle     loc_180008BF1
0x180008ac4  mov     rdx, rax
0x180008ac7  jns     short loc_180008ACD
0x180008ac9  lea     rdx, [rax+1]
0x180008acd  sar     rdx, 1
0x180008ad0  mov     r8, r11
0x180008ad3  and     r8, rsi
0x180008ad6  lea     rbx, ds:0[rdx*8]
0x180008ade  mov     rcx, [rbx+r9]
0x180008ae2  lea     r10, [rbx+r9]
0x180008ae6  and     rcx, rsi
0x180008ae9  cmp     rcx, r8
0x180008aec  ja      short loc_180008B05
0x180008aee  jnb     short loc_180008B03
0x180008af0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180008af7  lea     r9, [r10+8]
0x180008afb  sub     rcx, rdx
0x180008afe  add     rax, rcx
0x180008b01  jmp     short loc_180008ABB
0x180008b03  jbe     short loc_180008B0A
0x180008b05  mov     rax, rdx
0x180008b08  jmp     short loc_180008ABB
0x180008b0a  sar     rbx, 3
0x180008b0e  mov     r11, r9
0x180008b11  test    rbx, rbx
0x180008b14  jg      loc_180008BC7
0x180008b1a  add     r10, 8
0x180008b1e  lea     rcx, ds:0[rax*8]
0x180008b26  sub     rcx, r10
0x180008b29  add     rcx, r9
0x180008b2c  sar     rcx, 3
0x180008b30  test    rcx, rcx
0x180008b33  jg      short loc_180008B94
0x180008b35  lea     rax, [rsp+28h+arg_0]
0x180008b3a  mov     [rsp+28h+arg_8], rax
0x180008b3f  cmp     r11, r10
0x180008b42  jnz     loc_180008BCE
0x180008b48  mov     rbx, [rsp+28h+arg_10]
0x180008b4d  xor     eax, eax
0x180008b4f  cmp     r11, r10
0x180008b52  cmovnz  rax, r11
0x180008b56  add     rsp, 20h
0x180008b5a  pop     rsi
0x180008b5b  retn
0x180008b5c  mov     rdx, rbx
0x180008b5f  shr     rdx, 1
0x180008b62  mov     rcx, [r11+rdx*8]
0x180008b66  lea     rdi, [r11+rdx*8]
0x180008b6a  and     rcx, rsi
0x180008b6d  cmp     rcx, r8
0x180008b70  jnb     short loc_180008B8F
0x180008b72  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180008b79  lea     r11, [rdi+8]
0x180008b7d  sub     rcx, rdx
0x180008b80  add     rbx, rcx
0x180008b83  test    rbx, rbx
0x180008b86  jg      short loc_180008B5C
0x180008b88  mov     rdi, [rsp+28h+arg_18]
0x180008b8d  jmp     short loc_180008B1A
0x180008b8f  mov     rbx, rdx
0x180008b92  jmp     short loc_180008B83
0x180008b94  mov     rdx, rcx
0x180008b97  shr     rdx, 1
0x180008b9a  mov     rax, [r10+rdx*8]
0x180008b9e  lea     r9, [r10+rdx*8]
0x180008ba2  and     rax, rsi
0x180008ba5  cmp     r8, rax
0x180008ba8  jnb     short loc_180008BB4
0x180008baa  mov     rcx, rdx
0x180008bad  test    rcx, rcx
0x180008bb0  jg      short loc_180008B94
0x180008bb2  jmp     short loc_180008B35
0x180008bb4  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180008bbb  lea     r10, [r9+8]
0x180008bbf  sub     rax, rdx
0x180008bc2  add     rcx, rax
0x180008bc5  jmp     short loc_180008BAD
0x180008bc7  mov     [rsp+28h+arg_18], rdi
0x180008bcc  jmp     short loc_180008B5C
0x180008bce  mov     rdx, [r11]
0x180008bd1  lea     rcx, [rsp+28h+arg_8]
0x180008bd6  call    _lambda_a481841d582f381d2c5e66151ae159aa___operator__
0x180008bdb  test    al, al
0x180008bdd  jnz     loc_180008B48
0x180008be3  add     r11, 8
0x180008be7  cmp     r11, r10
0x180008bea  jnz     short loc_180008BCE
0x180008bec  jmp     loc_180008B48
0x180008bf1  mov     r10, r9
0x180008bf4  mov     r11, r9
0x180008bf7  jmp     loc_180008B48
```
