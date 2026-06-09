# wpcplugs::AppRepository::StateRepo::AppRepository::GetInfraPackageFamilies(void)

- ea: `0x18006ceb0`
- end: `0x18006d448`
- name: `?GetInfraPackageFamilies@AppRepository@StateRepo@1wpcplugs@@UEBA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ`
- size: `1432`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x1800060a0`
- `0x180008d50`
- `0x18001ccf0`
- `0x18002eb3c`
- `0x180069ba0`
- `0x18006a0b4`
- `0x18006b5a8`
- `0x18006ceb0`
- `0x18006e83c`
- `0x18006ef5c`
- `0x1800715e4`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006cf14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006cf80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006cfec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006cf14`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006cf80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006cfec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006d254`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006d2cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006d254`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006d2cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006d276`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006d276`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006cf51`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006cfbd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006d029`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006cf51`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006cfbd`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006d029`

## string_xrefs

- `0x18006d3b5`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006d3d2`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006d3ef`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006d40c`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006d421`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006d436`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
_QWORD *__fastcall wpcplugs::AppRepository::StateRepo::AppRepository::GetInfraPackageFamilies(__int64 a1, _QWORD *a2)
{
  int v3; // edi
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int ActivationFactory; // eax
  wil::details::in1diag3 *v8; // rcx
  HRESULT v9; // eax
  int v10; // edx
  unsigned int v11; // r8d
  int v12; // eax
  wil::details::in1diag3 *v13; // rcx
  HRESULT v14; // eax
  int v15; // edx
  unsigned int v16; // r8d
  int v17; // eax
  wil::details::in1diag3 *v18; // rcx
  int v19; // eax
  struct Windows::Internal::StateRepository::IPackageFamily *v20; // rdx
  int v21; // ecx
  _QWORD *Reserved1; // r14
  int v23; // eax
  int v24; // eax
  char v25; // r13
  int v26; // ecx
  struct Windows::Internal::StateRepository::IApplicationStatics *v27; // r8
  __int64 v28; // rbx
  __int64 (__fastcall *v29)(__int64, _QWORD, wpcplugs::AppRepository::StateRepo **); // rdi
  wpcplugs::AppRepository::StateRepo *v30; // rcx
  unsigned int v31; // ebx
  unsigned int v32; // r12d
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, _QWORD, wpcplugs::AppRepository::StateRepo **); // r15
  wpcplugs::AppRepository::StateRepo *v35; // rcx
  wpcplugs::AppRepository::StateRepo *v36; // rcx
  __int64 v37; // rdi
  void (__fastcall *v38)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rdx
  __int64 v40; // rax
  unsigned __int64 v41; // r8
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  struct Windows::Internal::StateRepository::IPackage *v46; // rcx
  __int64 v47; // rcx
  int v49; // [rsp+20h] [rbp-E0h]
  int v50; // [rsp+30h] [rbp-D0h]
  __int64 v51; // [rsp+38h] [rbp-C8h] BYREF
  struct Windows::Internal::StateRepository::IPackage *v52; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v53; // [rsp+48h] [rbp-B8h] BYREF
  int v54; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v55; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING v56; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v57; // [rsp+68h] [rbp-98h] BYREF
  __int64 v58; // [rsp+70h] [rbp-90h]
  unsigned int v59; // [rsp+78h] [rbp-88h] BYREF
  int *v60; // [rsp+80h] [rbp-80h]
  int v61; // [rsp+88h] [rbp-78h] BYREF
  wpcplugs::AppRepository::StateRepo *v62; // [rsp+90h] [rbp-70h] BYREF
  int i; // [rsp+98h] [rbp-68h]
  _QWORD v64[2]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v65[8]; // [rsp+B0h] [rbp-50h] BYREF
  int v66; // [rsp+B8h] [rbp-48h]
  __int64 v67; // [rsp+D0h] [rbp-30h]
  HSTRING_HEADER hstringHeader; // [rsp+D8h] [rbp-28h] BYREF
  HSTRING string; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v64[1] = a2;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v3 = 1;
  v50 = 1;
  v53 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.PackageFamily", 0x2Eu, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
