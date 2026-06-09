# OSIntegration::DEH::Internal::CustomInstallExecution::LoadFromStateRepository(void)

- ea: `0x140009cd8`
- end: `0x140009fd4`
- name: `?LoadFromStateRepository@CustomInstallExecution@Internal@DEH@OSIntegration@@IEAAXXZ`
- size: `764`
- prototype: `void __fastcall(PCWSTR *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000a8a8`

## callees

- `0x14000367c`
- `0x140003f8c`
- `0x140007d78`
- `0x140007e9c`
- `0x1400083f4`
- `0x140008af0`
- `0x140009448`
- `0x1400095e4`
- `0x1400098dc`
- `0x140009918`
- `0x140009cd8`
- `0x14000b8c0`
- `0x14000e61c`
- `0x14000f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140009d5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140009d5d`

## string_xrefs

- `0x140009d45`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009d7a`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009dd8`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009e2e`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009f67`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009f7c`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
void __fastcall OSIntegration::DEH::Internal::CustomInstallExecution::LoadFromStateRepository(PCWSTR *this)
{
  __int64 v2; // rax
  int v3; // eax
  const unsigned __int16 *StringRawBuffer; // rax
  int v5; // eax
  __int64 v6; // rsi
  __int64 (__fastcall *v7)(__int64, _DWORD **); // rdi
  int v8; // eax
  __int64 v9; // rsi
  __int64 (__fastcall *v10)(__int64, _DWORD *, _QWORD, PCWSTR); // rdi
  int v11; // eax
  int i; // eax
  __int64 (__fastcall *v13)(_DWORD *, _QWORD, struct Windows::Internal::StateRepository::ICustomInstallWork **); // rbx
  int v14; // eax
  _DWORD *v15; // rdi
  __int64 v16; // rsi
  __int64 (__fastcall *v17)(__int64, __int64, _QWORD, PCWSTR); // rdi
  int v18; // eax
  int v19; // [rsp+20h] [rbp-50h]
  __int64 v20; // [rsp+30h] [rbp-40h] BYREF
  _DWORD *v21; // [rsp+38h] [rbp-38h]
  unsigned int v22; // [rsp+40h] [rbp-30h]
  struct Windows::Internal::StateRepository::ICustomInstallWork *v23; // [rsp+48h] [rbp-28h] BYREF
  char v24[8]; // [rsp+50h] [rbp-20h] BYREF
  int v25; // [rsp+58h] [rbp-18h]
  char v26[16]; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  _DWORD *v28; // [rsp+A0h] [rbp+30h] BYREF
  _DWORD *v29; // [rsp+A8h] [rbp+38h] BYREF
  HSTRING string; // [rsp+B0h] [rbp+40h] BYREF
  __int64 *v31; // [rsp+B8h] [rbp+48h] BYREF

  v20 = 0;
  OSIntegration::DEH::Internal::CustomInstallExecution::GetPackageByPackageFullName(this[1]);
  v31 = 0;
  OSIntegration::DEH::Internal::CustomInstallExecution::GetPackageLocationForPackage(0, &v31);
  string = 0;
  v2 = *v31;
  string = 0;
  v3 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v2 + 88))(v31, &string);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1AD,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
      (const char *)(unsigned int)v3,
      v19);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v5 = Common::StringBuffer::SetValueFromString((Common::StringBuffer *)(this + 3), StringRawBuffer);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1AE,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
      (const char *)(unsigned int)v5,
      v19);
  v28 = 0;
  if ( *((_BYTE *)this + 88) )
  {
    v29 = 0;
    v6 = OSIntegration::DEH::Internal::SRStatics::s_userStatics;
    v7 = *(__int64 (__fastcall **)(__int64, _DWORD **))(*(_QWORD *)OSIntegration::DEH::Internal::SRStatics::s_userStatics
                                                      + 104LL);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v29);
    v8 = v7(v6, &v29);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1B4,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)v8,
        v19);
    v9 = OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics;
    v10 = *(__int64 (__fastcall **)(__int64, _DWORD *, _QWORD, PCWSTR))(*(_QWORD *)OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics
                                                                      + 200LL);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v28);
    v11 = v10(v9, v29, 0, this[10]);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1B6,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)v11,
        (int)&v28);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v29);
  }
  else
  {
    v16 = OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics;
    v17 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, PCWSTR))(*(_QWORD *)OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics
                                                                     + 200LL);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v28);
    v18 = v17(v16, OSIntegration::DEH::Internal::SRStatics::s_perMachineUser, 0, this[10]);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1BB,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)v18,
        (int)&v28);
  }
  v29 = v28;
  v21 = v28;
  v22 = 0;
  v23 = 0;
  wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::CustomInstallWork *>,wil::err_exception_policy>::end(
    &v29,
    v24);
  for ( i = 0; i != v25; i = ++v22 )
  {
    v13 = *(__int64 (__fastcall **)(_DWORD *, _QWORD, struct Windows::Internal::StateRepository::ICustomInstallWork **))(*(_QWORD *)v21 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v23);
    v14 = v13(v21, v22, &v23);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v14,
        (int)&v28);
    v15 = operator new(0x68u);
    memset_0(v15, 0, 0x68u);
    v15[18] = -1;
    v29 = v15;
    OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::LoadFromCustomInstallWork(
      (OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *)v15,
      v23);
    if ( (int)Common::Array<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::NoKey>>::EnsureCapacity(
                this + 6,
                (char *)this[8] + 1) >= 0 )
    {
      *(_QWORD *)&this[6][4 * (_QWORD)this[8]] = v15;
      this[8] = (PCWSTR)((char *)this[8] + 1);
    }
    Common::AutoPtrDeallocate<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>(0);
  }
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(v26);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v23);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v28);
  wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(&string);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v31);
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v20);
}

```

