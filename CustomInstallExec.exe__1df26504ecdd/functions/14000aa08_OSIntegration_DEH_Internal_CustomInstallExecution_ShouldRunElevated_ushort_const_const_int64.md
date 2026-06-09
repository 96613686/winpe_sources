# OSIntegration::DEH::Internal::CustomInstallExecution::ShouldRunElevated(ushort const * const,__int64)

- ea: `0x14000aa08`
- end: `0x14000aaf8`
- name: `?ShouldRunElevated@CustomInstallExecution@Internal@DEH@OSIntegration@@SA_NQEBG_J@Z`
- size: `240`
- prototype: `bool __fastcall(PCWSTR sourceString, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000d884`

## callees

- `0x140007d78`
- `0x140009448`
- `0x140009758`
- `0x1400098dc`
- `0x14000aa08`
- `0x14000f010`

## string_xrefs

- `0x14000aa85`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x14000aabd`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`

## pseudocode

```c
bool __fastcall OSIntegration::DEH::Internal::CustomInstallExecution::ShouldRunElevated(
        PCWSTR sourceString,
        __int64 a2)
{
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64, _QWORD, __int64); // rbx
  int v6; // eax
  int v7; // eax
  bool v8; // bl
  __int64 v10; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  int v12; // [rsp+70h] [rbp+30h] BYREF
  __int64 v13; // [rsp+78h] [rbp+38h] BYREF

  OSIntegration::DEH::Internal::SRStatics::Initialize();
  v10 = 0;
  OSIntegration::DEH::Internal::CustomInstallExecution::GetPackageByPackageFullName(sourceString);
  v13 = 0;
  v4 = OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics;
  v5 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64))(*(_QWORD *)OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics
                                                                   + 200LL);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v13);
  v6 = v5(v4, OSIntegration::DEH::Internal::SRStatics::s_perMachineUser, 0, a2);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x19B,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
      (const char *)(unsigned int)v6,
      (int)&v13);
  v12 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v13 + 56LL))(v13, &v12);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x19E,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
      (const char *)(unsigned int)v7,
      (int)&v13);
  v8 = v12 != 0;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v13);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v10);
  return v8;
}

```

## disassembly

```asm
0x14000aa08  mov     [rsp-18h+arg_0], rbx
0x14000aa0d  push    rbp
0x14000aa0e  push    rsi
0x14000aa0f  push    rdi
0x14000aa10  mov     rbp, rsp
0x14000aa13  sub     rsp, 40h
0x14000aa17  mov     rsi, rdx
0x14000aa1a  mov     rbx, rcx
0x14000aa1d  call    ?Initialize@SRStatics@Internal@DEH@OSIntegration@@SAXXZ; OSIntegration::DEH::Internal::SRStatics::Initialize(void)
0x14000aa22  mov     [rbp+var_10], 0
0x14000aa2a  lea     rdx, [rbp+var_10]
0x14000aa2e  mov     rcx, rbx; sourceString
0x14000aa31  call    ?GetPackageByPackageFullName@CustomInstallExecution@Internal@DEH@OSIntegration@@KAXPEBGAEAV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z; OSIntegration::DEH::Internal::CustomInstallExecution::GetPackageByPackageFullName(ushort const *,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> &)
0x14000aa36  mov     [rbp+arg_18], 0
0x14000aa3e  mov     rdi, cs:?s_customInstallWorkStatics@SRStatics@Internal@DEH@OSIntegration@@1V?$ComPtr@UICustomInstallWorkStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ICustomInstallWorkStatics> OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics
0x14000aa45  mov     rax, [rdi]
0x14000aa48  mov     rbx, [rax+0C8h]
0x14000aa4f  lea     rcx, [rbp+arg_18]
0x14000aa53  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x14000aa58  lea     rax, [rbp+arg_18]
0x14000aa5c  mov     qword ptr [rsp+40h+var_20], rax; int
0x14000aa61  mov     r9, rsi
0x14000aa64  mov     r8, [rbp+var_10]
0x14000aa68  mov     rdx, cs:?s_perMachineUser@SRStatics@Internal@DEH@OSIntegration@@1V?$ComPtr@UIUser@StateRepository@Internal@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUser> OSIntegration::DEH::Internal::SRStatics::s_perMachineUser
0x14000aa6f  mov     rcx, rdi
0x14000aa72  mov     rax, rbx
0x14000aa75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa7a  mov     rcx, [rbp+18h]; this
0x14000aa7e  test    eax, eax
0x14000aa80  jns     short loc_14000AA97
0x14000aa82  mov     r9d, eax; char *
0x14000aa85  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x14000aa8c  mov     edx, 19Bh; void *
0x14000aa91  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000aa97  mov     [rbp+arg_10], 0
0x14000aa9e  mov     rcx, [rbp+arg_18]
0x14000aaa2  mov     rax, [rcx]
0x14000aaa5  lea     rdx, [rbp+arg_10]
0x14000aaa9  mov     rax, [rax+38h]
0x14000aaad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aab2  mov     rcx, [rbp+18h]; this
0x14000aab6  test    eax, eax
0x14000aab8  jns     short loc_14000AACF
0x14000aaba  mov     r9d, eax; char *
0x14000aabd  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x14000aac4  mov     edx, 19Eh; void *
0x14000aac9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000aacf  cmp     [rbp+arg_10], 0
0x14000aad3  setnbe  bl
0x14000aad6  lea     rcx, [rbp+arg_18]
0x14000aada  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x14000aadf  nop
0x14000aae0  lea     rcx, [rbp+var_10]
0x14000aae4  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x14000aae9  mov     al, bl
0x14000aaeb  mov     rbx, [rsp+40h+arg_0]
0x14000aaf0  add     rsp, 40h
0x14000aaf4  pop     rdi
0x14000aaf5  pop     rsi
0x14000aaf6  pop     rbp
0x14000aaf7  retn
```
