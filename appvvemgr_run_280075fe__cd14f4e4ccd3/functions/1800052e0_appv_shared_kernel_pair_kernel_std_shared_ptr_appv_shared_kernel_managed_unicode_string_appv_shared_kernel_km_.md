# appv::shared::kernel::pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>::~pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>(void)

- ea: `0x1800052e0`
- end: `0x180005380`
- name: `??1?$pair@V?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@V?$shared_ptr@V?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@2@@kernel@shared@appv@@QEAA@XZ`
- size: `160`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180006880`
- `0x180009208`
- `0x18000a218`
- `0x18000c694`
- `0x18000c8cc`
- `0x18000e6c0`
- `0x180015828`
- `0x180019a60`
- `0x180019aa0`

## callees

- `0x1800052e0`
- `0x18001bb30`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>::~pair<kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>>,kernel_std::shared_ptr<appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>>>(
        __int64 a1)
{
  volatile signed __int32 *v1; // rbx
  __int64 result; // rax
  volatile signed __int32 *v4; // rbx

  v1 = *(volatile signed __int32 **)(a1 + 24);
  if ( v1 )
  {
    result = (unsigned int)_InterlockedDecrement(v1 + 2);
    if ( !(_DWORD)result )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v1 + 8LL))(v1);
      result = (unsigned int)_InterlockedDecrement(v1 + 3);
      if ( !(_DWORD)result )
        result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v1 + 16LL))(v1);
    }
  }
  v4 = *(volatile signed __int32 **)(a1 + 8);
  if ( v4 )
  {
    result = (unsigned int)_InterlockedDecrement(v4 + 2);
    if ( !(_DWORD)result )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
      result = (unsigned int)_InterlockedDecrement(v4 + 3);
      if ( !(_DWORD)result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 16LL))(v4);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800052e0  mov     [rsp+arg_0], rbx
0x1800052e5  mov     [rsp+arg_8], rsi
0x1800052ea  push    rdi
0x1800052eb  sub     rsp, 20h
0x1800052ef  mov     rbx, [rcx+18h]
0x1800052f3  or      esi, 0FFFFFFFFh
0x1800052f6  mov     rdi, rcx
0x1800052f9  test    rbx, rbx
0x1800052fc  jz      short loc_180005332
0x1800052fe  mov     eax, esi
0x180005300  lock xadd [rbx+8], eax
0x180005305  add     eax, esi
0x180005307  jnz     short loc_180005332
0x180005309  mov     rax, [rbx]
0x18000530c  mov     rcx, rbx
0x18000530f  mov     rax, [rax+8]
0x180005313  call    _guard_dispatch_icall
0x180005318  mov     eax, esi
0x18000531a  lock xadd [rbx+0Ch], eax
0x18000531f  add     eax, esi
0x180005321  jnz     short loc_180005332
0x180005323  mov     rax, [rbx]
0x180005326  mov     rcx, rbx
0x180005329  mov     rax, [rax+10h]
0x18000532d  call    _guard_dispatch_icall
0x180005332  mov     rbx, [rdi+8]
0x180005336  test    rbx, rbx
0x180005339  jz      short loc_18000536F
0x18000533b  mov     eax, esi
0x18000533d  lock xadd [rbx+8], eax
0x180005342  add     eax, esi
0x180005344  jnz     short loc_18000536F
0x180005346  mov     rax, [rbx]
0x180005349  mov     rcx, rbx
0x18000534c  mov     rax, [rax+8]
0x180005350  call    _guard_dispatch_icall
0x180005355  mov     eax, esi
0x180005357  lock xadd [rbx+0Ch], eax
0x18000535c  add     eax, esi
0x18000535e  jnz     short loc_18000536F
0x180005360  mov     rax, [rbx]
0x180005363  mov     rcx, rbx
0x180005366  mov     rax, [rax+10h]
0x18000536a  call    _guard_dispatch_icall
0x18000536f  mov     rbx, [rsp+28h+arg_0]
0x180005374  mov     rsi, [rsp+28h+arg_8]
0x180005379  add     rsp, 20h
0x18000537d  pop     rdi
0x18000537e  retn
```
