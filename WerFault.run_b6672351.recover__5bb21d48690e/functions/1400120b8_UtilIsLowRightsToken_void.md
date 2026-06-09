# UtilIsLowRightsToken(void *)

- ea: `0x1400120b8`
- end: `0x1400121df`
- name: `?UtilIsLowRightsToken@@YAJPEAX@Z`
- size: `295`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400130f8`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x1400120b8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001211f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001216c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001211f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001216c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x140012196`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x140012196`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001210f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001215c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001210f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001215c`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400121ac`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x1400121ac`

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
0x1400120b8  push    rbx
0x1400120ba  sub     rsp, 0B0h
0x1400120c1  mov     rax, cs:__security_cookie
0x1400120c8  xor     rax, rsp
0x1400120cb  mov     [rsp+0B8h+var_18], rax
0x1400120d3  xor     edx, edx; Val
0x1400120d5  mov     rbx, rcx
0x1400120d8  lea     rcx, [rsp+0B8h+pSid]; void *
0x1400120dd  lea     r8d, [rdx+58h]; Size
0x1400120e1  call    memset_0
0x1400120e6  mov     r9d, 4; TokenInformationLength
0x1400120ec  mov     [rsp+0B8h+TokenInformation], 0
0x1400120f4  lea     rax, [rsp+0B8h+var_84]
0x1400120f9  mov     [rsp+0B8h+var_84], r9d
0x1400120fe  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x140012103  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x140012108  mov     rcx, rbx; TokenHandle
0x14001210b  lea     edx, [r9+19h]; TokenInformationClass
0x14001210f  call    cs:__imp_GetTokenInformation
0x140012116  nop     dword ptr [rax+rax+00h]
0x14001211b  test    eax, eax
0x14001211d  jnz     short loc_140012186
0x14001211f  call    cs:__imp_GetLastError
0x140012126  nop     dword ptr [rax+rax+00h]
0x14001212b  test    eax, eax
0x14001212d  jle     short loc_140012139
0x14001212f  movzx   eax, ax
0x140012132  or      eax, 80070000h
0x140012137  test    eax, eax
0x140012139  jz      short loc_14001218D
0x14001213b  mov     r9d, 54h ; 'T'; TokenInformationLength
0x140012141  lea     rax, [rsp+0B8h+var_80]
0x140012146  lea     r8, [rsp+0B8h+pSid]; TokenInformation
0x14001214b  mov     [rsp+0B8h+var_80], r9d
0x140012150  mov     rcx, rbx; TokenHandle
0x140012153  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x140012158  lea     edx, [r9-3Bh]; TokenInformationClass
0x14001215c  call    cs:__imp_GetTokenInformation
0x140012163  nop     dword ptr [rax+rax+00h]
0x140012168  test    eax, eax
0x14001216a  jnz     short loc_140012191
0x14001216c  call    cs:__imp_GetLastError
0x140012173  nop     dword ptr [rax+rax+00h]
0x140012178  test    eax, eax
0x14001217a  jle     short loc_1400121C5
0x14001217c  movzx   eax, ax
0x14001217f  or      eax, 80070000h
0x140012184  jmp     short loc_1400121C5
0x140012186  cmp     [rsp+0B8h+TokenInformation], 0
0x14001218b  jz      short loc_14001213B
0x14001218d  xor     eax, eax
0x14001218f  jmp     short loc_1400121C5
0x140012191  mov     rcx, [rsp+0B8h+pSid]; pSid
0x140012196  call    cs:__imp_GetSidSubAuthorityCount
0x14001219d  nop     dword ptr [rax+rax+00h]
0x1400121a2  mov     rcx, [rsp+0B8h+pSid]; pSid
0x1400121a7  movzx   edx, byte ptr [rax]
0x1400121aa  dec     edx; nSubAuthority
0x1400121ac  call    cs:__imp_GetSidSubAuthority
0x1400121b3  nop     dword ptr [rax+rax+00h]
0x1400121b8  xor     ecx, ecx
0x1400121ba  cmp     dword ptr [rax], 2000h
0x1400121c0  setnb   cl
0x1400121c3  mov     eax, ecx
0x1400121c5  mov     rcx, [rsp+0B8h+var_18]
0x1400121cd  xor     rcx, rsp; StackCookie
0x1400121d0  call    __security_check_cookie
0x1400121d5  add     rsp, 0B0h
0x1400121dc  pop     rbx
0x1400121dd  retn
```
