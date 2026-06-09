# TrustLabelAceHelpers::ApplyTrustLabelToReparsePoint(ushort const *)

- ea: `0x18008a6c0`
- end: `0x18008a98f`
- name: `?ApplyTrustLabelToReparsePoint@TrustLabelAceHelpers@@SAJPEBG@Z`
- size: `719`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18015f0b0`

## callees

- `0x18006cb78`
- `0x18008a6c0`
- `0x1800924fc`
- `0x180098bf4`
- `0x1800a021c`
- `0x1800a5504`
- `0x1800a5970`
- `0x1800f0700`
- `0x1800f0760`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008a976`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008a976`
- `ntdll!RtlCreateAcl` at `0x18008a7b7`
- `ntdll!RtlCreateAcl` at `0x18008a7b7`
- `ntdll!RtlAddProcessTrustLabelAce` at `0x18008a817`
- `ntdll!RtlAddProcessTrustLabelAce` at `0x18008a817`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18008a874`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18008a874`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18008a8c5`
- `ntdll!RtlSetSaclSecurityDescriptor` at `0x18008a8c5`
- `ntdll!NtSetSecurityObject` at `0x18008a916`
- `ntdll!NtSetSecurityObject` at `0x18008a916`
- `ntdll!RtlFreeSid` at `0x18008a96c`
- `ntdll!RtlFreeSid` at `0x18008a96c`
- `ntdll!RtlLengthSid` at `0x18008a799`
- `ntdll!RtlLengthSid` at `0x18008a799`
- `api-ms-win-security-base-l1-1-0!SetSecurityAccessMask` at `0x18008a6e2`
- `api-ms-win-security-base-l1-1-0!SetSecurityAccessMask` at `0x18008a6e2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008a70e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18008a70e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TrustLabelAceHelpers::ApplyTrustLabelToReparsePoint(LPCWSTR lpFileName)
{
  HANDLE FileW; // rsi
  const char *v3; // r9
  unsigned int LastError; // ebx
  int WindowsPplTrustLabelSid; // eax
  size_t v7; // rbx
  struct _ACL *v8; // rdi
  NTSTATUS Acl; // eax
  unsigned __int64 v10; // rdx
  int v11; // eax
  unsigned __int64 v12; // rdx
  NTSTATUS v13; // eax
  unsigned __int64 v14; // rdx
  NTSTATUS v15; // eax
  unsigned __int64 v16; // rdx
  NTSTATUS v17; // eax
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rdx
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-50h]
  _OWORD SecurityDescriptor[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v22; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  DWORD DesiredAccess; // [rsp+98h] [rbp+28h] BYREF
  PSID Sid; // [rsp+A0h] [rbp+30h] BYREF
  HANDLE v26; // [rsp+A8h] [rbp+38h] BYREF

  DesiredAccess = 0;
  SetSecurityAccessMask(0x80u, &DesiredAccess);
  FileW = CreateFileW(lpFileName, DesiredAccess, 7u, 0, 3u, 0x2200000u, 0);
  v26 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x5E,
                  (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelhelpersbase.cpp",
                  v3);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v26);
    return LastError;
  }
  Sid = 0;
  WindowsPplTrustLabelSid = TrustLabelAceHelpers::GetWindowsPplTrustLabelSid(&Sid);
  LastError = WindowsPplTrustLabelSid;
  if ( WindowsPplTrustLabelSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelhelpersbase.cpp",
      (const char *)(unsigned int)WindowsPplTrustLabelSid,
      dwCreationDisposition);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v26);
    return LastError;
  }
  v7 = RtlLengthSid(Sid) + 20;
  v8 = (struct _ACL *)operator new(v7);
  Acl = RtlCreateAcl(v8, v7, 2u);
  if ( Acl < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x67,
                  (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelhelpersbase.cpp",
                  (const char *)(unsigned int)Acl,
                  dwCreationDisposition);
    operator delete(v8, v10);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v26);
    return LastError;
  }
  LOBYTE(dwCreationDisposition) = 20;
  v11 = RtlAddProcessTrustLabelAce(v8, 2, 0, Sid);
  if ( v11 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x6E,
                  (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelhelpersbase.cpp",
                  (const char *)(unsigned int)v11,
                  dwCreationDisposition);
    operator delete(v8, v12);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v26);
    return LastError;
  }
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v22 = 0;
  v13 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( v13 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x71,
                  (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelhelpersbase.cpp",
                  (const char *)(unsigned int)v13,
                  dwCreationDisposition);
    operator delete(v8, v14);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v26);
    return LastError;
  }
  v15 = RtlSetSaclSecurityDescriptor(SecurityDescriptor, 1u, v8, 0);
  if ( v15 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x72,
                  (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelhelpersbase.cpp",
                  (const char *)(unsigned int)v15,
                  dwCreationDisposition);
    operator delete(v8, v16);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v26);
    return LastError;
  }
  v17 = NtSetSecurityObject(FileW, 0x80u, SecurityDescriptor);
  if ( v17 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x77,
                  (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelhelpersbase.cpp",
                  (const char *)(unsigned int)v17,
                  dwCreationDisposition);
    operator delete(v8, v19);
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&Sid);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v26);
    return LastError;
  }
  operator delete(v8, v18);
  if ( Sid )
    RtlFreeSid(Sid);
  CloseHandle(FileW);
  return 0;
}

```

