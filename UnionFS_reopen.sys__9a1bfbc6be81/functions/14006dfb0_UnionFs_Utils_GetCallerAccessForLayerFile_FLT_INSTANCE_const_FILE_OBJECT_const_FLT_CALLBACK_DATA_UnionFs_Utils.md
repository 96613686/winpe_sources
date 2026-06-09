# UnionFs::Utils::GetCallerAccessForLayerFile(_FLT_INSTANCE const &,_FILE_OBJECT const &,_FLT_CALLBACK_DATA &,UnionFs::Utils::CallerAccessParams &,UnionFs::StackEventTracer &)

- ea: `0x14006dfb0`
- end: `0x14006e19b`
- name: `?GetCallerAccessForLayerFile@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAU_FLT_CALLBACK_DATA@@AEAUCallerAccessParams@12@AEAVStackEventTracer@2@@Z`
- size: `491`
- prototype: `__int64 __fastcall(UnionFs::Utils *__hidden this, const struct _FLT_INSTANCE *, const struct _FILE_OBJECT *, struct _FLT_CALLBACK_DATA *, struct UnionFs::Utils::CallerAccessParams *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14003ff88`

## callees

- `0x140056ac4`
- `0x140056afc`
- `0x140068770`
- `0x14006dfb0`
- `0x14006ff9c`
- `0x14007579c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006e061`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e105`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e15e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e17c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e061`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e105`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e15e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e17c`

## string_xrefs

- `0x14006e12c`: `PUSH: GetUserSidString`
- `0x14006e0d3`: `PUSH: AccessCheck`
- `0x14006dfd9`: `ORIGIN: Need SubjectSecurityContext in Cbd`
- `0x14006e02f`: `PUSH: QuerySecurity`
- `0x14006dfec`: `UnionFs::Utils::GetCallerAccessForLayerFile`
- `0x14006e040`: `UnionFs::Utils::GetCallerAccessForLayerFile`
- `0x14006e0e4`: `UnionFs::Utils::GetCallerAccessForLayerFile`
- `0x14006e13d`: `UnionFs::Utils::GetCallerAccessForLayerFile`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::GetCallerAccessForLayerFile(
        UnionFs::Utils *this,
        struct _FILE_OBJECT *a2,
        const struct _FILE_OBJECT *a3,
        struct _FLT_CALLBACK_DATA *a4,
        struct UnionFs::Utils::CallerAccessParams *a5)
{
  unsigned int v7; // ebx
  struct UnionFs::Utils::CallerAccessParams *v9; // rdi
  PVOID v10; // rbx
  int v11; // r8d
  int v12; // r15d
  int UserSidString; // r14d
  void *v14; // rcx
  const char *v15; // [rsp+28h] [rbp-49h]
  _BYTE v16[24]; // [rsp+40h] [rbp-31h]
  __int128 v17[2]; // [rsp+60h] [rbp-11h] BYREF
  __int64 v18; // [rsp+80h] [rbp+Fh]
  PVOID P; // [rsp+E0h] [rbp+6Fh] BYREF

  if ( LOBYTE(a3->Vpb->Flags) )
  {
    v7 = -1073741811;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000000DLL,
      (int)a5,
      (struct UnionFs::StackEventTracer *)0x24000211840LL,
      (unsigned __int64)"UnionFs::Utils::GetCallerAccessForLayerFile",
      "ORIGIN: Need SubjectSecurityContext in Cbd",
      v15);
    return v7;
  }
  v9 = a5;
  P = 0;
  v7 = UnionFs::Utils::QuerySecurity(this, a2, &P, (int)a5, 0x1FFu);
  if ( (v7 & 0x80000000) != 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)v7,
      (int)v9,
      (struct UnionFs::StackEventTracer *)0x3720021184FLL,
      (unsigned __int64)"UnionFs::Utils::GetCallerAccessForLayerFile",
      "PUSH: QuerySecurity",
      v15);
    if ( P )
      ExFreePoolWithTag(P, 0);
    return v7;
  }
  v10 = P;
  *(_OWORD *)&v16[8] = *(_OWORD *)&a4->IoStatus.Status;
  *(_QWORD *)v16 = 0;
  v11 = *(_DWORD *)(*(_QWORD *)&a3->Vpb->SerialNumber + 16LL);
  v17[0] = 0u;
  v17[1] = *(_OWORD *)v16;
  v18 = *(_OWORD *)&_mm_unpackhi_pd(*(__m128d *)&v16[8], *(__m128d *)&v16[8]);
  v12 = UnionFs::Utils::AccessCheck(v17, P, v11, (__int64)a3, (__int64)v9);
  if ( v12 >= 0 )
  {
    UserSidString = UnionFs::Utils::GetUserSidString((__int64)a3, (struct _UNICODE_STRING *)&a4->Thread, (int)v9);
    if ( UserSidString >= 0 )
    {
      v14 = *(void **)&a4->Flags;
      *(_QWORD *)&a4->Flags = v10;
      if ( v14 )
        ExFreePoolWithTag(v14, 0);
      return 0;
    }
    else
    {
      UnionFs::ProcessTraceStatusPushLocation(
        (UnionFs *)(unsigned int)UserSidString,
        (int)v9,
        (struct UnionFs::StackEventTracer *)0x24200211861LL,
        (unsigned __int64)"UnionFs::Utils::GetCallerAccessForLayerFile",
        "PUSH: GetUserSidString",
        v15);
      if ( v10 )
        ExFreePoolWithTag(v10, 0);
      return (unsigned int)UserSidString;
    }
  }
  else
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v12,
      (int)v9,
      (struct UnionFs::StackEventTracer *)0x2410021185BLL,
      (unsigned __int64)"UnionFs::Utils::GetCallerAccessForLayerFile",
      "PUSH: AccessCheck",
      v15);
    if ( v10 )
      ExFreePoolWithTag(v10, 0);
    return (unsigned int)v12;
  }
}

