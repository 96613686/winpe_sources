# ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessReference(ulong,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &)

- ea: `0x180008b90`
- end: `0x180008dce`
- name: `?RemoveProcessReference@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJKAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@@Z`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008dd4`

## callees

- `0x180008b90`
- `0x18000c5f4`
- `0x18000c768`
- `0x18000e610`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x180008cc7`
- `ntoskrnl!ExReleaseResourceLite` at `0x180008d37`
- `ntoskrnl!ExReleaseResourceLite` at `0x180008da1`
- `ntoskrnl!ExReleaseResourceLite` at `0x180008cc7`
- `ntoskrnl!ExReleaseResourceLite` at `0x180008d37`
- `ntoskrnl!ExReleaseResourceLite` at `0x180008da1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008cd3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008d43`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008dad`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008cd3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008d43`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180008dad`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180008bcc`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x180008bcc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180008bba`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180008bba`
- `ntoskrnl!RtlCompareUnicodeString` at `0x180008c3c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x180008c3c`

## pseudocode

```c
__int64 __fastcall ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::RemoveProcessReference(
        __int64 a1,
        int a2,
        const UNICODE_STRING *a3)
{
  bool v3; // r14
  _DWORD *v6; // rdi
  _QWORD *v7; // r15
  _QWORD *v8; // rbx
  volatile signed __int32 *v9; // rdi
  struct _ERESOURCE *v10; // rcx
  volatile signed __int32 *v12; // rdi
  struct _ERESOURCE *v13; // rcx
  volatile signed __int32 *v14; // rdi
  struct _ERESOURCE *v15; // rcx
  __int128 v16; // [rsp+20h] [rbp-10h] BYREF
  _QWORD *v17; // [rsp+70h] [rbp+40h] BYREF
  int v18; // [rsp+78h] [rbp+48h] BYREF
  char v19; // [rsp+88h] [rbp+58h] BYREF

  v18 = a2;
  v3 = 0;
  if ( *(_QWORD *)(a1 + 16) )
  {
    KeEnterCriticalRegion();
    v3 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 16), 1u) == 1;
  }
  v16 = 0;
  if ( (unsigned __int8)appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,unsigned long,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::find(
                          a1,
                          &v18,
                          &v16) )
  {
    v6 = (_DWORD *)v16;
    v7 = (_QWORD *)(v16 + 8);
    v8 = *(_QWORD **)(v16 + 32);
    if ( v8 != (_QWORD *)(v16 + 8) )
    {
      if ( !*(_BYTE *)(v16 + 40) )
        goto LABEL_7;
      while ( 1 )
      {
        v8 = (_QWORD *)v8[3];
LABEL_7:
        if ( v8 == v7 )
          break;
        if ( !RtlCompareUnicodeString((PCUNICODE_STRING)(*(_QWORD *)(*v8 + 120LL) + 16LL), a3 + 1, 1u) )
        {
          v17 = v8;
          appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(
            v6,
            &v19,
            &v17);
          if ( *v6
            || (unsigned __int8)appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,unsigned long,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::remove(
                                  a1,
                                  &v18) )
          {
            v12 = (volatile signed __int32 *)*((_QWORD *)&v16 + 1);
            if ( *((_QWORD *)&v16 + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v16 + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
                if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 16LL))(v12);
              }
            }
            if ( v3 )
            {
              v13 = *(struct _ERESOURCE **)(a1 + 16);
              if ( v13 )
              {
                ExReleaseResourceLite(v13);
                KeLeaveCriticalRegion();
              }
            }
            return 0;
          }
          else
          {
            v9 = (volatile signed __int32 *)*((_QWORD *)&v16 + 1);
            if ( *((_QWORD *)&v16 + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v16 + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
                if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
              }
            }
            if ( v3 )
            {
              v10 = *(struct _ERESOURCE **)(a1 + 16);
              if ( v10 )
              {
                ExReleaseResourceLite(v10);
                KeLeaveCriticalRegion();
              }
            }
            return 3221225701LL;
          }
        }
      }
    }
  }
  v14 = (volatile signed __int32 *)*((_QWORD *)&v16 + 1);
  if ( *((_QWORD *)&v16 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v16 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
  if ( v3 )
  {
    v15 = *(struct _ERESOURCE **)(a1 + 16);
    if ( v15 )
    {
      ExReleaseResourceLite(v15);
      KeLeaveCriticalRegion();
    }
  }
  return 3221225524LL;
}

```

## disassembly

