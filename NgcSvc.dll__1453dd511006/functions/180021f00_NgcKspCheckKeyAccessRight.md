# NgcKspCheckKeyAccessRight

- ea: `0x180021f00`
- end: `0x1800224a6`
- name: `NgcKspCheckKeyAccessRight`
- size: `1446`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002c024`
- `0x180039a30`
- `0x18007bb38`
- `0x18008447c`
- `0x180084768`

## callees

- `0x180021f00`
- `0x18005fb04`
- `0x1800aaaa0`
- `0x1800aabc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022097`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022321`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022327`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002238d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800223fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022097`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022321`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022327`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002238d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800223fc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800223ae`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800223ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180021f4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180021f4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002239c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002239c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180021f66`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180021f66`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022056`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800223ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022414`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002242d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022056`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800223ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180022414`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002242d`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180022194`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180022194`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800223df`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800223df`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002215f`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18002215f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021fc8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002208d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800220d7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021fc8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002208d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800220d7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800221a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800222d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800222fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800221a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800222d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800222fc`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800220ad`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800220ad`
- `ntdll!RtlIsMultiSessionSku` at `0x180022440`
- `ntdll!RtlIsMultiSessionSku` at `0x180022440`
- `ntdll!NtQueryInformationToken` at `0x18002210c`
- `ntdll!NtQueryInformationToken` at `0x1800221da`
- `ntdll!NtQueryInformationToken` at `0x18002210c`
- `ntdll!NtQueryInformationToken` at `0x1800221da`
- `ntdll!RtlNtStatusToDosError` at `0x18002212f`
- `ntdll!RtlNtStatusToDosError` at `0x180022219`
- `ntdll!RtlNtStatusToDosError` at `0x180022340`
- `ntdll!RtlNtStatusToDosError` at `0x18002212f`
- `ntdll!RtlNtStatusToDosError` at `0x180022219`
- `ntdll!RtlNtStatusToDosError` at `0x180022340`
- `RPCRT4!RpcRevertToSelf` at `0x180021fdb`
- `RPCRT4!RpcRevertToSelf` at `0x18002241f`
- `RPCRT4!RpcRevertToSelf` at `0x180021fdb`
- `RPCRT4!RpcRevertToSelf` at `0x18002241f`
- `RPCRT4!RpcImpersonateClient` at `0x180021f81`
- `RPCRT4!RpcImpersonateClient` at `0x180021f81`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180022183`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180022183`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180022493`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180022493`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18002245c`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18002245c`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x180021ff6`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x180021ff6`

## string_xrefs

- `0x180022283`: `windowsHelloCredentialAccess`

## pseudocode

