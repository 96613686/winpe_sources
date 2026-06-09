# UnionFs::UfsPathCachePayload::CheckAndCacheCallerAccess(_FLT_CALLBACK_DATA &,UnionFs::StackEventTracer &,bool)

- ea: `0x140041650`
- end: `0x1400419bf`
- name: `?CheckAndCacheCallerAccess@UfsPathCachePayload@UnionFs@@QEAAJAEAU_FLT_CALLBACK_DATA@@AEAVStackEventTracer@2@_N@Z`
- size: `879`
- prototype: `int(UnionFs::UfsPathCachePayload *__hidden this, struct _FLT_CALLBACK_DATA *, struct UnionFs::StackEventTracer *, bool)`
- caller_count: `3`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140013b60`
- `0x14001568c`
- `0x14005913c`

## callees

- `0x14000f81c`
- `0x14003f41c`
- `0x140041650`
- `0x140056c44`
- `0x140056c7c`
- `0x140068960`
- `0x14007018c`
- `0x1400782bc`
- `0x140079d8c`
- `0x140079dd4`
- `0x140079f68`
- `0x14007b2b0`
- `0x14007baf0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!RtlHashUnicodeString` at `0x1400416f7`
- `ntoskrnl!RtlHashUnicodeString` at `0x1400416f7`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140041758`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140041758`
- `ntoskrnl!PsGetHostSilo` at `0x1400417b1`
- `ntoskrnl!PsGetHostSilo` at `0x1400417b1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004178a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400418ba`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400418e1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004178a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400418ba`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400418e1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140041796`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400418c6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400418ed`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140041796`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400418c6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400418ed`

## string_xrefs

