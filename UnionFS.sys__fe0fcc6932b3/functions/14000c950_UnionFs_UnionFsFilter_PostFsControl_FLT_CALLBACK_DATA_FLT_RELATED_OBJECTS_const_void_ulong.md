# UnionFs::UnionFsFilter::PostFsControl(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void *,ulong)

- ea: `0x14000c950`
- end: `0x14000cb3c`
- name: `?PostFsControl@UnionFsFilter@UnionFs@@SA?AW4_FLT_POSTOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAXK@Z`
- size: `492`
- prototype: `__int64 __fastcall(struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *, const struct UnionFs::UfsStreamHandleCtx **this, char)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400056b4`
- `0x1400060b4`
- `0x140006168`
- `0x14000c950`
- `0x14000f6a0`
- `0x140056c7c`
- `0x14007a114`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000ca8d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000cad1`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000cafb`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000ca8d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000cad1`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14000cafb`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::PostFsControl(
        struct _FLT_CALLBACK_DATA *a1,
        const struct _FLT_RELATED_OBJECTS *a2,
        const struct UnionFs::UfsStreamHandleCtx **this,
        char a4)
{
  const struct UnionFs::UfsStreamHandleCtx **v8; // rbx
  NTSTATUS Status; // ecx
  __int64 v10; // rdx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  NTSTATUS v12; // ebp
  struct FsFltWil::Details::RundownRefCacheAware *v13; // rdx
  const struct UnionFs::UfsStreamHandleCtx *v14; // rcx
  const struct UnionFs::UfsStreamHandleCtx *v15; // rcx
  struct UnionFs::StackEventTracer *v17; // [rsp+28h] [rbp-320h]
  char v18[4]; // [rsp+30h] [rbp-318h] BYREF

  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v18, 0x76200010BD0uLL, a1);
  if ( a1->Iopb->Parameters.Read.ByteOffset.LowPart == 590059 )
  {
    v8 = this;
    this = 0;
  }
  else
  {
    v8 = 0;
    if ( !this )
      MicrosoftTelemetryAssertTriggeredMsgKM("No COW-I/O sync rundown");
  }
  Status = a1->IoStatus.Status;
  v10 = 0x80000000LL;
  if ( ((int)(Status + 0x80000000) < 0 || Status == -2147483643) && (a4 & 1) == 0 )
  {
    Iopb = a1->Iopb;
    if ( Iopb->Parameters.Read.ByteOffset.LowPart == 590059 )
    {
      v12 = UnionFs::UnionFsFilter::VirtualizeUSNInfo(
              (UnionFs::UnionFsFilter *)v18,
              a2,
              v8[1],
              *v8,
              (struct USN_RECORD_V2 *)Iopb->Parameters.Create.EaBuffer,
              (struct UnionFs::StackEventTracer *)v18);
      if ( v12 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v12,
          (int)v18,
          (struct UnionFs::StackEventTracer *)0x76100010C00LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PostFsControl",
          "PUSH: Post USN info virtualization",
          (const char *)v17);
        a1->IoStatus.Status = v12;
        a1->IoStatus.Information = 0;
        if ( this )
        {
          FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)this, v13);
          v14 = this[16];
          if ( v14 )
            (*(void (__fastcall **)(const struct UnionFs::UfsStreamHandleCtx *))(*(_QWORD *)v14 + 24LL))(v14);
          ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 896), this);
        }
LABEL_19:
        UnionFs::QueryUsnContext::~QueryUsnContext((UnionFs::QueryUsnContext *)v8);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 704), v8);
        goto LABEL_20;
      }
    }
  }
  if ( this )
  {
    FsFltWil::Details::ReleaseRundownProtectionCacheAware(
      (FsFltWil::Details *)this,
      (struct FsFltWil::Details::RundownRefCacheAware *)v10);
    v15 = this[16];
    if ( v15 )
      (*(void (__fastcall **)(const struct UnionFs::UfsStreamHandleCtx *))(*(_QWORD *)v15 + 24LL))(v15);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 896), this);
  }
  if ( v8 )
    goto LABEL_19;
LABEL_20:
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v18);
  return 0;
}

