# kernel_std::detail::sp_counted_impl_p<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::dispose(void)

- ea: `0x18000bd30`
- end: `0x18000bdaa`
- name: `?dispose@?$sp_counted_impl_p@V?$Generic_PackageGroupConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@detail@kernel_std@@UEAAXXZ`
- size: `122`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180005178`
- `0x18000bd30`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18000bd92`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000bd92`

## pseudocode

```c
void __fastcall kernel_std::detail::sp_counted_impl_p<Generic_PackageGroupConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::dispose(
        __int64 a1)
{
  _QWORD *v1; // rdi
  volatile signed __int32 *v2; // rbx

  v1 = *(_QWORD **)(a1 + 16);
  if ( v1 )
  {
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)(v1 + 2));
    v2 = (volatile signed __int32 *)v1[1];
    if ( v2 && _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
      if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 16LL))(v2);
    }
    ExFreePoolWithTag(v1, 0);
  }
}

```

## disassembly

```asm
0x18000bd30  mov     [rsp+arg_0], rbx
0x18000bd35  push    rdi
0x18000bd36  sub     rsp, 20h
0x18000bd3a  mov     rdi, [rcx+10h]
0x18000bd3e  test    rdi, rdi
0x18000bd41  jz      short loc_18000BD9E
0x18000bd43  lea     rcx, [rdi+10h]
0x18000bd47  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x18000bd4c  mov     rbx, [rdi+8]
0x18000bd50  test    rbx, rbx
0x18000bd53  jz      short loc_18000BD8D
0x18000bd55  or      eax, 0FFFFFFFFh
0x18000bd58  lock xadd [rbx+8], eax
0x18000bd5d  cmp     eax, 1
0x18000bd60  jnz     short loc_18000BD8D
0x18000bd62  mov     rax, [rbx]
0x18000bd65  mov     rcx, rbx
0x18000bd68  mov     rax, [rax+8]
0x18000bd6c  call    _guard_dispatch_icall
0x18000bd71  or      eax, 0FFFFFFFFh
0x18000bd74  lock xadd [rbx+0Ch], eax
0x18000bd79  cmp     eax, 1
0x18000bd7c  jnz     short loc_18000BD8D
0x18000bd7e  mov     rax, [rbx]
0x18000bd81  mov     rcx, rbx
0x18000bd84  mov     rax, [rax+10h]
0x18000bd88  call    _guard_dispatch_icall
0x18000bd8d  xor     edx, edx; Tag
0x18000bd8f  mov     rcx, rdi; P
0x18000bd92  call    cs:__imp_ExFreePoolWithTag
0x18000bd99  nop     dword ptr [rax+rax+00h]
0x18000bd9e  mov     rbx, [rsp+28h+arg_0]
0x18000bda3  add     rsp, 20h
0x18000bda7  pop     rdi
0x18000bda8  retn
```
