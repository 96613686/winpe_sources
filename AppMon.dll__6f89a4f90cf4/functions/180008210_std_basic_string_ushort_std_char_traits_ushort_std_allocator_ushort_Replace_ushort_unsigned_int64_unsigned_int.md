# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Replace<ushort>(unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)

- ea: `0x180008210`
- end: `0x1800083c8`
- name: `??$_Replace@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_K_KQEBG0@Z`
- size: `440`
- prototype: `__int64 __usercall@<rax>(void *Src@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180008d9c`

## callees

- `0x18000285e`
- `0x18000286a`
- `0x1800080c0`
- `0x180008210`
- `0x180009ef0`

## pseudocode

```c
_QWORD *__fastcall std::wstring::_Replace<unsigned short>(
        _QWORD *Src,
        unsigned __int64 a2,
        __int64 a3,
        char *a4,
        unsigned __int64 a5)
{
  unsigned __int64 v5; // r15
  unsigned __int64 v8; // rbp
  unsigned __int64 v9; // r8
  _QWORD *v10; // rax
  unsigned __int64 v12; // r13
  _QWORD *v13; // rax
  char *v14; // rdi
  unsigned __int64 v15; // rcx
  char *v16; // r8
  char *v17; // rdx
  __int64 v18; // rdi
  char *v19; // [rsp+90h] [rbp+18h]

  v5 = Src[2];
  if ( v5 < a2 )
    std::_String_val<std::_Simple_types<unsigned short>>::_Xran();
  v8 = 2;
  v9 = Src[3];
  if ( v5 - a2 < 2 )
    v8 = v5 - a2;
  if ( v8 == a5 )
  {
    if ( v9 <= 7 )
      v10 = Src;
    else
      v10 = (_QWORD *)*Src;
    memmove_0((char *)v10 + 2 * a2, a4, 2 * a5);
    return Src;
  }
  v12 = v5 - a2 - v8;
  if ( a5 < v8 )
  {
    if ( v9 <= 7 )
      v13 = Src;
    else
      v13 = (_QWORD *)*Src;
    v14 = (char *)v13 + 2 * a2;
    memmove_0(v14, a4, 2 * a5);
    memmove_0(&v14[2 * a5], &v14[2 * v8], 2 * v12 + 2);
    Src[2] = a5 + v5 - v8;
    return Src;
  }
  v15 = a5 - v8;
  if ( a5 - v8 <= v9 - v5 )
  {
    Src[2] = v15 + v5;
    if ( v9 <= 7 )
      v16 = (char *)Src;
    else
      v16 = (char *)*Src;
    v19 = &v16[2 * a2];
    v17 = &v19[2 * v8];
    if ( &a4[2 * a5] <= v19 || a4 > &v16[2 * v5] )
    {
      v18 = a5;
    }
    else if ( v17 > a4 )
    {
      v18 = (v17 - a4) >> 1;
    }
    else
    {
      v18 = 0;
    }
    memmove_0(&v17[2 * v15], v17, 2 * v12 + 2);
    memmove_0(v19, a4, 2 * v18);
    memcpy_0(&v19[2 * v18], &a4[2 * v18 + 2 * (a5 - v8)], 2 * (a5 - v18));
    return Src;
  }
  return (_QWORD *)std::wstring::_Reallocate_grow_by<_lambda_622fe101509e1fd0c758e599152cbb8b_,unsigned __int64,unsigned __int64,unsigned short const *,unsigned __int64>(
                     Src,
                     v8,
                     a4,
                     a5);
}

```

## disassembly

