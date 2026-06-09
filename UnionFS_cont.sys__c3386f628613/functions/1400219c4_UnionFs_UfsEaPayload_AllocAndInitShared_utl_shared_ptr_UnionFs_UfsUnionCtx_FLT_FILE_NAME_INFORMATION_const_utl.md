# UnionFs::UfsEaPayload::AllocAndInitShared(utl::shared_ptr<UnionFs::UfsUnionCtx>,_FLT_FILE_NAME_INFORMATION const &,utl::shared_ptr<UnionFs::UfsEaPayload> &,UnionFs::StackEventTracer &,bool)

- ea: `0x1400219c4`
- end: `0x140021c0c`
- name: `?AllocAndInitShared@UfsEaPayload@UnionFs@@SAJV?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@AEBU_FLT_FILE_NAME_INFORMATION@@AEAV?$shared_ptr@VUfsEaPayload@UnionFs@@@4@AEAVStackEventTracer@2@_N@Z`
- size: `584`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x14001d530`

## callees

- `0x14000f7fc`
- `0x14001f37c`
- `0x140021470`
- `0x140021550`
- `0x1400219c4`
- `0x14004397c`
- `0x140056ac4`
- `0x140056afc`
- `0x140079c48`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140021b6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021bc9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021b6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021bc9`
- `ntoskrnl!ExAllocatePool2` at `0x140021a15`
- `ntoskrnl!ExAllocatePool2` at `0x140021a15`

## string_xrefs

- `0x140021b7b`: `PUSH: Adding scratch path to EA payload`
- `0x140021af1`: `UnionFs::UfsEaPayload::AddScratchPath`
- `0x140021b34`: `UnionFs::UfsEaPayload::AddScratchPath`
- `0x140021b21`: `ORIGIN: Adding scratch path to EA payload`
- `0x140021ae0`: `PUSH: Allocating path name`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsEaPayload::AllocAndInitShared(
        __int64 *a1,
        __int64 a2,
        utl::_RefCountBase **a3,
        __int64 a4)
{
  utl::_RefCountBase *v5; // rcx
  UnionFs::UfsEaPayload *Pool2; // rax
  utl::_RefCountBase *v10; // rdi
  unsigned int v11; // ebx
  utl::_RefCountBase *v12; // rcx
  __int64 v14; // rax
  __int64 v15; // rcx
  utl::_RefCountBase *v16; // rcx
  struct _UNICODE_STRING *v17; // rdx
  struct _UNICODE_STRING *v18; // rdx
  struct _UNICODE_STRING *v19; // rdi
  struct _UNICODE_STRING *v20; // rbx
  utl::_RefCountBase *v21; // rcx
  utl::_RefCountBase *v22; // rax
  utl::_RefCountBase *v23; // rcx
  const char *v24; // [rsp+28h] [rbp-20h]
  const char *v25; // [rsp+28h] [rbp-20h]
  utl::_RefCountBase *v26[2]; // [rsp+30h] [rbp-18h] BYREF
  PVOID P; // [rsp+90h] [rbp+48h] BYREF

  *a3 = 0;
  v5 = a3[1];
  a3[1] = 0;
  if ( v5 )
    utl::_RefCountBase::_DecStrong(v5);
  *(_OWORD *)v26 = 0;
  Pool2 = (UnionFs::UfsEaPayload *)ExAllocatePool2(64, 224, 1952794197);
  if ( Pool2 )
    Pool2 = (UnionFs::UfsEaPayload *)UnionFs::UfsEaPayload::UfsEaPayload(Pool2, 0);
  utl::shared_ptr<UnionFs::UfsEaPayload>::reset<UnionFs::UfsEaPayload,0>(v26, Pool2);
  v10 = v26[0];
  if ( !v26[0] )
  {
    v11 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a4,
      (struct UnionFs::StackEventTracer *)0x20D00070227LL,
      (unsigned __int64)"UnionFs::UfsEaPayload::AllocAndInitShared",
      "ORIGIN: Allocating ea table payload node",
      v24);
LABEL_7:
    if ( v26[1] )
      utl::_RefCountBase::_DecStrong(v26[1]);
    v12 = (utl::_RefCountBase *)a1[1];
    if ( v12 )
      utl::_RefCountBase::_DecStrong(v12);
    return v11;
  }
  v14 = a1[1];
  v15 = *a1;
  if ( v14 )
    _InterlockedIncrement((volatile signed __int32 *)(v14 + 8));
  *((_QWORD *)v10 + 25) = v15;
  v16 = (utl::_RefCountBase *)*((_QWORD *)v10 + 26);
  *((_QWORD *)v10 + 26) = v14;
  if ( v16 )
    utl::_RefCountBase::_DecStrong(v16);
  P = 0;
  v11 = UnionFs::UfsPathName::AllocAndInit(a2, &P, a4);
  if ( (v11 & 0x80000000) != 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)v11,
      a4,
      (struct UnionFs::StackEventTracer *)0x2C3000701DFLL,
      (unsigned __int64)"UnionFs::UfsEaPayload::AddScratchPath",
      "PUSH: Allocating path name",
      v24);
