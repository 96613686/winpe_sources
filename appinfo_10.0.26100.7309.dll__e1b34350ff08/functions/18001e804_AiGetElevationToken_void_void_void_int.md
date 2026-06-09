# AiGetElevationToken(void *,void *,void * *,int *)

- ea: `0x18001e804`
- end: `0x18001e9f0`
- name: `?AiGetElevationToken@@YAKPEAX0PEAPEAXPEAH@Z`
- size: `492`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, HANDLE, PHANDLE DuplicateTokenHandle, int *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800230e0`
- `0x18003db90`

## callees

- `0x18000c790`
- `0x18000f9e0`
- `0x180012a14`
- `0x18001913c`
- `0x18001afdc`
- `0x18001e804`
- `0x180022b74`
- `0x1800243ec`
- `0x180024a98`
- `0x1800436d4`
- `0x180043a2c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e8a9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001e8a9`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001e9a9`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18001e9a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e8b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e8b9`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001e86c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18001e86c`
- `USERENV!UnloadUserProfile` at `0x18001e965`
- `USERENV!UnloadUserProfile` at `0x18001e965`

## pseudocode

```c
__int64 __fastcall AiGetElevationToken(HANDLE TokenHandle, HANDLE a2, PHANDLE DuplicateTokenHandle, int *a4)
{
  unsigned int v4; // ebx
  int v9; // eax
  NTSTATUS v10; // ecx
  DWORD LastError; // eax
  int v12; // edi
  int v13; // eax
  HANDLE v14; // rax
  int TokenInformation; // [rsp+50h] [rbp-20h] BYREF
  int v17; // [rsp+54h] [rbp-1Ch] BYREF
  DWORD ReturnLength; // [rsp+58h] [rbp-18h] BYREF
  HANDLE hToken; // [rsp+60h] [rbp-10h] BYREF
  HANDLE hProfile; // [rsp+68h] [rbp-8h] BYREF

  v4 = 0;
  v17 = 1;
  TokenInformation = 0;
  ReturnLength = 0;
  hProfile = 0;
  hToken = 0;
  if ( (unsigned int)LUAIsShadowAdminEnabled() )
  {
    v4 = AiBuildElevateTokenAPIParams((struct _CONSENTUI_PARAM_HEADER **)&hProfile);
    if ( v4 )
      goto LABEL_22;
    if ( !GetTokenInformation(a2, TokenSessionId, &TokenInformation, 4u, &ReturnLength) )
      goto LABEL_8;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      &hToken,
      0);
    v4 = AiLaunchConsentUI(a2, hProfile, L"Winsta0\\Default", 0, TokenInformation, 0x10000000, 9, -1, 0, &hToken);
    if ( v4 )
      goto LABEL_22;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_2045735225>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_2045735225>::GetImpl'::`2'::impl) )
    {
      hProfile = 0;
      v9 = AipLoadUserProfile(hToken, &hProfile);
      if ( v9 < 0 )
        goto LABEL_3;
      v12 = AipAddProfileReference(0xCu, hToken, hProfile);
      if ( v12 < 0 )
      {
        UnloadUserProfile(hToken, hProfile);
        v10 = v12;
        goto LABEL_4;
      }
    }
LABEL_14:
    if ( !TokenHandle )
      goto LABEL_21;
    v9 = AiCheckForTcbPrivilege(TokenHandle, &v17);
    if ( v9 < 0 )
      goto LABEL_3;
    v13 = v17;
    if ( a4 )
      *a4 = v17;
    if ( v13 )
    {
LABEL_21:
      v14 = hToken;
      hToken = 0;
      *DuplicateTokenHandle = v14;
      goto LABEL_22;
    }
    if ( DuplicateToken(hToken, SecurityIdentification, DuplicateTokenHandle) )
      goto LABEL_22;
LABEL_8:
    LastError = GetLastError();
    goto LABEL_5;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hToken,
    0);
  v9 = LUAGetElevatedToken(a2, &hToken);
  if ( v9 >= 0 )
    goto LABEL_14;
LABEL_3:
  v10 = v9;
LABEL_4:
  LastError = RtlNtStatusToDosErrorNoTeb(v10);
