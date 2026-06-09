# UnionFs::UfsPathCache::InsertEntry(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::InsertEntryFlags,utl::shared_ptr<UnionFs::UfsPathCachePayload> const &,UnionFs::InsertEntryResults &,UnionFs::StackEventTracer &,UnionFs::InsertEntryOptionalParams *)

- ea: `0x14003c734`
- end: `0x14003ccc4`
- name: `?InsertEntry@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@W4InsertEntryFlags@2@AEBV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@AEAUInsertEntryResults@2@AEAVStackEventTracer@2@PEAUInsertEntryOptionalParams@2@@Z`
- size: `1424`
- prototype: ``
- caller_count: `7`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x140013bb0`
- `0x1400156a8`
- `0x14003c658`
- `0x14005ae18`
- `0x14005e200`
- `0x140061880`
- `0x14007090c`

## callees

- `0x14000f7fc`
- `0x14003b618`
- `0x14003c0ec`
- `0x14003c734`
- `0x140044748`
- `0x140047ef8`
- `0x140056afc`
- `0x140079a6c`
- `0x140079c48`
- `0x14007b7d0`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003c859`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cb61`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cc79`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c859`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cb61`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cc79`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003c979`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003c99b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003c9fe`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003ca20`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003caf6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003cb18`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003cbd0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003cc13`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003cc35`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003c979`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003c99b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003c9fe`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003ca20`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003caf6`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003cb18`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003cbd0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003cc13`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003cc35`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003c985`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003c9a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003ca0a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003ca2c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cb02`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cb24`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cbdc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cc1f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cc41`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003c985`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003c9a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003ca0a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003ca2c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cb02`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cb24`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cbdc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cc1f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cc41`

## string_xrefs