LABEL_20:
    v19 = (struct _UNICODE_STRING *)P;
    if ( P )
    {
      if ( !*((_BYTE *)P + 16) )
        *(_OWORD *)P = 0;
      FsFltWil::Details::FreeUnicodeString(v19, v17);
      ExFreePoolWithTag(v19, 0);
    }
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)v11,
      a4,
      (struct UnionFs::StackEventTracer *)0x3A70007022ELL,
      (unsigned __int64)"UnionFs::UfsEaPayload::AllocAndInitShared",
      "PUSH: Adding scratch path to EA payload",
      v25);
    goto LABEL_7;
  }
  if ( !(unsigned __int8)utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>::push_back(
                           (char *)v10 + 176,
                           &P) )
  {
    v11 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a4,
      (struct UnionFs::StackEventTracer *)0x357000701E5LL,
      (unsigned __int64)"UnionFs::UfsEaPayload::AddScratchPath",
      "ORIGIN: Adding scratch path to EA payload",
      v24);
    goto LABEL_20;
  }
  v20 = (struct _UNICODE_STRING *)P;
  if ( P )
  {
    if ( !*((_BYTE *)P + 16) )
      *(_OWORD *)P = 0;
    FsFltWil::Details::FreeUnicodeString(v20, v18);
    ExFreePoolWithTag(v20, 0);
  }
  v21 = a3[1];
  v22 = v26[1];
  *a3 = v10;
  a3[1] = v22;
  if ( v21 )
    utl::_RefCountBase::_DecStrong(v21);
  v23 = (utl::_RefCountBase *)a1[1];
  if ( v23 )
    utl::_RefCountBase::_DecStrong(v23);
  return 0;
}

