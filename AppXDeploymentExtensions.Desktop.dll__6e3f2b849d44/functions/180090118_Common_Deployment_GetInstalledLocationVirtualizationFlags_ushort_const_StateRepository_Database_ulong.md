# Common::Deployment::GetInstalledLocationVirtualizationFlags(ushort const *,StateRepository::Database *,ulong &)

- ea: `0x180090118`
- end: `0x18009080d`
- name: `?GetInstalledLocationVirtualizationFlags@Deployment@Common@@YAJPEBGPEAVDatabase@StateRepository@@AEAK@Z`
- size: `1781`
- prototype: `__int64 __fastcall(Common::Deployment *this, struct StateRepository::Database *, struct StateRepository::Database *, unsigned int *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800aa10c`

## callees

- `0x180006970`
- `0x180012fc8`
- `0x18001adb4`
- `0x180046124`
- `0x180047410`
- `0x180059424`
- `0x18005dea4`
- `0x18005df00`
- `0x18005e510`
- `0x180087994`
- `0x180090118`
- `0x180090814`
- `0x1800aed10`
- `0x1800dd17c`
- `0x1800dd250`
- `0x1800eb4e0`
- `0x180192318`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180090577`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009065e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180090744`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180090577`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18009065e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180090744`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009054f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009063a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180090720`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009054f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009063a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180090720`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800904f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090535`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090602`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800906e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009075e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800904f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090535`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180090602`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800906e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009075e`

## string_xrefs

- `0x180090188`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x1800901d3`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x180090303`: `InstalledLocationVirtualization`
- `0x1800905b3`: `@DeletedItems`
- `0x1800903c1`: `UpdateActions`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Common::Deployment::GetInstalledLocationVirtualizationFlags(
        Common::Deployment *this,
        struct StateRepository::Database *a2,
        struct StateRepository::Database *a3,
        unsigned int *a4)
{
  const unsigned __int16 *v6; // rdx
  int v7; // eax
  const unsigned __int16 *v8; // r8
  unsigned int v9; // ebx
  int v10; // eax
  int Next; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64, __int64 *); // rbx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, __int64, __int64 *); // rbx
  int v20; // eax
  int v21; // eax
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, __int64, __int64 *); // rbx
  int v24; // eax
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, HSTRING *); // rbx
  int v27; // eax
  __int64 v28; // rdx
  const WCHAR *StringRawBuffer; // rax
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, __int64, __int64 *); // rbx
  __int64 v32; // rdi
  __int64 (__fastcall *v33)(__int64, HSTRING *); // rbx
  const WCHAR *v34; // rax
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, __int64, __int64 *); // rbx
  __int64 v37; // rdi
  __int64 (__fastcall *v38)(__int64, HSTRING *); // rbx
  const WCHAR *v39; // rax
  struct IInspectable *bIgnoreCase; // [rsp+20h] [rbp-E0h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  bool v43; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v45; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v46; // [rsp+48h] [rbp-B8h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v47; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v48; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v49; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v50; // [rsp+68h] [rbp-98h] BYREF
  __int64 v51; // [rsp+70h] [rbp-90h] BYREF
  __int64 v52; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v53[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v54[216]; // [rsp+90h] [rbp-70h] BYREF
  void *v55; // [rsp+168h] [rbp+68h]
  unsigned __int64 v56; // [rsp+170h] [rbp+70h]
  __int64 v57[11]; // [rsp+180h] [rbp+80h] BYREF
  int v58; // [rsp+1D8h] [rbp+D8h]
  HSTRING_HEADER hstringHeader; // [rsp+290h] [rbp+190h] BYREF
  __int64 v60; // [rsp+2A8h] [rbp+1A8h]
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  *(_DWORD *)a3 = 0;
  StateRepository::Entity::Package::Package((StateRepository::Entity::Package *)v57);
  StateRepository::Entity::PackageExtension::PackageExtension((StateRepository::Entity::PackageExtension *)v54);
  v7 = StateRepository::Entity::Package::GetByPackageFullName(a2, v6, (struct StateRepository::Entity::Package *)v57);
  v9 = v7;
  if ( v7 >= 0 )
  {
    if ( (v58 & 0x4000000) != 0 )
    {
      v43 = 0;
      v45 = 0;
      v10 = StateRepository::Entity::PackageExtension::FindByPackageAndCategory(
              a2,
              v57[0],
              v8,
              (struct StateRepository::Statement *)&v45);
      if ( v10 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xBA4,
          (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
          (const char *)(unsigned int)v10,
          (int)bIgnoreCase);
      Next = StateRepository::Entity::PackageExtension::FindNext(
               (struct StateRepository::Statement *)&v45,
               (struct StateRepository::Entity::PackageExtension *)v54,
               &v43);
      v9 = Next;
      if ( Next < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBA5,
          (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
          (const char *)(unsigned int)Next,
          (int)bIgnoreCase);
LABEL_8:
        StateRepository::Statement::~Statement((StateRepository::Statement *)&v45);
        goto LABEL_51;
      }
      if ( v43 )
      {
        v47 = 0;
        v50 = 0;
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v47);
        v12 = StateRepository::DictionarySerialization::WinRTReader::DeserializeAsPropertySet(
                (StateRepository::DictionarySerialization::WinRTReader *)&v50,
                v56,
                v55,
                &v47,
                bIgnoreCase);
        v9 = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBAE,
            (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
            (const char *)(unsigned int)v12,
            bIgnoreCasea);
LABEL_12:
          wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v50);
          Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v47);
          goto LABEL_8;
        }
        v49 = 0;
        v13 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
                &v47,
                &v49);
        v9 = v13;
        if ( v13 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBB1,
            (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
            (const char *)(unsigned int)v13,
            bIgnoreCasea);
LABEL_15:
          Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v49);
          goto LABEL_12;
        }
        v48 = 0;
        v14 = v49;
        v15 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v49 + 48LL);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v48);
        v60 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"InstalledLocationVirtualization",
          0x20u,
          0x1Fu);
        v16 = v15(v14, v60, &v48);
        v9 = v16;
        if ( v16 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBB6,
            (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
            (const char *)(unsigned int)v16,
            bIgnoreCasea);
LABEL_18:
          Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v48);
          goto LABEL_15;
        }
        v53[0] = 0;
        v17 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
                &v48,
                v53);
        v9 = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBB9,
            (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
            (const char *)(unsigned int)v17,
            bIgnoreCasea);
LABEL_21:
          Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(v53);
          goto LABEL_18;
        }
        v52 = 0;
        v18 = v53[0];
        v19 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v53[0] + 48LL);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v52);
        v60 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UpdateActions", 0xEu, 0xDu);
        v20 = v19(v18, v60, &v52);
        v9 = v20;
        if ( v20 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBBC,
            (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
            (const char *)(unsigned int)v20,
            bIgnoreCasea);
LABEL_24:
          Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v52);
          goto LABEL_21;
        }
        v51 = 0;
        v21 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
                &v52,
                &v51);
        v9 = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBBF,
            (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
            (const char *)(unsigned int)v21,
            bIgnoreCasea);
LABEL_27:
          Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v51);
          goto LABEL_24;
        }
        v46 = 0;
        v22 = v51;
        v23 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v51 + 48LL);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v46);
        v60 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"@AddedItems", 0xCu, 0xBu);
        v24 = v23(v22, v60, &v46);
        v9 = v24;
        if ( v24 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBC2,
            (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
            (const char *)(unsigned int)v24,
            bIgnoreCasea);
LABEL_30:
          Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v46);
          goto LABEL_27;
        }
        string = 0;
        v25 = v46;
        v26 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v46 + 152LL);
        WindowsDeleteString(0);
        string = 0;
        v27 = v26(v25, &string);
        v9 = v27;
        if ( v27 < 0 )
        {
          v28 = 3013;
LABEL_33:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v28,
            (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
            (const char *)(unsigned int)v27,
            bIgnoreCasea);
          WindowsDeleteString(string);
          string = 0;
          goto LABEL_30;
        }
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        if ( CompareStringOrdinal(StringRawBuffer, -1, L"reset", -1, 1) == 2 )
          *(_DWORD *)a3 |= 4u;
        v30 = v51;
        v31 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v51 + 48LL);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v46);
        v60 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"@DeletedItems", 0xEu, 0xDu);
        v27 = v31(v30, v60, &v46);
        v9 = v27;
        if ( v27 < 0 )
        {
          v28 = 3020;
          goto LABEL_33;
        }
        v32 = v46;
        v33 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v46 + 152LL);
        WindowsDeleteString(string);
        string = 0;
        v27 = v33(v32, &string);
        v9 = v27;
        if ( v27 < 0 )
        {
          v28 = 3022;
          goto LABEL_33;
        }
        v34 = WindowsGetStringRawBuffer(string, 0);
        if ( CompareStringOrdinal(v34, -1, L"reset", -1, 1) == 2 )
          *(_DWORD *)a3 |= 2u;
        v35 = v51;
        v36 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v51 + 48LL);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v46);
        v60 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"@ModifiedItems", 0xFu, 0xEu);
        v27 = v36(v35, v60, &v46);
        v9 = v27;
        if ( v27 < 0 )
        {
          v28 = 3029;
          goto LABEL_33;
        }
        v37 = v46;
        v38 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v46 + 152LL);
        WindowsDeleteString(string);
        string = 0;
        v27 = v38(v37, &string);
        v9 = v27;
        if ( v27 < 0 )
        {
          v28 = 3031;
          goto LABEL_33;
        }
        v39 = WindowsGetStringRawBuffer(string, 0);
        if ( CompareStringOrdinal(v39, -1, L"reset", -1, 1) == 2 )
          *(_DWORD *)a3 |= 1u;
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v46);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v51);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v52);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(v53);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v48);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v49);
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v50);
        Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(&v47);
      }
      StateRepository::Statement::~Statement((StateRepository::Statement *)&v45);
    }
    v9 = 0;
    goto LABEL_51;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB99,
    (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
    (const char *)(unsigned int)v7,
    (int)bIgnoreCase);
LABEL_51:
  StateRepository::Entity::PackageExtension::~PackageExtension((StateRepository::Entity::PackageExtension *)v54);
  StateRepository::Entity::Package::~Package((StateRepository::Entity::Package *)v57);
  return v9;
}

```

