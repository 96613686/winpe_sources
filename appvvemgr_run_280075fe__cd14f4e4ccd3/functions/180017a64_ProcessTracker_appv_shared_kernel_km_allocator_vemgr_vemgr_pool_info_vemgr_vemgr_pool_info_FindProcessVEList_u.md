# ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindProcessVEList(ulong,appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>,vemgr::vemgr_pool_info> &)

- ea: `0x180017a64`
- end: `0x180017c76`
- name: `?FindProcessVEList@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJKAEAV?$doubly_linked_list@V?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@Z`
- size: `530`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001a594`

## callees

- `0x18000c5f4`
- `0x18000c768`
- `0x180017a64`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180017b9c`
- `ntoskrnl!ExAllocatePool2` at `0x180017b9c`
- `ntoskrnl!ExReleaseResourceLite` at `0x180017b2a`
- `ntoskrnl!ExReleaseResourceLite` at `0x180017c43`
- `ntoskrnl!ExReleaseResourceLite` at `0x180017b2a`
- `ntoskrnl!ExReleaseResourceLite` at `0x180017c43`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180017b36`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180017c4f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180017b36`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180017c4f`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180017aa5`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180017aa5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180017a92`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180017a92`

## pseudocode

```c
__int64 __fastcall ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindProcessVEList(
        __int64 a1,
        int a2,
        __int64 a3)
{
  bool v3; // si
  volatile signed __int32 *v6; // rbx
  struct _ERESOURCE *v7; // rcx
  __int64 v9; // r15
  __int64 v10; // r12
  __int64 i; // rax
  _QWORD *v12; // rbx
  unsigned int v13; // ebp
  _QWORD *v14; // r15
  _QWORD *Pool2; // rax
  _QWORD *v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rax
  volatile signed __int32 *v19; // rbx
  struct _ERESOURCE *v20; // rcx
  __int128 v21; // [rsp+20h] [rbp-48h] BYREF
  __int64 v22; // [rsp+70h] [rbp+8h] BYREF
  int v23; // [rsp+78h] [rbp+10h] BYREF
  __int64 v24; // [rsp+88h] [rbp+20h] BYREF

  v23 = a2;
  v3 = 0;
  if ( *(_QWORD *)(a1 + 16) )
  {
    KeEnterCriticalRegion();
    v3 = ExAcquireResourceSharedLite(*(PERESOURCE *)(a1 + 16), 1u) == 1;
  }
  v21 = 0;
  if ( (unsigned __int8)appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,unsigned long,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::find(
                          a1,
                          &v23,
                          &v21) )
  {
    v9 = v21;
    v10 = a3 + 8;
    for ( i = *(_QWORD *)(a3 + 32);
          i != v10;
          i = *appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(
                 (_DWORD *)a3,
                 &v24,
                 (__int64)&v22) )
    {
      v22 = i;
    }
    v12 = *(_QWORD **)(v9 + 32);
    v13 = 0;
    v14 = (_QWORD *)(v9 + 8);
    while ( v12 != v14 )
    {
      Pool2 = (_QWORD *)ExAllocatePool2(256, 32, 1733125462);
      v16 = Pool2;
      if ( !Pool2 )
      {
        v13 = -1073741670;
        break;
      }
      *Pool2 = *v12;
      v17 = v12[1];
      v16[1] = v17;
      if ( v17 )
        _InterlockedAdd((volatile signed __int32 *)(v17 + 8), 1u);
      v16[3] = v16;
      v16[2] = v16;
      ++*(_DWORD *)a3;
      v18 = *(_QWORD *)(a3 + 24);
      v13 = 0;
      v16[3] = v10;
      v16[2] = v18;
      *(_QWORD *)(v18 + 24) = v16;
      *(_QWORD *)(a3 + 24) = v16;
      v12 = (_QWORD *)v12[3];
    }
    v19 = (volatile signed __int32 *)*((_QWORD *)&v21 + 1);
    if ( *((_QWORD *)&v21 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v21 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 16LL))(v19);
      }
    }
    if ( v3 )
    {
      v20 = *(struct _ERESOURCE **)(a1 + 16);
      if ( v20 )
      {
        ExReleaseResourceLite(v20);
        KeLeaveCriticalRegion();
      }
    }
    return v13;
  }
  else
  {
    v6 = (volatile signed __int32 *)*((_QWORD *)&v21 + 1);
    if ( *((_QWORD *)&v21 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v21 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
        if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 16LL))(v6);
      }
    }
    if ( v3 )
    {
      v7 = *(struct _ERESOURCE **)(a1 + 16);
      if ( v7 )
      {
        ExReleaseResourceLite(v7);
        KeLeaveCriticalRegion();
      }
    }
    return 3221225524LL;
  }
}

```

