# _anonymous_namespace_::SecurityDescriptorAndAcls::SecurityDescriptorAndAcls

- ea: `0x140072a98`
- end: `0x140072c66`
- name: `_anonymous_namespace_::SecurityDescriptorAndAcls::SecurityDescriptorAndAcls`
- size: `462`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400230ec`
- `0x140072c6c`
- `0x140072f48`
- `0x1400730a4`

## callees

- `0x14003c578`
- `0x140072a98`
- `0x1403790cc`
- `0x140379480`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140072bd9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140072bd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140072bc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140072bc6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140072bd1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140072bed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140072bd1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140072bed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140072b63`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140072b63`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140072b7b`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140072b7b`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140072b0b`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x140072b0b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140072ad6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140072ad6`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140072b99`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140072b99`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x140072b3f`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x140072b3f`

## string_xrefs

- `0x140072c1e`: `C:\__w\1\s\src\orchestrator\system\windows\common\PrivateNamespaceHelpers.cpp`
- `0x140072c30`: `C:\__w\1\s\src\orchestrator\system\windows\common\PrivateNamespaceHelpers.cpp`
- `0x140072c42`: `C:\__w\1\s\src\orchestrator\system\windows\common\PrivateNamespaceHelpers.cpp`
- `0x140072c54`: `C:\__w\1\s\src\orchestrator\system\windows\common\PrivateNamespaceHelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
struct _ACL **__fastcall anonymous_namespace_::SecurityDescriptorAndAcls::SecurityDescriptorAndAcls(
        struct _ACL **a1,
        PSID **a2)
{
  void **v4; // r15
  DWORD v5; // ebp
  PSID *v6; // rsi
  PSID *i; // rbx
  struct _ACL *v8; // rsi
  const char *v9; // r9
  PSID *v10; // rbx
  PSID *v11; // rdi
  const char *v12; // r9
  HLOCAL v13; // rbx
  const char *v14; // r9
  const char *v15; // r9
  void *v16; // rdi
  DWORD LastError; // ebp
  struct _ACL *v18; // rbx
  _QWORD v20[9]; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v20[1] = a1;
  *a1 = 0;
  v4 = (void **)(a1 + 1);
  a1[1] = 0;
  v5 = 8;
  v6 = a2[1];
  for ( i = *a2; i != v6; ++i )
    v5 += GetLengthSid(*i) + 12;
  v8 = (struct _ACL *)operator new[](v5, (const struct std::nothrow_t *)std::nothrow);
  v20[2] = v8;
  if ( !InitializeAcl(v8, v5, 2u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x4C,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\PrivateNamespaceHelpers.cpp",
      v9);
  v10 = *a2;
  v11 = a2[1];
  while ( v10 != v11 )
  {
    if ( !AddAccessAllowedAceEx(v8, 2u, 0, 0x10000000u, *v10) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x4F,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\PrivateNamespaceHelpers.cpp",
        v12);
    ++v10;
  }
  v13 = LocalAlloc(0x40u, 0x28u);
  v20[0] = v13;
  if ( !InitializeSecurityDescriptor(v13, 1u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x54,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\PrivateNamespaceHelpers.cpp",
      v14);
  if ( !SetSecurityDescriptorDacl(v13, 1, v8, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x55,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\PrivateNamespaceHelpers.cpp",
      v15);
  v16 = *v4;
  *v4 = 0;
  if ( v4 == v20 )
  {
    if ( v13 )
    {
      LastError = GetLastError();
      LocalFree(v13);
      SetLastError(LastError);
    }
  }
  else
  {
    *v4 = v13;
  }
  v18 = *a1;
  *a1 = v8;
  if ( v16 )
    LocalFree(v16);
  if ( v18 )
    operator delete(v18);
  return a1;
}

```

## disassembly

```asm
0x140072a98  mov     [rsp+arg_10], rbx
0x140072a9d  push    rbp
0x140072a9e  push    rsi
0x140072a9f  push    rdi
0x140072aa0  push    r14
0x140072aa2  push    r15
0x140072aa4  sub     rsp, 50h
0x140072aa8  mov     rdi, rdx
0x140072aab  mov     r14, rcx
0x140072aae  mov     [rsp+78h+var_40], rcx
0x140072ab3  mov     qword ptr [rcx], 0
0x140072aba  lea     r15, [rcx+8]
0x140072abe  mov     qword ptr [r15], 0
0x140072ac5  mov     ebp, 8
0x140072aca  mov     rsi, [rdx+8]
0x140072ace  mov     rbx, [rdx]
0x140072ad1  jmp     short loc_140072AE5
0x140072ad3  mov     rcx, [rbx]; pSid
0x140072ad6  call    cs:__imp_GetLengthSid
0x140072adc  add     ebp, 0Ch
0x140072adf  add     ebp, eax
0x140072ae1  add     rbx, 8
0x140072ae5  cmp     rbx, rsi
0x140072ae8  jnz     short loc_140072AD3
0x140072aea  mov     ecx, ebp; unsigned __int64
0x140072aec  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140072af3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140072af8  mov     rsi, rax
0x140072afb  mov     [rsp+78h+var_38], rax
0x140072b00  mov     r8d, 2; dwAclRevision
0x140072b06  mov     edx, ebp; nAclLength
0x140072b08  mov     rcx, rax; pAcl
0x140072b0b  call    cs:__imp_InitializeAcl
0x140072b11  mov     rcx, [rsp+78h]; this
0x140072b16  test    eax, eax
0x140072b18  jz      loc_140072C30
0x140072b1e  mov     rbx, [rdi]
0x140072b21  mov     rdi, [rdi+8]
0x140072b25  jmp     short loc_140072B56
0x140072b27  mov     rax, [rbx]
0x140072b2a  mov     [rsp+78h+pSid], rax; pSid
0x140072b2f  mov     r9d, 10000000h; AccessMask
0x140072b35  xor     r8d, r8d; AceFlags
0x140072b38  lea     edx, [r8+2]; dwAceRevision
0x140072b3c  mov     rcx, rsi; pAcl
0x140072b3f  call    cs:__imp_AddAccessAllowedAceEx
0x140072b45  mov     rcx, [rsp+78h]; this
0x140072b4a  test    eax, eax
0x140072b4c  jz      loc_140072C54
0x140072b52  add     rbx, 8
0x140072b56  cmp     rbx, rdi
0x140072b59  jnz     short loc_140072B27
0x140072b5b  mov     edx, 28h ; '('; uBytes
0x140072b60  lea     ecx, [rdx+18h]; uFlags
0x140072b63  call    cs:__imp_LocalAlloc
0x140072b69  mov     rbx, rax
0x140072b6c  mov     [rsp+78h+var_48], rax
0x140072b71  mov     edi, 1
0x140072b76  mov     edx, edi; dwRevision
0x140072b78  mov     rcx, rax; pSecurityDescriptor
0x140072b7b  call    cs:__imp_InitializeSecurityDescriptor
0x140072b81  mov     rcx, [rsp+78h]; this
0x140072b86  test    eax, eax
0x140072b88  jz      loc_140072C42
0x140072b8e  xor     r9d, r9d; bDaclDefaulted
0x140072b91  mov     r8, rsi; pDacl
0x140072b94  mov     edx, edi; bDaclPresent
0x140072b96  mov     rcx, rbx; pSecurityDescriptor
0x140072b99  call    cs:__imp_SetSecurityDescriptorDacl
0x140072b9f  mov     rcx, [rsp+78h]; this
0x140072ba4  test    eax, eax
0x140072ba6  jz      short loc_140072C1E
0x140072ba8  mov     rdi, [r15]
0x140072bab  mov     qword ptr [r15], 0
0x140072bb2  lea     rax, [rsp+78h+var_48]
0x140072bb7  cmp     r15, rax
0x140072bba  jz      short loc_140072BC1
0x140072bbc  mov     [r15], rbx
0x140072bbf  jmp     short loc_140072BDF
0x140072bc1  test    rbx, rbx
0x140072bc4  jz      short loc_140072BDF
0x140072bc6  call    cs:__imp_GetLastError
0x140072bcc  mov     ebp, eax
0x140072bce  mov     rcx, rbx; hMem
0x140072bd1  call    cs:__imp_LocalFree
0x140072bd7  mov     ecx, ebp; dwErrCode
0x140072bd9  call    cs:__imp_SetLastError
0x140072bdf  mov     rbx, [r14]
0x140072be2  mov     [r14], rsi
0x140072be5  test    rdi, rdi
0x140072be8  jz      short loc_140072BF4
0x140072bea  mov     rcx, rdi; hMem
0x140072bed  call    cs:__imp_LocalFree
0x140072bf3  nop
0x140072bf4  test    rbx, rbx
0x140072bf7  jz      short loc_140072C07
0x140072bf9  mov     edx, 8
0x140072bfe  mov     rcx, rbx; Block
0x140072c01  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140072c06  nop
0x140072c07  mov     rax, r14
0x140072c0a  mov     rbx, [rsp+78h+arg_10]
0x140072c12  add     rsp, 50h
0x140072c16  pop     r15
0x140072c18  pop     r14
0x140072c1a  pop     rdi
0x140072c1b  pop     rsi
0x140072c1c  pop     rbp
0x140072c1d  retn
0x140072c1e  lea     r8, aCW1SSrcOrchest_0; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140072c25  mov     edx, 55h ; 'U'; void *
0x140072c2a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140072c30  lea     r8, aCW1SSrcOrchest_0; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140072c37  mov     edx, 4Ch ; 'L'; void *
0x140072c3c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140072c42  lea     r8, aCW1SSrcOrchest_0; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140072c49  mov     edx, 54h ; 'T'; void *
0x140072c4e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140072c54  lea     r8, aCW1SSrcOrchest_0; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140072c5b  mov     edx, 4Fh ; 'O'; void *
0x140072c60  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
