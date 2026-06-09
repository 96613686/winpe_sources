# std::map<__int64,std::unique_ptr<SignalInfo,std::default_delete<SignalInfo>>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::unique_ptr<SignalInfo,std::default_delete<SignalInfo>>>>>::_Try_emplace<__int64 const &,>(__int64 const &)

- ea: `0x18000b0d0`
- end: `0x18000b1db`
- name: `??$_Try_emplace@AEB_J$$V@?$map@_JV?$unique_ptr@VSignalInfo@@U?$default_delete@VSignalInfo@@@std@@@std@@U?$less@_J@2@V?$allocator@U?$pair@$$CB_JV?$unique_ptr@VSignalInfo@@U?$default_delete@VSignalInfo@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignalInfo@@U?$default_delete@VSignalInfo@@@std@@@std@@@std@@PEAX@std@@_N@1@AEB_J@Z`
- size: `267`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000bbe8`

## callees

- `0x18000aac4`
- `0x18000ac5c`
- `0x18000adbc`
- `0x18000b0d0`
- `0x18000b290`
- `0x18000b4fc`
- `0x18000c82c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000b129`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18000b129`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::map<__int64,std::unique_ptr<SignalInfo>>::_Try_emplace<__int64 const &,>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v4; // r8
  __int64 *v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int128 v9; // [rsp+30h] [rbp-30h] BYREF
  __int128 v10; // [rsp+40h] [rbp-20h] BYREF
  __int64 v11; // [rsp+50h] [rbp-10h]
  __int64 v12; // [rsp+80h] [rbp+20h] BYREF
  _QWORD *v13; // [rsp+98h] [rbp+38h] BYREF

  v12 = a1;
  std::_Tree<std::_Tmap_traits<__int64,std::unique_ptr<SignalInfo>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::unique_ptr<SignalInfo>>>,0>>::_Find_lower_bound<__int64>(
    a1,
    &v10,
    a3);
  if ( *(_BYTE *)(v11 + 25) || *v4 < *(_QWORD *)(v11 + 32) )
  {
    if ( qword_18005F748 == 0x555555555555555LL )
      std::_Xlength_error("map/set too long");
    v13 = v4;
    v12 = qword_18005F740;
    *(_QWORD *)&v9 = &qword_18005F740;
    v5 = std::_Allocate<16,std::_Default_allocate_traits>(0x30u);
    std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>,void *>>>::construct<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>,std::piecewise_construct_t const &,std::tuple<__int64 const &>,std::tuple<>>(
      v6,
      v5 + 4,
      v7,
      &v13);
    std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(
      v5,
      &v12);
    std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(
      v5 + 1,
      &v12);
    std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(
      v5 + 2,
      &v12);
    *((_WORD *)v5 + 12) = 0;
    *((_QWORD *)&v9 + 1) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<SignalInfo>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<SignalInfo>>,void *>>>(&v9);
    v9 = v10;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>>>::_Insert_node(
                      &qword_18005F740,
                      &v9,
                      v5);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v11;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x18000b0d0  mov     [rsp-18h+arg_8], rbx
0x18000b0d5  mov     [rsp-18h+arg_0], rcx
0x18000b0da  push    rbp
0x18000b0db  push    rsi
0x18000b0dc  push    rdi
0x18000b0dd  mov     rbp, rsp
0x18000b0e0  sub     rsp, 60h
0x18000b0e4  mov     rdi, rdx
0x18000b0e7  lea     rdx, [rbp+var_20]
0x18000b0eb  call    ??$_Find_lower_bound@_J@?$_Tree@V?$_Tmap_traits@_JV?$unique_ptr@VSignalInfo@@U?$default_delete@VSignalInfo@@@std@@@std@@U?$less@_J@2@V?$allocator@U?$pair@$$CB_JV?$unique_ptr@VSignalInfo@@U?$default_delete@VSignalInfo@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignalInfo@@U?$default_delete@VSignalInfo@@@std@@@std@@@std@@PEAX@std@@@1@AEB_J@Z; std::_Tree<std::_Tmap_traits<__int64,std::unique_ptr<SignalInfo>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::unique_ptr<SignalInfo>>>,0>>::_Find_lower_bound<__int64>(__int64 const &)
0x18000b0f0  mov     rcx, [rbp+var_10]
0x18000b0f4  cmp     byte ptr [rcx+19h], 0
0x18000b0f8  jnz     short loc_18000B10F
0x18000b0fa  mov     rax, [rcx+20h]
0x18000b0fe  cmp     [r8], rax
0x18000b101  jl      short loc_18000B10F
0x18000b103  mov     [rdi], rcx
0x18000b106  mov     byte ptr [rdi+8], 0
0x18000b10a  jmp     loc_18000B1C8
0x18000b10f  mov     rax, 555555555555555h
0x18000b119  cmp     cs:qword_18005F748, rax
0x18000b120  jnz     short loc_18000B130
0x18000b122  lea     rcx, aMapSetTooLong; "map/set too long"
0x18000b129  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18000b130  mov     [rbp+arg_18], r8
0x18000b134  mov     rax, cs:qword_18005F740
0x18000b13b  mov     [rbp+arg_0], rax
0x18000b13f  lea     rsi, qword_18005F740
0x18000b146  mov     qword ptr [rbp+var_30], rsi
0x18000b14a  mov     qword ptr [rbp+var_30+8], 0
0x18000b152  mov     ecx, 30h ; '0'
0x18000b157  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000b15c  mov     rbx, rax
0x18000b15f  lea     rdx, [rax+20h]
0x18000b163  lea     r9, [rbp+arg_18]
0x18000b167  call    ??$construct@U?$pair@$$CB_JV?$unique_ptr@VBluetoothSignal@@U?$default_delete@VBluetoothSignal@@@std@@@std@@@std@@AEBUpiecewise_construct_t@2@V?$tuple@AEB_J@2@V?$tuple@$$V@2@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VBluetoothSignal@@U?$default_delete@VBluetoothSignal@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VBluetoothSignal@@U?$default_delete@VBluetoothSignal@@@std@@@std@@@std@@PEAX@std@@@1@QEAU?$pair@$$CB_JV?$unique_ptr@VBluetoothSignal@@U?$default_delete@VBluetoothSignal@@@std@@@std@@@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEB_J@1@$$QEAV?$tuple@$$V@1@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>,void *>>>::construct<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>,std::piecewise_construct_t const &,std::tuple<__int64 const &>,std::tuple<>>(std::allocator<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>,void *>> &,std::pair<__int64 const,std::unique_ptr<BluetoothSignal>> * const,std::piecewise_construct_t const &,std::tuple<__int64 const &> &&,std::tuple<> &&)
0x18000b16c  lea     rdx, [rbp+arg_0]
0x18000b170  mov     rcx, rbx
0x18000b173  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &)
0x18000b178  lea     rcx, [rbx+8]
0x18000b17c  lea     rdx, [rbp+arg_0]
0x18000b180  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &)
0x18000b185  lea     rcx, [rbx+10h]
0x18000b189  lea     rdx, [rbp+arg_0]
0x18000b18d  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &)
0x18000b192  mov     word ptr [rbx+18h], 0
0x18000b198  mov     qword ptr [rbp+var_30+8], 0
0x18000b1a0  lea     rcx, [rbp+var_30]
0x18000b1a4  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignalInfo@@U?$default_delete@VSignalInfo@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<SignalInfo>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<SignalInfo>>,void *>>>(void)
0x18000b1a9  movups  xmm0, [rbp+var_20]
0x18000b1ad  movdqu  [rbp+var_30], xmm0
0x18000b1b2  mov     r8, rbx
0x18000b1b5  lea     rdx, [rbp+var_30]
0x18000b1b9  mov     rcx, rsi
0x18000b1bc  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$unique_ptr@VBluetoothSignal@@U?$default_delete@VBluetoothSignal@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VBluetoothSignal@@U?$default_delete@VBluetoothSignal@@@std@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VBluetoothSignal@@U?$default_delete@VBluetoothSignal@@@std@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>,void *> *>,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>,void *> * const)
0x18000b1c1  mov     [rdi], rax
0x18000b1c4  mov     byte ptr [rdi+8], 1
0x18000b1c8  mov     rax, rdi
0x18000b1cb  mov     rbx, [rsp+60h+arg_8]
0x18000b1d3  add     rsp, 60h
0x18000b1d7  pop     rdi
0x18000b1d8  pop     rsi
0x18000b1d9  pop     rbp
0x18000b1da  retn
```
