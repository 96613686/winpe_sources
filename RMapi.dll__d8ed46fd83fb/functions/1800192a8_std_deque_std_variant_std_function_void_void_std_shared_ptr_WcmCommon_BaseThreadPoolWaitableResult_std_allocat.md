# std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>,std::allocator<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>>::_Growmap(unsigned __int64)

- ea: `0x1800192a8`
- end: `0x1800193fd`
- name: `?_Growmap@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAX_K@Z`
- size: `341`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180018094`
- `0x18001a094`
- `0x18001a1d8`
- `0x18001a31c`
- `0x18001b3d4`

## callees

- `0x180007c1c`
- `0x18000a6a0`
- `0x18000b490`
- `0x18000df40`
- `0x18000df4c`
- `0x1800192a8`
- `0x18001963c`

## pseudocode

```c
void *__fastcall std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Growmap(
        _QWORD *a1)
{
  unsigned __int64 v2; // rsi
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rdi
  __int64 size_of; // rax
  char *v6; // r14
  __int64 v7; // r15
  char *v8; // r12
  unsigned __int64 v9; // rax
  __int64 v10; // rax
  unsigned __int64 v11; // rsi
  size_t v12; // rbx
  const void *v13; // rdx
  char *v14; // rbx
  size_t v15; // r8
  char *v16; // rcx
  void *result; // rax
  __int64 v18; // rcx

  v2 = 1;
  v3 = a1[2];
  if ( v3 )
    v2 = v3;
  while ( v2 == v3 || v2 < 8 )
  {
    if ( 0x38E38E38E38E38ELL - v2 < v2 )
      std::deque<std::function<void (void)>>::_Xlen();
    v2 *= 2LL;
  }
  v4 = a1[3];
  size_of = std::_Get_size_of_n<8>(v2);
  v6 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v7 = 8 * v4;
  v8 = &v6[8 * v4];
  v9 = v2 >> 1;
  while ( v2 <= v9 )
    v2 *= 2LL;
  v10 = a1[2];
  v11 = v2 - v10;
  v12 = 8 * v10 - v7;
  memmove_0(v8, (const void *)(a1[1] + v7), v12);
  v13 = (const void *)a1[1];
  v14 = &v8[v12];
  if ( v4 > v11 )
  {
    memmove_0(v14, v13, 8 * v11);
    memmove_0(v6, (const void *)(8 * v11 + a1[1]), v7 - 8 * v11);
    v16 = &v6[v7 - 8 * v11];
    v15 = 8 * v11;
  }
  else
  {
    memmove_0(v14, v13, 8 * v4);
    memset_0(&v14[v7], 0, 8 * (v11 - v4));
    v15 = 8 * v4;
    v16 = v6;
  }
  result = memset_0(v16, 0, v15);
  v18 = a1[1];
  if ( v18 )
    result = (void *)std::_Deallocate<16>(v18, 8LL * a1[2]);
  a1[2] += v11;
  a1[1] = v6;
  return result;
}

