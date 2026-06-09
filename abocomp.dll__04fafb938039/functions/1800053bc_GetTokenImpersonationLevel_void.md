# GetTokenImpersonationLevel(void *)

- ea: `0x1800053bc`
- end: `0x180005424`
- name: `?GetTokenImpersonationLevel@@YA?AW4_SECURITY_IMPERSONATION_LEVEL@@PEAX@Z`
- size: `104`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000b68c`

## callees

- `0x180001f90`
- `0x1800053bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053f3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800053e9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800053e9`

## string_xrefs

- `0x18000540c`: `Error (%X) getting Token impersonation`

## pseudocode

```c
__int64 __fastcall GetTokenImpersonationLevel(void *a1)
{
  signed int LastError; // eax
  unsigned int TokenInformation; // [rsp+48h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+50h] [rbp+18h] BYREF

  TokenInformation = 0;
  ReturnLength = 0;
  if ( !GetTokenInformation(a1, TokenImpersonationLevel, &TokenInformation, 4u, &ReturnLength) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    ABO_MAPPER_LOG::WriteLogEntry(g_pAboLog, L"Error (%X) getting Token impersonation", (unsigned int)LastError);
  }
  return TokenInformation;
}

```

## disassembly

```asm
0x1800053bc  sub     rsp, 38h
0x1800053c0  mov     r9d, 4; TokenInformationLength
0x1800053c6  mov     [rsp+38h+TokenInformation], 0
0x1800053ce  lea     rax, [rsp+38h+arg_10]
0x1800053d3  mov     [rsp+38h+arg_10], 0
0x1800053db  lea     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1800053e0  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1800053e5  lea     edx, [r9+5]; TokenInformationClass
0x1800053e9  call    cs:__imp_GetTokenInformation
0x1800053ef  test    eax, eax
0x1800053f1  jnz     short loc_18000541B
0x1800053f3  call    cs:__imp_GetLastError
0x1800053f9  test    eax, eax
0x1800053fb  jle     short loc_180005405
0x1800053fd  movzx   eax, ax
0x180005400  or      eax, 80070000h
0x180005405  mov     rcx, cs:?g_pAboLog@@3PEAVABO_MAPPER_LOG@@EA; this
0x18000540c  lea     rdx, aErrorXGettingT; "Error (%X) getting Token impersonation"
0x180005413  mov     r8d, eax
0x180005416  call    ?WriteLogEntry@ABO_MAPPER_LOG@@QEAAJPEBGZZ; ABO_MAPPER_LOG::WriteLogEntry(ushort const *,...)
0x18000541b  mov     eax, [rsp+38h+TokenInformation]
0x18000541f  add     rsp, 38h
0x180005423  retn
```
