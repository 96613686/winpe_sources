# std::vector<Windows::UI::Composition::EffectSubgraphInput,std::allocator<Windows::UI::Composition::EffectSubgraphInput>>::_Emplace_reallocate<Windows::UI::Composition::EffectSubgraphInput>(Windows::UI::Composition::EffectSubgraphInput * const,Windows::UI::Composition::EffectSubgraphInput &&)

- ea: `0x180004df4`
- end: `0x180004eca`
- name: `??$_Emplace_reallocate@UEffectSubgraphInput@Composition@UI@Windows@@@?$vector@UEffectSubgraphInput@Composition@UI@Windows@@V?$allocator@UEffectSubgraphInput@Composition@UI@Windows@@@std@@@std@@AEAAPEAUEffectSubgraphInput@Composition@UI@Windows@@QEAU2345@$$QEAU2345@@Z`
- size: `214`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180004550`
- `0x180005440`
- `0x18000ab8c`
- `0x18000b520`

## callees

- `0x180004df4`
- `0x18000ad10`
- `0x18000ad40`
- `0x180016bf0`
- `0x180016c30`
- `0x180021ce0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180004e32`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180004e32`

## pseudocode

```c
char *__fastcall std::vector<Windows::UI::Composition::EffectSubgraphInput>::_Emplace_reallocate<Windows::UI::Composition::EffectSubgraphInput>(
        _QWORD *a1,
        _BYTE *a2,
        _QWORD *a3)
{
  _BYTE *v3; // rbp
  __int64 v6; // rax
  __int64 v8; // r15
  __int64 v9; // r12
  SIZE_T size_of; // rax
  char *v11; // rsi
  char *v12; // r14
  void *v13; // rcx
  _BYTE *v14; // r8
  _BYTE *v15; // rdx
  size_t v16; // r8

  v3 = (_BYTE *)*a1;
  v6 = (__int64)(a1[1] - *a1) >> 3;
  if ( v6 == 0x1FFFFFFFFFFFFFFFLL )
    std::_Xlength_error("vector too long");
  v8 = v6 + 1;
  v9 = std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode>>::_Calculate_growth(a1, v6 + 1);
  size_of = std::_Get_size_of_n<8>(v9);
  v11 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v12 = &v11[8 * ((a2 - v3) >> 3)];
  *(_QWORD *)v12 = *a3;
  v13 = v11;
  v14 = (_BYTE *)a1[1];
  v15 = (_BYTE *)*a1;
  if ( a2 == v14 )
  {
    v16 = v14 - v15;
  }
  else
  {
    memmove_0(v11, v15, (size_t)&a2[-*a1]);
    v13 = v12 + 8;
    v16 = a1[1] - (_QWORD)a2;
    v15 = a2;
  }
  memmove_0(v13, v15, v16);
  std::vector<Windows::Graphics::Effects::IGraphicsEffect *>::_Change_array(a1, v11, v8, v9);
  return &v11[8 * ((a2 - v3) >> 3)];
}

```

## disassembly

```asm
0x180004df4  push    rbx
0x180004df6  push    rbp
0x180004df7  push    rsi
0x180004df8  push    rdi
0x180004df9  push    r12
0x180004dfb  push    r13
0x180004dfd  push    r14
0x180004dff  push    r15
0x180004e01  sub     rsp, 28h
0x180004e05  mov     rbp, [rcx]
0x180004e08  mov     rbx, rcx
0x180004e0b  mov     rax, [rcx+8]
0x180004e0f  mov     r13, r8
0x180004e12  sub     rax, rbp
0x180004e15  mov     rcx, 1FFFFFFFFFFFFFFFh
0x180004e1f  sar     rax, 3
0x180004e23  mov     rdi, rdx
0x180004e26  cmp     rax, rcx
0x180004e29  jnz     short loc_180004E39
0x180004e2b  lea     rcx, aVectorTooLong; "vector too long"
0x180004e32  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180004e39  lea     r15, [rax+1]
0x180004e3d  mov     rcx, rbx
0x180004e40  mov     rdx, r15
0x180004e43  call    ?_Calculate_growth@?$vector@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@@2@@std@@AEBA_K_K@Z; std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode>>::_Calculate_growth(unsigned __int64)
0x180004e48  mov     rcx, rax
0x180004e4b  mov     r12, rax
0x180004e4e  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x180004e53  mov     rcx, rax; dwBytes
0x180004e56  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180004e5b  mov     rcx, rdi
0x180004e5e  mov     rsi, rax
0x180004e61  sub     rcx, rbp
0x180004e64  sar     rcx, 3
0x180004e68  lea     r14, [rax+rcx*8]
0x180004e6c  mov     rcx, [r13+0]
0x180004e70  mov     [r14], rcx
0x180004e73  mov     rcx, rax; void *
0x180004e76  mov     r8, [rbx+8]
0x180004e7a  mov     rdx, [rbx]; Src
0x180004e7d  cmp     rdi, r8
0x180004e80  jnz     short loc_180004E87
0x180004e82  sub     r8, rdx
0x180004e85  jmp     short loc_180004EA0
0x180004e87  mov     r8, rdi
0x180004e8a  sub     r8, [rbx]; Size
0x180004e8d  call    memmove_0
0x180004e92  mov     r8, [rbx+8]
0x180004e96  lea     rcx, [r14+8]; void *
0x180004e9a  sub     r8, rdi; Size
0x180004e9d  mov     rdx, rdi; Src
0x180004ea0  call    memmove_0
0x180004ea5  mov     r9, r12
0x180004ea8  mov     r8, r15
0x180004eab  mov     rdx, rsi
0x180004eae  mov     rcx, rbx
0x180004eb1  call    ?_Change_array@?$vector@PEAUIGraphicsEffect@Effects@Graphics@Windows@@V?$allocator@PEAUIGraphicsEffect@Effects@Graphics@Windows@@@std@@@std@@AEAAXQEAPEAUIGraphicsEffect@Effects@Graphics@Windows@@_K1@Z; std::vector<Windows::Graphics::Effects::IGraphicsEffect *>::_Change_array(Windows::Graphics::Effects::IGraphicsEffect * * const,unsigned __int64,unsigned __int64)
0x180004eb6  mov     rax, r14
0x180004eb9  add     rsp, 28h
0x180004ebd  pop     r15
0x180004ebf  pop     r14
0x180004ec1  pop     r13
0x180004ec3  pop     r12
0x180004ec5  pop     rdi
0x180004ec6  pop     rsi
0x180004ec7  pop     rbp
0x180004ec8  pop     rbx
0x180004ec9  retn
```
