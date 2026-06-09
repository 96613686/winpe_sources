# UtilIsLowRightsToken(void *)

- ea: `0x1400118fc`
- end: `0x1400119fe`
- name: `?UtilIsLowRightsToken@@YAJPEAX@Z`
- size: `258`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001280c`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x1400118fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001195d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001199e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001195d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001199e`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1400119c2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1400119c2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140011953`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140011994`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140011953`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140011994`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400119d2`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400119d2`

## pseudocode

```c
signed int __fastcall UtilIsLowRightsToken(HANDLE TokenHandle)
{
  signed int LastError; // eax
  bool v3; // zf
  signed int result; // eax
  PUCHAR SidSubAuthorityCount; // rax
  int TokenInformation; // [rsp+30h] [rbp-88h] BYREF
  DWORD ReturnLength; // [rsp+34h] [rbp-84h] BYREF
  DWORD v8; // [rsp+38h] [rbp-80h] BYREF
  PSID pSid[12]; // [rsp+40h] [rbp-78h] BYREF

  memset_0(pSid, 0, 0x58u);
  TokenInformation = 0;
  ReturnLength = 4;
  if ( !GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
  {
    LastError = GetLastError();
    v3 = LastError == 0;
    if ( LastError > 0 )
      v3 = 0;
    if ( !v3 )
      goto LABEL_5;
    return 0;
  }
  if ( TokenInformation )
    return 0;
LABEL_5:
  v8 = 84;
  if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, pSid, 0x54u, &v8) )
  {
    SidSubAuthorityCount = GetSidSubAuthorityCount(pSid[0]);
    return *GetSidSubAuthority(pSid[0], (unsigned int)*SidSubAuthorityCount - 1) >= 0x2000;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x1400118fc  push    rbx
0x1400118fe  sub     rsp, 0B0h
0x140011905  mov     rax, cs:__security_cookie
0x14001190c  xor     rax, rsp
0x14001190f  mov     [rsp+0B8h+var_18], rax
0x140011917  xor     edx, edx; Val
0x140011919  mov     rbx, rcx
0x14001191c  lea     rcx, [rsp+0B8h+pSid]; void *
0x140011921  lea     r8d, [rdx+58h]; Size
0x140011925  call    memset_0
0x14001192a  mov     r9d, 4; TokenInformationLength
0x140011930  mov     [rsp+0B8h+TokenInformation], 0
0x140011938  lea     rax, [rsp+0B8h+var_84]
0x14001193d  mov     [rsp+0B8h+var_84], r9d
0x140011942  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x140011947  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x14001194c  mov     rcx, rbx; TokenHandle
0x14001194f  lea     edx, [r9+19h]; TokenInformationClass
0x140011953  call    cs:__imp_GetTokenInformation
0x140011959  test    eax, eax
0x14001195b  jnz     short loc_1400119B2
0x14001195d  call    cs:__imp_GetLastError
0x140011963  test    eax, eax
0x140011965  jle     short loc_140011971
0x140011967  movzx   eax, ax
0x14001196a  or      eax, 80070000h
0x14001196f  test    eax, eax
0x140011971  jz      short loc_1400119B9
0x140011973  mov     r9d, 54h ; 'T'; TokenInformationLength
0x140011979  lea     rax, [rsp+0B8h+var_80]
0x14001197e  lea     r8, [rsp+0B8h+pSid]; TokenInformation
0x140011983  mov     [rsp+0B8h+var_80], r9d
0x140011988  mov     rcx, rbx; TokenHandle
0x14001198b  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x140011990  lea     edx, [r9-3Bh]; TokenInformationClass
0x140011994  call    cs:__imp_GetTokenInformation
0x14001199a  test    eax, eax
0x14001199c  jnz     short loc_1400119BD
0x14001199e  call    cs:__imp_GetLastError
0x1400119a4  test    eax, eax
0x1400119a6  jle     short loc_1400119E5
0x1400119a8  movzx   eax, ax
0x1400119ab  or      eax, 80070000h
0x1400119b0  jmp     short loc_1400119E5
0x1400119b2  cmp     [rsp+0B8h+TokenInformation], 0
0x1400119b7  jz      short loc_140011973
0x1400119b9  xor     eax, eax
0x1400119bb  jmp     short loc_1400119E5
0x1400119bd  mov     rcx, [rsp+0B8h+pSid]; pSid
0x1400119c2  call    cs:__imp_GetSidSubAuthorityCount
0x1400119c8  mov     rcx, [rsp+0B8h+pSid]; pSid
0x1400119cd  movzx   edx, byte ptr [rax]
0x1400119d0  dec     edx; nSubAuthority
0x1400119d2  call    cs:__imp_GetSidSubAuthority
0x1400119d8  xor     ecx, ecx
0x1400119da  cmp     dword ptr [rax], 2000h
0x1400119e0  setnb   cl
0x1400119e3  mov     eax, ecx
0x1400119e5  mov     rcx, [rsp+0B8h+var_18]
0x1400119ed  xor     rcx, rsp; StackCookie
0x1400119f0  call    __security_check_cookie
0x1400119f5  add     rsp, 0B0h
0x1400119fc  pop     rbx
0x1400119fd  retn
```
