# OSIntegration::DEH::Internal::CustomInstallExecution::ClearPackageStatus(void)

- ea: `0x140008758`
- end: `0x1400088e5`
- name: `?ClearPackageStatus@CustomInstallExecution@Internal@DEH@OSIntegration@@IEAAXXZ`
- size: `397`
- prototype: `void __fastcall(OSIntegration::DEH::Internal::CustomInstallExecution *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000a8a8`

## callees

- `0x1400033b0`
- `0x140007d78`
- `0x140007dfc`
- `0x140007ebc`
- `0x14000872c`
- `0x140008758`
- `0x14000891c`
- `0x1400098dc`
- `0x14000b8a0`
- `0x14000f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400088af`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400088af`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1400088c2`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!UpdatePackageStatus` at `0x1400088c2`

## string_xrefs

- `0x1400087ca`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x14000883f`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x1400088d3`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`

## pseudocode

```c
void __fastcall OSIntegration::DEH::Internal::CustomInstallExecution::ClearPackageStatus(
        OSIntegration::DEH::Internal::CustomInstallExecution *this)
{
  int v2; // eax
  _QWORD *v3; // r14
  __int64 v4; // r15
  const WCHAR *v5; // rsi
  unsigned __int64 v6; // rbx
  unsigned int v7; // eax
  int v8; // eax
  unsigned int updated; // eax
  _QWORD *v10; // [rsp+20h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-28h] BYREF
  __int64 v12; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  if ( *((_BYTE *)this + 88) )
  {
    v10 = 0;
    v12 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Management.Deployment.Internal.PackageManagerInternal",
      0x3Eu,
      0x3Du);
    v2 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(
           v12,
           &v10);
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x203,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)v2,
        (int)v10);
    v3 = v10;
    v4 = *v10;
    v5 = (const WCHAR *)*((_QWORD *)this + 1);
    v12 = 0;
    v6 = -1;
    do
      ++v6;
    while ( v5[v6] );
    if ( v6 <= 0xFFFFFFFF )
    {
      v7 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v6);
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, v5, v7, v6);
      v8 = (*(__int64 (__fastcall **)(_QWORD *, __int64))(v4 + 176))(v3, v12);
      if ( v8 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x204,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
          (const char *)(unsigned int)v8,
          (int)v10);
      Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v10);
      goto LABEL_10;
    }
    RaiseException(0x80070216, 1u, 0, 0);
  }
  updated = UpdatePackageStatus(*((_QWORD *)this + 1), 0x1000000, 0);
  if ( updated )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x209,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
      (const char *)updated,
      (unsigned int)v10);
LABEL_10:
  v10 = (_QWORD *)*((_QWORD *)this + 1);
  *(GUID *)&hstringHeader.Reserved.Reserved1 = OSIntegration::DEH::Internal::TraceLoggingStatic::s_customInstallExecId;
  CASTraceProvider::ClearPackageStatus<_GUID,unsigned short *>(&hstringHeader, &v10);
}

```

## disassembly

