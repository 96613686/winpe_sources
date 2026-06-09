# VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info> &,ConfigurationManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info> &,synchrozined_vemgr_notifications<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info> &,long &)

- ea: `0x1800168b0`
- end: `0x180016d01`
- name: `??0?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA@AEAV?$VfsVolumeManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAV?$ConfigurationManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAV?$synchrozined_vemgr_notifications@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAJ@Z`
- size: `1105`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180017334`

## callees

- `0x18000a9e4`
- `0x180016684`
- `0x1800168b0`
- `0x180016d08`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180016902`
- `ntoskrnl!ExAllocatePool2` at `0x180016966`
- `ntoskrnl!ExAllocatePool2` at `0x1800169a3`
- `ntoskrnl!ExAllocatePool2` at `0x1800169c9`
- `ntoskrnl!ExAllocatePool2` at `0x180016a42`
- `ntoskrnl!ExAllocatePool2` at `0x180016a66`
- `ntoskrnl!ExAllocatePool2` at `0x180016ab4`
- `ntoskrnl!ExAllocatePool2` at `0x180016af4`
- `ntoskrnl!ExAllocatePool2` at `0x180016bca`
- `ntoskrnl!ExAllocatePool2` at `0x180016c21`
- `ntoskrnl!ExAllocatePool2` at `0x180016902`
- `ntoskrnl!ExAllocatePool2` at `0x180016966`
- `ntoskrnl!ExAllocatePool2` at `0x1800169a3`
- `ntoskrnl!ExAllocatePool2` at `0x1800169c9`
- `ntoskrnl!ExAllocatePool2` at `0x180016a42`
- `ntoskrnl!ExAllocatePool2` at `0x180016a66`
- `ntoskrnl!ExAllocatePool2` at `0x180016ab4`
- `ntoskrnl!ExAllocatePool2` at `0x180016af4`
- `ntoskrnl!ExAllocatePool2` at `0x180016bca`
- `ntoskrnl!ExAllocatePool2` at `0x180016c21`
- `ntoskrnl!ExFreePoolWithTag` at `0x180016b3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x180016c64`
- `ntoskrnl!ExFreePoolWithTag` at `0x180016c75`
- `ntoskrnl!ExFreePoolWithTag` at `0x180016b3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x180016c64`
- `ntoskrnl!ExFreePoolWithTag` at `0x180016c75`
- `ntoskrnl!ExInitializeResourceLite` at `0x180016ad3`
- `ntoskrnl!ExInitializeResourceLite` at `0x180016ad3`
- `ntoskrnl!KeInitializeMutex` at `0x180016923`
- `ntoskrnl!KeInitializeMutex` at `0x180016984`
- `ntoskrnl!KeInitializeMutex` at `0x180016923`
- `ntoskrnl!KeInitializeMutex` at `0x180016984`
- `ntoskrnl!RtlInitUnicodeString` at `0x180016beb`
- `ntoskrnl!RtlInitUnicodeString` at `0x180016beb`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1800169fa`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x180016a97`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x1800169fa`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x180016a97`

## pseudocode

