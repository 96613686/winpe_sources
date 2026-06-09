# OSIntegration::DEH::Internal::ExeServerRegistration_Impl::PendingWriteToStore(OSIntegration::DEH::ICollectorPackageInformation const *,IActivationCatalogContext *)

- ea: `0x18003aef0`
- end: `0x18003b2cb`
- name: `?PendingWriteToStore@ExeServerRegistration_Impl@Internal@DEH@OSIntegration@@UEAAJPEBUICollectorPackageInformation@34@PEAUIActivationCatalogContext@@@Z`
- size: `987`
- prototype: `__int64 __fastcall(OSIntegration::DEH::Internal::ExeServerRegistration_Impl *__hidden this, const struct OSIntegration::DEH::ICollectorPackageInformation *, struct IActivationCatalogContext *)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000b3bc`
- `0x18003aef0`
- `0x18003c140`
- `0x180084114`
- `0x18009aff4`
- `0x1800f0260`
- `0x1801b369c`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003af63`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003afb0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003af63`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003afb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003af76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003afc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003affe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003af76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003afc3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003affe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003afea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003afea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b2a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b2c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b2a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b2c0`

## string_xrefs

- `0x18003b0a9`: `OSIntegration::DEH::Internal::ExeServerRegistration_Impl::PendingWriteToStore`
- `0x18003b0f5`: `OSIntegration::DEH::Internal::ExeServerRegistration_Impl::PendingWriteToStore`
- `0x18003b197`: `OSIntegration::DEH::Internal::ExeServerRegistration_Impl::PendingWriteToStore`
- `0x18003b209`: `OSIntegration::DEH::Internal::ExeServerRegistration_Impl::PendingWriteToStore`
- `0x18003b289`: `OSIntegration::DEH::Internal::ExeServerRegistration_Impl::PendingWriteToStore`
- `0x18003b0de`: `CalculateServerPermissions(strPackageSid)`
- `0x18003b18b`: `registrationStoreContext->CreateServerEntry( packageMoniker.Get(), _serverName.Get(), _properties)`
- `0x18003b247`: `incomingPackage->GetMainPackageFamilyMoniker(executionPackageFamily)`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OSIntegration::DEH::Internal::ExeServerRegistration_Impl::PendingWriteToStore(
        OSIntegration::DEH::Internal::ExeServerRegistration_Impl *this,
        const struct OSIntegration::DEH::ICollectorPackageInformation *a2,
        struct IActivationCatalogContext *a3)
{
  const WCHAR *v6; // rsi
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rbx
  __int64 v9; // rax
  const WCHAR *v10; // rbx
  char v11; // r13
  const WCHAR *StringRawBuffer; // rax
  int v13; // ebx
  __int64 v14; // rsi
  __int64 (__fastcall *v15)(__int64, char *); // rdi
  __int64 (__fastcall ***v16)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v17)(_QWORD, GUID *, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rcx
  const char *v20; // rax
  __int64 v21; // rdx
  int v23; // eax
  int v24; // eax
  __int64 v25; // rcx
  __int64 v26; // rcx
  int v27; // eax
  const char *v28; // rax
  __int64 v29; // rdx
  OpaqueString *v30; // rax
  int v31; // eax
  char *v32; // [rsp+28h] [rbp-61h]
  UINT32 length[2]; // [rsp+30h] [rbp-59h] BYREF
  __int64 v34; // [rsp+38h] [rbp-51h] BYREF
  HSTRING newString; // [rsp+40h] [rbp-49h] BYREF
  HSTRING v36; // [rsp+48h] [rbp-41h] BYREF
  HSTRING_HEADER v37; // [rsp+50h] [rbp-39h] BYREF
  HSTRING v38; // [rsp+68h] [rbp-21h] BYREF
  HSTRING_HEADER v39; // [rsp+70h] [rbp-19h] BYREF
  HSTRING string; // [rsp+88h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v6 = (const WCHAR *)(**(__int64 (__fastcall ***)(const struct OSIntegration::DEH::ICollectorPackageInformation *))a2)(a2);
  v7 = -1;
  v8 = -1;
  do
    ++v8;
  while ( v6[v8] );
  if ( v8 > 0xFFFFFFFF )
  {
    LODWORD(v8) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v6, v8, &hstringHeader, &string);
  v9 = (*(__int64 (__fastcall **)(const struct OSIntegration::DEH::ICollectorPackageInformation *))(*(_QWORD *)a2 + 32LL))(a2);
  v10 = (const WCHAR *)v9;
  do
    ++v7;
  while ( *(_WORD *)(v9 + 2 * v7) );
  if ( v7 > 0xFFFFFFFF )
  {
    LODWORD(v7) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v10, v7, &v39, &v38);
  v11 = (*(__int64 (__fastcall **)(const struct OSIntegration::DEH::ICollectorPackageInformation *))(*(_QWORD *)a2 + 40LL))(a2);
  v36 = 0;
  length[0] = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(v38, length);
  WindowsCreateStringReference(StringRawBuffer, length[0], &v37, &v36);
  v13 = (*(__int64 (__fastcall **)(OSIntegration::DEH::Internal::ExeServerRegistration_Impl *, HSTRING *))(*(_QWORD *)this + 328LL))(
          this,
          &v36);
  if ( v13 < 0 )
  {
    v20 = "CalculateServerPermissions(strPackageSid)";
    v21 = 774;
LABEL_16:
    LODWORD(v32) = v13;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activatableclassregistration.cpp",
      "OSIntegration::DEH::Internal::ExeServerRegistration_Impl::PendingWriteToStore",
      v20,
      v32,
      length[0]);
    return (unsigned int)v13;
  }
  v14 = *((_QWORD *)this + 28);
  v15 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v14 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 216);
  v13 = v15(v14, (char *)this + 216);
  if ( v13 < 0 )
  {
    v20 = "_attributes->GetView(&(_properties.CustomAttributes.MapView))";
    v21 = 776;
    goto LABEL_16;
  }
  v34 = 0;
  v16 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 31);
  v17 = **v16;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
  v18 = v17(v16, &GUID_e2fcc7c1_3bfc_5a0b_b2b0_72e769d1cb7e, &v34);
  v13 = v18;
  if ( v18 < 0 )
  {
    LODWORD(v32) = v18;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x30B,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activatableclassregistration.cpp",
      "OSIntegration::DEH::Internal::ExeServerRegistration_Impl::PendingWriteToStore",
      "_classNames.As(&classNamesIterable)",
      v32,
      length[0]);
    v19 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    return (unsigned int)v13;
  }
  v23 = MultiString::InitializeFromStringArray((HSTRING *)this + 19, v34);
  v13 = v23;
  if ( v23 < 0 )
  {
    LODWORD(v32) = v23;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x30E,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activatableclassregistration.cpp",
      "OSIntegration::DEH::Internal::ExeServerRegistration_Impl::PendingWriteToStore",
      "_properties.ActivatableClasses.InitializeFromStringArray(classNamesIterable.Get())",
      v32,
      length[0]);
LABEL_34:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    return (unsigned int)v13;
  }
  v24 = (*(__int64 (__fastcall **)(struct IActivationCatalogContext *, HSTRING, _QWORD, char *))(*(_QWORD *)a3 + 256LL))(
          a3,
          string,
          *((_QWORD *)this + 29),
          (char *)this + 40);
  v13 = v24;
  if ( v24 < 0 )
  {
    LODWORD(v32) = v24;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x312,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activatableclassregistration.cpp",
      "OSIntegration::DEH::Internal::ExeServerRegistration_Impl::PendingWriteToStore",
      "registrationStoreContext->CreateServerEntry( packageMoniker.Get(), _serverName.Get(), _properties)",
      v32,
      length[0]);
    v25 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    return (unsigned int)v13;
  }
  if ( v11 )
  {
    *(_QWORD *)length = 0;
    v27 = (*(__int64 (__fastcall **)(const struct OSIntegration::DEH::ICollectorPackageInformation *, UINT32 *))(*(_QWORD *)a2 + 64LL))(
            a2,
            length);
    v13 = v27;
    if ( v27 >= 0 )
    {
      v30 = OpaqueString::OpaqueString(&newString, (const struct OpaqueString *)length);
      v31 = SetRegistrationProperty<OpaqueString,OpaqueString>((char *)this + 112, v30);
      v13 = v31;
      if ( v31 >= 0 )
      {
        WindowsDeleteString(*(HSTRING *)length);
        goto LABEL_25;
      }
      LODWORD(v32) = v31;
      v28 = "SetRegistrationProperty( _properties.ExecutionPackageFamily, executionPackageFamily)";
      v29 = 795;
    }
    else
    {
      LODWORD(v32) = v27;
      v28 = "incomingPackage->GetMainPackageFamilyMoniker(executionPackageFamily)";
      v29 = 793;
    }
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activatableclassregistration.cpp",
      "OSIntegration::DEH::Internal::ExeServerRegistration_Impl::PendingWriteToStore",
      v28,
      v32,
      length[0]);
    WindowsDeleteString(*(HSTRING *)length);
    *(_QWORD *)length = 0;
    goto LABEL_34;
  }
LABEL_25:
  v26 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  return 0;
}

```

