# ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindProcessInVE(ulong,appv::shared::kernel::managed_unicode_string<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>> const &,kernel_std::shared_ptr<VirtualEnvironment<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>> &)

- ea: `0x180007b88`
- end: `0x180007d4c`
- name: `?FindProcessInVE@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@QEAAJKAEBV?$managed_unicode_string@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@@kernel@shared@appv@@AEAV?$shared_ptr@V?$VirtualEnvironment@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z`
- size: `452`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800054e8`
- `0x1800086a0`
- `0x1800099b4`
- `0x18000da60`

## callees

- `0x180005430`
- `0x180007b88`
- `0x18000c768`
- `0x18001bb30`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x180007c53`
- `ntoskrnl!ExReleaseResourceLite` at `0x180007d1a`
- `ntoskrnl!ExReleaseResourceLite` at `0x180007c53`
- `ntoskrnl!ExReleaseResourceLite` at `0x180007d1a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180007c5f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180007d26`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180007c5f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180007d26`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180007bce`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x180007bce`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180007bbb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180007bbb`
- `ntoskrnl!RtlCompareUnicodeString` at `0x180007c99`
- `ntoskrnl!RtlCompareUnicodeString` at `0x180007c99`

## pseudocode

```c
__int64 __fastcall ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::FindProcessInVE(
        __int64 a1,
        int a2,
        const UNICODE_STRING *a3,
        _QWORD *a4)
{
  bool v4; // bp
  volatile signed __int32 *v8; // rbx
  struct _ERESOURCE *v9; // rcx
  _QWORD *v11; // rbx
  _QWORD *v12; // rsi
  unsigned int v13; // esi
  volatile signed __int32 *v14; // rbx
  struct _ERESOURCE *v15; // rcx
  __int128 v16; // [rsp+20h] [rbp-38h] BYREF
  int v17; // [rsp+68h] [rbp+10h] BYREF

  v17 = a2;
  v4 = 0;
  if ( *(_QWORD *)(a1 + 16) )
  {
    KeEnterCriticalRegion();
    v4 = ExAcquireResourceSharedLite(*(PERESOURCE *)(a1 + 16), 1u) == 1;
  }
  v16 = 0;
  if ( (unsigned __int8)appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,unsigned long,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::find(
                          a1,
                          &v17,
                          &v16) )
  {
    v11 = *(_QWORD **)(v16 + 32);
    v12 = (_QWORD *)(v16 + 8);
    while ( v11 != v12 )
    {
      if ( !RtlCompareUnicodeString((PCUNICODE_STRING)(*(_QWORD *)(*v11 + 120LL) + 16LL), a3 + 1, 1u) )
      {
        *a4 = *v11;
        kernel_std::detail::shared_count::operator=(a4 + 1, v11 + 1);
        v13 = 0;
        goto LABEL_18;
      }
      v11 = (_QWORD *)v11[3];
    }
    v13 = -1073741772;
LABEL_18:
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
    if ( v4 )
    {
      v15 = *(struct _ERESOURCE **)(a1 + 16);
      if ( v15 )
      {
        ExReleaseResourceLite(v15);
        KeLeaveCriticalRegion();
      }
    }
    return v13;
  }
  else
  {
    v8 = (volatile signed __int32 *)*((_QWORD *)&v16 + 1);
    if ( *((_QWORD *)&v16 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v16 + 1) + 8LL), 0xFFFFFFFF) == 1 )
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
0x180007b88  mov     [rsp+arg_0], rbx
0x180007b8d  mov     [rsp+arg_10], rbp
0x180007b92  mov     [rsp+arg_8], edx
0x180007b96  push    rsi
0x180007b97  push    rdi
0x180007b98  push    r12
0x180007b9a  push    r14
0x180007b9c  push    r15
0x180007b9e  sub     rsp, 30h
0x180007ba2  xor     bpl, bpl
0x180007ba5  mov     rdi, r9
0x180007ba8  cmp     qword ptr [rcx+10h], 0
0x180007bad  mov     r15, r8
0x180007bb0  mov     r14, rcx
0x180007bb3  mov     r12d, 1
0x180007bb9  jz      short loc_180007BE5
0x180007bbb  call    cs:__imp_KeEnterCriticalRegion
0x180007bc2  nop     dword ptr [rax+rax+00h]
0x180007bc7  mov     rcx, [r14+10h]; Resource
0x180007bcb  mov     dl, r12b; Wait
0x180007bce  call    cs:__imp_ExAcquireResourceSharedLite
0x180007bd5  nop     dword ptr [rax+rax+00h]
0x180007bda  cmp     al, r12b
0x180007bdd  movzx   ebp, bpl
0x180007be1  cmovz   ebp, r12d
0x180007be5  xorps   xmm0, xmm0
0x180007be8  lea     r8, [rsp+58h+var_38]
0x180007bed  lea     rdx, [rsp+58h+arg_8]
0x180007bf2  mov     rcx, r14
0x180007bf5  movdqu  [rsp+58h+var_38], xmm0
0x180007bfb  call    ?find@?$indexed_avl_tree@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uless_predicate@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@KV?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@kernel@shared@appv@@QEAA_NAEBKAEAV?$shared_ptr@UProcessTrackerValue@?$ProcessTracker@U?$km_allocator@Uvemgr_pool_info@vemgr@@@kernel@shared@appv@@Uvemgr_pool_info@vemgr@@@@@kernel_std@@@Z; appv::shared::kernel::indexed_avl_tree<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::less_predicate,ulong,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue>>::find(ulong const &,kernel_std::shared_ptr<ProcessTracker<appv::shared::kernel::km_allocator<vemgr::vemgr_pool_info>,vemgr::vemgr_pool_info>::ProcessTrackerValue> &)
0x180007c00  test    al, al
0x180007c02  jnz     short loc_180007C75
0x180007c04  mov     rbx, qword ptr [rsp+58h+var_38+8]
0x180007c09  test    rbx, rbx
0x180007c0c  jz      short loc_180007C45
0x180007c0e  or      edi, 0FFFFFFFFh
0x180007c11  mov     eax, edi
0x180007c13  lock xadd [rbx+8], eax
0x180007c18  add     eax, edi
0x180007c1a  jnz     short loc_180007C45
0x180007c1c  mov     rax, [rbx]
0x180007c1f  mov     rcx, rbx
0x180007c22  mov     rax, [rax+8]
0x180007c26  call    _guard_dispatch_icall
0x180007c2b  mov     eax, edi
0x180007c2d  lock xadd [rbx+0Ch], eax
0x180007c32  add     eax, edi
0x180007c34  jnz     short loc_180007C45
0x180007c36  mov     rax, [rbx]
0x180007c39  mov     rcx, rbx
0x180007c3c  mov     rax, [rax+10h]
0x180007c40  call    _guard_dispatch_icall
0x180007c45  test    bpl, bpl
0x180007c48  jz      short loc_180007C6B
0x180007c4a  mov     rcx, [r14+10h]; Resource
0x180007c4e  test    rcx, rcx
0x180007c51  jz      short loc_180007C6B
0x180007c53  call    cs:__imp_ExReleaseResourceLite
0x180007c5a  nop     dword ptr [rax+rax+00h]
0x180007c5f  call    cs:__imp_KeLeaveCriticalRegion
0x180007c66  nop     dword ptr [rax+rax+00h]
0x180007c6b  mov     eax, 0C0000034h
0x180007c70  jmp     loc_180007D34
0x180007c75  mov     rax, qword ptr [rsp+58h+var_38]
0x180007c7a  mov     rbx, [rax+20h]
0x180007c7e  lea     rsi, [rax+8]
0x180007c82  cmp     rbx, rsi
0x180007c85  jz      short loc_180007CC6
0x180007c87  mov     rax, [rbx]
0x180007c8a  lea     rdx, [r15+10h]; String2
0x180007c8e  mov     r8b, r12b; CaseInSensitive
0x180007c91  mov     rcx, [rax+78h]
0x180007c95  add     rcx, 10h; String1
0x180007c99  call    cs:__imp_RtlCompareUnicodeString
0x180007ca0  nop     dword ptr [rax+rax+00h]
0x180007ca5  test    eax, eax
0x180007ca7  jz      short loc_180007CAF
0x180007ca9  mov     rbx, [rbx+18h]
0x180007cad  jmp     short loc_180007C82
0x180007caf  mov     rax, [rbx]
0x180007cb2  lea     rdx, [rbx+8]
0x180007cb6  lea     rcx, [rdi+8]
0x180007cba  mov     [rdi], rax
0x180007cbd  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x180007cc2  xor     esi, esi
0x180007cc4  jmp     short loc_180007CCB
0x180007cc6  mov     esi, 0C0000034h
0x180007ccb  mov     rbx, qword ptr [rsp+58h+var_38+8]
0x180007cd0  test    rbx, rbx
0x180007cd3  jz      short loc_180007D0C
0x180007cd5  or      edi, 0FFFFFFFFh
0x180007cd8  mov     eax, edi
0x180007cda  lock xadd [rbx+8], eax
0x180007cdf  add     eax, edi
0x180007ce1  jnz     short loc_180007D0C
0x180007ce3  mov     rax, [rbx]
0x180007ce6  mov     rcx, rbx
0x180007ce9  mov     rax, [rax+8]
0x180007ced  call    _guard_dispatch_icall
0x180007cf2  mov     eax, edi
0x180007cf4  lock xadd [rbx+0Ch], eax
0x180007cf9  add     eax, edi
0x180007cfb  jnz     short loc_180007D0C
0x180007cfd  mov     rax, [rbx]
0x180007d00  mov     rcx, rbx
0x180007d03  mov     rax, [rax+10h]
0x180007d07  call    _guard_dispatch_icall
0x180007d0c  test    bpl, bpl
0x180007d0f  jz      short loc_180007D32
0x180007d11  mov     rcx, [r14+10h]; Resource
0x180007d15  test    rcx, rcx
0x180007d18  jz      short loc_180007D32
0x180007d1a  call    cs:__imp_ExReleaseResourceLite
0x180007d21  nop     dword ptr [rax+rax+00h]
0x180007d26  call    cs:__imp_KeLeaveCriticalRegion
0x180007d2d  nop     dword ptr [rax+rax+00h]
0x180007d32  mov     eax, esi
0x180007d34  mov     rbx, [rsp+58h+arg_0]
0x180007d39  mov     rbp, [rsp+58h+arg_10]
0x180007d3e  add     rsp, 30h
0x180007d42  pop     r15
0x180007d44  pop     r14
0x180007d46  pop     r12
0x180007d48  pop     rdi
0x180007d49  pop     rsi
0x180007d4a  retn
```
