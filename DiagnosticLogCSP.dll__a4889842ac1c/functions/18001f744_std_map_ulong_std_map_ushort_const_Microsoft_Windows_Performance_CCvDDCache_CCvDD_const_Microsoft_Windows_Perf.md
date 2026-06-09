# std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>>::operator[](ulong const &)

- ea: `0x18001f744`
- end: `0x18001f87a`
- name: `??A?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@QEAAAEAV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@1@AEBK@Z`
- size: `310`
- prototype: `__int64 __fastcall(__int64 *, unsigned int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001f9e4`
- `0x18001fdf8`
- `0x180022a4c`

## callees

- `0x180001b84`
- `0x180010b08`
- `0x180010d94`
- `0x18001ed68`
- `0x18001f744`

## pseudocode

```c
__int64 __fastcall std::map<unsigned long,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>::operator[](
        __int64 *a1,
        unsigned int *a2)
{
  __int64 v4; // r14
  __int64 v5; // rax
  __int64 inserted; // r8
  unsigned int v7; // ecx
  _DWORD *v8; // rdi
  _QWORD *v9; // rax
  __int128 v11; // [rsp+20h] [rbp-30h] BYREF
  __int128 v12; // [rsp+30h] [rbp-20h]

  v4 = *a1;
  v5 = *(_QWORD *)(*a1 + 8);
  v12 = (unsigned __int64)v5;
  inserted = v4;
  if ( !*(_BYTE *)(v5 + 25) )
  {
    v7 = *a2;
    do
    {
      *(_QWORD *)&v12 = v5;
      if ( *(_DWORD *)(v5 + 32) >= v7 )
      {
        DWORD2(v12) = 1;
        inserted = v5;
      }
      else
      {
        DWORD2(v12) = 0;
        v5 += 16;
      }
      v5 = *(_QWORD *)v5;
    }
    while ( !*(_BYTE *)(v5 + 25) );
  }
  if ( *(_BYTE *)(inserted + 25) || *a2 < *(_DWORD *)(inserted + 32) )
  {
    if ( a1[1] == 0x492492492492492LL )
      std::_Throw_tree_length_error();
    *(_QWORD *)&v11 = a1;
    v8 = operator new(0x38u);
    *((_QWORD *)&v11 + 1) = v8;
    v8[8] = *a2;
    *((_QWORD *)v8 + 5) = 0;
    *((_QWORD *)v8 + 6) = 0;
    v9 = operator new(0x30u);
    *v9 = v9;
    v9[1] = v9;
    v9[2] = v9;
    *((_WORD *)v9 + 12) = 257;
    *((_QWORD *)v8 + 5) = v9;
    *(_QWORD *)v8 = v4;
    *((_QWORD *)v8 + 1) = v4;
    *((_QWORD *)v8 + 2) = v4;
    *((_WORD *)v8 + 12) = 0;
    *((_QWORD *)&v11 + 1) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>((__int64)&v11);
    v11 = v12;
    inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Insert_node(
                 a1,
                 &v11);
  }
  return inserted + 40;
}

```

## disassembly

```asm
0x18001f744  mov     [rsp-18h+arg_8], rbx
0x18001f749  mov     [rsp-18h+arg_10], rsi
0x18001f74e  push    rbp
0x18001f74f  push    rdi
0x18001f750  push    r14
0x18001f752  mov     rbp, rsp
0x18001f755  sub     rsp, 50h
0x18001f759  mov     rbx, rdx
0x18001f75c  mov     rsi, rcx
0x18001f75f  mov     r14, [rcx]
0x18001f762  mov     rax, [r14+8]
0x18001f766  mov     qword ptr [rbp+var_20], rax
0x18001f76a  mov     qword ptr [rbp+var_20+8], 0
0x18001f772  mov     r8, r14
0x18001f775  cmp     byte ptr [rax+19h], 0
0x18001f779  jnz     short loc_18001F7A6
0x18001f77b  mov     ecx, [rdx]
0x18001f77d  mov     qword ptr [rbp+var_20], rax
0x18001f781  cmp     [rax+20h], ecx
0x18001f784  jnb     short loc_18001F793
0x18001f786  mov     dword ptr [rbp+var_20+8], 0
0x18001f78d  add     rax, 10h
0x18001f791  jmp     short loc_18001F79D
0x18001f793  mov     dword ptr [rbp+var_20+8], 1
0x18001f79a  mov     r8, rax
0x18001f79d  mov     rax, [rax]
0x18001f7a0  cmp     byte ptr [rax+19h], 0
0x18001f7a4  jz      short loc_18001F77D
0x18001f7a6  cmp     byte ptr [r8+19h], 0
0x18001f7ab  jnz     short loc_18001F7B9
0x18001f7ad  mov     eax, [r8+20h]
0x18001f7b1  cmp     [rdx], eax
0x18001f7b3  jnb     loc_18001F85B
0x18001f7b9  mov     rax, 492492492492492h
0x18001f7c3  cmp     [rsi+8], rax
0x18001f7c7  jz      loc_18001F874
0x18001f7cd  mov     qword ptr [rbp+var_30], rsi
0x18001f7d1  mov     qword ptr [rbp+var_30+8], 0
0x18001f7d9  mov     ecx, 38h ; '8'; Size
0x18001f7de  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f7e3  mov     rdi, rax
0x18001f7e6  mov     qword ptr [rbp+var_30+8], rax
0x18001f7ea  mov     eax, [rbx]
0x18001f7ec  mov     [rdi+20h], eax
0x18001f7ef  mov     qword ptr [rdi+28h], 0
0x18001f7f7  mov     qword ptr [rdi+30h], 0
0x18001f7ff  mov     ecx, 30h ; '0'; Size
0x18001f804  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f809  mov     [rax], rax
0x18001f80c  mov     [rax+8], rax
0x18001f810  mov     [rax+10h], rax
0x18001f814  mov     word ptr [rax+18h], 101h
0x18001f81a  mov     [rdi+28h], rax
0x18001f81e  mov     [rdi], r14
0x18001f821  mov     [rdi+8], r14
0x18001f825  mov     [rdi+10h], r14
0x18001f829  mov     word ptr [rdi+18h], 0
0x18001f82f  mov     qword ptr [rbp+var_30+8], 0
0x18001f837  lea     rcx, [rbp+var_30]
0x18001f83b  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>(void)
0x18001f840  movups  xmm0, [rbp+var_20]
0x18001f844  movdqu  [rbp+var_30], xmm0
0x18001f849  mov     r8, rdi
0x18001f84c  lea     rdx, [rbp+var_30]
0x18001f850  mov     rcx, rsi
0x18001f853  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x18001f858  mov     r8, rax
0x18001f85b  lea     rax, [r8+28h]
0x18001f85f  lea     r11, [rsp+50h+var_s0]
0x18001f864  mov     rbx, [r11+28h]
0x18001f868  mov     rsi, [r11+30h]
0x18001f86c  mov     rsp, r11
0x18001f86f  pop     r14
0x18001f871  pop     rdi
0x18001f872  pop     rbp
0x18001f873  retn
0x18001f874  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
