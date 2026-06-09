# ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddJitvThread(ulong,ulong,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)

- ea: `0x18000566c`
- end: `0x180005889`
- name: `?AddJitvThread@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJKKAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z`
- size: `541`
- prototype: `__int64 __fastcall(__int64, int, int, const UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000da60`

## callees

- `0x180005430`
- `0x18000566c`
- `0x18000c768`
- `0x18000d63c`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x180005733`
- `ntoskrnl!ExReleaseResourceLite` at `0x180005856`
- `ntoskrnl!ExReleaseResourceLite` at `0x180005733`
- `ntoskrnl!ExReleaseResourceLite` at `0x180005856`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000573f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180005862`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000573f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180005862`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800056b2`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1800056b2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000569f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000569f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18000578a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18000578a`

## pseudocode

```c
__int64 __fastcall ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::AddJitvThread(
        __int64 a1,
        int a2,
        int a3,
        const UNICODE_STRING *a4)
{
  bool v4; // r14
  volatile signed __int32 *v8; // rbx
  struct _ERESOURCE *v9; // rcx
  __int64 v11; // rsi
  __int64 v12; // rbx
  __int64 v13; // r12
  unsigned int v14; // eax
  volatile signed __int32 *v15; // rbx
  unsigned int v16; // esi
  volatile signed __int32 *v17; // rbx
  struct _ERESOURCE *v18; // rcx
  __int128 v19; // [rsp+20h] [rbp-20h] BYREF
  __int128 v20; // [rsp+30h] [rbp-10h] BYREF
  int v21; // [rsp+80h] [rbp+40h] BYREF
  int v22; // [rsp+88h] [rbp+48h] BYREF

  v22 = a2;
  v4 = 0;
  if ( *(_QWORD *)(a1 + 16) )
  {
    KeEnterCriticalRegion();
    v4 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 16), 1u) == 1;
  }
  v20 = 0;
  if ( (unsigned __int8)appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,unsigned long,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::find(
                          a1,
                          &v22,
                          &v20) )
  {
    v11 = v20;
    v21 = a3;
    v19 = 0;
    v12 = *(_QWORD *)(v20 + 32);
    v13 = v20 + 8;
    while ( 1 )
    {
      if ( v12 == v13 )
      {
        v16 = -1073741772;
        goto LABEL_21;
      }
      if ( !RtlCompareUnicodeString((PCUNICODE_STRING)(*(_QWORD *)(*(_QWORD *)v12 + 120LL) + 16LL), a4 + 1, 1u) )
        break;
      v12 = *(_QWORD *)(v12 + 24);
    }
    *(_QWORD *)&v19 = *(_QWORD *)v12;
    kernel_std::detail::shared_count::operator=(
      (volatile signed __int32 **)&v19 + 1,
      (volatile signed __int32 **)(v12 + 8));
    v14 = appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,unsigned long,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>>::insert(
            v11 + 48,
            &v21,
            &v19);
    v15 = (volatile signed __int32 *)*((_QWORD *)&v19 + 1);
    v16 = v14;
    if ( *((_QWORD *)&v19 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v19 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 16LL))(v15);
      }
    }
LABEL_21:
    v17 = (volatile signed __int32 *)*((_QWORD *)&v20 + 1);
    if ( *((_QWORD *)&v20 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v20 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 16LL))(v17);
      }
    }
    if ( v4 )
    {
      v18 = *(struct _ERESOURCE **)(a1 + 16);
      if ( v18 )
      {
        ExReleaseResourceLite(v18);
        KeLeaveCriticalRegion();
      }
    }
    return v16;
  }
  else
  {
    v8 = (volatile signed __int32 *)*((_QWORD *)&v20 + 1);
    if ( *((_QWORD *)&v20 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v20 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 16LL))(v8);
      }
    }
    if ( v4 )
    {
      v9 = *(struct _ERESOURCE **)(a1 + 16);
      if ( v9 )
      {
        ExReleaseResourceLite(v9);
        KeLeaveCriticalRegion();
      }
    }
    return 3221225524LL;
  }
}

