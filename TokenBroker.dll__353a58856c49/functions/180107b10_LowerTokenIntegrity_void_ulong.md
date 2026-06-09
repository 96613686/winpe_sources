# LowerTokenIntegrity(void *,ulong)

- ea: `0x180107b10`
- end: `0x180107bca`
- name: `?LowerTokenIntegrity@@YAKPEAXK@Z`
- size: `186`
- prototype: `unsigned int __fastcall(HANDLE TokenHandle, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801074e8`

## callees

- `0x18008e690`
- `0x180107b10`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180107b97`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180107b97`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180107b3c`
- `api-ms-win-security-base-l1-1-0!GetSidLengthRequired` at `0x180107b3c`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180107b6d`
- `api-ms-win-security-base-l1-1-0!InitializeSid` at `0x180107b6d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180107b78`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180107b78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180107ba1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180107ba1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180107bac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180107bac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180107b49`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180107b49`

## pseudocode

```c
__int64 __fastcall LowerTokenIntegrity(HANDLE TokenHandle)
{
  DWORD v2; // esi
  _QWORD *v3; // rax
  _QWORD *v4; // rdi
  DWORD LastError; // ebx
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+20h] [rbp-38h] BYREF

  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 4096;
  v2 = GetSidLengthRequired(1u) + 16;
  v3 = LocalAlloc(0, v2);
  v4 = v3;
  if ( v3 )
  {
    *v3 = v3 + 2;
    LastError = 0;
    InitializeSid(v3 + 2, &pIdentifierAuthority, 1u);
    *GetSidSubAuthority((PSID)*v4, 0) = 4096;
    *((_DWORD *)v4 + 2) = 96;
    if ( !SetTokenInformation(TokenHandle, TokenIntegrityLevel, v4, v2) )
      LastError = GetLastError();
  }
  else
  {
    LastError = 8;
  }
  LocalFree(v4);
  return LastError;
}

```

## disassembly

```asm
0x180107b10  push    rbx
0x180107b12  push    rbp
0x180107b13  push    rsi
0x180107b14  push    rdi
0x180107b15  sub     rsp, 38h
0x180107b19  mov     rax, cs:__security_cookie
0x180107b20  xor     rax, rsp
0x180107b23  mov     [rsp+58h+var_30], rax
0x180107b28  mov     rbp, rcx
0x180107b2b  mov     dword ptr [rsp+58h+pIdentifierAuthority.Value], 0
0x180107b33  mov     cl, 1; nSubAuthorityCount
0x180107b35  mov     word ptr [rsp+58h+pIdentifierAuthority.Value+4], 1000h
0x180107b3c  call    cs:__imp_GetSidLengthRequired
0x180107b42  xor     ecx, ecx; uFlags
0x180107b44  lea     esi, [rax+10h]
0x180107b47  mov     edx, esi; uBytes
0x180107b49  call    cs:__imp_LocalAlloc
0x180107b4f  mov     rdi, rax
0x180107b52  test    rax, rax
0x180107b55  jnz     short loc_180107B5C
0x180107b57  lea     ebx, [rax+8]
0x180107b5a  jmp     short loc_180107BA9
0x180107b5c  lea     rcx, [rax+10h]; Sid
0x180107b60  mov     r8b, 1; nSubAuthorityCount
0x180107b63  lea     rdx, [rsp+58h+pIdentifierAuthority]; pIdentifierAuthority
0x180107b68  mov     [rax], rcx
0x180107b6b  xor     ebx, ebx
0x180107b6d  call    cs:__imp_InitializeSid
0x180107b73  mov     rcx, [rdi]; pSid
0x180107b76  xor     edx, edx; nSubAuthority
0x180107b78  call    cs:__imp_GetSidSubAuthority
0x180107b7e  mov     r9d, esi; TokenInformationLength
0x180107b81  lea     edx, [rbx+19h]; TokenInformationClass
0x180107b84  mov     r8, rdi; TokenInformation
0x180107b87  mov     rcx, rbp; TokenHandle
0x180107b8a  mov     dword ptr [rax], 1000h
0x180107b90  mov     dword ptr [rdi+8], 60h ; '`'
0x180107b97  call    cs:__imp_SetTokenInformation
0x180107b9d  test    eax, eax
0x180107b9f  jnz     short loc_180107BA9
0x180107ba1  call    cs:__imp_GetLastError
0x180107ba7  mov     ebx, eax
0x180107ba9  mov     rcx, rdi; hMem
0x180107bac  call    cs:__imp_LocalFree
0x180107bb2  mov     eax, ebx
0x180107bb4  mov     rcx, [rsp+58h+var_30]
0x180107bb9  xor     rcx, rsp; StackCookie
0x180107bbc  call    __security_check_cookie
0x180107bc1  add     rsp, 38h
0x180107bc5  pop     rdi
0x180107bc6  pop     rsi
0x180107bc7  pop     rbp
0x180107bc8  pop     rbx
0x180107bc9  retn
```
