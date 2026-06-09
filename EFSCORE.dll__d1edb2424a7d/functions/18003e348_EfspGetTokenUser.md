# EfspGetTokenUser

- ea: `0x18003e348`
- end: `0x18003e59b`
- name: `EfspGetTokenUser`
- size: `595`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18003818c`

## callees

- `0x180004f86`
- `0x1800102f0`
- `0x180010bf0`
- `0x18003bf9c`
- `0x18003df7c`
- `0x18003e348`
- `0x180063698`
- `0x1800d43e8`
- `0x1800d4510`
- `0x1800d45bc`
- `0x1800dca3c`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e567`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e567`
- `ntdll!RtlValidSid` at `0x18003e496`
- `ntdll!RtlValidSid` at `0x18003e496`
- `ntdll!NtQueryInformationToken` at `0x18003e420`
- `ntdll!NtQueryInformationToken` at `0x18003e4c1`
- `ntdll!NtQueryInformationToken` at `0x18003e4e9`
- `ntdll!NtQueryInformationToken` at `0x18003e420`
- `ntdll!NtQueryInformationToken` at `0x18003e4c1`
- `ntdll!NtQueryInformationToken` at `0x18003e4e9`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18003e50a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18003e50a`

## pseudocode

```c
__int64 __fastcall EfspGetTokenUser(__int64 a1)
{
  NTSTATUS InformationToken; // eax
  NTSTATUS v3; // esi
  _QWORD *v4; // rbx
  _QWORD *v5; // rax
  __int64 v6; // rcx
  int v7; // eax
  int UserContext; // eax
  ULONG TokenInformationLength[2]; // [rsp+30h] [rbp-D0h] BYREF
  void *NewTokenHandle; // [rsp+38h] [rbp-C8h]
  _DWORD v12[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE TokenInformation[1024]; // [rsp+50h] [rbp-B0h] BYREF

  TokenInformationLength[0] = 0;
  v12[0] = 0;
  *(_QWORD *)(a1 + 40) = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support>::GetImpl'::`2'::impl)
    && (unsigned int)LUAIsShadowAdminEnabled() )
  {
    LODWORD(NewTokenHandle) = 0;
    TokenInformationLength[1] = 0;
    LUAIsElevatedToken((HANDLE)0xFFFFFFFFFFFFFFFBLL);
  }
  InformationToken = NtQueryInformationToken(
                       (HANDLE)0xFFFFFFFFFFFFFFFBLL,
                       TokenUser,
                       TokenInformation,
                       0x400u,
                       TokenInformationLength);
  v3 = InformationToken;
  if ( InformationToken >= 0 || (v4 = 0, InformationToken == -1073741789) )
  {
    v5 = wil::details::heap_allocator::allocate(TokenInformationLength[0]);
    v4 = v5;
    if ( !v5 )
    {
      v3 = -1073741670;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -1073741670, 12, 44);
      goto LABEL_16;
    }
    if ( v3 < 0 )
    {
      v3 = NtQueryInformationToken(
             (HANDLE)0xFFFFFFFFFFFFFFFBLL,
             TokenUser,
             v5,
             TokenInformationLength[0],
             TokenInformationLength);
      if ( v3 < 0 )
        goto LABEL_16;
    }
    else
    {
      memcpy_0(v5, TokenInformation, TokenInformationLength[0]);
      *v4 = v4 + 2;
      if ( !RtlValidSid(v4 + 2) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v6);
    }
    v3 = NtQueryInformationToken((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenSessionId, v12, 4u, TokenInformationLength);
    if ( v3 >= 0 )
    {
      v7 = v12[0];
      *(_QWORD *)(a1 + 104) = 0;
      *(_DWORD *)(a1 + 72) = v7;
      UserContext = UMgrQueryUserContext(0);
      if ( UserContext < 0 )
        fnEfsLogTrace1(g_hPublisher, (unsigned int)&EFS_API_ERROR, UserContext, 12, 91);
      EfspGetLogonType((HANDLE)0xFFFFFFFFFFFFFFFBLL);
      *(_QWORD *)(a1 + 40) = v4;
      v4 = 0;
    }
  }
