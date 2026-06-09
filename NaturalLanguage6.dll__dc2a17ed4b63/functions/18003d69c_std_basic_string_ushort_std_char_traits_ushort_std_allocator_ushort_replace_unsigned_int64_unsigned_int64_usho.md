# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::replace(unsigned __int64,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x18003d69c`
- end: `0x18003d821`
- name: `?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0PEBG0@Z`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation`

## callers

- `0x18003b3c0`

## callees

- `0x180014ff4`
- `0x1800151c4`
- `0x180015204`
- `0x18003d69c`
- `0x18003d960`
- `0x18003dc1c`
- `0x18003e0d0`
- `0x18003e0fc`

## pseudocode

```c
_QWORD *__fastcall std::wstring::replace(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        unsigned __int64 a5)
{
  _QWORD *v9; // rax
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rbp
  _QWORD *v13; // rcx
  _QWORD *v14; // rdx
  unsigned __int64 v15; // r12
  _QWORD *v16; // rcx
  _QWORD *v17; // rdx
  _QWORD *v18; // rax
  _QWORD *v19; // rcx

  if ( std::wstring::_Inside(a1, a4) )
  {
    if ( a1[3] < 8u )
      v9 = a1;
    else
      v9 = (_QWORD *)*a1;
    return std::wstring::replace(a1, a2, a3, a1, (__int64)(a4 - (_QWORD)v9) >> 1, a5);
  }
  else
  {
    v11 = a1[2];
    if ( v11 < a2 )
      std::_Xout_of_range("invalid string position");
    if ( v11 - a2 < a3 )
      a3 = v11 - a2;
    if ( ~a5 <= v11 - a3 )
      std::_Xlength_error("string too long");
    v12 = v11 - a2 - a3;
    if ( a5 < a3 )
    {
      if ( a1[3] < 8u )
      {
        v13 = a1;
        v14 = a1;
      }
      else
      {
        v13 = (_QWORD *)*a1;
        v14 = (_QWORD *)*a1;
      }
      std::char_traits<unsigned short>::move((char *)v13 + 2 * a2 + 2 * a5, (char *)v14 + 2 * a2 + 2 * a3, v12);
    }
    if ( a5 || a3 )
    {
      v15 = a5 + a1[2] - a3;
      if ( (unsigned __int8)std::wstring::_Grow(a1, v15, 0) )
      {
        if ( a3 < a5 )
        {
          if ( a1[3] < 8u )
          {
            v16 = a1;
            v17 = a1;
          }
          else
          {
            v16 = (_QWORD *)*a1;
            v17 = (_QWORD *)*a1;
          }
          std::char_traits<unsigned short>::move((char *)v16 + 2 * a2 + 2 * a5, (char *)v17 + 2 * a2 + 2 * a3, v12);
        }
        if ( a1[3] < 8u )
          v18 = a1;
        else
          v18 = (_QWORD *)*a1;
        std::char_traits<unsigned short>::copy((char *)v18 + 2 * a2, a4, a5);
        if ( a1[3] < 8u )
          v19 = a1;
        else
          v19 = (_QWORD *)*a1;
        a1[2] = v15;
        *((_WORD *)v19 + v15) = 0;
      }
    }
    return a1;
  }
}

