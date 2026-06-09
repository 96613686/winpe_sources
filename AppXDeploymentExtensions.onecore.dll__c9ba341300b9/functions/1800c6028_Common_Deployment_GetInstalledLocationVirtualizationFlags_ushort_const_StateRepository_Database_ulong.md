# Common::Deployment::GetInstalledLocationVirtualizationFlags(ushort const *,StateRepository::Database *,ulong &)

- ea: `0x1800c6028`
- end: `0x1800c66e1`
- name: `?GetInstalledLocationVirtualizationFlags@Deployment@Common@@YAJPEBGPEAVDatabase@StateRepository@@AEAK@Z`
- size: `1721`
- prototype: `int(Common::Deployment *__hidden this, const unsigned __int16 *, struct StateRepository::Database *, unsigned int *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180069b90`

## callees

- `0x18000b3bc`
- `0x180027364`
- `0x18002aa6c`
- `0x18002ab68`
- `0x18002cb58`
- `0x18002cbe4`
- `0x180030344`
- `0x180077608`
- `0x18007b440`
- `0x18008f95c`
- `0x18008fbb0`
- `0x180098bf4`
- `0x1800a219c`
- `0x1800c6028`
- `0x1800f0260`
- `0x18012504c`
- `0x18017d1b0`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c647c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c6551`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c6625`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c647c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c6551`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800c6625`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c645a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c6533`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c6607`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c645a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c6533`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c6607`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c6408`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c6446`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c6501`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c65d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c6639`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c6408`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c6446`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c6501`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c65d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c6639`

## string_xrefs

