# Streaming::MDLListCache::GetMDL(kernel_std::shared_ptr<appv::shared::kernel::kmdl> &)

- ea: `0x1400105d8`
- end: `0x140010a08`
- name: `?GetMDL@MDLListCache@Streaming@@QEAAJAEAV?$shared_ptr@Vkmdl@kernel@shared@appv@@@kernel_std@@@Z`
- size: `1072`
- prototype: `__int64 __fastcall(PPAGED_LOOKASIDE_LIST Lookaside)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140010270`

## callees

- `0x140003bd8`
- `0x14000fd90`
- `0x14000fe80`
- `0x140010188`
- `0x1400105d8`
- `0x140010a10`
- `0x140010b08`
- `0x140015b30`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140010781`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140010781`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001068f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400106e6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001068f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400106e6`
- `ntoskrnl!ExReleaseResourceLite` at `0x140010683`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400106da`
- `ntoskrnl!ExReleaseResourceLite` at `0x140010683`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400106da`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140010621`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140010621`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001060b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001060b`
- `ntoskrnl!ExAllocatePool2` at `0x140010703`
- `ntoskrnl!ExAllocatePool2` at `0x14001080b`
- `ntoskrnl!ExAllocatePool2` at `0x140010703`
- `ntoskrnl!ExAllocatePool2` at `0x14001080b`

## pseudocode

