# UnionFs::Utils::GetCallerAccessForLayerFile(_FLT_INSTANCE const &,_FILE_OBJECT const &,_FLT_CALLBACK_DATA &,UnionFs::Utils::CallerAccessParams &,UnionFs::StackEventTracer &)

- ea: `0x14006e1a0`
- end: `0x14006e38b`
- name: `?GetCallerAccessForLayerFile@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAU_FLT_CALLBACK_DATA@@AEAUCallerAccessParams@12@AEAVStackEventTracer@2@@Z`
- size: `491`
- prototype: `__int64 __fastcall(UnionFs::Utils *__hidden this, const struct _FLT_INSTANCE *, const struct _FILE_OBJECT *, struct _FLT_CALLBACK_DATA *, struct UnionFs::Utils::CallerAccessParams *, struct UnionFs::StackEventTracer *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140040110`

## callees

- `0x140056c44`
- `0x140056c7c`
- `0x140068960`
- `0x14006e1a0`
- `0x14007018c`
- `0x14007599c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006e251`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e2f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e34e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e36c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e251`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e2f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e34e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006e36c`

## string_xrefs

- `0x14006e31c`: `PUSH: GetUserSidString`
- `0x14006e2c3`: `PUSH: AccessCheck`
- `0x14006e1c9`: `ORIGIN: Need SubjectSecurityContext in Cbd`
- `0x14006e21f`: `PUSH: QuerySecurity`
- `0x14006e1dc`: `UnionFs::Utils::GetCallerAccessForLayerFile`
- `0x14006e230`: `UnionFs::Utils::GetCallerAccessForLayerFile`
- `0x14006e2d4`: `UnionFs::Utils::GetCallerAccessForLayerFile`
- `0x14006e32d`: `UnionFs::Utils::GetCallerAccessForLayerFile`

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
      (struct UnionFs::StackEventTracer *)0x24000211876LL,
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
      (struct UnionFs::StackEventTracer *)0x37200211885LL,
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
        (struct UnionFs::StackEventTracer *)0x24200211897LL,
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
      (struct UnionFs::StackEventTracer *)0x24100211891LL,
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
0x14006e1a0  push    rbp
0x14006e1a2  push    rbx
0x14006e1a3  push    rsi
0x14006e1a4  push    rdi
0x14006e1a5  push    r14
0x14006e1a7  push    r15
0x14006e1a9  lea     rbp, [rsp-27h]
0x14006e1ae  sub     rsp, 98h
0x14006e1b5  mov     rax, [r8+10h]
0x14006e1b9  mov     rsi, r9
0x14006e1bc  mov     r14, r8
0x14006e1bf  cmp     byte ptr [rax+4], 0
0x14006e1c3  jz      short loc_14006E1F9
0x14006e1c5  mov     rdx, [rbp+4Fh+arg_20]; int
0x14006e1c9  lea     rax, aOriginNeedSubj; "ORIGIN: Need SubjectSecurityContext in "...
0x14006e1d0  mov     ebx, 0C000000Dh
0x14006e1d5  mov     qword ptr [rsp+0C0h+SecurityInformation], rax; char *
0x14006e1da  mov     ecx, ebx; this
0x14006e1dc  lea     r9, aUnionfsUtilsGe_13; "UnionFs::Utils::GetCallerAccessForLayer"...
0x14006e1e3  mov     r8, 24000211876h; struct UnionFs::StackEventTracer *
0x14006e1ed  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006e1f2  mov     eax, ebx
0x14006e1f4  jmp     loc_14006E37A
0x14006e1f9  mov     rdi, [rbp+4Fh+arg_20]
0x14006e1fd  lea     r8, [rbp+4Fh+P]
0x14006e201  mov     r9, rdi
0x14006e204  mov     [rbp+4Fh+P], 0
0x14006e20c  mov     [rsp+0C0h+SecurityInformation], 1FFh; SecurityInformation
0x14006e214  call    ?QuerySecurity@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAV?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$default_delete@U_SECURITY_DESCRIPTOR@@@utl@@@utl@@AEAVStackEventTracer@2@K@Z; UnionFs::Utils::QuerySecurity(_FLT_INSTANCE const &,_FILE_OBJECT const &,utl::unique_ptr<_SECURITY_DESCRIPTOR,utl::default_delete<_SECURITY_DESCRIPTOR>> &,UnionFs::StackEventTracer &,ulong)
0x14006e219  mov     ebx, eax
0x14006e21b  test    eax, eax
0x14006e21d  jns     short loc_14006E25F
0x14006e21f  lea     rax, aPushQuerysecur; "PUSH: QuerySecurity"
0x14006e226  mov     r8, 37200211885h; struct UnionFs::StackEventTracer *
0x14006e230  lea     r9, aUnionfsUtilsGe_13; "UnionFs::Utils::GetCallerAccessForLayer"...
0x14006e237  mov     qword ptr [rsp+0C0h+SecurityInformation], rax; char *
0x14006e23c  mov     rdx, rdi; int
0x14006e23f  mov     ecx, ebx; this
0x14006e241  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006e246  mov     rcx, [rbp+4Fh+P]; P
0x14006e24a  test    rcx, rcx
0x14006e24d  jz      short loc_14006E1F2
0x14006e24f  xor     edx, edx; Tag
0x14006e251  call    cs:__imp_ExFreePoolWithTag
0x14006e258  nop     dword ptr [rax+rax+00h]
0x14006e25d  jmp     short loc_14006E1F2
0x14006e25f  movups  xmm2, xmmword ptr [rsi+18h]
0x14006e263  mov     rax, [r14+10h]
0x14006e267  lea     rcx, [rbp+4Fh+var_60]
0x14006e26b  mov     rbx, [rbp+4Fh+P]
0x14006e26f  mov     r9, r14
0x14006e272  movups  [rbp+4Fh+var_80+8], xmm2
0x14006e276  mov     rdx, rbx
0x14006e279  mov     qword ptr [rbp+4Fh+var_90], 0
0x14006e281  unpckhpd xmm2, xmm2
0x14006e285  mov     r8, [rax+18h]
0x14006e289  mov     qword ptr [rbp+4Fh+var_90+8], 0
0x14006e291  movups  xmm0, [rbp+4Fh+var_90]
0x14006e295  mov     qword ptr [rbp+4Fh+var_80], 0
0x14006e29d  movups  xmm1, [rbp+4Fh+var_80]
0x14006e2a1  mov     r8d, [r8+10h]
0x14006e2a5  movaps  [rbp+4Fh+var_60], xmm0
0x14006e2a9  movaps  [rbp+4Fh+var_50], xmm1
0x14006e2ad  movsd   [rbp+4Fh+var_40], xmm2
0x14006e2b2  mov     qword ptr [rsp+0C0h+SecurityInformation], rdi
0x14006e2b7  call    ?AccessCheck@Utils@UnionFs@@YAJUAccessCheckParams@12@AEBU_SECURITY_DESCRIPTOR@@KAEAU_FLT_CALLBACK_DATA@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::AccessCheck(UnionFs::Utils::AccessCheckParams,_SECURITY_DESCRIPTOR const &,ulong,_FLT_CALLBACK_DATA &,UnionFs::StackEventTracer &)
0x14006e2bc  mov     r15d, eax
0x14006e2bf  test    eax, eax
0x14006e2c1  jns     short loc_14006E306
0x14006e2c3  lea     rax, aPushAccesschec; "PUSH: AccessCheck"
0x14006e2ca  mov     r8, 24100211891h; struct UnionFs::StackEventTracer *
0x14006e2d4  lea     r9, aUnionfsUtilsGe_13; "UnionFs::Utils::GetCallerAccessForLayer"...
0x14006e2db  mov     qword ptr [rsp+0C0h+SecurityInformation], rax; char *
0x14006e2e0  mov     rdx, rdi; int
0x14006e2e3  mov     ecx, r15d; this
0x14006e2e6  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006e2eb  test    rbx, rbx
0x14006e2ee  jz      short loc_14006E301
0x14006e2f0  xor     edx, edx; Tag
0x14006e2f2  mov     rcx, rbx; P
0x14006e2f5  call    cs:__imp_ExFreePoolWithTag
0x14006e2fc  nop     dword ptr [rax+rax+00h]
0x14006e301  mov     eax, r15d
0x14006e304  jmp     short loc_14006E37A
0x14006e306  lea     rdx, [rsi+8]
0x14006e30a  mov     r8, rdi
0x14006e30d  mov     rcx, r14
0x14006e310  call    ?GetUserSidString@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z; UnionFs::Utils::GetUserSidString(_FLT_CALLBACK_DATA const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)
0x14006e315  mov     r14d, eax
0x14006e318  test    eax, eax
0x14006e31a  jns     short loc_14006E35F
0x14006e31c  lea     rax, aPushGetusersid; "PUSH: GetUserSidString"
0x14006e323  mov     r8, 24200211897h; struct UnionFs::StackEventTracer *
0x14006e32d  lea     r9, aUnionfsUtilsGe_13; "UnionFs::Utils::GetCallerAccessForLayer"...
0x14006e334  mov     qword ptr [rsp+0C0h+SecurityInformation], rax; char *
0x14006e339  mov     rdx, rdi; int
0x14006e33c  mov     ecx, r14d; this
0x14006e33f  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006e344  test    rbx, rbx
0x14006e347  jz      short loc_14006E35A
0x14006e349  xor     edx, edx; Tag
0x14006e34b  mov     rcx, rbx; P
0x14006e34e  call    cs:__imp_ExFreePoolWithTag
0x14006e355  nop     dword ptr [rax+rax+00h]
0x14006e35a  mov     eax, r14d
0x14006e35d  jmp     short loc_14006E37A
0x14006e35f  mov     rcx, [rsi]; P
0x14006e362  mov     [rsi], rbx
0x14006e365  test    rcx, rcx
0x14006e368  jz      short loc_14006E378
0x14006e36a  xor     edx, edx; Tag
0x14006e36c  call    cs:__imp_ExFreePoolWithTag
0x14006e373  nop     dword ptr [rax+rax+00h]
0x14006e378  xor     eax, eax
0x14006e37a  add     rsp, 98h
0x14006e381  pop     r15
0x14006e383  pop     r14
0x14006e385  pop     rdi
0x14006e386  pop     rsi
0x14006e387  pop     rbx
0x14006e388  pop     rbp
0x14006e389  retn
```
