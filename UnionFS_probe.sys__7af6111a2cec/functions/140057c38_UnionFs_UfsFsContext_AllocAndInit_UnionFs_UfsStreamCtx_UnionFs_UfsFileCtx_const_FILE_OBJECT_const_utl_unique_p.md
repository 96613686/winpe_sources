# UnionFs::UfsFsContext::AllocAndInit(UnionFs::UfsStreamCtx &,UnionFs::UfsFileCtx const &,_FILE_OBJECT const &,utl::unique_ptr<UnionFs::UfsFsContext,utl::default_delete<UnionFs::UfsFsContext>> &,UnionFs::StackEventTracer &)

- ea: `0x140057c38`
- end: `0x140057e80`
- name: `?AllocAndInit@UfsFsContext@UnionFs@@SAJAEAVUfsStreamCtx@2@AEBVUfsFileCtx@2@AEBU_FILE_OBJECT@@AEAV?$unique_ptr@VUfsFsContext@UnionFs@@U?$default_delete@VUfsFsContext@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `584`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140026d7c`

## callees

- `0x140010148`
- `0x140056ac4`
- `0x140056afc`
- `0x140057554`
- `0x1400576a8`
- `0x140057a3c`
- `0x140057c38`

## import_xrefs

- `ntoskrnl!FsRtlFreeAePushLock` at `0x140057db8`
- `ntoskrnl!FsRtlFreeAePushLock` at `0x140057db8`
- `ntoskrnl!FsRtlInitializeOplock` at `0x140057ddf`
- `ntoskrnl!FsRtlInitializeOplock` at `0x140057ddf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057c6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057d16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057e03`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057c6d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057d16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057e03`
- `ntoskrnl!ExAllocatePool2` at `0x140057c89`
- `ntoskrnl!ExAllocatePool2` at `0x140057d35`
- `ntoskrnl!ExAllocatePool2` at `0x140057c89`
- `ntoskrnl!ExAllocatePool2` at `0x140057d35`
- `ntoskrnl!ExDeleteResourceLite` at `0x140057d05`
- `ntoskrnl!ExDeleteResourceLite` at `0x140057d05`
- `ntoskrnl!FsRtlAllocateAePushLock` at `0x140057cbc`
- `ntoskrnl!FsRtlAllocateAePushLock` at `0x140057cbc`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsFsContext::AllocAndInit(
        int a1,
        __int64 a2,
        __int64 a3,
        FSRTL_ADVANCED_FCB_HEADER **a4,
        int a5)
{
  FSRTL_ADVANCED_FCB_HEADER *v5; // rbx
  UnionFs::UfsFsContextNP *Pool2; // rax
  __int64 v11; // rbx
  __int64 AePushLock; // rdi
  __int64 v13; // rax
  FSRTL_ADVANCED_FCB_HEADER *v14; // rbx
  char *v16; // [rsp+28h] [rbp-50h]
  char *v17; // [rsp+28h] [rbp-50h]
  __int64 v18; // [rsp+30h] [rbp-48h] BYREF
  __int64 v19; // [rsp+98h] [rbp+20h] BYREF

  v5 = *a4;
  *a4 = 0;
  if ( v5 )
  {
    UnionFs::UfsFsContext::~UfsFsContext(v5);
    ExFreePoolWithTag(v5, 0);
  }
  Pool2 = (UnionFs::UfsFsContextNP *)ExAllocatePool2(66, 272, 1936082517);
  if ( !Pool2 || (v11 = UnionFs::UfsFsContextNP::UfsFsContextNP(Pool2)) == 0 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a5,
      (struct UnionFs::StackEventTracer *)0x113001D0028LL,
      (unsigned __int64)"UnionFs::UfsFsContextNP::AllocAndInit",
      "ORIGIN: Allocating non-paged fs ctx",
      v16);
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)0xC000009ALL,
      a5,
      (struct UnionFs::StackEventTracer *)0x119001D0052LL,
      (unsigned __int64)"UnionFs::UfsFsContext::AllocAndInit",
      "PUSH: Creating NP ctx",
      v17);
    return 3221225626LL;
  }
  AePushLock = FsRtlAllocateAePushLock(512, 1700873813);
  if ( !AePushLock )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a5,
      (struct UnionFs::StackEventTracer *)0x11D001D005ALL,
      (unsigned __int64)"UnionFs::UfsFsContext::AllocAndInit",
      "ORIGIN: Allocating AE pushlock",
      v16);
LABEL_7:
    ExDeleteResourceLite((PERESOURCE)(v11 + 56));
    ExFreePoolWithTag((PVOID)v11, 0);
    return 3221225626LL;
  }
  v13 = ExAllocatePool2(258, 224, 1936082517);
  if ( !v13 )
  {
LABEL_11:
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a5,
      (struct UnionFs::StackEventTracer *)0x233001D0068LL,
      (unsigned __int64)"UnionFs::UfsFsContext::AllocAndInit",
      "ORIGIN: Allocating paged fs ctx",
      v16);
    if ( AePushLock )
      FsRtlFreeAePushLock(AePushLock);
    if ( !v11 )
      return 3221225626LL;
    goto LABEL_7;
  }
  v19 = AePushLock;
  v18 = v11;
  AePushLock = UnionFs::UfsFsContext::UfsFsContext(v13, (unsigned int)&v18, (unsigned int)&v19, a1, a2, a3);
  if ( !AePushLock )
  {
    v11 = 0;
    goto LABEL_11;
  }
  if ( (unsigned int)Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline() )
    FsRtlInitializeOplock((POPLOCK)(AePushLock + 88));
  v14 = *a4;
  *a4 = (FSRTL_ADVANCED_FCB_HEADER *)AePushLock;
  if ( v14 )
  {
    UnionFs::UfsFsContext::~UfsFsContext(v14);
    ExFreePoolWithTag(v14, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x140057c38  push    rbx
0x140057c3a  push    rbp
0x140057c3b  push    rsi
0x140057c3c  push    rdi
0x140057c3d  push    r14
0x140057c3f  push    r15
0x140057c41  sub     rsp, 48h
0x140057c45  mov     rbx, [r9]
0x140057c48  mov     rsi, r9
0x140057c4b  mov     qword ptr [r9], 0
0x140057c52  mov     rbp, r8
0x140057c55  mov     r14, rdx
0x140057c58  mov     r15, rcx
0x140057c5b  test    rbx, rbx
0x140057c5e  jz      short loc_140057C79
0x140057c60  mov     rcx, rbx; AdvancedHeader
0x140057c63  call    ??1UfsFsContext@UnionFs@@QEAA@XZ; UnionFs::UfsFsContext::~UfsFsContext(void)
0x140057c68  xor     edx, edx; Tag
0x140057c6a  mov     rcx, rbx; P
0x140057c6d  call    cs:__imp_ExFreePoolWithTag
0x140057c74  nop     dword ptr [rax+rax+00h]
0x140057c79  mov     edx, 110h
0x140057c7e  mov     ecx, 42h ; 'B'
0x140057c83  mov     r8d, 73664655h
0x140057c89  call    cs:__imp_ExAllocatePool2
0x140057c90  nop     dword ptr [rax+rax+00h]
0x140057c95  test    rax, rax
0x140057c98  jz      loc_140057E13
0x140057c9e  mov     rcx, rax; this
0x140057ca1  call    ??0UfsFsContextNP@UnionFs@@AEAA@XZ; UnionFs::UfsFsContextNP::UfsFsContextNP(void)
0x140057ca6  mov     rbx, rax
0x140057ca9  test    rax, rax
0x140057cac  jz      loc_140057E13
0x140057cb2  mov     edx, 65614655h
0x140057cb7  mov     ecx, 200h
0x140057cbc  call    cs:__imp_FsRtlAllocateAePushLock
0x140057cc3  nop     dword ptr [rax+rax+00h]
0x140057cc8  mov     rdi, rax
0x140057ccb  test    rax, rax
0x140057cce  jnz     short loc_140057D27
0x140057cd0  mov     rdx, qword ptr [rsp+78h+arg_20]; int
0x140057cd8  lea     rax, aOriginAllocati_3; "ORIGIN: Allocating AE pushlock"
0x140057cdf  mov     esi, 0C000009Ah
0x140057ce4  mov     [rsp+78h+var_58], rax; char *
0x140057ce9  mov     ecx, esi; this
0x140057ceb  lea     r9, aUnionfsUfsfsco_1; "UnionFs::UfsFsContext::AllocAndInit"
0x140057cf2  mov     r8, 11D001D005Ah; struct UnionFs::StackEventTracer *
0x140057cfc  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140057d01  lea     rcx, [rbx+38h]; Resource
0x140057d05  call    cs:__imp_ExDeleteResourceLite
0x140057d0c  nop     dword ptr [rax+rax+00h]
0x140057d11  xor     edx, edx; Tag
0x140057d13  mov     rcx, rbx; P
0x140057d16  call    cs:__imp_ExFreePoolWithTag
0x140057d1d  nop     dword ptr [rax+rax+00h]
0x140057d22  jmp     loc_140057E70
0x140057d27  mov     edx, 0E0h
0x140057d2c  mov     r8d, 73664655h
0x140057d32  lea     ecx, [rdx+22h]
0x140057d35  call    cs:__imp_ExAllocatePool2
0x140057d3c  nop     dword ptr [rax+rax+00h]
0x140057d41  test    rax, rax
0x140057d44  jz      short loc_140057D7F
0x140057d46  mov     [rsp+78h+var_50], rbp; char *
0x140057d4b  lea     r8, [rsp+78h+arg_18]
0x140057d53  mov     r9, r15
0x140057d56  mov     [rsp+78h+var_58], r14
0x140057d5b  lea     rdx, [rsp+78h+var_48]
0x140057d60  mov     [rsp+78h+arg_18], rdi
0x140057d68  mov     rcx, rax
0x140057d6b  mov     [rsp+78h+var_48], rbx
0x140057d70  call    ??0UfsFsContext@UnionFs@@AEAA@V?$unique_ptr@VUfsFsContextNP@UnionFs@@U?$default_delete@VUfsFsContextNP@UnionFs@@@utl@@@utl@@V?$unique_ptr@XU?$function_deleter@P6AXPEAX@Z$1?FsRtlFreeAePushLock@@YAX0@Z@wil@@@wistd@@AEAVUfsStreamCtx@1@AEBVUfsFileCtx@1@AEBU_FILE_OBJECT@@@Z; UnionFs::UfsFsContext::UfsFsContext(utl::unique_ptr<UnionFs::UfsFsContextNP,utl::default_delete<UnionFs::UfsFsContextNP>>,wistd::unique_ptr<void,wil::function_deleter<void (*)(void *),&FsRtlFreeAePushLock(void *)>>,UnionFs::UfsStreamCtx &,UnionFs::UfsFileCtx const &,_FILE_OBJECT const &)
0x140057d75  mov     rdi, rax
0x140057d78  test    rax, rax
0x140057d7b  jnz     short loc_140057DD2
0x140057d7d  xor     ebx, ebx
0x140057d7f  mov     rdx, qword ptr [rsp+78h+arg_20]; int
0x140057d87  lea     rax, aOriginAllocati_61; "ORIGIN: Allocating paged fs ctx"
0x140057d8e  mov     esi, 0C000009Ah
0x140057d93  mov     [rsp+78h+var_58], rax; char *
0x140057d98  mov     ecx, esi; this
0x140057d9a  lea     r9, aUnionfsUfsfsco_1; "UnionFs::UfsFsContext::AllocAndInit"
0x140057da1  mov     r8, 233001D0068h; struct UnionFs::StackEventTracer *
0x140057dab  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140057db0  test    rdi, rdi
0x140057db3  jz      short loc_140057DC4
0x140057db5  mov     rcx, rdi
0x140057db8  call    cs:__imp_FsRtlFreeAePushLock
0x140057dbf  nop     dword ptr [rax+rax+00h]
0x140057dc4  test    rbx, rbx
0x140057dc7  jz      loc_140057E70
0x140057dcd  jmp     loc_140057D01
0x140057dd2  call    Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline
0x140057dd7  test    eax, eax
0x140057dd9  jz      short loc_140057DEB
0x140057ddb  lea     rcx, [rdi+58h]; Oplock
0x140057ddf  call    cs:__imp_FsRtlInitializeOplock
0x140057de6  nop     dword ptr [rax+rax+00h]
0x140057deb  mov     rbx, [rsi]
0x140057dee  mov     [rsi], rdi
0x140057df1  test    rbx, rbx
0x140057df4  jz      short loc_140057E0F
0x140057df6  mov     rcx, rbx; AdvancedHeader
0x140057df9  call    ??1UfsFsContext@UnionFs@@QEAA@XZ; UnionFs::UfsFsContext::~UfsFsContext(void)
0x140057dfe  xor     edx, edx; Tag
0x140057e00  mov     rcx, rbx; P
0x140057e03  call    cs:__imp_ExFreePoolWithTag
0x140057e0a  nop     dword ptr [rax+rax+00h]
0x140057e0f  xor     eax, eax
0x140057e11  jmp     short loc_140057E72
0x140057e13  mov     rdx, qword ptr [rsp+78h+arg_20]; int
0x140057e1b  lea     rax, aOriginAllocati_55; "ORIGIN: Allocating non-paged fs ctx"
0x140057e22  mov     esi, 0C000009Ah
0x140057e27  mov     [rsp+78h+var_58], rax; char *
0x140057e2c  mov     ecx, esi; this
0x140057e2e  lea     r9, aUnionfsUfsfsco; "UnionFs::UfsFsContextNP::AllocAndInit"
0x140057e35  mov     r8, 113001D0028h; struct UnionFs::StackEventTracer *
0x140057e3f  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140057e44  mov     rdx, qword ptr [rsp+78h+arg_20]; int
0x140057e4c  lea     rax, aPushCreatingNp; "PUSH: Creating NP ctx"
0x140057e53  lea     r9, aUnionfsUfsfsco_1; "UnionFs::UfsFsContext::AllocAndInit"
0x140057e5a  mov     [rsp+78h+var_58], rax; char *
0x140057e5f  mov     r8, 119001D0052h; struct UnionFs::StackEventTracer *
0x140057e69  mov     ecx, esi; this
0x140057e6b  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140057e70  mov     eax, esi
0x140057e72  add     rsp, 48h
0x140057e76  pop     r15
0x140057e78  pop     r14
0x140057e7a  pop     rdi
0x140057e7b  pop     rsi
0x140057e7c  pop     rbp
0x140057e7d  pop     rbx
0x140057e7e  retn
```
