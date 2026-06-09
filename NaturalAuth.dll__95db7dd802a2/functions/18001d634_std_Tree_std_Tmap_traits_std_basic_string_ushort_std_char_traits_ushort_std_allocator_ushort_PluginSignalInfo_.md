# std::_Tree<std::_Tmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,PluginSignalInfo,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,PluginSignalInfo>>,0>>::_Emplace<std::pair<ushort const *,PluginSignalInfo>>(std::pair<ushort const *,PluginSignalInfo> &&)

- ea: `0x18001d634`
- end: `0x18001d752`
- name: `??$_Emplace@U?$pair@PEBGUPluginSignalInfo@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginSignalInfo@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginSignalInfo@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginSignalInfo@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@PEBGUPluginSignalInfo@@@1@@Z`
- size: `286`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001db48`

## callees

- `0x18000aac4`
- `0x18000ac5c`
- `0x18000c82c`
- `0x18001d634`
- `0x18001d9f8`
- `0x18001da80`
- `0x18001db08`
- `0x18001dd30`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001d70a`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001d70a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Tree<std::_Tmap_traits<std::wstring,PluginSignalInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PluginSignalInfo>>,0>>::_Emplace<std::pair<unsigned short const *,PluginSignalInfo>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 *v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rax
  __int128 v9; // xmm6
  __int64 v10; // r14
  __int64 v11; // rcx
  __int128 v13; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v14[32]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v15; // [rsp+A0h] [rbp+38h] BYREF

  v15 = qword_18005F9A8;
  *(_QWORD *)&v13 = &qword_18005F9A8;
  v5 = std::_Allocate<16,std::_Default_allocate_traits>(0x58u);
  *((_QWORD *)&v13 + 1) = v5;
  std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<std::wstring const,PluginSignalInfo>,void *>>>::construct<std::pair<std::wstring const,PluginSignalInfo>,std::pair<unsigned short const *,PluginSignalInfo>>(
    v6,
    v5 + 4,
    a3);
  std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(
    v5,
    &v15);
  std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(
    v5 + 1,
    &v15);
  std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(
    v5 + 2,
    &v15);
  *((_WORD *)v5 + 12) = 0;
  v8 = std::_Tree<std::_Tmap_traits<std::wstring,PluginSignalInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PluginSignalInfo>>,0>>::_Find_lower_bound<std::wstring>(
         v7,
         v14,
         v5 + 4);
  v9 = *(_OWORD *)v8;
  v10 = *(_QWORD *)(v8 + 16);
  if ( (unsigned __int8)std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Lower_bound_duplicate<std::wstring>(
                          v11,
                          v10,
                          v5 + 4) )
  {
    *(_QWORD *)a2 = v10;
    *(_BYTE *)(a2 + 8) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,PluginSignalInfo>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,PluginSignalInfo>,void *>>>(&v13);
  }
  else
  {
    if ( qword_18005F9B0 == 0x2E8BA2E8BA2E8BALL )
      std::_Xlength_error("map/set too long");
    *((_QWORD *)&v13 + 1) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,PluginSignalInfo>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,PluginSignalInfo>,void *>>>(&v13);
    v13 = v9;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>>>::_Insert_node(
                      &qword_18005F9A8,
                      &v13,
                      v5);
    *(_BYTE *)(a2 + 8) = 1;
  }
  return a2;
}