```asm
0x140008758  mov     [rsp-28h+arg_8], rbx
0x14000875d  mov     [rsp-28h+arg_10], rsi
0x140008762  push    rbp
0x140008763  push    rdi
0x140008764  push    r12
0x140008766  push    r14
0x140008768  push    r15
0x14000876a  mov     rbp, rsp
0x14000876d  sub     rsp, 50h
0x140008771  mov     rax, cs:__security_cookie
0x140008778  xor     rax, rsp
0x14000877b  mov     [rbp+var_8], rax
0x14000877f  mov     rdi, rcx
0x140008782  xor     r12d, r12d
0x140008785  cmp     [rcx+58h], r12b
0x140008789  jz      loc_1400088B6
0x14000878f  mov     [rbp+var_30], r12
0x140008793  mov     [rbp+var_10], r12
0x140008797  lea     r9d, [r12+3Dh]; unsigned int
0x14000879c  lea     r8d, [r12+3Eh]; unsigned int
0x1400087a1  lea     rdx, ?RuntimeClass_Windows_Management_Deployment_Internal_PackageManagerInternal@@3QBGB; "Windows.Management.Deployment.Internal."...
0x1400087a8  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1400087ac  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1400087b1  nop
0x1400087b2  lea     rdx, [rbp+var_30]
0x1400087b6  mov     rcx, [rbp+var_10]
0x1400087ba  call    ??$ActivateInstance@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::Internal::IPackageManagerInternal>>)
0x1400087bf  mov     rcx, [rbp+28h]; this
0x1400087c3  test    eax, eax
0x1400087c5  jns     short loc_1400087DC
0x1400087c7  mov     r9d, eax; char *
0x1400087ca  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1400087d1  mov     edx, 203h; void *
0x1400087d6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400087dc  mov     r14, [rbp+var_30]
0x1400087e0  mov     r15, [r14]
0x1400087e3  mov     rsi, [rdi+8]
0x1400087e7  mov     [rbp+var_10], r12
0x1400087eb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400087ef  inc     rbx
0x1400087f2  cmp     [rsi+rbx*2], r12w
0x1400087f7  jnz     short loc_1400087EF
0x1400087f9  mov     eax, 0FFFFFFFFh
0x1400087fe  cmp     rbx, rax
0x140008801  ja      loc_1400088A0
0x140008807  mov     ecx, ebx; unsigned int
0x140008809  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x14000880e  mov     r9d, ebx; unsigned int
0x140008811  mov     r8d, eax; unsigned int
0x140008814  mov     rdx, rsi; sourceString
0x140008817  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x14000881b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140008820  nop
0x140008821  mov     rdx, [rbp+var_10]
0x140008825  mov     rcx, r14
0x140008828  mov     rax, [r15+0B0h]
0x14000882f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008834  mov     rcx, [rbp+28h]; this
0x140008838  test    eax, eax
0x14000883a  jns     short loc_140008851
0x14000883c  mov     r9d, eax; char *
0x14000883f  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140008846  mov     edx, 204h; void *
0x14000884b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140008851  lea     rcx, [rbp+var_30]
0x140008855  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x14000885a  mov     rax, [rdi+8]
0x14000885e  mov     [rbp+var_30], rax
0x140008862  movups  xmm0, xmmword ptr cs:?s_customInstallExecId@TraceLoggingStatic@Internal@DEH@OSIntegration@@0U_GUID@@A.Data1; _GUID OSIntegration::DEH::Internal::TraceLoggingStatic::s_customInstallExecId ...
0x140008869  movdqu  xmmword ptr [rbp+hstringHeader.Reserved], xmm0
0x14000886e  lea     rdx, [rbp+var_30]
0x140008872  lea     rcx, [rbp+hstringHeader]
0x140008876  call    ??$ClearPackageStatus@U_GUID@@PEAG@CASTraceProvider@@SAX$$QEAU_GUID@@$$QEAPEAG@Z; CASTraceProvider::ClearPackageStatus<_GUID,ushort *>(_GUID &&,ushort * &&)
0x14000887b  mov     rcx, [rbp+var_8]
0x14000887f  xor     rcx, rsp; StackCookie
0x140008882  call    __security_check_cookie
0x140008887  lea     r11, [rsp+50h+var_s0]
0x14000888c  mov     rbx, [r11+38h]
0x140008890  mov     rsi, [r11+40h]
0x140008894  mov     rsp, r11
0x140008897  pop     r15
0x140008899  pop     r14
0x14000889b  pop     r12
0x14000889d  pop     rdi
0x14000889e  pop     rbp
0x14000889f  retn
0x1400088a0  xor     r9d, r9d; lpArguments
0x1400088a3  xor     r8d, r8d; nNumberOfArguments
0x1400088a6  lea     edx, [r9+1]; dwExceptionFlags
0x1400088aa  mov     ecx, 80070216h; dwExceptionCode
0x1400088af  call    cs:__imp_RaiseException
0x1400088b5  nop
0x1400088b6  xor     r8d, r8d
0x1400088b9  mov     edx, 1000000h
0x1400088be  mov     rcx, [rcx+8]
0x1400088c2  call    cs:__imp_UpdatePackageStatus
0x1400088c8  test    eax, eax
0x1400088ca  jz      short loc_14000885A
0x1400088cc  mov     rcx, [rbp+28h]; this
0x1400088d0  mov     r9d, eax; char *
0x1400088d3  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1400088da  mov     edx, 209h; void *
0x1400088df  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
