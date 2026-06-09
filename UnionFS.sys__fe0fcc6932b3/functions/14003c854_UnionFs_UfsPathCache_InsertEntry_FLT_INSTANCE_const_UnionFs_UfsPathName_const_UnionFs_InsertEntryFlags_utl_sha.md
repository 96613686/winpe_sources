# UnionFs::UfsPathCache::InsertEntry(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,UnionFs::InsertEntryFlags,utl::shared_ptr<UnionFs::UfsPathCachePayload> const &,UnionFs::InsertEntryResults &,UnionFs::StackEventTracer &,UnionFs::InsertEntryOptionalParams *)

- ea: `0x14003c854`
- end: `0x14003cde4`
- name: `?InsertEntry@UfsPathCache@UnionFs@@QEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@W4InsertEntryFlags@2@AEBV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@AEAUInsertEntryResults@2@AEAVStackEventTracer@2@PEAUInsertEntryOptionalParams@2@@Z`
- size: `1424`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x140013b60`
- `0x14001568c`
- `0x14003c778`
- `0x14005af98`
- `0x14005e380`
- `0x140061a00`
- `0x140070afc`

## callees

- `0x14000f81c`
- `0x14003b738`
- `0x14003c20c`
- `0x14003c854`
- `0x1400448c8`
- `0x140048078`
- `0x140056c7c`
- `0x140079d8c`
- `0x140079f68`
- `0x14007baf0`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003c979`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cc81`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cd99`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c979`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cc81`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cd99`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003ca99`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003cabb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003cb1e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003cb40`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003cc16`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003cc38`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003ccf0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003cd33`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003cd55`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003ca99`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003cabb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003cb1e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003cb40`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003cc16`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003cc38`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003ccf0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003cd33`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003cd55`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003caa5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cac7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cb2a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cb4c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cc22`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cc44`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003ccfc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cd3f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cd61`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003caa5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cac7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cb2a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cb4c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cc22`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cc44`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003ccfc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cd3f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003cd61`

## string_xrefs

- `0x14003ca4f`: `PUSH: Inserting path cache payload`
- `0x14003c92e`: `PUSH: Getting copy of path for cache aging list`
- `0x14003c93f`: `UnionFs::UfsPathCache::InsertEntry`
- `0x14003ca60`: `UnionFs::UfsPathCache::InsertEntry`
- `0x14003cbd9`: `UnionFs::UfsPathCache::InsertEntry`
- `0x14003cbc8`: `PUSH: Setting cache control`

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
  v55 = off_14007E9E0;
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
0x14003c854  mov     [rsp-8+arg_18], rbx
0x14003c859  push    rbp
0x14003c85a  push    rsi
0x14003c85b  push    rdi
0x14003c85c  push    r12
0x14003c85e  push    r13
0x14003c860  push    r14
0x14003c862  push    r15
0x14003c864  lea     rbp, [rsp-60h]
0x14003c869  sub     rsp, 160h
0x14003c870  mov     rax, cs:__security_cookie
0x14003c877  xor     rax, rsp
0x14003c87a  mov     [rbp+90h+var_38], rax
0x14003c87e  mov     rdi, [rbp+90h+arg_28]
0x14003c885  mov     r14, rdx
0x14003c888  mov     r12, [rbp+90h+arg_20]
0x14003c88f  mov     r13, rcx
0x14003c892  mov     rcx, [rbp+90h+arg_38]
0x14003c899  mov     r10, r8
0x14003c89c  mov     rsi, [rbp+90h+arg_30]
0x14003c8a3  mov     [rbp+90h+var_F8], rdx
0x14003c8a7  xor     edx, edx
0x14003c8a9  mov     [rbp+90h+var_110], r9d
0x14003c8ad  mov     [rbp+90h+var_F0], r8
0x14003c8b1  mov     [rbp+90h+var_C8], 0
0x14003c8b9  test    rcx, rcx
0x14003c8bc  jz      short loc_14003C8C9
0x14003c8be  mov     rax, [rcx]
0x14003c8c1  mov     rdx, [rcx+8]
0x14003c8c5  mov     [rbp+90h+var_C8], rax
0x14003c8c9  lea     rax, off_14007E9E0
0x14003c8d0  mov     [rsp+190h+var_148], 0
0x14003c8d8  mov     [rbp+90h+var_A8], rax
0x14003c8dc  xor     ebx, ebx
0x14003c8de  mov     eax, dword ptr [rbp+90h+var_C8+4]
0x14003c8e1  mov     r15d, r9d
0x14003c8e4  mov     [rbp+90h+var_9C], eax
0x14003c8e7  lea     rax, [rsp+190h+var_148]
0x14003c8ec  mov     [rbp+90h+var_98], rax
0x14003c8f0  lea     rax, [rbp+90h+var_A8]
0x14003c8f4  mov     [rbp+90h+var_40], rax
0x14003c8f8  lea     rax, [rbp+90h+var_B0]
0x14003c8fc  mov     [rbp+90h+var_C0], rax
0x14003c900  mov     [rbp+90h+var_A0], r9d
0x14003c904  mov     [rbp+90h+var_90], rdx
0x14003c908  mov     [rsp+190h+P], rbx
0x14003c90d  and     r15d, 4
0x14003c911  jnz     loc_14003C9AB
0x14003c917  mov     r8, rsi
0x14003c91a  lea     rdx, [rsp+190h+P]
0x14003c91f  mov     rcx, r10; SourceString
0x14003c922  call    ?Copy@UfsPathName@UnionFs@@QEBAJAEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathName::Copy(utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &,UnionFs::StackEventTracer &)
0x14003c927  mov     r14d, eax
0x14003c92a  test    eax, eax
0x14003c92c  jns     short loc_14003C9A2
0x14003c92e  lea     rax, aPushGettingCop; "PUSH: Getting copy of path for cache ag"...
0x14003c935  mov     r8, 41F001000AFh; struct UnionFs::StackEventTracer *
0x14003c93f  lea     r9, aUnionfsUfspath_66; "UnionFs::UfsPathCache::InsertEntry"
0x14003c946  mov     [rsp+190h+var_170], rax; char *
0x14003c94b  mov     rdx, rsi; int
0x14003c94e  mov     ecx, r14d; this
0x14003c951  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003c956  mov     rbx, [rsp+190h+P]
0x14003c95b  test    rbx, rbx
0x14003c95e  jz      short loc_14003C985
0x14003c960  cmp     byte ptr [rbx+10h], 0
0x14003c964  jnz     short loc_14003C96C
0x14003c966  xorps   xmm0, xmm0
0x14003c969  movups  xmmword ptr [rbx], xmm0
0x14003c96c  mov     rcx, rbx; UnicodeString
0x14003c96f  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003c974  xor     edx, edx; Tag
0x14003c976  mov     rcx, rbx; P
0x14003c979  call    cs:__imp_ExFreePoolWithTag
0x14003c980  nop     dword ptr [rax+rax+00h]
0x14003c985  mov     rcx, [rbp+90h+var_40]
0x14003c989  test    rcx, rcx
0x14003c98c  jz      short loc_14003C99A
0x14003c98e  mov     rax, [rcx]
0x14003c991  mov     rax, [rax+18h]
0x14003c995  call    _guard_dispatch_icall
0x14003c99a  mov     eax, r14d
0x14003c99d  jmp     loc_14003CDBC
0x14003c9a2  mov     rbx, [rsp+190h+P]
0x14003c9a7  mov     r14, [rbp+90h+var_F8]
0x14003c9ab  mov     rax, [r12]
0x14003c9af  mov     [rbp+90h+var_108], rax
0x14003c9b3  mov     rax, [r12+8]
0x14003c9b8  mov     [rbp+90h+var_100], rax
0x14003c9bc  test    rax, rax
0x14003c9bf  jz      short loc_14003C9C5
0x14003c9c1  lock inc dword ptr [rax+8]
0x14003c9c5  lea     rdx, [r13+20h]
0x14003c9c9  lea     rcx, [rsp+190h+var_118]
0x14003c9ce  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x14003c9d3  mov     eax, r15d
0x14003c9d6  lea     r9, [rbp+90h+var_108]
0x14003c9da  neg     eax
0x14003c9dc  xorps   xmm0, xmm0
0x14003c9df  mov     rdx, r14
0x14003c9e2  sbb     ecx, ecx
0x14003c9e4  xor     r8d, r8d
0x14003c9e7  xor     eax, eax
0x14003c9e9  mov     [rsp+190h+var_140], r8
0x14003c9ee  and     ecx, 4
0x14003c9f1  mov     [rsp+190h+var_11F], eax
0x14003c9f5  inc     ecx
0x14003c9f7  mov     [rsp+190h+var_11B], ax
0x14003c9fc  mov     [rsp+190h+var_119], al
0x14003ca00  mov     eax, ecx
0x14003ca02  or      eax, 20h
0x14003ca05  mov     [rsp+190h+var_128], r8
0x14003ca0a  test    byte ptr [rbp+90h+var_110], 8
0x14003ca0e  mov     [rsp+190h+var_120], r8b
0x14003ca13  mov     r8, [rbp+90h+var_F0]
0x14003ca17  cmovz   eax, ecx
0x14003ca1a  lea     rcx, [rbp+90h+var_C8]
0x14003ca1e  mov     [rsp+190h+var_158], rcx
0x14003ca23  mov     rcx, r13
0x14003ca26  mov     [rsp+190h+var_160], eax
0x14003ca2a  lea     rax, [rsp+190h+var_140]
0x14003ca2f  mov     [rsp+190h+var_168], rsi; char *
0x14003ca34  mov     [rsp+190h+var_170], rax
0x14003ca39  movdqu  xmmword ptr [rsp+190h+Resource], xmm0
0x14003ca3f  call    ?Insert@UfsPathTable@UnionFs@@IEAAJAEBU_FLT_INSTANCE@@AEBVUfsPathName@2@AEBV?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@AEAUInsertResults@2@AEAVStackEventTracer@2@W4PathTableOptions@2@PEAUInsertOptionalParams@2@@Z; UnionFs::UfsPathTable::Insert(_FLT_INSTANCE const &,UnionFs::UfsPathName const &,utl::shared_ptr<UnionFs::UfsTablePayload> const &,UnionFs::InsertResults &,UnionFs::StackEventTracer &,UnionFs::PathTableOptions,UnionFs::InsertOptionalParams *)
0x14003ca44  mov     r14d, eax
0x14003ca47  test    eax, eax
0x14003ca49  jns     loc_14003CAEA
0x14003ca4f  lea     rax, aPushInsertingP_0; "PUSH: Inserting path cache payload"
0x14003ca56  mov     r8, 1FD001000D7h; struct UnionFs::StackEventTracer *
0x14003ca60  lea     r9, aUnionfsUfspath_66; "UnionFs::UfsPathCache::InsertEntry"
0x14003ca67  mov     [rsp+190h+var_170], rax; char *
0x14003ca6c  mov     rdx, rsi; int
0x14003ca6f  mov     ecx, r14d; this
0x14003ca72  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003ca77  mov     rcx, [rsp+190h+var_128]; this
0x14003ca7c  test    rcx, rcx
0x14003ca7f  jz      short loc_14003CA86
0x14003ca81  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003ca86  mov     rcx, [rsp+190h+Resource]; Resource
0x14003ca8b  mov     [rsp+190h+Resource], 0
0x14003ca94  test    rcx, rcx
0x14003ca97  jz      short loc_14003CAB1
0x14003ca99  call    cs:__imp_ExReleaseResourceLite
0x14003caa0  nop     dword ptr [rax+rax+00h]
0x14003caa5  call    cs:__imp_KeLeaveCriticalRegion
0x14003caac  nop     dword ptr [rax+rax+00h]
0x14003cab1  mov     rcx, [rsp+190h+var_118]; Resource
0x14003cab6  test    rcx, rcx
0x14003cab9  jz      short loc_14003CAD3
0x14003cabb  call    cs:__imp_ExReleaseResourceLite
0x14003cac2  nop     dword ptr [rax+rax+00h]
0x14003cac7  call    cs:__imp_KeLeaveCriticalRegion
0x14003cace  nop     dword ptr [rax+rax+00h]
0x14003cad3  mov     rcx, [rbp+90h+var_100]; this
0x14003cad7  test    rcx, rcx
0x14003cada  jz      loc_14003C95B
0x14003cae0  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003cae5  jmp     loc_14003C95B
0x14003caea  mov     ecx, dword ptr [rsp+190h+var_140]
0x14003caee  mov     eax, [rsp+190h+var_148]
0x14003caf2  mov     [rdi], ecx
0x14003caf4  mov     [rdi+20h], eax
0x14003caf7  cmp     ecx, 4
0x14003cafa  jnz     short loc_14003CB78
0x14003cafc  mov     rcx, [rsp+190h+var_128]; this
0x14003cb01  test    rcx, rcx
0x14003cb04  jz      short loc_14003CB0B
0x14003cb06  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003cb0b  mov     rcx, [rsp+190h+Resource]; Resource
0x14003cb10  mov     [rsp+190h+Resource], 0
0x14003cb19  test    rcx, rcx
0x14003cb1c  jz      short loc_14003CB36
0x14003cb1e  call    cs:__imp_ExReleaseResourceLite
0x14003cb25  nop     dword ptr [rax+rax+00h]
0x14003cb2a  call    cs:__imp_KeLeaveCriticalRegion
0x14003cb31  nop     dword ptr [rax+rax+00h]
0x14003cb36  mov     rcx, [rsp+190h+var_118]; Resource
0x14003cb3b  test    rcx, rcx
0x14003cb3e  jz      short loc_14003CB58
0x14003cb40  call    cs:__imp_ExReleaseResourceLite
0x14003cb47  nop     dword ptr [rax+rax+00h]
0x14003cb4c  call    cs:__imp_KeLeaveCriticalRegion
0x14003cb53  nop     dword ptr [rax+rax+00h]
0x14003cb58  mov     rcx, [rbp+90h+var_100]; this
0x14003cb5c  test    rcx, rcx
0x14003cb5f  jz      short loc_14003CB66
0x14003cb61  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003cb66  test    rbx, rbx
0x14003cb69  jz      loc_14003CDA5
0x14003cb6f  cmp     byte ptr [rbx+10h], 0
0x14003cb73  jmp     loc_14003CD84
0x14003cb78  mov     rax, [rbp+90h+var_F0]
0x14003cb7c  xor     r14d, r14d
0x14003cb7f  mov     r8, [rbp+90h+var_F8]
0x14003cb83  mov     [rbp+90h+var_D8], rax
0x14003cb87  lea     eax, [rcx-2]
0x14003cb8a  mov     [rbp+90h+var_E8], r13
0x14003cb8e  mov     [rbp+90h+var_E0], r8
0x14003cb92  mov     [rbp+90h+var_D0], 1
0x14003cb96  cmp     eax, 1
0x14003cb99  jbe     loc_14003CCB0
0x14003cb9f  test    r15d, r15d
0x14003cba2  jnz     loc_14003CD08
0x14003cba8  mov     rdx, [r12]
0x14003cbac  lea     r9, [rsp+190h+P]
0x14003cbb1  mov     rcx, r13
0x14003cbb4  mov     [rsp+190h+var_170], rsi
0x14003cbb9  call    ?AddToCacheListAfterInsertion@UfsPathCache@UnionFs@@AEAAJAEAVUfsPathCachePayload@2@AEBU_FLT_INSTANCE@@$$QEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z; UnionFs::UfsPathCache::AddToCacheListAfterInsertion(UnionFs::UfsPathCachePayload &,_FLT_INSTANCE const &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &&,UnionFs::StackEventTracer &)
0x14003cbbe  mov     edi, eax
0x14003cbc0  test    eax, eax
0x14003cbc2  jns     loc_14003CCA9
0x14003cbc8  lea     rax, aPushSettingCac; "PUSH: Setting cache control"
0x14003cbcf  mov     r8, 42E00100110h; struct UnionFs::StackEventTracer *
0x14003cbd9  lea     r9, aUnionfsUfspath_66; "UnionFs::UfsPathCache::InsertEntry"
0x14003cbe0  mov     [rsp+190h+var_170], rax; char *
0x14003cbe5  mov     rdx, rsi; int
0x14003cbe8  mov     ecx, edi; this
0x14003cbea  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14003cbef  lea     rcx, [rbp+90h+var_E8]
0x14003cbf3  call    wil__details__lambda_call__lambda_03595322f88c47eb2137ab4eeb719910______lambda_call__lambda_03595322f88c47eb2137ab4eeb719910___
0x14003cbf8  mov     rcx, [rsp+190h+var_128]; this
0x14003cbfd  test    rcx, rcx
0x14003cc00  jz      short loc_14003CC07
0x14003cc02  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003cc07  mov     rcx, [rsp+190h+Resource]; Resource
0x14003cc0c  mov     [rsp+190h+Resource], r14
0x14003cc11  test    rcx, rcx
0x14003cc14  jz      short loc_14003CC2E
0x14003cc16  call    cs:__imp_ExReleaseResourceLite
0x14003cc1d  nop     dword ptr [rax+rax+00h]
0x14003cc22  call    cs:__imp_KeLeaveCriticalRegion
0x14003cc29  nop     dword ptr [rax+rax+00h]
0x14003cc2e  mov     rcx, [rsp+190h+var_118]; Resource
0x14003cc33  test    rcx, rcx
0x14003cc36  jz      short loc_14003CC50
0x14003cc38  call    cs:__imp_ExReleaseResourceLite
0x14003cc3f  nop     dword ptr [rax+rax+00h]
0x14003cc44  call    cs:__imp_KeLeaveCriticalRegion
0x14003cc4b  nop     dword ptr [rax+rax+00h]
0x14003cc50  mov     rcx, [rbp+90h+var_100]; this
0x14003cc54  test    rcx, rcx
0x14003cc57  jz      short loc_14003CC5E
0x14003cc59  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003cc5e  mov     rbx, [rsp+190h+P]
0x14003cc63  test    rbx, rbx
0x14003cc66  jz      short loc_14003CC8D
0x14003cc68  cmp     [rbx+10h], r14b
0x14003cc6c  jnz     short loc_14003CC74
0x14003cc6e  xorps   xmm0, xmm0
0x14003cc71  movups  xmmword ptr [rbx], xmm0
0x14003cc74  mov     rcx, rbx; UnicodeString
0x14003cc77  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003cc7c  xor     edx, edx; Tag
0x14003cc7e  mov     rcx, rbx; P
0x14003cc81  call    cs:__imp_ExFreePoolWithTag
0x14003cc88  nop     dword ptr [rax+rax+00h]
0x14003cc8d  mov     rcx, [rbp+90h+var_40]
0x14003cc91  test    rcx, rcx
0x14003cc94  jz      short loc_14003CCA2
0x14003cc96  mov     rax, [rcx]
0x14003cc99  mov     rax, [rax+18h]
0x14003cc9d  call    _guard_dispatch_icall
0x14003cca2  mov     eax, edi
0x14003cca4  jmp     loc_14003CDBC
0x14003cca9  mov     rbx, [rsp+190h+P]
0x14003ccae  jmp     short loc_14003CD08
0x14003ccb0  mov     rax, [rsp+190h+var_128]
0x14003ccb5  mov     rcx, [rsp+190h+Resource+8]
0x14003ccba  test    rax, rax
0x14003ccbd  jz      short loc_14003CCC3
0x14003ccbf  lock inc dword ptr [rax+8]
0x14003ccc3  mov     [rdi+10h], rcx
0x14003ccc7  mov     rcx, [rdi+18h]; this
0x14003cccb  mov     [rdi+18h], rax
0x14003cccf  test    rcx, rcx
0x14003ccd2  jz      short loc_14003CCD9
0x14003ccd4  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003ccd9  mov     rcx, [rdi+8]; Resource
0x14003ccdd  mov     rax, [rsp+190h+Resource]
0x14003cce2  mov     [rsp+190h+Resource], r14
0x14003cce7  mov     [rdi+8], rax
0x14003cceb  test    rcx, rcx
0x14003ccee  jz      short loc_14003CD08
0x14003ccf0  call    cs:__imp_ExReleaseResourceLite
0x14003ccf7  nop     dword ptr [rax+rax+00h]
0x14003ccfc  call    cs:__imp_KeLeaveCriticalRegion
0x14003cd03  nop     dword ptr [rax+rax+00h]
0x14003cd08  lea     rcx, [rbp+90h+var_E8]
0x14003cd0c  mov     [rbp+90h+var_D0], r14b
0x14003cd10  call    wil__details__lambda_call__lambda_03595322f88c47eb2137ab4eeb719910______lambda_call__lambda_03595322f88c47eb2137ab4eeb719910___
0x14003cd15  mov     rcx, [rsp+190h+var_128]; this
0x14003cd1a  test    rcx, rcx
0x14003cd1d  jz      short loc_14003CD24
0x14003cd1f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003cd24  mov     rcx, [rsp+190h+Resource]; Resource
0x14003cd29  mov     [rsp+190h+Resource], r14
0x14003cd2e  test    rcx, rcx
0x14003cd31  jz      short loc_14003CD4B
0x14003cd33  call    cs:__imp_ExReleaseResourceLite
  ... truncated ...
```
