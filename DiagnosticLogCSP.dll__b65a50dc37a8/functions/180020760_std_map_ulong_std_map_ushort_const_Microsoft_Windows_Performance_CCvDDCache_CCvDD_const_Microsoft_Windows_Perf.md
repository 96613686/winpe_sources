# std::map<ulong,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>>>::operator[](ulong const &)

- ea: `0x180020760`
- end: `0x180020897`
- name: `??A?$map@KV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@@2@@std@@QEAAAEAV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@1@AEBK@Z`
- size: `311`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180020a14`
- `0x180020e38`
- `0x1800239f4`

## callees

- `0x180001bb4`
- `0x18001138c`
- `0x180011618`
- `0x18001fd5c`
- `0x180020760`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::map<unsigned short const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<unsigned short const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>(&v11);
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
0x180020760  mov     [rsp-18h+arg_8], rbx
0x180020765  mov     [rsp-18h+arg_10], rsi
0x18002076a  push    rbp
0x18002076b  push    rdi
0x18002076c  push    r14
0x18002076e  mov     rbp, rsp
0x180020771  sub     rsp, 50h
0x180020775  mov     rbx, rdx
0x180020778  mov     rsi, rcx
0x18002077b  mov     r14, [rcx]
0x18002077e  mov     rax, [r14+8]
0x180020782  mov     qword ptr [rbp+var_20], rax
0x180020786  mov     qword ptr [rbp+var_20+8], 0
0x18002078e  mov     r8, r14
0x180020791  cmp     byte ptr [rax+19h], 0
0x180020795  jnz     short loc_1800207C2
0x180020797  mov     ecx, [rdx]
0x180020799  mov     qword ptr [rbp+var_20], rax
0x18002079d  cmp     [rax+20h], ecx
0x1800207a0  jnb     short loc_1800207AF
0x1800207a2  mov     dword ptr [rbp+var_20+8], 0
0x1800207a9  add     rax, 10h
0x1800207ad  jmp     short loc_1800207B9
0x1800207af  mov     dword ptr [rbp+var_20+8], 1
0x1800207b6  mov     r8, rax
0x1800207b9  mov     rax, [rax]
0x1800207bc  cmp     byte ptr [rax+19h], 0
0x1800207c0  jz      short loc_180020799
0x1800207c2  cmp     byte ptr [r8+19h], 0
0x1800207c7  jnz     short loc_1800207D5
0x1800207c9  mov     eax, [r8+20h]
0x1800207cd  cmp     [rdx], eax
0x1800207cf  jnb     loc_180020877
0x1800207d5  mov     rax, 492492492492492h
0x1800207df  cmp     [rsi+8], rax
0x1800207e3  jz      loc_180020891
0x1800207e9  mov     qword ptr [rbp+var_30], rsi
0x1800207ed  mov     qword ptr [rbp+var_30+8], 0
0x1800207f5  mov     ecx, 38h ; '8'; Size
0x1800207fa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800207ff  mov     rdi, rax
0x180020802  mov     qword ptr [rbp+var_30+8], rax
0x180020806  mov     eax, [rbx]
0x180020808  mov     [rdi+20h], eax
0x18002080b  mov     qword ptr [rdi+28h], 0
0x180020813  mov     qword ptr [rdi+30h], 0
0x18002081b  mov     ecx, 30h ; '0'; Size
0x180020820  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020825  mov     [rax], rax
0x180020828  mov     [rax+8], rax
0x18002082c  mov     [rax+10h], rax
0x180020830  mov     word ptr [rax+18h], 101h
0x180020836  mov     [rdi+28h], rax
0x18002083a  mov     [rdi], r14
0x18002083d  mov     [rdi+8], r14
0x180020841  mov     [rdi+10h], r14
0x180020845  mov     word ptr [rdi+18h], 0
0x18002084b  mov     qword ptr [rbp+var_30+8], 0
0x180020853  lea     rcx, [rbp+var_30]
0x180020857  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$map@PEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@UlessLPCWSTR_ci@2345@V?$allocator@U?$pair@QEBGPEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,std::map<ushort const *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *,Microsoft::Windows::Performance::CCvDDCache::lessLPCWSTR_ci,std::allocator<std::pair<ushort const * const,Microsoft::Windows::Performance::CCvDDCache::CCvDD const *>>>>,void *>>>(void)
0x18002085c  movups  xmm0, [rbp+var_20]
0x180020860  movdqu  [rbp+var_30], xmm0
0x180020865  mov     r8, rdi
0x180020868  lea     rdx, [rbp+var_30]
0x18002086c  mov     rcx, rsi
0x18002086f  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> * const)
0x180020874  mov     r8, rax
0x180020877  lea     rax, [r8+28h]
0x18002087b  lea     r11, [rsp+50h+var_s0]
0x180020880  mov     rbx, [r11+28h]
0x180020884  mov     rsi, [r11+30h]
0x180020888  mov     rsp, r11
0x18002088b  pop     r14
0x18002088d  pop     rdi
0x18002088e  pop     rbp
0x18002088f  retn
0x180020891  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