- `0x1800c6098`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x1800c60ea`: `onecore\admin\appmodel\common\utilities.cpp`
- `0x1800c60cd`: `windows.installedLocationVirtualization`
- `0x1800c621a`: `InstalledLocationVirtualization`
- `0x1800c62d8`: `UpdateActions`
- `0x1800c64b2`: `@DeletedItems`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall Common::Deployment::GetInstalledLocationVirtualizationFlags(
        Common::Deployment *this,
        struct StateRepository::Database *a2,
        struct StateRepository::Database *a3,
        unsigned int *a4)
{
  const unsigned __int16 *v6; // rdx
  int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  int Next; // eax
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64, _QWORD); // rbx
  int v15; // eax
  int v16; // eax
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, __int64, _QWORD); // rbx
  int v19; // eax
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64, __int64 *); // rbx
  int v23; // eax
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, HSTRING *); // rbx
  int v26; // eax
  __int64 v27; // rdx
  const WCHAR *StringRawBuffer; // rax
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, __int64, __int64 *); // rbx
  __int64 v31; // rdi
  __int64 (__fastcall *v32)(__int64, HSTRING *); // rbx
  const WCHAR *v33; // rax
  __int64 v34; // rdi
  __int64 (__fastcall *v35)(__int64, __int64, __int64 *); // rbx
  __int64 v36; // rdi
  __int64 (__fastcall *v37)(__int64, HSTRING *); // rbx
  const WCHAR *v38; // rax
  struct IInspectable *bIgnoreCase; // [rsp+20h] [rbp-E0h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  bool v42; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v44; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v45; // [rsp+48h] [rbp-B8h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v46; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v47)(_QWORD, GUID *, __int64); // [rsp+58h] [rbp-A8h] BYREF
  __int64 v48; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v49; // [rsp+68h] [rbp-98h] BYREF
  __int64 v50; // [rsp+70h] [rbp-90h] BYREF
  __int64 (__fastcall ***v51)(_QWORD, GUID *, __int64); // [rsp+78h] [rbp-88h] BYREF
  _QWORD v52[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v53[216]; // [rsp+90h] [rbp-70h] BYREF
  void *v54; // [rsp+168h] [rbp+68h]
  unsigned __int64 v55; // [rsp+170h] [rbp+70h]
  __int64 v56[11]; // [rsp+180h] [rbp+80h] BYREF
  int v57; // [rsp+1D8h] [rbp+D8h]
  HSTRING_HEADER hstringHeader; // [rsp+290h] [rbp+190h] BYREF
  __int64 v59; // [rsp+2A8h] [rbp+1A8h]
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  *(_DWORD *)a3 = 0;
  StateRepository::Entity::Package::Package((StateRepository::Entity::Package *)v56);
  StateRepository::Entity::PackageExtension::PackageExtension((StateRepository::Entity::PackageExtension *)v53);
  v7 = StateRepository::Entity::Package::GetByPackageFullName(a2, v6, (struct StateRepository::Entity::Package *)v56);
  v8 = v7;
  if ( v7 >= 0 )
  {
    if ( (v57 & 0x4000000) != 0 )
    {
      v42 = 0;
      v44 = 0;
      v9 = StateRepository::Entity::PackageExtension::FindByPackageAndCategory(
             a2,
             v56[0],
             L"windows.installedLocationVirtualization",
             (struct StateRepository::Statement *)&v44);
      if ( v9 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xBA4,
          (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
          (const char *)(unsigned int)v9,
          (int)bIgnoreCase);
      Next = StateRepository::Entity::PackageExtension::FindNext(
               (struct StateRepository::Statement *)&v44,
               (struct StateRepository::Entity::PackageExtension *)v53,
               &v42);
      v8 = Next;
      if ( Next < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBA5,
          (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
          (const char *)(unsigned int)Next,
          (int)bIgnoreCase);
LABEL_8:
        StateRepository::Statement::~Statement((StateRepository::Statement *)&v44);
        goto LABEL_51;
      }
      if ( v42 )
      {
        v46 = 0;
        v49 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
        v11 = StateRepository::DictionarySerialization::WinRTReader::DeserializeAsPropertySet(
                (StateRepository::DictionarySerialization::WinRTReader *)&v49,
                v55,
                v54,
                &v46,
                bIgnoreCase);
        v8 = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBAE,
            (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
            (const char *)(unsigned int)v11,
            bIgnoreCasea);
LABEL_12:
          wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v49);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
          goto LABEL_8;
        }
        v48 = 0;
        v12 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
                (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v46,
                (__int64)&v48);
        v8 = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBB1,
            (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
            (const char *)(unsigned int)v12,
            bIgnoreCasea);
LABEL_15:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
          goto LABEL_12;
        }
        v47 = 0;
        v13 = v48;
        v14 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v48 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
        v59 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"InstalledLocationVirtualization",
          0x20u,
          0x1Fu);
        v15 = v14(v13, v59, &v47);
        v8 = v15;
        if ( v15 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBB6,
            (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
            (const char *)(unsigned int)v15,
            bIgnoreCasea);
LABEL_18:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
          goto LABEL_15;
        }
        v52[0] = 0;
        v16 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
                &v47,
                (__int64)v52);
        v8 = v16;
        if ( v16 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBB9,
            (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
            (const char *)(unsigned int)v16,
            bIgnoreCasea);
LABEL_21:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v52);
          goto LABEL_18;
        }
        v51 = 0;
        v17 = v52[0];
        v18 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v52[0] + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
        v59 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"UpdateActions", 0xEu, 0xDu);
        v19 = v18(v17, v59, &v51);
        v8 = v19;
        if ( v19 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBBC,
            (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
            (const char *)(unsigned int)v19,
            bIgnoreCasea);
LABEL_24:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
          goto LABEL_21;
        }
        v50 = 0;
        v20 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
                &v51,
                (__int64)&v50);
        v8 = v20;
        if ( v20 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBBF,
            (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
            (const char *)(unsigned int)v20,
            bIgnoreCasea);
LABEL_27:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
          goto LABEL_24;
        }
        v45 = 0;
        v21 = v50;
        v22 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v50 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
        v59 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"@AddedItems", 0xCu, 0xBu);
        v23 = v22(v21, v59, &v45);
        v8 = v23;
        if ( v23 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xBC2,
            (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
            (const char *)(unsigned int)v23,
            bIgnoreCasea);
LABEL_30:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
          goto LABEL_27;
        }
        string = 0;
        v24 = v45;
        v25 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v45 + 152LL);
        WindowsDeleteString(0);
        string = 0;
        v26 = v25(v24, &string);
        v8 = v26;
        if ( v26 < 0 )
        {
          v27 = 3013;
LABEL_33:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v27,
            (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
            (const char *)(unsigned int)v26,
            bIgnoreCasea);
          WindowsDeleteString(string);
          string = 0;
          goto LABEL_30;
        }
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        if ( CompareStringOrdinal(StringRawBuffer, -1, L"reset", -1, 1) == 2 )
          *(_DWORD *)a3 |= 4u;
        v29 = v50;
        v30 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v50 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
        v59 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"@DeletedItems", 0xEu, 0xDu);
        v26 = v30(v29, v59, &v45);
        v8 = v26;
        if ( v26 < 0 )
        {
          v27 = 3020;
          goto LABEL_33;
        }
        v31 = v45;
        v32 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v45 + 152LL);
        WindowsDeleteString(string);
        string = 0;
        v26 = v32(v31, &string);
        v8 = v26;
        if ( v26 < 0 )
        {
          v27 = 3022;
          goto LABEL_33;
        }
        v33 = WindowsGetStringRawBuffer(string, 0);
        if ( CompareStringOrdinal(v33, -1, L"reset", -1, 1) == 2 )
          *(_DWORD *)a3 |= 2u;
        v34 = v50;
        v35 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v50 + 48LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
        v59 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"@ModifiedItems", 0xFu, 0xEu);
        v26 = v35(v34, v59, &v45);
        v8 = v26;
        if ( v26 < 0 )
        {
          v27 = 3029;
          goto LABEL_33;
        }
        v36 = v45;
        v37 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v45 + 152LL);
        WindowsDeleteString(string);
        string = 0;
        v26 = v37(v36, &string);
        v8 = v26;
        if ( v26 < 0 )
        {
          v27 = 3031;
          goto LABEL_33;
        }
        v38 = WindowsGetStringRawBuffer(string, 0);
        if ( CompareStringOrdinal(v38, -1, L"reset", -1, 1) == 2 )
          *(_DWORD *)a3 |= 1u;
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v52);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v49);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46);
      }
      StateRepository::Statement::~Statement((StateRepository::Statement *)&v44);
    }
    v8 = 0;
    goto LABEL_51;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB99,
    (unsigned int)"onecore\\admin\\appmodel\\common\\utilities.cpp",
    (const char *)(unsigned int)v7,
    (int)bIgnoreCase);
LABEL_51:
  StateRepository::Entity::PackageExtension::~PackageExtension((StateRepository::Entity::PackageExtension *)v53);
  StateRepository::Entity::Package::~Package((StateRepository::Entity::Package *)v56);
  return v8;
}

```

