# kernel_std::detail::sp_counted_impl_p<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::dispose(void)

- ea: `0x18000bcf0`
- end: `0x18000bd1f`
- name: `?dispose@?$sp_counted_impl_p@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@detail@kernel_std@@UEAAXXZ`
- size: `47`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180004d50`
- `0x18000bcf0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18000bd0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000bd0c`

## pseudocode

```c
void __fastcall kernel_std::detail::sp_counted_impl_p<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::dispose(
        __int64 a1)
{
  void *v1; // rbx

  v1 = *(void **)(a1 + 16);
  if ( v1 )
  {
    Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::~Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(*(_QWORD **)(a1 + 16));
    ExFreePoolWithTag(v1, 0);
  }
}

```

## disassembly

```asm
0x18000bcf0  push    rbx
0x18000bcf2  sub     rsp, 20h
0x18000bcf6  mov     rbx, [rcx+10h]
0x18000bcfa  test    rbx, rbx
0x18000bcfd  jz      short loc_18000BD18
0x18000bcff  mov     rcx, rbx
0x18000bd02  call    ??1?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA@XZ; Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::~Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(void)
0x18000bd07  xor     edx, edx; Tag
0x18000bd09  mov     rcx, rbx; P
0x18000bd0c  call    cs:__imp_ExFreePoolWithTag
0x18000bd13  nop     dword ptr [rax+rax+00h]
0x18000bd18  add     rsp, 20h
0x18000bd1c  pop     rbx
0x18000bd1d  retn
```
