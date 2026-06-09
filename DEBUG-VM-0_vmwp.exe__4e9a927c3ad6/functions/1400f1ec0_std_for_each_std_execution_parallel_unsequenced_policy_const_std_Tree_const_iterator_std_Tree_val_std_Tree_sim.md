# std::for_each<std::execution::parallel_unsequenced_policy const &,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>>,std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>,0>(std::execution::parallel_unsequenced_policy const &,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>>,std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>)

- ea: `0x1400f1ec0`
- end: `0x1400f2091`
- name: `??$for_each@AEBVparallel_unsequenced_policy@execution@std@@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@@3@V?$function@$$A6AXAEBU?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@Z@3@$0A@@std@@YAXAEBVparallel_unsequenced_policy@execution@0@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@@0@1V?$function@$$A6AXAEBU?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@Z@0@@Z`
- size: `465`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1400b433c`

## callees

- `0x140023f74`
- `0x1400f1ec0`
- `0x1400f2098`
- `0x140132940`
- `0x14022d008`
- `0x14022d0b0`
- `0x14022d460`
- `0x1402369e4`
- `0x140236c6c`
- `0x1402c2010`

## import_xrefs

- `msvcp_win!__std_parallel_algorithms_hw_threads` at `0x1400f1ef7`
- `msvcp_win!__std_parallel_algorithms_hw_threads` at `0x1400f1ef7`
- `msvcp_win!__std_bulk_submit_threadpool_work` at `0x1400f1fbe`
- `msvcp_win!__std_bulk_submit_threadpool_work` at `0x1400f1fbe`
- `msvcp_win!__std_create_threadpool_work` at `0x1400f1f8c`
- `msvcp_win!__std_create_threadpool_work` at `0x1400f1f8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall std::for_each<std::execution::parallel_unsequenced_policy const &,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>>,std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>,0>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v4; // rsi
  __int64 v5; // rdi
  __int64 v6; // rbx
  unsigned __int64 v7; // r14
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // [rsp+20h] [rbp-78h] BYREF
  __int64 v17; // [rsp+28h] [rbp-70h]
  __int64 v18; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int64 v19; // [rsp+38h] [rbp-60h]
  __int64 v20; // [rsp+40h] [rbp-58h]
  __int64 v21; // [rsp+48h] [rbp-50h]
  __int64 v22; // [rsp+50h] [rbp-48h]
  __int128 v23; // [rsp+58h] [rbp-40h] BYREF
  __int64 v24; // [rsp+68h] [rbp-30h]
  __int64 v25; // [rsp+70h] [rbp-28h]

  v4 = a4;
  v5 = a3;
  v6 = a2;
  v17 = a4;
  v7 = (unsigned int)__std_parallel_algorithms_hw_threads();
  if ( v7 <= 1
    || (v8 = std::distance<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>>(
               v6,
               v5),
        v8 < 2) )
  {
LABEL_14:
    std::_For_each_ivdep<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,std::_Ref_fn<std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>>>(
      v6,
      v5,
      v4);
    v15 = *(_QWORD *)(v4 + 56);
    if ( v15 )
    {
      LOBYTE(v14) = v15 != v4;
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v15 + 32LL))(v15, v14);
      *(_QWORD *)(v4 + 56) = 0;
    }
  }
  else
  {
    v9 = 32LL * (unsigned int)v7;
    if ( v8 < (unsigned __int64)v9 )
      v9 = v8;
    try
    {
      v18 = 0;
      v19 = v9;
      v20 = v8;
      v21 = v8 / v9;
      v22 = v8 % v9;
      v23 = 0;
      v24 = 0;
      v25 = v4;
      std::_Static_partition_range<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,__int64,0>::_Populate(
        &v23,
        &v16,
        &v18,
        v6);
      v10 = __std_create_threadpool_work(
              std::_Static_partitioned_for_each2<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,__int64,std::_Ref_fn<std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>>>::_Threadpool_callback,
              &v18,
              0);
      v16 = v10;
      if ( !v10 )
        std::_Throw_parallelism_resources_exhausted();
      v11 = 4 * v7;
      if ( v19 < 4 * v7 )
        v11 = v19;
      __std_bulk_submit_threadpool_work(v10, v11);
      std::_Run_available_chunked_work<std::_Static_partitioned_for_each2<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,__int64,std::_Ref_fn<std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>>>>(&v18);
      std::_Work_ptr::~_Work_ptr((std::_Work_ptr *)&v16);
      if ( (_QWORD)v23 )
      {
        std::_Deallocate<16>(v23, (v24 - v23) & 0xFFFFFFFFFFFFFFF8uLL);
        v23 = 0;
        v24 = 0;
      }
      v13 = *(_QWORD *)(v4 + 56);
      if ( v13 )
      {
        LOBYTE(v12) = v13 != v4;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 32LL))(v13, v12);
        *(_QWORD *)(v4 + 56) = 0;
      }
    }
    catch ( std::_Parallelism_resources_exhausted )
    {
      v5 = a3;
      v6 = a2;
      v4 = v17;
      goto LABEL_14;
    }
  }
}

