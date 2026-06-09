# UnionFs::UfsPathCachePayload::CheckAndCacheCallerAccess(_FLT_CALLBACK_DATA &,UnionFs::StackEventTracer &,bool)

- ea: `0x1400414c8`
- end: `0x140041837`
- name: `?CheckAndCacheCallerAccess@UfsPathCachePayload@UnionFs@@QEAAJAEAU_FLT_CALLBACK_DATA@@AEAVStackEventTracer@2@_N@Z`
- size: `879`
- prototype: `int(UnionFs::UfsPathCachePayload *__hidden this, struct _FLT_CALLBACK_DATA *, struct UnionFs::StackEventTracer *, bool)`
- caller_count: `3`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140013bb0`
- `0x1400156a8`
- `0x140058fbc`

## callees

- `0x14000f7fc`
- `0x14003f2fc`
- `0x1400414c8`
- `0x140056ac4`
- `0x140056afc`
- `0x140068770`
- `0x14006ff9c`
- `0x140077f94`
- `0x140079a6c`
- `0x140079ab4`
- `0x140079c48`
- `0x14007af90`
- `0x14007b7d0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!RtlHashUnicodeString` at `0x14004156f`
- `ntoskrnl!RtlHashUnicodeString` at `0x14004156f`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400415d0`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400415d0`
- `ntoskrnl!PsGetHostSilo` at `0x140041629`
- `ntoskrnl!PsGetHostSilo` at `0x140041629`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041602`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041732`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041759`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041602`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041732`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041759`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004160e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004173e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140041765`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004160e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004173e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140041765`

## string_xrefs

- `0x14004151e`: `PUSH: GetUserSidString`
- `0x1400416a3`: `UnionFs::UfsPathCachePayload::CheckAndCacheCallerAccess`
- `0x14004170b`: `UnionFs::UfsPathCachePayload::CheckAndCacheCallerAccess`
- `0x1400417e9`: `UnionFs::UfsPathCachePayload::CheckAndCacheCallerAccess`
- `0x1400416f8`: `ORIGIN: Inserting callerSid`
- `0x1400417d8`: `PUSH: AccessCheck`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathCachePayload::CheckAndCacheCallerAccess(
        UnionFs::UfsPathCachePayload *this,
        struct _FLT_CALLBACK_DATA *a2,
        struct UnionFs::StackEventTracer *a3,
        char a4)
{
  char v6; // r12
  int UserSidString; // ebx
  const char *v9; // rax
  __int64 v10; // r8
  unsigned __int64 v11; // r14
  __int64 v12; // rcx
  __int64 *v13; // rbx
  __int64 *v14; // r12
  __int64 v15; // rdx
  __int64 v16; // rcx
  unsigned int *HostSilo; // rax
  volatile signed __int32 *v18; // rbx
  __int64 v19; // rcx
  __int64 v20; // rdx
  int v21; // r14d
  struct _UNICODE_STRING *v22; // rdx
  void *v23; // rdx
  __m128d *v24; // rax
  __m128d v25; // xmm2
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  int v27; // r8d
  char *v29; // [rsp+28h] [rbp-D8h]
  ULONG HashValue; // [rsp+44h] [rbp-BCh] BYREF
  PERESOURCE Resource[2]; // [rsp+48h] [rbp-B8h] BYREF
  UNICODE_STRING String; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v34; // [rsp+68h] [rbp-98h]
  __int64 v35; // [rsp+70h] [rbp-90h]
  _BYTE v36[24]; // [rsp+78h] [rbp-88h]
  __int64 v37; // [rsp+90h] [rbp-70h] BYREF
  __int128 v38[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v39; // [rsp+C0h] [rbp-40h]
  _BYTE v40[80]; // [rsp+D0h] [rbp-30h] BYREF

  v6 = a4;
  String = 0;
  UserSidString = UnionFs::Utils::GetUserSidString((__int64)a2, &String, (int)a3);
  if ( UserSidString < 0 )
  {
    v9 = "PUSH: GetUserSidString";
    v10 = 0x24300120181LL;
LABEL_32:
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)UserSidString,
      (int)a3,
      (struct UnionFs::StackEventTracer *)v10,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::CheckAndCacheCallerAccess",
      v9,
      v29);
    goto LABEL_34;
  }
  FsFltWil::AcquireResourceShared(Resource, *((_QWORD *)this + 17) + 80LL);
  if ( *((_QWORD *)this + 14) )
  {
    HashValue = 0;
    if ( RtlHashUnicodeString(&String, 1u, 0, &HashValue) < 0 )
      MicrosoftTelemetryAssertTriggeredMsgKM("RtlHashUnicodeString error?!");
    v11 = HashValue;
    v12 = *((_QWORD *)this + 14);
    v13 = *(__int64 **)(v12 + 16 * (HashValue & (unsigned __int64)((8LL << *((_BYTE *)this + 128)) - 1)));
    if ( v13 )
    {
      v14 = **(__int64 ***)(v12 + 16 * (HashValue & (unsigned __int64)((8LL << *((_BYTE *)this + 128)) - 1)) + 8);
      while ( v13 != v14 )
      {
        if ( v13[2] >= v11 )
        {
          if ( v13[2] > v11 )
            break;
          if ( RtlEqualUnicodeString(&String, (PCUNICODE_STRING)(v13 + 3), 1u) )
          {
            if ( v13 != (__int64 *)((char *)this + 96) )
              goto LABEL_28;
            break;
          }
        }
        v13 = (__int64 *)*v13;
      }
      v6 = a4;
    }
  }
  if ( Resource[0] )
  {
    ExReleaseResourceLite(Resource[0]);
    KeLeaveCriticalRegion();
  }
  memset(v40, 0, 0x48u);
  HostSilo = (unsigned int *)PsGetHostSilo(v16, v15);
  v18 = (volatile signed __int32 *)*((_QWORD *)this + 5);
  v19 = *((_QWORD *)this + 4);
  if ( v18 )
    _InterlockedIncrement(v18 + 2);
  v20 = **(_QWORD **)(v19 + 8);
  *(_OWORD *)Resource = *(_OWORD *)*((_QWORD *)this + 6);
  v21 = UnionFs::Utils::StatItemAsCaller(
          (const char *)Resource,
          v20,
          HostSilo,
          0,
          (__int64)v40,
          (UnionFs::Utils *)a2,
          (int)a3);
  if ( v18 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v18);
  if ( v21 < 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v21,
      (int)a3,
      (struct UnionFs::StackEventTracer *)0x24500120197LL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::CheckAndCacheCallerAccess",
      "PUSH: Stat layer item",
      v29);
    UserSidString = v21;
    goto LABEL_34;
  }
  if ( v6 )
  {
LABEL_30:
    v23 = (void *)*((_QWORD *)this + 10);
    HIDWORD(v34) = *((_DWORD *)this + 22);
    v24 = (__m128d *)*((_QWORD *)this + 6);
    v35 = 0;
    *(_QWORD *)v36 = 0;
    LODWORD(v34) = 1;
    v25 = *v24;
    Iopb = a2->Iopb;
    *(__m128d *)&v36[8] = v25;
    v27 = *(_DWORD *)(Iopb->Parameters.WMI.ProviderId + 16);
    v38[0] = v34;
    v38[1] = *(_OWORD *)v36;
    v39 = *(_OWORD *)&_mm_unpackhi_pd(v25, v25);
    UserSidString = UnionFs::Utils::AccessCheck(v38, v23, v27, (__int64)a2, (__int64)a3);
    if ( UserSidString >= 0 )
    {
      UserSidString = 0;
      goto LABEL_34;
    }
    v9 = "PUSH: AccessCheck";
    v10 = 0x244001201BALL;
    goto LABEL_32;
  }
  FsFltWil::AcquireResourceExclusive(Resource, *((_QWORD *)this + 17) + 80LL);
  utl::_HashTable<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,UnionFs::UfsPathCachePayload::SidHash,UnionFs::UfsPathCachePayload::SidEqualsPred,utl::allocator<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>,0>::_InsertImpl<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>(
    (char *)this + 96,
    &v37,
    &String);
  if ( v37 )
  {
LABEL_28:
    if ( Resource[0] )
    {
      ExReleaseResourceLite(Resource[0]);
      KeLeaveCriticalRegion();
    }
    goto LABEL_30;
  }
  UserSidString = -1073741670;
  UnionFs::ProcessTraceStatusOrigin(
    (UnionFs *)0xC000009ALL,
    (int)a3,
    (struct UnionFs::StackEventTracer *)0x246001201A5LL,
    (unsigned __int64)"UnionFs::UfsPathCachePayload::CheckAndCacheCallerAccess",
    "ORIGIN: Inserting callerSid",
    v29);
  if ( Resource[0] )
  {
    ExReleaseResourceLite(Resource[0]);
    KeLeaveCriticalRegion();
  }
LABEL_34:
  FsFltWil::Details::FreeUnicodeString(&String, v22);
  return (unsigned int)UserSidString;
}

```