## disassembly

```asm
0x1800c6028  push    rbp
0x1800c602a  push    rbx
0x1800c602b  push    rsi
0x1800c602c  push    rdi
0x1800c602d  push    r12
0x1800c602f  push    r14
0x1800c6031  push    r15
0x1800c6033  lea     rbp, [rsp-1C0h]
0x1800c603b  sub     rsp, 2C0h
0x1800c6042  mov     rax, cs:__security_cookie
0x1800c6049  xor     rax, rsp
0x1800c604c  mov     [rbp+1F0h+var_40], rax
0x1800c6053  mov     r14, r8
0x1800c6056  mov     rdi, rdx
0x1800c6059  mov     rdx, rcx
0x1800c605c  xor     r15d, r15d
0x1800c605f  mov     [r8], r15d
0x1800c6062  lea     rcx, [rbp+1F0h+var_170]; this
0x1800c6069  call    ??0Package@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::Package::Package(void)
0x1800c606e  nop
0x1800c606f  lea     rcx, [rbp+1F0h+var_260]; this
0x1800c6073  call    ??0PackageExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::PackageExtension::PackageExtension(void)
0x1800c6078  nop
0x1800c6079  lea     r8, [rbp+1F0h+var_170]; struct StateRepository::Entity::Package *
0x1800c6080  mov     rcx, rdi; struct StateRepository::Database *
0x1800c6083  call    ?GetByPackageFullName@Package@Entity@StateRepository@@SAJAEAVDatabase@3@PEBGAEAV123@@Z; StateRepository::Entity::Package::GetByPackageFullName(StateRepository::Database &,ushort const *,StateRepository::Entity::Package &)
0x1800c6088  mov     ebx, eax
0x1800c608a  test    eax, eax
0x1800c608c  jns     short loc_1800C60AE
0x1800c608e  mov     rcx, [rbp+1F8h]; this
0x1800c6095  mov     r9d, eax; char *
0x1800c6098  lea     r8, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x1800c609f  mov     edx, 0B99h; void *
0x1800c60a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c60a9  jmp     loc_1800C66A8
0x1800c60ae  test    [rbp+1F0h+var_118], 4000000h
0x1800c60b8  jz      loc_1800C66A5
0x1800c60be  mov     [rsp+2F0h+var_2C0], r15b
0x1800c60c3  mov     [rsp+2F0h+var_2B0], r15
0x1800c60c8  lea     r9, [rsp+2F0h+var_2B0]; struct StateRepository::Statement *
0x1800c60cd  lea     r8, ?ExtensionCategoryInstalledLocationVirtualization@Attribute@Manifest@Packaging@Appx@@3QBGB; "windows.installedLocationVirtualization"
0x1800c60d4  mov     rdx, [rbp+1F0h+var_170]; __int64
0x1800c60db  mov     rcx, rdi; struct StateRepository::Database *
0x1800c60de  call    ?FindByPackageAndCategory@PackageExtension@Entity@StateRepository@@SAJAEAVDatabase@3@_JPEBGAEAVStatement@3@@Z; StateRepository::Entity::PackageExtension::FindByPackageAndCategory(StateRepository::Database &,__int64,ushort const *,StateRepository::Statement &)
0x1800c60e3  mov     rcx, [rbp+1F8h]; this
0x1800c60ea  lea     rsi, aOnecoreAdminAp_84; "onecore\\admin\\appmodel\\common\\utili"...
0x1800c60f1  test    eax, eax
0x1800c60f3  jns     short loc_1800C6105
0x1800c60f5  mov     r9d, eax; char *
0x1800c60f8  mov     r8, rsi; unsigned int
0x1800c60fb  mov     edx, 0BA4h; void *
0x1800c6100  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800c6105  lea     r8, [rsp+2F0h+var_2C0]; bool *
0x1800c610a  lea     rdx, [rbp+1F0h+var_260]; struct StateRepository::Entity::PackageExtension *
0x1800c610e  lea     rcx, [rsp+2F0h+var_2B0]; this
0x1800c6113  call    ?FindNext@PackageExtension@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::PackageExtension::FindNext(StateRepository::Statement &,StateRepository::Entity::PackageExtension &,bool &)
0x1800c6118  mov     ebx, eax
0x1800c611a  test    eax, eax
0x1800c611c  jns     short loc_1800C6145
0x1800c611e  mov     rcx, [rbp+1F8h]; this
0x1800c6125  mov     r9d, eax; char *
0x1800c6128  mov     r8, rsi; unsigned int
0x1800c612b  mov     edx, 0BA5h; void *
0x1800c6130  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6135  nop
0x1800c6136  lea     rcx, [rsp+2F0h+var_2B0]; this
0x1800c613b  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800c6140  jmp     loc_1800C66A8
0x1800c6145  cmp     [rsp+2F0h+var_2C0], r15b
0x1800c614a  jz      loc_1800C669B
0x1800c6150  mov     [rsp+2F0h+var_2A0], r15
0x1800c6155  mov     [rsp+2F0h+var_288], r15
0x1800c615a  lea     rcx, [rsp+2F0h+var_2A0]
0x1800c615f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c6164  lea     r9, [rsp+2F0h+var_2A0]; struct Windows::Foundation::Collections::IPropertySet **
0x1800c6169  mov     r8, [rbp+1F0h+var_188]; void *
0x1800c616d  mov     rdx, [rbp+1F0h+var_180]; unsigned __int64
0x1800c6171  lea     rcx, [rsp+2F0h+var_288]; this
0x1800c6176  call    ?DeserializeAsPropertySet@WinRTReader@DictionarySerialization@StateRepository@@QEAAJ_KPEBXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEA_K@Z; StateRepository::DictionarySerialization::WinRTReader::DeserializeAsPropertySet(unsigned __int64,void const *,Windows::Foundation::Collections::IPropertySet * *,unsigned __int64 *)
0x1800c617b  mov     ebx, eax
0x1800c617d  test    eax, eax
0x1800c617f  jns     short loc_1800C61B0
0x1800c6181  mov     rcx, [rbp+1F8h]; this
0x1800c6188  mov     r9d, eax; char *
0x1800c618b  mov     r8, rsi; unsigned int
0x1800c618e  mov     edx, 0BAEh; void *
0x1800c6193  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6198  nop
0x1800c6199  lea     rcx, [rsp+2F0h+var_288]
0x1800c619e  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x1800c61a3  nop
0x1800c61a4  lea     rcx, [rsp+2F0h+var_2A0]
0x1800c61a9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c61ae  jmp     short loc_1800C6136
0x1800c61b0  mov     [rsp+2F0h+var_290], r15
0x1800c61b5  lea     rdx, [rsp+2F0h+var_290]
0x1800c61ba  lea     rcx, [rsp+2F0h+var_2A0]
0x1800c61bf  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x1800c61c4  mov     ebx, eax
0x1800c61c6  test    eax, eax
0x1800c61c8  jns     short loc_1800C61EE
0x1800c61ca  mov     rcx, [rbp+1F8h]; this
0x1800c61d1  mov     r9d, eax; char *
0x1800c61d4  mov     r8, rsi; unsigned int
0x1800c61d7  mov     edx, 0BB1h; void *
0x1800c61dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c61e1  nop
0x1800c61e2  lea     rcx, [rsp+2F0h+var_290]
0x1800c61e7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c61ec  jmp     short loc_1800C6199
0x1800c61ee  mov     [rsp+2F0h+var_298], r15
0x1800c61f3  mov     rdi, [rsp+2F0h+var_290]
0x1800c61f8  mov     rax, [rdi]
0x1800c61fb  mov     rbx, [rax+30h]
0x1800c61ff  lea     rcx, [rsp+2F0h+var_298]
0x1800c6204  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c6209  mov     [rbp+1F0h+var_48], r15
0x1800c6210  mov     r9d, 1Fh; unsigned int
0x1800c6216  lea     r8d, [r9+1]; unsigned int
0x1800c621a  lea     rdx, ?InstalledLocationVirtualization@ElementNameWithoutPrefix@Manifest@Packaging@Appx@@3QBGB; "InstalledLocationVirtualization"
0x1800c6221  lea     rcx, [rbp+1F0h+hstringHeader]; hstringHeader
0x1800c6228  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800c622d  nop
0x1800c622e  lea     r8, [rsp+2F0h+var_298]
0x1800c6233  mov     rdx, [rbp+1F0h+var_48]
0x1800c623a  mov     rcx, rdi
0x1800c623d  mov     rax, rbx
0x1800c6240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6245  mov     ebx, eax
0x1800c6247  test    eax, eax
0x1800c6249  jns     short loc_1800C6272
0x1800c624b  mov     rcx, [rbp+1F8h]; this
0x1800c6252  mov     r9d, eax; char *
0x1800c6255  mov     r8, rsi; unsigned int
0x1800c6258  mov     edx, 0BB6h; void *
0x1800c625d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6262  nop
0x1800c6263  lea     rcx, [rsp+2F0h+var_298]
0x1800c6268  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c626d  jmp     loc_1800C61E2
0x1800c6272  mov     [rbp+1F0h+var_270], r15
0x1800c6276  lea     rdx, [rbp+1F0h+var_270]
0x1800c627a  lea     rcx, [rsp+2F0h+var_298]
0x1800c627f  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x1800c6284  mov     ebx, eax
0x1800c6286  test    eax, eax
0x1800c6288  jns     short loc_1800C62AD
0x1800c628a  mov     rcx, [rbp+1F8h]; this
0x1800c6291  mov     r9d, eax; char *
0x1800c6294  mov     r8, rsi; unsigned int
0x1800c6297  mov     edx, 0BB9h; void *
0x1800c629c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c62a1  nop
0x1800c62a2  lea     rcx, [rbp+1F0h+var_270]
0x1800c62a6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c62ab  jmp     short loc_1800C6263
0x1800c62ad  mov     [rsp+2F0h+var_278], r15
0x1800c62b2  mov     rdi, [rbp+1F0h+var_270]
0x1800c62b6  mov     rax, [rdi]
0x1800c62b9  mov     rbx, [rax+30h]
0x1800c62bd  lea     rcx, [rsp+2F0h+var_278]
0x1800c62c2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c62c7  mov     [rbp+1F0h+var_48], r15
0x1800c62ce  mov     r9d, 0Dh; unsigned int
0x1800c62d4  lea     r8d, [r9+1]; unsigned int
0x1800c62d8  lea     rdx, aUpdateactions; "UpdateActions"
0x1800c62df  lea     rcx, [rbp+1F0h+hstringHeader]; hstringHeader
0x1800c62e6  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800c62eb  nop
0x1800c62ec  lea     r8, [rsp+2F0h+var_278]
0x1800c62f1  mov     rdx, [rbp+1F0h+var_48]
0x1800c62f8  mov     rcx, rdi
0x1800c62fb  mov     rax, rbx
0x1800c62fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6303  mov     ebx, eax
0x1800c6305  test    eax, eax
0x1800c6307  jns     short loc_1800C6330
0x1800c6309  mov     rcx, [rbp+1F8h]; this
0x1800c6310  mov     r9d, eax; char *
0x1800c6313  mov     r8, rsi; unsigned int
0x1800c6316  mov     edx, 0BBCh; void *
0x1800c631b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6320  nop
0x1800c6321  lea     rcx, [rsp+2F0h+var_278]
0x1800c6326  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c632b  jmp     loc_1800C62A2
0x1800c6330  mov     [rsp+2F0h+var_280], r15
0x1800c6335  lea     rdx, [rsp+2F0h+var_280]
0x1800c633a  lea     rcx, [rsp+2F0h+var_278]
0x1800c633f  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x1800c6344  mov     ebx, eax
0x1800c6346  test    eax, eax
0x1800c6348  jns     short loc_1800C636E
0x1800c634a  mov     rcx, [rbp+1F8h]; this
0x1800c6351  mov     r9d, eax; char *
0x1800c6354  mov     r8, rsi; unsigned int
0x1800c6357  mov     edx, 0BBFh; void *
0x1800c635c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6361  nop
0x1800c6362  lea     rcx, [rsp+2F0h+var_280]
0x1800c6367  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c636c  jmp     short loc_1800C6321
0x1800c636e  mov     [rsp+2F0h+var_2A8], r15
0x1800c6373  mov     rdi, [rsp+2F0h+var_280]
0x1800c6378  mov     rax, [rdi]
0x1800c637b  mov     rbx, [rax+30h]
0x1800c637f  lea     rcx, [rsp+2F0h+var_2A8]
0x1800c6384  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c6389  mov     [rbp+1F0h+var_48], r15
0x1800c6390  mov     r9d, 0Bh; unsigned int
0x1800c6396  lea     r8d, [r9+1]; unsigned int
0x1800c639a  lea     rdx, aAddeditems; "@AddedItems"
0x1800c63a1  lea     rcx, [rbp+1F0h+hstringHeader]; hstringHeader
0x1800c63a8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800c63ad  nop
0x1800c63ae  lea     r8, [rsp+2F0h+var_2A8]
0x1800c63b3  mov     rdx, [rbp+1F0h+var_48]
0x1800c63ba  mov     rcx, rdi
0x1800c63bd  mov     rax, rbx
0x1800c63c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c63c5  mov     ebx, eax
0x1800c63c7  test    eax, eax
0x1800c63c9  jns     short loc_1800C63F2
0x1800c63cb  mov     rcx, [rbp+1F8h]; this
0x1800c63d2  mov     r9d, eax; char *
0x1800c63d5  mov     r8, rsi; unsigned int
0x1800c63d8  mov     edx, 0BC2h; void *
0x1800c63dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c63e2  nop
0x1800c63e3  lea     rcx, [rsp+2F0h+var_2A8]
0x1800c63e8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c63ed  jmp     loc_1800C6362
0x1800c63f2  mov     [rsp+2F0h+string], r15
0x1800c63f7  mov     rdi, [rsp+2F0h+var_2A8]
0x1800c63fc  mov     rax, [rdi]
0x1800c63ff  mov     rbx, [rax+98h]
0x1800c6406  xor     ecx, ecx; string
0x1800c6408  call    cs:__imp_WindowsDeleteString
0x1800c640e  mov     [rsp+2F0h+string], r15
0x1800c6413  lea     rdx, [rsp+2F0h+string]
0x1800c6418  mov     rcx, rdi
0x1800c641b  mov     rax, rbx
0x1800c641e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6423  mov     ebx, eax
0x1800c6425  test    eax, eax
0x1800c6427  jns     short loc_1800C6453
0x1800c6429  mov     edx, 0BC5h; void *
0x1800c642e  mov     rcx, [rbp+1F8h]; this
0x1800c6435  mov     r9d, eax; char *
0x1800c6438  mov     r8, rsi; unsigned int
0x1800c643b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c6440  nop
0x1800c6441  mov     rcx, [rsp+2F0h+string]; string
0x1800c6446  call    cs:__imp_WindowsDeleteString
0x1800c644c  mov     [rsp+2F0h+string], r15
0x1800c6451  jmp     short loc_1800C63E3
0x1800c6453  xor     edx, edx; length
0x1800c6455  mov     rcx, [rsp+2F0h+string]; string
0x1800c645a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c6460  mov     [rsp+2F0h+bIgnoreCase], 1; bIgnoreCase
0x1800c6468  or      r12d, 0FFFFFFFFh
0x1800c646c  mov     r9d, r12d; cchCount2
0x1800c646f  lea     r8, aReset; "reset"
0x1800c6476  mov     edx, r12d; cchCount1
0x1800c6479  mov     rcx, rax; lpString1
0x1800c647c  call    cs:__imp_CompareStringOrdinal
0x1800c6482  cmp     eax, 2
0x1800c6485  jnz     short loc_1800C648B
0x1800c6487  or      dword ptr [r14], 4
0x1800c648b  mov     rdi, [rsp+2F0h+var_280]
0x1800c6490  mov     rax, [rdi]
0x1800c6493  mov     rbx, [rax+30h]
0x1800c6497  lea     rcx, [rsp+2F0h+var_2A8]
0x1800c649c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800c64a1  mov     [rbp+1F0h+var_48], r15
0x1800c64a8  mov     r9d, 0Dh; unsigned int
0x1800c64ae  lea     r8d, [r9+1]; unsigned int
0x1800c64b2  lea     rdx, aDeleteditems; "@DeletedItems"
0x1800c64b9  lea     rcx, [rbp+1F0h+hstringHeader]; hstringHeader
0x1800c64c0  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800c64c5  nop
0x1800c64c6  lea     r8, [rsp+2F0h+var_2A8]
0x1800c64cb  mov     rdx, [rbp+1F0h+var_48]
0x1800c64d2  mov     rcx, rdi
0x1800c64d5  mov     rax, rbx
0x1800c64d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c64dd  mov     ebx, eax
0x1800c64df  test    eax, eax
0x1800c64e1  jns     short loc_1800C64ED
0x1800c64e3  mov     edx, 0BCCh
0x1800c64e8  jmp     loc_1800C642E
0x1800c64ed  mov     rdi, [rsp+2F0h+var_2A8]
0x1800c64f2  mov     rax, [rdi]
0x1800c64f5  mov     rbx, [rax+98h]
0x1800c64fc  mov     rcx, [rsp+2F0h+string]; string
0x1800c6501  call    cs:__imp_WindowsDeleteString
0x1800c6507  mov     [rsp+2F0h+string], r15
0x1800c650c  lea     rdx, [rsp+2F0h+string]
0x1800c6511  mov     rcx, rdi
0x1800c6514  mov     rax, rbx
  ... truncated ...
```