```

## disassembly

```asm
0x18003d69c  push    rbx
0x18003d69e  push    rbp
0x18003d69f  push    rsi
0x18003d6a0  push    rdi
0x18003d6a1  push    r12
0x18003d6a3  push    r14
0x18003d6a5  push    r15
0x18003d6a7  sub     rsp, 30h
0x18003d6ab  mov     r14, rdx
0x18003d6ae  mov     r15, r9
0x18003d6b1  mov     rdx, r9
0x18003d6b4  mov     rdi, r8
0x18003d6b7  mov     rbx, rcx
0x18003d6ba  call    ?_Inside@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_NPEBG@Z; std::wstring::_Inside(ushort const *)
0x18003d6bf  test    al, al
0x18003d6c1  jz      short loc_18003D700
0x18003d6c3  cmp     qword ptr [rbx+18h], 8
0x18003d6c8  jb      short loc_18003D6CF
0x18003d6ca  mov     rax, [rbx]
0x18003d6cd  jmp     short loc_18003D6D2
0x18003d6cf  mov     rax, rbx
0x18003d6d2  sub     r15, rax
0x18003d6d5  mov     r9, rbx
0x18003d6d8  mov     rax, [rsp+68h+arg_20]
0x18003d6e0  mov     r8, rdi
0x18003d6e3  sar     r15, 1
0x18003d6e6  mov     rdx, r14
0x18003d6e9  mov     [rsp+68h+var_40], rax
0x18003d6ee  mov     rcx, rbx
0x18003d6f1  mov     [rsp+68h+var_48], r15
0x18003d6f6  call    ?replace@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0AEBV12@00@Z; std::wstring::replace(unsigned __int64,unsigned __int64,std::wstring const &,unsigned __int64,unsigned __int64)
0x18003d6fb  jmp     loc_18003D812
0x18003d700  mov     rcx, [rbx+10h]
0x18003d704  cmp     rcx, r14
0x18003d707  jnb     short loc_18003D716
0x18003d709  lea     rcx, aInvalidStringP; "invalid string position"
0x18003d710  call    ?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18003d716  mov     rsi, [rsp+68h+arg_20]
0x18003d71e  mov     rbp, rcx
0x18003d721  sub     rbp, r14
0x18003d724  mov     rax, rsi
0x18003d727  cmp     rbp, rdi
0x18003d72a  not     rax
0x18003d72d  cmovb   rdi, rbp
0x18003d731  sub     rcx, rdi
0x18003d734  cmp     rax, rcx
0x18003d737  ja      short loc_18003D746
0x18003d739  lea     rcx, aStringTooLong; "string too long"
0x18003d740  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18003d746  sub     rbp, rdi
0x18003d749  cmp     rsi, rdi
0x18003d74c  jnb     short loc_18003D77B
0x18003d74e  cmp     qword ptr [rbx+18h], 8
0x18003d753  jb      short loc_18003D75D
0x18003d755  mov     rcx, [rbx]
0x18003d758  mov     rdx, rcx
0x18003d75b  jmp     short loc_18003D763
0x18003d75d  mov     rcx, rbx
0x18003d760  mov     rdx, rbx
0x18003d763  lea     rax, [r14+rdi]
0x18003d767  mov     r8, rbp
0x18003d76a  lea     rdx, [rdx+rax*2]
0x18003d76e  lea     rax, [r14+rsi]
0x18003d772  lea     rcx, [rcx+rax*2]
0x18003d776  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x18003d77b  test    rsi, rsi
0x18003d77e  jnz     short loc_18003D789
0x18003d780  test    rdi, rdi
0x18003d783  jz      loc_18003D80F
0x18003d789  mov     r12, [rbx+10h]
0x18003d78d  xor     r8d, r8d
0x18003d790  sub     r12, rdi
0x18003d793  mov     rcx, rbx
0x18003d796  add     r12, rsi
0x18003d799  mov     rdx, r12
0x18003d79c  call    ?_Grow@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x18003d7a1  test    al, al
0x18003d7a3  jz      short loc_18003D80F
0x18003d7a5  cmp     rdi, rsi
0x18003d7a8  jnb     short loc_18003D7D7
0x18003d7aa  cmp     qword ptr [rbx+18h], 8
0x18003d7af  jb      short loc_18003D7B9
0x18003d7b1  mov     rcx, [rbx]
0x18003d7b4  mov     rdx, rcx
0x18003d7b7  jmp     short loc_18003D7BF
0x18003d7b9  mov     rcx, rbx
0x18003d7bc  mov     rdx, rbx
0x18003d7bf  lea     rax, [r14+rdi]
0x18003d7c3  mov     r8, rbp
0x18003d7c6  lea     rdx, [rdx+rax*2]
0x18003d7ca  lea     rax, [r14+rsi]
0x18003d7ce  lea     rcx, [rcx+rax*2]
0x18003d7d2  call    ?move@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::move(ushort *,ushort const *,unsigned __int64)
0x18003d7d7  cmp     qword ptr [rbx+18h], 8
0x18003d7dc  jb      short loc_18003D7E3
0x18003d7de  mov     rax, [rbx]
0x18003d7e1  jmp     short loc_18003D7E6
0x18003d7e3  mov     rax, rbx
0x18003d7e6  lea     rcx, [rax+r14*2]
0x18003d7ea  mov     r8, rsi
0x18003d7ed  mov     rdx, r15
0x18003d7f0  call    ?copy@?$char_traits@G@std@@SAPEAGPEAGPEBG_K@Z; std::char_traits<ushort>::copy(ushort *,ushort const *,unsigned __int64)
0x18003d7f5  cmp     qword ptr [rbx+18h], 8
0x18003d7fa  jb      short loc_18003D801
0x18003d7fc  mov     rcx, [rbx]
0x18003d7ff  jmp     short loc_18003D804
0x18003d801  mov     rcx, rbx
0x18003d804  xor     eax, eax
0x18003d806  mov     [rbx+10h], r12
0x18003d80a  mov     [rcx+r12*2], ax
0x18003d80f  mov     rax, rbx
0x18003d812  add     rsp, 30h
0x18003d816  pop     r15
0x18003d818  pop     r14
0x18003d81a  pop     r12
0x18003d81c  pop     rdi
0x18003d81d  pop     rsi
0x18003d81e  pop     rbp
0x18003d81f  pop     rbx
0x18003d820  retn
```
