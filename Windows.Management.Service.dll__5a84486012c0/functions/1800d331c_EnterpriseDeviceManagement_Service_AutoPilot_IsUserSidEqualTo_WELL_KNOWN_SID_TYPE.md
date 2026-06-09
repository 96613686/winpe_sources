# EnterpriseDeviceManagement::Service::AutoPilot::IsUserSidEqualTo(WELL_KNOWN_SID_TYPE)

- ea: `0x1800d331c`
- end: `0x1800d3400`
- name: `?IsUserSidEqualTo@AutoPilot@Service@EnterpriseDeviceManagement@@YA_NW4WELL_KNOWN_SID_TYPE@@@Z`
- size: `228`
- prototype: `bool __fastcall(EnterpriseDeviceManagement::Service::AutoPilot *__hidden this, enum WELL_KNOWN_SID_TYPE)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d2d34`

## callees

- `0x18000b820`
- `0x1800d331c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800d337f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800d337f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d336c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d336c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d33d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d33d4`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800d33b1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800d33b1`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800d3359`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800d3359`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800d33c4`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800d33c4`

## pseudocode

```c
bool __fastcall EnterpriseDeviceManagement::Service::AutoPilot::IsUserSidEqualTo(
        EnterpriseDeviceManagement::Service::AutoPilot *this,
        enum WELL_KNOWN_SID_TYPE a2)
{
  HANDLE CurrentProcess; // rax
  bool v3; // bl
  DWORD cbSid; // [rsp+30h] [rbp-D0h] BYREF
  DWORD ReturnLength; // [rsp+34h] [rbp-CCh] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE pSid[80]; // [rsp+40h] [rbp-C0h] BYREF
  PSID TokenInformation[32]; // [rsp+90h] [rbp-70h] BYREF

  cbSid = 68;
  if ( !CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
    return 0;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    return 0;
  ReturnLength = 0;
  v3 = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x100u, &ReturnLength) )
    v3 = EqualSid(TokenInformation[0], pSid);
  CloseHandle(TokenHandle);
  return v3;
}

```

## disassembly

```asm
0x1800d331c  mov     [rsp-8+arg_0], rbx
0x1800d3321  push    rbp
0x1800d3322  lea     rbp, [rsp-0A0h]
0x1800d332a  sub     rsp, 1A0h
0x1800d3331  mov     rax, cs:__security_cookie
0x1800d3338  xor     rax, rsp
0x1800d333b  mov     [rbp+0A0h+var_10], rax
0x1800d3342  xor     edx, edx; DomainSid
0x1800d3344  mov     [rsp+1A0h+cbSid], 44h ; 'D'
0x1800d334c  lea     r9, [rsp+1A0h+cbSid]; cbSid
0x1800d3351  lea     r8, [rsp+1A0h+pSid]; pSid
0x1800d3356  lea     ecx, [rdx+16h]; WellKnownSidType
0x1800d3359  call    cs:__imp_CreateWellKnownSid
0x1800d335f  test    eax, eax
0x1800d3361  jz      short loc_1800D33DE
0x1800d3363  mov     [rsp+1A0h+TokenHandle], 0
0x1800d336c  call    cs:__imp_GetCurrentProcess
0x1800d3372  lea     r8, [rsp+1A0h+TokenHandle]; TokenHandle
0x1800d3377  mov     edx, 8; DesiredAccess
0x1800d337c  mov     rcx, rax; ProcessHandle
0x1800d337f  call    cs:__imp_OpenProcessToken
0x1800d3385  test    eax, eax
0x1800d3387  jz      short loc_1800D33DE
0x1800d3389  mov     rcx, [rsp+1A0h+TokenHandle]; TokenHandle
0x1800d338e  lea     rax, [rsp+1A0h+var_16C]
0x1800d3393  mov     r9d, 100h; TokenInformationLength
0x1800d3399  mov     [rsp+1A0h+ReturnLength], rax; ReturnLength
0x1800d339e  lea     r8, [rbp+0A0h+TokenInformation]; TokenInformation
0x1800d33a2  mov     [rsp+1A0h+var_16C], 0
0x1800d33aa  mov     edx, 1; TokenInformationClass
0x1800d33af  xor     bl, bl
0x1800d33b1  call    cs:__imp_GetTokenInformation
0x1800d33b7  test    eax, eax
0x1800d33b9  jz      short loc_1800D33CF
0x1800d33bb  mov     rcx, [rbp+0A0h+TokenInformation]; pSid1
0x1800d33bf  lea     rdx, [rsp+1A0h+pSid]; pSid2
0x1800d33c4  call    cs:__imp_EqualSid
0x1800d33ca  test    eax, eax
0x1800d33cc  setnz   bl
0x1800d33cf  mov     rcx, [rsp+1A0h+TokenHandle]; hObject
0x1800d33d4  call    cs:__imp_CloseHandle
0x1800d33da  mov     al, bl
0x1800d33dc  jmp     short loc_1800D33E0
0x1800d33de  xor     al, al
0x1800d33e0  mov     rcx, [rbp+0A0h+var_10]
0x1800d33e7  xor     rcx, rsp; StackCookie
0x1800d33ea  call    __security_check_cookie
0x1800d33ef  mov     rbx, [rsp+1A0h+arg_0]
0x1800d33f7  add     rsp, 1A0h
0x1800d33fe  pop     rbp
0x1800d33ff  retn
```