## disassembly

```asm
0x180090118  push    rbp
0x18009011a  push    rbx
0x18009011b  push    rsi
0x18009011c  push    rdi
0x18009011d  push    r12
0x18009011f  push    r14
0x180090121  push    r15
0x180090123  lea     rbp, [rsp-1C0h]
0x18009012b  sub     rsp, 2C0h
0x180090132  mov     rax, cs:__security_cookie
0x180090139  xor     rax, rsp
0x18009013c  mov     [rbp+1F0h+var_40], rax
0x180090143  mov     r14, r8
0x180090146  mov     rdi, rdx
0x180090149  mov     rdx, rcx
0x18009014c  xor     r15d, r15d
0x18009014f  mov     [r8], r15d
0x180090152  lea     rcx, [rbp+1F0h+var_170]; this
0x180090159  call    ??0Package@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Package::Package(void)
0x18009015e  nop
0x18009015f  lea     rcx, [rbp+1F0h+var_260]; this
0x180090163  call    ??0PackageExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::PackageExtension::PackageExtension(void)
0x180090168  nop
0x180090169  lea     r8, [rbp+1F0h+var_170]; struct StateRepository::Entity::Package *
0x180090170  mov     rcx, rdi; struct StateRepository::Database *
0x180090173  call    ?GetByPackageFullName@Package@Entity@StateRepository@@SAJAEAVDatabase@3@PEBGAEAV123@@Z; StateRepository::Entity::Package::GetByPackageFullName(StateRepository::Database &,ushort const *,StateRepository::Entity::Package &)
0x180090178  mov     ebx, eax
0x18009017a  test    eax, eax
0x18009017c  jns     short loc_18009019E
0x18009017e  mov     rcx, [rbp+1F8h]; this
0x180090185  mov     r9d, eax; char *
0x180090188  lea     r8, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x18009018f  mov     edx, 0B99h; void *
0x180090194  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090199  jmp     loc_1800907D3
0x18009019e  test    [rbp+1F0h+var_118], 4000000h
0x1800901a8  jz      loc_1800907D0
0x1800901ae  mov     [rsp+2F0h+var_2C0], r15b
0x1800901b3  mov     [rsp+2F0h+var_2B0], r15
0x1800901b8  lea     r9, [rsp+2F0h+var_2B0]; struct StateRepository::Statement *
0x1800901bd  mov     rdx, [rbp+1F0h+var_170]; __int64
0x1800901c4  mov     rcx, rdi; struct StateRepository::Database *
0x1800901c7  call    ?FindByPackageAndCategory@PackageExtension@Entity@StateRepository@@SAJAEAVDatabase@3@_JPEBGAEAVStatement@3@@Z; StateRepository::Entity::PackageExtension::FindByPackageAndCategory(StateRepository::Database &,__int64,ushort const *,StateRepository::Statement &)
0x1800901cc  mov     rcx, [rbp+1F8h]; this
0x1800901d3  lea     rsi, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x1800901da  test    eax, eax
0x1800901dc  jns     short loc_1800901EE
0x1800901de  mov     r9d, eax; char *
0x1800901e1  mov     r8, rsi; unsigned int
0x1800901e4  mov     edx, 0BA4h; void *
0x1800901e9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800901ee  lea     r8, [rsp+2F0h+var_2C0]; bool *
0x1800901f3  lea     rdx, [rbp+1F0h+var_260]; struct StateRepository::Entity::PackageExtension *
0x1800901f7  lea     rcx, [rsp+2F0h+var_2B0]; struct StateRepository::Statement *
0x1800901fc  call    ?FindNext@PackageExtension@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::PackageExtension::FindNext(StateRepository::Statement &,StateRepository::Entity::PackageExtension &,bool &)
0x180090201  mov     ebx, eax
0x180090203  test    eax, eax
0x180090205  jns     short loc_18009022E
0x180090207  mov     rcx, [rbp+1F8h]; this
0x18009020e  mov     r9d, eax; char *
0x180090211  mov     r8, rsi; unsigned int
0x180090214  mov     edx, 0BA5h; void *
0x180090219  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009021e  nop
0x18009021f  lea     rcx, [rsp+2F0h+var_2B0]; this
0x180090224  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180090229  jmp     loc_1800907D3
0x18009022e  cmp     [rsp+2F0h+var_2C0], r15b
0x180090233  jz      loc_1800907C6
0x180090239  mov     [rsp+2F0h+var_2A0], r15
0x18009023e  mov     [rsp+2F0h+var_288], r15
0x180090243  lea     rcx, [rsp+2F0h+var_2A0]
0x180090248  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x18009024d  lea     r9, [rsp+2F0h+var_2A0]; struct Windows::Foundation::Collections::IPropertySet **
0x180090252  mov     r8, [rbp+1F0h+var_188]; void *
0x180090256  mov     rdx, [rbp+1F0h+var_180]; unsigned __int64
0x18009025a  lea     rcx, [rsp+2F0h+var_288]; this
0x18009025f  call    ?DeserializeAsPropertySet@WinRTReader@DictionarySerialization@StateRepository@@QEAAJ_KPEBXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEA_K@Z; StateRepository::DictionarySerialization::WinRTReader::DeserializeAsPropertySet(unsigned __int64,void const *,Windows::Foundation::Collections::IPropertySet * *,unsigned __int64 *)
0x180090264  mov     ebx, eax
0x180090266  test    eax, eax
0x180090268  jns     short loc_180090299
0x18009026a  mov     rcx, [rbp+1F8h]; this
0x180090271  mov     r9d, eax; char *
0x180090274  mov     r8, rsi; unsigned int
0x180090277  mov     edx, 0BAEh; void *
0x18009027c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090281  nop
0x180090282  lea     rcx, [rsp+2F0h+var_288]
0x180090287  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18009028c  nop
0x18009028d  lea     rcx, [rsp+2F0h+var_2A0]
0x180090292  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180090297  jmp     short loc_18009021F
0x180090299  mov     [rsp+2F0h+var_290], r15
0x18009029e  lea     rdx, [rsp+2F0h+var_290]
0x1800902a3  lea     rcx, [rsp+2F0h+var_2A0]
0x1800902a8  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x1800902ad  mov     ebx, eax
0x1800902af  test    eax, eax
0x1800902b1  jns     short loc_1800902D7
0x1800902b3  mov     rcx, [rbp+1F8h]; this
0x1800902ba  mov     r9d, eax; char *
0x1800902bd  mov     r8, rsi; unsigned int
0x1800902c0  mov     edx, 0BB1h; void *
0x1800902c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800902ca  nop
0x1800902cb  lea     rcx, [rsp+2F0h+var_290]
0x1800902d0  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800902d5  jmp     short loc_180090282
0x1800902d7  mov     [rsp+2F0h+var_298], r15
0x1800902dc  mov     rdi, [rsp+2F0h+var_290]
0x1800902e1  mov     rax, [rdi]
0x1800902e4  mov     rbx, [rax+30h]
0x1800902e8  lea     rcx, [rsp+2F0h+var_298]
0x1800902ed  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800902f2  mov     [rbp+1F0h+var_48], r15
0x1800902f9  mov     r9d, 1Fh; unsigned int
0x1800902ff  lea     r8d, [r9+1]; unsigned int
0x180090303  lea     rdx, ?InstalledLocationVirtualization@ElementNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "InstalledLocationVirtualization"
0x18009030a  lea     rcx, [rbp+1F0h+hstringHeader]; hstringHeader
0x180090311  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180090316  nop
0x180090317  lea     r8, [rsp+2F0h+var_298]
0x18009031c  mov     rdx, [rbp+1F0h+var_48]
0x180090323  mov     rcx, rdi
0x180090326  mov     rax, rbx
0x180090329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009032e  mov     ebx, eax
0x180090330  test    eax, eax
0x180090332  jns     short loc_18009035B
0x180090334  mov     rcx, [rbp+1F8h]; this
0x18009033b  mov     r9d, eax; char *
0x18009033e  mov     r8, rsi; unsigned int
0x180090341  mov     edx, 0BB6h; void *
0x180090346  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009034b  nop
0x18009034c  lea     rcx, [rsp+2F0h+var_298]
0x180090351  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180090356  jmp     loc_1800902CB
0x18009035b  mov     [rbp+1F0h+var_270], r15
0x18009035f  lea     rdx, [rbp+1F0h+var_270]
0x180090363  lea     rcx, [rsp+2F0h+var_298]
0x180090368  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x18009036d  mov     ebx, eax
0x18009036f  test    eax, eax
0x180090371  jns     short loc_180090396
0x180090373  mov     rcx, [rbp+1F8h]; this
0x18009037a  mov     r9d, eax; char *
0x18009037d  mov     r8, rsi; unsigned int
0x180090380  mov     edx, 0BB9h; void *
0x180090385  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009038a  nop
0x18009038b  lea     rcx, [rbp+1F0h+var_270]
0x18009038f  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180090394  jmp     short loc_18009034C
0x180090396  mov     [rsp+2F0h+var_278], r15
0x18009039b  mov     rdi, [rbp+1F0h+var_270]
0x18009039f  mov     rax, [rdi]
0x1800903a2  mov     rbx, [rax+30h]
0x1800903a6  lea     rcx, [rsp+2F0h+var_278]
0x1800903ab  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800903b0  mov     [rbp+1F0h+var_48], r15
0x1800903b7  mov     r9d, 0Dh; unsigned int
0x1800903bd  lea     r8d, [r9+1]; unsigned int
0x1800903c1  lea     rdx, aUpdateactions; "UpdateActions"
0x1800903c8  lea     rcx, [rbp+1F0h+hstringHeader]; hstringHeader
0x1800903cf  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800903d4  nop
0x1800903d5  lea     r8, [rsp+2F0h+var_278]
0x1800903da  mov     rdx, [rbp+1F0h+var_48]
0x1800903e1  mov     rcx, rdi
0x1800903e4  mov     rax, rbx
0x1800903e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800903ec  mov     ebx, eax
0x1800903ee  test    eax, eax
0x1800903f0  jns     short loc_180090419
0x1800903f2  mov     rcx, [rbp+1F8h]; this
0x1800903f9  mov     r9d, eax; char *
0x1800903fc  mov     r8, rsi; unsigned int
0x1800903ff  mov     edx, 0BBCh; void *
0x180090404  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180090409  nop
0x18009040a  lea     rcx, [rsp+2F0h+var_278]
0x18009040f  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180090414  jmp     loc_18009038B
0x180090419  mov     [rsp+2F0h+var_280], r15
0x18009041e  lea     rdx, [rsp+2F0h+var_280]
0x180090423  lea     rcx, [rsp+2F0h+var_278]
0x180090428  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x18009042d  mov     ebx, eax
0x18009042f  test    eax, eax
0x180090431  jns     short loc_180090457
0x180090433  mov     rcx, [rbp+1F8h]; this
0x18009043a  mov     r9d, eax; char *
0x18009043d  mov     r8, rsi; unsigned int
0x180090440  mov     edx, 0BBFh; void *
0x180090445  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009044a  nop
0x18009044b  lea     rcx, [rsp+2F0h+var_280]
0x180090450  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180090455  jmp     short loc_18009040A
0x180090457  mov     [rsp+2F0h+var_2A8], r15
0x18009045c  mov     rdi, [rsp+2F0h+var_280]
0x180090461  mov     rax, [rdi]
0x180090464  mov     rbx, [rax+30h]
0x180090468  lea     rcx, [rsp+2F0h+var_2A8]
0x18009046d  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x180090472  mov     [rbp+1F0h+var_48], r15
0x180090479  mov     r9d, 0Bh; unsigned int
0x18009047f  lea     r8d, [r9+1]; unsigned int
0x180090483  lea     rdx, aAddeditems; "@AddedItems"
0x18009048a  lea     rcx, [rbp+1F0h+hstringHeader]; hstringHeader
0x180090491  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180090496  nop
0x180090497  lea     r8, [rsp+2F0h+var_2A8]
0x18009049c  mov     rdx, [rbp+1F0h+var_48]
0x1800904a3  mov     rcx, rdi
0x1800904a6  mov     rax, rbx
0x1800904a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800904ae  mov     ebx, eax
0x1800904b0  test    eax, eax
0x1800904b2  jns     short loc_1800904DB
0x1800904b4  mov     rcx, [rbp+1F8h]; this
0x1800904bb  mov     r9d, eax; char *
0x1800904be  mov     r8, rsi; unsigned int
0x1800904c1  mov     edx, 0BC2h; void *
0x1800904c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800904cb  nop
0x1800904cc  lea     rcx, [rsp+2F0h+var_2A8]
0x1800904d1  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800904d6  jmp     loc_18009044B
0x1800904db  mov     [rsp+2F0h+string], r15
0x1800904e0  mov     rdi, [rsp+2F0h+var_2A8]
0x1800904e5  mov     rax, [rdi]
0x1800904e8  mov     rbx, [rax+98h]
0x1800904ef  xor     ecx, ecx; string
0x1800904f1  call    cs:__imp_WindowsDeleteString
0x1800904f8  nop     dword ptr [rax+rax+00h]
0x1800904fd  mov     [rsp+2F0h+string], r15
0x180090502  lea     rdx, [rsp+2F0h+string]
0x180090507  mov     rcx, rdi
0x18009050a  mov     rax, rbx
0x18009050d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090512  mov     ebx, eax
0x180090514  test    eax, eax
0x180090516  jns     short loc_180090548
0x180090518  mov     edx, 0BC5h; void *
0x18009051d  mov     rcx, [rbp+1F8h]; this
0x180090524  mov     r9d, eax; char *
0x180090527  mov     r8, rsi; unsigned int
0x18009052a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009052f  nop
0x180090530  mov     rcx, [rsp+2F0h+string]; string
0x180090535  call    cs:__imp_WindowsDeleteString
0x18009053c  nop     dword ptr [rax+rax+00h]
0x180090541  mov     [rsp+2F0h+string], r15
0x180090546  jmp     short loc_1800904CC
0x180090548  xor     edx, edx; length
0x18009054a  mov     rcx, [rsp+2F0h+string]; string
0x18009054f  call    cs:__imp_WindowsGetStringRawBuffer
0x180090556  nop     dword ptr [rax+rax+00h]
0x18009055b  mov     [rsp+2F0h+bIgnoreCase], 1; bIgnoreCase
0x180090563  or      r12d, 0FFFFFFFFh
0x180090567  mov     r9d, r12d; cchCount2
0x18009056a  lea     r8, aReset; "reset"
0x180090571  mov     edx, r12d; cchCount1
0x180090574  mov     rcx, rax; lpString1
0x180090577  call    cs:__imp_CompareStringOrdinal
0x18009057e  nop     dword ptr [rax+rax+00h]
0x180090583  cmp     eax, 2
0x180090586  jnz     short loc_18009058C
0x180090588  or      dword ptr [r14], 4
0x18009058c  mov     rdi, [rsp+2F0h+var_280]
0x180090591  mov     rax, [rdi]
0x180090594  mov     rbx, [rax+30h]
0x180090598  lea     rcx, [rsp+2F0h+var_2A8]
0x18009059d  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x1800905a2  mov     [rbp+1F0h+var_48], r15
0x1800905a9  mov     r9d, 0Dh; unsigned int
0x1800905af  lea     r8d, [r9+1]; unsigned int
0x1800905b3  lea     rdx, aDeleteditems_0; "@DeletedItems"
0x1800905ba  lea     rcx, [rbp+1F0h+hstringHeader]; hstringHeader
0x1800905c1  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800905c6  nop
0x1800905c7  lea     r8, [rsp+2F0h+var_2A8]
0x1800905cc  mov     rdx, [rbp+1F0h+var_48]
0x1800905d3  mov     rcx, rdi
0x1800905d6  mov     rax, rbx
0x1800905d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800905de  mov     ebx, eax
0x1800905e0  test    eax, eax
0x1800905e2  jns     short loc_1800905EE
0x1800905e4  mov     edx, 0BCCh
0x1800905e9  jmp     loc_18009051D
0x1800905ee  mov     rdi, [rsp+2F0h+var_2A8]
0x1800905f3  mov     rax, [rdi]
0x1800905f6  mov     rbx, [rax+98h]
0x1800905fd  mov     rcx, [rsp+2F0h+string]; string
0x180090602  call    cs:__imp_WindowsDeleteString
0x180090609  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
