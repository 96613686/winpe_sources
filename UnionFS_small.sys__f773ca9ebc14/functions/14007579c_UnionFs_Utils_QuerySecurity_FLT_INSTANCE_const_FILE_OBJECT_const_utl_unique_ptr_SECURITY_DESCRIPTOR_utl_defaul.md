# UnionFs::Utils::QuerySecurity(_FLT_INSTANCE const &,_FILE_OBJECT const &,utl::unique_ptr<_SECURITY_DESCRIPTOR,utl::default_delete<_SECURITY_DESCRIPTOR>> &,UnionFs::StackEventTracer &,ulong)

- ea: `0x14007579c`
- end: `0x140075902`
- name: `?QuerySecurity@Utils@UnionFs@@YAJAEBU_FLT_INSTANCE@@AEBU_FILE_OBJECT@@AEAV?$unique_ptr@U_SECURITY_DESCRIPTOR@@U?$default_delete@U_SECURITY_DESCRIPTOR@@@utl@@@utl@@AEAVStackEventTracer@2@K@Z`
- size: `358`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, PFILE_OBJECT FileObject@<rdx>, SECURITY_INFORMATION SecurityInformation)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14006c1fc`
- `0x14006dfb0`
- `0x1400733b0`

## callees

- `0x140056a50`
- `0x140056ac4`
- `0x1400679c8`
- `0x14007579c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400758cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400758e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400758cb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400758e8`
- `FLTMGR!FltQuerySecurityObject` at `0x1400757d8`
- `FLTMGR!FltQuerySecurityObject` at `0x140075888`
- `FLTMGR!FltQuerySecurityObject` at `0x1400757d8`
- `FLTMGR!FltQuerySecurityObject` at `0x140075888`

## string_xrefs

- `0x140075802`: `UnionFs::Utils::QuerySecurity`
- `0x14007584a`: `UnionFs::Utils::QuerySecurity`
- `0x1400758ab`: `UnionFs::Utils::QuerySecurity`
- `0x14007589a`: `API: Querying source security`

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
      (struct UnionFs::StackEventTracer *)0x2660021187DLL,
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
      (struct UnionFs::StackEventTracer *)0x26700211888LL,
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
      (struct UnionFs::StackEventTracer *)0x26800211892LL,
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
0x14007579c  push    rbx
0x14007579e  push    rbp
0x14007579f  push    rsi
0x1400757a0  push    rdi
0x1400757a1  push    r14
0x1400757a3  sub     rsp, 40h
0x1400757a7  lea     rax, [rsp+68h+var_38]
0x1400757ac  mov     [rsp+68h+var_38], 0
0x1400757b4  mov     rsi, r9
0x1400757b7  mov     [rsp+68h+LengthNeeded], rax; char *
0x1400757bc  mov     r14, r8
0x1400757bf  mov     [rsp+68h+Length], 0; Length
0x1400757c7  mov     r8d, [rsp+68h+SecurityInformation]; SecurityInformation
0x1400757cf  xor     r9d, r9d; SecurityDescriptor
0x1400757d2  mov     rdi, rdx
0x1400757d5  mov     rbp, rcx
0x1400757d8  call    cs:__imp_FltQuerySecurityObject
0x1400757df  nop     dword ptr [rax+rax+00h]
0x1400757e4  mov     ebx, eax
0x1400757e6  cmp     eax, 0C0000023h
0x1400757eb  jz      short loc_14007581F
0x1400757ed  test    eax, eax
0x1400757ef  jns     short loc_14007581F
0x1400757f1  lea     rax, aApiGettingSdSi; "API: Getting SD size"
0x1400757f8  mov     r8, 2660021187Dh; struct UnionFs::StackEventTracer *
0x140075802  lea     r9, aUnionfsUtilsQu_0; "UnionFs::Utils::QuerySecurity"
0x140075809  mov     qword ptr [rsp+68h+Length], rax; char *
0x14007580e  mov     rdx, rsi; int
0x140075811  mov     ecx, ebx; this
0x140075813  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140075818  mov     eax, ebx
0x14007581a  jmp     loc_1400758F6
0x14007581f  mov     edx, [rsp+68h+var_38]
0x140075823  lea     rcx, [rsp+68h+SecurityDescriptor]
0x140075828  call    ??$make_unique_pool@$$BY0A@W4byte@gsl@@$0BAA@$0GEHDEGFF@$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@W4byte@gsl@@U?$default_delete@$$BY0A@W4byte@gsl@@@utl@@@0@_K@Z; utl::make_unique_pool<gsl::byte [0],256,1685276245,0>(unsigned __int64)
0x14007582d  mov     rbx, [rsp+68h+SecurityDescriptor]
0x140075832  test    rbx, rbx
0x140075835  jnz     short loc_140075865
0x140075837  lea     rax, aOriginAllocati_43; "ORIGIN: Allocating SD buffer"
0x14007583e  mov     ebx, 0C000009Ah
0x140075843  mov     ecx, ebx; this
0x140075845  mov     qword ptr [rsp+68h+Length], rax; char *
0x14007584a  lea     r9, aUnionfsUtilsQu_0; "UnionFs::Utils::QuerySecurity"
0x140075851  mov     r8, 26700211888h; struct UnionFs::StackEventTracer *
0x14007585b  mov     rdx, rsi; int
0x14007585e  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140075863  jmp     short loc_140075818
0x140075865  mov     eax, [rsp+68h+var_38]
0x140075869  lea     rcx, [rsp+68h+var_38]
0x14007586e  mov     r8d, [rsp+68h+SecurityInformation]; SecurityInformation
0x140075876  mov     r9, rbx; SecurityDescriptor
0x140075879  mov     [rsp+68h+LengthNeeded], rcx; char *
0x14007587e  mov     rdx, rdi; FileObject
0x140075881  mov     rcx, rbp; Instance
0x140075884  mov     [rsp+68h+Length], eax; Length
0x140075888  call    cs:__imp_FltQuerySecurityObject
0x14007588f  nop     dword ptr [rax+rax+00h]
0x140075894  mov     edi, eax
0x140075896  test    eax, eax
0x140075898  jns     short loc_1400758DB
0x14007589a  lea     rax, aApiQueryingSou_0; "API: Querying source security"
0x1400758a1  mov     r8, 26800211892h; struct UnionFs::StackEventTracer *
0x1400758ab  lea     r9, aUnionfsUtilsQu_0; "UnionFs::Utils::QuerySecurity"
0x1400758b2  mov     qword ptr [rsp+68h+Length], rax; char *
0x1400758b7  mov     rdx, rsi; int
0x1400758ba  mov     ecx, edi; this
0x1400758bc  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400758c1  test    rbx, rbx
0x1400758c4  jz      short loc_1400758D7
0x1400758c6  xor     edx, edx; Tag
0x1400758c8  mov     rcx, rbx; P
0x1400758cb  call    cs:__imp_ExFreePoolWithTag
0x1400758d2  nop     dword ptr [rax+rax+00h]
0x1400758d7  mov     eax, edi
0x1400758d9  jmp     short loc_1400758F6
0x1400758db  mov     rcx, [r14]; P
0x1400758de  mov     [r14], rbx
0x1400758e1  test    rcx, rcx
0x1400758e4  jz      short loc_1400758F4
0x1400758e6  xor     edx, edx; Tag
0x1400758e8  call    cs:__imp_ExFreePoolWithTag
0x1400758ef  nop     dword ptr [rax+rax+00h]
0x1400758f4  xor     eax, eax
0x1400758f6  add     rsp, 40h
0x1400758fa  pop     r14
0x1400758fc  pop     rdi
0x1400758fd  pop     rsi
0x1400758fe  pop     rbp
0x1400758ff  pop     rbx
0x140075900  retn
```
