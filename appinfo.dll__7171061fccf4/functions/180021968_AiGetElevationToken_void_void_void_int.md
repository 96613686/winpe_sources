# AiGetElevationToken(void *,void *,void * *,int *)

- ea: `0x180021968`
- end: `0x180021b3a`
- name: `?AiGetElevationToken@@YAKPEAX0PEAPEAXPEAH@Z`
- size: `466`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, HANDLE, PHANDLE phNewToken, int *)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180026ba0`
- `0x1800409a0`

## callees

- `0x18000bde0`
- `0x18000c410`
- `0x18001158c`
- `0x18001b0d0`
- `0x18001d034`
- `0x180021968`
- `0x180028a3c`
- `0x1800290b4`
- `0x180045e88`
- `0x1800461e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021a6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021a6b`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800219d3`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800219d3`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180021a27`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180021a27`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021a61`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180021a61`
- `USERENV!UnloadUserProfile` at `0x180021b0b`
- `USERENV!UnloadUserProfile` at `0x180021b0b`

## pseudocode

```c
__int64 __fastcall AiGetElevationToken(HANDLE TokenHandle, HANDLE a2, PHANDLE phNewToken, int *a4)
{
  NTSTATUS v8; // eax
  ULONG LastError; // eax
  unsigned int UserProfile; // ebx
  int v11; // eax
  unsigned int TokenInformation; // [rsp+50h] [rbp-28h] BYREF
  int v14; // [rsp+54h] [rbp-24h] BYREF
  DWORD ReturnLength; // [rsp+58h] [rbp-20h] BYREF
  HANDLE hExistingToken; // [rsp+60h] [rbp-18h] BYREF
  HANDLE hProfile[2]; // [rsp+68h] [rbp-10h] BYREF

  TokenInformation = 0;
  ReturnLength = 0;
  v14 = 1;
  hProfile[0] = 0;
  hExistingToken = 0;
  if ( !(unsigned int)LUAIsShadowAdminEnabled() )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hExistingToken,
      0);
    v8 = LUAGetElevatedToken(a2, &hExistingToken);
    if ( v8 < 0 )
    {
LABEL_3:
      LastError = RtlNtStatusToDosErrorNoTeb(v8);
LABEL_4:
      UserProfile = LastError;
      goto LABEL_21;
    }
    UserProfile = 0;
    goto LABEL_6;
  }
  UserProfile = AiBuildElevateTokenAPIParams((struct _CONSENTUI_PARAM_HEADER **)hProfile);
  if ( UserProfile )
    goto LABEL_21;
  if ( !GetTokenInformation(a2, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
    goto LABEL_15;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hExistingToken,
    0);
  UserProfile = AiLaunchConsentUI(
                  a2,
                  (int *)hProfile[0],
                  L"Winsta0\\Default",
                  0,
                  TokenInformation,
                  0x10000000u,
                  9u,
                  0xFFFFFFFF,
                  0,
                  &hExistingToken);
  if ( !UserProfile )
  {
    hProfile[0] = 0;
    UserProfile = AipLoadUserProfile(hExistingToken, hProfile);
    if ( !UserProfile )
    {
      UserProfile = AipAddProfileReference(TokenInformation, hExistingToken, hProfile[0]);
      if ( UserProfile )
      {
        UnloadUserProfile(hExistingToken, hProfile[0]);
        goto LABEL_21;
      }
LABEL_6:
      if ( !TokenHandle )
        goto LABEL_20;
      v8 = AiCheckForTcbPrivilege(TokenHandle, &v14);
      if ( v8 < 0 )
        goto LABEL_3;
      v11 = v14;
      if ( a4 )
        *a4 = v14;
      if ( v11 )
      {
LABEL_20:
        *phNewToken = hExistingToken;
        hExistingToken = 0;
        goto LABEL_21;
      }
      if ( DuplicateTokenEx(hExistingToken, 0, 0, SecurityIdentification, TokenImpersonation, phNewToken) )
        goto LABEL_21;
LABEL_15:
      LastError = GetLastError();
      goto LABEL_4;
    }
  }
LABEL_21:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hExistingToken);
  return UserProfile;
}

