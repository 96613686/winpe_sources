# std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>>::operator[](ulong const &)

- ea: `0x18000eb20`
- end: `0x18000ec56`
- name: `??A?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@QEAAAEAV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@1@AEBK@Z`
- size: `310`
- prototype: `__int64 __fastcall(__int64 *, unsigned int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000edc4`
- `0x18000f1d8`
- `0x180011e1c`

## callees

- `0x1800018a0`
- `0x18000e148`
- `0x18000eb20`
- `0x180015920`
- `0x180015b50`

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
                 &v11,
                 v8);
  }
  return inserted + 40;
}

```

## disassembly

```asm
0x18000eb20  mov     [rsp-18h+arg_8], rbx
0x18000eb25  mov     [rsp-18h+arg_10], rsi
0x18000eb2a  push    rbp
0x18000eb2b  push    rdi
0x18000eb2c  push    r14
0x18000eb2e  mov     rbp, rsp
0x18000eb31  sub     rsp, 50h
0x18000eb35  mov     rbx, rdx
0x18000eb38  mov     rsi, rcx
0x18000eb3b  mov     r14, [rcx]
0x18000eb3e  mov     rax, [r14+8]
0x18000eb42  mov     qword ptr [rbp+var_20], rax
0x18000eb46  mov     qword ptr [rbp+var_20+8], 0
0x18000eb4e  mov     r8, r14
0x18000eb51  cmp     byte ptr [rax+19h], 0
0x18000eb55  jnz     short loc_18000EB82
0x18000eb57  mov     ecx, [rdx]
0x18000eb59  mov     qword ptr [rbp+var_20], rax
0x18000eb5d  cmp     [rax+20h], ecx
0x18000eb60  jnb     short loc_18000EB6F
0x18000eb62  mov     dword ptr [rbp+var_20+8], 0
0x18000eb69  add     rax, 10h
0x18000eb6d  jmp     short loc_18000EB79
0x18000eb6f  mov     dword ptr [rbp+var_20+8], 1
0x18000eb76  mov     r8, rax
0x18000eb79  mov     rax, [rax]
0x18000eb7c  cmp     byte ptr [rax+19h], 0
0x18000eb80  jz      short loc_18000EB59
0x18000eb82  cmp     byte ptr [r8+19h], 0
0x18000eb87  jnz     short loc_18000EB95
0x18000eb89  mov     eax, [r8+20h]
0x18000eb8d  cmp     [rdx], eax
0x18000eb8f  jnb     loc_18000EC37
0x18000eb95  mov     rax, 492492492492492h
0x18000eb9f  cmp     [rsi+8], rax
0x18000eba3  jz      loc_18000EC50
0x18000eba9  mov     qword ptr [rbp+var_30], rsi
0x18000ebad  mov     qword ptr [rbp+var_30+8], 0
0x18000ebb5  mov     ecx, 38h ; '8'; Size
0x18000ebba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ebbf  mov     rdi, rax
0x18000ebc2  mov     qword ptr [rbp+var_30+8], rax
0x18000ebc6  mov     eax, [rbx]
0x18000ebc8  mov     [rdi+20h], eax
0x18000ebcb  mov     qword ptr [rdi+28h], 0
0x18000ebd3  mov     qword ptr [rdi+30h], 0
0x18000ebdb  mov     ecx, 30h ; '0'; Size
0x18000ebe0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ebe5  mov     [rax], rax
0x18000ebe8  mov     [rax+8], rax
0x18000ebec  mov     [rax+10h], rax
0x18000ebf0  mov     word ptr [rax+18h], 101h
0x18000ebf6  mov     [rdi+28h], rax
0x18000ebfa  mov     [rdi], r14
0x18000ebfd  mov     [rdi+8], r14
0x18000ec01  mov     [rdi+10h], r14
0x18000ec05  mov     word ptr [rdi+18h], 0
0x18000ec0b  mov     qword ptr [rbp+var_30+8], 0
0x18000ec13  lea     rcx, [rbp+var_30]
0x18000ec17  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>(void)
0x18000ec1c  movups  xmm0, [rbp+var_20]
0x18000ec20  movdqu  [rbp+var_30], xmm0
0x18000ec25  mov     r8, rdi
0x18000ec28  lea     rdx, [rbp+var_30]
0x18000ec2c  mov     rcx, rsi
0x18000ec2f  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x18000ec34  mov     r8, rax
0x18000ec37  lea     rax, [r8+28h]
0x18000ec3b  lea     r11, [rsp+50h+var_s0]
0x18000ec40  mov     rbx, [r11+28h]
0x18000ec44  mov     rsi, [r11+30h]
0x18000ec48  mov     rsp, r11
0x18000ec4b  pop     r14
0x18000ec4d  pop     rdi
0x18000ec4e  pop     rbp
0x18000ec4f  retn
0x18000ec50  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
