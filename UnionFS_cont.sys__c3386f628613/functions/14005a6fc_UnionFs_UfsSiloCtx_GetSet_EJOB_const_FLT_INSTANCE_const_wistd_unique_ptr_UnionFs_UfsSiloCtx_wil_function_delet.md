# UnionFs::UfsSiloCtx::GetSet(_EJOB const &,_FLT_INSTANCE const &,wistd::unique_ptr<UnionFs::UfsSiloCtx,wil::function_deleter<void (*)(void *),&PsDereferenceSiloContext(void *)>> &,UnionFs::StackEventTracer &)

- ea: `0x14005a6fc`
- end: `0x14005aaef`
- name: `?GetSet@UfsSiloCtx@UnionFs@@SAJAEBU_EJOB@@AEBU_FLT_INSTANCE@@AEAV?$unique_ptr@VUfsSiloCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?PsDereferenceSiloContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z`
- size: `1011`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x14005f4e4`

## callees

- `0x14000110c`
- `0x14002333c`
- `0x1400276c4`
- `0x14003c24c`
- `0x14005572c`
- `0x140056a50`
- `0x140056afc`
- `0x14005a508`
- `0x14005a6fc`

## import_xrefs

- `ntoskrnl!PsGetSiloContext` at `0x14005aa26`
- `ntoskrnl!PsGetSiloContext` at `0x14005aa26`
- `ntoskrnl!PsInsertSiloContext` at `0x14005a980`
- `ntoskrnl!PsInsertSiloContext` at `0x14005a980`
- `ntoskrnl!PsCreateSiloContext` at `0x14005a840`
- `ntoskrnl!PsCreateSiloContext` at `0x14005a840`
- `ntoskrnl!PsGetSiloContainerId` at `0x14005a938`
- `ntoskrnl!PsGetSiloContainerId` at `0x14005a938`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005a72f`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005a7ed`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005a913`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005a967`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005aa4d`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005aab8`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005a72f`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005a7ed`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005a913`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005a967`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005aa4d`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005aab8`
- `FLTMGR!FltReleaseContext` at `0x14005a786`
- `FLTMGR!FltReleaseContext` at `0x14005a801`
- `FLTMGR!FltReleaseContext` at `0x14005aacc`
- `FLTMGR!FltReleaseContext` at `0x14005a786`
- `FLTMGR!FltReleaseContext` at `0x14005a801`
- `FLTMGR!FltReleaseContext` at `0x14005aacc`

## string_xrefs

- `0x14005a8c7`: `PUSH: Allocating silo's path cache`

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
          (unsigned int)byte_140098BD3,
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
0x14005a6fc  push    rbp
0x14005a6fe  push    rbx
0x14005a6ff  push    rsi
0x14005a700  push    rdi
0x14005a701  push    r12
0x14005a703  push    r13
0x14005a705  push    r14
0x14005a707  push    r15
0x14005a709  lea     rbp, [rsp-1Fh]
0x14005a70e  sub     rsp, 98h
0x14005a715  xor     r13d, r13d
0x14005a718  mov     r15, rcx
0x14005a71b  mov     rcx, [r8]
0x14005a71e  mov     r14, r9
0x14005a721  mov     [r8], r13
0x14005a724  mov     r12, r8
0x14005a727  mov     rbx, rdx
0x14005a72a  test    rcx, rcx
0x14005a72d  jz      short loc_14005A73B
0x14005a72f  call    cs:__imp_PsDereferenceSiloContext
0x14005a736  nop     dword ptr [rax+rax+00h]
0x14005a73b  mov     r9, r14
0x14005a73e  mov     [rbp+57h+Context], r13
0x14005a742  lea     r8, [rbp+57h+Context]
0x14005a746  xor     edx, edx
0x14005a748  mov     rcx, rbx; Instance
0x14005a74b  call    ?FltGet@UfsInstanceCtx@UnionFs@@SAJAEBU_FLT_INSTANCE@@_NAEAV?$unique_ptr@VUfsInstanceCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?FltReleaseContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsInstanceCtx::FltGet(_FLT_INSTANCE const &,bool,wistd::unique_ptr<UnionFs::UfsInstanceCtx,wil::function_deleter<void (*)(void *),&FltReleaseContext(void *)>> &,UnionFs::StackEventTracer &)
0x14005a750  mov     edi, eax
0x14005a752  test    eax, eax
0x14005a754  jns     short loc_14005A799
0x14005a756  lea     rax, aPushGettingIns_0; "PUSH: Getting instance context"
0x14005a75d  mov     r8, 311001C0095h; struct UnionFs::StackEventTracer *
0x14005a767  lea     r9, aUnionfsUfssilo; "UnionFs::UfsSiloCtx::GetSet"
0x14005a76e  mov     [rsp+0D0h+var_B0], rax; char *
0x14005a773  mov     rdx, r14; int
0x14005a776  mov     ecx, edi; this
0x14005a778  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005a77d  mov     rcx, [rbp+57h+Context]; Context
0x14005a781  test    rcx, rcx
0x14005a784  jz      short loc_14005A792
0x14005a786  call    cs:__imp_FltReleaseContext
0x14005a78d  nop     dword ptr [rax+rax+00h]
0x14005a792  mov     eax, edi
0x14005a794  jmp     loc_14005AADA
0x14005a799  mov     rdi, [rbp+57h+Context]
0x14005a79d  lea     r8, [rbp+57h+var_78]
0x14005a7a1  mov     rdx, rdi
0x14005a7a4  mov     [rbp+57h+var_78], r13
0x14005a7a8  mov     r9, r14
0x14005a7ab  mov     rcx, r15
0x14005a7ae  call    ?Get@UfsSiloCtx@UnionFs@@SAJAEBU_EJOB@@AEBVUfsInstanceCtx@2@AEAV?$unique_ptr@VUfsSiloCtx@UnionFs@@U?$function_deleter@P6AXPEAX@Z$1?PsDereferenceSiloContext@@YAX0@Z@wil@@@wistd@@AEAVStackEventTracer@2@@Z; UnionFs::UfsSiloCtx::Get(_EJOB const &,UnionFs::UfsInstanceCtx const &,wistd::unique_ptr<UnionFs::UfsSiloCtx,wil::function_deleter<void (*)(void *),&PsDereferenceSiloContext(void *)>> &,UnionFs::StackEventTracer &)
0x14005a7b3  mov     esi, eax
0x14005a7b5  test    eax, eax
0x14005a7b7  jns     short loc_14005A814
0x14005a7b9  lea     rax, aPushRetrieving; "PUSH: Retrieving silo context"
0x14005a7c0  mov     r8, 312001C009Dh; struct UnionFs::StackEventTracer *
0x14005a7ca  lea     r9, aUnionfsUfssilo; "UnionFs::UfsSiloCtx::GetSet"
0x14005a7d1  mov     [rsp+0D0h+var_B0], rax; char *
0x14005a7d6  mov     rdx, r14; int
0x14005a7d9  mov     ecx, esi; this
0x14005a7db  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005a7e0  mov     rcx, [rbp+57h+var_78]
0x14005a7e4  mov     [rbp+57h+var_78], r13
0x14005a7e8  test    rcx, rcx
0x14005a7eb  jz      short loc_14005A7F9
0x14005a7ed  call    cs:__imp_PsDereferenceSiloContext
0x14005a7f4  nop     dword ptr [rax+rax+00h]
0x14005a7f9  test    rdi, rdi
0x14005a7fc  jz      short loc_14005A80D
0x14005a7fe  mov     rcx, rdi; Context
0x14005a801  call    cs:__imp_FltReleaseContext
0x14005a808  nop     dword ptr [rax+rax+00h]
0x14005a80d  mov     eax, esi
0x14005a80f  jmp     loc_14005AADA
0x14005a814  cmp     [rbp+57h+var_78], r13
0x14005a818  jnz     loc_14005AAA3
0x14005a81e  lea     rax, [rbp+57h+Context]
0x14005a822  mov     [rbp+57h+Context], r13
0x14005a826  lea     r9, ?Cleanup@UfsSiloCtx@UnionFs@@CAXPEAX@Z; UnionFs::UfsSiloCtx::Cleanup(void *)
0x14005a82d  mov     [rsp+0D0h+var_B0], rax
0x14005a832  mov     edx, 30h ; '0'
0x14005a837  mov     r8d, 200h
0x14005a83d  mov     rcx, r15
0x14005a840  call    cs:__imp_PsCreateSiloContext
0x14005a847  nop     dword ptr [rax+rax+00h]
0x14005a84c  mov     esi, eax
0x14005a84e  mov     rdx, r14; int
0x14005a851  test    eax, eax
0x14005a853  jns     short loc_14005A87E
0x14005a855  lea     rax, aApiAllocatingS; "API: Allocating silo context"
0x14005a85c  mov     r8, 29C001C0029h; struct UnionFs::StackEventTracer *
0x14005a866  lea     r9, aUnionfsUfssilo_2; "UnionFs::UfsSiloCtx::AllocAndInit"
0x14005a86d  mov     [rsp+0D0h+var_B0], rax; char *
0x14005a872  mov     ecx, esi; this
0x14005a874  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005a879  jmp     loc_14005A91F
0x14005a87e  mov     rbx, [rbp+57h+Context]
0x14005a882  lea     rcx, [rbx+8]
0x14005a886  mov     [rbx], r15
0x14005a889  mov     [rcx], r13
0x14005a88c  mov     [rbx+10h], r13
0x14005a890  mov     [rbx+18h], r13
0x14005a894  call    ?AllocAndInit@UfsScratchMappingTable@UnionFs@@SAJAEAV?$unique_ptr@VUfsScratchMappingTable@UnionFs@@U?$default_delete@VUfsScratchMappingTable@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsScratchMappingTable::AllocAndInit(utl::unique_ptr<UnionFs::UfsScratchMappingTable,utl::default_delete<UnionFs::UfsScratchMappingTable>> &,UnionFs::StackEventTracer &)
0x14005a899  mov     esi, eax
0x14005a89b  mov     rdx, r14
0x14005a89e  test    eax, eax
0x14005a8a0  jns     short loc_14005A8B5
0x14005a8a2  lea     rax, aPushAllocating_31; "PUSH: Allocating silo's scratch mapping"...
0x14005a8a9  mov     r8, 2A1001C0034h
0x14005a8b3  jmp     short loc_14005A8FD
0x14005a8b5  lea     rcx, [rbx+10h]
0x14005a8b9  call    ?AllocAndInit@UfsPathCache@UnionFs@@SAJAEAV?$unique_ptr@VUfsPathCache@UnionFs@@U?$default_delete@VUfsPathCache@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathCache::AllocAndInit(utl::unique_ptr<UnionFs::UfsPathCache,utl::default_delete<UnionFs::UfsPathCache>> &,UnionFs::StackEventTracer &)
0x14005a8be  mov     esi, eax
0x14005a8c0  mov     rdx, r14
0x14005a8c3  test    eax, eax
0x14005a8c5  jns     short loc_14005A8DA
0x14005a8c7  lea     rax, aPushAllocating_17; "PUSH: Allocating silo's path cache"
0x14005a8ce  mov     r8, 313001C003Ah
0x14005a8d8  jmp     short loc_14005A8FD
0x14005a8da  lea     rcx, [rbx+18h]
0x14005a8de  call    ?AllocAndInit@UfsEaTable@UnionFs@@SAJAEAV?$unique_ptr@VUfsEaTable@UnionFs@@U?$default_delete@VUfsEaTable@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsEaTable::AllocAndInit(utl::unique_ptr<UnionFs::UfsEaTable,utl::default_delete<UnionFs::UfsEaTable>> &,UnionFs::StackEventTracer &)
0x14005a8e3  mov     esi, eax
0x14005a8e5  test    eax, eax
0x14005a8e7  jns     short loc_14005A935
0x14005a8e9  lea     rax, aPushAllocating_27; "PUSH: Allocating silo's EA table"
0x14005a8f0  mov     r8, 556001C003Fh; struct UnionFs::StackEventTracer *
0x14005a8fa  mov     rdx, r14; int
0x14005a8fd  lea     r9, aUnionfsUfssilo_2; "UnionFs::UfsSiloCtx::AllocAndInit"
0x14005a904  mov     [rsp+0D0h+var_B0], rax; char *
0x14005a909  mov     ecx, esi; this
0x14005a90b  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005a910  mov     rcx, rbx
0x14005a913  call    cs:__imp_PsDereferenceSiloContext
0x14005a91a  nop     dword ptr [rax+rax+00h]
0x14005a91f  lea     rax, aPushUfssiloctx; "PUSH: UfsSiloCtx::AllocAndInit"
0x14005a926  mov     r8, 2A2001C00A4h
0x14005a930  jmp     loc_14005A7CA
0x14005a935  mov     rcx, [rbx]
0x14005a938  call    cs:__imp_PsGetSiloContainerId
0x14005a93f  nop     dword ptr [rax+rax+00h]
0x14005a944  test    rax, rax
0x14005a947  lea     rcx, GUID_NULL
0x14005a94e  cmovnz  rcx, rax
0x14005a952  movups  xmm0, xmmword ptr [rcx]
0x14005a955  movdqu  xmmword ptr [rbx+20h], xmm0
0x14005a95a  mov     rcx, [rbp+57h+var_78]
0x14005a95e  mov     [rbp+57h+var_78], rbx
0x14005a962  test    rcx, rcx
0x14005a965  jz      short loc_14005A977
0x14005a967  call    cs:__imp_PsDereferenceSiloContext
0x14005a96e  nop     dword ptr [rax+rax+00h]
0x14005a973  mov     rbx, [rbp+57h+var_78]
0x14005a977  mov     edx, [rdi+74h]
0x14005a97a  mov     r8, rbx
0x14005a97d  mov     rcx, r15
0x14005a980  call    cs:__imp_PsInsertSiloContext
0x14005a987  nop     dword ptr [rax+rax+00h]
0x14005a98c  mov     esi, eax
0x14005a98e  cmp     eax, 0C00000BBh
0x14005a993  jnz     loc_14005AA85
0x14005a999  mov     eax, cs:dword_14009E178
0x14005a99f  lea     rbx, aUnionfsUfssilo; "UnionFs::UfsSiloCtx::GetSet"
0x14005a9a6  cmp     eax, 3
0x14005a9a9  jbe     short loc_14005AA0C
0x14005a9ab  lea     rax, aOnecoreBaseFsU_8; "onecore\\base\\fs\\unionfs\\sys\\siloct"...
0x14005a9b2  mov     dword ptr [rbp+57h+Context], 0C00000BBh
0x14005a9b9  mov     [rbp+57h+var_70], rax
0x14005a9bd  lea     rdx, byte_140098BD3
0x14005a9c4  lea     rax, aRacedWithAnoth; "Raced with another PsInsertSiloContext"
0x14005a9cb  mov     [rbp+57h+var_80], 0ADh
0x14005a9d2  mov     [rbp+57h+var_60], rax
0x14005a9d6  lea     rax, [rbp+57h+Context]
0x14005a9da  mov     [rsp+0D0h+var_90], rax
0x14005a9df  lea     rax, [rbp+57h+var_80]
0x14005a9e3  mov     [rsp+0D0h+var_98], rax
0x14005a9e8  lea     rax, [rbp+57h+var_70]
0x14005a9ec  mov     [rsp+0D0h+var_A0], rax
0x14005a9f1  lea     rax, [rbp+57h+var_68]
0x14005a9f5  mov     [rsp+0D0h+var_A8], rax; char *
0x14005a9fa  lea     rax, [rbp+57h+var_60]
0x14005a9fe  mov     [rsp+0D0h+var_B0], rax
0x14005aa03  mov     qword ptr [rbp+57h+var_68], rbx
0x14005aa07  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14005aa0c  lea     rax, [rbp+57h+var_78]
0x14005aa10  mov     [rbp+57h+var_50], r13
0x14005aa14  mov     [rbp+57h+var_58], rax
0x14005aa18  lea     r8, [rbp+57h+var_50]
0x14005aa1c  mov     [rbp+57h+var_48], 1
0x14005aa20  mov     rcx, r15
0x14005aa23  mov     edx, [rdi+74h]
0x14005aa26  call    cs:__imp_PsGetSiloContext
0x14005aa2d  nop     dword ptr [rax+rax+00h]
0x14005aa32  mov     esi, eax
0x14005aa34  cmp     [rbp+57h+var_48], r13b
0x14005aa38  jz      short loc_14005AA59
0x14005aa3a  mov     r8, [rbp+57h+var_58]
0x14005aa3e  mov     rdx, [rbp+57h+var_50]
0x14005aa42  mov     rcx, [r8]
0x14005aa45  mov     [r8], rdx
0x14005aa48  test    rcx, rcx
0x14005aa4b  jz      short loc_14005AA59
0x14005aa4d  call    cs:__imp_PsDereferenceSiloContext
0x14005aa54  nop     dword ptr [rax+rax+00h]
0x14005aa59  test    esi, esi
0x14005aa5b  jns     short loc_14005AAA3
0x14005aa5d  lea     rax, aApiGettingPreE; "API: Getting pre-existing silo context"
0x14005aa64  mov     r9, rbx; unsigned __int64
0x14005aa67  mov     r8, 2A5001C00B4h; struct UnionFs::StackEventTracer *
0x14005aa71  mov     rdx, r14; int
0x14005aa74  mov     [rsp+0D0h+var_B0], rax; char *
0x14005aa79  mov     ecx, esi; this
0x14005aa7b  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005aa80  jmp     loc_14005A7E0
0x14005aa85  test    esi, esi
0x14005aa87  jns     short loc_14005AAA3
0x14005aa89  lea     rax, aApiInsertingNe; "API: Inserting new silo context"
0x14005aa90  mov     r8, 2A3001C00B8h
0x14005aa9a  lea     r9, aUnionfsUfssilo; "UnionFs::UfsSiloCtx::GetSet"
0x14005aaa1  jmp     short loc_14005AA71
0x14005aaa3  mov     rcx, [r12]
0x14005aaa7  mov     rax, [rbp+57h+var_78]
0x14005aaab  mov     [r12], rax
0x14005aaaf  mov     [rbp+57h+var_78], r13
0x14005aab3  test    rcx, rcx
0x14005aab6  jz      short loc_14005AAC4
0x14005aab8  call    cs:__imp_PsDereferenceSiloContext
0x14005aabf  nop     dword ptr [rax+rax+00h]
0x14005aac4  test    rdi, rdi
0x14005aac7  jz      short loc_14005AAD8
0x14005aac9  mov     rcx, rdi; Context
0x14005aacc  call    cs:__imp_FltReleaseContext
0x14005aad3  nop     dword ptr [rax+rax+00h]
0x14005aad8  xor     eax, eax
0x14005aada  add     rsp, 98h
0x14005aae1  pop     r15
0x14005aae3  pop     r14
0x14005aae5  pop     r13
0x14005aae7  pop     r12
0x14005aae9  pop     rdi
0x14005aaea  pop     rsi
0x14005aaeb  pop     rbx
0x14005aaec  pop     rbp
0x14005aaed  retn
```