```c
__int64 __fastcall VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int *a5)
{
  struct _KMUTANT *Pool2; // rax
  int v7; // ecx
  struct _KMUTANT *v8; // rax
  struct _RTL_AVL_TABLE **v9; // rax
  struct _RTL_AVL_TABLE **v10; // rdi
  struct _RTL_AVL_TABLE *v11; // rax
  __int64 v12; // rax
  _QWORD *v13; // rax
  _DWORD *v14; // rdi
  struct _RTL_AVL_TABLE *v15; // rax
  struct _ERESOURCE *v16; // rax
  NTSTATUS v17; // eax
  __int64 v18; // rax
  volatile signed __int32 *v19; // rdi
  __int64 v20; // rax
  __int64 v21; // rax
  _QWORD *v22; // rdi
  __int64 v23; // rax
  void *v24; // rcx
  volatile signed __int32 *v25; // rdi
  __int64 v26; // rax

  *(_QWORD *)(a1 + 48) = a2;
  *(_QWORD *)(a1 + 56) = a3;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 64) = a4;
  *(_QWORD *)(a1 + 72) = 0;
  Pool2 = (struct _KMUTANT *)ExAllocatePool2(64, 56, 1733125462);
  *(_QWORD *)(a1 + 72) = Pool2;
  if ( Pool2 )
  {
    KeInitializeMutex(Pool2, 0);
    v7 = 0;
  }
  else
  {
    v7 = -1073741670;
  }
  *(_DWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *a5 = v7;
  *(_QWORD *)(a1 + 112) = a1 + 88;
  *(_QWORD *)(a1 + 104) = a1 + 88;
  *(_QWORD *)(a1 + 120) = 0;
  if ( v7 < 0 )
    return a1;
  v8 = (struct _KMUTANT *)ExAllocatePool2(64, 56, 1733125462);
  *(_QWORD *)(a1 + 120) = v8;
  if ( !v8 )
    goto LABEL_55;
  KeInitializeMutex(v8, 0);
  *a5 = 0;
  v9 = (struct _RTL_AVL_TABLE **)ExAllocatePool2(256, 8, 1733125462);
  v10 = v9;
  if ( v9 )
  {
    *v9 = 0;
    v11 = (struct _RTL_AVL_TABLE *)ExAllocatePool2(256, 104, 1733125462);
    *v10 = v11;
    if ( v11 )
      RtlInitializeGenericTableAvl(
        v11,
        appv::shared::kernel::avl_tree<appv::shared::kernel::pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVolume<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::iless_predicate,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<VfsVolumeManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVolume<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>>::less_predicate_wrapper>::avl_tree_order,
        appv::shared::kernel::avl_tree<appv::shared::kernel::pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::iless_predicate,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>::less_predicate_wrapper>::avl_tree_allocate,
        appv::shared::kernel::avl_tree<appv::shared::kernel::pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::iless_predicate,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>::less_predicate_wrapper>::avl_tree_free,
        0);
  }
  else
  {
    v10 = 0;
  }
  kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::reset<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(
    (__int64 *)a1,
    v10);
  if ( !*(_QWORD *)a1 )
    goto LABEL_55;
  v12 = *(_QWORD *)(a1 + 8);
  if ( !v12 || !*(_DWORD *)(v12 + 8) )
    goto LABEL_55;
  v13 = (_QWORD *)ExAllocatePool2(256, 24, 1733125462);
  v14 = v13;
  if ( v13 )
  {
    *v13 = 0;
    v15 = (struct _RTL_AVL_TABLE *)ExAllocatePool2(256, 104, 1733125462);
    *(_QWORD *)v14 = v15;
    if ( v15 )
      RtlInitializeGenericTableAvl(
        v15,
        appv::shared::kernel::avl_tree<appv::shared::kernel::pair<unsigned long,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,unsigned long,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>>::less_predicate_wrapper>::avl_tree_order,
        appv::shared::kernel::avl_tree<appv::shared::kernel::pair<unsigned long,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,unsigned long,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::less_predicate_wrapper>::avl_tree_allocate,
        appv::shared::kernel::avl_tree<appv::shared::kernel::pair<unsigned long,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>,appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,unsigned long,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::less_predicate_wrapper>::avl_tree_free,
        0);
    v14[2] = 1733125462;
    *((_QWORD *)v14 + 2) = 0;
    v16 = (struct _ERESOURCE *)ExAllocatePool2(64, 104, 1733125462);
    *((_QWORD *)v14 + 2) = v16;
    if ( v16 )
      v17 = ExInitializeResourceLite(v16);
    else
      v17 = -1073741670;
    *a5 = v17;
  }
  else
  {
    v14 = 0;
  }
  v18 = ExAllocatePool2(256, 24, 1715758931);
  if ( !v18 )
  {
    if ( v14 )
    {
      ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::~ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(v14);
      ExFreePoolWithTag(v14, 0);
    }
    v18 = 0;
    goto LABEL_27;
  }
  *(_DWORD *)(v18 + 8) = 1;
  *(_QWORD *)v18 = &kernel_std::detail::sp_counted_impl_p<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::`vftable';
  *(_DWORD *)(v18 + 12) = 1;
  *(_QWORD *)(v18 + 16) = v14;
  if ( !*(_DWORD *)(v18 + 8) )
