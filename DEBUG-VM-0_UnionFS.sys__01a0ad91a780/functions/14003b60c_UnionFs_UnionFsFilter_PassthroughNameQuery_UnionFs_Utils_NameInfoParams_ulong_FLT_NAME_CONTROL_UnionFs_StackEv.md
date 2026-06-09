# UnionFs::UnionFsFilter::PassthroughNameQuery(UnionFs::Utils::NameInfoParams,ulong,_FLT_NAME_CONTROL *,UnionFs::StackEventTracer &)

- ea: `0x14003b60c`
- end: `0x14003b732`
- name: `?PassthroughNameQuery@UnionFsFilter@UnionFs@@AEAAJUNameInfoParams@Utils@2@KPEAU_FLT_NAME_CONTROL@@AEAVStackEventTracer@2@@Z`
- size: `294`
- prototype: `int __high(struct UnionFs::Utils::NameInfoParams, unsigned int, struct _FLT_NAME_CONTROL *, struct UnionFs::StackEventTracer *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1400365c8`
- `0x140037b54`
- `0x14003a1a4`

## callees

- `0x14003b60c`
- `0x140056bd0`
- `0x140056c7c`
- `0x14006e394`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14003b6f6`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003b6f6`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x14003b6af`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x14003b6af`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003b694`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003b713`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003b694`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003b713`

## pseudocode

```c
__int64 __fastcall UnionFs::UnionFsFilter::PassthroughNameQuery(
        struct _FLT_FILE_NAME_INFORMATION *a1,
        __int128 *a2,
        unsigned int a3,
        struct _FLT_NAME_CONTROL *a4,
        __int64 a5)
{
  __int128 v5; // xmm0
  __int64 v6; // xmm1_8
  NTSTATUS v8; // ebx
  struct _FLT_FILE_NAME_INFORMATION *v9; // rcx
  struct _FLT_FILE_NAME_INFORMATION *v11; // rcx
  const char *v12; // [rsp+28h] [rbp-28h]
  __int128 v13; // [rsp+30h] [rbp-20h] BYREF
  __int64 v14; // [rsp+40h] [rbp-10h]
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+60h] [rbp+10h] BYREF

  FileNameInformation = a1;
  v5 = *a2;
  v6 = *((_QWORD *)a2 + 2);
  FileNameInformation = 0;
  v13 = v5;
  v14 = v6;
  v8 = UnionFs::Utils::GetFileNameInformation(&v13, a3, &FileNameInformation, a5);
  if ( v8 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v8,
      a5,
      (struct UnionFs::StackEventTracer *)0x174000F0612LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PassthroughNameQuery",
      "PUSH: Querying Filter Manager for name",
      v12);
LABEL_3:
    v9 = FileNameInformation;
    FileNameInformation = 0;
    if ( v9 )
      FltReleaseFileNameInformation(v9);
    return (unsigned int)v8;
  }
  v8 = FltCheckAndGrowNameControl(a4, FileNameInformation->Name.Length);
  if ( v8 < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v8,
      a5,
      (struct UnionFs::StackEventTracer *)0x175000F0617LL,
      (unsigned __int64)"UnionFs::UnionFsFilter::PassthroughNameQuery",
      "API: Growing FLT_NAME_CONTROL",
      v12);
    goto LABEL_3;
  }
  RtlCopyUnicodeString(&a4->Name, &FileNameInformation->Name);
  v11 = FileNameInformation;
  FileNameInformation = 0;
  if ( v11 )
    FltReleaseFileNameInformation(v11);
  return 0;
}

```

## disassembly

