# std::vector<std::unique_ptr<FilterBasicParameter,std::default_delete<FilterBasicParameter>>,std::allocator<std::unique_ptr<FilterBasicParameter,std::default_delete<FilterBasicParameter>>>>::_Reallocate(unsigned __int64)

- ea: `0x1800112f0`
- end: `0x1800113d5`
- name: `?_Reallocate@?$vector@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@@2@@std@@IEAAX_K@Z`
- size: `229`
- prototype: `__int64 *__fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18001161c`

## callees

- `0x180001a30`
- `0x180001bd8`
- `0x180010340`
- `0x1800112f0`
- `0x180024010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001139f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001139f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall std::vector<std::unique_ptr<FilterBasicParameter>>::_Reallocate(__int64 a1, unsigned __int64 a2)
{
  _QWORD *v4; // rbx
  _QWORD *v5; // rax
  __int64 **v6; // rsi
  __int64 v7; // rcx
  __int64 *v8; // r14
  __int64 *v9; // r13
  __int64 v10; // r12
  __int64 *result; // rax
  _QWORD *v12; // [rsp+68h] [rbp+10h]

  v4 = 0;
  v12 = 0;
  if ( a2 )
  {
    if ( a2 > 0x1FFFFFFFFFFFFFFFLL || (v5 = operator new(8 * a2), v4 = v5, (v12 = v5) == 0) )
      std::_Xbad_alloc();
  }
  v6 = (__int64 **)(a1 + 8);
  try
  {
    std::_Uninit_move<std::unique_ptr<FilterBasicParameter> *,std::unique_ptr<FilterBasicParameter> *,std::allocator<std::unique_ptr<FilterBasicParameter>>,std::unique_ptr<FilterBasicParameter>>(
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
          if ( *v8 )
            (**(void (__fastcall ***)(__int64, __int64))*v8)(*v8, 1);
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
    std::_Wrap_alloc<std::allocator<unsigned char>>::deallocate(v7, v12);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x1800112f0  mov     [rsp+arg_0], rbx
0x1800112f5  mov     [rsp+arg_10], rsi
0x1800112fa  push    rdi
0x1800112fb  push    r12
0x1800112fd  push    r13
0x1800112ff  push    r14
0x180011301  push    r15
0x180011303  sub     rsp, 30h
0x180011307  mov     r15, rdx
0x18001130a  mov     rdi, rcx
0x18001130d  xor     ebx, ebx
0x18001130f  mov     [rsp+58h+arg_8], rbx
0x180011314  test    rdx, rdx
0x180011317  jz      short loc_18001134A
0x180011319  mov     rax, 1FFFFFFFFFFFFFFFh
0x180011323  cmp     rdx, rax
0x180011326  ja      loc_1800113CF
0x18001132c  lea     rcx, ds:0[rdx*8]; Size
0x180011334  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011339  mov     rbx, rax
0x18001133c  mov     [rsp+58h+arg_8], rax
0x180011341  test    rax, rax
0x180011344  jz      loc_1800113CF
0x18001134a  lea     rsi, [rdi+8]
0x18001134e  mov     r8, rbx
0x180011351  mov     rdx, [rsi]
0x180011354  mov     rcx, [rdi]
0x180011357  call    ??$_Uninit_move@PEAV?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@PEAV12@V?$allocator@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@@2@V12@@std@@YAPEAV?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@V?$allocator@V?$unique_ptr@VFilterBasicParameter@@U?$default_delete@VFilterBasicParameter@@@std@@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<std::unique_ptr<FilterBasicParameter> *,std::unique_ptr<FilterBasicParameter> *,std::allocator<std::unique_ptr<FilterBasicParameter>>,std::unique_ptr<FilterBasicParameter>>(std::unique_ptr<FilterBasicParameter> *,std::unique_ptr<FilterBasicParameter> *,std::unique_ptr<FilterBasicParameter> *,std::_Wrap_alloc<std::allocator<std::unique_ptr<FilterBasicParameter>>> &,std::unique_ptr<FilterBasicParameter> *,std::_Nonscalar_ptr_iterator_tag)
0x18001135c  nop
0x18001135d  mov     r14, [rdi]
0x180011360  mov     r13, [rsi]
0x180011363  mov     r12, r13
0x180011366  sub     r12, r14
0x180011369  sar     r12, 3
0x18001136d  test    r14, r14
0x180011370  jz      short loc_1800113A5
0x180011372  cmp     r14, r13
0x180011375  jz      short loc_18001139C
0x180011377  mov     rcx, [r14]
0x18001137a  test    rcx, rcx
0x18001137d  jz      short loc_18001138F
0x18001137f  mov     rax, [rcx]
0x180011382  mov     edx, 1
0x180011387  mov     rax, [rax]
0x18001138a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001138f  add     r14, 8
0x180011393  cmp     r14, r13
0x180011396  jnz     short loc_180011377
0x180011398  lea     rsi, [rdi+8]
0x18001139c  mov     rcx, [rdi]
0x18001139f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800113a5  lea     rax, [rbx+r15*8]
0x1800113a9  mov     [rdi+10h], rax
0x1800113ad  lea     rax, [rbx+r12*8]
0x1800113b1  mov     [rsi], rax
0x1800113b4  mov     [rdi], rbx
0x1800113b7  mov     rbx, [rsp+58h+arg_0]
0x1800113bc  mov     rsi, [rsp+58h+arg_10]
0x1800113c1  add     rsp, 30h
0x1800113c5  pop     r15
0x1800113c7  pop     r14
0x1800113c9  pop     r13
0x1800113cb  pop     r12
0x1800113cd  pop     rdi
0x1800113ce  retn
0x1800113cf  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
