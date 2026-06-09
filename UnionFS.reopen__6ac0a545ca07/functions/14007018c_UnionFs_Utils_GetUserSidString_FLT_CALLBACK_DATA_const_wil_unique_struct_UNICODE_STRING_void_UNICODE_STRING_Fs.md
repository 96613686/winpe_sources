# UnionFs::Utils::GetUserSidString(_FLT_CALLBACK_DATA const &,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0> &,UnionFs::StackEventTracer &)

- ea: `0x14007018c`
- end: `0x1400702b0`
- name: `?GetUserSidString@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEAV?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@AEAVStackEventTracer@2@@Z`
- size: `292`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140013b60`
- `0x14001568c`
- `0x140041650`
- `0x140068960`
- `0x14006e1a0`

## callees

- `0x140056bd0`
- `0x140056c44`
- `0x14007018c`

## import_xrefs

- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14007024d`
- `ntoskrnl!RtlConvertSidToUnicodeString` at `0x14007024d`
- `ntoskrnl!SeQueryInformationToken` at `0x140070204`
- `ntoskrnl!SeQueryInformationToken` at `0x140070204`
- `ntoskrnl!ExFreePoolWithTag` at `0x140070291`
- `ntoskrnl!ExFreePoolWithTag` at `0x140070291`

## string_xrefs

