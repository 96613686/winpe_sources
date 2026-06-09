# kernel_std::detail::sp_counted_impl_p<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::dispose(void)

- ea: `0x18000bdb0`
- end: `0x18000bddf`
- name: `?dispose@?$sp_counted_impl_p@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@detail@kernel_std@@UEAAXXZ`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180004e20`
- `0x18000bdb0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18000bdcc`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000bdcc`

## pseudocode

```c
void __fastcall kernel_std::detail::sp_counted_impl_p<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::dispose(
        __int64 a1)
{
  void *v1; // rbx

  v1 = *(void **)(a1 + 16);
  if ( v1 )
  {
    Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::~Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(*(_QWORD **)(a1 + 16));
    ExFreePoolWithTag(v1, 0);
  }
}

```

## disassembly

```asm
0x18000bdb0  push    rbx
0x18000bdb2  sub     rsp, 20h
0x18000bdb6  mov     rbx, [rcx+10h]
0x18000bdba  test    rbx, rbx
0x18000bdbd  jz      short loc_18000BDD8
0x18000bdbf  mov     rcx, rbx
0x18000bdc2  call    ??1?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA@XZ; Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::~Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(void)
0x18000bdc7  xor     edx, edx; Tag
0x18000bdc9  mov     rcx, rbx; P
0x18000bdcc  call    cs:__imp_ExFreePoolWithTag
0x18000bdd3  nop     dword ptr [rax+rax+00h]
0x18000bdd8  add     rsp, 20h
0x18000bddc  pop     rbx
0x18000bddd  retn
```
