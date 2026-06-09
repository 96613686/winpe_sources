# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::replace(unsigned __int64,unsigned __int64,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,unsigned __int64,unsigned __int64)

- ea: `0x1800076b8`
- end: `0x180007974`
- name: `?replace@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K0AEBV12@00@Z`
- size: `700`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, unsigned __int64, _QWORD *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180007528`

## callees

- `0x1800076b8`
- `0x18000797c`
- `0x180008230`
- `0x18000825c`
- `0x180008976`
- `0x18000eacc`

## pseudocode

```c
_QWORD *__fastcall std::wstring::replace(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        _QWORD *a4,
        unsigned __int64 a5,
        unsigned __int64 a6)
{
  _QWORD *v7; // r15
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rbp
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // r14
  unsigned __int64 v13; // rsi
  unsigned __int64 v14; // rax
  __int64 v15; // r12
  unsigned __int64 v16; // rax
  _QWORD *v17; // rcx
  _QWORD *v18; // rdx
  _QWORD *v19; // rax
  _QWORD *v20; // rax
  _QWORD *v21; // rcx
  _QWORD *v22; // rcx
  _QWORD *v23; // rdx
  __int64 v24; // r8
  char *v25; // rdx
  char *v26; // rcx
  _QWORD *v27; // rcx
  _QWORD *v28; // rdx
  _QWORD *v29; // rax
  _QWORD *v30; // rcx
  unsigned __int64 v31; // r15
  _QWORD *v32; // rcx
  _QWORD *v33; // rax
  _QWORD *v34; // rax
  _QWORD *v35; // rcx
  __int64 v36; // r15
  _QWORD *v37; // rax
  _QWORD *v38; // rcx
  _QWORD *v39; // rcx
  _QWORD *v40; // rdx
  _QWORD *v41; // rcx
  unsigned __int64 v43; // [rsp+70h] [rbp+8h]

  v7 = a4;
  v8 = a1[2];
  v9 = a3;
  if ( v8 < a2 || (v11 = a4[2], v12 = a5, v11 < a5) )
    std::_Xout_of_range("invalid string position");
  v13 = a6;
  if ( v8 - a2 < a3 )
    v9 = v8 - a2;
  v14 = v11 - a5;
  if ( v14 < a6 )
    v13 = v14;
  if ( ~v13 <= v8 - v9 )
    std::_Xlength_error("string too long");
  v15 = v8 - a2 - v9;
  v43 = v8 + v13 - v9;
  if ( v8 < v43 )
    std::wstring::_Grow((__int64)a1, v8 + v13 - v9);
  v16 = a1[3];
  if ( a1 == v7 )
  {
    if ( v13 > v9 )
    {
      if ( a5 > a2 )
      {
        v31 = a2 + v9;
        if ( a2 + v9 > a5 )
        {
          if ( v16 < 8 )
          {
            v34 = a1;
            v35 = a1;
          }
          else
          {
            v34 = (_QWORD *)*a1;
            v35 = (_QWORD *)*a1;
          }
          std::char_traits<wchar_t>::move((char *)v34 + 2 * a2, (char *)v35 + 2 * a5, v9);
          v36 = 2 * v31;
          if ( a1[3] < 8u )
          {
            v38 = a1;
            v37 = a1;
          }
          else
          {
            v37 = (_QWORD *)*a1;
            v38 = (_QWORD *)*a1;
          }
          std::char_traits<wchar_t>::move((char *)v38 + 2 * a2 + 2 * v13, (char *)v37 + v36, v15);
          if ( a1[3] < 8u )
          {
            v39 = a1;
            v40 = a1;
          }
          else
          {
            v39 = (_QWORD *)*a1;
            v40 = (_QWORD *)*a1;
          }
          v26 = (char *)v39 + v36;
          v25 = (char *)v40 + 2 * a5 + 2 * v13;
          v24 = v13 - v9;
          goto LABEL_56;
        }
        if ( v16 < 8 )
        {
          v32 = a1;
          v33 = a1;
        }
        else
        {
          v32 = (_QWORD *)*a1;
          v33 = (_QWORD *)*a1;
        }
        std::char_traits<wchar_t>::move((char *)v32 + 2 * a2 + 2 * v13, (char *)v33 + 2 * v31, v15);
        if ( a1[3] < 8u )
        {
          v29 = a1;
          v30 = a1;
        }
        else
        {
          v29 = (_QWORD *)*a1;
          v30 = (_QWORD *)*a1;
        }
        v12 = v13 + a5 - v9;
      }
      else
      {
        if ( v16 < 8 )
        {
          v27 = a1;
          v28 = a1;
        }
        else
        {
          v27 = (_QWORD *)*a1;
          v28 = (_QWORD *)*a1;
        }
        std::char_traits<wchar_t>::move((char *)v27 + 2 * a2 + 2 * v13, (char *)v28 + 2 * a2 + 2 * v9, v15);
        if ( a1[3] < 8u )
        {
          v29 = a1;
          v30 = a1;
        }
        else
        {
          v29 = (_QWORD *)*a1;
          v30 = (_QWORD *)*a1;
        }
      }
      v25 = (char *)v30 + 2 * v12;
      v24 = v13;
      v26 = (char *)v29 + 2 * a2;
    }
    else
    {
      if ( v16 < 8 )
      {
        v20 = a1;
        v21 = a1;
      }
      else
      {
        v20 = (_QWORD *)*a1;
        v21 = (_QWORD *)*a1;
      }
      std::char_traits<wchar_t>::move((char *)v20 + 2 * a2, (char *)v21 + 2 * a5, v13);
      if ( a1[3] < 8u )
      {
        v22 = a1;
        v23 = a1;
      }
      else
      {
        v22 = (_QWORD *)*a1;
        v23 = (_QWORD *)*a1;
      }
      v24 = v15;
      v25 = (char *)v23 + 2 * a2 + 2 * v9;
      v26 = (char *)v22 + 2 * a2 + 2 * v13;
    }
LABEL_56:
    std::char_traits<wchar_t>::move(v26, v25, v24);
    goto LABEL_57;
  }
  if ( v16 < 8 )
  {
    v17 = a1;
    v18 = a1;
  }
  else
  {
    v17 = (_QWORD *)*a1;
    v18 = (_QWORD *)*a1;
  }
  std::char_traits<wchar_t>::move((char *)v17 + 2 * a2 + 2 * v13, (char *)v18 + 2 * a2 + 2 * v9, v15);
  if ( v7[3] >= 8u )
    v7 = (_QWORD *)*v7;
  if ( a1[3] < 8u )
    v19 = a1;
  else
    v19 = (_QWORD *)*a1;
  if ( v13 )
    memcpy_0((char *)v19 + 2 * a2, (char *)v7 + 2 * a5, 2 * v13);
LABEL_57:
  if ( a1[3] < 8u )
    v41 = a1;
  else
    v41 = (_QWORD *)*a1;
  a1[2] = v43;
  *((_WORD *)v41 + v43) = 0;
  return a1;
}

