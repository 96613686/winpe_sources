# _anonymous_namespace_::SecurityDescriptorAndAcls::SecurityDescriptorAndAcls

- ea: `0x1800642b8`
- end: `0x180064486`
- name: `_anonymous_namespace_::SecurityDescriptorAndAcls::SecurityDescriptorAndAcls`
- size: `462`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18006448c`
- `0x180064768`
- `0x1800648fc`
- `0x180064a3c`

## callees

- `0x180010f24`
- `0x1800642b8`
- `0x1800dddf4`
- `0x1800e3a00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800643e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800643e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800643f9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800643f9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180064383`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180064383`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800643f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006440d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800643f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006440d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800642f6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800642f6`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18006432b`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18006432b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800643b9`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800643b9`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18006435f`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAceEx` at `0x18006435f`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18006439b`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x18006439b`

## string_xrefs

- `0x18006443e`: `C:\__w\1\s\src\orchestrator\system\windows\common\PrivateNamespaceHelpers.cpp`
- `0x180064450`: `C:\__w\1\s\src\orchestrator\system\windows\common\PrivateNamespaceHelpers.cpp`
- `0x180064462`: `C:\__w\1\s\src\orchestrator\system\windows\common\PrivateNamespaceHelpers.cpp`
- `0x180064474`: `C:\__w\1\s\src\orchestrator\system\windows\common\PrivateNamespaceHelpers.cpp`

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
  v8 = (struct _ACL *)operator new[](v5, (const struct std::nothrow_t *)&std::nothrow);
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
    operator delete(v18, (const struct std::nothrow_t *)8);
  return a1;
}

```

## disassembly

```asm
0x1800642b8  mov     [rsp+arg_10], rbx
0x1800642bd  push    rbp
0x1800642be  push    rsi
0x1800642bf  push    rdi
0x1800642c0  push    r14
0x1800642c2  push    r15
0x1800642c4  sub     rsp, 50h
0x1800642c8  mov     rdi, rdx
0x1800642cb  mov     r14, rcx
0x1800642ce  mov     [rsp+78h+var_40], rcx
0x1800642d3  mov     qword ptr [rcx], 0
0x1800642da  lea     r15, [rcx+8]
0x1800642de  mov     qword ptr [r15], 0
0x1800642e5  mov     ebp, 8
0x1800642ea  mov     rsi, [rdx+8]
0x1800642ee  mov     rbx, [rdx]
0x1800642f1  jmp     short loc_180064305
0x1800642f3  mov     rcx, [rbx]; pSid
0x1800642f6  call    cs:__imp_GetLengthSid
0x1800642fc  add     ebp, 0Ch
0x1800642ff  add     ebp, eax
0x180064301  add     rbx, 8
0x180064305  cmp     rbx, rsi
0x180064308  jnz     short loc_1800642F3
0x18006430a  mov     ecx, ebp; unsigned __int64
0x18006430c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180064313  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180064318  mov     rsi, rax
0x18006431b  mov     [rsp+78h+var_38], rax
0x180064320  mov     r8d, 2; dwAclRevision
0x180064326  mov     edx, ebp; nAclLength
0x180064328  mov     rcx, rax; pAcl
0x18006432b  call    cs:__imp_InitializeAcl
0x180064331  mov     rcx, [rsp+78h]; this
0x180064336  test    eax, eax
0x180064338  jz      loc_180064450
0x18006433e  mov     rbx, [rdi]
0x180064341  mov     rdi, [rdi+8]
0x180064345  jmp     short loc_180064376
0x180064347  mov     rax, [rbx]
0x18006434a  mov     [rsp+78h+pSid], rax; pSid
0x18006434f  mov     r9d, 10000000h; AccessMask
0x180064355  xor     r8d, r8d; AceFlags
0x180064358  lea     edx, [r8+2]; dwAceRevision
0x18006435c  mov     rcx, rsi; pAcl
0x18006435f  call    cs:__imp_AddAccessAllowedAceEx
0x180064365  mov     rcx, [rsp+78h]; this
0x18006436a  test    eax, eax
0x18006436c  jz      loc_180064474
0x180064372  add     rbx, 8
0x180064376  cmp     rbx, rdi
0x180064379  jnz     short loc_180064347
0x18006437b  mov     edx, 28h ; '('; uBytes
0x180064380  lea     ecx, [rdx+18h]; uFlags
0x180064383  call    cs:__imp_LocalAlloc
0x180064389  mov     rbx, rax
0x18006438c  mov     [rsp+78h+var_48], rax
0x180064391  mov     edi, 1
0x180064396  mov     edx, edi; dwRevision
0x180064398  mov     rcx, rax; pSecurityDescriptor
0x18006439b  call    cs:__imp_InitializeSecurityDescriptor
0x1800643a1  mov     rcx, [rsp+78h]; this
0x1800643a6  test    eax, eax
0x1800643a8  jz      loc_180064462
0x1800643ae  xor     r9d, r9d; bDaclDefaulted
0x1800643b1  mov     r8, rsi; pDacl
0x1800643b4  mov     edx, edi; bDaclPresent
0x1800643b6  mov     rcx, rbx; pSecurityDescriptor
0x1800643b9  call    cs:__imp_SetSecurityDescriptorDacl
0x1800643bf  mov     rcx, [rsp+78h]; this
0x1800643c4  test    eax, eax
0x1800643c6  jz      short loc_18006443E
0x1800643c8  mov     rdi, [r15]
0x1800643cb  mov     qword ptr [r15], 0
0x1800643d2  lea     rax, [rsp+78h+var_48]
0x1800643d7  cmp     r15, rax
0x1800643da  jz      short loc_1800643E1
0x1800643dc  mov     [r15], rbx
0x1800643df  jmp     short loc_1800643FF
0x1800643e1  test    rbx, rbx
0x1800643e4  jz      short loc_1800643FF
0x1800643e6  call    cs:__imp_GetLastError
0x1800643ec  mov     ebp, eax
0x1800643ee  mov     rcx, rbx; hMem
0x1800643f1  call    cs:__imp_LocalFree
0x1800643f7  mov     ecx, ebp; dwErrCode
0x1800643f9  call    cs:__imp_SetLastError
0x1800643ff  mov     rbx, [r14]
0x180064402  mov     [r14], rsi
0x180064405  test    rdi, rdi
0x180064408  jz      short loc_180064414
0x18006440a  mov     rcx, rdi; hMem
0x18006440d  call    cs:__imp_LocalFree
0x180064413  nop
0x180064414  test    rbx, rbx
0x180064417  jz      short loc_180064427
0x180064419  mov     edx, 8; struct std::nothrow_t *
0x18006441e  mov     rcx, rbx; void *
0x180064421  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180064426  nop
0x180064427  mov     rax, r14
0x18006442a  mov     rbx, [rsp+78h+arg_10]
0x180064432  add     rsp, 50h
0x180064436  pop     r15
0x180064438  pop     r14
0x18006443a  pop     rdi
0x18006443b  pop     rsi
0x18006443c  pop     rbp
0x18006443d  retn
0x18006443e  lea     r8, aCW1SSrcOrchest; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180064445  mov     edx, 55h ; 'U'; void *
0x18006444a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180064450  lea     r8, aCW1SSrcOrchest; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180064457  mov     edx, 4Ch ; 'L'; void *
0x18006445c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180064462  lea     r8, aCW1SSrcOrchest; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x180064469  mov     edx, 54h ; 'T'; void *
0x18006446e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180064474  lea     r8, aCW1SSrcOrchest; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18006447b  mov     edx, 4Fh ; 'O'; void *
0x180064480  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
