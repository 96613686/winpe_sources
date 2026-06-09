# Windows::UI::Composition::EffectGenerator::Compile(void)

- ea: `0x18000c410`
- end: `0x18000c6f6`
- name: `?Compile@EffectGenerator@Composition@UI@Windows@@AEAAXXZ`
- size: `742`
- prototype: `void __fastcall(Windows::UI::Composition::EffectGenerator *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18000bda0`

## callees

- `0x180008320`
- `0x1800091fc`
- `0x18000b10c`
- `0x18000c410`
- `0x18000c6fc`
- `0x18000c75c`
- `0x18000c7a0`
- `0x18000cdd4`
- `0x18000d004`
- `0x18000d0d4`
- `0x18000d23c`
- `0x18000d5bc`
- `0x18000db84`
- `0x18000de60`
- `0x18002e010`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000c4fd`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000c4fd`

## pseudocode

```c
void __fastcall Windows::UI::Composition::EffectGenerator::Compile(Windows::UI::Composition::EffectGenerator *this)
{
  unsigned int v2; // eax
  _QWORD *v3; // rsi
  unsigned int v4; // r15d
  __int64 v5; // rdx
  __int64 v6; // r8
  unsigned __int64 v7; // rcx
  unsigned int v8; // eax
  __int64 v9; // rbp
  __int64 v10; // rax
  __int64 v11; // r8
  _QWORD *v12; // rcx
  __int64 v13; // r14
  __int64 v14; // rax
  _QWORD *v15; // rbx
  _QWORD *v16; // rsi
  __int64 v17; // rdx
  unsigned __int64 v18; // rbx
  unsigned __int64 v19; // rcx
  _QWORD *v20; // rsi
  __int64 v21; // rdx
  unsigned __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // r8
  __int64 v26; // rax
  Windows::UI::Composition::CompiledEffectSubgraph *v27; // rbx
  __int64 v28; // rax

  v2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)this + 16LL) + 32LL))(*(_QWORD *)this + 16LL);
  v3 = (_QWORD *)*((_QWORD *)this + 33);
  v4 = v2;
  v5 = v2;
  v6 = v3[2];
  v7 = 0xF0F0F0F0F0F0F0F1uLL * ((v3[3] - v6) >> 3);
  if ( v2 < v7 )
  {
    v27 = (Windows::UI::Composition::CompiledEffectSubgraph *)(v6 + 136LL * v2);
    std::_Destroy_range<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph>>(v27);
    v3[3] = v27;
  }
  else if ( v2 > v7 )
  {
    if ( v2 <= 0xF0F0F0F0F0F0F0F1uLL * ((v3[4] - v6) >> 3) )
      v3[3] = std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph>>(
                v3[3],
                v2 - v7,
                v3 + 2);
    else
      std::vector<Windows::UI::Composition::CompiledEffectSubgraph>::_Resize_reallocate<std::_Value_init_tag>(v3 + 2);
  }
  v8 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)(*(_QWORD *)this + 16LL) + 80LL))(
         *(_QWORD *)this + 16LL,
         v5);
  std::vector<std::string>::_Resize<std::_Value_init_tag>((char *)this + 48, v8);
  v9 = 0;
  if ( v4 )
  {
    while ( 1 )
    {
      v10 = *((_QWORD *)this + 33);
      v11 = *(_QWORD *)(v10 + 16);
      if ( 0xF0F0F0F0F0F0F0F1uLL * ((*(_QWORD *)(v10 + 24) - v11) >> 3) <= (unsigned int)v9
        || (v12 = *(_QWORD **)this,
            *((_QWORD *)this + 1) = v11 + 136LL * (unsigned int)v9,
            (__int64)(v12[4] - v12[3]) >> 3 <= (unsigned __int64)(unsigned int)v9) )
      {
LABEL_8:
        std::_Xout_of_range("invalid vector subscript");
        __debugbreak();
      }
      _mm_lfence();
      v13 = *(_QWORD *)(v12[3] + 8 * v9);
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD, _QWORD))(v12[2] + 64LL))(v12 + 2, (unsigned int)v9, 0) )
        break;
      Windows::UI::Composition::EffectGenerator::EmitShaderSourceForSubgraph(this, v9);
      Windows::UI::Composition::EffectGenerator::BuildCompiledEffectSubgraph(this);
LABEL_11:
      Windows::UI::Composition::PixelShaderSourceBuilder::~PixelShaderSourceBuilder((Windows::UI::Composition::EffectGenerator *)((char *)this + 88));
      Windows::UI::Composition::PixelShaderSourceBuilder::PixelShaderSourceBuilder((Windows::UI::Composition::EffectGenerator *)((char *)this + 88));
      v14 = *((_QWORD *)this + 3);
      if ( v14 != *((_QWORD *)this + 4) )
        *((_QWORD *)this + 4) = v14;
      v15 = (_QWORD *)*((_QWORD *)this + 9);
      std::_Tree_val<std::_Tree_simple_types<std::pair<enum ShaderLinkingArgument const,std::string>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<enum ShaderLinkingArgument const,std::string>,void *>>>(
        (char *)this + 72,
        (char *)this + 72,
        v15[1]);
      v15[1] = v15;
      v9 = (unsigned int)(v9 + 1);
      *v15 = v15;
      v15[2] = v15;
      *((_QWORD *)this + 10) = 0;
      *((_QWORD *)this + 1) = 0;
      *((_DWORD *)this + 4) = 0;
      if ( (unsigned int)v9 >= v4 )
        return;
    }
    **((_DWORD **)this + 1) = 1;
    v16 = (_QWORD *)*((_QWORD *)this + 1);
    v17 = v16[11];
    v18 = (unsigned int)((__int64)(*(_QWORD *)(v13 + 32) - *(_QWORD *)(v13 + 24)) >> 3);
    v19 = (v16[12] - v17) >> 2;
    if ( v18 < v19 )
    {
      v26 = v17 + 4 * v18;
    }
    else
    {
      if ( v18 <= v19 )
        goto LABEL_19;
      if ( v18 > (v16[13] - v17) >> 2 )
      {
        std::vector<Windows::UI::Composition::CompiledEffectSubgraph::SurfaceData>::_Resize_reallocate<std::_Value_init_tag>(
          v16 + 11,
          (unsigned int)v18);
        goto LABEL_19;
      }
      v26 = std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::SurfaceData>>(
              v16[12],
              (unsigned int)v18 - v19);
    }
    v16[12] = v26;
LABEL_19:
    v20 = (_QWORD *)*((_QWORD *)this + 1);
    v21 = v20[14];
    v22 = (v20[15] - v21) >> 3;
    if ( v18 < v22 )
    {
      v28 = v21 + 8 * v18;
    }
    else
    {
      if ( v18 <= v22 )
        goto LABEL_23;
      if ( v18 > (v20[16] - v21) >> 3 )
      {
        std::vector<Windows::UI::Composition::CompiledEffectSubgraph::InputBindings>::_Resize_reallocate<std::_Value_init_tag>(
          v20 + 14,
          v18);
        goto LABEL_23;
      }
      v28 = std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::InputBindings>>(
              v20[15],
              v18 - v22);
    }
    v20[15] = v28;
LABEL_23:
    v23 = *(_QWORD *)(v13 + 24);
    if ( !((*(_QWORD *)(v13 + 32) - v23) >> 3) )
      goto LABEL_8;
    v24 = *((_QWORD *)this + 1);
    v25 = *(_QWORD *)(v24 + 112);
    if ( !((*(_QWORD *)(v24 + 120) - v25) >> 3) )
      goto LABEL_8;
    *(_BYTE *)(v25 + 4) = *(_BYTE *)v23;
    *(_DWORD *)v25 = *(_DWORD *)(v23 + 4);
    goto LABEL_11;
  }
}

```