```

## disassembly

```asm
0x1800076b8  push    rbx
0x1800076ba  push    rbp
0x1800076bb  push    rsi
0x1800076bc  push    rdi
0x1800076bd  push    r12
0x1800076bf  push    r13
0x1800076c1  push    r14
0x1800076c3  push    r15
0x1800076c5  sub     rsp, 28h
0x1800076c9  mov     rdi, rdx
0x1800076cc  mov     r15, r9
0x1800076cf  mov     rdx, [rcx+10h]
0x1800076d3  mov     rbp, r8
0x1800076d6  mov     rbx, rcx
0x1800076d9  cmp     rdx, rdi
0x1800076dc  jb      loc_180007967
0x1800076e2  mov     rax, [r9+10h]
0x1800076e6  mov     r14, [rsp+68h+arg_20]
0x1800076ee  cmp     rax, r14
0x1800076f1  jb      loc_180007967
0x1800076f7  mov     rsi, [rsp+68h+arg_28]
0x1800076ff  mov     r12, rdx
0x180007702  sub     r12, rdi
0x180007705  mov     rcx, rdx
0x180007708  cmp     r12, r8
0x18000770b  cmovb   rbp, r12
0x18000770f  sub     rax, r14
0x180007712  cmp     rax, rsi
0x180007715  cmovb   rsi, rax
0x180007719  sub     rcx, rbp
0x18000771c  mov     rax, rsi
0x18000771f  not     rax
0x180007722  cmp     rax, rcx
0x180007725  ja      short loc_180007734
0x180007727  lea     rcx, aStringTooLong; "string too long"
0x18000772e  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180007734  mov     r13, rsi
0x180007737  sub     r12, rbp
0x18000773a  sub     r13, rbp
0x18000773d  lea     rax, [rdx+r13]
0x180007741  mov     [rsp+68h+arg_0], rax
0x180007746  cmp     rdx, rax
0x180007749  jnb     short loc_180007756
0x18000774b  mov     rdx, rax
0x18000774e  mov     rcx, rbx
0x180007751  call    ?_Grow@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA_N_K_N@Z; std::wstring::_Grow(unsigned __int64,bool)
0x180007756  mov     rax, [rbx+18h]
0x18000775a  cmp     rbx, r15
0x18000775d  jz      short loc_1800077C3
0x18000775f  cmp     rax, 8
0x180007763  jb      short loc_18000776D
0x180007765  mov     rcx, [rbx]
0x180007768  mov     rdx, rcx
0x18000776b  jmp     short loc_180007773
0x18000776d  mov     rcx, rbx
0x180007770  mov     rdx, rbx
0x180007773  lea     rax, [rdi+rbp]
0x180007777  mov     r8, r12
0x18000777a  lea     rdx, [rdx+rax*2]
0x18000777e  lea     rax, [rdi+rsi]
0x180007782  lea     rcx, [rcx+rax*2]
0x180007786  call    ?move@?$char_traits@_W@std@@SAPEA_WPEA_WPEB_W_K@Z; std::char_traits<wchar_t>::move(wchar_t *,wchar_t const *,unsigned __int64)
0x18000778b  cmp     qword ptr [r15+18h], 8
0x180007790  jb      short loc_180007795
0x180007792  mov     r15, [r15]
0x180007795  cmp     qword ptr [rbx+18h], 8
0x18000779a  jb      short loc_1800077A1
0x18000779c  mov     rax, [rbx]
0x18000779f  jmp     short loc_1800077A4
0x1800077a1  mov     rax, rbx
0x1800077a4  test    rsi, rsi
0x1800077a7  jz      loc_180007935
0x1800077ad  lea     r8, [rsi+rsi]; Size
0x1800077b1  lea     rdx, [r15+r14*2]; Src
0x1800077b5  lea     rcx, [rax+rdi*2]; void *
0x1800077b9  call    memcpy_0
0x1800077be  jmp     loc_180007935
0x1800077c3  cmp     rsi, rbp
0x1800077c6  ja      short loc_180007819
0x1800077c8  cmp     rax, 8
0x1800077cc  jb      short loc_1800077D6
0x1800077ce  mov     rax, [rbx]
0x1800077d1  mov     rcx, rax
0x1800077d4  jmp     short loc_1800077DC
0x1800077d6  mov     rax, rbx
0x1800077d9  mov     rcx, rbx
0x1800077dc  lea     rdx, [rcx+r14*2]
0x1800077e0  mov     r8, rsi
0x1800077e3  lea     rcx, [rax+rdi*2]
0x1800077e7  call    ?move@?$char_traits@_W@std@@SAPEA_WPEA_WPEB_W_K@Z; std::char_traits<wchar_t>::move(wchar_t *,wchar_t const *,unsigned __int64)
0x1800077ec  cmp     qword ptr [rbx+18h], 8
0x1800077f1  jb      short loc_1800077FB
0x1800077f3  mov     rcx, [rbx]
0x1800077f6  mov     rdx, rcx
0x1800077f9  jmp     short loc_180007801
0x1800077fb  mov     rcx, rbx
0x1800077fe  mov     rdx, rbx
0x180007801  lea     rax, [rdi+rbp]
0x180007805  mov     r8, r12
0x180007808  lea     rdx, [rdx+rax*2]
0x18000780c  lea     rax, [rdi+rsi]
0x180007810  lea     rcx, [rcx+rax*2]
0x180007814  jmp     loc_180007930
0x180007819  cmp     r14, rdi
0x18000781c  ja      short loc_18000786F
0x18000781e  cmp     rax, 8
0x180007822  jb      short loc_18000782C
0x180007824  mov     rcx, [rbx]
0x180007827  mov     rdx, rcx
0x18000782a  jmp     short loc_180007832
0x18000782c  mov     rcx, rbx
0x18000782f  mov     rdx, rbx
0x180007832  lea     rax, [rdi+rbp]
0x180007836  mov     r8, r12
0x180007839  lea     rdx, [rdx+rax*2]
0x18000783d  lea     rax, [rdi+rsi]
0x180007841  lea     rcx, [rcx+rax*2]
0x180007845  call    ?move@?$char_traits@_W@std@@SAPEA_WPEA_WPEB_W_K@Z; std::char_traits<wchar_t>::move(wchar_t *,wchar_t const *,unsigned __int64)
0x18000784a  cmp     qword ptr [rbx+18h], 8
0x18000784f  jb      short loc_180007859
0x180007851  mov     rax, [rbx]
0x180007854  mov     rcx, rax
0x180007857  jmp     short loc_18000785F
0x180007859  mov     rax, rbx
0x18000785c  mov     rcx, rbx
0x18000785f  lea     rdx, [rcx+r14*2]
0x180007863  mov     r8, rsi
0x180007866  lea     rcx, [rax+rdi*2]
0x18000786a  jmp     loc_180007930
0x18000786f  lea     r15, [rdi+rbp]
0x180007873  cmp     r15, r14
0x180007876  ja      short loc_1800078BD
0x180007878  cmp     rax, 8
0x18000787c  jb      short loc_180007886
0x18000787e  mov     rcx, [rbx]
0x180007881  mov     rax, rcx
0x180007884  jmp     short loc_18000788C
0x180007886  mov     rcx, rbx
0x180007889  mov     rax, rbx
0x18000788c  lea     rdx, [rax+r15*2]
0x180007890  mov     r8, r12
0x180007893  lea     rax, [rdi+rsi]
0x180007897  lea     rcx, [rcx+rax*2]
0x18000789b  call    ?move@?$char_traits@_W@std@@SAPEA_WPEA_WPEB_W_K@Z; std::char_traits<wchar_t>::move(wchar_t *,wchar_t const *,unsigned __int64)
0x1800078a0  cmp     qword ptr [rbx+18h], 8
0x1800078a5  jb      short loc_1800078AF
0x1800078a7  mov     rax, [rbx]
0x1800078aa  mov     rcx, rax
0x1800078ad  jmp     short loc_1800078B5
0x1800078af  mov     rax, rbx
0x1800078b2  mov     rcx, rbx
0x1800078b5  sub     r14, rbp
0x1800078b8  add     r14, rsi
0x1800078bb  jmp     short loc_18000785F
0x1800078bd  cmp     rax, 8
0x1800078c1  jb      short loc_1800078CB
0x1800078c3  mov     rax, [rbx]
0x1800078c6  mov     rcx, rax
0x1800078c9  jmp     short loc_1800078D1
0x1800078cb  mov     rax, rbx
0x1800078ce  mov     rcx, rbx
0x1800078d1  lea     rdx, [rcx+r14*2]
0x1800078d5  mov     r8, rbp
0x1800078d8  lea     rcx, [rax+rdi*2]
0x1800078dc  call    ?move@?$char_traits@_W@std@@SAPEA_WPEA_WPEB_W_K@Z; std::char_traits<wchar_t>::move(wchar_t *,wchar_t const *,unsigned __int64)
0x1800078e1  add     r15, r15
0x1800078e4  cmp     qword ptr [rbx+18h], 8
0x1800078e9  jb      short loc_1800078F3
0x1800078eb  mov     rax, [rbx]
0x1800078ee  mov     rcx, rax
0x1800078f1  jmp     short loc_1800078F9
0x1800078f3  mov     rcx, rbx
0x1800078f6  mov     rax, rbx
0x1800078f9  lea     rdx, [r15+rax]
0x1800078fd  mov     r8, r12
0x180007900  lea     rax, [rdi+rsi]
0x180007904  lea     rcx, [rcx+rax*2]
0x180007908  call    ?move@?$char_traits@_W@std@@SAPEA_WPEA_WPEB_W_K@Z; std::char_traits<wchar_t>::move(wchar_t *,wchar_t const *,unsigned __int64)
0x18000790d  cmp     qword ptr [rbx+18h], 8
0x180007912  jb      short loc_18000791C
0x180007914  mov     rcx, [rbx]
0x180007917  mov     rdx, rcx
0x18000791a  jmp     short loc_180007922
0x18000791c  mov     rcx, rbx
0x18000791f  mov     rdx, rbx
0x180007922  lea     rax, [r14+rsi]
0x180007926  add     rcx, r15
0x180007929  lea     rdx, [rdx+rax*2]
0x18000792d  mov     r8, r13
0x180007930  call    ?move@?$char_traits@_W@std@@SAPEA_WPEA_WPEB_W_K@Z; std::char_traits<wchar_t>::move(wchar_t *,wchar_t const *,unsigned __int64)
0x180007935  cmp     qword ptr [rbx+18h], 8
0x18000793a  jb      short loc_180007941
0x18000793c  mov     rcx, [rbx]
0x18000793f  jmp     short loc_180007944
0x180007941  mov     rcx, rbx
0x180007944  mov     rdx, [rsp+68h+arg_0]
0x180007949  xor     eax, eax
0x18000794b  mov     [rbx+10h], rdx
0x18000794f  mov     [rcx+rdx*2], ax
0x180007953  mov     rax, rbx
0x180007956  add     rsp, 28h
0x18000795a  pop     r15
0x18000795c  pop     r14
0x18000795e  pop     r13
0x180007960  pop     r12
0x180007962  pop     rdi
0x180007963  pop     rsi
0x180007964  pop     rbp
0x180007965  pop     rbx
0x180007966  retn
0x180007967  lea     rcx, aInvalidStringP; "invalid string position"
0x18000796e  call    ?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
```