```asm
0x180008b90  mov     [rsp-38h+arg_8], edx
0x180008b94  push    rbp
0x180008b95  push    rbx
0x180008b96  push    rsi
0x180008b97  push    rdi
0x180008b98  push    r13
0x180008b9a  push    r14
0x180008b9c  push    r15
0x180008b9e  mov     rbp, rsp
0x180008ba1  sub     rsp, 30h
0x180008ba5  xor     r14b, r14b
0x180008ba8  mov     r13, r8
0x180008bab  cmp     qword ptr [rcx+10h], 0
0x180008bb0  mov     rsi, rcx
0x180008bb3  mov     ebx, 1
0x180008bb8  jz      short loc_180008BE2
0x180008bba  call    cs:__imp_KeEnterCriticalRegion
0x180008bc1  nop     dword ptr [rax+rax+00h]
0x180008bc6  mov     rcx, [rsi+10h]; Resource
0x180008bca  mov     dl, bl; Wait
0x180008bcc  call    cs:__imp_ExAcquireResourceExclusiveLite
0x180008bd3  nop     dword ptr [rax+rax+00h]
0x180008bd8  cmp     al, bl
0x180008bda  movzx   r14d, r14b
0x180008bde  cmovz   r14d, ebx
0x180008be2  xorps   xmm0, xmm0
0x180008be5  lea     r8, [rbp+var_10]
0x180008be9  lea     rdx, [rbp+arg_8]
0x180008bed  mov     rcx, rsi
0x180008bf0  movdqu  [rbp+var_10], xmm0
0x180008bf5  call    ?find@?$indexed_avl_tree@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uless_predicate@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@KV?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@QEAA_NAEBKAEAV?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,ulong,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::find(ulong const &,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue> &)
0x180008bfa  test    al, al
0x180008bfc  jz      loc_180008D53
0x180008c02  mov     rdi, qword ptr [rbp+var_10]
0x180008c06  lea     r15, [rdi+8]
0x180008c0a  mov     rbx, [r15+18h]
0x180008c0e  cmp     rbx, r15
0x180008c11  jz      loc_180008D53
0x180008c17  cmp     byte ptr [rdi+28h], 0
0x180008c1b  jz      short loc_180008C21
0x180008c1d  mov     rbx, [rbx+18h]
0x180008c21  cmp     rbx, r15
0x180008c24  jz      loc_180008D53
0x180008c2a  mov     rax, [rbx]
0x180008c2d  lea     rdx, [r13+10h]; String2
0x180008c31  mov     r8b, 1; CaseInSensitive
0x180008c34  mov     rcx, [rax+78h]
0x180008c38  add     rcx, 10h; String1
0x180008c3c  call    cs:__imp_RtlCompareUnicodeString
0x180008c43  nop     dword ptr [rax+rax+00h]
0x180008c48  test    eax, eax
0x180008c4a  jnz     short loc_180008C1D
0x180008c4c  lea     r8, [rbp+arg_0]
0x180008c50  mov     [rbp+arg_0], rbx
0x180008c54  lea     rdx, [rbp+arg_18]
0x180008c58  mov     rcx, rdi
0x180008c5b  call    ?erase@?$doubly_linked_list@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@QEAA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@VCountedVE@?$VirtualEnvironmentTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@@234@V5234@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>,vemgr::vemgr_pool_info>::erase(appv::shared::kernel::bidirectional_list_iterator<appv::shared::kernel::dl_node_t<kernel_std::shared_ptr<VirtualEnvironmentTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::CountedVE>>>)
0x180008c60  cmp     dword ptr [rdi], 0
0x180008c63  jnz     loc_180008CE9
0x180008c69  lea     rdx, [rbp+arg_8]
0x180008c6d  mov     rcx, rsi
0x180008c70  call    ?remove@?$indexed_avl_tree@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uless_predicate@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@KV?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@QEAA_NAEBK@Z; appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,ulong,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::remove(ulong const &)
0x180008c75  test    al, al
0x180008c77  jnz     short loc_180008CE9
0x180008c79  mov     rdi, qword ptr [rbp+var_10+8]
0x180008c7d  test    rdi, rdi
0x180008c80  jz      short loc_180008CB9
0x180008c82  or      ebx, 0FFFFFFFFh
0x180008c85  mov     eax, ebx
0x180008c87  lock xadd [rdi+8], eax
0x180008c8c  add     eax, ebx
0x180008c8e  jnz     short loc_180008CB9
0x180008c90  mov     rax, [rdi]
0x180008c93  mov     rcx, rdi
0x180008c96  mov     rax, [rax+8]
0x180008c9a  call    _guard_dispatch_icall
0x180008c9f  mov     eax, ebx
0x180008ca1  lock xadd [rdi+0Ch], eax
0x180008ca6  add     eax, ebx
0x180008ca8  jnz     short loc_180008CB9
0x180008caa  mov     rax, [rdi]
0x180008cad  mov     rcx, rdi
0x180008cb0  mov     rax, [rax+10h]
0x180008cb4  call    _guard_dispatch_icall
0x180008cb9  test    r14b, r14b
0x180008cbc  jz      short loc_180008CDF
0x180008cbe  mov     rcx, [rsi+10h]; Resource
0x180008cc2  test    rcx, rcx
0x180008cc5  jz      short loc_180008CDF
0x180008cc7  call    cs:__imp_ExReleaseResourceLite
0x180008cce  nop     dword ptr [rax+rax+00h]
0x180008cd3  call    cs:__imp_KeLeaveCriticalRegion
0x180008cda  nop     dword ptr [rax+rax+00h]
0x180008cdf  mov     eax, 0C00000E5h
0x180008ce4  jmp     loc_180008DBE
0x180008ce9  mov     rdi, qword ptr [rbp+var_10+8]
0x180008ced  test    rdi, rdi
0x180008cf0  jz      short loc_180008D29
0x180008cf2  or      ebx, 0FFFFFFFFh
0x180008cf5  mov     eax, ebx
0x180008cf7  lock xadd [rdi+8], eax
0x180008cfc  add     eax, ebx
0x180008cfe  jnz     short loc_180008D29
0x180008d00  mov     rax, [rdi]
0x180008d03  mov     rcx, rdi
0x180008d06  mov     rax, [rax+8]
0x180008d0a  call    _guard_dispatch_icall
0x180008d0f  mov     eax, ebx
0x180008d11  lock xadd [rdi+0Ch], eax
0x180008d16  add     eax, ebx
0x180008d18  jnz     short loc_180008D29
0x180008d1a  mov     rax, [rdi]
0x180008d1d  mov     rcx, rdi
0x180008d20  mov     rax, [rax+10h]
0x180008d24  call    _guard_dispatch_icall
0x180008d29  test    r14b, r14b
0x180008d2c  jz      short loc_180008D4F
0x180008d2e  mov     rcx, [rsi+10h]; Resource
0x180008d32  test    rcx, rcx
0x180008d35  jz      short loc_180008D4F
0x180008d37  call    cs:__imp_ExReleaseResourceLite
0x180008d3e  nop     dword ptr [rax+rax+00h]
0x180008d43  call    cs:__imp_KeLeaveCriticalRegion
0x180008d4a  nop     dword ptr [rax+rax+00h]
0x180008d4f  xor     eax, eax
0x180008d51  jmp     short loc_180008DBE
0x180008d53  mov     rdi, qword ptr [rbp+var_10+8]
0x180008d57  test    rdi, rdi
0x180008d5a  jz      short loc_180008D93
0x180008d5c  or      ebx, 0FFFFFFFFh
0x180008d5f  mov     eax, ebx
0x180008d61  lock xadd [rdi+8], eax
0x180008d66  add     eax, ebx
0x180008d68  jnz     short loc_180008D93
0x180008d6a  mov     rax, [rdi]
0x180008d6d  mov     rcx, rdi
0x180008d70  mov     rax, [rax+8]
0x180008d74  call    _guard_dispatch_icall
0x180008d79  mov     eax, ebx
0x180008d7b  lock xadd [rdi+0Ch], eax
0x180008d80  add     eax, ebx
0x180008d82  jnz     short loc_180008D93
0x180008d84  mov     rax, [rdi]
0x180008d87  mov     rcx, rdi
0x180008d8a  mov     rax, [rax+10h]
0x180008d8e  call    _guard_dispatch_icall
0x180008d93  test    r14b, r14b
0x180008d96  jz      short loc_180008DB9
0x180008d98  mov     rcx, [rsi+10h]; Resource
0x180008d9c  test    rcx, rcx
0x180008d9f  jz      short loc_180008DB9
0x180008da1  call    cs:__imp_ExReleaseResourceLite
0x180008da8  nop     dword ptr [rax+rax+00h]
0x180008dad  call    cs:__imp_KeLeaveCriticalRegion
0x180008db4  nop     dword ptr [rax+rax+00h]
0x180008db9  mov     eax, 0C0000034h
0x180008dbe  add     rsp, 30h
0x180008dc2  pop     r15
0x180008dc4  pop     r14
0x180008dc6  pop     r13
0x180008dc8  pop     rdi
0x180008dc9  pop     rsi
0x180008dca  pop     rbx
0x180008dcb  pop     rbp
0x180008dcc  retn
```
