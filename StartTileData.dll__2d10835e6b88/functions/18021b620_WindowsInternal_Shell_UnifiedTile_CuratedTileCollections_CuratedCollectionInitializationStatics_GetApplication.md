# WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedCollectionInitializationStatics::GetApplicationUserModelIdFromLinkFile(HSTRING__ * const,HSTRING__ * *)

- ea: `0x18021b620`
- end: `0x18021bad8`
- name: `?GetApplicationUserModelIdFromLinkFile@CuratedCollectionInitializationStatics@CuratedTileCollections@UnifiedTile@Shell@WindowsInternal@@UEAAJQEAUHSTRING__@@PEAPEAU6@@Z`
- size: `1208`
- prototype: `int(WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedCollectionInitializationStatics *__hidden this, HSTRING, HSTRING *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000ce94`
- `0x18001aca4`
- `0x1800676a8`
- `0x1800c06e8`
- `0x1800c18c4`
- `0x180115e7c`
- `0x180161204`
- `0x180201e50`
- `0x18021b620`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18021b98e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18021b98e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021b694`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18021b694`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18021b741`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18021b741`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021b93e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021ba2a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021b93e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021ba2a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18021b6a7`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18021b6a7`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x18021b8c7`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x18021b8c7`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18021b6e8`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x18021b6e8`

## string_xrefs

