# GetMandatoryLabel(ushort * *)

- ea: `0x18000cbb8`
- end: `0x18000cc9a`
- name: `?GetMandatoryLabel@@YAJPEAPEAG@Z`
- size: `226`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800066dc`

## callees

- `0x18000cbb8`
- `0x18000ce0c`
- `0x18000d488`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x18000cbf5`
- `ADVAPI32!OpenProcessToken` at `0x18000cbf5`
- `ADVAPI32!GetTokenInformation` at `0x18000cc20`
- `ADVAPI32!GetTokenInformation` at `0x18000cc5d`
- `ADVAPI32!GetTokenInformation` at `0x18000cc20`
- `ADVAPI32!GetTokenInformation` at `0x18000cc5d`
- `ADVAPI32!ConvertSidToStringSidW` at `0x18000cc6d`
- `ADVAPI32!ConvertSidToStringSidW` at `0x18000cc6d`
- `KERNEL32!GetLastError` at `0x18000cc2a`
- `KERNEL32!GetLastError` at `0x18000cc2a`
- `KERNEL32!CloseHandle` at `0x18000cc85`
- `KERNEL32!CloseHandle` at `0x18000cc85`
- `KERNEL32!GetCurrentProcess` at `0x18000cbe2`
- `KERNEL32!GetCurrentProcess` at `0x18000cbe2`

## pseudocode

```c
__int64 __fastcall GetMandatoryLabel(LPWSTR *StringSid)
{
  unsigned int v3; // ebx
  HANDLE CurrentProcess; // rax
  PSID *v5; // rsi
  DWORD TokenInformationLength; // [rsp+50h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+10h] BYREF

  if ( !StringSid )
    return 2147500035LL;
  v3 = -2147467259;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    TokenInformationLength = 0;
    if ( !GetTokenInformation(TokenHandle, TokenIntegrityLevel, 0, 0, &TokenInformationLength) && GetLastError() == 122 )
    {
      v5 = (PSID *)operator new[](TokenInformationLength);
      if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, v5, TokenInformationLength, &TokenInformationLength) )
      {
        if ( ConvertSidToStringSidW(*v5, StringSid) )
          v3 = 0;
      }
      operator delete(v5);
    }
    CloseHandle(TokenHandle);
  }
  return v3;
}

```

## disassembly

```asm
0x18000cbb8  mov     [rsp+arg_10], rbx
0x18000cbbd  push    rbp
0x18000cbbe  push    rsi
0x18000cbbf  push    rdi
0x18000cbc0  sub     rsp, 30h
0x18000cbc4  xor     ebp, ebp
0x18000cbc6  mov     rdi, rcx
0x18000cbc9  test    rcx, rcx
0x18000cbcc  jnz     short loc_18000CBD8
0x18000cbce  mov     eax, 80004003h
0x18000cbd3  jmp     loc_18000CC8D
0x18000cbd8  mov     ebx, 80004005h
0x18000cbdd  mov     [rsp+48h+TokenHandle], rbp
0x18000cbe2  call    cs:__imp_GetCurrentProcess
0x18000cbe8  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x18000cbed  mov     edx, 8; DesiredAccess
0x18000cbf2  mov     rcx, rax; ProcessHandle
0x18000cbf5  call    cs:__imp_OpenProcessToken
0x18000cbfb  test    eax, eax
0x18000cbfd  jz      loc_18000CC8B
0x18000cc03  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x18000cc08  lea     rax, [rsp+48h+TokenInformationLength]
0x18000cc0d  xor     r9d, r9d; TokenInformationLength
0x18000cc10  mov     [rsp+48h+TokenInformationLength], ebp
0x18000cc14  xor     r8d, r8d; TokenInformation
0x18000cc17  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000cc1c  lea     edx, [r9+19h]; TokenInformationClass
0x18000cc20  call    cs:__imp_GetTokenInformation
0x18000cc26  test    eax, eax
0x18000cc28  jnz     short loc_18000CC80
0x18000cc2a  call    cs:__imp_GetLastError
0x18000cc30  cmp     eax, 7Ah ; 'z'
0x18000cc33  jnz     short loc_18000CC80
0x18000cc35  mov     ecx, [rsp+48h+TokenInformationLength]; unsigned __int64
0x18000cc39  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000cc3e  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x18000cc43  mov     rsi, rax
0x18000cc46  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x18000cc4b  lea     rax, [rsp+48h+TokenInformationLength]
0x18000cc50  mov     r8, rsi; TokenInformation
0x18000cc53  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000cc58  mov     edx, 19h; TokenInformationClass
0x18000cc5d  call    cs:__imp_GetTokenInformation
0x18000cc63  test    eax, eax
0x18000cc65  jz      short loc_18000CC78
0x18000cc67  mov     rcx, [rsi]; Sid
0x18000cc6a  mov     rdx, rdi; StringSid
0x18000cc6d  call    cs:__imp_ConvertSidToStringSidW
0x18000cc73  test    eax, eax
0x18000cc75  cmovnz  ebx, ebp
0x18000cc78  mov     rcx, rsi; Block
0x18000cc7b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000cc80  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18000cc85  call    cs:__imp_CloseHandle
0x18000cc8b  mov     eax, ebx
0x18000cc8d  mov     rbx, [rsp+48h+arg_10]
0x18000cc92  add     rsp, 30h
0x18000cc96  pop     rdi
0x18000cc97  pop     rsi
0x18000cc98  pop     rbp
0x18000cc99  retn
```
