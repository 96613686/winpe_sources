# WindowsInternal::Shell::UnifiedTile::UnifiedTileIdentifierExtractorFactory::ExtractFromStorageItem(Windows::Storage::IStorageItem *,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier * *)

- ea: `0x180050a70`
- end: `0x180050ef6`
- name: `?ExtractFromStorageItem@UnifiedTileIdentifierExtractorFactory@UnifiedTile@Shell@WindowsInternal@@UEAAJPEAUIStorageItem@Storage@Windows@@PEAPEAUIUnifiedTileIdentifier@234@@Z`
- size: `1158`
- prototype: `__int64 __fastcall(WindowsInternal::Shell::UnifiedTile::UnifiedTileIdentifierExtractorFactory *__hidden this, struct Windows::Storage::IStorageItem *, struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier **)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000ce94`
- `0x180011188`
- `0x1800186e0`
- `0x18001aca4`
- `0x18002f1fc`
- `0x1800301cc`
- `0x18004ffc0`
- `0x180050a70`
- `0x180050efc`
- `0x1800514bc`
- `0x1800a8e20`
- `0x1800a8e40`
- `0x1800bfce0`
- `0x1800d8e48`
- `0x180201e50`
- `0x180204e28`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180050e0b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180050e0b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180050bfe`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180050bfe`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180050c46`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180050c46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050b4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050c8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ce0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050dcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050e7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050b4e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050c8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050ce0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050dcd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180050e7d`
- `ext-ms-win-shell-shell32-l1-2-2!__imp_GetShellItemFromStorageItem` at `0x180050aca`
- `ext-ms-win-shell-shell32-l1-2-2!__imp_GetShellItemFromStorageItem` at `0x180050aca`

## string_xrefs

