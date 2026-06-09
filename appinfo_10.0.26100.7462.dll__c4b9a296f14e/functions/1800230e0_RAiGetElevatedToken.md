# RAiGetElevatedToken

- ea: `0x1800230e0`
- end: `0x180023497`
- name: `RAiGetElevatedToken`
- size: `951`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a230`
- `0x18000c790`
- `0x18000f9e0`
- `0x18001959c`
- `0x18001afdc`
- `0x18001dfd8`
- `0x18001e444`
- `0x18001e804`
- `0x180021e28`
- `0x180021ed8`
- `0x180022bb0`
- `0x1800230e0`
- `0x1800234a0`
- `0x1800243ec`
- `0x180024a98`
- `0x180043c14`
- `0x180043f6c`
- `0x1800449fa`
- `0x180044a20`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x18002340d`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18002340d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023308`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180023308`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800233b9`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1800233b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023318`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023318`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180023270`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180023270`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800231dd`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800231dd`

## string_xrefs

- `0x180023158`: `GetElevatedTokenActivity`

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
      &WPP_67bea7eefcf5311daaba7659c5767e76_Traceguids,
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
    WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_67bea7eefcf5311daaba7659c5767e76_Traceguids, Reply);
  LUATelemetry::GetElevatedTokenActivity::~GetElevatedTokenActivity((LUATelemetry::GetElevatedTokenActivity *)v18);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&ExistingTokenHandle);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hProcess);
}

```

## disassembly

