# Broker::ApplicationIdentity::ApplicationIdentity(Broker::ApplicationIdentity const &)

- ea: `0x18000800c`
- end: `0x1800081fd`
- name: `??0ApplicationIdentity@Broker@@QEAA@AEBU01@@Z`
- size: `497`
- prototype: `__int64 __fastcall(Broker::ApplicationIdentity *__hidden this, const struct Broker::ApplicationIdentity *)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180007be0`
- `0x180009460`
- `0x180013018`

## callees

- `0x1800035f8`
- `0x180004be0`
- `0x18000800c`
- `0x180009640`
- `0x180012d88`
- `0x1800165aa`
- `0x1800165b6`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800081e8`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800081f6`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800081e8`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800081f6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
Broker::ApplicationIdentity *__fastcall Broker::ApplicationIdentity::ApplicationIdentity(
        Broker::ApplicationIdentity *this,
        const struct Broker::ApplicationIdentity *a2)
{
  __int64 v4; // rdx
  _QWORD *v5; // rbx
  unsigned __int64 v6; // rdi
  _QWORD *v7; // rdi
  unsigned __int64 v8; // rbx
  __int64 v10; // rbp
  unsigned __int64 v11; // r10
  void *v12; // rax
  __int64 v13; // rbp
  unsigned __int64 v14; // r10
  void *v15; // rax
  __int64 v16; // rdi
  size_t v17; // rbx

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  v4 = *((_QWORD *)a2 + 1) - *(_QWORD *)a2;
  if ( v4 )
  {
    std::vector<unsigned char>::_Buy_nonzero(this, v4);
    v16 = *(_QWORD *)this;
    v17 = *((_QWORD *)a2 + 1) - *(_QWORD *)a2;
    memmove_0(*(void **)this, *(const void **)a2, v17);
    *((_QWORD *)this + 1) = v17 + v16;
  }
  v5 = (_QWORD *)((char *)a2 + 24);
  *(_OWORD *)((char *)this + 24) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  v6 = *((_QWORD *)a2 + 5);
  if ( *((_QWORD *)a2 + 6) > 7u )
    v5 = (_QWORD *)*v5;
  if ( v6 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v6 > 7 )
  {
    v10 = std::wstring::_Calculate_growth(*((_QWORD *)a2 + 5), 7);
    if ( v10 + 1 > v11 )
      std::_Throw_bad_array_new_length();
    v12 = (void *)std::_Allocate<16,std::_Default_allocate_traits>(2 * (v10 + 1));
    *((_QWORD *)this + 3) = v12;
    *((_QWORD *)this + 5) = v6;
    *((_QWORD *)this + 6) = v10;
    memcpy_0(v12, v5, 2 * v6 + 2);
  }
  else
  {
    *((_QWORD *)this + 5) = v6;
    *((_QWORD *)this + 6) = 7;
    *(_OWORD *)((char *)this + 24) = *(_OWORD *)v5;
  }
  v7 = (_QWORD *)((char *)a2 + 56);
  *(_OWORD *)((char *)this + 56) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  v8 = *((_QWORD *)a2 + 9);
  if ( *((_QWORD *)a2 + 10) > 7u )
    v7 = (_QWORD *)*v7;
  if ( v8 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlength_error("string too long");
  if ( v8 > 7 )
  {
    v13 = std::wstring::_Calculate_growth(*((_QWORD *)a2 + 9), 7);
    if ( v13 + 1 > v14 )
      std::_Throw_bad_array_new_length();
    v15 = (void *)std::_Allocate<16,std::_Default_allocate_traits>(2 * (v13 + 1));
    *((_QWORD *)this + 7) = v15;
    *((_QWORD *)this + 9) = v8;
    *((_QWORD *)this + 10) = v13;
    memcpy_0(v15, v7, 2 * v8 + 2);
  }
  else
  {
    *((_QWORD *)this + 9) = v8;
    *((_QWORD *)this + 10) = 7;
    *(_OWORD *)((char *)this + 56) = *(_OWORD *)v7;
  }
  return this;
}

```

## disassembly

