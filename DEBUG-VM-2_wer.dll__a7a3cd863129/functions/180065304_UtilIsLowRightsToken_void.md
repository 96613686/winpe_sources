# UtilIsLowRightsToken(void *)

- ea: `0x180065304`
- end: `0x180065406`
- name: `?UtilIsLowRightsToken@@YAJPEAX@Z`
- size: `258`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006528c`

## callees

- `0x180050db0`
- `0x1800517cc`
- `0x180065304`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065365`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800653a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180065365`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800653a6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006535b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006539c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006535b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006539c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800653da`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1800653da`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800653ca`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x1800653ca`

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
0x180065304  push    rbx
0x180065306  sub     rsp, 0B0h
0x18006530d  mov     rax, cs:__security_cookie
0x180065314  xor     rax, rsp
0x180065317  mov     [rsp+0B8h+var_18], rax
0x18006531f  xor     edx, edx; Val
0x180065321  mov     rbx, rcx
0x180065324  lea     rcx, [rsp+0B8h+pSid]; void *
0x180065329  lea     r8d, [rdx+58h]; Size
0x18006532d  call    memset_0
0x180065332  mov     r9d, 4; TokenInformationLength
0x180065338  mov     [rsp+0B8h+TokenInformation], 0
0x180065340  lea     rax, [rsp+0B8h+var_84]
0x180065345  mov     [rsp+0B8h+var_84], r9d
0x18006534a  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x18006534f  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180065354  mov     rcx, rbx; TokenHandle
0x180065357  lea     edx, [r9+19h]; TokenInformationClass
0x18006535b  call    cs:__imp_GetTokenInformation
0x180065361  test    eax, eax
0x180065363  jnz     short loc_1800653BA
0x180065365  call    cs:__imp_GetLastError
0x18006536b  test    eax, eax
0x18006536d  jle     short loc_180065379
0x18006536f  movzx   eax, ax
0x180065372  or      eax, 80070000h
0x180065377  test    eax, eax
0x180065379  jz      short loc_1800653C1
0x18006537b  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180065381  lea     rax, [rsp+0B8h+var_80]
0x180065386  lea     r8, [rsp+0B8h+pSid]; TokenInformation
0x18006538b  mov     [rsp+0B8h+var_80], r9d
0x180065390  mov     rcx, rbx; TokenHandle
0x180065393  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180065398  lea     edx, [r9-3Bh]; TokenInformationClass
0x18006539c  call    cs:__imp_GetTokenInformation
0x1800653a2  test    eax, eax
0x1800653a4  jnz     short loc_1800653C5
0x1800653a6  call    cs:__imp_GetLastError
0x1800653ac  test    eax, eax
0x1800653ae  jle     short loc_1800653ED
0x1800653b0  movzx   eax, ax
0x1800653b3  or      eax, 80070000h
0x1800653b8  jmp     short loc_1800653ED
0x1800653ba  cmp     [rsp+0B8h+TokenInformation], 0
0x1800653bf  jz      short loc_18006537B
0x1800653c1  xor     eax, eax
0x1800653c3  jmp     short loc_1800653ED
0x1800653c5  mov     rcx, [rsp+0B8h+pSid]; pSid
0x1800653ca  call    cs:__imp_GetSidSubAuthorityCount
0x1800653d0  mov     rcx, [rsp+0B8h+pSid]; pSid
0x1800653d5  movzx   edx, byte ptr [rax]
0x1800653d8  dec     edx; nSubAuthority
0x1800653da  call    cs:__imp_GetSidSubAuthority
0x1800653e0  xor     ecx, ecx
0x1800653e2  cmp     dword ptr [rax], 2000h
0x1800653e8  setnb   cl
0x1800653eb  mov     eax, ecx
0x1800653ed  mov     rcx, [rsp+0B8h+var_18]
0x1800653f5  xor     rcx, rsp; StackCookie
0x1800653f8  call    __security_check_cookie
0x1800653fd  add     rsp, 0B0h
0x180065404  pop     rbx
0x180065405  retn
```
