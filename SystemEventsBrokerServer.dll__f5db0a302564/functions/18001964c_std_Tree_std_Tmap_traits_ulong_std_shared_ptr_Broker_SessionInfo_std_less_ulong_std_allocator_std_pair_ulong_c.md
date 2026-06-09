# std::_Tree<std::_Tmap_traits<ulong,std::shared_ptr<Broker::_SessionInfo>,std::less<ulong>,std::allocator<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>,0>>::_Emplace<std::pair<ulong,std::shared_ptr<Broker::_SessionInfo>>>(std::pair<ulong,std::shared_ptr<Broker::_SessionInfo>> &&)

- ea: `0x18001964c`
- end: `0x18001972c`
- name: `??$_Emplace@U?$pair@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@@1@@Z`
- size: `224`
- prototype: `__int64 __fastcall(__int64 *, __int64, _DWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012b8c`
- `0x180019618`

## callees

- `0x180014ac0`
- `0x180018fe8`
- `0x18001964c`
- `0x18001a310`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800196cb`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800196cb`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<Broker::_SessionInfo>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>,0>>::_Emplace<std::pair<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>(
        __int64 *a1,
        __int64 a2,
        _DWORD *a3)
{
  int v3; // esi
  __int64 v6; // rdx
  __int64 v7; // rax
  __int64 v8; // rbp
  _QWORD *v9; // rax
  __int64 v10; // rbx
  __int64 v12; // [rsp+20h] [rbp-58h] BYREF
  int v13; // [rsp+28h] [rbp-50h]
  int v14; // [rsp+2Ch] [rbp-4Ch]
  _QWORD v15[9]; // [rsp+30h] [rbp-48h] BYREF

  v3 = 0;
  v6 = *a1;
  v7 = *(_QWORD *)(*a1 + 8);
  if ( *(_BYTE *)(v7 + 25) )
  {
    v8 = *(_QWORD *)(*a1 + 8);
  }
  else
  {
    do
    {
      v8 = v7;
      if ( *(_DWORD *)(v7 + 32) >= *a3 )
      {
        v3 = 1;
        v6 = v7;
      }
      else
      {
        v3 = 0;
        v7 += 16;
      }
      v7 = *(_QWORD *)v7;
    }
    while ( !*(_BYTE *)(v7 + 25) );
  }
  if ( *(_BYTE *)(v6 + 25) || *a3 < *(_DWORD *)(v6 + 32) )
  {
    if ( a1[1] == 0x492492492492492LL )
      std::_Xlength_error("map/set too long");
    v9 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>,void *>>>(
           v15,
           (__int64)a1,
           *a1,
           (__int64)a3);
    v10 = v9[1];
    v9[1] = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<unsigned long,std::shared_ptr<Broker::_SessionInfo>>>>,void *>>>(v15);
    v12 = v8;
    v13 = v3;
    v14 = 0;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<Broker::_SessionInfo>>>>::_Insert_node(
                      a1,
                      &v12,
                      v10);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v6;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x18001964c  push    rbx
0x18001964e  push    rbp
0x18001964f  push    rsi
0x180019650  push    rdi
0x180019651  push    r12
0x180019653  push    r14
0x180019655  sub     rsp, 48h
0x180019659  mov     r10, [rcx]
0x18001965c  xor     esi, esi
0x18001965e  xor     r12d, r12d
0x180019661  mov     rdi, rdx
0x180019664  mov     r14, rcx
0x180019667  mov     rdx, r10
0x18001966a  mov     rax, [r10+8]
0x18001966e  cmp     [rax+19h], sil
0x180019672  jnz     short loc_18001969A
0x180019674  mov     ecx, [r8]
0x180019677  mov     rbp, rax
0x18001967a  cmp     [rax+20h], ecx
0x18001967d  jnb     short loc_180019687
0x18001967f  xor     esi, esi
0x180019681  add     rax, 10h
0x180019685  jmp     short loc_18001968F
0x180019687  mov     esi, 1
0x18001968c  mov     rdx, rax
0x18001968f  mov     rax, [rax]
0x180019692  cmp     [rax+19h], r12b
0x180019696  jz      short loc_180019677
0x180019698  jmp     short loc_18001969D
0x18001969a  mov     rbp, rax
0x18001969d  cmp     [rdx+19h], r12b
0x1800196a1  jnz     short loc_1800196B4
0x1800196a3  mov     eax, [rdx+20h]
0x1800196a6  cmp     [r8], eax
0x1800196a9  jb      short loc_1800196B4
0x1800196ab  mov     [rdi], rdx
0x1800196ae  mov     [rdi+8], r12b
0x1800196b2  jmp     short loc_18001971C
0x1800196b4  mov     rax, 492492492492492h
0x1800196be  cmp     [r14+8], rax
0x1800196c2  jnz     short loc_1800196D2
0x1800196c4  lea     rcx, aMapSetTooLong; "map/set too long"
0x1800196cb  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800196d2  mov     r9, r8
0x1800196d5  lea     rcx, [rsp+78h+var_48]
0x1800196da  mov     r8, r10
0x1800196dd  mov     rdx, r14
0x1800196e0  call    ??$?0U?$pair@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@PEAX@1@$$QEAU?$pair@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@@1@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>,void *>> &,std::_Tree_node<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>,void *> *,std::pair<ulong,std::shared_ptr<Broker::_SessionInfo>> &&)
0x1800196e5  lea     rcx, [rsp+78h+var_48]
0x1800196ea  mov     rbx, [rax+8]
0x1800196ee  mov     [rax+8], r12
0x1800196f2  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@V?$map@KV?$shared_ptr@U_SessionInfo@Broker@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@2@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<std::map<ulong,std::shared_ptr<Broker::_SessionInfo>>>>,void *>>>(void)
0x1800196f7  mov     r8, rbx
0x1800196fa  mov     [rsp+78h+var_58], rbp
0x1800196ff  lea     rdx, [rsp+78h+var_58]
0x180019704  mov     [rsp+78h+var_50], esi
0x180019708  mov     rcx, r14
0x18001970b  mov     [rsp+78h+var_4C], r12d
0x180019710  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@U_SessionInfo@Broker@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>,void *> *>,std::_Tree_node<std::pair<ulong const,std::shared_ptr<Broker::_SessionInfo>>,void *> * const)
0x180019715  mov     [rdi], rax
0x180019718  mov     byte ptr [rdi+8], 1
0x18001971c  mov     rax, rdi
0x18001971f  add     rsp, 48h
0x180019723  pop     r14
0x180019725  pop     r12
0x180019727  pop     rdi
0x180019728  pop     rsi
0x180019729  pop     rbp
0x18001972a  pop     rbx
0x18001972b  retn
```
