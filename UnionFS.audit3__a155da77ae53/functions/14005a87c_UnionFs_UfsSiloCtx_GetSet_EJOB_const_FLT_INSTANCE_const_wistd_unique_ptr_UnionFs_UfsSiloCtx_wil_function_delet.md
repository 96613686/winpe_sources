# UnionFs::UfsSiloCtx::GetSet(_EJOB const &,_FLT_INSTANCE const &,wistd::unique_ptr<UnionFs::UfsSiloCtx,wil::function_deleter<void (*)(void *),&PsDereferenceSiloContext(void *)>> &,UnionFs::StackEventTracer &)

- ea: `0x14005a87c`
- end: `0x14005ac6f`
- name: `?GetSet@UfsSiloCtx@UnionFs@@SAJAEBU_EJOB@@AEBU_FLT_INSTANCE@@AEAV?$unique_ptr@VUfsSiloCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?PsDereferenceSiloContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z`
- size: `1011`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x14005f664`

## callees

- `0x14000110c`
- `0x1400233dc`
- `0x140027764`
- `0x14003c36c`
- `0x1400558ac`
- `0x140056bd0`
- `0x140056c7c`
- `0x14005a688`
- `0x14005a87c`

## import_xrefs

- `ntoskrnl!PsGetSiloContext` at `0x14005aba6`
- `ntoskrnl!PsGetSiloContext` at `0x14005aba6`
- `ntoskrnl!PsInsertSiloContext` at `0x14005ab00`
- `ntoskrnl!PsInsertSiloContext` at `0x14005ab00`
- `ntoskrnl!PsCreateSiloContext` at `0x14005a9c0`
- `ntoskrnl!PsCreateSiloContext` at `0x14005a9c0`
- `ntoskrnl!PsGetSiloContainerId` at `0x14005aab8`
- `ntoskrnl!PsGetSiloContainerId` at `0x14005aab8`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005a8af`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005a96d`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005aa93`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005aae7`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005abcd`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005ac38`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005a8af`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005a96d`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005aa93`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005aae7`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005abcd`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005ac38`
- `FLTMGR!FltReleaseContext` at `0x14005a906`
- `FLTMGR!FltReleaseContext` at `0x14005a981`
- `FLTMGR!FltReleaseContext` at `0x14005ac4c`
- `FLTMGR!FltReleaseContext` at `0x14005a906`
- `FLTMGR!FltReleaseContext` at `0x14005a981`
- `FLTMGR!FltReleaseContext` at `0x14005ac4c`

## string_xrefs

- `0x14005aa47`: `PUSH: Allocating silo's path cache`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsSiloCtx::GetSet(
        __int64 a1,
        struct _FLT_INSTANCE *a2,
        GUID **a3,
        struct UnionFs::StackEventTracer *a4)
{
  GUID *v5; // rcx
  int v9; // edi
  unsigned int *v11; // rdi
  int inserted; // esi
  const char *v13; // rax
  __int64 v14; // r8
  GUID *v15; // rcx
  GUID *v16; // rbx
  __int64 *v17; // rcx
  int v18; // edx
  const char *v19; // rax
  __int64 v20; // r8
  __int64 SiloContainerId; // rax
  GUID *v22; // rcx
  GUID *v23; // rcx
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  PFLT_CONTEXT v27; // rcx
  const char *v28; // rax
  __int64 v29; // r8
  GUID *v30; // rcx
  char *v31; // [rsp+28h] [rbp-51h]
  int v32; // [rsp+50h] [rbp-29h] BYREF
  GUID *v33; // [rsp+58h] [rbp-21h] BYREF
  const char *v34; // [rsp+60h] [rbp-19h] BYREF
  char v35[8]; // [rsp+68h] [rbp-11h] BYREF
  const char *v36; // [rsp+70h] [rbp-9h] BYREF
  PFLT_CONTEXT *v37; // [rsp+78h] [rbp-1h]
  void *v38; // [rsp+80h] [rbp+7h] BYREF
  char v39; // [rsp+88h] [rbp+Fh]
  PFLT_CONTEXT Context; // [rsp+F0h] [rbp+77h] BYREF

