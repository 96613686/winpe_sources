# AiGetElevationToken(void *,void *,void * *,int *)

- ea: `0x18001e424`
- end: `0x18001e5b1`
- name: `?AiGetElevationToken@@YAKPEAX0PEAPEAXPEAH@Z`
- size: `397`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, HANDLE, PHANDLE DuplicateTokenHandle, int *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800249f0`
- `0x18003bfe0`

## callees

- `0x18000c790`
- `0x18000f8b0`
- `0x18001ac0c`
- `0x18001e424`
- `0x180025cfc`
- `0x1800263a8`
- `0x180041b0c`
- `0x180041e64`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001e56a`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001e56a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e4c9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e4c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e4d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e4d9`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001e48c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001e48c`

## pseudocode

```c
__int64 __fastcall AiGetElevationToken(HANDLE TokenHandle, HANDLE a2, PHANDLE DuplicateTokenHandle, int *a4)
{
  unsigned int v4; // ebx
  NTSTATUS v9; // eax
  DWORD LastError; // eax
  int v11; // eax
  HANDLE v12; // rax
  int TokenInformation; // [rsp+50h] [rbp-20h] BYREF
  int v15; // [rsp+54h] [rbp-1Ch] BYREF
  DWORD ReturnLength; // [rsp+58h] [rbp-18h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+60h] [rbp-10h] BYREF
  struct _CONSENTUI_PARAM_HEADER *v18; // [rsp+68h] [rbp-8h] BYREF

  v4 = 0;
  v15 = 1;
  TokenInformation = 0;
  ReturnLength = 0;
  v18 = 0;
  ExistingTokenHandle = 0;
  if ( (unsigned int)LUAIsShadowAdminEnabled() )
  {
    v4 = AiBuildElevateTokenAPIParams(&v18);
    if ( v4 )
      goto LABEL_17;
    if ( !GetTokenInformation(a2, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
      goto LABEL_7;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &ExistingTokenHandle,
      0);
    v4 = AiLaunchConsentUI(
           a2,
           v18,
           L"Winsta0\\Default",
           0,
           TokenInformation,
           0x10000000,
           9,
           -1,
           0,
           &ExistingTokenHandle);
    if ( v4 )
      goto LABEL_17;
LABEL_9:
    if ( !TokenHandle )
      goto LABEL_16;
    v9 = AiCheckForTcbPrivilege(TokenHandle, &v15);
    if ( v9 < 0 )
      goto LABEL_3;
    v11 = v15;
    if ( a4 )
      *a4 = v15;
    if ( v11 )
    {
LABEL_16:
      v12 = ExistingTokenHandle;
      ExistingTokenHandle = 0;
      *DuplicateTokenHandle = v12;
      goto LABEL_17;
    }
    if ( DuplicateToken(ExistingTokenHandle, SecurityIdentification, DuplicateTokenHandle) )
      goto LABEL_17;
LABEL_7:
    LastError = GetLastError();
    goto LABEL_4;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &ExistingTokenHandle,
    0);
  v9 = LUAGetElevatedToken(a2, &ExistingTokenHandle);
  if ( v9 >= 0 )
    goto LABEL_9;
LABEL_3:
  LastError = RtlNtStatusToDosErrorNoTeb(v9);
LABEL_4:
  v4 = LastError;
LABEL_17:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ExistingTokenHandle);
  return v4;
}

```

## disassembly