LABEL_5:
  v4 = LastError;
LABEL_22:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
  return v4;
}

```

## disassembly

```asm
0x18001e804  mov     [rsp-18h+arg_0], rbx
0x18001e809  mov     [rsp-18h+arg_8], rsi
0x18001e80e  mov     [rsp-18h+arg_10], rdi
0x18001e813  push    rbp
0x18001e814  push    r14
0x18001e816  push    r15
0x18001e818  mov     rbp, rsp
0x18001e81b  sub     rsp, 70h
0x18001e81f  xor     ebx, ebx
0x18001e821  mov     [rbp+var_1C], 1
0x18001e828  and     [rbp+TokenInformation], ebx
0x18001e82b  mov     rsi, r9
0x18001e82e  and     [rbp+var_18], ebx
0x18001e831  mov     r15, r8
0x18001e834  and     [rbp+hProfile], rbx
0x18001e838  mov     rdi, rdx
0x18001e83b  and     [rbp+hToken], rbx
0x18001e83f  mov     r14, rcx
0x18001e842  call    LUAIsShadowAdminEnabled
0x18001e847  test    eax, eax
0x18001e849  jnz     short loc_18001E87F
0x18001e84b  xor     edx, edx
0x18001e84d  lea     rcx, [rbp+hToken]
0x18001e851  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001e856  lea     rdx, [rbp+hToken]; NewTokenHandle
0x18001e85a  mov     rcx, rdi; TokenHandle
0x18001e85d  call    LUAGetElevatedToken
0x18001e862  test    eax, eax
0x18001e864  jns     loc_18001E978
0x18001e86a  mov     ecx, eax; Status
0x18001e86c  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18001e873  nop     dword ptr [rax+rax+00h]
0x18001e878  mov     ebx, eax
0x18001e87a  jmp     loc_18001E9CA
0x18001e87f  lea     rcx, [rbp+hProfile]; struct _CONSENTUI_PARAM_HEADER **
0x18001e883  call    ?AiBuildElevateTokenAPIParams@@YAKPEAPEAU_CONSENTUI_PARAM_HEADER@@@Z; AiBuildElevateTokenAPIParams(_CONSENTUI_PARAM_HEADER * *)
0x18001e888  mov     ebx, eax
0x18001e88a  test    eax, eax
0x18001e88c  jnz     loc_18001E9CA
0x18001e892  lea     rax, [rbp+var_18]
0x18001e896  mov     rcx, rdi; TokenHandle
0x18001e899  lea     r9d, [rbx+4]; TokenInformationLength
0x18001e89d  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x18001e8a2  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18001e8a6  lea     edx, [rbx+0Ch]; TokenInformationClass
0x18001e8a9  call    cs:__imp_GetTokenInformation
0x18001e8b0  nop     dword ptr [rax+rax+00h]
0x18001e8b5  test    eax, eax
0x18001e8b7  jnz     short loc_18001E8C7
0x18001e8b9  call    cs:__imp_GetLastError
0x18001e8c0  nop     dword ptr [rax+rax+00h]
0x18001e8c5  jmp     short loc_18001E878
0x18001e8c7  xor     edx, edx
0x18001e8c9  lea     rcx, [rbp+hToken]
0x18001e8cd  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18001e8d2  mov     rdx, [rbp+hProfile]
0x18001e8d6  lea     rax, [rbp+hToken]
0x18001e8da  mov     [rsp+70h+var_28], rax
0x18001e8df  lea     r8, aWinsta0Default; "Winsta0\\Default"
0x18001e8e6  and     [rsp+70h+var_30], 0
0x18001e8ec  xor     r9d, r9d
0x18001e8ef  or      [rsp+70h+var_38], 0FFFFFFFFh
0x18001e8f4  mov     rcx, rdi
0x18001e8f7  mov     eax, [rbp+TokenInformation]
0x18001e8fa  mov     [rsp+70h+var_40], 9
0x18001e902  mov     [rsp+70h+var_48], 10000000h
0x18001e90a  mov     dword ptr [rsp+70h+ReturnLength], eax
0x18001e90e  call    ?AiLaunchConsentUI@@YAKPEAXPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAUHWND__@@KKW4ELEVATION_REASON@@KPEBDPEAPEAX@Z; AiLaunchConsentUI(void *,_CONSENTUI_PARAM_HEADER *,ushort const *,HWND__ *,ulong,ulong,ELEVATION_REASON,ulong,char const *,void * *)
0x18001e913  mov     ebx, eax
0x18001e915  test    eax, eax
0x18001e917  jnz     loc_18001E9CA
0x18001e91d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_2045735225@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_2045735225@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_2045735225> `wil::Feature<__WilFeatureTraits_Feature_2045735225>::GetImpl(void)'::`2'::impl
0x18001e924  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_2045735225@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_2045735225>::__private_IsEnabled(void)
0x18001e929  test    al, al
0x18001e92b  jz      short loc_18001E978
0x18001e92d  mov     rcx, [rbp+hToken]; hToken
0x18001e931  lea     rdx, [rbp+hProfile]; void **
0x18001e935  and     [rbp+hProfile], 0
0x18001e93a  call    ?AipLoadUserProfile@@YAKPEAXPEAPEAX@Z; AipLoadUserProfile(void *,void * *)
0x18001e93f  test    eax, eax
0x18001e941  js      loc_18001E86A
0x18001e947  mov     r8, [rbp+hProfile]; void *
0x18001e94b  lea     ecx, [rbx+0Ch]; unsigned int
0x18001e94e  mov     rdx, [rbp+hToken]; void *
0x18001e952  call    ?AipAddProfileReference@@YAKKPEAX0@Z; AipAddProfileReference(ulong,void *,void *)
0x18001e957  mov     edi, eax
0x18001e959  test    eax, eax
0x18001e95b  jns     short loc_18001E978
0x18001e95d  mov     rdx, [rbp+hProfile]; hProfile
0x18001e961  mov     rcx, [rbp+hToken]; hToken
0x18001e965  call    cs:__imp_UnloadUserProfile
0x18001e96c  nop     dword ptr [rax+rax+00h]
0x18001e971  mov     ecx, edi
0x18001e973  jmp     loc_18001E86C
0x18001e978  test    r14, r14
0x18001e97b  jz      short loc_18001E9BE
0x18001e97d  lea     rdx, [rbp+var_1C]; int *
0x18001e981  mov     rcx, r14; TokenHandle
0x18001e984  call    ?AiCheckForTcbPrivilege@@YAJPEAXPEAH@Z; AiCheckForTcbPrivilege(void *,int *)
0x18001e989  test    eax, eax
0x18001e98b  js      loc_18001E86A
0x18001e991  mov     eax, [rbp+var_1C]
0x18001e994  test    rsi, rsi
0x18001e997  jz      short loc_18001E99B
0x18001e999  mov     [rsi], eax
0x18001e99b  test    eax, eax
0x18001e99d  jnz     short loc_18001E9BE
0x18001e99f  mov     rcx, [rbp+hToken]; ExistingTokenHandle
0x18001e9a3  lea     edx, [rax+1]; ImpersonationLevel
0x18001e9a6  mov     r8, r15; DuplicateTokenHandle
0x18001e9a9  call    cs:__imp_DuplicateToken
0x18001e9b0  nop     dword ptr [rax+rax+00h]
0x18001e9b5  test    eax, eax
0x18001e9b7  jnz     short loc_18001E9CA
0x18001e9b9  jmp     loc_18001E8B9
0x18001e9be  mov     rax, [rbp+hToken]
0x18001e9c2  and     [rbp+hToken], 0
0x18001e9c7  mov     [r15], rax
0x18001e9ca  lea     rcx, [rbp+hToken]
0x18001e9ce  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001e9d3  lea     r11, [rsp+70h+var_s0]
0x18001e9d8  mov     eax, ebx
0x18001e9da  mov     rbx, [r11+20h]
0x18001e9de  mov     rsi, [r11+28h]
0x18001e9e2  mov     rdi, [r11+30h]
0x18001e9e6  mov     rsp, r11
0x18001e9e9  pop     r15
0x18001e9eb  pop     r14
0x18001e9ed  pop     rbp
0x18001e9ee  retn
```
