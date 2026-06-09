# OSIntegration::DEH::Internal::CustomInstallExecution::Run(ushort const * const,__int64,bool)

- ea: `0x14000a8a8`
- end: `0x14000a9ff`
- name: `?Run@CustomInstallExecution@Internal@DEH@OSIntegration@@SAHQEBG_J_N@Z`
- size: `343`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, char)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000d1a0`

## callees

- `0x140002430`
- `0x1400033b0`
- `0x14000818c`
- `0x1400084f8`
- `0x140008524`
- `0x140008758`
- `0x140008e20`
- `0x140009758`
- `0x1400098dc`
- `0x140009cd8`
- `0x14000a8a8`
- `0x14000ab00`
- `0x14000ad14`
- `0x14000e61c`

## string_xrefs

- `0x14000a8e2`: `CustomInstallExecRun`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::CustomInstallExecution::Run(
        const unsigned __int16 *a1,
        __int64 a2,
        char a3)
{
  unsigned int v6; // ebx
  __int128 v8; // [rsp+40h] [rbp-C0h] BYREF
  int v9; // [rsp+50h] [rbp-B0h]
  __int128 v10; // [rsp+58h] [rbp-A8h]
  int v11; // [rsp+68h] [rbp-98h]
  __int128 v12; // [rsp+70h] [rbp-90h]
  unsigned __int64 v13; // [rsp+80h] [rbp-80h]
  char v14; // [rsp+88h] [rbp-78h]
  __int64 v15; // [rsp+90h] [rbp-70h]
  char v16; // [rsp+98h] [rbp-68h]
  struct _GUID v17; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v18[42]; // [rsp+B0h] [rbp-50h] BYREF

  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&qword_140016038);
  wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v18,
    "CustomInstallExecRun");
  v18[0] = &CASTraceProvider::CustomInstallExecRun::`vftable';
  CASTraceProvider::CustomInstallExecRun::StartActivity((CASTraceProvider::CustomInstallExecRun *)v18);
  OSIntegration::DEH::Internal::TraceLoggingStatic::s_customInstallExecId = *(GUID *)(v18[34] + 8LL);
  OSIntegration::DEH::Internal::SRStatics::Initialize();
  v8 = 0;
  v9 = 0;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 1;
  v15 = 0;
  v16 = 0;
  Common::StringBuffer::SetValueFromString((Common::StringBuffer *)&v8, a1);
  v15 = a2;
  v16 = a3 ^ 1;
  OSIntegration::DEH::Internal::CustomInstallExecution::LoadFromStateRepository((OSIntegration::DEH::Internal::CustomInstallExecution *)&v8);
  v6 = OSIntegration::DEH::Internal::CustomInstallExecution::ExecuteActions((OSIntegration::DEH::Internal::CustomInstallExecution *)&v8);
  if ( !v6 )
    OSIntegration::DEH::Internal::CustomInstallExecution::ClearPackageStatus((OSIntegration::DEH::Internal::CustomInstallExecution *)&v8);
  v17 = OSIntegration::DEH::Internal::TraceLoggingStatic::s_customInstallExecId;
  CASTraceProvider::CustomInstallExecRun::Stop((CASTraceProvider::CustomInstallExecRun *)v18, &v17, a1, v13, v6);
  OSIntegration::DEH::Internal::CustomInstallExecution::~CustomInstallExecution((OSIntegration::DEH::Internal::CustomInstallExecution *)&v8);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&OSIntegration::DEH::Internal::SRStatics::s_perMachineUser);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics);
  CASTraceProvider::CustomInstallExecRun::~CustomInstallExecRun((CASTraceProvider::CustomInstallExecRun *)v18);
  return v6;
}

