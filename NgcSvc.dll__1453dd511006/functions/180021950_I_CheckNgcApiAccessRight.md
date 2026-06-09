# I_CheckNgcApiAccessRight

- ea: `0x180021950`
- end: `0x180021eec`
- name: `I_CheckNgcApiAccessRight`
- size: `1436`
- prototype: ``
- caller_count: `20`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180069f50`
- `0x18006a378`
- `0x18006a7c4`
- `0x18006b150`
- `0x18006cb40`
- `0x18006d0a8`
- `0x18006d2a0`
- `0x18006d918`
- `0x18006df20`
- `0x18006e128`
- `0x18006e554`
- `0x18006f620`
- `0x18006ffbc`
- `0x1800702f8`
- `0x1800706b0`
- `0x1800708b8`
- `0x1800717f4`
- `0x18008447c`
- `0x180084768`
- `0x1800849c0`

## callees

- `0x180021950`
- `0x18005fb04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021a93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021cbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021cc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ced`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021a93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021cbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021cc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021ced`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d5c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180021d0e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180021d0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800219a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800219a4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021cfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180021cfc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800219bc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800219bc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021b79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021d4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021d71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021d8a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021b79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021d4d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021d71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021d8a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180021c65`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180021c65`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180021d3f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180021d3f`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180021b2f`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x180021b2f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021a07`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021a89`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021ad3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021b0f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021a07`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021a89`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021ad3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021b0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021b47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021b6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021c99`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021b47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021b6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021c99`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021aa9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180021aa9`
- `ntdll!RtlIsMultiSessionSku` at `0x180021da9`
- `ntdll!RtlIsMultiSessionSku` at `0x180021da9`
- `ntdll!RtlNtStatusToDosError` at `0x180021dc9`
- `ntdll!RtlNtStatusToDosError` at `0x180021dc9`
- `RPCRT4!RpcRevertToSelf` at `0x180021a1a`
- `RPCRT4!RpcRevertToSelf` at `0x180021d7c`
- `RPCRT4!RpcRevertToSelf` at `0x180021a1a`
- `RPCRT4!RpcRevertToSelf` at `0x180021d7c`
- `RPCRT4!RpcImpersonateClient` at `0x180021984`
- `RPCRT4!RpcImpersonateClient` at `0x180021984`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180021c2e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180021c2e`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180021dbd`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180021dbd`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x180021a35`
- `ext-ms-win-session-winsta-l1-1-0!WinStationIsSessionRemoteable` at `0x180021a35`

## pseudocode

```c
__int64 __fastcall I_CheckNgcApiAccessRight(void *a1, __int64 a2, int a3, const WCHAR *a4, int a5)
{
  PSID *v5; // rdi
  PSID *v6; // rsi
  RPC_STATUS v9; // eax
  signed int LastError; // ebx
  unsigned int v11; // r14d
  int v12; // r15d
  HANDLE CurrentThread; // rax
  signed int v14; // eax
  signed int v16; // eax
  signed int v17; // eax
  HANDLE CurrentProcess; // rax
  NTSTATUS v19; // eax
  _BYTE v20[4]; // [rsp+30h] [rbp-40h] BYREF
  DWORD TokenInformation; // [rsp+34h] [rbp-3Ch] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-38h] BYREF
  DWORD phNewToken[2]; // [rsp+40h] [rbp-30h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-20h] BYREF

  v5 = 0;
  v6 = 0;
  hMem = 0;
  v9 = RpcImpersonateClient(a1);
  LastError = v9;
  v11 = -2146893808;
  if ( v9 )
  {
    v12 = 0;
    if ( v9 != 1725 )
      goto LABEL_19;
  }
  else
  {
    v12 = 1;
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
        *(_QWORD *)phNewToken = 0;
        if ( DuplicateTokenEx(
               TokenHandle,
               0x2000000u,
               0,
               SecurityIdentification,
               TokenImpersonation,
               (PHANDLE)phNewToken) )
        {
          CloseHandle(TokenHandle);
          v5 = *(PSID **)phNewToken;
          goto LABEL_5;
        }
      }
      LastError = GetLastError();
    }
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    if ( LastError < 0 )
      goto LABEL_14;
    goto LABEL_7;
  }
  v5 = (PSID *)TokenHandle;
LABEL_5:
  TokenHandle = 0;
  LastError = 0;
