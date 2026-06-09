# inverted::CInvertedIndex::~CInvertedIndex(void)

- ea: `0x18014de0c`
- end: `0x18014e13f`
- name: `??1CInvertedIndex@inverted@@UEAA@XZ`
- size: `819`
- prototype: `void __fastcall(inverted::CInvertedIndex *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18021a160`

## callees

- `0x180036d60`
- `0x180046788`
- `0x180048bc8`
- `0x1800798a8`
- `0x18008b084`
- `0x18009729c`
- `0x1800a6928`
- `0x1800c6dac`
- `0x1800c89fc`
- `0x1800f2ee8`
- `0x18013cd74`
- `0x18013dde4`
- `0x18013e624`
- `0x18013e868`
- `0x180147024`
- `0x18014de0c`
- `0x18014e148`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18014e02c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18014e02c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18014de4b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18014de61`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18014de4b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18014de61`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18014e005`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18014e012`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18014e01f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18014e005`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18014e012`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18014e01f`

## pseudocode

```c
void __fastcall inverted::CInvertedIndex::~CInvertedIndex(inverted::CInvertedIndex *this)
{
  __int64 v2; // rcx
  std::_Ref_count_base *v3; // rcx
  std::_Ref_count_base *v4; // rcx
  std::_Ref_count_base *v5; // rcx
  std::_Ref_count_base *v6; // rcx
  __int64 v7; // rcx
  std::_Ref_count_base *v8; // rcx
  std::_Ref_count_base *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  std::_Ref_count_base *v12; // rcx
  std::_Ref_count_base *v13; // rcx
  std::_Ref_count_base *v14; // rcx
  std::_Ref_count_base *v15; // rcx
  std::_Ref_count_base *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  std::_Ref_count_base *v20; // rcx

  *(_QWORD *)this = &inverted::CInvertedIndex::`vftable'{for `inverted::IInvertedIndex'};
  *((_QWORD *)this + 1) = &inverted::CInvertedIndex::`vftable'{for `inverted::IStoreAppData'};
  inverted::CInvertedIndex::_StopAllRunningMerges(this);
  *((_BYTE *)this + 481) = 0;
  WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 59), 1);
  *((_BYTE *)this + 465) = 0;
  WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 57), 1);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl'::`2'::impl) )
  {
    v2 = *((_QWORD *)this + 32);
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 48LL))(v2);
  }
  std::unique_ptr<inverted::IEmbeddingTableProvider>::~unique_ptr<inverted::IEmbeddingTableProvider>((char *)this + 1104);
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 137);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  v4 = (std::_Ref_count_base *)*((_QWORD *)this + 135);
  if ( v4 )
    std::_Ref_count_base::_Decref(v4);
  __1___Tree_V___Tmap_traits_V__array_E_0EE__std__V__map_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___KU__less_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2_V__allocator_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___K_std___2__2_U__less_V__array_E_0EE__std___2_V__allocator_U__pair___CBV__array_E_0EE__std__V__map_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___KU__less_V__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___2_V__allocator_U__pair___CBV__basic_string__WU__char_traits__W_std__V__allocator__W_2__std___K_std___2__2__std___2__0A__std___std__QEAA_XZ((char *)this + 1032);
  sparse_bit_allocator<unsigned __int64>::~sparse_bit_allocator<unsigned __int64>((char *)this + 904);
  v5 = (std::_Ref_count_base *)*((_QWORD *)this + 112);
  if ( v5 )
    std::_Ref_count_base::_Decref(v5);
  v6 = (std::_Ref_count_base *)*((_QWORD *)this + 110);
  if ( v6 )
    std::_Ref_count_base::_Decref(v6);
  v7 = *((_QWORD *)this + 105);
  if ( v7 )
  {
    std::_Deallocate<16>(v7, (*((_QWORD *)this + 107) - v7) & 0xFFFFFFFFFFFFFFF0uLL);
    *((_QWORD *)this + 105) = 0;
    *((_QWORD *)this + 106) = 0;
    *((_QWORD *)this + 107) = 0;
  }
  std::_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<inverted::IContext>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<inverted::IContext>>>,0>>::~_Tree<std::_Tmap_traits<unsigned int,std::shared_ptr<inverted::IContext>,std::less<unsigned int>,std::allocator<std::pair<unsigned int const,std::shared_ptr<inverted::IContext>>>,0>>((char *)this + 824);
  v8 = (std::_Ref_count_base *)*((_QWORD *)this + 102);
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
  v9 = (std::_Ref_count_base *)*((_QWORD *)this + 100);
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
  std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const,unsigned int>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<unsigned short const,unsigned int>,void *>>>(
    (char *)this + 776,
    (char *)this + 776);
  std::_Tree<std::_Tmap_traits<unsigned long,unsigned int,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,unsigned int>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,unsigned int,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,unsigned int>>,0>>((char *)this + 760);
  v10 = *((_QWORD *)this + 92);
  if ( v10 )
  {
    std::_Deallocate<16>(v10, 4 * ((*((_QWORD *)this + 94) - v10) >> 2));
    *((_QWORD *)this + 92) = 0;
    *((_QWORD *)this + 93) = 0;
    *((_QWORD *)this + 94) = 0;
  }
  v11 = *((_QWORD *)this + 89);
  if ( v11 )
  {
    std::_Deallocate<16>(v11, 4 * ((*((_QWORD *)this + 91) - v11) >> 2));
    *((_QWORD *)this + 89) = 0;
    *((_QWORD *)this + 90) = 0;
    *((_QWORD *)this + 91) = 0;
  }
  CloseHandle(*((HANDLE *)this + 88));
  CloseHandle(*((HANDLE *)this + 87));
  CloseHandle(*((HANDLE *)this + 84));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 632));
  std::_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>::~_Tree<std::_Tset_traits<unsigned int,std::less<unsigned int>,std::allocator<unsigned int>,0>>((char *)this + 608);
  std::vector<std::shared_ptr<inverted::IInvertedIndex>>::_Tidy((char *)this + 584);
  std::vector<std::shared_ptr<inverted::IInvertedIndex>>::_Tidy((char *)this + 560);
  std::vector<std::shared_ptr<inverted::IInvertedIndex>>::_Tidy((char *)this + 536);
  v12 = (std::_Ref_count_base *)*((_QWORD *)this + 66);
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
  std::wstring::_Tidy_deallocate((char *)this + 488);
  CThreadPoolWork::~CThreadPoolWork((inverted::CInvertedIndex *)((char *)this + 472));
  CThreadPoolWork::~CThreadPoolWork((inverted::CInvertedIndex *)((char *)this + 456));
  v13 = (std::_Ref_count_base *)*((_QWORD *)this + 56);
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
  v14 = (std::_Ref_count_base *)*((_QWORD *)this + 33);
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  v15 = (std::_Ref_count_base *)*((_QWORD *)this + 31);
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
  v16 = (std::_Ref_count_base *)*((_QWORD *)this + 29);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  std::function<dynamic_sparse_bit<unsigned __int64> (void)>::~function<dynamic_sparse_bit<unsigned __int64> (void)>((char *)this + 160);
  v18 = *((_QWORD *)this + 19);
  if ( v18 )
  {
    LOBYTE(v17) = v18 != (_QWORD)this + 96;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 32LL))(v18, v17);
    *((_QWORD *)this + 19) = 0;
  }
  v19 = *((_QWORD *)this + 11);
  if ( v19 )
  {
    LOBYTE(v17) = v19 != (_QWORD)this + 32;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 32LL))(v19, v17);
    *((_QWORD *)this + 11) = 0;
  }
  v20 = (std::_Ref_count_base *)*((_QWORD *)this + 3);
  if ( v20 )
    std::_Ref_count_base::_Decwref(v20);
}

