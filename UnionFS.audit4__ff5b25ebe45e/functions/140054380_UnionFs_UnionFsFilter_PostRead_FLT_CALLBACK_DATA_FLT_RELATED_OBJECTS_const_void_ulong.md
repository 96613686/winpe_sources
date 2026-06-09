# UnionFs::UnionFsFilter::PostRead(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void *,ulong)

- ea: `0x140054380`
- end: `0x1400545a4`
- name: `?PostRead@UnionFsFilter@UnionFs@@SA?AW4_FLT_POSTOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAXK@Z`
- size: `548`
- prototype: `FLT_POSTOP_CALLBACK_STATUS __stdcall(PFLT_CALLBACK_DATA Data, PCFLT_RELATED_OBJECTS FltObjects, PVOID CompletionContext, FLT_POST_OPERATION_FLAGS Flags)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000110c`
- `0x140054380`
- `0x140079d44`
- `0x14007a0c0`
- `0x14007a114`
- `0x14007b2b0`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400543ad`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005441b`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400543ad`
- `ntoskrnl!KeGetCurrentIrql` at `0x14005441b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005457d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14005457d`
- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x1400543e9`
- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x1400543e9`

## string_xrefs

- `0x14005443b`: `onecore\base\fs\unionfs\sys\read.cpp`
- `0x140054401`: `Failed to post read completion processing`
- `0x140054446`: `UnionFs::UnionFsFilter::PostRead`
- `0x140054503`: `!shadowFileObject->PrivateCacheMap || (shadowFileObject->PrivateCacheMap == backingFileObject->PrivateCacheMap)`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::PostRead(
        PFLT_CALLBACK_DATA Data,
        struct _FLT_RELATED_OBJECTS *FltObjects,
        PVOID CompletionContext,
        FLT_POST_OPERATION_FLAGS Flags)
{
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  PFILE_OBJECT FileObject; // rsi
  _QWORD *FsContext2; // rbx
  __int64 v14; // rbx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  __int64 Information_low; // r14
  int v17; // r12d
  enum _FLT_POSTOP_CALLBACK_STATUS IrpFlags; // ecx
  char v19; // r15
  bool v20; // r15
  SECTION_OBJECT_POINTERS *v21; // rax
  PVOID PrivateCacheMap; // rax
  __int64 v23; // rcx
  int v24; // [rsp+50h] [rbp-20h] BYREF
  const char *v25; // [rsp+58h] [rbp-18h] BYREF
  const char *v26; // [rsp+60h] [rbp-10h] BYREF
  const char *v27; // [rsp+68h] [rbp-8h] BYREF
  FsFltWil::Details *QuadPart; // [rsp+C0h] [rbp+50h] BYREF
  enum _FLT_POSTOP_CALLBACK_STATUS RetPostOperationStatus; // [rsp+C8h] [rbp+58h] BYREF

  if ( (Flags & 1) == 0 )
  {
    if ( KeGetCurrentIrql() >= 2u )
    {
      RetPostOperationStatus = FLT_POSTOP_FINISHED_PROCESSING;
      if ( FltDoCompletionProcessingWhenSafe(
             Data,
             FltObjects,
             CompletionContext,
             Flags,
             UnionFs::UnionFsFilter::PostRead,
             &RetPostOperationStatus) )
      {
        return (unsigned int)RetPostOperationStatus;
      }
      MicrosoftTelemetryAssertTriggeredMsgKM("Failed to post read completion processing");
      if ( (unsigned int)dword_14009E178 > 2 )
      {
        v24 = 160;
        LODWORD(QuadPart) = KeGetCurrentIrql();
        v25 = "onecore\\base\\fs\\unionfs\\sys\\read.cpp";
        v26 = "UnionFs::UnionFsFilter::PostRead";
        v27 = "Failed to post read completion processing";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v9,
          (unsigned int)byte_140098659,
          v10,
          v11,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&v25,
          (__int64)&v24,
          (__int64)&QuadPart);
      }
    }
    FileObject = FltObjects->FileObject;
    FsContext2 = FileObject->FsContext2;
    FsFltWil::AcquirePushLockShared(&QuadPart, FsContext2 + 4);
    v14 = FsContext2[3];
    if ( QuadPart )
      FsFltWil::Details::ReleasePushLockShared(QuadPart, (unsigned __int64 *)&FltObjects->Size);
    if ( v14 )
    {
      Iopb = Data->Iopb;
      Information_low = LODWORD(Data->IoStatus.Information);
      v17 = FileObject->Flags & 2;
      IrpFlags = Iopb->IrpFlags;
      v19 = Iopb->IrpFlags;
      QuadPart = (FsFltWil::Details *)Iopb->Parameters.Read.ByteOffset.QuadPart;
      v20 = (v19 & 1) == 0;
      v21 = *(SECTION_OBJECT_POINTERS **)(v14 + 40);
      RetPostOperationStatus = IrpFlags;
      if ( FileObject->SectionObjectPointer != v21 )
        MicrosoftTelemetryAssertTriggeredMsgKM("shadowFileObject->SectionObjectPointer == backingFileObject->SectionObjectPointer");
      PrivateCacheMap = FileObject->PrivateCacheMap;
      if ( PrivateCacheMap && PrivateCacheMap != *(PVOID *)(v14 + 48) )
        MicrosoftTelemetryAssertTriggeredMsgKM(
          "!shadowFileObject->PrivateCacheMap || (shadowFileObject->PrivateCacheMap == backingFileObject->PrivateCacheMap)");
      if ( v20 && (FileObject->Flags & 0x4000) == 0 )
        FileObject->PrivateCacheMap = *(PVOID *)(v14 + 48);
      if ( Data->IoStatus.Status >= 0 && v17 && (RetPostOperationStatus & 2) == 0 && (_DWORD)Information_low )
        FileObject->CurrentByteOffset.QuadPart = (LONGLONG)QuadPart + Information_low;
    }
  }
  if ( CompletionContext )
  {
    FsFltWil::Details::ReleaseRundownProtectionCacheAware(
      (FsFltWil::Details *)CompletionContext,
      (struct FsFltWil::Details::RundownRefCacheAware *)FltObjects);
    v23 = *((_QWORD *)CompletionContext + 16);
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 24LL))(v23);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 896), CompletionContext);
  }
  return 0;
}

```

