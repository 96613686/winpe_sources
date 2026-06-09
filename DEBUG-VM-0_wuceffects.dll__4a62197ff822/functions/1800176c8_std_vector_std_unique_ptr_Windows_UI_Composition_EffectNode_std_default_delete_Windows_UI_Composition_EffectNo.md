# std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode,std::default_delete<Windows::UI::Composition::EffectNode>>,std::allocator<std::unique_ptr<Windows::UI::Composition::EffectNode,std::default_delete<Windows::UI::Composition::EffectNode>>>>::_Emplace_reallocate<>(std::unique_ptr<Windows::UI::Composition::EffectNode,std::default_delete<Windows::UI::Composition::EffectNode>> * const)

- ea: `0x1800176c8`
- end: `0x1800177e6`
- name: `??$_Emplace_reallocate@$$V@?$vector@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@1@QEAV21@@Z`
- size: `286`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180009730`

## callees

- `0x18000a280`
- `0x18000a620`
- `0x18000ad10`
- `0x18000ad40`
- `0x180016bf0`
- `0x1800176c8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017701`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017701`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode>>::_Emplace_reallocate<>(
        __int64 **a1,
        __int64 *a2)
{
  __int64 *v2; // rdi
  __int64 v5; // rax
  __int64 v6; // rbp
  __int64 v7; // r12
  SIZE_T size_of; // rax
  __int64 v9; // r14
  _QWORD *v10; // r15
  _QWORD *v11; // rcx
  __int64 *v12; // r8
  __int64 *v13; // rdx
  _QWORD *v14; // rdi
  __int64 v15; // rax
  _QWORD *v16; // rdx
  __int64 v17; // rax
  __int64 *v18; // rcx
  __int64 v19; // rax

  v2 = *a1;
  v5 = a1[1] - *a1;
  if ( v5 == 0x1FFFFFFFFFFFFFFFLL )
    std::_Xlength_error("vector too long");
  v6 = v5 + 1;
  v7 = std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode>>::_Calculate_growth(a1, v5 + 1);
  size_of = std::_Get_size_of_n<8>(v7);
  v9 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v10 = (_QWORD *)(v9 + 8 * (a2 - v2));
  v11 = (_QWORD *)v9;
  *v10 = 0;
  v12 = a1[1];
  v13 = *a1;
  if ( a2 == v12 )
  {
    while ( v13 != v12 )
    {
      v15 = *v13;
      *v13 = 0;
      *v11++ = v15;
      ++v13;
    }
    v16 = v11;
  }
  else
  {
    v14 = v10 + 1;
    while ( v13 != a2 )
    {
      v17 = *v13;
      *v13 = 0;
      *v11++ = v17;
      ++v13;
    }
    std::_Destroy_range<std::allocator<std::unique_ptr<Windows::UI::Composition::EffectNode>>>(v11, v11);
    v18 = a1[1];
    while ( a2 != v18 )
    {
      v19 = *a2;
      *a2 = 0;
      *v14++ = v19;
      ++a2;
    }
    v16 = v14;
    v11 = v14;
  }
  std::_Destroy_range<std::allocator<std::unique_ptr<Windows::UI::Composition::EffectNode>>>(v11, v16);
  std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode>>::_Change_array(a1, v9, v6, v7);
  return v10;
}

