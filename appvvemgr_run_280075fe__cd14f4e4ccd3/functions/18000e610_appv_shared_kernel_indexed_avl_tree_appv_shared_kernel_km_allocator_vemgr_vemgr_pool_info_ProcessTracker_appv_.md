# appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,ulong,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::remove(ulong const &)

- ea: `0x18000e610`
- end: `0x18000e6b8`
- name: `?remove@?$indexed_avl_tree@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uless_predicate@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@KV?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@QEAA_NAEBK@Z`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180008b90`
- `0x180008dd4`

## callees

- `0x18000e610`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x18000e63e`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x18000e63e`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x18000e655`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x18000e655`

## pseudocode

```c
bool __fastcall appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,unsigned long,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::remove(
        PRTL_AVL_TABLE *a1,
        int *a2)
{
  struct _RTL_AVL_TABLE *v3; // rcx
  bool v4; // di
  PVOID v5; // rax
  volatile signed __int32 *v6; // rbx
  int Buffer; // [rsp+20h] [rbp-28h] BYREF
  __int128 v9; // [rsp+28h] [rbp-20h]

  v3 = *a1;
  Buffer = *a2;
  v9 = 0;
  v4 = v3 && (v5 = RtlLookupElementGenericTableAvl(v3, &Buffer)) != 0 && RtlDeleteElementGenericTableAvl(*a1, v5) != 0;
  v6 = (volatile signed __int32 *)*((_QWORD *)&v9 + 1);
  if ( *((_QWORD *)&v9 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v9 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000e610  mov     [rsp+arg_0], rbx
0x18000e615  push    rdi
0x18000e616  sub     rsp, 40h
0x18000e61a  mov     eax, [rdx]
0x18000e61c  mov     rbx, rcx
0x18000e61f  mov     rcx, [rcx]; Table
0x18000e622  xorps   xmm0, xmm0
0x18000e625  mov     [rsp+48h+Buffer], eax
0x18000e629  movdqu  [rsp+48h+var_20], xmm0
0x18000e62f  test    rcx, rcx
0x18000e632  jnz     short loc_18000E639
0x18000e634  xor     dil, dil
0x18000e637  jmp     short loc_18000E667
0x18000e639  lea     rdx, [rsp+48h+Buffer]; Buffer
0x18000e63e  call    cs:__imp_RtlLookupElementGenericTableAvl
0x18000e645  nop     dword ptr [rax+rax+00h]
0x18000e64a  test    rax, rax
0x18000e64d  jz      short loc_18000E634
0x18000e64f  mov     rcx, [rbx]; Table
0x18000e652  mov     rdx, rax; Buffer
0x18000e655  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18000e65c  nop     dword ptr [rax+rax+00h]
0x18000e661  test    al, al
0x18000e663  setnz   dil
0x18000e667  mov     rbx, qword ptr [rsp+48h+var_20+8]
0x18000e66c  test    rbx, rbx
0x18000e66f  jz      short loc_18000E6A9
0x18000e671  or      eax, 0FFFFFFFFh
0x18000e674  lock xadd [rbx+8], eax
0x18000e679  cmp     eax, 1
0x18000e67c  jnz     short loc_18000E6A9
0x18000e67e  mov     rax, [rbx]
0x18000e681  mov     rcx, rbx
0x18000e684  mov     rax, [rax+8]
0x18000e688  call    _guard_dispatch_icall
0x18000e68d  or      edx, 0FFFFFFFFh
0x18000e690  lock xadd [rbx+0Ch], edx
0x18000e695  cmp     edx, 1
0x18000e698  jnz     short loc_18000E6A9
0x18000e69a  mov     rdx, [rbx]
0x18000e69d  mov     rcx, rbx
0x18000e6a0  mov     rax, [rdx+10h]
0x18000e6a4  call    _guard_dispatch_icall
0x18000e6a9  mov     rbx, [rsp+48h+arg_0]
0x18000e6ae  mov     al, dil
0x18000e6b1  add     rsp, 40h
0x18000e6b5  pop     rdi
0x18000e6b6  retn
```
