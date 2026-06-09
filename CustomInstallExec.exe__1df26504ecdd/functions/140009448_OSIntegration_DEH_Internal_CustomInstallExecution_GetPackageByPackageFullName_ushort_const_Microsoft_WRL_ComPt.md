# OSIntegration::DEH::Internal::CustomInstallExecution::GetPackageByPackageFullName(ushort const *,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> &)

- ea: `0x140009448`
- end: `0x1400095db`
- name: `?GetPackageByPackageFullName@CustomInstallExecution@Internal@DEH@OSIntegration@@KAXPEBGAEAV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z`
- size: `403`
- prototype: `__int64 __fastcall(PCWSTR sourceString, __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140009cd8`
- `0x14000aa08`

## callees

- `0x1400033b0`
- `0x140007d78`
- `0x14000872c`
- `0x14000891c`
- `0x140009448`
- `0x1400098dc`
- `0x14000f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400095d4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400095d4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400094b6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1400094b6`

## string_xrefs

- `0x1400094c7`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x140009549`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::CustomInstallExecution::GetPackageByPackageFullName(
        PCWSTR sourceString,
        __int64 *a2)
{
  __int64 v4; // rbx
  int ActivationFactory; // eax
  _QWORD *v6; // rsi
  __int64 v7; // r15
  unsigned __int64 v8; // rbx
  unsigned int v9; // eax
  int v10; // eax
  __int64 v11; // rbx
  __int64 v13; // [rsp+20h] [rbp-40h] BYREF
  _QWORD *v14; // [rsp+28h] [rbp-38h] BYREF
  __int64 v15; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  __int64 v17; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v14 = 0;
  v17 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.Package",
    0x29u,
    0x28u);
  v4 = v17;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v14);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v14);
  if ( ActivationFactory < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CD,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v13);
  v13 = 0;
  v6 = v14;
  v7 = *v14;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v13);
  v17 = 0;
  v8 = -1;
  do
    ++v8;
  while ( sourceString[v8] );
  if ( v8 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x1400095DALL);
  }
  v9 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v8);
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, sourceString, v9, v8);
  v10 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64 *))(v7 + 176))(v6, v17, &v13);
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1D0,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
      (const char *)(unsigned int)v10,
      v13);
  v11 = v13;
  if ( *a2 != v13 )
  {
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
    v15 = *a2;
    *a2 = v11;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v15);
  }
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v13);
  return Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(&v14);
}

```

## disassembly

```asm
0x140009448  mov     [rsp-28h+arg_10], rbx
0x14000944d  mov     [rsp-28h+arg_18], rsi
0x140009452  push    rbp
0x140009453  push    rdi
0x140009454  push    r12
0x140009456  push    r14
0x140009458  push    r15
0x14000945a  mov     rbp, rsp
0x14000945d  sub     rsp, 60h
0x140009461  mov     rax, cs:__security_cookie
0x140009468  xor     rax, rsp
0x14000946b  mov     [rbp+var_8], rax
0x14000946f  mov     rdi, rdx
0x140009472  mov     r14, rcx
0x140009475  xor     r12d, r12d
0x140009478  mov     [rbp+var_38], r12
0x14000947c  mov     [rbp+var_10], r12
0x140009480  lea     r9d, [r12+28h]; unsigned int
0x140009485  lea     r8d, [r12+29h]; unsigned int
0x14000948a  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x140009491  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x140009495  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x14000949a  nop
0x14000949b  mov     rbx, [rbp+var_10]
0x14000949f  lea     rcx, [rbp+var_38]
0x1400094a3  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x1400094a8  lea     r8, [rbp+var_38]
0x1400094ac  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x1400094b3  mov     rcx, rbx
0x1400094b6  call    cs:__imp_RoGetActivationFactory
0x1400094bc  mov     rcx, [rbp+28h]; this
0x1400094c0  test    eax, eax
0x1400094c2  jns     short loc_1400094D9
0x1400094c4  mov     r9d, eax; char *
0x1400094c7  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1400094ce  mov     edx, 1CDh; void *
0x1400094d3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1400094d9  mov     [rbp+var_40], r12
0x1400094dd  mov     rsi, [rbp+var_38]
0x1400094e1  mov     r15, [rsi]
0x1400094e4  lea     rcx, [rbp+var_40]
0x1400094e8  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x1400094ed  mov     [rbp+var_10], r12
0x1400094f1  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400094f5  inc     rbx
0x1400094f8  cmp     [r14+rbx*2], r12w
0x1400094fd  jnz     short loc_1400094F5
0x1400094ff  mov     eax, 0FFFFFFFFh
0x140009504  cmp     rbx, rax
0x140009507  ja      loc_1400095C5
0x14000950d  mov     ecx, ebx; unsigned int
0x14000950f  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x140009514  mov     r9d, ebx; unsigned int
0x140009517  mov     r8d, eax; unsigned int
0x14000951a  mov     rdx, r14; sourceString
0x14000951d  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x140009521  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140009526  nop
0x140009527  lea     r8, [rbp+var_40]
0x14000952b  mov     rdx, [rbp+var_10]
0x14000952f  mov     rcx, rsi
0x140009532  mov     rax, [r15+0B0h]
0x140009539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000953e  mov     rcx, [rbp+28h]; this
0x140009542  test    eax, eax
0x140009544  jns     short loc_14000955B
0x140009546  mov     r9d, eax; char *
0x140009549  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x140009550  mov     edx, 1D0h; void *
0x140009555  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000955b  mov     rbx, [rbp+var_40]
0x14000955f  cmp     [rdi], rbx
0x140009562  jz      short loc_14000958D
0x140009564  test    rbx, rbx
0x140009567  jz      short loc_140009579
0x140009569  mov     rax, [rbx]
0x14000956c  mov     rcx, rbx
0x14000956f  mov     rax, [rax+8]
0x140009573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009578  nop
0x140009579  mov     rax, [rdi]
0x14000957c  mov     [rbp+var_30], rax
0x140009580  mov     [rdi], rbx
0x140009583  lea     rcx, [rbp+var_30]
0x140009587  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x14000958c  nop
0x14000958d  lea     rcx, [rbp+var_40]
0x140009591  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x140009596  nop
0x140009597  lea     rcx, [rbp+var_38]
0x14000959b  call    ?InternalRelease@?$ComPtr@UIPackageLocationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageLocationStatics>::InternalRelease(void)
0x1400095a0  mov     rcx, [rbp+var_8]
0x1400095a4  xor     rcx, rsp; StackCookie
0x1400095a7  call    __security_check_cookie
0x1400095ac  lea     r11, [rsp+60h+var_s0]
0x1400095b1  mov     rbx, [r11+40h]
0x1400095b5  mov     rsi, [r11+48h]
0x1400095b9  mov     rsp, r11
0x1400095bc  pop     r15
0x1400095be  pop     r14
0x1400095c0  pop     r12
0x1400095c2  pop     rdi
0x1400095c3  pop     rbp
0x1400095c4  retn
0x1400095c5  xor     r9d, r9d; lpArguments
0x1400095c8  xor     r8d, r8d; nNumberOfArguments
0x1400095cb  lea     edx, [r9+1]; dwExceptionFlags
0x1400095cf  mov     ecx, 80070216h; dwExceptionCode
0x1400095d4  call    cs:__imp_RaiseException
```