```

## disassembly

```asm
0x14006dfb0  push    rbp
0x14006dfb2  push    rbx
0x14006dfb3  push    rsi
0x14006dfb4  push    rdi
0x14006dfb5  push    r14
0x14006dfb7  push    r15
0x14006dfb9  lea     rbp, [rsp-27h]
0x14006dfbe  sub     rsp, 98h
0x14006dfc5  mov     rax, [r8+10h]
0x14006dfc9  mov     rsi, r9
0x14006dfcc  mov     r14, r8
0x14006dfcf  cmp     byte ptr [rax+4], 0
0x14006dfd3  jz      short loc_14006E009
0x14006dfd5  mov     rdx, [rbp+4Fh+arg_20]; int
0x14006dfd9  lea     rax, aOriginNeedSubj; "ORIGIN: Need SubjectSecurityContext in "...
0x14006dfe0  mov     ebx, 0C000000Dh
0x14006dfe5  mov     qword ptr [rsp+0C0h+SecurityInformation], rax; char *
0x14006dfea  mov     ecx, ebx; this
0x14006dfec  lea     r9, aUnionfsUtilsGe_13; "UnionFs::Utils::GetCallerAccessForLayer"...
0x14006dff3  mov     r8, 24000211840h; struct UnionFs::StackEventTracer *
0x14006dffd  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006e002  mov     eax, ebx
0x14006e004  jmp     loc_14006E18A
0x14006e009  mov     rdi, [rbp+4Fh+arg_20]
0x14006e00d  lea     r8, [rbp+4Fh+P]
0x14006e011  mov     r9, rdi
0x14006e014  mov     [rbp+4Fh+P], 0
0x14006e01c  mov     [rsp+0C0h+SecurityInformation], 1FFh; SecurityInformation
0x14006e024  call    ?QuerySecurity@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAV?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$default_delete@U_SECURITY_DESCRIPTOR@@@utl@@@utl@@AEAVStackEventTracer@2@K@Z; UnionFs::Utils::QuerySecurity(_FLT_INSTANCE const &,_FILE_OBJECT const &,utl::unique_ptr<_SECURITY_DESCRIPTOR,utl::default_delete<_SECURITY_DESCRIPTOR>> &,UnionFs::StackEventTracer &,ulong)
0x14006e029  mov     ebx, eax
0x14006e02b  test    eax, eax
0x14006e02d  jns     short loc_14006E06F
0x14006e02f  lea     rax, aPushQuerysecur; "PUSH: QuerySecurity"
0x14006e036  mov     r8, 3720021184Fh; struct UnionFs::StackEventTracer *
0x14006e040  lea     r9, aUnionfsUtilsGe_13; "UnionFs::Utils::GetCallerAccessForLayer"...
0x14006e047  mov     qword ptr [rsp+0C0h+SecurityInformation], rax; char *
0x14006e04c  mov     rdx, rdi; int
0x14006e04f  mov     ecx, ebx; this
0x14006e051  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006e056  mov     rcx, [rbp+4Fh+P]; P
0x14006e05a  test    rcx, rcx
0x14006e05d  jz      short loc_14006E002
0x14006e05f  xor     edx, edx; Tag
0x14006e061  call    cs:__imp_ExFreePoolWithTag
0x14006e068  nop     dword ptr [rax+rax+00h]
0x14006e06d  jmp     short loc_14006E002
0x14006e06f  movups  xmm2, xmmword ptr [rsi+18h]
0x14006e073  mov     rax, [r14+10h]
0x14006e077  lea     rcx, [rbp+4Fh+var_60]
0x14006e07b  mov     rbx, [rbp+4Fh+P]
0x14006e07f  mov     r9, r14
0x14006e082  movups  [rbp+4Fh+var_80+8], xmm2
0x14006e086  mov     rdx, rbx
0x14006e089  mov     qword ptr [rbp+4Fh+var_90], 0
0x14006e091  unpckhpd xmm2, xmm2
0x14006e095  mov     r8, [rax+18h]
0x14006e099  mov     qword ptr [rbp+4Fh+var_90+8], 0
0x14006e0a1  movups  xmm0, [rbp+4Fh+var_90]
0x14006e0a5  mov     qword ptr [rbp+4Fh+var_80], 0
0x14006e0ad  movups  xmm1, [rbp+4Fh+var_80]
0x14006e0b1  mov     r8d, [r8+10h]
0x14006e0b5  movaps  [rbp+4Fh+var_60], xmm0
0x14006e0b9  movaps  [rbp+4Fh+var_50], xmm1
0x14006e0bd  movsd   [rbp+4Fh+var_40], xmm2
0x14006e0c2  mov     qword ptr [rsp+0C0h+SecurityInformation], rdi
0x14006e0c7  call    ?AccessCheck@Utils@UnionFs@@YAJUAccessCheckParams@12@AEBU_SECURITY_DESCRIPTOR@@KAEAU_FLT_CALLBACK_DATA@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::AccessCheck(UnionFs::Utils::AccessCheckParams,_SECURITY_DESCRIPTOR const &,ulong,_FLT_CALLBACK_DATA &,UnionFs::StackEventTracer &)
0x14006e0cc  mov     r15d, eax
0x14006e0cf  test    eax, eax
0x14006e0d1  jns     short loc_14006E116
0x14006e0d3  lea     rax, aPushAccesschec; "PUSH: AccessCheck"
0x14006e0da  mov     r8, 2410021185Bh; struct UnionFs::StackEventTracer *
0x14006e0e4  lea     r9, aUnionfsUtilsGe_13; "UnionFs::Utils::GetCallerAccessForLayer"...
0x14006e0eb  mov     qword ptr [rsp+0C0h+SecurityInformation], rax; char *
0x14006e0f0  mov     rdx, rdi; int
0x14006e0f3  mov     ecx, r15d; this
0x14006e0f6  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006e0fb  test    rbx, rbx
0x14006e0fe  jz      short loc_14006E111
0x14006e100  xor     edx, edx; Tag
0x14006e102  mov     rcx, rbx; P
0x14006e105  call    cs:__imp_ExFreePoolWithTag
0x14006e10c  nop     dword ptr [rax+rax+00h]
0x14006e111  mov     eax, r15d
0x14006e114  jmp     short loc_14006E18A
0x14006e116  lea     rdx, [rsi+8]
0x14006e11a  mov     r8, rdi
0x14006e11d  mov     rcx, r14
0x14006e120  call    ?GetUserSidString@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetUserSidString(_FLT_CALLBACK_DATA const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)
0x14006e125  mov     r14d, eax
0x14006e128  test    eax, eax
0x14006e12a  jns     short loc_14006E16F
0x14006e12c  lea     rax, aPushGetusersid; "PUSH: GetUserSidString"
0x14006e133  mov     r8, 24200211861h; struct UnionFs::StackEventTracer *
0x14006e13d  lea     r9, aUnionfsUtilsGe_13; "UnionFs::Utils::GetCallerAccessForLayer"...
0x14006e144  mov     qword ptr [rsp+0C0h+SecurityInformation], rax; char *
0x14006e149  mov     rdx, rdi; int
0x14006e14c  mov     ecx, r14d; this
0x14006e14f  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006e154  test    rbx, rbx
0x14006e157  jz      short loc_14006E16A
0x14006e159  xor     edx, edx; Tag
0x14006e15b  mov     rcx, rbx; P
0x14006e15e  call    cs:__imp_ExFreePoolWithTag
0x14006e165  nop     dword ptr [rax+rax+00h]
0x14006e16a  mov     eax, r14d
0x14006e16d  jmp     short loc_14006E18A
0x14006e16f  mov     rcx, [rsi]; P
0x14006e172  mov     [rsi], rbx
0x14006e175  test    rcx, rcx
0x14006e178  jz      short loc_14006E188
0x14006e17a  xor     edx, edx; Tag
0x14006e17c  call    cs:__imp_ExFreePoolWithTag
0x14006e183  nop     dword ptr [rax+rax+00h]
0x14006e188  xor     eax, eax
0x14006e18a  add     rsp, 98h
0x14006e191  pop     r15
0x14006e193  pop     r14
0x14006e195  pop     rdi
0x14006e196  pop     rsi
0x14006e197  pop     rbx
0x14006e198  pop     rbp
0x14006e199  retn
```
