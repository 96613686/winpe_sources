# RetailDemoStartup::StartupAppManager::EnsurePackageIsRegistered(void)

- ea: `0x18004449c`
- end: `0x1800445c9`
- name: `?EnsurePackageIsRegistered@StartupAppManager@RetailDemoStartup@@AEAAJXZ`
- size: `301`
- prototype: `__int64 __fastcall(RetailDemoStartup::StartupAppManager *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180045828`

## callees

- `0x180003390`
- `0x180008bbc`
- `0x18000aa7c`
- `0x18001092c`
- `0x18001bf68`
- `0x18002666c`
- `0x180040694`
- `0x180042e88`
- `0x18004449c`
- `0x180050010`

## import_xrefs

- `api-ms-win-appmodel-runtime-internal-l1-1-4!GetEffectivePackageStatusForUserSid` at `0x1800444ce`
- `api-ms-win-appmodel-runtime-internal-l1-1-4!GetEffectivePackageStatusForUserSid` at `0x1800444ce`

## string_xrefs

- `0x1800444df`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\startupappmanager.cpp`
- `0x18004458b`: `pcshell\shell\retaildemo\desktoptaskfactory\retaildemouseragent\service\startupappmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
int __fastcall RetailDemoStartup::StartupAppManager::EnsurePackageIsRegistered(
        RetailDemoStartup::StartupAppManager *this)
{
  __int64 v2; // rax
  unsigned int EffectivePackageStatusForUserSid; // eax
  __int64 v5; // r8
  int v6; // eax
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD); // rbx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // [rsp+20h] [rbp-48h] BYREF
  __int64 v17; // [rsp+28h] [rbp-40h] BYREF
  __int64 v18; // [rsp+30h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-30h] BYREF
  __int64 v20; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  v16 = 0;
  v2 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this);
  EffectivePackageStatusForUserSid = GetEffectivePackageStatusForUserSid(0, v2, &v16);
  if ( EffectivePackageStatusForUserSid )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x2D,
             (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\startupappmanager.cpp",
             (const char *)EffectivePackageStatusForUserSid,
             v16);
  if ( (v16 & 0x400800) != 0 )
  {
    v17 = 0;
    v20 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Management.Deployment.Internal.PackageManagerInternal",
      0x3Eu,
      0x3Du);
    v6 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(
           v20,
           &v17,
           v5);
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 51;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"pcshell\\shell\\retaildemo\\desktoptaskfactory\\retaildemouseragent\\service\\startupappmanager.cpp",
        (const char *)(unsigned int)v6,
        v16);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17, v14, v15);
      return v7;
    }
    v9 = v17;
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v17 + 264LL);
    v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(this);
    v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v18);
    v6 = v10(v9, *(_QWORD *)(v11 + 24));
    v7 = v6;
    if ( v6 < 0 )
    {
      v8 = 52;
      goto LABEL_8;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17, v12, v13);
  }
  return 0;
}

```

## disassembly

```asm
0x18004449c  push    rbp
0x18004449e  push    rbx
0x18004449f  push    rsi
0x1800444a0  push    rdi
0x1800444a1  mov     rbp, rsp
0x1800444a4  sub     rsp, 68h
0x1800444a8  mov     rax, cs:__security_cookie
0x1800444af  xor     rax, rsp
0x1800444b2  mov     [rbp+var_10], rax
0x1800444b6  mov     rsi, rcx
0x1800444b9  mov     [rbp+var_48], 0
0x1800444c0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800444c5  lea     r8, [rbp+var_48]
0x1800444c9  mov     rdx, rax
0x1800444cc  xor     ecx, ecx
0x1800444ce  call    cs:__imp_GetEffectivePackageStatusForUserSid
0x1800444d4  test    eax, eax
0x1800444d6  jz      short loc_1800444F5
0x1800444d8  mov     rcx, [rbp+20h]; this
0x1800444dc  mov     r9d, eax; char *
0x1800444df  lea     r8, aPcshellShellRe_16; "pcshell\\shell\\retaildemo\\desktoptask"...
0x1800444e6  mov     edx, 2Dh ; '-'; void *
0x1800444eb  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800444f0  jmp     loc_1800445B4
0x1800444f5  test    [rbp+var_48], 400800h
0x1800444fc  jz      loc_1800445B2
0x180044502  mov     [rbp+var_40], 0
0x18004450a  mov     [rbp+var_18], 0
0x180044512  mov     r9d, 3Dh ; '='; unsigned int
0x180044518  lea     r8d, [r9+1]; unsigned int
0x18004451c  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_Internal_PackageManagerInternal@@3QBGB; "Windows.Management.Deployment.Internal."...
0x180044523  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x180044527  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004452c  lea     rdx, [rbp+var_40]
0x180044530  mov     rcx, [rbp+var_18]
0x180044534  call    ??$ActivateInstance@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>)
0x180044539  mov     ebx, eax
0x18004453b  test    eax, eax
0x18004453d  jns     short loc_180044546
0x18004453f  mov     edx, 33h ; '3'
0x180044544  jmp     short loc_180044588
0x180044546  mov     rdi, [rbp+var_40]
0x18004454a  mov     rax, [rdi]
0x18004454d  mov     rbx, [rax+108h]
0x180044554  mov     rcx, rsi
0x180044557  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004455c  mov     [rbp+var_38], rax
0x180044560  lea     rdx, [rbp+var_38]
0x180044564  lea     rcx, [rbp+hstringHeader]
0x180044568  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18004456d  nop
0x18004456e  mov     rdx, [rax+18h]
0x180044572  mov     rcx, rdi
0x180044575  mov     rax, rbx
0x180044578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004457d  mov     ebx, eax
0x18004457f  test    eax, eax
0x180044581  jns     short loc_1800445A9
0x180044583  mov     edx, 34h ; '4'; void *
0x180044588  mov     r9d, eax; char *
0x18004458b  lea     r8, aPcshellShellRe_16; "pcshell\\shell\\retaildemo\\desktoptask"...
0x180044592  mov     rcx, [rbp+20h]; this
0x180044596  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004459b  nop
0x18004459c  lea     rcx, [rbp+var_40]
0x1800445a0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800445a5  mov     eax, ebx
0x1800445a7  jmp     short loc_1800445B4
0x1800445a9  lea     rcx, [rbp+var_40]
0x1800445ad  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800445b2  xor     eax, eax
0x1800445b4  mov     rcx, [rbp+var_10]
0x1800445b8  xor     rcx, rsp; StackCookie
0x1800445bb  call    __security_check_cookie
0x1800445c0  add     rsp, 68h
0x1800445c4  pop     rdi
0x1800445c5  pop     rsi
0x1800445c6  pop     rbx
0x1800445c7  pop     rbp
0x1800445c8  retn
```