LABEL_56:
    wil::details::in1diag3::Throw_Hr(
      v8,
      (void *)0x141,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v49);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_86f5b0ee_9560_4d76_a06a_ca4c8bfe4426, &v53);
  v8 = retaddr;
  if ( ActivationFactory < 0 )
    goto LABEL_56;
  v52 = 0;
  string = 0;
  v9 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Application", 0x2Cu, &hstringHeader, &string);
  if ( v9 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v9, v10, v11);
LABEL_58:
    wil::details::in1diag3::Throw_Hr(
      v13,
      (void *)0x144,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v12,
      v49);
  }
  v12 = RoGetActivationFactory(string, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v52);
  v13 = retaddr;
  if ( v12 < 0 )
    goto LABEL_58;
  v51 = 0;
  string = 0;
  v14 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Package", 0x28u, &hstringHeader, &string);
  if ( v14 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v14, v15, v16);
LABEL_60:
    wil::details::in1diag3::Throw_Hr(
      v18,
      (void *)0x147,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v17,
      v49);
  }
  v17 = RoGetActivationFactory(string, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v51);
  v18 = retaddr;
  if ( v17 < 0 )
    goto LABEL_60;
  v57 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v53 + 144LL))(v53, &v57);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14A,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v19,
      v49);
  wil::GetRangeNoThrow<Windows::Internal::StateRepository::PackageFamily *>(v65, v57);
  wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::PackageFamily *>>::begin(
    v65,
    &hstringHeader);
  v21 = v66;
  for ( i = v66; ; v21 = i )
  {
    Reserved1 = hstringHeader.Reserved.Reserved1;
    if ( **((int **)hstringHeader.Reserved.Reserved1 + 2) < 0 || *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] == v21 )
      break;
    if ( wpcplugs::AppRepository::StateRepo::IsFirstPartyPackage(
           *((wpcplugs::AppRepository::StateRepo **)hstringHeader.Reserved.Reserved1 + 4),
           v20) )
    {
      v55 = 0;
      v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v51 + 216LL))(
              v51,
              Reserved1[4],
              1,
              &v55);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x151,
          (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
          (const char *)(unsigned int)v23,
          v49);
      v54 = 0;
      v24 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v55 + 56LL))(v55, &v54);
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x154,
          (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
          (const char *)(unsigned int)v24,
          v49);
      if ( v54 )
      {
        v25 = 0;
        v58 = v55;
        v60 = &v61;
        v61 = 0;
        v62 = 0;
        v26 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v55 + 56LL))(v55, &v59);
        *v60 = v26;
        v50 = v3 | 6;
        if ( v26 >= 0 && v59 )
        {
          v28 = v58;
          v29 = *(__int64 (__fastcall **)(__int64, _QWORD, wpcplugs::AppRepository::StateRepo **))(*(_QWORD *)v58 + 48LL);
          v30 = v62;
          if ( v62 )
          {
            v62 = 0;
            (*(void (__fastcall **)(wpcplugs::AppRepository::StateRepo *))(*(_QWORD *)v30 + 16LL))(v30);
          }
          v26 = v29(v28, 0, &v62);
          *v60 = v26;
        }
        v31 = 0;
        v32 = v59;
        while ( v26 >= 0 && v31 != v32 )
        {
          if ( wpcplugs::AppRepository::StateRepo::HasAppListEntry(v62, v52, v27) )
          {
            v25 = 1;
            break;
          }
          ++v31;
          v26 = *v60;
          if ( *v60 < 0 )
            break;
          if ( v31 < v59 )
          {
            v33 = v58;
            v34 = *(__int64 (__fastcall **)(__int64, _QWORD, wpcplugs::AppRepository::StateRepo **))(*(_QWORD *)v58 + 48LL);
            v35 = v62;
            if ( v62 )
            {
              v62 = 0;
              (*(void (__fastcall **)(wpcplugs::AppRepository::StateRepo *))(*(_QWORD *)v35 + 16LL))(v35);
            }
            v26 = v34(v33, v31, &v62);
            *v60 = v26;
          }
        }
        v36 = v62;
        if ( v62 )
        {
          v62 = 0;
          (*(void (__fastcall **)(wpcplugs::AppRepository::StateRepo *))(*(_QWORD *)v36 + 16LL))(v36);
        }
        if ( !v25 )
        {
          v56 = 0;
          v37 = Reserved1[4];
          v38 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v37 + 88LL);
          WindowsDeleteString(0);
          v56 = 0;
          v38(v37, &v56);
          StringRawBuffer = WindowsGetStringRawBuffer(v56, 0);
          v64[0] = StringRawBuffer;
          v40 = a2[1];
          if ( v40 == a2[2] )
          {
            std::vector<std::wstring>::_Emplace_reallocate<unsigned short const *>(a2, a2[1], v64);
          }
          else
          {
            *(_OWORD *)v40 = 0;
            *(_QWORD *)(v40 + 16) = 0;
            *(_QWORD *)(v40 + 24) = 0;
            v41 = -1;
            do
              ++v41;
            while ( StringRawBuffer[v41] );
            std::wstring::_Construct<1,unsigned short const *>((char **)v40, StringRawBuffer, v41);
            a2[1] += 32LL;
          }
          WindowsDeleteString(v56);
        }
      }
      v42 = v55;
      if ( v55 )
      {
        v55 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      }
      v3 = v50;
    }
    wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::PackageFamily *>>::vector_iterator_nothrow::operator++(&hstringHeader);
  }
  v43 = v67;
  if ( v67 )
  {
    v67 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v44 = v57;
  if ( v57 )
  {
    v57 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  }
  v45 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  }
  v46 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *))(*(_QWORD *)v46 + 16LL))(v46);
  }
  v47 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
  }
  return a2;
}

