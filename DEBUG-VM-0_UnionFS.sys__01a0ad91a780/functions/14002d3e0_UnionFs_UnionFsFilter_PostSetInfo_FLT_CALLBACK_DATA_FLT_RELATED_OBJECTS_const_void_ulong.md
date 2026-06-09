# UnionFs::UnionFsFilter::PostSetInfo(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void *,ulong)

- ea: `0x14002d3e0`
- end: `0x14002d6c9`
- name: `?PostSetInfo@UnionFsFilter@UnionFs@@SA?AW4_FLT_POSTOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAXK@Z`
- size: `745`
- prototype: `enum _FLT_POSTOP_CALLBACK_STATUS __fastcall(struct _FLT_CALLBACK_DATA *this, const struct _FLT_RELATED_OBJECTS *, struct _FLT_RELATED_OBJECTS *, unsigned int)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, installer_update`

## callees

- `0x1400056b4`
- `0x140006168`
- `0x14000f81c`
- `0x14002af6c`
- `0x14002be04`
- `0x14002ca90`
- `0x14002d3e0`
- `0x140042674`
- `0x14004327c`
- `0x1400435f4`
- `0x140056c7c`
- `0x14007a114`
- `0x14007baf0`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002d5a8`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002d5a8`
- `ntoskrnl!ObfDereferenceObject` at `0x14002d58b`
- `ntoskrnl!ObfDereferenceObject` at `0x14002d58b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002d54a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002d61a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002d54a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002d61a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002d556`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002d626`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002d556`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002d626`

## string_xrefs

- `0x14002d661`: `PUSH: Post rename`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::PostSetInfo(
        struct _FLT_CALLBACK_DATA *this,
        struct _FLT_CALLBACK_DATA *a2,
        struct _ERESOURCE *a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rdx
  PFILE_OBJECT v7; // rcx
  struct _LOOKASIDE_LIST_EX *v8; // rcx
  bool v9; // sf
  PFLT_FILTER Blink; // r14
  const PFLT_VOLUME *p_OwnerTable; // rsi
  volatile signed __int32 *v12; // rdi
  struct _ERESOURCE *v13; // rcx
  utl::_RefCountBase *OwnerTable; // rcx
  struct _LIST_ENTRY *Flink; // rcx
  NTSTATUS v16; // r14d
  struct _ERESOURCE *v17; // rcx
  NTSTATUS v18; // ebx
  const char *v20; // [rsp+28h] [rbp-D8h]
  PERESOURCE Resource; // [rsp+30h] [rbp-D0h] BYREF
  int v22[188]; // [rsp+38h] [rbp-C8h] BYREF

  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v22, 0x339000B0A86uLL, this);
  Iopb = this->Iopb;
  switch ( Iopb->Parameters.Create.Options )
  {
    case 0xAu:
      goto LABEL_39;
    case 0xBu:
      goto LABEL_16;
    case 0x13u:
    case 0x14u:
    case 0x27u:
      v9 = this->IoStatus.Status < 0;
      Resource = a3;
      if ( !v9 && a3->SystemResourcesList.Flink )
        UnionFs::UfsStreamCtx::UpdateSFOFileSizesForScratchBFO((UnionFs::UfsStreamCtx *)a3->SystemResourcesList.Flink);
      utl::unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>::~unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>(&Resource);
      goto LABEL_41;
    case 0x41u:
LABEL_39:
      v18 = UnionFs::PostRename(
              (UnionFs *)this,
              a2,
              (struct _FLT_RELATED_OBJECTS *)a3,
              (struct UnionFs::StackEventTracer *)v22);
      if ( v18 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v18,
          (int)v22,
          (struct UnionFs::StackEventTracer *)0x344000B0A91LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PostSetInfo",
          "PUSH: Post rename",
          v20);
        this->IoStatus.Status = v18;
        this->IoStatus.Information = 0;
      }
      goto LABEL_41;
    case 0x48u:
LABEL_16:
      Blink = (PFLT_FILTER)a3->SystemResourcesList.Blink;
      p_OwnerTable = (const PFLT_VOLUME *)&a3->OwnerTable;
      if ( Blink )
      {
        v12 = (volatile signed __int32 *)*p_OwnerTable;
        if ( *p_OwnerTable )
          _InterlockedIncrement(v12 + 2);
        (*(void (__fastcall **)(PFLT_FILTER, PERESOURCE *))(*(_QWORD *)Blink + 16LL))(Blink, &Resource);
        if ( *((_WORD *)Blink + 85) != 2 || this->IoStatus.Status )
        {
          v16 = UnionFs::UfsPathCachePayload::RevertSoftTombstone(Blink, (struct UnionFs::StackEventTracer *)v22);
          if ( v16 < 0 )
          {
            UnionFs::ProcessTraceStatusPushLocation(
              (UnionFs *)(unsigned int)v16,
              (int)v22,
              (struct UnionFs::StackEventTracer *)0x45D000B0AB3LL,
              (unsigned __int64)"UnionFs::UnionFsFilter::PostSetInfo",
              "PUSH: Reverting soft tombstone",
              v20);
            v17 = Resource;
            this->IoStatus.Status = v16;
            this->IoStatus.Information = 0;
            Resource = 0;
            if ( v17 )
            {
              ExReleaseResourceLite(v17);
              KeLeaveCriticalRegion();
            }
            if ( v12 )
              utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v12);
            OwnerTable = (utl::_RefCountBase *)a3->OwnerTable;
            goto LABEL_27;
          }
        }
        else
        {
          UnionFs::UfsPathCachePayload::InvalidateNoRevertSoftTombstone(Blink, 0x44F000B0AACLL);
          UnionFs::UfsPathCachePayload::RevertSoftTombstone(Blink);
        }
        v13 = Resource;
        Resource = 0;
        if ( v13 )
        {
          ExReleaseResourceLite(v13);
          KeLeaveCriticalRegion();
        }
        if ( v12 )
          utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v12);
      }
      OwnerTable = *p_OwnerTable;
LABEL_27:
      if ( OwnerTable )
        utl::_RefCountBase::_DecStrong(OwnerTable);
      Flink = a3->SystemResourcesList.Flink;
      a3->SystemResourcesList.Flink = 0;
      if ( Flink )
        ObfDereferenceObject(Flink);
      v8 = (struct _LOOKASIDE_LIST_EX *)((char *)UnionFs::g_FilterState + 416);
      goto LABEL_32;
  }
  if ( a3 )
  {
    FsFltWil::Details::ReleaseRundownProtectionCacheAware(
      (FsFltWil::Details *)a3,
      (struct FsFltWil::Details::RundownRefCacheAware *)Iopb);
    v7 = *(PFILE_OBJECT *)&a3[1].ActiveCount;
    if ( v7 )
      (*(void (__fastcall **)(PFILE_OBJECT))(*(_QWORD *)&v7->Type + 24LL))(v7);
    v8 = (struct _LOOKASIDE_LIST_EX *)((char *)UnionFs::g_FilterState + 896);
LABEL_32:
    ExFreeToLookasideListEx(v8, a3);
  }
LABEL_41:
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v22);
  return 0;
}

```

