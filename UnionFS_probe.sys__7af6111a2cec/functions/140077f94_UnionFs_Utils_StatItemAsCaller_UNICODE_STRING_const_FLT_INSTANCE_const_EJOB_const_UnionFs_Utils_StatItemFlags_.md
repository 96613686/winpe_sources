# UnionFs::Utils::StatItemAsCaller(_UNICODE_STRING const &,_FLT_INSTANCE const &,_EJOB const &,UnionFs::Utils::StatItemFlags,_FILE_STAT_INFORMATION *,_FLT_CALLBACK_DATA &,UnionFs::StackEventTracer &)

- ea: `0x140077f94`
- end: `0x1400782fb`
- name: `?StatItemAsCaller@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBU_FLT_INSTANCE@@AEBU_EJOB@@W4StatItemFlags@12@PEAU_FILE_STAT_INFORMATION@@AEAU_FLT_CALLBACK_DATA@@AEAVStackEventTracer@2@@Z`
- size: `871`
- prototype: ``
- caller_count: `6`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x140017370`
- `0x14001834c`
- `0x140019438`
- `0x1400414c8`
- `0x14006117c`
- `0x140078304`

## callees

- `0x140056a88`
- `0x140056ac4`
- `0x140056afc`
- `0x140067aa8`
- `0x14006f108`
- `0x140077774`
- `0x140077f94`
- `0x14007b7d0`
- `0x14007bc00`

## import_xrefs

- `ntoskrnl!SeImpersonateClientEx` at `0x14007819b`
- `ntoskrnl!SeImpersonateClientEx` at `0x14007819b`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14007806e`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x14007806e`
- `ntoskrnl!SeCreateClientSecurityFromSubjectContext` at `0x1400780e8`
- `ntoskrnl!SeCreateClientSecurityFromSubjectContext` at `0x1400780e8`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x14007824b`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x14007824b`
- `ntoskrnl!ObfDereferenceObject` at `0x140078087`
- `ntoskrnl!ObfDereferenceObject` at `0x140078164`
- `ntoskrnl!ObfDereferenceObject` at `0x1400782cc`
- `ntoskrnl!ObfDereferenceObject` at `0x140078087`
- `ntoskrnl!ObfDereferenceObject` at `0x140078164`
- `ntoskrnl!ObfDereferenceObject` at `0x1400782cc`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14007814e`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140078189`
- `ntoskrnl!SeUnlockSubjectContext` at `0x14007814e`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140078189`
- `ntoskrnl!SeDeleteClientSecurity` at `0x140078133`
- `ntoskrnl!SeDeleteClientSecurity` at `0x1400781e7`
- `ntoskrnl!SeDeleteClientSecurity` at `0x140078207`
- `ntoskrnl!SeDeleteClientSecurity` at `0x140078133`
- `ntoskrnl!SeDeleteClientSecurity` at `0x1400781e7`
- `ntoskrnl!SeDeleteClientSecurity` at `0x140078207`
- `ntoskrnl!SeLockSubjectContext` at `0x1400780bf`
- `ntoskrnl!SeLockSubjectContext` at `0x1400780bf`

## string_xrefs