```

## disassembly

```asm
0x18014de0c  push    rbx
0x18014de0e  push    rbp
0x18014de0f  push    rsi
0x18014de10  push    rdi
0x18014de11  push    r14
0x18014de13  sub     rsp, 20h
0x18014de17  mov     rbx, rcx
0x18014de1a  lea     rax, ??_7CInvertedIndex@inverted@@6BIInvertedIndex@1@@; const inverted::CInvertedIndex::`vftable'{for `inverted::IInvertedIndex'}
0x18014de21  mov     [rcx], rax
0x18014de24  lea     rax, ??_7CInvertedIndex@inverted@@6BIStoreAppData@1@@; const inverted::CInvertedIndex::`vftable'{for `inverted::IStoreAppData'}
0x18014de2b  mov     [rcx+8], rax
0x18014de2f  call    ?_StopAllRunningMerges@CInvertedIndex@inverted@@AEAAXXZ; inverted::CInvertedIndex::_StopAllRunningMerges(void)
0x18014de34  lea     rdi, [rbx+1D8h]
0x18014de3b  xor     r14d, r14d
0x18014de3e  mov     [rdi+9], r14b
0x18014de42  lea     ebp, [r14+1]
0x18014de46  mov     edx, ebp; fCancelPendingCallbacks
0x18014de48  mov     rcx, [rdi]; pwk
0x18014de4b  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18014de51  lea     rsi, [rbx+1C8h]
0x18014de58  mov     [rsi+9], r14b
0x18014de5c  mov     edx, ebp; fCancelPendingCallbacks
0x18014de5e  mov     rcx, [rsi]; pwk
0x18014de61  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18014de67  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_47942714@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714> `wil::Feature<__WilFeatureTraits_Feature_47942714>::GetImpl(void)'::`2'::impl
0x18014de6e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_47942714@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_47942714>::__private_IsEnabled(void)
0x18014de73  test    al, al
0x18014de75  jz      short loc_18014DE8F
0x18014de77  mov     rcx, [rbx+100h]
0x18014de7e  test    rcx, rcx
0x18014de81  jz      short loc_18014DE8F
0x18014de83  mov     rax, [rcx]
0x18014de86  mov     rax, [rax+30h]
0x18014de8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014de8f  lea     rcx, [rbx+450h]
0x18014de96  call    ??1?$unique_ptr@UIEmbeddingTableProvider@inverted@@U?$default_delete@UIEmbeddingTableProvider@inverted@@@std@@@std@@QEAA@XZ; std::unique_ptr<inverted::IEmbeddingTableProvider>::~unique_ptr<inverted::IEmbeddingTableProvider>(void)
0x18014de9b  mov     rcx, [rbx+448h]; this
0x18014dea2  test    rcx, rcx
0x18014dea5  jz      short loc_18014DEAC
0x18014dea7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18014deac  mov     rcx, [rbx+438h]; this
0x18014deb3  test    rcx, rcx
0x18014deb6  jz      short loc_18014DEBD
0x18014deb8  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18014debd  lea     rcx, [rbx+408h]
0x18014dec4  call    ??1?$_Tree@V?$_Tmap_traits@V?$array@E$0EE@@std@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@@2@U?$less@V?$array@E$0EE@@std@@@2@V?$allocator@U?$pair@$$CBV?$array@E$0EE@@std@@V?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_KU?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_K@std@@@2@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ
0x18014dec9  lea     rcx, [rbx+388h]
0x18014ded0  call    ??1?$sparse_bit_allocator@_K@@QEAA@XZ; sparse_bit_allocator<unsigned __int64>::~sparse_bit_allocator<unsigned __int64>(void)
0x18014ded5  mov     rcx, [rbx+380h]; this
0x18014dedc  test    rcx, rcx
0x18014dedf  jz      short loc_18014DEE6
0x18014dee1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18014dee6  mov     rcx, [rbx+370h]; this
0x18014deed  test    rcx, rcx
0x18014def0  jz      short loc_18014DEF7
0x18014def2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18014def7  mov     rcx, [rbx+348h]
0x18014defe  test    rcx, rcx
0x18014df01  jz      short loc_18014DF2B
0x18014df03  mov     rdx, [rbx+358h]
0x18014df0a  sub     rdx, rcx
0x18014df0d  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18014df11  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18014df16  mov     [rbx+348h], r14
0x18014df1d  mov     [rbx+350h], r14
0x18014df24  mov     [rbx+358h], r14
0x18014df2b  lea     rcx, [rbx+338h]
0x18014df32  call    ??1?$_Tree@V?$_Tmap_traits@IV?$shared_ptr@UIContext@inverted@@@std@@U?$less@I@2@V?$allocator@U?$pair@$$CBIV?$shared_ptr@UIContext@inverted@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<uint,std::shared_ptr<inverted::IContext>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<inverted::IContext>>>,0>>::~_Tree<std::_Tmap_traits<uint,std::shared_ptr<inverted::IContext>,std::less<uint>,std::allocator<std::pair<uint const,std::shared_ptr<inverted::IContext>>>,0>>(void)
0x18014df37  mov     rcx, [rbx+330h]; this
0x18014df3e  test    rcx, rcx
0x18014df41  jz      short loc_18014DF48
0x18014df43  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18014df48  mov     rcx, [rbx+320h]; this
0x18014df4f  test    rcx, rcx
0x18014df52  jz      short loc_18014DF59
0x18014df54  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18014df59  lea     rcx, [rbx+308h]
0x18014df60  mov     rdx, rcx
0x18014df63  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBGI@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBGI@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBGI@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const,uint>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<ushort const,uint>,void *>>>(std::allocator<std::_Tree_node<std::pair<ushort const,uint>,void *>> &)
0x18014df68  lea     rcx, [rbx+2F8h]
0x18014df6f  call    ??1?$_Tree@V?$_Tmap_traits@KIU?$less@K@std@@V?$allocator@U?$pair@$$CBKI@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,uint,std::less<ulong>,std::allocator<std::pair<ulong const,uint>>,0>>::~_Tree<std::_Tmap_traits<ulong,uint,std::less<ulong>,std::allocator<std::pair<ulong const,uint>>,0>>(void)
0x18014df74  mov     rcx, [rbx+2E0h]
0x18014df7b  mov     rbp, 0AAAAAAAAAAAAAAABh
0x18014df85  test    rcx, rcx
0x18014df88  jz      short loc_18014DFBE
0x18014df8a  mov     rax, [rbx+2F0h]
0x18014df91  sub     rax, rcx
0x18014df94  sar     rax, 2
0x18014df98  imul    rax, rbp
0x18014df9c  lea     rdx, [rax+rax*2]
0x18014dfa0  shl     rdx, 2
0x18014dfa4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18014dfa9  mov     [rbx+2E0h], r14
0x18014dfb0  mov     [rbx+2E8h], r14
0x18014dfb7  mov     [rbx+2F0h], r14
0x18014dfbe  mov     rcx, [rbx+2C8h]
0x18014dfc5  test    rcx, rcx
0x18014dfc8  jz      short loc_18014DFFE
0x18014dfca  mov     rax, [rbx+2D8h]
0x18014dfd1  sub     rax, rcx
0x18014dfd4  sar     rax, 2
0x18014dfd8  imul    rax, rbp
0x18014dfdc  lea     rdx, [rax+rax*2]
0x18014dfe0  shl     rdx, 2
0x18014dfe4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18014dfe9  mov     [rbx+2C8h], r14
0x18014dff0  mov     [rbx+2D0h], r14
0x18014dff7  mov     [rbx+2D8h], r14
0x18014dffe  mov     rcx, [rbx+2C0h]; hObject
0x18014e005  call    cs:__imp_CloseHandle
0x18014e00b  mov     rcx, [rbx+2B8h]; hObject
0x18014e012  call    cs:__imp_CloseHandle
0x18014e018  mov     rcx, [rbx+2A0h]; hObject
0x18014e01f  call    cs:__imp_CloseHandle
0x18014e025  lea     rcx, [rbx+278h]; lpCriticalSection
0x18014e02c  call    cs:__imp_DeleteCriticalSection
0x18014e032  lea     rcx, [rbx+260h]
0x18014e039  call    ??1?$_Tree@V?$_Tset_traits@IU?$less@I@std@@V?$allocator@I@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>::~_Tree<std::_Tset_traits<uint,std::less<uint>,std::allocator<uint>,0>>(void)
0x18014e03e  lea     rcx, [rbx+248h]
0x18014e045  call    ?_Tidy@?$vector@V?$shared_ptr@UIInvertedIndex@inverted@@@std@@V?$allocator@V?$shared_ptr@UIInvertedIndex@inverted@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<inverted::IInvertedIndex>>::_Tidy(void)
0x18014e04a  lea     rcx, [rbx+230h]
0x18014e051  call    ?_Tidy@?$vector@V?$shared_ptr@UIInvertedIndex@inverted@@@std@@V?$allocator@V?$shared_ptr@UIInvertedIndex@inverted@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<inverted::IInvertedIndex>>::_Tidy(void)
0x18014e056  lea     rcx, [rbx+218h]
0x18014e05d  call    ?_Tidy@?$vector@V?$shared_ptr@UIInvertedIndex@inverted@@@std@@V?$allocator@V?$shared_ptr@UIInvertedIndex@inverted@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<inverted::IInvertedIndex>>::_Tidy(void)
0x18014e062  mov     rcx, [rbx+210h]; this
0x18014e069  test    rcx, rcx
0x18014e06c  jz      short loc_18014E073
0x18014e06e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18014e073  lea     rcx, [rbx+1E8h]
0x18014e07a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18014e07f  mov     rcx, rdi; this
0x18014e082  call    ??1CThreadPoolWork@@QEAA@XZ; CThreadPoolWork::~CThreadPoolWork(void)
0x18014e087  mov     rcx, rsi; this
0x18014e08a  call    ??1CThreadPoolWork@@QEAA@XZ; CThreadPoolWork::~CThreadPoolWork(void)
0x18014e08f  mov     rcx, [rbx+1C0h]; this
0x18014e096  test    rcx, rcx
0x18014e099  jz      short loc_18014E0A0
0x18014e09b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18014e0a0  mov     rcx, [rbx+108h]; this
0x18014e0a7  test    rcx, rcx
0x18014e0aa  jz      short loc_18014E0B1
0x18014e0ac  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18014e0b1  mov     rcx, [rbx+0F8h]; this
0x18014e0b8  test    rcx, rcx
0x18014e0bb  jz      short loc_18014E0C2
0x18014e0bd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18014e0c2  mov     rcx, [rbx+0E8h]; this
0x18014e0c9  test    rcx, rcx
0x18014e0cc  jz      short loc_18014E0D3
0x18014e0ce  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18014e0d3  lea     rcx, [rbx+0A0h]
0x18014e0da  call    ??1?$function@$$A6A?AU?$dynamic_sparse_bit@_K@@XZ@std@@QEAA@XZ; std::function<dynamic_sparse_bit<unsigned __int64> (void)>::~function<dynamic_sparse_bit<unsigned __int64> (void)>(void)
0x18014e0df  lea     rdi, [rbx+60h]
0x18014e0e3  mov     rcx, [rdi+38h]
0x18014e0e7  test    rcx, rcx
0x18014e0ea  jz      short loc_18014E102
0x18014e0ec  mov     rax, [rcx]
0x18014e0ef  cmp     rcx, rdi
0x18014e0f2  setnz   dl
0x18014e0f5  mov     rax, [rax+20h]
0x18014e0f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014e0fe  mov     [rdi+38h], r14
0x18014e102  lea     rdi, [rbx+20h]
0x18014e106  mov     rcx, [rdi+38h]
0x18014e10a  test    rcx, rcx
0x18014e10d  jz      short loc_18014E125
0x18014e10f  mov     rax, [rcx]
0x18014e112  cmp     rcx, rdi
0x18014e115  setnz   dl
0x18014e118  mov     rax, [rax+20h]
0x18014e11c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014e121  mov     [rdi+38h], r14
0x18014e125  mov     rcx, [rbx+18h]; this
0x18014e129  test    rcx, rcx
0x18014e12c  jz      short loc_18014E134
0x18014e12e  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18014e133  nop
0x18014e134  add     rsp, 20h
0x18014e138  pop     r14
0x18014e13a  pop     rdi
0x18014e13b  pop     rsi
0x18014e13c  pop     rbp
0x18014e13d  pop     rbx
0x18014e13e  retn
```