- `0x14003c92f`: `PUSH: Inserting path cache payload`
- `0x14003c80e`: `PUSH: Getting copy of path for cache aging list`
- `0x14003c81f`: `UnionFs::UfsPathCache::InsertEntry`
- `0x14003c940`: `UnionFs::UfsPathCache::InsertEntry`
- `0x14003cab9`: `UnionFs::UfsPathCache::InsertEntry`
- `0x14003caa8`: `PUSH: Setting cache control`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathCache::InsertEntry(
        __int64 a1,
        __int64 a2,
        const UNICODE_STRING *a3,
        int a4,
        __int64 *a5,
        __int64 a6,
        int a7,
        _QWORD *a8)
{
  int v8; // r14d
  __int64 v10; // rdx
  struct _UNICODE_STRING *v11; // rbx
  int v12; // r15d
  int v13; // r14d
  struct _UNICODE_STRING *v14; // rdx
  volatile signed __int32 *v16; // rax
  int v17; // eax
  struct _UNICODE_STRING *v18; // rdx
  struct _ERESOURCE *v19; // rcx
  int v20; // ecx
  int v21; // eax
  struct _ERESOURCE *v22; // rcx
  bool v23; // zf
  int v24; // edi
  struct _UNICODE_STRING *v25; // rdx
  struct _ERESOURCE *v26; // rcx
  struct _UNICODE_STRING *v27; // rbx
  utl::_RefCountBase *v28; // rax
  PERESOURCE v29; // rcx
  utl::_RefCountBase *v30; // rcx
  struct _ERESOURCE *v31; // rcx
  PERESOURCE v32; // rax
  struct _ERESOURCE *v33; // rcx
  char *v34; // [rsp+28h] [rbp-D8h]
  char *v35; // [rsp+28h] [rbp-D8h]
  PVOID P; // [rsp+40h] [rbp-C0h] BYREF
  int v37; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v38; // [rsp+50h] [rbp-B0h] BYREF
  PERESOURCE Resource[2]; // [rsp+58h] [rbp-A8h]
  utl::_RefCountBase *v40; // [rsp+68h] [rbp-98h]
  char v41; // [rsp+70h] [rbp-90h]
  int v42; // [rsp+71h] [rbp-8Fh]
  __int16 v43; // [rsp+75h] [rbp-8Bh]
  char v44; // [rsp+77h] [rbp-89h]
  PERESOURCE v45; // [rsp+78h] [rbp-88h] BYREF
  int v46; // [rsp+80h] [rbp-80h]
  __int64 v47; // [rsp+88h] [rbp-78h] BYREF
  utl::_RefCountBase *v48; // [rsp+90h] [rbp-70h]
  __int64 v49; // [rsp+98h] [rbp-68h]
  const UNICODE_STRING *v50; // [rsp+A0h] [rbp-60h]
  _QWORD v51[3]; // [rsp+A8h] [rbp-58h] BYREF
  char v52; // [rsp+C0h] [rbp-40h]
  _QWORD v53[3]; // [rsp+C8h] [rbp-38h] BYREF
  char v54; // [rsp+E0h] [rbp-20h] BYREF
  __int64 (__fastcall **v55)(); // [rsp+E8h] [rbp-18h] BYREF
  int v56; // [rsp+F0h] [rbp-10h]
  int v57; // [rsp+F4h] [rbp-Ch]
  int *v58; // [rsp+F8h] [rbp-8h]
  __int64 v59; // [rsp+100h] [rbp+0h]
  __int64 (__fastcall ***v60)(); // [rsp+150h] [rbp+50h]

  v8 = a2;
  v49 = a2;
  v10 = 0;
  v46 = a4;
  v50 = a3;
  v53[0] = 0;
  if ( a8 )
  {
    v10 = a8[1];
    v53[0] = *a8;
  }
  v37 = 0;
  v55 = off_14007E9D8;
  v11 = 0;
  v57 = HIDWORD(v53[0]);
  v58 = &v37;
  v60 = &v55;
  v53[1] = &v54;
  v56 = a4;
  v59 = v10;
  P = 0;
  v12 = a4 & 4;
  if ( (a4 & 4) == 0 )
  {
    v13 = UnionFs::UfsPathName::Copy(a3, (__int64 *)&P, a7);
    if ( v13 < 0 )
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v13,
        a7,
        (struct UnionFs::StackEventTracer *)0x41F001000AFLL,
        (unsigned __int64)"UnionFs::UfsPathCache::InsertEntry",
        "PUSH: Getting copy of path for cache aging list",
        v34);
      v11 = (struct _UNICODE_STRING *)P;
LABEL_6:
      if ( v11 )
      {
        if ( !LOBYTE(v11[1].Length) )
          *v11 = 0;
        FsFltWil::Details::FreeUnicodeString(v11, v14);
        ExFreePoolWithTag(v11, 0);
      }
      if ( v60 )
        ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v60)[3])(v60);
      return (unsigned int)v13;
    }
    v11 = (struct _UNICODE_STRING *)P;
    v8 = v49;
  }
  v47 = *a5;
  v16 = (volatile signed __int32 *)a5[1];
  v48 = (utl::_RefCountBase *)v16;
  if ( v16 )
    _InterlockedIncrement(v16 + 2);
  FsFltWil::AcquireResourceExclusive(&v45, a1 + 32);
  v38 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v17 = (v12 != 0 ? 5 : 1) | 0x20;
  v40 = 0;
  v41 = 0;
  if ( (v46 & 8) == 0 )
    v17 = v12 != 0 ? 5 : 1;
  *(_OWORD *)Resource = 0;
  v13 = UnionFs::UfsPathTable::Insert(a1, v8, (_DWORD)v50, (unsigned int)&v47, (__int64)&v38, a7, v17, (__int64)v53);
  if ( v13 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v13,
      a7,
      (struct UnionFs::StackEventTracer *)0x1FD001000D7LL,
      (unsigned __int64)"UnionFs::UfsPathCache::InsertEntry",
      "PUSH: Inserting path cache payload",
      v35);
    if ( v40 )
      utl::_RefCountBase::_DecStrong(v40);
    v19 = Resource[0];
    Resource[0] = 0;
    if ( v19 )
    {
      ExReleaseResourceLite(v19);
      KeLeaveCriticalRegion();
    }
    if ( v45 )
    {
      ExReleaseResourceLite(v45);
      KeLeaveCriticalRegion();
    }
    if ( v48 )
      utl::_RefCountBase::_DecStrong(v48);
    goto LABEL_6;
  }
  v20 = v38;
  v21 = v37;
  *(_DWORD *)a6 = v38;
  *(_DWORD *)(a6 + 32) = v21;
  if ( v20 == 4 )
  {
    if ( v40 )
      utl::_RefCountBase::_DecStrong(v40);
    v22 = Resource[0];
    Resource[0] = 0;
    if ( v22 )
    {
      ExReleaseResourceLite(v22);
      KeLeaveCriticalRegion();
    }
    if ( v45 )
    {
      ExReleaseResourceLite(v45);
      KeLeaveCriticalRegion();
    }
    if ( v48 )
      utl::_RefCountBase::_DecStrong(v48);
    if ( !v11 )
      goto LABEL_76;
    v23 = LOBYTE(v11[1].Length) == 0;
LABEL_73:
    if ( v23 )
      *v11 = 0;
    FsFltWil::Details::FreeUnicodeString(v11, v18);
    ExFreePoolWithTag(v11, 0);
LABEL_76:
    if ( v60 )
      ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v60)[3])(v60);
    return 0;
  }
  v51[2] = v50;
  v51[0] = a1;
  v51[1] = v49;
  v52 = 1;
  if ( (unsigned int)(v20 - 2) <= 1 )
  {
    v28 = v40;
    v29 = Resource[1];
    if ( v40 )
      _InterlockedIncrement((volatile signed __int32 *)v40 + 2);
    *(_QWORD *)(a6 + 16) = v29;
    v30 = *(utl::_RefCountBase **)(a6 + 24);
    *(_QWORD *)(a6 + 24) = v28;
    if ( v30 )
      utl::_RefCountBase::_DecStrong(v30);
    v31 = *(struct _ERESOURCE **)(a6 + 8);
    v32 = Resource[0];
    Resource[0] = 0;
    *(_QWORD *)(a6 + 8) = v32;
    if ( v31 )
    {
      ExReleaseResourceLite(v31);
      KeLeaveCriticalRegion();
    }
    goto LABEL_63;
  }
  if ( v12 )
  {
LABEL_63:
    v52 = 0;
    wil::details::lambda_call__lambda_03595322f88c47eb2137ab4eeb719910___::_lambda_call__lambda_03595322f88c47eb2137ab4eeb719910___(v51);
    if ( v40 )
      utl::_RefCountBase::_DecStrong(v40);
    v33 = Resource[0];
    Resource[0] = 0;
    if ( v33 )
    {
      ExReleaseResourceLite(v33);
      KeLeaveCriticalRegion();
    }
    if ( v45 )
    {
      ExReleaseResourceLite(v45);
      KeLeaveCriticalRegion();
    }
    if ( v48 )
      utl::_RefCountBase::_DecStrong(v48);
    if ( !v11 )
      goto LABEL_76;
    v23 = LOBYTE(v11[1].Length) == 0;
    goto LABEL_73;
  }
  v24 = UnionFs::UfsPathCache::AddToCacheListAfterInsertion(a1, *a5, v49, (unsigned int)&P, a7);
  if ( v24 >= 0 )
  {
    v11 = (struct _UNICODE_STRING *)P;
    goto LABEL_63;
  }
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)v24,
    a7,
    (struct UnionFs::StackEventTracer *)0x42E00100110LL,
    (unsigned __int64)"UnionFs::UfsPathCache::InsertEntry",
    "PUSH: Setting cache control",
    v35);
  wil::details::lambda_call__lambda_03595322f88c47eb2137ab4eeb719910___::_lambda_call__lambda_03595322f88c47eb2137ab4eeb719910___(v51);
  if ( v40 )
    utl::_RefCountBase::_DecStrong(v40);
  v26 = Resource[0];
  Resource[0] = 0;
  if ( v26 )
  {
    ExReleaseResourceLite(v26);
    KeLeaveCriticalRegion();
  }
  if ( v45 )
  {
    ExReleaseResourceLite(v45);
    KeLeaveCriticalRegion();
  }
  if ( v48 )
    utl::_RefCountBase::_DecStrong(v48);
  v27 = (struct _UNICODE_STRING *)P;
  if ( P )
  {
    if ( !*((_BYTE *)P + 16) )
      *(_OWORD *)P = 0;
    FsFltWil::Details::FreeUnicodeString(v27, v25);
    ExFreePoolWithTag(v27, 0);
  }
  if ( v60 )
    ((void (__fastcall *)(__int64 (__fastcall ***)()))(*v60)[3])(v60);
  return (unsigned int)v24;
}