- `0x1400780fb`: `API: Creating security client context`
- `0x1400781ad`: `API: Impersonating client`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::StatItemAsCaller(
        const char *a1,
        __int64 a2,
        unsigned int *a3,
        int a4,
        __int64 a5,
        UnionFs::Utils *a6,
        int a7)
{
  NTSTATUS v9; // ebx
  bool v10; // zf
  char *v11; // rdi
  PACCESS_TOKEN v12; // rbx
  __int64 v13; // rax
  struct _SECURITY_SUBJECT_CONTEXT *v14; // rbx
  NTSTATUS ClientSecurityFromSubjectContext; // r14d
  __int64 v17; // rcx
  struct _FILE_OBJECT *v18; // rcx
  char *v19; // [rsp+28h] [rbp-C9h]
  char *v20; // [rsp+28h] [rbp-C9h]
  const struct _UNICODE_STRING *v21; // [rsp+30h] [rbp-C1h]
  char v22; // [rsp+50h] [rbp-A1h] BYREF
  unsigned __int8 CopyOnOpen; // [rsp+51h] [rbp-A0h] BYREF
  unsigned __int8 EffectiveOnly[6]; // [rsp+52h] [rbp-9Fh] BYREF
  PVOID Object; // [rsp+58h] [rbp-99h] BYREF
  enum _SECURITY_IMPERSONATION_LEVEL ImpersonationLevel; // [rsp+60h] [rbp-91h] BYREF
  _BYTE v27[116]; // [rsp+64h] [rbp-8Dh] BYREF

  *(_DWORD *)&v27[4] = a4;
  *(_QWORD *)&v27[20] = a3;
  *(_QWORD *)&v27[12] = a5;
  *(_DWORD *)v27 = 0;
  if ( !UnionFs::Utils::GetObjectAttributesFlags(a6, (const struct _FLT_CALLBACK_DATA *)v27, a3) )
  {
    v9 = -1073741808;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0000010LL,
      a7,
      (struct UnionFs::StackEventTracer *)0xF300210A08LL,
      (unsigned __int64)"UnionFs::Utils::StatItemAsCaller",
      "ORIGIN: Getting attribute flags",
      v19);
    return (unsigned int)v9;
  }
  v10 = *((_BYTE *)a6 + 80) == 1;
  v11 = (char *)a6 + 16;
  v22 = 0;
  Object = 0;
  CopyOnOpen = 0;
  EffectiveOnly[0] = 0;
  ImpersonationLevel = SecurityAnonymous;
  if ( !v10 && (*(_BYTE *)(*(_QWORD *)v11 + 6LL) & 1) == 0 )
    goto LABEL_24;
  v12 = PsReferenceImpersonationToken(KeGetCurrentThread(), &CopyOnOpen, EffectiveOnly, &ImpersonationLevel);
  if ( Object )
    ObfDereferenceObject(Object);
  v13 = *(_QWORD *)v11;
  Object = v12;
  *(_DWORD *)&v27[28] = 12;
  *(_QWORD *)&v27[32] = 0x100000002LL;
  v14 = (struct _SECURITY_SUBJECT_CONTEXT *)(*(_QWORD *)(*(_QWORD *)(v13 + 24) + 8LL) + 32LL);
  SeLockSubjectContext(v14);
  memset(&v27[44], 0, 0x48u);
  ClientSecurityFromSubjectContext = SeCreateClientSecurityFromSubjectContext(
                                       v14,
                                       (PSECURITY_QUALITY_OF_SERVICE)&v27[28],
                                       0,
                                       (PSECURITY_CLIENT_CONTEXT)&v27[44]);
  if ( ClientSecurityFromSubjectContext >= 0 )
  {
    if ( v14 && v14->PrimaryToken )
      SeUnlockSubjectContext(v14);
    v9 = SeImpersonateClientEx((PSECURITY_CLIENT_CONTEXT)&v27[44], 0);
    if ( v9 < 0 )
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)v9,
        a7,
        (struct UnionFs::StackEventTracer *)0xEF00210A32LL,
        (unsigned __int64)"UnionFs::Utils::StatItemAsCaller",
        "API: Impersonating client",
        a1,
        v21);
      if ( *(_QWORD *)&v27[60] )
        SeDeleteClientSecurity(&v27[44]);
LABEL_27:
      if ( Object )
        ObfDereferenceObject(Object);
      return (unsigned int)v9;
    }
    v22 = 1;
    if ( *(_QWORD *)&v27[60] )
      SeDeleteClientSecurity(&v27[44]);
