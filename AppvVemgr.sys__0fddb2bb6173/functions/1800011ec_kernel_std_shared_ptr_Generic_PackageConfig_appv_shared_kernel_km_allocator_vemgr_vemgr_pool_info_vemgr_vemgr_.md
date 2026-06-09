# kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info> *)

- ea: `0x1800011ec`
- end: `0x180001293`
- name: `??$?0V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$shared_ptr@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@QEAA@PEAV?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z`
- size: `167`
- prototype: `_QWORD *__fastcall(_QWORD *, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180001598`
- `0x180001788`
- `0x180010b50`
- `0x18001a79c`

## callees

- `0x1800011ec`
- `0x180004d50`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180001217`
- `ntoskrnl!ExAllocatePool2` at `0x180001217`
- `ntoskrnl!ExFreePoolWithTag` at `0x180001261`
- `ntoskrnl!ExFreePoolWithTag` at `0x180001261`

## pseudocode

```c
_QWORD *__fastcall kernel_std::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(
        _QWORD *a1,
        void *a2)
{
  __int64 Pool2; // rax
  __int64 v5; // rax

  *a1 = a2;
  a1[1] = 0;
  Pool2 = ExAllocatePool2(256, 24, 1715758931);
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 16) = a2;
    *(_DWORD *)(Pool2 + 8) = 1;
    *(_DWORD *)(Pool2 + 12) = 1;
    *(_QWORD *)Pool2 = &kernel_std::detail::sp_counted_impl_p<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::`vftable';
    a1[1] = Pool2;
  }
  else
  {
    a1[1] = 0;
    if ( a2 )
    {
      Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::~Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(a2);
      ExFreePoolWithTag(a2, 0);
    }
  }
  v5 = a1[1];
  if ( !v5 || !*(_DWORD *)(v5 + 8) )
    *a1 = 0;
  return a1;
}

```

## disassembly

```asm
0x1800011ec  mov     [rsp+arg_0], rbx
0x1800011f1  push    rdi
0x1800011f2  sub     rsp, 20h
0x1800011f6  mov     [rcx], rdx
0x1800011f9  mov     rdi, rdx
0x1800011fc  mov     qword ptr [rcx+8], 0
0x180001204  mov     rbx, rcx
0x180001207  mov     ecx, 100h
0x18000120c  mov     edx, 18h
0x180001211  mov     r8d, 66446753h
0x180001217  call    cs:__imp_ExAllocatePool2
0x18000121e  nop     dword ptr [rax+rax+00h]
0x180001223  test    rax, rax
0x180001226  jz      short loc_180001247
0x180001228  mov     ecx, 1
0x18000122d  mov     [rax+10h], rdi
0x180001231  mov     [rax+8], ecx
0x180001234  mov     [rax+0Ch], ecx
0x180001237  lea     rcx, ??_7?$sp_counted_impl_p@V?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@detail@kernel_std@@6B@; const kernel_std::detail::sp_counted_impl_p<Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::`vftable'
0x18000123e  mov     [rax], rcx
0x180001241  mov     [rbx+8], rax
0x180001245  jmp     short loc_18000126D
0x180001247  mov     qword ptr [rbx+8], 0
0x18000124f  test    rdi, rdi
0x180001252  jz      short loc_18000126D
0x180001254  mov     rcx, rdi
0x180001257  call    ??1?$Generic_PackageConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA@XZ; Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::~Generic_PackageConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(void)
0x18000125c  xor     edx, edx; Tag
0x18000125e  mov     rcx, rdi; P
0x180001261  call    cs:__imp_ExFreePoolWithTag
0x180001268  nop     dword ptr [rax+rax+00h]
0x18000126d  mov     rax, [rbx+8]
0x180001271  test    rax, rax
0x180001274  jz      short loc_18000127D
0x180001276  mov     eax, [rax+8]
0x180001279  test    eax, eax
0x18000127b  jnz     short loc_180001284
0x18000127d  mov     qword ptr [rbx], 0
0x180001284  mov     rax, rbx
0x180001287  mov     rbx, [rsp+28h+arg_0]
0x18000128c  add     rsp, 20h
0x180001290  pop     rdi
0x180001291  retn
```
