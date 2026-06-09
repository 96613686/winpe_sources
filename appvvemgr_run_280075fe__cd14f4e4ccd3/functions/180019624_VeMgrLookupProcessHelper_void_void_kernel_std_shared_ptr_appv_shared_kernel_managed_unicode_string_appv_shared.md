# VeMgrLookupProcessHelper(void *,void *,kernel_std::shared_ptr<appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>> &,_VE_USER_SID *)

- ea: `0x180019624`
- end: `0x18001990d`
- name: `?VeMgrLookupProcessHelper@@YAJPEAX0AEAV?$shared_ptr@V?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@kernel_std@@PEAT_VE_USER_SID@@@Z`
- size: `745`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x18001aea0`

## callees

- `0x180005430`
- `0x180007e10`
- `0x18000ab2c`
- `0x18000c768`
- `0x1800178ec`
- `0x180019624`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x180019716`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001978f`
- `ntoskrnl!ExReleaseResourceLite` at `0x180019716`
- `ntoskrnl!ExReleaseResourceLite` at `0x18001978f`
- `ntoskrnl!RtlCopySid` at `0x18001986f`
- `ntoskrnl!RtlCopySid` at `0x18001986f`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001988c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800198a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x18001988c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800198a8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180019722`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001979b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180019722`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18001979b`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180019687`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180019687`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001966f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18001966f`

## pseudocode

```c
__int64 __fastcall VeMgrLookupProcessHelper(unsigned int a1, unsigned int a2, _QWORD *a3, void *a4)
{
  bool v4; // r14
  __int64 v7; // r15
  NTSTATUS v8; // r12d
  volatile signed __int32 *v9; // rdi
  struct _ERESOURCE *v10; // rcx
  NTSTATUS JitvThread; // eax
  volatile signed __int32 *v12; // rdi
  NTSTATUS PrimaryVE; // esi
  struct _ERESOURCE *v14; // rcx
  volatile signed __int32 *v15; // rdi
  __int64 v17; // rdi
  __int64 v18; // rdx
  bool v19; // zf
  volatile signed __int32 *v20; // rdi
  unsigned int v21; // [rsp+20h] [rbp-30h] BYREF
  __int128 v22; // [rsp+28h] [rbp-28h] BYREF
  PVOID P[3]; // [rsp+38h] [rbp-18h] BYREF

  v4 = 0;
  v21 = a1;
  v22 = 0;
  v7 = *(_QWORD *)(*((_QWORD *)vemgr::g_pDeviceExtn + 4) + 16LL);
  if ( *(_QWORD *)(v7 + 16) )
  {
    KeEnterCriticalRegion();
    v4 = ExAcquireResourceSharedLite(*(PERESOURCE *)(v7 + 16), 1u) == 1;
  }
  *(_OWORD *)P = 0;
  v8 = -1073741772;
  if ( !(unsigned __int8)appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,unsigned long,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::find(
                           v7,
                           &v21,
                           P) )
  {
    v9 = (volatile signed __int32 *)P[1];
    if ( P[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)P[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
      }
    }
    if ( v4 )
    {
      v10 = *(struct _ERESOURCE **)(v7 + 16);
      if ( v10 )
      {
        ExReleaseResourceLite(v10);
        KeLeaveCriticalRegion();
      }
    }
LABEL_19:
    PrimaryVE = ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::GetPrimaryVE(
                  *(_QWORD *)(*((_QWORD *)vemgr::g_pDeviceExtn + 4) + 16LL),
                  a1,
                  &v22);
    goto LABEL_20;
  }
  JitvThread = ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue::FindJitvThread(
                 P[0],
                 a2,
                 &v22);
  v12 = (volatile signed __int32 *)P[1];
  PrimaryVE = JitvThread;
  if ( P[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)P[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  if ( v4 )
  {
    v14 = *(struct _ERESOURCE **)(v7 + 16);
    if ( v14 )
    {
      ExReleaseResourceLite(v14);
      KeLeaveCriticalRegion();
    }
  }
  if ( PrimaryVE == -1073741772 )
    goto LABEL_19;
LABEL_20:
  if ( PrimaryVE < 0 )
  {
LABEL_21:
    v15 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
    if ( *((_QWORD *)&v22 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 16LL))(v15);
    }
    return (unsigned int)PrimaryVE;
  }
  v17 = v22;
  v18 = v22 + 128;
  *a3 = *(_QWORD *)(v22 + 120);
  kernel_std::detail::shared_count::operator=(a3 + 1, v18);
  v19 = *(_DWORD *)(v17 + 40) == 0;
  memset(P, 0, sizeof(P));
  if ( !v19 )
  {
    v8 = appv::shared::kernel::sid<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(
           (__int64)P,
           *(void **)(**(_QWORD **)(v17 + 72) + 96LL),
           *(_DWORD *)(**(_QWORD **)(v17 + 72) + 80LL));
    if ( v8 >= 0 )
    {
      PrimaryVE = RtlCopySid(0x44u, a4, P[2]);
      if ( P[1] )
        ExFreePoolWithTag(P[1], 0);
      goto LABEL_21;
    }
  }
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0);
  v20 = (volatile signed __int32 *)*((_QWORD *)&v22 + 1);
  if ( *((_QWORD *)&v22 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v22 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
      if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 16LL))(v20);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180019624  mov     [rsp-38h+arg_8], rbx
0x180019629  mov     [rsp-38h+DestinationSid], r9
0x18001962e  mov     [rsp-38h+arg_0], rcx
0x180019633  push    rbp
0x180019634  push    rsi
0x180019635  push    rdi
0x180019636  push    r12
0x180019638  push    r13
0x18001963a  push    r14
0x18001963c  push    r15
0x18001963e  mov     rbp, rsp
0x180019641  sub     rsp, 50h
0x180019645  mov     rax, cs:?g_pDeviceExtn@vemgr@@3PEAUDEVICE_EXTENSION@1@EA; vemgr::DEVICE_EXTENSION * vemgr::g_pDeviceExtn
0x18001964c  xor     r14b, r14b
0x18001964f  xorps   xmm0, xmm0
0x180019652  mov     [rbp+var_30], ecx
0x180019655  mov     r13, r8
0x180019658  mov     rbx, rdx
0x18001965b  movdqu  [rbp+var_28], xmm0
0x180019660  mov     r10, [rax+20h]
0x180019664  mov     r15, [r10+10h]
0x180019668  cmp     qword ptr [r15+10h], 0
0x18001966d  jz      short loc_18001969E
0x18001966f  call    cs:__imp_KeEnterCriticalRegion
0x180019676  nop     dword ptr [rax+rax+00h]
0x18001967b  mov     rcx, [r15+10h]; Resource
0x18001967f  mov     edi, 1
0x180019684  mov     dl, dil; Wait
0x180019687  call    cs:__imp_ExAcquireResourceSharedLite
0x18001968e  nop     dword ptr [rax+rax+00h]
0x180019693  cmp     al, dil
0x180019696  movzx   r14d, r14b
0x18001969a  cmovz   r14d, edi
0x18001969e  xorps   xmm0, xmm0
0x1800196a1  lea     r8, [rbp+P]
0x1800196a5  lea     rdx, [rbp+var_30]
0x1800196a9  mov     rcx, r15
0x1800196ac  movdqu  xmmword ptr [rbp+P], xmm0
0x1800196b1  call    ?find@?$indexed_avl_tree@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uless_predicate@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@KV?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@QEAA_NAEBKAEAV?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,ulong,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::find(ulong const &,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue> &)
0x1800196b6  mov     r12d, 0C0000034h
0x1800196bc  test    al, al
0x1800196be  jnz     short loc_180019730
0x1800196c0  mov     rdi, [rbp+P+8]
0x1800196c4  or      ebx, 0FFFFFFFFh
0x1800196c7  test    rdi, rdi
0x1800196ca  jz      short loc_180019700
0x1800196cc  mov     eax, ebx
0x1800196ce  lock xadd [rdi+8], eax
0x1800196d3  add     eax, ebx
0x1800196d5  jnz     short loc_180019700
0x1800196d7  mov     rax, [rdi]
0x1800196da  mov     rcx, rdi
0x1800196dd  mov     rax, [rax+8]
0x1800196e1  call    _guard_dispatch_icall
0x1800196e6  mov     eax, ebx
0x1800196e8  lock xadd [rdi+0Ch], eax
0x1800196ed  add     eax, ebx
0x1800196ef  jnz     short loc_180019700
0x1800196f1  mov     rax, [rdi]
0x1800196f4  mov     rcx, rdi
0x1800196f7  mov     rax, [rax+10h]
0x1800196fb  call    _guard_dispatch_icall
0x180019700  test    r14b, r14b
0x180019703  jz      loc_1800197AC
0x180019709  mov     rcx, [r15+10h]; Resource
0x18001970d  test    rcx, rcx
0x180019710  jz      loc_1800197AC
0x180019716  call    cs:__imp_ExReleaseResourceLite
0x18001971d  nop     dword ptr [rax+rax+00h]
0x180019722  call    cs:__imp_KeLeaveCriticalRegion
0x180019729  nop     dword ptr [rax+rax+00h]
0x18001972e  jmp     short loc_1800197AC
0x180019730  mov     rcx, [rbp+P]
0x180019734  lea     r8, [rbp+var_28]
0x180019738  mov     edx, ebx
0x18001973a  call    ?FindJitvThread@ProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJKAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue::FindJitvThread(ulong,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x18001973f  mov     rdi, [rbp+P+8]
0x180019743  or      ebx, 0FFFFFFFFh
0x180019746  mov     esi, eax
0x180019748  test    rdi, rdi
0x18001974b  jz      short loc_180019781
0x18001974d  mov     eax, ebx
0x18001974f  lock xadd [rdi+8], eax
0x180019754  add     eax, ebx
0x180019756  jnz     short loc_180019781
0x180019758  mov     rax, [rdi]
0x18001975b  mov     rcx, rdi
0x18001975e  mov     rax, [rax+8]
0x180019762  call    _guard_dispatch_icall
0x180019767  mov     eax, ebx
0x180019769  lock xadd [rdi+0Ch], eax
0x18001976e  add     eax, ebx
0x180019770  jnz     short loc_180019781
0x180019772  mov     rax, [rdi]
0x180019775  mov     rcx, rdi
0x180019778  mov     rax, [rax+10h]
0x18001977c  call    _guard_dispatch_icall
0x180019781  test    r14b, r14b
0x180019784  jz      short loc_1800197A7
0x180019786  mov     rcx, [r15+10h]; Resource
0x18001978a  test    rcx, rcx
0x18001978d  jz      short loc_1800197A7
0x18001978f  call    cs:__imp_ExReleaseResourceLite
0x180019796  nop     dword ptr [rax+rax+00h]
0x18001979b  call    cs:__imp_KeLeaveCriticalRegion
0x1800197a2  nop     dword ptr [rax+rax+00h]
0x1800197a7  cmp     esi, r12d
0x1800197aa  jnz     short loc_1800197C9
0x1800197ac  mov     rax, cs:?g_pDeviceExtn@vemgr@@3PEAUDEVICE_EXTENSION@1@EA; vemgr::DEVICE_EXTENSION * vemgr::g_pDeviceExtn
0x1800197b3  lea     r8, [rbp+var_28]
0x1800197b7  mov     edx, dword ptr [rbp+arg_0]
0x1800197ba  mov     rcx, [rax+20h]
0x1800197be  mov     rcx, [rcx+10h]
0x1800197c2  call    ?GetPrimaryVE@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJKAEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::GetPrimaryVE(ulong,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)
0x1800197c7  mov     esi, eax
0x1800197c9  test    esi, esi
0x1800197cb  jns     short loc_180019811
0x1800197cd  mov     rdi, qword ptr [rbp+var_28+8]
0x1800197d1  test    rdi, rdi
0x1800197d4  jz      short loc_18001980A
0x1800197d6  mov     eax, ebx
0x1800197d8  lock xadd [rdi+8], eax
0x1800197dd  add     eax, ebx
0x1800197df  jnz     short loc_18001980A
0x1800197e1  mov     rax, [rdi]
0x1800197e4  mov     rcx, rdi
0x1800197e7  mov     rax, [rax+8]
0x1800197eb  call    _guard_dispatch_icall
0x1800197f0  mov     eax, ebx
0x1800197f2  lock xadd [rdi+0Ch], eax
0x1800197f7  add     eax, ebx
0x1800197f9  jnz     short loc_18001980A
0x1800197fb  mov     rax, [rdi]
0x1800197fe  mov     rcx, rdi
0x180019801  mov     rax, [rax+10h]
0x180019805  call    _guard_dispatch_icall
0x18001980a  mov     eax, esi
0x18001980c  jmp     loc_1800198F4
0x180019811  mov     rdi, qword ptr [rbp+var_28]
0x180019815  lea     rcx, [r13+8]
0x180019819  mov     rax, [rdi+78h]
0x18001981d  lea     rdx, [rdi+80h]
0x180019824  mov     [r13+0], rax
0x180019828  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x18001982d  cmp     dword ptr [rdi+28h], 0
0x180019831  xorps   xmm0, xmm0
0x180019834  movdqu  xmmword ptr [rbp+P+8], xmm0
0x180019839  mov     [rbp+P], 0
0x180019841  jz      short loc_18001989D
0x180019843  mov     rax, [rdi+48h]
0x180019847  lea     rcx, [rbp+P]
0x18001984b  mov     rdx, [rax]
0x18001984e  mov     r8d, [rdx+50h]
0x180019852  mov     rdx, [rdx+60h]
0x180019856  call    ?assign@?$sid@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@QEAAJPEAXK@Z; appv::shared::kernel::sid<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>>::assign(void *,ulong)
0x18001985b  mov     r12d, eax
0x18001985e  test    eax, eax
0x180019860  js      short loc_18001989D
0x180019862  mov     r8, [rbp+SourceSid]; SourceSid
0x180019866  mov     ecx, 44h ; 'D'; DestinationSidLength
0x18001986b  mov     rdx, [rbp+DestinationSid]; DestinationSid
0x18001986f  call    cs:__imp_RtlCopySid
0x180019876  nop     dword ptr [rax+rax+00h]
0x18001987b  mov     rcx, [rbp+P+8]; P
0x18001987f  mov     esi, eax
0x180019881  test    rcx, rcx
0x180019884  jz      loc_1800197CD
0x18001988a  xor     edx, edx; Tag
0x18001988c  call    cs:__imp_ExFreePoolWithTag
0x180019893  nop     dword ptr [rax+rax+00h]
0x180019898  jmp     loc_1800197CD
0x18001989d  mov     rcx, [rbp+P+8]; P
0x1800198a1  test    rcx, rcx
0x1800198a4  jz      short loc_1800198B4
0x1800198a6  xor     edx, edx; Tag
0x1800198a8  call    cs:__imp_ExFreePoolWithTag
0x1800198af  nop     dword ptr [rax+rax+00h]
0x1800198b4  mov     rdi, qword ptr [rbp+var_28+8]
0x1800198b8  test    rdi, rdi
0x1800198bb  jz      short loc_1800198F1
0x1800198bd  mov     eax, ebx
0x1800198bf  lock xadd [rdi+8], eax
0x1800198c4  add     eax, ebx
0x1800198c6  jnz     short loc_1800198F1
0x1800198c8  mov     rax, [rdi]
0x1800198cb  mov     rcx, rdi
0x1800198ce  mov     rax, [rax+8]
0x1800198d2  call    _guard_dispatch_icall
0x1800198d7  mov     edx, ebx
0x1800198d9  lock xadd [rdi+0Ch], edx
0x1800198de  add     edx, ebx
0x1800198e0  jnz     short loc_1800198F1
0x1800198e2  mov     rdx, [rdi]
0x1800198e5  mov     rcx, rdi
0x1800198e8  mov     rax, [rdx+10h]
0x1800198ec  call    _guard_dispatch_icall
0x1800198f1  mov     eax, r12d
0x1800198f4  mov     rbx, [rsp+50h+arg_8]
0x1800198fc  add     rsp, 50h
0x180019900  pop     r15
0x180019902  pop     r14
0x180019904  pop     r13
0x180019906  pop     r12
0x180019908  pop     rdi
0x180019909  pop     rsi
0x18001990a  pop     rbp
0x18001990b  retn
```