LABEL_27:
    v14 = 0;
  *(_QWORD *)(a1 + 16) = v14;
  v19 = *(volatile signed __int32 **)(a1 + 24);
  *(_QWORD *)(a1 + 24) = v18;
  if ( v19 )
  {
    if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 16LL))(v19);
    }
  }
  if ( !*(_QWORD *)(a1 + 16) || (v20 = *(_QWORD *)(a1 + 24)) == 0 || !*(_DWORD *)(v20 + 8) )
    *a5 = -1073741670;
  if ( *a5 < 0 )
    return a1;
  v21 = ExAllocatePool2(256, 32, 1733125462);
  v22 = (_QWORD *)v21;
  if ( v21 )
  {
    *(_QWORD *)v21 = 0;
    *(_QWORD *)(v21 + 8) = 0;
    RtlInitUnicodeString((PUNICODE_STRING)(v21 + 16), 0);
    *a5 = appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
            v22,
            L"\\Device\\AppvVfs",
            15);
  }
  else
  {
    v22 = 0;
  }
  v23 = ExAllocatePool2(256, 24, 1715758931);
  if ( !v23 )
  {
    v23 = 0;
    if ( v22 )
    {
      v24 = (void *)v22[1];
      if ( v24 )
        ExFreePoolWithTag(v24, 0);
      ExFreePoolWithTag(v22, 0);
      v23 = 0;
    }
    goto LABEL_47;
  }
  *(_DWORD *)(v23 + 8) = 1;
  *(_QWORD *)v23 = &kernel_std::detail::sp_counted_impl_p<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::`vftable';
  *(_DWORD *)(v23 + 12) = 1;
  *(_QWORD *)(v23 + 16) = v22;
  if ( !*(_DWORD *)(v23 + 8) )
LABEL_47:
    v22 = 0;
  *(_QWORD *)(a1 + 32) = v22;
  v25 = *(volatile signed __int32 **)(a1 + 40);
  *(_QWORD *)(a1 + 40) = v23;
  if ( v25 )
  {
    if ( _InterlockedExchangeAdd(v25 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
      if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 16LL))(v25);
    }
  }
  if ( !*(_QWORD *)(a1 + 32) || (v26 = *(_QWORD *)(a1 + 40)) == 0 || !*(_DWORD *)(v26 + 8) )
LABEL_55:
    *a5 = -1073741670;
  return a1;
}

```

## disassembly

