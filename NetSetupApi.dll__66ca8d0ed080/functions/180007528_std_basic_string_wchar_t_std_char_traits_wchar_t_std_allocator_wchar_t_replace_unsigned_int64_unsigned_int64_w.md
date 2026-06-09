# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::replace(unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)

- ea: `0x180007528`
- end: `0x1800076b0`
- name: `?replace@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K0PEB_W0@Z`
- size: `392`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, unsigned __int64, _BYTE *, unsigned __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180007af4`

## callees

- `0x180007528`
- `0x1800076b8`
- `0x18000797c`
- `0x180008230`
- `0x18000825c`
- `0x180008976`
- `0x18000eacc`
- `0x18000eb38`

## pseudocode

```c
_QWORD *__fastcall std::wstring::replace(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        _BYTE *a4,
        unsigned __int64 a5)
{
  _QWORD *v9; // rax
  unsigned __int64 v11; // rcx
  __int64 v12; // rbp
  _QWORD *v13; // rcx
  _QWORD *v14; // rdx
  unsigned __int64 v15; // r12
  _QWORD *v16; // rcx
  _QWORD *v17; // rdx
  _QWORD *v18; // rax
  _QWORD *v19; // rcx

  if ( std::wstring::_Inside(a1, (unsigned __int64)a4) )
  {
    if ( a1[3] < 8u )
      v9 = a1;
    else
      v9 = (_QWORD *)*a1;
    return std::wstring::replace(a1, a2, a3, a1, (a4 - (_BYTE *)v9) >> 1, a5);
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
      std::char_traits<wchar_t>::move((char *)v13 + 2 * a2 + 2 * a5, (char *)v14 + 2 * a2 + 2 * a3, v12);
    }
    if ( a5 || a3 )
    {
      v15 = a5 + a1[2] - a3;
      if ( std::wstring::_Grow((__int64)a1, v15) )
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
          std::char_traits<wchar_t>::move((char *)v16 + 2 * a2 + 2 * a5, (char *)v17 + 2 * a2 + 2 * a3, v12);
        }
        if ( a1[3] < 8u )
          v18 = a1;
        else
          v18 = (_QWORD *)*a1;
        if ( a5 )
          memcpy_0((char *)v18 + 2 * a2, a4, 2 * a5);
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
0x180007528  push    rbx
0x18000752a  push    rbp
0x18000752b  push    rsi
0x18000752c  push    rdi
0x18000752d  push    r12
0x18000752f  push    r14
0x180007531  push    r15
0x180007533  sub     rsp, 30h
0x180007537  mov     r14, rdx
0x18000753a  mov     r15, r9
0x18000753d  mov     rdx, r9
0x180007540  mov     rdi, r8
0x180007543  mov     rbx, rcx
0x180007546  call    ?_Inside@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA_NPEB_W@Z; std::wstring::_Inside(wchar_t const *)
0x18000754b  test    al, al
0x18000754d  jz      short loc_18000758C
0x18000754f  cmp     qword ptr [rbx+18h], 8
0x180007554  jb      short loc_18000755B
0x180007556  mov     rax, [rbx]
0x180007559  jmp     short loc_18000755E
0x18000755b  mov     rax, rbx
0x18000755e  sub     r15, rax
0x180007561  mov     r9, rbx
0x180007564  mov     rax, [rsp+68h+arg_20]
0x18000756c  mov     r8, rdi
0x18000756f  sar     r15, 1
0x180007572  mov     rdx, r14
0x180007575  mov     [rsp+68h+var_40], rax
0x18000757a  mov     rcx, rbx
0x18000757d  mov     [rsp+68h+var_48], r15
0x180007582  call    ?replace@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K0AEBV12@00@Z; std::wstring::replace(unsigned __int64,unsigned __int64,std::wstring const &,unsigned __int64,unsigned __int64)
0x180007587  jmp     loc_1800076A1
0x18000758c  mov     rcx, [rbx+10h]
0x180007590  cmp     rcx, r14
0x180007593  jnb     short loc_1800075A2
0x180007595  lea     rcx, aInvalidStringP; "invalid string position"
0x18000759c  call    ?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x1800075a2  mov     rsi, [rsp+68h+arg_20]
0x1800075aa  mov     rbp, rcx
0x1800075ad  sub     rbp, r14
0x1800075b0  mov     rax, rsi
0x1800075b3  cmp     rbp, rdi
0x1800075b6  not     rax
0x1800075b9  cmovb   rdi, rbp
0x1800075bd  sub     rcx, rdi
0x1800075c0  cmp     rax, rcx
0x1800075c3  ja      short loc_1800075D2
0x1800075c5  lea     rcx, aStringTooLong; "string too long"
0x1800075cc  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800075d2  sub     rbp, rdi
0x1800075d5  cmp     rsi, rdi
0x1800075d8  jnb     short loc_180007607
0x1800075da  cmp     qword ptr [rbx+18h], 8
0x1800075df  jb      short loc_1800075E9
0x1800075e1  mov     rcx, [rbx]
0x1800075e4  mov     rdx, rcx
0x1800075e7  jmp     short loc_1800075EF
0x1800075e9  mov     rcx, rbx
0x1800075ec  mov     rdx, rbx
0x1800075ef  lea     rax, [r14+rdi]
0x1800075f3  mov     r8, rbp
0x1800075f6  lea     rdx, [rdx+rax*2]
0x1800075fa  lea     rax, [r14+rsi]
0x1800075fe  lea     rcx, [rcx+rax*2]
0x180007602  call    ?move@?$char_traits@_W@std@@SAPEA_WPEA_WPEB_W_K@Z; std::char_traits<wchar_t>::move(wchar_t *,wchar_t const *,unsigned __int64)
0x180007607  test    rsi, rsi
0x18000760a  jnz     short loc_180007615
0x18000760c  test    rdi, rdi
0x18000760f  jz      loc_18000769E
0x180007615  mov     r12, [rbx+10h]
0x180007619  mov     rcx, rbx
0x18000761c  sub     r12, rdi
0x18000761f  add     r12, rsi
0x180007622  mov     rdx, r12
0x180007625  call    ?_Grow@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x18000762a  test    al, al
0x18000762c  jz      short loc_18000769E
0x18000762e  cmp     rdi, rsi
0x180007631  jnb     short loc_180007660
0x180007633  cmp     qword ptr [rbx+18h], 8
0x180007638  jb      short loc_180007642
0x18000763a  mov     rcx, [rbx]
0x18000763d  mov     rdx, rcx
0x180007640  jmp     short loc_180007648
0x180007642  mov     rcx, rbx
0x180007645  mov     rdx, rbx
0x180007648  lea     rax, [r14+rdi]
0x18000764c  mov     r8, rbp
0x18000764f  lea     rdx, [rdx+rax*2]
0x180007653  lea     rax, [r14+rsi]
0x180007657  lea     rcx, [rcx+rax*2]
0x18000765b  call    ?move@?$char_traits@_W@std@@SAPEA_WPEA_WPEB_W_K@Z; std::char_traits<wchar_t>::move(wchar_t *,wchar_t const *,unsigned __int64)
0x180007660  cmp     qword ptr [rbx+18h], 8
0x180007665  jb      short loc_18000766C
0x180007667  mov     rax, [rbx]
0x18000766a  jmp     short loc_18000766F
0x18000766c  mov     rax, rbx
0x18000766f  test    rsi, rsi
0x180007672  jz      short loc_180007684
0x180007674  lea     r8, [rsi+rsi]; Size
0x180007678  mov     rdx, r15; Src
0x18000767b  lea     rcx, [rax+r14*2]; void *
0x18000767f  call    memcpy_0
0x180007684  cmp     qword ptr [rbx+18h], 8
0x180007689  jb      short loc_180007690
0x18000768b  mov     rcx, [rbx]
0x18000768e  jmp     short loc_180007693
0x180007690  mov     rcx, rbx
0x180007693  xor     eax, eax
0x180007695  mov     [rbx+10h], r12
0x180007699  mov     [rcx+r12*2], ax
0x18000769e  mov     rax, rbx
0x1800076a1  add     rsp, 30h
0x1800076a5  pop     r15
0x1800076a7  pop     r14
0x1800076a9  pop     r12
0x1800076ab  pop     rdi
0x1800076ac  pop     rsi
0x1800076ad  pop     rbp
0x1800076ae  pop     rbx
0x1800076af  retn
```