```c
__int64 __fastcall NgcKspCheckKeyAccessRight(
        void *a1,
        int a2,
        const WCHAR *a3,
        int a4,
        wchar_t *String1,
        __int64 a6,
        LPWSTR *a7)
{
  void *v8; // rdi
  LPWSTR *v9; // r15
  int v10; // r14d
  HANDLE CurrentThread; // rax
  void *v12; // rsi
  signed int LastError; // ebx
  RPC_STATUS v14; // eax
  signed int v16; // eax
  PSID *v17; // rsi
  NTSTATUS v18; // eax
  int v19; // eax
  signed int v20; // eax
  PSID v21; // r14
  BOOL v22; // ebx
  NTSTATUS v23; // eax
  int v24; // ebx
  signed int v25; // eax
  signed int v26; // eax
  signed int v27; // eax
  signed int v28; // eax
  HANDLE CurrentProcess; // rax
  NTSTATUS v30; // eax
  char ReturnLength; // [rsp+28h] [rbp-51h]
  ULONG v32; // [rsp+38h] [rbp-41h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-39h] BYREF
  _QWORD v34[5]; // [rsp+48h] [rbp-31h] BYREF
  int v35; // [rsp+70h] [rbp-9h]
  int v36; // [rsp+74h] [rbp-5h]
  const wchar_t *v37; // [rsp+78h] [rbp-1h]
  __int64 v38; // [rsp+80h] [rbp+7h]
  DWORD TokenInformation; // [rsp+D0h] [rbp+57h] BYREF
  int v40; // [rsp+E0h] [rbp+67h] BYREF

  v40 = a4;
  v8 = 0;
  v9 = a7;
  if ( a7 )
    *a7 = 0;
  v10 = 0;
  if ( a2 )
  {
    v14 = RpcImpersonateClient(a1);
    LastError = v14;
    if ( v14 )
    {
      if ( v14 != 1725 )
        goto LABEL_21;
    }
    else
    {
      v10 = 1;
    }
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    if ( LastError == 1008 )
    {
      CurrentProcess = GetCurrentProcess();
      if ( OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
      {
        a7 = 0;
        if ( DuplicateTokenEx(TokenHandle, 0x2000000u, 0, SecurityIdentification, TokenImpersonation, (PHANDLE)&a7) )
        {
          CloseHandle(TokenHandle);
          v12 = a7;
          goto LABEL_6;
        }
      }
      LastError = GetLastError();
    }
    v12 = 0;
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    if ( LastError < 0 )
      goto LABEL_17;
    goto LABEL_10;
  }
  v12 = TokenHandle;
LABEL_6:
  TokenHandle = 0;
  LastError = 0;
LABEL_10:
  LOBYTE(v40) = 0;
  TokenInformation = 0;
  LODWORD(a7) = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenSessionId, &TokenInformation, 4u, (PDWORD)&a7) )
  {
    if ( v10 )
    {
      RpcRevertToSelf();
      v10 = 0;
    }
    if ( (unsigned __int8)IsWinStationIsSessionRemoteablePresent()
      && (unsigned __int8)WinStationIsSessionRemoteable(0, TokenInformation, &v40)
      && (_BYTE)v40 )
    {
      LastError = -2146893808;
    }
    else
    {
      v8 = v12;
      v12 = 0;
    }
  }
  else
  {
    LastError = -2146893808;
  }
LABEL_17:
  if ( v10 )
    RpcRevertToSelf();
  if ( v12 )
    CloseHandle(v12);
LABEL_21:
  if ( LastError < 0 )
    goto LABEL_22;
  if ( v9 )
    *v9 = 0;
  TokenInformation = 0;
  if ( GetTokenInformation(v8, TokenUser, 0, 0, &TokenInformation)
    || (v16 = GetLastError(), LastError = v16, v16 == 122) )
  {
    v17 = (PSID *)LocalAlloc(0, TokenInformation);
    if ( !v17 )
    {
      LastError = -2147024882;
      goto LABEL_22;
    }
    if ( GetTokenInformation(v8, TokenUser, v17, TokenInformation, &TokenInformation) )
      goto LABEL_31;
    GetLastError();
    v26 = GetLastError();
    LastError = v26;
    if ( v26 > 0 )
      LastError = (unsigned __int16)v26 | 0x80070000;
    LocalFree(v17);
  }
  else if ( v16 > 0 )
  {
    LastError = (unsigned __int16)v16 | 0x80070000;
  }
  v17 = 0;
  if ( LastError < 0 )
    goto LABEL_22;
LABEL_31:
  LOBYTE(v40) = 0;
  LODWORD(a7) = 0;
  v32 = 0;
  v18 = NtQueryInformationToken(v8, TokenIsAppContainer, &a7, 4u, &v32);
  if ( v18 )
  {
    v20 = RtlNtStatusToDosError(v18);
    LastError = v20;
    if ( v20 > 0 )
      LastError = (unsigned __int16)v20 | 0x80070000;
    v19 = 0;
    if ( LastError < 0 )
      goto LABEL_57;
  }
  else
  {
    if ( !(_DWORD)a7 )
      goto LABEL_39;
    v19 = 1;
  }
  if ( v19 )
  {
    if ( !(unsigned __int8)RtlIsMultiSessionSku() )
    {
      v30 = CapabilityCheck(v8, L"userSigninSupport", &v40);
      if ( v30 )
      {
        v27 = RtlNtStatusToDosError(v30);
        LastError = v27;
        if ( v27 > 0 )
          LastError = (unsigned __int16)v27 | 0x80070000;
        if ( LastError < 0 )
          goto LABEL_57;
      }
      else if ( (_BYTE)v40 )
      {
        goto LABEL_55;
      }
    }
    goto LABEL_40;
  }
LABEL_39:
  if ( IsWellKnownSid(*v17, WinLocalSystemSid) )
    goto LABEL_55;
LABEL_40:
  if ( !a3 )
    goto LABEL_46;
  v21 = *v17;
  a7 = 0;
  v22 = 0;
  if ( ConvertStringSidToSidW(a3, (PSID *)&a7) )
    v22 = EqualSid(a7, v21);
  if ( a7 )
    LocalFree(a7);
  if ( !v22 )
  {
    LastError = -2146893808;
  }
  else
  {
LABEL_46:
    LODWORD(a7) = 0;
    v40 = 0;
    v32 = 0;
    v23 = NtQueryInformationToken(v8, TokenIsAppContainer, &v40, 4u, &v32);
    if ( v23 )
    {
      v25 = RtlNtStatusToDosError(v23);
      LastError = v25;
      if ( v25 > 0 )
        LastError = (unsigned __int16)v25 | 0x80070000;
      if ( LastError < 0 )
        goto LABEL_57;
      goto LABEL_55;
    }
    if ( !v40 )
      goto LABEL_55;
    v24 = (int)String1;
    if ( (int)GetDomainRelevantKeyCharacteristics(String1) < 0 )
    {
      LastError = -2146893808;
      goto LABEL_57;
    }
    v34[0] = L"networkingVpnProvider";
    v34[1] = 0x100000;
    v34[2] = L"ID_CAP_NETWORKING_VPN_PROVIDER";
    v34[3] = 0x100000;
    v34[4] = L"sharedUserCertificates";
    v35 = 0x20000;
    v37 = L"windowsHelloCredentialAccess";
    v36 = 3932160;
    v38 = 3932160;
    LastError = CheckAppAccessRightBasedOnCapability(
                  (_DWORD)v8,
                  (unsigned int)a7 & 0x3E0000 | 0x10000,
                  v24,
                  a6,
                  ReturnLength,
                  (__int64)v34);
    if ( LastError >= 0 )
    {
LABEL_55:
      if ( !v9 || ConvertSidToStringSidW(*v17, v9) )
      {
        LastError = 0;
      }
      else
      {
        v28 = GetLastError();
        LastError = v28;
        if ( v28 > 0 )
          LastError = (unsigned __int16)v28 | 0x80070000;
      }
    }
  }
LABEL_57:
  if ( v17 )
    LocalFree(v17);
LABEL_22:
  if ( v8 )
    CloseHandle(v8);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180021f00  mov     rax, rsp
0x180021f03  mov     [rax+20h], r9d
0x180021f07  push    rbp
0x180021f08  push    rbx
0x180021f09  push    rdi
0x180021f0a  lea     rbp, [rax-47h]
0x180021f0e  sub     rsp, 0A0h
0x180021f15  mov     [rax-20h], r12
0x180021f19  mov     r12, r8
0x180021f1c  mov     [rax-28h], r13
0x180021f20  xor     r13d, r13d
0x180021f23  mov     [rax-30h], r14
0x180021f27  mov     edi, r13d
0x180021f2a  mov     [rax-38h], r15
0x180021f2e  mov     r15, [rbp+3Fh+arg_30]
0x180021f32  test    r15, r15
0x180021f35  jnz     loc_180022375
0x180021f3b  mov     [rsp+0B0h+arg_0], rsi
0x180021f43  mov     r14d, r13d
0x180021f46  test    edx, edx
0x180021f48  jnz     short loc_180021F81
0x180021f4a  mov     [rbp+3Fh+TokenHandle], r13
0x180021f4e  call    cs:__imp_GetCurrentThread
0x180021f54  lea     r9, [rbp+3Fh+TokenHandle]; TokenHandle
0x180021f58  mov     edx, 8; DesiredAccess
0x180021f5d  mov     rcx, rax; ThreadHandle
0x180021f60  mov     r8d, 1; OpenAsSelf
0x180021f66  call    cs:__imp_OpenThreadToken
0x180021f6c  test    eax, eax
0x180021f6e  jz      loc_18002238D
0x180021f74  mov     rsi, [rbp+3Fh+TokenHandle]
0x180021f78  mov     [rbp+3Fh+TokenHandle], r13
0x180021f7c  mov     ebx, r13d
0x180021f7f  jmp     short loc_180021F9D
0x180021f81  call    cs:__imp_RpcImpersonateClient
0x180021f87  mov     ebx, eax
0x180021f89  test    eax, eax
0x180021f8b  jnz     loc_18002237D
0x180021f91  mov     r14d, 1
0x180021f97  jmp     short loc_180021F4A
0x180021f99  test    ebx, ebx
0x180021f9b  js      short loc_180022010
0x180021f9d  lea     rax, [rbp+3Fh+arg_30]
0x180021fa1  mov     byte ptr [rbp+3Fh+arg_18], dil
0x180021fa5  mov     r9d, 4; TokenInformationLength
0x180021fab  mov     qword ptr [rsp+0B0h+ReturnLength], rax; ReturnLength
0x180021fb0  lea     r8, [rbp+3Fh+TokenInformation]; TokenInformation
0x180021fb4  mov     [rbp+3Fh+TokenInformation], r13d
0x180021fb8  mov     edx, 0Ch; TokenInformationClass
0x180021fbd  mov     dword ptr [rbp+3Fh+arg_30], r13d
0x180021fc1  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x180021fc8  call    cs:__imp_GetTokenInformation
0x180021fce  test    eax, eax
0x180021fd0  jz      loc_180022123
0x180021fd6  test    r14d, r14d
0x180021fd9  jz      short loc_180021FE4
0x180021fdb  call    cs:__imp_RpcRevertToSelf
0x180021fe1  mov     r14d, r13d
0x180021fe4  call    IsWinStationIsSessionRemoteablePresent
0x180021fe9  test    al, al
0x180021feb  jz      short loc_18002200A
0x180021fed  mov     edx, [rbp+3Fh+TokenInformation]
0x180021ff0  lea     r8, [rbp+3Fh+arg_18]
0x180021ff4  xor     ecx, ecx
0x180021ff6  call    cs:__imp_WinStationIsSessionRemoteable
0x180021ffc  test    al, al
0x180021ffe  jz      short loc_18002200A
0x180022000  cmp     byte ptr [rbp+3Fh+arg_18], dil
0x180022004  jnz     loc_1800222DB
0x18002200a  mov     rdi, rsi
0x18002200d  mov     rsi, r13
0x180022010  test    r14d, r14d
0x180022013  jnz     loc_18002241F
0x180022019  test    rsi, rsi
0x18002201c  jnz     loc_18002242A
0x180022022  test    ebx, ebx
0x180022024  jns     short loc_180022069
0x180022026  mov     r15, [rsp+0B0h+var_30]
0x18002202e  mov     r14, [rsp+0B0h+var_28]
0x180022036  mov     r13, [rsp+0B0h+var_20]
0x18002203e  mov     r12, [rsp+98h]
0x180022046  mov     rsi, [rsp+0B0h+arg_0]
0x18002204e  test    rdi, rdi
0x180022051  jz      short loc_18002205C
0x180022053  mov     rcx, rdi; hObject
0x180022056  call    cs:__imp_CloseHandle
0x18002205c  mov     eax, ebx
0x18002205e  add     rsp, 0A0h
0x180022065  pop     rdi
0x180022066  pop     rbx
0x180022067  pop     rbp
0x180022068  retn
0x180022069  test    r15, r15
0x18002206c  jnz     loc_180022438
0x180022072  lea     rax, [rbp+3Fh+TokenInformation]
0x180022076  mov     [rbp+3Fh+TokenInformation], r13d
0x18002207a  xor     r9d, r9d; TokenInformationLength
0x18002207d  mov     qword ptr [rsp+0B0h+ReturnLength], rax; ReturnLength
0x180022082  xor     r8d, r8d; TokenInformation
0x180022085  mov     edx, 1; TokenInformationClass
0x18002208a  mov     rcx, rdi; TokenHandle
0x18002208d  call    cs:__imp_GetTokenInformation
0x180022093  test    eax, eax
0x180022095  jnz     short loc_1800220A8
0x180022097  call    cs:__imp_GetLastError
0x18002209d  mov     ebx, eax
0x18002209f  cmp     eax, 7Ah ; 'z'
0x1800220a2  jnz     loc_180022312
0x1800220a8  mov     edx, [rbp+3Fh+TokenInformation]; uBytes
0x1800220ab  xor     ecx, ecx; uFlags
0x1800220ad  call    cs:__imp_LocalAlloc
0x1800220b3  mov     rsi, rax
0x1800220b6  test    rax, rax
0x1800220b9  jz      loc_1800222E5
0x1800220bf  mov     r9d, [rbp+3Fh+TokenInformation]; TokenInformationLength
0x1800220c3  lea     rax, [rbp+3Fh+TokenInformation]
0x1800220c7  mov     r8, rsi; TokenInformation
0x1800220ca  mov     qword ptr [rsp+0B0h+ReturnLength], rax; ReturnLength
0x1800220cf  mov     edx, 1; TokenInformationClass
0x1800220d4  mov     rcx, rdi; TokenHandle
0x1800220d7  call    cs:__imp_GetTokenInformation
0x1800220dd  test    eax, eax
0x1800220df  jz      loc_180022321
0x1800220e5  lea     rax, [rbp+3Fh+var_80]
0x1800220e9  mov     byte ptr [rbp+3Fh+arg_18], r13b
0x1800220ed  mov     r9d, 4; TokenInformationLength
0x1800220f3  mov     qword ptr [rsp+0B0h+ReturnLength], rax; ReturnLength
0x1800220f8  lea     r8, [rbp+3Fh+arg_30]; TokenInformation
0x1800220fc  mov     dword ptr [rbp+3Fh+arg_30], r13d
0x180022100  mov     edx, 1Dh; TokenInformationClass
0x180022105  mov     [rbp+3Fh+var_80], r13d
0x180022109  mov     rcx, rdi; TokenHandle
0x18002210c  call    cs:__imp_NtQueryInformationToken
0x180022112  test    eax, eax
0x180022114  jnz     short loc_18002212D
0x180022116  cmp     dword ptr [rbp+3Fh+arg_30], r13d
0x18002211a  jz      short loc_180022157
0x18002211c  mov     eax, 1
0x180022121  jmp     short loc_18002214F
0x180022123  mov     ebx, 80090010h
0x180022128  jmp     loc_180022010
0x18002212d  mov     ecx, eax; Status
0x18002212f  call    cs:__imp_RtlNtStatusToDosError
0x180022135  mov     ebx, eax
0x180022137  test    eax, eax
0x180022139  jle     short loc_180022144
0x18002213b  movzx   ebx, ax
0x18002213e  or      ebx, 80070000h
0x180022144  mov     eax, r13d
0x180022147  test    ebx, ebx
0x180022149  js      loc_1800222C4
0x18002214f  test    eax, eax
0x180022151  jnz     loc_180022440
0x180022157  mov     rcx, [rsi]; pSid
0x18002215a  mov     edx, 16h; WellKnownSidType
0x18002215f  call    cs:__imp_IsWellKnownSid
0x180022165  test    eax, eax
0x180022167  jnz     loc_1800222B8
0x18002216d  test    r12, r12
0x180022170  jz      short loc_1800221B3
0x180022172  mov     r14, [rsi]
0x180022175  lea     rdx, [rbp+3Fh+arg_30]; Sid
0x180022179  mov     rcx, r12; StringSid
0x18002217c  mov     [rbp+3Fh+arg_30], r13
0x180022180  mov     ebx, r13d
0x180022183  call    cs:__imp_ConvertStringSidToSidW
0x180022189  test    eax, eax
0x18002218b  jz      short loc_18002219C
0x18002218d  mov     rcx, [rbp+3Fh+arg_30]; pSid1
0x180022191  mov     rdx, r14; pSid2
0x180022194  call    cs:__imp_EqualSid
0x18002219a  mov     ebx, eax
0x18002219c  mov     rcx, [rbp+3Fh+arg_30]; hMem
0x1800221a0  test    rcx, rcx
0x1800221a3  jz      short loc_1800221AB
0x1800221a5  call    cs:__imp_LocalFree
0x1800221ab  test    ebx, ebx
0x1800221ad  jz      loc_180022479
0x1800221b3  lea     rax, [rbp+3Fh+var_80]
0x1800221b7  mov     dword ptr [rbp+3Fh+arg_30], r13d
0x1800221bb  mov     r9d, 4; TokenInformationLength
0x1800221c1  mov     qword ptr [rsp+0B0h+ReturnLength], rax; ReturnLength
0x1800221c6  lea     r8, [rbp+3Fh+arg_18]; TokenInformation
0x1800221ca  mov     [rbp+3Fh+arg_18], r13d
0x1800221ce  mov     edx, 1Dh; TokenInformationClass
0x1800221d3  mov     [rbp+3Fh+var_80], r13d
0x1800221d7  mov     rcx, rdi; TokenHandle
0x1800221da  call    cs:__imp_NtQueryInformationToken
0x1800221e0  test    eax, eax
0x1800221e2  jnz     short loc_180022217
0x1800221e4  mov     eax, r13d
0x1800221e7  cmp     [rbp+3Fh+arg_18], r13d
0x1800221eb  jnz     loc_180022483
0x1800221f1  test    eax, eax
0x1800221f3  jz      loc_1800222B8
0x1800221f9  mov     rbx, [rbp+3Fh+String1]
0x1800221fd  lea     rdx, [rbp+3Fh+arg_30]
0x180022201  mov     rcx, rbx; String1
0x180022204  call    GetDomainRelevantKeyCharacteristics
0x180022209  test    eax, eax
0x18002220b  jns     short loc_18002223B
0x18002220d  mov     ebx, 80090010h
0x180022212  jmp     loc_1800222C4
0x180022217  mov     ecx, eax; Status
0x180022219  call    cs:__imp_RtlNtStatusToDosError
0x18002221f  mov     ebx, eax
0x180022221  test    eax, eax
0x180022223  jle     short loc_18002222E
0x180022225  movzx   ebx, ax
0x180022228  or      ebx, 80070000h
0x18002222e  test    ebx, ebx
0x180022230  jns     loc_1800222B8
0x180022236  jmp     loc_1800222C4
0x18002223b  mov     edx, dword ptr [rbp+3Fh+arg_30]
0x18002223e  lea     rax, aNetworkingvpnp; "networkingVpnProvider"
0x180022245  mov     r9, [rbp+3Fh+arg_28]
0x180022249  and     edx, 3E0000h
0x18002224f  mov     [rbp+3Fh+var_70], rax
0x180022253  bts     edx, 10h
0x180022257  lea     rax, aIdCapNetworkin; "ID_CAP_NETWORKING_VPN_PROVIDER"
0x18002225e  mov     [rbp+3Fh+var_68], 100000h
0x180022266  mov     [rbp+3Fh+var_60], rax
0x18002226a  mov     r8, rbx
0x18002226d  lea     rax, aSharedusercert; "sharedUserCertificates"
0x180022274  mov     [rbp+3Fh+var_58], 100000h
0x18002227c  mov     [rbp+3Fh+var_50], rax
0x180022280  mov     rcx, rdi
0x180022283  lea     rax, aWindowshellocr; "windowsHelloCredentialAccess"
0x18002228a  mov     [rbp+3Fh+var_48], 20000h
0x180022291  mov     [rbp+3Fh+var_40], rax
0x180022295  lea     rax, [rbp+3Fh+var_70]
0x180022299  mov     qword ptr [rsp+0B0h+ReturnLength+8], rax
0x18002229e  mov     [rbp+3Fh+var_44], 3C0000h
0x1800222a5  mov     [rbp+3Fh+var_38], 3C0000h
0x1800222ad  call    CheckAppAccessRightBasedOnCapability
0x1800222b2  mov     ebx, eax
0x1800222b4  test    eax, eax
0x1800222b6  js      short loc_1800222C4
0x1800222b8  test    r15, r15
0x1800222bb  jnz     loc_18002248D
0x1800222c1  mov     ebx, r13d
0x1800222c4  test    rsi, rsi
0x1800222c7  jz      loc_180022026
0x1800222cd  mov     rcx, rsi; hMem
0x1800222d0  call    cs:__imp_LocalFree
0x1800222d6  jmp     loc_180022026
0x1800222db  mov     ebx, 80090010h
0x1800222e0  jmp     loc_180022010
0x1800222e5  mov     ebx, 8007000Eh
0x1800222ea  jmp     loc_180022026
0x1800222ef  test    ebx, ebx
0x1800222f1  jns     loc_18002216D
0x1800222f7  jmp     short loc_1800222C4
0x1800222f9  mov     rcx, rsi; hMem
0x1800222fc  call    cs:__imp_LocalFree
0x180022302  mov     rsi, r13
0x180022305  test    ebx, ebx
0x180022307  js      loc_180022026
0x18002230d  jmp     loc_1800220E5
0x180022312  test    eax, eax
0x180022314  jle     short loc_180022302
0x180022316  movzx   ebx, ax
0x180022319  or      ebx, 80070000h
0x18002231f  jmp     short loc_180022302
0x180022321  call    cs:__imp_GetLastError
0x180022327  call    cs:__imp_GetLastError
0x18002232d  mov     ebx, eax
0x18002232f  test    eax, eax
0x180022331  jle     short loc_1800222F9
0x180022333  movzx   ebx, ax
0x180022336  or      ebx, 80070000h
0x18002233c  jmp     short loc_1800222F9
0x18002233e  mov     ecx, eax; Status
0x180022340  call    cs:__imp_RtlNtStatusToDosError
0x180022346  mov     ebx, eax
0x180022348  test    eax, eax
0x18002234a  jle     short loc_1800222EF
0x18002234c  movzx   ebx, ax
0x18002234f  or      ebx, 80070000h
0x180022355  jmp     short loc_1800222EF
0x180022357  call    cs:__imp_GetLastError
0x18002235d  mov     ebx, eax
0x18002235f  test    eax, eax
0x180022361  jle     loc_1800222C4
0x180022367  movzx   ebx, ax
0x18002236a  or      ebx, 80070000h
0x180022370  jmp     loc_1800222C4
0x180022375  mov     [r15], r13
0x180022378  jmp     loc_180021F3B
0x18002237d  cmp     eax, 6BDh
0x180022382  jnz     loc_180022022
0x180022388  jmp     loc_180021F4A
0x18002238d  call    cs:__imp_GetLastError
0x180022393  mov     ebx, eax
0x180022395  cmp     eax, 3F0h
0x18002239a  jnz     short loc_180022404
0x18002239c  call    cs:__imp_GetCurrentProcess
0x1800223a2  lea     r8, [rbp+3Fh+TokenHandle]; TokenHandle
0x1800223a6  mov     edx, 0Ah; DesiredAccess
0x1800223ab  mov     rcx, rax; ProcessHandle
  ... truncated ...
```