## disassembly

```asm
0x140009cd8  push    rbp
0x140009cda  push    rbx
0x140009cdb  push    rsi
0x140009cdc  push    rdi
0x140009cdd  push    r14
0x140009cdf  mov     rbp, rsp
0x140009ce2  sub     rsp, 70h
0x140009ce6  mov     r14, rcx
0x140009ce9  mov     [rbp+var_40], 0
0x140009cf1  lea     rdx, [rbp+var_40]
0x140009cf5  mov     rcx, [rcx+8]; sourceString
0x140009cf9  call    ?GetPackageByPackageFullName@CustomInstallExecution@Internal@DEH@OSIntegration@@KAXPEBGAEAV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z; OSIntegration::DEH::Internal::CustomInstallExecution::GetPackageByPackageFullName(ushort const *,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> &)
0x140009cfe  mov     [rbp+arg_18], 0
0x140009d06  lea     rdx, [rbp+arg_18]
0x140009d0a  mov     rbx, [rbp+var_40]
0x140009d0e  mov     rcx, rbx
0x140009d11  call    ?GetPackageLocationForPackage@CustomInstallExecution@Internal@DEH@OSIntegration@@KAXPEAUIPackage@StateRepository@2Windows@@AEAV?$ComPtr@UIPackageLocation@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z; OSIntegration::DEH::Internal::CustomInstallExecution::GetPackageLocationForPackage(Windows::Internal::StateRepository::IPackage *,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocation> &)
0x140009d16  mov     [rbp+string], 0
0x140009d1e  mov     rcx, [rbp+arg_18]
0x140009d22  mov     rax, [rcx]
0x140009d25  mov     [rbp+string], 0
0x140009d2d  lea     rdx, [rbp+string]
0x140009d31  mov     rax, [rax+58h]
0x140009d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009d3a  mov     rcx, [rbp+28h]; this
0x140009d3e  test    eax, eax
0x140009d40  jns     short loc_140009D57
0x140009d42  mov     r9d, eax; char *
0x140009d45  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009d4c  mov     edx, 1ADh; void *
0x140009d51  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009d57  xor     edx, edx; length
0x140009d59  mov     rcx, [rbp+string]; string
0x140009d5d  call    cs:__imp_WindowsGetStringRawBuffer
0x140009d63  lea     rcx, [r14+18h]; this
0x140009d67  mov     rdx, rax; unsigned __int16 *
0x140009d6a  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x140009d6f  mov     rcx, [rbp+28h]; this
0x140009d73  test    eax, eax
0x140009d75  jns     short loc_140009D8C
0x140009d77  mov     r9d, eax; char *
0x140009d7a  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009d81  mov     edx, 1AEh; void *
0x140009d86  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009d8c  mov     [rbp+arg_0], 0
0x140009d94  cmp     byte ptr [r14+58h], 0
0x140009d99  jz      loc_140009F1C
0x140009d9f  mov     [rbp+arg_8], 0
0x140009da7  mov     rsi, cs:?s_userStatics@SRStatics@Internal@DEH@OSIntegration@@1V?$ComPtr@UIUserStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUserStatics> OSIntegration::DEH::Internal::SRStatics::s_userStatics
0x140009dae  mov     rax, [rsi]
0x140009db1  mov     rdi, [rax+68h]
0x140009db5  lea     rcx, [rbp+arg_8]
0x140009db9  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x140009dbe  lea     rdx, [rbp+arg_8]
0x140009dc2  mov     rcx, rsi
0x140009dc5  mov     rax, rdi
0x140009dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009dcd  mov     rcx, [rbp+28h]; this
0x140009dd1  test    eax, eax
0x140009dd3  jns     short loc_140009DEA
0x140009dd5  mov     r9d, eax; char *
0x140009dd8  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009ddf  mov     edx, 1B4h; void *
0x140009de4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009dea  mov     rsi, cs:?s_customInstallWorkStatics@SRStatics@Internal@DEH@OSIntegration@@1V?$ComPtr@UICustomInstallWorkStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ICustomInstallWorkStatics> OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics
0x140009df1  mov     rax, [rsi]
0x140009df4  mov     rdi, [rax+0C8h]
0x140009dfb  lea     rcx, [rbp+arg_0]
0x140009dff  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x140009e04  lea     rax, [rbp+arg_0]
0x140009e08  mov     qword ptr [rsp+70h+var_50], rax; int
0x140009e0d  mov     r9, [r14+50h]
0x140009e11  mov     r8, rbx
0x140009e14  mov     rdx, [rbp+arg_8]
0x140009e18  mov     rcx, rsi
0x140009e1b  mov     rax, rdi
0x140009e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e23  mov     rcx, [rbp+28h]; this
0x140009e27  test    eax, eax
0x140009e29  jns     short loc_140009E40
0x140009e2b  mov     r9d, eax; char *
0x140009e2e  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009e35  mov     edx, 1B6h; void *
0x140009e3a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009e40  lea     rcx, [rbp+arg_8]
0x140009e44  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x140009e49  mov     rax, [rbp+arg_0]
0x140009e4d  mov     [rbp+arg_8], rax
0x140009e51  mov     [rbp+var_38], rax
0x140009e55  mov     [rbp+var_30], 0
0x140009e5c  mov     [rbp+var_28], 0
0x140009e64  lea     rdx, [rbp+var_20]
0x140009e68  lea     rcx, [rbp+arg_8]
0x140009e6c  call    ?end@?$vector_range@U?$IVectorView@PEAVCustomInstallWork@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::CustomInstallWork *>,wil::err_exception_policy>::end(void)
0x140009e71  nop
0x140009e72  mov     esi, 68h ; 'h'
0x140009e77  mov     eax, [rbp+var_30]
0x140009e7a  cmp     eax, [rbp+var_18]
0x140009e7d  jz      loc_140009F8E
0x140009e83  mov     rdi, [rbp+var_38]
0x140009e87  mov     rax, [rdi]
0x140009e8a  mov     rbx, [rax+30h]
0x140009e8e  lea     rcx, [rbp+var_28]
0x140009e92  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x140009e97  lea     r8, [rbp+var_28]
0x140009e9b  mov     edx, [rbp+var_30]
0x140009e9e  mov     rcx, rdi
0x140009ea1  mov     rax, rbx
0x140009ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009ea9  mov     rcx, [rbp+28h]; this
0x140009ead  test    eax, eax
0x140009eaf  js      loc_140009F79
0x140009eb5  mov     rcx, rsi; Size
0x140009eb8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009ebd  mov     rdi, rax
0x140009ec0  mov     r8, rsi; Size
0x140009ec3  xor     edx, edx; Val
0x140009ec5  mov     rcx, rax; void *
0x140009ec8  call    memset_0
0x140009ecd  mov     dword ptr [rdi+48h], 0FFFFFFFFh
0x140009ed4  mov     [rbp+arg_8], rdi
0x140009ed8  mov     rdx, [rbp+var_28]; struct Windows::Internal::StateRepository::ICustomInstallWork *
0x140009edc  mov     rcx, rdi; this
0x140009edf  call    ?LoadFromCustomInstallWork@CustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@QEAAXPEAUICustomInstallWork@StateRepository@2Windows@@@Z; OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::LoadFromCustomInstallWork(Windows::Internal::StateRepository::ICustomInstallWork *)
0x140009ee4  mov     rdx, [r14+40h]
0x140009ee8  inc     rdx
0x140009eeb  lea     rcx, [r14+30h]
0x140009eef  call    ?EnsureCapacity@?$Array@VCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@V?$ContainerOperations@VCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@V1234@@Common@@VNoKey@6@V?$ContainerOperations@VNoKey@Common@@VCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@@6@V?$ArrayOperations@VCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@VNoKey@Common@@@6@@Common@@QEAAJ_K@Z; Common::Array<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::ContainerOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::NoKey,Common::ContainerOperations<Common::NoKey,OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>,Common::ArrayOperations<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper,Common::NoKey>>::EnsureCapacity(unsigned __int64)
0x140009ef4  test    eax, eax
0x140009ef6  js      short loc_140009F08
0x140009ef8  mov     rcx, [r14+40h]
0x140009efc  mov     rax, [r14+30h]
0x140009f00  mov     [rax+rcx*8], rdi
0x140009f04  inc     qword ptr [r14+40h]
0x140009f08  xor     ecx, ecx
0x140009f0a  call    ??$AutoPtrDeallocate@VCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@@Common@@YAXPEAVCustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@@Z; Common::AutoPtrDeallocate<OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper>(OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *)
0x140009f0f  mov     eax, [rbp+var_30]
0x140009f12  inc     eax
0x140009f14  mov     [rbp+var_30], eax
0x140009f17  jmp     loc_140009E7A
0x140009f1c  mov     rsi, cs:?s_customInstallWorkStatics@SRStatics@Internal@DEH@OSIntegration@@1V?$ComPtr@UICustomInstallWorkStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ICustomInstallWorkStatics> OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics
0x140009f23  mov     rax, [rsi]
0x140009f26  mov     rdi, [rax+0C8h]
0x140009f2d  lea     rcx, [rbp+arg_0]
0x140009f31  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x140009f36  lea     rax, [rbp+arg_0]
0x140009f3a  mov     qword ptr [rsp+70h+var_50], rax; int
0x140009f3f  mov     r9, [r14+50h]
0x140009f43  mov     r8, rbx
0x140009f46  mov     rdx, cs:?s_perMachineUser@SRStatics@Internal@DEH@OSIntegration@@1V?$ComPtr@UIUser@StateRepository@Internal@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IUser> OSIntegration::DEH::Internal::SRStatics::s_perMachineUser
0x140009f4d  mov     rcx, rsi
0x140009f50  mov     rax, rdi
0x140009f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009f58  mov     rcx, [rbp+28h]; this
0x140009f5c  test    eax, eax
0x140009f5e  jns     loc_140009E49
0x140009f64  mov     r9d, eax; char *
0x140009f67  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009f6e  mov     edx, 1BBh; void *
0x140009f73  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009f79  mov     r9d, eax; char *
0x140009f7c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140009f83  mov     edx, 1CBEh; void *
0x140009f88  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140009f8e  lea     rcx, [rbp+var_10]
0x140009f92  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x140009f97  nop
0x140009f98  lea     rcx, [rbp+var_28]
0x140009f9c  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x140009fa1  nop
0x140009fa2  lea     rcx, [rbp+arg_0]
0x140009fa6  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x140009fab  nop
0x140009fac  lea     rcx, [rbp+string]
0x140009fb0  call    ??1?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>(void)
0x140009fb5  nop
0x140009fb6  lea     rcx, [rbp+arg_18]
0x140009fba  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x140009fbf  nop
0x140009fc0  lea     rcx, [rbp+var_40]
0x140009fc4  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x140009fc9  add     rsp, 70h
0x140009fcd  pop     r14
0x140009fcf  pop     rdi
0x140009fd0  pop     rsi
0x140009fd1  pop     rbx
0x140009fd2  pop     rbp
0x140009fd3  retn
```