- `0x18021b674`: `shellcommon\shell\tiles\curatedtilecollections\brokers\curatedcollectioninitializationbroker\lib\curatedcollectioninitializationstatics.cpp`
- `0x18021b6fe`: `shellcommon\shell\tiles\curatedtilecollections\brokers\curatedcollectioninitializationbroker\lib\curatedcollectioninitializationstatics.cpp`
- `0x18021b757`: `shellcommon\shell\tiles\curatedtilecollections\brokers\curatedcollectioninitializationbroker\lib\curatedcollectioninitializationstatics.cpp`
- `0x18021b822`: `shellcommon\shell\tiles\curatedtilecollections\brokers\curatedcollectioninitializationbroker\lib\curatedcollectioninitializationstatics.cpp`
- `0x18021b877`: `shellcommon\shell\tiles\curatedtilecollections\brokers\curatedcollectioninitializationbroker\lib\curatedcollectioninitializationstatics.cpp`
- `0x18021b914`: `shellcommon\shell\tiles\curatedtilecollections\brokers\curatedcollectioninitializationbroker\lib\curatedcollectioninitializationstatics.cpp`
- `0x18021b9fe`: `shellcommon\shell\tiles\curatedtilecollections\brokers\curatedcollectioninitializationbroker\lib\curatedcollectioninitializationstatics.cpp`
- `0x18021ba4c`: `shellcommon\shell\tiles\curatedtilecollections\brokers\curatedcollectioninitializationbroker\lib\curatedcollectioninitializationstatics.cpp`
- `0x18021ba76`: `shellcommon\shell\tiles\curatedtilecollections\brokers\curatedcollectioninitializationbroker\lib\curatedcollectioninitializationstatics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedCollectionInitializationStatics::GetApplicationUserModelIdFromLinkFile(
        WindowsInternal::Shell::UnifiedTile::CuratedTileCollections::CuratedCollectionInitializationStatics *this,
        HSTRING a2,
        HSTRING *a3)
{
  int IsShellExperience; // ebx
  __int64 v6; // rdx
  const WCHAR *StringRawBuffer; // rax
  HRESULT v8; // eax
  HRESULT v9; // eax
  LPVOID v10; // rdi
  __int64 (__fastcall *v11)(LPVOID, void *, __int64, PCNZWCH *); // rbx
  __int64 v12; // r14
  char v13; // r15
  int v14; // eax
  void *v15; // rdi
  __int64 (__fastcall *v16)(void *, _QWORD, const GUID *, GUID *); // rbx
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  HRESULT v20; // eax
  wil::details::in1diag3 *v21; // rcx
  __int64 v22; // rdx
  ITEMIDLIST *v23; // rcx
  HRESULT String; // eax
  __int64 v25; // r9
  __int64 v26; // rdx
  void *v27; // rdi
  __int64 (__fastcall *v28)(void *, __int64, PCNZWCH *); // rbx
  int v29; // eax
  ITEMIDLIST *v30; // rcx
  int v32; // [rsp+20h] [rbp-E0h]
  int *v33; // [rsp+20h] [rbp-E0h]
  int v34; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v35; // [rsp+38h] [rbp-C8h] BYREF
  LPCITEMIDLIST pidl; // [rsp+40h] [rbp-C0h] BYREF
  void *v37; // [rsp+48h] [rbp-B8h] BYREF
  int v38[2]; // [rsp+50h] [rbp-B0h] BYREF
  void *ppv; // [rsp+58h] [rbp-A8h] BYREF
  PCNZWCH sourceString; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v41; // [rsp+68h] [rbp-98h]
  __int64 v42; // [rsp+70h] [rbp-90h]
  LPCITEMIDLIST *p_pidl; // [rsp+78h] [rbp-88h] BYREF
  __int64 v44; // [rsp+80h] [rbp-80h] BYREF
  char v45; // [rsp+88h] [rbp-78h]
  WCHAR Dst[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v34 = 0;
  *a3 = 0;
  IsShellExperience = CallerIdentity::EnsureCallingProcessIsShellExperience(this);
  if ( IsShellExperience < 0 )
  {
    v6 = 210;
    goto LABEL_3;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  if ( ExpandEnvironmentStringsW(StringRawBuffer, Dst, 0x104u) )
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    v8 = SHCreateItemFromParsingName(Dst, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
    IsShellExperience = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD9,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\curatedcollectioninitializationbroker\\"
                      "lib\\curatedcollectioninitializationstatics.cpp",
        (const char *)(unsigned int)v8,
        v32);
LABEL_47:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      return (unsigned int)IsShellExperience;
    }
    v35 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    v9 = CoCreateInstance(
           &GUID_660b90c8_73a9_4b58_8cae_355b7f55341b,
           0,
           3u,
           &GUID_21cbc515_2dde_4d66_8292_ba34bd25094a,
           &v35);
    IsShellExperience = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDD,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\curatedcollectioninitializationbroker\\"
                      "lib\\curatedcollectioninitializationstatics.cpp",
        (const char *)(unsigned int)v9,
        (int)v33);
LABEL_46:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
      goto LABEL_47;
    }
    sourceString = 0;
    v41 = 0;
    v42 = 0;
    v10 = v35;
    v11 = *(__int64 (__fastcall **)(LPVOID, void *, __int64, PCNZWCH *))(*(_QWORD *)v35 + 136LL);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
    v12 = -1;
    v41 = -1;
    v42 = -1;
    v13 = 1;
    v14 = v11(v10, ppv, 1, &sourceString);
    IsShellExperience = v14;
    if ( v14 >= 0 )
    {
LABEL_31:
      if ( sourceString && *sourceString )
      {
        do
          ++v12;
        while ( sourceString[v12] );
        String = WindowsCreateString(sourceString, v12, a3);
        IsShellExperience = String;
        if ( String >= 0 )
          goto LABEL_45;
        v25 = (unsigned int)String;
        v26 = 258;
      }
      else
      {
        IsShellExperience = -2147024894;
        v25 = 2147942402LL;
        v26 = 265;
      }
      goto LABEL_44;
    }
    if ( v14 != -2147217657 )
    {
      v25 = (unsigned int)v14;
      v26 = 252;
LABEL_44:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\curatedcollectioninitializationbroker\\"
                      "lib\\curatedcollectioninitializationstatics.cpp",
        (const char *)v25,
        (int)v33);
      goto LABEL_45;
    }
    *(_QWORD *)v38 = 0;
    v15 = ppv;
    v16 = *(__int64 (__fastcall **)(void *, _QWORD, const GUID *, GUID *))(*(_QWORD *)ppv + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v38);
    v33 = v38;
    v17 = v16(v15, 0, &BHID_SFUIObject, &GUID_000214f9_0000_0000_c000_000000000046);
    if ( v17 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE6,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\curatedcollectioninitializationbroker\\"
                      "lib\\curatedcollectioninitializationstatics.cpp",
        (const char *)(unsigned int)v17,
        (int)v38);
LABEL_28:
      if ( sourceString && *sourceString )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v38);
        goto LABEL_31;
      }
      IsShellExperience = -2147217657;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF8,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\curatedcollectioninitializationbroker\\"
                      "lib\\curatedcollectioninitializationstatics.cpp",
        (const char *)0x80040F07LL,
        (int)v33);
LABEL_40:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v38);
LABEL_45:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
      goto LABEL_46;
    }
    pidl = 0;
    v18 = **(_QWORD **)v38;
    p_pidl = &pidl;
    v44 = 0;
    v45 = 1;
    v34 = 1;
    v19 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(v18 + 32))(*(_QWORD *)v38, &v44);
    if ( v19 >= 0 )
    {
      if ( pidl )
        goto LABEL_19;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xE9,
        (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\curatedcollectioninitializationbroker\\"
                      "lib\\curatedcollectioninitializationstatics.cpp",
        (const char *)(unsigned int)v19,
        (int)v38);
    }
    v13 = 0;
LABEL_19:
    wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pidl);
    if ( !v13 )
      goto LABEL_26;
    v37 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    v20 = SHCreateItemFromIDList(pidl, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &v37);
    v21 = retaddr;
    if ( v20 >= 0 )
    {
      v34 = 0x20000000;
      v20 = (*(__int64 (__fastcall **)(void *, __int64, int *))(*(_QWORD *)v37 + 48LL))(v37, 0x20000000, &v34);
      v21 = retaddr;
      if ( v20 >= 0 )
      {
        if ( (v34 & 0x20000000) != 0 )
        {
          v27 = v37;
          v28 = *(__int64 (__fastcall **)(void *, __int64, PCNZWCH *))(*(_QWORD *)v37 + 40LL);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
          v41 = -1;
          v42 = -1;
          v29 = v28(v27, 2147647488LL, &sourceString);
          IsShellExperience = v29;
          if ( v29 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xF1,
              (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\curatedcollectioninitializationb"
                            "roker\\lib\\curatedcollectioninitializationstatics.cpp",
              (const char *)(unsigned int)v29,
              (int)v33);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
            v30 = (ITEMIDLIST *)pidl;
            pidl = 0;
            if ( v30 )
              CoTaskMemFree(v30);
            goto LABEL_40;
          }
        }
        goto LABEL_25;
      }
      v22 = 239;
    }
    else
    {
      v22 = 236;
    }
    wil::details::in1diag3::_Log_Hr(
      v21,
      (void *)v22,
      (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\curatedcollectioninitializationbroker\\l"
                    "ib\\curatedcollectioninitializationstatics.cpp",
      (const char *)(unsigned int)v20,
      (int)v33);
LABEL_25:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
LABEL_26:
    v23 = (ITEMIDLIST *)pidl;
    pidl = 0;
    if ( v23 )
      CoTaskMemFree(v23);
    goto LABEL_28;
  }
  IsShellExperience = ResultFromKnownLastError();
  if ( IsShellExperience >= 0 )
    return (unsigned int)IsShellExperience;
  v6 = 213;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"shellcommon\\shell\\tiles\\curatedtilecollections\\brokers\\curatedcollectioninitializationbroker\\lib"
                  "\\curatedcollectioninitializationstatics.cpp",
    (const char *)(unsigned int)IsShellExperience,
    v32);
  return (unsigned int)IsShellExperience;
}

```

