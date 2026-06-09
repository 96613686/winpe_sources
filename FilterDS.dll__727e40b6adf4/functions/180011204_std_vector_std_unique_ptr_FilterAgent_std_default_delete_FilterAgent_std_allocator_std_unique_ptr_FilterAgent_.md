# std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>::_Reallocate(unsigned __int64)

- ea: `0x180011204`
- end: `0x1800112ea`
- name: `?_Reallocate@?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@IEAAX_K@Z`
- size: `230`
- prototype: `__int64 *__fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task`

## callers

- `0x1800114c8`

## callees

- `0x180001a30`
- `0x180001bd8`
- `0x18000ef28`
- `0x1800102fc`
- `0x180011204`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001129e`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800112b4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001129e`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800112b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall std::vector<std::unique_ptr<FilterAgent>>::_Reallocate(__int64 a1, unsigned __int64 a2)
{
  _QWORD *v4; // rbx
  _QWORD *v5; // rax
  __int64 **v6; // rsi
  __int64 v7; // rcx
  __int64 *v8; // r14
  __int64 *v9; // r13
  __int64 v10; // r12
  FilterAgent *v11; // rsi
  __int64 *result; // rax
  _QWORD *v13; // [rsp+68h] [rbp+10h]

  v4 = 0;
  v13 = 0;
  if ( a2 )
  {
    if ( a2 > 0x1FFFFFFFFFFFFFFFLL || (v5 = operator new(8 * a2), v4 = v5, (v13 = v5) == 0) )
      std::_Xbad_alloc();
  }
  v6 = (__int64 **)(a1 + 8);
  try
  {
    std::_Uninit_move<std::unique_ptr<FilterAgent> *,std::unique_ptr<FilterAgent> *,std::allocator<std::unique_ptr<FilterAgent>>,std::unique_ptr<FilterAgent>>(
      *(__int64 **)a1,
      *(__int64 **)(a1 + 8),
      v4);
    v8 = *(__int64 **)a1;
    v9 = *v6;
    v10 = ((__int64)*v6 - *(_QWORD *)a1) >> 3;
    if ( *(_QWORD *)a1 )
    {
      if ( v8 != v9 )
      {
        do
        {
          v11 = (FilterAgent *)*v8;
          if ( *v8 )
          {
            FilterAgent::~FilterAgent((FilterAgent *)*v8);
            operator delete(v11);
          }
          ++v8;
        }
        while ( v8 != v9 );
        v6 = (__int64 **)(a1 + 8);
      }
      operator delete(*(void **)a1);
    }
    *(_QWORD *)(a1 + 16) = &v4[a2];
    result = &v4[v10];
    *v6 = result;
    *(_QWORD *)a1 = v4;
  }
  catch ( ... )
  {
    std::_Wrap_alloc<std::allocator<unsigned char>>::deallocate(v7, v13);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180011204  mov     [rsp+arg_0], rbx
0x180011209  mov     [rsp+arg_10], rsi
0x18001120e  push    rdi
0x18001120f  push    r12
0x180011211  push    r13
0x180011213  push    r14
0x180011215  push    r15
0x180011217  sub     rsp, 30h
0x18001121b  mov     r15, rdx
0x18001121e  mov     rdi, rcx
0x180011221  xor     ebx, ebx
0x180011223  mov     [rsp+58h+arg_8], rbx
0x180011228  test    rdx, rdx
0x18001122b  jz      short loc_18001125E
0x18001122d  mov     rax, 1FFFFFFFFFFFFFFFh
0x180011237  cmp     rdx, rax
0x18001123a  ja      loc_1800112E4
0x180011240  lea     rcx, ds:0[rdx*8]; Size
0x180011248  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001124d  mov     rbx, rax
0x180011250  mov     [rsp+58h+arg_8], rax
0x180011255  test    rax, rax
0x180011258  jz      loc_1800112E4
0x18001125e  lea     rsi, [rdi+8]
0x180011262  mov     r8, rbx
0x180011265  mov     rdx, [rsi]
0x180011268  mov     rcx, [rdi]
0x18001126b  call    ??$_Uninit_move@PEAV?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@PEAV12@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@V12@@std@@YAPEAV?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<std::unique_ptr<FilterAgent> *,std::unique_ptr<FilterAgent> *,std::allocator<std::unique_ptr<FilterAgent>>,std::unique_ptr<FilterAgent>>(std::unique_ptr<FilterAgent> *,std::unique_ptr<FilterAgent> *,std::unique_ptr<FilterAgent> *,std::_Wrap_alloc<std::allocator<std::unique_ptr<FilterAgent>>> &,std::unique_ptr<FilterAgent> *,std::_Nonscalar_ptr_iterator_tag)
0x180011270  nop
0x180011271  mov     r14, [rdi]
0x180011274  mov     r13, [rsi]
0x180011277  mov     r12, r13
0x18001127a  sub     r12, r14
0x18001127d  sar     r12, 3
0x180011281  test    r14, r14
0x180011284  jz      short loc_1800112BA
0x180011286  cmp     r14, r13
0x180011289  jz      short loc_1800112B1
0x18001128b  mov     rsi, [r14]
0x18001128e  test    rsi, rsi
0x180011291  jz      short loc_1800112A4
0x180011293  mov     rcx, rsi; this
0x180011296  call    ??1FilterAgent@@QEAA@XZ; FilterAgent::~FilterAgent(void)
0x18001129b  mov     rcx, rsi
0x18001129e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800112a4  add     r14, 8
0x1800112a8  cmp     r14, r13
0x1800112ab  jnz     short loc_18001128B
0x1800112ad  lea     rsi, [rdi+8]
0x1800112b1  mov     rcx, [rdi]
0x1800112b4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800112ba  lea     rax, [rbx+r15*8]
0x1800112be  mov     [rdi+10h], rax
0x1800112c2  lea     rax, [rbx+r12*8]
0x1800112c6  mov     [rsi], rax
0x1800112c9  mov     [rdi], rbx
0x1800112cc  mov     rbx, [rsp+58h+arg_0]
0x1800112d1  mov     rsi, [rsp+58h+arg_10]
0x1800112d6  add     rsp, 30h
0x1800112da  pop     r15
0x1800112dc  pop     r14
0x1800112de  pop     r13
0x1800112e0  pop     r12
0x1800112e2  pop     rdi
0x1800112e3  retn
0x1800112e4  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
