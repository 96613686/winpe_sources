# _anonymous_namespace_::IsWizardUser

- ea: `0x14000ed9c`
- end: `0x14000ee85`
- name: `_anonymous_namespace_::IsWizardUser`
- size: `233`
- prototype: `char()`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation`

## callers

- `0x14000d3a0`

## callees

- `0x1400029a8`
- `0x14000eca4`
- `0x14000ed9c`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x14000edf0`
- `ADVAPI32!GetTokenInformation` at `0x14000ee2e`
- `ADVAPI32!GetTokenInformation` at `0x14000edf0`
- `ADVAPI32!GetTokenInformation` at `0x14000ee2e`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14000ee47`
- `ADVAPI32!ConvertSidToStringSidW` at `0x14000ee47`
- `ADVAPI32!OpenProcessToken` at `0x14000edc4`
- `ADVAPI32!OpenProcessToken` at `0x14000edc4`
- `KERNEL32!GetLastError` at `0x14000edfa`
- `KERNEL32!GetLastError` at `0x14000edfa`
- `KERNEL32!CloseHandle` at `0x14000ee74`
- `KERNEL32!CloseHandle` at `0x14000ee74`
- `KERNEL32!LocalFree` at `0x14000ee61`
- `KERNEL32!LocalFree` at `0x14000ee61`
- `KERNEL32!GetCurrentProcess` at `0x14000edb2`
- `KERNEL32!GetCurrentProcess` at `0x14000edb2`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000ee6a`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14000ee6a`

## pseudocode

```c
char anonymous_namespace_::IsWizardUser()
{
  char v0; // di
  HANDLE CurrentProcess; // rax
  void **v2; // rbx
  void *v3; // rcx
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
      if ( v2 )
      {
        if ( GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength) )
        {
          v3 = *v2;
          StringSid = 0;
          if ( ConvertSidToStringSidW(v3, &StringSid) )
          {
            v0 = IsWizardOnlyAccount(StringSid);
            LocalFree(StringSid);
          }
        }
        operator delete[](v2);
      }
    }
    CloseHandle(TokenHandle);
  }
  return v0;
}

```

## disassembly

```asm
0x14000ed9c  push    rbp
0x14000ed9e  push    rbx
0x14000ed9f  push    rdi
0x14000eda0  mov     rbp, rsp
0x14000eda3  sub     rsp, 30h
0x14000eda7  xor     dil, dil
0x14000edaa  mov     [rbp+TokenHandle], 0
0x14000edb2  call    cs:__imp_GetCurrentProcess
0x14000edb8  lea     r8, [rbp+TokenHandle]; TokenHandle
0x14000edbc  mov     edx, 8; DesiredAccess
0x14000edc1  mov     rcx, rax; ProcessHandle
0x14000edc4  call    cs:__imp_OpenProcessToken
0x14000edca  test    eax, eax
0x14000edcc  jz      loc_14000EE7A
0x14000edd2  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14000edd6  lea     rax, [rbp+TokenInformationLength]
0x14000edda  xor     r9d, r9d; TokenInformationLength
0x14000eddd  mov     [rbp+TokenInformationLength], 0
0x14000ede4  xor     r8d, r8d; TokenInformation
0x14000ede7  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x14000edec  lea     edx, [r9+1]; TokenInformationClass
0x14000edf0  call    cs:__imp_GetTokenInformation
0x14000edf6  test    eax, eax
0x14000edf8  jnz     short loc_14000EE70
0x14000edfa  call    cs:__imp_GetLastError
0x14000ee00  cmp     eax, 7Ah ; 'z'
0x14000ee03  jnz     short loc_14000EE70
0x14000ee05  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x14000ee08  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14000ee0d  mov     rbx, rax
0x14000ee10  test    rax, rax
0x14000ee13  jz      short loc_14000EE70
0x14000ee15  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x14000ee19  lea     rax, [rbp+TokenInformationLength]
0x14000ee1d  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x14000ee21  mov     r8, rbx; TokenInformation
0x14000ee24  mov     edx, 1; TokenInformationClass
0x14000ee29  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x14000ee2e  call    cs:__imp_GetTokenInformation
0x14000ee34  test    eax, eax
0x14000ee36  jz      short loc_14000EE67
0x14000ee38  mov     rcx, [rbx]; Sid
0x14000ee3b  lea     rdx, [rbp+StringSid]; StringSid
0x14000ee3f  mov     [rbp+StringSid], 0
0x14000ee47  call    cs:__imp_ConvertSidToStringSidW
0x14000ee4d  test    eax, eax
0x14000ee4f  jz      short loc_14000EE67
0x14000ee51  mov     rcx, [rbp+StringSid]; unsigned __int16 *
0x14000ee55  call    ?IsWizardOnlyAccount@@YA_NPEBG@Z; IsWizardOnlyAccount(ushort const *)
0x14000ee5a  mov     rcx, [rbp+StringSid]; hMem
0x14000ee5e  mov     dil, al
0x14000ee61  call    cs:__imp_LocalFree
0x14000ee67  mov     rcx, rbx
0x14000ee6a  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14000ee70  mov     rcx, [rbp+TokenHandle]; hObject
0x14000ee74  call    cs:__imp_CloseHandle
0x14000ee7a  mov     al, dil
0x14000ee7d  add     rsp, 30h
0x14000ee81  pop     rdi
0x14000ee82  pop     rbx
0x14000ee83  pop     rbp
0x14000ee84  retn
```
