# UnionFs::Utils::OplockCompleteWorkItemRoutine(_FLT_DEFERRED_IO_WORKITEM *,_FLT_CALLBACK_DATA *,void *)

- ea: `0x1400749f0`
- end: `0x140074b84`
- name: `?OplockCompleteWorkItemRoutine@Utils@UnionFs@@YAXPEAU_FLT_DEFERRED_IO_WORKITEM@@PEAU_FLT_CALLBACK_DATA@@PEAX@Z`
- size: `404`
- prototype: `void __stdcall(PFLT_DEFERRED_IO_WORKITEM FltWorkItem, PFLT_CALLBACK_DATA CallbackData, PVOID Context)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400055d0`
- `0x140006168`
- `0x14000ccb0`
- `0x140011e20`
- `0x140034900`
- `0x140054740`
- `0x140056c44`
- `0x1400749f0`
- `0x14007baf0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140074b51`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140074b51`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140074b34`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140074b34`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140074b1a`
- `FLTMGR!FltCompletePendedPreOperation` at `0x140074b1a`

## string_xrefs

- `0x140074af5`: `UnionFs::Utils::OplockCompleteWorkItemRoutine`
- `0x140074aeb`: `ORIGIN: Failure in oplock completion`

## pseudocode

```c
void __fastcall UnionFs::Utils::OplockCompleteWorkItemRoutine(
        PFLT_DEFERRED_IO_WORKITEM FltWorkItem,
        PFLT_CALLBACK_DATA CallbackData,
        const struct _FLT_RELATED_OBJECTS **Context)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  UCHAR MajorFunction; // cl
  __int64 v7; // rbp
  FLT_PREOP_CALLBACK_STATUS v8; // edi
  enum _FLT_PREOP_CALLBACK_STATUS v9; // eax
  UnionFs *Status; // rcx
  struct _FLT_DEFERRED_IO_WORKITEM *v11; // rcx
  const char *v12; // [rsp+28h] [rbp-330h]
  struct _FLT_RELATED_OBJECTS Contexta[15]; // [rsp+30h] [rbp-328h] BYREF

  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)&Contexta[0].Filter, 0x6DA00212806uLL);
  Iopb = CallbackData->Iopb;
  *(_QWORD *)&Contexta[0].Size = 0;
  MajorFunction = Iopb->MajorFunction;
  if ( MajorFunction )
  {
    switch ( MajorFunction )
    {
      case 3u:
        v7 = 0x6DC0021281DLL;
        v9 = UnionFs::UnionFsFilter::PreRead(CallbackData, *Context, (void **)Contexta);
        break;
      case 6u:
        v7 = 0x6DD00212823LL;
        v9 = UnionFs::UnionFsFilter::PreSetInfo(CallbackData, *Context, Contexta);
        break;
      case 0xDu:
        v7 = 0x6DE00212829LL;
        v9 = (unsigned int)UnionFs::UnionFsFilter::PreFsControl(CallbackData, *Context, (void **)Contexta);
        break;
      default:
        CallbackData->IoStatus.Status = -1073741808;
        v7 = 0x6DF00212834LL;
        CallbackData->IoStatus.Information = 0;
        v8 = FLT_PREOP_COMPLETE;
        goto LABEL_11;
    }
  }
  else
  {
    v7 = 0x6DB00212817LL;
    v9 = (unsigned int)UnionFs::UnionFsFilter::PreCreate(CallbackData, *Context, (void **)Contexta);
  }
  v8 = v9;
  if ( v9 != FLT_PREOP_COMPLETE )
    goto LABEL_13;
LABEL_11:
  Status = (UnionFs *)(unsigned int)CallbackData->IoStatus.Status;
  if ( (int)Status < 0 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      Status,
      (int)&Contexta[0].Filter,
      (struct UnionFs::StackEventTracer *)v7,
      (unsigned __int64)"UnionFs::Utils::OplockCompleteWorkItemRoutine",
      "ORIGIN: Failure in oplock completion",
      v12);
LABEL_13:
    if ( v8 == FLT_PREOP_PENDING )
      goto LABEL_15;
  }
  FltCompletePendedPreOperation(CallbackData, v8, *(PVOID *)&Contexta[0].Size);
LABEL_15:
  if ( Context )
  {
    v11 = (struct _FLT_DEFERRED_IO_WORKITEM *)Context[1];
    if ( v11 )
      FltFreeDeferredIoWorkItem(v11);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)UnionFs::g_FilterState + 28, Context);
  }
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)&Contexta[0].Filter);
}

```

## disassembly

