# UnionFs::UnionFsFilter::PostQueryInfo(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void *,ulong)

- ea: `0x14002c3a0`
- end: `0x14002c9e9`
- name: `?PostQueryInfo@UnionFsFilter@UnionFs@@SA?AW4_FLT_POSTOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAXK@Z`
- size: `1609`
- prototype: `enum _FLT_POSTOP_CALLBACK_STATUS __fastcall(struct _FLT_CALLBACK_DATA *, const struct _FLT_RELATED_OBJECTS *this, UnionFs::QueryInfoContext *, unsigned int)`
- caller_count: `0`
- callee_count: `19`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x140005574`
- `0x1400056b4`
- `0x140005ff8`
- `0x140006168`
- `0x14000efd0`
- `0x14000f7fc`
- `0x14002793c`
- `0x14002c3a0`
- `0x140034f9c`
- `0x140035198`
- `0x140035564`
- `0x1400356bc`
- `0x140035890`
- `0x140056afc`
- `0x140079df4`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007b8b0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002c5c2`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002c97d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002c9a7`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002c5c2`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002c97d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002c9a7`
- `FLTMGR!FltReleaseContext` at `0x14002c7f6`
- `FLTMGR!FltReleaseContext` at `0x14002c7f6`

## string_xrefs

- `0x14002c625`: `PUSH: Post query hard link`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::PostQueryInfo(
        struct _FLT_CALLBACK_DATA *a1,
        struct _FLT_RELATED_OBJECTS *this,
        UnionFs::QueryInfoContext *a3,
        int a4)
{
  unsigned __int64 Iopb; // rdx
  __int64 v8; // rcx
  UnionFs::QueryInfoContext *v9; // rdi
  UnionFs::QueryInfoContext *v10; // rbx
  NTSTATUS Status; // r14d
  struct _FLT_RELATED_OBJECTS *v12; // rax
  struct UnionFs::UfsUnionCtx *v13; // r14
  struct FsFltWil::Details::RundownRefCacheAware *v14; // rdx
  NTSTATUS v15; // esi
  const char *v16; // rax
  __int64 v17; // r8
  __int64 v18; // rdx
  struct FsFltWil::Details::RundownRefCacheAware *v19; // rdx
  __int64 v20; // rcx
  NTSTATUS v21; // esi
  utl::_RefCountBase *v22; // rcx
  struct _FLT_RELATED_OBJECTS *v23; // rax
  UnionFs *v24; // rsi
  LARGE_INTEGER ByteOffset; // r12
  int v26; // eax
  struct UnionFs::UfsUnionCtx *v27; // r8
  PFLT_IO_PARAMETER_BLOCK v28; // rax
  ULONG Length; // ecx
  ULONG v30; // eax
  ULONG v31; // ecx
  __int64 v32; // rcx
  _WORD *v33; // rax
  int v34; // esi
  unsigned int v35; // r12d
  ULONG v36; // esi
  __int64 v37; // rcx
  __int64 v38; // rcx
  struct UnionFs::StackEventTracer *v40; // [rsp+20h] [rbp-E0h]
  struct UnionFs::StackEventTracer *v41; // [rsp+28h] [rbp-D8h]
  struct _FILE_NAME_INFORMATION *v42; // [rsp+28h] [rbp-D8h]
  struct _FILE_NAME_INFORMATION *v43; // [rsp+28h] [rbp-D8h]
  struct UnionFs::StackEventTracer *v44; // [rsp+38h] [rbp-C8h]
  _FILE_EA_INFORMATION v45; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v46[12]; // [rsp+44h] [rbp-BCh] BYREF
  struct UnionFs::UfsUnionCtx *v47; // [rsp+50h] [rbp-B0h]
  unsigned int v48[2]; // [rsp+58h] [rbp-A8h]
  PFLT_CONTEXT Context; // [rsp+60h] [rbp-A0h] BYREF
  char v50[8]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v51[14]; // [rsp+70h] [rbp-90h] BYREF
  struct _FLT_RELATED_OBJECTS *v52; // [rsp+E0h] [rbp-20h]
  utl::_RefCountBase *v53; // [rsp+E8h] [rbp-18h]
  __int64 v54; // [rsp+F0h] [rbp-10h] BYREF
  char v55; // [rsp+F8h] [rbp-8h]
  _BYTE v56[112]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v57; // [rsp+170h] [rbp+70h]
  struct _FLT_CALLBACK_DATA v58; // [rsp+178h] [rbp+78h] BYREF
  _QWORD v59[46]; // [rsp+1F0h] [rbp+F0h]
  unsigned __int16 v60; // [rsp+362h] [rbp+262h]

  *(_QWORD *)&v46[4] = this;
  *(_DWORD *)v46 = a4;
  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)&v58, 0x61C000B0BB4uLL, a1);
  Iopb = a1->Iopb->Parameters.Create.Options - 18;
  if ( (unsigned int)Iopb <= 0x32 && (v8 = 0x4000010000001LL, _bittest64(&v8, Iopb)) )
  {
    v9 = a3;
    v10 = 0;
  }
  else
  {
    v9 = 0;
    if ( !a3 )
      MicrosoftTelemetryAssertTriggeredMsgKM("No COW-I/O sync rundown");
    v10 = a3;
  }
  Status = a1->IoStatus.Status;
  if ( (int)(Status + 0x80000000) >= 0 && Status != -2147483643 || (v46[0] & 1) != 0 )
    goto LABEL_69;
  Iopb = (unsigned __int64)a1->Iopb;
  switch ( *(_DWORD *)(Iopb + 32) )
  {
    case 4:
      *(_DWORD *)(*(_QWORD *)(Iopb + 40) + 32LL) &= ~0x800000u;
      goto LABEL_69;
    case 0x12:
      v22 = (utl::_RefCountBase *)*((_QWORD *)v9 + 2);
      v47 = *(struct UnionFs::UfsUnionCtx **)v9;
      v23 = (struct _FLT_RELATED_OBJECTS *)*((_QWORD *)v9 + 1);
      v53 = v22;
      v52 = v23;
      *((_QWORD *)v9 + 1) = 0;
      *((_QWORD *)v9 + 2) = 0;
      v54 = *((_QWORD *)v9 + 3);
      v55 = *((_BYTE *)v9 + 32);
      wistd::function<void (bool)>::function<void (bool)>(v56, (char *)v9 + 40);
      memset((char *)v9 + 24, 0, 0x88u);
      v24 = *(UnionFs **)&v46[4];
      ByteOffset = a1->Iopb->Parameters.Read.ByteOffset;
      v26 = UnionFs::VirtualizeInternalInfo(
              *(UnionFs **)&v46[4],
              v52,
              v47,
              (const struct UnionFs::UfsStreamHandleCtx *)(ByteOffset.QuadPart + 64),
              (struct _FILE_INTERNAL_INFORMATION *)&v58,
              v41);
      *(_DWORD *)v46 = v26;
      if ( v26 < 0 )
      {
        UnionFs::ProcessTraceStatusPushLocation(
          (UnionFs *)(unsigned int)v26,
          (int)&v58,
          (struct UnionFs::StackEventTracer *)0x604000B0C01LL,
          (unsigned __int64)"UnionFs::UnionFsFilter::PostQueryInfo",
          "PUSH: Handling internal info",
          (const char *)v43);
        a1->IoStatus.Status = *(_DWORD *)v46;
        goto LABEL_22;
      }
      *(_DWORD *)(ByteOffset.QuadPart + 32) &= ~0x800000u;
      v27 = v47;
      LOBYTE(v45.EaSize) = 0;
      if ( (*(_DWORD *)v47 & 1) != 0 && (*(_DWORD *)v47 & 0x20) == 0 )
      {
        v15 = UnionFs::VirtualizeEaInfo(
                v24,
                v52,
                (const struct UnionFs::UfsUnionCtx *)(ByteOffset.QuadPart + 72),
                &v45,
                (struct UnionFs::StackEventTracer *)&v58,
                (struct UnionFs::StackEventTracer *)v43);
        if ( v15 < 0 )
        {
          v16 = "PUSH: Handling EA info";
          v17 = 0x569000B0C1ALL;
          goto LABEL_21;
        }
        v24 = *(UnionFs **)&v46[4];
        v27 = v47;
      }
      v28 = a1->Iopb;
      v18 = ByteOffset.QuadPart + 96;
      *(_QWORD *)v48 = ByteOffset.QuadPart + 96;
      Length = v28->Parameters.Read.Length;
      v30 = *(_DWORD *)(ByteOffset.QuadPart + 96);
      v31 = Length - 100;
      if ( v30 >= v31 )
        v30 = v31;
      v32 = *((_QWORD *)v24 + 4);
      *(_DWORD *)v46 = v30;
      *(_QWORD *)&v46[4] = v32;
      v33 = *(_WORD **)(v32 + 24);
      if ( !v33 || *v33 != 17217 )
        goto LABEL_66;
      if ( v27 )
      {
        v34 = *(_DWORD *)v27;
      }
      else
      {
        UnionFs::UfsStreamHandleCtx::FltGet(&Context, *((_QWORD *)v24 + 3));
        if ( !Context )
          goto LABEL_66;
        v34 = *(_DWORD *)Context;
        FltReleaseContext(Context);
        v32 = *(_QWORD *)&v46[4];
        v18 = ByteOffset.QuadPart + 96;
      }
      if ( (v34 & 1) != 0 )
      {
        *(_QWORD *)(ByteOffset.QuadPart + 80) = 0;
        *(_QWORD *)(ByteOffset.QuadPart + 80) = *(_QWORD *)(v32 + 104);
        v35 = *(_DWORD *)v18;
        v36 = a1->Iopb->Parameters.Read.Length;
        v51[0] = off_14007E928;
        v51[13] = v51;
        UnionFs::StackEventTracer::SetIgnoreStatusCallback(&v58, v50);
        v15 = UnionFs::VirtualizeNameInfo(
                *(UnionFs **)&v46[4],
                v47,
                0,
                v36 - 96,
                v48[0],
                (struct _FILE_NAME_INFORMATION *)v46,
                &v58.Flags,
                v44);
        if ( v60 )
        {
          v37 = v59[15 * --v60];
          v59[15 * v60] = 0;
          if ( v37 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 24LL))(v37);
        }
        v18 = 2147483653LL;
        if ( (int)(v15 + 0x80000000) >= 0 && v15 != -2147483643 )
        {
          v16 = "PUSH: Handling name info";
          v17 = 0x605000B0C4ELL;
          goto LABEL_21;
        }
        if ( Status == -2147483643 || v15 == -2147483643 )
        {
          if ( **(_DWORD **)v48 > v35 )
            v35 = **(_DWORD **)v48;
          **(_DWORD **)v48 = v35;
          a1->IoStatus.Status = -2147483643;
          goto LABEL_67;
        }
      }
LABEL_66:
      a1->IoStatus.Status = Status;
      if ( Status == 260 )
        goto LABEL_23;
LABEL_67:
      a1->IoStatus.Information = (unsigned int)(*(_DWORD *)v46 + 100);
      goto LABEL_23;
    case 0x22:
      *(_DWORD *)(*(_QWORD *)(Iopb + 40) + 48LL) &= ~0x800000u;
      goto LABEL_69;
    case 0x23:
      **(_DWORD **)(Iopb + 40) &= ~0x800000u;
      goto LABEL_69;
    case 0x2E:
      v21 = UnionFs::VirtualizeHardLinkInfo(
              *(UnionFs **)v9,
              *((const struct UnionFs::UfsStreamHandleCtx **)v9 + 1),
              (const struct UnionFs::UfsUnionCtx *)a1,
              &v58,
              v40);
      if ( v21 >= 0 )
        goto LABEL_69;
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v21,
        (int)&v58,
        (struct UnionFs::StackEventTracer *)0x62A000B0C77LL,
        (unsigned __int64)"UnionFs::UnionFsFilter::PostQueryInfo",
        "PUSH: Post query hard link",
        (const char *)v41);
      a1->IoStatus.Status = v21;
      a1->IoStatus.Information = 0;
LABEL_27:
      if ( v10 )
      {
        FsFltWil::Details::ReleaseRundownProtectionCacheAware(v10, v19);
        v20 = *((_QWORD *)v10 + 16);
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 24LL))(v20);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 896), v10);
      }
      goto LABEL_74;
  }
  if ( *(_DWORD *)(Iopb + 32) != 68 )
  {
    if ( *(_DWORD *)(Iopb + 32) == 70 || *(_DWORD *)(Iopb + 32) == 77 )
      *(_DWORD *)(*(_QWORD *)(Iopb + 40) + 56LL) &= ~0x800000u;
    goto LABEL_69;
  }
  v12 = (struct _FLT_RELATED_OBJECTS *)*((_QWORD *)v9 + 1);
  v13 = *(struct UnionFs::UfsUnionCtx **)v9;
  v53 = (utl::_RefCountBase *)*((_QWORD *)v9 + 2);
  v52 = v12;
  *((_QWORD *)v9 + 1) = 0;
  *((_QWORD *)v9 + 2) = 0;
  v54 = *((_QWORD *)v9 + 3);
  v55 = *((_BYTE *)v9 + 32);
  wistd::function<void (bool)>::function<void (bool)>(v56, (char *)v9 + 40);
  memset((char *)v9 + 24, 0, 0x88u);
  v15 = UnionFs::VirtualizeStatInfo(
          (UnionFs *)this,
          v52,
          v13,
          (const struct UnionFs::UfsStreamHandleCtx *)a1->Iopb->Parameters.Read.ByteOffset.QuadPart,
          (struct _FILE_STAT_INFORMATION *)&v58,
          v41);
  if ( v15 < 0 )
  {
    v16 = "PUSH: Post query stat info";
    v17 = 0x2BF000B0BE8LL;
LABEL_21:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v15,
      (int)&v58,
      (struct UnionFs::StackEventTracer *)v17,
      (unsigned __int64)"UnionFs::UnionFsFilter::PostQueryInfo",
      v16,
      (const char *)v42);
    a1->IoStatus.Status = v15;
LABEL_22:
    a1->IoStatus.Information = 0;
LABEL_23:
    FsFltWil::Details::ReleaseRundownProtectionCacheAware(
      (FsFltWil::Details *)&v54,
      (struct FsFltWil::Details::RundownRefCacheAware *)v18);
    if ( v57 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 24LL))(v57);
    if ( v53 )
      utl::_RefCountBase::_DecStrong(v53);
    goto LABEL_27;
  }
  FsFltWil::Details::ReleaseRundownProtectionCacheAware((FsFltWil::Details *)&v54, v14);
  if ( v57 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 24LL))(v57);
  if ( v53 )
    utl::_RefCountBase::_DecStrong(v53);
LABEL_69:
  if ( v10 )
  {
    FsFltWil::Details::ReleaseRundownProtectionCacheAware(v10, (struct FsFltWil::Details::RundownRefCacheAware *)Iopb);
    v38 = *((_QWORD *)v10 + 16);
    if ( v38 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 24LL))(v38);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 896), v10);
  }
  if ( v9 )
  {
LABEL_74:
    UnionFs::QueryInfoContext::~QueryInfoContext(v9);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 608), v9);
  }
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)&v58);
  return 0;
}

```