LABEL_24:
    v17 = *(_QWORD *)v11;
    *(_QWORD *)&v27[44] = &v22;
    *(_QWORD *)&v27[52] = &Object;
    *(_QWORD *)&v27[60] = &CopyOnOpen;
    v18 = *(struct _FILE_OBJECT **)(v17 + 8);
    *(_QWORD *)&v27[68] = EffectiveOnly;
    *(_QWORD *)&v27[76] = &ImpersonationLevel;
    v27[84] = 1;
    IoGetTransactionParameterBlock(v18);
    v20 = *(char **)&v27[12];
    v9 = UnionFs::Utils::StatItem(a1, a2, *(unsigned int *)v27, *(_QWORD *)&v27[20], *(_DWORD *)&v27[4]);
    if ( v9 < 0 )
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)v9,
        a7,
        (struct UnionFs::StackEventTracer *)0x25B00210A52LL,
        (unsigned __int64)"UnionFs::Utils::StatItemAsCaller",
        "PUSH: StatItem",
        v20);
    wil::details::lambda_call__lambda_14d80e2c71013e3ae3fbb1e0a5e2b745___::_lambda_call__lambda_14d80e2c71013e3ae3fbb1e0a5e2b745___(&v27[44]);
    goto LABEL_27;
  }
  UnionFs::ProcessTraceStatusFromApi(
    (UnionFs *)(unsigned int)ClientSecurityFromSubjectContext,
    a7,
    (struct UnionFs::StackEventTracer *)0xEE00210A29LL,
    (unsigned __int64)"UnionFs::Utils::StatItemAsCaller",
    "API: Creating security client context",
    a1,
    v21);
  if ( *(_QWORD *)&v27[60] )
    SeDeleteClientSecurity(&v27[44]);
  if ( v14 && v14->PrimaryToken )
    SeUnlockSubjectContext(v14);
  if ( Object )
    ObfDereferenceObject(Object);
  return (unsigned int)ClientSecurityFromSubjectContext;
}

