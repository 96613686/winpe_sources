# Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::~Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(void)

- ea: `0x180004d50`
- end: `0x180004e19`
- name: `??1?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA@XZ`
- size: `201`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800011ec`
- `0x18000bcf0`

## callees

- `0x180004d50`
- `0x180005178`
- `0x18000ad50`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180004dbf`
- `ntoskrnl!ExFreePoolWithTag` at `0x180004dbf`

## pseudocode

```c
void __fastcall Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::~Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(
        _QWORD *a1)
{
  volatile signed __int32 *v2; // rbx
  void *v3; // rcx
  volatile signed __int32 *v4; // rbx

  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)(a1 + 12));
  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(a1 + 7);
  v2 = (volatile signed __int32 *)a1[9];
  if ( v2 )
  {
    if ( !_InterlockedDecrement(v2 + 2) )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
      if ( !_InterlockedDecrement(v2 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 16LL))(v2);
    }
  }
  v3 = (void *)a1[3];
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  v4 = (volatile signed __int32 *)a1[1];
  if ( v4 && !_InterlockedDecrement(v4 + 2) )
  {
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    if ( !_InterlockedDecrement(v4 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 16LL))(v4);
  }
}

```

## disassembly

```asm
0x180004d50  mov     [rsp+arg_0], rbx
0x180004d55  mov     [rsp+arg_8], rsi
0x180004d5a  push    rdi
0x180004d5b  sub     rsp, 20h
0x180004d5f  mov     rdi, rcx
0x180004d62  add     rcx, 60h ; '`'
0x180004d66  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x180004d6b  lea     rcx, [rdi+38h]
0x180004d6f  call    ?clear@?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(void)
0x180004d74  mov     rbx, [rdi+48h]
0x180004d78  or      esi, 0FFFFFFFFh
0x180004d7b  test    rbx, rbx
0x180004d7e  jz      short loc_180004DB4
0x180004d80  mov     eax, esi
0x180004d82  lock xadd [rbx+8], eax
0x180004d87  add     eax, esi
0x180004d89  jnz     short loc_180004DB4
0x180004d8b  mov     rax, [rbx]
0x180004d8e  mov     rcx, rbx
0x180004d91  mov     rax, [rax+8]
0x180004d95  call    _guard_dispatch_icall
0x180004d9a  mov     eax, esi
0x180004d9c  lock xadd [rbx+0Ch], eax
0x180004da1  add     eax, esi
0x180004da3  jnz     short loc_180004DB4
0x180004da5  mov     rax, [rbx]
0x180004da8  mov     rcx, rbx
0x180004dab  mov     rax, [rax+10h]
0x180004daf  call    _guard_dispatch_icall
0x180004db4  mov     rcx, [rdi+18h]; P
0x180004db8  test    rcx, rcx
0x180004dbb  jz      short loc_180004DCB
0x180004dbd  xor     edx, edx; Tag
0x180004dbf  call    cs:__imp_ExFreePoolWithTag
0x180004dc6  nop     dword ptr [rax+rax+00h]
0x180004dcb  mov     rbx, [rdi+8]
0x180004dcf  test    rbx, rbx
0x180004dd2  jz      short loc_180004E08
0x180004dd4  mov     eax, esi
0x180004dd6  lock xadd [rbx+8], eax
0x180004ddb  add     eax, esi
0x180004ddd  jnz     short loc_180004E08
0x180004ddf  mov     rax, [rbx]
0x180004de2  mov     rcx, rbx
0x180004de5  mov     rax, [rax+8]
0x180004de9  call    _guard_dispatch_icall
0x180004dee  mov     eax, esi
0x180004df0  lock xadd [rbx+0Ch], eax
0x180004df5  add     eax, esi
0x180004df7  jnz     short loc_180004E08
0x180004df9  mov     rax, [rbx]
0x180004dfc  mov     rcx, rbx
0x180004dff  mov     rax, [rax+10h]
0x180004e03  call    _guard_dispatch_icall
0x180004e08  mov     rbx, [rsp+28h+arg_0]
0x180004e0d  mov     rsi, [rsp+28h+arg_8]
0x180004e12  add     rsp, 20h
0x180004e16  pop     rdi
0x180004e17  retn
```
