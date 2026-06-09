# std::vector<Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater,std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater>>::_Emplace_reallocate<Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater &>(Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater * const,Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater &)

- ea: `0x180003c28`
- end: `0x180003dae`
- name: `??$_Emplace_reallocate@AEAUConstantBufferUpdater@CompiledEffectSubgraph@Composition@UI@Windows@@@?$vector@UConstantBufferUpdater@CompiledEffectSubgraph@Composition@UI@Windows@@V?$allocator@UConstantBufferUpdater@CompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@AEAAPEAUConstantBufferUpdater@CompiledEffectSubgraph@Composition@UI@Windows@@QEAU23456@AEAU23456@@Z`
- size: `390`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180003804`

## callees

- `0x180002b6c`
- `0x180003c28`
- `0x18000a88c`
- `0x18000ad40`
- `0x18001afe4`
- `0x18001b21c`
- `0x18001ed08`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180003c71`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180003c71`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_DWORD *__fastcall std::vector<Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater>::_Emplace_reallocate<Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater &>(
        __int64 *a1,
        __int64 a2,
        _DWORD *a3)
{
  unsigned __int64 v6; // r9
  __int64 v7; // rdi
  __int64 v8; // r15
  unsigned __int64 v9; // r14
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  SIZE_T size_of; // rax
  __int64 v13; // rsi
  _DWORD *v14; // r15
  __int64 v15; // rdx
  _DWORD *v16; // r8
  __int64 v17; // rcx

  v6 = 0x8E38E38E38E38E39uLL * ((a1[1] - *a1) >> 3);
  v7 = 0x38E38E38E38E38ELL;
  if ( v6 == 0x38E38E38E38E38ELL )
    std::_Xlength_error("vector too long");
  v8 = (a2 - *a1) / 72;
  v9 = v6 + 1;
  v10 = 0x8E38E38E38E38E39uLL * ((a1[2] - *a1) >> 3);
  v11 = (0x8E38E38E38E38E39uLL * ((a1[2] - *a1) >> 3)) >> 1;
  if ( v10 <= 0x38E38E38E38E38ELL - v11 )
  {
    v7 = v11 + v10;
    if ( v11 + v10 < v9 )
      v7 = v6 + 1;
  }
  size_of = std::_Get_size_of_n<72>(v7);
  v13 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v14 = (_DWORD *)(v13 + 72 * v8);
  *v14 = *a3;
  v14[1] = a3[1];
  std::function<void (void const *,void *)>::function<void (void const *,void *)>(v14 + 2, a3 + 2);
  v15 = a1[1];
  v16 = (_DWORD *)v13;
  v17 = *a1;
  if ( a2 != v15 )
  {
    std::_Uninitialized_move<Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater *>(v17, a2, v13);
    v16 = v14 + 18;
    v15 = a1[1];
    v17 = a2;
  }
  std::_Uninitialized_move<Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater *>(v17, v15, v16);
  if ( *a1 )
  {
    std::_Destroy_range<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater>>(
      *a1,
      a1[1]);
    std::_Deallocate<16>(*a1, 8 * ((a1[2] - *a1) >> 3));
  }
  *a1 = v13;
  a1[1] = v13 + 72 * v9;
  a1[2] = v13 + 72 * v7;
  return v14;
}

```

## disassembly

