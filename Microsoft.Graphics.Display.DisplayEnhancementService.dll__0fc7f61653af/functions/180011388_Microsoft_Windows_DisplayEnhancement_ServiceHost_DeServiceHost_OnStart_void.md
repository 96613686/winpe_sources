# Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost::OnStart(void)

- ea: `0x180011388`
- end: `0x1800114d7`
- name: `?OnStart@DeServiceHost@ServiceHost@DisplayEnhancement@Windows@Microsoft@@QEAAXXZ`
- size: `335`
- prototype: `void __fastcall(Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000a008`

## callees

- `0x1800058bc`
- `0x180009f68`
- `0x18000f778`
- `0x180011000`
- `0x180011028`
- `0x1800112f0`
- `0x18001130c`
- `0x180011388`
- `0x180011704`
- `0x180012ccc`
- `0x18006908c`
- `0x1800ed010`

## import_xrefs

- `ntdll!NtUpdateWnfStateData` at `0x1800113c0`
- `ntdll!NtUpdateWnfStateData` at `0x1800113c0`

## string_xrefs

- `0x1800113d2`: `onecoreuap\drivers\mobilepc\displayenhancement\service\deservicehost\lib\deservicehost.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost::OnStart(
        Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost *this)
{
  int updated; // eax
  const char *v2; // r9
  Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost *v3; // rdi
  __int64 *Shared; // rax
  std::_Ref_count_base *v5; // rcx
  Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost *v6; // rdi
  __int64 *v7; // rax
  std::_Ref_count_base *v8; // rcx
  const char *v9; // r9
  __int64 v10; // rcx
  __int64 v11; // rcx
  void *v12; // rdx
  unsigned int v13; // r8d
  const char *v14; // r9
  _BYTE v15[8]; // [rsp+40h] [rbp-18h] BYREF
  std::_Ref_count_base *v16; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost *v18; // [rsp+60h] [rbp+8h] BYREF

  v18 = this;
  LOBYTE(v18) = 1;
  updated = NtUpdateWnfStateData(&WNF_PO_BASIC_BRIGHTNESS_ENGINE_DISABLED, &v18, 1);
  try
  {
    if ( updated < 0 )
      wil::details::in1diag3::_Throw_NtStatus(
        retaddr,
        (void *)0x34,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\deservicehost\\lib\\deservicehost.cpp",
        (const char *)(unsigned int)updated,
        0);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\deservicehost\\lib\\deservicehost.cpp",
      v2);
  }
  try
  {
    v3 = (Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost *)operator new(0x10u);
    v18 = v3;
    *(_QWORD *)v3 = 0;
    *((_QWORD *)v3 + 1) = 0;
    Shared = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(v15);
    std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
      v3,
      Shared);
    v5 = v16;
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
    v18 = v3;
    std::unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer> (*)(void),&public: static std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer> Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void),>>::operator=<std::default_delete<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer> (*)(void),&public: static std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer> Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void),>>,0>(
      (__int64)v5,
      (__int64 *)&v18);
    std::unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer> (*)(void),&public: static std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer> Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void),>>::~unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer> (*)(void),&public: static std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer> Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void),>>(&v18);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)qword_18012ABF8 + 32LL))(*(_QWORD *)qword_18012ABF8);
    v6 = (Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost *)operator new(0x10u);
    v18 = v6;
    *(_QWORD *)v6 = 0;
    *((_QWORD *)v6 + 1) = 0;
    v7 = (__int64 *)Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer::GetOrMakeShared(v15);
    std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(
      v6,
      v7);
    v8 = v16;
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
    v18 = v6;
    std::unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer> (*)(void),&public: static std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer> Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer::GetOrMakeShared(void),>>::operator=<std::default_delete<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer> (*)(void),&public: static std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer> Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer::GetOrMakeShared(void),>>,0>(
      (__int64)v8,
      (__int64 *)&v18);
    std::unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer> (*)(void),&public: static std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer> Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer::GetOrMakeShared(void),>>::~unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer> (*)(void),&public: static std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer> Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer::GetOrMakeShared(void),>>(&v18);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)qword_18012AC00 + 8LL))(*(_QWORD *)qword_18012AC00);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\displayenhancement\\service\\deservicehost\\lib\\deservicehost.cpp",
      v9);
    std::unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer> (*)(void),&public: static std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer> Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void),>>::reset(
      v10,
      0);
    std::unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer> (*)(void),&public: static std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer> Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer::GetOrMakeShared(void),>>::reset(
      v11,
      0);
    wil::details::in1diag3::Throw_CaughtException(retaddr, v12, v13, v14);
  }
}

```