```

## disassembly

```asm
0x14003c734  mov     [rsp-8+arg_18], rbx
0x14003c739  push    rbp
0x14003c73a  push    rsi
0x14003c73b  push    rdi
0x14003c73c  push    r12
0x14003c73e  push    r13
0x14003c740  push    r14
0x14003c742  push    r15
0x14003c744  lea     rbp, [rsp-60h]
0x14003c749  sub     rsp, 160h
0x14003c750  mov     rax, cs:__security_cookie
0x14003c757  xor     rax, rsp
0x14003c75a  mov     [rbp+90h+var_38], rax
0x14003c75e  mov     rdi, [rbp+90h+arg_28]
0x14003c765  mov     r14, rdx
0x14003c768  mov     r12, [rbp+90h+arg_20]
0x14003c76f  mov     r13, rcx
0x14003c772  mov     rcx, [rbp+90h+arg_38]
0x14003c779  mov     r10, r8
0x14003c77c  mov     rsi, [rbp+90h+arg_30]
0x14003c783  mov     [rbp+90h+var_F8], rdx
0x14003c787  xor     edx, edx
0x14003c789  mov     [rbp+90h+var_110], r9d
0x14003c78d  mov     [rbp+90h+var_F0], r8
0x14003c791  mov     [rbp+90h+var_C8], 0
0x14003c799  test    rcx, rcx
0x14003c79c  jz      short loc_14003C7A9
0x14003c79e  mov     rax, [rcx]
0x14003c7a1  mov     rdx, [rcx+8]
0x14003c7a5  mov     [rbp+90h+var_C8], rax
0x14003c7a9  lea     rax, off_14007E9D8
0x14003c7b0  mov     [rsp+190h+var_148], 0
0x14003c7b8  mov     [rbp+90h+var_A8], rax
0x14003c7bc  xor     ebx, ebx
0x14003c7be  mov     eax, dword ptr [rbp+90h+var_C8+4]
0x14003c7c1  mov     r15d, r9d
0x14003c7c4  mov     [rbp+90h+var_9C], eax
0x14003c7c7  lea     rax, [rsp+190h+var_148]
0x14003c7cc  mov     [rbp+90h+var_98], rax
0x14003c7d0  lea     rax, [rbp+90h+var_A8]
0x14003c7d4  mov     [rbp+90h+var_40], rax
0x14003c7d8  lea     rax, [rbp+90h+var_B0]
0x14003c7dc  mov     [rbp+90h+var_C0], rax
0x14003c7e0  mov     [rbp+90h+var_A0], r9d
0x14003c7e4  mov     [rbp+90h+var_90], rdx
0x14003c7e8  mov     [rsp+190h+P], rbx
0x14003c7ed  and     r15d, 4
0x14003c7f1  jnz     loc_14003C88B
0x14003c7f7  mov     r8, rsi
0x14003c7fa  lea     rdx, [rsp+190h+P]
0x14003c7ff  mov     rcx, r10; SourceString
0x14003c802  call    ?Copy@UfsPathName@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::Copy(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x14003c807  mov     r14d, eax
0x14003c80a  test    eax, eax
0x14003c80c  jns     short loc_14003C882
0x14003c80e  lea     rax, aPushGettingCop; "PUSH: Getting copy of path for cache ag"...
0x14003c815  mov     r8, 41F001000AFh; struct UnionFs::StackEventTracer *
0x14003c81f  lea     r9, aUnionfsUfspath_66; "UnionFs::UfsPathCache::InsertEntry"
0x14003c826  mov     [rsp+190h+var_170], rax; char *
0x14003c82b  mov     rdx, rsi; int
0x14003c82e  mov     ecx, r14d; this
0x14003c831  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003c836  mov     rbx, [rsp+190h+P]
0x14003c83b  test    rbx, rbx
0x14003c83e  jz      short loc_14003C865
0x14003c840  cmp     byte ptr [rbx+10h], 0
0x14003c844  jnz     short loc_14003C84C
0x14003c846  xorps   xmm0, xmm0
0x14003c849  movups  xmmword ptr [rbx], xmm0
0x14003c84c  mov     rcx, rbx; UnicodeString
0x14003c84f  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003c854  xor     edx, edx; Tag
0x14003c856  mov     rcx, rbx; P
0x14003c859  call    cs:__imp_ExFreePoolWithTag
0x14003c860  nop     dword ptr [rax+rax+00h]
0x14003c865  mov     rcx, [rbp+90h+var_40]
0x14003c869  test    rcx, rcx
0x14003c86c  jz      short loc_14003C87A
0x14003c86e  mov     rax, [rcx]
0x14003c871  mov     rax, [rax+18h]
0x14003c875  call    _guard_dispatch_icall
0x14003c87a  mov     eax, r14d
0x14003c87d  jmp     loc_14003CC9C
0x14003c882  mov     rbx, [rsp+190h+P]
0x14003c887  mov     r14, [rbp+90h+var_F8]
0x14003c88b  mov     rax, [r12]
0x14003c88f  mov     [rbp+90h+var_108], rax
0x14003c893  mov     rax, [r12+8]
0x14003c898  mov     [rbp+90h+var_100], rax
0x14003c89c  test    rax, rax
0x14003c89f  jz      short loc_14003C8A5
0x14003c8a1  lock inc dword ptr [rax+8]
0x14003c8a5  lea     rdx, [r13+20h]
0x14003c8a9  lea     rcx, [rsp+190h+var_118]
0x14003c8ae  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x14003c8b3  mov     eax, r15d
0x14003c8b6  lea     r9, [rbp+90h+var_108]
0x14003c8ba  neg     eax
0x14003c8bc  xorps   xmm0, xmm0
0x14003c8bf  mov     rdx, r14
0x14003c8c2  sbb     ecx, ecx
0x14003c8c4  xor     r8d, r8d
0x14003c8c7  xor     eax, eax
0x14003c8c9  mov     [rsp+190h+var_140], r8
0x14003c8ce  and     ecx, 4
0x14003c8d1  mov     [rsp+190h+var_11F], eax
0x14003c8d5  inc     ecx
0x14003c8d7  mov     [rsp+190h+var_11B], ax
0x14003c8dc  mov     [rsp+190h+var_119], al
0x14003c8e0  mov     eax, ecx
0x14003c8e2  or      eax, 20h
0x14003c8e5  mov     [rsp+190h+var_128], r8
0x14003c8ea  test    byte ptr [rbp+90h+var_110], 8
0x14003c8ee  mov     [rsp+190h+var_120], r8b
0x14003c8f3  mov     r8, [rbp+90h+var_F0]
0x14003c8f7  cmovz   eax, ecx
0x14003c8fa  lea     rcx, [rbp+90h+var_C8]
0x14003c8fe  mov     [rsp+190h+var_158], rcx
0x14003c903  mov     rcx, r13
0x14003c906  mov     [rsp+190h+var_160], eax
0x14003c90a  lea     rax, [rsp+190h+var_140]
0x14003c90f  mov     [rsp+190h+var_168], rsi; char *
0x14003c914  mov     [rsp+190h+var_170], rax
0x14003c919  movdqu  xmmword ptr [rsp+190h+Resource], xmm0
0x14003c91f  call    ?Insert@UfsPathTable@UnionFs@@IEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@AEBV?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@AEAUInsertResults@2@AEAVStackEventTracer@2@W4PathTableOptions@2@PEAUInsertOptionalParams@2@@Z; UnionFs::UfsPathTable::Insert(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,utl::shared_ptr<UnionFs::UfsTablePayload> const &,UnionFs::InsertResults &,UnionFs::StackEventTracer &,UnionFs::PathTableOptions,UnionFs::InsertOptionalParams *)
0x14003c924  mov     r14d, eax
0x14003c927  test    eax, eax
0x14003c929  jns     loc_14003C9CA
0x14003c92f  lea     rax, aPushInsertingP_0; "PUSH: Inserting path cache payload"
0x14003c936  mov     r8, 1FD001000D7h; struct UnionFs::StackEventTracer *
0x14003c940  lea     r9, aUnionfsUfspath_66; "UnionFs::UfsPathCache::InsertEntry"
0x14003c947  mov     [rsp+190h+var_170], rax; char *
0x14003c94c  mov     rdx, rsi; int
0x14003c94f  mov     ecx, r14d; this
0x14003c952  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003c957  mov     rcx, [rsp+190h+var_128]; this
0x14003c95c  test    rcx, rcx
0x14003c95f  jz      short loc_14003C966
0x14003c961  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003c966  mov     rcx, [rsp+190h+Resource]; Resource
0x14003c96b  mov     [rsp+190h+Resource], 0
0x14003c974  test    rcx, rcx
0x14003c977  jz      short loc_14003C991
0x14003c979  call    cs:__imp_ExReleaseResourceLite
0x14003c980  nop     dword ptr [rax+rax+00h]
0x14003c985  call    cs:__imp_KeLeaveCriticalRegion
0x14003c98c  nop     dword ptr [rax+rax+00h]
0x14003c991  mov     rcx, [rsp+190h+var_118]; Resource
0x14003c996  test    rcx, rcx
0x14003c999  jz      short loc_14003C9B3
0x14003c99b  call    cs:__imp_ExReleaseResourceLite
0x14003c9a2  nop     dword ptr [rax+rax+00h]
0x14003c9a7  call    cs:__imp_KeLeaveCriticalRegion
0x14003c9ae  nop     dword ptr [rax+rax+00h]
0x14003c9b3  mov     rcx, [rbp+90h+var_100]; this
0x14003c9b7  test    rcx, rcx
0x14003c9ba  jz      loc_14003C83B
0x14003c9c0  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003c9c5  jmp     loc_14003C83B
0x14003c9ca  mov     ecx, dword ptr [rsp+190h+var_140]
0x14003c9ce  mov     eax, [rsp+190h+var_148]
0x14003c9d2  mov     [rdi], ecx
0x14003c9d4  mov     [rdi+20h], eax
0x14003c9d7  cmp     ecx, 4
0x14003c9da  jnz     short loc_14003CA58
0x14003c9dc  mov     rcx, [rsp+190h+var_128]; this
0x14003c9e1  test    rcx, rcx
0x14003c9e4  jz      short loc_14003C9EB
0x14003c9e6  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003c9eb  mov     rcx, [rsp+190h+Resource]; Resource
0x14003c9f0  mov     [rsp+190h+Resource], 0
0x14003c9f9  test    rcx, rcx
0x14003c9fc  jz      short loc_14003CA16
0x14003c9fe  call    cs:__imp_ExReleaseResourceLite
0x14003ca05  nop     dword ptr [rax+rax+00h]
0x14003ca0a  call    cs:__imp_KeLeaveCriticalRegion
0x14003ca11  nop     dword ptr [rax+rax+00h]
0x14003ca16  mov     rcx, [rsp+190h+var_118]; Resource
0x14003ca1b  test    rcx, rcx
0x14003ca1e  jz      short loc_14003CA38
0x14003ca20  call    cs:__imp_ExReleaseResourceLite
0x14003ca27  nop     dword ptr [rax+rax+00h]
0x14003ca2c  call    cs:__imp_KeLeaveCriticalRegion
0x14003ca33  nop     dword ptr [rax+rax+00h]
0x14003ca38  mov     rcx, [rbp+90h+var_100]; this
0x14003ca3c  test    rcx, rcx
0x14003ca3f  jz      short loc_14003CA46
0x14003ca41  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003ca46  test    rbx, rbx
0x14003ca49  jz      loc_14003CC85
0x14003ca4f  cmp     byte ptr [rbx+10h], 0
0x14003ca53  jmp     loc_14003CC64
0x14003ca58  mov     rax, [rbp+90h+var_F0]
0x14003ca5c  xor     r14d, r14d
0x14003ca5f  mov     r8, [rbp+90h+var_F8]
0x14003ca63  mov     [rbp+90h+var_D8], rax
0x14003ca67  lea     eax, [rcx-2]
0x14003ca6a  mov     [rbp+90h+var_E8], r13
0x14003ca6e  mov     [rbp+90h+var_E0], r8
0x14003ca72  mov     [rbp+90h+var_D0], 1
0x14003ca76  cmp     eax, 1
0x14003ca79  jbe     loc_14003CB90
0x14003ca7f  test    r15d, r15d
0x14003ca82  jnz     loc_14003CBE8
0x14003ca88  mov     rdx, [r12]
0x14003ca8c  lea     r9, [rsp+190h+P]
0x14003ca91  mov     rcx, r13
0x14003ca94  mov     [rsp+190h+var_170], rsi
0x14003ca99  call    ?AddToCacheListAfterInsertion@UfsPathCache@UnionFs@@AEAAJAEAVUfsPathCachePayload@2@AEBU_FLT_INSTANCE@@$$QEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathCache::AddToCacheListAfterInsertion(UnionFs::UfsPathCachePayload &,_FLT_INSTANCE const &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &&,UnionFs::StackEventTracer &)
0x14003ca9e  mov     edi, eax
0x14003caa0  test    eax, eax
0x14003caa2  jns     loc_14003CB89
0x14003caa8  lea     rax, aPushSettingCac; "PUSH: Setting cache control"
0x14003caaf  mov     r8, 42E00100110h; struct UnionFs::StackEventTracer *
0x14003cab9  lea     r9, aUnionfsUfspath_66; "UnionFs::UfsPathCache::InsertEntry"
0x14003cac0  mov     [rsp+190h+var_170], rax; char *
0x14003cac5  mov     rdx, rsi; int
0x14003cac8  mov     ecx, edi; this
0x14003caca  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003cacf  lea     rcx, [rbp+90h+var_E8]
0x14003cad3  call    wil__details__lambda_call__lambda_03595322f88c47eb2137ab4eeb719910______lambda_call__lambda_03595322f88c47eb2137ab4eeb719910___
0x14003cad8  mov     rcx, [rsp+190h+var_128]; this
0x14003cadd  test    rcx, rcx
0x14003cae0  jz      short loc_14003CAE7
0x14003cae2  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003cae7  mov     rcx, [rsp+190h+Resource]; Resource
0x14003caec  mov     [rsp+190h+Resource], r14
0x14003caf1  test    rcx, rcx
0x14003caf4  jz      short loc_14003CB0E
0x14003caf6  call    cs:__imp_ExReleaseResourceLite
0x14003cafd  nop     dword ptr [rax+rax+00h]
0x14003cb02  call    cs:__imp_KeLeaveCriticalRegion
0x14003cb09  nop     dword ptr [rax+rax+00h]
0x14003cb0e  mov     rcx, [rsp+190h+var_118]; Resource
0x14003cb13  test    rcx, rcx
0x14003cb16  jz      short loc_14003CB30
0x14003cb18  call    cs:__imp_ExReleaseResourceLite
0x14003cb1f  nop     dword ptr [rax+rax+00h]
0x14003cb24  call    cs:__imp_KeLeaveCriticalRegion
0x14003cb2b  nop     dword ptr [rax+rax+00h]
0x14003cb30  mov     rcx, [rbp+90h+var_100]; this
0x14003cb34  test    rcx, rcx
0x14003cb37  jz      short loc_14003CB3E
0x14003cb39  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003cb3e  mov     rbx, [rsp+190h+P]
0x14003cb43  test    rbx, rbx
0x14003cb46  jz      short loc_14003CB6D
0x14003cb48  cmp     [rbx+10h], r14b
0x14003cb4c  jnz     short loc_14003CB54
0x14003cb4e  xorps   xmm0, xmm0
0x14003cb51  movups  xmmword ptr [rbx], xmm0
0x14003cb54  mov     rcx, rbx; UnicodeString
0x14003cb57  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003cb5c  xor     edx, edx; Tag
0x14003cb5e  mov     rcx, rbx; P
0x14003cb61  call    cs:__imp_ExFreePoolWithTag
0x14003cb68  nop     dword ptr [rax+rax+00h]
0x14003cb6d  mov     rcx, [rbp+90h+var_40]
0x14003cb71  test    rcx, rcx
0x14003cb74  jz      short loc_14003CB82
0x14003cb76  mov     rax, [rcx]
0x14003cb79  mov     rax, [rax+18h]
0x14003cb7d  call    _guard_dispatch_icall
0x14003cb82  mov     eax, edi
0x14003cb84  jmp     loc_14003CC9C
0x14003cb89  mov     rbx, [rsp+190h+P]
0x14003cb8e  jmp     short loc_14003CBE8
0x14003cb90  mov     rax, [rsp+190h+var_128]
0x14003cb95  mov     rcx, [rsp+190h+Resource+8]
0x14003cb9a  test    rax, rax
0x14003cb9d  jz      short loc_14003CBA3
0x14003cb9f  lock inc dword ptr [rax+8]
0x14003cba3  mov     [rdi+10h], rcx
0x14003cba7  mov     rcx, [rdi+18h]; this
0x14003cbab  mov     [rdi+18h], rax
0x14003cbaf  test    rcx, rcx
0x14003cbb2  jz      short loc_14003CBB9
0x14003cbb4  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003cbb9  mov     rcx, [rdi+8]; Resource
0x14003cbbd  mov     rax, [rsp+190h+Resource]
0x14003cbc2  mov     [rsp+190h+Resource], r14
0x14003cbc7  mov     [rdi+8], rax
0x14003cbcb  test    rcx, rcx
0x14003cbce  jz      short loc_14003CBE8
0x14003cbd0  call    cs:__imp_ExReleaseResourceLite
0x14003cbd7  nop     dword ptr [rax+rax+00h]
0x14003cbdc  call    cs:__imp_KeLeaveCriticalRegion
0x14003cbe3  nop     dword ptr [rax+rax+00h]
0x14003cbe8  lea     rcx, [rbp+90h+var_E8]
0x14003cbec  mov     [rbp+90h+var_D0], r14b
0x14003cbf0  call    wil__details__lambda_call__lambda_03595322f88c47eb2137ab4eeb719910______lambda_call__lambda_03595322f88c47eb2137ab4eeb719910___
0x14003cbf5  mov     rcx, [rsp+190h+var_128]; this
0x14003cbfa  test    rcx, rcx
0x14003cbfd  jz      short loc_14003CC04
0x14003cbff  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003cc04  mov     rcx, [rsp+190h+Resource]; Resource
0x14003cc09  mov     [rsp+190h+Resource], r14
0x14003cc0e  test    rcx, rcx
0x14003cc11  jz      short loc_14003CC2B
0x14003cc13  call    cs:__imp_ExReleaseResourceLite
  ... truncated ...
```
