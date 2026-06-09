# std::map<_bstr_t,TaskSchedulerSignal *,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,TaskSchedulerSignal *>>>::_Try_emplace<_bstr_t const &,>(_bstr_t const &)

- ea: `0x1800291d0`
- end: `0x1800292de`
- name: `??$_Try_emplace@AEBV_bstr_t@@$$V@?$map@V_bstr_t@@PEAVTaskSchedulerSignal@@U?$less@V_bstr_t@@@std@@V?$allocator@U?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@std@@@4@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@std@@PEAX@std@@_N@1@AEBV_bstr_t@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(__int64, __int64, const struct _bstr_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task`

## callers

- `0x18002a01c`

## callees

- `0x18000aac4`
- `0x18000ac5c`
- `0x18000c82c`
- `0x1800290b4`
- `0x1800291a4`
- `0x1800291d0`
- `0x1800293c0`
- `0x180029708`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002922c`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002922c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::map<_bstr_t,TaskSchedulerSignal *>::_Try_emplace<_bstr_t const &,>(
        __int64 a1,
        __int64 a2,
        const struct _bstr_t *a3)
{
  __int64 v5; // rbx
  __int64 v6; // rcx
  __int64 *v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // r8
  __int128 v11; // [rsp+30h] [rbp-30h] BYREF
  __int128 v12; // [rsp+40h] [rbp-20h] BYREF
  __int64 v13; // [rsp+50h] [rbp-10h]
  __int64 v14; // [rsp+80h] [rbp+20h] BYREF
  const struct _bstr_t *v15; // [rsp+98h] [rbp+38h] BYREF

  v14 = a1;
  std::_Tree<std::_Tmap_traits<_bstr_t,TaskSchedulerSignal *,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,TaskSchedulerSignal *>>,0>>::_Find_lower_bound<_bstr_t>(
    a1,
    &v12,
    a3);
  v5 = v13;
  if ( std::_Tree<std::_Tmap_traits<_bstr_t,TaskSchedulerSignal *,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,TaskSchedulerSignal *>>,0>>::_Lower_bound_duplicate<_bstr_t>(
         v6,
         v13,
         a3) )
  {
    *(_QWORD *)a2 = v5;
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( qword_18005F9E8 == 0x555555555555555LL )
      std::_Xlength_error("map/set too long");
    v15 = a3;
    v14 = qword_18005F9E0;
    *(_QWORD *)&v11 = &qword_18005F9E0;
    v7 = std::_Allocate<16,std::_Default_allocate_traits>(0x30u);
    std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<_bstr_t const,TaskSchedulerSignal *>,void *>>>::construct<std::pair<_bstr_t const,TaskSchedulerSignal *>,std::piecewise_construct_t const &,std::tuple<_bstr_t const &>,std::tuple<>>(
      v8,
      v7 + 4,
      v9,
      &v15);
    std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(
      v7,
      &v14);
    std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(
      v7 + 1,
      &v14);
    std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(
      v7 + 2,
      &v14);
    *((_WORD *)v7 + 12) = 0;
    *((_QWORD *)&v11 + 1) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_bstr_t const,TaskSchedulerSignal *>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_bstr_t const,TaskSchedulerSignal *>,void *>>>(&v11);
    v11 = v12;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>>>::_Insert_node(
                      &qword_18005F9E0,
                      &v11,
                      v7);
    *(_BYTE *)(a2 + 8) = 1;
  }
  return a2;
}

```

## disassembly