```

## disassembly

```asm
0x18000566c  mov     [rsp-38h+arg_10], rbx
0x180005671  mov     [rsp-38h+arg_8], edx
0x180005675  push    rbp
0x180005676  push    rsi
0x180005677  push    rdi
0x180005678  push    r12
0x18000567a  push    r13
0x18000567c  push    r14
0x18000567e  push    r15
0x180005680  mov     rbp, rsp
0x180005683  sub     rsp, 40h
0x180005687  xor     r14b, r14b
0x18000568a  mov     r13, r9
0x18000568d  cmp     qword ptr [rcx+10h], 0
0x180005692  mov     ebx, r8d
0x180005695  mov     r15, rcx
0x180005698  mov     edi, 1
0x18000569d  jz      short loc_1800056C9
0x18000569f  call    cs:__imp_KeEnterCriticalRegion
0x1800056a6  nop     dword ptr [rax+rax+00h]
0x1800056ab  mov     rcx, [r15+10h]; Resource
0x1800056af  mov     dl, dil; Wait
0x1800056b2  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1800056b9  nop     dword ptr [rax+rax+00h]
0x1800056be  cmp     al, dil
0x1800056c1  movzx   r14d, r14b
0x1800056c5  cmovz   r14d, edi
0x1800056c9  xorps   xmm0, xmm0
0x1800056cc  lea     r8, [rbp+var_10]
0x1800056d0  lea     rdx, [rbp+arg_8]
0x1800056d4  mov     rcx, r15
0x1800056d7  movdqu  [rbp+var_10], xmm0
0x1800056dc  call    ?find@?$indexed_avl_tree@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uless_predicate@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@KV?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@QEAA_NAEBKAEAV?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,ulong,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::find(ulong const &,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue> &)
0x1800056e1  test    al, al
0x1800056e3  jnz     short loc_180005755
0x1800056e5  mov     rbx, qword ptr [rbp+var_10+8]
0x1800056e9  test    rbx, rbx
0x1800056ec  jz      short loc_180005725
0x1800056ee  or      edi, 0FFFFFFFFh
0x1800056f1  mov     eax, edi
0x1800056f3  lock xadd [rbx+8], eax
0x1800056f8  add     eax, edi
0x1800056fa  jnz     short loc_180005725
0x1800056fc  mov     rax, [rbx]
0x1800056ff  mov     rcx, rbx
0x180005702  mov     rax, [rax+8]
0x180005706  call    _guard_dispatch_icall
0x18000570b  mov     eax, edi
0x18000570d  lock xadd [rbx+0Ch], eax
0x180005712  add     eax, edi
0x180005714  jnz     short loc_180005725
0x180005716  mov     rax, [rbx]
0x180005719  mov     rcx, rbx
0x18000571c  mov     rax, [rax+10h]
0x180005720  call    _guard_dispatch_icall
0x180005725  test    r14b, r14b
0x180005728  jz      short loc_18000574B
0x18000572a  mov     rcx, [r15+10h]; Resource
0x18000572e  test    rcx, rcx
0x180005731  jz      short loc_18000574B
0x180005733  call    cs:__imp_ExReleaseResourceLite
0x18000573a  nop     dword ptr [rax+rax+00h]
0x18000573f  call    cs:__imp_KeLeaveCriticalRegion
0x180005746  nop     dword ptr [rax+rax+00h]
0x18000574b  mov     eax, 0C0000034h
0x180005750  jmp     loc_180005870
0x180005755  mov     rsi, qword ptr [rbp+var_10]
0x180005759  xorps   xmm0, xmm0
0x18000575c  mov     [rbp+arg_0], ebx
0x18000575f  movdqu  [rbp+var_20], xmm0
0x180005764  mov     rbx, [rsi+20h]
0x180005768  lea     r12, [rsi+8]
0x18000576c  or      edi, 0FFFFFFFFh
0x18000576f  cmp     rbx, r12
0x180005772  jz      loc_180005806
0x180005778  mov     rax, [rbx]
0x18000577b  lea     rdx, [r13+10h]; String2
0x18000577f  mov     r8b, 1; CaseInSensitive
0x180005782  mov     rcx, [rax+78h]
0x180005786  add     rcx, 10h; String1
0x18000578a  call    cs:__imp_RtlCompareUnicodeString
0x180005791  nop     dword ptr [rax+rax+00h]
0x180005796  test    eax, eax
0x180005798  jz      short loc_1800057A0
0x18000579a  mov     rbx, [rbx+18h]
0x18000579e  jmp     short loc_18000576C
0x1800057a0  mov     rax, [rbx]
0x1800057a3  lea     rdx, [rbx+8]
0x1800057a7  lea     rcx, [rbp+var_20+8]
0x1800057ab  mov     qword ptr [rbp+var_20], rax
0x1800057af  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x1800057b4  lea     rcx, [rsi+30h]
0x1800057b8  lea     r8, [rbp+var_20]
0x1800057bc  lea     rdx, [rbp+arg_0]
0x1800057c0  call    ?insert@?$indexed_avl_tree@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uless_predicate@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@KV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@QEAAJAEBKAEBV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,ulong,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>>>::insert(ulong const &,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> const &)
0x1800057c5  mov     rbx, qword ptr [rbp+var_20+8]
0x1800057c9  mov     esi, eax
0x1800057cb  test    rbx, rbx
0x1800057ce  jz      short loc_18000580B
0x1800057d0  mov     eax, edi
0x1800057d2  lock xadd [rbx+8], eax
0x1800057d7  add     eax, edi
0x1800057d9  jnz     short loc_18000580B
0x1800057db  mov     rax, [rbx]
0x1800057de  mov     rcx, rbx
0x1800057e1  mov     rax, [rax+8]
0x1800057e5  call    _guard_dispatch_icall
0x1800057ea  mov     eax, edi
0x1800057ec  lock xadd [rbx+0Ch], eax
0x1800057f1  add     eax, edi
0x1800057f3  jnz     short loc_18000580B
0x1800057f5  mov     rax, [rbx]
0x1800057f8  mov     rcx, rbx
0x1800057fb  mov     rax, [rax+10h]
0x1800057ff  call    _guard_dispatch_icall
0x180005804  jmp     short loc_18000580B
0x180005806  mov     esi, 0C0000034h
0x18000580b  mov     rbx, qword ptr [rbp+var_10+8]
0x18000580f  test    rbx, rbx
0x180005812  jz      short loc_180005848
0x180005814  mov     eax, edi
0x180005816  lock xadd [rbx+8], eax
0x18000581b  add     eax, edi
0x18000581d  jnz     short loc_180005848
0x18000581f  mov     rax, [rbx]
0x180005822  mov     rcx, rbx
0x180005825  mov     rax, [rax+8]
0x180005829  call    _guard_dispatch_icall
0x18000582e  mov     eax, edi
0x180005830  lock xadd [rbx+0Ch], eax
0x180005835  add     eax, edi
0x180005837  jnz     short loc_180005848
0x180005839  mov     rax, [rbx]
0x18000583c  mov     rcx, rbx
0x18000583f  mov     rax, [rax+10h]
0x180005843  call    _guard_dispatch_icall
0x180005848  test    r14b, r14b
0x18000584b  jz      short loc_18000586E
0x18000584d  mov     rcx, [r15+10h]; Resource
0x180005851  test    rcx, rcx
0x180005854  jz      short loc_18000586E
0x180005856  call    cs:__imp_ExReleaseResourceLite
0x18000585d  nop     dword ptr [rax+rax+00h]
0x180005862  call    cs:__imp_KeLeaveCriticalRegion
0x180005869  nop     dword ptr [rax+rax+00h]
0x18000586e  mov     eax, esi
0x180005870  mov     rbx, [rsp+40h+arg_10]
0x180005878  add     rsp, 40h
0x18000587c  pop     r15
0x18000587e  pop     r14
0x180005880  pop     r13
0x180005882  pop     r12
0x180005884  pop     rdi
0x180005885  pop     rsi
0x180005886  pop     rbp
0x180005887  retn
```
