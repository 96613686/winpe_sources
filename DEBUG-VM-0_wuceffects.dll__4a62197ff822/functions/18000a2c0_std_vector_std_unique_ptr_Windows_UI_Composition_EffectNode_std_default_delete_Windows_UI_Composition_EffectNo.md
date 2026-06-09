# std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode,std::default_delete<Windows::UI::Composition::EffectNode>>,std::allocator<std::unique_ptr<Windows::UI::Composition::EffectNode,std::default_delete<Windows::UI::Composition::EffectNode>>>>::reserve(unsigned __int64)

- ea: `0x18000a2c0`
- end: `0x18000a3f2`
- name: `?reserve@?$vector@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@@2@@std@@QEAAX_K@Z`
- size: `306`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009730`

## callees

- `0x18000a2c0`
- `0x18000a6d0`
- `0x18000ad10`
- `0x18000ad40`
- `0x180021084`
- `0x1800257b8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a3d0`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000a3d0`

## pseudocode

```c
unsigned __int64 __fastcall std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode>>::reserve(
        __int64 a1,
        unsigned __int64 a2)
{
  __int64 *v4; // rcx
  unsigned __int64 result; // rax
  __int64 v6; // r15
  SIZE_T size_of; // rax
  __int64 v8; // rax
  __int64 *v9; // r8
  __int64 v10; // r14
  __int64 v11; // rdx
  __int64 *i; // rax
  __int64 v13; // rcx
  __int64 *v14; // rbx
  __int64 *j; // rsi
  _QWORD *v16; // rcx
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // [rsp+50h] [rbp+8h] BYREF
  void *v19; // [rsp+58h] [rbp+10h] BYREF

  v4 = *(__int64 **)a1;
  result = (__int64)(*(_QWORD *)(a1 + 16) - (_QWORD)v4) >> 3;
  if ( a2 > result )
  {
    if ( a2 > 0x1FFFFFFFFFFFFFFFLL )
      std::_Xlength_error("vector too long");
    v6 = (__int64)(*(_QWORD *)(a1 + 8) - (_QWORD)v4) >> 3;
    size_of = std::_Get_size_of_n<8>(a2);
    v8 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    v9 = *(__int64 **)(a1 + 8);
    v10 = v8;
    v11 = v8;
    for ( i = *(__int64 **)a1; i != v9; *(_QWORD *)(v11 - 8) = v13 )
    {
      v13 = *i;
      v11 += 8;
      *i++ = 0;
    }
    v14 = *(__int64 **)a1;
    if ( *(_QWORD *)a1 )
    {
      for ( j = *(__int64 **)(a1 + 8); v14 != j; ++v14 )
        std::unique_ptr<Windows::UI::Composition::EffectNode>::~unique_ptr<Windows::UI::Composition::EffectNode>((_QWORD **)v14);
      v16 = *(_QWORD **)a1;
      v17 = (*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) & 0xFFFFFFFFFFFFFFF8uLL;
      v19 = *(void **)a1;
      v18 = v17;
      if ( v17 >= 0x1000 )
      {
        std::_Adjust_manually_vector_aligned(&v19, &v18);
        v16 = v19;
      }
      operator delete(v16);
    }
    *(_QWORD *)a1 = v10;
    *(_QWORD *)(a1 + 8) = v10 + 8 * v6;
    result = v10 + 8 * a2;
    *(_QWORD *)(a1 + 16) = result;
  }
  return result;
}

```

## disassembly

