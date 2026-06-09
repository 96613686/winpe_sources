# UnionFs::Utils::StatItemAsCaller(_UNICODE_STRING const &,_FLT_INSTANCE const &,_EJOB const &,UnionFs::Utils::StatItemFlags,_FILE_STAT_INFORMATION *,_FLT_CALLBACK_DATA &,UnionFs::StackEventTracer &)

- ea: `0x1400782bc`
- end: `0x140078623`
- name: `?StatItemAsCaller@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBU_FLT_INSTANCE@@AEBU_EJOB@@W4StatItemFlags@12@PEAU_FILE_STAT_INFORMATION@@AEAU_FLT_CALLBACK_DATA@@AEAVStackEventTracer@2@@Z`
- size: `871`
- prototype: ``
- caller_count: `6`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1400173f0`
- `0x1400183cc`
- `0x1400194b8`
- `0x140041650`
- `0x1400612fc`
- `0x14007862c`

## callees

- `0x140056c08`
- `0x140056c44`
- `0x140056c7c`
- `0x140067c98`
- `0x14006f2f8`
- `0x140077a60`
- `0x1400782bc`
- `0x14007baf0`
- `0x14007bf40`

## import_xrefs

- `ntoskrnl!SeImpersonateClientEx` at `0x1400784c3`
- `ntoskrnl!SeImpersonateClientEx` at `0x1400784c3`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140078396`
- `ntoskrnl!PsReferenceImpersonationToken` at `0x140078396`
- `ntoskrnl!SeCreateClientSecurityFromSubjectContext` at `0x140078410`
- `ntoskrnl!SeCreateClientSecurityFromSubjectContext` at `0x140078410`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140078573`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x140078573`
- `ntoskrnl!ObfDereferenceObject` at `0x1400783af`
- `ntoskrnl!ObfDereferenceObject` at `0x14007848c`
- `ntoskrnl!ObfDereferenceObject` at `0x1400785f4`
- `ntoskrnl!ObfDereferenceObject` at `0x1400783af`
- `ntoskrnl!ObfDereferenceObject` at `0x14007848c`
- `ntoskrnl!ObfDereferenceObject` at `0x1400785f4`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140078476`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400784b1`
- `ntoskrnl!SeUnlockSubjectContext` at `0x140078476`
- `ntoskrnl!SeUnlockSubjectContext` at `0x1400784b1`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14007845b`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14007850f`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14007852f`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14007845b`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14007850f`
- `ntoskrnl!SeDeleteClientSecurity` at `0x14007852f`
- `ntoskrnl!SeLockSubjectContext` at `0x1400783e7`
- `ntoskrnl!SeLockSubjectContext` at `0x1400783e7`

## string_xrefs

- `0x1400784d5`: `API: Impersonating client`
- `0x140078423`: `API: Creating security client context`

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
      (struct UnionFs::StackEventTracer *)0xF300210A14LL,
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
        (struct UnionFs::StackEventTracer *)0xEF00210A3ELL,
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
        (struct UnionFs::StackEventTracer *)0x25B00210A5ELL,
        (unsigned __int64)"UnionFs::Utils::StatItemAsCaller",
        "PUSH: StatItem",
        v20);
    wil::details::lambda_call__lambda_14d80e2c71013e3ae3fbb1e0a5e2b745___::_lambda_call__lambda_14d80e2c71013e3ae3fbb1e0a5e2b745___(&v27[44]);
    goto LABEL_27;
  }
  UnionFs::ProcessTraceStatusFromApi(
    (UnionFs *)(unsigned int)ClientSecurityFromSubjectContext,
    a7,
    (struct UnionFs::StackEventTracer *)0xEE00210A35LL,
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
0x1400782bc  push    rbp
0x1400782be  push    rbx
0x1400782bf  push    rsi
0x1400782c0  push    rdi
0x1400782c1  push    r12
0x1400782c3  push    r13
0x1400782c5  push    r14
0x1400782c7  push    r15
0x1400782c9  lea     rbp, [rsp-7]
0x1400782ce  sub     rsp, 0F8h
0x1400782d5  mov     rax, cs:__security_cookie
0x1400782dc  xor     rax, rsp
0x1400782df  mov     [rbp+3Fh+var_50], rax
0x1400782e3  mov     rax, [rbp+3Fh+arg_20]
0x1400782e7  mov     r13, rdx
0x1400782ea  mov     r15, [rbp+3Fh+arg_28]
0x1400782ee  lea     rdx, [rsp+130h+var_CC]; struct _FLT_CALLBACK_DATA *
0x1400782f3  mov     rsi, qword ptr [rbp+3Fh+arg_30]
0x1400782f7  mov     r12, rcx
0x1400782fa  xor     r14d, r14d
0x1400782fd  mov     dword ptr [rsp+130h+var_CC+4], r9d
0x140078302  mov     rcx, r15; this
0x140078305  mov     qword ptr [rbp+3Fh+var_CC+14h], r8
0x140078309  mov     qword ptr [rsp+130h+var_CC+0Ch], rax
0x14007830e  mov     dword ptr [rsp+130h+var_CC], r14d
0x140078313  call    ?GetObjectAttributesFlags@Utils@UnionFs@@YA_NAEBU_FLT_CALLBACK_DATA@@PEAK@Z; UnionFs::Utils::GetObjectAttributesFlags(_FLT_CALLBACK_DATA const &,ulong *)
0x140078318  test    al, al
0x14007831a  jnz     short loc_14007834D
0x14007831c  lea     rax, aOriginGettingA; "ORIGIN: Getting attribute flags"
0x140078323  mov     ebx, 0C0000010h
0x140078328  mov     ecx, ebx; this
0x14007832a  mov     [rsp+130h+var_110], rax; char *
0x14007832f  lea     r9, aUnionfsUtilsSt_0; "UnionFs::Utils::StatItemAsCaller"
0x140078336  mov     r8, 0F300210A14h; struct UnionFs::StackEventTracer *
0x140078340  mov     rdx, rsi; int
0x140078343  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140078348  jmp     loc_140078600
0x14007834d  cmp     byte ptr [r15+50h], 1
0x140078352  lea     rdi, [r15+10h]
0x140078356  mov     [rsp+130h+var_E0], r14b
0x14007835b  mov     [rsp+130h+Object], r14
0x140078360  mov     [rsp+130h+CopyOnOpen], r14b
0x140078365  mov     [rsp+130h+EffectiveOnly], r14b
0x14007836a  mov     [rsp+130h+ImpersonationLevel], r14d
0x14007836f  jz      short loc_14007837E
0x140078371  mov     rax, [rdi]
0x140078374  test    byte ptr [rax+6], 1
0x140078378  jz      loc_14007853B
0x14007837e  mov     rcx, gs:188h; Thread
0x140078387  lea     r9, [rsp+130h+ImpersonationLevel]; ImpersonationLevel
0x14007838c  lea     r8, [rsp+130h+EffectiveOnly]; EffectiveOnly
0x140078391  lea     rdx, [rsp+130h+CopyOnOpen]; CopyOnOpen
0x140078396  call    cs:__imp_PsReferenceImpersonationToken
0x14007839d  nop     dword ptr [rax+rax+00h]
0x1400783a2  mov     rcx, [rsp+130h+Object]; Object
0x1400783a7  mov     rbx, rax
0x1400783aa  test    rcx, rcx
0x1400783ad  jz      short loc_1400783BB
0x1400783af  call    cs:__imp_ObfDereferenceObject
0x1400783b6  nop     dword ptr [rax+rax+00h]
0x1400783bb  mov     rax, [rdi]
0x1400783be  mov     [rsp+130h+Object], rbx
0x1400783c3  mov     dword ptr [rbp+3Fh+var_CC+24h], 1
0x1400783ca  mov     dword ptr [rbp+3Fh+var_CC+1Ch], 0Ch
0x1400783d1  mov     dword ptr [rbp+3Fh+var_CC+20h], 2
0x1400783d8  mov     rcx, [rax+18h]
0x1400783dc  mov     rbx, [rcx+8]
0x1400783e0  add     rbx, 20h ; ' '
0x1400783e4  mov     rcx, rbx; SubjectContext
0x1400783e7  call    cs:__imp_SeLockSubjectContext
0x1400783ee  nop     dword ptr [rax+rax+00h]
0x1400783f3  xor     edx, edx; Val
0x1400783f5  lea     rcx, [rbp+3Fh+var_CC+2Ch]; void *
0x1400783f9  lea     r8d, [rdx+48h]; Size
0x1400783fd  call    memset
0x140078402  lea     r9, [rbp+3Fh+var_CC+2Ch]; ClientContext
0x140078406  xor     r8d, r8d; ServerIsRemote
0x140078409  lea     rdx, [rbp+3Fh+var_CC+1Ch]; ClientSecurityQos
0x14007840d  mov     rcx, rbx; SubjectContext
0x140078410  call    cs:__imp_SeCreateClientSecurityFromSubjectContext
0x140078417  nop     dword ptr [rax+rax+00h]
0x14007841c  mov     r14d, eax
0x14007841f  test    eax, eax
0x140078421  jns     short loc_1400784A0
0x140078423  lea     rax, aApiCreatingSec; "API: Creating security client context"
0x14007842a  mov     [rsp+130h+var_108], r12; char *
0x14007842f  lea     r9, aUnionfsUtilsSt_0; "UnionFs::Utils::StatItemAsCaller"
0x140078436  mov     [rsp+130h+var_110], rax; char *
0x14007843b  mov     r8, 0EE00210A35h; struct UnionFs::StackEventTracer *
0x140078445  mov     rdx, rsi; int
0x140078448  mov     ecx, r14d; this
0x14007844b  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2AEBU_UNICODE_STRING@@@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *,_UNICODE_STRING const &)
0x140078450  cmp     qword ptr [rbp+3Fh+var_CC+3Ch], 0
0x140078455  jz      short loc_140078467
0x140078457  lea     rcx, [rbp+3Fh+var_CC+2Ch]
0x14007845b  call    cs:__imp_SeDeleteClientSecurity
0x140078462  nop     dword ptr [rax+rax+00h]
0x140078467  test    rbx, rbx
0x14007846a  jz      short loc_140078482
0x14007846c  cmp     qword ptr [rbx+10h], 0
0x140078471  jz      short loc_140078482
0x140078473  mov     rcx, rbx; SubjectContext
0x140078476  call    cs:__imp_SeUnlockSubjectContext
0x14007847d  nop     dword ptr [rax+rax+00h]
0x140078482  mov     rcx, [rsp+130h+Object]; Object
0x140078487  test    rcx, rcx
0x14007848a  jz      short loc_140078498
0x14007848c  call    cs:__imp_ObfDereferenceObject
0x140078493  nop     dword ptr [rax+rax+00h]
0x140078498  mov     eax, r14d
0x14007849b  jmp     loc_140078602
0x1400784a0  xor     r14d, r14d
0x1400784a3  test    rbx, rbx
0x1400784a6  jz      short loc_1400784BD
0x1400784a8  cmp     [rbx+10h], r14
0x1400784ac  jz      short loc_1400784BD
0x1400784ae  mov     rcx, rbx; SubjectContext
0x1400784b1  call    cs:__imp_SeUnlockSubjectContext
0x1400784b8  nop     dword ptr [rax+rax+00h]
0x1400784bd  xor     edx, edx; ServerThread
0x1400784bf  lea     rcx, [rbp+3Fh+var_CC+2Ch]; ClientContext
0x1400784c3  call    cs:__imp_SeImpersonateClientEx
0x1400784ca  nop     dword ptr [rax+rax+00h]
0x1400784cf  mov     ebx, eax
0x1400784d1  test    eax, eax
0x1400784d3  jns     short loc_140078520
0x1400784d5  lea     rax, aApiImpersonati; "API: Impersonating client"
0x1400784dc  mov     [rsp+130h+var_108], r12; char *
0x1400784e1  lea     r9, aUnionfsUtilsSt_0; "UnionFs::Utils::StatItemAsCaller"
0x1400784e8  mov     [rsp+130h+var_110], rax; char *
0x1400784ed  mov     r8, 0EF00210A3Eh; struct UnionFs::StackEventTracer *
0x1400784f7  mov     rdx, rsi; int
0x1400784fa  mov     ecx, ebx; this
0x1400784fc  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2AEBU_UNICODE_STRING@@@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *,_UNICODE_STRING const &)
0x140078501  cmp     qword ptr [rbp+3Fh+var_CC+3Ch], r14
0x140078505  jz      loc_1400785EA
0x14007850b  lea     rcx, [rbp+3Fh+var_CC+2Ch]
0x14007850f  call    cs:__imp_SeDeleteClientSecurity
0x140078516  nop     dword ptr [rax+rax+00h]
0x14007851b  jmp     loc_1400785EA
0x140078520  mov     [rsp+130h+var_E0], 1
0x140078525  cmp     qword ptr [rbp+3Fh+var_CC+3Ch], r14
0x140078529  jz      short loc_14007853B
0x14007852b  lea     rcx, [rbp+3Fh+var_CC+2Ch]
0x14007852f  call    cs:__imp_SeDeleteClientSecurity
0x140078536  nop     dword ptr [rax+rax+00h]
0x14007853b  mov     rcx, [rdi]
0x14007853e  lea     rax, [rsp+130h+var_E0]
0x140078543  mov     qword ptr [rbp+3Fh+var_CC+2Ch], rax
0x140078547  lea     rax, [rsp+130h+Object]
0x14007854c  mov     qword ptr [rbp+3Fh+var_CC+34h], rax
0x140078550  lea     rax, [rsp+130h+CopyOnOpen]
0x140078555  mov     qword ptr [rbp+3Fh+var_CC+3Ch], rax
0x140078559  lea     rax, [rsp+130h+EffectiveOnly]
0x14007855e  mov     rcx, [rcx+8]; FileObject
0x140078562  mov     qword ptr [rbp+3Fh+var_CC+44h], rax
0x140078566  lea     rax, [rsp+130h+ImpersonationLevel]
0x14007856b  mov     qword ptr [rbp+3Fh+var_CC+4Ch], rax
0x14007856f  mov     [rbp+3Fh+var_CC+54h], 1
0x140078573  call    cs:__imp_IoGetTransactionParameterBlock
0x14007857a  nop     dword ptr [rax+rax+00h]
0x14007857f  mov     r9, qword ptr [rbp+3Fh+var_CC+14h]
0x140078583  mov     rdx, r13
0x140078586  mov     r8d, dword ptr [rsp+130h+var_CC]
0x14007858b  mov     rcx, r12
0x14007858e  mov     [rsp+130h+var_F0], r15
0x140078593  mov     [rsp+130h+var_F8], rax
0x140078598  mov     rax, qword ptr [rsp+130h+var_CC+0Ch]
0x14007859d  mov     [rsp+130h+var_100], rsi
0x1400785a2  mov     [rsp+130h+var_108], rax; char *
0x1400785a7  mov     eax, dword ptr [rsp+130h+var_CC+4]
0x1400785ab  mov     dword ptr [rsp+130h+var_110], eax
0x1400785af  call    ?StatItem@Utils@UnionFs@@YAJAEBU_UNICODE_STRING@@AEBU_FLT_INSTANCE@@KAEBU_EJOB@@W4StatItemFlags@12@PEAU_FILE_STAT_INFORMATION@@AEAVStackEventTracer@2@QEAU_TXN_PARAMETER_BLOCK@@PEAU_FLT_CALLBACK_DATA@@@Z; UnionFs::Utils::StatItem(_UNICODE_STRING const &,_FLT_INSTANCE const &,ulong,_EJOB const &,UnionFs::Utils::StatItemFlags,_FILE_STAT_INFORMATION *,UnionFs::StackEventTracer &,_TXN_PARAMETER_BLOCK * const,_FLT_CALLBACK_DATA *)
0x1400785b4  mov     ebx, eax
0x1400785b6  test    eax, eax
0x1400785b8  jns     short loc_1400785E1
0x1400785ba  lea     rax, aPushStatitem; "PUSH: StatItem"
0x1400785c1  mov     r8, 25B00210A5Eh; struct UnionFs::StackEventTracer *
0x1400785cb  lea     r9, aUnionfsUtilsSt_0; "UnionFs::Utils::StatItemAsCaller"
0x1400785d2  mov     [rsp+130h+var_110], rax; char *
0x1400785d7  mov     rdx, rsi; int
0x1400785da  mov     ecx, ebx; this
0x1400785dc  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400785e1  lea     rcx, [rbp+3Fh+var_CC+2Ch]
0x1400785e5  call    wil__details__lambda_call__lambda_14d80e2c71013e3ae3fbb1e0a5e2b745______lambda_call__lambda_14d80e2c71013e3ae3fbb1e0a5e2b745___
0x1400785ea  mov     rcx, [rsp+130h+Object]; Object
0x1400785ef  test    rcx, rcx
0x1400785f2  jz      short loc_140078600
0x1400785f4  call    cs:__imp_ObfDereferenceObject
0x1400785fb  nop     dword ptr [rax+rax+00h]
0x140078600  mov     eax, ebx
0x140078602  mov     rcx, [rbp+3Fh+var_50]
0x140078606  xor     rcx, rsp; StackCookie
0x140078609  call    __security_check_cookie
0x14007860e  add     rsp, 0F8h
0x140078615  pop     r15
0x140078617  pop     r14
0x140078619  pop     r13
0x14007861b  pop     r12
0x14007861d  pop     rdi
0x14007861e  pop     rsi
0x14007861f  pop     rbx
0x140078620  pop     rbp
0x140078621  retn
```
