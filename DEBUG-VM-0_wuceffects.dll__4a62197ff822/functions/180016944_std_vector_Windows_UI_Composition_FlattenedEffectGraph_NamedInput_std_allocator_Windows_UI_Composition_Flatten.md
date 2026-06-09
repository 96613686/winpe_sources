# std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput,std::allocator<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>>::_Emplace_reallocate<>(Windows::UI::Composition::FlattenedEffectGraph::NamedInput * const)

- ea: `0x180016944`
- end: `0x180016a08`
- name: `??$_Emplace_reallocate@$$V@?$vector@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@AEAAPEAUNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@QEAU23456@@Z`
- size: `196`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180009730`

## callees

- `0x18000ad40`
- `0x18000adc0`
- `0x180016944`
- `0x180016a10`
- `0x180016a48`
- `0x180016a90`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180016979`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180016979`

## pseudocode

```c
_QWORD *__fastcall std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>::_Emplace_reallocate<>(
        __int64 *a1,
        __int64 a2)
{
  __int64 v2; // rsi
  __int64 v5; // rax
  __int64 v6; // rbp
  __int64 v7; // r14
  SIZE_T size_of; // rax
  __int64 v9; // r8
  _QWORD *v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // r11

  v2 = *a1;
  v5 = (a1[1] - *a1) >> 4;
  if ( v5 == 0xFFFFFFFFFFFFFFFLL )
    std::_Xlength_error("vector too long");
  v6 = v5 + 1;
  v7 = std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>::_Calculate_growth(a1, v5 + 1);
  size_of = std::_Get_size_of_n<16>(v7);
  v9 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v10 = (_QWORD *)(((a2 - v2) & 0xFFFFFFFFFFFFFFF0uLL) + v9);
  v10[1] = 0;
  *v10 = 0;
  v11 = a1[1];
  v12 = *a1;
  if ( a2 != v11 )
  {
    std::_Uninitialized_move<Windows::UI::Composition::FlattenedEffectGraph::NamedInput *>(v12, a2, v9);
    v11 = a1[1];
    v9 = (__int64)(v10 + 2);
    v12 = a2;
  }
  std::_Uninitialized_move<Windows::UI::Composition::FlattenedEffectGraph::NamedInput *>(v12, v11, v9);
  std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>::_Change_array((__int64)a1, v13, v6, v7);
  return v10;
}

```

## disassembly

```asm
0x180016944  push    rbx
0x180016946  push    rbp
0x180016947  push    rsi
0x180016948  push    rdi
0x180016949  push    r14
0x18001694b  sub     rsp, 20h
0x18001694f  mov     rsi, [rcx]
0x180016952  mov     rbx, rcx
0x180016955  mov     rax, [rcx+8]
0x180016959  mov     rdi, rdx
0x18001695c  sub     rax, rsi
0x18001695f  mov     rcx, 0FFFFFFFFFFFFFFFh
0x180016969  sar     rax, 4
0x18001696d  cmp     rax, rcx
0x180016970  jnz     short loc_180016980
0x180016972  lea     rcx, aVectorTooLong; "vector too long"
0x180016979  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180016980  lea     rbp, [rax+1]
0x180016984  mov     rcx, rbx
0x180016987  mov     rdx, rbp
0x18001698a  call    ?_Calculate_growth@?$vector@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@AEBA_K_K@Z; std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>::_Calculate_growth(unsigned __int64)
0x18001698f  mov     rcx, rax
0x180016992  mov     r14, rax
0x180016995  call    ??$_Get_size_of_n@$0BA@@std@@YA_K_K@Z; std::_Get_size_of_n<16>(unsigned __int64)
0x18001699a  mov     rcx, rax; dwBytes
0x18001699d  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800169a2  mov     rcx, rdi
0x1800169a5  mov     r11, rax
0x1800169a8  sub     rcx, rsi
0x1800169ab  mov     r8, rax
0x1800169ae  and     rcx, 0FFFFFFFFFFFFFFF0h
0x1800169b2  lea     rsi, [rcx+rax]
0x1800169b6  mov     qword ptr [rsi+8], 0
0x1800169be  mov     qword ptr [rsi], 0
0x1800169c5  mov     rdx, [rbx+8]
0x1800169c9  mov     rcx, [rbx]
0x1800169cc  cmp     rdi, rdx
0x1800169cf  jz      short loc_1800169E4
0x1800169d1  mov     rdx, rdi
0x1800169d4  call    ??$_Uninitialized_move@PEAUNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@YAPEAUNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@QEAU12345@0PEAU12345@AEAV?$allocator@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_move<Windows::UI::Composition::FlattenedEffectGraph::NamedInput *>(Windows::UI::Composition::FlattenedEffectGraph::NamedInput * const,Windows::UI::Composition::FlattenedEffectGraph::NamedInput * const,Windows::UI::Composition::FlattenedEffectGraph::NamedInput *,std::allocator<Windows::UI::Composition::FlattenedEffectGraph::NamedInput> &)
0x1800169d9  mov     rdx, [rbx+8]
0x1800169dd  lea     r8, [rsi+10h]
0x1800169e1  mov     rcx, rdi
0x1800169e4  call    ??$_Uninitialized_move@PEAUNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@YAPEAUNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@QEAU12345@0PEAU12345@AEAV?$allocator@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_move<Windows::UI::Composition::FlattenedEffectGraph::NamedInput *>(Windows::UI::Composition::FlattenedEffectGraph::NamedInput * const,Windows::UI::Composition::FlattenedEffectGraph::NamedInput * const,Windows::UI::Composition::FlattenedEffectGraph::NamedInput *,std::allocator<Windows::UI::Composition::FlattenedEffectGraph::NamedInput> &)
0x1800169e9  mov     r9, r14
0x1800169ec  mov     r8, rbp
0x1800169ef  mov     rdx, r11
0x1800169f2  mov     rcx, rbx
0x1800169f5  call    ?_Change_array@?$vector@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@V?$allocator@UNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@@std@@@std@@AEAAXQEAUNamedInput@FlattenedEffectGraph@Composition@UI@Windows@@_K1@Z; std::vector<Windows::UI::Composition::FlattenedEffectGraph::NamedInput>::_Change_array(Windows::UI::Composition::FlattenedEffectGraph::NamedInput * const,unsigned __int64,unsigned __int64)
0x1800169fa  mov     rax, rsi
0x1800169fd  add     rsp, 20h
0x180016a01  pop     r14
0x180016a03  pop     rdi
0x180016a04  pop     rsi
0x180016a05  pop     rbp
0x180016a06  pop     rbx
0x180016a07  retn
```
