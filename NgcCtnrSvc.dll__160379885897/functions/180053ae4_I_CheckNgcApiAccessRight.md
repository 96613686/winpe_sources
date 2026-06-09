# I_CheckNgcApiAccessRight

- ea: `0x180053ae4`
- end: `0x180053caa`
- name: `I_CheckNgcApiAccessRight`
- size: `454`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const WCHAR *, int TokenInformation)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180051998`
- `0x180051aa0`

## callees

- `0x18001b974`
- `0x180053ae4`
- `0x180053cb0`
- `0x18005f314`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053b80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053b80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053c8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180053c8a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180053c23`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180053c23`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053c5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053c73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053c5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053c73`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180053bfc`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180053bfc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180053b70`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180053b70`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180053c3e`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180053c3e`
- `ntdll!RtlNtStatusToDosError` at `0x180053bdf`
- `ntdll!RtlNtStatusToDosError` at `0x180053bdf`
- `ntdll!RtlIsMultiSessionSku` at `0x180053bae`
- `ntdll!RtlIsMultiSessionSku` at `0x180053bae`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180053bcd`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180053bcd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall I_CheckNgcApiAccessRight(__int64 a1, __int64 a2, __int64 a3, const WCHAR *a4, int TokenInformation)
{
  signed int v6; // ebx
  int UserSid; // eax
  PSID *v8; // rsi
  signed int LastError; // eax
  NTSTATUS v10; // eax
  bool v11; // cf
  HANDLE TokenHandle; // [rsp+30h] [rbp-10h] BYREF
  PSID Sid; // [rsp+38h] [rbp-8h] BYREF
  PSID *ReturnLength; // [rsp+68h] [rbp+28h] BYREF
  int v16; // [rsp+70h] [rbp+30h] BYREF

  v16 = a3;
  ReturnLength = 0;
  TokenHandle = 0;
  Sid = 0;
  v6 = DoKeyAccessCheckWorkRequiringImpersonation(a1, a2, a3, &TokenHandle);
  if ( v6 < 0 )
    goto LABEL_21;
  UserSid = GetUserSid(TokenHandle);
  v8 = ReturnLength;
  v6 = UserSid;
  if ( UserSid >= 0 )
  {
    TokenInformation = 0;
    LODWORD(ReturnLength) = 0;
    if ( !GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, (PDWORD)&ReturnLength) )
    {
LABEL_4:
      LastError = GetLastError();
      goto LABEL_5;
    }
    if ( TokenInformation == 1 )
    {
      LOBYTE(v16) = 0;
      if ( !(unsigned __int8)RtlIsMultiSessionSku() )
      {
        v10 = CapabilityCheck(TokenHandle, L"userSigninSupport", &v16);
        if ( v10 )
        {
          LastError = RtlNtStatusToDosError(v10);
LABEL_5:
          v6 = LastError;
          if ( LastError > 0 )
            v6 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_19;
        }
      }
      v11 = (_BYTE)v16 != 0;
    }
    else
    {
      if ( IsWellKnownSid(*v8, WinLocalSystemSid) )
      {
        v6 = 0;
        goto LABEL_19;
      }
      if ( !a4 )
      {
        v6 = -2147024891;
        goto LABEL_19;
      }
      if ( !ConvertStringSidToSidW(a4, &Sid) )
        goto LABEL_4;
      v11 = EqualSid(Sid, *v8);
    }
    v6 = v11 ? 0 : 0x80070005;
  }
LABEL_19:
  if ( v8 )
    LocalFree(v8);
LABEL_21:
  if ( Sid )
    LocalFree(Sid);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return HResultToSecurityStatus(v6);
}