- `0x180050add`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtileidentifierextractor.cpp`
- `0x180050c59`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtileidentifierextractor.cpp`
- `0x180050db2`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtileidentifierextractor.cpp`
- `0x180050e4c`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtileidentifierextractor.cpp`
- `0x180050eb7`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtileidentifierextractor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::UnifiedTileIdentifierExtractorFactory::ExtractFromStorageItem(
        WindowsInternal::Shell::UnifiedTile::UnifiedTileIdentifierExtractorFactory *this,
        struct Windows::Storage::IStorageItem *a2,
        struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier **a3)
{
  int ShellItemFromStorageItem; // eax
  int v6; // r8d
  unsigned int v7; // ebx
  __int64 v8; // rcx
  void *v9; // rbx
  int v10; // edi
  int v11; // ebx
  bool v12; // di
  HRESULT v13; // eax
  LPVOID v14; // rcx
  __int64 v15; // rcx
  LPVOID v16; // rdi
  int (__fastcall *v17)(LPVOID, __int64, _QWORD, LPVOID *); // r14
  void *v18; // rbx
  LPVOID v19; // rcx
  const WCHAR *v20; // rbx
  unsigned __int64 v21; // rdi
  unsigned int v22; // eax
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rcx
  int ppv; // [rsp+20h] [rbp-59h]
  int ppva; // [rsp+20h] [rbp-59h]
  _BYTE v31[8]; // [rsp+30h] [rbp-49h] BYREF
  __int64 v32; // [rsp+38h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-39h] BYREF
  LPVOID v34; // [rsp+48h] [rbp-31h] BYREF
  __int64 v35; // [rsp+50h] [rbp-29h] BYREF
  LPVOID v36; // [rsp+58h] [rbp-21h] BYREF
  PROPERTYKEY v37; // [rsp+60h] [rbp-19h] BYREF
  __int64 v38; // [rsp+80h] [rbp+7h] BYREF
  HSTRING_HEADER pvar; // [rsp+88h] [rbp+Fh] BYREF
  void *v40; // [rsp+A0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *a3 = 0;
  v32 = 0;
  if ( !(unsigned __int8)IsGetShellItemFromStorageItemPresent(this) )
  {
    v7 = -2147467263;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtileidentifierextractor.cpp",
      (const char *)0x80004001LL,
      ppv);
LABEL_55:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    return v7;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  ShellItemFromStorageItem = GetShellItemFromStorageItem(a2, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &v32);
  v7 = ShellItemFromStorageItem;
  if ( ShellItemFromStorageItem < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtileidentifierextractor.cpp",
      (const char *)(unsigned int)ShellItemFromStorageItem,
      ppv);
    v8 = v32;
    if ( v32 )
    {
      v32 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return v7;
  }
  v35 = 0;
  pv = 0;
  if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(
              (unsigned int)&v35,
              v32,
              v6,
              (unsigned int)`WindowsInternal::Shell::UnifiedTile::UnifiedTileIdentifierExtractorFactory::ExtractFromStorageItem'::`2'::propertyKeys,
              2) < 0 )
    goto LABEL_21;
  v9 = pv;
  if ( pv )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v34);
    CoTaskMemFree(v9);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v34);
  }
  pv = 0;
  v37 = PKEY_AppUserModel_ID;
  if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::GetAsString<_tagpropertykey>(&v35, &v37, &pv) >= 0
    && *(_WORD *)pv )
  {
    v10 = 0;
    LOWORD(pvar.Reserved.Reserved1) = 0;
    v37.fmtid = (GUID)PKEY_AppUserModel_HostEnvironment;
    v37.pid = 14;
    v11 = (*(__int64 (__fastcall **)(__int64, PROPERTYKEY *, HSTRING_HEADER *))(*(_QWORD *)v35 + 40LL))(
            v35,
            &v37,
            &pvar);
    if ( v11 >= 0 )
    {
      if ( LOWORD(pvar.Reserved.Reserved1) )
      {
        if ( LOWORD(pvar.Reserved.Reserved1) == 19 )
          v10 = *(_DWORD *)&pvar.Reserved.Reserved2[8];
        else
          v11 = -2147352571;
      }
      else
      {
        v11 = -2147023728;
      }
    }
    PropVariantClear(&pvar.Reserved.Reserved1);
    v12 = v11 < 0 || !v10;
  }
  else
  {
LABEL_21:
    v34 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
    v13 = CoCreateInstance(
            &GUID_660b90c8_73a9_4b58_8cae_355b7f55341b,
            0,
            1u,
            &GUID_21cbc515_2dde_4d66_8292_ba34bd25094a,
            &v34);
    v7 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x60,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtileidentifierextractor.cpp",
        (const char *)(unsigned int)v13,
        ppva);
      v14 = v34;
      if ( v34 )
      {
        v34 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v14 + 16LL))(v14);
      }
      if ( pv )
        CoTaskMemFree(pv);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
      v15 = v32;
      if ( v32 )
      {
        v32 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      return v7;
    }
    v16 = v34;
    v17 = *(int (__fastcall **)(LPVOID, __int64, _QWORD, LPVOID *))(*(_QWORD *)v34 + 136LL);
    v18 = pv;
    if ( pv )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v36);
      CoTaskMemFree(v18);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v36);
    }
    pv = 0;
    v12 = v17(v16, v32, 0, &pv) >= 0;
    v19 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
    }
  }
  v20 = (const WCHAR *)pv;
  if ( pv )
  {
    if ( *(_WORD *)pv )
    {
      v38 = 0;
      if ( v12 )
      {
        v40 = 0;
        v21 = -1;
        do
          ++v21;
        while ( *((_WORD *)pv + v21) );
        if ( v21 > 0xFFFFFFFF )
        {
          RaiseException(0x80070216, 1u, 0, 0);
          __debugbreak();
        }
        v22 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v21);
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(&pvar, v20, v22, v21);
        v36 = v40;
        v31[0] = 0;
        v23 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::Win32UnifiedTileIdentifier,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,HSTRING__ * &,bool>(
                a3,
                &v36,
                v31);
        v7 = v23;
        if ( v23 < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x6F,
            (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtileidentifierextractor.cpp",
            (const char *)(unsigned int)v23,
            ppva);
        if ( pv )
          CoTaskMemFree(pv);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
        v24 = v32;
        if ( v32 )
        {
          v32 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        }
        return v7;
      }
      v36 = pv;
      v25 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&pvar, &v36);
      v36 = 0;
      v34 = *(LPVOID *)(v25 + 24);
      v26 = Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTileIdentifier,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,HSTRING__ * &,HSTRING__ * &>(
              a3,
              &v34,
              &v36);
      v7 = v26;
      if ( v26 < 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x74,
          (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtileidentifierextractor.cpp",
          (const char *)(unsigned int)v26,
          ppva);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pv);
      Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::ITileImageResourceOptions>::~ComPtr<WindowsInternal::Shell::UnifiedTile::ITileImageResourceOptions>(&v35);
      goto LABEL_55;
    }
    CoTaskMemFree(pv);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  v27 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  return 0;
}

