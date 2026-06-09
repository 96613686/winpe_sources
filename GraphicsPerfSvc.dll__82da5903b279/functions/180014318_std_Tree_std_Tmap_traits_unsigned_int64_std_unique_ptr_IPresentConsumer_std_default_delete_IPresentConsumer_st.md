# std::_Tree<std::_Tmap_traits<unsigned __int64,std::unique_ptr<IPresentConsumer,std::default_delete<IPresentConsumer>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer,std::default_delete<IPresentConsumer>>>>,0>>::_Emplace<std::pair<unsigned __int64,std::unique_ptr<IPresentConsumer,std::default_delete<IPresentConsumer>>>>(std::pair<unsigned __int64,std::unique_ptr<IPresentConsumer,std::default_delete<IPresentConsumer>>> &&)

- ea: `0x180014318`
- end: `0x180014424`
- name: `??$_Emplace@U?$pair@_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@1@@Z`
- size: `268`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800146b4`

## callees

- `0x18000b5ec`
- `0x18000c1b8`
- `0x1800142d0`
- `0x180014318`
- `0x180014660`
- `0x1800149dc`
- `0x180015754`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180014372`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180014372`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<unsigned __int64,std::unique_ptr<IPresentConsumer>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>>,0>>::_Emplace<std::pair<unsigned __int64,std::unique_ptr<IPresentConsumer>>>(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 lower; // rax
  _QWORD *v7; // r8
  __int128 v8; // xmm6
  __int64 v9; // rdx
  __int64 *v10; // rbx
  __int64 v11; // rcx
  _OWORD v13[2]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v14; // [rsp+80h] [rbp+8h] BYREF

  lower = std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::_Find_lower_bound<unsigned __int64>(
            a1,
            v13);
  v8 = *(_OWORD *)lower;
  v9 = *(_QWORD *)(lower + 16);
  if ( *(_BYTE *)(v9 + 25) || *v7 < *(_QWORD *)(v9 + 32) )
  {
    if ( a1[1] == 0x555555555555555LL )
      std::_Xlength_error("map/set too long");
    v14 = *a1;
    v13[0] = (unsigned __int64)a1;
    v10 = std::_Allocate<16,std::_Default_allocate_traits>(0x30u);
    std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *>>>::construct<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,std::pair<unsigned __int64,std::unique_ptr<IPresentConsumer>>>(
      v11,
      v10 + 4,
      a3);
    std::_Construct_in_place<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> *,std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> * &>(
      v10,
      &v14);
    std::_Construct_in_place<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> *,std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> * &>(
      v10 + 1,
      &v14);
    std::_Construct_in_place<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> *,std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> * &>(
      v10 + 2,
      &v14);
    *((_WORD *)v10 + 12) = 0;
    *((_QWORD *)&v13[0] + 1) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *>>>(v13);
    v13[0] = v8;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>>>::_Insert_node(
                      a1,
                      v13,
                      v10);
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
0x180014318  push    rbx
0x18001431a  push    rbp
0x18001431b  push    rsi
0x18001431c  push    rdi
0x18001431d  sub     rsp, 58h
0x180014321  movaps  [rsp+78h+var_38], xmm6
0x180014326  mov     rbp, r8
0x180014329  mov     rdi, rdx
0x18001432c  mov     rsi, rcx
0x18001432f  lea     rdx, [rsp+78h+var_58]
0x180014334  call    ??$_Find_lower_bound@_K@?$_Tree@V?$_Tmap_traits@_KV?$shared_ptr@UPresentEvent@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CB_KV?$shared_ptr@UPresentEvent@@@std@@@std@@PEAX@std@@@1@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,std::shared_ptr<PresentEvent>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::shared_ptr<PresentEvent>>>,0>>::_Find_lower_bound<unsigned __int64>(unsigned __int64 const &)
0x180014339  movups  xmm6, xmmword ptr [rax]
0x18001433c  mov     rdx, [rax+10h]
0x180014340  cmp     byte ptr [rdx+19h], 0
0x180014344  jnz     short loc_18001435B
0x180014346  mov     rax, [rdx+20h]
0x18001434a  cmp     [r8], rax
0x18001434d  jb      short loc_18001435B
0x18001434f  mov     [rdi], rdx
0x180014352  mov     byte ptr [rdi+8], 0
0x180014356  jmp     loc_180014413
0x18001435b  mov     rax, 555555555555555h
0x180014365  cmp     [rsi+8], rax
0x180014369  jnz     short loc_180014379
0x18001436b  lea     rcx, aMapSetTooLong; "map/set too long"
0x180014372  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180014379  mov     rax, [rsi]
0x18001437c  mov     [rsp+78h+arg_0], rax
0x180014384  mov     qword ptr [rsp+78h+var_58], rsi
0x180014389  mov     qword ptr [rsp+78h+var_58+8], 0
0x180014392  mov     ecx, 30h ; '0'
0x180014397  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001439c  mov     rbx, rax
0x18001439f  lea     rdx, [rax+20h]
0x1800143a3  mov     r8, rbp
0x1800143a6  call    ??$construct@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@U?$pair@_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@2@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@PEAX@std@@@1@QEAU?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@1@$$QEAU?$pair@_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@1@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *>>>::construct<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,std::pair<unsigned __int64,std::unique_ptr<IPresentConsumer>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *>> &,std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>> * const,std::pair<unsigned __int64,std::unique_ptr<IPresentConsumer>> &&)
0x1800143ab  lea     rdx, [rsp+78h+arg_0]
0x1800143b3  mov     rcx, rbx
0x1800143b6  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> *,std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> * &>(std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> * &,std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> * &)
0x1800143bb  lea     rcx, [rbx+8]
0x1800143bf  lea     rdx, [rsp+78h+arg_0]
0x1800143c7  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> *,std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> * &>(std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> * &,std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> * &)
0x1800143cc  lea     rcx, [rbx+10h]
0x1800143d0  lea     rdx, [rsp+78h+arg_0]
0x1800143d8  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> *,std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> * &>(std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> * &,std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> * &)
0x1800143dd  mov     word ptr [rbx+18h], 0
0x1800143e3  mov     qword ptr [rsp+78h+var_58+8], 0
0x1800143ec  lea     rcx, [rsp+78h+var_58]
0x1800143f1  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *>>>(void)
0x1800143f6  movdqu  [rsp+78h+var_58], xmm6
0x1800143fc  mov     r8, rbx
0x1800143ff  lea     rdx, [rsp+78h+var_58]
0x180014404  mov     rcx, rsi
0x180014407  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@UIPresentConsumer@@U?$default_delete@UIPresentConsumer@@@std@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPresentConsumer>>,void *> * const)
0x18001440c  mov     [rdi], rax
0x18001440f  mov     byte ptr [rdi+8], 1
0x180014413  mov     rax, rdi
0x180014416  movaps  xmm6, [rsp+78h+var_38]
0x18001441b  add     rsp, 58h
0x18001441f  pop     rdi
0x180014420  pop     rsi
0x180014421  pop     rbp
0x180014422  pop     rbx
0x180014423  retn
```