## disassembly

```asm
0x14002d3e0  mov     [rsp-8+arg_18], rbx
0x14002d3e5  push    rbp
0x14002d3e6  push    rsi
0x14002d3e7  push    rdi
0x14002d3e8  push    r14
0x14002d3ea  push    r15
0x14002d3ec  lea     rbp, [rsp-230h]
0x14002d3f4  sub     rsp, 330h
0x14002d3fb  mov     rax, cs:__security_cookie
0x14002d402  xor     rax, rsp
0x14002d405  mov     [rbp+250h+var_28], rax
0x14002d40c  mov     rbx, r8
0x14002d40f  mov     rdi, rdx
0x14002d412  mov     r8, rcx; struct _FLT_CALLBACK_DATA *
0x14002d415  mov     r15, rcx
0x14002d418  lea     rcx, [rsp+350h+var_318]; this
0x14002d41d  mov     rdx, 339000B0A86h; unsigned __int64
0x14002d427  call    ??0StackEventTracer@UnionFs@@QEAA@_KPEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64,_FLT_CALLBACK_DATA const *)
0x14002d42c  mov     rdx, [r15+10h]; struct FsFltWil::Details::RundownRefCacheAware *
0x14002d430  mov     r8d, [rdx+20h]
0x14002d434  sub     r8d, 0Ah
0x14002d438  jz      loc_14002D648
0x14002d43e  sub     r8d, 1
0x14002d442  jz      loc_14002D4CE
0x14002d448  sub     r8d, 8
0x14002d44c  jz      short loc_14002D4A6
0x14002d44e  sub     r8d, 1
0x14002d452  jz      short loc_14002D4A6
0x14002d454  sub     r8d, 13h
0x14002d458  jz      short loc_14002D4A6
0x14002d45a  sub     r8d, 1Ah
0x14002d45e  jz      loc_14002D648
0x14002d464  cmp     r8d, 7
0x14002d468  jz      short loc_14002D4CE
0x14002d46a  test    rbx, rbx
0x14002d46d  jz      loc_14002D696
0x14002d473  mov     rcx, rbx; this
0x14002d476  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14002d47b  mov     rcx, [rbx+80h]
0x14002d482  test    rcx, rcx
0x14002d485  jz      short loc_14002D493
0x14002d487  mov     rax, [rcx]
0x14002d48a  mov     rax, [rax+18h]
0x14002d48e  call    _guard_dispatch_icall
0x14002d493  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14002d49a  add     rcx, 380h
0x14002d4a1  jmp     loc_14002D5A5
0x14002d4a6  cmp     dword ptr [r15+18h], 0
0x14002d4ab  mov     [rsp+350h+Resource], rbx
0x14002d4b0  jl      short loc_14002D4BF
0x14002d4b2  mov     rcx, [rbx]; this
0x14002d4b5  test    rcx, rcx
0x14002d4b8  jz      short loc_14002D4BF
0x14002d4ba  call    ?UpdateSFOFileSizesForScratchBFO@UfsStreamCtx@UnionFs@@QEAAXXZ; UnionFs::UfsStreamCtx::UpdateSFOFileSizesForScratchBFO(void)
0x14002d4bf  lea     rcx, [rsp+350h+Resource]
0x14002d4c4  call    ??1?$unique_ptr@USetFileSizeContext@UnionFs@@U?$default_delete@USetFileSizeContext@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>::~unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>(void)
0x14002d4c9  jmp     loc_14002D696
0x14002d4ce  mov     r14, [rbx+8]
0x14002d4d2  lea     rsi, [rbx+10h]
0x14002d4d6  test    r14, r14
0x14002d4d9  jz      loc_14002D56F
0x14002d4df  mov     rdi, [rsi]
0x14002d4e2  test    rdi, rdi
0x14002d4e5  jz      short loc_14002D4EB
0x14002d4e7  lock inc dword ptr [rdi+8]
0x14002d4eb  mov     rax, [r14]
0x14002d4ee  lea     rdx, [rsp+350h+Resource]
0x14002d4f3  mov     rcx, r14
0x14002d4f6  mov     rax, [rax+10h]
0x14002d4fa  call    _guard_dispatch_icall
0x14002d4ff  movzx   eax, word ptr [r14+0AAh]
0x14002d507  nop
0x14002d508  cmp     ax, 2
0x14002d50c  jnz     loc_14002D5B9
0x14002d512  cmp     dword ptr [r15+18h], 0
0x14002d517  jnz     loc_14002D5B9
0x14002d51d  mov     rdx, 44F000B0AACh
0x14002d527  mov     rcx, r14
0x14002d52a  call    ?InvalidateNoRevertSoftTombstone@UfsPathCachePayload@UnionFs@@AEAAXT_TAGGED_SOURCE@@@Z; UnionFs::UfsPathCachePayload::InvalidateNoRevertSoftTombstone(_TAGGED_SOURCE)
0x14002d52f  mov     rcx, r14; this
0x14002d532  call    ?RevertSoftTombstone@UfsPathCachePayload@UnionFs@@AEAA_NXZ; UnionFs::UfsPathCachePayload::RevertSoftTombstone(void)
0x14002d537  mov     rcx, [rsp+350h+Resource]; Resource
0x14002d53c  mov     [rsp+350h+Resource], 0
0x14002d545  test    rcx, rcx
0x14002d548  jz      short loc_14002D562
0x14002d54a  call    cs:__imp_ExReleaseResourceLite
0x14002d551  nop     dword ptr [rax+rax+00h]
0x14002d556  call    cs:__imp_KeLeaveCriticalRegion
0x14002d55d  nop     dword ptr [rax+rax+00h]
0x14002d562  test    rdi, rdi
0x14002d565  jz      short loc_14002D56F
0x14002d567  mov     rcx, rdi; this
0x14002d56a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002d56f  mov     rcx, [rsi]; this
0x14002d572  test    rcx, rcx
0x14002d575  jz      short loc_14002D57C
0x14002d577  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002d57c  mov     rcx, [rbx]; Object
0x14002d57f  mov     qword ptr [rbx], 0
0x14002d586  test    rcx, rcx
0x14002d589  jz      short loc_14002D597
0x14002d58b  call    cs:__imp_ObfDereferenceObject
0x14002d592  nop     dword ptr [rax+rax+00h]
0x14002d597  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14002d59e  add     rcx, 1A0h; Lookaside
0x14002d5a5  mov     rdx, rbx; Entry
0x14002d5a8  call    cs:__imp_ExFreeToLookasideListEx
0x14002d5af  nop     dword ptr [rax+rax+00h]
0x14002d5b4  jmp     loc_14002D696
0x14002d5b9  lea     rdx, [rsp+350h+var_318]; struct UnionFs::StackEventTracer *
0x14002d5be  mov     rcx, r14; this
0x14002d5c1  call    ?RevertSoftTombstone@UfsPathCachePayload@UnionFs@@QEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsPathCachePayload::RevertSoftTombstone(UnionFs::StackEventTracer &)
0x14002d5c6  mov     r14d, eax
0x14002d5c9  test    eax, eax
0x14002d5cb  jns     loc_14002D537
0x14002d5d1  lea     rax, aPushRevertingS; "PUSH: Reverting soft tombstone"
0x14002d5d8  mov     r8, 45D000B0AB3h; struct UnionFs::StackEventTracer *
0x14002d5e2  lea     r9, aUnionfsUnionfs_55; "UnionFs::UnionFsFilter::PostSetInfo"
0x14002d5e9  mov     [rsp+350h+var_330], rax; char *
0x14002d5ee  lea     rdx, [rsp+350h+var_318]; int
0x14002d5f3  mov     ecx, r14d; this
0x14002d5f6  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002d5fb  mov     rcx, [rsp+350h+Resource]; Resource
0x14002d600  mov     [r15+18h], r14d
0x14002d604  mov     qword ptr [r15+20h], 0
0x14002d60c  mov     [rsp+350h+Resource], 0
0x14002d615  test    rcx, rcx
0x14002d618  jz      short loc_14002D632
0x14002d61a  call    cs:__imp_ExReleaseResourceLite
0x14002d621  nop     dword ptr [rax+rax+00h]
0x14002d626  call    cs:__imp_KeLeaveCriticalRegion
0x14002d62d  nop     dword ptr [rax+rax+00h]
0x14002d632  test    rdi, rdi
0x14002d635  jz      short loc_14002D63F
0x14002d637  mov     rcx, rdi; this
0x14002d63a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002d63f  mov     rcx, [rbx+10h]
0x14002d643  jmp     loc_14002D572
0x14002d648  lea     r9, [rsp+350h+var_318]; void *
0x14002d64d  mov     r8, rbx; struct _FLT_RELATED_OBJECTS *
0x14002d650  mov     rdx, rdi; struct _FLT_CALLBACK_DATA *
0x14002d653  mov     rcx, r15; this
0x14002d656  call    ?PostRename@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@PEAXAEAVStackEventTracer@1@@Z; UnionFs::PostRename(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,void *,UnionFs::StackEventTracer &)
0x14002d65b  mov     ebx, eax
0x14002d65d  test    eax, eax
0x14002d65f  jns     short loc_14002D696
0x14002d661  lea     rax, aPushPostRename; "PUSH: Post rename"
0x14002d668  mov     r8, 344000B0A91h; struct UnionFs::StackEventTracer *
0x14002d672  lea     r9, aUnionfsUnionfs_55; "UnionFs::UnionFsFilter::PostSetInfo"
0x14002d679  mov     [rsp+350h+var_330], rax; char *
0x14002d67e  lea     rdx, [rsp+350h+var_318]; int
0x14002d683  mov     ecx, ebx; this
0x14002d685  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002d68a  mov     [r15+18h], ebx
0x14002d68e  mov     qword ptr [r15+20h], 0
0x14002d696  lea     rcx, [rsp+350h+var_318]; this
0x14002d69b  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x14002d6a0  xor     eax, eax
0x14002d6a2  mov     rcx, [rbp+250h+var_28]
0x14002d6a9  xor     rcx, rsp; StackCookie
0x14002d6ac  call    __security_check_cookie
0x14002d6b1  mov     rbx, [rsp+350h+arg_18]
0x14002d6b9  add     rsp, 330h
0x14002d6c0  pop     r15
0x14002d6c2  pop     r14
0x14002d6c4  pop     rdi
0x14002d6c5  pop     rsi
0x14002d6c6  pop     rbp
0x14002d6c7  retn
```