```

## disassembly

```asm
0x180050a70  mov     [rsp-8+arg_0], rbx
0x180050a75  push    rbp
0x180050a76  push    rsi
0x180050a77  push    rdi
0x180050a78  push    r14
0x180050a7a  push    r15
0x180050a7c  lea     rbp, [rsp-37h]
0x180050a81  sub     rsp, 0B0h
0x180050a88  mov     rax, cs:__security_cookie
0x180050a8f  xor     rax, rsp
0x180050a92  mov     [rbp+57h+var_28], rax
0x180050a96  mov     rsi, r8
0x180050a99  mov     rbx, rdx
0x180050a9c  xor     r15d, r15d
0x180050a9f  mov     [r8], r15
0x180050aa2  mov     [rbp+57h+var_98], r15
0x180050aa6  call    IsGetShellItemFromStorageItemPresent
0x180050aab  test    al, al
0x180050aad  jz      loc_180050EAB
0x180050ab3  lea     rcx, [rbp+57h+var_98]
0x180050ab7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180050abc  lea     r8, [rbp+57h+var_98]
0x180050ac0  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x180050ac7  mov     rcx, rbx
0x180050aca  call    cs:__imp_GetShellItemFromStorageItem
0x180050ad0  mov     ebx, eax
0x180050ad2  test    eax, eax
0x180050ad4  jns     short loc_180050B0D
0x180050ad6  mov     rcx, [rbp+5Fh]; this
0x180050ada  mov     r9d, eax; char *
0x180050add  lea     r8, aShellcommonShe_153; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x180050ae4  lea     edx, [r15+42h]; void *
0x180050ae8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050aed  nop
0x180050aee  mov     rcx, [rbp+57h+var_98]
0x180050af2  test    rcx, rcx
0x180050af5  jz      short loc_180050B08
0x180050af7  mov     [rbp+57h+var_98], r15
0x180050afb  mov     rax, [rcx]
0x180050afe  mov     rax, [rax+10h]
0x180050b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050b07  nop
0x180050b08  jmp     loc_180050ED1
0x180050b0d  mov     [rbp+57h+var_80], r15
0x180050b11  mov     [rbp+57h+pv], r15
0x180050b15  mov     [rsp+0D0h+ppv], 2
0x180050b1d  lea     r9, ?propertyKeys@?1??ExtractFromStorageItem@UnifiedTileIdentifierExtractorFactory@UnifiedTile@Shell@WindowsInternal@@UEAAJPEAUIStorageItem@Storage@Windows@@PEAPEAUIUnifiedTileIdentifier@345@@Z@4QBU_tagpropertykey@@B; _tagpropertykey const near * const `WindowsInternal::Shell::UnifiedTile::UnifiedTileIdentifierExtractorFactory::ExtractFromStorageItem(Windows::Storage::IStorageItem *,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier * *)'::`2'::propertyKeys
0x180050b24  mov     rdx, [rbp+57h+var_98]
0x180050b28  lea     rcx, [rbp+57h+var_80]
0x180050b2c  call    ?InitFromItem@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEAAJPEAUIUnknown@@W4GETPROPERTYSTOREFLAGS@@PEBU_tagpropertykey@@I@Z; wil::PropertyStoreHelperBase<IPropertyStore>::InitFromItem(IUnknown *,GETPROPERTYSTOREFLAGS,_tagpropertykey const *,uint)
0x180050b31  test    eax, eax
0x180050b33  js      loc_180050C1C
0x180050b39  mov     rbx, [rbp+57h+pv]
0x180050b3d  test    rbx, rbx
0x180050b40  jz      short loc_180050B5D
0x180050b42  lea     rcx, [rbp+57h+var_88]; this
0x180050b46  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180050b4b  mov     rcx, rbx; pv
0x180050b4e  call    cs:__imp_CoTaskMemFree
0x180050b54  lea     rcx, [rbp+57h+var_88]; this
0x180050b58  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180050b5d  mov     [rbp+57h+pv], r15
0x180050b61  movups  xmm0, xmmword ptr cs:PKEY_AppUserModel_ID.fmtid.Data1
0x180050b68  movaps  [rbp+57h+var_70], xmm0
0x180050b6c  mov     eax, cs:PKEY_AppUserModel_ID.pid
0x180050b72  mov     [rbp+57h+var_60], eax
0x180050b75  lea     r8, [rbp+57h+pv]
0x180050b79  lea     rdx, [rbp+57h+var_70]
0x180050b7d  lea     rcx, [rbp+57h+var_80]
0x180050b81  call    ??$GetAsString@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAPEAG@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetAsString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x180050b86  test    eax, eax
0x180050b88  js      loc_180050C1C
0x180050b8e  mov     rax, [rbp+57h+pv]
0x180050b92  cmp     [rax], r15w
0x180050b96  jz      loc_180050C1C
0x180050b9c  movups  xmm0, cs:PKEY_AppUserModel_HostEnvironment
0x180050ba3  mov     ecx, cs:dword_18041CFE8
0x180050ba9  mov     edi, r15d
0x180050bac  mov     word ptr [rbp+57h+pvar], r15w
0x180050bb1  movaps  [rbp+57h+var_70], xmm0
0x180050bb5  mov     [rbp+57h+var_60], ecx
0x180050bb8  mov     rcx, [rbp+57h+var_80]
0x180050bbc  mov     rax, [rcx]
0x180050bbf  lea     r8, [rbp+57h+pvar]
0x180050bc3  lea     rdx, [rbp+57h+var_70]
0x180050bc7  mov     rax, [rax+28h]
0x180050bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050bd0  mov     ebx, eax
0x180050bd2  movzx   eax, word ptr [rbp+57h+pvar]
0x180050bd6  test    ebx, ebx
0x180050bd8  js      short loc_180050BFA
0x180050bda  test    ax, ax
0x180050bdd  jnz     short loc_180050BE6
0x180050bdf  mov     ebx, 80070490h
0x180050be4  jmp     short loc_180050BFA
0x180050be6  test    ebx, ebx
0x180050be8  js      short loc_180050BFA
0x180050bea  cmp     ax, 13h
0x180050bee  jnz     short loc_180050BF5
0x180050bf0  mov     edi, [rbp+57h+var_40]
0x180050bf3  jmp     short loc_180050BFA
0x180050bf5  mov     ebx, 80020005h
0x180050bfa  lea     rcx, [rbp+57h+pvar]; pvar
0x180050bfe  call    cs:__imp_PropVariantClear
0x180050c04  test    ebx, ebx
0x180050c06  js      short loc_180050C14
0x180050c08  test    edi, edi
0x180050c0a  jz      short loc_180050C14
0x180050c0c  mov     dil, r15b
0x180050c0f  jmp     loc_180050D2C
0x180050c14  mov     dil, 1
0x180050c17  jmp     loc_180050D2C
0x180050c1c  mov     [rbp+57h+var_88], r15
0x180050c20  lea     rcx, [rbp+57h+var_88]
0x180050c24  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180050c29  lea     rax, [rbp+57h+var_88]
0x180050c2d  mov     qword ptr [rsp+0D0h+ppv], rax; int
0x180050c32  lea     r9, _GUID_21cbc515_2dde_4d66_8292_ba34bd25094a; riid
0x180050c39  xor     edx, edx; pUnkOuter
0x180050c3b  lea     r8d, [rdx+1]; dwClsContext
0x180050c3f  lea     rcx, _GUID_660b90c8_73a9_4b58_8cae_355b7f55341b; rclsid
0x180050c46  call    cs:__imp_CoCreateInstance
0x180050c4c  mov     ebx, eax
0x180050c4e  test    eax, eax
0x180050c50  jns     short loc_180050CBD
0x180050c52  mov     rcx, [rbp+5Fh]; this
0x180050c56  mov     r9d, eax; char *
0x180050c59  lea     r8, aShellcommonShe_153; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x180050c60  mov     edx, 60h ; '`'; void *
0x180050c65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050c6a  nop
0x180050c6b  mov     rcx, [rbp+57h+var_88]
0x180050c6f  test    rcx, rcx
0x180050c72  jz      short loc_180050C85
0x180050c74  mov     [rbp+57h+var_88], r15
0x180050c78  mov     rax, [rcx]
0x180050c7b  mov     rax, [rax+10h]
0x180050c7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050c84  nop
0x180050c85  mov     rcx, [rbp+57h+pv]; pv
0x180050c89  test    rcx, rcx
0x180050c8c  jz      short loc_180050C94
0x180050c8e  call    cs:__imp_CoTaskMemFree
0x180050c94  lea     rcx, [rbp+57h+var_80]
0x180050c98  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180050c9d  nop
0x180050c9e  mov     rcx, [rbp+57h+var_98]
0x180050ca2  test    rcx, rcx
0x180050ca5  jz      short loc_180050CB8
0x180050ca7  mov     [rbp+57h+var_98], r15
0x180050cab  mov     rax, [rcx]
0x180050cae  mov     rax, [rax+10h]
0x180050cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050cb7  nop
0x180050cb8  jmp     loc_180050ED1
0x180050cbd  mov     rdi, [rbp+57h+var_88]
0x180050cc1  mov     rax, [rdi]
0x180050cc4  mov     r14, [rax+88h]
0x180050ccb  mov     rbx, [rbp+57h+pv]
0x180050ccf  test    rbx, rbx
0x180050cd2  jz      short loc_180050CEF
0x180050cd4  lea     rcx, [rbp+57h+var_78]; this
0x180050cd8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180050cdd  mov     rcx, rbx; pv
0x180050ce0  call    cs:__imp_CoTaskMemFree
0x180050ce6  lea     rcx, [rbp+57h+var_78]; this
0x180050cea  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180050cef  mov     [rbp+57h+pv], r15
0x180050cf3  lea     r9, [rbp+57h+pv]
0x180050cf7  xor     r8d, r8d
0x180050cfa  mov     rdx, [rbp+57h+var_98]
0x180050cfe  mov     rcx, rdi
0x180050d01  mov     rax, r14
0x180050d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d09  mov     edi, eax
0x180050d0b  shr     edi, 1Fh
0x180050d0e  xor     dil, 1
0x180050d12  mov     rcx, [rbp+57h+var_88]
0x180050d16  test    rcx, rcx
0x180050d19  jz      short loc_180050D2C
0x180050d1b  mov     [rbp+57h+var_88], r15
0x180050d1f  mov     rdx, [rcx]
0x180050d22  mov     rax, [rdx+10h]
0x180050d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d2b  nop
0x180050d2c  mov     rbx, [rbp+57h+pv]
0x180050d30  test    rbx, rbx
0x180050d33  jz      loc_180050E83
0x180050d39  cmp     [rbx], r15w
0x180050d3d  jz      loc_180050E7A
0x180050d43  mov     [rbp+57h+var_50], r15
0x180050d47  test    dil, dil
0x180050d4a  jz      loc_180050E12
0x180050d50  mov     [rbp+57h+var_30], r15
0x180050d54  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180050d58  inc     rdi
0x180050d5b  cmp     [rbx+rdi*2], r15w
0x180050d60  jnz     short loc_180050D58
0x180050d62  mov     eax, 0FFFFFFFFh
0x180050d67  cmp     rdi, rax
0x180050d6a  ja      loc_180050DFC
0x180050d70  mov     ecx, edi; unsigned int
0x180050d72  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180050d77  mov     r9d, edi; unsigned int
0x180050d7a  mov     r8d, eax; unsigned int
0x180050d7d  mov     rdx, rbx; sourceString
0x180050d80  lea     rcx, [rbp+57h+pvar]; hstringHeader
0x180050d84  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180050d89  mov     rax, [rbp+57h+var_30]
0x180050d8d  mov     [rbp+57h+var_78], rax
0x180050d91  mov     [rbp+57h+var_A0], r15b
0x180050d95  lea     r8, [rbp+57h+var_A0]
0x180050d99  lea     rdx, [rbp+57h+var_78]
0x180050d9d  mov     rcx, rsi
0x180050da0  call    ??$MakeAndInitialize@VWin32UnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@UIUnifiedTileIdentifier@234@AEAPEAUHSTRING__@@_N@Details@WRL@Microsoft@@YAJPEAPEAUIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@AEAPEAUHSTRING__@@$$QEA_N@Z; Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::Win32UnifiedTileIdentifier,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,HSTRING__ * &,bool>(WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier * *,HSTRING__ * &,bool &&)
0x180050da5  mov     ebx, eax
0x180050da7  test    eax, eax
0x180050da9  jns     short loc_180050DC4
0x180050dab  mov     rcx, [rbp+5Fh]; this
0x180050daf  mov     r9d, eax; char *
0x180050db2  lea     r8, aShellcommonShe_153; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x180050db9  mov     edx, 6Fh ; 'o'; void *
0x180050dbe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050dc3  nop
0x180050dc4  mov     rcx, [rbp+57h+pv]; pv
0x180050dc8  test    rcx, rcx
0x180050dcb  jz      short loc_180050DD3
0x180050dcd  call    cs:__imp_CoTaskMemFree
0x180050dd3  lea     rcx, [rbp+57h+var_80]
0x180050dd7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180050ddc  nop
0x180050ddd  mov     rcx, [rbp+57h+var_98]
0x180050de1  test    rcx, rcx
0x180050de4  jz      short loc_180050DF7
0x180050de6  mov     [rbp+57h+var_98], r15
0x180050dea  mov     rax, [rcx]
0x180050ded  mov     rax, [rax+10h]
0x180050df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050df6  nop
0x180050df7  jmp     loc_180050ED1
0x180050dfc  xor     r9d, r9d; lpArguments
0x180050dff  xor     r8d, r8d; nNumberOfArguments
0x180050e02  lea     edx, [r9+1]; dwExceptionFlags
0x180050e06  mov     ecx, 80070216h; dwExceptionCode
0x180050e0b  call    cs:__imp_RaiseException
0x180050e11  int     3; Trap to Debugger
0x180050e12  mov     [rbp+57h+var_78], rbx
0x180050e16  lea     rdx, [rbp+57h+var_78]
0x180050e1a  lea     rcx, [rbp+57h+pvar]
0x180050e1e  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x180050e23  mov     [rbp+57h+var_78], r15
0x180050e27  mov     rax, [rax+18h]
0x180050e2b  mov     [rbp+57h+var_88], rax
0x180050e2f  lea     r8, [rbp+57h+var_78]
0x180050e33  lea     rdx, [rbp+57h+var_88]
0x180050e37  mov     rcx, rsi
0x180050e3a  call    ??$MakeAndInitialize@VPackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@UIUnifiedTileIdentifier@234@AEAPEAUHSTRING__@@AEAPEAU6@@Details@WRL@Microsoft@@YAJPEAPEAUIUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@AEAPEAUHSTRING__@@1@Z; Microsoft::WRL::Details::MakeAndInitialize<WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTileIdentifier,WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier,HSTRING__ * &,HSTRING__ * &>(WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier * *,HSTRING__ * &,HSTRING__ * &)
0x180050e3f  mov     ebx, eax
0x180050e41  test    eax, eax
0x180050e43  jns     short loc_180050E5D
0x180050e45  mov     rcx, [rbp+5Fh]; this
0x180050e49  mov     r9d, eax; char *
0x180050e4c  lea     r8, aShellcommonShe_153; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x180050e53  mov     edx, 74h ; 't'; void *
0x180050e58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050e5d  lea     rcx, [rbp+57h+var_50]
0x180050e61  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180050e66  lea     rcx, [rbp+57h+pv]
0x180050e6a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180050e6f  lea     rcx, [rbp+57h+var_80]; void *
0x180050e73  call    ??1?$ComPtr@UITileImageResourceOptions@UnifiedTile@Shell@WindowsInternal@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<WindowsInternal::Shell::UnifiedTile::ITileImageResourceOptions>::~ComPtr<WindowsInternal::Shell::UnifiedTile::ITileImageResourceOptions>(void)
0x180050e78  jmp     short loc_180050EC8
0x180050e7a  mov     rcx, rbx; pv
0x180050e7d  call    cs:__imp_CoTaskMemFree
0x180050e83  lea     rcx, [rbp+57h+var_80]
0x180050e87  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180050e8c  nop
0x180050e8d  mov     rcx, [rbp+57h+var_98]
0x180050e91  test    rcx, rcx
0x180050e94  jz      short loc_180050EA7
0x180050e96  mov     [rbp+57h+var_98], r15
0x180050e9a  mov     rax, [rcx]
0x180050e9d  mov     rax, [rax+10h]
0x180050ea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ea6  nop
0x180050ea7  xor     eax, eax
0x180050ea9  jmp     short loc_180050ED3
0x180050eab  mov     rcx, [rbp+5Fh]; this
0x180050eaf  mov     ebx, 80004001h
0x180050eb4  mov     r9d, ebx; char *
0x180050eb7  lea     r8, aShellcommonShe_153; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x180050ebe  mov     edx, 46h ; 'F'; void *
0x180050ec3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180050ec8  lea     rcx, [rbp+57h+var_98]
0x180050ecc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180050ed1  mov     eax, ebx
0x180050ed3  mov     rcx, [rbp+57h+var_28]
0x180050ed7  xor     rcx, rsp; StackCookie
0x180050eda  call    __security_check_cookie
0x180050edf  mov     rbx, [rsp+0D0h+arg_0]
  ... truncated ...
```