```

## disassembly

```asm
0x1400219c4  push    rbp
0x1400219c6  push    rbx
0x1400219c7  push    rsi
0x1400219c8  push    rdi
0x1400219c9  push    r14
0x1400219cb  push    r15
0x1400219cd  mov     rbp, rsp
0x1400219d0  sub     rsp, 48h
0x1400219d4  mov     r14, rcx
0x1400219d7  mov     qword ptr [r8], 0
0x1400219de  mov     rcx, [r8+8]; this
0x1400219e2  mov     r15, r9
0x1400219e5  mov     qword ptr [r8+8], 0
0x1400219ed  mov     rsi, r8
0x1400219f0  mov     rbx, rdx
0x1400219f3  test    rcx, rcx
0x1400219f6  jz      short loc_1400219FD
0x1400219f8  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400219fd  xorps   xmm0, xmm0
0x140021a00  mov     edx, 0E0h
0x140021a05  mov     ecx, 40h ; '@'
0x140021a0a  mov     r8d, 74654655h
0x140021a10  movdqu  xmmword ptr [rbp+var_18], xmm0
0x140021a15  call    cs:__imp_ExAllocatePool2
0x140021a1c  nop     dword ptr [rax+rax+00h]
0x140021a21  test    rax, rax
0x140021a24  jz      short loc_140021A30
0x140021a26  xor     edx, edx; bool
0x140021a28  mov     rcx, rax; this
0x140021a2b  call    ??0UfsEaPayload@UnionFs@@AEAA@_N@Z; UnionFs::UfsEaPayload::UfsEaPayload(bool)
0x140021a30  mov     rdx, rax
0x140021a33  lea     rcx, [rbp+var_18]
0x140021a37  call    ??$reset@VUfsEaPayload@UnionFs@@$0A@@?$shared_ptr@VUfsEaPayload@UnionFs@@@utl@@QEAA_NPEAVUfsEaPayload@UnionFs@@@Z; utl::shared_ptr<UnionFs::UfsEaPayload>::reset<UnionFs::UfsEaPayload,0>(UnionFs::UfsEaPayload *)
0x140021a3c  mov     rdi, [rbp+var_18]
0x140021a40  test    rdi, rdi
0x140021a43  jnz     short loc_140021A94
0x140021a45  lea     rax, aOriginAllocati_14; "ORIGIN: Allocating ea table payload nod"...
0x140021a4c  mov     ebx, 0C000009Ah
0x140021a51  mov     ecx, ebx; this
0x140021a53  mov     [rsp+48h+var_28], rax; char *
0x140021a58  lea     r9, aUnionfsUfseapa_2; "UnionFs::UfsEaPayload::AllocAndInitShar"...
0x140021a5f  mov     r8, 20D00070227h; struct UnionFs::StackEventTracer *
0x140021a69  mov     rdx, r15; int
0x140021a6c  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140021a71  mov     rcx, [rbp+var_18+8]; this
0x140021a75  test    rcx, rcx
0x140021a78  jz      short loc_140021A7F
0x140021a7a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140021a7f  mov     rcx, [r14+8]; this
0x140021a83  test    rcx, rcx
0x140021a86  jz      short loc_140021A8D
0x140021a88  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140021a8d  mov     eax, ebx
0x140021a8f  jmp     loc_140021BFE
0x140021a94  mov     rax, [r14+8]
0x140021a98  mov     rcx, [r14]
0x140021a9b  test    rax, rax
0x140021a9e  jz      short loc_140021AA4
0x140021aa0  lock inc dword ptr [rax+8]
0x140021aa4  mov     [rdi+0C8h], rcx
0x140021aab  mov     rcx, [rdi+0D0h]; this
0x140021ab2  mov     [rdi+0D0h], rax
0x140021ab9  test    rcx, rcx
0x140021abc  jz      short loc_140021AC3
0x140021abe  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140021ac3  mov     r8, r15
0x140021ac6  mov     [rbp+P], 0
0x140021ace  lea     rdx, [rbp+P]
0x140021ad2  mov     rcx, rbx
0x140021ad5  call    ?AllocAndInit@UfsPathName@UnionFs@@SAJAEBU_FLT_FILE_NAME_INFORMATION@@AEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInit(_FLT_FILE_NAME_INFORMATION const &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140021ada  mov     ebx, eax
0x140021adc  test    eax, eax
0x140021ade  jns     short loc_140021B09
0x140021ae0  lea     rax, aPushAllocating_19; "PUSH: Allocating path name"
0x140021ae7  mov     r8, 2C3000701DFh; struct UnionFs::StackEventTracer *
0x140021af1  lea     r9, aUnionfsUfseapa_1; "UnionFs::UfsEaPayload::AddScratchPath"
0x140021af8  mov     [rsp+48h+var_28], rax; char *
0x140021afd  mov     rdx, r15; int
0x140021b00  mov     ecx, ebx; this
0x140021b02  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140021b07  jmp     short loc_140021B4D
0x140021b09  lea     rcx, [rdi+0B0h]
0x140021b10  lea     rdx, [rbp+P]
0x140021b14  call    ?push_back@?$vector@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@2@@utl@@QEAA_N$$QEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@2@@Z; utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>::push_back(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &&)
0x140021b19  test    al, al
0x140021b1b  jnz     loc_140021BA7
0x140021b21  lea     rax, aOriginAddingSc; "ORIGIN: Adding scratch path to EA paylo"...
0x140021b28  mov     ebx, 0C000009Ah
0x140021b2d  mov     ecx, ebx; this
0x140021b2f  mov     [rsp+48h+var_28], rax; char *
0x140021b34  lea     r9, aUnionfsUfseapa_1; "UnionFs::UfsEaPayload::AddScratchPath"
0x140021b3b  mov     r8, 357000701E5h; struct UnionFs::StackEventTracer *
0x140021b45  mov     rdx, r15; int
0x140021b48  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140021b4d  mov     rdi, [rbp+P]
0x140021b51  test    rdi, rdi
0x140021b54  jz      short loc_140021B7B
0x140021b56  cmp     byte ptr [rdi+10h], 0
0x140021b5a  jnz     short loc_140021B62
0x140021b5c  xorps   xmm0, xmm0
0x140021b5f  movups  xmmword ptr [rdi], xmm0
0x140021b62  mov     rcx, rdi; UnicodeString
0x140021b65  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140021b6a  xor     edx, edx; Tag
0x140021b6c  mov     rcx, rdi; P
0x140021b6f  call    cs:__imp_ExFreePoolWithTag
0x140021b76  nop     dword ptr [rax+rax+00h]
0x140021b7b  lea     rax, aPushAddingScra; "PUSH: Adding scratch path to EA payload"
0x140021b82  mov     r8, 3A70007022Eh; struct UnionFs::StackEventTracer *
0x140021b8c  lea     r9, aUnionfsUfseapa_2; "UnionFs::UfsEaPayload::AllocAndInitShar"...
0x140021b93  mov     [rsp+48h+var_28], rax; char *
0x140021b98  mov     rdx, r15; int
0x140021b9b  mov     ecx, ebx; this
0x140021b9d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140021ba2  jmp     loc_140021A71
0x140021ba7  mov     rbx, [rbp+P]
0x140021bab  test    rbx, rbx
0x140021bae  jz      short loc_140021BD5
0x140021bb0  cmp     byte ptr [rbx+10h], 0
0x140021bb4  jnz     short loc_140021BBC
0x140021bb6  xorps   xmm0, xmm0
0x140021bb9  movups  xmmword ptr [rbx], xmm0
0x140021bbc  mov     rcx, rbx; UnicodeString
0x140021bbf  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140021bc4  xor     edx, edx; Tag
0x140021bc6  mov     rcx, rbx; P
0x140021bc9  call    cs:__imp_ExFreePoolWithTag
0x140021bd0  nop     dword ptr [rax+rax+00h]
0x140021bd5  mov     rcx, [rsi+8]; this
0x140021bd9  mov     rax, [rbp+var_18+8]
0x140021bdd  mov     [rsi], rdi
0x140021be0  mov     [rsi+8], rax
0x140021be4  test    rcx, rcx
0x140021be7  jz      short loc_140021BEE
0x140021be9  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140021bee  mov     rcx, [r14+8]; this
0x140021bf2  test    rcx, rcx
0x140021bf5  jz      short loc_140021BFC
0x140021bf7  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140021bfc  xor     eax, eax
0x140021bfe  add     rsp, 48h
0x140021c02  pop     r15
0x140021c04  pop     r14
0x140021c06  pop     rdi
0x140021c07  pop     rsi
0x140021c08  pop     rbx
0x140021c09  pop     rbp
0x140021c0a  retn
```