```asm
0x180003c28  push    rbx
0x180003c2a  push    rbp
0x180003c2b  push    rsi
0x180003c2c  push    rdi
0x180003c2d  push    r12
0x180003c2f  push    r13
0x180003c31  push    r14
0x180003c33  push    r15
0x180003c35  sub     rsp, 58h
0x180003c39  mov     r13, r8
0x180003c3c  mov     rbp, rdx
0x180003c3f  mov     rbx, rcx
0x180003c42  mov     r9, [rcx+8]
0x180003c46  sub     r9, [rcx]
0x180003c49  sar     r9, 3
0x180003c4d  mov     r8, 8E38E38E38E38E39h
0x180003c57  imul    r9, r8
0x180003c5b  mov     rdi, 38E38E38E38E38Eh
0x180003c65  cmp     r9, rdi
0x180003c68  jnz     short loc_180003C78
0x180003c6a  lea     rcx, aVectorTooLong; "vector too long"
0x180003c71  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180003c78  mov     rcx, rbp
0x180003c7b  sub     rcx, [rbx]
0x180003c7e  mov     rax, 0E38E38E38E38E39h
0x180003c88  imul    rcx
0x180003c8b  mov     r15, rdx
0x180003c8e  sar     r15, 2
0x180003c92  mov     rax, r15
0x180003c95  shr     rax, 3Fh
0x180003c99  add     r15, rax
0x180003c9c  lea     r14, [r9+1]
0x180003ca0  mov     rcx, [rbx+10h]
0x180003ca4  sub     rcx, [rbx]
0x180003ca7  sar     rcx, 3
0x180003cab  imul    rcx, r8
0x180003caf  mov     rdx, rcx
0x180003cb2  shr     rdx, 1
0x180003cb5  mov     rax, rdi
0x180003cb8  sub     rax, rdx
0x180003cbb  cmp     rcx, rax
0x180003cbe  ja      short loc_180003CCB
0x180003cc0  lea     rdi, [rdx+rcx]
0x180003cc4  cmp     rdi, r14
0x180003cc7  cmovb   rdi, r14
0x180003ccb  mov     rcx, rdi
0x180003cce  call    ??$_Get_size_of_n@$0EI@@std@@YA_K_K@Z; std::_Get_size_of_n<72>(unsigned __int64)
0x180003cd3  mov     rcx, rax; dwBytes
0x180003cd6  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180003cdb  mov     rsi, rax
0x180003cde  lea     rcx, [r15+r15*8]
0x180003ce2  lea     r15, [rax+rcx*8]
0x180003ce6  lea     r12, [r15+48h]
0x180003cea  mov     [rsp+98h+var_78], rbx
0x180003cef  mov     [rsp+98h+var_70], rax
0x180003cf4  mov     [rsp+98h+var_68], rdi
0x180003cf9  mov     [rsp+98h+var_60], r12
0x180003cfe  mov     [rsp+98h+var_58], r12
0x180003d03  mov     ecx, [r13+0]
0x180003d07  mov     [r15], ecx
0x180003d0a  mov     ecx, [r13+4]
0x180003d0e  mov     [r15+4], ecx
0x180003d12  lea     rdx, [r13+8]
0x180003d16  lea     rcx, [r15+8]
0x180003d1a  call    ??0?$function@$$A6AXPEBXPEAX@Z@std@@QEAA@AEBV01@@Z; std::function<void (void const *,void *)>::function<void (void const *,void *)>(std::function<void (void const *,void *)> const &)
0x180003d1f  mov     rdx, [rbx+8]
0x180003d23  mov     r8, rsi
0x180003d26  mov     rcx, [rbx]
0x180003d29  cmp     rbp, rdx
0x180003d2c  jz      short loc_180003D40
0x180003d2e  mov     rdx, rbp
0x180003d31  call    ??$_Uninitialized_move@PEAUConstantBufferUpdater@CompiledEffectSubgraph@Composition@UI@Windows@@V?$allocator@UConstantBufferUpdater@CompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@YAPEAUConstantBufferUpdater@CompiledEffectSubgraph@Composition@UI@Windows@@QEAU12345@0PEAU12345@AEAV?$allocator@UConstantBufferUpdater@CompiledEffectSubgraph@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_move<Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater *>(Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater * const,Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater * const,Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater *,std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater> &)
0x180003d36  mov     r8, r12
0x180003d39  mov     rdx, [rbx+8]
0x180003d3d  mov     rcx, rbp
0x180003d40  call    ??$_Uninitialized_move@PEAUConstantBufferUpdater@CompiledEffectSubgraph@Composition@UI@Windows@@V?$allocator@UConstantBufferUpdater@CompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@YAPEAUConstantBufferUpdater@CompiledEffectSubgraph@Composition@UI@Windows@@QEAU12345@0PEAU12345@AEAV?$allocator@UConstantBufferUpdater@CompiledEffectSubgraph@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_move<Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater *>(Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater * const,Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater * const,Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater *,std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater> &)
0x180003d45  mov     rcx, [rbx]
0x180003d48  test    rcx, rcx
0x180003d4b  jz      short loc_180003D7F
0x180003d4d  mov     rdx, [rbx+8]
0x180003d51  call    ??$_Destroy_range@V?$allocator@UConstantBufferUpdater@CompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@YAXPEAUConstantBufferUpdater@CompiledEffectSubgraph@Composition@UI@Windows@@QEAU12345@AEAV?$allocator@UConstantBufferUpdater@CompiledEffectSubgraph@Composition@UI@Windows@@@0@@Z; std::_Destroy_range<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater>>(Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater *,Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater * const,std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::ConstantBufferUpdater> &)
0x180003d56  mov     rax, [rbx+10h]
0x180003d5a  sub     rax, [rbx]
0x180003d5d  sar     rax, 3
0x180003d61  mov     rcx, 8E38E38E38E38E39h
0x180003d6b  imul    rax, rcx
0x180003d6f  lea     rdx, [rax+rax*8]
0x180003d73  shl     rdx, 3
0x180003d77  mov     rcx, [rbx]
0x180003d7a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180003d7f  mov     [rbx], rsi
0x180003d82  lea     rcx, [r14+r14*8]
0x180003d86  lea     rdx, [rsi+rcx*8]
0x180003d8a  mov     [rbx+8], rdx
0x180003d8e  lea     rcx, [rdi+rdi*8]
0x180003d92  lea     rdx, [rsi+rcx*8]
0x180003d96  mov     [rbx+10h], rdx
0x180003d9a  mov     rax, r15
0x180003d9d  add     rsp, 58h
0x180003da1  pop     r15
0x180003da3  pop     r14
0x180003da5  pop     r13
0x180003da7  pop     r12
0x180003da9  pop     rdi
0x180003daa  pop     rsi
0x180003dab  pop     rbp
0x180003dac  pop     rbx
0x180003dad  retn
```