```

## disassembly

```asm
0x1800192a8  mov     [rsp+arg_8], rbx
0x1800192ad  mov     [rsp+arg_10], rbp
0x1800192b2  push    rsi
0x1800192b3  push    rdi
0x1800192b4  push    r12
0x1800192b6  push    r14
0x1800192b8  push    r15
0x1800192ba  sub     rsp, 20h
0x1800192be  mov     rbp, rcx
0x1800192c1  mov     esi, 1
0x1800192c6  mov     rcx, [rcx+10h]
0x1800192ca  test    rcx, rcx
0x1800192cd  cmovnz  rsi, rcx
0x1800192d1  mov     rax, rsi
0x1800192d4  sub     rax, rcx
0x1800192d7  cmp     rax, 1
0x1800192db  jb      short loc_1800192E3
0x1800192dd  cmp     rsi, 8
0x1800192e1  jnb     short loc_1800192FE
0x1800192e3  mov     rax, 38E38E38E38E38Eh
0x1800192ed  sub     rax, rsi
0x1800192f0  cmp     rax, rsi
0x1800192f3  jb      loc_1800193F7
0x1800192f9  add     rsi, rsi
0x1800192fc  jmp     short loc_1800192D1
0x1800192fe  mov     rdi, [rbp+18h]
0x180019302  mov     rcx, rsi
0x180019305  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18001930a  mov     rcx, rax
0x18001930d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180019312  mov     r14, rax
0x180019315  lea     r15, ds:0[rdi*8]
0x18001931d  lea     r12, [r15+rax]
0x180019321  mov     rax, rsi
0x180019324  shr     rax, 1
0x180019327  jmp     short loc_18001932C
0x180019329  add     rsi, rsi
0x18001932c  cmp     rsi, rax
0x18001932f  jbe     short loc_180019329
0x180019331  mov     rcx, [rbp+8]
0x180019335  mov     rax, [rbp+10h]
0x180019339  sub     rsi, rax
0x18001933c  shl     rax, 3
0x180019340  lea     rdx, [rcx+r15]; Src
0x180019344  sub     rax, rdx
0x180019347  lea     rbx, [rax+rcx]
0x18001934b  mov     rcx, r12; void *
0x18001934e  mov     r8, rbx; Size
0x180019351  call    memmove_0
0x180019356  mov     rdx, [rbp+8]; Src
0x18001935a  add     rbx, r12
0x18001935d  mov     rcx, rbx; void *
0x180019360  cmp     rdi, rsi
0x180019363  ja      short loc_18001938A
0x180019365  mov     r8, r15; Size
0x180019368  call    memmove_0
0x18001936d  mov     r8, rsi
0x180019370  lea     rcx, [rbx+r15]; void *
0x180019374  sub     r8, rdi
0x180019377  xor     edx, edx; Val
0x180019379  shl     r8, 3; Size
0x18001937d  call    memset_0
0x180019382  mov     r8, r15
0x180019385  mov     rcx, r14
0x180019388  jmp     short loc_1800193BB
0x18001938a  lea     rdi, ds:0[rsi*8]
0x180019392  mov     r8, rdi; Size
0x180019395  call    memmove_0
0x18001939a  mov     rax, [rbp+8]
0x18001939e  mov     rcx, r14; void *
0x1800193a1  lea     rdx, [rdi+rax]; Src
0x1800193a5  sub     rax, rdx
0x1800193a8  lea     rbx, [rax+r15]
0x1800193ac  mov     r8, rbx; Size
0x1800193af  call    memmove_0
0x1800193b4  lea     rcx, [rbx+r14]; void *
0x1800193b8  mov     r8, rdi; Size
0x1800193bb  xor     edx, edx; Val
0x1800193bd  call    memset_0
0x1800193c2  mov     rcx, [rbp+8]
0x1800193c6  test    rcx, rcx
0x1800193c9  jz      short loc_1800193D8
0x1800193cb  mov     rdx, [rbp+10h]
0x1800193cf  shl     rdx, 3
0x1800193d3  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800193d8  add     [rbp+10h], rsi
0x1800193dc  mov     rbx, [rsp+48h+arg_8]
0x1800193e1  mov     [rbp+8], r14
0x1800193e5  mov     rbp, [rsp+48h+arg_10]
0x1800193ea  add     rsp, 20h
0x1800193ee  pop     r15
0x1800193f0  pop     r14
0x1800193f2  pop     r12
0x1800193f4  pop     rdi
0x1800193f5  pop     rsi
0x1800193f6  retn
0x1800193f7  call    ?_Xlen@?$deque@V?$function@$$A6AXXZ@std@@V?$allocator@V?$function@$$A6AXXZ@std@@@2@@std@@CAXXZ; std::deque<std::function<void (void)>>::_Xlen(void)
```
