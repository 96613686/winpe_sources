# std::map<unsigned __int64,PresentTraceConsumerCore::MakeResidentPendingOperation,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>>>::_Try_emplace<unsigned __int64 const &,>(unsigned __int64 const &)

- ea: `0x1800170dc`
- end: `0x1800171c1`
- name: `??$_Try_emplace@AEB_K$$V@?$map@_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@@4@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@std@@_N@1@AEB_K@Z`
- size: `229`
- prototype: `__int64 __fastcall(__int64 *, __int64, unsigned __int64 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180019ee0`

## callees

- `0x180015754`
- `0x180015954`
- `0x180015bcc`
- `0x1800170dc`
- `0x180017c9c`

## pseudocode

```c
__int64 __fastcall std::map<unsigned __int64,PresentTraceConsumerCore::MakeResidentPendingOperation>::_Try_emplace<unsigned __int64 const &,>(
        __int64 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        unsigned __int64 a4)
{
  __int64 v5; // rcx
  __int64 v7; // rdx
  __int64 v8; // rax
  _QWORD *ResidentPending; // rax
  __int64 v10; // rbx
  _QWORD v12[2]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v13; // [rsp+40h] [rbp-28h] BYREF
  unsigned __int64 *v14; // [rsp+90h] [rbp+28h] BYREF

  v5 = *a1;
  v7 = v5;
  v8 = *(_QWORD *)(v5 + 8);
  v13 = (unsigned __int64)v8;
  if ( !*(_BYTE *)(v8 + 25) )
  {
    a4 = *a3;
    do
    {
      *(_QWORD *)&v13 = v8;
      if ( *(_QWORD *)(v8 + 32) >= a4 )
      {
        DWORD2(v13) = 1;
        v7 = v8;
      }
      else
      {
        DWORD2(v13) = 0;
        v8 += 16;
      }
      v8 = *(_QWORD *)v8;
    }
    while ( !*(_BYTE *)(v8 + 25) );
  }
  if ( *(_BYTE *)(v7 + 25) || *a3 < *(_QWORD *)(v7 + 32) )
  {
    if ( a1[1] == 0x492492492492492LL )
      std::_Throw_tree_length_error();
    v14 = a3;
    ResidentPending = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>>>(
                        v12,
                        (__int64)a1,
                        v5,
                        a4,
                        &v14);
    v10 = ResidentPending[1];
    ResidentPending[1] = 0;
    std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>,void *>>>(v12);
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>>>::_Insert_node(
                      a1,
                      &v13,
                      v10);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v7;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x1800170dc  push    rbp
0x1800170de  push    rbx
0x1800170df  push    rsi
0x1800170e0  push    rdi
0x1800170e1  mov     rbp, rsp
0x1800170e4  sub     rsp, 68h
0x1800170e8  mov     rsi, rcx
0x1800170eb  mov     qword ptr [rbp+var_28+8], 0
0x1800170f3  mov     rcx, [rcx]
0x1800170f6  mov     rdi, rdx
0x1800170f9  mov     rdx, rcx
0x1800170fc  mov     rax, [rcx+8]
0x180017100  mov     qword ptr [rbp+var_28], rax
0x180017104  cmp     byte ptr [rax+19h], 0
0x180017108  jnz     short loc_180017137
0x18001710a  mov     r9, [r8]
0x18001710d  mov     qword ptr [rbp+var_28], rax
0x180017111  cmp     [rax+20h], r9
0x180017115  jnb     short loc_180017124
0x180017117  mov     dword ptr [rbp+var_28+8], 0
0x18001711e  add     rax, 10h
0x180017122  jmp     short loc_18001712E
0x180017124  mov     dword ptr [rbp+var_28+8], 1
0x18001712b  mov     rdx, rax
0x18001712e  mov     rax, [rax]
0x180017131  cmp     byte ptr [rax+19h], 0
0x180017135  jz      short loc_18001710D
0x180017137  cmp     byte ptr [rdx+19h], 0
0x18001713b  jnz     short loc_18001714F
0x18001713d  mov     rax, [rdx+20h]
0x180017141  cmp     [r8], rax
0x180017144  jb      short loc_18001714F
0x180017146  mov     [rdi], rdx
0x180017149  mov     byte ptr [rdi+8], 0
0x18001714d  jmp     short loc_1800171AF
0x18001714f  mov     rax, 492492492492492h
0x180017159  cmp     [rsi+8], rax
0x18001715d  jz      short loc_1800171BB
0x18001715f  mov     [rbp+arg_0], r8
0x180017163  lea     rax, [rbp+arg_0]
0x180017167  mov     r8, rcx
0x18001716a  mov     [rsp+68h+var_48], rax
0x18001716f  lea     rcx, [rbp+var_38]
0x180017173  mov     rdx, rsi
0x180017176  call    ??$?0AEBUpiecewise_construct_t@std@@V?$tuple@AEB_K@1@V?$tuple@$$V@1@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_KUMakeResidentPendingOperation@PresentTraceConsumerCore@@@std@@PEAX@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEB_K@1@$$QEAV?$tuple@$$V@1@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *>> &,std::_Tree_node<std::pair<unsigned __int64 const,PresentTraceConsumerCore::MakeResidentPendingOperation>,void *> *,std::piecewise_construct_t const &,std::tuple<unsigned __int64 const &> &&,std::tuple<> &&)
0x18001717b  lea     rcx, [rbp+var_38]
0x18001717f  mov     rbx, [rax+8]
0x180017183  mov     qword ptr [rax+8], 0
0x18001718b  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>,void *>>>(void)
0x180017190  movups  xmm0, [rbp+var_28]
0x180017194  mov     r8, rbx
0x180017197  lea     rdx, [rbp+var_28]
0x18001719b  mov     rcx, rsi
0x18001719e  movdqu  [rbp+var_28], xmm0
0x1800171a3  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> * const)
0x1800171a8  mov     [rdi], rax
0x1800171ab  mov     byte ptr [rdi+8], 1
0x1800171af  mov     rax, rdi
0x1800171b2  add     rsp, 68h
0x1800171b6  pop     rdi
0x1800171b7  pop     rsi
0x1800171b8  pop     rbx
0x1800171b9  pop     rbp
0x1800171ba  retn
0x1800171bb  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
