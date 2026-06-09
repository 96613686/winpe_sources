# UnionFs::UfsPathCachePayload::AllocAndInitSharedEmpty(utl::shared_ptr<UnionFs::UfsPathCachePayload> &,UnionFs::StackEventTracer &,bool)

- ea: `0x140040ff4`
- end: `0x1400411c1`
- name: `?AllocAndInitSharedEmpty@UfsPathCachePayload@UnionFs@@SAJAEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@AEAVStackEventTracer@2@_N@Z`
- size: `461`
- prototype: ``
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14002e468`
- `0x1400411c8`
- `0x14005e380`
- `0x140070afc`

## callees

- `0x14000f81c`
- `0x14003f618`
- `0x14003f8d4`
- `0x14003fef8`
- `0x140040020`
- `0x140040ff4`
- `0x140056c44`
- `0x140056c7c`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140041092`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140041158`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14004119f`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140041092`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140041158`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14004119f`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400410bb`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400410bb`

## string_xrefs

- `0x14004105a`: `UnionFs::UfsPathCachePayload::AllocAndInitSharedEmpty`
- `0x140041113`: `UnionFs::UfsPathCachePayload::AllocAndInitSharedEmpty`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathCachePayload::AllocAndInitSharedEmpty(_QWORD *a1, __int64 a2, char a3)
{
  utl::_RefCountBase *v4; // rcx
  int v7; // ebx
  PVOID v8; // rdi
  PVOID v10; // rax
  __int64 v11; // r8
  UnionFs::UfsPathCachePayloadNP *v12; // rbx
  utl::_RefCountBase *v13; // rcx
  const char *v14; // [rsp+28h] [rbp-18h]
  utl::_RefCountBase *v15[2]; // [rsp+30h] [rbp-10h] BYREF
  PVOID Entry; // [rsp+60h] [rbp+20h] BYREF

  *a1 = 0;
  v4 = (utl::_RefCountBase *)a1[1];
  a1[1] = 0;
  if ( v4 )
    utl::_RefCountBase::_DecStrong(v4);
  Entry = 0;
  v7 = UnionFs::UfsPathCachePayloadNP::AllocAndInit(&Entry, a2);
  if ( v7 >= 0 )
  {
    *(_OWORD *)v15 = 0;
    v10 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1664));
    if ( v10 )
    {
      v12 = 0;
      LOBYTE(v11) = a3;
      v10 = (PVOID)UnionFs::UfsPathCachePayload::UfsPathCachePayload(v10, &Entry, v11);
    }
    else
    {
      v12 = (UnionFs::UfsPathCachePayloadNP *)Entry;
    }
    utl::shared_ptr<UnionFs::UfsPathCachePayload>::reset<UnionFs::UfsPathCachePayload,0>(v15, v10);
    if ( v15[0] )
    {
      v13 = (utl::_RefCountBase *)a1[1];
      *a1 = v15[0];
      a1[1] = v15[1];
      if ( v13 )
        utl::_RefCountBase::_DecStrong(v13);
      if ( v12 )
      {
        UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(v12);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1568), v12);
      }
      return 0;
    }
    else
    {
      UnionFs::ProcessTraceStatusOrigin(
        (UnionFs *)0xC000009ALL,
        a2,
        (struct UnionFs::StackEventTracer *)0x1FC00120174LL,
        (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitSharedEmpty",
        "ORIGIN: Allocating tombstone payload",
        v14);
      if ( v15[1] )
        utl::_RefCountBase::_DecStrong(v15[1]);
      if ( v12 )
      {
        UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(v12);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1568), v12);
      }
      return 3221225626LL;
    }
  }
  else
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v7,
      a2,
      (struct UnionFs::StackEventTracer *)0x11B0012016ALL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocAndInitSharedEmpty",
      "PUSH: Creating NP ctx",
      v14);
    v8 = Entry;
    if ( Entry )
    {
      UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP((UnionFs::UfsPathCachePayloadNP *)Entry);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1568), v8);
    }
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x140040ff4  mov     [rsp-18h+arg_8], rbx
0x140040ff9  mov     [rsp-18h+arg_10], rsi
0x140040ffe  push    rbp
0x140040fff  push    rdi
0x140041000  push    r14
0x140041002  mov     rbp, rsp
0x140041005  sub     rsp, 40h
0x140041009  mov     rdi, rcx
0x14004100c  mov     qword ptr [rcx], 0
0x140041013  mov     rcx, [rcx+8]; this
0x140041017  mov     r14b, r8b
0x14004101a  mov     rsi, rdx
0x14004101d  mov     qword ptr [rdi+8], 0
0x140041025  test    rcx, rcx
0x140041028  jz      short loc_14004102F
0x14004102a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004102f  mov     rdx, rsi
0x140041032  mov     [rbp+Entry], 0
0x14004103a  lea     rcx, [rbp+Entry]
0x14004103e  call    ?AllocAndInit@UfsPathCachePayloadNP@UnionFs@@SAJAEAV?$unique_ptr@VUfsPathCachePayloadNP@UnionFs@@U?$default_delete@VUfsPathCachePayloadNP@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathCachePayloadNP::AllocAndInit(utl::unique_ptr<UnionFs::UfsPathCachePayloadNP,utl::default_delete<UnionFs::UfsPathCachePayloadNP>> &,UnionFs::StackEventTracer &)
0x140041043  mov     ebx, eax
0x140041045  test    eax, eax
0x140041047  jns     short loc_1400410A5
0x140041049  lea     rax, aPushCreatingNp; "PUSH: Creating NP ctx"
0x140041050  mov     r8, 11B0012016Ah; struct UnionFs::StackEventTracer *
0x14004105a  lea     r9, aUnionfsUfspath_54; "UnionFs::UfsPathCachePayload::AllocAndI"...
0x140041061  mov     [rsp+40h+var_20], rax; char *
0x140041066  mov     rdx, rsi; int
0x140041069  mov     ecx, ebx; this
0x14004106b  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140041070  mov     rdi, [rbp+Entry]
0x140041074  test    rdi, rdi
0x140041077  jz      short loc_14004109E
0x140041079  mov     rcx, rdi; this
0x14004107c  call    ??1UfsPathCachePayloadNP@UnionFs@@QEAA@XZ; UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(void)
0x140041081  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140041088  mov     rdx, rdi; Entry
0x14004108b  add     rcx, 620h; Lookaside
0x140041092  call    cs:__imp_ExFreeToLookasideListEx
0x140041099  nop     dword ptr [rax+rax+00h]
0x14004109e  mov     eax, ebx
0x1400410a0  jmp     loc_1400411AD
0x1400410a5  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400410ac  xorps   xmm0, xmm0
0x1400410af  add     rcx, 680h; Lookaside
0x1400410b6  movdqu  xmmword ptr [rbp+var_10], xmm0
0x1400410bb  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400410c2  nop     dword ptr [rax+rax+00h]
0x1400410c7  test    rax, rax
0x1400410ca  jz      short loc_1400410E7
0x1400410cc  mov     rcx, [rbp+Entry]
0x1400410d0  lea     rdx, [rbp+Entry]
0x1400410d4  mov     [rbp+Entry], rcx
0x1400410d8  xor     ebx, ebx
0x1400410da  mov     rcx, rax
0x1400410dd  mov     r8b, r14b
0x1400410e0  call    ??0UfsPathCachePayload@UnionFs@@AEAA@V?$unique_ptr@$$CBVUfsPathCachePayloadNP@UnionFs@@U?$default_delete@$$CBVUfsPathCachePayloadNP@UnionFs@@@utl@@@utl@@_N@Z; UnionFs::UfsPathCachePayload::UfsPathCachePayload(utl::unique_ptr<UnionFs::UfsPathCachePayloadNP const,utl::default_delete<UnionFs::UfsPathCachePayloadNP const>>,bool)
0x1400410e5  jmp     short loc_1400410EB
0x1400410e7  mov     rbx, [rbp+Entry]
0x1400410eb  mov     rdx, rax
0x1400410ee  lea     rcx, [rbp+var_10]
0x1400410f2  call    ??$reset@VUfsPathCachePayload@UnionFs@@$0A@@?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@QEAA_NPEAVUfsPathCachePayload@UnionFs@@@Z; utl::shared_ptr<UnionFs::UfsPathCachePayload>::reset<UnionFs::UfsPathCachePayload,0>(UnionFs::UfsPathCachePayload *)
0x1400410f7  mov     rax, [rbp+var_10]
0x1400410fb  test    rax, rax
0x1400410fe  jnz     short loc_140041168
0x140041100  lea     rax, aOriginAllocati_11; "ORIGIN: Allocating tombstone payload"
0x140041107  mov     edi, 0C000009Ah
0x14004110c  mov     ecx, edi; this
0x14004110e  mov     [rsp+40h+var_20], rax; char *
0x140041113  lea     r9, aUnionfsUfspath_54; "UnionFs::UfsPathCachePayload::AllocAndI"...
0x14004111a  mov     r8, 1FC00120174h; struct UnionFs::StackEventTracer *
0x140041124  mov     rdx, rsi; int
0x140041127  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004112c  mov     rcx, [rbp+var_10+8]; this
0x140041130  test    rcx, rcx
0x140041133  jz      short loc_14004113A
0x140041135  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004113a  test    rbx, rbx
0x14004113d  jz      short loc_140041164
0x14004113f  mov     rcx, rbx; this
0x140041142  call    ??1UfsPathCachePayloadNP@UnionFs@@QEAA@XZ; UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(void)
0x140041147  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14004114e  mov     rdx, rbx; Entry
0x140041151  add     rcx, 620h; Lookaside
0x140041158  call    cs:__imp_ExFreeToLookasideListEx
0x14004115f  nop     dword ptr [rax+rax+00h]
0x140041164  mov     eax, edi
0x140041166  jmp     short loc_1400411AD
0x140041168  mov     rcx, [rdi+8]; this
0x14004116c  mov     [rdi], rax
0x14004116f  mov     rax, [rbp+var_10+8]
0x140041173  mov     [rdi+8], rax
0x140041177  test    rcx, rcx
0x14004117a  jz      short loc_140041181
0x14004117c  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140041181  test    rbx, rbx
0x140041184  jz      short loc_1400411AB
0x140041186  mov     rcx, rbx; this
0x140041189  call    ??1UfsPathCachePayloadNP@UnionFs@@QEAA@XZ; UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(void)
0x14004118e  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140041195  mov     rdx, rbx; Entry
0x140041198  add     rcx, 620h; Lookaside
0x14004119f  call    cs:__imp_ExFreeToLookasideListEx
0x1400411a6  nop     dword ptr [rax+rax+00h]
0x1400411ab  xor     eax, eax
0x1400411ad  mov     rbx, [rsp+40h+arg_8]
0x1400411b2  mov     rsi, [rsp+40h+arg_10]
0x1400411b7  add     rsp, 40h
0x1400411bb  pop     r14
0x1400411bd  pop     rdi
0x1400411be  pop     rbp
0x1400411bf  retn
```
