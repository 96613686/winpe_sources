# SignInToMSATask::Execute(void)

- ea: `0x1800253f0`
- end: `0x180025720`
- name: `?Execute@SignInToMSATask@@MEAAXXZ`
- size: `816`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180003390`
- `0x180008bbc`
- `0x18001094c`
- `0x180022484`
- `0x180022ad8`
- `0x180024288`
- `0x1800246f0`
- `0x180024a48`
- `0x180024a5c`
- `0x180024a74`
- `0x180024acc`
- `0x1800253f0`
- `0x180025a0c`
- `0x180025bc0`
- `0x180025c4c`
- `0x180025cd8`
- `0x18002e5b8`
- `0x18002fc68`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180025570`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180025570`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002559c`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18002559c`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180025604`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180025604`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180025537`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180025537`

## string_xrefs

- `0x18002551b`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x1800255ba`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x180025615`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`
- `0x180025651`: `pcshell\shell\retaildemo\desktoptaskfactory\lib\signintomsatask.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall SignInToMSATask::Execute(HSTRING *this, __int64 a2)
{
  SignInToMSATask *v3; // rcx
  bool IsInternetConnected; // si
  __int64 (__fastcall ***v5)(); // rdx
  __int64 v6; // rax
  __int64 v7; // rcx
  int v8; // eax
  HANDLE v9; // rdi
  HSTRING v10; // rbx
  HANDLE CurrentProcess; // rax
  int Error; // eax
  unsigned int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rdx
  int v16; // eax
  __int64 (__fastcall ***v17)(); // rdx
  __int64 v18; // rdx
  __int64 v19; // r8
  SignInToMSATask *v20; // rcx
  int dwDesiredAccess; // [rsp+20h] [rbp-E0h]
  int dwDesiredAccessa; // [rsp+20h] [rbp-E0h]
  unsigned int dwDesiredAccessb; // [rsp+20h] [rbp-E0h]
  HSTRING v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  int Data; // [rsp+50h] [rbp-B0h] BYREF
  __int64 *v27; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpValueName; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpSubKey; // [rsp+68h] [rbp-98h] BYREF
  __int64 *v30; // [rsp+70h] [rbp-90h] BYREF
  HANDLE TargetHandle; // [rsp+78h] [rbp-88h] BYREF
  char v32; // [rsp+80h] [rbp-80h]
  _QWORD v33[2]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v34[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v35[24]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 (__fastcall **v36)(); // [rsp+D0h] [rbp-30h] BYREF
  __int128 v37; // [rsp+D8h] [rbp-28h]
  __int64 (__fastcall ***v38)(); // [rsp+108h] [rbp+8h]
  __int64 (__fastcall **v39)(); // [rsp+110h] [rbp+10h] BYREF
  __int128 v40; // [rsp+118h] [rbp+18h]
  __int64 (__fastcall ***v41)(); // [rsp+148h] [rbp+48h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]

  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_AutoMSA_and_ProvisioningAppFixes>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_RDX_AutoMSA_and_ProvisioningAppFixes>::GetImpl'::`2'::impl,
    a2);
  lpSubKey = L"Software\\Microsoft\\Windows\\CurrentVersion\\Policies\\System";
  lpValueName = L"NoConnectedUser";
  LOBYTE(v24) = 0;
  IsInternetConnected = SignInToMSATask::IsInternetConnected(v3);
  v38 = 0;
  v36 = off_180052988;
  v37 = *(_OWORD *)_lambda_6d98a26ab645bb601d6c6842c9556ef9_::_lambda_6d98a26ab645bb601d6c6842c9556ef9_(
                     (_lambda_6d98a26ab645bb601d6c6842c9556ef9_ *)v33,
                     &v24,
                     this);
  v38 = &v36;
  RetailDemoUtil::ExecuteAsDemoUser(&v36);
  if ( v38 )
  {
    v5 = &v36;
    LOBYTE(v5) = v38 != &v36;
    ((void (__fastcall *)(__int64 (__fastcall ***)(), __int64 (__fastcall ***)()))(*v38)[4])(v38, v5);
  }
  v6 = lambda_40a5eac435b028b9a69f9690193b14ae_::_lambda_40a5eac435b028b9a69f9690193b14ae_(
         v35,
         &v24,
         &lpSubKey,
         &lpValueName);
  wil::ScopeExit__lambda_40a5eac435b028b9a69f9690193b14ae___(v34, v6);
  if ( !(_BYTE)v24 && IsInternetConnected )
  {
    RetailDemoUtil::GetUserAgent(&v27, 0);
    HIDWORD(v24) = 0;
    v8 = (*(__int64 (__fastcall **)(__int64 *, char *))(*v27 + 112))(v27, (char *)&v24 + 4);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x54,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\signintomsatask.cpp",
        (const char *)(unsigned int)v8,
        dwDesiredAccess);
    v9 = OpenProcess(0x40u, 0, HIDWORD(v24));
    v33[0] = v9;
    v25 = 0;
    v30 = &v25;
    TargetHandle = 0;
    v32 = 1;
    v10 = this[6];
    if ( v10 )
      v10 = *(HSTRING *)v10;
    CurrentProcess = GetCurrentProcess();
    if ( DuplicateHandle(CurrentProcess, v10, v9, &TargetHandle, 0, 0, 2u) )
      Error = 0;
    else
      Error = ResultFromKnownLastError();
    if ( Error < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5A,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\signintomsatask.cpp",
        (const char *)(unsigned int)Error,
        dwDesiredAccessa);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&v30);
    Data = 0;
    v13 = RegSetKeyValueW(HKEY_LOCAL_MACHINE, lpSubKey, lpValueName, 4u, &Data, 4u);
    if ( v13 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x5D,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\signintomsatask.cpp",
        (const char *)v13,
        dwDesiredAccessb);
    v14 = *v27;
    v15 = v25;
    v25 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64 *, __int64))(v14 + 104))(v27, v15);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\lib\\signintomsatask.cpp",
        (const char *)(unsigned int)v16,
        dwDesiredAccessb);
    v41 = 0;
    v39 = off_180052958;
    v40 = *(_OWORD *)_lambda_6d98a26ab645bb601d6c6842c9556ef9_::_lambda_6d98a26ab645bb601d6c6842c9556ef9_(
                       (_lambda_6d98a26ab645bb601d6c6842c9556ef9_ *)&v30,
                       &v24,
                       this);
    v41 = &v39;
    RetailDemoUtil::ExecuteAsDemoUser(&v39);
    if ( v41 )
    {
      v17 = &v39;
      LOBYTE(v17) = v41 != &v39;
      ((void (__fastcall *)(__int64 (__fastcall ***)(), __int64 (__fastcall ***)()))(*v41)[4])(v41, v17);
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v25);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v33);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v27, v18, v19);
  }
  LOBYTE(v7) = IsInternetConnected;
  RetailDemo::Health::details::RetailDemoHealthTracker<1>::HandleEvent<6,bool,bool>(v7);
  SignInToMSATask::ReportMsaFunctioning(v20);
  wil::details::ScopeExitFn__lambda_40a5eac435b028b9a69f9690193b14ae___::_ScopeExitFn__lambda_40a5eac435b028b9a69f9690193b14ae___(v34);
}