## disassembly

```asm
0x180011388  mov     rax, rsp
0x18001138b  mov     [rax+8], rcx
0x18001138f  push    rdi
0x180011390  sub     rsp, 50h
0x180011394  mov     byte ptr [rax+8], 1
0x180011398  mov     dword ptr [rax-28h], 0
0x18001139f  mov     dword ptr [rax-30h], 0
0x1800113a6  mov     qword ptr [rax-38h], 0
0x1800113ae  xor     r9d, r9d
0x1800113b1  lea     r8d, [r9+1]
0x1800113b5  lea     rdx, [rax+8]
0x1800113b9  lea     rcx, WNF_PO_BASIC_BRIGHTNESS_ENGINE_DISABLED
0x1800113c0  call    cs:__imp_NtUpdateWnfStateData
0x1800113c6  mov     rcx, [rsp+58h]; this
0x1800113cb  test    eax, eax
0x1800113cd  jns     short loc_1800113E4
0x1800113cf  mov     r9d, eax; char *
0x1800113d2  lea     r8, aOnecoreuapDriv_23; "onecoreuap\\drivers\\mobilepc\\displaye"...
0x1800113d9  mov     edx, 34h ; '4'; void *
0x1800113de  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x1800113e4  jmp     short $+2
0x1800113e6  mov     ecx, 10h; Size
0x1800113eb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800113f0  mov     rdi, rax
0x1800113f3  mov     [rsp+58h+arg_0], rax
0x1800113f8  mov     qword ptr [rax], 0
0x1800113ff  mov     qword ptr [rax+8], 0
0x180011407  lea     rcx, [rsp+58h+var_18]
0x18001140c  call    ?GetOrMakeShared@DeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ; Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void)
0x180011411  mov     rdx, rax
0x180011414  mov     rcx, rdi
0x180011417  call    ??$?4V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@$0A@@?$shared_ptr@V?$OEMSetting@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>> &&)
0x18001141c  mov     rcx, [rsp+58h+var_10]; this
0x180011421  test    rcx, rcx
0x180011424  jz      short loc_18001142C
0x180011426  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001142b  nop
0x18001142c  mov     [rsp+58h+arg_0], rdi
0x180011431  lea     rdx, [rsp+58h+arg_0]
0x180011436  call    ??$?4U?$default_delete@V?$RpcServerLifetime@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@P6A?AV?$shared_ptr@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ$1?GetOrMakeShared@11234@SA?AV56@XZ$$V@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@$0A@@?$unique_ptr@V?$RpcServerLifetime@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@P6A?AV?$shared_ptr@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ$1?GetOrMakeShared@11234@SA?AV56@XZ$$V@Foundation@DisplayEnhancement@Windows@Microsoft@@U?$default_delete@V?$RpcServerLifetime@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@P6A?AV?$shared_ptr@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ$1?GetOrMakeShared@11234@SA?AV56@XZ$$V@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer> (*)(void),&Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void),>>::operator=<std::default_delete<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer> (*)(void),&Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void),>>,0>(std::unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer> (*)(void),&Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void),>> &&)
0x18001143b  lea     rcx, [rsp+58h+arg_0]
0x180011440  call    ??1?$unique_ptr@V?$RpcServerLifetime@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@P6A?AV?$shared_ptr@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ$1?GetOrMakeShared@11234@SA?AV56@XZ$$V@Foundation@DisplayEnhancement@Windows@Microsoft@@U?$default_delete@V?$RpcServerLifetime@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@P6A?AV?$shared_ptr@VDeManagementRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ$1?GetOrMakeShared@11234@SA?AV56@XZ$$V@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer> (*)(void),&Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void),>>::~unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer> (*)(void),&Microsoft::Windows::DisplayEnhancement::DeManagementRpcServer::DeManagementRpcServer::GetOrMakeShared(void),>>(void)
0x180011445  mov     rax, cs:qword_18012ABF8
0x18001144c  mov     rcx, [rax]
0x18001144f  mov     rax, [rcx]
0x180011452  mov     rax, [rax+20h]
0x180011456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001145b  mov     ecx, 10h; Size
0x180011460  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011465  mov     rdi, rax
0x180011468  mov     [rsp+58h+arg_0], rax
0x18001146d  mov     qword ptr [rax], 0
0x180011474  mov     qword ptr [rax+8], 0
0x18001147c  lea     rcx, [rsp+58h+var_18]
0x180011481  call    ?GetOrMakeShared@DeoRpcServer@1DisplayEnhancement@Windows@Microsoft@@SA?AV?$shared_ptr@VDeoRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ; Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer::GetOrMakeShared(void)
0x180011486  mov     rdx, rax
0x180011489  mov     rcx, rdi
0x18001148c  call    ??$?4V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@$0A@@?$shared_ptr@V?$OEMSetting@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV?$shared_ptr@V?$OEMSettingFromRegistry@_N@OEMSettings@DisplayEnhancement@Windows@Microsoft@@@1@@Z; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSetting<bool>>::operator=<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>,0>(std::shared_ptr<Microsoft::Windows::DisplayEnhancement::OEMSettings::OEMSettingFromRegistry<bool>> &&)
0x180011491  mov     rcx, [rsp+58h+var_10]; this
0x180011496  test    rcx, rcx
0x180011499  jz      short loc_1800114A1
0x18001149b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800114a0  nop
0x1800114a1  mov     [rsp+58h+arg_0], rdi
0x1800114a6  lea     rdx, [rsp+58h+arg_0]
0x1800114ab  call    ??$?4U?$default_delete@V?$RpcServerLifetime@VDeoRpcServer@1DisplayEnhancement@Windows@Microsoft@@P6A?AV?$shared_ptr@VDeoRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ$1?GetOrMakeShared@11234@SA?AV56@XZ$$V@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@$0A@@?$unique_ptr@V?$RpcServerLifetime@VDeoRpcServer@1DisplayEnhancement@Windows@Microsoft@@P6A?AV?$shared_ptr@VDeoRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ$1?GetOrMakeShared@11234@SA?AV56@XZ$$V@Foundation@DisplayEnhancement@Windows@Microsoft@@U?$default_delete@V?$RpcServerLifetime@VDeoRpcServer@1DisplayEnhancement@Windows@Microsoft@@P6A?AV?$shared_ptr@VDeoRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ$1?GetOrMakeShared@11234@SA?AV56@XZ$$V@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer> (*)(void),&Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer::GetOrMakeShared(void),>>::operator=<std::default_delete<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer> (*)(void),&Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer::GetOrMakeShared(void),>>,0>(std::unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer> (*)(void),&Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer::GetOrMakeShared(void),>> &&)
0x1800114b0  lea     rcx, [rsp+58h+arg_0]
0x1800114b5  call    ??1?$unique_ptr@V?$RpcServerLifetime@VDeoRpcServer@1DisplayEnhancement@Windows@Microsoft@@P6A?AV?$shared_ptr@VDeoRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ$1?GetOrMakeShared@11234@SA?AV56@XZ$$V@Foundation@DisplayEnhancement@Windows@Microsoft@@U?$default_delete@V?$RpcServerLifetime@VDeoRpcServer@1DisplayEnhancement@Windows@Microsoft@@P6A?AV?$shared_ptr@VDeoRpcServer@1DisplayEnhancement@Windows@Microsoft@@@std@@XZ$1?GetOrMakeShared@11234@SA?AV56@XZ$$V@Foundation@DisplayEnhancement@Windows@Microsoft@@@std@@@std@@QEAA@XZ; std::unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer> (*)(void),&Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer::GetOrMakeShared(void),>>::~unique_ptr<Microsoft::Windows::DisplayEnhancement::Foundation::RpcServerLifetime<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer,std::shared_ptr<Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer> (*)(void),&Microsoft::Windows::DisplayEnhancement::DeoRpcServer::DeoRpcServer::GetOrMakeShared(void),>>(void)
0x1800114ba  mov     rax, cs:qword_18012AC00
0x1800114c1  mov     rcx, [rax]
0x1800114c4  mov     rax, [rcx]
0x1800114c7  mov     rax, [rax+8]
0x1800114cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800114d0  nop
0x1800114d1  add     rsp, 50h
0x1800114d5  pop     rdi
0x1800114d6  retn
```