```

## disassembly

```asm
0x18001d634  mov     [rsp-30h+arg_0], rcx
0x18001d639  push    rbp
0x18001d63a  push    rbx
0x18001d63b  push    rsi
0x18001d63c  push    rdi
0x18001d63d  push    r12
0x18001d63f  push    r14
0x18001d641  mov     rbp, rsp
0x18001d644  sub     rsp, 68h
0x18001d648  movaps  [rsp+68h+var_18], xmm6
0x18001d64d  mov     rbx, r8
0x18001d650  mov     rdi, rdx
0x18001d653  mov     rax, cs:qword_18005F9A8
0x18001d65a  mov     [rbp+arg_0], rax
0x18001d65e  lea     r12, qword_18005F9A8
0x18001d665  mov     qword ptr [rbp+var_48], r12
0x18001d669  mov     qword ptr [rbp+var_48+8], 0
0x18001d671  mov     ecx, 58h ; 'X'
0x18001d676  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001d67b  mov     rsi, rax
0x18001d67e  mov     qword ptr [rbp+var_48+8], rax
0x18001d682  lea     rdx, [rax+20h]
0x18001d686  mov     r8, rbx
0x18001d689  call    ??$construct@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginSignalInfo@@@std@@U?$pair@PEBGUPluginSignalInfo@@@2@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginSignalInfo@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginSignalInfo@@@std@@PEAX@std@@@1@QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginSignalInfo@@@1@$$QEAU?$pair@PEBGUPluginSignalInfo@@@1@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<std::wstring const,PluginSignalInfo>,void *>>>::construct<std::pair<std::wstring const,PluginSignalInfo>,std::pair<ushort const *,PluginSignalInfo>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,PluginSignalInfo>,void *>> &,std::pair<std::wstring const,PluginSignalInfo> * const,std::pair<ushort const *,PluginSignalInfo> &&)
0x18001d68e  lea     rdx, [rbp+arg_0]
0x18001d692  mov     rcx, rsi
0x18001d695  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &)
0x18001d69a  lea     rcx, [rsi+8]
0x18001d69e  lea     rdx, [rbp+arg_0]
0x18001d6a2  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &)
0x18001d6a7  lea     rcx, [rsi+10h]
0x18001d6ab  lea     rdx, [rbp+arg_0]
0x18001d6af  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &)
0x18001d6b4  mov     word ptr [rsi+18h], 0
0x18001d6ba  lea     r8, [rsi+20h]
0x18001d6be  lea     rdx, [rbp+var_38]
0x18001d6c2  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginSignalInfo@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginSignalInfo@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginSignalInfo@@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,PluginSignalInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PluginSignalInfo>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18001d6c7  movups  xmm6, xmmword ptr [rax]
0x18001d6ca  mov     r14, [rax+10h]
0x18001d6ce  lea     r8, [rsi+20h]
0x18001d6d2  mov     rdx, r14
0x18001d6d5  call    ??$_Lower_bound_duplicate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::wstring,void *> * const,std::wstring const &)
0x18001d6da  test    al, al
0x18001d6dc  jz      short loc_18001D6F0
0x18001d6de  mov     [rdi], r14
0x18001d6e1  mov     byte ptr [rdi+8], 0
0x18001d6e5  lea     rcx, [rbp+var_48]
0x18001d6e9  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginSignalInfo@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,PluginSignalInfo>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,PluginSignalInfo>,void *>>>(void)
0x18001d6ee  jmp     short loc_18001D73D
0x18001d6f0  mov     rax, 2E8BA2E8BA2E8BAh
0x18001d6fa  cmp     cs:qword_18005F9B0, rax
0x18001d701  jnz     short loc_18001D711
0x18001d703  lea     rcx, aMapSetTooLong; "map/set too long"
0x18001d70a  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001d711  mov     qword ptr [rbp+var_48+8], 0
0x18001d719  lea     rcx, [rbp+var_48]
0x18001d71d  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UPluginSignalInfo@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,PluginSignalInfo>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,PluginSignalInfo>,void *>>>(void)
0x18001d722  movdqu  [rbp+var_48], xmm6
0x18001d727  mov     r8, rsi
0x18001d72a  lea     rdx, [rbp+var_48]
0x18001d72e  mov     rcx, r12
0x18001d731  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$unique_ptr@VBluetoothSignal@@U?$default_delete@VBluetoothSignal@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VBluetoothSignal@@U?$default_delete@VBluetoothSignal@@@std@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VBluetoothSignal@@U?$default_delete@VBluetoothSignal@@@std@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>,void *> *>,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>,void *> * const)
0x18001d736  mov     [rdi], rax
0x18001d739  mov     byte ptr [rdi+8], 1
0x18001d73d  mov     rax, rdi
0x18001d740  movaps  xmm6, [rsp+68h+var_18]
0x18001d745  add     rsp, 68h
0x18001d749  pop     r14
0x18001d74b  pop     r12
0x18001d74d  pop     rdi
0x18001d74e  pop     rsi
0x18001d74f  pop     rbx
0x18001d750  pop     rbp
0x18001d751  retn
```