- `0x1400416a6`: `PUSH: GetUserSidString`
- `0x14004182b`: `UnionFs::UfsPathCachePayload::CheckAndCacheCallerAccess`
- `0x140041893`: `UnionFs::UfsPathCachePayload::CheckAndCacheCallerAccess`
- `0x140041971`: `UnionFs::UfsPathCachePayload::CheckAndCacheCallerAccess`
- `0x140041880`: `ORIGIN: Inserting callerSid`
- `0x140041960`: `PUSH: AccessCheck`

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
    v10 = 0x2430012019ALL;
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
  FsFltWil::AcquireResourceShared(Resource, *((_QWORD *)this + 18) + 80LL);
  if ( *((_QWORD *)this + 15) )
  {
    HashValue = 0;
    if ( RtlHashUnicodeString(&String, 1u, 0, &HashValue) < 0 )
      MicrosoftTelemetryAssertTriggeredMsgKM("RtlHashUnicodeString error?!");
    v11 = HashValue;
    v12 = *((_QWORD *)this + 15);
    v13 = *(__int64 **)(v12 + 16 * (HashValue & (unsigned __int64)((8LL << *((_BYTE *)this + 136)) - 1)));
    if ( v13 )
    {
      v14 = **(__int64 ***)(v12 + 16 * (HashValue & (unsigned __int64)((8LL << *((_BYTE *)this + 136)) - 1)) + 8);
      while ( v13 != v14 )
      {
        if ( v13[2] >= v11 )
        {
          if ( v13[2] > v11 )
            break;
          if ( RtlEqualUnicodeString(&String, (PCUNICODE_STRING)(v13 + 3), 1u) )
          {
            if ( v13 != (__int64 *)((char *)this + 104) )
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
      (struct UnionFs::StackEventTracer *)0x245001201B0LL,
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
    v10 = 0x244001201D3LL;
    goto LABEL_32;
  }
  FsFltWil::AcquireResourceExclusive(Resource, *((_QWORD *)this + 18) + 80LL);
  utl::_HashTable<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,UnionFs::UfsPathCachePayload::SidHash,UnionFs::UfsPathCachePayload::SidEqualsPred,utl::allocator<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>,0>::_InsertImpl<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>(
    (char *)this + 104,
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
    (struct UnionFs::StackEventTracer *)0x246001201BELL,
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
0x140041650  mov     [rsp-8+arg_18], rbx
0x140041655  push    rbp
0x140041656  push    rsi
0x140041657  push    rdi
0x140041658  push    r12
0x14004165a  push    r13
0x14004165c  push    r14
0x14004165e  push    r15
0x140041660  lea     rbp, [rsp-30h]
0x140041665  sub     rsp, 130h
0x14004166c  mov     rax, cs:__security_cookie
0x140041673  xor     rax, rsp
0x140041676  mov     [rbp+60h+var_40], rax
0x14004167a  mov     r13, rdx
0x14004167d  mov     [rsp+160h+var_120], r9b
0x140041682  mov     rsi, rcx
0x140041685  lea     rdx, [rsp+160h+String]
0x14004168a  xorps   xmm0, xmm0
0x14004168d  mov     rcx, r13
0x140041690  mov     r12b, r9b
0x140041693  mov     rdi, r8
0x140041696  movups  xmmword ptr [rsp+160h+String.Length], xmm0
0x14004169b  call    ?GetUserSidString@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetUserSidString(_FLT_CALLBACK_DATA const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)
0x1400416a0  mov     ebx, eax
0x1400416a2  test    eax, eax
0x1400416a4  jns     short loc_1400416BC
0x1400416a6  lea     rax, aPushGetusersid; "PUSH: GetUserSidString"
0x1400416ad  mov     r8, 2430012019Ah
0x1400416b7  jmp     loc_140041971
0x1400416bc  mov     rdx, [rsi+90h]
0x1400416c3  lea     rcx, [rsp+160h+Resource]
0x1400416c8  add     rdx, 50h ; 'P'
0x1400416cc  call    ?AcquireResourceShared@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceShared(_ERESOURCE &)
0x1400416d1  lea     r15, [rsi+68h]
0x1400416d5  cmp     qword ptr [r15+10h], 0
0x1400416da  jz      loc_140041780
0x1400416e0  lea     r9, [rsp+160h+HashValue]; HashValue
0x1400416e5  mov     [rsp+160h+HashValue], 0
0x1400416ed  xor     r8d, r8d; HashAlgorithm
0x1400416f0  lea     rcx, [rsp+160h+String]; String
0x1400416f5  mov     dl, 1; CaseInSensitive
0x1400416f7  call    cs:__imp_RtlHashUnicodeString
0x1400416fe  nop     dword ptr [rax+rax+00h]
0x140041703  test    eax, eax
0x140041705  jns     short loc_140041713
0x140041707  lea     rcx, aRtlhashunicode; "RtlHashUnicodeString error?!"
0x14004170e  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140041713  mov     cl, [r15+20h]
0x140041717  mov     eax, 8
0x14004171c  mov     r14d, [rsp+160h+HashValue]
0x140041721  shl     rax, cl
0x140041724  mov     rcx, [r15+10h]
0x140041728  dec     rax
0x14004172b  and     rax, r14
0x14004172e  add     rax, rax
0x140041731  mov     rbx, [rcx+rax*8]
0x140041735  test    rbx, rbx
0x140041738  jz      short loc_140041780
0x14004173a  mov     rax, [rcx+rax*8+8]
0x14004173f  mov     r12, [rax]
0x140041742  jmp     short loc_14004176B
0x140041744  cmp     [rbx+10h], r14
0x140041748  jb      short loc_140041768
0x14004174a  ja      short loc_14004177B
0x14004174c  lea     rdx, [rbx+18h]; String2
0x140041750  mov     r8b, 1; CaseInSensitive
0x140041753  lea     rcx, [rsp+160h+String]; String1
0x140041758  call    cs:__imp_RtlEqualUnicodeString
0x14004175f  nop     dword ptr [rax+rax+00h]
0x140041764  test    al, al
0x140041766  jnz     short loc_140041772
0x140041768  mov     rbx, [rbx]
0x14004176b  cmp     rbx, r12
0x14004176e  jnz     short loc_140041744
0x140041770  jmp     short loc_14004177B
0x140041772  cmp     rbx, r15
0x140041775  jnz     loc_1400418D7
0x14004177b  mov     r12b, [rsp+160h+var_120]
0x140041780  mov     rcx, [rsp+160h+Resource]; Resource
0x140041785  test    rcx, rcx
0x140041788  jz      short loc_1400417A2
0x14004178a  call    cs:__imp_ExReleaseResourceLite
0x140041791  nop     dword ptr [rax+rax+00h]
0x140041796  call    cs:__imp_KeLeaveCriticalRegion
0x14004179d  nop     dword ptr [rax+rax+00h]
0x1400417a2  xor     edx, edx; Val
0x1400417a4  lea     rcx, [rbp+60h+var_90]; void *
0x1400417a8  lea     r8d, [rdx+48h]; Size
0x1400417ac  call    memset
0x1400417b1  call    cs:__imp_PsGetHostSilo
0x1400417b8  nop     dword ptr [rax+rax+00h]
0x1400417bd  mov     rbx, [rsi+28h]
0x1400417c1  mov     rcx, [rsi+20h]
0x1400417c5  test    rbx, rbx
0x1400417c8  jz      short loc_1400417CE
0x1400417ca  lock inc dword ptr [rbx+8]
0x1400417ce  mov     rcx, [rcx+8]
0x1400417d2  xor     r9d, r9d
0x1400417d5  mov     [rsp+160h+var_130], rdi
0x1400417da  mov     r8, rax
0x1400417dd  mov     [rsp+160h+var_138], r13; char *
0x1400417e2  mov     rdx, [rcx]
0x1400417e5  mov     rcx, [rsi+30h]
0x1400417e9  movups  xmm0, xmmword ptr [rcx]
0x1400417ec  lea     rcx, [rbp+60h+var_90]
0x1400417f0  mov     [rsp+160h+var_140], rcx
0x1400417f5  lea     rcx, [rsp+160h+Resource]
0x1400417fa  movdqu  xmmword ptr [rsp+160h+Resource], xmm0
0x140041800  call    ?StatItemAsCaller@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBU_FLT_INSTANCE@@AEBU_EJOB@@W4StatItemFlags@12@PEAU_FILE_STAT_INFORMATION@@AEAU_FLT_CALLBACK_DATA@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::StatItemAsCaller(_UNICODE_STRING const &,_FLT_INSTANCE const &,_EJOB const &,UnionFs::Utils::StatItemFlags,_FILE_STAT_INFORMATION *,_FLT_CALLBACK_DATA &,UnionFs::StackEventTracer &)
0x140041805  mov     r14d, eax
0x140041808  test    rbx, rbx
0x14004180b  jz      short loc_140041815
0x14004180d  mov     rcx, rbx; this
0x140041810  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140041815  test    r14d, r14d
0x140041818  jns     short loc_14004184A
0x14004181a  lea     rax, aPushStatLayerI; "PUSH: Stat layer item"
0x140041821  mov     r8, 245001201B0h; struct UnionFs::StackEventTracer *
0x14004182b  lea     r9, aUnionfsUfspath_64; "UnionFs::UfsPathCachePayload::CheckAndC"...
0x140041832  mov     [rsp+160h+var_140], rax; char *
0x140041837  mov     rdx, rdi; int
0x14004183a  mov     ecx, r14d; this
0x14004183d  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140041842  mov     ebx, r14d
0x140041845  jmp     loc_14004198B
0x14004184a  test    r12b, r12b
0x14004184d  jnz     loc_1400418F9
0x140041853  mov     rdx, [rsi+90h]
0x14004185a  lea     rcx, [rsp+160h+Resource]
0x14004185f  add     rdx, 50h ; 'P'
0x140041863  call    ?AcquireResourceExclusive@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceExclusive(_ERESOURCE &)
0x140041868  lea     r8, [rsp+160h+String]
0x14004186d  mov     rcx, r15
0x140041870  lea     rdx, [rbp+60h+var_D0]
0x140041874  call    ??$_InsertImpl@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@?$_HashTable@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@V12@USidHash@UfsPathCachePayload@UnionFs@@USidEqualsPred@45@V?$allocator@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@utl@@$0A@@utl@@AEAA?AU?$pair@V?$_DlistConstIt@U?$_HashNode@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@utl@@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@utl@@_N@1@$$QEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@Z; utl::_HashTable<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,UnionFs::UfsPathCachePayload::SidHash,UnionFs::UfsPathCachePayload::SidEqualsPred,utl::allocator<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>,0>::_InsertImpl<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>(wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &&)
0x140041879  cmp     [rbp+60h+var_D0], 0
0x14004187e  jnz     short loc_1400418D7
0x140041880  lea     rax, aOriginInsertin; "ORIGIN: Inserting callerSid"
0x140041887  mov     ebx, 0C000009Ah
0x14004188c  mov     ecx, ebx; this
0x14004188e  mov     [rsp+160h+var_140], rax; char *
0x140041893  lea     r9, aUnionfsUfspath_64; "UnionFs::UfsPathCachePayload::CheckAndC"...
0x14004189a  mov     r8, 246001201BEh; struct UnionFs::StackEventTracer *
0x1400418a4  mov     rdx, rdi; int
0x1400418a7  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400418ac  mov     rcx, [rsp+160h+Resource]; Resource
0x1400418b1  test    rcx, rcx
0x1400418b4  jz      loc_14004198B
0x1400418ba  call    cs:__imp_ExReleaseResourceLite
0x1400418c1  nop     dword ptr [rax+rax+00h]
0x1400418c6  call    cs:__imp_KeLeaveCriticalRegion
0x1400418cd  nop     dword ptr [rax+rax+00h]
0x1400418d2  jmp     loc_14004198B
0x1400418d7  mov     rcx, [rsp+160h+Resource]; Resource
0x1400418dc  test    rcx, rcx
0x1400418df  jz      short loc_1400418F9
0x1400418e1  call    cs:__imp_ExReleaseResourceLite
0x1400418e8  nop     dword ptr [rax+rax+00h]
0x1400418ed  call    cs:__imp_KeLeaveCriticalRegion
0x1400418f4  nop     dword ptr [rax+rax+00h]
0x1400418f9  mov     eax, [rsi+58h]
0x1400418fc  xor     ecx, ecx
0x1400418fe  mov     rdx, [rsi+50h]
0x140041902  mov     r9, r13
0x140041905  mov     dword ptr [rsp+160h+var_F8+4], eax
0x140041909  mov     rax, [rsi+30h]
0x14004190d  mov     qword ptr [rsp+160h+var_F8+8], rcx
0x140041912  mov     qword ptr [rsp+160h+var_E8], rcx
0x140041917  or      ecx, 1
0x14004191a  mov     dword ptr [rsp+160h+var_F8], ecx
0x14004191e  lea     rcx, [rbp+60h+var_C0]
0x140041922  movups  xmm2, xmmword ptr [rax]
0x140041925  mov     rax, [r13+10h]
0x140041929  movups  xmm0, [rsp+160h+var_F8]
0x14004192e  mov     [rsp+160h+var_140], rdi
0x140041933  movups  xmmword ptr [rbp+60h+var_E8+8], xmm2
0x140041937  mov     r8, [rax+18h]
0x14004193b  movups  xmm1, xmmword ptr [rsp+160h+var_E8]
0x140041940  unpckhpd xmm2, xmm2
0x140041944  mov     r8d, [r8+10h]
0x140041948  movaps  [rbp+60h+var_C0], xmm0
0x14004194c  movaps  [rbp+60h+var_B0], xmm1
0x140041950  movsd   [rbp+60h+var_A0], xmm2
0x140041955  call    ?AccessCheck@Utils@UnionFs@@YAJUAccessCheckParams@12@AEBU_SECURITY_DESCRIPTOR@@KAEAU_FLT_CALLBACK_DATA@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::AccessCheck(UnionFs::Utils::AccessCheckParams,_SECURITY_DESCRIPTOR const &,ulong,_FLT_CALLBACK_DATA &,UnionFs::StackEventTracer &)
0x14004195a  mov     ebx, eax
0x14004195c  test    eax, eax
0x14004195e  jns     short loc_140041989
0x140041960  lea     rax, aPushAccesschec; "PUSH: AccessCheck"
0x140041967  mov     r8, 244001201D3h; struct UnionFs::StackEventTracer *
0x140041971  lea     r9, aUnionfsUfspath_64; "UnionFs::UfsPathCachePayload::CheckAndC"...
0x140041978  mov     [rsp+160h+var_140], rax; char *
0x14004197d  mov     rdx, rdi; int
0x140041980  mov     ecx, ebx; this
0x140041982  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140041987  jmp     short loc_14004198B
0x140041989  xor     ebx, ebx
0x14004198b  lea     rcx, [rsp+160h+String]; UnicodeString
0x140041990  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140041995  mov     eax, ebx
0x140041997  mov     rcx, [rbp+60h+var_40]
0x14004199b  xor     rcx, rsp; StackCookie
0x14004199e  call    __security_check_cookie
0x1400419a3  mov     rbx, [rsp+160h+arg_18]
0x1400419ab  add     rsp, 130h
0x1400419b2  pop     r15
0x1400419b4  pop     r14
0x1400419b6  pop     r13
0x1400419b8  pop     r12
0x1400419ba  pop     rdi
0x1400419bb  pop     rsi
0x1400419bc  pop     rbp
0x1400419bd  retn
```
