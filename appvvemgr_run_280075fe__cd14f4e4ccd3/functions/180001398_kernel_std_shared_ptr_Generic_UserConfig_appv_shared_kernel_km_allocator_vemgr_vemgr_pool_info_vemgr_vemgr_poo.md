# kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info> *)

- ea: `0x180001398`
- end: `0x18000143f`
- name: `??$?0V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@?$shared_ptr@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@QEAA@PEAV?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@Z`
- size: `167`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000e960`
- `0x180011538`

## callees

- `0x180001398`
- `0x180004e20`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1800013c3`
- `ntoskrnl!ExAllocatePool2` at `0x1800013c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000140d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000140d`

## pseudocode

```c
_QWORD *__fastcall kernel_std::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::shared_ptr<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>(
        _QWORD *a1,
        _QWORD *a2)
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
    *(_QWORD *)Pool2 = &kernel_std::detail::sp_counted_impl_p<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::`vftable';
    a1[1] = Pool2;
  }
  else
  {
    a1[1] = 0;
    if ( a2 )
    {
      Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::~Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(a2);
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
0x180001398  mov     [rsp+arg_0], rbx
0x18000139d  push    rdi
0x18000139e  sub     rsp, 20h
0x1800013a2  mov     [rcx], rdx
0x1800013a5  mov     rdi, rdx
0x1800013a8  mov     qword ptr [rcx+8], 0
0x1800013b0  mov     rbx, rcx
0x1800013b3  mov     ecx, 100h
0x1800013b8  mov     edx, 18h
0x1800013bd  mov     r8d, 66446753h
0x1800013c3  call    cs:__imp_ExAllocatePool2
0x1800013ca  nop     dword ptr [rax+rax+00h]
0x1800013cf  test    rax, rax
0x1800013d2  jz      short loc_1800013F3
0x1800013d4  mov     ecx, 1
0x1800013d9  mov     [rax+10h], rdi
0x1800013dd  mov     [rax+8], ecx
0x1800013e0  mov     [rax+0Ch], ecx
0x1800013e3  lea     rcx, ??_7?$sp_counted_impl_p@V?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@detail@kernel_std@@6B@; const kernel_std::detail::sp_counted_impl_p<Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>::`vftable'
0x1800013ea  mov     [rax], rcx
0x1800013ed  mov     [rbx+8], rax
0x1800013f1  jmp     short loc_180001419
0x1800013f3  mov     qword ptr [rbx+8], 0
0x1800013fb  test    rdi, rdi
0x1800013fe  jz      short loc_180001419
0x180001400  mov     rcx, rdi
0x180001403  call    ??1?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA@XZ; Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::~Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(void)
0x180001408  xor     edx, edx; Tag
0x18000140a  mov     rcx, rdi; P
0x18000140d  call    cs:__imp_ExFreePoolWithTag
0x180001414  nop     dword ptr [rax+rax+00h]
0x180001419  mov     rax, [rbx+8]
0x18000141d  test    rax, rax
0x180001420  jz      short loc_180001429
0x180001422  mov     eax, [rax+8]
0x180001425  test    eax, eax
0x180001427  jnz     short loc_180001430
0x180001429  mov     qword ptr [rbx], 0
0x180001430  mov     rax, rbx
0x180001433  mov     rbx, [rsp+28h+arg_0]
0x180001438  add     rsp, 20h
0x18000143c  pop     rdi
0x18000143d  retn
```
