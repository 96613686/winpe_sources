# UnionFs::Utils::RequestOplockCompletionWorkItemRoutine(_FLT_GENERIC_WORKITEM *,void *,void *)

- ea: `0x140076bb0`
- end: `0x140076f9b`
- name: `?RequestOplockCompletionWorkItemRoutine@Utils@UnionFs@@YAXPEAU_FLT_GENERIC_WORKITEM@@PEAX1@Z`
- size: `1003`
- prototype: `void __stdcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400055d0`
- `0x140006168`
- `0x140056bd0`
- `0x140056c44`
- `0x140056c7c`
- `0x140057b24`
- `0x140076860`
- `0x140076bb0`
- `0x140079cc4`
- `0x140079dd4`
- `0x14007baf0`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x140076e48`
- `ntoskrnl!KeClearEvent` at `0x140076e48`
- `ntoskrnl!KeInitializeEvent` at `0x140076db6`
- `ntoskrnl!KeInitializeEvent` at `0x140076db6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140076ce1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140076f38`
- `ntoskrnl!ExFreePoolWithTag` at `0x140076ce1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140076f38`
- `ntoskrnl!KeWaitForSingleObject` at `0x140076e37`
- `ntoskrnl!KeWaitForSingleObject` at `0x140076e37`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140076f67`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140076f67`
- `ntoskrnl!ExReleaseFastMutex` at `0x140076c9f`
- `ntoskrnl!ExReleaseFastMutex` at `0x140076d91`
- `ntoskrnl!ExReleaseFastMutex` at `0x140076c9f`
- `ntoskrnl!ExReleaseFastMutex` at `0x140076d91`
- `ntoskrnl!ExReleaseResourceLite` at `0x140076e09`
- `ntoskrnl!ExReleaseResourceLite` at `0x140076f1b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140076e09`
- `ntoskrnl!ExReleaseResourceLite` at `0x140076f1b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140076e15`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140076f27`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140076e15`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140076f27`

## string_xrefs

- `0x140076c27`: `UnionFs::Utils::RequestOplockCompletionWorkItemRoutine`
- `0x140076d28`: `UnionFs::Utils::RequestOplockCompletionWorkItemRoutine`
- `0x140076ed5`: `UnionFs::Utils::RequestOplockCompletionWorkItemRoutine`
- `0x140076f00`: `UnionFs::Utils::RequestOplockCompletionWorkItemRoutine`

## pseudocode

