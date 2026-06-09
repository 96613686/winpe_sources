# UnionFs::UnionFsFilter::PostWrite(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void *,ulong)

- ea: `0x140079780`
- end: `0x140079911`
- name: `?PostWrite@UnionFsFilter@UnionFs@@SA?AW4_FLT_POSTOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAXK@Z`
- size: `401`
- prototype: `FLT_POSTOP_CALLBACK_STATUS __stdcall(PFLT_CALLBACK_DATA Data, PCFLT_RELATED_OBJECTS FltObjects, PVOID CompletionContext, FLT_POST_OPERATION_FLAGS Flags)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x140004240`
- `0x14002af6c`
- `0x14002be04`
- `0x140079780`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400797b2`
- `ntoskrnl!KeGetCurrentIrql` at `0x140079856`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400797b2`
- `ntoskrnl!KeGetCurrentIrql` at `0x140079856`
- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x1400797f6`
- `FLTMGR!FltDoCompletionProcessingWhenSafe` at `0x1400797f6`

## string_xrefs

- `0x140079876`: `onecore\base\fs\unionfs\sys\write.cpp`
- `0x14007988c`: `Failed to post write completion processing`
- `0x140079881`: `UnionFs::UnionFsFilter::PostWrite`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::PostWrite(
        PFLT_CALLBACK_DATA Data,
        PCFLT_RELATED_OBJECTS FltObjects,
        UnionFs::UfsStreamCtx **CompletionContext,
        FLT_POST_OPERATION_FLAGS Flags)
{
  enum _FLT_POSTOP_CALLBACK_STATUS v8; // ebx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  int CurrentIrql; // [rsp+50h] [rbp-30h] BYREF
  UnionFs::UfsStreamCtx **v14; // [rsp+58h] [rbp-28h] BYREF
  const char *v15; // [rsp+60h] [rbp-20h] BYREF
  const char *v16; // [rsp+68h] [rbp-18h] BYREF
  const char *v17; // [rsp+70h] [rbp-10h] BYREF
  enum _FLT_POSTOP_CALLBACK_STATUS RetPostOperationStatus; // [rsp+B0h] [rbp+30h] BYREF
  bool v19; // [rsp+B8h] [rbp+38h] BYREF

  v14 = CompletionContext;
  if ( (Flags & 1) != 0 )
  {
LABEL_13:
    v8 = FLT_POSTOP_FINISHED_PROCESSING;
    goto LABEL_14;
  }
  if ( KeGetCurrentIrql() < 2u )
  {
    if ( Data->IoStatus.Status >= 0 && *CompletionContext )
      UnionFs::UfsStreamCtx::UpdateSFOFileSizesForScratchBFO(*CompletionContext);
    goto LABEL_13;
  }
  v14 = 0;
  RetPostOperationStatus = FLT_POSTOP_FINISHED_PROCESSING;
  if ( !FltDoCompletionProcessingWhenSafe(
          Data,
          FltObjects,
          CompletionContext,
          Flags,
          UnionFs::UnionFsFilter::PostWrite,
          &RetPostOperationStatus) )
  {
    if ( (unsigned int)dword_14009E178 > 3
      && (qword_14009E188 & 0x80000) != 0
      && (qword_14009E190 & 0x80000) == qword_14009E190 )
    {
      v19 = (Data->Iopb->IrpFlags & 2) != 0;
      LODWORD(v14) = 155;
      CurrentIrql = KeGetCurrentIrql();
      v15 = "onecore\\base\\fs\\unionfs\\sys\\write.cpp";
      v16 = "UnionFs::UnionFsFilter::PostWrite";
      v17 = "Failed to post write completion processing";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
        v9,
        (unsigned int)word_14009A5B2,
        v10,
        v11,
        (__int64)&v17,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v14,
        (__int64)&CurrentIrql,
        (__int64)&v19);
    }
    v14 = CompletionContext;
    goto LABEL_13;
  }
  v8 = RetPostOperationStatus;
LABEL_14:
  utl::unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>::~unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>(&v14);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140079780  mov     [rsp-18h+arg_0], rbx
0x140079785  mov     [rsp-18h+arg_8], rsi
0x14007978a  push    rbp
0x14007978b  push    rdi
0x14007978c  push    r14
0x14007978e  mov     rbp, rsp
0x140079791  sub     rsp, 80h
0x140079798  mov     rbx, r8
0x14007979b  mov     esi, r9d
0x14007979e  mov     [rbp+var_28], rbx
0x1400797a2  mov     r14, rdx
0x1400797a5  mov     rdi, rcx
0x1400797a8  test    r9b, 1
0x1400797ac  jnz     loc_1400798EB
0x1400797b2  call    cs:__imp_KeGetCurrentIrql
0x1400797b9  nop     dword ptr [rax+rax+00h]
0x1400797be  cmp     al, 2
0x1400797c0  jb      loc_1400798D8
0x1400797c6  lea     rax, [rbp+arg_10]
0x1400797ca  mov     [rbp+var_28], 0
0x1400797d2  mov     [rsp+80h+RetPostOperationStatus], rax; RetPostOperationStatus
0x1400797d7  mov     r9d, esi; Flags
0x1400797da  lea     rax, ?PostWrite@UnionFsFilter@UnionFs@@SA?AW4_FLT_POSTOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAXK@Z; UnionFs::UnionFsFilter::PostWrite(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void *,ulong)
0x1400797e1  mov     [rbp+arg_10], 0
0x1400797e8  mov     r8, rbx; CompletionContext
0x1400797eb  mov     [rsp+80h+SafePostCallback], rax; SafePostCallback
0x1400797f0  mov     rdx, r14; FltObjects
0x1400797f3  mov     rcx, rdi; Data
0x1400797f6  call    cs:__imp_FltDoCompletionProcessingWhenSafe
0x1400797fd  nop     dword ptr [rax+rax+00h]
0x140079802  test    al, al
0x140079804  jz      short loc_14007980E
0x140079806  mov     ebx, [rbp+arg_10]
0x140079809  jmp     loc_1400798ED
0x14007980e  mov     eax, cs:dword_14009E178
0x140079814  cmp     eax, 3
0x140079817  jbe     loc_1400798D2
0x14007981d  mov     rcx, cs:qword_14009E190
0x140079824  mov     edx, 80000h
0x140079829  mov     rax, cs:qword_14009E188
0x140079830  test    rdx, rax
0x140079833  jz      loc_1400798D2
0x140079839  mov     rax, rcx
0x14007983c  and     rax, rdx
0x14007983f  cmp     rax, rcx
0x140079842  jnz     loc_1400798D2
0x140079848  mov     rax, [rdi+10h]
0x14007984c  mov     ecx, [rax]
0x14007984e  shr     ecx, 1
0x140079850  and     cl, 1
0x140079853  mov     [rbp+arg_18], cl
0x140079856  call    cs:__imp_KeGetCurrentIrql
0x14007985d  nop     dword ptr [rax+rax+00h]
0x140079862  lea     rdx, word_14009A5B2
0x140079869  mov     dword ptr [rbp+var_28], 9Bh
0x140079870  movzx   eax, al
0x140079873  mov     [rbp+var_30], eax
0x140079876  lea     rax, aOnecoreBaseFsU_21; "onecore\\base\\fs\\unionfs\\sys\\write."...
0x14007987d  mov     [rbp+var_20], rax
0x140079881  lea     rax, aUnionfsUnionfs_6; "UnionFs::UnionFsFilter::PostWrite"
0x140079888  mov     [rbp+var_18], rax
0x14007988c  lea     rax, aFailedToPostWr; "Failed to post write completion process"...
0x140079893  mov     [rbp+var_10], rax
0x140079897  lea     rax, [rbp+arg_18]
0x14007989b  mov     [rsp+80h+var_38], rax
0x1400798a0  lea     rax, [rbp+var_30]
0x1400798a4  mov     [rsp+80h+var_40], rax
0x1400798a9  lea     rax, [rbp+var_28]
0x1400798ad  mov     [rsp+80h+var_48], rax
0x1400798b2  lea     rax, [rbp+var_20]
0x1400798b6  mov     [rsp+80h+var_50], rax
0x1400798bb  lea     rax, [rbp+var_18]
0x1400798bf  mov     [rsp+80h+RetPostOperationStatus], rax
0x1400798c4  lea     rax, [rbp+var_10]
0x1400798c8  mov     [rsp+80h+SafePostCallback], rax
0x1400798cd  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x1400798d2  mov     [rbp+var_28], rbx
0x1400798d6  jmp     short loc_1400798EB
0x1400798d8  cmp     dword ptr [rdi+18h], 0
0x1400798dc  jl      short loc_1400798EB
0x1400798de  mov     rcx, [rbx]; this
0x1400798e1  test    rcx, rcx
0x1400798e4  jz      short loc_1400798EB
0x1400798e6  call    ?UpdateSFOFileSizesForScratchBFO@UfsStreamCtx@UnionFs@@QEAAXXZ; UnionFs::UfsStreamCtx::UpdateSFOFileSizesForScratchBFO(void)
0x1400798eb  xor     ebx, ebx
0x1400798ed  lea     rcx, [rbp+var_28]
0x1400798f1  call    ??1?$unique_ptr@USetFileSizeContext@UnionFs@@U?$default_delete@USetFileSizeContext@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>::~unique_ptr<UnionFs::SetFileSizeContext,utl::default_delete<UnionFs::SetFileSizeContext>>(void)
0x1400798f6  lea     r11, [rsp+80h+var_s0]
0x1400798fe  mov     eax, ebx
0x140079900  mov     rbx, [r11+20h]
0x140079904  mov     rsi, [r11+28h]
0x140079908  mov     rsp, r11
0x14007990b  pop     r14
0x14007990d  pop     rdi
0x14007990e  pop     rbp
0x14007990f  retn
```