```

## disassembly

```asm
0x180021968  push    rbp
0x18002196a  push    rbx
0x18002196b  push    rsi
0x18002196c  push    rdi
0x18002196d  push    r14
0x18002196f  push    r15
0x180021971  mov     rbp, rsp
0x180021974  sub     rsp, 78h
0x180021978  mov     rsi, r9
0x18002197b  mov     [rbp+TokenInformation], 0
0x180021982  mov     r15, r8
0x180021985  mov     [rbp+ReturnLength], 0
0x18002198c  mov     rdi, rdx
0x18002198f  mov     [rbp+var_24], 1
0x180021996  mov     r14, rcx
0x180021999  mov     [rbp+hProfile], 0
0x1800219a1  mov     [rbp+hExistingToken], 0
0x1800219a9  call    LUAIsShadowAdminEnabled
0x1800219ae  test    eax, eax
0x1800219b0  jnz     loc_180021A37
0x1800219b6  xor     edx, edx
0x1800219b8  lea     rcx, [rbp+hExistingToken]
0x1800219bc  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800219c1  lea     rdx, [rbp+hExistingToken]; NewTokenHandle
0x1800219c5  mov     rcx, rdi; TokenHandle
0x1800219c8  call    LUAGetElevatedToken
0x1800219cd  test    eax, eax
0x1800219cf  jns     short loc_1800219E0
0x1800219d1  mov     ecx, eax; Status
0x1800219d3  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800219d9  mov     ebx, eax
0x1800219db  jmp     loc_180021B22
0x1800219e0  xor     ebx, ebx
0x1800219e2  test    r14, r14
0x1800219e5  jz      loc_180021B13
0x1800219eb  lea     rdx, [rbp+var_24]; int *
0x1800219ef  mov     rcx, r14; TokenHandle
0x1800219f2  call    ?AiCheckForTcbPrivilege@@YAJPEAXPEAH@Z; AiCheckForTcbPrivilege(void *,int *)
0x1800219f7  test    eax, eax
0x1800219f9  js      short loc_1800219D1
0x1800219fb  mov     eax, [rbp+var_24]
0x1800219fe  test    rsi, rsi
0x180021a01  jz      short loc_180021A05
0x180021a03  mov     [rsi], eax
0x180021a05  test    eax, eax
0x180021a07  jnz     loc_180021B13
0x180021a0d  mov     rcx, [rbp+hExistingToken]; hExistingToken
0x180021a11  lea     r9d, [rax+1]; ImpersonationLevel
0x180021a15  mov     [rsp+78h+phNewToken], r15; phNewToken
0x180021a1a  xor     r8d, r8d; lpTokenAttributes
0x180021a1d  xor     edx, edx; dwDesiredAccess
0x180021a1f  mov     [rsp+78h+TokenType], 2; TokenType
0x180021a27  call    cs:__imp_DuplicateTokenEx
0x180021a2d  test    eax, eax
0x180021a2f  jnz     loc_180021B22
0x180021a35  jmp     short loc_180021A6B
0x180021a37  lea     rcx, [rbp+hProfile]; struct _CONSENTUI_PARAM_HEADER **
0x180021a3b  call    ?AiBuildElevateTokenAPIParams@@YAKPEAPEAU_CONSENTUI_PARAM_HEADER@@@Z; AiBuildElevateTokenAPIParams(_CONSENTUI_PARAM_HEADER * *)
0x180021a40  mov     ebx, eax
0x180021a42  test    eax, eax
0x180021a44  jnz     loc_180021B22
0x180021a4a  lea     rax, [rbp+ReturnLength]
0x180021a4e  mov     rcx, rdi; TokenHandle
0x180021a51  lea     r9d, [rbx+4]; TokenInformationLength
0x180021a55  mov     qword ptr [rsp+78h+TokenType], rax; ReturnLength
0x180021a5a  lea     r8, [rbp+TokenInformation]; TokenInformation
0x180021a5e  lea     edx, [rbx+0Ch]; TokenInformationClass
0x180021a61  call    cs:__imp_GetTokenInformation
0x180021a67  test    eax, eax
0x180021a69  jnz     short loc_180021A76
0x180021a6b  call    cs:__imp_GetLastError
0x180021a71  jmp     loc_1800219D9
0x180021a76  xor     edx, edx
0x180021a78  lea     rcx, [rbp+hExistingToken]
0x180021a7c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180021a81  mov     eax, [rbp+TokenInformation]
0x180021a84  lea     rcx, [rbp+hExistingToken]
0x180021a88  mov     rdx, [rbp+hProfile]
0x180021a8c  lea     r8, aWinsta0Default; "Winsta0\\Default"
0x180021a93  mov     [rsp+78h+var_30], rcx
0x180021a98  xor     r9d, r9d
0x180021a9b  mov     [rsp+78h+var_38], 0
0x180021aa4  mov     rcx, rdi
0x180021aa7  mov     [rsp+78h+var_40], 0FFFFFFFFh
0x180021aaf  mov     [rsp+78h+var_48], 9
0x180021ab7  mov     dword ptr [rsp+78h+phNewToken], 10000000h
0x180021abf  mov     [rsp+78h+TokenType], eax
0x180021ac3  call    ?AiLaunchConsentUI@@YAKPEAXPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAUHWND__@@KKW4ELEVATION_REASON@@KPEBDPEAPEAX@Z; AiLaunchConsentUI(void *,_CONSENTUI_PARAM_HEADER *,ushort const *,HWND__ *,ulong,ulong,ELEVATION_REASON,ulong,char const *,void * *)
0x180021ac8  mov     ebx, eax
0x180021aca  test    eax, eax
0x180021acc  jnz     short loc_180021B22
0x180021ace  mov     rcx, [rbp+hExistingToken]; hToken
0x180021ad2  lea     rdx, [rbp+hProfile]; void **
0x180021ad6  mov     [rbp+hProfile], 0
0x180021ade  call    ?AipLoadUserProfile@@YAKPEAXPEAPEAX@Z; AipLoadUserProfile(void *,void * *)
0x180021ae3  mov     ebx, eax
0x180021ae5  test    eax, eax
0x180021ae7  jnz     short loc_180021B22
0x180021ae9  mov     r8, [rbp+hProfile]; void *
0x180021aed  mov     rdx, [rbp+hExistingToken]; void *
0x180021af1  mov     ecx, [rbp+TokenInformation]; unsigned int
0x180021af4  call    ?AipAddProfileReference@@YAKKPEAX0@Z; AipAddProfileReference(ulong,void *,void *)
0x180021af9  mov     ebx, eax
0x180021afb  test    eax, eax
0x180021afd  jz      loc_1800219E2
0x180021b03  mov     rdx, [rbp+hProfile]; hProfile
0x180021b07  mov     rcx, [rbp+hExistingToken]; hToken
0x180021b0b  call    cs:__imp_UnloadUserProfile
0x180021b11  jmp     short loc_180021B22
0x180021b13  mov     rax, [rbp+hExistingToken]
0x180021b17  mov     [r15], rax
0x180021b1a  mov     [rbp+hExistingToken], 0
0x180021b22  lea     rcx, [rbp+hExistingToken]
0x180021b26  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180021b2b  mov     eax, ebx
0x180021b2d  add     rsp, 78h
0x180021b31  pop     r15
0x180021b33  pop     r14
0x180021b35  pop     rdi
0x180021b36  pop     rsi
0x180021b37  pop     rbx
0x180021b38  pop     rbp
0x180021b39  retn
```
