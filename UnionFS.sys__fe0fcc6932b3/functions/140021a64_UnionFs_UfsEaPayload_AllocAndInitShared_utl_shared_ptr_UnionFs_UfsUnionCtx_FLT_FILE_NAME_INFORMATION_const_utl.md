# UnionFs::UfsEaPayload::AllocAndInitShared(utl::shared_ptr<UnionFs::UfsUnionCtx>,_FLT_FILE_NAME_INFORMATION const &,utl::shared_ptr<UnionFs::UfsEaPayload> &,UnionFs::StackEventTracer &,bool)

- ea: `0x140021a64`
- end: `0x140021cac`
- name: `?AllocAndInitShared@UfsEaPayload@UnionFs@@SAJV?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@AEBU_FLT_FILE_NAME_INFORMATION@@AEAV?$shared_ptr@VUfsEaPayload@UnionFs@@@4@AEAVStackEventTracer@2@_N@Z`
- size: `584`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x14001d5d0`

## callees

- `0x14000f81c`
- `0x14001f41c`
- `0x140021510`
- `0x1400215f0`
- `0x140021a64`
- `0x140043afc`
- `0x140056c44`
- `0x140056c7c`
- `0x140079f68`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140021c0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021c69`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021c0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021c69`
- `ntoskrnl!ExAllocatePool2` at `0x140021ab5`
- `ntoskrnl!ExAllocatePool2` at `0x140021ab5`

## string_xrefs

- `0x140021c1b`: `PUSH: Adding scratch path to EA payload`
- `0x140021b91`: `UnionFs::UfsEaPayload::AddScratchPath`
- `0x140021bd4`: `UnionFs::UfsEaPayload::AddScratchPath`
- `0x140021bc1`: `ORIGIN: Adding scratch path to EA payload`
- `0x140021b80`: `PUSH: Allocating path name`

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
0x140021a64  push    rbp
0x140021a66  push    rbx
0x140021a67  push    rsi
0x140021a68  push    rdi
0x140021a69  push    r14
0x140021a6b  push    r15
0x140021a6d  mov     rbp, rsp
0x140021a70  sub     rsp, 48h
0x140021a74  mov     r14, rcx
0x140021a77  mov     qword ptr [r8], 0
0x140021a7e  mov     rcx, [r8+8]; this
0x140021a82  mov     r15, r9
0x140021a85  mov     qword ptr [r8+8], 0
0x140021a8d  mov     rsi, r8
0x140021a90  mov     rbx, rdx
0x140021a93  test    rcx, rcx
0x140021a96  jz      short loc_140021A9D
0x140021a98  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140021a9d  xorps   xmm0, xmm0
0x140021aa0  mov     edx, 0E0h
0x140021aa5  mov     ecx, 40h ; '@'
0x140021aaa  mov     r8d, 74654655h
0x140021ab0  movdqu  xmmword ptr [rbp+var_18], xmm0
0x140021ab5  call    cs:__imp_ExAllocatePool2
0x140021abc  nop     dword ptr [rax+rax+00h]
0x140021ac1  test    rax, rax
0x140021ac4  jz      short loc_140021AD0
0x140021ac6  xor     edx, edx; bool
0x140021ac8  mov     rcx, rax; this
0x140021acb  call    ??0UfsEaPayload@UnionFs@@AEAA@_N@Z; UnionFs::UfsEaPayload::UfsEaPayload(bool)
0x140021ad0  mov     rdx, rax
0x140021ad3  lea     rcx, [rbp+var_18]
0x140021ad7  call    ??$reset@VUfsEaPayload@UnionFs@@$0A@@?$shared_ptr@VUfsEaPayload@UnionFs@@@utl@@QEAA_NPEAVUfsEaPayload@UnionFs@@@Z; utl::shared_ptr<UnionFs::UfsEaPayload>::reset<UnionFs::UfsEaPayload,0>(UnionFs::UfsEaPayload *)
0x140021adc  mov     rdi, [rbp+var_18]
0x140021ae0  test    rdi, rdi
0x140021ae3  jnz     short loc_140021B34
0x140021ae5  lea     rax, aOriginAllocati_14; "ORIGIN: Allocating ea table payload nod"...
0x140021aec  mov     ebx, 0C000009Ah
0x140021af1  mov     ecx, ebx; this
0x140021af3  mov     [rsp+48h+var_28], rax; char *
0x140021af8  lea     r9, aUnionfsUfseapa_2; "UnionFs::UfsEaPayload::AllocAndInitShar"...
0x140021aff  mov     r8, 20D00070227h; struct UnionFs::StackEventTracer *
0x140021b09  mov     rdx, r15; int
0x140021b0c  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140021b11  mov     rcx, [rbp+var_18+8]; this
0x140021b15  test    rcx, rcx
0x140021b18  jz      short loc_140021B1F
0x140021b1a  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140021b1f  mov     rcx, [r14+8]; this
0x140021b23  test    rcx, rcx
0x140021b26  jz      short loc_140021B2D
0x140021b28  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140021b2d  mov     eax, ebx
0x140021b2f  jmp     loc_140021C9E
0x140021b34  mov     rax, [r14+8]
0x140021b38  mov     rcx, [r14]
0x140021b3b  test    rax, rax
0x140021b3e  jz      short loc_140021B44
0x140021b40  lock inc dword ptr [rax+8]
0x140021b44  mov     [rdi+0C8h], rcx
0x140021b4b  mov     rcx, [rdi+0D0h]; this
0x140021b52  mov     [rdi+0D0h], rax
0x140021b59  test    rcx, rcx
0x140021b5c  jz      short loc_140021B63
0x140021b5e  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140021b63  mov     r8, r15
0x140021b66  mov     [rbp+P], 0
0x140021b6e  lea     rdx, [rbp+P]
0x140021b72  mov     rcx, rbx
0x140021b75  call    ?AllocAndInit@UfsPathName@UnionFs@@SAJAEBU_FLT_FILE_NAME_INFORMATION@@AEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::AllocAndInit(_FLT_FILE_NAME_INFORMATION const &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x140021b7a  mov     ebx, eax
0x140021b7c  test    eax, eax
0x140021b7e  jns     short loc_140021BA9
0x140021b80  lea     rax, aPushAllocating_19; "PUSH: Allocating path name"
0x140021b87  mov     r8, 2C3000701DFh; struct UnionFs::StackEventTracer *
0x140021b91  lea     r9, aUnionfsUfseapa_1; "UnionFs::UfsEaPayload::AddScratchPath"
0x140021b98  mov     [rsp+48h+var_28], rax; char *
0x140021b9d  mov     rdx, r15; int
0x140021ba0  mov     ecx, ebx; this
0x140021ba2  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140021ba7  jmp     short loc_140021BED
0x140021ba9  lea     rcx, [rdi+0B0h]
0x140021bb0  lea     rdx, [rbp+P]
0x140021bb4  call    ?push_back@?$vector@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@@2@@utl@@QEAA_N$$QEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@2@@Z; utl::vector<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>,utl::allocator<utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>>>>::push_back(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &&)
0x140021bb9  test    al, al
0x140021bbb  jnz     loc_140021C47
0x140021bc1  lea     rax, aOriginAddingSc; "ORIGIN: Adding scratch path to EA paylo"...
0x140021bc8  mov     ebx, 0C000009Ah
0x140021bcd  mov     ecx, ebx; this
0x140021bcf  mov     [rsp+48h+var_28], rax; char *
0x140021bd4  lea     r9, aUnionfsUfseapa_1; "UnionFs::UfsEaPayload::AddScratchPath"
0x140021bdb  mov     r8, 357000701E5h; struct UnionFs::StackEventTracer *
0x140021be5  mov     rdx, r15; int
0x140021be8  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140021bed  mov     rdi, [rbp+P]
0x140021bf1  test    rdi, rdi
0x140021bf4  jz      short loc_140021C1B
0x140021bf6  cmp     byte ptr [rdi+10h], 0
0x140021bfa  jnz     short loc_140021C02
0x140021bfc  xorps   xmm0, xmm0
0x140021bff  movups  xmmword ptr [rdi], xmm0
0x140021c02  mov     rcx, rdi; UnicodeString
0x140021c05  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140021c0a  xor     edx, edx; Tag
0x140021c0c  mov     rcx, rdi; P
0x140021c0f  call    cs:__imp_ExFreePoolWithTag
0x140021c16  nop     dword ptr [rax+rax+00h]
0x140021c1b  lea     rax, aPushAddingScra; "PUSH: Adding scratch path to EA payload"
0x140021c22  mov     r8, 3A70007022Eh; struct UnionFs::StackEventTracer *
0x140021c2c  lea     r9, aUnionfsUfseapa_2; "UnionFs::UfsEaPayload::AllocAndInitShar"...
0x140021c33  mov     [rsp+48h+var_28], rax; char *
0x140021c38  mov     rdx, r15; int
0x140021c3b  mov     ecx, ebx; this
0x140021c3d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140021c42  jmp     loc_140021B11
0x140021c47  mov     rbx, [rbp+P]
0x140021c4b  test    rbx, rbx
0x140021c4e  jz      short loc_140021C75
0x140021c50  cmp     byte ptr [rbx+10h], 0
0x140021c54  jnz     short loc_140021C5C
0x140021c56  xorps   xmm0, xmm0
0x140021c59  movups  xmmword ptr [rbx], xmm0
0x140021c5c  mov     rcx, rbx; UnicodeString
0x140021c5f  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140021c64  xor     edx, edx; Tag
0x140021c66  mov     rcx, rbx; P
0x140021c69  call    cs:__imp_ExFreePoolWithTag
0x140021c70  nop     dword ptr [rax+rax+00h]
0x140021c75  mov     rcx, [rsi+8]; this
0x140021c79  mov     rax, [rbp+var_18+8]
0x140021c7d  mov     [rsi], rdi
0x140021c80  mov     [rsi+8], rax
0x140021c84  test    rcx, rcx
0x140021c87  jz      short loc_140021C8E
0x140021c89  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140021c8e  mov     rcx, [r14+8]; this
0x140021c92  test    rcx, rcx
0x140021c95  jz      short loc_140021C9C
0x140021c97  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140021c9c  xor     eax, eax
0x140021c9e  add     rsp, 48h
0x140021ca2  pop     r15
0x140021ca4  pop     r14
0x140021ca6  pop     rdi
0x140021ca7  pop     rsi
0x140021ca8  pop     rbx
0x140021ca9  pop     rbp
0x140021caa  retn
```