## disassembly

```asm
0x18008a6c0  mov     [rsp-18h+arg_0], rbx
0x18008a6c5  push    rbp
0x18008a6c6  push    rsi
0x18008a6c7  push    rdi
0x18008a6c8  mov     rbp, rsp
0x18008a6cb  sub     rsp, 70h
0x18008a6cf  mov     rbx, rcx
0x18008a6d2  mov     [rbp+DesiredAccess], 0
0x18008a6d9  lea     rdx, [rbp+DesiredAccess]; DesiredAccess
0x18008a6dd  mov     ecx, 80h; SecurityInformation
0x18008a6e2  call    cs:__imp_SetSecurityAccessMask
0x18008a6e8  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x18008a6f1  mov     [rsp+70h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18008a6f9  mov     [rsp+70h+dwCreationDisposition], 3; int
0x18008a701  xor     r9d, r9d; lpSecurityAttributes
0x18008a704  lea     r8d, [r9+7]; dwShareMode
0x18008a708  mov     edx, [rbp+DesiredAccess]; dwDesiredAccess
0x18008a70b  mov     rcx, rbx; lpFileName
0x18008a70e  call    cs:__imp_CreateFileW
0x18008a714  mov     rsi, rax
0x18008a717  mov     [rbp+arg_18], rax
0x18008a71b  lea     rcx, [rax+1]
0x18008a71f  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18008a726  jnz     short loc_18008A750
0x18008a728  mov     rcx, [rbp+18h]; this
0x18008a72c  lea     r8, aOnecoreBaseApp_50; "onecore\\base\\appmodel\\trust\\trustla"...
0x18008a733  mov     edx, 5Eh ; '^'; void *
0x18008a738  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008a73d  mov     ebx, eax
0x18008a73f  lea     rcx, [rbp+arg_18]
0x18008a743  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008a748  nop
0x18008a749  mov     eax, ebx
0x18008a74b  jmp     loc_18008A97F
0x18008a750  mov     [rbp+Sid], 0
0x18008a758  lea     rcx, [rbp+Sid]; Sid
0x18008a75c  call    ?GetWindowsPplTrustLabelSid@TrustLabelAceHelpers@@SAJPEAPEAX@Z; TrustLabelAceHelpers::GetWindowsPplTrustLabelSid(void * *)
0x18008a761  mov     ebx, eax
0x18008a763  test    eax, eax
0x18008a765  jns     short loc_18008A795
0x18008a767  mov     rcx, [rbp+18h]; this
0x18008a76b  mov     r9d, eax; char *
0x18008a76e  lea     r8, aOnecoreBaseApp_50; "onecore\\base\\appmodel\\trust\\trustla"...
0x18008a775  mov     edx, 61h ; 'a'; void *
0x18008a77a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008a77f  lea     rcx, [rbp+Sid]
0x18008a783  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008a788  nop
0x18008a789  lea     rcx, [rbp+arg_18]
0x18008a78d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008a792  nop
0x18008a793  jmp     short loc_18008A749
0x18008a795  mov     rcx, [rbp+Sid]; Sid
0x18008a799  call    cs:__imp_RtlLengthSid
0x18008a79f  lea     ebx, [rax+14h]
0x18008a7a2  mov     ecx, ebx; Size
0x18008a7a4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18008a7a9  mov     rdi, rax
0x18008a7ac  mov     r8d, 2; AclRevision
0x18008a7b2  mov     edx, ebx; AclSize
0x18008a7b4  mov     rcx, rax; Acl
0x18008a7b7  call    cs:__imp_RtlCreateAcl
0x18008a7bd  test    eax, eax
0x18008a7bf  jns     short loc_18008A7FC
0x18008a7c1  mov     rcx, [rbp+18h]; this
0x18008a7c5  mov     r9d, eax; char *
0x18008a7c8  lea     r8, aOnecoreBaseApp_50; "onecore\\base\\appmodel\\trust\\trustla"...
0x18008a7cf  mov     edx, 67h ; 'g'; void *
0x18008a7d4  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18008a7d9  mov     ebx, eax
0x18008a7db  mov     rcx, rdi; void *
0x18008a7de  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18008a7e3  lea     rcx, [rbp+Sid]
0x18008a7e7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008a7ec  nop
0x18008a7ed  lea     rcx, [rbp+arg_18]
0x18008a7f1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008a7f6  nop
0x18008a7f7  jmp     loc_18008A749
0x18008a7fc  mov     [rsp+70h+dwFlagsAndAttributes], 1F01A9h
0x18008a804  mov     byte ptr [rsp+70h+dwCreationDisposition], 14h; int
0x18008a809  mov     r9, [rbp+Sid]
0x18008a80d  xor     r8d, r8d
0x18008a810  lea     edx, [r8+2]
0x18008a814  mov     rcx, rdi
0x18008a817  call    cs:__imp_RtlAddProcessTrustLabelAce
0x18008a81d  test    eax, eax
0x18008a81f  jns     short loc_18008A85C
0x18008a821  mov     rcx, [rbp+18h]; this
0x18008a825  mov     r9d, eax; char *
0x18008a828  lea     r8, aOnecoreBaseApp_50; "onecore\\base\\appmodel\\trust\\trustla"...
0x18008a82f  mov     edx, 6Eh ; 'n'; void *
0x18008a834  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18008a839  mov     ebx, eax
0x18008a83b  mov     rcx, rdi; void *
0x18008a83e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18008a843  lea     rcx, [rbp+Sid]
0x18008a847  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008a84c  nop
0x18008a84d  lea     rcx, [rbp+arg_18]
0x18008a851  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008a856  nop
0x18008a857  jmp     loc_18008A749
0x18008a85c  xorps   xmm0, xmm0
0x18008a85f  xor     eax, eax
0x18008a861  movups  [rbp+SecurityDescriptor], xmm0
0x18008a865  movups  [rbp+var_20], xmm0
0x18008a869  mov     [rbp+var_10], rax
0x18008a86d  lea     edx, [rax+1]; Revision
0x18008a870  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18008a874  call    cs:__imp_RtlCreateSecurityDescriptor
0x18008a87a  test    eax, eax
0x18008a87c  jns     short loc_18008A8B9
0x18008a87e  mov     rcx, [rbp+18h]; this
0x18008a882  mov     r9d, eax; char *
0x18008a885  lea     r8, aOnecoreBaseApp_50; "onecore\\base\\appmodel\\trust\\trustla"...
0x18008a88c  mov     edx, 71h ; 'q'; void *
0x18008a891  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18008a896  mov     ebx, eax
0x18008a898  mov     rcx, rdi; void *
0x18008a89b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18008a8a0  lea     rcx, [rbp+Sid]
0x18008a8a4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008a8a9  nop
0x18008a8aa  lea     rcx, [rbp+arg_18]
0x18008a8ae  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008a8b3  nop
0x18008a8b4  jmp     loc_18008A749
0x18008a8b9  xor     r9d, r9d; SaclDefaulted
0x18008a8bc  mov     r8, rdi; Sacl
0x18008a8bf  mov     dl, 1; SaclPresent
0x18008a8c1  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18008a8c5  call    cs:__imp_RtlSetSaclSecurityDescriptor
0x18008a8cb  test    eax, eax
0x18008a8cd  jns     short loc_18008A90A
0x18008a8cf  mov     rcx, [rbp+18h]; this
0x18008a8d3  mov     r9d, eax; char *
0x18008a8d6  lea     r8, aOnecoreBaseApp_50; "onecore\\base\\appmodel\\trust\\trustla"...
0x18008a8dd  mov     edx, 72h ; 'r'; void *
0x18008a8e2  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18008a8e7  mov     ebx, eax
0x18008a8e9  mov     rcx, rdi; void *
0x18008a8ec  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18008a8f1  lea     rcx, [rbp+Sid]
0x18008a8f5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008a8fa  nop
0x18008a8fb  lea     rcx, [rbp+arg_18]
0x18008a8ff  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008a904  nop
0x18008a905  jmp     loc_18008A749
0x18008a90a  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18008a90e  mov     edx, 80h; SecurityInformation
0x18008a913  mov     rcx, rsi; Handle
0x18008a916  call    cs:__imp_NtSetSecurityObject
0x18008a91c  test    eax, eax
0x18008a91e  jns     short loc_18008A95B
0x18008a920  mov     rcx, [rbp+18h]; this
0x18008a924  mov     r9d, eax; char *
0x18008a927  lea     r8, aOnecoreBaseApp_50; "onecore\\base\\appmodel\\trust\\trustla"...
0x18008a92e  mov     edx, 77h ; 'w'; void *
0x18008a933  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18008a938  mov     ebx, eax
0x18008a93a  mov     rcx, rdi; void *
0x18008a93d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18008a942  lea     rcx, [rbp+Sid]
0x18008a946  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?RtlFreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&RtlFreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18008a94b  nop
0x18008a94c  lea     rcx, [rbp+arg_18]
0x18008a950  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18008a955  nop
0x18008a956  jmp     loc_18008A749
0x18008a95b  mov     rcx, rdi; void *
0x18008a95e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18008a963  mov     rcx, [rbp+Sid]; Sid
0x18008a967  test    rcx, rcx
0x18008a96a  jz      short loc_18008A973
0x18008a96c  call    cs:__imp_RtlFreeSid
0x18008a972  nop
0x18008a973  mov     rcx, rsi; hObject
0x18008a976  call    cs:__imp_CloseHandle
0x18008a97c  nop
0x18008a97d  xor     eax, eax
0x18008a97f  mov     rbx, [rsp+70h+arg_0]
0x18008a987  add     rsp, 70h
0x18008a98b  pop     rdi
0x18008a98c  pop     rsi
0x18008a98d  pop     rbp
0x18008a98e  retn
```
