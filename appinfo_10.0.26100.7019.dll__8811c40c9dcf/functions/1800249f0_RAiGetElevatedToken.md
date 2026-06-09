# RAiGetElevatedToken

- ea: `0x1800249f0`
- end: `0x180024da7`
- name: `RAiGetElevatedToken`
- size: `951`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a230`
- `0x18000c790`
- `0x18000f8b0`
- `0x1800191cc`
- `0x18001ac0c`
- `0x18001dbf8`
- `0x18001e064`
- `0x18001e424`
- `0x180023678`
- `0x180023728`
- `0x18002444c`
- `0x1800249f0`
- `0x180024db0`
- `0x180025cfc`
- `0x1800263a8`
- `0x180041b0c`
- `0x180041e64`
- `0x18004292a`
- `0x180042950`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180024d1d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180024d1d`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180024cc9`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180024cc9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024c18`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180024c18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024c28`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180024b80`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180024b80`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180024aed`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180024aed`

## string_xrefs

- `0x180024a68`: `GetElevatedTokenActivity`

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
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      &WPP_f5aaa73de7b43f98c43505c36bde04ec_Traceguids,
      (unsigned int)a3);
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
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_f5aaa73de7b43f98c43505c36bde04ec_Traceguids, Reply);
  LUATelemetry::GetElevatedTokenActivity::~GetElevatedTokenActivity((LUATelemetry::GetElevatedTokenActivity *)v18);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ExistingTokenHandle);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
}

```

## disassembly

