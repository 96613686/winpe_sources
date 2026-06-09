# OSIntegration::DEH::Internal::ExeServerRegistration_Impl::CalculateServerPermissions(Windows::Internal::String const &)

- ea: `0x1800147f0`
- end: `0x180014d4a`
- name: `?CalculateServerPermissions@ExeServerRegistration_Impl@Internal@DEH@OSIntegration@@EEAAJAEBVString@2Windows@@@Z`
- size: `1370`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::ExeServerRegistration_Impl *__hidden this, const struct Windows::Internal::String *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180012964`
- `0x1800138e0`
- `0x1800147f0`
- `0x18003a300`
- `0x18003bfc0`
- `0x18003c6a8`
- `0x18009aff4`
- `0x1800a219c`
- `0x1800f0260`
- `0x1800f0700`
- `0x1800f073c`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014a81`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014af3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014a81`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180014af3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014a94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014b07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014a94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180014b07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180014aa9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180014b1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180014aa9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180014b1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180014840`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180014840`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800148bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800148bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014851`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800149b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014a09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014a30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014ac0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014b37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014cc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014851`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800149b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014a09`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014a30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014ac0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014b37`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014cc5`
- `ntdll!RtlIsMultiSessionSku` at `0x180014bb6`
- `ntdll!RtlIsMultiSessionSku` at `0x180014bb6`

## string_xrefs

