# UnionFs::Utils::QuerySecurity(_FLT_INSTANCE const &,_FILE_OBJECT const &,utl::unique_ptr<_SECURITY_DESCRIPTOR,utl::default_delete<_SECURITY_DESCRIPTOR>> &,UnionFs::StackEventTracer &,ulong)

- ea: `0x14007599c`
- end: `0x140075b02`
- name: `?QuerySecurity@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAV?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$default_delete@U_SECURITY_DESCRIPTOR@@@utl@@@utl@@AEAVStackEventTracer@2@K@Z`
- size: `358`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, SECURITY_INFORMATION SecurityInformation)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14006c3ec`
- `0x14006e1a0`
- `0x1400735d4`

## callees

- `0x140056bd0`
- `0x140056c44`
- `0x140067b48`
- `0x14007599c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140075acb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075ae8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075acb`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075ae8`
- `FLTMGR!FltQuerySecurityObject` at `0x1400759d8`
- `FLTMGR!FltQuerySecurityObject` at `0x140075a88`
- `FLTMGR!FltQuerySecurityObject` at `0x1400759d8`
- `FLTMGR!FltQuerySecurityObject` at `0x140075a88`

## string_xrefs

- `0x140075a02`: `UnionFs::Utils::QuerySecurity`
- `0x140075a4a`: `UnionFs::Utils::QuerySecurity`
- `0x140075aab`: `UnionFs::Utils::QuerySecurity`
- `0x140075a9a`: `API: Querying source security`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::QuerySecurity(
        PFLT_INSTANCE Instance,
        PFILE_OBJECT FileObject,
        void **a3,
        int a4,
        SECURITY_INFORMATION SecurityInformation)
{
  NTSTATUS v9; // eax
  unsigned int v10; // ebx
  PSECURITY_DESCRIPTOR v12; // rbx
  NTSTATUS v13; // edi
  void *v14; // rcx
  const char *LengthNeeded; // [rsp+28h] [rbp-40h]
  const char *LengthNeededa; // [rsp+28h] [rbp-40h]
  ULONG Length; // [rsp+30h] [rbp-38h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor[6]; // [rsp+38h] [rbp-30h] BYREF

  Length = 0;
  v9 = FltQuerySecurityObject(Instance, FileObject, SecurityInformation, 0, 0, &Length);
  v10 = v9;
  if ( v9 != -1073741789 && v9 < 0 )
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v9,
      a4,
      (struct UnionFs::StackEventTracer *)0x266002118B3LL,
      (unsigned __int64)"UnionFs::Utils::QuerySecurity",
      "API: Getting SD size",
      LengthNeeded);
    return v10;
  }
  utl::make_unique_pool<enum gsl::byte [0],256,1685276245,0>(SecurityDescriptor, Length);
  v12 = SecurityDescriptor[0];
  if ( !SecurityDescriptor[0] )
  {
    v10 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a4,
      (struct UnionFs::StackEventTracer *)0x267002118BELL,
      (unsigned __int64)"UnionFs::Utils::QuerySecurity",
      "ORIGIN: Allocating SD buffer",
      LengthNeeded);
    return v10;
  }
  v13 = FltQuerySecurityObject(Instance, FileObject, SecurityInformation, SecurityDescriptor[0], Length, &Length);
  if ( v13 >= 0 )
  {
    v14 = *a3;
    *a3 = v12;
    if ( v14 )
      ExFreePoolWithTag(v14, 0);
    return 0;
  }
  else
  {
    UnionFs::ProcessTraceStatusFromApi(
      (UnionFs *)(unsigned int)v13,
      a4,
      (struct UnionFs::StackEventTracer *)0x268002118C8LL,
      (unsigned __int64)"UnionFs::Utils::QuerySecurity",
      "API: Querying source security",
      LengthNeededa);
    if ( v12 )
      ExFreePoolWithTag(v12, 0);
    return (unsigned int)v13;
  }
}

