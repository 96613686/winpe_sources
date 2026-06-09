# EnterpriseDeviceManagement::Service::AutoPilot::IsUserSidEqualTo(WELL_KNOWN_SID_TYPE)

- ea: `0x1800d58f4`
- end: `0x1800d5a01`
- name: `?IsUserSidEqualTo@AutoPilot@Service@EnterpriseDeviceManagement@@YA_NW4WELL_KNOWN_SID_TYPE@@@Z`
- size: `269`
- prototype: `bool __fastcall(EnterpriseDeviceManagement::Service::AutoPilot *__hidden this, enum WELL_KNOWN_SID_TYPE)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800d52f4`

## callees

- `0x18000b8f0`
- `0x1800d58f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800d5967`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800d5967`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d594e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d594e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d59ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d59ce`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800d599f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800d599f`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800d5931`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800d5931`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800d59b8`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800d59b8`

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
0x1800d58f4  mov     [rsp-8+arg_0], rbx
0x1800d58f9  push    rbp
0x1800d58fa  lea     rbp, [rsp-0A0h]
0x1800d5902  sub     rsp, 1A0h
0x1800d5909  mov     rax, cs:__security_cookie
0x1800d5910  xor     rax, rsp
0x1800d5913  mov     [rbp+0A0h+var_10], rax
0x1800d591a  xor     edx, edx; DomainSid
0x1800d591c  mov     [rsp+1A0h+cbSid], 44h ; 'D'
0x1800d5924  lea     r9, [rsp+1A0h+cbSid]; cbSid
0x1800d5929  lea     r8, [rsp+1A0h+pSid]; pSid
0x1800d592e  lea     ecx, [rdx+16h]; WellKnownSidType
0x1800d5931  call    cs:__imp_CreateWellKnownSid
0x1800d5938  nop     dword ptr [rax+rax+00h]
0x1800d593d  test    eax, eax
0x1800d593f  jz      loc_1800D59DE
0x1800d5945  mov     [rsp+1A0h+TokenHandle], 0
0x1800d594e  call    cs:__imp_GetCurrentProcess
0x1800d5955  nop     dword ptr [rax+rax+00h]
0x1800d595a  lea     r8, [rsp+1A0h+TokenHandle]; TokenHandle
0x1800d595f  mov     edx, 8; DesiredAccess
0x1800d5964  mov     rcx, rax; ProcessHandle
0x1800d5967  call    cs:__imp_OpenProcessToken
0x1800d596e  nop     dword ptr [rax+rax+00h]
0x1800d5973  test    eax, eax
0x1800d5975  jz      short loc_1800D59DE
0x1800d5977  mov     rcx, [rsp+1A0h+TokenHandle]; TokenHandle
0x1800d597c  lea     rax, [rsp+1A0h+var_16C]
0x1800d5981  mov     r9d, 100h; TokenInformationLength
0x1800d5987  mov     [rsp+1A0h+ReturnLength], rax; ReturnLength
0x1800d598c  lea     r8, [rbp+0A0h+TokenInformation]; TokenInformation
0x1800d5990  mov     [rsp+1A0h+var_16C], 0
0x1800d5998  mov     edx, 1; TokenInformationClass
0x1800d599d  xor     bl, bl
0x1800d599f  call    cs:__imp_GetTokenInformation
0x1800d59a6  nop     dword ptr [rax+rax+00h]
0x1800d59ab  test    eax, eax
0x1800d59ad  jz      short loc_1800D59C9
0x1800d59af  mov     rcx, [rbp+0A0h+TokenInformation]; pSid1
0x1800d59b3  lea     rdx, [rsp+1A0h+pSid]; pSid2
0x1800d59b8  call    cs:__imp_EqualSid
0x1800d59bf  nop     dword ptr [rax+rax+00h]
0x1800d59c4  test    eax, eax
0x1800d59c6  setnz   bl
0x1800d59c9  mov     rcx, [rsp+1A0h+TokenHandle]; hObject
0x1800d59ce  call    cs:__imp_CloseHandle
0x1800d59d5  nop     dword ptr [rax+rax+00h]
0x1800d59da  mov     al, bl
0x1800d59dc  jmp     short loc_1800D59E0
0x1800d59de  xor     al, al
0x1800d59e0  mov     rcx, [rbp+0A0h+var_10]
0x1800d59e7  xor     rcx, rsp; StackCookie
0x1800d59ea  call    __security_check_cookie
0x1800d59ef  mov     rbx, [rsp+1A0h+arg_0]
0x1800d59f7  add     rsp, 1A0h
0x1800d59fe  pop     rbp
0x1800d59ff  retn
```