```

## disassembly

```asm
0x180053ae4  mov     [rsp-18h+arg_0], rbx
0x180053ae9  mov     [rsp-18h+arg_10], r8d
0x180053aee  mov     [rsp-18h+arg_8], rdx
0x180053af3  push    rbp
0x180053af4  push    rsi
0x180053af5  push    r14
0x180053af7  mov     rbp, rsp
0x180053afa  sub     rsp, 40h
0x180053afe  mov     r14, r9
0x180053b01  mov     [rbp+arg_8], 0
0x180053b09  lea     r9, [rbp+TokenHandle]
0x180053b0d  mov     [rbp+TokenHandle], 0
0x180053b15  mov     [rbp+Sid], 0
0x180053b1d  call    DoKeyAccessCheckWorkRequiringImpersonation
0x180053b22  mov     ebx, eax
0x180053b24  test    eax, eax
0x180053b26  js      loc_180053C6A
0x180053b2c  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180053b30  lea     rdx, [rbp+arg_8]
0x180053b34  call    GetUserSid
0x180053b39  mov     rsi, [rbp+arg_8]
0x180053b3d  mov     ebx, eax
0x180053b3f  test    eax, eax
0x180053b41  js      loc_180053C56
0x180053b47  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x180053b4b  lea     rax, [rbp+arg_8]
0x180053b4f  mov     r9d, 4; TokenInformationLength
0x180053b55  mov     [rbp+TokenInformation], 0
0x180053b5c  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180053b60  mov     dword ptr [rbp+arg_8], 0
0x180053b67  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180053b6c  lea     edx, [r9+19h]; TokenInformationClass
0x180053b70  call    cs:__imp_GetTokenInformation
0x180053b77  nop     dword ptr [rax+rax+00h]
0x180053b7c  test    eax, eax
0x180053b7e  jnz     short loc_180053BA4
0x180053b80  call    cs:__imp_GetLastError
0x180053b87  nop     dword ptr [rax+rax+00h]
0x180053b8c  mov     ebx, eax
0x180053b8e  test    eax, eax
0x180053b90  jle     loc_180053C56
0x180053b96  movzx   ebx, ax
0x180053b99  or      ebx, 80070000h
0x180053b9f  jmp     loc_180053C56
0x180053ba4  cmp     [rbp+TokenInformation], 1
0x180053ba8  jnz     short loc_180053BF4
0x180053baa  mov     byte ptr [rbp+arg_10], 0
0x180053bae  call    cs:__imp_RtlIsMultiSessionSku
0x180053bb5  nop     dword ptr [rax+rax+00h]
0x180053bba  test    al, al
0x180053bbc  jnz     short loc_180053BED
0x180053bbe  mov     rcx, [rbp+TokenHandle]
0x180053bc2  lea     r8, [rbp+arg_10]
0x180053bc6  lea     rdx, aUsersigninsupp; "userSigninSupport"
0x180053bcd  call    cs:__imp_CapabilityCheck
0x180053bd4  nop     dword ptr [rax+rax+00h]
0x180053bd9  test    eax, eax
0x180053bdb  jz      short loc_180053BED
0x180053bdd  mov     ecx, eax; Status
0x180053bdf  call    cs:__imp_RtlNtStatusToDosError
0x180053be6  nop     dword ptr [rax+rax+00h]
0x180053beb  jmp     short loc_180053B8C
0x180053bed  mov     al, byte ptr [rbp+arg_10]
0x180053bf0  neg     al
0x180053bf2  jmp     short loc_180053C4C
0x180053bf4  mov     rcx, [rsi]; pSid
0x180053bf7  mov     edx, 16h; WellKnownSidType
0x180053bfc  call    cs:__imp_IsWellKnownSid
0x180053c03  nop     dword ptr [rax+rax+00h]
0x180053c08  test    eax, eax
0x180053c0a  jz      short loc_180053C10
0x180053c0c  xor     ebx, ebx
0x180053c0e  jmp     short loc_180053C56
0x180053c10  test    r14, r14
0x180053c13  jnz     short loc_180053C1C
0x180053c15  mov     ebx, 80070005h
0x180053c1a  jmp     short loc_180053C56
0x180053c1c  lea     rdx, [rbp+Sid]; Sid
0x180053c20  mov     rcx, r14; StringSid
0x180053c23  call    cs:__imp_ConvertStringSidToSidW
0x180053c2a  nop     dword ptr [rax+rax+00h]
0x180053c2f  test    eax, eax
0x180053c31  jz      loc_180053B80
0x180053c37  mov     rdx, [rsi]; pSid2
0x180053c3a  mov     rcx, [rbp+Sid]; pSid1
0x180053c3e  call    cs:__imp_EqualSid
0x180053c45  nop     dword ptr [rax+rax+00h]
0x180053c4a  neg     eax
0x180053c4c  sbb     ebx, ebx
0x180053c4e  not     ebx
0x180053c50  and     ebx, 80070005h
0x180053c56  test    rsi, rsi
0x180053c59  jz      short loc_180053C6A
0x180053c5b  mov     rcx, rsi; hMem
0x180053c5e  call    cs:__imp_LocalFree
0x180053c65  nop     dword ptr [rax+rax+00h]
0x180053c6a  mov     rcx, [rbp+Sid]; hMem
0x180053c6e  test    rcx, rcx
0x180053c71  jz      short loc_180053C7F
0x180053c73  call    cs:__imp_LocalFree
0x180053c7a  nop     dword ptr [rax+rax+00h]
0x180053c7f  cmp     [rbp+TokenHandle], 0
0x180053c84  jz      short loc_180053C96
0x180053c86  mov     rcx, [rbp+TokenHandle]; hObject
0x180053c8a  call    cs:__imp_CloseHandle
0x180053c91  nop     dword ptr [rax+rax+00h]
0x180053c96  mov     ecx, ebx; int
0x180053c98  mov     rbx, [rsp+40h+arg_0]
0x180053c9d  add     rsp, 40h
0x180053ca1  pop     r14
0x180053ca3  pop     rsi
0x180053ca4  pop     rbp
0x180053ca5  jmp     ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
```
