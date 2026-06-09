# _anonymous_namespace_::IsWizardUser

- ea: `0x18039b174`
- end: `0x18039b2aa`
- name: `_anonymous_namespace_::IsWizardUser`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180399e2c`

## callees

- `0x180040f94`
- `0x180098f4c`
- `0x1801432d4`
- `0x1801451d0`
- `0x18039b094`
- `0x18039b174`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18039b1e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18039b1e7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18039b1a1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18039b1a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18039b189`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18039b189`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039b293`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18039b293`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18039b27b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18039b27b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18039b1d3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18039b220`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18039b1d3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18039b220`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18039b23f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18039b23f`

## pseudocode

```c
bool anonymous_namespace_::IsWizardUser()
{
  bool v0; // bl
  HANDLE CurrentProcess; // rax
  void **v2; // rdi
  const struct std::nothrow_t *v3; // rdx
  void *v4; // rcx
  const unsigned __int16 *v5; // rbx
  DWORD TokenInformationLength; // [rsp+50h] [rbp+20h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+28h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp+30h] BYREF

  v0 = 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    TokenInformationLength = 0;
    if ( !GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() == 122 )
    {
      v2 = (void **)operator new[](TokenInformationLength);
      if ( GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength) )
      {
        v4 = *v2;
        StringSid = 0;
        if ( ConvertSidToStringSidW(v4, &StringSid) )
        {
          v5 = StringSid;
          v0 = IsUserOOBE() || IsCredentialReset() || IsCamCxhOnlyUser(v5);
          LocalFree(StringSid);
        }
      }
      operator delete(v2, v3);
    }
    CloseHandle(TokenHandle);
  }
  return v0;
}

```

## disassembly

```asm
0x18039b174  push    rbp
0x18039b176  push    rbx
0x18039b177  push    rdi
0x18039b178  mov     rbp, rsp
0x18039b17b  sub     rsp, 30h
0x18039b17f  xor     bl, bl
0x18039b181  mov     [rbp+TokenHandle], 0
0x18039b189  call    cs:__imp_GetCurrentProcess
0x18039b190  nop     dword ptr [rax+rax+00h]
0x18039b195  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18039b199  mov     edx, 8; DesiredAccess
0x18039b19e  mov     rcx, rax; ProcessHandle
0x18039b1a1  call    cs:__imp_OpenProcessToken
0x18039b1a8  nop     dword ptr [rax+rax+00h]
0x18039b1ad  test    eax, eax
0x18039b1af  jz      loc_18039B29F
0x18039b1b5  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18039b1b9  lea     rax, [rbp+TokenInformationLength]
0x18039b1bd  xor     r9d, r9d; TokenInformationLength
0x18039b1c0  mov     [rbp+TokenInformationLength], 0
0x18039b1c7  xor     r8d, r8d; TokenInformation
0x18039b1ca  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18039b1cf  lea     edx, [r9+1]; TokenInformationClass
0x18039b1d3  call    cs:__imp_GetTokenInformation
0x18039b1da  nop     dword ptr [rax+rax+00h]
0x18039b1df  test    eax, eax
0x18039b1e1  jnz     loc_18039B28F
0x18039b1e7  call    cs:__imp_GetLastError
0x18039b1ee  nop     dword ptr [rax+rax+00h]
0x18039b1f3  cmp     eax, 7Ah ; 'z'
0x18039b1f6  jnz     loc_18039B28F
0x18039b1fc  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x18039b1ff  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18039b204  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18039b208  mov     rdi, rax
0x18039b20b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18039b20f  lea     rax, [rbp+TokenInformationLength]
0x18039b213  mov     r8, rdi; TokenInformation
0x18039b216  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18039b21b  mov     edx, 1; TokenInformationClass
0x18039b220  call    cs:__imp_GetTokenInformation
0x18039b227  nop     dword ptr [rax+rax+00h]
0x18039b22c  test    eax, eax
0x18039b22e  jz      short loc_18039B287
0x18039b230  mov     rcx, [rdi]; Sid
0x18039b233  lea     rdx, [rbp+StringSid]; StringSid
0x18039b237  mov     [rbp+StringSid], 0
0x18039b23f  call    cs:__imp_ConvertSidToStringSidW
0x18039b246  nop     dword ptr [rax+rax+00h]
0x18039b24b  test    eax, eax
0x18039b24d  jz      short loc_18039B287
0x18039b24f  mov     rbx, [rbp+StringSid]
0x18039b253  call    ?IsUserOOBE@@YA_NXZ; IsUserOOBE(void)
0x18039b258  test    al, al
0x18039b25a  jnz     short loc_18039B275
0x18039b25c  call    ?IsCredentialReset@@YA_NXZ; IsCredentialReset(void)
0x18039b261  test    al, al
0x18039b263  jnz     short loc_18039B275
0x18039b265  mov     rcx, rbx; unsigned __int16 *
0x18039b268  call    ?IsCamCxhOnlyUser@@YA_NPEBG@Z; IsCamCxhOnlyUser(ushort const *)
0x18039b26d  test    al, al
0x18039b26f  jnz     short loc_18039B275
0x18039b271  xor     bl, bl
0x18039b273  jmp     short loc_18039B277
0x18039b275  mov     bl, 1
0x18039b277  mov     rcx, [rbp+StringSid]; hMem
0x18039b27b  call    cs:__imp_LocalFree
0x18039b282  nop     dword ptr [rax+rax+00h]
0x18039b287  mov     rcx, rdi; void *
0x18039b28a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18039b28f  mov     rcx, [rbp+TokenHandle]; hObject
0x18039b293  call    cs:__imp_CloseHandle
0x18039b29a  nop     dword ptr [rax+rax+00h]
0x18039b29f  mov     al, bl
0x18039b2a1  add     rsp, 30h
0x18039b2a5  pop     rdi
0x18039b2a6  pop     rbx
0x18039b2a7  pop     rbp
0x18039b2a8  retn
```