```c
void __fastcall UnionFs::Utils::RequestOplockCompletionWorkItemRoutine(
        PFLT_GENERIC_WORKITEM FltWorkItem,
        PVOID FltObject,
        PVOID Context)
{
  __int64 v4; // rcx
  int v5; // edx
  __int64 v6; // rsi
  __int64 v7; // rbx
  int v8; // eax
  struct _ERESOURCE *v9; // rdi
  unsigned int v10; // r14d
  struct _FAST_MUTEX *v11; // rcx
  PVOID v12; // rdx
  UnionFs *v13; // rcx
  unsigned int v14; // r14d
  struct _FAST_MUTEX *v15; // rcx
  int v16; // eax
  int v17; // eax
  PVOID v18; // rbx
  char *v19; // [rsp+28h] [rbp-D8h]
  char *v20; // [rsp+28h] [rbp-D8h]
  PFAST_MUTEX FastMutex; // [rsp+40h] [rbp-C0h] BYREF
  PVOID Entry; // [rsp+48h] [rbp-B8h] BYREF
  struct _KEVENT Event; // [rsp+50h] [rbp-B0h] BYREF
  char v24[4]; // [rsp+68h] [rbp-98h] BYREF

  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v24, 0x6F7002126CBuLL);
  Entry = Context;
  v4 = *((_QWORD *)Context + 5);
  v5 = *((_DWORD *)Context + 6);
  v6 = *(_QWORD *)(*(_QWORD *)Context + 24LL);
  v7 = *(_QWORD *)(*(_QWORD *)(v4 + 16) + 48LL);
  if ( !v5 )
    goto LABEL_17;
  if ( v5 != 1 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000000DLL,
      (int)v24,
      (struct UnionFs::StackEventTracer *)0x6FD00212769LL,
      (unsigned __int64)"UnionFs::Utils::RequestOplockCompletionWorkItemRoutine",
      "ORIGIN: Invalid oplock operation in callback",
      v19);
    goto LABEL_19;
  }
  v8 = *(_DWORD *)(v4 + 24);
  if ( v8 == -2147483602 )
  {
    FsFltWil::AcquireResourceShared(&FastMutex, *(_QWORD *)(v6 + 120) + 56LL);
    v9 = (struct _ERESOURCE *)FastMutex;
    v10 = *(_DWORD *)(v7 + 8);
    FsFltWil::AcquireFastMutex(&FastMutex, *(_QWORD *)(v6 + 120) + 216LL);
    v11 = FastMutex;
    if ( v10 <= *(_DWORD *)(v6 + 216) )
      *(_DWORD *)(v6 + 216) = v10;
    if ( v11 )
      ExReleaseFastMutex(v11);
LABEL_32:
    v17 = UnionFs::Utils::RequestOplock(
            *((PFLT_INSTANCE *)Entry + 1),
            *((PFILE_OBJECT *)Entry + 2),
            (__int64)&Entry,
            (int)v24);
    if ( v17 < 0 )
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v17,
        (int)v24,
        (struct UnionFs::StackEventTracer *)0x6D10021277ALL,
        (unsigned __int64)"UnionFs::Utils::RequestOplockCompletionWorkItemRoutine",
        "PUSH: Acknowledging oplock break",
        v20);
LABEL_35:
    if ( v9 )
    {
      ExReleaseResourceLite(v9);
      KeLeaveCriticalRegion();
    }
LABEL_37:
    ExFreePoolWithTag((PVOID)v7, 0);
LABEL_38:
    v18 = Entry;
    if ( Entry )
    {
      UnionFs::Utils::RequestOplockContext::~RequestOplockContext((UnionFs::Utils::RequestOplockContext *)Entry);
      v12 = v18;
      goto LABEL_40;
    }
    goto LABEL_41;
  }
  if ( v8 < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v8,
      (int)v24,
      (struct UnionFs::StackEventTracer *)0x6F80021270BLL,
      (unsigned __int64)"UnionFs::Utils::RequestOplockCompletionWorkItemRoutine",
      "API: Oplock break acknowledgment failed",
      v19);
    goto LABEL_19;
  }
  if ( v8 || *(_QWORD *)(v4 + 32) )
  {
LABEL_17:
    v13 = (UnionFs *)*(unsigned int *)(v4 + 24);
    if ( (int)v13 >= 0 )
    {
      FsFltWil::AcquireResourceShared(&FastMutex, *(_QWORD *)(v6 + 120) + 56LL);
      v9 = (struct _ERESOURCE *)FastMutex;
      v14 = *(_DWORD *)(v7 + 8);
      FsFltWil::AcquireFastMutex(&FastMutex, *(_QWORD *)(v6 + 120) + 216LL);
      v15 = FastMutex;
      if ( v14 <= *(_DWORD *)(v6 + 216) )
        *(_DWORD *)(v6 + 216) = v14;
      if ( v15 )
        ExReleaseFastMutex(v15);
      memset(&Event, 0, sizeof(Event));
      KeInitializeEvent(&Event, NotificationEvent, 0);
      while ( 1 )
      {
        LODWORD(v19) = 0;
        v16 = ((__int64 (__fastcall *)(__int64, _QWORD, struct _KEVENT *, void *, _QWORD))UnionFs::Flt_CheckUpperOplock)(
                v6 + 88,
                *(unsigned int *)(v7 + 8),
                &Event,
                &lambda_d3744a3ec78c830341c2c93f7007b5ba_::_lambda_invoker_cdecl_,
                0);
        if ( v16 < 0 )
        {
          UnionFs::ProcessTraceStatusFromApi(
            (UnionFs *)(unsigned int)v16,
            (int)v24,
            (struct UnionFs::StackEventTracer *)0x6FC0021274DLL,
            (unsigned __int64)"UnionFs::Utils::RequestOplockCompletionWorkItemRoutine",
            "API: Unexpected FltCheckUpperOplock failure",
            v19);
          goto LABEL_35;
        }
        if ( v16 != 259 )
          break;
        if ( v9 )
        {
          ExReleaseResourceLite(v9);
          KeLeaveCriticalRegion();
        }
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        KeClearEvent(&Event);
        FsFltWil::AcquireResourceShared(&FastMutex, *(_QWORD *)(v6 + 120) + 56LL);
        v9 = (struct _ERESOURCE *)FastMutex;
        FastMutex = 0;
      }
      if ( (*(_BYTE *)(v7 + 12) & 1) == 0 )
        goto LABEL_35;
      goto LABEL_32;
    }
    UnionFs::ProcessTraceStatusFromApi(
      v13,
      (int)v24,
      (struct UnionFs::StackEventTracer *)0x6F90021272BLL,
      (unsigned __int64)"UnionFs::Utils::RequestOplockCompletionWorkItemRoutine",
      "API: Oplock request failed",
      v19);
LABEL_19:
    if ( !v7 )
      goto LABEL_38;
    goto LABEL_37;
  }
  if ( v7 )
  {
    ExFreePoolWithTag(*(PVOID *)(*(_QWORD *)(v4 + 16) + 48LL), 0);
    Context = Entry;
  }
  if ( Context )
  {
    UnionFs::Utils::RequestOplockContext::~RequestOplockContext((UnionFs::Utils::RequestOplockContext *)Context);
    v12 = Context;
LABEL_40:
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)UnionFs::g_FilterState + 27, v12);
  }
LABEL_41:
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v24);
}

```