```c
__int64 __fastcall Streaming::MDLListCache::GetMDL(PPAGED_LOOKASIDE_LIST Lookaside, appv::shared::kernel::kmdl **a2)
{
  bool v2; // di
  bool v3; // zf
  struct _PAGED_LOOKASIDE_LIST *i; // rdx
  struct _ERESOURCE *v7; // rcx
  __int64 v8; // rdx
  volatile signed __int32 *v9; // rdi
  struct _ERESOURCE *v10; // rcx
  __int64 Pool2; // rax
  appv::shared::kernel::kmdl *v12; // r14
  int Flink_high; // edi
  PVOID v14; // rax
  int v15; // esi
  volatile signed __int32 *v16; // rdi
  __int64 v18; // rax
  volatile signed __int32 *v19; // rsi
  int v20; // r15d
  volatile signed __int32 *v21; // rsi
  volatile signed __int32 *v22; // rsi
  appv::shared::kernel::kmdl *v23; // [rsp+20h] [rbp-20h] BYREF
  volatile signed __int32 *v24; // [rsp+28h] [rbp-18h] BYREF
  __int128 v25; // [rsp+30h] [rbp-10h] BYREF

  v2 = 0;
  v3 = *(_QWORD *)&Lookaside[1].L.Depth == 0;
  v25 = 0;
  if ( !v3 )
  {
    KeEnterCriticalRegion();
    v2 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)&Lookaside[1].L.Depth, 1u) == 1;
  }
  for ( i = (struct _PAGED_LOOKASIDE_LIST *)Lookaside[1].L.FreeEx;
        i != (struct _PAGED_LOOKASIDE_LIST *)&Lookaside[1].L.FreeMisses;
        i = *(struct _PAGED_LOOKASIDE_LIST **)&i->L.AllocateMisses )
  {
    if ( !*(_BYTE *)(i->L.ListHead.Alignment + 16) )
    {
      *(_BYTE *)(i->L.ListHead.Alignment + 16) = 1;
      *(_QWORD *)&v25 = i->L.ListHead.Alignment;
      kernel_std::detail::shared_count::operator=((char *)&v25 + 8, &i->L.SingleListHead + 1);
      if ( v2 )
      {
        v7 = *(struct _ERESOURCE **)&Lookaside[1].L.Depth;
        if ( v7 )
        {
          ExReleaseResourceLite(v7);
          KeLeaveCriticalRegion();
        }
      }
      v8 = v25 + 8;
      *a2 = *(appv::shared::kernel::kmdl **)v25;
      kernel_std::detail::shared_count::operator=(a2 + 1, v8);
      v9 = (volatile signed __int32 *)*((_QWORD *)&v25 + 1);
      if ( *((_QWORD *)&v25 + 1) )
        goto LABEL_57;
      return 0;
    }
  }
  if ( v2 )
  {
    v10 = *(struct _ERESOURCE **)&Lookaside[1].L.Depth;
    if ( v10 )
    {
      ExReleaseResourceLite(v10);
      KeLeaveCriticalRegion();
    }
  }
  Pool2 = ExAllocatePool2(256, 64, LODWORD(Lookaside[1].L.ListHead.Alignment));
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
  kernel_std::shared_ptr<appv::shared::kernel::kmdl>::shared_ptr<appv::shared::kernel::kmdl>(&v23, Pool2);
  v12 = v23;
  if ( !v23 )
  {
    v9 = v24;
    if ( !v24 )
      return 3221225626LL;
LABEL_38:
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return 3221225626LL;
  }
  Flink_high = HIDWORD(Lookaside[1].L.ListEntry.Flink);
  appv::shared::kernel::kmdl::close(v23);
  v14 = ExAllocateFromPagedLookasideList(Lookaside);
  *((_QWORD *)v12 + 4) = v14;
  if ( !v14 )
  {
    v15 = -1073741670;
    goto LABEL_23;
  }
  *((_DWORD *)v12 + 12) = Flink_high;
  *((_QWORD *)v12 + 5) = Lookaside;
  v15 = appv::shared::kernel::kmdl::Lock(v12);
  if ( v15 < 0 )
  {
LABEL_23:
    v16 = v24;
    if ( v24 )
    {
      if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 16LL))(v16);
      }
    }
    return (unsigned int)v15;
  }
  v18 = ExAllocatePool2(256, 24, LODWORD(Lookaside[1].L.ListHead.Alignment));
  v9 = v24;
  if ( v18 )
  {
    *(_QWORD *)v18 = v12;
    *(_QWORD *)(v18 + 8) = v9;
    if ( v9 )
      _InterlockedAdd(v9 + 2, 1u);
    *(_BYTE *)(v18 + 16) = 1;
  }
  kernel_std::shared_ptr<Streaming::MDLEntry>::shared_ptr<Streaming::MDLEntry>(&v25, v18);
  if ( !(_QWORD)v25 )
  {
    v19 = (volatile signed __int32 *)*((_QWORD *)&v25 + 1);
    if ( *((_QWORD *)&v25 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v25 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 16LL))(v19);
      }
    }
    if ( !v9 )
      return 3221225626LL;
    goto LABEL_38;
  }
  v20 = Streaming::MDLList::AddItem(&Lookaside[1].L.SingleListHead + 1, &v25);
  if ( v20 >= 0 )
  {
    *a2 = v12;
    kernel_std::detail::shared_count::operator=(a2 + 1, &v24);
    v22 = (volatile signed __int32 *)*((_QWORD *)&v25 + 1);
    if ( *((_QWORD *)&v25 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v25 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
        if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 16LL))(v22);
      }
    }
    if ( v9 )
    {
LABEL_57:
      if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
      }
    }
    return 0;
  }
  else
  {
    v21 = (volatile signed __int32 *)*((_QWORD *)&v25 + 1);
    if ( *((_QWORD *)&v25 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v25 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
        if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 16LL))(v21);
      }
    }
    if ( v9 )
    {
      if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
      {
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 16LL))(v9);
      }
    }
    return (unsigned int)v20;
  }
}

```

## disassembly

