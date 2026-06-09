# std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode,std::default_delete<Windows::UI::Composition::EffectNode>>,std::allocator<std::unique_ptr<Windows::UI::Composition::EffectNode,std::default_delete<Windows::UI::Composition::EffectNode>>>>::_Emplace_reallocate<std::unique_ptr<Windows::UI::Composition::EffectNode,std::default_delete<Windows::UI::Composition::EffectNode>>>(std::unique_ptr<Windows::UI::Composition::EffectNode,std::default_delete<Windows::UI::Composition::EffectNode>> * const,std::unique_ptr<Windows::UI::Composition::EffectNode,std::default_delete<Windows::UI::Composition::EffectNode>> &&)

- ea: `0x180004ed0`
- end: `0x180004ff3`
- name: `??$_Emplace_reallocate@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@@?$vector@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@1@QEAV21@$$QEAV21@@Z`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180005ce0`

## callees

- `0x180004ed0`
- `0x18000a280`
- `0x18000a620`
- `0x18000ad10`
- `0x18000ad40`
- `0x180016bf0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180004f0e`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180004f0e`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode>>::_Emplace_reallocate<std::unique_ptr<Windows::UI::Composition::EffectNode>>(
        __int64 **a1,
        __int64 *a2,
        __int64 *a3)
{
  __int64 *v3; // rdi
  __int64 v6; // rax
  __int64 v8; // r12
  __int64 v9; // r13
  SIZE_T size_of; // rax
  __int64 v11; // r14
  _QWORD *v12; // rbp
  __int64 v13; // rcx
  _QWORD *v14; // rcx
  __int64 *v15; // r8
  __int64 *v16; // rdx
  _QWORD *v17; // rdi
  __int64 v18; // rax
  _QWORD *v19; // rdx
  __int64 v20; // rax
  __int64 *v21; // rcx
  __int64 v22; // rax

  v3 = *a1;
  v6 = a1[1] - *a1;
  if ( v6 == 0x1FFFFFFFFFFFFFFFLL )
    std::_Xlength_error("vector too long");
  v8 = v6 + 1;
  v9 = std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode>>::_Calculate_growth(a1, v6 + 1);
  size_of = std::_Get_size_of_n<8>(v9);
  v11 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v12 = (_QWORD *)(v11 + 8 * (a2 - v3));
  v13 = *a3;
  *a3 = 0;
  *v12 = v13;
  v14 = (_QWORD *)v11;
  v15 = a1[1];
  v16 = *a1;
  if ( a2 == v15 )
  {
    while ( v16 != v15 )
    {
      v18 = *v16;
      *v16 = 0;
      *v14++ = v18;
      ++v16;
    }
    v19 = v14;
  }
  else
  {
    v17 = v12 + 1;
    while ( v16 != a2 )
    {
      v20 = *v16;
      *v16 = 0;
      *v14++ = v20;
      ++v16;
    }
    std::_Destroy_range<std::allocator<std::unique_ptr<Windows::UI::Composition::EffectNode>>>(v14, v14);
    v21 = a1[1];
    while ( a2 != v21 )
    {
      v22 = *a2;
      *a2 = 0;
      *v17++ = v22;
      ++a2;
    }
    v19 = v17;
    v14 = v17;
  }
  std::_Destroy_range<std::allocator<std::unique_ptr<Windows::UI::Composition::EffectNode>>>(v14, v19);
  std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode>>::_Change_array(a1, v11, v8, v9);
  return v12;
}