```

## disassembly

```asm
0x1400f1ec0  mov     [rsp+arg_0], rbx
0x1400f1ec5  mov     [rsp+arg_10], r8
0x1400f1eca  mov     [rsp+arg_8], rdx
0x1400f1ecf  push    rsi
0x1400f1ed0  push    rdi
0x1400f1ed1  push    r14
0x1400f1ed3  sub     rsp, 80h
0x1400f1eda  mov     rax, cs:__security_cookie
0x1400f1ee1  xor     rax, rsp
0x1400f1ee4  mov     [rsp+98h+var_20], rax
0x1400f1ee9  mov     rsi, r9
0x1400f1eec  mov     rdi, r8
0x1400f1eef  mov     rbx, rdx
0x1400f1ef2  mov     [rsp+98h+var_70], r9
0x1400f1ef7  call    cs:__imp___std_parallel_algorithms_hw_threads
0x1400f1efe  nop     dword ptr [rax+rax+00h]
0x1400f1f03  mov     r14d, eax
0x1400f1f06  cmp     r14, 1
0x1400f1f0a  jbe     loc_1400F203F
0x1400f1f10  mov     rdx, rdi
0x1400f1f13  mov     rcx, rbx
0x1400f1f16  call    ??$distance@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@YA_JV?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@0@0@Z; std::distance<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>>(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>)
0x1400f1f1b  cmp     rax, 2
0x1400f1f1f  jl      loc_1400F203F
0x1400f1f25  mov     ecx, r14d
0x1400f1f28  shl     rcx, 5
0x1400f1f2c  cmp     rax, rcx
0x1400f1f2f  cmovb   rcx, rax
0x1400f1f33  xor     edi, edi
0x1400f1f35  mov     [rsp+98h+var_68], rdi
0x1400f1f3a  mov     [rsp+98h+var_60], rcx
0x1400f1f3f  mov     [rsp+98h+var_58], rax
0x1400f1f44  cqo
0x1400f1f46  idiv    rcx
0x1400f1f49  mov     [rsp+98h+var_50], rax
0x1400f1f4e  mov     [rsp+98h+var_48], rdx
0x1400f1f53  xorps   xmm0, xmm0
0x1400f1f56  movdqu  [rsp+98h+var_40], xmm0
0x1400f1f5c  mov     [rsp+98h+var_30], rdi
0x1400f1f61  mov     [rsp+98h+var_28], rsi
0x1400f1f66  mov     r9, rbx
0x1400f1f69  lea     r8, [rsp+98h+var_68]
0x1400f1f6e  lea     rdx, [rsp+98h+var_78]
0x1400f1f73  lea     rcx, [rsp+98h+var_40]
0x1400f1f78  call    ?_Populate@?$_Static_partition_range@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@_J$0A@@std@@QEAA?AV?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@2@AEBU?$_Static_partition_team@_J@2@V32@@Z; std::_Static_partition_range<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,__int64,0>::_Populate(std::_Static_partition_team<__int64> const &,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>)
0x1400f1f7d  xor     r8d, r8d
0x1400f1f80  lea     rdx, [rsp+98h+var_68]
0x1400f1f85  lea     rcx, ?_Threadpool_callback@?$_Static_partitioned_for_each2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@_JU?$_Ref_fn@V?$function@$$A6AXAEBU?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@Z@std@@@2@@std@@SAXPEAU__std_TP_CALLBACK_INSTANCE@@QEAXPEAU__std_TP_WORK@@@Z; std::_Static_partitioned_for_each2<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,__int64,std::_Ref_fn<std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>>>::_Threadpool_callback(__std_TP_CALLBACK_INSTANCE *,void * const,__std_TP_WORK *)
0x1400f1f8c  call    cs:__imp___std_create_threadpool_work
0x1400f1f93  nop     dword ptr [rax+rax+00h]
0x1400f1f98  mov     [rsp+98h+var_78], rax
0x1400f1f9d  test    rax, rax
0x1400f1fa0  jnz     short loc_1400F1FA8
0x1400f1fa2  call    ?_Throw_parallelism_resources_exhausted@std@@YAXXZ; std::_Throw_parallelism_resources_exhausted(void)
0x1400f1fa8  lea     rdx, ds:0[r14*4]
0x1400f1fb0  cmp     [rsp+98h+var_60], rdx
0x1400f1fb5  cmovb   rdx, [rsp+98h+var_60]
0x1400f1fbb  mov     rcx, rax
0x1400f1fbe  call    cs:__imp___std_bulk_submit_threadpool_work
0x1400f1fc5  nop     dword ptr [rax+rax+00h]
0x1400f1fca  lea     rcx, [rsp+98h+var_68]
0x1400f1fcf  call    ??$_Run_available_chunked_work@U?$_Static_partitioned_for_each2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@_JU?$_Ref_fn@V?$function@$$A6AXAEBU?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@Z@std@@@2@@std@@@std@@YAXAEAU?$_Static_partitioned_for_each2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@_JU?$_Ref_fn@V?$function@$$A6AXAEBU?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@Z@std@@@2@@0@@Z; std::_Run_available_chunked_work<std::_Static_partitioned_for_each2<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,__int64,std::_Ref_fn<std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>>>>(std::_Static_partitioned_for_each2<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,__int64,std::_Ref_fn<std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>>> &)
0x1400f1fd4  nop
0x1400f1fd5  lea     rcx, [rsp+98h+var_78]; this
0x1400f1fda  call    ??1_Work_ptr@std@@QEAA@XZ; std::_Work_ptr::~_Work_ptr(void)
0x1400f1fdf  nop
0x1400f1fe0  mov     rcx, qword ptr [rsp+98h+var_40]
0x1400f1fe5  test    rcx, rcx
0x1400f1fe8  jz      short loc_1400F2009
0x1400f1fea  mov     rdx, [rsp+98h+var_30]
0x1400f1fef  sub     rdx, rcx
0x1400f1ff2  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1400f1ff6  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1400f1ffb  xorps   xmm0, xmm0
0x1400f1ffe  movdqu  [rsp+98h+var_40], xmm0
0x1400f2004  mov     [rsp+98h+var_30], rdi
0x1400f2009  mov     rcx, [rsi+38h]
0x1400f200d  test    rcx, rcx
0x1400f2010  jz      short loc_1400F2028
0x1400f2012  mov     rax, [rcx]
0x1400f2015  cmp     rcx, rsi
0x1400f2018  setnz   dl
0x1400f201b  mov     rax, [rax+20h]
0x1400f201f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f2024  mov     [rsi+38h], rdi
0x1400f2028  jmp     short loc_1400F206F
0x1400f202a  mov     rdi, [rsp+98h+arg_10]
0x1400f2032  mov     rbx, [rsp+98h+arg_8]
0x1400f203a  mov     rsi, [rsp+98h+var_70]
0x1400f203f  mov     r8, rsi
0x1400f2042  mov     rdx, rdi
0x1400f2045  mov     rcx, rbx
0x1400f2048  call    ??$_For_each_ivdep@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@U?$_Ref_fn@V?$function@$$A6AXAEBU?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@Z@std@@@2@@std@@YAXV?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@0@V10@U?$_Ref_fn@V?$function@$$A6AXAEBU?$pair@$$CB_KV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UVirtualDeviceMigrationInfo@@@std@@@std@@@std@@@std@@@Z@std@@@0@@Z; std::_For_each_ivdep<std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,std::_Ref_fn<std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>>>(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>>>>,std::_Iterator_base0>,std::_Ref_fn<std::function<void (std::pair<unsigned __int64 const,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<VirtualDeviceMigrationInfo>>>> const &)>>)
0x1400f204d  nop
0x1400f204e  mov     rcx, [rsi+38h]
0x1400f2052  xor     edi, edi
0x1400f2054  test    rcx, rcx
0x1400f2057  jz      short loc_1400F206F
0x1400f2059  mov     rax, [rcx]
0x1400f205c  cmp     rcx, rsi
0x1400f205f  setnz   dl
0x1400f2062  mov     rax, [rax+20h]
0x1400f2066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400f206b  mov     [rsi+38h], rdi
0x1400f206f  mov     rcx, [rsp+98h+var_20]
0x1400f2074  xor     rcx, rsp; StackCookie
0x1400f2077  call    __security_check_cookie
0x1400f207c  mov     rbx, [rsp+98h+arg_0]
0x1400f2084  add     rsp, 80h
0x1400f208b  pop     r14
0x1400f208d  pop     rdi
0x1400f208e  pop     rsi
0x1400f208f  retn
```
