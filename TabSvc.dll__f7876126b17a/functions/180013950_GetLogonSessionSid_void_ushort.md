# GetLogonSessionSid(void *,ushort * *)

- ea: `0x180013950`
- end: `0x180013a00`
- name: `?GetLogonSessionSid@@YAJPEAXPEAPEAG@Z`
- size: `176`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, LPWSTR *StringSid)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800169d0`
- `0x180023f54`
- `0x180024260`
- `0x1800282a0`

## callees

- `0x180013950`
- `0x18001bc04`
- `0x18001bff0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001398f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800139ca`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001398f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800139ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013999`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013999`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800139e0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800139e0`

## pseudocode

```c
__int64 __fastcall GetLogonSessionSid(HANDLE TokenHandle, LPWSTR *StringSid)
{
  unsigned int v5; // ebx
  PSID *v6; // rdi
  const struct std::nothrow_t *v7; // rdx
  DWORD TokenInformationLength; // [rsp+68h] [rbp+10h] BYREF

  if ( !StringSid )
    return 2147500035LL;
  TokenInformationLength = 0;
  v5 = -2147467259;
  if ( !GetTokenInformation(TokenHandle, TokenLogonSid, 0, 0, &TokenInformationLength) && GetLastError() == 122 )
  {
    v6 = (PSID *)operator new[](TokenInformationLength);
    if ( GetTokenInformation(TokenHandle, TokenLogonSid, v6, TokenInformationLength, &TokenInformationLength)
      && *(_DWORD *)v6 == 1 )
    {
      if ( ConvertSidToStringSidW(v6[1], StringSid) )
        v5 = 0;
    }
    operator delete(v6, v7);
  }
  return v5;
}

```

## disassembly

```asm
0x180013950  push    rbx
0x180013952  push    rbp
0x180013953  push    rsi
0x180013954  push    rdi
0x180013955  sub     rsp, 38h
0x180013959  mov     rsi, rdx
0x18001395c  mov     rbp, rcx
0x18001395f  test    rdx, rdx
0x180013962  jnz     short loc_18001396E
0x180013964  mov     eax, 80004003h
0x180013969  jmp     loc_1800139F7
0x18001396e  xor     r9d, r9d; TokenInformationLength
0x180013971  mov     [rsp+58h+TokenInformationLength], 0
0x180013979  lea     rax, [rsp+58h+TokenInformationLength]
0x18001397e  xor     r8d, r8d; TokenInformation
0x180013981  mov     ebx, 80004005h
0x180013986  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18001398b  lea     edx, [r9+1Ch]; TokenInformationClass
0x18001398f  call    cs:__imp_GetTokenInformation
0x180013995  test    eax, eax
0x180013997  jnz     short loc_1800139F5
0x180013999  call    cs:__imp_GetLastError
0x18001399f  cmp     eax, 7Ah ; 'z'
0x1800139a2  jnz     short loc_1800139F5
0x1800139a4  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x1800139a8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800139ad  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x1800139b2  mov     rdi, rax
0x1800139b5  lea     rax, [rsp+58h+TokenInformationLength]
0x1800139ba  mov     r8, rdi; TokenInformation
0x1800139bd  mov     edx, 1Ch; TokenInformationClass
0x1800139c2  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800139c7  mov     rcx, rbp; TokenHandle
0x1800139ca  call    cs:__imp_GetTokenInformation
0x1800139d0  test    eax, eax
0x1800139d2  jz      short loc_1800139ED
0x1800139d4  cmp     dword ptr [rdi], 1
0x1800139d7  jnz     short loc_1800139ED
0x1800139d9  mov     rcx, [rdi+8]; Sid
0x1800139dd  mov     rdx, rsi; StringSid
0x1800139e0  call    cs:__imp_ConvertSidToStringSidW
0x1800139e6  xor     ecx, ecx
0x1800139e8  test    eax, eax
0x1800139ea  cmovnz  ebx, ecx
0x1800139ed  mov     rcx, rdi; void *
0x1800139f0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800139f5  mov     eax, ebx
0x1800139f7  add     rsp, 38h
0x1800139fb  pop     rdi
0x1800139fc  pop     rsi
0x1800139fd  pop     rbp
0x1800139fe  pop     rbx
0x1800139ff  retn
```
