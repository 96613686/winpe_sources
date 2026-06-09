# kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> *)

- ea: `0x180001448`
- end: `0x1800014fe`
- name: `??$?0V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@QEAA@PEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z`
- size: `182`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003f50`
- `0x180006880`
- `0x18000b478`
- `0x1800134a8`

## callees

- `0x180001448`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x180001473`
- `ntoskrnl!ExAllocatePool2` at `0x180001473`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800014bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800014cc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800014bb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800014cc`

## pseudocode

```c
_QWORD *__fastcall kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 Pool2; // rax
  void *v5; // rcx
  __int64 v6; // rax

  *a1 = a2;
  a1[1] = 0;
  Pool2 = ExAllocatePool2(256, 24, 1715758931);
  if ( Pool2 )
  {
    *(_QWORD *)(Pool2 + 16) = a2;
    *(_DWORD *)(Pool2 + 8) = 1;
    *(_DWORD *)(Pool2 + 12) = 1;
    *(_QWORD *)Pool2 = &kernel_std::detail::sp_counted_impl_p<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::`vftable';
    a1[1] = Pool2;
  }
  else
  {
    a1[1] = 0;
    if ( a2 )
    {
      v5 = (void *)a2[1];
      if ( v5 )
        ExFreePoolWithTag(v5, 0);
      ExFreePoolWithTag(a2, 0);
    }
  }
  v6 = a1[1];
  if ( !v6 || !*(_DWORD *)(v6 + 8) )
    *a1 = 0;
  return a1;
}

```

## disassembly

```asm
0x180001448  mov     [rsp+arg_0], rbx
0x18000144d  push    rdi
0x18000144e  sub     rsp, 20h
0x180001452  mov     [rcx], rdx
0x180001455  mov     rdi, rdx
0x180001458  mov     qword ptr [rcx+8], 0
0x180001460  mov     rbx, rcx
0x180001463  mov     ecx, 100h
0x180001468  mov     edx, 18h
0x18000146d  mov     r8d, 66446753h
0x180001473  call    cs:__imp_ExAllocatePool2
0x18000147a  nop     dword ptr [rax+rax+00h]
0x18000147f  test    rax, rax
0x180001482  jz      short loc_1800014A3
0x180001484  mov     ecx, 1
0x180001489  mov     [rax+10h], rdi
0x18000148d  mov     [rax+8], ecx
0x180001490  mov     [rax+0Ch], ecx
0x180001493  lea     rcx, ??_7?$sp_counted_impl_p@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@detail@kernel_std@@6B@; const kernel_std::detail::sp_counted_impl_p<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>::`vftable'
0x18000149a  mov     [rax], rcx
0x18000149d  mov     [rbx+8], rax
0x1800014a1  jmp     short loc_1800014D8
0x1800014a3  mov     qword ptr [rbx+8], 0
0x1800014ab  test    rdi, rdi
0x1800014ae  jz      short loc_1800014D8
0x1800014b0  mov     rcx, [rdi+8]; P
0x1800014b4  test    rcx, rcx
0x1800014b7  jz      short loc_1800014C7
0x1800014b9  xor     edx, edx; Tag
0x1800014bb  call    cs:__imp_ExFreePoolWithTag
0x1800014c2  nop     dword ptr [rax+rax+00h]
0x1800014c7  xor     edx, edx; Tag
0x1800014c9  mov     rcx, rdi; P
0x1800014cc  call    cs:__imp_ExFreePoolWithTag
0x1800014d3  nop     dword ptr [rax+rax+00h]
0x1800014d8  mov     rax, [rbx+8]
0x1800014dc  test    rax, rax
0x1800014df  jz      short loc_1800014E8
0x1800014e1  mov     eax, [rax+8]
0x1800014e4  test    eax, eax
0x1800014e6  jnz     short loc_1800014EF
0x1800014e8  mov     qword ptr [rbx], 0
0x1800014ef  mov     rax, rbx
0x1800014f2  mov     rbx, [rsp+28h+arg_0]
0x1800014f7  add     rsp, 20h
0x1800014fb  pop     rdi
0x1800014fc  retn
```
