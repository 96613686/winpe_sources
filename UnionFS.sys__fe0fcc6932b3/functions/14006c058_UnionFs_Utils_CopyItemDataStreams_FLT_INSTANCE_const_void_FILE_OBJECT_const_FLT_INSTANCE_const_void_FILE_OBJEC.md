# UnionFs::Utils::CopyItemDataStreams(_FLT_INSTANCE const &,void *,_FILE_OBJECT const &,_FLT_INSTANCE const &,void *,_FILE_OBJECT const &,UnionFs::Utils::CopyItemFlags,UnionFs::StackEventTracer &)

- ea: `0x14006c058`
- end: `0x14006c3e6`
- name: `?CopyItemDataStreams@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@PEAXAEBU_FILE_OBJECT@@012W4CopyItemFlags@12@AEAVStackEventTracer@2@@Z`
- size: `910`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x14006c3ec`

## callees

- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x14006b03c`
- `0x14006b274`
- `0x14006c058`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006c123`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c374`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c389`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c123`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c374`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c389`
- `ntoskrnl!ExAllocatePool2` at `0x14006c0f3`
- `ntoskrnl!ExAllocatePool2` at `0x14006c0f3`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14006c209`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14006c209`
- `FLTMGR!FltSetInformationFile` at `0x14006c249`
- `FLTMGR!FltSetInformationFile` at `0x14006c249`
- `FLTMGR!FltQueryInformationFile` at `0x14006c159`
- `FLTMGR!FltQueryInformationFile` at `0x14006c159`

## string_xrefs