```

## disassembly

```asm
0x1800253f0  mov     [rsp-8+arg_8], rbx
0x1800253f5  mov     [rsp-8+arg_10], rsi
0x1800253fa  push    rbp
0x1800253fb  push    rdi
0x1800253fc  push    r14
0x1800253fe  lea     rbp, [rsp-60h]
0x180025403  sub     rsp, 160h
0x18002540a  mov     rax, cs:__security_cookie
0x180025411  xor     rax, rsp
0x180025414  mov     [rbp+70h+var_20], rax
0x180025418  mov     r14, rcx
0x18002541b  mov     dl, 1
0x18002541d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RDX_AutoMSA_and_ProvisioningAppFixes@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_AutoMSA_and_ProvisioningAppFixes@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_AutoMSA_and_ProvisioningAppFixes> `wil::Feature<__WilFeatureTraits_Feature_RDX_AutoMSA_and_ProvisioningAppFixes>::GetImpl(void)'::`2'::impl
0x180025424  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_RDX_AutoMSA_and_ProvisioningAppFixes@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RDX_AutoMSA_and_ProvisioningAppFixes>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x180025429  lea     rax, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180025430  mov     [rsp+170h+lpSubKey], rax
0x180025435  lea     rax, aNoconnecteduse; "NoConnectedUser"
0x18002543c  mov     [rsp+170h+lpValueName], rax
0x180025441  mov     byte ptr [rsp+170h+var_130], 0
0x180025446  call    ?IsInternetConnected@SignInToMSATask@@AEAA_NXZ; SignInToMSATask::IsInternetConnected(void)
0x18002544b  mov     sil, al
0x18002544e  mov     [rbp+70h+var_68], 0
0x180025456  lea     rax, off_180052988
0x18002545d  mov     [rbp+70h+var_A0], rax
0x180025461  mov     r8, r14; HSTRING *
0x180025464  lea     rdx, [rsp+170h+var_130]; HSTRING *
0x180025469  lea     rcx, [rbp+70h+var_E8]; this
0x18002546d  call    ??0_lambda_6d98a26ab645bb601d6c6842c9556ef9_@@QEAA@AEAPEAUHSTRING__@@0@Z; _lambda_6d98a26ab645bb601d6c6842c9556ef9_::_lambda_6d98a26ab645bb601d6c6842c9556ef9_(HSTRING__ * &,HSTRING__ * &)
0x180025472  movups  xmm0, xmmword ptr [rax]
0x180025475  movdqu  [rbp+70h+var_98], xmm0
0x18002547a  lea     rax, [rbp+70h+var_A0]
0x18002547e  mov     [rbp+70h+var_68], rax
0x180025482  lea     rcx, [rbp+70h+var_A0]
0x180025486  call    ?ExecuteAsDemoUser@RetailDemoUtil@@YAXAEBV?$function@$$A6AXXZ@std@@@Z; RetailDemoUtil::ExecuteAsDemoUser(std::function<void (void)> const &)
0x18002548b  nop
0x18002548c  mov     rcx, [rbp+70h+var_68]
0x180025490  test    rcx, rcx
0x180025493  jz      short loc_1800254AB
0x180025495  mov     rax, [rcx]
0x180025498  lea     rdx, [rbp+70h+var_A0]
0x18002549c  cmp     rcx, rdx
0x18002549f  setnz   dl
0x1800254a2  mov     rax, [rax+20h]
0x1800254a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254ab  lea     r9, [rsp+170h+lpValueName]
0x1800254b0  lea     r8, [rsp+170h+lpSubKey]
0x1800254b5  lea     rdx, [rsp+170h+var_130]
0x1800254ba  lea     rcx, [rbp+70h+var_B8]
0x1800254be  call    _lambda_40a5eac435b028b9a69f9690193b14ae____lambda_40a5eac435b028b9a69f9690193b14ae_
0x1800254c3  mov     rdx, rax
0x1800254c6  lea     rcx, [rbp+70h+var_D8]
0x1800254ca  call    wil__ScopeExit__lambda_40a5eac435b028b9a69f9690193b14ae___
0x1800254cf  nop
0x1800254d0  mov     dl, byte ptr [rsp+170h+var_130]
0x1800254d4  test    dl, dl
0x1800254d6  jnz     loc_1800256E5
0x1800254dc  test    sil, sil
0x1800254df  jz      loc_1800256E5
0x1800254e5  xor     edx, edx
0x1800254e7  lea     rcx, [rsp+170h+var_118]
0x1800254ec  call    ?GetUserAgent@RetailDemoUtil@@YA?AV?$ComPtr@UIRetailDemoUserAgent@@@WRL@Microsoft@@PEAUIServiceProvider@@@Z; RetailDemoUtil::GetUserAgent(IServiceProvider *)
0x1800254f1  nop
0x1800254f2  mov     dword ptr [rsp+170h+var_130+4], 0
0x1800254fa  mov     rcx, [rsp+170h+var_118]
0x1800254ff  mov     rax, [rcx]
0x180025502  lea     rdx, [rsp+170h+var_130+4]
0x180025507  mov     rax, [rax+70h]
0x18002550b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025510  mov     rcx, [rbp+78h]; this
0x180025514  test    eax, eax
0x180025516  jns     short loc_18002552D
0x180025518  mov     r9d, eax; char *
0x18002551b  lea     r8, aPcshellShellRe_18; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180025522  mov     edx, 54h ; 'T'; void *
0x180025527  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002552d  mov     r8d, dword ptr [rsp+170h+var_130+4]; dwProcessId
0x180025532  xor     edx, edx; bInheritHandle
0x180025534  lea     ecx, [rdx+40h]; dwDesiredAccess
0x180025537  call    cs:__imp_OpenProcess
0x18002553d  mov     rdi, rax
0x180025540  mov     [rbp+70h+var_E8], rax
0x180025544  mov     [rsp+170h+var_128], 0
0x18002554d  lea     rax, [rsp+170h+var_128]
0x180025552  mov     [rsp+170h+var_100], rax
0x180025557  mov     [rsp+170h+TargetHandle], 0
0x180025560  mov     [rbp+70h+var_F0], 1
0x180025564  mov     rbx, [r14+30h]
0x180025568  test    rbx, rbx
0x18002556b  jz      short loc_180025570
0x18002556d  mov     rbx, [rbx]
0x180025570  call    cs:__imp_GetCurrentProcess
0x180025576  mov     [rsp+170h+dwOptions], 2; dwOptions
0x18002557e  mov     [rsp+170h+bInheritHandle], 0; bInheritHandle
0x180025586  mov     [rsp+170h+dwDesiredAccess], 0; int
0x18002558e  lea     r9, [rsp+170h+TargetHandle]; lpTargetHandle
0x180025593  mov     r8, rdi; hTargetProcessHandle
0x180025596  mov     rdx, rbx; hSourceHandle
0x180025599  mov     rcx, rax; hSourceProcessHandle
0x18002559c  call    cs:__imp_DuplicateHandle
0x1800255a2  test    eax, eax
0x1800255a4  jz      short loc_1800255AA
0x1800255a6  xor     eax, eax
0x1800255a8  jmp     short loc_1800255AF
0x1800255aa  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800255af  mov     rcx, [rbp+78h]; this
0x1800255b3  test    eax, eax
0x1800255b5  jns     short loc_1800255CC
0x1800255b7  mov     r9d, eax; char *
0x1800255ba  lea     r8, aPcshellShellRe_18; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800255c1  mov     edx, 5Ah ; 'Z'; void *
0x1800255c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800255cc  lea     rcx, [rsp+170h+var_100]
0x1800255d1  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800255d6  mov     [rsp+170h+Data], 0
0x1800255de  mov     r9d, 4; dwType
0x1800255e4  mov     [rsp+170h+bInheritHandle], r9d; cbData
0x1800255e9  lea     rax, [rsp+170h+Data]
0x1800255ee  mov     qword ptr [rsp+170h+dwDesiredAccess], rax; int
0x1800255f3  mov     r8, [rsp+170h+lpValueName]; lpValueName
0x1800255f8  mov     rdx, [rsp+170h+lpSubKey]; lpSubKey
0x1800255fd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180025604  call    cs:__imp_RegSetKeyValueW
0x18002560a  mov     rcx, [rbp+78h]; this
0x18002560e  test    eax, eax
0x180025610  jz      short loc_180025627
0x180025612  mov     r9d, eax; char *
0x180025615  lea     r8, aPcshellShellRe_18; "pcshell\\shell\\retaildemo\\desktoptask"...
0x18002561c  mov     edx, 5Dh ; ']'; void *
0x180025621  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x180025627  mov     rcx, [rsp+170h+var_118]
0x18002562c  mov     rax, [rcx]
0x18002562f  mov     rdx, [rsp+170h+var_128]
0x180025634  mov     [rsp+170h+var_128], 0
0x18002563d  mov     rax, [rax+68h]
0x180025641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025646  mov     rcx, [rbp+78h]; this
0x18002564a  test    eax, eax
0x18002564c  jns     short loc_180025663
0x18002564e  mov     r9d, eax; char *
0x180025651  lea     r8, aPcshellShellRe_18; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180025658  mov     edx, 5Eh ; '^'; void *
0x18002565d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180025663  mov     [rbp+70h+var_28], 0
0x18002566b  lea     rax, off_180052958
0x180025672  mov     [rbp+70h+var_60], rax
0x180025676  mov     r8, r14; HSTRING *
0x180025679  lea     rdx, [rsp+170h+var_130]; HSTRING *
0x18002567e  lea     rcx, [rsp+170h+var_100]; this
0x180025683  call    ??0_lambda_6d98a26ab645bb601d6c6842c9556ef9_@@QEAA@AEAPEAUHSTRING__@@0@Z; _lambda_6d98a26ab645bb601d6c6842c9556ef9_::_lambda_6d98a26ab645bb601d6c6842c9556ef9_(HSTRING__ * &,HSTRING__ * &)
0x180025688  movups  xmm0, xmmword ptr [rax]
0x18002568b  movdqu  [rbp+70h+var_58], xmm0
0x180025690  lea     rax, [rbp+70h+var_60]
0x180025694  mov     [rbp+70h+var_28], rax
0x180025698  lea     rcx, [rbp+70h+var_60]
0x18002569c  call    ?ExecuteAsDemoUser@RetailDemoUtil@@YAXAEBV?$function@$$A6AXXZ@std@@@Z; RetailDemoUtil::ExecuteAsDemoUser(std::function<void (void)> const &)
0x1800256a1  nop
0x1800256a2  mov     rcx, [rbp+70h+var_28]
0x1800256a6  test    rcx, rcx
0x1800256a9  jz      short loc_1800256C2
0x1800256ab  mov     rax, [rcx]
0x1800256ae  lea     rdx, [rbp+70h+var_60]
0x1800256b2  cmp     rcx, rdx
0x1800256b5  setnz   dl
0x1800256b8  mov     rax, [rax+20h]
0x1800256bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256c1  nop
0x1800256c2  lea     rcx, [rsp+170h+var_128]
0x1800256c7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800256cc  nop
0x1800256cd  lea     rcx, [rbp+70h+var_E8]
0x1800256d1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800256d6  nop
0x1800256d7  lea     rcx, [rsp+170h+var_118]
0x1800256dc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800256e1  mov     dl, byte ptr [rsp+170h+var_130]
0x1800256e5  mov     cl, sil
0x1800256e8  call    ??$HandleEvent@$05_N_N@?$RetailDemoHealthTracker@$00@details@Health@RetailDemo@@SAX_N0@Z; RetailDemo::Health::details::RetailDemoHealthTracker<1>::HandleEvent<6,bool,bool>(bool,bool)
0x1800256ed  call    ?ReportMsaFunctioning@SignInToMSATask@@AEAAXXZ; SignInToMSATask::ReportMsaFunctioning(void)
0x1800256f2  nop
0x1800256f3  lea     rcx, [rbp+70h+var_D8]
0x1800256f7  call    wil__details__ScopeExitFn__lambda_40a5eac435b028b9a69f9690193b14ae______ScopeExitFn__lambda_40a5eac435b028b9a69f9690193b14ae___
0x1800256fc  mov     rcx, [rbp+70h+var_20]
0x180025700  xor     rcx, rsp; StackCookie
0x180025703  call    __security_check_cookie
0x180025708  lea     r11, [rsp+170h+var_10]
0x180025710  mov     rbx, [r11+28h]
0x180025714  mov     rsi, [r11+30h]
0x180025718  mov     rsp, r11
0x18002571b  pop     r14
0x18002571d  pop     rdi
0x18002571e  pop     rbp
0x18002571f  retn
```