```asm
0x1800291d0  mov     [rsp-18h+arg_8], rbx
0x1800291d5  mov     [rsp-18h+arg_0], rcx
0x1800291da  push    rbp
0x1800291db  push    rsi
0x1800291dc  push    rdi
0x1800291dd  mov     rbp, rsp
0x1800291e0  sub     rsp, 60h
0x1800291e4  mov     rsi, r8
0x1800291e7  mov     rdi, rdx
0x1800291ea  lea     rdx, [rbp+var_20]
0x1800291ee  call    ??$_Find_lower_bound@V_bstr_t@@@?$_Tree@V?$_Tmap_traits@V_bstr_t@@PEAVTaskSchedulerSignal@@U?$less@V_bstr_t@@@std@@V?$allocator@U?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@std@@@4@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@std@@PEAX@std@@@1@AEBV_bstr_t@@@Z; std::_Tree<std::_Tmap_traits<_bstr_t,TaskSchedulerSignal *,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,TaskSchedulerSignal *>>,0>>::_Find_lower_bound<_bstr_t>(_bstr_t const &)
0x1800291f3  mov     r8, rsi
0x1800291f6  mov     rbx, [rbp+var_10]
0x1800291fa  mov     rdx, rbx
0x1800291fd  call    ??$_Lower_bound_duplicate@V_bstr_t@@@?$_Tree@V?$_Tmap_traits@V_bstr_t@@PEAVTaskSchedulerSignal@@U?$less@V_bstr_t@@@std@@V?$allocator@U?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@std@@@4@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@std@@PEAX@1@AEBV_bstr_t@@@Z; std::_Tree<std::_Tmap_traits<_bstr_t,TaskSchedulerSignal *,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,TaskSchedulerSignal *>>,0>>::_Lower_bound_duplicate<_bstr_t>(std::_Tree_node<std::pair<_bstr_t const,TaskSchedulerSignal *>,void *> * const,_bstr_t const &)
0x180029202  test    al, al
0x180029204  jz      short loc_180029212
0x180029206  mov     [rdi], rbx
0x180029209  mov     byte ptr [rdi+8], 0
0x18002920d  jmp     loc_1800292CB
0x180029212  mov     rax, 555555555555555h
0x18002921c  cmp     cs:qword_18005F9E8, rax
0x180029223  jnz     short loc_180029233
0x180029225  lea     rcx, aMapSetTooLong; "map/set too long"
0x18002922c  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180029233  mov     [rbp+arg_18], rsi
0x180029237  mov     rax, cs:qword_18005F9E0
0x18002923e  mov     [rbp+arg_0], rax
0x180029242  lea     rsi, qword_18005F9E0
0x180029249  mov     qword ptr [rbp+var_30], rsi
0x18002924d  mov     qword ptr [rbp+var_30+8], 0
0x180029255  mov     ecx, 30h ; '0'
0x18002925a  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18002925f  mov     rbx, rax
0x180029262  lea     rdx, [rax+20h]
0x180029266  lea     r9, [rbp+arg_18]
0x18002926a  call    ??$construct@U?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@std@@AEBUpiecewise_construct_t@2@V?$tuple@AEBV_bstr_t@@@2@V?$tuple@$$V@2@@?$_Default_allocator_traits@V?$allocator@U?$_Tree_node@U?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@std@@PEAX@std@@@1@QEAU?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@AEBV_bstr_t@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Default_allocator_traits<std::allocator<std::_Tree_node<std::pair<_bstr_t const,TaskSchedulerSignal *>,void *>>>::construct<std::pair<_bstr_t const,TaskSchedulerSignal *>,std::piecewise_construct_t const &,std::tuple<_bstr_t const &>,std::tuple<>>(std::allocator<std::_Tree_node<std::pair<_bstr_t const,TaskSchedulerSignal *>,void *>> &,std::pair<_bstr_t const,TaskSchedulerSignal *> * const,std::piecewise_construct_t const &,std::tuple<_bstr_t const &> &&,std::tuple<> &&)
0x18002926f  lea     rdx, [rbp+arg_0]
0x180029273  mov     rcx, rbx
0x180029276  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &)
0x18002927b  lea     rcx, [rbx+8]
0x18002927f  lea     rdx, [rbp+arg_0]
0x180029283  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &)
0x180029288  lea     rcx, [rbx+10h]
0x18002928c  lea     rdx, [rbp+arg_0]
0x180029290  call    ??$_Construct_in_place@PEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@std@@AEAPEAU12@@std@@YAXAEAPEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@@std@@PEAX@0@0@Z; std::_Construct_in_place<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> *,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &>(std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<GenericPlugin::Signal>>,void *> * &)
0x180029295  mov     word ptr [rbx+18h], 0
0x18002929b  mov     qword ptr [rbp+var_30+8], 0
0x1800292a3  lea     rcx, [rbp+var_30]
0x1800292a7  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_bstr_t const,TaskSchedulerSignal *>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<_bstr_t const,TaskSchedulerSignal *>,void *>>>(void)
0x1800292ac  movups  xmm0, [rbp+var_20]
0x1800292b0  movdqu  [rbp+var_30], xmm0
0x1800292b5  mov     r8, rbx
0x1800292b8  lea     rdx, [rbp+var_30]
0x1800292bc  mov     rcx, rsi
0x1800292bf  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$unique_ptr@VBluetoothSignal@@U?$default_delete@VBluetoothSignal@@@std@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VBluetoothSignal@@U?$default_delete@VBluetoothSignal@@@std@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_JV?$unique_ptr@VBluetoothSignal@@U?$default_delete@VBluetoothSignal@@@std@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>,void *> *>,std::_Tree_node<std::pair<__int64 const,std::unique_ptr<BluetoothSignal>>,void *> * const)
0x1800292c4  mov     [rdi], rax
0x1800292c7  mov     byte ptr [rdi+8], 1
0x1800292cb  mov     rax, rdi
0x1800292ce  mov     rbx, [rsp+60h+arg_8]
0x1800292d6  add     rsp, 60h
0x1800292da  pop     rdi
0x1800292db  pop     rsi
0x1800292dc  pop     rbp
0x1800292dd  retn
```
