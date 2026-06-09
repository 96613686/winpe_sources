# RAiGetElevatedToken

- ea: `0x180026ba0`
- end: `0x180026f3a`
- name: `RAiGetElevatedToken`
- size: `922`
- prototype: `__int64 __fastcall(struct _RPC_ASYNC_STATE *, __int64, void *)`
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180009d50`
- `0x18000bde0`
- `0x18000c410`
- `0x18001b558`
- `0x18001d034`
- `0x1800212cc`
- `0x18002172c`
- `0x180021968`
- `0x1800259b0`
- `0x180025a5c`
- `0x180026630`
- `0x180026ba0`
- `0x180026f40`
- `0x180028a3c`
- `0x1800290b4`
- `0x180045e88`
- `0x1800461e8`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180026eb7`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180026eb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026dcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026dcb`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180026d2f`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180026d2f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180026ca2`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180026ca2`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180026e69`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180026e69`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026dc1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180026dc1`

## string_xrefs

- `0x180026c1d`: `GetElevatedTokenActivity`

## pseudocode

```c
__int64 __fastcall RAiGetElevatedToken(struct _RPC_ASYNC_STATE *a1, __int64 a2, void *a3)
{
  NTSTATUS v4; // eax
  ULONG Reply; // [rsp+50h] [rbp-B0h] BYREF
  int v7; // [rsp+54h] [rbp-ACh]
  HANDLE ExistingTokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v9; // [rsp+60h] [rbp-A0h]
  int v10; // [rsp+64h] [rbp-9Ch]
  int v11; // [rsp+68h] [rbp-98h]
  int TokenInformation; // [rsp+6Ch] [rbp-94h]
  HANDLE TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hProcess; // [rsp+78h] [rbp-88h] BYREF
  DWORD v15; // [rsp+80h] [rbp-80h]
  struct _CONSENTUI_PARAM_HEADER *v16; // [rsp+88h] [rbp-78h]
  PRPC_ASYNC_STATE pAsync; // [rsp+90h] [rbp-70h]
  _QWORD v18[42]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Filename[264]; // [rsp+1F0h] [rbp+F0h] BYREF

  pAsync = a1;
  Reply = 0;
  v9 = 0;
  TokenInformation = 0;
  v15 = 0;
  v16 = 0;
  v10 = 0;
  v11 = 0;
  v7 = 0;
  memset_0(Filename, 0, 0x208u);
  hProcess = 0;
  TokenHandle = 0;
  ExistingTokenHandle = 0;
  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v18);
  v18[0] = &LUATelemetry::GetElevatedTokenActivity::`vftable';
  LUATelemetry::GetElevatedTokenActivity::StartActivity((LUATelemetry::GetElevatedTokenActivity *)v18);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_67bea7eefcf5311daaba7659c5767e76_Traceguids, (unsigned int)a3);
  v4 = LUAIsElevatedToken(a3);
  if ( v4 >= 0 )
    Reply = 87;
  else
    Reply = RtlNtStatusToDosErrorNoTeb(v4);
  LUATelemetry::GetElevatedTokenActivity::Stop(
    (LUATelemetry::GetElevatedTokenActivity *)v18,
    Reply,
    Filename,
    0,
    0,
    v10,
    v11,
    v7);
  RpcAsyncCompleteCall(pAsync, &Reply);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_67bea7eefcf5311daaba7659c5767e76_Traceguids, Reply);
  LUATelemetry::GetElevatedTokenActivity::~GetElevatedTokenActivity((LUATelemetry::GetElevatedTokenActivity *)v18);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ExistingTokenHandle);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
}

```

## disassembly