- `0x14006c0aa`: `ORIGIN: No stream copy flags set`
- `0x14006c330`: `UnionFs::Utils::CopyItemDataStreams`
- `0x14006c359`: `UnionFs::Utils::CopyItemDataStreams`
- `0x14006c3af`: `UnionFs::Utils::CopyItemDataStreams`
- `0x14006c287`: `PUSH: Copying default stream`
- `0x14006c1d9`: `curStreamsInfo.StreamNameLength <= static_cast<ULONG>(USHORT_MAX)`
- `0x14006c2fe`: `(curStreamsInfo.NextEntryOffset == 0) || ((curStreamsInfo.NextEntryOffset + sizeof(FILE_STREAM_INFORMATION)) <= fileInfoSize)`
- `0x14006c348`: `PUSH: Copying alternate data stream`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::CopyItemDataStreams(
        struct _FLT_INSTANCE *a1,
        struct _FLT_INSTANCE *a2,
        struct _FILE_OBJECT *a3,
        struct _FLT_INSTANCE *a4,
        struct _FLT_INSTANCE *a5,
        struct _FILE_OBJECT *a6,
        char a7,
        __int64 a8)
{
  struct _FLT_INSTANCE *v8; // rdi
  const char *v9; // rax
  __int64 v10; // r8
  unsigned int v11; // ebx
  unsigned int *v12; // rbx
  ULONG v13; // r15d
  bool v14; // zf
  __int64 v15; // rdx
  unsigned __int64 v16; // r13
  unsigned int *Pool2; // rax
  unsigned int *v18; // r14
  int v19; // edi
  const char *v20; // rax
  __int64 v21; // r8
  struct _FLT_INSTANCE *v22; // r15
  const char *v23; // rax
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 v26; // rax
  const char *LengthReturned; // [rsp+28h] [rbp-91h]
  ULONG v29; // [rsp+50h] [rbp-69h] BYREF
  struct _FLT_INSTANCE *FileInformation; // [rsp+58h] [rbp-61h] BYREF
  PFILE_OBJECT v31; // [rsp+60h] [rbp-59h]
  PFLT_INSTANCE Instance; // [rsp+68h] [rbp-51h]
  PFILE_OBJECT FileObject; // [rsp+70h] [rbp-49h]
  UNICODE_STRING String1; // [rsp+78h] [rbp-41h] BYREF
  UNICODE_STRING String2; // [rsp+88h] [rbp-31h] BYREF
  struct _FLT_INSTANCE *v36; // [rsp+98h] [rbp-21h]
  struct _FLT_INSTANCE *v37; // [rsp+A0h] [rbp-19h]
  __int128 v38; // [rsp+A8h] [rbp-11h] BYREF

  v8 = a1;
  v36 = a5;
  v31 = a6;
  Instance = a4;
  FileObject = a3;
  v37 = a2;
  FileInformation = a1;
  if ( (a7 & 6) != 0 )
  {
    v12 = 0;
    v29 = 0;
    v13 = 32;
    while ( 1 )
    {
      v14 = v13 == -2048;
      v13 += 2048;
      v15 = v13;
      if ( v14 )
        v15 = 1;
      v16 = v13;
      Pool2 = (unsigned int *)ExAllocatePool2(256, v15, 1651721813);
      v18 = Pool2;
      if ( Pool2 )
        memset(Pool2, 0, v13);
      else
        v18 = 0;
      if ( v12 )
        ExFreePoolWithTag(v12, 0);
      if ( !v18 )
      {
        v9 = "ORIGIN: Allocating stream info buffer";
        v10 = 0x26C00211DD7LL;
        v11 = -1073741670;
        goto LABEL_42;
      }
      v12 = v18;
      v19 = FltQueryInformationFile(v8, FileObject, v18, v13, FileStreamInformation, &v29);
      if ( v19 != -2147483643 && v19 != -1073741789 )
        break;
      v8 = FileInformation;
    }
    if ( v19 >= 0 )
    {
      if ( v29 )
      {
        v22 = FileInformation;
        *(_QWORD *)&String2.Length = 1048590;
        v38 = *(_OWORD *)L"::$DATA";
        String2.Buffer = (PWSTR)&v38;
        while ( v12 )
        {
          if ( v12[1] > 0xFFFF )
            MicrosoftTelemetryAssertTriggeredMsgKM("curStreamsInfo.StreamNameLength <= static_cast<ULONG>(USHORT_MAX)");
          String1.Length = *((_WORD *)v12 + 2);
          String1.MaximumLength = String1.Length;
          *(_DWORD *)(&String1.MaximumLength + 1) = 0;
          String1.Buffer = (PWSTR)(v12 + 6);
          if ( RtlCompareUnicodeString(&String1, &String2, 1u) )
          {
            if ( (a7 & 4) != 0 )
            {
              v19 = UnionFs::Utils::CopyDataStream(
                      v22,
                      v37,
                      FileObject,
                      &String1,
                      Instance,
                      v36,
                      v31,
                      &String1,
                      *((const struct _UNICODE_STRING **)v12 + 1),
                      a8);
              if ( v19 < 0 )
              {
                v23 = "PUSH: Copying alternate data stream";
                v24 = 0x27A00211E29LL;
                goto LABEL_38;
              }
            }
          }
          else if ( (a7 & 2) != 0 )
          {
            FileInformation = (struct _FLT_INSTANCE *)*((_QWORD *)v12 + 1);
            v19 = FltSetInformationFile(Instance, v31, &FileInformation, 8u, FileEndOfFileInformation);
            if ( v19 < 0 )
            {
              v20 = "API: Setting target EOF";
              v21 = 0x26E00211E09LL;
              goto LABEL_36;
            }
            v19 = UnionFs::Utils::CopyDataStream(
                    v22,
                    FileObject,
                    Instance,
                    v31,
                    *((_QWORD *)v12 + 1),
                    (ULONG)LengthReturned,
                    a8);
            if ( v19 < 0 )
            {
              v23 = "PUSH: Copying default stream";
              v24 = 0x27900211E14LL;
LABEL_38:
              UnionFs::ProcessTraceStatusPushLocation(
                (UnionFs *)(unsigned int)v19,
                a8,
                (struct UnionFs::StackEventTracer *)v24,
                (unsigned __int64)"UnionFs::Utils::CopyItemDataStreams",
                v23,
                LengthReturned);
              goto LABEL_39;
            }
          }
          v25 = *v12;
          if ( (_DWORD)v25 && v25 + 32 > v16 )
            MicrosoftTelemetryAssertTriggeredMsgKM(
              "(curStreamsInfo.NextEntryOffset == 0) || ((curStreamsInfo.NextEntryOffset + sizeof(FILE_STREAM_INFORMATION"
              ")) <= fileInfoSize)");
          v26 = *v12;
          if ( (_DWORD)v26 )
            v12 = (unsigned int *)((char *)v12 + v26);
          else
            v12 = 0;
        }
      }
      ExFreePoolWithTag(v18, 0);
      return 0;
    }
    else
    {
      v20 = "API: Querying streams information";
      v21 = 0x26D00211DE5LL;
LABEL_36:
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)v19,
        a8,
        (struct UnionFs::StackEventTracer *)v21,
        (unsigned __int64)"UnionFs::Utils::CopyItemDataStreams",
        v20,
        LengthReturned);
LABEL_39:
      ExFreePoolWithTag(v18, 0);
      return (unsigned int)v19;
    }
  }
  else
  {
    v9 = "ORIGIN: No stream copy flags set";
    v10 = 0x26B00211DC3LL;
    v11 = -1073741811;
LABEL_42:
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)v11,
      a8,
      (struct UnionFs::StackEventTracer *)v10,
      (unsigned __int64)"UnionFs::Utils::CopyItemDataStreams",
      v9,
      LengthReturned);
    return v11;
  }
}

