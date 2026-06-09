# UnionFs::UfsFsContext::AllocAndInit(UnionFs::UfsStreamCtx &,UnionFs::UfsFileCtx const &,_FILE_OBJECT const &,utl::unique_ptr<UnionFs::UfsFsContext,utl::default_delete<UnionFs::UfsFsContext>> &,UnionFs::StackEventTracer &)

- ea: `0x140057db8`
- end: `0x140058000`
- name: `?AllocAndInit@UfsFsContext@UnionFs@@SAJAEAVUfsStreamCtx@2@AEBVUfsFileCtx@2@AEBU_FILE_OBJECT@@AEAV?$unique_ptr@VUfsFsContext@UnionFs@@U?$default_delete@VUfsFsContext@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `584`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x140026e1c`

## callees

- `0x140010168`
- `0x140056c44`
- `0x140056c7c`
- `0x1400576d4`
- `0x140057828`
- `0x140057bbc`
- `0x140057db8`

## import_xrefs

- `ntoskrnl!FsRtlFreeAePushLock` at `0x140057f38`
- `ntoskrnl!FsRtlFreeAePushLock` at `0x140057f38`
- `ntoskrnl!FsRtlInitializeOplock` at `0x140057f5f`
- `ntoskrnl!FsRtlInitializeOplock` at `0x140057f5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057ded`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057e96`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057f83`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057ded`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057e96`
- `ntoskrnl!ExFreePoolWithTag` at `0x140057f83`
- `ntoskrnl!ExAllocatePool2` at `0x140057e09`
- `ntoskrnl!ExAllocatePool2` at `0x140057eb5`
- `ntoskrnl!ExAllocatePool2` at `0x140057e09`
- `ntoskrnl!ExAllocatePool2` at `0x140057eb5`
- `ntoskrnl!ExDeleteResourceLite` at `0x140057e85`
- `ntoskrnl!ExDeleteResourceLite` at `0x140057e85`
- `ntoskrnl!FsRtlAllocateAePushLock` at `0x140057e3c`
- `ntoskrnl!FsRtlAllocateAePushLock` at `0x140057e3c`

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
0x140057db8  push    rbx
0x140057dba  push    rbp
0x140057dbb  push    rsi
0x140057dbc  push    rdi
0x140057dbd  push    r14
0x140057dbf  push    r15
0x140057dc1  sub     rsp, 48h
0x140057dc5  mov     rbx, [r9]
0x140057dc8  mov     rsi, r9
0x140057dcb  mov     qword ptr [r9], 0
0x140057dd2  mov     rbp, r8
0x140057dd5  mov     r14, rdx
0x140057dd8  mov     r15, rcx
0x140057ddb  test    rbx, rbx
0x140057dde  jz      short loc_140057DF9
0x140057de0  mov     rcx, rbx; AdvancedHeader
0x140057de3  call    ??1UfsFsContext@UnionFs@@QEAA@XZ; UnionFs::UfsFsContext::~UfsFsContext(void)
0x140057de8  xor     edx, edx; Tag
0x140057dea  mov     rcx, rbx; P
0x140057ded  call    cs:__imp_ExFreePoolWithTag
0x140057df4  nop     dword ptr [rax+rax+00h]
0x140057df9  mov     edx, 110h
0x140057dfe  mov     ecx, 42h ; 'B'
0x140057e03  mov     r8d, 73664655h
0x140057e09  call    cs:__imp_ExAllocatePool2
0x140057e10  nop     dword ptr [rax+rax+00h]
0x140057e15  test    rax, rax
0x140057e18  jz      loc_140057F93
0x140057e1e  mov     rcx, rax; this
0x140057e21  call    ??0UfsFsContextNP@UnionFs@@AEAA@XZ; UnionFs::UfsFsContextNP::UfsFsContextNP(void)
0x140057e26  mov     rbx, rax
0x140057e29  test    rax, rax
0x140057e2c  jz      loc_140057F93
0x140057e32  mov     edx, 65614655h
0x140057e37  mov     ecx, 200h
0x140057e3c  call    cs:__imp_FsRtlAllocateAePushLock
0x140057e43  nop     dword ptr [rax+rax+00h]
0x140057e48  mov     rdi, rax
0x140057e4b  test    rax, rax
0x140057e4e  jnz     short loc_140057EA7
0x140057e50  mov     rdx, qword ptr [rsp+78h+arg_20]; int
0x140057e58  lea     rax, aOriginAllocati_3; "ORIGIN: Allocating AE pushlock"
0x140057e5f  mov     esi, 0C000009Ah
0x140057e64  mov     [rsp+78h+var_58], rax; char *
0x140057e69  mov     ecx, esi; this
0x140057e6b  lea     r9, aUnionfsUfsfsco_1; "UnionFs::UfsFsContext::AllocAndInit"
0x140057e72  mov     r8, 11D001D005Ah; struct UnionFs::StackEventTracer *
0x140057e7c  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140057e81  lea     rcx, [rbx+38h]; Resource
0x140057e85  call    cs:__imp_ExDeleteResourceLite
0x140057e8c  nop     dword ptr [rax+rax+00h]
0x140057e91  xor     edx, edx; Tag
0x140057e93  mov     rcx, rbx; P
0x140057e96  call    cs:__imp_ExFreePoolWithTag
0x140057e9d  nop     dword ptr [rax+rax+00h]
0x140057ea2  jmp     loc_140057FF0
0x140057ea7  mov     edx, 0E0h
0x140057eac  mov     r8d, 73664655h
0x140057eb2  lea     ecx, [rdx+22h]
0x140057eb5  call    cs:__imp_ExAllocatePool2
0x140057ebc  nop     dword ptr [rax+rax+00h]
0x140057ec1  test    rax, rax
0x140057ec4  jz      short loc_140057EFF
0x140057ec6  mov     [rsp+78h+var_50], rbp; char *
0x140057ecb  lea     r8, [rsp+78h+arg_18]
0x140057ed3  mov     r9, r15
0x140057ed6  mov     [rsp+78h+var_58], r14
0x140057edb  lea     rdx, [rsp+78h+var_48]
0x140057ee0  mov     [rsp+78h+arg_18], rdi
0x140057ee8  mov     rcx, rax
0x140057eeb  mov     [rsp+78h+var_48], rbx
0x140057ef0  call    ??0UfsFsContext@UnionFs@@AEAA@V?$unique_ptr@VUfsFsContextNP@UnionFs@@U?$default_delete@VUfsFsContextNP@UnionFs@@@utl@@@utl@@V?$unique_ptr@XU?$function_deleter@P6AXPEAX@Z$1?FsRtlFreeAePushLock@@YAX0@Z@wil@@@wistd@@AEAVUfsStreamCtx@1@AEBVUfsFileCtx@1@AEBU_FILE_OBJECT@@@Z; UnionFs::UfsFsContext::UfsFsContext(utl::unique_ptr<UnionFs::UfsFsContextNP,utl::default_delete<UnionFs::UfsFsContextNP>>,wistd::unique_ptr<void,wil::function_deleter<void (*)(void *),&FsRtlFreeAePushLock(void *)>>,UnionFs::UfsStreamCtx &,UnionFs::UfsFileCtx const &,_FILE_OBJECT const &)
0x140057ef5  mov     rdi, rax
0x140057ef8  test    rax, rax
0x140057efb  jnz     short loc_140057F52
0x140057efd  xor     ebx, ebx
0x140057eff  mov     rdx, qword ptr [rsp+78h+arg_20]; int
0x140057f07  lea     rax, aOriginAllocati_62; "ORIGIN: Allocating paged fs ctx"
0x140057f0e  mov     esi, 0C000009Ah
0x140057f13  mov     [rsp+78h+var_58], rax; char *
0x140057f18  mov     ecx, esi; this
0x140057f1a  lea     r9, aUnionfsUfsfsco_1; "UnionFs::UfsFsContext::AllocAndInit"
0x140057f21  mov     r8, 233001D0068h; struct UnionFs::StackEventTracer *
0x140057f2b  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140057f30  test    rdi, rdi
0x140057f33  jz      short loc_140057F44
0x140057f35  mov     rcx, rdi
0x140057f38  call    cs:__imp_FsRtlFreeAePushLock
0x140057f3f  nop     dword ptr [rax+rax+00h]
0x140057f44  test    rbx, rbx
0x140057f47  jz      loc_140057FF0
0x140057f4d  jmp     loc_140057E81
0x140057f52  call    Feature_UnionFS_OplockSupport__private_IsEnabledDeviceUsageNoInline
0x140057f57  test    eax, eax
0x140057f59  jz      short loc_140057F6B
0x140057f5b  lea     rcx, [rdi+58h]; Oplock
0x140057f5f  call    cs:__imp_FsRtlInitializeOplock
0x140057f66  nop     dword ptr [rax+rax+00h]
0x140057f6b  mov     rbx, [rsi]
0x140057f6e  mov     [rsi], rdi
0x140057f71  test    rbx, rbx
0x140057f74  jz      short loc_140057F8F
0x140057f76  mov     rcx, rbx; AdvancedHeader
0x140057f79  call    ??1UfsFsContext@UnionFs@@QEAA@XZ; UnionFs::UfsFsContext::~UfsFsContext(void)
0x140057f7e  xor     edx, edx; Tag
0x140057f80  mov     rcx, rbx; P
0x140057f83  call    cs:__imp_ExFreePoolWithTag
0x140057f8a  nop     dword ptr [rax+rax+00h]
0x140057f8f  xor     eax, eax
0x140057f91  jmp     short loc_140057FF2
0x140057f93  mov     rdx, qword ptr [rsp+78h+arg_20]; int
0x140057f9b  lea     rax, aOriginAllocati_56; "ORIGIN: Allocating non-paged fs ctx"
0x140057fa2  mov     esi, 0C000009Ah
0x140057fa7  mov     [rsp+78h+var_58], rax; char *
0x140057fac  mov     ecx, esi; this
0x140057fae  lea     r9, aUnionfsUfsfsco; "UnionFs::UfsFsContextNP::AllocAndInit"
0x140057fb5  mov     r8, 113001D0028h; struct UnionFs::StackEventTracer *
0x140057fbf  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140057fc4  mov     rdx, qword ptr [rsp+78h+arg_20]; int
0x140057fcc  lea     rax, aPushCreatingNp; "PUSH: Creating NP ctx"
0x140057fd3  lea     r9, aUnionfsUfsfsco_1; "UnionFs::UfsFsContext::AllocAndInit"
0x140057fda  mov     [rsp+78h+var_58], rax; char *
0x140057fdf  mov     r8, 119001D0052h; struct UnionFs::StackEventTracer *
0x140057fe9  mov     ecx, esi; this
0x140057feb  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140057ff0  mov     eax, esi
0x140057ff2  add     rsp, 48h
0x140057ff6  pop     r15
0x140057ff8  pop     r14
0x140057ffa  pop     rdi
0x140057ffb  pop     rsi
0x140057ffc  pop     rbp
0x140057ffd  pop     rbx
0x140057ffe  retn
```