```asm
0x1800249f0  push    rbp
0x1800249f2  push    rbx
0x1800249f3  push    rsi
0x1800249f4  push    rdi
0x1800249f5  push    r12
0x1800249f7  push    r13
0x1800249f9  push    r14
0x1800249fb  push    r15
0x1800249fd  lea     rbp, [rsp-318h]
0x180024a05  sub     rsp, 418h
0x180024a0c  mov     rax, cs:__security_cookie
0x180024a13  xor     rax, rsp
0x180024a16  mov     [rbp+350h+var_50], rax
0x180024a1d  xor     r15d, r15d
0x180024a20  mov     [rbp+350h+pAsync], rcx
0x180024a24  mov     rbx, r8
0x180024a27  mov     [rsp+450h+var_3F0], r15d
0x180024a2c  mov     r13, rdx
0x180024a2f  mov     [rsp+450h+TokenInformation], r15d
0x180024a34  xor     edx, edx; Val
0x180024a36  mov     [rbp+350h+var_3D0], r15d
0x180024a3a  mov     r8d, 208h; Size
0x180024a40  mov     [rbp+350h+var_3C8], r15
0x180024a44  lea     rcx, [rbp+350h+Filename]; void *
0x180024a4b  mov     [rsp+450h+var_3EC], r15d
0x180024a50  mov     edi, r15d
0x180024a53  mov     [rsp+450h+var_3E8], r15d
0x180024a58  mov     r14d, r15d
0x180024a5b  mov     [rsp+450h+var_3FC], r15d
0x180024a60  mov     rsi, r9
0x180024a63  call    memset_0
0x180024a68  lea     rdx, aGetelevatedtok; "GetElevatedTokenActivity"
0x180024a6f  mov     [rsp+450h+hProcess], r15
0x180024a74  lea     rcx, [rbp+350h+var_3B0]; struct wil::details::IFailureCallback *
0x180024a78  mov     [rsp+450h+TokenHandle], r15
0x180024a7d  mov     [rsp+450h+ExistingTokenHandle], r15
0x180024a82  call    ??0?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180024a87  lea     rax, ??_7GetElevatedTokenActivity@LUATelemetry@@6B@; const LUATelemetry::GetElevatedTokenActivity::`vftable'
0x180024a8e  lea     rcx, [rbp+350h+var_3B0]; this
0x180024a92  mov     [rbp+350h+var_3B0], rax
0x180024a96  call    ?StartActivity@GetElevatedTokenActivity@LUATelemetry@@QEAAXXZ; LUATelemetry::GetElevatedTokenActivity::StartActivity(void)
0x180024a9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024aa2  lea     rax, WPP_GLOBAL_Control
0x180024aa9  cmp     rcx, rax
0x180024aac  jz      short loc_180024ACB
0x180024aae  test    byte ptr [rcx+1Ch], 1
0x180024ab2  jz      short loc_180024ACB
0x180024ab4  mov     rcx, [rcx+10h]
0x180024ab8  lea     edx, [r15+0Ah]
0x180024abc  mov     r9d, ebx
0x180024abf  lea     r8, WPP_f5aaa73de7b43f98c43505c36bde04ec_Traceguids
0x180024ac6  call    WPP_SF_D
0x180024acb  lea     r8, [rsp+450h+var_3E8]
0x180024ad0  mov     rcx, rbx; TokenHandle
0x180024ad3  lea     rdx, [rsp+450h+var_3EC]
0x180024ad8  call    LUAIsElevatedToken
0x180024add  mov     r15d, [rsp+450h+var_3EC]
0x180024ae2  mov     r12d, [rsp+450h+var_3E8]
0x180024ae7  test    eax, eax
0x180024ae9  jns     short loc_180024B02
0x180024aeb  mov     ecx, eax; Status
0x180024aed  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180024af4  nop     dword ptr [rax+rax+00h]
0x180024af9  mov     [rsp+450h+Reply], eax
0x180024afd  jmp     loc_180024CE6
0x180024b02  test    r12d, r12d
0x180024b05  jz      loc_180024CDE
0x180024b0b  test    r15d, r15d
0x180024b0e  jnz     loc_180024CDE
0x180024b14  xor     edx, edx
0x180024b16  lea     rcx, [rsp+450h+TokenHandle]
0x180024b1b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180024b20  xor     edx, edx
0x180024b22  lea     rcx, [rsp+450h+hProcess]
0x180024b27  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180024b2c  and     [rsp+450h+ReturnLength], rdi
0x180024b31  lea     r9, [rsp+450h+var_3F0]; unsigned int *
0x180024b36  lea     r8, [rsp+450h+TokenHandle]; void **
0x180024b3b  mov     rcx, r13; void *
0x180024b3e  lea     rdx, [rsp+450h+hProcess]; void **
0x180024b43  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x180024b48  mov     edi, [rsp+450h+var_3F0]
0x180024b4c  xor     r13d, r13d
0x180024b4f  mov     [rsp+450h+Reply], eax
0x180024b53  test    eax, eax
0x180024b55  jnz     loc_180024CE6
0x180024b5b  test    edi, edi
0x180024b5d  jz      short loc_180024B6C
0x180024b5f  mov     [rsp+450h+Reply], 5
0x180024b67  jmp     loc_180024CE6
0x180024b6c  mov     rcx, [rsp+450h+hProcess]; hProcess
0x180024b71  lea     r8, [rbp+350h+Filename]; lpFilename
0x180024b78  mov     r9d, 104h; nSize
0x180024b7e  xor     edx, edx; hModule
0x180024b80  call    cs:__imp_K32GetModuleFileNameExW
0x180024b87  nop     dword ptr [rax+rax+00h]
0x180024b8c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x180024b93  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x180024b98  test    al, al
0x180024b9a  jz      short loc_180024BB6
0x180024b9c  mov     rcx, [rsp+450h+TokenHandle]; TokenHandle
0x180024ba1  lea     r9, [rsp+450h+var_3FC]; int *
0x180024ba6  mov     r8, rsi; DuplicateTokenHandle
0x180024ba9  mov     rdx, rbx; HANDLE
0x180024bac  call    ?AiGetElevationToken@@YAKPEAX0PEAPEAXPEAH@Z; AiGetElevationToken(void *,void *,void * *,int *)
0x180024bb1  jmp     loc_180024AF9
0x180024bb6  call    LUAIsShadowAdminEnabled
0x180024bbb  mov     r14d, eax
0x180024bbe  test    eax, eax
0x180024bc0  jnz     short loc_180024BE8
0x180024bc2  xor     edx, edx
0x180024bc4  lea     rcx, [rsp+450h+ExistingTokenHandle]
0x180024bc9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180024bce  lea     rdx, [rsp+450h+ExistingTokenHandle]; NewTokenHandle
0x180024bd3  mov     rcx, rbx; TokenHandle
0x180024bd6  call    LUAGetElevatedToken
0x180024bdb  test    eax, eax
0x180024bdd  jns     loc_180024C8F
0x180024be3  jmp     loc_180024AEB
0x180024be8  lea     rcx, [rbp+350h+var_3C8]; struct _CONSENTUI_PARAM_HEADER **
0x180024bec  call    ?AiBuildElevateTokenAPIParams@@YAKPEAPEAU_CONSENTUI_PARAM_HEADER@@@Z; AiBuildElevateTokenAPIParams(_CONSENTUI_PARAM_HEADER * *)
0x180024bf1  mov     [rsp+450h+Reply], eax
0x180024bf5  test    eax, eax
0x180024bf7  jnz     loc_180024CE6
0x180024bfd  mov     r9d, 4; TokenInformationLength
0x180024c03  lea     rax, [rbp+350h+var_3D0]
0x180024c07  lea     r8, [rsp+450h+TokenInformation]; TokenInformation
0x180024c0c  mov     [rsp+450h+ReturnLength], rax; ReturnLength
0x180024c11  mov     rcx, rbx; TokenHandle
0x180024c14  lea     edx, [r9+8]; TokenInformationClass
0x180024c18  call    cs:__imp_GetTokenInformation
0x180024c1f  nop     dword ptr [rax+rax+00h]
0x180024c24  test    eax, eax
0x180024c26  jnz     short loc_180024C39
0x180024c28  call    cs:__imp_GetLastError
0x180024c2f  nop     dword ptr [rax+rax+00h]
0x180024c34  jmp     loc_180024AF9
0x180024c39  xor     edx, edx
0x180024c3b  lea     rcx, [rsp+450h+ExistingTokenHandle]
0x180024c40  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180024c45  mov     rdx, [rbp+350h+var_3C8]
0x180024c49  lea     rax, [rsp+450h+ExistingTokenHandle]
0x180024c4e  mov     [rsp+450h+var_408], rax
0x180024c53  lea     r8, aWinsta0Default; "Winsta0\\Default"
0x180024c5a  mov     eax, [rsp+450h+TokenInformation]
0x180024c5e  xor     r9d, r9d
0x180024c61  mov     [rsp+450h+var_410], r13
0x180024c66  mov     rcx, rbx
0x180024c69  or      [rsp+450h+var_418], 0FFFFFFFFh
0x180024c6e  mov     [rsp+450h+var_420], 9
0x180024c76  mov     [rsp+450h+var_428], 10000000h
0x180024c7e  mov     dword ptr [rsp+450h+ReturnLength], eax
0x180024c82  call    ?AiLaunchConsentUI@@YAKPEAXPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAUHWND__@@KKW4ELEVATION_REASON@@KPEBDPEAPEAX@Z; AiLaunchConsentUI(void *,_CONSENTUI_PARAM_HEADER *,ushort const *,HWND__ *,ulong,ulong,ELEVATION_REASON,ulong,char const *,void * *)
0x180024c87  mov     [rsp+450h+Reply], eax
0x180024c8b  test    eax, eax
0x180024c8d  jnz     short loc_180024CE6
0x180024c8f  mov     rcx, [rsp+450h+TokenHandle]; TokenHandle
0x180024c94  lea     rdx, [rsp+450h+var_3FC]; int *
0x180024c99  call    ?AiCheckForTcbPrivilege@@YAJPEAXPEAH@Z; AiCheckForTcbPrivilege(void *,int *)
0x180024c9e  test    eax, eax
0x180024ca0  js      loc_180024AEB
0x180024ca6  cmp     [rsp+450h+var_3FC], r13d
0x180024cab  jz      short loc_180024CBC
0x180024cad  mov     rax, [rsp+450h+ExistingTokenHandle]
0x180024cb2  mov     [rsi], rax
0x180024cb5  mov     [rsp+450h+ExistingTokenHandle], r13
0x180024cba  jmp     short loc_180024CE6
0x180024cbc  mov     rcx, [rsp+450h+ExistingTokenHandle]; ExistingTokenHandle
0x180024cc1  mov     r8, rsi; DuplicateTokenHandle
0x180024cc4  mov     edx, 1; ImpersonationLevel
0x180024cc9  call    cs:__imp_DuplicateToken
0x180024cd0  nop     dword ptr [rax+rax+00h]
0x180024cd5  test    eax, eax
0x180024cd7  jnz     short loc_180024CE6
0x180024cd9  jmp     loc_180024C28
0x180024cde  mov     [rsp+450h+Reply], 57h ; 'W'
0x180024ce6  mov     eax, [rsp+450h+var_3FC]
0x180024cea  lea     r8, [rbp+350h+Filename]; unsigned __int16 *
0x180024cf1  mov     edx, [rsp+450h+Reply]; unsigned int
0x180024cf5  lea     rcx, [rbp+350h+var_3B0]; this
0x180024cf9  mov     [rsp+450h+var_418], eax; int
0x180024cfd  mov     r9d, edi; unsigned int
0x180024d00  mov     [rsp+450h+var_420], r12d; int
0x180024d05  mov     [rsp+450h+var_428], r15d; int
0x180024d0a  mov     dword ptr [rsp+450h+ReturnLength], r14d; int
0x180024d0f  call    ?Stop@GetElevatedTokenActivity@LUATelemetry@@QEAAXKPEBGKHHHH@Z; LUATelemetry::GetElevatedTokenActivity::Stop(ulong,ushort const *,ulong,int,int,int,int)
0x180024d14  mov     rcx, [rbp+350h+pAsync]; pAsync
0x180024d18  lea     rdx, [rsp+450h+Reply]; Reply
0x180024d1d  call    cs:__imp_RpcAsyncCompleteCall
0x180024d24  nop     dword ptr [rax+rax+00h]
0x180024d29  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d30  lea     rax, WPP_GLOBAL_Control
0x180024d37  cmp     rcx, rax
0x180024d3a  jz      short loc_180024D5C
0x180024d3c  test    byte ptr [rcx+1Ch], 1
0x180024d40  jz      short loc_180024D5C
0x180024d42  mov     r9d, [rsp+450h+Reply]
0x180024d47  lea     r8, WPP_f5aaa73de7b43f98c43505c36bde04ec_Traceguids
0x180024d4e  mov     rcx, [rcx+10h]
0x180024d52  mov     edx, 0Bh
0x180024d57  call    WPP_SF_D
0x180024d5c  lea     rcx, [rbp+350h+var_3B0]; this
0x180024d60  call    ??1GetElevatedTokenActivity@LUATelemetry@@QEAA@XZ; LUATelemetry::GetElevatedTokenActivity::~GetElevatedTokenActivity(void)
0x180024d65  lea     rcx, [rsp+450h+ExistingTokenHandle]
0x180024d6a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180024d6f  lea     rcx, [rsp+450h+TokenHandle]
0x180024d74  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180024d79  lea     rcx, [rsp+450h+hProcess]
0x180024d7e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180024d83  mov     rcx, [rbp+350h+var_50]
0x180024d8a  xor     rcx, rsp; StackCookie
0x180024d8d  call    __security_check_cookie
0x180024d92  add     rsp, 418h
0x180024d99  pop     r15
0x180024d9b  pop     r14
0x180024d9d  pop     r13
0x180024d9f  pop     r12
0x180024da1  pop     rdi
0x180024da2  pop     rsi
0x180024da3  pop     rbx
0x180024da4  pop     rbp
0x180024da5  retn
```