  v5 = *a3;
  *a3 = 0;
  if ( v5 )
    PsDereferenceSiloContext(v5);
  Context = 0;
  v9 = UnionFs::UfsInstanceCtx::FltGet(a2);
  if ( v9 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v9,
      (int)a4,
      (struct UnionFs::StackEventTracer *)0x311001C0095LL,
      (unsigned __int64)"UnionFs::UfsSiloCtx::GetSet",
      "PUSH: Getting instance context",
      v31);
    if ( Context )
      FltReleaseContext(Context);
    return (unsigned int)v9;
  }
  v11 = (unsigned int *)Context;
  v33 = 0;
  inserted = UnionFs::UfsSiloCtx::Get(a1, Context, &v33, a4);
  if ( inserted < 0 )
  {
    v13 = "PUSH: Retrieving silo context";
    v14 = 0x312001C009DLL;
LABEL_9:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)inserted,
      (int)a4,
      (struct UnionFs::StackEventTracer *)v14,
      (unsigned __int64)"UnionFs::UfsSiloCtx::GetSet",
      v13,
      v31);
LABEL_10:
    v15 = v33;
    v33 = 0;
    if ( v15 )
      PsDereferenceSiloContext(v15);
    if ( v11 )
      FltReleaseContext(v11);
    return (unsigned int)inserted;
  }
  if ( !v33 )
  {
    Context = 0;
    inserted = PsCreateSiloContext(a1, 48, 512, UnionFs::UfsSiloCtx::Cleanup, &Context);
    if ( inserted < 0 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)inserted,
        (int)a4,
        (struct UnionFs::StackEventTracer *)0x29C001C0029LL,
        (unsigned __int64)"UnionFs::UfsSiloCtx::AllocAndInit",
        "API: Allocating silo context",
        v31);
LABEL_25:
      v13 = "PUSH: UfsSiloCtx::AllocAndInit";
      v14 = 0x2A2001C00A4LL;
      goto LABEL_9;
    }
    v16 = (GUID *)Context;
    v17 = (__int64 *)((char *)Context + 8);
    *(_QWORD *)Context = a1;
    *v17 = 0;
    *(_QWORD *)&v16[1].Data1 = 0;
    *(_QWORD *)v16[1].Data4 = 0;
    inserted = UnionFs::UfsScratchMappingTable::AllocAndInit(v17, a4);
    v18 = (int)a4;
    if ( inserted < 0 )
    {
      v19 = "PUSH: Allocating silo's scratch mapping table";
      v20 = 0x2A1001C0034LL;
LABEL_24:
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)inserted,
        v18,
        (struct UnionFs::StackEventTracer *)v20,
        (unsigned __int64)"UnionFs::UfsSiloCtx::AllocAndInit",
        v19,
        v31);
      PsDereferenceSiloContext(v16);
      goto LABEL_25;
    }
    inserted = UnionFs::UfsPathCache::AllocAndInit(&v16[1], a4);
    v18 = (int)a4;
    if ( inserted < 0 )
    {
      v19 = "PUSH: Allocating silo's path cache";
      v20 = 0x313001C003ALL;
      goto LABEL_24;
    }
    inserted = UnionFs::UfsEaTable::AllocAndInit((__int64 *)v16[1].Data4, a4);
    if ( inserted < 0 )
    {
      v19 = "PUSH: Allocating silo's EA table";
      v20 = 0x556001C003FLL;
      v18 = (int)a4;
      goto LABEL_24;
    }
    SiloContainerId = PsGetSiloContainerId(*(_QWORD *)&v16->Data1);
    v22 = &GUID_NULL;
    if ( SiloContainerId )
      v22 = (GUID *)SiloContainerId;
    v16[2] = *v22;
    v23 = v33;
    v33 = v16;
    if ( v23 )
    {
      PsDereferenceSiloContext(v23);
      v16 = v33;
    }
    inserted = PsInsertSiloContext(a1, v11[29], v16);
    if ( inserted == -1073741637 )
    {
      if ( (unsigned int)dword_14009E178 > 3 )
      {
        LODWORD(Context) = -1073741637;
        v34 = "onecore\\base\\fs\\unionfs\\sys\\siloctx.cpp";
        v32 = 173;
        v36 = "Raced with another PsInsertSiloContext";
        *(_QWORD *)v35 = "UnionFs::UfsSiloCtx::GetSet";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v24,
          (unsigned int)byte_140098C53,
          v25,
          v26,
          (__int64)&v36,
          (__int64)v35,
          (__int64)&v34,
          (__int64)&v32,
          (__int64)&Context);
      }
      v38 = 0;
      v37 = (PFLT_CONTEXT *)&v33;
      v39 = 1;
      inserted = PsGetSiloContext(a1, v11[29], &v38);
      if ( v39 )
      {
        v27 = *v37;
        *v37 = v38;
        if ( v27 )
          PsDereferenceSiloContext(v27);
      }
      if ( inserted < 0 )
      {
        v28 = "API: Getting pre-existing silo context";
        v29 = 0x2A5001C00B4LL;
LABEL_38:
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)inserted,
          (int)a4,
          (struct UnionFs::StackEventTracer *)v29,
          (unsigned __int64)"UnionFs::UfsSiloCtx::GetSet",
          v28,
          v31);
        goto LABEL_10;
      }
    }
    else if ( inserted < 0 )
    {
      v28 = "API: Inserting new silo context";
      v29 = 0x2A3001C00B8LL;
      goto LABEL_38;
    }
  }
  v30 = *a3;
  *a3 = v33;
  v33 = 0;
  if ( v30 )
    PsDereferenceSiloContext(v30);
  if ( v11 )
    FltReleaseContext(v11);
  return 0;
}

