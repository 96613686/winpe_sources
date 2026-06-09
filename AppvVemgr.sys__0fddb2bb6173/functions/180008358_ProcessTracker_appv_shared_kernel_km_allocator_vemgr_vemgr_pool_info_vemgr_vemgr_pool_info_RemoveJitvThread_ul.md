# ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveJitvThread(ulong,ulong)

- ea: `0x180008358`
- end: `0x180008554`
- name: `?RemoveJitvThread@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJKK@Z`
- size: `508`
- prototype: `__int64 __fastcall(__int64, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000da60`

## callees

- `0x180008358`
- `0x18000c768`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x180008419`
- `ntoskrnl!ExReleaseResourceLite` at `0x180008524`
- `ntoskrnl!ExReleaseResourceLite` at `0x180008419`
- `ntoskrnl!ExReleaseResourceLite` at `0x180008524`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008425`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008530`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008425`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008530`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x180008460`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x180008460`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180008395`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180008395`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000837e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000837e`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x180008478`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x180008478`

## pseudocode

```c
__int64 __fastcall ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveJitvThread(
        __int64 a1,
        int a2,
        int a3)
{
  bool v3; // r14
  volatile signed __int32 *v6; // rdi
  struct _ERESOURCE *v7; // rcx
  __int64 v9; // rbx
  struct _RTL_AVL_TABLE *v10; // rcx
  bool v11; // si
  PVOID v12; // rax
  volatile signed __int32 *v13; // rdi
  volatile signed __int32 *v14; // rdi
  unsigned int v15; // esi
  struct _ERESOURCE *v16; // rcx
  __int128 v17; // [rsp+20h] [rbp-48h] BYREF
  int Buffer; // [rsp+30h] [rbp-38h] BYREF
  __int128 v19; // [rsp+38h] [rbp-30h]
  int v20; // [rsp+78h] [rbp+10h] BYREF

  v20 = a2;
  v3 = 0;
  if ( *(_QWORD *)(a1 + 16) )
  {
    KeEnterCriticalRegion();
    v3 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 16), 1u) == 1;
  }
  v17 = 0;
  if ( appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,unsigned long,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::find(
         (struct _RTL_AVL_TABLE **)a1,
         &v20,
         (__int64)&v17) )
  {
    v9 = v17;
    Buffer = a3;
    v19 = 0;
    v10 = *(struct _RTL_AVL_TABLE **)(v17 + 48);
    v11 = v10
       && (v12 = RtlLookupElementGenericTableAvl(v10, &Buffer)) != 0
       && RtlDeleteElementGenericTableAvl(*(PRTL_AVL_TABLE *)(v9 + 48), v12) != 0;
    v13 = (volatile signed __int32 *)*((_QWORD *)&v19 + 1);
    if ( *((_QWORD *)&v19 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v19 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 16LL))(v13);
      }
    }
    v14 = (volatile signed __int32 *)*((_QWORD *)&v17 + 1);
    v15 = !v11 ? 0xC0000034 : 0;
    if ( *((_QWORD *)&v17 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v17 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 16LL))(v14);
      }
    }
    if ( v3 )
    {
      v16 = *(struct _ERESOURCE **)(a1 + 16);
      if ( v16 )
      {
        ExReleaseResourceLite(v16);
        KeLeaveCriticalRegion();
      }
    }
    return v15;
  }
  else
  {
    v6 = (volatile signed __int32 *)*((_QWORD *)&v17 + 1);
    if ( *((_QWORD *)&v17 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v17 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
        if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 16LL))(v6);
      }
    }
    if ( v3 )
    {
      v7 = *(struct _ERESOURCE **)(a1 + 16);
      if ( v7 )
      {
        ExReleaseResourceLite(v7);
        KeLeaveCriticalRegion();
      }
    }
    return 3221225524LL;
  }
}

```

## disassembly