- `0x1400701ab`: `ORIGIN: Need SubjectSecurityContext in Cbd`
- `0x1400701be`: `UnionFs::Utils::GetUserSidString`
- `0x140070227`: `UnionFs::Utils::GetUserSidString`
- `0x140070270`: `UnionFs::Utils::GetUserSidString`
- `0x14007025f`: `API: Convert SID to string`
- `0x140070216`: `API: Getting caller's SID`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::GetUserSidString(__int64 a1, struct _UNICODE_STRING *a2, int a3)
{
  __int64 v3; // rax
  NTSTATUS v6; // ebx
  __int64 v7; // rdx
  void *v8; // rcx
  const char *v10; // [rsp+28h] [rbp-10h]
  PVOID TokenInformation; // [rsp+40h] [rbp+8h] BYREF

  v3 = *(_QWORD *)(a1 + 16);
  if ( *(_BYTE *)(v3 + 4) )
  {
    v6 = -1073741811;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000000DLL,
      a3,
      (struct UnionFs::StackEventTracer *)0x23F0021184CLL,
      (unsigned __int64)"UnionFs::Utils::GetUserSidString",
      "ORIGIN: Need SubjectSecurityContext in Cbd",
      v10);
  }
  else
  {
    v7 = *(_QWORD *)(*(_QWORD *)(v3 + 24) + 8LL);
    v8 = *(void **)(v7 + 32);
    if ( !v8 )
      v8 = *(void **)(v7 + 48);
    TokenInformation = 0;
    v6 = SeQueryInformationToken(v8, TokenUser, &TokenInformation);
    if ( v6 >= 0 )
    {
      v6 = RtlConvertSidToUnicodeString(a2, *(PSID *)TokenInformation, 1u);
      if ( v6 >= 0 )
        v6 = 0;
      else
        UnionFs::ProcessTraceStatusFromApi(
          (UnionFs *)(unsigned int)v6,
          a3,
          (struct UnionFs::StackEventTracer *)0x23800211863LL,
          (unsigned __int64)"UnionFs::Utils::GetUserSidString",
          "API: Convert SID to string",
          v10);
      ExFreePoolWithTag(TokenInformation, 0);
    }
    else
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)v6,
        a3,
        (struct UnionFs::StackEventTracer *)0x2370021185ALL,
        (unsigned __int64)"UnionFs::Utils::GetUserSidString",
        "API: Getting caller's SID",
        v10);
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14007018c  mov     [rsp+arg_8], rbx
0x140070191  mov     [rsp+arg_10], rsi
0x140070196  push    rdi
0x140070197  sub     rsp, 30h
0x14007019b  mov     rax, [rcx+10h]
0x14007019f  mov     rdi, r8
0x1400701a2  mov     rsi, rdx
0x1400701a5  cmp     byte ptr [rax+4], 0
0x1400701a9  jz      short loc_1400701DC
0x1400701ab  lea     rax, aOriginNeedSubj; "ORIGIN: Need SubjectSecurityContext in "...
0x1400701b2  mov     ebx, 0C000000Dh
0x1400701b7  mov     ecx, ebx; this
0x1400701b9  mov     [rsp+38h+var_18], rax; char *
0x1400701be  lea     r9, aUnionfsUtilsGe_5; "UnionFs::Utils::GetUserSidString"
0x1400701c5  mov     r8, 23F0021184Ch; struct UnionFs::StackEventTracer *
0x1400701cf  mov     rdx, rdi; int
0x1400701d2  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400701d7  jmp     loc_14007029D
0x1400701dc  mov     rax, [rax+18h]
0x1400701e0  mov     rdx, [rax+8]
0x1400701e4  mov     rcx, [rdx+20h]
0x1400701e8  test    rcx, rcx
0x1400701eb  jnz     short loc_1400701F1
0x1400701ed  mov     rcx, [rdx+30h]; Token
0x1400701f1  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1400701f6  mov     [rsp+38h+TokenInformation], 0
0x1400701ff  mov     edx, 1; TokenInformationClass
0x140070204  call    cs:__imp_SeQueryInformationToken
0x14007020b  nop     dword ptr [rax+rax+00h]
0x140070210  mov     ebx, eax
0x140070212  test    eax, eax
0x140070214  jns     short loc_14007023F
0x140070216  lea     rax, aApiGettingCall; "API: Getting caller's SID"
0x14007021d  mov     r8, 2370021185Ah; struct UnionFs::StackEventTracer *
0x140070227  lea     r9, aUnionfsUtilsGe_5; "UnionFs::Utils::GetUserSidString"
0x14007022e  mov     [rsp+38h+var_18], rax; char *
0x140070233  mov     rdx, rdi; int
0x140070236  mov     ecx, ebx; this
0x140070238  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14007023d  jmp     short loc_14007029D
0x14007023f  mov     rdx, [rsp+38h+TokenInformation]
0x140070244  mov     r8b, 1; AllocateDestinationString
0x140070247  mov     rcx, rsi; UnicodeString
0x14007024a  mov     rdx, [rdx]; Sid
0x14007024d  call    cs:__imp_RtlConvertSidToUnicodeString
0x140070254  nop     dword ptr [rax+rax+00h]
0x140070259  mov     ebx, eax
0x14007025b  test    eax, eax
0x14007025d  jns     short loc_140070288
0x14007025f  lea     rax, aApiConvertSidT; "API: Convert SID to string"
0x140070266  mov     r8, 23800211863h; struct UnionFs::StackEventTracer *
0x140070270  lea     r9, aUnionfsUtilsGe_5; "UnionFs::Utils::GetUserSidString"
0x140070277  mov     [rsp+38h+var_18], rax; char *
0x14007027c  mov     rdx, rdi; int
0x14007027f  mov     ecx, ebx; this
0x140070281  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140070286  jmp     short loc_14007028A
0x140070288  xor     ebx, ebx
0x14007028a  mov     rcx, [rsp+38h+TokenInformation]; P
0x14007028f  xor     edx, edx; Tag
0x140070291  call    cs:__imp_ExFreePoolWithTag
0x140070298  nop     dword ptr [rax+rax+00h]
0x14007029d  mov     rsi, [rsp+38h+arg_10]
0x1400702a2  mov     eax, ebx
0x1400702a4  mov     rbx, [rsp+38h+arg_8]
0x1400702a9  add     rsp, 30h
0x1400702ad  pop     rdi
0x1400702ae  retn
```
