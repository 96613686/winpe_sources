# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)

- ea: `0x18000c860`
- end: `0x18000c998`
- name: `??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z`
- size: `312`
- prototype: `char **__fastcall(char **, unsigned __int64, __int64, const void *)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000cea0`
- `0x18000d8b8`
- `0x18000db14`
- `0x18000dcc8`

## callees

- `0x18000207c`
- `0x1800020a0`
- `0x18000abd0`
- `0x18000abf8`
- `0x18000c860`
- `0x18000e7ec`

## pseudocode

```c
char **__fastcall std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        char **a1,
        unsigned __int64 a2,
        __int64 a3,
        const void *a4)
{
  __int64 v4; // rbx
  unsigned __int64 v8; // rbp
  unsigned __int64 v9; // rcx
  __int64 v10; // rdx
  size_t v11; // rcx
  void *v12; // rax
  _QWORD *v13; // rsi
  char *v14; // rax
  char *v15; // rcx
  char **result; // rax

  v4 = 0x7FFFFFFFFFFFFFFELL;
  if ( a2 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  v8 = (unsigned __int64)a1[3];
  v9 = a2 | 7;
  if ( (a2 | 7) <= 0x7FFFFFFFFFFFFFFELL && (v10 = v8 >> 1, v8 <= 0x7FFFFFFFFFFFFFFELL - (v8 >> 1)) )
  {
    v4 = v10 + v8;
    if ( v9 >= v10 + v8 )
      v4 = v9;
    if ( (unsigned __int64)(v4 + 1) > 0x7FFFFFFFFFFFFFFFLL )
      goto LABEL_23;
    v11 = 2 * (v4 + 1);
    if ( !v11 )
    {
      v13 = 0;
      goto LABEL_15;
    }
  }
  else
  {
    v11 = -2;
  }
  if ( v11 < 0x1000 )
  {
    v13 = operator new(v11);
    goto LABEL_15;
  }
  if ( v11 + 39 < v11 )
LABEL_23:
    __scrt_throw_std_bad_array_new_length();
  v12 = operator new(v11 + 39);
  if ( !v12 )
    goto LABEL_18;
  v13 = (_QWORD *)(((unsigned __int64)v12 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v13 - 1) = v12;
LABEL_15:
  a1[3] = (char *)v4;
  a1[2] = (char *)a2;
  memcpy_0(v13, a4, 2 * a2);
  *((_WORD *)v13 + a2) = 0;
  if ( v8 > 7 )
  {
    v14 = *a1;
    if ( 2 * v8 + 2 < 0x1000 )
    {
      v15 = *a1;
    }
    else
    {
      v15 = (char *)*((_QWORD *)v14 - 1);
      if ( (unsigned __int64)(v14 - v15 - 8) > 0x1F )
LABEL_18:
        __fastfail(5u);
    }
    operator delete(v15);
  }
  result = a1;
  *a1 = (char *)v13;
  return result;
}

```

## disassembly

```asm
0x18000c860  push    rbx
0x18000c862  push    rbp
0x18000c863  push    rsi
0x18000c864  push    rdi
0x18000c865  push    r14
0x18000c867  push    r15
0x18000c869  sub     rsp, 28h
0x18000c86d  mov     rbx, 7FFFFFFFFFFFFFFEh
0x18000c877  mov     r15, r9
0x18000c87a  mov     r14, rdx
0x18000c87d  mov     rdi, rcx
0x18000c880  cmp     rdx, rbx
0x18000c883  ja      loc_18000C98C
0x18000c889  mov     rbp, [rcx+18h]
0x18000c88d  mov     rcx, rdx
0x18000c890  or      rcx, 7
0x18000c894  cmp     rcx, rbx
0x18000c897  ja      short loc_18000C8AA
0x18000c899  mov     rdx, rbp
0x18000c89c  mov     rax, rbx
0x18000c89f  shr     rdx, 1
0x18000c8a2  sub     rax, rdx
0x18000c8a5  cmp     rbp, rax
0x18000c8a8  jbe     short loc_18000C8E6
0x18000c8aa  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x18000c8b1  cmp     rcx, 1000h
0x18000c8b8  jb      short loc_18000C911
0x18000c8ba  lea     rax, [rcx+27h]
0x18000c8be  cmp     rax, rcx
0x18000c8c1  jbe     loc_18000C992
0x18000c8c7  mov     rcx, rax; Size
0x18000c8ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c8cf  test    rax, rax
0x18000c8d2  jz      loc_18000C96A
0x18000c8d8  lea     rsi, [rax+27h]
0x18000c8dc  and     rsi, 0FFFFFFFFFFFFFFE0h
0x18000c8e0  mov     [rsi-8], rax
0x18000c8e4  jmp     short loc_18000C919
0x18000c8e6  lea     rbx, [rdx+rbp]
0x18000c8ea  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000c8f4  cmp     rcx, rbx
0x18000c8f7  cmovnb  rbx, rcx
0x18000c8fb  lea     rcx, [rbx+1]
0x18000c8ff  cmp     rcx, rax
0x18000c902  ja      loc_18000C992
0x18000c908  add     rcx, rcx
0x18000c90b  jnz     short loc_18000C8B1
0x18000c90d  xor     esi, esi
0x18000c90f  jmp     short loc_18000C919
0x18000c911  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c916  mov     rsi, rax
0x18000c919  mov     [rdi+18h], rbx
0x18000c91d  mov     rdx, r15; Src
0x18000c920  lea     rbx, [r14+r14]
0x18000c924  mov     [rdi+10h], r14
0x18000c928  mov     r8, rbx; Size
0x18000c92b  mov     rcx, rsi; void *
0x18000c92e  call    memcpy_0
0x18000c933  xor     ecx, ecx
0x18000c935  mov     [rbx+rsi], cx
0x18000c939  cmp     rbp, 7
0x18000c93d  jbe     short loc_18000C979
0x18000c93f  mov     rax, [rdi]
0x18000c942  lea     rdx, ds:2[rbp*2]
0x18000c94a  cmp     rdx, 1000h
0x18000c951  jb      short loc_18000C971
0x18000c953  mov     rcx, [rax-8]
0x18000c957  sub     rax, rcx
0x18000c95a  sub     rax, 8
0x18000c95e  cmp     rax, 1Fh
0x18000c962  ja      short loc_18000C96A
0x18000c964  add     rdx, 27h ; '''
0x18000c968  jmp     short loc_18000C974
0x18000c96a  mov     ecx, 5
0x18000c96f  int     29h; Win8: RtlFailFast(ecx)
0x18000c971  mov     rcx, rax; Block
0x18000c974  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c979  mov     rax, rdi
0x18000c97c  mov     [rax], rsi
0x18000c97f  add     rsp, 28h
0x18000c983  pop     r15
0x18000c985  pop     r14
0x18000c987  pop     rdi
0x18000c988  pop     rsi
0x18000c989  pop     rbp
0x18000c98a  pop     rbx
0x18000c98b  retn
0x18000c98c  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18000c992  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
