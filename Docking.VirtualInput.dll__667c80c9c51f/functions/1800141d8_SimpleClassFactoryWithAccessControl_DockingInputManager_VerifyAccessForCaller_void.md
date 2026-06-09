# SimpleClassFactoryWithAccessControl<DockingInputManager>::VerifyAccessForCaller(void)

- ea: `0x1800141d8`
- end: `0x1800144ff`
- name: `?VerifyAccessForCaller@?$SimpleClassFactoryWithAccessControl@VDockingInputManager@@@@AEAAJXZ`
- size: `807`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013ae0`

## callees

- `0x180004ba0`
- `0x180004bac`
- `0x180006784`
- `0x1800067a4`
- `0x18000b810`
- `0x18000c3d4`
- `0x1800131fc`
- `0x1800134bc`
- `0x18001351c`
- `0x1800141d8`
- `0x180014528`
- `0x18001aff4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001423d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001423d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014263`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014263`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800141e5`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1800141e5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800142f2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800142f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 SimpleClassFactoryWithAccessControl<DockingInputManager>::VerifyAccessForCaller()
{
  unsigned int v0; // eax
  const char *v1; // r9
  void *v3; // rax
  unsigned int TokenInformation; // eax
  const char *v5; // r9
  bool *v6; // r9
  unsigned int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rcx
  int ReturnLength; // [rsp+20h] [rbp-88h]
  int ReturnLengtha; // [rsp+20h] [rbp-88h]
  unsigned __int16 v12; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v13[2]; // [rsp+32h] [rbp-76h] BYREF
  _BYTE v14[4]; // [rsp+34h] [rbp-74h] BYREF
  char v15[8]; // [rsp+38h] [rbp-70h] BYREF
  HRESULT v16; // [rsp+40h] [rbp-68h]
  int v17; // [rsp+44h] [rbp-64h]
  int v18; // [rsp+48h] [rbp-60h] BYREF
  int v19; // [rsp+4Ch] [rbp-5Ch]
  int v20; // [rsp+50h] [rbp-58h]
  unsigned int LastError; // [rsp+58h] [rbp-50h]
  DWORD v23; // [rsp+5Ch] [rbp-4Ch] BYREF
  unsigned int v25; // [rsp+64h] [rbp-44h]
  unsigned int v26; // [rsp+68h] [rbp-40h]
  unsigned int v27; // [rsp+6Ch] [rbp-3Ch]
  int v28; // [rsp+70h] [rbp-38h]
  PHANDLE TokenHandle; // [rsp+78h] [rbp-30h]
  HANDLE ThreadHandle; // [rsp+80h] [rbp-28h]
  void *v31; // [rsp+88h] [rbp-20h]
  CallerIdentity *v32; // [rsp+90h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v16 = CoImpersonateClient();
  if ( v16 >= 0 )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>(v15);
    v18 = 0;
    memset(v13, 0, 1u);
    wil::ScopeExit<_lambda_fa82d6765b4dbbc65aa6b3636f8ab4dd_>(v14, v13);
    TokenHandle = (PHANDLE)Microsoft::WRL::Details::Forward<std::nullptr_t>(v15);
    ThreadHandle = GetCurrentThread();
    v0 = OpenThreadToken(ThreadHandle, 8u, 1, TokenHandle);
    if ( !(unsigned int)wil::verify_BOOL<int>(v0) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x43,
                    (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\dockinginputmanager.cpp",
                    v1);
      wil::details::ScopeExitFn<_lambda_fa82d6765b4dbbc65aa6b3636f8ab4dd_>::~ScopeExitFn<_lambda_fa82d6765b4dbbc65aa6b3636f8ab4dd_>(v14);
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>(v15);
      return LastError;
    }
    v23 = 0;
    v3 = (void *)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::get(v15);
    TokenInformation = GetTokenInformation(v3, TokenIsAppContainer, &v18, 4u, &v23);
    if ( !(unsigned int)wil::verify_BOOL<int>(TokenInformation) )
    {
      v25 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x46,
              (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\dockinginputmanager.cpp",
              v5);
      wil::details::ScopeExitFn<_lambda_fa82d6765b4dbbc65aa6b3636f8ab4dd_>::~ScopeExitFn<_lambda_fa82d6765b4dbbc65aa6b3636f8ab4dd_>(v14);
      wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>(v15);
      return v25;
    }
    wil::details::ScopeExitFn<_lambda_fa82d6765b4dbbc65aa6b3636f8ab4dd_>::~ScopeExitFn<_lambda_fa82d6765b4dbbc65aa6b3636f8ab4dd_>(v14);
    if ( v18 )
    {
      LOBYTE(v12) = 0;
      v31 = L"inputInjection";
      v32 = (CallerIdentity *)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::get(v15);
      v7 = CallerIdentity::CheckCapabilityFromImpersonationToken(v32, v31, &v12, v6);
      v19 = wil::verify_BOOL<int>(v7);
      if ( v19 < 0 )
      {
        v20 = v19;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4D,
          (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\dockinginputmanager.cpp",
          (const char *)(unsigned int)v19,
          ReturnLengtha);
        v26 = v20;
        wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>(v15);
        return v26;
      }
      LOBYTE(v8) = v12;
      HIBYTE(v12) = (unsigned __int8)wil::verify_bool<bool,0>(v8) == 0;
      LOBYTE(v9) = HIBYTE(v12);
      if ( (unsigned __int8)wil::verify_bool<bool,0>(v9) )
      {
        v28 = wil::verify_BOOL<int>(2147942405LL);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4E,
          (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\dockinginputmanager.cpp",
          (const char *)0x80070005LL,
          ReturnLengtha);
        v27 = -2147024891;
        wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>(v15);
        return v27;
      }
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>(v15);
    return 0;
  }
  if ( v16 == -2147417833 )
    return 0;
  v17 = wil::verify_BOOL<int>((unsigned int)v16);
  if ( v17 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecoreuap\\shell\\docking\\virtualinput\\lib\\dockinginputmanager.cpp",
      (const char *)(unsigned int)v17,
      ReturnLength);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800141d8  mov     [rsp+arg_0], rcx
0x1800141dd  push    rdi
0x1800141de  sub     rsp, 0A0h
0x1800141e5  call    cs:__imp_CoImpersonateClient
0x1800141eb  mov     [rsp+0A8h+var_68], eax
0x1800141ef  cmp     [rsp+0A8h+var_68], 0
0x1800141f4  jl      loc_1800144A8
0x1800141fa  lea     rcx, [rsp+0A8h+var_70]
0x1800141ff  call    ??0?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>(void)
0x180014204  nop
0x180014205  mov     dword ptr [rsp+0A8h+var_64+4], 0
0x18001420d  lea     rax, [rsp+0A8h+var_76]
0x180014212  mov     rdi, rax
0x180014215  xor     eax, eax
0x180014217  mov     ecx, 1
0x18001421c  rep stosb
0x18001421e  lea     rdx, [rsp+0A8h+var_76]
0x180014223  lea     rcx, [rsp+0A8h+var_74]
0x180014228  call    ??$ScopeExit@V_lambda_fa82d6765b4dbbc65aa6b3636f8ab4dd_@@@wil@@YA?AV?$ScopeExitFn@V_lambda_fa82d6765b4dbbc65aa6b3636f8ab4dd_@@@details@0@$$QEAV_lambda_fa82d6765b4dbbc65aa6b3636f8ab4dd_@@@Z; wil::ScopeExit<_lambda_fa82d6765b4dbbc65aa6b3636f8ab4dd_>(_lambda_fa82d6765b4dbbc65aa6b3636f8ab4dd_ &&)
0x18001422d  nop
0x18001422e  lea     rcx, [rsp+0A8h+var_70]
0x180014233  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x180014238  mov     [rsp+0A8h+TokenHandle], rax
0x18001423d  call    cs:__imp_GetCurrentThread
0x180014243  mov     [rsp+0A8h+ThreadHandle], rax
0x18001424b  mov     r9, [rsp+0A8h+TokenHandle]; TokenHandle
0x180014250  mov     r8d, 1; OpenAsSelf
0x180014256  mov     edx, 8; DesiredAccess
0x18001425b  mov     rcx, [rsp+0A8h+ThreadHandle]; ThreadHandle
0x180014263  call    cs:__imp_OpenThreadToken
0x180014269  mov     ecx, eax
0x18001426b  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x180014270  mov     dword ptr [rsp+0A8h+var_58+4], eax
0x180014274  cmp     dword ptr [rsp+0A8h+var_58+4], 0
0x180014279  jnz     short loc_1800142B9
0x18001427b  mov     rax, [rsp+0A8h]
0x180014283  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\docking\\virtualinpu"...
0x18001428a  mov     edx, 43h ; 'C'; void *
0x18001428f  mov     rcx, rax; this
0x180014292  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180014297  mov     [rsp+0A8h+var_50], eax
0x18001429b  lea     rcx, [rsp+0A8h+var_74]
0x1800142a0  call    ??1?$ScopeExitFn@V_lambda_fa82d6765b4dbbc65aa6b3636f8ab4dd_@@@details@wil@@QEAA@XZ; wil::details::ScopeExitFn<_lambda_fa82d6765b4dbbc65aa6b3636f8ab4dd_>::~ScopeExitFn<_lambda_fa82d6765b4dbbc65aa6b3636f8ab4dd_>(void)
0x1800142a5  nop
0x1800142a6  lea     rcx, [rsp+0A8h+var_70]
0x1800142ab  call    ??1?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x1800142b0  mov     eax, [rsp+0A8h+var_50]
0x1800142b4  jmp     loc_1800144F6
0x1800142b9  xor     eax, eax
0x1800142bb  test    eax, eax
0x1800142bd  jnz     loc_18001422E
0x1800142c3  mov     [rsp+0A8h+var_4C], 0
0x1800142cb  lea     rcx, [rsp+0A8h+var_70]
0x1800142d0  call    ?get@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEBAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::get(void)
0x1800142d5  lea     rcx, [rsp+0A8h+var_4C]
0x1800142da  mov     qword ptr [rsp+0A8h+ReturnLength], rcx; int
0x1800142df  mov     r9d, 4; TokenInformationLength
0x1800142e5  lea     r8, [rsp+0A8h+var_64+4]; TokenInformation
0x1800142ea  mov     edx, 1Dh; TokenInformationClass
0x1800142ef  mov     rcx, rax; TokenHandle
0x1800142f2  call    cs:__imp_GetTokenInformation
0x1800142f8  mov     ecx, eax
0x1800142fa  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x1800142ff  mov     [rsp+0A8h+var_48], eax
0x180014303  cmp     [rsp+0A8h+var_48], 0
0x180014308  jnz     short loc_180014348
0x18001430a  mov     rax, [rsp+0A8h]
0x180014312  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\docking\\virtualinpu"...
0x180014319  mov     edx, 46h ; 'F'; void *
0x18001431e  mov     rcx, rax; this
0x180014321  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180014326  mov     [rsp+0A8h+var_44], eax
0x18001432a  lea     rcx, [rsp+0A8h+var_74]
0x18001432f  call    ??1?$ScopeExitFn@V_lambda_fa82d6765b4dbbc65aa6b3636f8ab4dd_@@@details@wil@@QEAA@XZ; wil::details::ScopeExitFn<_lambda_fa82d6765b4dbbc65aa6b3636f8ab4dd_>::~ScopeExitFn<_lambda_fa82d6765b4dbbc65aa6b3636f8ab4dd_>(void)
0x180014334  nop
0x180014335  lea     rcx, [rsp+0A8h+var_70]
0x18001433a  call    ??1?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x18001433f  mov     eax, [rsp+0A8h+var_44]
0x180014343  jmp     loc_1800144F6
0x180014348  xor     eax, eax
0x18001434a  test    eax, eax
0x18001434c  jnz     loc_1800142CB
0x180014352  lea     rcx, [rsp+0A8h+var_74]
0x180014357  call    ??1?$ScopeExitFn@V_lambda_fa82d6765b4dbbc65aa6b3636f8ab4dd_@@@details@wil@@QEAA@XZ; wil::details::ScopeExitFn<_lambda_fa82d6765b4dbbc65aa6b3636f8ab4dd_>::~ScopeExitFn<_lambda_fa82d6765b4dbbc65aa6b3636f8ab4dd_>(void)
0x18001435c  nop
0x18001435d  cmp     dword ptr [rsp+0A8h+var_64+4], 0
0x180014362  jz      loc_18001449B
0x180014368  mov     byte ptr [rsp+0A8h+var_78], 0
0x18001436d  mov     rax, cs:off_18001E2D0; "inputInjection"
0x180014374  mov     [rsp+0A8h+var_20], rax
0x18001437c  lea     rcx, [rsp+0A8h+var_70]
0x180014381  call    ?get@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEBAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::get(void)
0x180014386  mov     [rsp+0A8h+var_18], rax
0x18001438e  lea     r8, [rsp+0A8h+var_78]; unsigned __int16 *
0x180014393  mov     rdx, [rsp+0A8h+var_20]; void *
0x18001439b  mov     rcx, [rsp+0A8h+var_18]; this
0x1800143a3  call    ?CheckCapabilityFromImpersonationToken@CallerIdentity@@YAJPEAXPEBGPEA_N@Z; CallerIdentity::CheckCapabilityFromImpersonationToken(void *,ushort const *,bool *)
0x1800143a8  mov     ecx, eax
0x1800143aa  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x1800143af  mov     [rsp+0A8h+var_5C], eax
0x1800143b3  cmp     [rsp+0A8h+var_5C], 0
0x1800143b8  jge     short loc_180014405
0x1800143ba  mov     eax, [rsp+0A8h+var_5C]
0x1800143be  mov     dword ptr [rsp+0A8h+var_58], eax
0x1800143c2  mov     rax, [rsp+0A8h]
0x1800143ca  mov     r9d, dword ptr [rsp+0A8h+var_58]; char *
0x1800143cf  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\docking\\virtualinpu"...
0x1800143d6  mov     edx, 4Dh ; 'M'; void *
0x1800143db  mov     rcx, rax; this
0x1800143de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800143e3  nop
0x1800143e4  mov     eax, dword ptr [rsp+0A8h+var_58]
0x1800143e8  mov     [rsp+0A8h+var_40], eax
0x1800143ec  lea     rcx, [rsp+0A8h+var_70]
0x1800143f1  call    ??1?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x1800143f6  mov     eax, [rsp+0A8h+var_40]
0x1800143fa  jmp     loc_1800144F6
0x1800143ff  xor     eax, eax
0x180014401  test    eax, eax
0x180014403  jnz     short loc_1800143BA
0x180014405  xor     eax, eax
0x180014407  test    eax, eax
0x180014409  jnz     loc_18001436D
0x18001440f  mov     cl, byte ptr [rsp+0A8h+var_78]
0x180014413  call    ??$verify_bool@_N$0A@@wil@@YA_N_N@Z; wil::verify_bool<bool,0>(bool)
0x180014418  movzx   eax, al
0x18001441b  test    eax, eax
0x18001441d  jnz     short loc_180014426
0x18001441f  mov     byte ptr [rsp+0A8h+var_78+1], 1
0x180014424  jmp     short loc_18001442B
0x180014426  mov     byte ptr [rsp+0A8h+var_78+1], 0
0x18001442b  mov     cl, byte ptr [rsp+0A8h+var_78+1]
0x18001442f  call    ??$verify_bool@_N$0A@@wil@@YA_N_N@Z; wil::verify_bool<bool,0>(bool)
0x180014434  movzx   eax, al
0x180014437  test    eax, eax
0x180014439  jz      short loc_180014491
0x18001443b  mov     ecx, 80070005h
0x180014440  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x180014445  mov     [rsp+0A8h+var_38], eax
0x180014449  xor     eax, eax
0x18001444b  cmp     eax, 1
0x18001444e  jz      short loc_180014473
0x180014450  mov     rax, [rsp+0A8h]
0x180014458  mov     r9d, 80070005h; char *
0x18001445e  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\docking\\virtualinpu"...
0x180014465  mov     edx, 4Eh ; 'N'; void *
0x18001446a  mov     rcx, rax; this
0x18001446d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014472  nop
0x180014473  mov     [rsp+0A8h+var_3C], 80070005h
0x18001447b  lea     rcx, [rsp+0A8h+var_70]
0x180014480  call    ??1?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x180014485  mov     eax, [rsp+0A8h+var_3C]
0x180014489  jmp     short loc_1800144F6
0x18001448b  xor     eax, eax
0x18001448d  test    eax, eax
0x18001448f  jnz     short loc_18001443B
0x180014491  xor     eax, eax
0x180014493  test    eax, eax
0x180014495  jnz     loc_18001440F
0x18001449b  lea     rcx, [rsp+0A8h+var_70]
0x1800144a0  call    ??1?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::~unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>(void)
0x1800144a5  nop
0x1800144a6  jmp     short loc_1800144F4
0x1800144a8  cmp     [rsp+0A8h+var_68], 80010117h
0x1800144b0  jz      short loc_1800144F4
0x1800144b2  mov     ecx, [rsp+0A8h+var_68]
0x1800144b6  call    ??$verify_BOOL@H@wil@@YAHH@Z; wil::verify_BOOL<int>(int)
0x1800144bb  mov     dword ptr [rsp+0A8h+var_64], eax
0x1800144bf  cmp     dword ptr [rsp+0A8h+var_64], 0
0x1800144c4  jge     short loc_1800144E8
0x1800144c6  mov     rax, [rsp+0A8h]
0x1800144ce  mov     r9d, dword ptr [rsp+0A8h+var_64]; char *
0x1800144d3  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\docking\\virtualinpu"...
0x1800144da  mov     edx, 54h ; 'T'; void *
0x1800144df  mov     rcx, rax; this
0x1800144e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800144e7  nop
0x1800144e8  mov     eax, dword ptr [rsp+0A8h+var_64]
0x1800144ec  jmp     short loc_1800144F6
0x1800144ee  xor     eax, eax
0x1800144f0  test    eax, eax
0x1800144f2  jnz     short loc_1800144B2
0x1800144f4  xor     eax, eax
0x1800144f6  add     rsp, 0A0h
0x1800144fd  pop     rdi
0x1800144fe  retn
```