## disassembly

```asm
0x140076bb0  push    rbp
0x140076bb2  push    rbx
0x140076bb3  push    rsi
0x140076bb4  push    rdi
0x140076bb5  push    r14
0x140076bb7  lea     rbp, [rsp-260h]
0x140076bbf  sub     rsp, 360h
0x140076bc6  mov     rax, cs:__security_cookie
0x140076bcd  xor     rax, rsp
0x140076bd0  mov     [rbp+280h+var_28], rax
0x140076bd7  mov     rdx, 6F7002126CBh; unsigned __int64
0x140076be1  lea     rcx, [rsp+380h+var_318]; this
0x140076be6  mov     rdi, r8
0x140076be9  call    ??0StackEventTracer@UnionFs@@QEAA@_K@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64)
0x140076bee  mov     [rsp+380h+Entry], rdi
0x140076bf3  mov     rcx, [rdi+28h]
0x140076bf7  mov     rax, [rdi]
0x140076bfa  mov     edx, [rdi+18h]
0x140076bfd  mov     rbx, [rcx+10h]
0x140076c01  mov     rsi, [rax+18h]
0x140076c05  mov     rbx, [rbx+30h]
0x140076c09  test    edx, edx
0x140076c0b  jz      loc_140076D0B
0x140076c11  cmp     edx, 1
0x140076c14  jz      short loc_140076C47
0x140076c16  lea     rax, aOriginInvalidO; "ORIGIN: Invalid oplock operation in cal"...
0x140076c1d  mov     r8, 6FD00212769h; struct UnionFs::StackEventTracer *
0x140076c27  lea     r9, aUnionfsUtilsRe_0; "UnionFs::Utils::RequestOplockCompletion"...
0x140076c2e  mov     [rsp+380h+Timeout], rax; char *
0x140076c33  lea     rdx, [rsp+380h+var_318]; int
0x140076c38  mov     ecx, 0C000000Dh; this
0x140076c3d  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140076c42  jmp     loc_140076D39
0x140076c47  mov     eax, [rcx+18h]
0x140076c4a  cmp     eax, 8000002Eh
0x140076c4f  jnz     short loc_140076CB0
0x140076c51  mov     rdx, [rsi+78h]
0x140076c55  lea     rcx, [rsp+380h+FastMutex]
0x140076c5a  add     rdx, 38h ; '8'
0x140076c5e  call    ?AcquireResourceShared@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceShared(_ERESOURCE &)
0x140076c63  mov     rdx, [rsi+78h]
0x140076c67  lea     rcx, [rsp+380h+FastMutex]
0x140076c6c  mov     rdi, [rsp+380h+FastMutex]
0x140076c71  add     rdx, 0D8h
0x140076c78  mov     r14d, [rbx+8]
0x140076c7c  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x140076c81  mov     rcx, [rsp+380h+FastMutex]; FastMutex
0x140076c86  cmp     r14d, [rsi+0D8h]
0x140076c8d  ja      short loc_140076C96
0x140076c8f  mov     [rsi+0D8h], r14d
0x140076c96  test    rcx, rcx
0x140076c99  jz      loc_140076E83
0x140076c9f  call    cs:__imp_ExReleaseFastMutex
0x140076ca6  nop     dword ptr [rax+rax+00h]
0x140076cab  jmp     loc_140076E83
0x140076cb0  test    eax, eax
0x140076cb2  jns     short loc_140076CCE
0x140076cb4  lea     rcx, aApiOplockBreak_1; "API: Oplock break acknowledgment failed"
0x140076cbb  mov     r8, 6F80021270Bh
0x140076cc5  mov     [rsp+380h+Timeout], rcx
0x140076cca  mov     ecx, eax
0x140076ccc  jmp     short loc_140076D28
0x140076cce  jnz     short loc_140076D0B
0x140076cd0  cmp     qword ptr [rcx+20h], 0
0x140076cd5  jnz     short loc_140076D0B
0x140076cd7  test    rbx, rbx
0x140076cda  jz      short loc_140076CF2
0x140076cdc  xor     edx, edx; Tag
0x140076cde  mov     rcx, rbx; P
0x140076ce1  call    cs:__imp_ExFreePoolWithTag
0x140076ce8  nop     dword ptr [rax+rax+00h]
0x140076ced  mov     rdi, [rsp+380h+Entry]
0x140076cf2  test    rdi, rdi
0x140076cf5  jz      loc_140076F73
0x140076cfb  mov     rcx, rdi; this
0x140076cfe  call    ??1RequestOplockContext@Utils@UnionFs@@QEAA@XZ; UnionFs::Utils::RequestOplockContext::~RequestOplockContext(void)
0x140076d03  mov     rdx, rdi
0x140076d06  jmp     loc_140076F59
0x140076d0b  mov     ecx, [rcx+18h]; this
0x140076d0e  test    ecx, ecx
0x140076d10  jns     short loc_140076D47
0x140076d12  lea     rax, aApiOplockReque; "API: Oplock request failed"
0x140076d19  mov     r8, 6F90021272Bh; struct UnionFs::StackEventTracer *
0x140076d23  mov     [rsp+380h+Timeout], rax; char *
0x140076d28  lea     r9, aUnionfsUtilsRe_0; "UnionFs::Utils::RequestOplockCompletion"...
0x140076d2f  lea     rdx, [rsp+380h+var_318]; int
0x140076d34  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140076d39  test    rbx, rbx
0x140076d3c  jz      loc_140076F44
0x140076d42  jmp     loc_140076F33
0x140076d47  mov     rdx, [rsi+78h]
0x140076d4b  lea     rcx, [rsp+380h+FastMutex]
0x140076d50  add     rdx, 38h ; '8'
0x140076d54  call    ?AcquireResourceShared@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceShared(_ERESOURCE &)
0x140076d59  mov     rdx, [rsi+78h]
0x140076d5d  lea     rcx, [rsp+380h+FastMutex]
0x140076d62  mov     rdi, [rsp+380h+FastMutex]
0x140076d67  add     rdx, 0D8h
0x140076d6e  mov     r14d, [rbx+8]
0x140076d72  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x140076d77  mov     rcx, [rsp+380h+FastMutex]; FastMutex
0x140076d7c  cmp     r14d, [rsi+0D8h]
0x140076d83  ja      short loc_140076D8C
0x140076d85  mov     [rsi+0D8h], r14d
0x140076d8c  test    rcx, rcx
0x140076d8f  jz      short loc_140076D9D
0x140076d91  call    cs:__imp_ExReleaseFastMutex
0x140076d98  nop     dword ptr [rax+rax+00h]
0x140076d9d  xorps   xmm0, xmm0
0x140076da0  lea     rcx, [rsp+380h+Event]; Event
0x140076da5  xor     eax, eax
0x140076da7  xor     r8d, r8d; State
0x140076daa  xor     edx, edx; Type
0x140076dac  mov     [rsp+380h+Event.Header.WaitListHead.Blink], rax
0x140076db1  movups  xmmword ptr [rsp+380h+Event.Header], xmm0
0x140076db6  call    cs:__imp_KeInitializeEvent
0x140076dbd  nop     dword ptr [rax+rax+00h]
0x140076dc2  mov     rax, cs:?Flt_CheckUpperOplock@UnionFs@@3P6AJPEAPEAXKPEAXP6AXPEAU_FLT_CALLBACK_DATA@@1@Z3K@ZEA; long (*UnionFs::Flt_CheckUpperOplock)(void * *,ulong,void *,void (*)(_FLT_CALLBACK_DATA *,void *),void (*)(_FLT_CALLBACK_DATA *,void *),ulong)
0x140076dc9  lea     r9, _lambda_d3744a3ec78c830341c2c93f7007b5ba____lambda_invoker_cdecl_
0x140076dd0  mov     edx, [rbx+8]
0x140076dd3  lea     r8, [rsp+380h+Event]
0x140076dd8  mov     dword ptr [rsp+380h+var_358], 0; char *
0x140076de0  lea     rcx, [rsi+58h]
0x140076de4  mov     [rsp+380h+Timeout], 0
0x140076ded  call    _guard_dispatch_icall
0x140076df2  test    eax, eax
0x140076df4  js      loc_140076EEA
0x140076dfa  cmp     eax, 103h
0x140076dff  jnz     short loc_140076E79
0x140076e01  test    rdi, rdi
0x140076e04  jz      short loc_140076E21
0x140076e06  mov     rcx, rdi; Resource
0x140076e09  call    cs:__imp_ExReleaseResourceLite
0x140076e10  nop     dword ptr [rax+rax+00h]
0x140076e15  call    cs:__imp_KeLeaveCriticalRegion
0x140076e1c  nop     dword ptr [rax+rax+00h]
0x140076e21  xor     r9d, r9d; Alertable
0x140076e24  mov     [rsp+380h+Timeout], 0; Timeout
0x140076e2d  xor     r8d, r8d; WaitMode
0x140076e30  lea     rcx, [rsp+380h+Event]; Object
0x140076e35  xor     edx, edx; WaitReason
0x140076e37  call    cs:__imp_KeWaitForSingleObject
0x140076e3e  nop     dword ptr [rax+rax+00h]
0x140076e43  lea     rcx, [rsp+380h+Event]; Event
0x140076e48  call    cs:__imp_KeClearEvent
0x140076e4f  nop     dword ptr [rax+rax+00h]
0x140076e54  mov     rdx, [rsi+78h]
0x140076e58  lea     rcx, [rsp+380h+FastMutex]
0x140076e5d  add     rdx, 38h ; '8'
0x140076e61  call    ?AcquireResourceShared@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceShared(_ERESOURCE &)
0x140076e66  mov     rdi, [rsp+380h+FastMutex]
0x140076e6b  mov     [rsp+380h+FastMutex], 0
0x140076e74  jmp     loc_140076DC2
0x140076e79  test    byte ptr [rbx+0Ch], 1
0x140076e7d  jz      loc_140076F13
0x140076e83  mov     rcx, [rsp+380h+Entry]
0x140076e88  lea     rax, [rsp+380h+var_318]
0x140076e8d  mov     r9d, [rbx+8]
0x140076e91  mov     r8d, 1
0x140076e97  mov     [rsp+380h+var_350], 0
0x140076e9f  mov     [rsp+380h+var_358], rax; char *
0x140076ea4  lea     rax, [rsp+380h+Entry]
0x140076ea9  mov     rdx, [rcx+10h]; FileObject
0x140076ead  mov     rcx, [rcx+8]; Instance
0x140076eb1  mov     [rsp+380h+Timeout], rax; __int64
0x140076eb6  call    ?RequestOplock@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@W4RequestOplockOperation@12@K$$QEAV?$unique_ptr@VRequestOplockContext@Utils@UnionFs@@U?$default_delete@VRequestOplockContext@Utils@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@K@Z; UnionFs::Utils::RequestOplock(_FLT_INSTANCE const &,_FILE_OBJECT const &,UnionFs::Utils::RequestOplockOperation,ulong,utl::unique_ptr<UnionFs::Utils::RequestOplockContext,utl::default_delete<UnionFs::Utils::RequestOplockContext>> &&,UnionFs::StackEventTracer &,ulong)
0x140076ebb  test    eax, eax
0x140076ebd  jns     short loc_140076F13
0x140076ebf  lea     rcx, aPushAcknowledg; "PUSH: Acknowledging oplock break"
0x140076ec6  mov     r8, 6D10021277Ah; struct UnionFs::StackEventTracer *
0x140076ed0  mov     [rsp+380h+Timeout], rcx; char *
0x140076ed5  lea     r9, aUnionfsUtilsRe_0; "UnionFs::Utils::RequestOplockCompletion"...
0x140076edc  mov     ecx, eax; this
0x140076ede  lea     rdx, [rsp+380h+var_318]; int
0x140076ee3  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140076ee8  jmp     short loc_140076F13
0x140076eea  lea     rcx, aApiUnexpectedF; "API: Unexpected FltCheckUpperOplock fai"...
0x140076ef1  mov     r8, 6FC0021274Dh; struct UnionFs::StackEventTracer *
0x140076efb  mov     [rsp+380h+Timeout], rcx; char *
0x140076f00  lea     r9, aUnionfsUtilsRe_0; "UnionFs::Utils::RequestOplockCompletion"...
0x140076f07  mov     ecx, eax; this
0x140076f09  lea     rdx, [rsp+380h+var_318]; int
0x140076f0e  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140076f13  test    rdi, rdi
0x140076f16  jz      short loc_140076F33
0x140076f18  mov     rcx, rdi; Resource
0x140076f1b  call    cs:__imp_ExReleaseResourceLite
0x140076f22  nop     dword ptr [rax+rax+00h]
0x140076f27  call    cs:__imp_KeLeaveCriticalRegion
0x140076f2e  nop     dword ptr [rax+rax+00h]
0x140076f33  xor     edx, edx; Tag
0x140076f35  mov     rcx, rbx; P
0x140076f38  call    cs:__imp_ExFreePoolWithTag
0x140076f3f  nop     dword ptr [rax+rax+00h]
0x140076f44  mov     rbx, [rsp+380h+Entry]
0x140076f49  test    rbx, rbx
0x140076f4c  jz      short loc_140076F73
0x140076f4e  mov     rcx, rbx; this
0x140076f51  call    ??1RequestOplockContext@Utils@UnionFs@@QEAA@XZ; UnionFs::Utils::RequestOplockContext::~RequestOplockContext(void)
0x140076f56  mov     rdx, rbx; Entry
0x140076f59  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140076f60  add     rcx, 0A20h; Lookaside
0x140076f67  call    cs:__imp_ExFreeToLookasideListEx
0x140076f6e  nop     dword ptr [rax+rax+00h]
0x140076f73  lea     rcx, [rsp+380h+var_318]; this
0x140076f78  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x140076f7d  mov     rcx, [rbp+280h+var_28]
0x140076f84  xor     rcx, rsp; StackCookie
0x140076f87  call    __security_check_cookie
0x140076f8c  add     rsp, 360h
0x140076f93  pop     r14
0x140076f95  pop     rdi
0x140076f96  pop     rsi
0x140076f97  pop     rbx
0x140076f98  pop     rbp
0x140076f99  retn
```