## disassembly

```asm
0x18000c410  push    rbx
0x18000c412  push    rbp
0x18000c413  push    rsi
0x18000c414  push    rdi
0x18000c415  push    r13
0x18000c417  push    r14
0x18000c419  push    r15
0x18000c41b  sub     rsp, 20h
0x18000c41f  mov     rdi, rcx
0x18000c422  mov     rcx, [rcx]
0x18000c425  add     rcx, 10h
0x18000c429  mov     rax, [rcx]
0x18000c42c  mov     rax, [rax+20h]
0x18000c430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c435  mov     rsi, [rdi+108h]
0x18000c43c  mov     r13, 0F0F0F0F0F0F0F0F1h
0x18000c446  mov     r15d, eax
0x18000c449  mov     edx, eax
0x18000c44b  mov     r8, [rsi+10h]
0x18000c44f  mov     rcx, [rsi+18h]
0x18000c453  sub     rcx, r8
0x18000c456  sar     rcx, 3
0x18000c45a  imul    rcx, r13
0x18000c45e  cmp     r15, rcx
0x18000c461  jb      loc_18000C695
0x18000c467  jbe     short loc_18000C48A
0x18000c469  mov     rax, [rsi+20h]
0x18000c46d  sub     rax, r8
0x18000c470  sar     rax, 3
0x18000c474  imul    rax, r13
0x18000c478  cmp     rdx, rax
0x18000c47b  jbe     loc_18000C6BE
0x18000c481  lea     rcx, [rsi+10h]
0x18000c485  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@VCompiledEffectSubgraph@Composition@UI@Windows@@V?$allocator@VCompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<Windows::UI::Composition::CompiledEffectSubgraph>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000c48a  mov     rcx, [rdi]
0x18000c48d  add     rcx, 10h
0x18000c491  mov     rax, [rcx]
0x18000c494  mov     rax, [rax+50h]
0x18000c498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c49d  mov     edx, eax
0x18000c49f  lea     rcx, [rdi+30h]
0x18000c4a3  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<std::string>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000c4a8  xor     ebp, ebp
0x18000c4aa  test    r15d, r15d
0x18000c4ad  jz      loc_18000C59E
0x18000c4b3  mov     rax, [rdi+108h]
0x18000c4ba  mov     edx, ebp
0x18000c4bc  mov     r8, [rax+10h]
0x18000c4c0  mov     rcx, [rax+18h]
0x18000c4c4  sub     rcx, r8
0x18000c4c7  sar     rcx, 3
0x18000c4cb  imul    rcx, r13
0x18000c4cf  cmp     rcx, rdx
0x18000c4d2  jbe     short loc_18000C4F6
0x18000c4d4  mov     rcx, [rdi]
0x18000c4d7  imul    rax, rdx, 88h
0x18000c4de  add     rax, r8
0x18000c4e1  mov     [rdi+8], rax
0x18000c4e5  mov     rax, [rcx+20h]
0x18000c4e9  sub     rax, [rcx+18h]
0x18000c4ed  sar     rax, 3
0x18000c4f1  cmp     rax, rdx
0x18000c4f4  ja      short loc_18000C504
0x18000c4f6  lea     rcx, aInvalidVectorS; "invalid vector subscript"
0x18000c4fd  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18000c503  int     3; Trap to Debugger
0x18000c504  lfence
0x18000c507  mov     rax, [rcx+18h]
0x18000c50b  xor     r8d, r8d
0x18000c50e  add     rcx, 10h
0x18000c512  mov     edx, ebp
0x18000c514  mov     r14, [rax+rbp*8]
0x18000c518  mov     rax, [rcx]
0x18000c51b  mov     rax, [rax+40h]
0x18000c51f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c524  test    al, al
0x18000c526  jnz     loc_18000C5AD
0x18000c52c  mov     edx, ebp; unsigned int
0x18000c52e  mov     rcx, rdi; this
0x18000c531  call    ?EmitShaderSourceForSubgraph@EffectGenerator@Composition@UI@Windows@@AEAAXI@Z; Windows::UI::Composition::EffectGenerator::EmitShaderSourceForSubgraph(uint)
0x18000c536  mov     rcx, rdi; this
0x18000c539  call    ?BuildCompiledEffectSubgraph@EffectGenerator@Composition@UI@Windows@@AEAAXI@Z; Windows::UI::Composition::EffectGenerator::BuildCompiledEffectSubgraph(uint)
0x18000c53e  lea     rcx, [rdi+58h]; this
0x18000c542  call    ??1PixelShaderSourceBuilder@Composition@UI@Windows@@QEAA@XZ; Windows::UI::Composition::PixelShaderSourceBuilder::~PixelShaderSourceBuilder(void)
0x18000c547  lea     rcx, [rdi+58h]; this
0x18000c54b  call    ??0PixelShaderSourceBuilder@Composition@UI@Windows@@QEAA@XZ; Windows::UI::Composition::PixelShaderSourceBuilder::PixelShaderSourceBuilder(void)
0x18000c550  mov     rax, [rdi+18h]
0x18000c554  cmp     rax, [rdi+20h]
0x18000c558  jz      short loc_18000C55E
0x18000c55a  mov     [rdi+20h], rax
0x18000c55e  lea     rcx, [rdi+48h]
0x18000c562  mov     rbx, [rcx]
0x18000c565  mov     rdx, rcx
0x18000c568  mov     r8, [rbx+8]
0x18000c56c  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBW4ShaderLinkingArgument@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4ShaderLinkingArgument@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBW4ShaderLinkingArgument@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBW4ShaderLinkingArgument@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ShaderLinkingArgument const,std::string>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ShaderLinkingArgument const,std::string>,void *>>>(std::allocator<std::_Tree_node<std::pair<ShaderLinkingArgument const,std::string>,void *>> &,std::_Tree_node<std::pair<ShaderLinkingArgument const,std::string>,void *> *)
0x18000c571  mov     [rbx+8], rbx
0x18000c575  inc     ebp
0x18000c577  mov     [rbx], rbx
0x18000c57a  mov     [rbx+10h], rbx
0x18000c57e  mov     qword ptr [rdi+50h], 0
0x18000c586  mov     qword ptr [rdi+8], 0
0x18000c58e  mov     dword ptr [rdi+10h], 0
0x18000c595  cmp     ebp, r15d
0x18000c598  jb      loc_18000C4B3
0x18000c59e  add     rsp, 20h
0x18000c5a2  pop     r15
0x18000c5a4  pop     r14
0x18000c5a6  pop     r13
0x18000c5a8  pop     rdi
0x18000c5a9  pop     rsi
0x18000c5aa  pop     rbp
0x18000c5ab  pop     rbx
0x18000c5ac  retn
0x18000c5ad  mov     rax, [rdi+8]
0x18000c5b1  mov     dword ptr [rax], 1
0x18000c5b7  mov     rsi, [rdi+8]
0x18000c5bb  mov     rbx, [r14+20h]
0x18000c5bf  sub     rbx, [r14+18h]
0x18000c5c3  sar     rbx, 3
0x18000c5c7  mov     rdx, [rsi+58h]
0x18000c5cb  mov     rcx, [rsi+60h]
0x18000c5cf  sub     rcx, rdx
0x18000c5d2  mov     ebx, ebx
0x18000c5d4  sar     rcx, 2
0x18000c5d8  cmp     rbx, rcx
0x18000c5db  jb      loc_18000C688
0x18000c5e1  jbe     short loc_18000C602
0x18000c5e3  mov     rax, [rsi+68h]
0x18000c5e7  sub     rax, rdx
0x18000c5ea  mov     edx, ebx
0x18000c5ec  sar     rax, 2
0x18000c5f0  cmp     rbx, rax
0x18000c5f3  jbe     loc_18000C6D7
0x18000c5f9  lea     rcx, [rsi+58h]
0x18000c5fd  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@USurfaceData@CompiledEffectSubgraph@Composition@UI@Windows@@V?$allocator@USurfaceData@CompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<Windows::UI::Composition::CompiledEffectSubgraph::SurfaceData>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000c602  mov     rsi, [rdi+8]
0x18000c606  mov     rdx, [rsi+70h]
0x18000c60a  mov     rcx, [rsi+78h]
0x18000c60e  sub     rcx, rdx
0x18000c611  sar     rcx, 3
0x18000c615  cmp     rbx, rcx
0x18000c618  jb      loc_18000C6B4
0x18000c61e  jbe     short loc_18000C643
0x18000c620  mov     rax, [rsi+80h]
0x18000c627  sub     rax, rdx
0x18000c62a  sar     rax, 3
0x18000c62e  cmp     rbx, rax
0x18000c631  jbe     loc_18000C6E5
0x18000c637  mov     rdx, rbx
0x18000c63a  lea     rcx, [rsi+70h]
0x18000c63e  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@UInputBindings@CompiledEffectSubgraph@Composition@UI@Windows@@V?$allocator@UInputBindings@CompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<Windows::UI::Composition::CompiledEffectSubgraph::InputBindings>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000c643  mov     rdx, [r14+18h]
0x18000c647  mov     rax, [r14+20h]
0x18000c64b  sub     rax, rdx
0x18000c64e  sar     rax, 3
0x18000c652  test    rax, rax
0x18000c655  jz      loc_18000C4F6
0x18000c65b  mov     rax, [rdi+8]
0x18000c65f  mov     r8, [rax+70h]
0x18000c663  mov     rcx, [rax+78h]
0x18000c667  sub     rcx, r8
0x18000c66a  sar     rcx, 3
0x18000c66e  test    rcx, rcx
0x18000c671  jz      loc_18000C4F6
0x18000c677  mov     al, [rdx]
0x18000c679  mov     [r8+4], al
0x18000c67d  mov     eax, [rdx+4]
0x18000c680  mov     [r8], eax
0x18000c683  jmp     loc_18000C53E
0x18000c688  lea     rax, [rdx+rbx*4]
0x18000c68c  mov     [rsi+60h], rax
0x18000c690  jmp     loc_18000C602
0x18000c695  imul    rbx, rdx, 88h
0x18000c69c  mov     rdx, [rsi+18h]
0x18000c6a0  add     rbx, r8
0x18000c6a3  mov     rcx, rbx; this
0x18000c6a6  call    ??$_Destroy_range@V?$allocator@VCompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@YAXPEAVCompiledEffectSubgraph@Composition@UI@Windows@@QEAV1234@AEAV?$allocator@VCompiledEffectSubgraph@Composition@UI@Windows@@@0@@Z; std::_Destroy_range<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph>>(Windows::UI::Composition::CompiledEffectSubgraph *,Windows::UI::Composition::CompiledEffectSubgraph * const,std::allocator<Windows::UI::Composition::CompiledEffectSubgraph> &)
0x18000c6ab  mov     [rsi+18h], rbx
0x18000c6af  jmp     loc_18000C48A
0x18000c6b4  lea     rax, [rdx+rbx*8]
0x18000c6b8  mov     [rsi+78h], rax
0x18000c6bc  jmp     short loc_18000C643
0x18000c6be  sub     rdx, rcx
0x18000c6c1  lea     r8, [rsi+10h]
0x18000c6c5  mov     rcx, [rsi+18h]
0x18000c6c9  call    ??$_Uninitialized_value_construct_n@V?$allocator@VCompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@YAPEAVCompiledEffectSubgraph@Composition@UI@Windows@@PEAV1234@_KAEAV?$allocator@VCompiledEffectSubgraph@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph>>(Windows::UI::Composition::CompiledEffectSubgraph *,unsigned __int64,std::allocator<Windows::UI::Composition::CompiledEffectSubgraph> &)
0x18000c6ce  mov     [rsi+18h], rax
0x18000c6d2  jmp     loc_18000C48A
0x18000c6d7  sub     rdx, rcx
0x18000c6da  mov     rcx, [rsi+60h]
0x18000c6de  call    ??$_Uninitialized_value_construct_n@V?$allocator@USurfaceData@CompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@YAPEAUSurfaceData@CompiledEffectSubgraph@Composition@UI@Windows@@PEAU12345@_KAEAV?$allocator@USurfaceData@CompiledEffectSubgraph@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::SurfaceData>>(Windows::UI::Composition::CompiledEffectSubgraph::SurfaceData *,unsigned __int64,std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::SurfaceData> &)
0x18000c6e3  jmp     short loc_18000C68C
0x18000c6e5  sub     rbx, rcx
0x18000c6e8  mov     rcx, [rsi+78h]
0x18000c6ec  mov     rdx, rbx
0x18000c6ef  call    ??$_Uninitialized_value_construct_n@V?$allocator@UInputBindings@CompiledEffectSubgraph@Composition@UI@Windows@@@std@@@std@@YAPEAUInputBindings@CompiledEffectSubgraph@Composition@UI@Windows@@PEAU12345@_KAEAV?$allocator@UInputBindings@CompiledEffectSubgraph@Composition@UI@Windows@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::InputBindings>>(Windows::UI::Composition::CompiledEffectSubgraph::InputBindings *,unsigned __int64,std::allocator<Windows::UI::Composition::CompiledEffectSubgraph::InputBindings> &)
0x18000c6f4  jmp     short loc_18000C6B8
```