## disassembly

```asm
0x14002c3a0  mov     [rsp-8+arg_10], rbx
0x14002c3a5  push    rbp
0x14002c3a6  push    rsi
0x14002c3a7  push    rdi
0x14002c3a8  push    r12
0x14002c3aa  push    r13
0x14002c3ac  push    r14
0x14002c3ae  push    r15
0x14002c3b0  lea     rbp, [rsp-370h]
0x14002c3b8  sub     rsp, 470h
0x14002c3bf  mov     rax, cs:__security_cookie
0x14002c3c6  xor     rax, rsp
0x14002c3c9  mov     [rbp+3A0h+var_38], rax
0x14002c3d0  mov     rsi, r8
0x14002c3d3  mov     qword ptr [rsp+4A0h+var_45C+4], rdx
0x14002c3d8  mov     r8, rcx; struct _FLT_CALLBACK_DATA *
0x14002c3db  mov     dword ptr [rsp+4A0h+var_45C], r9d
0x14002c3e0  mov     r12, rdx
0x14002c3e3  mov     r13, rcx
0x14002c3e6  lea     rcx, [rbp+3A0h+var_328]; this
0x14002c3ea  mov     rdx, 61C000B0BB4h; unsigned __int64
0x14002c3f4  call    ??0StackEventTracer@UnionFs@@QEAA@_KPEBU_FLT_CALLBACK_DATA@@@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64,_FLT_CALLBACK_DATA const *)
0x14002c3f9  mov     rax, [r13+10h]
0x14002c3fd  mov     edx, [rax+20h]
0x14002c400  add     edx, 0FFFFFFEEh
0x14002c403  cmp     edx, 32h ; '2'
0x14002c406  ja      short loc_14002C423
0x14002c408  mov     rcx, 4000010000001h
0x14002c412  bt      rcx, rdx
0x14002c416  jnb     short loc_14002C423
0x14002c418  xor     r15d, r15d
0x14002c41b  mov     rdi, rsi
0x14002c41e  mov     ebx, r15d
0x14002c421  jmp     short loc_14002C43D
0x14002c423  xor     r15d, r15d
0x14002c426  mov     edi, r15d
0x14002c429  test    rsi, rsi
0x14002c42c  jnz     short loc_14002C43A
0x14002c42e  lea     rcx, aNoCowIOSyncRun; "No COW-I/O sync rundown"
0x14002c435  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14002c43a  mov     rbx, rsi
0x14002c43d  mov     r14d, [r13+18h]
0x14002c441  mov     ecx, 80000000h
0x14002c446  lea     eax, [r14+rcx]
0x14002c44a  test    ecx, eax
0x14002c44c  jnz     short loc_14002C45B
0x14002c44e  cmp     r14d, 80000005h
0x14002c455  jnz     loc_14002C947
0x14002c45b  test    [rsp+4A0h+var_45C], 1
0x14002c460  jnz     loc_14002C947
0x14002c466  mov     rdx, [r13+10h]; struct FsFltWil::Details::RundownRefCacheAware *
0x14002c46a  mov     ecx, [rdx+20h]
0x14002c46d  sub     ecx, 4
0x14002c470  jz      loc_14002C93E
0x14002c476  sub     ecx, 0Eh
0x14002c479  jz      loc_14002C675
0x14002c47f  sub     ecx, 10h
0x14002c482  jz      loc_14002C667
0x14002c488  sub     ecx, 1
0x14002c48b  jz      loc_14002C65A
0x14002c491  sub     ecx, 0Bh
0x14002c494  jz      loc_14002C608
0x14002c49a  sub     ecx, 16h
0x14002c49d  jz      short loc_14002C4BB
0x14002c49f  sub     ecx, 2
0x14002c4a2  jz      short loc_14002C4AD
0x14002c4a4  cmp     ecx, 7
0x14002c4a7  jnz     loc_14002C947
0x14002c4ad  mov     rax, [rdx+28h]
0x14002c4b1  btr     dword ptr [rax+38h], 17h
0x14002c4b6  jmp     loc_14002C947
0x14002c4bb  mov     rcx, [rdi+10h]
0x14002c4bf  lea     rdx, [rdi+28h]
0x14002c4c3  mov     rax, [rdi+8]
0x14002c4c7  mov     r14, [rdi]
0x14002c4ca  mov     [rbp+3A0h+var_3B8], rcx
0x14002c4ce  lea     rcx, [rbp+3A0h+var_3A0]
0x14002c4d2  mov     [rbp+3A0h+var_3C0], rax
0x14002c4d6  mov     [rdi+8], r15
0x14002c4da  mov     [rdi+10h], r15
0x14002c4de  mov     rax, [rdi+18h]
0x14002c4e2  mov     [rbp+3A0h+var_3B0], rax
0x14002c4e6  mov     al, [rdi+20h]
0x14002c4e9  mov     [rbp+3A0h+var_3A8], al
0x14002c4ec  call    ??0?$function@$$A6AX_N@Z@wistd@@QEAA@AEBV01@@Z; wistd::function<void (bool)>::function<void (bool)>(wistd::function<void (bool)> const &)
0x14002c4f1  xor     edx, edx; Val
0x14002c4f3  lea     rcx, [rdi+18h]; void *
0x14002c4f7  mov     r8d, 88h; Size
0x14002c4fd  call    memset
0x14002c502  mov     r9, [r13+10h]
0x14002c506  lea     rax, [rbp+3A0h+var_328]
0x14002c50a  mov     rdx, [rbp+3A0h+var_3C0]; struct _FLT_RELATED_OBJECTS *
0x14002c50e  mov     r8, r14; struct UnionFs::UfsUnionCtx *
0x14002c511  mov     rcx, r12; this
0x14002c514  mov     [rsp+4A0h+var_480], rax; struct _FILE_STAT_INFORMATION *
0x14002c519  mov     r9, [r9+28h]; struct UnionFs::UfsStreamHandleCtx *
0x14002c51d  call    ?VirtualizeStatInfo@UnionFs@@YAJAEBU_FLT_RELATED_OBJECTS@@AEAVUfsUnionCtx@1@AEBVUfsStreamHandleCtx@1@AEAU_FILE_STAT_INFORMATION@@AEAVStackEventTracer@1@@Z; UnionFs::VirtualizeStatInfo(_FLT_RELATED_OBJECTS const &,UnionFs::UfsUnionCtx &,UnionFs::UfsStreamHandleCtx const &,_FILE_STAT_INFORMATION &,UnionFs::StackEventTracer &)
0x14002c522  mov     esi, eax
0x14002c524  test    eax, eax
0x14002c526  jns     loc_14002C5D3
0x14002c52c  lea     rax, aPushPostQueryS; "PUSH: Post query stat info"
0x14002c533  mov     r8, 2BF000B0BE8h; struct UnionFs::StackEventTracer *
0x14002c53d  lea     r9, aUnionfsUnionfs_40; "UnionFs::UnionFsFilter::PostQueryInfo"
0x14002c544  mov     [rsp+4A0h+var_480], rax; char *
0x14002c549  lea     rdx, [rbp+3A0h+var_328]; int
0x14002c54d  mov     ecx, esi; this
0x14002c54f  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002c554  mov     [r13+18h], esi
0x14002c558  mov     [r13+20h], r15
0x14002c55c  lea     rcx, [rbp+3A0h+var_3B0]; this
0x14002c560  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14002c565  mov     rcx, [rbp+3A0h+var_330]
0x14002c569  test    rcx, rcx
0x14002c56c  jz      short loc_14002C57A
0x14002c56e  mov     rax, [rcx]
0x14002c571  mov     rax, [rax+18h]
0x14002c575  call    _guard_dispatch_icall
0x14002c57a  mov     rcx, [rbp+3A0h+var_3B8]; this
0x14002c57e  test    rcx, rcx
0x14002c581  jz      short loc_14002C588
0x14002c583  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002c588  test    rbx, rbx
0x14002c58b  jz      loc_14002C98E
0x14002c591  mov     rcx, rbx; this
0x14002c594  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14002c599  mov     rcx, [rbx+80h]
0x14002c5a0  test    rcx, rcx
0x14002c5a3  jz      short loc_14002C5B1
0x14002c5a5  mov     rax, [rcx]
0x14002c5a8  mov     rax, [rax+18h]
0x14002c5ac  call    _guard_dispatch_icall
0x14002c5b1  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14002c5b8  mov     rdx, rbx; Entry
0x14002c5bb  add     rcx, 380h; Lookaside
0x14002c5c2  call    cs:__imp_ExFreeToLookasideListEx
0x14002c5c9  nop     dword ptr [rax+rax+00h]
0x14002c5ce  jmp     loc_14002C98E
0x14002c5d3  lea     rcx, [rbp+3A0h+var_3B0]; this
0x14002c5d7  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x14002c5dc  mov     rcx, [rbp+3A0h+var_330]
0x14002c5e0  test    rcx, rcx
0x14002c5e3  jz      short loc_14002C5F1
0x14002c5e5  mov     rax, [rcx]
0x14002c5e8  mov     rax, [rax+18h]
0x14002c5ec  call    _guard_dispatch_icall
0x14002c5f1  mov     rcx, [rbp+3A0h+var_3B8]; this
0x14002c5f5  test    rcx, rcx
0x14002c5f8  jz      loc_14002C947
0x14002c5fe  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14002c603  jmp     loc_14002C947
0x14002c608  mov     rdx, [rdi+8]; struct UnionFs::UfsStreamHandleCtx *
0x14002c60c  lea     r9, [rbp+3A0h+var_328]; struct _FLT_CALLBACK_DATA *
0x14002c610  mov     rcx, [rdi]; this
0x14002c613  mov     r8, r13; struct UnionFs::UfsUnionCtx *
0x14002c616  call    ?VirtualizeHardLinkInfo@UnionFs@@YAJAEBVUfsStreamHandleCtx@1@AEBVUfsUnionCtx@1@AEAU_FLT_CALLBACK_DATA@@AEAVStackEventTracer@1@@Z; UnionFs::VirtualizeHardLinkInfo(UnionFs::UfsStreamHandleCtx const &,UnionFs::UfsUnionCtx const &,_FLT_CALLBACK_DATA &,UnionFs::StackEventTracer &)
0x14002c61b  mov     esi, eax
0x14002c61d  test    eax, eax
0x14002c61f  jns     loc_14002C947
0x14002c625  lea     rax, aPushPostQueryH; "PUSH: Post query hard link"
0x14002c62c  mov     r8, 62A000B0C77h; struct UnionFs::StackEventTracer *
0x14002c636  lea     r9, aUnionfsUnionfs_40; "UnionFs::UnionFsFilter::PostQueryInfo"
0x14002c63d  mov     [rsp+4A0h+var_480], rax; char *
0x14002c642  lea     rdx, [rbp+3A0h+var_328]; int
0x14002c646  mov     ecx, esi; this
0x14002c648  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002c64d  mov     [r13+18h], esi
0x14002c651  mov     [r13+20h], r15
0x14002c655  jmp     loc_14002C588
0x14002c65a  mov     rax, [rdx+28h]
0x14002c65e  btr     dword ptr [rax], 17h
0x14002c662  jmp     loc_14002C947
0x14002c667  mov     rax, [rdx+28h]
0x14002c66b  btr     dword ptr [rax+30h], 17h
0x14002c670  jmp     loc_14002C947
0x14002c675  mov     rax, [rdi]
0x14002c678  lea     rdx, [rdi+28h]
0x14002c67c  mov     rcx, [rdi+10h]
0x14002c680  mov     [rsp+4A0h+var_450], rax
0x14002c685  mov     rax, [rdi+8]
0x14002c689  mov     [rbp+3A0h+var_3B8], rcx
0x14002c68d  lea     rcx, [rbp+3A0h+var_3A0]
0x14002c691  mov     [rbp+3A0h+var_3C0], rax
0x14002c695  mov     [rdi+8], r15
0x14002c699  mov     [rdi+10h], r15
0x14002c69d  mov     rax, [rdi+18h]
0x14002c6a1  mov     [rbp+3A0h+var_3B0], rax
0x14002c6a5  mov     al, [rdi+20h]
0x14002c6a8  mov     [rbp+3A0h+var_3A8], al
0x14002c6ab  call    ??0?$function@$$A6AX_N@Z@wistd@@QEAA@AEBV01@@Z; wistd::function<void (bool)>::function<void (bool)>(wistd::function<void (bool)> const &)
0x14002c6b0  xor     edx, edx; Val
0x14002c6b2  lea     rcx, [rdi+18h]; void *
0x14002c6b6  mov     r8d, 88h; Size
0x14002c6bc  call    memset
0x14002c6c1  mov     rax, [r13+10h]
0x14002c6c5  mov     rsi, qword ptr [rsp+4A0h+var_45C+4]
0x14002c6ca  mov     r8, [rsp+4A0h+var_450]; struct UnionFs::UfsUnionCtx *
0x14002c6cf  mov     rcx, rsi; this
0x14002c6d2  mov     rdx, [rbp+3A0h+var_3C0]; struct _FLT_RELATED_OBJECTS *
0x14002c6d6  mov     r12, [rax+28h]
0x14002c6da  lea     rax, [rbp+3A0h+var_328]
0x14002c6de  mov     [rsp+4A0h+var_480], rax; struct _FILE_INTERNAL_INFORMATION *
0x14002c6e3  lea     r9, [r12+40h]; struct UnionFs::UfsStreamHandleCtx *
0x14002c6e8  call    ?VirtualizeInternalInfo@UnionFs@@YAJAEBU_FLT_RELATED_OBJECTS@@AEAVUfsUnionCtx@1@AEBVUfsStreamHandleCtx@1@AEAU_FILE_INTERNAL_INFORMATION@@AEAVStackEventTracer@1@@Z; UnionFs::VirtualizeInternalInfo(_FLT_RELATED_OBJECTS const &,UnionFs::UfsUnionCtx &,UnionFs::UfsStreamHandleCtx const &,_FILE_INTERNAL_INFORMATION &,UnionFs::StackEventTracer &)
0x14002c6ed  mov     dword ptr [rsp+4A0h+var_45C], eax
0x14002c6f1  test    eax, eax
0x14002c6f3  jns     short loc_14002C72A
0x14002c6f5  lea     rcx, aPushHandlingIn; "PUSH: Handling internal info"
0x14002c6fc  mov     r8, 604000B0C01h; struct UnionFs::StackEventTracer *
0x14002c706  mov     [rsp+4A0h+var_480], rcx; char *
0x14002c70b  lea     r9, aUnionfsUnionfs_40; "UnionFs::UnionFsFilter::PostQueryInfo"
0x14002c712  mov     ecx, eax; this
0x14002c714  lea     rdx, [rbp+3A0h+var_328]; int
0x14002c718  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002c71d  mov     eax, dword ptr [rsp+4A0h+var_45C]
0x14002c721  mov     [r13+18h], eax
0x14002c725  jmp     loc_14002C558
0x14002c72a  btr     dword ptr [r12+20h], 17h
0x14002c731  mov     r8, [rsp+4A0h+var_450]
0x14002c736  mov     byte ptr [rsp+4A0h+var_460.EaSize], r15b
0x14002c73b  mov     eax, [r8]
0x14002c73e  test    al, 1
0x14002c740  jz      short loc_14002C78B
0x14002c742  test    al, 20h
0x14002c744  jnz     short loc_14002C78B
0x14002c746  mov     rdx, [rbp+3A0h+var_3C0]; struct _FLT_RELATED_OBJECTS *
0x14002c74a  lea     rax, [rbp+3A0h+var_328]
0x14002c74e  lea     r8, [r12+48h]; struct UnionFs::UfsUnionCtx *
0x14002c753  mov     [rsp+4A0h+var_480], rax; struct UnionFs::StackEventTracer *
0x14002c758  lea     r9, [rsp+4A0h+var_460]; struct _FILE_EA_INFORMATION *
0x14002c75d  mov     rcx, rsi; this
0x14002c760  call    ?VirtualizeEaInfo@UnionFs@@YAJAEBU_FLT_RELATED_OBJECTS@@AEBVUfsUnionCtx@1@AEAU_FILE_EA_INFORMATION@@PEA_NAEAVStackEventTracer@1@@Z; UnionFs::VirtualizeEaInfo(_FLT_RELATED_OBJECTS const &,UnionFs::UfsUnionCtx const &,_FILE_EA_INFORMATION &,bool *,UnionFs::StackEventTracer &)
0x14002c765  mov     esi, eax
0x14002c767  test    eax, eax
0x14002c769  jns     short loc_14002C781
0x14002c76b  lea     rax, aPushHandlingEa; "PUSH: Handling EA info"
0x14002c772  mov     r8, 569000B0C1Ah
0x14002c77c  jmp     loc_14002C53D
0x14002c781  mov     rsi, qword ptr [rsp+4A0h+var_45C+4]
0x14002c786  mov     r8, [rsp+4A0h+var_450]
0x14002c78b  mov     rax, [r13+10h]
0x14002c78f  lea     rdx, [r12+60h]
0x14002c794  mov     qword ptr [rsp+4A0h+var_448], rdx
0x14002c799  mov     ecx, [rax+18h]
0x14002c79c  mov     eax, [rdx]
0x14002c79e  add     ecx, 0FFFFFF9Ch
0x14002c7a1  cmp     eax, ecx
0x14002c7a3  cmovnb  eax, ecx
0x14002c7a6  mov     rcx, [rsi+20h]
0x14002c7aa  mov     dword ptr [rsp+4A0h+var_45C], eax
0x14002c7ae  mov     qword ptr [rsp+4A0h+var_45C+4], rcx
0x14002c7b3  mov     rax, [rcx+18h]
0x14002c7b7  test    rax, rax
0x14002c7ba  jz      loc_14002C91D
0x14002c7c0  mov     r9d, 4341h
0x14002c7c6  cmp     [rax], r9w
0x14002c7ca  jnz     loc_14002C91D
0x14002c7d0  test    r8, r8
0x14002c7d3  jnz     short loc_14002C80E
0x14002c7d5  mov     rdx, [rsi+18h]
0x14002c7d9  mov     r8, rcx
0x14002c7dc  lea     rcx, [rsp+4A0h+Context]
0x14002c7e1  call    ?FltGet@UfsStreamHandleCtx@UnionFs@@SA?AV?$unique_ptr@VUfsStreamHandleCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@@Z; UnionFs::UfsStreamHandleCtx::FltGet(_FLT_INSTANCE const &,_FILE_OBJECT const &)
0x14002c7e6  mov     rcx, [rsp+4A0h+Context]; Context
0x14002c7eb  test    rcx, rcx
0x14002c7ee  jz      loc_14002C91D
0x14002c7f4  mov     esi, [rcx]
0x14002c7f6  call    cs:__imp_FltReleaseContext
0x14002c7fd  nop     dword ptr [rax+rax+00h]
0x14002c802  mov     rcx, qword ptr [rsp+4A0h+var_45C+4]
0x14002c807  lea     rdx, [r12+60h]
0x14002c80c  jmp     short loc_14002C811
0x14002c80e  mov     esi, [r8]
0x14002c811  test    sil, 1
0x14002c815  jz      loc_14002C91D
0x14002c81b  xor     eax, eax
0x14002c81d  mov     [r12+50h], rax
0x14002c822  mov     rax, [rcx+68h]
0x14002c826  lea     rcx, [rbp+3A0h+var_328]
0x14002c82a  mov     [r12+50h], rax
0x14002c82f  mov     rax, [r13+10h]
0x14002c833  mov     r12d, [rdx]
0x14002c836  lea     rdx, [rsp+4A0h+var_438]
0x14002c83b  mov     esi, [rax+18h]
0x14002c83e  lea     rax, off_14007E928
0x14002c845  mov     [rsp+4A0h+var_430], rax
0x14002c84a  add     esi, 0FFFFFFA0h
0x14002c84d  lea     rax, [rsp+4A0h+var_430]
0x14002c852  mov     [rbp+3A0h+var_3C8], rax
0x14002c856  call    ?SetIgnoreStatusCallback@StackEventTracer@UnionFs@@QEAAXV?$function@$$A6A_NJ@Z@wistd@@@Z; UnionFs::StackEventTracer::SetIgnoreStatusCallback(wistd::function<bool (long)>)
0x14002c85b  mov     rdx, [rsp+4A0h+var_450]; struct UnionFs::UfsShadowFileObject *
0x14002c860  lea     rax, [rbp+3A0h+var_328]
0x14002c864  mov     rcx, qword ptr [rsp+4A0h+var_45C+4]; this
0x14002c869  mov     r9d, esi; bool
0x14002c86c  mov     [rsp+4A0h+var_470], rax; unsigned int *
0x14002c871  xor     r8d, r8d; struct UnionFs::UfsStreamHandleCtx *
0x14002c874  lea     rax, [rsp+4A0h+var_45C]
0x14002c879  mov     [rsp+4A0h+var_478], rax; struct _FILE_NAME_INFORMATION *
0x14002c87e  mov     rax, qword ptr [rsp+4A0h+var_448]
0x14002c883  mov     [rsp+4A0h+var_480], rax; unsigned int
0x14002c888  call    ?VirtualizeNameInfo@UnionFs@@YAJAEBVUfsShadowFileObject@1@AEBVUfsStreamHandleCtx@1@_NKAEAU_FILE_NAME_INFORMATION@@AEAKAEAVStackEventTracer@1@@Z; UnionFs::VirtualizeNameInfo(UnionFs::UfsShadowFileObject const &,UnionFs::UfsStreamHandleCtx const &,bool,ulong,_FILE_NAME_INFORMATION &,ulong &,UnionFs::StackEventTracer &)
  ... truncated ...
```
