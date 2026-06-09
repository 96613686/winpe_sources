# Streaming::MDLCache::GetFreeMdl(ulong,kernel_std::shared_ptr<appv::shared::kernel::kmdl> &)

- ea: `0x140010270`
- end: `0x1400105cf`
- name: `?GetFreeMdl@MDLCache@Streaming@@QEAAJKAEAV?$shared_ptr@Vkmdl@kernel@shared@appv@@@kernel_std@@@Z`
- size: `863`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140011154`

## callees

- `0x140003bd8`
- `0x14000fd90`
- `0x14000fe80`
- `0x140010188`
- `0x140010270`
- `0x1400105d8`
- `0x140010a10`
- `0x140010b08`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400102de`
- `ntoskrnl!ExAllocatePool2` at `0x14001034d`
- `ntoskrnl!ExAllocatePool2` at `0x1400103cf`
- `ntoskrnl!ExAllocatePool2` at `0x1400102de`
- `ntoskrnl!ExAllocatePool2` at `0x14001034d`
- `ntoskrnl!ExAllocatePool2` at `0x1400103cf`

## pseudocode

```c
__int64 __fastcall Streaming::MDLCache::GetFreeMdl(__int64 a1, unsigned int a2, __int64 a3)
{
  PVOID v3; // r13
  __int64 v5; // rbx
  struct _PAGED_LOOKASIDE_LIST *v6; // rcx
  __int64 Pool2; // rax
  appv::shared::kernel::kmdl *v9; // r15
  volatile signed __int32 *v10; // rdi
  __int64 v11; // rax
  int v12; // esi
  volatile signed __int32 *v13; // rdi
  __int64 v14; // rax
  volatile signed __int32 *v15; // rsi
  int v16; // r12d
  volatile signed __int32 *v17; // rsi
  volatile signed __int32 *v18; // rsi
  appv::shared::kernel::kmdl *v19; // [rsp+20h] [rbp-28h] BYREF
  volatile signed __int32 *v20; // [rsp+28h] [rbp-20h] BYREF
  __int64 v21; // [rsp+30h] [rbp-18h] BYREF
  volatile signed __int32 *v22; // [rsp+38h] [rbp-10h]

  v3 = Streaming::staging_operations::gMDLCache;
  v5 = a2;
  if ( a2 <= 0x1000 )
  {
    v6 = (struct _PAGED_LOOKASIDE_LIST *)Streaming::staging_operations::gMDLCache;
    return Streaming::MDLListCache::GetMDL(v6);
  }
  if ( a2 <= 0x20000 )
  {
    v6 = (struct _PAGED_LOOKASIDE_LIST *)((char *)Streaming::staging_operations::gMDLCache + 256);
    return Streaming::MDLListCache::GetMDL(v6);
  }
  if ( a2 <= 0x100000 )
  {
    v6 = (struct _PAGED_LOOKASIDE_LIST *)((char *)Streaming::staging_operations::gMDLCache + 512);
    return Streaming::MDLListCache::GetMDL(v6);
  }
  Pool2 = ExAllocatePool2(256, 64, 1919772275);
  if ( Pool2 )
  {
    *(_BYTE *)Pool2 = 0;
    *(_QWORD *)(Pool2 + 8) = 0;
    *(_QWORD *)(Pool2 + 16) = 0;
    *(_QWORD *)(Pool2 + 24) = 0;
    *(_QWORD *)(Pool2 + 32) = 0;
    *(_DWORD *)(Pool2 + 48) = 0;
    *(_QWORD *)(Pool2 + 56) = 0;
  }
  else
  {
    Pool2 = 0;
  }
  kernel_std::shared_ptr<appv::shared::kernel::kmdl>::shared_ptr<appv::shared::kernel::kmdl>(&v19, Pool2);
  v9 = v19;
  if ( !v19 )
  {
    v10 = v20;
    if ( !v20 )
      return 3221225626LL;
LABEL_33:
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return 3221225626LL;
  }
  appv::shared::kernel::kmdl::close(v19);
  v11 = ExAllocatePool2(256, v5, 1919772275);
  *((_QWORD *)v9 + 3) = v11;
  if ( !v11 )
  {
    v12 = -1073741670;
    goto LABEL_17;
  }
  *((_DWORD *)v9 + 12) = v5;
  v12 = appv::shared::kernel::kmdl::Lock(v9);
  if ( v12 < 0 )
  {
LABEL_17:
    v13 = v20;
    if ( v20 )
    {
      if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 16LL))(v13);
      }
    }
    return (unsigned int)v12;
  }
  v14 = ExAllocatePool2(256, 24, 1919772275);
  v10 = v20;
  if ( v14 )
  {
    *(_QWORD *)v14 = v9;
    *(_QWORD *)(v14 + 8) = v10;
    if ( v10 )
      _InterlockedIncrement(v10 + 2);
    *(_BYTE *)(v14 + 16) = 1;
  }
  else
  {
    v14 = 0;
  }
  kernel_std::shared_ptr<Streaming::MDLEntry>::shared_ptr<Streaming::MDLEntry>(&v21, v14);
  if ( !v21 )
  {
    v15 = v22;
    if ( v22 )
    {
      if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 16LL))(v15);
      }
    }
    if ( !v10 )
      return 3221225626LL;
    goto LABEL_33;
  }
  v16 = Streaming::MDLList::AddItem((__int64)v3 + 768, &v21);
  if ( v16 >= 0 )
  {
    *(_QWORD *)a3 = v9;
    kernel_std::detail::shared_count::operator=((volatile signed __int32 **)(a3 + 8), &v20);
    v18 = v22;
    if ( v22 )
    {
      if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 16LL))(v18);
      }
    }
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 16LL))(v10);
      }
    }
    return 0;
  }
  else
  {
    v17 = v22;
    if ( v22 )
    {
      if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 16LL))(v17);
      }
    }
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 16LL))(v10);
      }
    }
    return (unsigned int)v16;
  }
}

```