## disassembly

```asm
0x18003aef0  mov     [rsp-8+arg_18], rbx
0x18003aef5  push    rbp
0x18003aef6  push    rsi
0x18003aef7  push    rdi
0x18003aef8  push    r12
0x18003aefa  push    r13
0x18003aefc  push    r14
0x18003aefe  push    r15
0x18003af00  lea     rbp, [rsp-27h]
0x18003af05  sub     rsp, 0B0h
0x18003af0c  mov     rax, cs:__security_cookie
0x18003af13  xor     rax, rsp
0x18003af16  mov     [rbp+57h+var_38], rax
0x18003af1a  mov     r12, r8
0x18003af1d  mov     r15, rdx
0x18003af20  mov     r14, rcx
0x18003af23  mov     rax, [rdx]
0x18003af26  mov     rcx, rdx
0x18003af29  mov     rax, [rax]
0x18003af2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003af31  mov     rsi, rax
0x18003af34  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003af38  mov     rbx, rdi
0x18003af3b  xor     eax, eax
0x18003af3d  inc     rbx
0x18003af40  cmp     [rsi+rbx*2], ax
0x18003af44  jnz     short loc_18003AF3D
0x18003af46  mov     r13d, 0FFFFFFFFh
0x18003af4c  cmp     rbx, r13
0x18003af4f  jbe     short loc_18003AF69
0x18003af51  mov     ebx, r13d
0x18003af54  xor     r9d, r9d; lpArguments
0x18003af57  xor     r8d, r8d; nNumberOfArguments
0x18003af5a  lea     edx, [r9+1]; dwExceptionFlags
0x18003af5e  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003af63  call    cs:__imp_RaiseException
0x18003af69  lea     r9, [rbp+57h+string]; string
0x18003af6d  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18003af71  mov     edx, ebx; length
0x18003af73  mov     rcx, rsi; sourceString
0x18003af76  call    cs:__imp_WindowsCreateStringReference
0x18003af7c  mov     rax, [r15]
0x18003af7f  mov     rcx, r15
0x18003af82  mov     rax, [rax+20h]
0x18003af86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003af8b  mov     rbx, rax
0x18003af8e  xor     esi, esi
0x18003af90  inc     rdi
0x18003af93  cmp     [rax+rdi*2], si
0x18003af97  jnz     short loc_18003AF90
0x18003af99  cmp     rdi, r13
0x18003af9c  jbe     short loc_18003AFB6
0x18003af9e  mov     edi, r13d
0x18003afa1  xor     r9d, r9d; lpArguments
0x18003afa4  xor     r8d, r8d; nNumberOfArguments
0x18003afa7  lea     edx, [r9+1]; dwExceptionFlags
0x18003afab  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003afb0  call    cs:__imp_RaiseException
0x18003afb6  lea     r9, [rbp+57h+var_78]; string
0x18003afba  lea     r8, [rbp+57h+var_70]; hstringHeader
0x18003afbe  mov     edx, edi; length
0x18003afc0  mov     rcx, rbx; sourceString
0x18003afc3  call    cs:__imp_WindowsCreateStringReference
0x18003afc9  mov     rax, [r15]
0x18003afcc  mov     rcx, r15
0x18003afcf  mov     rax, [rax+28h]
0x18003afd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003afd8  mov     r13b, al
0x18003afdb  mov     [rbp+57h+var_98], rsi
0x18003afdf  mov     [rbp+57h+length], esi
0x18003afe2  lea     rdx, [rbp+57h+length]; length
0x18003afe6  mov     rcx, [rbp+57h+var_78]; string
0x18003afea  call    cs:__imp_WindowsGetStringRawBuffer
0x18003aff0  lea     r9, [rbp+57h+var_98]; string
0x18003aff4  lea     r8, [rbp+57h+var_90]; hstringHeader
0x18003aff8  mov     edx, [rbp+57h+length]; length
0x18003affb  mov     rcx, rax; sourceString
0x18003affe  call    cs:__imp_WindowsCreateStringReference
0x18003b004  mov     rcx, [r14]
0x18003b007  mov     rax, [rcx+148h]
0x18003b00e  lea     rdx, [rbp+57h+var_98]
0x18003b012  mov     rcx, r14
0x18003b015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b01a  mov     ebx, eax
0x18003b01c  test    eax, eax
0x18003b01e  js      loc_18003B0DE
0x18003b024  mov     rsi, [r14+0E0h]
0x18003b02b  mov     rax, [rsi]
0x18003b02e  mov     rdi, [rax+48h]
0x18003b032  lea     rbx, [r14+0D8h]
0x18003b039  mov     rcx, rbx
0x18003b03c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003b041  mov     rdx, rbx
0x18003b044  mov     rcx, rsi
0x18003b047  mov     rax, rdi
0x18003b04a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b04f  mov     ebx, eax
0x18003b051  xor     esi, esi
0x18003b053  test    eax, eax
0x18003b055  js      loc_18003B133
0x18003b05b  mov     [rbp+57h+var_A8], rsi
0x18003b05f  mov     rdi, [r14+0F8h]
0x18003b066  mov     rax, [rdi]
0x18003b069  mov     rbx, [rax]
0x18003b06c  lea     rcx, [rbp+57h+var_A8]
0x18003b070  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003b075  lea     r8, [rbp+57h+var_A8]
0x18003b079  lea     rdx, _GUID_e2fcc7c1_3bfc_5a0b_b2b0_72e769d1cb7e
0x18003b080  mov     rcx, rdi
0x18003b083  mov     rax, rbx
0x18003b086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b08b  mov     ebx, eax
0x18003b08d  test    eax, eax
0x18003b08f  jns     loc_18003B141
0x18003b095  mov     rcx, [rbp+5Fh]; this
0x18003b099  mov     dword ptr [rsp+0E0h+var_B8], eax; char *
0x18003b09d  lea     rax, aClassnamesAsCl; "_classNames.As(&classNamesIterable)"
0x18003b0a4  mov     [rsp+0E0h+var_C0], rax; char *
0x18003b0a9  lea     r9, aOsintegrationD_269; "OSIntegration::DEH::Internal::ExeServer"...
0x18003b0b0  lea     r8, aOnecoreAdminAp_30; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003b0b7  mov     edx, 30Bh; void *
0x18003b0bc  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003b0c1  nop
0x18003b0c2  mov     rcx, [rbp+57h+var_A8]
0x18003b0c6  test    rcx, rcx
0x18003b0c9  jz      short loc_18003B0DC
0x18003b0cb  mov     [rbp+57h+var_A8], rsi
0x18003b0cf  mov     rax, [rcx]
0x18003b0d2  mov     rax, [rax+10h]
0x18003b0d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b0db  nop
0x18003b0dc  jmp     short loc_18003B10A
0x18003b0de  lea     rax, aCalculateserve; "CalculateServerPermissions(strPackageSi"...
0x18003b0e5  mov     edx, 306h; void *
0x18003b0ea  mov     dword ptr [rsp+0E0h+var_B8], ebx; char *
0x18003b0ee  lea     r8, aOnecoreAdminAp_30; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003b0f5  lea     r9, aOsintegrationD_269; "OSIntegration::DEH::Internal::ExeServer"...
0x18003b0fc  mov     [rsp+0E0h+var_C0], rax; char *
0x18003b101  mov     rcx, [rbp+5Fh]; this
0x18003b105  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003b10a  mov     eax, ebx
0x18003b10c  mov     rcx, [rbp+57h+var_38]
0x18003b110  xor     rcx, rsp; StackCookie
0x18003b113  call    __security_check_cookie
0x18003b118  mov     rbx, [rsp+0E0h+arg_18]
0x18003b120  add     rsp, 0B0h
0x18003b127  pop     r15
0x18003b129  pop     r14
0x18003b12b  pop     r13
0x18003b12d  pop     r12
0x18003b12f  pop     rdi
0x18003b130  pop     rsi
0x18003b131  pop     rbp
0x18003b132  retn
0x18003b133  lea     rax, aAttributesGetv_0; "_attributes->GetView(&(_properties.Cust"...
0x18003b13a  mov     edx, 308h
0x18003b13f  jmp     short loc_18003B0EA
0x18003b141  lea     rcx, [r14+98h]; string
0x18003b148  mov     rdx, [rbp+57h+var_A8]
0x18003b14c  call    ?InitializeFromStringArray@MultiString@@QEAAJPEAU?$IIterable@PEAUHSTRING__@@@Collections@Foundation@Windows@@@Z; MultiString::InitializeFromStringArray(Windows::Foundation::Collections::IIterable<HSTRING__ *> *)
0x18003b151  mov     ebx, eax
0x18003b153  test    eax, eax
0x18003b155  js      loc_18003B1F5
0x18003b15b  mov     rax, [r12]
0x18003b15f  lea     r9, [r14+28h]
0x18003b163  mov     r8, [r14+0E8h]
0x18003b16a  mov     rdx, [rbp+57h+string]
0x18003b16e  mov     rcx, r12
0x18003b171  mov     rax, [rax+100h]
0x18003b178  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b17d  mov     ebx, eax
0x18003b17f  test    eax, eax
0x18003b181  jns     short loc_18003B1CF
0x18003b183  mov     rcx, [rbp+5Fh]; this
0x18003b187  mov     dword ptr [rsp+0E0h+var_B8], eax; char *
0x18003b18b  lea     rax, aRegistrationst_15; "registrationStoreContext->CreateServerE"...
0x18003b192  mov     [rsp+0E0h+var_C0], rax; char *
0x18003b197  lea     r9, aOsintegrationD_269; "OSIntegration::DEH::Internal::ExeServer"...
0x18003b19e  lea     r8, aOnecoreAdminAp_30; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003b1a5  mov     edx, 312h; void *
0x18003b1aa  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003b1af  nop
0x18003b1b0  mov     rcx, [rbp+57h+var_A8]
0x18003b1b4  test    rcx, rcx
0x18003b1b7  jz      short loc_18003B1CA
0x18003b1b9  mov     [rbp+57h+var_A8], rsi
0x18003b1bd  mov     rax, [rcx]
0x18003b1c0  mov     rax, [rax+10h]
0x18003b1c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b1c9  nop
0x18003b1ca  jmp     loc_18003B10A
0x18003b1cf  test    r13b, r13b
0x18003b1d2  jnz     short loc_18003B226
0x18003b1d4  mov     rcx, [rbp+57h+var_A8]
0x18003b1d8  test    rcx, rcx
0x18003b1db  jz      short loc_18003B1EE
0x18003b1dd  mov     [rbp+57h+var_A8], rsi
0x18003b1e1  mov     rax, [rcx]
0x18003b1e4  mov     rax, [rax+10h]
0x18003b1e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b1ed  nop
0x18003b1ee  xor     eax, eax
0x18003b1f0  jmp     loc_18003B10C
0x18003b1f5  mov     rcx, [rbp+5Fh]; this
0x18003b1f9  mov     dword ptr [rsp+0E0h+var_B8], eax; char *
0x18003b1fd  lea     rax, aPropertiesActi; "_properties.ActivatableClasses.Initiali"...
0x18003b204  mov     [rsp+0E0h+var_C0], rax; char *
0x18003b209  lea     r9, aOsintegrationD_269; "OSIntegration::DEH::Internal::ExeServer"...
0x18003b210  lea     r8, aOnecoreAdminAp_30; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003b217  mov     edx, 30Eh; void *
0x18003b21c  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003b221  jmp     loc_18003B2AE
0x18003b226  mov     qword ptr [rbp+57h+length], rsi
0x18003b22a  mov     rax, [r15]
0x18003b22d  lea     rdx, [rbp+57h+length]
0x18003b231  mov     rcx, r15
0x18003b234  mov     rax, [rax+40h]
0x18003b238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b23d  mov     ebx, eax
0x18003b23f  test    eax, eax
0x18003b241  jns     short loc_18003B255
0x18003b243  mov     dword ptr [rsp+0E0h+var_B8], eax
0x18003b247  lea     rax, aIncomingpackag_6; "incomingPackage->GetMainPackageFamilyMo"...
0x18003b24e  mov     edx, 319h
0x18003b253  jmp     short loc_18003B284
0x18003b255  lea     rdx, [rbp+57h+length]; struct OpaqueString *
0x18003b259  lea     rcx, [rbp+57h+newString]; newString
0x18003b25d  call    ??0OpaqueString@@QEAA@AEBV0@@Z; OpaqueString::OpaqueString(OpaqueString const &)
0x18003b262  mov     rdx, rax
0x18003b265  lea     rcx, [r14+70h]
0x18003b269  call    ??$SetRegistrationProperty@VOpaqueString@@V1@@@YAJAEAU?$Optional@VOpaqueString@@@@VOpaqueString@@@Z; SetRegistrationProperty<OpaqueString,OpaqueString>(Optional<OpaqueString> &,OpaqueString)
0x18003b26e  mov     ebx, eax
0x18003b270  test    eax, eax
0x18003b272  jns     short loc_18003B2BC
0x18003b274  mov     dword ptr [rsp+0E0h+var_B8], eax; char *
0x18003b278  lea     rax, aSetregistratio_23; "SetRegistrationProperty( _properties.Ex"...
0x18003b27f  mov     edx, 31Bh; void *
0x18003b284  mov     [rsp+0E0h+var_C0], rax; char *
0x18003b289  lea     r9, aOsintegrationD_269; "OSIntegration::DEH::Internal::ExeServer"...
0x18003b290  lea     r8, aOnecoreAdminAp_30; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18003b297  mov     rcx, [rbp+5Fh]; this
0x18003b29b  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18003b2a0  mov     rcx, qword ptr [rbp+57h+length]; string
0x18003b2a4  call    cs:__imp_WindowsDeleteString
0x18003b2aa  mov     qword ptr [rbp+57h+length], rsi
0x18003b2ae  lea     rcx, [rbp+57h+var_A8]
0x18003b2b2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003b2b7  jmp     loc_18003B10A
0x18003b2bc  mov     rcx, qword ptr [rbp+57h+length]; string
0x18003b2c0  call    cs:__imp_WindowsDeleteString
0x18003b2c6  jmp     loc_18003B1D4
```
