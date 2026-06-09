# VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ParentProcessIsVirtual(ulong,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> &,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> &,bool &)

- ea: `0x180008048`
- end: `0x18000815c`
- name: `?ParentProcessIsVirtual@?$VirtualEnvironmentManager@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@AEAA_NKAEAV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@AEAV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEA_N@Z`
- size: `276`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180007840`
- `0x180018484`
- `0x18001872c`

## callees

- `0x180005430`
- `0x180007e10`
- `0x180008048`
- `0x18000acbc`
- `0x18001bb30`

## pseudocode

```c
char __fastcall VirtualEnvironmentManager<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ParentProcessIsVirtual(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _BYTE *a5)
{
  __int64 v5; // rcx
  __int64 v8; // rbx
  unsigned int *v9; // rdx
  volatile signed __int32 *v10; // rdi
  volatile signed __int32 *v12; // rdi
  __int128 v13; // [rsp+20h] [rbp-18h] BYREF

  v5 = *(_QWORD *)(a1 + 16);
  v13 = 0;
  if ( (int)ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::GetPrimaryVE(
              v5,
              a2,
              &v13) >= 0
    && ((v8 = v13, !*(_DWORD *)(v13 + 40))
      ? (v9 = (unsigned int *)(v13 + 136))
      : (v9 = (unsigned int *)(**(_QWORD **)(v13 + 72) + 48LL)),
        (int)appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::build_managed_unicode_string(
               a4,
               v9) >= 0) )
  {
    *a5 = *(_BYTE *)(v8 + 116);
    *(_QWORD *)a3 = *(_QWORD *)(v8 + 120);
    kernel_std::detail::shared_count::operator=(
      (volatile signed __int32 **)(a3 + 8),
      (volatile signed __int32 **)(v8 + 128));
    v12 = (volatile signed __int32 *)*((_QWORD *)&v13 + 1);
    if ( *((_QWORD *)&v13 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v13 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        if ( !_InterlockedDecrement(v12 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 16LL))(v12);
      }
    }
    return 1;
  }
  else
  {
    v10 = (volatile signed __int32 *)*((_QWORD *)&v13 + 1);
    if ( *((_QWORD *)&v13 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v13 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      if ( !_InterlockedDecrement(v10 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180008048  mov     rax, rsp
0x18000804b  mov     [rax+8], rbx
0x18000804f  mov     [rax+10h], rsi
0x180008053  push    rdi
0x180008054  sub     rsp, 30h
0x180008058  mov     rcx, [rcx+10h]
0x18000805c  mov     rdi, r8
0x18000805f  xorps   xmm0, xmm0
0x180008062  lea     r8, [rax-18h]
0x180008066  movdqu  xmmword ptr [rax-18h], xmm0
0x18000806b  mov     rsi, r9
0x18000806e  call    ?GetPrimaryVE@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJKAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::GetPrimaryVE(ulong,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x180008073  test    eax, eax
0x180008075  js      short loc_1800080A2
0x180008077  mov     rbx, [rsp+38h+var_18]
0x18000807c  cmp     dword ptr [rbx+28h], 0
0x180008080  jz      short loc_18000808F
0x180008082  mov     rax, [rbx+48h]
0x180008086  mov     rdx, [rax]
0x180008089  add     rdx, 30h ; '0'
0x18000808d  jmp     short loc_180008096
0x18000808f  lea     rdx, [rbx+88h]
0x180008096  mov     rcx, rsi
0x180008099  call    ?build_managed_unicode_string@?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJAEBV1234@@Z; appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::build_managed_unicode_string(appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)
0x18000809e  test    eax, eax
0x1800080a0  jns     short loc_1800080E7
0x1800080a2  mov     rdi, [rsp+38h+var_10]
0x1800080a7  test    rdi, rdi
0x1800080aa  jz      short loc_1800080E3
0x1800080ac  or      ebx, 0FFFFFFFFh
0x1800080af  mov     eax, ebx
0x1800080b1  lock xadd [rdi+8], eax
0x1800080b6  add     eax, ebx
0x1800080b8  jnz     short loc_1800080E3
0x1800080ba  mov     rax, [rdi]
0x1800080bd  mov     rcx, rdi
0x1800080c0  mov     rax, [rax+8]
0x1800080c4  call    _guard_dispatch_icall
0x1800080c9  mov     eax, ebx
0x1800080cb  lock xadd [rdi+0Ch], eax
0x1800080d0  add     eax, ebx
0x1800080d2  jnz     short loc_1800080E3
0x1800080d4  mov     rax, [rdi]
0x1800080d7  mov     rcx, rdi
0x1800080da  mov     rax, [rax+10h]
0x1800080de  call    _guard_dispatch_icall
0x1800080e3  xor     al, al
0x1800080e5  jmp     short loc_18000814B
0x1800080e7  mov     cl, [rbx+74h]
0x1800080ea  lea     rdx, [rbx+80h]
0x1800080f1  mov     rax, [rsp+38h+arg_20]
0x1800080f6  mov     [rax], cl
0x1800080f8  lea     rcx, [rdi+8]
0x1800080fc  mov     rax, [rbx+78h]
0x180008100  mov     [rdi], rax
0x180008103  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x180008108  mov     rdi, [rsp+38h+var_10]
0x18000810d  test    rdi, rdi
0x180008110  jz      short loc_180008149
0x180008112  or      ebx, 0FFFFFFFFh
0x180008115  mov     eax, ebx
0x180008117  lock xadd [rdi+8], eax
0x18000811c  add     eax, ebx
0x18000811e  jnz     short loc_180008149
0x180008120  mov     rax, [rdi]
0x180008123  mov     rcx, rdi
0x180008126  mov     rax, [rax+8]
0x18000812a  call    _guard_dispatch_icall
0x18000812f  mov     eax, ebx
0x180008131  lock xadd [rdi+0Ch], eax
0x180008136  add     eax, ebx
0x180008138  jnz     short loc_180008149
0x18000813a  mov     rax, [rdi]
0x18000813d  mov     rcx, rdi
0x180008140  mov     rax, [rax+10h]
0x180008144  call    _guard_dispatch_icall
0x180008149  mov     al, 1
0x18000814b  mov     rbx, [rsp+38h+arg_0]
0x180008150  mov     rsi, [rsp+38h+arg_8]
0x180008155  add     rsp, 30h
0x180008159  pop     rdi
0x18000815a  retn
```