```asm
0x18000800c  mov     [rsp+arg_8], rbx
0x180008011  mov     [rsp+arg_10], rbp
0x180008016  mov     [rsp+arg_0], rcx
0x18000801b  push    rsi
0x18000801c  push    rdi
0x18000801d  push    r13
0x18000801f  push    r14
0x180008021  push    r15
0x180008023  sub     rsp, 20h
0x180008027  mov     r14, rdx
0x18000802a  mov     rsi, rcx
0x18000802d  mov     qword ptr [rcx], 0
0x180008034  mov     qword ptr [rcx+8], 0
0x18000803c  mov     qword ptr [rcx+10h], 0
0x180008044  mov     rdx, [rdx+8]
0x180008048  sub     rdx, [r14]
0x18000804b  jnz     loc_1800081B7
0x180008051  lea     rbx, [r14+18h]
0x180008055  xorps   xmm0, xmm0
0x180008058  movups  xmmword ptr [rsi+18h], xmm0
0x18000805c  mov     qword ptr [rsi+28h], 0
0x180008064  mov     qword ptr [rsi+30h], 0
0x18000806c  mov     rdi, [rbx+10h]
0x180008070  mov     r15d, 7
0x180008076  cmp     [rbx+18h], r15
0x18000807a  jbe     short loc_18000807F
0x18000807c  mov     rbx, [rbx]
0x18000807f  mov     r13, 7FFFFFFFFFFFFFFEh
0x180008089  cmp     rdi, r13
0x18000808c  ja      loc_1800081E1
0x180008092  mov     r10, 7FFFFFFFFFFFFFFFh
0x18000809c  cmp     rdi, r15
0x18000809f  ja      short loc_180008115
0x1800080a1  mov     [rsi+28h], rdi
0x1800080a5  mov     [rsi+30h], r15
0x1800080a9  movups  xmm0, xmmword ptr [rbx]
0x1800080ac  movdqu  xmmword ptr [rsi+18h], xmm0
0x1800080b1  lea     rdi, [r14+38h]
0x1800080b5  xorps   xmm0, xmm0
0x1800080b8  movups  xmmword ptr [rsi+38h], xmm0
0x1800080bc  mov     qword ptr [rsi+48h], 0
0x1800080c4  mov     qword ptr [rsi+50h], 0
0x1800080cc  mov     rbx, [rdi+10h]
0x1800080d0  cmp     [rdi+18h], r15
0x1800080d4  jbe     short loc_1800080D9
0x1800080d6  mov     rdi, [rdi]
0x1800080d9  cmp     rbx, r13
0x1800080dc  ja      loc_1800081EF
0x1800080e2  cmp     rbx, r15
0x1800080e5  ja      loc_18000816B
0x1800080eb  mov     [rsi+48h], rbx
0x1800080ef  mov     [rsi+50h], r15
0x1800080f3  movups  xmm0, xmmword ptr [rdi]
0x1800080f6  movdqu  xmmword ptr [rsi+38h], xmm0
0x1800080fb  mov     rax, rsi
0x1800080fe  mov     rbx, [rsp+48h+arg_8]
0x180008103  mov     rbp, [rsp+48h+arg_10]
0x180008108  add     rsp, 20h
0x18000810c  pop     r15
0x18000810e  pop     r14
0x180008110  pop     r13
0x180008112  pop     rdi
0x180008113  pop     rsi
0x180008114  retn
0x180008115  mov     r8, r13
0x180008118  mov     rdx, r15
0x18000811b  mov     rcx, rdi
0x18000811e  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x180008123  mov     rbp, rax
0x180008126  lea     rcx, [rax+1]
0x18000812a  cmp     rcx, r10
0x18000812d  jbe     short loc_180008135
0x18000812f  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x180008135  add     rcx, rcx
0x180008138  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000813d  mov     [rsi+18h], rax
0x180008141  mov     [rsi+28h], rdi
0x180008145  mov     [rsi+30h], rbp
0x180008149  lea     r8, ds:2[rdi*2]; Size
0x180008151  mov     rdx, rbx; Src
0x180008154  mov     rcx, rax; void *
0x180008157  call    memcpy_0
0x18000815c  mov     r10, 7FFFFFFFFFFFFFFFh
0x180008166  jmp     loc_1800080B1
0x18000816b  mov     r8, r13
0x18000816e  mov     rdx, r15
0x180008171  mov     rcx, rbx
0x180008174  call    ?_Calculate_growth@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@CA_K_K00@Z; std::wstring::_Calculate_growth(unsigned __int64,unsigned __int64,unsigned __int64)
0x180008179  mov     rbp, rax
0x18000817c  lea     rcx, [rax+1]
0x180008180  cmp     rcx, r10
0x180008183  jbe     short loc_18000818B
0x180008185  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x18000818b  add     rcx, rcx
0x18000818e  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180008193  mov     [rsi+38h], rax
0x180008197  mov     [rsi+48h], rbx
0x18000819b  mov     [rsi+50h], rbp
0x18000819f  lea     r8, ds:2[rbx*2]; Size
0x1800081a7  mov     rdx, rdi; Src
0x1800081aa  mov     rcx, rax; void *
0x1800081ad  call    memcpy_0
0x1800081b2  jmp     loc_1800080FB
0x1800081b7  call    ?_Buy_nonzero@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Buy_nonzero(unsigned __int64)
0x1800081bc  mov     rdi, [rsi]
0x1800081bf  mov     rbx, [r14+8]
0x1800081c3  sub     rbx, [r14]
0x1800081c6  mov     r8, rbx; Size
0x1800081c9  mov     rdx, [r14]; Src
0x1800081cc  mov     rcx, rdi; void *
0x1800081cf  call    memmove_0
0x1800081d4  lea     rax, [rbx+rdi]
0x1800081d8  mov     [rsi+8], rax
0x1800081dc  jmp     loc_180008051
0x1800081e1  lea     rcx, aStringTooLong; "string too long"
0x1800081e8  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800081ef  lea     rcx, aStringTooLong; "string too long"
0x1800081f6  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