LABEL_16:
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support>::GetImpl'::`2'::impl);
  if ( v4 )
    EfsFreeHeap(v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003e348  push    rbp
0x18003e34a  push    rbx
0x18003e34b  push    rsi
0x18003e34c  push    rdi
0x18003e34d  push    r14
0x18003e34f  push    r15
0x18003e351  lea     rbp, [rsp-368h]
0x18003e359  sub     rsp, 468h
0x18003e360  mov     rax, cs:__security_cookie
0x18003e367  xor     rax, rsp
0x18003e36a  mov     [rbp+390h+var_40], rax
0x18003e371  mov     r14, rcx
0x18003e374  mov     [rsp+490h+TokenInformationLength], 0
0x18003e37c  mov     rdi, 0FFFFFFFFFFFFFFFBh
0x18003e383  mov     [rsp+490h+var_450], 0
0x18003e38b  xor     r15b, r15b
0x18003e38e  mov     qword ptr [rcx+28h], 0
0x18003e396  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support>::GetImpl(void)'::`2'::impl
0x18003e39d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support>::__private_IsEnabled(void)
0x18003e3a2  test    al, al
0x18003e3a4  jz      short loc_18003E403
0x18003e3a6  call    LUAIsShadowAdminEnabled
0x18003e3ab  test    eax, eax
0x18003e3ad  jz      short loc_18003E403
0x18003e3af  lea     r8, [rsp+490h+NewTokenHandle]
0x18003e3b4  mov     dword ptr [rsp+490h+NewTokenHandle], 0
0x18003e3bc  lea     rdx, [rsp+490h+var_45C]
0x18003e3c1  mov     [rsp+490h+var_45C], 0
0x18003e3c9  mov     rcx, rdi; TokenHandle
0x18003e3cc  call    LUAIsElevatedToken
0x18003e3d1  test    eax, eax
0x18003e3d3  jnz     short loc_18003E403
0x18003e3d5  cmp     [rsp+490h+var_45C], eax
0x18003e3d9  jz      short loc_18003E403
0x18003e3db  cmp     dword ptr [rsp+490h+NewTokenHandle], eax
0x18003e3df  jz      short loc_18003E403
0x18003e3e1  lea     rdx, [rsp+490h+NewTokenHandle]; NewTokenHandle
0x18003e3e6  mov     [rsp+490h+NewTokenHandle], 0
0x18003e3ef  mov     rcx, rdi; TokenHandle
0x18003e3f2  call    LUAGetStandardToken
0x18003e3f7  test    eax, eax
0x18003e3f9  jnz     short loc_18003E403
0x18003e3fb  mov     rdi, [rsp+490h+NewTokenHandle]
0x18003e400  mov     r15b, 1
0x18003e403  lea     rax, [rsp+490h+TokenInformationLength]
0x18003e408  mov     r9d, 400h; TokenInformationLength
0x18003e40e  lea     r8, [rsp+490h+TokenInformation]; TokenInformation
0x18003e413  mov     [rsp+490h+ReturnLength], rax; ReturnLength
0x18003e418  mov     edx, 1; TokenInformationClass
0x18003e41d  mov     rcx, rdi; TokenHandle
0x18003e420  call    cs:__imp_NtQueryInformationToken
0x18003e426  mov     esi, eax
0x18003e428  test    eax, eax
0x18003e42a  jns     short loc_18003E439
0x18003e42c  xor     ebx, ebx
0x18003e42e  cmp     eax, 0C0000023h
0x18003e433  jnz     loc_18003E54A
0x18003e439  mov     ecx, [rsp+490h+TokenInformationLength]; unsigned __int64
0x18003e43d  call    ?allocate@heap_allocator@details@wil@@SAPEAX_K@Z; wil::details::heap_allocator::allocate(unsigned __int64)
0x18003e442  mov     rbx, rax
0x18003e445  test    rax, rax
0x18003e448  jnz     short loc_18003E479
0x18003e44a  mov     rcx, cs:g_hPublisher
0x18003e451  lea     r9d, [rax+0Ch]
0x18003e455  mov     r8d, 0C000009Ah
0x18003e45b  mov     dword ptr [rsp+490h+ReturnLength], 12Ch
0x18003e463  lea     rdx, EFS_TRACE_ERROR
0x18003e46a  mov     esi, 0C000009Ah
0x18003e46f  call    fnEfsLogTrace1
0x18003e474  jmp     loc_18003E54A
0x18003e479  test    esi, esi
0x18003e47b  js      short loc_18003E4A7
0x18003e47d  mov     r8d, [rsp+490h+TokenInformationLength]; Size
0x18003e482  lea     rdx, [rsp+490h+TokenInformation]; Src
0x18003e487  mov     rcx, rbx; void *
0x18003e48a  call    memcpy_0
0x18003e48f  lea     rcx, [rbx+10h]; Sid
0x18003e493  mov     [rbx], rcx
0x18003e496  call    cs:__imp_RtlValidSid
0x18003e49c  test    al, al
0x18003e49e  jnz     short loc_18003E4CD
0x18003e4a0  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "RtlValidSid(pTokenUser->User.Sid)")
0x18003e4a5  jmp     short loc_18003E4CD
0x18003e4a7  mov     r9d, [rsp+490h+TokenInformationLength]; TokenInformationLength
0x18003e4ac  lea     rax, [rsp+490h+TokenInformationLength]
0x18003e4b1  mov     r8, rbx; TokenInformation
0x18003e4b4  mov     [rsp+490h+ReturnLength], rax; ReturnLength
0x18003e4b9  mov     edx, 1; TokenInformationClass
0x18003e4be  mov     rcx, rdi; TokenHandle
0x18003e4c1  call    cs:__imp_NtQueryInformationToken
0x18003e4c7  mov     esi, eax
0x18003e4c9  test    eax, eax
0x18003e4cb  js      short loc_18003E54A
0x18003e4cd  mov     r9d, 4; TokenInformationLength
0x18003e4d3  lea     rax, [rsp+490h+TokenInformationLength]
0x18003e4d8  lea     r8, [rsp+490h+var_450]; TokenInformation
0x18003e4dd  mov     [rsp+490h+ReturnLength], rax; ReturnLength
0x18003e4e2  mov     rcx, rdi; TokenHandle
0x18003e4e5  lea     edx, [r9+8]; TokenInformationClass
0x18003e4e9  call    cs:__imp_NtQueryInformationToken
0x18003e4ef  mov     esi, eax
0x18003e4f1  test    eax, eax
0x18003e4f3  js      short loc_18003E54A
0x18003e4f5  mov     eax, [rsp+490h+var_450]
0x18003e4f9  lea     rdx, [r14+68h]
0x18003e4fd  xor     ecx, ecx
0x18003e4ff  mov     qword ptr [rdx], 0
0x18003e506  mov     [r14+48h], eax
0x18003e50a  call    cs:__imp_UMgrQueryUserContext
0x18003e510  test    eax, eax
0x18003e512  jns     short loc_18003E538
0x18003e514  mov     rcx, cs:g_hPublisher
0x18003e51b  lea     rdx, EFS_API_ERROR
0x18003e522  mov     r9d, 0Ch
0x18003e528  mov     dword ptr [rsp+490h+ReturnLength], 15Bh
0x18003e530  mov     r8d, eax
0x18003e533  call    fnEfsLogTrace1
0x18003e538  lea     rdx, [r14+58h]
0x18003e53c  mov     rcx, rdi; TokenHandle
0x18003e53f  call    EfspGetLogonType
0x18003e544  mov     [r14+28h], rbx
0x18003e548  xor     ebx, ebx
0x18003e54a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support>::GetImpl(void)'::`2'::impl
0x18003e551  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PDE_LUA_ShadowAdmin_Support>::__private_IsEnabled(void)
0x18003e556  test    al, al
0x18003e558  jz      short loc_18003E56D
0x18003e55a  test    r15b, r15b
0x18003e55d  jz      short loc_18003E56D
0x18003e55f  test    rdi, rdi
0x18003e562  jz      short loc_18003E56D
0x18003e564  mov     rcx, rdi; hObject
0x18003e567  call    cs:__imp_CloseHandle
0x18003e56d  test    rbx, rbx
0x18003e570  jz      short loc_18003E57A
0x18003e572  mov     rcx, rbx; lpMem
0x18003e575  call    EfsFreeHeap
0x18003e57a  mov     eax, esi
0x18003e57c  mov     rcx, [rbp+390h+var_40]
0x18003e583  xor     rcx, rsp; StackCookie
0x18003e586  call    __security_check_cookie
0x18003e58b  add     rsp, 468h
0x18003e592  pop     r15
0x18003e594  pop     r14
0x18003e596  pop     rdi
0x18003e597  pop     rsi
0x18003e598  pop     rbx
0x18003e599  pop     rbp
0x18003e59a  retn
```