```asm
0x180008210  mov     [rsp+arg_8], rbx
0x180008215  mov     [rsp+arg_10], r8
0x18000821a  push    rbp
0x18000821b  push    rsi
0x18000821c  push    rdi
0x18000821d  push    r12
0x18000821f  push    r13
0x180008221  push    r14
0x180008223  push    r15
0x180008225  sub     rsp, 40h
0x180008229  mov     r15, [rcx+10h]
0x18000822d  mov     r12, r9
0x180008230  mov     rsi, rcx
0x180008233  cmp     r15, rdx
0x180008236  jb      loc_1800083C2
0x18000823c  mov     r14, [rsp+78h+arg_20]
0x180008244  mov     ebp, 2
0x180008249  mov     r8, [rcx+18h]
0x18000824d  mov     r13, r15
0x180008250  sub     r13, rdx
0x180008253  cmp     r13, rbp
0x180008256  cmovb   rbp, r13
0x18000825a  cmp     rbp, r14
0x18000825d  jnz     short loc_180008285
0x18000825f  cmp     r8, 7
0x180008263  jbe     short loc_18000826A
0x180008265  mov     rax, [rcx]
0x180008268  jmp     short loc_18000826D
0x18000826a  mov     rax, rsi
0x18000826d  lea     rcx, [rax+rdx*2]; void *
0x180008271  mov     rdx, r12; Src
0x180008274  lea     r8, [r14+r14]; Size
0x180008278  call    memmove_0
0x18000827d  mov     rax, rsi
0x180008280  jmp     loc_1800083AA
0x180008285  sub     r13, rbp
0x180008288  cmp     r14, rbp
0x18000828b  jnb     short loc_1800082D2
0x18000828d  cmp     r8, 7
0x180008291  jbe     short loc_180008298
0x180008293  mov     rax, [rcx]
0x180008296  jmp     short loc_18000829B
0x180008298  mov     rax, rsi
0x18000829b  lea     rdi, [rax+rdx*2]
0x18000829f  mov     rdx, r12; Src
0x1800082a2  lea     rbx, [r14+r14]
0x1800082a6  mov     rcx, rdi; void *
0x1800082a9  mov     r8, rbx; Size
0x1800082ac  call    memmove_0
0x1800082b1  lea     r8, ds:2[r13*2]; Size
0x1800082b9  lea     rdx, [rdi+rbp*2]; Src
0x1800082bd  lea     rcx, [rdi+rbx]; void *
0x1800082c1  call    memmove_0
0x1800082c6  sub     r15, rbp
0x1800082c9  add     r15, r14
0x1800082cc  mov     [rsi+10h], r15
0x1800082d0  jmp     short loc_18000827D
0x1800082d2  mov     rcx, r14
0x1800082d5  mov     rax, r8
0x1800082d8  sub     rcx, rbp
0x1800082db  sub     rax, r15
0x1800082de  mov     [rsp+78h+arg_0], rcx
0x1800082e6  cmp     rcx, rax
0x1800082e9  ja      loc_18000838D
0x1800082ef  lea     rax, [rcx+r15]
0x1800082f3  mov     [rsi+10h], rax
0x1800082f7  cmp     r8, 7
0x1800082fb  jbe     short loc_180008302
0x1800082fd  mov     r8, [rsi]
0x180008300  jmp     short loc_180008305
0x180008302  mov     r8, rsi
0x180008305  lea     r9, [r8+rdx*2]
0x180008309  lea     rax, [r12+r14*2]
0x18000830d  mov     [rsp+78h+arg_10], r9
0x180008315  lea     rdx, [r9+rbp*2]; Src
0x180008319  cmp     rax, r9
0x18000831c  jbe     short loc_18000833B
0x18000831e  lea     rax, [r8+r15*2]
0x180008322  cmp     r12, rax
0x180008325  ja      short loc_18000833B
0x180008327  cmp     rdx, r12
0x18000832a  ja      short loc_180008330
0x18000832c  xor     edi, edi
0x18000832e  jmp     short loc_18000833E
0x180008330  mov     rdi, rdx
0x180008333  sub     rdi, r12
0x180008336  sar     rdi, 1
0x180008339  jmp     short loc_18000833E
0x18000833b  mov     rdi, r14
0x18000833e  lea     r8, ds:2[r13*2]; Size
0x180008346  lea     rcx, [rdx+rcx*2]; void *
0x18000834a  call    memmove_0
0x18000834f  mov     r15, [rsp+78h+arg_10]
0x180008357  lea     rbx, [rdi+rdi]
0x18000835b  mov     r8, rbx; Size
0x18000835e  mov     rcx, r15; void *
0x180008361  mov     rdx, r12; Src
0x180008364  call    memmove_0
0x180008369  mov     rax, [rsp+78h+arg_0]
0x180008371  lea     rcx, [rbx+r15]; void *
0x180008375  add     rax, rdi
0x180008378  sub     r14, rdi
0x18000837b  lea     rdx, [r12+rax*2]; Src
0x18000837f  lea     r8, [r14+r14]; Size
0x180008383  call    memcpy_0
0x180008388  jmp     loc_18000827D
0x18000838d  mov     r9, rdx
0x180008390  mov     [rsp+78h+var_48], r14; __int64
0x180008395  mov     rdx, rcx
0x180008398  mov     [rsp+78h+var_50], r12; void *
0x18000839d  mov     rcx, rsi; Src
0x1800083a0  mov     [rsp+78h+var_58], rbp; __int64
0x1800083a5  call    ??$_Reallocate_grow_by@V_lambda_622fe101509e1fd0c758e599152cbb8b_@@_K_KPEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_622fe101509e1fd0c758e599152cbb8b_@@_K2PEBG2@Z; std::wstring::_Reallocate_grow_by<_lambda_622fe101509e1fd0c758e599152cbb8b_,unsigned __int64,unsigned __int64,ushort const *,unsigned __int64>(unsigned __int64,_lambda_622fe101509e1fd0c758e599152cbb8b_,unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)
0x1800083aa  mov     rbx, [rsp+78h+arg_8]
0x1800083b2  add     rsp, 40h
0x1800083b6  pop     r15
0x1800083b8  pop     r14
0x1800083ba  pop     r13
0x1800083bc  pop     r12
0x1800083be  pop     rdi
0x1800083bf  pop     rsi
0x1800083c0  pop     rbp
0x1800083c1  retn
0x1800083c2  call    ?_Xran@?$_String_val@U?$_Simple_types@G@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<ushort>>::_Xran(void)
```