```

## disassembly

```asm
0x14000c950  mov     [rsp+arg_10], rbx
0x14000c955  mov     [rsp+arg_18], rbp
0x14000c95a  push    rsi
0x14000c95b  push    rdi
0x14000c95c  push    r14
0x14000c95e  sub     rsp, 330h
0x14000c965  mov     rax, cs:__security_cookie
0x14000c96c  xor     rax, rsp
0x14000c96f  mov     [rsp+348h+var_28], rax
0x14000c977  mov     rdi, r8
0x14000c97a  mov     r14, rdx
0x14000c97d  mov     r8, rcx; struct _FLT_CALLBACK_DATA *
0x14000c980  mov     rsi, rcx
0x14000c983  lea     rcx, [rsp+348h+var_318]; this
0x14000c988  mov     rdx, 76200010BD0h; unsigned __int64
0x14000c992  mov     ebp, r9d
0x14000c995  call    ??0StackEventTracer@UnionFs@@QEAA@_KPEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64,_FLT_CALLBACK_DATA const *)
0x14000c99a  mov     rax, [rsi+10h]
0x14000c99e  cmp     dword ptr [rax+28h], 900EBh
0x14000c9a5  jz      short loc_14000C9BC
0x14000c9a7  xor     ebx, ebx
0x14000c9a9  test    rdi, rdi
0x14000c9ac  jnz     short loc_14000C9C1
0x14000c9ae  lea     rcx, aNoCowIOSyncRun; "No COW-I/O sync rundown"
0x14000c9b5  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14000c9ba  jmp     short loc_14000C9C1
0x14000c9bc  mov     rbx, rdi
0x14000c9bf  xor     edi, edi
0x14000c9c1  mov     ecx, [rsi+18h]
0x14000c9c4  mov     edx, 80000000h; struct FsFltWil::Details::RundownRefCacheAware *
0x14000c9c9  lea     eax, [rcx+rdx]
0x14000c9cc  test    edx, eax
0x14000c9ce  jnz     short loc_14000C9DC
0x14000c9d0  cmp     ecx, 80000005h
0x14000c9d6  jnz     loc_14000CA9B
0x14000c9dc  test    bpl, 1
0x14000c9e0  jnz     loc_14000CA9B
0x14000c9e6  mov     rax, [rsi+10h]
0x14000c9ea  cmp     dword ptr [rax+28h], 900EBh
0x14000c9f1  jnz     loc_14000CA9B
0x14000c9f7  mov     rax, [rax+38h]
0x14000c9fb  lea     rcx, [rsp+348h+var_318]; this
0x14000ca00  mov     r9, [rbx]; struct UnionFs::UfsStreamHandleCtx *
0x14000ca03  mov     rdx, r14; struct _FLT_RELATED_OBJECTS *
0x14000ca06  mov     r8, [rbx+8]; struct UnionFs::UfsUnionCtx *
0x14000ca0a  mov     [rsp+348h+var_320], rcx; char *
0x14000ca0f  mov     [rsp+348h+var_328], rax; struct USN_RECORD_V2 *
0x14000ca14  call    ?VirtualizeUSNInfo@UnionFsFilter@UnionFs@@QEAAJAEBU_FLT_RELATED_OBJECTS@@AEAVUfsUnionCtx@2@AEBVUfsStreamHandleCtx@2@AEAUUSN_RECORD_V2@@AEAVStackEventTracer@2@@Z; UnionFs::UnionFsFilter::VirtualizeUSNInfo(_FLT_RELATED_OBJECTS const &,UnionFs::UfsUnionCtx &,UnionFs::UfsStreamHandleCtx const &,USN_RECORD_V2 &,UnionFs::StackEventTracer &)
0x14000ca19  mov     ebp, eax
0x14000ca1b  test    eax, eax
0x14000ca1d  jns     short loc_14000CA9B
0x14000ca1f  lea     rax, aPushPostUsnInf; "PUSH: Post USN info virtualization"
0x14000ca26  mov     r8, 76100010C00h; struct UnionFs::StackEventTracer *
0x14000ca30  lea     r9, aUnionfsUnionfs_39; "UnionFs::UnionFsFilter::PostFsControl"
0x14000ca37  mov     [rsp+348h+var_328], rax; char *
0x14000ca3c  lea     rdx, [rsp+348h+var_318]; int
0x14000ca41  mov     ecx, ebp; this
0x14000ca43  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14000ca48  mov     [rsi+18h], ebp
0x14000ca4b  mov     qword ptr [rsi+20h], 0
0x14000ca53  test    rdi, rdi
0x14000ca56  jz      loc_14000CAE2
0x14000ca5c  mov     rcx, rdi; this
0x14000ca5f  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14000ca64  mov     rcx, [rdi+80h]
0x14000ca6b  test    rcx, rcx
0x14000ca6e  jz      short loc_14000CA7C
0x14000ca70  mov     rax, [rcx]
0x14000ca73  mov     rax, [rax+18h]
0x14000ca77  call    _guard_dispatch_icall
0x14000ca7c  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000ca83  mov     rdx, rdi; Entry
0x14000ca86  add     rcx, 380h; Lookaside
0x14000ca8d  call    cs:__imp_ExFreeToLookasideListEx
0x14000ca94  nop     dword ptr [rax+rax+00h]
0x14000ca99  jmp     short loc_14000CAE2
0x14000ca9b  test    rdi, rdi
0x14000ca9e  jz      short loc_14000CADD
0x14000caa0  mov     rcx, rdi; this
0x14000caa3  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14000caa8  mov     rcx, [rdi+80h]
0x14000caaf  test    rcx, rcx
0x14000cab2  jz      short loc_14000CAC0
0x14000cab4  mov     rax, [rcx]
0x14000cab7  mov     rax, [rax+18h]
0x14000cabb  call    _guard_dispatch_icall
0x14000cac0  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000cac7  mov     rdx, rdi; Entry
0x14000caca  add     rcx, 380h; Lookaside
0x14000cad1  call    cs:__imp_ExFreeToLookasideListEx
0x14000cad8  nop     dword ptr [rax+rax+00h]
0x14000cadd  test    rbx, rbx
0x14000cae0  jz      short loc_14000CB07
0x14000cae2  mov     rcx, rbx; this
0x14000cae5  call    ??1QueryUsnContext@UnionFs@@QEAA@XZ; UnionFs::QueryUsnContext::~QueryUsnContext(void)
0x14000caea  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14000caf1  mov     rdx, rbx; Entry
0x14000caf4  add     rcx, 2C0h; Lookaside
0x14000cafb  call    cs:__imp_ExFreeToLookasideListEx
0x14000cb02  nop     dword ptr [rax+rax+00h]
0x14000cb07  lea     rcx, [rsp+348h+var_318]; this
0x14000cb0c  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x14000cb11  xor     eax, eax
0x14000cb13  mov     rcx, [rsp+348h+var_28]
0x14000cb1b  xor     rcx, rsp; StackCookie
0x14000cb1e  call    __security_check_cookie
0x14000cb23  lea     r11, [rsp+348h+var_18]
0x14000cb2b  mov     rbx, [r11+30h]
0x14000cb2f  mov     rbp, [r11+38h]
0x14000cb33  mov     rsp, r11
0x14000cb36  pop     r14
0x14000cb38  pop     rdi
0x14000cb39  pop     rsi
0x14000cb3a  retn
```