```asm
0x18000a2c0  push    rbp
0x18000a2c2  push    rdi
0x18000a2c3  sub     rsp, 38h
0x18000a2c7  mov     rdi, rcx
0x18000a2ca  mov     rbp, rdx
0x18000a2cd  mov     rcx, [rcx]
0x18000a2d0  mov     rax, [rdi+10h]
0x18000a2d4  sub     rax, rcx
0x18000a2d7  sar     rax, 3
0x18000a2db  cmp     rdx, rax
0x18000a2de  jbe     loc_18000A3C2
0x18000a2e4  mov     rax, 1FFFFFFFFFFFFFFFh
0x18000a2ee  cmp     rdx, rax
0x18000a2f1  ja      loc_18000A3C9
0x18000a2f7  mov     [rsp+48h+arg_10], rbx
0x18000a2fc  mov     [rsp+48h+var_20], r14
0x18000a301  mov     [rsp+48h+var_28], r15
0x18000a306  mov     r15, [rdi+8]
0x18000a30a  sub     r15, rcx
0x18000a30d  mov     rcx, rdx
0x18000a310  sar     r15, 3
0x18000a314  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18000a319  mov     rcx, rax; dwBytes
0x18000a31c  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000a321  mov     r8, [rdi+8]
0x18000a325  mov     r14, rax
0x18000a328  mov     rdx, rax
0x18000a32b  mov     rax, [rdi]
0x18000a32e  cmp     rax, r8
0x18000a331  jz      short loc_18000A34E
0x18000a333  mov     rcx, [rax]
0x18000a336  lea     rdx, [rdx+8]
0x18000a33a  mov     qword ptr [rax], 0
0x18000a341  add     rax, 8
0x18000a345  mov     [rdx-8], rcx
0x18000a349  cmp     rax, r8
0x18000a34c  jnz     short loc_18000A333
0x18000a34e  mov     rbx, [rdi]
0x18000a351  test    rbx, rbx
0x18000a354  jz      short loc_18000A3A0
0x18000a356  mov     [rsp+48h+var_18], rsi
0x18000a35b  mov     rsi, [rdi+8]
0x18000a35f  cmp     rbx, rsi
0x18000a362  jz      short loc_18000A375
0x18000a364  mov     rcx, rbx
0x18000a367  call    ??1?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::UI::Composition::EffectNode>::~unique_ptr<Windows::UI::Composition::EffectNode>(void)
0x18000a36c  add     rbx, 8
0x18000a370  cmp     rbx, rsi
0x18000a373  jnz     short loc_18000A364
0x18000a375  mov     rcx, [rdi]; void *
0x18000a378  mov     rdx, [rdi+10h]
0x18000a37c  mov     rsi, [rsp+48h+var_18]
0x18000a381  sub     rdx, rcx
0x18000a384  and     rdx, 0FFFFFFFFFFFFFFF8h; unsigned __int64
0x18000a388  mov     [rsp+48h+arg_8], rcx
0x18000a38d  mov     [rsp+48h+arg_0], rdx
0x18000a392  cmp     rdx, 1000h
0x18000a399  jnb     short loc_18000A3D7
0x18000a39b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000a3a0  mov     rbx, [rsp+48h+arg_10]
0x18000a3a5  lea     rax, [r14+r15*8]
0x18000a3a9  mov     r15, [rsp+48h+var_28]
0x18000a3ae  mov     [rdi], r14
0x18000a3b1  mov     [rdi+8], rax
0x18000a3b5  lea     rax, [r14+rbp*8]
0x18000a3b9  mov     r14, [rsp+48h+var_20]
0x18000a3be  mov     [rdi+10h], rax
0x18000a3c2  add     rsp, 38h
0x18000a3c6  pop     rdi
0x18000a3c7  pop     rbp
0x18000a3c8  retn
0x18000a3c9  lea     rcx, aVectorTooLong; "vector too long"
0x18000a3d0  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000a3d7  lea     rdx, [rsp+48h+arg_0]; unsigned __int64 *
0x18000a3dc  lea     rcx, [rsp+48h+arg_8]; void **
0x18000a3e1  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x18000a3e6  mov     rdx, [rsp+48h+arg_0]
0x18000a3eb  mov     rcx, [rsp+48h+arg_8]
0x18000a3f0  jmp     short loc_18000A39B
```
