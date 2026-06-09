# std::map<__int64,std::unique_ptr<GenericPlugin::Signal,std::default_delete<GenericPlugin::Signal>>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal,std::default_delete<GenericPlugin::Signal>>>>>::_Try_emplace<__int64 const &,>(__int64 const &)

- ea: `0x18002cf10`
- end: `0x18002d001`
- name: `??$_Try_emplace@AEB_J$$V@?$map@_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@U?$less@_J@2@V?$allocator@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@std@@_N@1@AEB_J@Z`
- size: `241`
- prototype: `__int64 __fastcall(__int64 *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18002d2f0`

## callees

- `0x18000aac4`
- `0x18000ac5c`
- `0x18000b290`
- `0x18000c82c`
- `0x18002cebc`
- `0x18002cf10`
- `0x18002d03c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002cf61`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002cf61`

## pseudocode

```c
__int64 __fastcall std::map<__int64,std::unique_ptr<GenericPlugin::Signal>>::_Try_emplace<__int64 const &,>(
        __int64 *a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v5; // r8
  __int64 *v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // r8
  _QWORD *v10; // [rsp+30h] [rbp-48h] BYREF
  __int128 v11; // [rsp+40h] [rbp-38h] BYREF
  __int128 v12; // [rsp+50h] [rbp-28h] BYREF
  __int64 v13; // [rsp+60h] [rbp-18h]
  __int64 v14; // [rsp+B8h] [rbp+40h] BYREF

  std::_Tree<std::_Tmap_traits<__int64,std::unique_ptr<GenericPlugin::Signal>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>>,0>>::_Find_lower_bound<__int64>(
    a1,
    &v12,
    a3);
  if ( *(_BYTE *)(v13 + 25) || *v5 < *(_QWORD *)(v13 + 32) )
  {
    if ( a1[1] == 0x555555555555555LL )
      std::_Xlength_error("map/set too long");
    v10 = v5;
    v14 = *a1;
    v11 = (unsigned __int64)a1;
    v6 = std::_Allocate<16,std::_Default_allocate_traits>(0x30u);
    std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>,void *>>>::construct<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>,std::piecewise_construct_t const &,std::tuple<__int64 const &>,std::tuple<>>(
      v7,
      v6 + 4,
      v8,
      &v10);
    std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(
      v6,
      &v14);
    std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(
      v6 + 1,
      &v14);
    std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(
      v6 + 2,
      &v14);
    *((_WORD *)v6 + 12) = 0;
    *((_QWORD *)&v11 + 1) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *>>>(&v11);
    v11 = v12;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>>>::_Insert_node(
                      a1,
                      &v11,
                      v6);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v13;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x18002cf10  push    rbp
0x18002cf12  push    rbx
0x18002cf13  push    rsi
0x18002cf14  push    rdi
0x18002cf15  mov     rbp, rsp
0x18002cf18  sub     rsp, 78h
0x18002cf1c  mov     rdi, rdx
0x18002cf1f  mov     rsi, rcx
0x18002cf22  lea     rdx, [rbp+var_28]
0x18002cf26  call    ??$_Find_lower_bound@_J@?$_Tree@V?$_Tmap_traits@_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@U?$less@_J@2@V?$allocator@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@std@@@1@AEB_J@Z; std::_Tree<std::_Tmap_traits<__int64,std::unique_ptr<GenericPlugin::Signal>,std::less<__int64>,std::allocator<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>>,0>>::_Find_lower_bound<__int64>(__int64 const &)
0x18002cf2b  mov     rdx, [rbp+var_18]
0x18002cf2f  cmp     byte ptr [rdx+19h], 0
0x18002cf33  jnz     short loc_18002CF4A
0x18002cf35  mov     rax, [rdx+20h]
0x18002cf39  cmp     [r8], rax
0x18002cf3c  jl      short loc_18002CF4A
0x18002cf3e  mov     [rdi], rdx
0x18002cf41  mov     byte ptr [rdi+8], 0
0x18002cf45  jmp     loc_18002CFF5
0x18002cf4a  mov     rax, 555555555555555h
0x18002cf54  cmp     [rsi+8], rax
0x18002cf58  jnz     short loc_18002CF68
0x18002cf5a  lea     rcx, aMapSetTooLong; "map/set too long"
0x18002cf61  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002cf68  mov     [rbp+var_48], r8
0x18002cf6c  mov     rax, [rsi]
0x18002cf6f  mov     [rbp+arg_18], rax
0x18002cf73  mov     qword ptr [rbp+var_38], rsi
0x18002cf77  mov     qword ptr [rbp+var_38+8], 0
0x18002cf7f  mov     ecx, 30h ; '0'
0x18002cf84  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002cf89  mov     rbx, rax
0x18002cf8c  lea     rdx, [rax+20h]
0x18002cf90  lea     r9, [rbp+var_48]
0x18002cf94  call    ??$construct@U?$pair@$$CB_JV?$unique_ptr@VBluetoothSignal@@U?$default_delete@VBluetoothSignal@@@std@@@std@@@std@@AEBUpiecewise_construct_t@2@V?$tuple@AEB_J@2@V?$tuple@$$V@2@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VBluetoothSignal@@U?$default_delete@VBluetoothSignal@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VBluetoothSignal@@U?$default_delete@VBluetoothSignal@@@std@@@std@@@std@@PEAX@std@@@1@QEAU?$pair@$$CB_JV?$unique_ptr@VBluetoothSignal@@U?$default_delete@VBluetoothSignal@@@std@@@std@@@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEB_J@1@$$QEAV?$tuple@$$V@1@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>,void *>>>::construct<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>,std::piecewise_construct_t const &,std::tuple<__int64 const &>,std::tuple<>>(std::allocator<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>,void *>> &,std::pair<__int64 const,std::unique_ptr<BluetoothSignal>> * const,std::piecewise_construct_t const &,std::tuple<__int64 const &> &&,std::tuple<> &&)
0x18002cf99  lea     rdx, [rbp+arg_18]
0x18002cf9d  mov     rcx, rbx
0x18002cfa0  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &)
0x18002cfa5  lea     rcx, [rbx+8]
0x18002cfa9  lea     rdx, [rbp+arg_18]
0x18002cfad  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &)
0x18002cfb2  lea     rcx, [rbx+10h]
0x18002cfb6  lea     rdx, [rbp+arg_18]
0x18002cfba  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &)
0x18002cfbf  mov     word ptr [rbx+18h], 0
0x18002cfc5  mov     qword ptr [rbp+var_38+8], 0
0x18002cfcd  lea     rcx, [rbp+var_38]
0x18002cfd1  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *>>>(void)
0x18002cfd6  movups  xmm0, [rbp+var_28]
0x18002cfda  movdqu  [rbp+var_38], xmm0
0x18002cfdf  mov     r8, rbx
0x18002cfe2  lea     rdx, [rbp+var_38]
0x18002cfe6  mov     rcx, rsi
0x18002cfe9  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$unique_ptr@VBluetoothSignal@@U?$default_delete@VBluetoothSignal@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VBluetoothSignal@@U?$default_delete@VBluetoothSignal@@@std@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VBluetoothSignal@@U?$default_delete@VBluetoothSignal@@@std@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>,void *> *>,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>,void *> * const)
0x18002cfee  mov     [rdi], rax
0x18002cff1  mov     byte ptr [rdi+8], 1
0x18002cff5  mov     rax, rdi
0x18002cff8  add     rsp, 78h
0x18002cffc  pop     rdi
0x18002cffd  pop     rsi
0x18002cffe  pop     rbx
0x18002cfff  pop     rbp
0x18002d000  retn
```