```asm
0x18001e424  mov     [rsp-18h+arg_0], rbx
0x18001e429  mov     [rsp-18h+arg_8], rsi
0x18001e42e  mov     [rsp-18h+arg_10], rdi
0x18001e433  push    rbp
0x18001e434  push    r14
0x18001e436  push    r15
0x18001e438  mov     rbp, rsp
0x18001e43b  sub     rsp, 70h
0x18001e43f  xor     ebx, ebx
0x18001e441  mov     [rbp+var_1C], 1
0x18001e448  and     [rbp+TokenInformation], ebx
0x18001e44b  mov     rdi, r9
0x18001e44e  and     [rbp+var_18], ebx
0x18001e451  mov     r15, r8
0x18001e454  and     [rbp+var_8], rbx
0x18001e458  mov     r14, rdx
0x18001e45b  and     [rbp+ExistingTokenHandle], rbx
0x18001e45f  mov     rsi, rcx
0x18001e462  call    LUAIsShadowAdminEnabled
0x18001e467  test    eax, eax
0x18001e469  jnz     short loc_18001E49F
0x18001e46b  xor     edx, edx
0x18001e46d  lea     rcx, [rbp+ExistingTokenHandle]
0x18001e471  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001e476  lea     rdx, [rbp+ExistingTokenHandle]; NewTokenHandle
0x18001e47a  mov     rcx, r14; TokenHandle
0x18001e47d  call    LUAGetElevatedToken
0x18001e482  test    eax, eax
0x18001e484  jns     loc_18001E539
0x18001e48a  mov     ecx, eax; Status
0x18001e48c  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18001e493  nop     dword ptr [rax+rax+00h]
0x18001e498  mov     ebx, eax
0x18001e49a  jmp     loc_18001E58B
0x18001e49f  lea     rcx, [rbp+var_8]; struct _CONSENTUI_PARAM_HEADER **
0x18001e4a3  call    ?AiBuildElevateTokenAPIParams@@YAKPEAPEAU_CONSENTUI_PARAM_HEADER@@@Z; AiBuildElevateTokenAPIParams(_CONSENTUI_PARAM_HEADER * *)
0x18001e4a8  mov     ebx, eax
0x18001e4aa  test    eax, eax
0x18001e4ac  jnz     loc_18001E58B
0x18001e4b2  lea     rax, [rbp+var_18]
0x18001e4b6  mov     rcx, r14; TokenHandle
0x18001e4b9  lea     r9d, [rbx+4]; TokenInformationLength
0x18001e4bd  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18001e4c2  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18001e4c6  lea     edx, [rbx+0Ch]; TokenInformationClass
0x18001e4c9  call    cs:__imp_GetTokenInformation
0x18001e4d0  nop     dword ptr [rax+rax+00h]
0x18001e4d5  test    eax, eax
0x18001e4d7  jnz     short loc_18001E4E7
0x18001e4d9  call    cs:__imp_GetLastError
0x18001e4e0  nop     dword ptr [rax+rax+00h]
0x18001e4e5  jmp     short loc_18001E498
0x18001e4e7  xor     edx, edx
0x18001e4e9  lea     rcx, [rbp+ExistingTokenHandle]
0x18001e4ed  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001e4f2  mov     rdx, [rbp+var_8]
0x18001e4f6  lea     rax, [rbp+ExistingTokenHandle]
0x18001e4fa  mov     [rsp+70h+var_28], rax
0x18001e4ff  lea     r8, aWinsta0Default; "Winsta0\\Default"
0x18001e506  and     [rsp+70h+var_30], 0
0x18001e50c  xor     r9d, r9d
0x18001e50f  or      [rsp+70h+var_38], 0FFFFFFFFh
0x18001e514  mov     rcx, r14
0x18001e517  mov     eax, [rbp+TokenInformation]
0x18001e51a  mov     [rsp+70h+var_40], 9
0x18001e522  mov     [rsp+70h+var_48], 10000000h
0x18001e52a  mov     dword ptr [rsp+70h+ReturnLength], eax
0x18001e52e  call    ?AiLaunchConsentUI@@YAKPEAXPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAUHWND__@@KKW4ELEVATION_REASON@@KPEBDPEAPEAX@Z; AiLaunchConsentUI(void *,_CONSENTUI_PARAM_HEADER *,ushort const *,HWND__ *,ulong,ulong,ELEVATION_REASON,ulong,char const *,void * *)
0x18001e533  mov     ebx, eax
0x18001e535  test    eax, eax
0x18001e537  jnz     short loc_18001E58B
0x18001e539  test    rsi, rsi
0x18001e53c  jz      short loc_18001E57F
0x18001e53e  lea     rdx, [rbp+var_1C]; int *
0x18001e542  mov     rcx, rsi; TokenHandle
0x18001e545  call    ?AiCheckForTcbPrivilege@@YAJPEAXPEAH@Z; AiCheckForTcbPrivilege(void *,int *)
0x18001e54a  test    eax, eax
0x18001e54c  js      loc_18001E48A
0x18001e552  mov     eax, [rbp+var_1C]
0x18001e555  test    rdi, rdi
0x18001e558  jz      short loc_18001E55C
0x18001e55a  mov     [rdi], eax
0x18001e55c  test    eax, eax
0x18001e55e  jnz     short loc_18001E57F
0x18001e560  mov     rcx, [rbp+ExistingTokenHandle]; ExistingTokenHandle
0x18001e564  lea     edx, [rax+1]; ImpersonationLevel
0x18001e567  mov     r8, r15; DuplicateTokenHandle
0x18001e56a  call    cs:__imp_DuplicateToken
0x18001e571  nop     dword ptr [rax+rax+00h]
0x18001e576  test    eax, eax
0x18001e578  jnz     short loc_18001E58B
0x18001e57a  jmp     loc_18001E4D9
0x18001e57f  mov     rax, [rbp+ExistingTokenHandle]
0x18001e583  and     [rbp+ExistingTokenHandle], 0
0x18001e588  mov     [r15], rax
0x18001e58b  lea     rcx, [rbp+ExistingTokenHandle]
0x18001e58f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001e594  lea     r11, [rsp+70h+var_s0]
0x18001e599  mov     eax, ebx
0x18001e59b  mov     rbx, [r11+20h]
0x18001e59f  mov     rsi, [r11+28h]
0x18001e5a3  mov     rdi, [r11+30h]
0x18001e5a7  mov     rsp, r11
0x18001e5aa  pop     r15
0x18001e5ac  pop     r14
0x18001e5ae  pop     rbp
0x18001e5af  retn
```
