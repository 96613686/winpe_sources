# UnionFs::Utils::CopyItemDataStreams(_FLT_INSTANCE const &,void *,_FILE_OBJECT const &,_FLT_INSTANCE const &,void *,_FILE_OBJECT const &,UnionFs::Utils::CopyItemFlags,UnionFs::StackEventTracer &)

- ea: `0x14006be68`
- end: `0x14006c1f6`
- name: `?CopyItemDataStreams@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@PEAXAEBU_FILE_OBJECT@@012W4CopyItemFlags@12@AEAVStackEventTracer@2@@Z`
- size: `910`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14006c1fc`

## callees

- `0x140056a50`
- `0x140056ac4`
- `0x140056afc`
- `0x14006ae4c`
- `0x14006b084`
- `0x14006be68`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006bf33`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c184`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c199`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bf33`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c184`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006c199`
- `ntoskrnl!ExAllocatePool2` at `0x14006bf03`
- `ntoskrnl!ExAllocatePool2` at `0x14006bf03`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14006c019`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14006c019`
- `FLTMGR!FltSetInformationFile` at `0x14006c059`
- `FLTMGR!FltSetInformationFile` at `0x14006c059`
- `FLTMGR!FltQueryInformationFile` at `0x14006bf69`
- `FLTMGR!FltQueryInformationFile` at `0x14006bf69`

## string_xrefs

- `0x14006beba`: `ORIGIN: No stream copy flags set`
- `0x14006c140`: `UnionFs::Utils::CopyItemDataStreams`
- `0x14006c169`: `UnionFs::Utils::CopyItemDataStreams`
- `0x14006c1bf`: `UnionFs::Utils::CopyItemDataStreams`
- `0x14006c097`: `PUSH: Copying default stream`
- `0x14006bfe9`: `curStreamsInfo.StreamNameLength <= static_cast<ULONG>(USHORT_MAX)`
- `0x14006c10e`: `(curStreamsInfo.NextEntryOffset == 0) || ((curStreamsInfo.NextEntryOffset + sizeof(FILE_STREAM_INFORMATION)) <= fileInfoSize)`
- `0x14006c158`: `PUSH: Copying alternate data stream`

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
        v10 = 0x26C00211DA1LL;
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
                v24 = 0x27A00211DF3LL;
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
              v21 = 0x26E00211DD3LL;
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
              v24 = 0x27900211DDELL;
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
      v21 = 0x26D00211DAFLL;
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
    v10 = 0x26B00211D8DLL;
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
0x14006be68  push    rbp
0x14006be6a  push    rbx
0x14006be6b  push    rsi
0x14006be6c  push    rdi
0x14006be6d  push    r13
0x14006be6f  push    r14
0x14006be71  push    r15
0x14006be73  lea     rbp, [rsp-7]
0x14006be78  sub     rsp, 0C0h
0x14006be7f  mov     rax, cs:__security_cookie
0x14006be86  xor     rax, rsp
0x14006be89  mov     [rbp+37h+var_38], rax
0x14006be8d  test    [rbp+37h+arg_30], 6
0x14006be91  mov     rdi, rcx
0x14006be94  mov     rax, [rbp+37h+arg_20]
0x14006be98  mov     rsi, qword ptr [rbp+37h+arg_38]
0x14006be9c  mov     [rbp+37h+var_58], rax
0x14006bea0  mov     rax, [rbp+37h+arg_28]
0x14006bea4  mov     [rbp+37h+var_90], rax
0x14006bea8  mov     [rbp+37h+Instance], r9
0x14006beac  mov     [rbp+37h+FileObject], r8
0x14006beb0  mov     [rbp+37h+var_50], rdx
0x14006beb4  mov     [rbp+37h+FileInformation], rcx
0x14006beb8  jnz     short loc_14006BED5
0x14006beba  lea     rax, aOriginNoStream; "ORIGIN: No stream copy flags set"
0x14006bec1  mov     r8, 26B00211D8Dh
0x14006becb  mov     ebx, 0C000000Dh
0x14006bed0  jmp     loc_14006C1BF
0x14006bed5  xor     ebx, ebx
0x14006bed7  mov     [rbp+37h+var_A0], ebx
0x14006beda  lea     r15d, [rbx+20h]
0x14006bede  lea     eax, [rbx+1]
0x14006bee1  jmp     short loc_14006BEE7
0x14006bee3  mov     rdi, [rbp+37h+FileInformation]
0x14006bee7  add     r15d, 800h
0x14006beee  mov     ecx, 100h
0x14006bef3  mov     edx, r15d
0x14006bef6  mov     r8d, 62734655h
0x14006befc  cmovz   rdx, rax
0x14006bf00  mov     r13d, r15d
0x14006bf03  call    cs:__imp_ExAllocatePool2
0x14006bf0a  nop     dword ptr [rax+rax+00h]
0x14006bf0f  mov     r14, rax
0x14006bf12  test    rax, rax
0x14006bf15  jz      short loc_14006BF26
0x14006bf17  mov     r8d, r13d; Size
0x14006bf1a  xor     edx, edx; Val
0x14006bf1c  mov     rcx, rax; void *
0x14006bf1f  call    memset
0x14006bf24  jmp     short loc_14006BF29
0x14006bf26  xor     r14d, r14d
0x14006bf29  test    rbx, rbx
0x14006bf2c  jz      short loc_14006BF3F
0x14006bf2e  xor     edx, edx; Tag
0x14006bf30  mov     rcx, rbx; P
0x14006bf33  call    cs:__imp_ExFreePoolWithTag
0x14006bf3a  nop     dword ptr [rax+rax+00h]
0x14006bf3f  test    r14, r14
0x14006bf42  jz      loc_14006C1A9
0x14006bf48  mov     rdx, [rbp+37h+FileObject]; FileObject
0x14006bf4c  lea     rax, [rbp+37h+var_A0]
0x14006bf50  mov     [rsp+0F0h+LengthReturned], rax; char *
0x14006bf55  mov     r9d, r15d; Length
0x14006bf58  mov     r8, r14; FileInformation
0x14006bf5b  mov     [rsp+0F0h+FileInformationClass], 16h; FileInformationClass
0x14006bf63  mov     rcx, rdi; Instance
0x14006bf66  mov     rbx, r14
0x14006bf69  call    cs:__imp_FltQueryInformationFile
0x14006bf70  nop     dword ptr [rax+rax+00h]
0x14006bf75  mov     edi, eax
0x14006bf77  cmp     eax, 80000005h
0x14006bf7c  mov     eax, 1
0x14006bf81  jz      loc_14006BEE3
0x14006bf87  cmp     edi, 0C0000023h
0x14006bf8d  jz      loc_14006BEE3
0x14006bf93  test    edi, edi
0x14006bf95  jns     short loc_14006BFAD
0x14006bf97  lea     rax, aApiQueryingStr; "API: Querying streams information"
0x14006bf9e  mov     r8, 26D00211DAFh
0x14006bfa8  jmp     loc_14006C140
0x14006bfad  cmp     [rbp+37h+var_A0], 0
0x14006bfb1  jz      loc_14006C194
0x14006bfb7  movups  xmm0, xmmword ptr cs:aData; "::$DATA"
0x14006bfbe  mov     r15, [rbp+37h+FileInformation]
0x14006bfc2  lea     rax, [rbp+37h+var_48]
0x14006bfc6  mov     qword ptr [rbp+37h+String2.Length], 10000Eh
0x14006bfce  movdqu  [rbp+37h+var_48], xmm0
0x14006bfd3  mov     [rbp+37h+String2.Buffer], rax
0x14006bfd7  test    rbx, rbx
0x14006bfda  jz      loc_14006C194
0x14006bfe0  cmp     dword ptr [rbx+4], 0FFFFh
0x14006bfe7  jbe     short loc_14006BFF5
0x14006bfe9  lea     rcx, aCurstreamsinfo; "curStreamsInfo.StreamNameLength <= stat"...
0x14006bff0  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14006bff5  movzx   eax, word ptr [rbx+4]
0x14006bff9  lea     rdx, [rbp+37h+String2]; String2
0x14006bffd  mov     [rbp+37h+String1.Length], ax
0x14006c001  lea     rcx, [rbp+37h+String1]; String1
0x14006c005  mov     [rbp+37h+String1.MaximumLength], ax
0x14006c009  mov     r8b, 1; CaseInSensitive
0x14006c00c  xor     eax, eax
0x14006c00e  mov     dword ptr [rbp+37h+String1+4], eax
0x14006c011  lea     rax, [rbx+18h]
0x14006c015  mov     [rbp+37h+String1.Buffer], rax
0x14006c019  call    cs:__imp_RtlCompareUnicodeString
0x14006c020  nop     dword ptr [rax+rax+00h]
0x14006c025  test    eax, eax
0x14006c027  jnz     loc_14006C0AD
0x14006c02d  test    [rbp+37h+arg_30], 2
0x14006c031  jz      loc_14006C0FF
0x14006c037  mov     rax, [rbx+8]
0x14006c03b  lea     r8, [rbp+37h+FileInformation]; FileInformation
0x14006c03f  mov     rdx, [rbp+37h+var_90]; FileObject
0x14006c043  mov     r9d, 8; Length
0x14006c049  mov     rcx, [rbp+37h+Instance]; Instance
0x14006c04d  mov     [rbp+37h+FileInformation], rax
0x14006c051  mov     [rsp+0F0h+FileInformationClass], 14h; FileInformationClass
0x14006c059  call    cs:__imp_FltSetInformationFile
0x14006c060  nop     dword ptr [rax+rax+00h]
0x14006c065  mov     edi, eax
0x14006c067  test    eax, eax
0x14006c069  js      loc_14006C12F
0x14006c06f  mov     rax, [rbx+8]
0x14006c073  mov     rcx, r15; InitiatingInstance
0x14006c076  mov     r9, [rbp+37h+var_90]; struct _FLT_INSTANCE *
0x14006c07a  mov     r8, [rbp+37h+Instance]; Instance
0x14006c07e  mov     rdx, [rbp+37h+FileObject]; FileObject
0x14006c082  mov     [rsp+0F0h+var_C0], rsi; bool
0x14006c087  mov     qword ptr [rsp+0F0h+FileInformationClass], rax; BytesWritten
0x14006c08c  call    ?CopyDataStream@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@01_J_NAEAVStackEventTracer@2@@Z; UnionFs::Utils::CopyDataStream(_FLT_INSTANCE const &,_FILE_OBJECT const &,_FLT_INSTANCE const &,_FILE_OBJECT const &,__int64,bool,UnionFs::StackEventTracer &)
0x14006c091  mov     edi, eax
0x14006c093  test    eax, eax
0x14006c095  jns     short loc_14006C0FF
0x14006c097  lea     rax, aPushCopyingDef; "PUSH: Copying default stream"
0x14006c09e  mov     r8, 27900211DDEh
0x14006c0a8  jmp     loc_14006C169
0x14006c0ad  test    [rbp+37h+arg_30], 4
0x14006c0b1  jz      short loc_14006C0FF
0x14006c0b3  mov     rax, [rbx+8]
0x14006c0b7  lea     r9, [rbp+37h+String1]; struct _FILE_OBJECT *
0x14006c0bb  mov     r8, [rbp+37h+FileObject]; void *
0x14006c0bf  mov     rcx, r15; InitiatingInstance
0x14006c0c2  mov     rdx, [rbp+37h+var_50]; struct _FLT_INSTANCE *
0x14006c0c6  mov     [rsp+0F0h+var_A8], rsi; __int64
0x14006c0cb  mov     [rsp+0F0h+var_B0], rax; struct _UNICODE_STRING *
0x14006c0d0  lea     rax, [rbp+37h+String1]
0x14006c0d4  mov     [rsp+0F0h+var_B8], rax; struct _FILE_OBJECT *
0x14006c0d9  mov     rax, [rbp+37h+var_90]
0x14006c0dd  mov     [rsp+0F0h+var_C0], rax; void *
0x14006c0e2  mov     rax, [rbp+37h+var_58]
0x14006c0e6  mov     [rsp+0F0h+LengthReturned], rax; char *
0x14006c0eb  mov     rax, [rbp+37h+Instance]
0x14006c0ef  mov     qword ptr [rsp+0F0h+FileInformationClass], rax; Instance
0x14006c0f4  call    ?CopyDataStream@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@PEAXAEBU_FILE_OBJECT@@AEBU_UNICODE_STRING@@0123_JAEAVStackEventTracer@2@@Z; UnionFs::Utils::CopyDataStream(_FLT_INSTANCE const &,void *,_FILE_OBJECT const &,_UNICODE_STRING const &,_FLT_INSTANCE const &,void *,_FILE_OBJECT const &,_UNICODE_STRING const &,__int64,UnionFs::StackEventTracer &)
0x14006c0f9  mov     edi, eax
0x14006c0fb  test    eax, eax
0x14006c0fd  js      short loc_14006C158
0x14006c0ff  mov     eax, [rbx]
0x14006c101  test    eax, eax
0x14006c103  jz      short loc_14006C11A
0x14006c105  add     rax, 20h ; ' '
0x14006c109  cmp     rax, r13
0x14006c10c  jbe     short loc_14006C11A
0x14006c10e  lea     rcx, aCurstreamsinfo_0; "(curStreamsInfo.NextEntryOffset == 0) |"...
0x14006c115  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14006c11a  mov     eax, [rbx]
0x14006c11c  test    eax, eax
0x14006c11e  jz      short loc_14006C128
0x14006c120  add     rbx, rax
0x14006c123  jmp     loc_14006BFD7
0x14006c128  xor     ebx, ebx
0x14006c12a  jmp     loc_14006BFD7
0x14006c12f  lea     rax, aApiSettingTarg; "API: Setting target EOF"
0x14006c136  mov     r8, 26E00211DD3h; struct UnionFs::StackEventTracer *
0x14006c140  lea     r9, aUnionfsUtilsCo_6; "UnionFs::Utils::CopyItemDataStreams"
0x14006c147  mov     qword ptr [rsp+0F0h+FileInformationClass], rax; char *
0x14006c14c  mov     rdx, rsi; int
0x14006c14f  mov     ecx, edi; this
0x14006c151  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006c156  jmp     short loc_14006C17F
0x14006c158  lea     rax, aPushCopyingAlt; "PUSH: Copying alternate data stream"
0x14006c15f  mov     r8, 27A00211DF3h; struct UnionFs::StackEventTracer *
0x14006c169  lea     r9, aUnionfsUtilsCo_6; "UnionFs::Utils::CopyItemDataStreams"
0x14006c170  mov     qword ptr [rsp+0F0h+FileInformationClass], rax; char *
0x14006c175  mov     rdx, rsi; int
0x14006c178  mov     ecx, edi; this
0x14006c17a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006c17f  xor     edx, edx; Tag
0x14006c181  mov     rcx, r14; P
0x14006c184  call    cs:__imp_ExFreePoolWithTag
0x14006c18b  nop     dword ptr [rax+rax+00h]
0x14006c190  mov     eax, edi
0x14006c192  jmp     short loc_14006C1D7
0x14006c194  xor     edx, edx; Tag
0x14006c196  mov     rcx, r14; P
0x14006c199  call    cs:__imp_ExFreePoolWithTag
0x14006c1a0  nop     dword ptr [rax+rax+00h]
0x14006c1a5  xor     eax, eax
0x14006c1a7  jmp     short loc_14006C1D7
0x14006c1a9  lea     rax, aOriginAllocati_5; "ORIGIN: Allocating stream info buffer"
0x14006c1b0  mov     r8, 26C00211DA1h; struct UnionFs::StackEventTracer *
0x14006c1ba  mov     ebx, 0C000009Ah
0x14006c1bf  lea     r9, aUnionfsUtilsCo_6; "UnionFs::Utils::CopyItemDataStreams"
0x14006c1c6  mov     qword ptr [rsp+0F0h+FileInformationClass], rax; char *
0x14006c1cb  mov     rdx, rsi; int
0x14006c1ce  mov     ecx, ebx; this
0x14006c1d0  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006c1d5  mov     eax, ebx
0x14006c1d7  mov     rcx, [rbp+37h+var_38]
0x14006c1db  xor     rcx, rsp; StackCookie
0x14006c1de  call    __security_check_cookie
0x14006c1e3  add     rsp, 0C0h
0x14006c1ea  pop     r15
0x14006c1ec  pop     r14
0x14006c1ee  pop     r13
0x14006c1f0  pop     rdi
0x14006c1f1  pop     rsi
0x14006c1f2  pop     rbx
0x14006c1f3  pop     rbp
0x14006c1f4  retn
```