LABEL_7:
  TokenInformation = 0;
  ReturnLength = 0;
  v20[0] = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
  {
    if ( v12 )
    {
      RpcRevertToSelf();
      v12 = 0;
    }
    if ( (unsigned __int8)IsWinStationIsSessionRemoteablePresent()
      && (unsigned __int8)WinStationIsSessionRemoteable(0, TokenInformation, v20)
      && v20[0] )
    {
      LastError = -2146893808;
    }
    else
    {
      v6 = v5;
      v5 = 0;
    }
  }
  else
  {
    LastError = -2146893808;
  }
LABEL_14:
  if ( v12 )
    RpcRevertToSelf();
  if ( v5 )
    CloseHandle(v5);
  v5 = 0;
LABEL_19:
  if ( LastError < 0 )
    goto LABEL_31;
  TokenInformation = 0;
  if ( GetTokenInformation(v6, TokenUser, 0, 0, &TokenInformation)
    || (v14 = GetLastError(), LastError = v14, v14 == 122) )
  {
    v5 = (PSID *)LocalAlloc(0, TokenInformation);
    if ( !v5 )
    {
      LastError = -2147024882;
      goto LABEL_31;
    }
    if ( GetTokenInformation(v6, TokenUser, v5, TokenInformation, &TokenInformation) )
      goto LABEL_24;
    GetLastError();
    v17 = GetLastError();
    LastError = v17;
    if ( v17 > 0 )
      LastError = (unsigned __int16)v17 | 0x80070000;
    LocalFree(v5);
    v5 = 0;
  }
  else if ( v14 > 0 )
  {
    LastError = (unsigned __int16)v14 | 0x80070000;
  }
  if ( LastError < 0 )
    goto LABEL_31;
LABEL_24:
  if ( a2 )
  {
    ReturnLength = 0;
    phNewToken[0] = 0;
    if ( !GetTokenInformation(v6, TokenIsAppContainer, &ReturnLength, 4u, phNewToken) )
    {
LABEL_53:
      v16 = GetLastError();
LABEL_54:
      LastError = v16;
      if ( v16 > 0 )
        LastError = (unsigned __int16)v16 | 0x80070000;
      goto LABEL_29;
    }
    if ( ReturnLength == 1 )
    {
      v20[0] = 0;
      if ( a3 && (unsigned __int8)RtlIsMultiSessionSku() || (v19 = CapabilityCheck(v6, a2, v20)) == 0 )
      {
        LastError = -2147024891;
        if ( v20[0] )
          LastError = 0;
        goto LABEL_29;
      }
      v16 = RtlNtStatusToDosError(v19);
      goto LABEL_54;
    }
  }
  if ( !IsWellKnownSid(*v5, WinLocalSystemSid) )
  {
    if ( !a4 )
    {
      LastError = -2147024891;
      if ( a5 )
        LastError = 0;
      goto LABEL_29;
    }
    if ( ConvertStringSidToSidW(a4, &hMem) )
    {
      LastError = -2147024891;
      if ( EqualSid(hMem, *v5) )
        LastError = 0;
      goto LABEL_29;
    }
    goto LABEL_53;
  }
  LastError = 0;
LABEL_29:
  if ( v5 )
    LocalFree(v5);
LABEL_31:
  if ( hMem )
    LocalFree(hMem);
  if ( v6 )
    CloseHandle(v6);
  if ( LastError > -2147014847 )
  {
    if ( LastError > -2147014831 )
    {
      switch ( LastError )
      {
        case -2146434965:
          return (unsigned int)-2146893773;
        case -2146434964:
          return (unsigned int)-2146893775;
        case -2089418750:
          return (unsigned int)-2146893819;
      }
      return (unsigned int)LastError;
    }
    if ( LastError != -2147014831 )
    {
      switch ( LastError )
      {
        case -2147014846:
          v11 = -2146893776;
          break;
        case -2147014844:
        case -2147014843:
        case -2147014842:
        case -2147014839:
        case -2147014838:
        case -2147014836:
        case -2147014835:
          return (unsigned int)-2146893771;
        default:
          return (unsigned int)LastError;
      }
      return v11;
    }
    return (unsigned int)-2146893771;
  }
  if ( LastError == -2147014847 )
    return (unsigned int)-2146893771;
  if ( LastError > -2147024891 )
  {
    if ( LastError == -2147024882 )
      return (unsigned int)-2146893810;
    if ( LastError != -2147024809 )
    {
      if ( LastError == -2147024713 )
        return (unsigned int)-2146893809;
      if ( LastError != -2147023728 )
      {
        if ( LastError == -2147023673 )
          return (unsigned int)-2146893770;
        return (unsigned int)LastError;
      }
      return (unsigned int)-2146893807;
    }
    return (unsigned int)-2146893785;
  }
  if ( LastError != -2147024891 )
  {
    if ( LastError == -2147467263 )
      return (unsigned int)-2146893783;
    if ( LastError != -2147467261 )
    {
      if ( LastError == -2147467259 )
        return (unsigned int)-2146893792;
      if ( LastError == -2147418113 )
        return (unsigned int)-2146893779;
      if ( LastError != -2147024894 )
        return (unsigned int)LastError;
      return (unsigned int)-2146893807;
    }
    return (unsigned int)-2146893785;
  }
  return v11;
}