```asm
0x1400105d8  push    rbp
0x1400105da  push    rbx
0x1400105db  push    rsi
0x1400105dc  push    rdi
0x1400105dd  push    r12
0x1400105df  push    r14
0x1400105e1  push    r15
0x1400105e3  mov     rbp, rsp
0x1400105e6  sub     rsp, 40h
0x1400105ea  xor     dil, dil
0x1400105ed  xorps   xmm0, xmm0
0x1400105f0  cmp     qword ptr [rcx+90h], 0
0x1400105f8  mov     r12, rdx
0x1400105fb  mov     rbx, rcx
0x1400105fe  mov     r15d, 1
0x140010604  movdqu  [rbp+var_10], xmm0
0x140010609  jz      short loc_140010638
0x14001060b  call    cs:__imp_KeEnterCriticalRegion
0x140010612  nop     dword ptr [rax+rax+00h]
0x140010617  mov     rcx, [rbx+90h]; Resource
0x14001061e  mov     dl, r15b; Wait
0x140010621  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140010628  nop     dword ptr [rax+rax+00h]
0x14001062d  cmp     al, r15b
0x140010630  movzx   edi, dil
0x140010634  cmovz   edi, r15d
0x140010638  mov     rdx, [rbx+0B8h]
0x14001063f  lea     rcx, [rbx+0A0h]
0x140010646  cmp     rdx, rcx
0x140010649  jz      short loc_1400106C9
0x14001064b  mov     rax, [rdx]
0x14001064e  cmp     byte ptr [rax+10h], 0
0x140010652  jz      short loc_14001065A
0x140010654  mov     rdx, [rdx+18h]
0x140010658  jmp     short loc_140010646
0x14001065a  mov     [rax+10h], r15b
0x14001065e  lea     rcx, [rbp+var_10+8]
0x140010662  mov     rax, [rdx]
0x140010665  add     rdx, 8
0x140010669  mov     qword ptr [rbp+var_10], rax
0x14001066d  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x140010672  test    dil, dil
0x140010675  jz      short loc_14001069B
0x140010677  mov     rcx, [rbx+90h]; Resource
0x14001067e  test    rcx, rcx
0x140010681  jz      short loc_14001069B
0x140010683  call    cs:__imp_ExReleaseResourceLite
0x14001068a  nop     dword ptr [rax+rax+00h]
0x14001068f  call    cs:__imp_KeLeaveCriticalRegion
0x140010696  nop     dword ptr [rax+rax+00h]
0x14001069b  mov     rdx, qword ptr [rbp+var_10]
0x14001069f  lea     rcx, [r12+8]
0x1400106a4  mov     rax, [rdx]
0x1400106a7  add     rdx, 8
0x1400106ab  mov     [r12], rax
0x1400106af  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x1400106b4  mov     rdi, qword ptr [rbp+var_10+8]
0x1400106b8  test    rdi, rdi
0x1400106bb  jz      loc_1400109F6
0x1400106c1  or      ebx, 0FFFFFFFFh
0x1400106c4  jmp     loc_1400109C2
0x1400106c9  test    dil, dil
0x1400106cc  jz      short loc_1400106F2
0x1400106ce  mov     rcx, [rbx+90h]; Resource
0x1400106d5  test    rcx, rcx
0x1400106d8  jz      short loc_1400106F2
0x1400106da  call    cs:__imp_ExReleaseResourceLite
0x1400106e1  nop     dword ptr [rax+rax+00h]
0x1400106e6  call    cs:__imp_KeLeaveCriticalRegion
0x1400106ed  nop     dword ptr [rax+rax+00h]
0x1400106f2  mov     r8d, [rbx+80h]
0x1400106f9  mov     edx, 40h ; '@'
0x1400106fe  mov     ecx, 100h
0x140010703  call    cs:__imp_ExAllocatePool2
0x14001070a  nop     dword ptr [rax+rax+00h]
0x14001070f  test    rax, rax
0x140010712  jz      short loc_140010746
0x140010714  mov     byte ptr [rax], 0
0x140010717  mov     qword ptr [rax+8], 0
0x14001071f  mov     qword ptr [rax+10h], 0
0x140010727  mov     qword ptr [rax+18h], 0
0x14001072f  mov     qword ptr [rax+20h], 0
0x140010737  mov     dword ptr [rax+30h], 0
0x14001073e  mov     qword ptr [rax+38h], 0
0x140010746  mov     rdx, rax
0x140010749  lea     rcx, [rbp+var_20]
0x14001074d  call    ??$?0Vkmdl@kernel@shared@appv@@@?$shared_ptr@Vkmdl@kernel@shared@appv@@@kernel_std@@QEAA@PEAVkmdl@kernel@shared@appv@@@Z; kernel_std::shared_ptr<appv::shared::kernel::kmdl>::shared_ptr<appv::shared::kernel::kmdl>(appv::shared::kernel::kmdl *)
0x140010752  mov     r14, [rbp+var_20]
0x140010756  test    r14, r14
0x140010759  jnz     short loc_140010770
0x14001075b  mov     rdi, [rbp+var_18]
0x14001075f  test    rdi, rdi
0x140010762  jz      loc_1400108C5
0x140010768  or      ebx, 0FFFFFFFFh
0x14001076b  jmp     loc_140010891
0x140010770  mov     edi, [rbx+0C4h]
0x140010776  mov     rcx, r14; this
0x140010779  call    ?close@kmdl@kernel@shared@appv@@AEAAXXZ; appv::shared::kernel::kmdl::close(void)
0x14001077e  mov     rcx, rbx; Lookaside
0x140010781  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140010788  nop     dword ptr [rax+rax+00h]
0x14001078d  mov     [r14+20h], rax
0x140010791  test    rax, rax
0x140010794  jnz     short loc_14001079D
0x140010796  mov     esi, 0C000009Ah
0x14001079b  jmp     short loc_1400107B3
0x14001079d  mov     rcx, r14; this
0x1400107a0  mov     [r14+30h], edi
0x1400107a4  mov     [r14+28h], rbx
0x1400107a8  call    ?Lock@kmdl@kernel@shared@appv@@AEAAJXZ; appv::shared::kernel::kmdl::Lock(void)
0x1400107ad  mov     esi, eax
0x1400107af  test    eax, eax
0x1400107b1  jns     short loc_1400107FA
0x1400107b3  mov     rdi, [rbp+var_18]
0x1400107b7  test    rdi, rdi
0x1400107ba  jz      short loc_1400107F3
0x1400107bc  or      ebx, 0FFFFFFFFh
0x1400107bf  mov     ecx, ebx
0x1400107c1  lock xadd [rdi+8], ecx
0x1400107c6  add     ecx, ebx
0x1400107c8  jnz     short loc_1400107F3
0x1400107ca  mov     rax, [rdi]
0x1400107cd  mov     rcx, rdi
0x1400107d0  mov     rax, [rax+8]
0x1400107d4  call    _guard_dispatch_icall
0x1400107d9  mov     eax, ebx
0x1400107db  lock xadd [rdi+0Ch], eax
0x1400107e0  add     eax, ebx
0x1400107e2  jnz     short loc_1400107F3
0x1400107e4  mov     rax, [rdi]
0x1400107e7  mov     rcx, rdi
0x1400107ea  mov     rax, [rax+10h]
0x1400107ee  call    _guard_dispatch_icall
0x1400107f3  mov     eax, esi
0x1400107f5  jmp     loc_1400109F8
0x1400107fa  mov     r8d, [rbx+80h]
0x140010801  mov     edx, 18h
0x140010806  mov     ecx, 100h
0x14001080b  call    cs:__imp_ExAllocatePool2
0x140010812  nop     dword ptr [rax+rax+00h]
0x140010817  mov     rdi, [rbp+var_18]
0x14001081b  test    rax, rax
0x14001081e  jz      short loc_140010835
0x140010820  mov     [rax], r14
0x140010823  mov     [rax+8], rdi
0x140010827  test    rdi, rdi
0x14001082a  jz      short loc_140010831
0x14001082c  lock add [rdi+8], r15d
0x140010831  mov     [rax+10h], r15b
0x140010835  mov     rdx, rax
0x140010838  lea     rcx, [rbp+var_10]
0x14001083c  call    ??$?0UMDLEntry@Streaming@@@?$shared_ptr@UMDLEntry@Streaming@@@kernel_std@@QEAA@PEAUMDLEntry@Streaming@@@Z; kernel_std::shared_ptr<Streaming::MDLEntry>::shared_ptr<Streaming::MDLEntry>(Streaming::MDLEntry *)
0x140010841  cmp     qword ptr [rbp+var_10], 0
0x140010846  jnz     loc_1400108CF
0x14001084c  mov     rsi, qword ptr [rbp+var_10+8]
0x140010850  or      ebx, 0FFFFFFFFh
0x140010853  test    rsi, rsi
0x140010856  jz      short loc_14001088C
0x140010858  mov     eax, ebx
0x14001085a  lock xadd [rsi+8], eax
0x14001085f  add     eax, ebx
0x140010861  jnz     short loc_14001088C
0x140010863  mov     rax, [rsi]
0x140010866  mov     rcx, rsi
0x140010869  mov     rax, [rax+8]
0x14001086d  call    _guard_dispatch_icall
0x140010872  mov     eax, ebx
0x140010874  lock xadd [rsi+0Ch], eax
0x140010879  add     eax, ebx
0x14001087b  jnz     short loc_14001088C
0x14001087d  mov     rax, [rsi]
0x140010880  mov     rcx, rsi
0x140010883  mov     rax, [rax+10h]
0x140010887  call    _guard_dispatch_icall
0x14001088c  test    rdi, rdi
0x14001088f  jz      short loc_1400108C5
0x140010891  mov     eax, ebx
0x140010893  lock xadd [rdi+8], eax
0x140010898  add     eax, ebx
0x14001089a  jnz     short loc_1400108C5
0x14001089c  mov     rax, [rdi]
0x14001089f  mov     rcx, rdi
0x1400108a2  mov     rax, [rax+8]
0x1400108a6  call    _guard_dispatch_icall
0x1400108ab  mov     eax, ebx
0x1400108ad  lock xadd [rdi+0Ch], eax
0x1400108b2  add     eax, ebx
0x1400108b4  jnz     short loc_1400108C5
0x1400108b6  mov     rax, [rdi]
0x1400108b9  mov     rcx, rdi
0x1400108bc  mov     rax, [rax+10h]
0x1400108c0  call    _guard_dispatch_icall
0x1400108c5  mov     eax, 0C000009Ah
0x1400108ca  jmp     loc_1400109F8
0x1400108cf  lea     rcx, [rbx+88h]
0x1400108d6  lea     rdx, [rbp+var_10]
0x1400108da  call    ?AddItem@MDLList@Streaming@@QEAAJAEAV?$shared_ptr@UMDLEntry@Streaming@@@kernel_std@@@Z; Streaming::MDLList::AddItem(kernel_std::shared_ptr<Streaming::MDLEntry> &)
0x1400108df  mov     r15d, eax
0x1400108e2  test    eax, eax
0x1400108e4  jns     loc_14001096B
0x1400108ea  mov     rsi, qword ptr [rbp+var_10+8]
0x1400108ee  or      ebx, 0FFFFFFFFh
0x1400108f1  test    rsi, rsi
0x1400108f4  jz      short loc_14001092A
0x1400108f6  mov     ecx, ebx
0x1400108f8  lock xadd [rsi+8], ecx
0x1400108fd  add     ecx, ebx
0x1400108ff  jnz     short loc_14001092A
0x140010901  mov     rax, [rsi]
0x140010904  mov     rcx, rsi
0x140010907  mov     rax, [rax+8]
0x14001090b  call    _guard_dispatch_icall
0x140010910  mov     eax, ebx
0x140010912  lock xadd [rsi+0Ch], eax
0x140010917  add     eax, ebx
0x140010919  jnz     short loc_14001092A
0x14001091b  mov     rax, [rsi]
0x14001091e  mov     rcx, rsi
0x140010921  mov     rax, [rax+10h]
0x140010925  call    _guard_dispatch_icall
0x14001092a  test    rdi, rdi
0x14001092d  jz      short loc_140010963
0x14001092f  mov     eax, ebx
0x140010931  lock xadd [rdi+8], eax
0x140010936  add     eax, ebx
0x140010938  jnz     short loc_140010963
0x14001093a  mov     rax, [rdi]
0x14001093d  mov     rcx, rdi
0x140010940  mov     rax, [rax+8]
0x140010944  call    _guard_dispatch_icall
0x140010949  mov     eax, ebx
0x14001094b  lock xadd [rdi+0Ch], eax
0x140010950  add     eax, ebx
0x140010952  jnz     short loc_140010963
0x140010954  mov     rax, [rdi]
0x140010957  mov     rcx, rdi
0x14001095a  mov     rax, [rax+10h]
0x14001095e  call    _guard_dispatch_icall
0x140010963  mov     eax, r15d
0x140010966  jmp     loc_1400109F8
0x14001096b  lea     rcx, [r12+8]
0x140010970  mov     [r12], r14
0x140010974  lea     rdx, [rbp+var_18]
0x140010978  call    ??4shared_count@detail@kernel_std@@QEAAAEAV012@AEBV012@@Z; kernel_std::detail::shared_count::operator=(kernel_std::detail::shared_count const &)
0x14001097d  mov     rsi, qword ptr [rbp+var_10+8]
0x140010981  or      ebx, 0FFFFFFFFh
0x140010984  test    rsi, rsi
0x140010987  jz      short loc_1400109BD
0x140010989  mov     eax, ebx
0x14001098b  lock xadd [rsi+8], eax
0x140010990  add     eax, ebx
0x140010992  jnz     short loc_1400109BD
0x140010994  mov     rax, [rsi]
0x140010997  mov     rcx, rsi
0x14001099a  mov     rax, [rax+8]
0x14001099e  call    _guard_dispatch_icall
0x1400109a3  mov     eax, ebx
0x1400109a5  lock xadd [rsi+0Ch], eax
0x1400109aa  add     eax, ebx
0x1400109ac  jnz     short loc_1400109BD
0x1400109ae  mov     rax, [rsi]
0x1400109b1  mov     rcx, rsi
0x1400109b4  mov     rax, [rax+10h]
0x1400109b8  call    _guard_dispatch_icall
0x1400109bd  test    rdi, rdi
0x1400109c0  jz      short loc_1400109F6
0x1400109c2  mov     eax, ebx
0x1400109c4  lock xadd [rdi+8], eax
0x1400109c9  add     eax, ebx
0x1400109cb  jnz     short loc_1400109F6
0x1400109cd  mov     rax, [rdi]
0x1400109d0  mov     rcx, rdi
0x1400109d3  mov     rax, [rax+8]
0x1400109d7  call    _guard_dispatch_icall
0x1400109dc  mov     eax, ebx
0x1400109de  lock xadd [rdi+0Ch], eax
0x1400109e3  add     eax, ebx
0x1400109e5  jnz     short loc_1400109F6
0x1400109e7  mov     rax, [rdi]
0x1400109ea  mov     rcx, rdi
0x1400109ed  mov     rax, [rax+10h]
0x1400109f1  call    _guard_dispatch_icall
0x1400109f6  xor     eax, eax
0x1400109f8  add     rsp, 40h
0x1400109fc  pop     r15
0x1400109fe  pop     r14
0x140010a00  pop     r12
0x140010a02  pop     rdi
0x140010a03  pop     rsi
0x140010a04  pop     rbx
0x140010a05  pop     rbp
0x140010a06  retn
```