## disassembly

```asm
0x180017a64  mov     [rsp+arg_10], rbx
0x180017a69  mov     [rsp+arg_8], edx
0x180017a6d  push    rbp
0x180017a6e  push    rsi
0x180017a6f  push    rdi
0x180017a70  push    r12
0x180017a72  push    r13
0x180017a74  push    r14
0x180017a76  push    r15
0x180017a78  sub     rsp, 30h
0x180017a7c  xor     sil, sil
0x180017a7f  mov     rdi, r8
0x180017a82  cmp     qword ptr [rcx+10h], 0
0x180017a87  mov     r14, rcx
0x180017a8a  mov     r13d, 1
0x180017a90  jz      short loc_180017ABC
0x180017a92  call    cs:__imp_KeEnterCriticalRegion
0x180017a99  nop     dword ptr [rax+rax+00h]
0x180017a9e  mov     rcx, [r14+10h]; Resource
0x180017aa2  mov     dl, r13b; Wait
0x180017aa5  call    cs:__imp_ExAcquireResourceSharedLite
0x180017aac  nop     dword ptr [rax+rax+00h]
0x180017ab1  cmp     al, r13b
0x180017ab4  movzx   esi, sil
0x180017ab8  cmovz   esi, r13d
0x180017abc  xorps   xmm0, xmm0
0x180017abf  lea     r8, [rsp+68h+var_48]
0x180017ac4  lea     rdx, [rsp+68h+arg_8]
0x180017ac9  mov     rcx, r14
0x180017acc  movdqu  [rsp+68h+var_48], xmm0
0x180017ad2  call    ?find@?$indexed_avl_tree@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uless_predicate@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@KV?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@QEAA_NAEBKAEAV?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,ulong,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::find(ulong const &,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue> &)
0x180017ad7  test    al, al
0x180017ad9  jnz     short loc_180017B4C
0x180017adb  mov     rbx, qword ptr [rsp+68h+var_48+8]
0x180017ae0  test    rbx, rbx
0x180017ae3  jz      short loc_180017B1C
0x180017ae5  or      edi, 0FFFFFFFFh
0x180017ae8  mov     eax, edi
0x180017aea  lock xadd [rbx+8], eax
0x180017aef  add     eax, edi
0x180017af1  jnz     short loc_180017B1C
0x180017af3  mov     rax, [rbx]
0x180017af6  mov     rcx, rbx
0x180017af9  mov     rax, [rax+8]
0x180017afd  call    _guard_dispatch_icall
0x180017b02  mov     eax, edi
0x180017b04  lock xadd [rbx+0Ch], eax
0x180017b09  add     eax, edi
0x180017b0b  jnz     short loc_180017B1C
0x180017b0d  mov     rax, [rbx]
0x180017b10  mov     rcx, rbx
0x180017b13  mov     rax, [rax+10h]
0x180017b17  call    _guard_dispatch_icall
0x180017b1c  test    sil, sil
0x180017b1f  jz      short loc_180017B42
0x180017b21  mov     rcx, [r14+10h]; Resource
0x180017b25  test    rcx, rcx
0x180017b28  jz      short loc_180017B42
0x180017b2a  call    cs:__imp_ExReleaseResourceLite
0x180017b31  nop     dword ptr [rax+rax+00h]
0x180017b36  call    cs:__imp_KeLeaveCriticalRegion
0x180017b3d  nop     dword ptr [rax+rax+00h]
0x180017b42  mov     eax, 0C0000034h
0x180017b47  jmp     loc_180017C5D
0x180017b4c  mov     r15, qword ptr [rsp+68h+var_48]
0x180017b51  lea     r12, [rdi+8]
0x180017b55  mov     rax, [rdi+20h]
0x180017b59  cmp     rax, r12
0x180017b5c  jz      short loc_180017B7D
0x180017b5e  lea     r8, [rsp+68h+arg_0]
0x180017b63  mov     [rsp+68h+arg_0], rax
0x180017b68  lea     rdx, [rsp+68h+arg_18]
0x180017b70  mov     rcx, rdi
0x180017b73  call    ?erase@?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@234@V5234@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(appv::shared::kernel::bidirectional_list_iterator<appv::shared::kernel::dl_node_t<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>>>)
0x180017b78  mov     rax, [rax]
0x180017b7b  jmp     short loc_180017B59
0x180017b7d  mov     rbx, [r15+20h]
0x180017b81  xor     ebp, ebp
0x180017b83  add     r15, 8
0x180017b87  cmp     rbx, r15
0x180017b8a  jz      short loc_180017BF4
0x180017b8c  mov     edx, 20h ; ' '
0x180017b91  mov     ecx, 100h
0x180017b96  mov     r8d, 674D6556h
0x180017b9c  call    cs:__imp_ExAllocatePool2
0x180017ba3  nop     dword ptr [rax+rax+00h]
0x180017ba8  mov     rdx, rax
0x180017bab  test    rax, rax
0x180017bae  jz      short loc_180017BEF
0x180017bb0  mov     rcx, [rbx]
0x180017bb3  mov     [rax], rcx
0x180017bb6  mov     rax, [rbx+8]
0x180017bba  mov     [rdx+8], rax
0x180017bbe  test    rax, rax
0x180017bc1  jz      short loc_180017BC8
0x180017bc3  lock add [rax+8], r13d
0x180017bc8  mov     [rdx+18h], rdx
0x180017bcc  mov     [rdx+10h], rdx
0x180017bd0  add     [rdi], r13d
0x180017bd3  mov     rax, [rdi+18h]
0x180017bd7  xor     ebp, ebp
0x180017bd9  mov     [rdx+18h], r12
0x180017bdd  mov     [rdx+10h], rax
0x180017be1  mov     [rax+18h], rdx
0x180017be5  mov     [rdi+18h], rdx
0x180017be9  mov     rbx, [rbx+18h]
0x180017bed  jmp     short loc_180017B87
0x180017bef  mov     ebp, 0C000009Ah
0x180017bf4  mov     rbx, qword ptr [rsp+68h+var_48+8]
0x180017bf9  test    rbx, rbx
0x180017bfc  jz      short loc_180017C35
0x180017bfe  or      edi, 0FFFFFFFFh
0x180017c01  mov     eax, edi
0x180017c03  lock xadd [rbx+8], eax
0x180017c08  add     eax, edi
0x180017c0a  jnz     short loc_180017C35
0x180017c0c  mov     rax, [rbx]
0x180017c0f  mov     rcx, rbx
0x180017c12  mov     rax, [rax+8]
0x180017c16  call    _guard_dispatch_icall
0x180017c1b  mov     eax, edi
0x180017c1d  lock xadd [rbx+0Ch], eax
0x180017c22  add     eax, edi
0x180017c24  jnz     short loc_180017C35
0x180017c26  mov     rax, [rbx]
0x180017c29  mov     rcx, rbx
0x180017c2c  mov     rax, [rax+10h]
0x180017c30  call    _guard_dispatch_icall
0x180017c35  test    sil, sil
0x180017c38  jz      short loc_180017C5B
0x180017c3a  mov     rcx, [r14+10h]; Resource
0x180017c3e  test    rcx, rcx
0x180017c41  jz      short loc_180017C5B
0x180017c43  call    cs:__imp_ExReleaseResourceLite
0x180017c4a  nop     dword ptr [rax+rax+00h]
0x180017c4f  call    cs:__imp_KeLeaveCriticalRegion
0x180017c56  nop     dword ptr [rax+rax+00h]
0x180017c5b  mov     eax, ebp
0x180017c5d  mov     rbx, [rsp+68h+arg_10]
0x180017c65  add     rsp, 30h
0x180017c69  pop     r15
0x180017c6b  pop     r14
0x180017c6d  pop     r13
0x180017c6f  pop     r12
0x180017c71  pop     rdi
0x180017c72  pop     rsi
0x180017c73  pop     rbp
0x180017c74  retn
```
