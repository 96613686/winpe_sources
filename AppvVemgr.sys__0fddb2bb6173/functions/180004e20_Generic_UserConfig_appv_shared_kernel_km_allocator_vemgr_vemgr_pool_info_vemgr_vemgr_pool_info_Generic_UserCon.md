# Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::~Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(void)

- ea: `0x180004e20`
- end: `0x180004f1a`
- name: `??1?$Generic_UserConfig@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAA@XZ`
- size: `250`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180001398`
- `0x18000bdb0`

## callees

- `0x180004e20`
- `0x180005178`
- `0x18000ad50`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x180004e92`
- `ntoskrnl!ExFreePoolWithTag` at `0x180004ea9`
- `ntoskrnl!ExFreePoolWithTag` at `0x180004ec0`
- `ntoskrnl!ExFreePoolWithTag` at `0x180004e92`
- `ntoskrnl!ExFreePoolWithTag` at `0x180004ea9`
- `ntoskrnl!ExFreePoolWithTag` at `0x180004ec0`

## pseudocode

```c
void __fastcall Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::~Generic_UserConfig<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>(
        _QWORD *a1)
{
  volatile signed __int32 *v2; // rbx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  volatile signed __int32 *v6; // rbx

  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>((__int64)(a1 + 18));
  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(a1 + 13);
  v2 = (volatile signed __int32 *)a1[15];
  if ( v2 )
  {
    if ( !_InterlockedDecrement(v2 + 2) )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
      if ( !_InterlockedDecrement(v2 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 16LL))(v2);
    }
  }
  v3 = (void *)a1[11];
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  v4 = (void *)a1[7];
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  v5 = (void *)a1[3];
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  v6 = (volatile signed __int32 *)a1[1];
  if ( v6 && !_InterlockedDecrement(v6 + 2) )
  {
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    if ( !_InterlockedDecrement(v6 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 16LL))(v6);
  }
}

```

## disassembly

```asm
0x180004e20  mov     [rsp+arg_0], rbx
0x180004e25  mov     [rsp+arg_8], rsi
0x180004e2a  push    rdi
0x180004e2b  sub     rsp, 20h
0x180004e2f  mov     rdi, rcx
0x180004e32  add     rcx, 90h
0x180004e39  call    ??1?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::~doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>(void)
0x180004e3e  lea     rcx, [rdi+68h]
0x180004e42  call    ?clear@?$doubly_linked_list@V?$shared_ptr@U?$Generic_VfsMapping@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Generic_VfsMapping<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,vemgr::vemgr_pool_info>::clear(void)
0x180004e47  mov     rbx, [rdi+78h]
0x180004e4b  or      esi, 0FFFFFFFFh
0x180004e4e  test    rbx, rbx
0x180004e51  jz      short loc_180004E87
0x180004e53  mov     eax, esi
0x180004e55  lock xadd [rbx+8], eax
0x180004e5a  add     eax, esi
0x180004e5c  jnz     short loc_180004E87
0x180004e5e  mov     rax, [rbx]
0x180004e61  mov     rcx, rbx
0x180004e64  mov     rax, [rax+8]
0x180004e68  call    _guard_dispatch_icall
0x180004e6d  mov     eax, esi
0x180004e6f  lock xadd [rbx+0Ch], eax
0x180004e74  add     eax, esi
0x180004e76  jnz     short loc_180004E87
0x180004e78  mov     rax, [rbx]
0x180004e7b  mov     rcx, rbx
0x180004e7e  mov     rax, [rax+10h]
0x180004e82  call    _guard_dispatch_icall
0x180004e87  mov     rcx, [rdi+58h]; P
0x180004e8b  test    rcx, rcx
0x180004e8e  jz      short loc_180004E9E
0x180004e90  xor     edx, edx; Tag
0x180004e92  call    cs:__imp_ExFreePoolWithTag
0x180004e99  nop     dword ptr [rax+rax+00h]
0x180004e9e  mov     rcx, [rdi+38h]; P
0x180004ea2  test    rcx, rcx
0x180004ea5  jz      short loc_180004EB5
0x180004ea7  xor     edx, edx; Tag
0x180004ea9  call    cs:__imp_ExFreePoolWithTag
0x180004eb0  nop     dword ptr [rax+rax+00h]
0x180004eb5  mov     rcx, [rdi+18h]; P
0x180004eb9  test    rcx, rcx
0x180004ebc  jz      short loc_180004ECC
0x180004ebe  xor     edx, edx; Tag
0x180004ec0  call    cs:__imp_ExFreePoolWithTag
0x180004ec7  nop     dword ptr [rax+rax+00h]
0x180004ecc  mov     rbx, [rdi+8]
0x180004ed0  test    rbx, rbx
0x180004ed3  jz      short loc_180004F09
0x180004ed5  mov     eax, esi
0x180004ed7  lock xadd [rbx+8], eax
0x180004edc  add     eax, esi
0x180004ede  jnz     short loc_180004F09
0x180004ee0  mov     rax, [rbx]
0x180004ee3  mov     rcx, rbx
0x180004ee6  mov     rax, [rax+8]
0x180004eea  call    _guard_dispatch_icall
0x180004eef  mov     eax, esi
0x180004ef1  lock xadd [rbx+0Ch], eax
0x180004ef6  add     eax, esi
0x180004ef8  jnz     short loc_180004F09
0x180004efa  mov     rax, [rbx]
0x180004efd  mov     rcx, rbx
0x180004f00  mov     rax, [rax+10h]
0x180004f04  call    _guard_dispatch_icall
0x180004f09  mov     rbx, [rsp+28h+arg_0]
0x180004f0e  mov     rsi, [rsp+28h+arg_8]
0x180004f13  add     rsp, 20h
0x180004f17  pop     rdi
0x180004f18  retn
```