```asm
0x180026ba0  push    rbp
0x180026ba2  push    rbx
0x180026ba3  push    rsi
0x180026ba4  push    rdi
0x180026ba5  push    r12
0x180026ba7  push    r13
0x180026ba9  push    r14
0x180026bab  push    r15
0x180026bad  lea     rbp, [rsp-318h]
0x180026bb5  sub     rsp, 418h
0x180026bbc  mov     rax, cs:__security_cookie
0x180026bc3  xor     rax, rsp
0x180026bc6  mov     [rbp+350h+var_50], rax
0x180026bcd  xor     r15d, r15d
0x180026bd0  mov     [rbp+350h+pAsync], rcx
0x180026bd4  mov     rbx, r8
0x180026bd7  mov     [rsp+450h+Reply], r15d
0x180026bdc  mov     r13, rdx
0x180026bdf  mov     [rsp+450h+var_3F0], r15d
0x180026be4  xor     edx, edx; Val
0x180026be6  mov     [rsp+450h+TokenInformation], r15d
0x180026beb  mov     r8d, 208h; Size
0x180026bf1  mov     [rbp+350h+var_3D0], r15d
0x180026bf5  lea     rcx, [rbp+350h+Filename]; void *
0x180026bfc  mov     [rbp+350h+var_3C8], r15
0x180026c00  mov     edi, r15d
0x180026c03  mov     [rsp+450h+var_3EC], r15d
0x180026c08  mov     r14d, r15d
0x180026c0b  mov     [rsp+450h+var_3E8], r15d
0x180026c10  mov     [rsp+450h+var_3FC], r15d
0x180026c15  mov     rsi, r9
0x180026c18  call    memset_0
0x180026c1d  lea     rdx, aGetelevatedtok; "GetElevatedTokenActivity"
0x180026c24  mov     [rsp+450h+hProcess], r15
0x180026c29  lea     rcx, [rbp+350h+var_3B0]; struct wil::details::IFailureCallback *
0x180026c2d  mov     [rsp+450h+TokenHandle], r15
0x180026c32  mov     [rsp+450h+ExistingTokenHandle], r15
0x180026c37  call    ??0?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180026c3c  lea     rax, ??_7GetElevatedTokenActivity@LUATelemetry@@6B@; const LUATelemetry::GetElevatedTokenActivity::`vftable'
0x180026c43  lea     rcx, [rbp+350h+var_3B0]; this
0x180026c47  mov     [rbp+350h+var_3B0], rax
0x180026c4b  call    ?StartActivity@GetElevatedTokenActivity@LUATelemetry@@QEAAXXZ; LUATelemetry::GetElevatedTokenActivity::StartActivity(void)
0x180026c50  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c57  lea     rax, WPP_GLOBAL_Control
0x180026c5e  cmp     rcx, rax
0x180026c61  jz      short loc_180026C80
0x180026c63  test    byte ptr [rcx+1Ch], 1
0x180026c67  jz      short loc_180026C80
0x180026c69  mov     rcx, [rcx+10h]
0x180026c6d  lea     edx, [r15+0Ah]
0x180026c71  mov     r9d, ebx
0x180026c74  lea     r8, WPP_67bea7eefcf5311daaba7659c5767e76_Traceguids
0x180026c7b  call    WPP_SF_D
0x180026c80  lea     r8, [rsp+450h+var_3E8]
0x180026c85  mov     rcx, rbx; TokenHandle
0x180026c88  lea     rdx, [rsp+450h+var_3EC]
0x180026c8d  call    LUAIsElevatedToken
0x180026c92  mov     r15d, [rsp+450h+var_3EC]
0x180026c97  mov     r12d, [rsp+450h+var_3E8]
0x180026c9c  test    eax, eax
0x180026c9e  jns     short loc_180026CB1
0x180026ca0  mov     ecx, eax; Status
0x180026ca2  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180026ca8  mov     [rsp+450h+Reply], eax
0x180026cac  jmp     loc_180026E80
0x180026cb1  test    r12d, r12d
0x180026cb4  jz      loc_180026E78
0x180026cba  test    r15d, r15d
0x180026cbd  jnz     loc_180026E78
0x180026cc3  xor     edx, edx
0x180026cc5  lea     rcx, [rsp+450h+TokenHandle]
0x180026cca  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180026ccf  xor     edx, edx
0x180026cd1  lea     rcx, [rsp+450h+hProcess]
0x180026cd6  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180026cdb  lea     r9, [rsp+450h+var_3F0]; unsigned int *
0x180026ce0  mov     [rsp+450h+ReturnLength], rdi; unsigned int *
0x180026ce5  lea     r8, [rsp+450h+TokenHandle]; void **
0x180026cea  mov     rcx, r13; void *
0x180026ced  lea     rdx, [rsp+450h+hProcess]; void **
0x180026cf2  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x180026cf7  mov     edi, [rsp+450h+var_3F0]
0x180026cfb  xor     r13d, r13d
0x180026cfe  mov     [rsp+450h+Reply], eax
0x180026d02  test    eax, eax
0x180026d04  jnz     loc_180026E80
0x180026d0a  test    edi, edi
0x180026d0c  jz      short loc_180026D1B
0x180026d0e  mov     [rsp+450h+Reply], 5
0x180026d16  jmp     loc_180026E80
0x180026d1b  mov     rcx, [rsp+450h+hProcess]; hProcess
0x180026d20  lea     r8, [rbp+350h+Filename]; lpFilename
0x180026d27  mov     r9d, 104h; nSize
0x180026d2d  xor     edx, edx; hModule
0x180026d2f  call    cs:__imp_K32GetModuleFileNameExW
0x180026d35  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x180026d3c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x180026d41  test    al, al
0x180026d43  jz      short loc_180026D5F
0x180026d45  mov     rcx, [rsp+450h+TokenHandle]; TokenHandle
0x180026d4a  lea     r9, [rsp+450h+var_3FC]; int *
0x180026d4f  mov     r8, rsi; phNewToken
0x180026d52  mov     rdx, rbx; HANDLE
0x180026d55  call    ?AiGetElevationToken@@YAKPEAX0PEAPEAXPEAH@Z; AiGetElevationToken(void *,void *,void * *,int *)
0x180026d5a  jmp     loc_180026CA8
0x180026d5f  call    LUAIsShadowAdminEnabled
0x180026d64  mov     r14d, eax
0x180026d67  test    eax, eax
0x180026d69  jnz     short loc_180026D91
0x180026d6b  xor     edx, edx
0x180026d6d  lea     rcx, [rsp+450h+ExistingTokenHandle]
0x180026d72  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180026d77  lea     rdx, [rsp+450h+ExistingTokenHandle]; NewTokenHandle
0x180026d7c  mov     rcx, rbx; TokenHandle
0x180026d7f  call    LUAGetElevatedToken
0x180026d84  test    eax, eax
0x180026d86  jns     loc_180026E2F
0x180026d8c  jmp     loc_180026CA0
0x180026d91  lea     rcx, [rbp+350h+var_3C8]; struct _CONSENTUI_PARAM_HEADER **
0x180026d95  call    ?AiBuildElevateTokenAPIParams@@YAKPEAPEAU_CONSENTUI_PARAM_HEADER@@@Z; AiBuildElevateTokenAPIParams(_CONSENTUI_PARAM_HEADER * *)
0x180026d9a  mov     [rsp+450h+Reply], eax
0x180026d9e  test    eax, eax
0x180026da0  jnz     loc_180026E80
0x180026da6  mov     r9d, 4; TokenInformationLength
0x180026dac  lea     rax, [rbp+350h+var_3D0]
0x180026db0  lea     r8, [rsp+450h+TokenInformation]; TokenInformation
0x180026db5  mov     [rsp+450h+ReturnLength], rax; ReturnLength
0x180026dba  mov     rcx, rbx; TokenHandle
0x180026dbd  lea     edx, [r9+8]; TokenInformationClass
0x180026dc1  call    cs:__imp_GetTokenInformation
0x180026dc7  test    eax, eax
0x180026dc9  jnz     short loc_180026DD6
0x180026dcb  call    cs:__imp_GetLastError
0x180026dd1  jmp     loc_180026CA8
0x180026dd6  xor     edx, edx
0x180026dd8  lea     rcx, [rsp+450h+ExistingTokenHandle]
0x180026ddd  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180026de2  mov     rdx, [rbp+350h+var_3C8]
0x180026de6  lea     rax, [rsp+450h+ExistingTokenHandle]
0x180026deb  mov     [rsp+450h+var_408], rax
0x180026df0  lea     r8, aWinsta0Default; "Winsta0\\Default"
0x180026df7  mov     eax, [rsp+450h+TokenInformation]
0x180026dfb  xor     r9d, r9d
0x180026dfe  mov     [rsp+450h+var_410], r13
0x180026e03  mov     rcx, rbx
0x180026e06  mov     [rsp+450h+var_418], 0FFFFFFFFh
0x180026e0e  mov     [rsp+450h+var_420], 9
0x180026e16  mov     [rsp+450h+var_428], 10000000h
0x180026e1e  mov     dword ptr [rsp+450h+ReturnLength], eax
0x180026e22  call    ?AiLaunchConsentUI@@YAKPEAXPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAUHWND__@@KKW4ELEVATION_REASON@@KPEBDPEAPEAX@Z; AiLaunchConsentUI(void *,_CONSENTUI_PARAM_HEADER *,ushort const *,HWND__ *,ulong,ulong,ELEVATION_REASON,ulong,char const *,void * *)
0x180026e27  mov     [rsp+450h+Reply], eax
0x180026e2b  test    eax, eax
0x180026e2d  jnz     short loc_180026E80
0x180026e2f  mov     rcx, [rsp+450h+TokenHandle]; TokenHandle
0x180026e34  lea     rdx, [rsp+450h+var_3FC]; int *
0x180026e39  call    ?AiCheckForTcbPrivilege@@YAJPEAXPEAH@Z; AiCheckForTcbPrivilege(void *,int *)
0x180026e3e  test    eax, eax
0x180026e40  js      loc_180026CA0
0x180026e46  cmp     [rsp+450h+var_3FC], r13d
0x180026e4b  jz      short loc_180026E5C
0x180026e4d  mov     rax, [rsp+450h+ExistingTokenHandle]
0x180026e52  mov     [rsi], rax
0x180026e55  mov     [rsp+450h+ExistingTokenHandle], r13
0x180026e5a  jmp     short loc_180026E80
0x180026e5c  mov     rcx, [rsp+450h+ExistingTokenHandle]; ExistingTokenHandle
0x180026e61  mov     r8, rsi; DuplicateTokenHandle
0x180026e64  mov     edx, 1; ImpersonationLevel
0x180026e69  call    cs:__imp_DuplicateToken
0x180026e6f  test    eax, eax
0x180026e71  jnz     short loc_180026E80
0x180026e73  jmp     loc_180026DCB
0x180026e78  mov     [rsp+450h+Reply], 57h ; 'W'
0x180026e80  mov     eax, [rsp+450h+var_3FC]
0x180026e84  lea     r8, [rbp+350h+Filename]; unsigned __int16 *
0x180026e8b  mov     edx, [rsp+450h+Reply]; unsigned int
0x180026e8f  lea     rcx, [rbp+350h+var_3B0]; this
0x180026e93  mov     [rsp+450h+var_418], eax; int
0x180026e97  mov     r9d, edi; unsigned int
0x180026e9a  mov     [rsp+450h+var_420], r12d; int
0x180026e9f  mov     [rsp+450h+var_428], r15d; int
0x180026ea4  mov     dword ptr [rsp+450h+ReturnLength], r14d; int
0x180026ea9  call    ?Stop@GetElevatedTokenActivity@LUATelemetry@@QEAAXKPEBGKHHHH@Z; LUATelemetry::GetElevatedTokenActivity::Stop(ulong,ushort const *,ulong,int,int,int,int)
0x180026eae  mov     rcx, [rbp+350h+pAsync]; pAsync
0x180026eb2  lea     rdx, [rsp+450h+Reply]; Reply
0x180026eb7  call    cs:__imp_RpcAsyncCompleteCall
0x180026ebd  mov     rcx, cs:WPP_GLOBAL_Control
0x180026ec4  lea     rax, WPP_GLOBAL_Control
0x180026ecb  cmp     rcx, rax
0x180026ece  jz      short loc_180026EF0
0x180026ed0  test    byte ptr [rcx+1Ch], 1
0x180026ed4  jz      short loc_180026EF0
0x180026ed6  mov     r9d, [rsp+450h+Reply]
0x180026edb  lea     r8, WPP_67bea7eefcf5311daaba7659c5767e76_Traceguids
0x180026ee2  mov     rcx, [rcx+10h]
0x180026ee6  mov     edx, 0Bh
0x180026eeb  call    WPP_SF_D
0x180026ef0  lea     rcx, [rbp+350h+var_3B0]; this
0x180026ef4  call    ??1GetElevatedTokenActivity@LUATelemetry@@QEAA@XZ; LUATelemetry::GetElevatedTokenActivity::~GetElevatedTokenActivity(void)
0x180026ef9  lea     rcx, [rsp+450h+ExistingTokenHandle]
0x180026efe  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180026f03  lea     rcx, [rsp+450h+TokenHandle]
0x180026f08  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180026f0d  lea     rcx, [rsp+450h+hProcess]
0x180026f12  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180026f17  mov     rcx, [rbp+350h+var_50]
0x180026f1e  xor     rcx, rsp; StackCookie
0x180026f21  call    __security_check_cookie
0x180026f26  add     rsp, 418h
0x180026f2d  pop     r15
0x180026f2f  pop     r14
0x180026f31  pop     r13
0x180026f33  pop     r12
0x180026f35  pop     rdi
0x180026f36  pop     rsi
0x180026f37  pop     rbx
0x180026f38  pop     rbp
0x180026f39  retn
```