- `0x180014969`: `packageDacl`
- `0x180014b64`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180014b7c`: `packageSidString.SetValueFromString(packageSid.GetRawBuffer(nullptr))`
- `0x180014c0f`: `securityDescriptorString.Initialize(defaultAAAPermissionsBase)`
- `0x180014c3c`: `StringCchPrintfW(packageDacl, length, comDACLFormat, packageSidString.GetChars())`
- `0x180014c7b`: `securityDescriptorString.Concat(saclString, &securityDescriptorString)`
- `0x180014d00`: `securityDescriptorString.Concat(packageDaclString, &securityDescriptorString)`
- `0x180014d15`: `SetRegistrationProperty(_properties.Permissions, securityDescriptorString.Get())`
- `0x180014ce8`: `securityDescriptorString.Initialize(permissions)`

## pseudocode

```c
__int64 __fastcall OSIntegration::DEH::Internal::ExeServerRegistration_Impl::CalculateServerPermissions(
        OSIntegration::DEH::Internal::ExeServerRegistration_Impl *this,
        HSTRING *a2)
{
  __int64 v2; // rax
  HSTRING v4; // rbx
  HSTRING *v6; // rax
  BOOL IsStringEmpty; // edi
  __int64 v8; // rax
  HSTRING v9; // rcx
  const unsigned __int16 *StringRawBuffer; // rax
  const unsigned __int16 *v11; // r8
  __int64 v12; // rcx
  HRESULT v13; // edi
  void *v14; // r14
  unsigned __int64 v15; // r12
  __int64 v16; // rax
  unsigned __int64 v17; // rdi
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // kr00_8
  wchar_t *v20; // rax
  WCHAR *v21; // rsi
  WCHAR *v22; // rcx
  unsigned __int64 v23; // rdx
  void *v24; // rcx
  HSTRING *v26; // rax
  int v27; // edi
  unsigned __int64 v28; // rdi
  HSTRING v29; // rdi
  const WCHAR *v30; // rbx
  HRESULT v31; // ebx
  unsigned __int64 v32; // rdx
  char IsMultiSessionSku; // al
  const unsigned __int16 *v34; // rdx
  int v35; // eax
  const char *v36; // rax
  __int64 v37; // rdx
  unsigned __int64 v38; // rdx
  int v39; // [rsp+20h] [rbp-59h]
  char *v40; // [rsp+28h] [rbp-51h]
  HSTRING newString; // [rsp+30h] [rbp-49h] BYREF
  HSTRING string; // [rsp+38h] [rbp-41h] BYREF
  void *v43[2]; // [rsp+40h] [rbp-39h] BYREF
  int v44; // [rsp+50h] [rbp-29h]
  HSTRING string2; // [rsp+58h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-19h] BYREF
  HSTRING v47; // [rsp+78h] [rbp-1h] BYREF
  HSTRING_HEADER v48; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v2 = *(_QWORD *)this;
  v4 = 0;
  newString = 0;
  v6 = (HSTRING *)(*(__int64 (__fastcall **)(OSIntegration::DEH::Internal::ExeServerRegistration_Impl *, HSTRING *))(v2 + 136))(
                    this,
                    &string);
  IsStringEmpty = WindowsIsStringEmpty(*v6);
  if ( string )
    WindowsDeleteString(string);
  v8 = *(_QWORD *)this;
  if ( !IsStringEmpty )
  {
    v26 = (HSTRING *)(*(__int64 (__fastcall **)(OSIntegration::DEH::Internal::ExeServerRegistration_Impl *, HSTRING *))(v8 + 136))(
                       this,
                       &string);
    v4 = *v26;
    *v26 = 0;
    newString = v4;
    if ( string )
      WindowsDeleteString(string);
    goto LABEL_27;
  }
  if ( !(*(unsigned int (__fastcall **)(OSIntegration::DEH::Internal::ExeServerRegistration_Impl *))(v8 + 152))(this) )
  {
    if ( off_1802E0C20 )
    {
      v13 = Windows::Internal::String::_InitializeHelper((Windows::Internal::String *)&newString, off_1802E0C20);
      if ( v13 >= 0 )
        goto LABEL_50;
      v4 = newString;
    }
    else
    {
      v13 = -2147467261;
    }
    LODWORD(v40) = v13;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x329,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activatableclassregistration.cpp",
      "OSIntegration::DEH::Internal::ExeServerRegistration_Impl::CalculateServerPermissions",
      "securityDescriptorString.Initialize(defaultAAAPermissionsBase)",
      v40,
      (int)newString);
    goto LABEL_22;
  }
  if ( (*(unsigned int (__fastcall **)(OSIntegration::DEH::Internal::ExeServerRegistration_Impl *))(*(_QWORD *)this
                                                                                                  + 152LL))(this) != 2 )
    goto LABEL_6;
  IsMultiSessionSku = RtlIsMultiSessionSku();
  v34 = L"O:PSG:BAD:(A;;0xB;;;SY)(A;;0xB;;;BA)(A;;0xB;;;BU)";
  if ( !IsMultiSessionSku )
    v34 = L"O:PSG:BAD:(A;;0xB;;;SY)(A;;0xB;;;IU)(A;;0xB;;;BA)(A;;0xB;;;BU)";
  v35 = Windows::Internal::String::_InitializeHelper((Windows::Internal::String *)&newString, v34);
  v31 = v35;
  if ( v35 < 0 )
  {
    LODWORD(v40) = v35;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x33B,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activatableclassregistration.cpp",
      "OSIntegration::DEH::Internal::ExeServerRegistration_Impl::CalculateServerPermissions",
      "securityDescriptorString.Initialize(permissions)",
      v40,
      (int)newString);
LABEL_66:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&newString);
    return (unsigned int)v31;
  }
LABEL_50:
  v4 = newString;
LABEL_6:
  if ( (*(unsigned int (__fastcall **)(OSIntegration::DEH::Internal::ExeServerRegistration_Impl *))(*(_QWORD *)this
                                                                                                  + 152LL))(this) != 2 )
    goto LABEL_27;
  v9 = *a2;
  v44 = 0;
  *(_OWORD *)v43 = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(v9, 0);
  if ( StringRawBuffer )
  {
    v11 = StringRawBuffer;
    v12 = 1073741822;
    do
    {
      if ( !*v11 )
        break;
      ++v11;
      --v12;
    }
    while ( v12 );
    v13 = v12 == 0 ? 0x80070057 : 0;
    if ( v12 )
    {
      v13 = Common::StringBuffer::SetValue(
              (Common::StringBuffer *)v43,
              StringRawBuffer,
              v12 != 0 ? 1073741822 - v12 : 0);
      if ( v13 >= 0 )
        goto LABEL_13;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x249,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)(unsigned int)v13,
        v39);
    }
    LODWORD(v40) = v13;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x347,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activatableclassregistration.cpp",
      "OSIntegration::DEH::Internal::ExeServerRegistration_Impl::CalculateServerPermissions",
      "packageSidString.SetValueFromString(packageSid.GetRawBuffer(nullptr))",
      v40,
      (int)newString);
    v24 = v43[1];
    if ( !v43[1] )
      goto LABEL_22;
    goto LABEL_21;
  }
