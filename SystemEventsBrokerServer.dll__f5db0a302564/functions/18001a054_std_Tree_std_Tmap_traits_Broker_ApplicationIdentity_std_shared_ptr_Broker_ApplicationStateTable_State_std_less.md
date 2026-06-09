# std::_Tree<std::_Tmap_traits<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>,std::less<Broker::ApplicationIdentity>,std::allocator<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>,0>>::_Emplace<std::pair<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>>>(std::pair<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>> &&)

- ea: `0x18001a054`
- end: `0x18001a109`
- name: `??$_Emplace@U?$pair@UApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@UApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@U?$less@UApplicationIdentity@Broker@@@4@V?$allocator@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@UApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@1@@Z`
- size: `181`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180007880`

## callees

- `0x1800116a0`
- `0x1800140e0`
- `0x180016360`
- `0x18001a054`
- `0x180021410`
- `0x180021750`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001a0ab`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001a0ab`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>,std::less<Broker::ApplicationIdentity>,std::allocator<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>,0>>::_Emplace<std::pair<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>>>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rax
  __int64 v7; // rbx
  __int128 v8; // xmm6
  __int64 v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // rbx
  _QWORD v13[2]; // [rsp+20h] [rbp-68h] BYREF
  _OWORD v14[2]; // [rsp+30h] [rbp-58h] BYREF

  v6 = std::_Tree<std::_Tmap_traits<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>,std::less<Broker::ApplicationIdentity>,std::allocator<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>,0>>::_Find_lower_bound<Broker::ApplicationIdentity>(
         a1,
         v14);
  v7 = *(_QWORD *)(v6 + 16);
  v8 = *(_OWORD *)v6;
  if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>,std::less<Broker::ApplicationIdentity>,std::allocator<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>,0>>::_Lower_bound_duplicate<Broker::ApplicationIdentity>(
                          v9,
                          v7,
                          a3) )
  {
    *(_QWORD *)a2 = v7;
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( a1[1] == 0x1E1E1E1E1E1E1E1LL )
      std::_Xlength_error("map/set too long");
    v10 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *>>>(
            v13,
            (__int64)a1,
            *a1,
            a3);
    v11 = v10[1];
    v10[1] = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *>>>(v13);
    v14[0] = v8;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>::_Insert_node(
                      a1,
                      v14,
                      v11);
    *(_BYTE *)(a2 + 8) = 1;
  }
  return a2;
}

```

## disassembly

```asm
0x18001a054  push    rbx
0x18001a056  push    rbp
0x18001a057  push    rsi
0x18001a058  push    rdi
0x18001a059  sub     rsp, 68h
0x18001a05d  mov     rdi, rdx
0x18001a060  movaps  [rsp+88h+var_38], xmm6
0x18001a065  lea     rdx, [rsp+88h+var_58]
0x18001a06a  mov     rbp, r8
0x18001a06d  mov     rsi, rcx
0x18001a070  call    ??$_Find_lower_bound@UApplicationIdentity@Broker@@@?$_Tree@V?$_Tmap_traits@UApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@U?$less@UApplicationIdentity@Broker@@@4@V?$allocator@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@4@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@std@@@1@AEBUApplicationIdentity@Broker@@@Z; std::_Tree<std::_Tmap_traits<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>,std::less<Broker::ApplicationIdentity>,std::allocator<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>,0>>::_Find_lower_bound<Broker::ApplicationIdentity>(Broker::ApplicationIdentity const &)
0x18001a075  mov     r8, rbp
0x18001a078  mov     rbx, [rax+10h]
0x18001a07c  movups  xmm6, xmmword ptr [rax]
0x18001a07f  mov     rdx, rbx
0x18001a082  call    ??$_Lower_bound_duplicate@UApplicationIdentity@Broker@@@?$_Tree@V?$_Tmap_traits@UApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@U?$less@UApplicationIdentity@Broker@@@4@V?$allocator@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@4@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@1@AEBUApplicationIdentity@Broker@@@Z; std::_Tree<std::_Tmap_traits<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>,std::less<Broker::ApplicationIdentity>,std::allocator<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>,0>>::_Lower_bound_duplicate<Broker::ApplicationIdentity>(std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *> * const,Broker::ApplicationIdentity const &)
0x18001a087  test    al, al
0x18001a089  jz      short loc_18001A094
0x18001a08b  mov     [rdi], rbx
0x18001a08e  mov     byte ptr [rdi+8], 0
0x18001a092  jmp     short loc_18001A0F8
0x18001a094  mov     rax, 1E1E1E1E1E1E1E1h
0x18001a09e  cmp     [rsi+8], rax
0x18001a0a2  jnz     short loc_18001A0B2
0x18001a0a4  lea     rcx, aMapSetTooLong; "map/set too long"
0x18001a0ab  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001a0b2  mov     r8, [rsi]
0x18001a0b5  lea     rcx, [rsp+88h+var_68]
0x18001a0ba  mov     r9, rbp
0x18001a0bd  mov     rdx, rsi
0x18001a0c0  call    ??$?0U?$pair@UApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@1@$$QEAU?$pair@UApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@1@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *>>>(std::allocator<std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *>> &,std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *> *,std::pair<Broker::ApplicationIdentity,std::shared_ptr<Broker::ApplicationStateTable::State>> &&)
0x18001a0c5  lea     rcx, [rsp+88h+var_68]
0x18001a0ca  mov     rbx, [rax+8]
0x18001a0ce  mov     qword ptr [rax+8], 0
0x18001a0d6  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *>>>(void)
0x18001a0db  mov     r8, rbx
0x18001a0de  lea     rdx, [rsp+88h+var_58]
0x18001a0e3  mov     rcx, rsi
0x18001a0e6  movdqu  [rsp+88h+var_58], xmm6
0x18001a0ec  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBUApplicationIdentity@Broker@@V?$shared_ptr@VState@ApplicationStateTable@Broker@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *> *>,std::_Tree_node<std::pair<Broker::ApplicationIdentity const,std::shared_ptr<Broker::ApplicationStateTable::State>>,void *> * const)
0x18001a0f1  mov     [rdi], rax
0x18001a0f4  mov     byte ptr [rdi+8], 1
0x18001a0f8  movaps  xmm6, [rsp+88h+var_38]
0x18001a0fd  mov     rax, rdi
0x18001a100  add     rsp, 68h
0x18001a104  pop     rdi
0x18001a105  pop     rsi
0x18001a106  pop     rbp
0x18001a107  pop     rbx
0x18001a108  retn
```