```asm
0x14003b60c  mov     [rsp-8+arg_8], rbx
0x14003b611  mov     [rsp-8+arg_10], rdi
0x14003b616  mov     [rsp-8+FileNameInformation], rcx
0x14003b61b  push    rbp
0x14003b61c  mov     rbp, rsp
0x14003b61f  sub     rsp, 50h
0x14003b623  movaps  xmm0, xmmword ptr [rdx]
0x14003b626  lea     rcx, [rbp+var_20]
0x14003b62a  movsd   xmm1, qword ptr [rdx+10h]
0x14003b62f  mov     eax, r8d
0x14003b632  mov     rdi, r9
0x14003b635  mov     [rbp+FileNameInformation], 0
0x14003b63d  mov     r9, [rbp+arg_20]
0x14003b641  lea     r8, [rbp+FileNameInformation]
0x14003b645  mov     edx, eax
0x14003b647  movaps  [rbp+var_20], xmm0
0x14003b64b  movsd   [rbp+var_10], xmm1
0x14003b650  call    ?GetFileNameInformation@Utils@UnionFs@@YAJUNameInfoParams@12@KAEAV?$unique_ptr@U_FLT_FILE_NAME_INFORMATION@@U?$function_deleter@P6AXPEAU_FLT_FILE_NAME_INFORMATION@@@Z$1?FltReleaseFileNameInformation@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetFileNameInformation(UnionFs::Utils::NameInfoParams,ulong,wistd::unique_ptr<_FLT_FILE_NAME_INFORMATION,wil::function_deleter<void (*)(_FLT_FILE_NAME_INFORMATION *),&FltReleaseFileNameInformation(_FLT_FILE_NAME_INFORMATION *)>> &,UnionFs::StackEventTracer &)
0x14003b655  mov     ebx, eax
0x14003b657  test    eax, eax
0x14003b659  jns     short loc_14003B6A4
0x14003b65b  mov     rdx, [rbp+arg_20]; int
0x14003b65f  lea     rax, aPushQueryingFi; "PUSH: Querying Filter Manager for name"
0x14003b666  lea     r9, aUnionfsUnionfs_35; "UnionFs::UnionFsFilter::PassthroughName"...
0x14003b66d  mov     [rsp+50h+var_30], rax; char *
0x14003b672  mov     r8, 174000F0612h; struct UnionFs::StackEventTracer *
0x14003b67c  mov     ecx, ebx; this
0x14003b67e  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003b683  mov     rcx, [rbp+FileNameInformation]; FileNameInformation
0x14003b687  mov     [rbp+FileNameInformation], 0
0x14003b68f  test    rcx, rcx
0x14003b692  jz      short loc_14003B6A0
0x14003b694  call    cs:__imp_FltReleaseFileNameInformation
0x14003b69b  nop     dword ptr [rax+rax+00h]
0x14003b6a0  mov     eax, ebx
0x14003b6a2  jmp     short loc_14003B721
0x14003b6a4  mov     rdx, [rbp+FileNameInformation]
0x14003b6a8  mov     rcx, rdi; NameCtrl
0x14003b6ab  movzx   edx, word ptr [rdx+8]; NewSize
0x14003b6af  call    cs:__imp_FltCheckAndGrowNameControl
0x14003b6b6  nop     dword ptr [rax+rax+00h]
0x14003b6bb  mov     ebx, eax
0x14003b6bd  test    eax, eax
0x14003b6bf  jns     short loc_14003B6EB
0x14003b6c1  mov     rdx, [rbp+arg_20]; int
0x14003b6c5  lea     rax, aApiGrowingFltN; "API: Growing FLT_NAME_CONTROL"
0x14003b6cc  lea     r9, aUnionfsUnionfs_35; "UnionFs::UnionFsFilter::PassthroughName"...
0x14003b6d3  mov     [rsp+50h+var_30], rax; char *
0x14003b6d8  mov     r8, 175000F0617h; struct UnionFs::StackEventTracer *
0x14003b6e2  mov     ecx, ebx; this
0x14003b6e4  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003b6e9  jmp     short loc_14003B683
0x14003b6eb  mov     rdx, [rbp+FileNameInformation]
0x14003b6ef  mov     rcx, rdi; DestinationString
0x14003b6f2  add     rdx, 8; SourceString
0x14003b6f6  call    cs:__imp_RtlCopyUnicodeString
0x14003b6fd  nop     dword ptr [rax+rax+00h]
0x14003b702  mov     rcx, [rbp+FileNameInformation]; FileNameInformation
0x14003b706  mov     [rbp+FileNameInformation], 0
0x14003b70e  test    rcx, rcx
0x14003b711  jz      short loc_14003B71F
0x14003b713  call    cs:__imp_FltReleaseFileNameInformation
0x14003b71a  nop     dword ptr [rax+rax+00h]
0x14003b71f  xor     eax, eax
0x14003b721  mov     rbx, [rsp+50h+arg_8]
0x14003b726  mov     rdi, [rsp+50h+arg_10]
0x14003b72b  add     rsp, 50h
0x14003b72f  pop     rbp
0x14003b730  retn
```