## disassembly

```asm
0x140010270  push    rbp
0x140010272  push    rbx
0x140010273  push    rsi
0x140010274  push    rdi
0x140010275  push    r12
0x140010277  push    r13
0x140010279  push    r14
0x14001027b  push    r15
0x14001027d  mov     rbp, rsp
0x140010280  sub     rsp, 48h
0x140010284  mov     r13, cs:?gMDLCache@staging_operations@Streaming@@3PEAVMDLCache@2@EA; Streaming::MDLCache * Streaming::staging_operations::gMDLCache
0x14001028b  mov     r14, r8
0x14001028e  mov     ebx, edx
0x140010290  cmp     edx, 1000h
0x140010296  ja      short loc_1400102A8
0x140010298  mov     rcx, r13; Lookaside
0x14001029b  mov     rdx, r14
0x14001029e  call    ?GetMDL@MDLListCache@Streaming@@QEAAJAEAV?$shared_ptr@Vkmdl@kernel@shared@appv@@@kernel_std@@@Z; Streaming::MDLListCache::GetMDL(kernel_std::shared_ptr<appv::shared::kernel::kmdl> &)
0x1400102a3  jmp     loc_1400105BD
0x1400102a8  cmp     ebx, 20000h
0x1400102ae  ja      short loc_1400102B9
0x1400102b0  lea     rcx, [r13+100h]
0x1400102b7  jmp     short loc_14001029B
0x1400102b9  cmp     ebx, 100000h
0x1400102bf  ja      short loc_1400102CA
0x1400102c1  lea     rcx, [r13+200h]
0x1400102c8  jmp     short loc_14001029B
0x1400102ca  mov     edi, 726D6673h
0x1400102cf  mov     esi, 100h
0x1400102d4  mov     r8d, edi
0x1400102d7  mov     ecx, esi
0x1400102d9  mov     edx, 40h ; '@'
0x1400102de  call    cs:__imp_ExAllocatePool2
0x1400102e5  nop     dword ptr [rax+rax+00h]
0x1400102ea  xor     r12d, r12d
0x1400102ed  test    rax, rax
0x1400102f0  jz      short loc_14001030F
0x1400102f2  mov     [rax], r12b
0x1400102f5  mov     [rax+8], r12
0x1400102f9  mov     [rax+10h], r12
0x1400102fd  mov     [rax+18h], r12
0x140010301  mov     [rax+20h], r12
0x140010305  mov     [rax+30h], r12d
0x140010309  mov     [rax+38h], r12
0x14001030d  jmp     short loc_140010312
0x14001030f  mov     rax, r12
0x140010312  mov     rdx, rax
0x140010315  lea     rcx, [rbp+var_28]
0x140010319  call    ??$?0Vkmdl@kernel@shared@appv@@@?$shared_ptr@Vkmdl@kernel@shared@appv@@@kernel_std@@QEAA@PEAVkmdl@kernel@shared@appv@@@Z; kernel_std::shared_ptr<appv::shared::kernel::kmdl>::shared_ptr<appv::shared::kernel::kmdl>(appv::shared::kernel::kmdl *)
0x14001031e  mov     r15, [rbp+var_28]
0x140010322  test    r15, r15
0x140010325  jnz     short loc_14001033C
0x140010327  mov     rdi, [rbp+var_20]
0x14001032b  test    rdi, rdi
0x14001032e  jz      loc_14001048C
0x140010334  or      ebx, 0FFFFFFFFh
0x140010337  jmp     loc_140010458
0x14001033c  mov     rcx, r15; this
0x14001033f  call    ?close@kmdl@kernel@shared@appv@@AEAAXXZ; appv::shared::kernel::kmdl::close(void)
0x140010344  mov     rdx, rbx
0x140010347  mov     r8d, edi
0x14001034a  mov     rcx, rsi
0x14001034d  call    cs:__imp_ExAllocatePool2
0x140010354  nop     dword ptr [rax+rax+00h]
0x140010359  mov     [r15+18h], rax
0x14001035d  test    rax, rax
0x140010360  jnz     short loc_140010369
0x140010362  mov     esi, 0C000009Ah
0x140010367  jmp     short loc_14001037B
0x140010369  mov     rcx, r15; this
0x14001036c  mov     [r15+30h], ebx
0x140010370  call    ?Lock@kmdl@kernel@shared@appv@@AEAAJXZ; appv::shared::kernel::kmdl::Lock(void)
0x140010375  mov     esi, eax
0x140010377  test    eax, eax
0x140010379  jns     short loc_1400103C2
0x14001037b  mov     rdi, [rbp+var_20]
0x14001037f  test    rdi, rdi
0x140010382  jz      short loc_1400103BB
0x140010384  or      ebx, 0FFFFFFFFh
0x140010387  mov     ecx, ebx
0x140010389  lock xadd [rdi+8], ecx
0x14001038e  add     ecx, ebx
0x140010390  jnz     short loc_1400103BB
0x140010392  mov     rax, [rdi]
0x140010395  mov     rcx, rdi
0x140010398  mov     rax, [rax+8]
0x14001039c  call    _guard_dispatch_icall
0x1400103a1  mov     eax, ebx
0x1400103a3  lock xadd [rdi+0Ch], eax
0x1400103a8  add     eax, ebx
0x1400103aa  jnz     short loc_1400103BB
0x1400103ac  mov     rax, [rdi]
0x1400103af  mov     rcx, rdi
0x1400103b2  mov     rax, [rax+10h]
0x1400103b6  call    _guard_dispatch_icall
0x1400103bb  mov     eax, esi
0x1400103bd  jmp     loc_1400105BD
0x1400103c2  mov     r8d, edi
0x1400103c5  mov     edx, 18h
0x1400103ca  mov     ecx, 100h
0x1400103cf  call    cs:__imp_ExAllocatePool2
0x1400103d6  nop     dword ptr [rax+rax+00h]
0x1400103db  mov     rdi, [rbp+var_20]
0x1400103df  test    rax, rax
0x1400103e2  jz      short loc_1400103FA
0x1400103e4  mov     [rax], r15
0x1400103e7  mov     [rax+8], rdi
0x1400103eb  test    rdi, rdi
0x1400103ee  jz      short loc_1400103F4
0x1400103f0  lock inc dword ptr [rdi+8]
0x1400103f4  mov     byte ptr [rax+10h], 1
0x1400103f8  jmp     short loc_1400103FD
0x1400103fa  mov     rax, r12
0x1400103fd  mov     rdx, rax
0x140010400  lea     rcx, [rbp+var_18]
0x140010404  call    ??$?0UMDLEntry@Streaming@@@?$shared_ptr@UMDLEntry@Streaming@@@kernel_std@@QEAA@PEAUMDLEntry@Streaming@@@Z; kernel_std::shared_ptr<Streaming::MDLEntry>::shared_ptr<Streaming::MDLEntry>(Streaming::MDLEntry *)
0x140010409  cmp     [rbp+var_18], r12
0x14001040d  jnz     loc_140010496
0x140010413  mov     rsi, [rbp+var_10]
0x140010417  or      ebx, 0FFFFFFFFh
0x14001041a  test    rsi, rsi
0x14001041d  jz      short loc_140010453
0x14001041f  mov     eax, ebx
0x140010421  lock xadd [rsi+8], eax
0x140010426  add     eax, ebx
0x140010428  jnz     short loc_140010453
0x14001042a  mov     rax, [rsi]
0x14001042d  mov     rcx, rsi
0x140010430  mov     rax, [rax+8]
0x140010434  call    _guard_dispatch_icall
0x140010439  mov     eax, ebx
0x14001043b  lock xadd [rsi+0Ch], eax
0x140010440  add     eax, ebx
0x140010442  jnz     short loc_140010453
0x140010444  mov     rax, [rsi]
0x140010447  mov     rcx, rsi
0x14001044a  mov     rax, [rax+10h]
0x14001044e  call    _guard_dispatch_icall
0x140010453  test    rdi, rdi
0x140010456  jz      short loc_14001048C
0x140010458  mov     eax, ebx
0x14001045a  lock xadd [rdi+8], eax
0x14001045f  add     eax, ebx
0x140010461  jnz     short loc_14001048C
0x140010463  mov     rax, [rdi]
0x140010466  mov     rcx, rdi
0x140010469  mov     rax, [rax+8]
0x14001046d  call    _guard_dispatch_icall
0x140010472  mov     eax, ebx
0x140010474  lock xadd [rdi+0Ch], eax
0x140010479  add     eax, ebx
0x14001047b  jnz     short loc_14001048C
0x14001047d  mov     rax, [rdi]
0x140010480  mov     rcx, rdi
0x140010483  mov     rax, [rax+10h]
0x140010487  call    _guard_dispatch_icall
0x14001048c  mov     eax, 0C000009Ah
0x140010491  jmp     loc_1400105BD
0x140010496  lea     rcx, [r13+300h]
0x14001049d  lea     rdx, [rbp+var_18]
0x1400104a1  call    ?AddItem@MDLList@Streaming@@QEAAJAEAV?$shared_ptr@UMDLEntry@Streaming@@@kernel_std@@@Z; Streaming::MDLList::AddItem(kernel_std::shared_ptr<Streaming::MDLEntry> &)
0x1400104a6  mov     r12d, eax
0x1400104a9  test    eax, eax
0x1400104ab  jns     loc_140010532
0x1400104b1  mov     rsi, [rbp+var_10]
0x1400104b5  or      ebx, 0FFFFFFFFh
0x1400104b8  test    rsi, rsi
0x1400104bb  jz      short loc_1400104F1
0x1400104bd  mov     ecx, ebx
0x1400104bf  lock xadd [rsi+8], ecx
0x1400104c4  add     ecx, ebx
0x1400104c6  jnz     short loc_1400104F1
0x1400104c8  mov     rax, [rsi]
0x1400104cb  mov     rcx, rsi
0x1400104ce  mov     rax, [rax+8]
0x1400104d2  call    _guard_dispatch_icall
0x1400104d7  mov     eax, ebx
0x1400104d9  lock xadd [rsi+0Ch], eax
0x1400104de  add     eax, ebx
0x1400104e0  jnz     short loc_1400104F1
0x1400104e2  mov     rax, [rsi]
0x1400104e5  mov     rcx, rsi
0x1400104e8  mov     rax, [rax+10h]
0x1400104ec  call    _guard_dispatch_icall
0x1400104f1  test    rdi, rdi
0x1400104f4  jz      short loc_14001052A
0x1400104f6  mov     eax, ebx
0x1400104f8  lock xadd [rdi+8], eax
0x1400104fd  add     eax, ebx
0x1400104ff  jnz     short loc_14001052A
0x140010501  mov     rax, [rdi]
0x140010504  mov     rcx, rdi
0x140010507  mov     rax, [rax+8]
0x14001050b  call    _guard_dispatch_icall
0x140010510  mov     eax, ebx
0x140010512  lock xadd [rdi+0Ch], eax
0x140010517  add     eax, ebx
0x140010519  jnz     short loc_14001052A
0x14001051b  mov     rax, [rdi]
0x14001051e  mov     rcx, rdi
0x140010521  mov     rax, [rax+10h]
0x140010525  call    _guard_dispatch_icall
0x14001052a  mov     eax, r12d
0x14001052d  jmp     loc_1400105BD
0x140010532  lea     rcx, [r14+8]
0x140010536  mov     [r14], r15
0x140010539  lea     rdx, [rbp+var_20]
0x14001053d  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x140010542  mov     rsi, [rbp+var_10]
0x140010546  or      ebx, 0FFFFFFFFh
0x140010549  test    rsi, rsi
0x14001054c  jz      short loc_140010582
0x14001054e  mov     eax, ebx
0x140010550  lock xadd [rsi+8], eax
0x140010555  add     eax, ebx
0x140010557  jnz     short loc_140010582
0x140010559  mov     rax, [rsi]
0x14001055c  mov     rcx, rsi
0x14001055f  mov     rax, [rax+8]
0x140010563  call    _guard_dispatch_icall
0x140010568  mov     eax, ebx
0x14001056a  lock xadd [rsi+0Ch], eax
0x14001056f  add     eax, ebx
0x140010571  jnz     short loc_140010582
0x140010573  mov     rax, [rsi]
0x140010576  mov     rcx, rsi
0x140010579  mov     rax, [rax+10h]
0x14001057d  call    _guard_dispatch_icall
0x140010582  test    rdi, rdi
0x140010585  jz      short loc_1400105BB
0x140010587  mov     eax, ebx
0x140010589  lock xadd [rdi+8], eax
0x14001058e  add     eax, ebx
0x140010590  jnz     short loc_1400105BB
0x140010592  mov     rax, [rdi]
0x140010595  mov     rcx, rdi
0x140010598  mov     rax, [rax+8]
0x14001059c  call    _guard_dispatch_icall
0x1400105a1  mov     eax, ebx
0x1400105a3  lock xadd [rdi+0Ch], eax
0x1400105a8  add     eax, ebx
0x1400105aa  jnz     short loc_1400105BB
0x1400105ac  mov     rax, [rdi]
0x1400105af  mov     rcx, rdi
0x1400105b2  mov     rax, [rax+10h]
0x1400105b6  call    _guard_dispatch_icall
0x1400105bb  xor     eax, eax
0x1400105bd  add     rsp, 48h
0x1400105c1  pop     r15
0x1400105c3  pop     r14
0x1400105c5  pop     r13
0x1400105c7  pop     r12
0x1400105c9  pop     rdi
0x1400105ca  pop     rsi
0x1400105cb  pop     rbx
0x1400105cc  pop     rbp
0x1400105cd  retn
```