```

## disassembly

```asm
0x14000a8a8  push    rbp
0x14000a8aa  push    rbx
0x14000a8ab  push    rsi
0x14000a8ac  push    rdi
0x14000a8ad  lea     rbp, [rsp-118h]
0x14000a8b5  sub     rsp, 218h
0x14000a8bc  mov     rax, cs:__security_cookie
0x14000a8c3  xor     rax, rsp
0x14000a8c6  mov     [rbp+130h+var_30], rax
0x14000a8cd  mov     dil, r8b
0x14000a8d0  mov     rbx, rdx
0x14000a8d3  mov     rsi, rcx
0x14000a8d6  lea     rcx, qword_140016038; CallbackContext
0x14000a8dd  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14000a8e2  lea     rdx, aCustominstalle; "CustomInstallExecRun"
0x14000a8e9  lea     rcx, [rbp+130h+var_180]
0x14000a8ed  call    ??0?$ActivityBase@VCASTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CASTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x14000a8f2  lea     rax, ??_7CustomInstallExecRun@CASTraceProvider@@6B@; const CASTraceProvider::CustomInstallExecRun::`vftable'
0x14000a8f9  mov     [rbp+130h+var_180], rax
0x14000a8fd  lea     rcx, [rbp+130h+var_180]; this
0x14000a901  call    ?StartActivity@CustomInstallExecRun@CASTraceProvider@@QEAAXXZ; CASTraceProvider::CustomInstallExecRun::StartActivity(void)
0x14000a906  nop
0x14000a907  mov     rax, [rbp+130h+var_70]
0x14000a90e  movups  xmm0, xmmword ptr [rax+8]
0x14000a912  movdqu  xmmword ptr cs:?s_customInstallExecId@TraceLoggingStatic@Internal@DEH@OSIntegration@@0U_GUID@@A.Data1, xmm0; _GUID OSIntegration::DEH::Internal::TraceLoggingStatic::s_customInstallExecId ...
0x14000a91a  call    ?Initialize@SRStatics@Internal@DEH@OSIntegration@@SAXXZ; OSIntegration::DEH::Internal::SRStatics::Initialize(void)
0x14000a91f  mov     [rsp+230h+var_1FF], 1
0x14000a924  xor     eax, eax
0x14000a926  xorps   xmm0, xmm0
0x14000a929  movups  [rsp+230h+var_1F0], xmm0
0x14000a92e  mov     [rsp+230h+var_1E0], eax
0x14000a932  movups  [rsp+230h+var_1D8], xmm0
0x14000a937  mov     [rsp+230h+var_1C8], eax
0x14000a93b  xorps   xmm1, xmm1
0x14000a93e  movdqa  [rsp+230h+var_1C0], xmm1
0x14000a944  mov     [rbp+130h+var_1B0], rax
0x14000a948  mov     [rbp+130h+var_1A8], 1
0x14000a94c  mov     [rbp+130h+var_1A0], rax
0x14000a950  mov     [rbp+130h+var_198], al
0x14000a953  mov     rdx, rsi; unsigned __int16 *
0x14000a956  lea     rcx, [rsp+230h+var_1F0]; this
0x14000a95b  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x14000a960  mov     [rbp+130h+var_1A0], rbx
0x14000a964  xor     dil, 1
0x14000a968  mov     [rbp+130h+var_198], dil
0x14000a96c  lea     rcx, [rsp+230h+var_1F0]; this
0x14000a971  call    ?LoadFromStateRepository@CustomInstallExecution@Internal@DEH@OSIntegration@@IEAAXXZ; OSIntegration::DEH::Internal::CustomInstallExecution::LoadFromStateRepository(void)
0x14000a976  lea     rcx, [rsp+230h+var_1F0]; this
0x14000a97b  call    ?ExecuteActions@CustomInstallExecution@Internal@DEH@OSIntegration@@IEAAKXZ; OSIntegration::DEH::Internal::CustomInstallExecution::ExecuteActions(void)
0x14000a980  mov     ebx, eax
0x14000a982  test    eax, eax
0x14000a984  jnz     short loc_14000A990
0x14000a986  lea     rcx, [rsp+230h+var_1F0]; this
0x14000a98b  call    ?ClearPackageStatus@CustomInstallExecution@Internal@DEH@OSIntegration@@IEAAXXZ; OSIntegration::DEH::Internal::CustomInstallExecution::ClearPackageStatus(void)
0x14000a990  movups  xmm0, xmmword ptr cs:?s_customInstallExecId@TraceLoggingStatic@Internal@DEH@OSIntegration@@0U_GUID@@A.Data1; _GUID OSIntegration::DEH::Internal::TraceLoggingStatic::s_customInstallExecId ...
0x14000a997  movdqu  xmmword ptr [rbp+130h+var_190.Data1], xmm0
0x14000a99c  mov     [rsp+230h+var_210], ebx; unsigned int
0x14000a9a0  mov     r9, [rbp+130h+var_1B0]; unsigned __int64
0x14000a9a4  mov     r8, rsi; unsigned __int16 *
0x14000a9a7  lea     rdx, [rbp+130h+var_190]; struct _GUID *
0x14000a9ab  lea     rcx, [rbp+130h+var_180]; this
0x14000a9af  call    ?Stop@CustomInstallExecRun@CASTraceProvider@@QEAAXU_GUID@@PEBG_KK@Z; CASTraceProvider::CustomInstallExecRun::Stop(_GUID,ushort const *,unsigned __int64,ulong)
0x14000a9b4  nop
0x14000a9b5  lea     rcx, [rsp+230h+var_1F0]; this
0x14000a9ba  call    ??1CustomInstallExecution@Internal@DEH@OSIntegration@@QEAA@XZ; OSIntegration::DEH::Internal::CustomInstallExecution::~CustomInstallExecution(void)
0x14000a9bf  nop
0x14000a9c0  lea     rcx, ?s_perMachineUser@SRStatics@Internal@DEH@OSIntegration@@1V?$ComPtr@UIUser@StateRepository@Internal@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUser> OSIntegration::DEH::Internal::SRStatics::s_perMachineUser
0x14000a9c7  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x14000a9cc  lea     rcx, ?s_customInstallWorkStatics@SRStatics@Internal@DEH@OSIntegration@@1V?$ComPtr@UICustomInstallWorkStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ICustomInstallWorkStatics> OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics
0x14000a9d3  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x14000a9d8  nop
0x14000a9d9  lea     rcx, [rbp+130h+var_180]; this
0x14000a9dd  call    ??1CustomInstallExecRun@CASTraceProvider@@QEAA@XZ; CASTraceProvider::CustomInstallExecRun::~CustomInstallExecRun(void)
0x14000a9e2  mov     eax, ebx
0x14000a9e4  mov     rcx, [rbp+130h+var_30]
0x14000a9eb  xor     rcx, rsp; StackCookie
0x14000a9ee  call    __security_check_cookie
0x14000a9f3  add     rsp, 218h
0x14000a9fa  pop     rdi
0x14000a9fb  pop     rsi
0x14000a9fc  pop     rbx
0x14000a9fd  pop     rbp
0x14000a9fe  retn
```