## disassembly

```asm
0x18021b620  mov     [rsp-8+arg_0], rbx
0x18021b625  mov     [rsp-8+arg_18], rdi
0x18021b62a  push    rbp
0x18021b62b  push    r12
0x18021b62d  push    r13
0x18021b62f  push    r14
0x18021b631  push    r15
0x18021b633  lea     rbp, [rsp-1B0h]
0x18021b63b  sub     rsp, 2B0h
0x18021b642  mov     rax, cs:__security_cookie
0x18021b649  xor     rax, rsp
0x18021b64c  mov     [rbp+1D0h+var_30], rax
0x18021b653  mov     r12, r8
0x18021b656  mov     rdi, rdx
0x18021b659  xor     r13d, r13d
0x18021b65c  mov     [rsp+2D0h+var_2A0], r13d
0x18021b661  mov     [r8], r13
0x18021b664  call    ?EnsureCallingProcessIsShellExperience@CallerIdentity@@YAJXZ; CallerIdentity::EnsureCallingProcessIsShellExperience(void)
0x18021b669  mov     ebx, eax
0x18021b66b  test    eax, eax
0x18021b66d  jns     short loc_18021B68F
0x18021b66f  mov     edx, 0D2h; void *
0x18021b674  lea     r8, aShellcommonShe_55; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18021b67b  mov     r9d, ebx; char *
0x18021b67e  mov     rcx, [rbp+1D8h]; this
0x18021b685  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021b68a  jmp     loc_18021BAAA
0x18021b68f  xor     edx, edx; length
0x18021b691  mov     rcx, rdi; string
0x18021b694  call    cs:__imp_WindowsGetStringRawBuffer
0x18021b69a  mov     rcx, rax; lpSrc
0x18021b69d  mov     r8d, 104h; nSize
0x18021b6a3  lea     rdx, [rbp+1D0h+Dst]; lpDst
0x18021b6a7  call    cs:__imp_ExpandEnvironmentStringsW
0x18021b6ad  test    eax, eax
0x18021b6af  jnz     short loc_18021B6C7
0x18021b6b1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18021b6b6  mov     ebx, eax
0x18021b6b8  test    eax, eax
0x18021b6ba  jns     loc_18021BAAA
0x18021b6c0  mov     edx, 0D5h
0x18021b6c5  jmp     short loc_18021B674
0x18021b6c7  mov     [rsp+2D0h+ppv], r13
0x18021b6cc  lea     rcx, [rsp+2D0h+ppv]
0x18021b6d1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021b6d6  lea     r9, [rsp+2D0h+ppv]; ppv
0x18021b6db  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18021b6e2  xor     edx, edx; pbc
0x18021b6e4  lea     rcx, [rbp+1D0h+Dst]; pszPath
0x18021b6e8  call    cs:__imp_SHCreateItemFromParsingName
0x18021b6ee  mov     ebx, eax
0x18021b6f0  test    eax, eax
0x18021b6f2  jns     short loc_18021B714
0x18021b6f4  mov     rcx, [rbp+1D8h]; this
0x18021b6fb  mov     r9d, eax; char *
0x18021b6fe  lea     r8, aShellcommonShe_55; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18021b705  mov     edx, 0D9h; void *
0x18021b70a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021b70f  jmp     loc_18021BAA0
0x18021b714  mov     [rsp+2D0h+var_298], r13
0x18021b719  lea     rcx, [rsp+2D0h+var_298]
0x18021b71e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021b723  lea     rax, [rsp+2D0h+var_298]
0x18021b728  mov     [rsp+2D0h+var_2B0], rax; int
0x18021b72d  lea     r9, _GUID_21cbc515_2dde_4d66_8292_ba34bd25094a; riid
0x18021b734  xor     edx, edx; pUnkOuter
0x18021b736  lea     r8d, [rdx+3]; dwClsContext
0x18021b73a  lea     rcx, _GUID_660b90c8_73a9_4b58_8cae_355b7f55341b; rclsid
0x18021b741  call    cs:__imp_CoCreateInstance
0x18021b747  mov     ebx, eax
0x18021b749  test    eax, eax
0x18021b74b  jns     short loc_18021B76D
0x18021b74d  mov     rcx, [rbp+1D8h]; this
0x18021b754  mov     r9d, eax; char *
0x18021b757  lea     r8, aShellcommonShe_55; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18021b75e  mov     edx, 0DDh; void *
0x18021b763  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021b768  jmp     loc_18021BA95
0x18021b76d  mov     [rsp+2D0h+sourceString], r13
0x18021b772  mov     [rsp+2D0h+var_268], r13
0x18021b777  mov     [rsp+2D0h+var_260], r13
0x18021b77c  mov     rdi, [rsp+2D0h+var_298]
0x18021b781  mov     rax, [rdi]
0x18021b784  mov     rbx, [rax+88h]
0x18021b78b  lea     rcx, [rsp+2D0h+sourceString]
0x18021b790  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18021b795  or      r14, 0FFFFFFFFFFFFFFFFh
0x18021b799  mov     [rsp+2D0h+var_268], r14
0x18021b79e  mov     [rsp+2D0h+var_260], r14
0x18021b7a3  lea     r9, [rsp+2D0h+sourceString]
0x18021b7a8  lea     r15d, [r14+2]
0x18021b7ac  mov     r8d, r15d
0x18021b7af  mov     rdx, [rsp+2D0h+ppv]
0x18021b7b4  mov     rcx, rdi
0x18021b7b7  mov     rax, rbx
0x18021b7ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021b7bf  mov     ebx, eax
0x18021b7c1  test    eax, eax
0x18021b7c3  jns     loc_18021B966
0x18021b7c9  cmp     eax, 80040F07h
0x18021b7ce  jnz     loc_18021BA5F
0x18021b7d4  mov     qword ptr [rsp+2D0h+var_280], r13
0x18021b7d9  mov     rdi, [rsp+2D0h+ppv]
0x18021b7de  mov     rax, [rdi]
0x18021b7e1  mov     rbx, [rax+18h]
0x18021b7e5  lea     rcx, [rsp+2D0h+var_280]
0x18021b7ea  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021b7ef  lea     rax, [rsp+2D0h+var_280]
0x18021b7f4  mov     [rsp+2D0h+var_2B0], rax; int
0x18021b7f9  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046
0x18021b800  lea     r8, BHID_SFUIObject
0x18021b807  xor     edx, edx
0x18021b809  mov     rcx, rdi
0x18021b80c  mov     rax, rbx
0x18021b80f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021b814  mov     rcx, [rbp+1D8h]; this
0x18021b81b  test    eax, eax
0x18021b81d  jns     short loc_18021B838
0x18021b81f  mov     r9d, eax; char *
0x18021b822  lea     r8, aShellcommonShe_55; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18021b829  mov     edx, 0E6h; void *
0x18021b82e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18021b833  jmp     loc_18021B944
0x18021b838  mov     [rsp+2D0h+pidl], r13
0x18021b83d  mov     rcx, qword ptr [rsp+2D0h+var_280]
0x18021b842  mov     rax, [rcx]
0x18021b845  lea     rdx, [rsp+2D0h+pidl]
0x18021b84a  mov     [rsp+2D0h+var_258], rdx
0x18021b84f  mov     [rbp+1D0h+var_250], r13
0x18021b853  mov     [rbp+1D0h+var_248], r15b
0x18021b857  mov     [rsp+2D0h+var_2A0], r15d
0x18021b85c  lea     rdx, [rbp+1D0h+var_250]
0x18021b860  mov     rax, [rax+20h]
0x18021b864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021b869  mov     rcx, [rbp+1D8h]; this
0x18021b870  test    eax, eax
0x18021b872  jns     short loc_18021B88A
0x18021b874  mov     r9d, eax; char *
0x18021b877  lea     r8, aShellcommonShe_55; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18021b87e  mov     edx, 0E9h; void *
0x18021b883  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18021b888  jmp     short loc_18021B891
0x18021b88a  cmp     [rsp+2D0h+pidl], r13
0x18021b88f  jnz     short loc_18021B894
0x18021b891  mov     r15b, r13b
0x18021b894  lea     rcx, [rsp+2D0h+var_258]
0x18021b899  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18021b89e  test    r15b, r15b
0x18021b8a1  jz      loc_18021B92F
0x18021b8a7  mov     [rsp+2D0h+var_288], r13
0x18021b8ac  lea     rcx, [rsp+2D0h+var_288]
0x18021b8b1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021b8b6  lea     r8, [rsp+2D0h+var_288]; ppv
0x18021b8bb  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x18021b8c2  mov     rcx, [rsp+2D0h+pidl]; pidl
0x18021b8c7  call    cs:__imp_SHCreateItemFromIDList
0x18021b8cd  mov     rcx, [rbp+1D8h]
0x18021b8d4  test    eax, eax
0x18021b8d6  jns     short loc_18021B8DF
0x18021b8d8  mov     edx, 0ECh
0x18021b8dd  jmp     short loc_18021B914
0x18021b8df  mov     ebx, 20000000h
0x18021b8e4  mov     [rsp+2D0h+var_2A0], ebx
0x18021b8e8  mov     rcx, [rsp+2D0h+var_288]
0x18021b8ed  mov     rax, [rcx]
0x18021b8f0  lea     r8, [rsp+2D0h+var_2A0]
0x18021b8f5  mov     edx, ebx
0x18021b8f7  mov     rax, [rax+30h]
0x18021b8fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021b900  mov     rcx, [rbp+1D8h]; this
0x18021b907  test    eax, eax
0x18021b909  jns     loc_18021B9AB
0x18021b90f  mov     edx, 0EFh; void *
0x18021b914  lea     r8, aShellcommonShe_55; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18021b91b  mov     r9d, eax; char *
0x18021b91e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18021b923  nop
0x18021b924  lea     rcx, [rsp+2D0h+var_288]
0x18021b929  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021b92e  nop
0x18021b92f  mov     rcx, [rsp+2D0h+pidl]; pv
0x18021b934  mov     [rsp+2D0h+pidl], r13
0x18021b939  test    rcx, rcx
0x18021b93c  jz      short loc_18021B944
0x18021b93e  call    cs:__imp_CoTaskMemFree
0x18021b944  mov     rax, [rsp+2D0h+sourceString]
0x18021b949  test    rax, rax
0x18021b94c  jz      loc_18021BA3D
0x18021b952  cmp     [rax], r13w
0x18021b956  jz      loc_18021BA3D
0x18021b95c  lea     rcx, [rsp+2D0h+var_280]
0x18021b961  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021b966  mov     rcx, [rsp+2D0h+sourceString]; sourceString
0x18021b96b  test    rcx, rcx
0x18021b96e  jz      loc_18021BA69
0x18021b974  cmp     [rcx], r13w
0x18021b978  jz      loc_18021BA69
0x18021b97e  inc     r14
0x18021b981  cmp     [rcx+r14*2], r13w
0x18021b986  jnz     short loc_18021B97E
0x18021b988  mov     r8, r12; string
0x18021b98b  mov     edx, r14d; length
0x18021b98e  call    cs:__imp_WindowsCreateString
0x18021b994  mov     ebx, eax
0x18021b996  test    eax, eax
0x18021b998  jns     loc_18021BA8A
0x18021b99e  mov     r9d, eax
0x18021b9a1  mov     edx, 102h
0x18021b9a6  jmp     loc_18021BA76
0x18021b9ab  test    [rsp+2D0h+var_2A0], ebx
0x18021b9af  jz      loc_18021B924
0x18021b9b5  mov     rdi, [rsp+2D0h+var_288]
0x18021b9ba  mov     rax, [rdi]
0x18021b9bd  mov     rbx, [rax+28h]
0x18021b9c1  lea     rcx, [rsp+2D0h+sourceString]
0x18021b9c6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18021b9cb  mov     [rsp+2D0h+var_268], r14
0x18021b9d0  mov     [rsp+2D0h+var_260], r14
0x18021b9d5  lea     r8, [rsp+2D0h+sourceString]
0x18021b9da  mov     edx, 80028000h
0x18021b9df  mov     rcx, rdi
0x18021b9e2  mov     rax, rbx
0x18021b9e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18021b9ea  mov     ebx, eax
0x18021b9ec  test    eax, eax
0x18021b9ee  jns     loc_18021B924
0x18021b9f4  mov     rcx, [rbp+1D8h]; this
0x18021b9fb  mov     r9d, eax; char *
0x18021b9fe  lea     r8, aShellcommonShe_55; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18021ba05  mov     edx, 0F1h; void *
0x18021ba0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021ba0f  nop
0x18021ba10  lea     rcx, [rsp+2D0h+var_288]
0x18021ba15  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021ba1a  nop
0x18021ba1b  mov     rcx, [rsp+2D0h+pidl]; pv
0x18021ba20  mov     [rsp+2D0h+pidl], r13
0x18021ba25  test    rcx, rcx
0x18021ba28  jz      short loc_18021BA31
0x18021ba2a  call    cs:__imp_CoTaskMemFree
0x18021ba30  nop
0x18021ba31  lea     rcx, [rsp+2D0h+var_280]
0x18021ba36  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021ba3b  jmp     short loc_18021BA8A
0x18021ba3d  mov     rcx, [rbp+1D8h]; this
0x18021ba44  mov     ebx, 80040F07h
0x18021ba49  mov     r9d, ebx; char *
0x18021ba4c  lea     r8, aShellcommonShe_55; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18021ba53  mov     edx, 0F8h; void *
0x18021ba58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021ba5d  jmp     short loc_18021BA31
0x18021ba5f  mov     r9d, eax
0x18021ba62  mov     edx, 0FCh
0x18021ba67  jmp     short loc_18021BA76
0x18021ba69  mov     ebx, 80070002h
0x18021ba6e  mov     r9d, ebx; char *
0x18021ba71  mov     edx, 109h; void *
0x18021ba76  lea     r8, aShellcommonShe_55; "shellcommon\\shell\\tiles\\curatedtilec"...
0x18021ba7d  mov     rcx, [rbp+1D8h]; this
0x18021ba84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18021ba89  nop
0x18021ba8a  lea     rcx, [rsp+2D0h+sourceString]
0x18021ba8f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18021ba94  nop
0x18021ba95  lea     rcx, [rsp+2D0h+var_298]
0x18021ba9a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021ba9f  nop
0x18021baa0  lea     rcx, [rsp+2D0h+ppv]
0x18021baa5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18021baaa  mov     eax, ebx
0x18021baac  mov     rcx, [rbp+1D0h+var_30]
0x18021bab3  xor     rcx, rsp; StackCookie
0x18021bab6  call    __security_check_cookie
0x18021babb  lea     r11, [rsp+2D0h+var_20]
0x18021bac3  mov     rbx, [r11+30h]
0x18021bac7  mov     rdi, [r11+48h]
0x18021bacb  mov     rsp, r11
0x18021bace  pop     r15
0x18021bad0  pop     r14
0x18021bad2  pop     r13
0x18021bad4  pop     r12
0x18021bad6  pop     rbp
0x18021bad7  retn
```