```

## disassembly

```asm
0x14005a87c  push    rbp
0x14005a87e  push    rbx
0x14005a87f  push    rsi
0x14005a880  push    rdi
0x14005a881  push    r12
0x14005a883  push    r13
0x14005a885  push    r14
0x14005a887  push    r15
0x14005a889  lea     rbp, [rsp-1Fh]
0x14005a88e  sub     rsp, 98h
0x14005a895  xor     r13d, r13d
0x14005a898  mov     r15, rcx
0x14005a89b  mov     rcx, [r8]
0x14005a89e  mov     r14, r9
0x14005a8a1  mov     [r8], r13
0x14005a8a4  mov     r12, r8
0x14005a8a7  mov     rbx, rdx
0x14005a8aa  test    rcx, rcx
0x14005a8ad  jz      short loc_14005A8BB
0x14005a8af  call    cs:__imp_PsDereferenceSiloContext
0x14005a8b6  nop     dword ptr [rax+rax+00h]
0x14005a8bb  mov     r9, r14
0x14005a8be  mov     [rbp+57h+Context], r13
0x14005a8c2  lea     r8, [rbp+57h+Context]
0x14005a8c6  xor     edx, edx
0x14005a8c8  mov     rcx, rbx; Instance
0x14005a8cb  call    ?FltGet@UfsInstanceCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@_NAEAV?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsInstanceCtx::FltGet(_FLT_INSTANCE const &,bool,wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x14005a8d0  mov     edi, eax
0x14005a8d2  test    eax, eax
0x14005a8d4  jns     short loc_14005A919
0x14005a8d6  lea     rax, aPushGettingIns_0; "PUSH: Getting instance context"
0x14005a8dd  mov     r8, 311001C0095h; struct UnionFs::StackEventTracer *
0x14005a8e7  lea     r9, aUnionfsUfssilo; "UnionFs::UfsSiloCtx::GetSet"
0x14005a8ee  mov     [rsp+0D0h+var_B0], rax; char *
0x14005a8f3  mov     rdx, r14; int
0x14005a8f6  mov     ecx, edi; this
0x14005a8f8  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005a8fd  mov     rcx, [rbp+57h+Context]; Context
0x14005a901  test    rcx, rcx
0x14005a904  jz      short loc_14005A912
0x14005a906  call    cs:__imp_FltReleaseContext
0x14005a90d  nop     dword ptr [rax+rax+00h]
0x14005a912  mov     eax, edi
0x14005a914  jmp     loc_14005AC5A
0x14005a919  mov     rdi, [rbp+57h+Context]
0x14005a91d  lea     r8, [rbp+57h+var_78]
0x14005a921  mov     rdx, rdi
0x14005a924  mov     [rbp+57h+var_78], r13
0x14005a928  mov     r9, r14
0x14005a92b  mov     rcx, r15
0x14005a92e  call    ?Get@UfsSiloCtx@UnionFs@@SAJAEBU_EJOB@@AEBVUfsInstanceCtx@2@AEAV?$unique_ptr@VUfsSiloCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?PsDereferenceSiloContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsSiloCtx::Get(_EJOB const &,UnionFs::UfsInstanceCtx const &,wistd::unique_ptr<UnionFs::UfsSiloCtx,wil::function_deleter<void (*)(void *),&PsDereferenceSiloContext(void *)>> &,UnionFs::StackEventTracer &)
0x14005a933  mov     esi, eax
0x14005a935  test    eax, eax
0x14005a937  jns     short loc_14005A994
0x14005a939  lea     rax, aPushRetrieving; "PUSH: Retrieving silo context"
0x14005a940  mov     r8, 312001C009Dh; struct UnionFs::StackEventTracer *
0x14005a94a  lea     r9, aUnionfsUfssilo; "UnionFs::UfsSiloCtx::GetSet"
0x14005a951  mov     [rsp+0D0h+var_B0], rax; char *
0x14005a956  mov     rdx, r14; int
0x14005a959  mov     ecx, esi; this
0x14005a95b  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005a960  mov     rcx, [rbp+57h+var_78]
0x14005a964  mov     [rbp+57h+var_78], r13
0x14005a968  test    rcx, rcx
0x14005a96b  jz      short loc_14005A979
0x14005a96d  call    cs:__imp_PsDereferenceSiloContext
0x14005a974  nop     dword ptr [rax+rax+00h]
0x14005a979  test    rdi, rdi
0x14005a97c  jz      short loc_14005A98D
0x14005a97e  mov     rcx, rdi; Context
0x14005a981  call    cs:__imp_FltReleaseContext
0x14005a988  nop     dword ptr [rax+rax+00h]
0x14005a98d  mov     eax, esi
0x14005a98f  jmp     loc_14005AC5A
0x14005a994  cmp     [rbp+57h+var_78], r13
0x14005a998  jnz     loc_14005AC23
0x14005a99e  lea     rax, [rbp+57h+Context]
0x14005a9a2  mov     [rbp+57h+Context], r13
0x14005a9a6  lea     r9, ?Cleanup@UfsSiloCtx@UnionFs@@CAXPEAX@Z; UnionFs::UfsSiloCtx::Cleanup(void *)
0x14005a9ad  mov     [rsp+0D0h+var_B0], rax
0x14005a9b2  mov     edx, 30h ; '0'
0x14005a9b7  mov     r8d, 200h
0x14005a9bd  mov     rcx, r15
0x14005a9c0  call    cs:__imp_PsCreateSiloContext
0x14005a9c7  nop     dword ptr [rax+rax+00h]
0x14005a9cc  mov     esi, eax
0x14005a9ce  mov     rdx, r14; int
0x14005a9d1  test    eax, eax
0x14005a9d3  jns     short loc_14005A9FE
0x14005a9d5  lea     rax, aApiAllocatingS; "API: Allocating silo context"
0x14005a9dc  mov     r8, 29C001C0029h; struct UnionFs::StackEventTracer *
0x14005a9e6  lea     r9, aUnionfsUfssilo_2; "UnionFs::UfsSiloCtx::AllocAndInit"
0x14005a9ed  mov     [rsp+0D0h+var_B0], rax; char *
0x14005a9f2  mov     ecx, esi; this
0x14005a9f4  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005a9f9  jmp     loc_14005AA9F
0x14005a9fe  mov     rbx, [rbp+57h+Context]
0x14005aa02  lea     rcx, [rbx+8]
0x14005aa06  mov     [rbx], r15
0x14005aa09  mov     [rcx], r13
0x14005aa0c  mov     [rbx+10h], r13
0x14005aa10  mov     [rbx+18h], r13
0x14005aa14  call    ?AllocAndInit@UfsScratchMappingTable@UnionFs@@SAJAEAV?$unique_ptr@VUfsScratchMappingTable@UnionFs@@U?$default_delete@VUfsScratchMappingTable@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsScratchMappingTable::AllocAndInit(utl::unique_ptr<UnionFs::UfsScratchMappingTable,utl::default_delete<UnionFs::UfsScratchMappingTable>> &,UnionFs::StackEventTracer &)
0x14005aa19  mov     esi, eax
0x14005aa1b  mov     rdx, r14
0x14005aa1e  test    eax, eax
0x14005aa20  jns     short loc_14005AA35
0x14005aa22  lea     rax, aPushAllocating_31; "PUSH: Allocating silo's scratch mapping"...
0x14005aa29  mov     r8, 2A1001C0034h
0x14005aa33  jmp     short loc_14005AA7D
0x14005aa35  lea     rcx, [rbx+10h]
0x14005aa39  call    ?AllocAndInit@UfsPathCache@UnionFs@@SAJAEAV?$unique_ptr@VUfsPathCache@UnionFs@@U?$default_delete@VUfsPathCache@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathCache::AllocAndInit(utl::unique_ptr<UnionFs::UfsPathCache,utl::default_delete<UnionFs::UfsPathCache>> &,UnionFs::StackEventTracer &)
0x14005aa3e  mov     esi, eax
0x14005aa40  mov     rdx, r14
0x14005aa43  test    eax, eax
0x14005aa45  jns     short loc_14005AA5A
0x14005aa47  lea     rax, aPushAllocating_17; "PUSH: Allocating silo's path cache"
0x14005aa4e  mov     r8, 313001C003Ah
0x14005aa58  jmp     short loc_14005AA7D
0x14005aa5a  lea     rcx, [rbx+18h]
0x14005aa5e  call    ?AllocAndInit@UfsEaTable@UnionFs@@SAJAEAV?$unique_ptr@VUfsEaTable@UnionFs@@U?$default_delete@VUfsEaTable@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsEaTable::AllocAndInit(utl::unique_ptr<UnionFs::UfsEaTable,utl::default_delete<UnionFs::UfsEaTable>> &,UnionFs::StackEventTracer &)
0x14005aa63  mov     esi, eax
0x14005aa65  test    eax, eax
0x14005aa67  jns     short loc_14005AAB5
0x14005aa69  lea     rax, aPushAllocating_27; "PUSH: Allocating silo's EA table"
0x14005aa70  mov     r8, 556001C003Fh; struct UnionFs::StackEventTracer *
0x14005aa7a  mov     rdx, r14; int
0x14005aa7d  lea     r9, aUnionfsUfssilo_2; "UnionFs::UfsSiloCtx::AllocAndInit"
0x14005aa84  mov     [rsp+0D0h+var_B0], rax; char *
0x14005aa89  mov     ecx, esi; this
0x14005aa8b  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005aa90  mov     rcx, rbx
0x14005aa93  call    cs:__imp_PsDereferenceSiloContext
0x14005aa9a  nop     dword ptr [rax+rax+00h]
0x14005aa9f  lea     rax, aPushUfssiloctx; "PUSH: UfsSiloCtx::AllocAndInit"
0x14005aaa6  mov     r8, 2A2001C00A4h
0x14005aab0  jmp     loc_14005A94A
0x14005aab5  mov     rcx, [rbx]
0x14005aab8  call    cs:__imp_PsGetSiloContainerId
0x14005aabf  nop     dword ptr [rax+rax+00h]
0x14005aac4  test    rax, rax
0x14005aac7  lea     rcx, GUID_NULL
0x14005aace  cmovnz  rcx, rax
0x14005aad2  movups  xmm0, xmmword ptr [rcx]
0x14005aad5  movdqu  xmmword ptr [rbx+20h], xmm0
0x14005aada  mov     rcx, [rbp+57h+var_78]
0x14005aade  mov     [rbp+57h+var_78], rbx
0x14005aae2  test    rcx, rcx
0x14005aae5  jz      short loc_14005AAF7
0x14005aae7  call    cs:__imp_PsDereferenceSiloContext
0x14005aaee  nop     dword ptr [rax+rax+00h]
0x14005aaf3  mov     rbx, [rbp+57h+var_78]
0x14005aaf7  mov     edx, [rdi+74h]
0x14005aafa  mov     r8, rbx
0x14005aafd  mov     rcx, r15
0x14005ab00  call    cs:__imp_PsInsertSiloContext
0x14005ab07  nop     dword ptr [rax+rax+00h]
0x14005ab0c  mov     esi, eax
0x14005ab0e  cmp     eax, 0C00000BBh
0x14005ab13  jnz     loc_14005AC05
0x14005ab19  mov     eax, cs:dword_14009E178
0x14005ab1f  lea     rbx, aUnionfsUfssilo; "UnionFs::UfsSiloCtx::GetSet"
0x14005ab26  cmp     eax, 3
0x14005ab29  jbe     short loc_14005AB8C
0x14005ab2b  lea     rax, aOnecoreBaseFsU_8; "onecore\\base\\fs\\unionfs\\sys\\siloct"...
0x14005ab32  mov     dword ptr [rbp+57h+Context], 0C00000BBh
0x14005ab39  mov     [rbp+57h+var_70], rax
0x14005ab3d  lea     rdx, byte_140098C53
0x14005ab44  lea     rax, aRacedWithAnoth; "Raced with another PsInsertSiloContext"
0x14005ab4b  mov     [rbp+57h+var_80], 0ADh
0x14005ab52  mov     [rbp+57h+var_60], rax
0x14005ab56  lea     rax, [rbp+57h+Context]
0x14005ab5a  mov     [rsp+0D0h+var_90], rax
0x14005ab5f  lea     rax, [rbp+57h+var_80]
0x14005ab63  mov     [rsp+0D0h+var_98], rax
0x14005ab68  lea     rax, [rbp+57h+var_70]
0x14005ab6c  mov     [rsp+0D0h+var_A0], rax
0x14005ab71  lea     rax, [rbp+57h+var_68]
0x14005ab75  mov     [rsp+0D0h+var_A8], rax; char *
0x14005ab7a  lea     rax, [rbp+57h+var_60]
0x14005ab7e  mov     [rsp+0D0h+var_B0], rax
0x14005ab83  mov     qword ptr [rbp+57h+var_68], rbx
0x14005ab87  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14005ab8c  lea     rax, [rbp+57h+var_78]
0x14005ab90  mov     [rbp+57h+var_50], r13
0x14005ab94  mov     [rbp+57h+var_58], rax
0x14005ab98  lea     r8, [rbp+57h+var_50]
0x14005ab9c  mov     [rbp+57h+var_48], 1
0x14005aba0  mov     rcx, r15
0x14005aba3  mov     edx, [rdi+74h]
0x14005aba6  call    cs:__imp_PsGetSiloContext
0x14005abad  nop     dword ptr [rax+rax+00h]
0x14005abb2  mov     esi, eax
0x14005abb4  cmp     [rbp+57h+var_48], r13b
0x14005abb8  jz      short loc_14005ABD9
0x14005abba  mov     r8, [rbp+57h+var_58]
0x14005abbe  mov     rdx, [rbp+57h+var_50]
0x14005abc2  mov     rcx, [r8]
0x14005abc5  mov     [r8], rdx
0x14005abc8  test    rcx, rcx
0x14005abcb  jz      short loc_14005ABD9
0x14005abcd  call    cs:__imp_PsDereferenceSiloContext
0x14005abd4  nop     dword ptr [rax+rax+00h]
0x14005abd9  test    esi, esi
0x14005abdb  jns     short loc_14005AC23
0x14005abdd  lea     rax, aApiGettingPreE; "API: Getting pre-existing silo context"
0x14005abe4  mov     r9, rbx; unsigned __int64
0x14005abe7  mov     r8, 2A5001C00B4h; struct UnionFs::StackEventTracer *
0x14005abf1  mov     rdx, r14; int
0x14005abf4  mov     [rsp+0D0h+var_B0], rax; char *
0x14005abf9  mov     ecx, esi; this
0x14005abfb  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005ac00  jmp     loc_14005A960
0x14005ac05  test    esi, esi
0x14005ac07  jns     short loc_14005AC23
0x14005ac09  lea     rax, aApiInsertingNe; "API: Inserting new silo context"
0x14005ac10  mov     r8, 2A3001C00B8h
0x14005ac1a  lea     r9, aUnionfsUfssilo; "UnionFs::UfsSiloCtx::GetSet"
0x14005ac21  jmp     short loc_14005ABF1
0x14005ac23  mov     rcx, [r12]
0x14005ac27  mov     rax, [rbp+57h+var_78]
0x14005ac2b  mov     [r12], rax
0x14005ac2f  mov     [rbp+57h+var_78], r13
0x14005ac33  test    rcx, rcx
0x14005ac36  jz      short loc_14005AC44
0x14005ac38  call    cs:__imp_PsDereferenceSiloContext
0x14005ac3f  nop     dword ptr [rax+rax+00h]
0x14005ac44  test    rdi, rdi
0x14005ac47  jz      short loc_14005AC58
0x14005ac49  mov     rcx, rdi; Context
0x14005ac4c  call    cs:__imp_FltReleaseContext
0x14005ac53  nop     dword ptr [rax+rax+00h]
0x14005ac58  xor     eax, eax
0x14005ac5a  add     rsp, 98h
0x14005ac61  pop     r15
0x14005ac63  pop     r14
0x14005ac65  pop     r13
0x14005ac67  pop     r12
0x14005ac69  pop     rdi
0x14005ac6a  pop     rsi
0x14005ac6b  pop     rbx
0x14005ac6c  pop     rbp
0x14005ac6d  retn
```
