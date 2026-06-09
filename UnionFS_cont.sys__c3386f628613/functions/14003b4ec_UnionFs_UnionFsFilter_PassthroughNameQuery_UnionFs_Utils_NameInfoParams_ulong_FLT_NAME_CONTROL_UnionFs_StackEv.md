# UnionFs::UnionFsFilter::PassthroughNameQuery(UnionFs::Utils::NameInfoParams,ulong,_FLT_NAME_CONTROL *,UnionFs::StackEventTracer &)

- ea: `0x14003b4ec`
- end: `0x14003b612`
- name: `?PassthroughNameQuery@UnionFsFilter@UnionFs@@AEAAJUNameInfoParams@Utils@2@KPEAU_FLT_NAME_CONTROL@@AEAVStackEventTracer@2@@Z`
- size: `294`
- prototype: `int __high(struct UnionFs::Utils::NameInfoParams, unsigned int, struct _FLT_NAME_CONTROL *, struct UnionFs::StackEventTracer *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140036488`
- `0x140037a14`
- `0x14003a064`

## callees

- `0x14003b4ec`
- `0x140056a50`
- `0x140056afc`
- `0x14006e1a4`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14003b5d6`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14003b5d6`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x14003b58f`
- `FLTMGR!FltCheckAndGrowNameControl` at `0x14003b58f`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003b574`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003b5f3`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003b574`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003b5f3`

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
      (struct UnionFs::StackEventTracer *)0x174000F0611LL,
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
      (struct UnionFs::StackEventTracer *)0x175000F0616LL,
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
0x14003b4ec  mov     [rsp-8+arg_8], rbx
0x14003b4f1  mov     [rsp-8+arg_10], rdi
0x14003b4f6  mov     [rsp-8+FileNameInformation], rcx
0x14003b4fb  push    rbp
0x14003b4fc  mov     rbp, rsp
0x14003b4ff  sub     rsp, 50h
0x14003b503  movaps  xmm0, xmmword ptr [rdx]
0x14003b506  lea     rcx, [rbp+var_20]
0x14003b50a  movsd   xmm1, qword ptr [rdx+10h]
0x14003b50f  mov     eax, r8d
0x14003b512  mov     rdi, r9
0x14003b515  mov     [rbp+FileNameInformation], 0
0x14003b51d  mov     r9, [rbp+arg_20]
0x14003b521  lea     r8, [rbp+FileNameInformation]
0x14003b525  mov     edx, eax
0x14003b527  movaps  [rbp+var_20], xmm0
0x14003b52b  movsd   [rbp+var_10], xmm1
0x14003b530  call    ?GetFileNameInformation@Utils@UnionFs@@YAJUNameInfoParams@12@KAEAV?$unique_ptr@U_FLT_FILE_NAME_INFORMATION@@U?$function_deleter@P6AXPEAU_FLT_FILE_NAME_INFORMATION@@@Z$1?FltReleaseFileNameInformation@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetFileNameInformation(UnionFs::Utils::NameInfoParams,ulong,wistd::unique_ptr<_FLT_FILE_NAME_INFORMATION,wil::function_deleter<void (*)(_FLT_FILE_NAME_INFORMATION *),&FltReleaseFileNameInformation(_FLT_FILE_NAME_INFORMATION *)>> &,UnionFs::StackEventTracer &)
0x14003b535  mov     ebx, eax
0x14003b537  test    eax, eax
0x14003b539  jns     short loc_14003B584
0x14003b53b  mov     rdx, [rbp+arg_20]; int
0x14003b53f  lea     rax, aPushQueryingFi; "PUSH: Querying Filter Manager for name"
0x14003b546  lea     r9, aUnionfsUnionfs_34; "UnionFs::UnionFsFilter::PassthroughName"...
0x14003b54d  mov     [rsp+50h+var_30], rax; char *
0x14003b552  mov     r8, 174000F0611h; struct UnionFs::StackEventTracer *
0x14003b55c  mov     ecx, ebx; this
0x14003b55e  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003b563  mov     rcx, [rbp+FileNameInformation]; FileNameInformation
0x14003b567  mov     [rbp+FileNameInformation], 0
0x14003b56f  test    rcx, rcx
0x14003b572  jz      short loc_14003B580
0x14003b574  call    cs:__imp_FltReleaseFileNameInformation
0x14003b57b  nop     dword ptr [rax+rax+00h]
0x14003b580  mov     eax, ebx
0x14003b582  jmp     short loc_14003B601
0x14003b584  mov     rdx, [rbp+FileNameInformation]
0x14003b588  mov     rcx, rdi; NameCtrl
0x14003b58b  movzx   edx, word ptr [rdx+8]; NewSize
0x14003b58f  call    cs:__imp_FltCheckAndGrowNameControl
0x14003b596  nop     dword ptr [rax+rax+00h]
0x14003b59b  mov     ebx, eax
0x14003b59d  test    eax, eax
0x14003b59f  jns     short loc_14003B5CB
0x14003b5a1  mov     rdx, [rbp+arg_20]; int
0x14003b5a5  lea     rax, aApiGrowingFltN; "API: Growing FLT_NAME_CONTROL"
0x14003b5ac  lea     r9, aUnionfsUnionfs_34; "UnionFs::UnionFsFilter::PassthroughName"...
0x14003b5b3  mov     [rsp+50h+var_30], rax; char *
0x14003b5b8  mov     r8, 175000F0616h; struct UnionFs::StackEventTracer *
0x14003b5c2  mov     ecx, ebx; this
0x14003b5c4  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003b5c9  jmp     short loc_14003B563
0x14003b5cb  mov     rdx, [rbp+FileNameInformation]
0x14003b5cf  mov     rcx, rdi; DestinationString
0x14003b5d2  add     rdx, 8; SourceString
0x14003b5d6  call    cs:__imp_RtlCopyUnicodeString
0x14003b5dd  nop     dword ptr [rax+rax+00h]
0x14003b5e2  mov     rcx, [rbp+FileNameInformation]; FileNameInformation
0x14003b5e6  mov     [rbp+FileNameInformation], 0
0x14003b5ee  test    rcx, rcx
0x14003b5f1  jz      short loc_14003B5FF
0x14003b5f3  call    cs:__imp_FltReleaseFileNameInformation
0x14003b5fa  nop     dword ptr [rax+rax+00h]
0x14003b5ff  xor     eax, eax
0x14003b601  mov     rbx, [rsp+50h+arg_8]
0x14003b606  mov     rdi, [rsp+50h+arg_10]
0x14003b60b  add     rsp, 50h
0x14003b60f  pop     rbp
0x14003b610  retn
```