```

## disassembly

```asm
0x180021950  mov     rax, rsp
0x180021953  mov     [rax+18h], r8d
0x180021957  push    rbp
0x180021958  push    rbx
0x180021959  push    r14
0x18002195b  mov     rbp, rsp
0x18002195e  sub     rsp, 70h
0x180021962  mov     [rax+8], rsi
0x180021966  mov     [rax+10h], rdi
0x18002196a  xor     edi, edi
0x18002196c  mov     [rax+20h], r12
0x180021970  mov     esi, edi
0x180021972  mov     [rax-20h], r13
0x180021976  mov     r12, rdx
0x180021979  mov     [rax-28h], r15
0x18002197d  mov     r13, r9
0x180021980  mov     [rbp+hMem], rdi
0x180021984  call    cs:__imp_RpcImpersonateClient
0x18002198a  mov     ebx, eax
0x18002198c  mov     r14d, 80090010h
0x180021992  test    eax, eax
0x180021994  jnz     loc_180021CDA
0x18002199a  mov     r15d, 1
0x1800219a0  mov     [rbp+TokenHandle], rdi
0x1800219a4  call    cs:__imp_GetCurrentThread
0x1800219aa  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1800219ae  mov     edx, 8; DesiredAccess
0x1800219b3  mov     rcx, rax; ThreadHandle
0x1800219b6  mov     r8d, 1; OpenAsSelf
0x1800219bc  call    cs:__imp_OpenThreadToken
0x1800219c2  test    eax, eax
0x1800219c4  jz      loc_180021CED
0x1800219ca  mov     rdi, [rbp+TokenHandle]
0x1800219ce  xor     eax, eax
0x1800219d0  mov     [rbp+TokenHandle], rax
0x1800219d4  mov     ebx, eax
0x1800219d6  jmp     short loc_1800219DE
0x1800219d8  test    ebx, ebx
0x1800219da  js      short loc_180021A4E
0x1800219dc  xor     eax, eax
0x1800219de  mov     [rbp+TokenInformation], eax
0x1800219e1  lea     r8, [rbp+TokenInformation]; TokenInformation
0x1800219e5  mov     [rbp+var_38], eax
0x1800219e8  mov     r9d, 4; TokenInformationLength
0x1800219ee  lea     rax, [rbp+var_38]
0x1800219f2  mov     [rbp+var_40], sil
0x1800219f6  mov     edx, 0Ch; TokenInformationClass
0x1800219fb  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180021a00  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x180021a07  call    cs:__imp_GetTokenInformation
0x180021a0d  test    eax, eax
0x180021a0f  jz      loc_180021C56
0x180021a15  test    r15d, r15d
0x180021a18  jz      short loc_180021A23
0x180021a1a  call    cs:__imp_RpcRevertToSelf
0x180021a20  xor     r15d, r15d
0x180021a23  call    IsWinStationIsSessionRemoteablePresent
0x180021a28  test    al, al
0x180021a2a  jz      short loc_180021A49
0x180021a2c  mov     edx, [rbp+TokenInformation]
0x180021a2f  lea     r8, [rbp+var_40]
0x180021a33  xor     ecx, ecx
0x180021a35  call    cs:__imp_WinStationIsSessionRemoteable
0x180021a3b  test    al, al
0x180021a3d  jz      short loc_180021A49
0x180021a3f  cmp     [rbp+var_40], sil
0x180021a43  jnz     loc_180021C7C
0x180021a49  mov     rsi, rdi
0x180021a4c  xor     edi, edi
0x180021a4e  test    r15d, r15d
0x180021a51  jnz     loc_180021D7C
0x180021a57  test    rdi, rdi
0x180021a5a  jnz     loc_180021D87
0x180021a60  xor     edi, edi
0x180021a62  mov     r15, [rsp+70h+var_10]
0x180021a67  test    ebx, ebx
0x180021a69  js      loc_180021B4D
0x180021a6f  lea     rax, [rbp+TokenInformation]
0x180021a73  mov     [rbp+TokenInformation], edi
0x180021a76  xor     r9d, r9d; TokenInformationLength
0x180021a79  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180021a7e  xor     r8d, r8d; TokenInformation
0x180021a81  mov     edx, 1; TokenInformationClass
0x180021a86  mov     rcx, rsi; TokenHandle
0x180021a89  call    cs:__imp_GetTokenInformation
0x180021a8f  test    eax, eax
0x180021a91  jnz     short loc_180021AA4
0x180021a93  call    cs:__imp_GetLastError
0x180021a99  mov     ebx, eax
0x180021a9b  cmp     eax, 7Ah ; 'z'
0x180021a9e  jnz     loc_180021CAE
0x180021aa4  mov     edx, [rbp+TokenInformation]; uBytes
0x180021aa7  xor     ecx, ecx; uFlags
0x180021aa9  call    cs:__imp_LocalAlloc
0x180021aaf  mov     rdi, rax
0x180021ab2  test    rax, rax
0x180021ab5  jz      loc_180021D95
0x180021abb  mov     r9d, [rbp+TokenInformation]; TokenInformationLength
0x180021abf  lea     rax, [rbp+TokenInformation]
0x180021ac3  mov     r8, rdi; TokenInformation
0x180021ac6  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180021acb  mov     edx, 1; TokenInformationClass
0x180021ad0  mov     rcx, rsi; TokenHandle
0x180021ad3  call    cs:__imp_GetTokenInformation
0x180021ad9  test    eax, eax
0x180021adb  jz      loc_180021CBD
0x180021ae1  test    r12, r12
0x180021ae4  jz      short loc_180021B27
0x180021ae6  lea     rax, [rbp+var_30]
0x180021aea  mov     [rbp+var_38], 0
0x180021af1  mov     r9d, 4; TokenInformationLength
0x180021af7  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x180021afc  lea     r8, [rbp+var_38]; TokenInformation
0x180021b00  mov     [rbp+var_30], 0
0x180021b07  mov     edx, 1Dh; TokenInformationClass
0x180021b0c  mov     rcx, rsi; TokenHandle
0x180021b0f  call    cs:__imp_GetTokenInformation
0x180021b15  test    eax, eax
0x180021b17  jz      loc_180021C38
0x180021b1d  cmp     [rbp+var_38], 1
0x180021b21  jz      loc_180021D9F
0x180021b27  mov     rcx, [rdi]; pSid
0x180021b2a  mov     edx, 16h; WellKnownSidType
0x180021b2f  call    cs:__imp_IsWellKnownSid
0x180021b35  test    eax, eax
0x180021b37  jz      loc_180021C22
0x180021b3d  xor     ebx, ebx
0x180021b3f  test    rdi, rdi
0x180021b42  jz      short loc_180021B4D
0x180021b44  mov     rcx, rdi; hMem
0x180021b47  call    cs:__imp_LocalFree
0x180021b4d  mov     rcx, [rbp+hMem]; hMem
0x180021b51  mov     r13, [rsp+70h+var_8]
0x180021b56  mov     r12, [rsp+70h+arg_18]
0x180021b5e  mov     rdi, [rsp+70h+arg_8]
0x180021b66  test    rcx, rcx
0x180021b69  jz      short loc_180021B71
0x180021b6b  call    cs:__imp_LocalFree
0x180021b71  test    rsi, rsi
0x180021b74  jz      short loc_180021B7F
0x180021b76  mov     rcx, rsi; hObject
0x180021b79  call    cs:__imp_CloseHandle
0x180021b7f  mov     rsi, [rsp+70h+arg_0]
0x180021b87  cmp     ebx, 80072741h
0x180021b8d  jg      short loc_180021BEE
0x180021b8f  jz      loc_180021E9B; jumptable 0000000180021E8E cases -2147014844--2147014842,-2147014839,-2147014838,-2147014836,-2147014835
0x180021b95  cmp     ebx, 80070005h
0x180021b9b  jg      loc_180021E07
0x180021ba1  jz      short loc_180021BE2
0x180021ba3  cmp     ebx, 80004001h
0x180021ba9  jz      loc_180021DFC
0x180021baf  cmp     ebx, 80004003h
0x180021bb5  jz      loc_180021E54
0x180021bbb  cmp     ebx, 80004005h
0x180021bc1  jz      loc_180021DF1
0x180021bc7  cmp     ebx, 8000FFFFh
0x180021bcd  jz      loc_180021DE6
0x180021bd3  cmp     ebx, 80070002h
0x180021bd9  jz      loc_180021E3E
0x180021bdf  mov     r14d, ebx; jumptable 0000000180021E8E default case, cases -2147014845,-2147014841,-2147014840,-2147014837
0x180021be2  mov     eax, r14d
0x180021be5  add     rsp, 70h
0x180021be9  pop     r14
0x180021beb  pop     rbx
0x180021bec  pop     rbp
0x180021bed  retn
0x180021bee  cmp     ebx, 80072751h
0x180021bf4  jle     loc_180021E6A
0x180021bfa  cmp     ebx, 8010006Bh
0x180021c00  jz      loc_180021EB1
0x180021c06  cmp     ebx, 8010006Ch
0x180021c0c  jz      loc_180021EA6
0x180021c12  cmp     ebx, 83760002h
0x180021c18  jnz     short def_180021E8E; jumptable 0000000180021E8E default case, cases -2147014845,-2147014841,-2147014840,-2147014837
0x180021c1a  mov     r14d, 80090005h
0x180021c20  jmp     short loc_180021BE2
0x180021c22  test    r13, r13
0x180021c25  jz      short loc_180021C84
0x180021c27  lea     rdx, [rbp+hMem]; Sid
0x180021c2b  mov     rcx, r13; StringSid
0x180021c2e  call    cs:__imp_ConvertStringSidToSidW
0x180021c34  test    eax, eax
0x180021c36  jnz     short loc_180021C5E
0x180021c38  call    cs:__imp_GetLastError
0x180021c3e  mov     ebx, eax
0x180021c40  test    eax, eax
0x180021c42  jle     loc_180021B3F
0x180021c48  movzx   ebx, ax
0x180021c4b  or      ebx, 80070000h
0x180021c51  jmp     loc_180021B3F
0x180021c56  mov     ebx, r14d
0x180021c59  jmp     loc_180021A4E
0x180021c5e  mov     rdx, [rdi]; pSid2
0x180021c61  mov     rcx, [rbp+hMem]; pSid1
0x180021c65  call    cs:__imp_EqualSid
0x180021c6b  xor     edx, edx
0x180021c6d  mov     ebx, 80070005h
0x180021c72  test    eax, eax
0x180021c74  cmovnz  ebx, edx
0x180021c77  jmp     loc_180021B3F
0x180021c7c  mov     ebx, r14d
0x180021c7f  jmp     loc_180021A4E
0x180021c84  xor     eax, eax
0x180021c86  mov     ebx, 80070005h
0x180021c8b  cmp     [rbp+arg_20], eax
0x180021c8e  cmovnz  ebx, eax
0x180021c91  jmp     loc_180021B3F
0x180021c96  mov     rcx, rdi; hMem
0x180021c99  call    cs:__imp_LocalFree
0x180021c9f  xor     edi, edi
0x180021ca1  test    ebx, ebx
0x180021ca3  jns     loc_180021AE1
0x180021ca9  jmp     loc_180021B4D
0x180021cae  test    eax, eax
0x180021cb0  jle     short loc_180021CA1
0x180021cb2  movzx   ebx, ax
0x180021cb5  or      ebx, 80070000h
0x180021cbb  jmp     short loc_180021CA1
0x180021cbd  call    cs:__imp_GetLastError
0x180021cc3  call    cs:__imp_GetLastError
0x180021cc9  mov     ebx, eax
0x180021ccb  test    eax, eax
0x180021ccd  jle     short loc_180021C96
0x180021ccf  movzx   ebx, ax
0x180021cd2  or      ebx, 80070000h
0x180021cd8  jmp     short loc_180021C96
0x180021cda  mov     r15d, edi
0x180021cdd  cmp     eax, 6BDh
0x180021ce2  jnz     loc_180021A62
0x180021ce8  jmp     loc_1800219A0
0x180021ced  call    cs:__imp_GetLastError
0x180021cf3  mov     ebx, eax
0x180021cf5  cmp     eax, 3F0h
0x180021cfa  jnz     short loc_180021D64
0x180021cfc  call    cs:__imp_GetCurrentProcess
0x180021d02  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180021d06  mov     edx, 0Ah; DesiredAccess
0x180021d0b  mov     rcx, rax; ProcessHandle
0x180021d0e  call    cs:__imp_OpenProcessToken
0x180021d14  test    eax, eax
0x180021d16  jz      short loc_180021D5C
0x180021d18  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x180021d1c  lea     rax, [rbp+var_30]
0x180021d20  mov     [rsp+70h+phNewToken], rax; phNewToken
0x180021d25  mov     r9d, 1; ImpersonationLevel
0x180021d2b  xor     r8d, r8d; lpTokenAttributes
0x180021d2e  mov     dword ptr [rsp+70h+ReturnLength], 2; TokenType
0x180021d36  mov     edx, 2000000h; dwDesiredAccess
0x180021d3b  mov     qword ptr [rbp+var_30], rdi
0x180021d3f  call    cs:__imp_DuplicateTokenEx
0x180021d45  test    eax, eax
0x180021d47  jz      short loc_180021D5C
0x180021d49  mov     rcx, [rbp+TokenHandle]; hObject
0x180021d4d  call    cs:__imp_CloseHandle
0x180021d53  mov     rdi, qword ptr [rbp+var_30]
0x180021d57  jmp     loc_1800219CE
0x180021d5c  call    cs:__imp_GetLastError
0x180021d62  mov     ebx, eax
0x180021d64  mov     rcx, [rbp+TokenHandle]; hObject
0x180021d68  test    rcx, rcx
0x180021d6b  jz      loc_1800219D8
0x180021d71  call    cs:__imp_CloseHandle
0x180021d77  jmp     loc_1800219D8
0x180021d7c  call    cs:__imp_RpcRevertToSelf
0x180021d82  jmp     loc_180021A57
0x180021d87  mov     rcx, rdi; hObject
0x180021d8a  call    cs:__imp_CloseHandle
0x180021d90  jmp     loc_180021A60
0x180021d95  mov     ebx, 8007000Eh
0x180021d9a  jmp     loc_180021B4D
0x180021d9f  cmp     [rbp+arg_10], 0
0x180021da3  mov     [rbp+var_40], 0
0x180021da7  jz      short loc_180021DB3
0x180021da9  call    cs:__imp_RtlIsMultiSessionSku
0x180021daf  test    al, al
0x180021db1  jnz     short loc_180021DD4
0x180021db3  lea     r8, [rbp+var_40]
0x180021db7  mov     rdx, r12
0x180021dba  mov     rcx, rsi
0x180021dbd  call    cs:__imp_CapabilityCheck
0x180021dc3  test    eax, eax
0x180021dc5  jz      short loc_180021DD4
0x180021dc7  mov     ecx, eax; Status
0x180021dc9  call    cs:__imp_RtlNtStatusToDosError
0x180021dcf  jmp     loc_180021C3E
0x180021dd4  xor     eax, eax
0x180021dd6  mov     ebx, 80070005h
0x180021ddb  cmp     [rbp+var_40], al
0x180021dde  cmovnz  ebx, eax
0x180021de1  jmp     loc_180021B3F
0x180021de6  mov     r14d, 8009002Dh
0x180021dec  jmp     loc_180021BE2
0x180021df1  mov     r14d, 80090020h
0x180021df7  jmp     loc_180021BE2
0x180021dfc  mov     r14d, 80090029h
0x180021e02  jmp     loc_180021BE2
0x180021e07  cmp     ebx, 8007000Eh
0x180021e0d  jz      short loc_180021E5F
0x180021e0f  cmp     ebx, 80070057h
0x180021e15  jz      short loc_180021E54
  ... truncated ...
```