```

## disassembly

```asm
0x14006c058  push    rbp
0x14006c05a  push    rbx
0x14006c05b  push    rsi
0x14006c05c  push    rdi
0x14006c05d  push    r13
0x14006c05f  push    r14
0x14006c061  push    r15
0x14006c063  lea     rbp, [rsp-7]
0x14006c068  sub     rsp, 0C0h
0x14006c06f  mov     rax, cs:__security_cookie
0x14006c076  xor     rax, rsp
0x14006c079  mov     [rbp+37h+var_38], rax
0x14006c07d  test    [rbp+37h+arg_30], 6
0x14006c081  mov     rdi, rcx
0x14006c084  mov     rax, [rbp+37h+arg_20]
0x14006c088  mov     rsi, qword ptr [rbp+37h+arg_38]
0x14006c08c  mov     [rbp+37h+var_58], rax
0x14006c090  mov     rax, [rbp+37h+arg_28]
0x14006c094  mov     [rbp+37h+var_90], rax
0x14006c098  mov     [rbp+37h+Instance], r9
0x14006c09c  mov     [rbp+37h+FileObject], r8
0x14006c0a0  mov     [rbp+37h+var_50], rdx
0x14006c0a4  mov     [rbp+37h+FileInformation], rcx
0x14006c0a8  jnz     short loc_14006C0C5
0x14006c0aa  lea     rax, aOriginNoStream; "ORIGIN: No stream copy flags set"
0x14006c0b1  mov     r8, 26B00211DC3h
0x14006c0bb  mov     ebx, 0C000000Dh
0x14006c0c0  jmp     loc_14006C3AF
0x14006c0c5  xor     ebx, ebx
0x14006c0c7  mov     [rbp+37h+var_A0], ebx
0x14006c0ca  lea     r15d, [rbx+20h]
0x14006c0ce  lea     eax, [rbx+1]
0x14006c0d1  jmp     short loc_14006C0D7
0x14006c0d3  mov     rdi, [rbp+37h+FileInformation]
0x14006c0d7  add     r15d, 800h
0x14006c0de  mov     ecx, 100h
0x14006c0e3  mov     edx, r15d
0x14006c0e6  mov     r8d, 62734655h
0x14006c0ec  cmovz   rdx, rax
0x14006c0f0  mov     r13d, r15d
0x14006c0f3  call    cs:__imp_ExAllocatePool2
0x14006c0fa  nop     dword ptr [rax+rax+00h]
0x14006c0ff  mov     r14, rax
0x14006c102  test    rax, rax
0x14006c105  jz      short loc_14006C116
0x14006c107  mov     r8d, r13d; Size
0x14006c10a  xor     edx, edx; Val
0x14006c10c  mov     rcx, rax; void *
0x14006c10f  call    memset
0x14006c114  jmp     short loc_14006C119
0x14006c116  xor     r14d, r14d
0x14006c119  test    rbx, rbx
0x14006c11c  jz      short loc_14006C12F
0x14006c11e  xor     edx, edx; Tag
0x14006c120  mov     rcx, rbx; P
0x14006c123  call    cs:__imp_ExFreePoolWithTag
0x14006c12a  nop     dword ptr [rax+rax+00h]
0x14006c12f  test    r14, r14
0x14006c132  jz      loc_14006C399
0x14006c138  mov     rdx, [rbp+37h+FileObject]; FileObject
0x14006c13c  lea     rax, [rbp+37h+var_A0]
0x14006c140  mov     [rsp+0F0h+LengthReturned], rax; char *
0x14006c145  mov     r9d, r15d; Length
0x14006c148  mov     r8, r14; FileInformation
0x14006c14b  mov     [rsp+0F0h+FileInformationClass], 16h; FileInformationClass
0x14006c153  mov     rcx, rdi; Instance
0x14006c156  mov     rbx, r14
0x14006c159  call    cs:__imp_FltQueryInformationFile
0x14006c160  nop     dword ptr [rax+rax+00h]
0x14006c165  mov     edi, eax
0x14006c167  cmp     eax, 80000005h
0x14006c16c  mov     eax, 1
0x14006c171  jz      loc_14006C0D3
0x14006c177  cmp     edi, 0C0000023h
0x14006c17d  jz      loc_14006C0D3
0x14006c183  test    edi, edi
0x14006c185  jns     short loc_14006C19D
0x14006c187  lea     rax, aApiQueryingStr; "API: Querying streams information"
0x14006c18e  mov     r8, 26D00211DE5h
0x14006c198  jmp     loc_14006C330
0x14006c19d  cmp     [rbp+37h+var_A0], 0
0x14006c1a1  jz      loc_14006C384
0x14006c1a7  movups  xmm0, xmmword ptr cs:aData; "::$DATA"
0x14006c1ae  mov     r15, [rbp+37h+FileInformation]
0x14006c1b2  lea     rax, [rbp+37h+var_48]
0x14006c1b6  mov     qword ptr [rbp+37h+String2.Length], 10000Eh
0x14006c1be  movdqu  [rbp+37h+var_48], xmm0
0x14006c1c3  mov     [rbp+37h+String2.Buffer], rax
0x14006c1c7  test    rbx, rbx
0x14006c1ca  jz      loc_14006C384
0x14006c1d0  cmp     dword ptr [rbx+4], 0FFFFh
0x14006c1d7  jbe     short loc_14006C1E5
0x14006c1d9  lea     rcx, aCurstreamsinfo; "curStreamsInfo.StreamNameLength <= stat"...
0x14006c1e0  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14006c1e5  movzx   eax, word ptr [rbx+4]
0x14006c1e9  lea     rdx, [rbp+37h+String2]; String2
0x14006c1ed  mov     [rbp+37h+String1.Length], ax
0x14006c1f1  lea     rcx, [rbp+37h+String1]; String1
0x14006c1f5  mov     [rbp+37h+String1.MaximumLength], ax
0x14006c1f9  mov     r8b, 1; CaseInSensitive
0x14006c1fc  xor     eax, eax
0x14006c1fe  mov     dword ptr [rbp+37h+String1+4], eax
0x14006c201  lea     rax, [rbx+18h]
0x14006c205  mov     [rbp+37h+String1.Buffer], rax
0x14006c209  call    cs:__imp_RtlCompareUnicodeString
0x14006c210  nop     dword ptr [rax+rax+00h]
0x14006c215  test    eax, eax
0x14006c217  jnz     loc_14006C29D
0x14006c21d  test    [rbp+37h+arg_30], 2
0x14006c221  jz      loc_14006C2EF
0x14006c227  mov     rax, [rbx+8]
0x14006c22b  lea     r8, [rbp+37h+FileInformation]; FileInformation
0x14006c22f  mov     rdx, [rbp+37h+var_90]; FileObject
0x14006c233  mov     r9d, 8; Length
0x14006c239  mov     rcx, [rbp+37h+Instance]; Instance
0x14006c23d  mov     [rbp+37h+FileInformation], rax
0x14006c241  mov     [rsp+0F0h+FileInformationClass], 14h; FileInformationClass
0x14006c249  call    cs:__imp_FltSetInformationFile
0x14006c250  nop     dword ptr [rax+rax+00h]
0x14006c255  mov     edi, eax
0x14006c257  test    eax, eax
0x14006c259  js      loc_14006C31F
0x14006c25f  mov     rax, [rbx+8]
0x14006c263  mov     rcx, r15; InitiatingInstance
0x14006c266  mov     r9, [rbp+37h+var_90]; struct _FLT_INSTANCE *
0x14006c26a  mov     r8, [rbp+37h+Instance]; Instance
0x14006c26e  mov     rdx, [rbp+37h+FileObject]; FileObject
0x14006c272  mov     [rsp+0F0h+var_C0], rsi; bool
0x14006c277  mov     qword ptr [rsp+0F0h+FileInformationClass], rax; BytesWritten
0x14006c27c  call    ?CopyDataStream@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@01_J_NAEAVStackEventTracer@2@@Z; UnionFs::Utils::CopyDataStream(_FLT_INSTANCE const &,_FILE_OBJECT const &,_FLT_INSTANCE const &,_FILE_OBJECT const &,__int64,bool,UnionFs::StackEventTracer &)
0x14006c281  mov     edi, eax
0x14006c283  test    eax, eax
0x14006c285  jns     short loc_14006C2EF
0x14006c287  lea     rax, aPushCopyingDef; "PUSH: Copying default stream"
0x14006c28e  mov     r8, 27900211E14h
0x14006c298  jmp     loc_14006C359
0x14006c29d  test    [rbp+37h+arg_30], 4
0x14006c2a1  jz      short loc_14006C2EF
0x14006c2a3  mov     rax, [rbx+8]
0x14006c2a7  lea     r9, [rbp+37h+String1]; struct _FILE_OBJECT *
0x14006c2ab  mov     r8, [rbp+37h+FileObject]; void *
0x14006c2af  mov     rcx, r15; InitiatingInstance
0x14006c2b2  mov     rdx, [rbp+37h+var_50]; struct _FLT_INSTANCE *
0x14006c2b6  mov     [rsp+0F0h+var_A8], rsi; __int64
0x14006c2bb  mov     [rsp+0F0h+var_B0], rax; struct _UNICODE_STRING *
0x14006c2c0  lea     rax, [rbp+37h+String1]
0x14006c2c4  mov     [rsp+0F0h+var_B8], rax; struct _FILE_OBJECT *
0x14006c2c9  mov     rax, [rbp+37h+var_90]
0x14006c2cd  mov     [rsp+0F0h+var_C0], rax; void *
0x14006c2d2  mov     rax, [rbp+37h+var_58]
0x14006c2d6  mov     [rsp+0F0h+LengthReturned], rax; char *
0x14006c2db  mov     rax, [rbp+37h+Instance]
0x14006c2df  mov     qword ptr [rsp+0F0h+FileInformationClass], rax; Instance
0x14006c2e4  call    ?CopyDataStream@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@PEAXAEBU_FILE_OBJECT@@AEBU_UNICODE_STRING@@0123_JAEAVStackEventTracer@2@@Z; UnionFs::Utils::CopyDataStream(_FLT_INSTANCE const &,void *,_FILE_OBJECT const &,_UNICODE_STRING const &,_FLT_INSTANCE const &,void *,_FILE_OBJECT const &,_UNICODE_STRING const &,__int64,UnionFs::StackEventTracer &)
0x14006c2e9  mov     edi, eax
0x14006c2eb  test    eax, eax
0x14006c2ed  js      short loc_14006C348
0x14006c2ef  mov     eax, [rbx]
0x14006c2f1  test    eax, eax
0x14006c2f3  jz      short loc_14006C30A
0x14006c2f5  add     rax, 20h ; ' '
0x14006c2f9  cmp     rax, r13
0x14006c2fc  jbe     short loc_14006C30A
0x14006c2fe  lea     rcx, aCurstreamsinfo_0; "(curStreamsInfo.NextEntryOffset == 0) |"...
0x14006c305  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14006c30a  mov     eax, [rbx]
0x14006c30c  test    eax, eax
0x14006c30e  jz      short loc_14006C318
0x14006c310  add     rbx, rax
0x14006c313  jmp     loc_14006C1C7
0x14006c318  xor     ebx, ebx
0x14006c31a  jmp     loc_14006C1C7
0x14006c31f  lea     rax, aApiSettingTarg; "API: Setting target EOF"
0x14006c326  mov     r8, 26E00211E09h; struct UnionFs::StackEventTracer *
0x14006c330  lea     r9, aUnionfsUtilsCo_6; "UnionFs::Utils::CopyItemDataStreams"
0x14006c337  mov     qword ptr [rsp+0F0h+FileInformationClass], rax; char *
0x14006c33c  mov     rdx, rsi; int
0x14006c33f  mov     ecx, edi; this
0x14006c341  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006c346  jmp     short loc_14006C36F
0x14006c348  lea     rax, aPushCopyingAlt; "PUSH: Copying alternate data stream"
0x14006c34f  mov     r8, 27A00211E29h; struct UnionFs::StackEventTracer *
0x14006c359  lea     r9, aUnionfsUtilsCo_6; "UnionFs::Utils::CopyItemDataStreams"
0x14006c360  mov     qword ptr [rsp+0F0h+FileInformationClass], rax; char *
0x14006c365  mov     rdx, rsi; int
0x14006c368  mov     ecx, edi; this
0x14006c36a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006c36f  xor     edx, edx; Tag
0x14006c371  mov     rcx, r14; P
0x14006c374  call    cs:__imp_ExFreePoolWithTag
0x14006c37b  nop     dword ptr [rax+rax+00h]
0x14006c380  mov     eax, edi
0x14006c382  jmp     short loc_14006C3C7
0x14006c384  xor     edx, edx; Tag
0x14006c386  mov     rcx, r14; P
0x14006c389  call    cs:__imp_ExFreePoolWithTag
0x14006c390  nop     dword ptr [rax+rax+00h]
0x14006c395  xor     eax, eax
0x14006c397  jmp     short loc_14006C3C7
0x14006c399  lea     rax, aOriginAllocati_5; "ORIGIN: Allocating stream info buffer"
0x14006c3a0  mov     r8, 26C00211DD7h; struct UnionFs::StackEventTracer *
0x14006c3aa  mov     ebx, 0C000009Ah
0x14006c3af  lea     r9, aUnionfsUtilsCo_6; "UnionFs::Utils::CopyItemDataStreams"
0x14006c3b6  mov     qword ptr [rsp+0F0h+FileInformationClass], rax; char *
0x14006c3bb  mov     rdx, rsi; int
0x14006c3be  mov     ecx, ebx; this
0x14006c3c0  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006c3c5  mov     eax, ebx
0x14006c3c7  mov     rcx, [rbp+37h+var_38]
0x14006c3cb  xor     rcx, rsp; StackCookie
0x14006c3ce  call    __security_check_cookie
0x14006c3d3  add     rsp, 0C0h
0x14006c3da  pop     r15
0x14006c3dc  pop     r14
0x14006c3de  pop     r13
0x14006c3e0  pop     rdi
0x14006c3e1  pop     rsi
0x14006c3e2  pop     rbx
0x14006c3e3  pop     rbp
0x14006c3e4  retn
```
