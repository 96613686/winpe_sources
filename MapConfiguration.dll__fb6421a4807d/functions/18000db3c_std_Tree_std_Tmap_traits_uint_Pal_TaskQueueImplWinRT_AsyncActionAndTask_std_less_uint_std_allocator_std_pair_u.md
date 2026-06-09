# std::_Tree<std::_Tmap_traits<uint,Pal::TaskQueueImplWinRT::AsyncActionAndTask,std::less<uint>,std::allocator<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>,0>>::_Emplace<std::pair<uint,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>(std::pair<uint,Pal::TaskQueueImplWinRT::AsyncActionAndTask> &&)

- ea: `0x18000db3c`
- end: `0x18000dc7c`
- name: `??$_Emplace@U?$pair@IUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@@?$_Tree@V?$_Tmap_traits@IUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@@5@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@IUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@1@@Z`
- size: `320`
- prototype: `__int64 __fastcall(__int64 *, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18001a208`

## callees

- `0x18000b7fc`
- `0x18000b928`
- `0x18000db3c`
- `0x18000f14c`
- `0x180011254`
- `0x1800149b8`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000dbd1`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000dbd1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Tree<std::_Tmap_traits<unsigned int,Pal::TaskQueueImplWinRT::AsyncActionAndTask,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>,0>>::_Emplace<std::pair<unsigned int,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>(
        __int64 *a1,
        __int64 a2,
        unsigned int *a3)
{
  __int64 v6; // rcx
  __int64 v7; // rax
  int v8; // esi
  __int64 v9; // rdx
  unsigned int v10; // r8d
  __int64 *v11; // r12
  __int64 *v12; // rbx
  __int64 v13; // rcx
  __int64 *v15; // [rsp+20h] [rbp-10h] BYREF
  unsigned __int64 v16; // [rsp+28h] [rbp-8h]
  __int64 v17; // [rsp+60h] [rbp+30h] BYREF
  __int64 v18; // [rsp+70h] [rbp+40h]

  v6 = *a1;
  v7 = *(_QWORD *)(v6 + 8);
  v8 = 0;
  v18 = 0;
  v9 = v6;
  if ( *(_BYTE *)(v7 + 25) )
  {
    v11 = (__int64 *)v7;
  }
  else
  {
    v10 = *a3;
    do
    {
      v11 = (__int64 *)v7;
      if ( *(_DWORD *)(v7 + 32) >= v10 )
      {
        v8 = 1;
        v9 = v7;
      }
      else
      {
        v8 = 0;
        v7 += 16;
      }
      v7 = *(_QWORD *)v7;
    }
    while ( !*(_BYTE *)(v7 + 25) );
  }
  if ( *(_BYTE *)(v9 + 25) || *a3 < *(_DWORD *)(v9 + 32) )
  {
    if ( a1[1] == 0x3FFFFFFFFFFFFFFLL )
      std::_Xlength_error("map/set too long");
    v17 = v6;
    v15 = a1;
    v12 = std::_Allocate<16,std::_Default_allocate_traits>(0x40u);
    std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<unsigned int const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *>>>::construct<std::pair<unsigned int const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,std::pair<unsigned int,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>(
      v13,
      v12 + 4,
      a3);
    std::_Construct_in_place<std::_Tree_node<std::pair<unsigned int const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *> *,std::_Tree_node<std::pair<unsigned int const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *> * &>(
      v12,
      &v17);
    std::_Construct_in_place<std::_Tree_node<std::pair<unsigned int const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *> *,std::_Tree_node<std::pair<unsigned int const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *> * &>(
      v12 + 1,
      &v17);
    std::_Construct_in_place<std::_Tree_node<std::pair<unsigned int const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *> *,std::_Tree_node<std::pair<unsigned int const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *> * &>(
      v12 + 2,
      &v17);
    *((_WORD *)v12 + 12) = 0;
    v16 = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned int const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned int const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *>>>(&v15);
    v15 = v11;
    v16 = __PAIR64__(v18, v8);
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,enum MapControl::ConfigurationKeys>>>::_Insert_node(
                      a1,
                      &v15,
                      v12);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v9;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x18000db3c  mov     [rsp-28h+arg_8], rbx
0x18000db41  mov     [rsp-28h+arg_18], rsi
0x18000db46  push    rbp
0x18000db47  push    rdi
0x18000db48  push    r12
0x18000db4a  push    r14
0x18000db4c  push    r15
0x18000db4e  mov     rbp, rsp
0x18000db51  sub     rsp, 30h
0x18000db55  mov     r14, r8
0x18000db58  mov     rdi, rdx
0x18000db5b  mov     r15, rcx
0x18000db5e  mov     rcx, [rcx]
0x18000db61  mov     rax, [rcx+8]
0x18000db65  xor     esi, esi
0x18000db67  xor     edx, edx
0x18000db69  mov     [rbp+arg_10], rdx
0x18000db6d  mov     rdx, rcx
0x18000db70  cmp     [rax+19h], sil
0x18000db74  jnz     short loc_18000DB9D
0x18000db76  mov     r8d, [r8]
0x18000db79  mov     r12, rax
0x18000db7c  cmp     [rax+20h], r8d
0x18000db80  jnb     short loc_18000DB8A
0x18000db82  xor     esi, esi
0x18000db84  add     rax, 10h
0x18000db88  jmp     short loc_18000DB92
0x18000db8a  mov     esi, 1
0x18000db8f  mov     rdx, rax
0x18000db92  mov     rax, [rax]
0x18000db95  cmp     byte ptr [rax+19h], 0
0x18000db99  jz      short loc_18000DB79
0x18000db9b  jmp     short loc_18000DBA0
0x18000db9d  mov     r12, rax
0x18000dba0  cmp     byte ptr [rdx+19h], 0
0x18000dba4  jnz     short loc_18000DBBA
0x18000dba6  mov     eax, [rdx+20h]
0x18000dba9  cmp     [r14], eax
0x18000dbac  jb      short loc_18000DBBA
0x18000dbae  mov     [rdi], rdx
0x18000dbb1  mov     byte ptr [rdi+8], 0
0x18000dbb5  jmp     loc_18000DC62
0x18000dbba  mov     rax, 3FFFFFFFFFFFFFFh
0x18000dbc4  cmp     [r15+8], rax
0x18000dbc8  jnz     short loc_18000DBD8
0x18000dbca  lea     rcx, aMapSetTooLong; "map/set too long"
0x18000dbd1  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000dbd8  mov     [rbp+arg_0], rcx
0x18000dbdc  mov     [rbp+var_10], r15
0x18000dbe0  mov     [rbp+var_8], 0
0x18000dbe8  mov     ecx, 40h ; '@'
0x18000dbed  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000dbf2  mov     rbx, rax
0x18000dbf5  lea     rdx, [rax+20h]
0x18000dbf9  mov     r8, r14
0x18000dbfc  call    ??$construct@U?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@U?$pair@IUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@2@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@U?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@PEAX@std@@@1@QEAU?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@1@$$QEAU?$pair@IUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@1@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *>>>::construct<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,std::pair<uint,Pal::TaskQueueImplWinRT::AsyncActionAndTask>>(std::allocator<std::_Tree_node<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *>> &,std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask> * const,std::pair<uint,Pal::TaskQueueImplWinRT::AsyncActionAndTask> &&)
0x18000dc01  lea     rdx, [rbp+arg_0]
0x18000dc05  mov     rcx, rbx
0x18000dc08  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *> *,std::_Tree_node<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *> * &>(std::_Tree_node<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *> * &,std::_Tree_node<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *> * &)
0x18000dc0d  lea     rcx, [rbx+8]
0x18000dc11  lea     rdx, [rbp+arg_0]
0x18000dc15  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *> *,std::_Tree_node<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *> * &>(std::_Tree_node<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *> * &,std::_Tree_node<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *> * &)
0x18000dc1a  lea     rcx, [rbx+10h]
0x18000dc1e  lea     rdx, [rbp+arg_0]
0x18000dc22  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *> *,std::_Tree_node<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *> * &>(std::_Tree_node<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *> * &,std::_Tree_node<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *> * &)
0x18000dc27  mov     word ptr [rbx+18h], 0
0x18000dc2d  mov     [rbp+var_8], 0
0x18000dc35  lea     rcx, [rbp+var_10]
0x18000dc39  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBIUAsyncActionAndTask@TaskQueueImplWinRT@Pal@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<uint const,Pal::TaskQueueImplWinRT::AsyncActionAndTask>,void *>>>(void)
0x18000dc3e  mov     [rbp+var_10], r12
0x18000dc42  mov     dword ptr [rbp+var_8], esi
0x18000dc45  mov     rax, [rbp+arg_10]
0x18000dc49  mov     dword ptr [rbp+var_8+4], eax
0x18000dc4c  mov     r8, rbx
0x18000dc4f  lea     rdx, [rbp+var_10]
0x18000dc53  mov     rcx, r15
0x18000dc56  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4ConfigurationKeys@MapControl@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4ConfigurationKeys@MapControl@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4ConfigurationKeys@MapControl@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,MapControl::ConfigurationKeys>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,MapControl::ConfigurationKeys>,void *> *>,std::_Tree_node<std::pair<std::wstring const,MapControl::ConfigurationKeys>,void *> * const)
0x18000dc5b  mov     [rdi], rax
0x18000dc5e  mov     byte ptr [rdi+8], 1
0x18000dc62  mov     rax, rdi
0x18000dc65  mov     rbx, [rsp+30h+arg_8]
0x18000dc6a  mov     rsi, [rsp+30h+arg_18]
0x18000dc6f  add     rsp, 30h
0x18000dc73  pop     r15
0x18000dc75  pop     r14
0x18000dc77  pop     r12
0x18000dc79  pop     rdi
0x18000dc7a  pop     rbp
0x18000dc7b  retn
```