LABEL_13:
  v14 = v43[1];
  v15 = -1;
  v16 = -1;
  do
    ++v16;
  while ( *((_WORD *)v43[1] + v16) );
  v17 = v16 + 13;
  v19 = v16 + 13;
  v18 = 2 * (v16 + 13);
  if ( !is_mul_ok(v19, 2u) )
    v18 = -1;
  v20 = (wchar_t *)operator new[](v18, (const struct std::nothrow_t *)std::nothrow);
  v21 = v20;
  if ( !v20 )
  {
    v13 = -2147024882;
    LODWORD(v40) = -2147024882;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x34B,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activatableclassregistration.cpp",
      "OSIntegration::DEH::Internal::ExeServerRegistration_Impl::CalculateServerPermissions",
      "packageDacl",
      v40,
      (int)newString);
    v22 = 0;
LABEL_19:
    operator delete(v22, 2u);
    if ( !v14 )
    {
LABEL_22:
      if ( v4 )
        WindowsDeleteString(v4);
      return (unsigned int)v13;
    }
    v24 = v14;
LABEL_21:
    operator delete(v24, v23);
    goto LABEL_22;
  }
  v13 = StringCchPrintfW(v20, v17, L"(A;;0xB;;;%s)", v14);
  if ( v13 < 0 )
  {
    v36 = "StringCchPrintfW(packageDacl, length, comDACLFormat, packageSidString.GetChars())";
    v37 = 844;
LABEL_56:
    LODWORD(v40) = v13;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v37,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activatableclassregistration.cpp",
      "OSIntegration::DEH::Internal::ExeServerRegistration_Impl::CalculateServerPermissions",
      v36,
      v40,
      (int)newString);
    v22 = v21;
    goto LABEL_19;
  }
  v28 = -1;
  do
    ++v28;
  while ( v21[v28] );
  if ( v28 > 0xFFFFFFFF )
  {
    LODWORD(v28) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v21, v28, &hstringHeader, &string2);
  newString = 0;
  v13 = WindowsConcatString(v4, string2, &newString);
  if ( v13 < 0 )
  {
    v36 = "securityDescriptorString.Concat(packageDaclString, &securityDescriptorString)";
    v37 = 847;
    goto LABEL_56;
  }
  v29 = newString;
  WindowsDeleteString(v4);
  v30 = off_1802E0C18;
  do
    ++v15;
  while ( off_1802E0C18[v15] );
  if ( v15 > 0xFFFFFFFF )
  {
    LODWORD(v15) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v30, v15, &v48, &v47);
  string = 0;
  v31 = WindowsConcatString(v29, v47, &string);
  if ( v31 < 0 )
  {
    LODWORD(v40) = v31;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x353,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activatableclassregistration.cpp",
      "OSIntegration::DEH::Internal::ExeServerRegistration_Impl::CalculateServerPermissions",
      "securityDescriptorString.Concat(saclString, &securityDescriptorString)",
      v40,
      (int)newString);
    operator delete(v21, 2u);
    if ( v14 )
      operator delete(v14, v38);
    if ( v29 )
      WindowsDeleteString(v29);
    return (unsigned int)v31;
  }
  v4 = string;
  newString = string;
  WindowsDeleteString(v29);
  operator delete(v21, 2u);
  if ( v14 )
    operator delete(v14, v32);
LABEL_27:
  v27 = SecurityDescriptor::InitializeFromSDDLString(
          (OSIntegration::DEH::Internal::ExeServerRegistration_Impl *)((char *)this + 136),
          v4);
  if ( v27 < 0 )
  {
    LODWORD(v40) = v27;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x35B,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activatableclassregistration.cpp",
      "OSIntegration::DEH::Internal::ExeServerRegistration_Impl::CalculateServerPermissions",
      "SetRegistrationProperty(_properties.Permissions, securityDescriptorString.Get())",
      v40,
      (int)newString);
    v31 = v27;
    goto LABEL_66;
  }
  if ( v4 )
    WindowsDeleteString(v4);
  return 0;
}