```asm
0x180008358  mov     [rsp+arg_0], rbx
0x18000835d  mov     [rsp+arg_10], rbp
0x180008362  mov     [rsp+arg_8], edx
0x180008366  push    rsi
0x180008367  push    rdi
0x180008368  push    r14
0x18000836a  sub     rsp, 50h
0x18000836e  xor     r14b, r14b
0x180008371  mov     edi, r8d
0x180008374  cmp     qword ptr [rcx+10h], 0
0x180008379  mov     rbp, rcx
0x18000837c  jz      short loc_1800083AB
0x18000837e  call    cs:__imp_KeEnterCriticalRegion
0x180008385  nop     dword ptr [rax+rax+00h]
0x18000838a  mov     rcx, [rbp+10h]; Resource
0x18000838e  mov     ebx, 1
0x180008393  mov     dl, bl; Wait
0x180008395  call    cs:__imp_ExAcquireResourceExclusiveLite
0x18000839c  nop     dword ptr [rax+rax+00h]
0x1800083a1  cmp     al, bl
0x1800083a3  movzx   r14d, r14b
0x1800083a7  cmovz   r14d, ebx
0x1800083ab  xorps   xmm0, xmm0
0x1800083ae  lea     r8, [rsp+68h+var_48]
0x1800083b3  lea     rdx, [rsp+68h+arg_8]
0x1800083b8  mov     rcx, rbp
0x1800083bb  movdqu  [rsp+68h+var_48], xmm0
0x1800083c1  call    ?find@?$indexed_avl_tree@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uless_predicate@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@KV?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@QEAA_NAEBKAEAV?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,ulong,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::find(ulong const &,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue> &)
0x1800083c6  test    al, al
0x1800083c8  jnz     short loc_18000843B
0x1800083ca  mov     rdi, qword ptr [rsp+68h+var_48+8]
0x1800083cf  test    rdi, rdi
0x1800083d2  jz      short loc_18000840B
0x1800083d4  or      ebx, 0FFFFFFFFh
0x1800083d7  mov     eax, ebx
0x1800083d9  lock xadd [rdi+8], eax
0x1800083de  add     eax, ebx
0x1800083e0  jnz     short loc_18000840B
0x1800083e2  mov     rax, [rdi]
0x1800083e5  mov     rcx, rdi
0x1800083e8  mov     rax, [rax+8]
0x1800083ec  call    _guard_dispatch_icall
0x1800083f1  mov     eax, ebx
0x1800083f3  lock xadd [rdi+0Ch], eax
0x1800083f8  add     eax, ebx
0x1800083fa  jnz     short loc_18000840B
0x1800083fc  mov     rax, [rdi]
0x1800083ff  mov     rcx, rdi
0x180008402  mov     rax, [rax+10h]
0x180008406  call    _guard_dispatch_icall
0x18000840b  test    r14b, r14b
0x18000840e  jz      short loc_180008431
0x180008410  mov     rcx, [rbp+10h]; Resource
0x180008414  test    rcx, rcx
0x180008417  jz      short loc_180008431
0x180008419  call    cs:__imp_ExReleaseResourceLite
0x180008420  nop     dword ptr [rax+rax+00h]
0x180008425  call    cs:__imp_KeLeaveCriticalRegion
0x18000842c  nop     dword ptr [rax+rax+00h]
0x180008431  mov     eax, 0C0000034h
0x180008436  jmp     loc_18000853E
0x18000843b  mov     rbx, qword ptr [rsp+68h+var_48]
0x180008440  xorps   xmm0, xmm0
0x180008443  mov     [rsp+68h+Buffer], edi
0x180008447  movdqu  [rsp+68h+var_30], xmm0
0x18000844d  mov     rcx, [rbx+30h]; Table
0x180008451  test    rcx, rcx
0x180008454  jnz     short loc_18000845B
0x180008456  xor     sil, sil
0x180008459  jmp     short loc_18000848A
0x18000845b  lea     rdx, [rsp+68h+Buffer]; Buffer
0x180008460  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180008467  nop     dword ptr [rax+rax+00h]
0x18000846c  test    rax, rax
0x18000846f  jz      short loc_180008456
0x180008471  mov     rcx, [rbx+30h]; Table
0x180008475  mov     rdx, rax; Buffer
0x180008478  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18000847f  nop     dword ptr [rax+rax+00h]
0x180008484  test    al, al
0x180008486  setnz   sil
0x18000848a  mov     rdi, qword ptr [rsp+68h+var_30+8]
0x18000848f  or      ebx, 0FFFFFFFFh
0x180008492  test    rdi, rdi
0x180008495  jz      short loc_1800084CB
0x180008497  mov     eax, ebx
0x180008499  lock xadd [rdi+8], eax
0x18000849e  add     eax, ebx
0x1800084a0  jnz     short loc_1800084CB
0x1800084a2  mov     rax, [rdi]
0x1800084a5  mov     rcx, rdi
0x1800084a8  mov     rax, [rax+8]
0x1800084ac  call    _guard_dispatch_icall
0x1800084b1  mov     eax, ebx
0x1800084b3  lock xadd [rdi+0Ch], eax
0x1800084b8  add     eax, ebx
0x1800084ba  jnz     short loc_1800084CB
0x1800084bc  mov     rax, [rdi]
0x1800084bf  mov     rcx, rdi
0x1800084c2  mov     rax, [rax+10h]
0x1800084c6  call    _guard_dispatch_icall
0x1800084cb  mov     rdi, qword ptr [rsp+68h+var_48+8]
0x1800084d0  neg     sil
0x1800084d3  sbb     esi, esi
0x1800084d5  not     esi
0x1800084d7  and     esi, 0C0000034h
0x1800084dd  test    rdi, rdi
0x1800084e0  jz      short loc_180008516
0x1800084e2  mov     eax, ebx
0x1800084e4  lock xadd [rdi+8], eax
0x1800084e9  add     eax, ebx
0x1800084eb  jnz     short loc_180008516
0x1800084ed  mov     rax, [rdi]
0x1800084f0  mov     rcx, rdi
0x1800084f3  mov     rax, [rax+8]
0x1800084f7  call    _guard_dispatch_icall
0x1800084fc  mov     eax, ebx
0x1800084fe  lock xadd [rdi+0Ch], eax
0x180008503  add     eax, ebx
0x180008505  jnz     short loc_180008516
0x180008507  mov     rax, [rdi]
0x18000850a  mov     rcx, rdi
0x18000850d  mov     rax, [rax+10h]
0x180008511  call    _guard_dispatch_icall
0x180008516  test    r14b, r14b
0x180008519  jz      short loc_18000853C
0x18000851b  mov     rcx, [rbp+10h]; Resource
0x18000851f  test    rcx, rcx
0x180008522  jz      short loc_18000853C
0x180008524  call    cs:__imp_ExReleaseResourceLite
0x18000852b  nop     dword ptr [rax+rax+00h]
0x180008530  call    cs:__imp_KeLeaveCriticalRegion
0x180008537  nop     dword ptr [rax+rax+00h]
0x18000853c  mov     eax, esi
0x18000853e  lea     r11, [rsp+68h+var_18]
0x180008543  mov     rbx, [r11+20h]
0x180008547  mov     rbp, [r11+30h]
0x18000854b  mov     rsp, r11
0x18000854e  pop     r14
0x180008550  pop     rdi
0x180008551  pop     rsi
0x180008552  retn
```