## disassembly

```asm
0x140054380  mov     [rsp-38h+arg_0], rbx
0x140054385  push    rbp
0x140054386  push    rsi
0x140054387  push    rdi
0x140054388  push    r12
0x14005438a  push    r13
0x14005438c  push    r14
0x14005438e  push    r15
0x140054390  mov     rbp, rsp
0x140054393  sub     rsp, 70h
0x140054397  mov     ebx, r9d
0x14005439a  mov     rdi, r8
0x14005439d  mov     rsi, rdx
0x1400543a0  mov     r13, rcx
0x1400543a3  test    r9b, 1
0x1400543a7  jnz     loc_140054547
0x1400543ad  call    cs:__imp_KeGetCurrentIrql
0x1400543b4  nop     dword ptr [rax+rax+00h]
0x1400543b9  cmp     al, 2
0x1400543bb  jb      loc_140054487
0x1400543c1  lea     rax, [rbp+arg_18]
0x1400543c5  mov     [rbp+arg_18], 0
0x1400543cc  mov     [rsp+70h+RetPostOperationStatus], rax; RetPostOperationStatus
0x1400543d1  mov     r9d, ebx; Flags
0x1400543d4  lea     rax, ?PostRead@UnionFsFilter@UnionFs@@SA?AW4_FLT_POSTOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAXK@Z; UnionFs::UnionFsFilter::PostRead(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void *,ulong)
0x1400543db  mov     r8, rdi; CompletionContext
0x1400543de  mov     rdx, rsi; FltObjects
0x1400543e1  mov     [rsp+70h+SafePostCallback], rax; SafePostCallback
0x1400543e6  mov     rcx, r13; Data
0x1400543e9  call    cs:__imp_FltDoCompletionProcessingWhenSafe
0x1400543f0  nop     dword ptr [rax+rax+00h]
0x1400543f5  test    al, al
0x1400543f7  jz      short loc_140054401
0x1400543f9  mov     eax, [rbp+arg_18]
0x1400543fc  jmp     loc_14005458B
0x140054401  lea     rbx, aFailedToPostRe; "Failed to post read completion processi"...
0x140054408  mov     rcx, rbx
0x14005440b  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140054410  mov     eax, cs:dword_14009E178
0x140054416  cmp     eax, 2
0x140054419  jbe     short loc_140054487
0x14005441b  call    cs:__imp_KeGetCurrentIrql
0x140054422  nop     dword ptr [rax+rax+00h]
0x140054427  lea     rdx, byte_140098659
0x14005442e  mov     [rbp+var_20], 0A0h
0x140054435  movzx   eax, al
0x140054438  mov     dword ptr [rbp+arg_10], eax
0x14005443b  lea     rax, aOnecoreBaseFsU_22; "onecore\\base\\fs\\unionfs\\sys\\read.c"...
0x140054442  mov     [rbp+var_18], rax
0x140054446  lea     rax, aUnionfsUnionfs_67; "UnionFs::UnionFsFilter::PostRead"
0x14005444d  mov     [rbp+var_10], rax
0x140054451  lea     rax, [rbp+arg_10]
0x140054455  mov     [rsp+70h+var_30], rax
0x14005445a  lea     rax, [rbp+var_20]
0x14005445e  mov     [rsp+70h+var_38], rax
0x140054463  lea     rax, [rbp+var_18]
0x140054467  mov     [rsp+70h+var_40], rax
0x14005446c  lea     rax, [rbp+var_10]
0x140054470  mov     [rsp+70h+RetPostOperationStatus], rax
0x140054475  lea     rax, [rbp+var_8]
0x140054479  mov     [rsp+70h+SafePostCallback], rax
0x14005447e  mov     [rbp+var_8], rbx
0x140054482  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140054487  mov     rsi, [rsi+20h]
0x14005448b  lea     rcx, [rbp+arg_10]
0x14005448f  mov     rbx, [rsi+20h]
0x140054493  lea     rdx, [rbx+20h]
0x140054497  call    ?AcquirePushLockShared@FsFltWil@@YA?AV?$unique_ptr@_KU?$function_deleter@P6AXPEA_K@Z$1?ReleasePushLockShared@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEA_K@Z; FsFltWil::AcquirePushLockShared(unsigned __int64 &)
0x14005449c  mov     rcx, [rbp+arg_10]; this
0x1400544a0  mov     rbx, [rbx+18h]
0x1400544a4  test    rcx, rcx
0x1400544a7  jz      short loc_1400544AE
0x1400544a9  call    ?ReleasePushLockShared@Details@FsFltWil@@YAXPEA_K@Z; FsFltWil::Details::ReleasePushLockShared(unsigned __int64 *)
0x1400544ae  test    rbx, rbx
0x1400544b1  jz      loc_140054547
0x1400544b7  mov     rax, [r13+10h]
0x1400544bb  mov     r12d, [rsi+50h]
0x1400544bf  mov     r14d, [r13+20h]
0x1400544c3  and     r12d, 2
0x1400544c7  mov     ecx, [rax]
0x1400544c9  mov     r15b, cl
0x1400544cc  mov     rax, [rax+28h]
0x1400544d0  not     r15b
0x1400544d3  mov     [rbp+arg_10], rax
0x1400544d7  and     r15b, 1
0x1400544db  mov     rax, [rbx+28h]
0x1400544df  mov     [rbp+arg_18], ecx
0x1400544e2  cmp     [rsi+28h], rax
0x1400544e6  jz      short loc_1400544F4
0x1400544e8  lea     rcx, aShadowfileobje; "shadowFileObject->SectionObjectPointer "...
0x1400544ef  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400544f4  mov     rax, [rsi+30h]
0x1400544f8  test    rax, rax
0x1400544fb  jz      short loc_14005450F
0x1400544fd  cmp     rax, [rbx+30h]
0x140054501  jz      short loc_14005450F
0x140054503  lea     rcx, aShadowfileobje_0; "!shadowFileObject->PrivateCacheMap || ("...
0x14005450a  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14005450f  test    r15b, r15b
0x140054512  jz      short loc_140054525
0x140054514  test    dword ptr [rsi+50h], 4000h
0x14005451b  jnz     short loc_140054525
0x14005451d  mov     rax, [rbx+30h]
0x140054521  mov     [rsi+30h], rax
0x140054525  cmp     dword ptr [r13+18h], 0
0x14005452a  jl      short loc_140054547
0x14005452c  test    r12d, r12d
0x14005452f  jz      short loc_140054547
0x140054531  test    byte ptr [rbp+arg_18], 2
0x140054535  jnz     short loc_140054547
0x140054537  test    r14d, r14d
0x14005453a  jz      short loc_140054547
0x14005453c  mov     rax, r14
0x14005453f  add     rax, [rbp+arg_10]
0x140054543  mov     [rsi+68h], rax
0x140054547  test    rdi, rdi
0x14005454a  jz      short loc_140054589
0x14005454c  mov     rcx, rdi; this
0x14005454f  call    ?ReleaseRundownProtectionCacheAware@Details@FsFltWil@@YAXPEAURundownRefCacheAware@12@@Z; FsFltWil::Details::ReleaseRundownProtectionCacheAware(FsFltWil::Details::RundownRefCacheAware *)
0x140054554  mov     rcx, [rdi+80h]
0x14005455b  test    rcx, rcx
0x14005455e  jz      short loc_14005456C
0x140054560  mov     rax, [rcx]
0x140054563  mov     rax, [rax+18h]
0x140054567  call    _guard_dispatch_icall
0x14005456c  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140054573  mov     rdx, rdi; Entry
0x140054576  add     rcx, 380h; Lookaside
0x14005457d  call    cs:__imp_ExFreeToLookasideListEx
0x140054584  nop     dword ptr [rax+rax+00h]
0x140054589  xor     eax, eax
0x14005458b  mov     rbx, [rsp+70h+arg_0]
0x140054593  add     rsp, 70h
0x140054597  pop     r15
0x140054599  pop     r14
0x14005459b  pop     r13
0x14005459d  pop     r12
0x14005459f  pop     rdi
0x1400545a0  pop     rsi
0x1400545a1  pop     rbp
0x1400545a2  retn
```