```

## disassembly

```asm
0x18006ceb0  push    rbp
0x18006ceb2  push    rbx
0x18006ceb3  push    rsi
0x18006ceb4  push    rdi
0x18006ceb5  push    r12
0x18006ceb7  push    r13
0x18006ceb9  push    r14
0x18006cebb  push    r15
0x18006cebd  lea     rbp, [rsp-8]
0x18006cec2  sub     rsp, 108h
0x18006cec9  mov     rax, cs:__security_cookie
0x18006ced0  xor     rax, rsp
0x18006ced3  mov     [rbp+40h+var_48], rax
0x18006ced7  mov     rsi, rdx
0x18006ceda  mov     [rbp+40h+var_98], rdx
0x18006cede  xor     r15d, r15d
0x18006cee1  mov     [rsp+140h+var_110], r15d
0x18006cee6  mov     [rdx], r15
0x18006cee9  mov     [rdx+8], r15
0x18006ceed  mov     [rdx+10h], r15
0x18006cef1  lea     edi, [r15+1]
0x18006cef5  mov     [rsp+140h+var_110], edi
0x18006cef9  mov     [rsp+140h+var_F8], r15
0x18006cefe  mov     [rbp+40h+string], r15
0x18006cf02  lea     r9, [rbp+40h+string]; string
0x18006cf06  lea     r8, [rbp+40h+hstringHeader]; hstringHeader
0x18006cf0a  lea     edx, [rdi+2Dh]; length
0x18006cf0d  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_PackageFamily@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18006cf14  call    cs:__imp_WindowsCreateStringReference
0x18006cf1a  test    eax, eax
0x18006cf1c  js      loc_18006D3C7
0x18006cf22  mov     rbx, [rbp+40h+string]
0x18006cf26  mov     rcx, [rsp+140h+var_F8]
0x18006cf2b  test    rcx, rcx
0x18006cf2e  jz      short loc_18006CF42
0x18006cf30  mov     [rsp+140h+var_F8], r15
0x18006cf35  mov     rax, [rcx]
0x18006cf38  mov     rax, [rax+10h]
0x18006cf3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cf41  nop
0x18006cf42  lea     r8, [rsp+140h+var_F8]
0x18006cf47  lea     rdx, _GUID_86f5b0ee_9560_4d76_a06a_ca4c8bfe4426
0x18006cf4e  mov     rcx, rbx
0x18006cf51  call    cs:__imp_RoGetActivationFactory
0x18006cf57  mov     rcx, [rbp+48h]
0x18006cf5b  test    eax, eax
0x18006cf5d  js      loc_18006D3CF
0x18006cf63  mov     [rsp+140h+var_100], r15
0x18006cf68  mov     [rbp+40h+string], r15
0x18006cf6c  lea     r9, [rbp+40h+string]; string
0x18006cf70  lea     r8, [rbp+40h+hstringHeader]; hstringHeader
0x18006cf74  mov     edx, 2Ch ; ','; length
0x18006cf79  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x18006cf80  call    cs:__imp_WindowsCreateStringReference
0x18006cf86  test    eax, eax
0x18006cf88  js      loc_18006D3E4
0x18006cf8e  mov     rbx, [rbp+40h+string]
0x18006cf92  mov     rcx, [rsp+140h+var_100]
0x18006cf97  test    rcx, rcx
0x18006cf9a  jz      short loc_18006CFAE
0x18006cf9c  mov     [rsp+140h+var_100], r15
0x18006cfa1  mov     rax, [rcx]
0x18006cfa4  mov     rax, [rax+10h]
0x18006cfa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cfad  nop
0x18006cfae  lea     r8, [rsp+140h+var_100]
0x18006cfb3  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x18006cfba  mov     rcx, rbx
0x18006cfbd  call    cs:__imp_RoGetActivationFactory
0x18006cfc3  mov     rcx, [rbp+48h]
0x18006cfc7  test    eax, eax
0x18006cfc9  js      loc_18006D3EC
0x18006cfcf  mov     [rsp+140h+var_108], r15
0x18006cfd4  mov     [rbp+40h+string], r15
0x18006cfd8  lea     r9, [rbp+40h+string]; string
0x18006cfdc  lea     r8, [rbp+40h+hstringHeader]; hstringHeader
0x18006cfe0  mov     edx, 28h ; '('; length
0x18006cfe5  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18006cfec  call    cs:__imp_WindowsCreateStringReference
0x18006cff2  test    eax, eax
0x18006cff4  js      loc_18006D401
0x18006cffa  mov     rbx, [rbp+40h+string]
0x18006cffe  mov     rcx, [rsp+140h+var_108]
0x18006d003  test    rcx, rcx
0x18006d006  jz      short loc_18006D01A
0x18006d008  mov     [rsp+140h+var_108], r15
0x18006d00d  mov     rax, [rcx]
0x18006d010  mov     rax, [rax+10h]
0x18006d014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d019  nop
0x18006d01a  lea     r8, [rsp+140h+var_108]
0x18006d01f  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x18006d026  mov     rcx, rbx
0x18006d029  call    cs:__imp_RoGetActivationFactory
0x18006d02f  mov     rcx, [rbp+48h]
0x18006d033  test    eax, eax
0x18006d035  js      loc_18006D409
0x18006d03b  mov     [rsp+140h+var_D8], r15
0x18006d040  mov     rcx, [rsp+140h+var_F8]
0x18006d045  mov     rax, [rcx]
0x18006d048  lea     rdx, [rsp+140h+var_D8]
0x18006d04d  mov     rax, [rax+90h]
0x18006d054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d059  mov     rcx, [rbp+48h]; this
0x18006d05d  test    eax, eax
0x18006d05f  js      loc_18006D41E
0x18006d065  mov     rdx, [rsp+140h+var_D8]
0x18006d06a  lea     rcx, [rbp+40h+var_90]
0x18006d06e  call    ??$GetRangeNoThrow@PEAVPackageFamily@StateRepository@Internal@Windows@@@wil@@YA?AV?$vector_range_nothrow@U?$IVectorView@PEAVPackageFamily@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@@0@PEAU?$IVectorView@PEAVPackageFamily@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@PEAJ@Z; wil::GetRangeNoThrow<Windows::Internal::StateRepository::PackageFamily *>(Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::PackageFamily *> *,long *)
0x18006d073  nop
0x18006d074  lea     rdx, [rbp+40h+hstringHeader]
0x18006d078  lea     rcx, [rbp+40h+var_90]
0x18006d07c  call    ?begin@?$vector_range_nothrow@U?$IVectorView@PEAVPackageFamily@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@@wil@@QEAA?AVvector_iterator_nothrow@12@XZ; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::PackageFamily *>>::begin(void)
0x18006d081  mov     ecx, [rbp+40h+var_88]
0x18006d084  mov     [rbp+40h+var_A8], ecx
0x18006d087  mov     r14, qword ptr [rbp+40h+hstringHeader.Reserved]
0x18006d08b  mov     rax, [r14+10h]
0x18006d08f  cmp     [rax], r15d
0x18006d092  jl      loc_18006D305
0x18006d098  cmp     dword ptr [rbp+40h+hstringHeader.Reserved+8], ecx
0x18006d09b  jz      loc_18006D305
0x18006d0a1  mov     rcx, [r14+20h]; this
0x18006d0a5  call    ?IsFirstPartyPackage@StateRepo@AppRepository@wpcplugs@@YA_NPEAUIPackageFamily@StateRepository@Internal@Windows@@@Z; wpcplugs::AppRepository::StateRepo::IsFirstPartyPackage(Windows::Internal::StateRepository::IPackageFamily *)
0x18006d0aa  test    al, al
0x18006d0ac  jz      loc_18006D2F4
0x18006d0b2  mov     [rsp+140h+var_E8], r15
0x18006d0b7  mov     rcx, [rsp+140h+var_108]
0x18006d0bc  mov     rax, [rcx]
0x18006d0bf  lea     r9, [rsp+140h+var_E8]
0x18006d0c4  mov     r8d, 1
0x18006d0ca  mov     rdx, [r14+20h]
0x18006d0ce  mov     rax, [rax+0D8h]
0x18006d0d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d0da  mov     rcx, [rbp+48h]; this
0x18006d0de  test    eax, eax
0x18006d0e0  js      loc_18006D3B2
0x18006d0e6  mov     [rsp+140h+var_F0], r15d
0x18006d0eb  mov     rcx, [rsp+140h+var_E8]
0x18006d0f0  mov     rax, [rcx]
0x18006d0f3  lea     rdx, [rsp+140h+var_F0]
0x18006d0f8  mov     rax, [rax+38h]
0x18006d0fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d101  mov     rcx, [rbp+48h]; this
0x18006d105  test    eax, eax
0x18006d107  js      loc_18006D433
0x18006d10d  cmp     [rsp+140h+var_F0], r15d
0x18006d112  jbe     loc_18006D2D4
0x18006d118  mov     r13b, r15b
0x18006d11b  mov     rcx, [rsp+140h+var_E8]
0x18006d120  mov     [rsp+140h+var_D0], rcx
0x18006d125  lea     rax, [rbp+40h+var_B8]
0x18006d129  mov     [rbp+40h+var_C0], rax
0x18006d12d  mov     [rbp+40h+var_B8], r15d
0x18006d131  mov     [rbp+40h+var_B0], r15
0x18006d135  mov     rax, [rcx]
0x18006d138  lea     rdx, [rsp+140h+var_C8]
0x18006d13d  mov     rax, [rax+38h]
0x18006d141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d146  mov     ecx, eax
0x18006d148  mov     rax, [rbp+40h+var_C0]
0x18006d14c  mov     [rax], ecx
0x18006d14e  or      edi, 6
0x18006d151  mov     [rsp+140h+var_110], edi
0x18006d155  test    ecx, ecx
0x18006d157  js      short loc_18006D19F
0x18006d159  cmp     [rsp+140h+var_C8], r15d
0x18006d15e  jbe     short loc_18006D19F
0x18006d160  mov     rbx, [rsp+140h+var_D0]
0x18006d165  mov     rax, [rbx]
0x18006d168  mov     rdi, [rax+30h]
0x18006d16c  mov     rcx, [rbp+40h+var_B0]
0x18006d170  test    rcx, rcx
0x18006d173  jz      short loc_18006D186
0x18006d175  mov     [rbp+40h+var_B0], r15
0x18006d179  mov     rax, [rcx]
0x18006d17c  mov     rax, [rax+10h]
0x18006d180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d185  nop
0x18006d186  lea     r8, [rbp+40h+var_B0]
0x18006d18a  xor     edx, edx
0x18006d18c  mov     rcx, rbx
0x18006d18f  mov     rax, rdi
0x18006d192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d197  mov     ecx, eax
0x18006d199  mov     rax, [rbp+40h+var_C0]
0x18006d19d  mov     [rax], ecx
0x18006d19f  mov     ebx, r15d
0x18006d1a2  mov     r12d, [rsp+140h+var_C8]
0x18006d1a7  test    ecx, ecx
0x18006d1a9  js      short loc_18006D21F
0x18006d1ab  cmp     ebx, r12d
0x18006d1ae  jz      short loc_18006D21F
0x18006d1b0  mov     rdx, [rsp+140h+var_100]; struct Windows::Internal::StateRepository::IPackage *
0x18006d1b5  mov     rcx, [rbp+40h+var_B0]; this
0x18006d1b9  call    ?HasAppListEntry@StateRepo@AppRepository@wpcplugs@@YA_NPEAUIPackage@StateRepository@Internal@Windows@@PEAUIApplicationStatics@567@@Z; wpcplugs::AppRepository::StateRepo::HasAppListEntry(Windows::Internal::StateRepository::IPackage *,Windows::Internal::StateRepository::IApplicationStatics *)
0x18006d1be  test    al, al
0x18006d1c0  jnz     short loc_18006D21C
0x18006d1c2  inc     ebx
0x18006d1c4  mov     rax, [rbp+40h+var_C0]
0x18006d1c8  mov     ecx, [rax]
0x18006d1ca  test    ecx, ecx
0x18006d1cc  js      short loc_18006D21F
0x18006d1ce  cmp     ebx, [rsp+140h+var_C8]
0x18006d1d2  jnb     short loc_18006D1A7
0x18006d1d4  mov     rdi, [rsp+140h+var_D0]
0x18006d1d9  mov     rax, [rdi]
0x18006d1dc  mov     r15, [rax+30h]
0x18006d1e0  mov     rcx, [rbp+40h+var_B0]
0x18006d1e4  test    rcx, rcx
0x18006d1e7  jz      short loc_18006D1FE
0x18006d1e9  mov     [rbp+40h+var_B0], 0
0x18006d1f1  mov     rax, [rcx]
0x18006d1f4  mov     rax, [rax+10h]
0x18006d1f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d1fd  nop
0x18006d1fe  lea     r8, [rbp+40h+var_B0]
0x18006d202  mov     edx, ebx
0x18006d204  mov     rcx, rdi
0x18006d207  mov     rax, r15
0x18006d20a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d20f  mov     ecx, eax
0x18006d211  mov     rax, [rbp+40h+var_C0]
0x18006d215  mov     [rax], ecx
0x18006d217  xor     r15d, r15d
0x18006d21a  jmp     short loc_18006D1A7
0x18006d21c  mov     r13b, 1
0x18006d21f  mov     rcx, [rbp+40h+var_B0]
0x18006d223  test    rcx, rcx
0x18006d226  jz      short loc_18006D239
0x18006d228  mov     [rbp+40h+var_B0], r15
0x18006d22c  mov     rax, [rcx]
0x18006d22f  mov     rax, [rax+10h]
0x18006d233  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d238  nop
0x18006d239  test    r13b, r13b
0x18006d23c  jnz     loc_18006D2D4
0x18006d242  mov     [rsp+140h+var_E0], r15
0x18006d247  mov     rdi, [r14+20h]
0x18006d24b  mov     rax, [rdi]
0x18006d24e  mov     rbx, [rax+58h]
0x18006d252  xor     ecx, ecx; string
0x18006d254  call    cs:__imp_WindowsDeleteString
0x18006d25a  mov     [rsp+140h+var_E0], r15
0x18006d25f  lea     rdx, [rsp+140h+var_E0]
0x18006d264  mov     rcx, rdi
0x18006d267  mov     rax, rbx
0x18006d26a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d26f  xor     edx, edx; length
0x18006d271  mov     rcx, [rsp+140h+var_E0]; string
0x18006d276  call    cs:__imp_WindowsGetStringRawBuffer
0x18006d27c  mov     rdx, rax
0x18006d27f  mov     [rbp+40h+var_A0], rax
0x18006d283  mov     rax, [rsi+8]
0x18006d287  cmp     rax, [rsi+10h]
0x18006d28b  jz      short loc_18006D2B8
0x18006d28d  xorps   xmm0, xmm0
0x18006d290  movups  xmmword ptr [rax], xmm0
0x18006d293  mov     [rax+10h], r15
0x18006d297  mov     [rax+18h], r15
0x18006d29b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18006d29f  inc     r8
0x18006d2a2  cmp     [rdx+r8*2], r15w
0x18006d2a7  jnz     short loc_18006D29F
0x18006d2a9  mov     rcx, rax
0x18006d2ac  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18006d2b1  add     qword ptr [rsi+8], 20h ; ' '
0x18006d2b6  jmp     short loc_18006D2C8
0x18006d2b8  lea     r8, [rbp+40h+var_A0]
0x18006d2bc  mov     rdx, rax
0x18006d2bf  mov     rcx, rsi
0x18006d2c2  call    ??$_Emplace_reallocate@PEBG@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@$$QEAPEBG@Z; std::vector<std::wstring>::_Emplace_reallocate<ushort const *>(std::wstring * const,ushort const * &&)
0x18006d2c7  nop
0x18006d2c8  mov     rcx, [rsp+140h+var_E0]; string
0x18006d2cd  call    cs:__imp_WindowsDeleteString
0x18006d2d3  nop
0x18006d2d4  mov     rcx, [rsp+140h+var_E8]
0x18006d2d9  test    rcx, rcx
0x18006d2dc  jz      short loc_18006D2F0
0x18006d2de  mov     [rsp+140h+var_E8], r15
0x18006d2e3  mov     rax, [rcx]
0x18006d2e6  mov     rax, [rax+10h]
0x18006d2ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d2ef  nop
0x18006d2f0  mov     edi, [rsp+140h+var_110]
0x18006d2f4  lea     rcx, [rbp+40h+hstringHeader]
0x18006d2f8  call    ??Evector_iterator_nothrow@?$vector_range_nothrow@U?$IVectorView@PEAVPackageFamily@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@@wil@@QEAAAEAV012@XZ; wil::vector_range_nothrow<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::PackageFamily *>>::vector_iterator_nothrow::operator++(void)
0x18006d2fd  mov     ecx, [rbp+40h+var_A8]
0x18006d300  jmp     loc_18006D087
0x18006d305  mov     rcx, [rbp+40h+var_70]
0x18006d309  test    rcx, rcx
0x18006d30c  jz      short loc_18006D31F
0x18006d30e  mov     [rbp+40h+var_70], r15
0x18006d312  mov     rax, [rcx]
0x18006d315  mov     rax, [rax+10h]
0x18006d319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d31e  nop
0x18006d31f  mov     rcx, [rsp+140h+var_D8]
0x18006d324  test    rcx, rcx
0x18006d327  jz      short loc_18006D33B
0x18006d329  mov     [rsp+140h+var_D8], r15
  ... truncated ...
```