```asm
0x1800230e0  push    rbp
0x1800230e2  push    rbx
0x1800230e3  push    rsi
0x1800230e4  push    rdi
0x1800230e5  push    r12
0x1800230e7  push    r13
0x1800230e9  push    r14
0x1800230eb  push    r15
0x1800230ed  lea     rbp, [rsp-318h]
0x1800230f5  sub     rsp, 418h
0x1800230fc  mov     rax, cs:__security_cookie
0x180023103  xor     rax, rsp
0x180023106  mov     [rbp+350h+var_50], rax
0x18002310d  xor     r15d, r15d
0x180023110  mov     [rbp+350h+pAsync], rcx
0x180023114  mov     rbx, r8
0x180023117  mov     [rsp+450h+var_3F0], r15d
0x18002311c  mov     r13, rdx
0x18002311f  mov     [rsp+450h+TokenInformation], r15d
0x180023124  xor     edx, edx; Val
0x180023126  mov     [rbp+350h+var_3D0], r15d
0x18002312a  mov     r8d, 208h; Size
0x180023130  mov     [rbp+350h+var_3C8], r15
0x180023134  lea     rcx, [rbp+350h+Filename]; void *
0x18002313b  mov     [rsp+450h+var_3EC], r15d
0x180023140  mov     edi, r15d
0x180023143  mov     [rsp+450h+var_3E8], r15d
0x180023148  mov     r14d, r15d
0x18002314b  mov     [rsp+450h+var_3FC], r15d
0x180023150  mov     rsi, r9
0x180023153  call    memset_0
0x180023158  lea     rdx, aGetelevatedtok; "GetElevatedTokenActivity"
0x18002315f  mov     [rsp+450h+hProcess], r15
0x180023164  lea     rcx, [rbp+350h+var_3B0]; struct wil::details::IFailureCallback *
0x180023168  mov     [rsp+450h+TokenHandle], r15
0x18002316d  mov     [rsp+450h+ExistingTokenHandle], r15
0x180023172  call    ??0?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180023177  lea     rax, ??_7GetElevatedTokenActivity@LUATelemetry@@6B@; const LUATelemetry::GetElevatedTokenActivity::`vftable'
0x18002317e  lea     rcx, [rbp+350h+var_3B0]; this
0x180023182  mov     [rbp+350h+var_3B0], rax
0x180023186  call    ?StartActivity@GetElevatedTokenActivity@LUATelemetry@@QEAAXXZ; LUATelemetry::GetElevatedTokenActivity::StartActivity(void)
0x18002318b  mov     rcx, cs:WPP_GLOBAL_Control
0x180023192  lea     rax, WPP_GLOBAL_Control
0x180023199  cmp     rcx, rax
0x18002319c  jz      short loc_1800231BB
0x18002319e  test    byte ptr [rcx+1Ch], 1
0x1800231a2  jz      short loc_1800231BB
0x1800231a4  mov     rcx, [rcx+10h]
0x1800231a8  lea     edx, [r15+0Ah]
0x1800231ac  mov     r9d, ebx
0x1800231af  lea     r8, WPP_67bea7eefcf5311daaba7659c5767e76_Traceguids
0x1800231b6  call    WPP_SF_D
0x1800231bb  lea     r8, [rsp+450h+var_3E8]
0x1800231c0  mov     rcx, rbx; TokenHandle
0x1800231c3  lea     rdx, [rsp+450h+var_3EC]
0x1800231c8  call    LUAIsElevatedToken
0x1800231cd  mov     r15d, [rsp+450h+var_3EC]
0x1800231d2  mov     r12d, [rsp+450h+var_3E8]
0x1800231d7  test    eax, eax
0x1800231d9  jns     short loc_1800231F2
0x1800231db  mov     ecx, eax; Status
0x1800231dd  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800231e4  nop     dword ptr [rax+rax+00h]
0x1800231e9  mov     [rsp+450h+Reply], eax
0x1800231ed  jmp     loc_1800233D6
0x1800231f2  test    r12d, r12d
0x1800231f5  jz      loc_1800233CE
0x1800231fb  test    r15d, r15d
0x1800231fe  jnz     loc_1800233CE
0x180023204  xor     edx, edx
0x180023206  lea     rcx, [rsp+450h+TokenHandle]
0x18002320b  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180023210  xor     edx, edx
0x180023212  lea     rcx, [rsp+450h+hProcess]
0x180023217  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002321c  and     [rsp+450h+ReturnLength], rdi
0x180023221  lea     r9, [rsp+450h+var_3F0]; unsigned int *
0x180023226  lea     r8, [rsp+450h+TokenHandle]; void **
0x18002322b  mov     rcx, r13; void *
0x18002322e  lea     rdx, [rsp+450h+hProcess]; void **
0x180023233  call    ?AiGetClientInformation@@YAKPEAXPEAPEAX1PEAK2@Z; AiGetClientInformation(void *,void * *,void * *,ulong *,ulong *)
0x180023238  mov     edi, [rsp+450h+var_3F0]
0x18002323c  xor     r13d, r13d
0x18002323f  mov     [rsp+450h+Reply], eax
0x180023243  test    eax, eax
0x180023245  jnz     loc_1800233D6
0x18002324b  test    edi, edi
0x18002324d  jz      short loc_18002325C
0x18002324f  mov     [rsp+450h+Reply], 5
0x180023257  jmp     loc_1800233D6
0x18002325c  mov     rcx, [rsp+450h+hProcess]; hProcess
0x180023261  lea     r8, [rbp+350h+Filename]; lpFilename
0x180023268  mov     r9d, 104h; nSize
0x18002326e  xor     edx, edx; hModule
0x180023270  call    cs:__imp_K32GetModuleFileNameExW
0x180023277  nop     dword ptr [rax+rax+00h]
0x18002327c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x180023283  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x180023288  test    al, al
0x18002328a  jz      short loc_1800232A6
0x18002328c  mov     rcx, [rsp+450h+TokenHandle]; TokenHandle
0x180023291  lea     r9, [rsp+450h+var_3FC]; int *
0x180023296  mov     r8, rsi; DuplicateTokenHandle
0x180023299  mov     rdx, rbx; HANDLE
0x18002329c  call    ?AiGetElevationToken@@YAKPEAX0PEAPEAXPEAH@Z; AiGetElevationToken(void *,void *,void * *,int *)
0x1800232a1  jmp     loc_1800231E9
0x1800232a6  call    LUAIsShadowAdminEnabled
0x1800232ab  mov     r14d, eax
0x1800232ae  test    eax, eax
0x1800232b0  jnz     short loc_1800232D8
0x1800232b2  xor     edx, edx
0x1800232b4  lea     rcx, [rsp+450h+ExistingTokenHandle]
0x1800232b9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800232be  lea     rdx, [rsp+450h+ExistingTokenHandle]; NewTokenHandle
0x1800232c3  mov     rcx, rbx; TokenHandle
0x1800232c6  call    LUAGetElevatedToken
0x1800232cb  test    eax, eax
0x1800232cd  jns     loc_18002337F
0x1800232d3  jmp     loc_1800231DB
0x1800232d8  lea     rcx, [rbp+350h+var_3C8]; struct _CONSENTUI_PARAM_HEADER **
0x1800232dc  call    ?AiBuildElevateTokenAPIParams@@YAKPEAPEAU_CONSENTUI_PARAM_HEADER@@@Z; AiBuildElevateTokenAPIParams(_CONSENTUI_PARAM_HEADER * *)
0x1800232e1  mov     [rsp+450h+Reply], eax
0x1800232e5  test    eax, eax
0x1800232e7  jnz     loc_1800233D6
0x1800232ed  mov     r9d, 4; TokenInformationLength
0x1800232f3  lea     rax, [rbp+350h+var_3D0]
0x1800232f7  lea     r8, [rsp+450h+TokenInformation]; TokenInformation
0x1800232fc  mov     [rsp+450h+ReturnLength], rax; ReturnLength
0x180023301  mov     rcx, rbx; TokenHandle
0x180023304  lea     edx, [r9+8]; TokenInformationClass
0x180023308  call    cs:__imp_GetTokenInformation
0x18002330f  nop     dword ptr [rax+rax+00h]
0x180023314  test    eax, eax
0x180023316  jnz     short loc_180023329
0x180023318  call    cs:__imp_GetLastError
0x18002331f  nop     dword ptr [rax+rax+00h]
0x180023324  jmp     loc_1800231E9
0x180023329  xor     edx, edx
0x18002332b  lea     rcx, [rsp+450h+ExistingTokenHandle]
0x180023330  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180023335  mov     rdx, [rbp+350h+var_3C8]
0x180023339  lea     rax, [rsp+450h+ExistingTokenHandle]
0x18002333e  mov     [rsp+450h+var_408], rax
0x180023343  lea     r8, aWinsta0Default; "Winsta0\\Default"
0x18002334a  mov     eax, [rsp+450h+TokenInformation]
0x18002334e  xor     r9d, r9d
0x180023351  mov     [rsp+450h+var_410], r13
0x180023356  mov     rcx, rbx
0x180023359  or      [rsp+450h+var_418], 0FFFFFFFFh
0x18002335e  mov     [rsp+450h+var_420], 9
0x180023366  mov     [rsp+450h+var_428], 10000000h
0x18002336e  mov     dword ptr [rsp+450h+ReturnLength], eax
0x180023372  call    ?AiLaunchConsentUI@@YAKPEAXPEAU_CONSENTUI_PARAM_HEADER@@PEBGPEAUHWND__@@KKW4ELEVATION_REASON@@KPEBDPEAPEAX@Z; AiLaunchConsentUI(void *,_CONSENTUI_PARAM_HEADER *,ushort const *,HWND__ *,ulong,ulong,ELEVATION_REASON,ulong,char const *,void * *)
0x180023377  mov     [rsp+450h+Reply], eax
0x18002337b  test    eax, eax
0x18002337d  jnz     short loc_1800233D6
0x18002337f  mov     rcx, [rsp+450h+TokenHandle]; TokenHandle
0x180023384  lea     rdx, [rsp+450h+var_3FC]; int *
0x180023389  call    ?AiCheckForTcbPrivilege@@YAJPEAXPEAH@Z; AiCheckForTcbPrivilege(void *,int *)
0x18002338e  test    eax, eax
0x180023390  js      loc_1800231DB
0x180023396  cmp     [rsp+450h+var_3FC], r13d
0x18002339b  jz      short loc_1800233AC
0x18002339d  mov     rax, [rsp+450h+ExistingTokenHandle]
0x1800233a2  mov     [rsi], rax
0x1800233a5  mov     [rsp+450h+ExistingTokenHandle], r13
0x1800233aa  jmp     short loc_1800233D6
0x1800233ac  mov     rcx, [rsp+450h+ExistingTokenHandle]; ExistingTokenHandle
0x1800233b1  mov     r8, rsi; DuplicateTokenHandle
0x1800233b4  mov     edx, 1; ImpersonationLevel
0x1800233b9  call    cs:__imp_DuplicateToken
0x1800233c0  nop     dword ptr [rax+rax+00h]
0x1800233c5  test    eax, eax
0x1800233c7  jnz     short loc_1800233D6
0x1800233c9  jmp     loc_180023318
0x1800233ce  mov     [rsp+450h+Reply], 57h ; 'W'
0x1800233d6  mov     eax, [rsp+450h+var_3FC]
0x1800233da  lea     r8, [rbp+350h+Filename]; unsigned __int16 *
0x1800233e1  mov     edx, [rsp+450h+Reply]; unsigned int
0x1800233e5  lea     rcx, [rbp+350h+var_3B0]; this
0x1800233e9  mov     [rsp+450h+var_418], eax; int
0x1800233ed  mov     r9d, edi; unsigned int
0x1800233f0  mov     [rsp+450h+var_420], r12d; int
0x1800233f5  mov     [rsp+450h+var_428], r15d; int
0x1800233fa  mov     dword ptr [rsp+450h+ReturnLength], r14d; int
0x1800233ff  call    ?Stop@GetElevatedTokenActivity@LUATelemetry@@QEAAXKPEBGKHHHH@Z; LUATelemetry::GetElevatedTokenActivity::Stop(ulong,ushort const *,ulong,int,int,int,int)
0x180023404  mov     rcx, [rbp+350h+pAsync]; pAsync
0x180023408  lea     rdx, [rsp+450h+Reply]; Reply
0x18002340d  call    cs:__imp_RpcAsyncCompleteCall
0x180023414  nop     dword ptr [rax+rax+00h]
0x180023419  mov     rcx, cs:WPP_GLOBAL_Control
0x180023420  lea     rax, WPP_GLOBAL_Control
0x180023427  cmp     rcx, rax
0x18002342a  jz      short loc_18002344C
0x18002342c  test    byte ptr [rcx+1Ch], 1
0x180023430  jz      short loc_18002344C
0x180023432  mov     r9d, [rsp+450h+Reply]
0x180023437  lea     r8, WPP_67bea7eefcf5311daaba7659c5767e76_Traceguids
0x18002343e  mov     rcx, [rcx+10h]
0x180023442  mov     edx, 0Bh
0x180023447  call    WPP_SF_D
0x18002344c  lea     rcx, [rbp+350h+var_3B0]; this
0x180023450  call    ??1GetElevatedTokenActivity@LUATelemetry@@QEAA@XZ; LUATelemetry::GetElevatedTokenActivity::~GetElevatedTokenActivity(void)
0x180023455  lea     rcx, [rsp+450h+ExistingTokenHandle]
0x18002345a  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002345f  lea     rcx, [rsp+450h+TokenHandle]
0x180023464  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180023469  lea     rcx, [rsp+450h+hProcess]
0x18002346e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180023473  mov     rcx, [rbp+350h+var_50]
0x18002347a  xor     rcx, rsp; StackCookie
0x18002347d  call    __security_check_cookie
0x180023482  add     rsp, 418h
0x180023489  pop     r15
0x18002348b  pop     r14
0x18002348d  pop     r13
0x18002348f  pop     r12
0x180023491  pop     rdi
0x180023492  pop     rsi
0x180023493  pop     rbx
0x180023494  pop     rbp
0x180023495  retn
```