```

## disassembly

```asm
0x1800147f0  mov     [rsp-8+arg_10], rbx
0x1800147f5  push    rbp
0x1800147f6  push    rsi
0x1800147f7  push    rdi
0x1800147f8  push    r12
0x1800147fa  push    r13
0x1800147fc  push    r14
0x1800147fe  push    r15
0x180014800  lea     rbp, [rsp-27h]
0x180014805  sub     rsp, 0A0h
0x18001480c  mov     rax, cs:__security_cookie
0x180014813  xor     rax, rsp
0x180014816  mov     [rbp+57h+var_38], rax
0x18001481a  mov     rax, [rcx]
0x18001481d  mov     rsi, rdx
0x180014820  xor     r13d, r13d
0x180014823  lea     rdx, [rbp+57h+string]
0x180014827  mov     ebx, r13d
0x18001482a  mov     r15, rcx
0x18001482d  mov     [rbp+57h+newString], rbx
0x180014831  mov     rax, [rax+88h]
0x180014838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001483d  mov     rcx, [rax]; string
0x180014840  call    cs:__imp_WindowsIsStringEmpty
0x180014846  mov     rcx, [rbp+57h+string]; string
0x18001484a  mov     edi, eax
0x18001484c  test    rcx, rcx
0x18001484f  jz      short loc_180014857
0x180014851  call    cs:__imp_WindowsDeleteString
0x180014857  mov     rax, [r15]
0x18001485a  mov     rcx, r15
0x18001485d  test    edi, edi
0x18001485f  jz      loc_1800149E6
0x180014865  mov     rax, [rax+98h]
0x18001486c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014871  test    eax, eax
0x180014873  jz      loc_180014BEC
0x180014879  mov     rax, [r15]
0x18001487c  mov     rcx, r15
0x18001487f  mov     rax, [rax+98h]
0x180014886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001488b  cmp     eax, 2
0x18001488e  jz      loc_180014BB6
0x180014894  mov     rax, [r15]
0x180014897  mov     rcx, r15
0x18001489a  mov     rax, [rax+98h]
0x1800148a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148a6  cmp     eax, 2
0x1800148a9  jnz     loc_180014A0F
0x1800148af  mov     rcx, [rsi]; string
0x1800148b2  xorps   xmm0, xmm0
0x1800148b5  xor     edx, edx; length
0x1800148b7  mov     [rbp+57h+var_80], r13d
0x1800148bb  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x1800148bf  call    cs:__imp_WindowsGetStringRawBuffer
0x1800148c5  mov     r9, rax
0x1800148c8  test    rax, rax
0x1800148cb  jz      short loc_180014925
0x1800148cd  mov     edx, 3FFFFFFEh
0x1800148d2  mov     r8, rax
0x1800148d5  mov     ecx, edx
0x1800148d7  cmp     [r8], r13w
0x1800148db  jz      short loc_1800148E7
0x1800148dd  add     r8, 2
0x1800148e1  sub     rcx, 1
0x1800148e5  jnz     short loc_1800148D7
0x1800148e7  mov     rax, rcx
0x1800148ea  neg     rax
0x1800148ed  mov     rax, rcx
0x1800148f0  sbb     edi, edi
0x1800148f2  sub     rdx, rcx
0x1800148f5  not     edi
0x1800148f7  and     edi, 80070057h
0x1800148fd  neg     rax
0x180014900  sbb     r8, r8
0x180014903  and     r8, rdx; unsigned int
0x180014906  test    rcx, rcx
0x180014909  jz      loc_180014B60
0x18001490f  mov     rdx, r9; unsigned __int16 *
0x180014912  lea     rcx, [rbp+57h+var_90]; this
0x180014916  call    ?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z; Common::StringBuffer::SetValue(ushort const *,ulong)
0x18001491b  mov     edi, eax
0x18001491d  test    eax, eax
0x18001491f  js      loc_180014B78
0x180014925  mov     r14, [rbp+57h+var_90+8]
0x180014929  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001492d  mov     rax, r12
0x180014930  inc     rax
0x180014933  cmp     [r14+rax*2], r13w
0x180014938  jnz     short loc_180014930
0x18001493a  lea     rdi, [rax+0Dh]
0x18001493e  mov     eax, 2
0x180014943  mul     rdi
0x180014946  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001494d  cmovb   rax, r12
0x180014951  mov     rcx, rax; unsigned __int64
0x180014954  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180014959  mov     rsi, rax
0x18001495c  test    rax, rax
0x18001495f  jnz     loc_180014A3A
0x180014965  mov     rcx, [rbp+5Fh]; this
0x180014969  lea     rax, aPackagedacl; "packageDacl"
0x180014970  mov     edi, 8007000Eh
0x180014975  lea     r9, aOsintegrationD_397; "OSIntegration::DEH::Internal::ExeServer"...
0x18001497c  mov     dword ptr [rsp+0D0h+var_A8], edi; char *
0x180014980  lea     r8, aOnecoreAdminAp_30; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180014987  mov     edx, 34Bh; void *
0x18001498c  mov     [rsp+0D0h+var_B0], rax; char *
0x180014991  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180014996  xor     ecx, ecx; void *
0x180014998  mov     edx, 2; unsigned __int64
0x18001499d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800149a2  test    r14, r14
0x1800149a5  jz      short loc_1800149AF
0x1800149a7  mov     rcx, r14; void *
0x1800149aa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800149af  test    rbx, rbx
0x1800149b2  jz      short loc_1800149BD
0x1800149b4  mov     rcx, rbx; string
0x1800149b7  call    cs:__imp_WindowsDeleteString
0x1800149bd  mov     eax, edi
0x1800149bf  mov     rcx, [rbp+57h+var_38]
0x1800149c3  xor     rcx, rsp; StackCookie
0x1800149c6  call    __security_check_cookie
0x1800149cb  mov     rbx, [rsp+0D0h+arg_10]
0x1800149d3  add     rsp, 0A0h
0x1800149da  pop     r15
0x1800149dc  pop     r14
0x1800149de  pop     r13
0x1800149e0  pop     r12
0x1800149e2  pop     rdi
0x1800149e3  pop     rsi
0x1800149e4  pop     rbp
0x1800149e5  retn
0x1800149e6  mov     rax, [rax+88h]
0x1800149ed  lea     rdx, [rbp+57h+string]
0x1800149f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149f6  mov     rbx, [rax]
0x1800149f9  mov     [rax], r13
0x1800149fc  mov     rcx, [rbp+57h+string]; string
0x180014a00  mov     [rbp+57h+newString], rbx
0x180014a04  test    rcx, rcx
0x180014a07  jz      short loc_180014A0F
0x180014a09  call    cs:__imp_WindowsDeleteString
0x180014a0f  lea     rcx, [r15+88h]; this
0x180014a16  mov     rdx, rbx; HSTRING
0x180014a19  call    ?InitializeFromSDDLString@SecurityDescriptor@@QEAAJPEAUHSTRING__@@@Z; SecurityDescriptor::InitializeFromSDDLString(HSTRING__ *)
0x180014a1e  mov     edi, eax
0x180014a20  test    eax, eax
0x180014a22  js      loc_180014D11
0x180014a28  test    rbx, rbx
0x180014a2b  jz      short loc_180014A36
0x180014a2d  mov     rcx, rbx; string
0x180014a30  call    cs:__imp_WindowsDeleteString
0x180014a36  xor     eax, eax
0x180014a38  jmp     short loc_1800149BF
0x180014a3a  mov     r9, r14
0x180014a3d  lea     r8, aA0xbS; "(A;;0xB;;;%s)"
0x180014a44  mov     rdx, rdi; unsigned __int64
0x180014a47  mov     rcx, rsi; Buffer
0x180014a4a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180014a4f  mov     edi, eax
0x180014a51  test    eax, eax
0x180014a53  js      loc_180014C3C
0x180014a59  mov     rdi, r12
0x180014a5c  inc     rdi
0x180014a5f  cmp     [rsi+rdi*2], r13w
0x180014a64  jnz     short loc_180014A5C
0x180014a66  mov     eax, 0FFFFFFFFh
0x180014a6b  cmp     rdi, rax
0x180014a6e  jbe     short loc_180014A87
0x180014a70  xor     r9d, r9d; lpArguments
0x180014a73  xor     r8d, r8d; nNumberOfArguments
0x180014a76  mov     ecx, 0C000000Dh; dwExceptionCode
0x180014a7b  mov     edi, eax
0x180014a7d  lea     edx, [r9+1]; dwExceptionFlags
0x180014a81  call    cs:__imp_RaiseException
0x180014a87  lea     r9, [rbp+57h+string2]; string
0x180014a8b  mov     edx, edi; length
0x180014a8d  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180014a91  mov     rcx, rsi; sourceString
0x180014a94  call    cs:__imp_WindowsCreateStringReference
0x180014a9a  mov     rdx, [rbp+57h+string2]; string2
0x180014a9e  lea     r8, [rbp+57h+newString]; newString
0x180014aa2  mov     rcx, rbx; string1
0x180014aa5  mov     [rbp+57h+newString], r13
0x180014aa9  call    cs:__imp_WindowsConcatString
0x180014aaf  mov     edi, eax
0x180014ab1  test    eax, eax
0x180014ab3  js      loc_180014D00
0x180014ab9  mov     rdi, [rbp+57h+newString]
0x180014abd  mov     rcx, rbx; string
0x180014ac0  call    cs:__imp_WindowsDeleteString
0x180014ac6  mov     rbx, cs:off_1802E0C18; "S:(ML;;NX;;;LW)"
0x180014acd  inc     r12
0x180014ad0  cmp     [rbx+r12*2], r13w
0x180014ad5  jnz     short loc_180014ACD
0x180014ad7  mov     eax, 0FFFFFFFFh
0x180014adc  cmp     r12, rax
0x180014adf  jbe     short loc_180014AF9
0x180014ae1  xor     r9d, r9d; lpArguments
0x180014ae4  xor     r8d, r8d; nNumberOfArguments
0x180014ae7  mov     ecx, 0C000000Dh; dwExceptionCode
0x180014aec  mov     r12d, eax
0x180014aef  lea     edx, [r9+1]; dwExceptionFlags
0x180014af3  call    cs:__imp_RaiseException
0x180014af9  lea     r9, [rbp+57h+var_58]; string
0x180014afd  mov     edx, r12d; length
0x180014b00  lea     r8, [rbp+57h+var_50]; hstringHeader
0x180014b04  mov     rcx, rbx; sourceString
0x180014b07  call    cs:__imp_WindowsCreateStringReference
0x180014b0d  mov     rdx, [rbp+57h+var_58]; string2
0x180014b11  lea     r8, [rbp+57h+string]; newString
0x180014b15  mov     rcx, rdi; string1
0x180014b18  mov     [rbp+57h+string], r13
0x180014b1c  call    cs:__imp_WindowsConcatString
0x180014b22  mov     ebx, eax
0x180014b24  test    eax, eax
0x180014b26  js      loc_180014C77
0x180014b2c  mov     rbx, [rbp+57h+string]
0x180014b30  mov     rcx, rdi; string
0x180014b33  mov     [rbp+57h+newString], rbx
0x180014b37  call    cs:__imp_WindowsDeleteString
0x180014b3d  mov     edx, 2; unsigned __int64
0x180014b42  mov     rcx, rsi; void *
0x180014b45  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014b4a  test    r14, r14
0x180014b4d  jz      loc_180014A0F
0x180014b53  mov     rcx, r14; void *
0x180014b56  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180014b5b  jmp     loc_180014A0F
0x180014b60  mov     rcx, [rbp+5Fh]; this
0x180014b64  lea     r8, aOnecoreBaseApp_88; "onecore\\base\\appmodel\\common\\widest"...
0x180014b6b  mov     r9d, edi; char *
0x180014b6e  mov     edx, 249h; void *
0x180014b73  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014b78  mov     rcx, [rbp+5Fh]; this
0x180014b7c  lea     rax, aPackagesidstri; "packageSidString.SetValueFromString(pac"...
0x180014b83  mov     dword ptr [rsp+0D0h+var_A8], edi; char *
0x180014b87  lea     r9, aOsintegrationD_397; "OSIntegration::DEH::Internal::ExeServer"...
0x180014b8e  lea     r8, aOnecoreAdminAp_30; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180014b95  mov     [rsp+0D0h+var_B0], rax; char *
0x180014b9a  mov     edx, 347h; void *
0x180014b9f  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180014ba4  mov     rcx, [rbp+57h+var_90+8]
0x180014ba8  test    rcx, rcx
0x180014bab  jnz     loc_1800149AA
0x180014bb1  jmp     loc_1800149AF
0x180014bb6  call    cs:__imp_RtlIsMultiSessionSku
0x180014bbc  test    al, al
0x180014bbe  lea     rcx, aOPsgBadA0xbSyA; "O:PSG:BAD:(A;;0xB;;;SY)(A;;0xB;;;IU)(A;"...
0x180014bc5  lea     rdx, aOPsgBadA0xbSyA_0; "O:PSG:BAD:(A;;0xB;;;SY)(A;;0xB;;;BA)(A;"...
0x180014bcc  cmovz   rdx, rcx; unsigned __int16 *
0x180014bd0  lea     rcx, [rbp+57h+newString]; this
0x180014bd4  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x180014bd9  mov     ebx, eax
0x180014bdb  test    eax, eax
0x180014bdd  js      loc_180014CD2
0x180014be3  mov     rbx, [rbp+57h+newString]
0x180014be7  jmp     loc_180014894
0x180014bec  mov     rdx, cs:off_1802E0C20; unsigned __int16 *
0x180014bf3  test    rdx, rdx
0x180014bf6  jz      short loc_180014C70
0x180014bf8  lea     rcx, [rbp+57h+newString]; this
0x180014bfc  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z; Windows::Internal::String::_InitializeHelper(ushort const *)
0x180014c01  mov     edi, eax
0x180014c03  test    eax, eax
0x180014c05  jns     short loc_180014BE3
0x180014c07  mov     rbx, [rbp+57h+newString]
0x180014c0b  mov     rcx, [rbp+5Fh]; this
0x180014c0f  lea     rax, aSecuritydescri_3; "securityDescriptorString.Initialize(def"...
0x180014c16  mov     dword ptr [rsp+0D0h+var_A8], edi; char *
0x180014c1a  lea     r9, aOsintegrationD_397; "OSIntegration::DEH::Internal::ExeServer"...
0x180014c21  lea     r8, aOnecoreAdminAp_30; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180014c28  mov     [rsp+0D0h+var_B0], rax; char *
0x180014c2d  mov     edx, 329h; void *
0x180014c32  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180014c37  jmp     loc_1800149AF
0x180014c3c  lea     rax, aStringcchprint_3; "StringCchPrintfW(packageDacl, length, c"...
0x180014c43  mov     edx, 34Ch; void *
0x180014c48  mov     rcx, [rbp+5Fh]; this
0x180014c4c  lea     r8, aOnecoreAdminAp_30; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180014c53  mov     dword ptr [rsp+0D0h+var_A8], edi; char *
0x180014c57  lea     r9, aOsintegrationD_397; "OSIntegration::DEH::Internal::ExeServer"...
0x180014c5e  mov     [rsp+0D0h+var_B0], rax; char *
0x180014c63  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180014c68  mov     rcx, rsi
0x180014c6b  jmp     loc_180014998
0x180014c70  mov     edi, 80004003h
0x180014c75  jmp     short loc_180014C0B
0x180014c77  mov     rcx, [rbp+5Fh]; this
0x180014c7b  lea     rax, aSecuritydescri_1; "securityDescriptorString.Concat(saclStr"...
0x180014c82  mov     dword ptr [rsp+0D0h+var_A8], ebx; char *
0x180014c86  lea     r9, aOsintegrationD_397; "OSIntegration::DEH::Internal::ExeServer"...
0x180014c8d  lea     r8, aOnecoreAdminAp_30; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180014c94  mov     [rsp+0D0h+var_B0], rax; char *
0x180014c99  mov     edx, 353h; void *
0x180014c9e  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180014ca3  mov     edx, 2; unsigned __int64
0x180014ca8  mov     rcx, rsi; void *
  ... truncated ...
```