## disassembly

```asm
0x1400414c8  mov     [rsp-8+arg_18], rbx
0x1400414cd  push    rbp
0x1400414ce  push    rsi
0x1400414cf  push    rdi
0x1400414d0  push    r12
0x1400414d2  push    r13
0x1400414d4  push    r14
0x1400414d6  push    r15
0x1400414d8  lea     rbp, [rsp-30h]
0x1400414dd  sub     rsp, 130h
0x1400414e4  mov     rax, cs:__security_cookie
0x1400414eb  xor     rax, rsp
0x1400414ee  mov     [rbp+60h+var_40], rax
0x1400414f2  mov     r13, rdx
0x1400414f5  mov     [rsp+160h+var_120], r9b
0x1400414fa  mov     rsi, rcx
0x1400414fd  lea     rdx, [rsp+160h+String]
0x140041502  xorps   xmm0, xmm0
0x140041505  mov     rcx, r13
0x140041508  mov     r12b, r9b
0x14004150b  mov     rdi, r8
0x14004150e  movups  xmmword ptr [rsp+160h+String.Length], xmm0
0x140041513  call    ?GetUserSidString@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetUserSidString(_FLT_CALLBACK_DATA const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)
0x140041518  mov     ebx, eax
0x14004151a  test    eax, eax
0x14004151c  jns     short loc_140041534
0x14004151e  lea     rax, aPushGetusersid; "PUSH: GetUserSidString"
0x140041525  mov     r8, 24300120181h
0x14004152f  jmp     loc_1400417E9
0x140041534  mov     rdx, [rsi+88h]
0x14004153b  lea     rcx, [rsp+160h+Resource]
0x140041540  add     rdx, 50h ; 'P'
0x140041544  call    ?AcquireResourceShared@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceShared(_ERESOURCE &)
0x140041549  lea     r15, [rsi+60h]
0x14004154d  cmp     qword ptr [r15+10h], 0
0x140041552  jz      loc_1400415F8
0x140041558  lea     r9, [rsp+160h+HashValue]; HashValue
0x14004155d  mov     [rsp+160h+HashValue], 0
0x140041565  xor     r8d, r8d; HashAlgorithm
0x140041568  lea     rcx, [rsp+160h+String]; String
0x14004156d  mov     dl, 1; CaseInSensitive
0x14004156f  call    cs:__imp_RtlHashUnicodeString
0x140041576  nop     dword ptr [rax+rax+00h]
0x14004157b  test    eax, eax
0x14004157d  jns     short loc_14004158B
0x14004157f  lea     rcx, aRtlhashunicode; "RtlHashUnicodeString error?!"
0x140041586  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14004158b  mov     cl, [r15+20h]
0x14004158f  mov     eax, 8
0x140041594  mov     r14d, [rsp+160h+HashValue]
0x140041599  shl     rax, cl
0x14004159c  mov     rcx, [r15+10h]
0x1400415a0  dec     rax
0x1400415a3  and     rax, r14
0x1400415a6  add     rax, rax
0x1400415a9  mov     rbx, [rcx+rax*8]
0x1400415ad  test    rbx, rbx
0x1400415b0  jz      short loc_1400415F8
0x1400415b2  mov     rax, [rcx+rax*8+8]
0x1400415b7  mov     r12, [rax]
0x1400415ba  jmp     short loc_1400415E3
0x1400415bc  cmp     [rbx+10h], r14
0x1400415c0  jb      short loc_1400415E0
0x1400415c2  ja      short loc_1400415F3
0x1400415c4  lea     rdx, [rbx+18h]; String2
0x1400415c8  mov     r8b, 1; CaseInSensitive
0x1400415cb  lea     rcx, [rsp+160h+String]; String1
0x1400415d0  call    cs:__imp_RtlEqualUnicodeString
0x1400415d7  nop     dword ptr [rax+rax+00h]
0x1400415dc  test    al, al
0x1400415de  jnz     short loc_1400415EA
0x1400415e0  mov     rbx, [rbx]
0x1400415e3  cmp     rbx, r12
0x1400415e6  jnz     short loc_1400415BC
0x1400415e8  jmp     short loc_1400415F3
0x1400415ea  cmp     rbx, r15
0x1400415ed  jnz     loc_14004174F
0x1400415f3  mov     r12b, [rsp+160h+var_120]
0x1400415f8  mov     rcx, [rsp+160h+Resource]; Resource
0x1400415fd  test    rcx, rcx
0x140041600  jz      short loc_14004161A
0x140041602  call    cs:__imp_ExReleaseResourceLite
0x140041609  nop     dword ptr [rax+rax+00h]
0x14004160e  call    cs:__imp_KeLeaveCriticalRegion
0x140041615  nop     dword ptr [rax+rax+00h]
0x14004161a  xor     edx, edx; Val
0x14004161c  lea     rcx, [rbp+60h+var_90]; void *
0x140041620  lea     r8d, [rdx+48h]; Size
0x140041624  call    memset
0x140041629  call    cs:__imp_PsGetHostSilo
0x140041630  nop     dword ptr [rax+rax+00h]
0x140041635  mov     rbx, [rsi+28h]
0x140041639  mov     rcx, [rsi+20h]
0x14004163d  test    rbx, rbx
0x140041640  jz      short loc_140041646
0x140041642  lock inc dword ptr [rbx+8]
0x140041646  mov     rcx, [rcx+8]
0x14004164a  xor     r9d, r9d
0x14004164d  mov     [rsp+160h+var_130], rdi
0x140041652  mov     r8, rax
0x140041655  mov     [rsp+160h+var_138], r13; char *
0x14004165a  mov     rdx, [rcx]
0x14004165d  mov     rcx, [rsi+30h]
0x140041661  movups  xmm0, xmmword ptr [rcx]
0x140041664  lea     rcx, [rbp+60h+var_90]
0x140041668  mov     [rsp+160h+var_140], rcx
0x14004166d  lea     rcx, [rsp+160h+Resource]
0x140041672  movdqu  xmmword ptr [rsp+160h+Resource], xmm0
0x140041678  call    ?StatItemAsCaller@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBU_FLT_INSTANCE@@AEBU_EJOB@@W4StatItemFlags@12@PEAU_FILE_STAT_INFORMATION@@AEAU_FLT_CALLBACK_DATA@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::StatItemAsCaller(_UNICODE_STRING const &,_FLT_INSTANCE const &,_EJOB const &,UnionFs::Utils::StatItemFlags,_FILE_STAT_INFORMATION *,_FLT_CALLBACK_DATA &,UnionFs::StackEventTracer &)
0x14004167d  mov     r14d, eax
0x140041680  test    rbx, rbx
0x140041683  jz      short loc_14004168D
0x140041685  mov     rcx, rbx; this
0x140041688  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004168d  test    r14d, r14d
0x140041690  jns     short loc_1400416C2
0x140041692  lea     rax, aPushStatLayerI; "PUSH: Stat layer item"
0x140041699  mov     r8, 24500120197h; struct UnionFs::StackEventTracer *
0x1400416a3  lea     r9, aUnionfsUfspath_64; "UnionFs::UfsPathCachePayload::CheckAndC"...
0x1400416aa  mov     [rsp+160h+var_140], rax; char *
0x1400416af  mov     rdx, rdi; int
0x1400416b2  mov     ecx, r14d; this
0x1400416b5  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400416ba  mov     ebx, r14d
0x1400416bd  jmp     loc_140041803
0x1400416c2  test    r12b, r12b
0x1400416c5  jnz     loc_140041771
0x1400416cb  mov     rdx, [rsi+88h]
0x1400416d2  lea     rcx, [rsp+160h+Resource]
0x1400416d7  add     rdx, 50h ; 'P'
0x1400416db  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x1400416e0  lea     r8, [rsp+160h+String]
0x1400416e5  mov     rcx, r15
0x1400416e8  lea     rdx, [rbp+60h+var_D0]
0x1400416ec  call    ??$_InsertImpl@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@?$_HashTable@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@V12@USidHash@UfsPathCachePayload@UnionFs@@USidEqualsPred@45@V?$allocator@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@utl@@$0A@@utl@@AEAA?AU?$pair@V?$_DlistConstIt@U?$_HashNode@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@utl@@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@utl@@_N@1@$$QEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@Z; utl::_HashTable<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,UnionFs::UfsPathCachePayload::SidHash,UnionFs::UfsPathCachePayload::SidEqualsPred,utl::allocator<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>,0>::_InsertImpl<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>(wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &&)
0x1400416f1  cmp     [rbp+60h+var_D0], 0
0x1400416f6  jnz     short loc_14004174F
0x1400416f8  lea     rax, aOriginInsertin; "ORIGIN: Inserting callerSid"
0x1400416ff  mov     ebx, 0C000009Ah
0x140041704  mov     ecx, ebx; this
0x140041706  mov     [rsp+160h+var_140], rax; char *
0x14004170b  lea     r9, aUnionfsUfspath_64; "UnionFs::UfsPathCachePayload::CheckAndC"...
0x140041712  mov     r8, 246001201A5h; struct UnionFs::StackEventTracer *
0x14004171c  mov     rdx, rdi; int
0x14004171f  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140041724  mov     rcx, [rsp+160h+Resource]; Resource
0x140041729  test    rcx, rcx
0x14004172c  jz      loc_140041803
0x140041732  call    cs:__imp_ExReleaseResourceLite
0x140041739  nop     dword ptr [rax+rax+00h]
0x14004173e  call    cs:__imp_KeLeaveCriticalRegion
0x140041745  nop     dword ptr [rax+rax+00h]
0x14004174a  jmp     loc_140041803
0x14004174f  mov     rcx, [rsp+160h+Resource]; Resource
0x140041754  test    rcx, rcx
0x140041757  jz      short loc_140041771
0x140041759  call    cs:__imp_ExReleaseResourceLite
0x140041760  nop     dword ptr [rax+rax+00h]
0x140041765  call    cs:__imp_KeLeaveCriticalRegion
0x14004176c  nop     dword ptr [rax+rax+00h]
0x140041771  mov     eax, [rsi+58h]
0x140041774  xor     ecx, ecx
0x140041776  mov     rdx, [rsi+50h]
0x14004177a  mov     r9, r13
0x14004177d  mov     dword ptr [rsp+160h+var_F8+4], eax
0x140041781  mov     rax, [rsi+30h]
0x140041785  mov     qword ptr [rsp+160h+var_F8+8], rcx
0x14004178a  mov     qword ptr [rsp+160h+var_E8], rcx
0x14004178f  or      ecx, 1
0x140041792  mov     dword ptr [rsp+160h+var_F8], ecx
0x140041796  lea     rcx, [rbp+60h+var_C0]
0x14004179a  movups  xmm2, xmmword ptr [rax]
0x14004179d  mov     rax, [r13+10h]
0x1400417a1  movups  xmm0, [rsp+160h+var_F8]
0x1400417a6  mov     [rsp+160h+var_140], rdi
0x1400417ab  movups  xmmword ptr [rbp+60h+var_E8+8], xmm2
0x1400417af  mov     r8, [rax+18h]
0x1400417b3  movups  xmm1, xmmword ptr [rsp+160h+var_E8]
0x1400417b8  unpckhpd xmm2, xmm2
0x1400417bc  mov     r8d, [r8+10h]
0x1400417c0  movaps  [rbp+60h+var_C0], xmm0
0x1400417c4  movaps  [rbp+60h+var_B0], xmm1
0x1400417c8  movsd   [rbp+60h+var_A0], xmm2
0x1400417cd  call    ?AccessCheck@Utils@UnionFs@@YAJUAccessCheckParams@12@AEBU_SECURITY_DESCRIPTOR@@KAEAU_FLT_CALLBACK_DATA@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::AccessCheck(UnionFs::Utils::AccessCheckParams,_SECURITY_DESCRIPTOR const &,ulong,_FLT_CALLBACK_DATA &,UnionFs::StackEventTracer &)
0x1400417d2  mov     ebx, eax
0x1400417d4  test    eax, eax
0x1400417d6  jns     short loc_140041801
0x1400417d8  lea     rax, aPushAccesschec; "PUSH: AccessCheck"
0x1400417df  mov     r8, 244001201BAh; struct UnionFs::StackEventTracer *
0x1400417e9  lea     r9, aUnionfsUfspath_64; "UnionFs::UfsPathCachePayload::CheckAndC"...
0x1400417f0  mov     [rsp+160h+var_140], rax; char *
0x1400417f5  mov     rdx, rdi; int
0x1400417f8  mov     ecx, ebx; this
0x1400417fa  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400417ff  jmp     short loc_140041803
0x140041801  xor     ebx, ebx
0x140041803  lea     rcx, [rsp+160h+String]; UnicodeString
0x140041808  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14004180d  mov     eax, ebx
0x14004180f  mov     rcx, [rbp+60h+var_40]
0x140041813  xor     rcx, rsp; StackCookie
0x140041816  call    __security_check_cookie
0x14004181b  mov     rbx, [rsp+160h+arg_18]
0x140041823  add     rsp, 130h
0x14004182a  pop     r15
0x14004182c  pop     r14
0x14004182e  pop     r13
0x140041830  pop     r12
0x140041832  pop     rdi
0x140041833  pop     rsi
0x140041834  pop     rbp
0x140041835  retn
```