```

## disassembly

```asm
0x1800176c8  push    rbx
0x1800176ca  push    rbp
0x1800176cb  push    rsi
0x1800176cc  push    rdi
0x1800176cd  push    r12
0x1800176cf  push    r14
0x1800176d1  push    r15
0x1800176d3  sub     rsp, 20h
0x1800176d7  mov     rdi, [rcx]
0x1800176da  mov     rsi, rcx
0x1800176dd  mov     rax, [rcx+8]
0x1800176e1  mov     rbx, rdx
0x1800176e4  sub     rax, rdi
0x1800176e7  mov     rcx, 1FFFFFFFFFFFFFFFh
0x1800176f1  sar     rax, 3
0x1800176f5  cmp     rax, rcx
0x1800176f8  jnz     short loc_180017708
0x1800176fa  lea     rcx, aVectorTooLong; "vector too long"
0x180017701  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180017708  lea     rbp, [rax+1]
0x18001770c  mov     rcx, rsi
0x18001770f  mov     rdx, rbp
0x180017712  call    ?_Calculate_growth@?$vector@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@@2@@std@@AEBA_K_K@Z; std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode>>::_Calculate_growth(unsigned __int64)
0x180017717  mov     rcx, rax
0x18001771a  mov     r12, rax
0x18001771d  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x180017722  mov     rcx, rax; dwBytes
0x180017725  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001772a  mov     rcx, rbx
0x18001772d  mov     r14, rax
0x180017730  sub     rcx, rdi
0x180017733  sar     rcx, 3
0x180017737  lea     r15, [rax+rcx*8]
0x18001773b  mov     rcx, rax
0x18001773e  mov     qword ptr [r15], 0
0x180017745  mov     r8, [rsi+8]
0x180017749  mov     rdx, [rsi]
0x18001774c  cmp     rbx, r8
0x18001774f  jz      short loc_18001776C
0x180017751  lea     rdi, [r15+8]
0x180017755  jmp     short loc_18001778B
0x180017757  mov     rax, [rdx]
0x18001775a  mov     qword ptr [rdx], 0
0x180017761  mov     [rcx], rax
0x180017764  add     rcx, 8
0x180017768  add     rdx, 8
0x18001776c  cmp     rdx, r8
0x18001776f  jnz     short loc_180017757
0x180017771  mov     rdx, rcx
0x180017774  jmp     short loc_1800177BE
0x180017776  mov     rax, [rdx]
0x180017779  mov     qword ptr [rdx], 0
0x180017780  mov     [rcx], rax
0x180017783  add     rcx, 8
0x180017787  add     rdx, 8
0x18001778b  cmp     rdx, rbx
0x18001778e  jnz     short loc_180017776
0x180017790  mov     rdx, rcx
0x180017793  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<Windows::UI::Composition::EffectNode>>>(std::unique_ptr<Windows::UI::Composition::EffectNode> *,std::unique_ptr<Windows::UI::Composition::EffectNode> * const,std::allocator<std::unique_ptr<Windows::UI::Composition::EffectNode>> &)
0x180017798  mov     rcx, [rsi+8]
0x18001779c  jmp     short loc_1800177B3
0x18001779e  mov     rax, [rbx]
0x1800177a1  mov     qword ptr [rbx], 0
0x1800177a8  mov     [rdi], rax
0x1800177ab  add     rdi, 8
0x1800177af  add     rbx, 8
0x1800177b3  cmp     rbx, rcx
0x1800177b6  jnz     short loc_18001779E
0x1800177b8  mov     rdx, rdi
0x1800177bb  mov     rcx, rdi
0x1800177be  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<Windows::UI::Composition::EffectNode>>>(std::unique_ptr<Windows::UI::Composition::EffectNode> *,std::unique_ptr<Windows::UI::Composition::EffectNode> * const,std::allocator<std::unique_ptr<Windows::UI::Composition::EffectNode>> &)
0x1800177c3  mov     r9, r12
0x1800177c6  mov     r8, rbp
0x1800177c9  mov     rdx, r14
0x1800177cc  mov     rcx, rsi
0x1800177cf  call    ?_Change_array@?$vector@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@@2@@std@@AEAAXQEAV?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@2@_K1@Z; std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode>>::_Change_array(std::unique_ptr<Windows::UI::Composition::EffectNode> * const,unsigned __int64,unsigned __int64)
0x1800177d4  mov     rax, r15
0x1800177d7  add     rsp, 20h
0x1800177db  pop     r15
0x1800177dd  pop     r14
0x1800177df  pop     r12
0x1800177e1  pop     rdi
0x1800177e2  pop     rsi
0x1800177e3  pop     rbp
0x1800177e4  pop     rbx
0x1800177e5  retn
```