```

## disassembly

```asm
0x180004ed0  push    rbx
0x180004ed2  push    rbp
0x180004ed3  push    rsi
0x180004ed4  push    rdi
0x180004ed5  push    r12
0x180004ed7  push    r13
0x180004ed9  push    r14
0x180004edb  push    r15
0x180004edd  sub     rsp, 28h
0x180004ee1  mov     rdi, [rcx]
0x180004ee4  mov     rsi, rcx
0x180004ee7  mov     rax, [rcx+8]
0x180004eeb  mov     r15, r8
0x180004eee  sub     rax, rdi
0x180004ef1  mov     rcx, 1FFFFFFFFFFFFFFFh
0x180004efb  sar     rax, 3
0x180004eff  mov     rbx, rdx
0x180004f02  cmp     rax, rcx
0x180004f05  jnz     short loc_180004F15
0x180004f07  lea     rcx, aVectorTooLong; "vector too long"
0x180004f0e  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180004f15  lea     r12, [rax+1]
0x180004f19  mov     rcx, rsi
0x180004f1c  mov     rdx, r12
0x180004f1f  call    ?_Calculate_growth@?$vector@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@@2@@std@@AEBA_K_K@Z; std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode>>::_Calculate_growth(unsigned __int64)
0x180004f24  mov     rcx, rax
0x180004f27  mov     r13, rax
0x180004f2a  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x180004f2f  mov     rcx, rax; dwBytes
0x180004f32  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180004f37  xor     r9d, r9d
0x180004f3a  mov     rcx, rbx
0x180004f3d  sub     rcx, rdi
0x180004f40  mov     r14, rax
0x180004f43  sar     rcx, 3
0x180004f47  lea     rbp, [rax+rcx*8]
0x180004f4b  mov     rcx, [r15]
0x180004f4e  mov     [r15], r9
0x180004f51  mov     [rbp+0], rcx
0x180004f55  mov     rcx, rax
0x180004f58  mov     r8, [rsi+8]
0x180004f5c  mov     rdx, [rsi]
0x180004f5f  cmp     rbx, r8
0x180004f62  jz      short loc_180004F7B
0x180004f64  lea     rdi, [rbp+8]
0x180004f68  jmp     short loc_180004F96
0x180004f6a  mov     rax, [rdx]
0x180004f6d  mov     [rdx], r9
0x180004f70  mov     [rcx], rax
0x180004f73  add     rcx, 8
0x180004f77  add     rdx, 8
0x180004f7b  cmp     rdx, r8
0x180004f7e  jnz     short loc_180004F6A
0x180004f80  mov     rdx, rcx
0x180004f83  jmp     short loc_180004FC9
0x180004f85  mov     rax, [rdx]
0x180004f88  mov     [rdx], r9
0x180004f8b  mov     [rcx], rax
0x180004f8e  add     rcx, 8
0x180004f92  add     rdx, 8
0x180004f96  cmp     rdx, rbx
0x180004f99  jnz     short loc_180004F85
0x180004f9b  mov     rdx, rcx
0x180004f9e  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<Windows::UI::Composition::EffectNode>>>(std::unique_ptr<Windows::UI::Composition::EffectNode> *,std::unique_ptr<Windows::UI::Composition::EffectNode> * const,std::allocator<std::unique_ptr<Windows::UI::Composition::EffectNode>> &)
0x180004fa3  mov     rcx, [rsi+8]
0x180004fa7  jmp     short loc_180004FBE
0x180004fa9  mov     rax, [rbx]
0x180004fac  mov     qword ptr [rbx], 0
0x180004fb3  mov     [rdi], rax
0x180004fb6  add     rdi, 8
0x180004fba  add     rbx, 8
0x180004fbe  cmp     rbx, rcx
0x180004fc1  jnz     short loc_180004FA9
0x180004fc3  mov     rdx, rdi
0x180004fc6  mov     rcx, rdi
0x180004fc9  call    ??$_Destroy_range@V?$allocator@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@@std@@@std@@YAXPEAV?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@0@QEAV10@AEAV?$allocator@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::unique_ptr<Windows::UI::Composition::EffectNode>>>(std::unique_ptr<Windows::UI::Composition::EffectNode> *,std::unique_ptr<Windows::UI::Composition::EffectNode> * const,std::allocator<std::unique_ptr<Windows::UI::Composition::EffectNode>> &)
0x180004fce  mov     r9, r13
0x180004fd1  mov     r8, r12
0x180004fd4  mov     rdx, r14
0x180004fd7  mov     rcx, rsi
0x180004fda  call    ?_Change_array@?$vector@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@V?$allocator@V?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@std@@@2@@std@@AEAAXQEAV?$unique_ptr@VEffectNode@Composition@UI@Windows@@U?$default_delete@VEffectNode@Composition@UI@Windows@@@std@@@2@_K1@Z; std::vector<std::unique_ptr<Windows::UI::Composition::EffectNode>>::_Change_array(std::unique_ptr<Windows::UI::Composition::EffectNode> * const,unsigned __int64,unsigned __int64)
0x180004fdf  mov     rax, rbp
0x180004fe2  add     rsp, 28h
0x180004fe6  pop     r15
0x180004fe8  pop     r14
0x180004fea  pop     r13
0x180004fec  pop     r12
0x180004fee  pop     rdi
0x180004fef  pop     rsi
0x180004ff0  pop     rbp
0x180004ff1  pop     rbx
0x180004ff2  retn
```
