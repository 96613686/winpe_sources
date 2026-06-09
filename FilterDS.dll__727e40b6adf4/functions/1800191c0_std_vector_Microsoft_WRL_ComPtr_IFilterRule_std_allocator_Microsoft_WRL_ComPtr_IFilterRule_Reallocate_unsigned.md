# std::vector<Microsoft::WRL::ComPtr<IFilterRule>,std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>>::_Reallocate(unsigned __int64)

- ea: `0x1800191c0`
- end: `0x1800192a9`
- name: `?_Reallocate@?$vector@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@std@@@std@@IEAAX_K@Z`
- size: `233`
- prototype: `__int64 *__fastcall(void **, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001932c`

## callees

- `0x180001a30`
- `0x180001bd8`
- `0x180017160`
- `0x1800191c0`
- `0x180024010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180019273`
- `msvcrt!??3@YAXPEAX@Z` at `0x180019273`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 *__fastcall std::vector<Microsoft::WRL::ComPtr<IFilterRule>>::_Reallocate(void **a1, unsigned __int64 a2)
{
  _QWORD *v4; // rbx
  __int64 v5; // rcx
  __int64 *v6; // rdi
  __int64 *v7; // r13
  __int64 v8; // r12
  __int64 v9; // rcx
  __int64 **v10; // r14
  __int64 *result; // rax
  _QWORD *v12; // [rsp+68h] [rbp+10h]

  v4 = 0;
  v12 = 0;
  if ( a2 )
  {
    if ( a2 > 0x1FFFFFFFFFFFFFFFLL || (v4 = operator new(8 * a2), (v12 = v4) == 0) )
      std::_Xbad_alloc();
  }
  try
  {
    v10 = (__int64 **)(a1 + 1);
    std::_Uninit_move<Microsoft::WRL::ComPtr<IFilterRule> *,Microsoft::WRL::ComPtr<IFilterRule> *,std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>,Microsoft::WRL::ComPtr<IFilterRule>>(
      *a1,
      a1[1],
      v4);
  }
  catch ( ... )
  {
    std::_Wrap_alloc<std::allocator<unsigned char>>::deallocate(v5, v12);
    throw;
  }
  v6 = (__int64 *)*a1;
  v7 = *v10;
  v8 = ((char *)*v10 - (_BYTE *)*a1) >> 3;
  if ( *a1 )
  {
    if ( v6 != v7 )
    {
      do
      {
        v9 = *v6;
        if ( *v6 )
        {
          *v6 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        }
        ++v6;
      }
      while ( v6 != v7 );
      v10 = (__int64 **)(a1 + 1);
    }
    operator delete(*a1);
  }
  a1[2] = &v4[a2];
  result = &v4[v8];
  *v10 = result;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x1800191c0  mov     [rsp+arg_0], rbx
0x1800191c5  mov     [rsp+arg_10], rsi
0x1800191ca  push    rdi
0x1800191cb  push    r12
0x1800191cd  push    r13
0x1800191cf  push    r14
0x1800191d1  push    r15
0x1800191d3  sub     rsp, 30h
0x1800191d7  mov     r15, rdx
0x1800191da  mov     rsi, rcx
0x1800191dd  xor     ebx, ebx
0x1800191df  mov     [rsp+58h+arg_8], rbx
0x1800191e4  test    rdx, rdx
0x1800191e7  jz      short loc_18001921A
0x1800191e9  mov     rax, 1FFFFFFFFFFFFFFFh
0x1800191f3  cmp     rdx, rax
0x1800191f6  ja      loc_1800192A3
0x1800191fc  lea     rcx, ds:0[rdx*8]; Size
0x180019204  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019209  mov     rbx, rax
0x18001920c  mov     [rsp+58h+arg_8], rax
0x180019211  test    rax, rax
0x180019214  jz      loc_1800192A3
0x18001921a  lea     r14, [rsi+8]
0x18001921e  mov     r8, rbx
0x180019221  mov     rdx, [r14]
0x180019224  mov     rcx, [rsi]
0x180019227  call    ??$_Uninit_move@PEAV?$ComPtr@UIFilterRule@@@WRL@Microsoft@@PEAV123@V?$allocator@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@std@@V123@@std@@YAPEAV?$ComPtr@UIFilterRule@@@WRL@Microsoft@@PEAV123@00AEAU?$_Wrap_alloc@V?$allocator@V?$ComPtr@UIFilterRule@@@WRL@Microsoft@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z; std::_Uninit_move<Microsoft::WRL::ComPtr<IFilterRule> *,Microsoft::WRL::ComPtr<IFilterRule> *,std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>,Microsoft::WRL::ComPtr<IFilterRule>>(Microsoft::WRL::ComPtr<IFilterRule> *,Microsoft::WRL::ComPtr<IFilterRule> *,Microsoft::WRL::ComPtr<IFilterRule> *,std::_Wrap_alloc<std::allocator<Microsoft::WRL::ComPtr<IFilterRule>>> &,Microsoft::WRL::ComPtr<IFilterRule> *,std::_Nonscalar_ptr_iterator_tag)
0x18001922c  nop
0x18001922d  mov     rdi, [rsi]
0x180019230  mov     r13, [r14]
0x180019233  mov     r12, r13
0x180019236  sub     r12, rdi
0x180019239  sar     r12, 3
0x18001923d  test    rdi, rdi
0x180019240  jz      short loc_180019279
0x180019242  cmp     rdi, r13
0x180019245  jz      short loc_180019270
0x180019247  mov     rcx, [rdi]
0x18001924a  test    rcx, rcx
0x18001924d  jz      short loc_180019263
0x18001924f  mov     qword ptr [rdi], 0
0x180019256  mov     rax, [rcx]
0x180019259  mov     rax, [rax+10h]
0x18001925d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019262  nop
0x180019263  add     rdi, 8
0x180019267  cmp     rdi, r13
0x18001926a  jnz     short loc_180019247
0x18001926c  lea     r14, [rsi+8]
0x180019270  mov     rcx, [rsi]
0x180019273  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180019279  lea     rax, [rbx+r15*8]
0x18001927d  mov     [rsi+10h], rax
0x180019281  lea     rax, [rbx+r12*8]
0x180019285  mov     [r14], rax
0x180019288  mov     [rsi], rbx
0x18001928b  mov     rbx, [rsp+58h+arg_0]
0x180019290  mov     rsi, [rsp+58h+arg_10]
0x180019295  add     rsp, 30h
0x180019299  pop     r15
0x18001929b  pop     r14
0x18001929d  pop     r13
0x18001929f  pop     r12
0x1800192a1  pop     rdi
0x1800192a2  retn
0x1800192a3  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