```asm
0x1400749f0  push    rbx
0x1400749f2  push    rbp
0x1400749f3  push    rsi
0x1400749f4  push    rdi
0x1400749f5  sub     rsp, 338h
0x1400749fc  mov     rax, cs:__security_cookie
0x140074a03  xor     rax, rsp
0x140074a06  mov     [rsp+358h+var_30], rax
0x140074a0e  mov     rbx, rdx
0x140074a11  lea     rcx, [rsp+358h+var_320]; this
0x140074a16  mov     rdx, 6DA00212806h; unsigned __int64
0x140074a20  mov     rsi, r8
0x140074a23  call    ??0StackEventTracer@UnionFs@@QEAA@_K@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64)
0x140074a28  mov     rax, [rbx+10h]
0x140074a2c  mov     [rsp+358h+Context], 0
0x140074a35  mov     cl, [rax+4]
0x140074a38  test    cl, cl
0x140074a3a  jz      loc_140074AC3
0x140074a40  cmp     cl, 3
0x140074a43  jz      short loc_140074AA7
0x140074a45  cmp     cl, 6
0x140074a48  jz      short loc_140074A8B
0x140074a4a  cmp     cl, 0Dh
0x140074a4d  jz      short loc_140074A6F
0x140074a4f  mov     dword ptr [rbx+18h], 0C0000010h
0x140074a56  mov     rbp, 6DF00212834h
0x140074a60  mov     qword ptr [rbx+20h], 0
0x140074a68  mov     edi, 4
0x140074a6d  jmp     short loc_140074AE4
0x140074a6f  mov     rdx, [rsi]; struct _FLT_RELATED_OBJECTS *
0x140074a72  lea     r8, [rsp+358h+Context]; void **
0x140074a77  mov     rcx, rbx; struct _FLT_CALLBACK_DATA *
0x140074a7a  mov     rbp, 6DE00212829h
0x140074a84  call    ?PreFsControl@UnionFsFilter@UnionFs@@SA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAPEAX@Z; UnionFs::UnionFsFilter::PreFsControl(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void * *)
0x140074a89  jmp     short loc_140074ADD
0x140074a8b  mov     rdx, [rsi]; struct _FLT_RELATED_OBJECTS *
0x140074a8e  lea     r8, [rsp+358h+Context]; struct _FLT_RELATED_OBJECTS *
0x140074a93  mov     rcx, rbx; this
0x140074a96  mov     rbp, 6DD00212823h
0x140074aa0  call    ?PreSetInfo@UnionFsFilter@UnionFs@@SA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAPEAX@Z; UnionFs::UnionFsFilter::PreSetInfo(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void * *)
0x140074aa5  jmp     short loc_140074ADD
0x140074aa7  mov     rdx, [rsi]; struct _FLT_RELATED_OBJECTS *
0x140074aaa  lea     r8, [rsp+358h+Context]; void **
0x140074aaf  mov     rcx, rbx; struct _FLT_CALLBACK_DATA *
0x140074ab2  mov     rbp, 6DC0021281Dh
0x140074abc  call    ?PreRead@UnionFsFilter@UnionFs@@SA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAPEAX@Z; UnionFs::UnionFsFilter::PreRead(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void * *)
0x140074ac1  jmp     short loc_140074ADD
0x140074ac3  mov     rdx, [rsi]; struct _FLT_RELATED_OBJECTS *
0x140074ac6  lea     r8, [rsp+358h+Context]; void **
0x140074acb  mov     rcx, rbx; struct _FLT_CALLBACK_DATA *
0x140074ace  mov     rbp, 6DB00212817h
0x140074ad8  call    ?PreCreate@UnionFsFilter@UnionFs@@SA?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAU_FLT_CALLBACK_DATA@@PEBU_FLT_RELATED_OBJECTS@@PEAPEAX@Z; UnionFs::UnionFsFilter::PreCreate(_FLT_CALLBACK_DATA *,_FLT_RELATED_OBJECTS const *,void * *)
0x140074add  mov     edi, eax
0x140074adf  cmp     eax, 4
0x140074ae2  jnz     short loc_140074B0B
0x140074ae4  mov     ecx, [rbx+18h]; this
0x140074ae7  test    ecx, ecx
0x140074ae9  jns     short loc_140074B10
0x140074aeb  lea     rax, aOriginFailureI; "ORIGIN: Failure in oplock completion"
0x140074af2  mov     r8, rbp; struct UnionFs::StackEventTracer *
0x140074af5  lea     r9, aUnionfsUtilsOp_0; "UnionFs::Utils::OplockCompleteWorkItemR"...
0x140074afc  mov     [rsp+358h+var_338], rax; char *
0x140074b01  lea     rdx, [rsp+358h+var_320]; int
0x140074b06  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140074b0b  cmp     edi, 2
0x140074b0e  jz      short loc_140074B26
0x140074b10  mov     r8, [rsp+358h+Context]; Context
0x140074b15  mov     edx, edi; CallbackStatus
0x140074b17  mov     rcx, rbx; CallbackData
0x140074b1a  call    cs:__imp_FltCompletePendedPreOperation
0x140074b21  nop     dword ptr [rax+rax+00h]
0x140074b26  test    rsi, rsi
0x140074b29  jz      short loc_140074B5D
0x140074b2b  mov     rcx, [rsi+8]; FltWorkItem
0x140074b2f  test    rcx, rcx
0x140074b32  jz      short loc_140074B40
0x140074b34  call    cs:__imp_FltFreeDeferredIoWorkItem
0x140074b3b  nop     dword ptr [rax+rax+00h]
0x140074b40  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140074b47  mov     rdx, rsi; Entry
0x140074b4a  add     rcx, 0A80h; Lookaside
0x140074b51  call    cs:__imp_ExFreeToLookasideListEx
0x140074b58  nop     dword ptr [rax+rax+00h]
0x140074b5d  lea     rcx, [rsp+358h+var_320]; this
0x140074b62  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x140074b67  mov     rcx, [rsp+358h+var_30]
0x140074b6f  xor     rcx, rsp; StackCookie
0x140074b72  call    __security_check_cookie
0x140074b77  add     rsp, 338h
0x140074b7e  pop     rdi
0x140074b7f  pop     rsi
0x140074b80  pop     rbp
0x140074b81  pop     rbx
0x140074b82  retn
```