```asm
0x1800168b0  push    rbx
0x1800168b2  push    rbp
0x1800168b3  push    rsi
0x1800168b4  push    rdi
0x1800168b5  push    r12
0x1800168b7  push    r13
0x1800168b9  push    r14
0x1800168bb  push    r15
0x1800168bd  sub     rsp, 38h
0x1800168c1  xor     ebp, ebp
0x1800168c3  mov     [rcx+30h], rdx
0x1800168c7  mov     [rcx+38h], r8
0x1800168cb  mov     rbx, rcx
0x1800168ce  mov     [rcx], rbp
0x1800168d1  mov     r15d, 674D6556h
0x1800168d7  mov     [rcx+8], rbp
0x1800168db  mov     r8d, r15d
0x1800168de  mov     [rcx+10h], rbp
0x1800168e2  lea     edi, [rbp+38h]
0x1800168e5  mov     [rcx+18h], rbp
0x1800168e9  lea     r12d, [rbp+40h]
0x1800168ed  mov     [rcx+20h], rbp
0x1800168f1  mov     edx, edi
0x1800168f3  mov     [rcx+28h], rbp
0x1800168f7  mov     [rcx+40h], r9
0x1800168fb  mov     [rcx+48h], rbp
0x1800168ff  mov     ecx, r12d
0x180016902  call    cs:__imp_ExAllocatePool2
0x180016909  nop     dword ptr [rax+rax+00h]
0x18001690e  mov     [rbx+48h], rax
0x180016912  test    rax, rax
0x180016915  jnz     short loc_18001691E
0x180016917  mov     ecx, 0C000009Ah
0x18001691c  jmp     short loc_180016931
0x18001691e  xor     edx, edx; Level
0x180016920  mov     rcx, rax; Mutex
0x180016923  call    cs:__imp_KeInitializeMutex
0x18001692a  nop     dword ptr [rax+rax+00h]
0x18001692f  mov     ecx, ebp
0x180016931  mov     rsi, [rsp+78h+arg_20]
0x180016939  lea     rax, [rbx+58h]
0x18001693d  mov     [rbx+50h], ebp
0x180016940  mov     [rax], rbp
0x180016943  mov     [rax+8], rbp
0x180016947  mov     [rsi], ecx
0x180016949  mov     [rax+18h], rax
0x18001694d  mov     [rax+10h], rax
0x180016951  mov     [rbx+78h], rbp
0x180016955  test    ecx, ecx
0x180016957  js      loc_180016CEC
0x18001695d  mov     r8d, r15d
0x180016960  mov     rdx, rdi
0x180016963  mov     rcx, r12
0x180016966  call    cs:__imp_ExAllocatePool2
0x18001696d  nop     dword ptr [rax+rax+00h]
0x180016972  mov     [rbx+78h], rax
0x180016976  test    rax, rax
0x180016979  jz      loc_180016CE6
0x18001697f  xor     edx, edx; Level
0x180016981  mov     rcx, rax; Mutex
0x180016984  call    cs:__imp_KeInitializeMutex
0x18001698b  nop     dword ptr [rax+rax+00h]
0x180016990  mov     r13d, 100h
0x180016996  mov     [rsi], ebp
0x180016998  mov     ecx, r13d
0x18001699b  mov     r8d, r15d
0x18001699e  mov     edx, 8
0x1800169a3  call    cs:__imp_ExAllocatePool2
0x1800169aa  nop     dword ptr [rax+rax+00h]
0x1800169af  mov     rdi, rax
0x1800169b2  mov     r14d, 68h ; 'h'
0x1800169b8  test    rax, rax
0x1800169bb  jz      short loc_180016A08
0x1800169bd  mov     r8d, r15d
0x1800169c0  mov     [rax], rbp
0x1800169c3  mov     edx, r14d
0x1800169c6  mov     ecx, r13d
0x1800169c9  call    cs:__imp_ExAllocatePool2
0x1800169d0  nop     dword ptr [rax+rax+00h]
0x1800169d5  mov     [rdi], rax
0x1800169d8  test    rax, rax
0x1800169db  jz      short loc_180016A0B
0x1800169dd  lea     r9, ?avl_tree_free@?$avl_tree@V?$pair@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@V?$shared_ptr@V?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@2@@kernel@shared@appv@@U?$km_allocator@Uvemgr_pool_info@vemgr@@@234@Uless_predicate_wrapper@?$indexed_avl_tree@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uiless_predicate@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@234@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@V?$shared_ptr@V?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@8@@234@@kernel@shared@appv@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x1800169e4  mov     [rsp+78h+TableContext], rbp; TableContext
0x1800169e9  lea     r8, ?avl_tree_allocate@?$avl_tree@V?$pair@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@V?$shared_ptr@V?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@2@@kernel@shared@appv@@U?$km_allocator@Uvemgr_pool_info@vemgr@@@234@Uless_predicate_wrapper@?$indexed_avl_tree@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uiless_predicate@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@234@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@V?$shared_ptr@V?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@8@@234@@kernel@shared@appv@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x1800169f0  mov     rcx, rax; Table
0x1800169f3  lea     rdx, ?avl_tree_order@?$avl_tree@V?$pair@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@V?$shared_ptr@V?$CountedVolume@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$VfsVolumeManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@2@@kernel@shared@appv@@U?$km_allocator@Uvemgr_pool_info@vemgr@@@234@Uless_predicate_wrapper@?$indexed_avl_tree@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uiless_predicate@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@234@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@V?$shared_ptr@V?$CountedVolume@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@?$VfsVolumeManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@8@@234@@kernel@shared@appv@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x1800169fa  call    cs:__imp_RtlInitializeGenericTableAvl
0x180016a01  nop     dword ptr [rax+rax+00h]
0x180016a06  jmp     short loc_180016A0B
0x180016a08  mov     rdi, rbp
0x180016a0b  mov     rdx, rdi
0x180016a0e  mov     rcx, rbx
0x180016a11  call    ??$reset@V?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$shared_ptr@V?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@QEAAXPEAV?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z; kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::reset<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info> *)
0x180016a16  cmp     [rbx], rbp
0x180016a19  jz      loc_180016CE6
0x180016a1f  mov     rax, [rbx+8]
0x180016a23  test    rax, rax
0x180016a26  jz      loc_180016CE6
0x180016a2c  mov     eax, [rax+8]
0x180016a2f  test    eax, eax
0x180016a31  jz      loc_180016CE6
0x180016a37  mov     r8d, r15d
0x180016a3a  mov     edx, 18h
0x180016a3f  mov     rcx, r13
0x180016a42  call    cs:__imp_ExAllocatePool2
0x180016a49  nop     dword ptr [rax+rax+00h]
0x180016a4e  mov     rdi, rax
0x180016a51  test    rax, rax
0x180016a54  jz      loc_180016AE3
0x180016a5a  mov     r8d, r15d
0x180016a5d  mov     [rax], rbp
0x180016a60  mov     rdx, r14
0x180016a63  mov     rcx, r13
0x180016a66  call    cs:__imp_ExAllocatePool2
0x180016a6d  nop     dword ptr [rax+rax+00h]
0x180016a72  mov     [rdi], rax
0x180016a75  test    rax, rax
0x180016a78  jz      short loc_180016AA3
0x180016a7a  lea     r9, ?avl_tree_free@?$avl_tree@V?$pair@KV?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@U?$km_allocator@Uvemgr_pool_info@vemgr@@@234@Uless_predicate_wrapper@?$indexed_avl_tree@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uless_predicate@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@KV?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@234@@kernel@shared@appv@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x180016a81  mov     [rsp+78h+TableContext], rbp; TableContext
0x180016a86  lea     r8, ?avl_tree_allocate@?$avl_tree@V?$pair@KV?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@U?$km_allocator@Uvemgr_pool_info@vemgr@@@234@Uless_predicate_wrapper@?$indexed_avl_tree@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uless_predicate@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@KV?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@234@@kernel@shared@appv@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180016a8d  mov     rcx, rax; Table
0x180016a90  lea     rdx, ?avl_tree_order@?$avl_tree@V?$pair@KV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@U?$km_allocator@Uvemgr_pool_info@vemgr@@@234@Uless_predicate_wrapper@?$indexed_avl_tree@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uless_predicate@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@KV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@234@@kernel@shared@appv@@CA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180016a97  call    cs:__imp_RtlInitializeGenericTableAvl
0x180016a9e  nop     dword ptr [rax+rax+00h]
0x180016aa3  mov     r8d, r15d
0x180016aa6  mov     [rdi+8], r15d
0x180016aaa  mov     rdx, r14
0x180016aad  mov     [rdi+10h], rbp
0x180016ab1  mov     rcx, r12
0x180016ab4  call    cs:__imp_ExAllocatePool2
0x180016abb  nop     dword ptr [rax+rax+00h]
0x180016ac0  mov     [rdi+10h], rax
0x180016ac4  test    rax, rax
0x180016ac7  jnz     short loc_180016AD0
0x180016ac9  mov     eax, 0C000009Ah
0x180016ace  jmp     short loc_180016ADF
0x180016ad0  mov     rcx, rax; Resource
0x180016ad3  call    cs:__imp_ExInitializeResourceLite
0x180016ada  nop     dword ptr [rax+rax+00h]
0x180016adf  mov     [rsi], eax
0x180016ae1  jmp     short loc_180016AE6
0x180016ae3  mov     rdi, rbp
0x180016ae6  mov     edx, 18h
0x180016aeb  mov     r8d, 66446753h
0x180016af1  mov     rcx, r13
0x180016af4  call    cs:__imp_ExAllocatePool2
0x180016afb  nop     dword ptr [rax+rax+00h]
0x180016b00  mov     r12d, 1
0x180016b06  test    rax, rax
0x180016b09  jz      short loc_180016B2A
0x180016b0b  lea     rcx, ??_7?$sp_counted_impl_p@V?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@detail@kernel_std@@6B@; const kernel_std::detail::sp_counted_impl_p<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::`vftable'
0x180016b12  mov     [rax+8], r12d
0x180016b16  mov     [rax], rcx
0x180016b19  mov     [rax+0Ch], r12d
0x180016b1d  mov     [rax+10h], rdi
0x180016b21  mov     ecx, [rax+8]
0x180016b24  test    ecx, ecx
0x180016b26  jnz     short loc_180016B4E
0x180016b28  jmp     short loc_180016B4B
0x180016b2a  test    rdi, rdi
0x180016b2d  jz      short loc_180016B48
0x180016b2f  mov     rcx, rdi
0x180016b32  call    ??1?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA@XZ; ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::~ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(void)
0x180016b37  xor     edx, edx; Tag
0x180016b39  mov     rcx, rdi; P
0x180016b3c  call    cs:__imp_ExFreePoolWithTag
0x180016b43  nop     dword ptr [rax+rax+00h]
0x180016b48  mov     rax, rbp
0x180016b4b  mov     rdi, rbp
0x180016b4e  mov     [rbx+10h], rdi
0x180016b52  or      r14d, 0FFFFFFFFh
0x180016b56  mov     rdi, [rbx+18h]
0x180016b5a  mov     [rbx+18h], rax
0x180016b5e  test    rdi, rdi
0x180016b61  jz      short loc_180016B9B
0x180016b63  mov     eax, r14d
0x180016b66  lock xadd [rdi+8], eax
0x180016b6b  add     eax, r14d
0x180016b6e  jnz     short loc_180016B9B
0x180016b70  mov     rax, [rdi]
0x180016b73  mov     rcx, rdi
0x180016b76  mov     rax, [rax+8]
0x180016b7a  call    _guard_dispatch_icall
0x180016b7f  mov     eax, r14d
0x180016b82  lock xadd [rdi+0Ch], eax
0x180016b87  add     eax, r14d
0x180016b8a  jnz     short loc_180016B9B
0x180016b8c  mov     rax, [rdi]
0x180016b8f  mov     rcx, rdi
0x180016b92  mov     rax, [rax+10h]
0x180016b96  call    _guard_dispatch_icall
0x180016b9b  cmp     [rbx+10h], rbp
0x180016b9f  jz      short loc_180016BB1
0x180016ba1  mov     rax, [rbx+18h]
0x180016ba5  test    rax, rax
0x180016ba8  jz      short loc_180016BB1
0x180016baa  mov     eax, [rax+8]
0x180016bad  test    eax, eax
0x180016baf  jnz     short loc_180016BB7
0x180016bb1  mov     dword ptr [rsi], 0C000009Ah
0x180016bb7  cmp     [rsi], ebp
0x180016bb9  jl      loc_180016CEC
0x180016bbf  mov     r8d, r15d
0x180016bc2  mov     edx, 20h ; ' '
0x180016bc7  mov     rcx, r13
0x180016bca  call    cs:__imp_ExAllocatePool2
0x180016bd1  nop     dword ptr [rax+rax+00h]
0x180016bd6  mov     rdi, rax
0x180016bd9  test    rax, rax
0x180016bdc  jz      short loc_180016C10
0x180016bde  lea     rcx, [rax+10h]; DestinationString
0x180016be2  mov     [rax], rbp
0x180016be5  xor     edx, edx; SourceString
0x180016be7  mov     [rax+8], rbp
0x180016beb  call    cs:__imp_RtlInitUnicodeString
0x180016bf2  nop     dword ptr [rax+rax+00h]
0x180016bf7  mov     r8d, 0Fh
0x180016bfd  lea     rdx, aDeviceAppvvfs; "\\Device\\AppvVfs"
0x180016c04  mov     rcx, rdi
0x180016c07  call    ?assign@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAAJPEB_W_K@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(wchar_t const *,unsigned __int64)
0x180016c0c  mov     [rsi], eax
0x180016c0e  jmp     short loc_180016C13
0x180016c10  mov     rdi, rbp
0x180016c13  mov     edx, 18h
0x180016c18  mov     r8d, 66446753h
0x180016c1e  mov     rcx, r13
0x180016c21  call    cs:__imp_ExAllocatePool2
0x180016c28  nop     dword ptr [rax+rax+00h]
0x180016c2d  test    rax, rax
0x180016c30  jz      short loc_180016C51
0x180016c32  lea     rcx, ??_7?$sp_counted_impl_p@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@detail@kernel_std@@6B@; const kernel_std::detail::sp_counted_impl_p<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::`vftable'
0x180016c39  mov     [rax+8], r12d
0x180016c3d  mov     [rax], rcx
0x180016c40  mov     [rax+0Ch], r12d
0x180016c44  mov     [rax+10h], rdi
0x180016c48  mov     ecx, [rax+8]
0x180016c4b  test    ecx, ecx
0x180016c4d  jnz     short loc_180016C87
0x180016c4f  jmp     short loc_180016C84
0x180016c51  mov     rax, rbp
0x180016c54  test    rdi, rdi
0x180016c57  jz      short loc_180016C84
0x180016c59  mov     rcx, [rdi+8]; P
0x180016c5d  test    rcx, rcx
0x180016c60  jz      short loc_180016C70
0x180016c62  xor     edx, edx; Tag
0x180016c64  call    cs:__imp_ExFreePoolWithTag
0x180016c6b  nop     dword ptr [rax+rax+00h]
0x180016c70  xor     edx, edx; Tag
0x180016c72  mov     rcx, rdi; P
0x180016c75  call    cs:__imp_ExFreePoolWithTag
0x180016c7c  nop     dword ptr [rax+rax+00h]
0x180016c81  mov     rax, rbp
0x180016c84  mov     rdi, rbp
0x180016c87  mov     [rbx+20h], rdi
0x180016c8b  mov     rdi, [rbx+28h]
0x180016c8f  mov     [rbx+28h], rax
0x180016c93  test    rdi, rdi
0x180016c96  jz      short loc_180016CD0
0x180016c98  mov     eax, r14d
0x180016c9b  lock xadd [rdi+8], eax
0x180016ca0  add     eax, r14d
0x180016ca3  jnz     short loc_180016CD0
0x180016ca5  mov     rax, [rdi]
0x180016ca8  mov     rcx, rdi
0x180016cab  mov     rax, [rax+8]
0x180016caf  call    _guard_dispatch_icall
0x180016cb4  mov     eax, r14d
0x180016cb7  lock xadd [rdi+0Ch], eax
0x180016cbc  add     eax, r14d
0x180016cbf  jnz     short loc_180016CD0
0x180016cc1  mov     rax, [rdi]
0x180016cc4  mov     rcx, rdi
0x180016cc7  mov     rax, [rax+10h]
0x180016ccb  call    _guard_dispatch_icall
0x180016cd0  cmp     [rbx+20h], rbp
0x180016cd4  jz      short loc_180016CE6
0x180016cd6  mov     rax, [rbx+28h]
0x180016cda  test    rax, rax
0x180016cdd  jz      short loc_180016CE6
0x180016cdf  mov     eax, [rax+8]
0x180016ce2  test    eax, eax
0x180016ce4  jnz     short loc_180016CEC
0x180016ce6  mov     dword ptr [rsi], 0C000009Ah
0x180016cec  mov     rax, rbx
0x180016cef  add     rsp, 38h
0x180016cf3  pop     r15
0x180016cf5  pop     r14
0x180016cf7  pop     r13
0x180016cf9  pop     r12
0x180016cfb  pop     rdi
0x180016cfc  pop     rsi
0x180016cfd  pop     rbp
0x180016cfe  pop     rbx
0x180016cff  retn
```