```

## disassembly

```asm
0x14007599c  push    rbx
0x14007599e  push    rbp
0x14007599f  push    rsi
0x1400759a0  push    rdi
0x1400759a1  push    r14
0x1400759a3  sub     rsp, 40h
0x1400759a7  lea     rax, [rsp+68h+var_38]
0x1400759ac  mov     [rsp+68h+var_38], 0
0x1400759b4  mov     rsi, r9
0x1400759b7  mov     [rsp+68h+LengthNeeded], rax; char *
0x1400759bc  mov     r14, r8
0x1400759bf  mov     [rsp+68h+Length], 0; Length
0x1400759c7  mov     r8d, [rsp+68h+SecurityInformation]; SecurityInformation
0x1400759cf  xor     r9d, r9d; SecurityDescriptor
0x1400759d2  mov     rdi, rdx
0x1400759d5  mov     rbp, rcx
0x1400759d8  call    cs:__imp_FltQuerySecurityObject
0x1400759df  nop     dword ptr [rax+rax+00h]
0x1400759e4  mov     ebx, eax
0x1400759e6  cmp     eax, 0C0000023h
0x1400759eb  jz      short loc_140075A1F
0x1400759ed  test    eax, eax
0x1400759ef  jns     short loc_140075A1F
0x1400759f1  lea     rax, aApiGettingSdSi; "API: Getting SD size"
0x1400759f8  mov     r8, 266002118B3h; struct UnionFs::StackEventTracer *
0x140075a02  lea     r9, aUnionfsUtilsQu_0; "UnionFs::Utils::QuerySecurity"
0x140075a09  mov     qword ptr [rsp+68h+Length], rax; char *
0x140075a0e  mov     rdx, rsi; int
0x140075a11  mov     ecx, ebx; this
0x140075a13  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140075a18  mov     eax, ebx
0x140075a1a  jmp     loc_140075AF6
0x140075a1f  mov     edx, [rsp+68h+var_38]
0x140075a23  lea     rcx, [rsp+68h+SecurityDescriptor]
0x140075a28  call    ??$make_unique_pool@$$BY0A@W4byte@gsl@@$0BAA@$0GEHDEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@_K@Z; utl::make_unique_pool<gsl::byte [0],256,1685276245,0>(unsigned __int64)
0x140075a2d  mov     rbx, [rsp+68h+SecurityDescriptor]
0x140075a32  test    rbx, rbx
0x140075a35  jnz     short loc_140075A65
0x140075a37  lea     rax, aOriginAllocati_44; "ORIGIN: Allocating SD buffer"
0x140075a3e  mov     ebx, 0C000009Ah
0x140075a43  mov     ecx, ebx; this
0x140075a45  mov     qword ptr [rsp+68h+Length], rax; char *
0x140075a4a  lea     r9, aUnionfsUtilsQu_0; "UnionFs::Utils::QuerySecurity"
0x140075a51  mov     r8, 267002118BEh; struct UnionFs::StackEventTracer *
0x140075a5b  mov     rdx, rsi; int
0x140075a5e  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140075a63  jmp     short loc_140075A18
0x140075a65  mov     eax, [rsp+68h+var_38]
0x140075a69  lea     rcx, [rsp+68h+var_38]
0x140075a6e  mov     r8d, [rsp+68h+SecurityInformation]; SecurityInformation
0x140075a76  mov     r9, rbx; SecurityDescriptor
0x140075a79  mov     [rsp+68h+LengthNeeded], rcx; char *
0x140075a7e  mov     rdx, rdi; FileObject
0x140075a81  mov     rcx, rbp; Instance
0x140075a84  mov     [rsp+68h+Length], eax; Length
0x140075a88  call    cs:__imp_FltQuerySecurityObject
0x140075a8f  nop     dword ptr [rax+rax+00h]
0x140075a94  mov     edi, eax
0x140075a96  test    eax, eax
0x140075a98  jns     short loc_140075ADB
0x140075a9a  lea     rax, aApiQueryingSou_0; "API: Querying source security"
0x140075aa1  mov     r8, 268002118C8h; struct UnionFs::StackEventTracer *
0x140075aab  lea     r9, aUnionfsUtilsQu_0; "UnionFs::Utils::QuerySecurity"
0x140075ab2  mov     qword ptr [rsp+68h+Length], rax; char *
0x140075ab7  mov     rdx, rsi; int
0x140075aba  mov     ecx, edi; this
0x140075abc  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140075ac1  test    rbx, rbx
0x140075ac4  jz      short loc_140075AD7
0x140075ac6  xor     edx, edx; Tag
0x140075ac8  mov     rcx, rbx; P
0x140075acb  call    cs:__imp_ExFreePoolWithTag
0x140075ad2  nop     dword ptr [rax+rax+00h]
0x140075ad7  mov     eax, edi
0x140075ad9  jmp     short loc_140075AF6
0x140075adb  mov     rcx, [r14]; P
0x140075ade  mov     [r14], rbx
0x140075ae1  test    rcx, rcx
0x140075ae4  jz      short loc_140075AF4
0x140075ae6  xor     edx, edx; Tag
0x140075ae8  call    cs:__imp_ExFreePoolWithTag
0x140075aef  nop     dword ptr [rax+rax+00h]
0x140075af4  xor     eax, eax
0x140075af6  add     rsp, 40h
0x140075afa  pop     r14
0x140075afc  pop     rdi
0x140075afd  pop     rsi
0x140075afe  pop     rbp
0x140075aff  pop     rbx
0x140075b00  retn
```