```

## disassembly

```asm
0x140077f94  push    rbp
0x140077f96  push    rbx
0x140077f97  push    rsi
0x140077f98  push    rdi
0x140077f99  push    r12
0x140077f9b  push    r13
0x140077f9d  push    r14
0x140077f9f  push    r15
0x140077fa1  lea     rbp, [rsp-7]
0x140077fa6  sub     rsp, 0F8h
0x140077fad  mov     rax, cs:__security_cookie
0x140077fb4  xor     rax, rsp
0x140077fb7  mov     [rbp+3Fh+var_50], rax
0x140077fbb  mov     rax, [rbp+3Fh+arg_20]
0x140077fbf  mov     r13, rdx
0x140077fc2  mov     r15, [rbp+3Fh+arg_28]
0x140077fc6  lea     rdx, [rsp+130h+var_CC]; struct _FLT_CALLBACK_DATA *
0x140077fcb  mov     rsi, qword ptr [rbp+3Fh+arg_30]
0x140077fcf  mov     r12, rcx
0x140077fd2  xor     r14d, r14d
0x140077fd5  mov     dword ptr [rsp+130h+var_CC+4], r9d
0x140077fda  mov     rcx, r15; this
0x140077fdd  mov     qword ptr [rbp+3Fh+var_CC+14h], r8
0x140077fe1  mov     qword ptr [rsp+130h+var_CC+0Ch], rax
0x140077fe6  mov     dword ptr [rsp+130h+var_CC], r14d
0x140077feb  call    ?GetObjectAttributesFlags@Utils@UnionFs@@YA_NAEBU_FLT_CALLBACK_DATA@@PEAK@Z; UnionFs::Utils::GetObjectAttributesFlags(_FLT_CALLBACK_DATA const &,ulong *)
0x140077ff0  test    al, al
0x140077ff2  jnz     short loc_140078025
0x140077ff4  lea     rax, aOriginGettingA; "ORIGIN: Getting attribute flags"
0x140077ffb  mov     ebx, 0C0000010h
0x140078000  mov     ecx, ebx; this
0x140078002  mov     [rsp+130h+var_110], rax; char *
0x140078007  lea     r9, aUnionfsUtilsSt_0; "UnionFs::Utils::StatItemAsCaller"
0x14007800e  mov     r8, 0F300210A08h; struct UnionFs::StackEventTracer *
0x140078018  mov     rdx, rsi; int
0x14007801b  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140078020  jmp     loc_1400782D8
0x140078025  cmp     byte ptr [r15+50h], 1
0x14007802a  lea     rdi, [r15+10h]
0x14007802e  mov     [rsp+130h+var_E0], r14b
0x140078033  mov     [rsp+130h+Object], r14
0x140078038  mov     [rsp+130h+CopyOnOpen], r14b
0x14007803d  mov     [rsp+130h+EffectiveOnly], r14b
0x140078042  mov     [rsp+130h+ImpersonationLevel], r14d
0x140078047  jz      short loc_140078056
0x140078049  mov     rax, [rdi]
0x14007804c  test    byte ptr [rax+6], 1
0x140078050  jz      loc_140078213
0x140078056  mov     rcx, gs:188h; Thread
0x14007805f  lea     r9, [rsp+130h+ImpersonationLevel]; ImpersonationLevel
0x140078064  lea     r8, [rsp+130h+EffectiveOnly]; EffectiveOnly
0x140078069  lea     rdx, [rsp+130h+CopyOnOpen]; CopyOnOpen
0x14007806e  call    cs:__imp_PsReferenceImpersonationToken
0x140078075  nop     dword ptr [rax+rax+00h]
0x14007807a  mov     rcx, [rsp+130h+Object]; Object
0x14007807f  mov     rbx, rax
0x140078082  test    rcx, rcx
0x140078085  jz      short loc_140078093
0x140078087  call    cs:__imp_ObfDereferenceObject
0x14007808e  nop     dword ptr [rax+rax+00h]
0x140078093  mov     rax, [rdi]
0x140078096  mov     [rsp+130h+Object], rbx
0x14007809b  mov     dword ptr [rbp+3Fh+var_CC+24h], 1
0x1400780a2  mov     dword ptr [rbp+3Fh+var_CC+1Ch], 0Ch
0x1400780a9  mov     dword ptr [rbp+3Fh+var_CC+20h], 2
0x1400780b0  mov     rcx, [rax+18h]
0x1400780b4  mov     rbx, [rcx+8]
0x1400780b8  add     rbx, 20h ; ' '
0x1400780bc  mov     rcx, rbx; SubjectContext
0x1400780bf  call    cs:__imp_SeLockSubjectContext
0x1400780c6  nop     dword ptr [rax+rax+00h]
0x1400780cb  xor     edx, edx; Val
0x1400780cd  lea     rcx, [rbp+3Fh+var_CC+2Ch]; void *
0x1400780d1  lea     r8d, [rdx+48h]; Size
0x1400780d5  call    memset
0x1400780da  lea     r9, [rbp+3Fh+var_CC+2Ch]; ClientContext
0x1400780de  xor     r8d, r8d; ServerIsRemote
0x1400780e1  lea     rdx, [rbp+3Fh+var_CC+1Ch]; ClientSecurityQos
0x1400780e5  mov     rcx, rbx; SubjectContext
0x1400780e8  call    cs:__imp_SeCreateClientSecurityFromSubjectContext
0x1400780ef  nop     dword ptr [rax+rax+00h]
0x1400780f4  mov     r14d, eax
0x1400780f7  test    eax, eax
0x1400780f9  jns     short loc_140078178
0x1400780fb  lea     rax, aApiCreatingSec; "API: Creating security client context"
0x140078102  mov     [rsp+130h+var_108], r12; char *
0x140078107  lea     r9, aUnionfsUtilsSt_0; "UnionFs::Utils::StatItemAsCaller"
0x14007810e  mov     [rsp+130h+var_110], rax; char *
0x140078113  mov     r8, 0EE00210A29h; struct UnionFs::StackEventTracer *
0x14007811d  mov     rdx, rsi; int
0x140078120  mov     ecx, r14d; this
0x140078123  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2AEBU_UNICODE_STRING@@@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *,_UNICODE_STRING const &)
0x140078128  cmp     qword ptr [rbp+3Fh+var_CC+3Ch], 0
0x14007812d  jz      short loc_14007813F
0x14007812f  lea     rcx, [rbp+3Fh+var_CC+2Ch]
0x140078133  call    cs:__imp_SeDeleteClientSecurity
0x14007813a  nop     dword ptr [rax+rax+00h]
0x14007813f  test    rbx, rbx
0x140078142  jz      short loc_14007815A
0x140078144  cmp     qword ptr [rbx+10h], 0
0x140078149  jz      short loc_14007815A
0x14007814b  mov     rcx, rbx; SubjectContext
0x14007814e  call    cs:__imp_SeUnlockSubjectContext
0x140078155  nop     dword ptr [rax+rax+00h]
0x14007815a  mov     rcx, [rsp+130h+Object]; Object
0x14007815f  test    rcx, rcx
0x140078162  jz      short loc_140078170
0x140078164  call    cs:__imp_ObfDereferenceObject
0x14007816b  nop     dword ptr [rax+rax+00h]
0x140078170  mov     eax, r14d
0x140078173  jmp     loc_1400782DA
0x140078178  xor     r14d, r14d
0x14007817b  test    rbx, rbx
0x14007817e  jz      short loc_140078195
0x140078180  cmp     [rbx+10h], r14
0x140078184  jz      short loc_140078195
0x140078186  mov     rcx, rbx; SubjectContext
0x140078189  call    cs:__imp_SeUnlockSubjectContext
0x140078190  nop     dword ptr [rax+rax+00h]
0x140078195  xor     edx, edx; ServerThread
0x140078197  lea     rcx, [rbp+3Fh+var_CC+2Ch]; ClientContext
0x14007819b  call    cs:__imp_SeImpersonateClientEx
0x1400781a2  nop     dword ptr [rax+rax+00h]
0x1400781a7  mov     ebx, eax
0x1400781a9  test    eax, eax
0x1400781ab  jns     short loc_1400781F8
0x1400781ad  lea     rax, aApiImpersonati; "API: Impersonating client"
0x1400781b4  mov     [rsp+130h+var_108], r12; char *
0x1400781b9  lea     r9, aUnionfsUtilsSt_0; "UnionFs::Utils::StatItemAsCaller"
0x1400781c0  mov     [rsp+130h+var_110], rax; char *
0x1400781c5  mov     r8, 0EF00210A32h; struct UnionFs::StackEventTracer *
0x1400781cf  mov     rdx, rsi; int
0x1400781d2  mov     ecx, ebx; this
0x1400781d4  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2AEBU_UNICODE_STRING@@@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *,_UNICODE_STRING const &)
0x1400781d9  cmp     qword ptr [rbp+3Fh+var_CC+3Ch], r14
0x1400781dd  jz      loc_1400782C2
0x1400781e3  lea     rcx, [rbp+3Fh+var_CC+2Ch]
0x1400781e7  call    cs:__imp_SeDeleteClientSecurity
0x1400781ee  nop     dword ptr [rax+rax+00h]
0x1400781f3  jmp     loc_1400782C2
0x1400781f8  mov     [rsp+130h+var_E0], 1
0x1400781fd  cmp     qword ptr [rbp+3Fh+var_CC+3Ch], r14
0x140078201  jz      short loc_140078213
0x140078203  lea     rcx, [rbp+3Fh+var_CC+2Ch]
0x140078207  call    cs:__imp_SeDeleteClientSecurity
0x14007820e  nop     dword ptr [rax+rax+00h]
0x140078213  mov     rcx, [rdi]
0x140078216  lea     rax, [rsp+130h+var_E0]
0x14007821b  mov     qword ptr [rbp+3Fh+var_CC+2Ch], rax
0x14007821f  lea     rax, [rsp+130h+Object]
0x140078224  mov     qword ptr [rbp+3Fh+var_CC+34h], rax
0x140078228  lea     rax, [rsp+130h+CopyOnOpen]
0x14007822d  mov     qword ptr [rbp+3Fh+var_CC+3Ch], rax
0x140078231  lea     rax, [rsp+130h+EffectiveOnly]
0x140078236  mov     rcx, [rcx+8]; FileObject
0x14007823a  mov     qword ptr [rbp+3Fh+var_CC+44h], rax
0x14007823e  lea     rax, [rsp+130h+ImpersonationLevel]
0x140078243  mov     qword ptr [rbp+3Fh+var_CC+4Ch], rax
0x140078247  mov     [rbp+3Fh+var_CC+54h], 1
0x14007824b  call    cs:__imp_IoGetTransactionParameterBlock
0x140078252  nop     dword ptr [rax+rax+00h]
0x140078257  mov     r9, qword ptr [rbp+3Fh+var_CC+14h]
0x14007825b  mov     rdx, r13
0x14007825e  mov     r8d, dword ptr [rsp+130h+var_CC]
0x140078263  mov     rcx, r12
0x140078266  mov     [rsp+130h+var_F0], r15
0x14007826b  mov     [rsp+130h+var_F8], rax
0x140078270  mov     rax, qword ptr [rsp+130h+var_CC+0Ch]
0x140078275  mov     [rsp+130h+var_100], rsi
0x14007827a  mov     [rsp+130h+var_108], rax; char *
0x14007827f  mov     eax, dword ptr [rsp+130h+var_CC+4]
0x140078283  mov     dword ptr [rsp+130h+var_110], eax
0x140078287  call    ?StatItem@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBU_FLT_INSTANCE@@KAEBU_EJOB@@W4StatItemFlags@12@PEAU_FILE_STAT_INFORMATION@@AEAVStackEventTracer@2@QEAU_TXN_PARAMETER_BLOCK@@PEAU_FLT_CALLBACK_DATA@@@Z; UnionFs::Utils::StatItem(_UNICODE_STRING const &,_FLT_INSTANCE const &,ulong,_EJOB const &,UnionFs::Utils::StatItemFlags,_FILE_STAT_INFORMATION *,UnionFs::StackEventTracer &,_TXN_PARAMETER_BLOCK * const,_FLT_CALLBACK_DATA *)
0x14007828c  mov     ebx, eax
0x14007828e  test    eax, eax
0x140078290  jns     short loc_1400782B9
0x140078292  lea     rax, aPushStatitem; "PUSH: StatItem"
0x140078299  mov     r8, 25B00210A52h; struct UnionFs::StackEventTracer *
0x1400782a3  lea     r9, aUnionfsUtilsSt_0; "UnionFs::Utils::StatItemAsCaller"
0x1400782aa  mov     [rsp+130h+var_110], rax; char *
0x1400782af  mov     rdx, rsi; int
0x1400782b2  mov     ecx, ebx; this
0x1400782b4  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400782b9  lea     rcx, [rbp+3Fh+var_CC+2Ch]
0x1400782bd  call    wil__details__lambda_call__lambda_14d80e2c71013e3ae3fbb1e0a5e2b745______lambda_call__lambda_14d80e2c71013e3ae3fbb1e0a5e2b745___
0x1400782c2  mov     rcx, [rsp+130h+Object]; Object
0x1400782c7  test    rcx, rcx
0x1400782ca  jz      short loc_1400782D8
0x1400782cc  call    cs:__imp_ObfDereferenceObject
0x1400782d3  nop     dword ptr [rax+rax+00h]
0x1400782d8  mov     eax, ebx
0x1400782da  mov     rcx, [rbp+3Fh+var_50]
0x1400782de  xor     rcx, rsp; StackCookie
0x1400782e1  call    __security_check_cookie
0x1400782e6  add     rsp, 0F8h
0x1400782ed  pop     r15
0x1400782ef  pop     r14
0x1400782f1  pop     r13
0x1400782f3  pop     r12
0x1400782f5  pop     rdi
0x1400782f6  pop     rsi
0x1400782f7  pop     rbx
0x1400782f8  pop     rbp
0x1400782f9  retn
```
