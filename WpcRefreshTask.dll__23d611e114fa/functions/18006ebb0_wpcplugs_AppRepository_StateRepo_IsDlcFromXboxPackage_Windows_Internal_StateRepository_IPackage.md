# wpcplugs::AppRepository::StateRepo::IsDlcFromXboxPackage(Windows::Internal::StateRepository::IPackage *)

- ea: `0x18006ebb0`
- end: `0x18006ef56`
- name: `?IsDlcFromXboxPackage@StateRepo@AppRepository@wpcplugs@@YA_NPEAUIPackage@StateRepository@Internal@Windows@@@Z`
- size: `934`
- prototype: `bool __fastcall(wpcplugs::AppRepository::StateRepo *__hidden this, struct Windows::Internal::StateRepository::IPackage *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180071070`

## callees

- `0x1800060a0`
- `0x18001ccf0`
- `0x18002eb3c`
- `0x18006ebb0`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ed44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ee2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ed44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18006ee2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006ebee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006edb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006ebee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006edb9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006ec28`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006ec28`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x18006ed59`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x18006ed59`

## string_xrefs

- `0x18006eea1`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006eebe`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006eed3`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006eee8`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006eefd`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006ef12`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006ef27`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`
- `0x18006ef3c`: `shellcommon\shell\wpccore\plugs\apprepository.staterepo\apprepository.staterepo.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
bool __fastcall wpcplugs::AppRepository::StateRepo::IsDlcFromXboxPackage(
        wpcplugs::AppRepository::StateRepo *this,
        struct Windows::Internal::StateRepository::IPackage *a2)
{
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  int ActivationFactory; // eax
  wil::details::in1diag3 *v7; // rcx
  int v8; // eax
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v13; // eax
  __int64 v14; // rax
  int v15; // eax
  void *v16; // rcx
  int v17; // eax
  int v18; // eax
  _QWORD *v19; // rbx
  __int64 v20; // rdi
  HRESULT v21; // eax
  int v22; // edx
  unsigned int v23; // r8d
  int v24; // eax
  bool v25; // bl
  _QWORD *v26; // rcx
  __int64 (__fastcall ***v27)(_QWORD, GUID *, _QWORD **); // rcx
  void *v28; // rcx
  _QWORD *v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  int v32; // [rsp+20h] [rbp-39h] BYREF
  __int64 v33; // [rsp+28h] [rbp-31h] BYREF
  __int64 v34; // [rsp+30h] [rbp-29h] BYREF
  int v35; // [rsp+38h] [rbp-21h] BYREF
  unsigned int v36; // [rsp+3Ch] [rbp-1Dh] BYREF
  _QWORD *v37; // [rsp+40h] [rbp-19h] BYREF
  __int64 (__fastcall ***v38)(_QWORD, GUID *, _QWORD **); // [rsp+48h] [rbp-11h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-9h] BYREF
  _QWORD *v40; // [rsp+58h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+7h] BYREF
  HSTRING string; // [rsp+78h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v33 = 0;
  string = 0;
  v3 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.XboxPackage", 0x2Cu, &hstringHeader, &string);
  if ( v3 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
LABEL_35:
    wil::details::in1diag3::Throw_Hr(
      v7,
      (void *)0x10B,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v32);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_e1a3bc26_0387_453d_b463_c296a38a35b0, &v33);
  v7 = retaddr;
  if ( ActivationFactory < 0 )
    goto LABEL_35;
  v34 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, wpcplugs::AppRepository::StateRepo *, __int64 *))(*(_QWORD *)v33 + 208LL))(
         v33,
         this,
         &v34);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10E,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v8,
      v32);
  v35 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v34 + 56LL))(v34, &v35);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
      (const char *)(unsigned int)v9,
      v32);
  if ( v35 )
  {
    v40 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)v34 + 48LL))(v34, 0, &v40);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x119,
        (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
        (const char *)(unsigned int)v13,
        v32);
    v36 = 0;
    pv = 0;
    v14 = *v40;
    hstringHeader.Reserved.Reserved1 = &pv;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
    hstringHeader.Reserved.Reserved2[16] = 1;
    v15 = (*(__int64 (__fastcall **)(_QWORD *, unsigned int *, char *))(v14 + 384))(
            v40,
            &v36,
            &hstringHeader.Reserved.Reserved2[8]);
    if ( v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11D,
        (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
        (const char *)(unsigned int)v15,
        v32);
    if ( hstringHeader.Reserved.Reserved2[16] )
    {
      v16 = *(void **)hstringHeader.Reserved.Reserved1;
      *(_QWORD *)hstringHeader.Reserved.Reserved1 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[8];
      if ( v16 )
        CoTaskMemFree(v16);
    }
    v38 = 0;
    v17 = SRDictionaryToPropertySet(v36, pv, &v38);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11F,
        (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
        (const char *)(unsigned int)v17,
        v32);
    v37 = 0;
    v18 = (**v38)(v38, &GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca, &v37);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x122,
        (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
        (const char *)(unsigned int)v18,
        v32);
    LOBYTE(v32) = 0;
    v19 = v37;
    v20 = *v37;
    string = 0;
    v21 = WindowsCreateStringReference(L"AllowedProductId", 0x10u, &hstringHeader, &string);
    if ( v21 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v21, v22, v23);
      JUMPOUT(0x18006EF55LL);
    }
    v24 = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, int *))(v20 + 64))(v19, string, &v32);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x125,
        (unsigned int)"shellcommon\\shell\\wpccore\\plugs\\apprepository.staterepo\\apprepository.staterepo.cpp",
        (const char *)(unsigned int)v24,
        v32);
    v25 = (_BYTE)v32 != 0;
    v26 = v37;
    if ( v37 )
    {
      v37 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
    }
    v27 = v38;
    if ( v38 )
    {
      v38 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD **)))(*v27)[2])(v27);
    }
    v28 = pv;
    pv = 0;
    if ( v28 )
      CoTaskMemFree(v28);
    v29 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v29 + 16LL))(v29);
    }
    v30 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    v31 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    return v25;
  }
  else
  {
    v10 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    v11 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x18006ebb0  push    rbp
0x18006ebb2  push    rbx
0x18006ebb3  push    rsi
0x18006ebb4  push    rdi
0x18006ebb5  lea     rbp, [rsp-3Fh]
0x18006ebba  sub     rsp, 98h
0x18006ebc1  mov     rax, cs:__security_cookie
0x18006ebc8  xor     rax, rsp
0x18006ebcb  mov     [rbp+57h+var_30], rax
0x18006ebcf  mov     rdi, rcx
0x18006ebd2  xor     esi, esi
0x18006ebd4  mov     [rbp+57h+var_88], rsi
0x18006ebd8  mov     [rbp+57h+string], rsi
0x18006ebdc  lea     r9, [rbp+57h+string]; string
0x18006ebe0  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18006ebe4  lea     edx, [rsi+2Ch]; length
0x18006ebe7  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_XboxPackage@@3QBGB; "Windows.Internal.StateRepository.XboxPa"...
0x18006ebee  call    cs:__imp_WindowsCreateStringReference
0x18006ebf4  test    eax, eax
0x18006ebf6  js      loc_18006EEB3
0x18006ebfc  mov     rbx, [rbp+57h+string]
0x18006ec00  mov     rcx, [rbp+57h+var_88]
0x18006ec04  test    rcx, rcx
0x18006ec07  jz      short loc_18006EC1A
0x18006ec09  mov     [rbp+57h+var_88], rsi
0x18006ec0d  mov     rax, [rcx]
0x18006ec10  mov     rax, [rax+10h]
0x18006ec14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ec19  nop
0x18006ec1a  lea     r8, [rbp+57h+var_88]
0x18006ec1e  lea     rdx, _GUID_e1a3bc26_0387_453d_b463_c296a38a35b0
0x18006ec25  mov     rcx, rbx
0x18006ec28  call    cs:__imp_RoGetActivationFactory
0x18006ec2e  mov     rcx, [rbp+5Fh]
0x18006ec32  test    eax, eax
0x18006ec34  js      loc_18006EEBB
0x18006ec3a  mov     [rbp+57h+var_80], rsi
0x18006ec3e  mov     rcx, [rbp+57h+var_88]
0x18006ec42  mov     rax, [rcx]
0x18006ec45  lea     r8, [rbp+57h+var_80]
0x18006ec49  mov     rdx, rdi
0x18006ec4c  mov     rax, [rax+0D0h]
0x18006ec53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ec58  mov     rcx, [rbp+5Fh]; this
0x18006ec5c  test    eax, eax
0x18006ec5e  js      loc_18006EED0
0x18006ec64  mov     [rbp+57h+var_78], esi
0x18006ec67  mov     rcx, [rbp+57h+var_80]
0x18006ec6b  mov     rax, [rcx]
0x18006ec6e  lea     rdx, [rbp+57h+var_78]
0x18006ec72  mov     rax, [rax+38h]
0x18006ec76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ec7b  mov     rcx, [rbp+5Fh]; this
0x18006ec7f  test    eax, eax
0x18006ec81  js      loc_18006EEE5
0x18006ec87  cmp     [rbp+57h+var_78], esi
0x18006ec8a  jnz     short loc_18006ECC7
0x18006ec8c  mov     rcx, [rbp+57h+var_80]
0x18006ec90  test    rcx, rcx
0x18006ec93  jz      short loc_18006ECA6
0x18006ec95  mov     [rbp+57h+var_80], rsi
0x18006ec99  mov     rax, [rcx]
0x18006ec9c  mov     rax, [rax+10h]
0x18006eca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eca5  nop
0x18006eca6  mov     rcx, [rbp+57h+var_88]
0x18006ecaa  test    rcx, rcx
0x18006ecad  jz      short loc_18006ECC0
0x18006ecaf  mov     [rbp+57h+var_88], rsi
0x18006ecb3  mov     rax, [rcx]
0x18006ecb6  mov     rax, [rax+10h]
0x18006ecba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ecbf  nop
0x18006ecc0  xor     al, al
0x18006ecc2  jmp     loc_18006EE86
0x18006ecc7  mov     [rbp+57h+var_58], rsi
0x18006eccb  mov     rcx, [rbp+57h+var_80]
0x18006eccf  mov     rax, [rcx]
0x18006ecd2  lea     r8, [rbp+57h+var_58]
0x18006ecd6  xor     edx, edx
0x18006ecd8  mov     rax, [rax+30h]
0x18006ecdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ece1  mov     rcx, [rbp+5Fh]; this
0x18006ece5  test    eax, eax
0x18006ece7  js      loc_18006EEFA
0x18006eced  mov     [rbp+57h+var_74], esi
0x18006ecf0  mov     [rbp+57h+pv], rsi
0x18006ecf4  mov     rcx, [rbp+57h+var_58]
0x18006ecf8  mov     rax, [rcx]
0x18006ecfb  lea     rdx, [rbp+57h+pv]
0x18006ecff  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rdx
0x18006ed03  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rsi
0x18006ed07  mov     byte ptr [rbp+57h+hstringHeader.Reserved+10h], 1
0x18006ed0b  lea     r8, [rbp+57h+hstringHeader.Reserved+8]
0x18006ed0f  lea     rdx, [rbp+57h+var_74]
0x18006ed13  mov     rax, [rax+180h]
0x18006ed1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ed1f  mov     rcx, [rbp+5Fh]; this
0x18006ed23  test    eax, eax
0x18006ed25  js      loc_18006EF0F
0x18006ed2b  cmp     byte ptr [rbp+57h+hstringHeader.Reserved+10h], sil
0x18006ed2f  jz      short loc_18006ED4A
0x18006ed31  mov     rdx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x18006ed35  mov     rcx, [rdx]; pv
0x18006ed38  mov     rax, qword ptr [rbp+57h+hstringHeader.Reserved+8]
0x18006ed3c  mov     [rdx], rax
0x18006ed3f  test    rcx, rcx
0x18006ed42  jz      short loc_18006ED4A
0x18006ed44  call    cs:__imp_CoTaskMemFree
0x18006ed4a  mov     [rbp+57h+var_68], rsi
0x18006ed4e  lea     r8, [rbp+57h+var_68]
0x18006ed52  mov     rdx, [rbp+57h+pv]
0x18006ed56  mov     ecx, [rbp+57h+var_74]
0x18006ed59  call    cs:__imp_SRDictionaryToPropertySet
0x18006ed5f  mov     rcx, [rbp+5Fh]; this
0x18006ed63  test    eax, eax
0x18006ed65  js      loc_18006EF24
0x18006ed6b  mov     [rbp+57h+var_70], rsi
0x18006ed6f  mov     rcx, [rbp+57h+var_68]
0x18006ed73  mov     rax, [rcx]
0x18006ed76  lea     r8, [rbp+57h+var_70]
0x18006ed7a  lea     rdx, _GUID_1b0d3570_0877_5ec2_8a2c_3b9539506aca
0x18006ed81  mov     rax, [rax]
0x18006ed84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ed89  nop
0x18006ed8a  mov     rcx, [rbp+5Fh]; this
0x18006ed8e  test    eax, eax
0x18006ed90  js      loc_18006EF39
0x18006ed96  mov     byte ptr [rbp+57h+var_90], sil
0x18006ed9a  mov     rbx, [rbp+57h+var_70]
0x18006ed9e  mov     rdi, [rbx]
0x18006eda1  mov     [rbp+57h+string], rsi
0x18006eda5  lea     r9, [rbp+57h+string]; string
0x18006eda9  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18006edad  mov     edx, 10h; length
0x18006edb2  lea     rcx, aAllowedproduct; "AllowedProductId"
0x18006edb9  call    cs:__imp_WindowsCreateStringReference
0x18006edbf  test    eax, eax
0x18006edc1  js      loc_18006EF4E
0x18006edc7  lea     r8, [rbp+57h+var_90]
0x18006edcb  mov     rdx, [rbp+57h+string]
0x18006edcf  mov     rcx, rbx
0x18006edd2  mov     rax, [rdi+40h]
0x18006edd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006eddb  mov     rcx, [rbp+5Fh]; this
0x18006eddf  test    eax, eax
0x18006ede1  js      loc_18006EE9E
0x18006ede7  cmp     byte ptr [rbp+57h+var_90], sil
0x18006edeb  setnz   bl
0x18006edee  mov     rcx, [rbp+57h+var_70]
0x18006edf2  test    rcx, rcx
0x18006edf5  jz      short loc_18006EE08
0x18006edf7  mov     [rbp+57h+var_70], rsi
0x18006edfb  mov     rax, [rcx]
0x18006edfe  mov     rax, [rax+10h]
0x18006ee02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ee07  nop
0x18006ee08  mov     rcx, [rbp+57h+var_68]
0x18006ee0c  test    rcx, rcx
0x18006ee0f  jz      short loc_18006EE22
0x18006ee11  mov     [rbp+57h+var_68], rsi
0x18006ee15  mov     rax, [rcx]
0x18006ee18  mov     rax, [rax+10h]
0x18006ee1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ee21  nop
0x18006ee22  mov     rcx, [rbp+57h+pv]; pv
0x18006ee26  mov     [rbp+57h+pv], rsi
0x18006ee2a  test    rcx, rcx
0x18006ee2d  jz      short loc_18006EE36
0x18006ee2f  call    cs:__imp_CoTaskMemFree
0x18006ee35  nop
0x18006ee36  mov     rcx, [rbp+57h+var_58]
0x18006ee3a  test    rcx, rcx
0x18006ee3d  jz      short loc_18006EE50
0x18006ee3f  mov     [rbp+57h+var_58], rsi
0x18006ee43  mov     rax, [rcx]
0x18006ee46  mov     rax, [rax+10h]
0x18006ee4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ee4f  nop
0x18006ee50  mov     rcx, [rbp+57h+var_80]
0x18006ee54  test    rcx, rcx
0x18006ee57  jz      short loc_18006EE6A
0x18006ee59  mov     [rbp+57h+var_80], rsi
0x18006ee5d  mov     rax, [rcx]
0x18006ee60  mov     rax, [rax+10h]
0x18006ee64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ee69  nop
0x18006ee6a  mov     rcx, [rbp+57h+var_88]
0x18006ee6e  test    rcx, rcx
0x18006ee71  jz      short loc_18006EE84
0x18006ee73  mov     [rbp+57h+var_88], rsi
0x18006ee77  mov     rdx, [rcx]
0x18006ee7a  mov     rax, [rdx+10h]
0x18006ee7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ee83  nop
0x18006ee84  mov     al, bl
0x18006ee86  mov     rcx, [rbp+57h+var_30]
0x18006ee8a  xor     rcx, rsp; StackCookie
0x18006ee8d  call    __security_check_cookie
0x18006ee92  add     rsp, 98h
0x18006ee99  pop     rdi
0x18006ee9a  pop     rsi
0x18006ee9b  pop     rbx
0x18006ee9c  pop     rbp
0x18006ee9d  retn
0x18006ee9e  mov     r9d, eax; char *
0x18006eea1  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006eea8  mov     edx, 125h; void *
0x18006eead  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006eeb3  mov     ecx, eax; this
0x18006eeb5  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18006eeba  nop
0x18006eebb  mov     r9d, eax; char *
0x18006eebe  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006eec5  mov     edx, 10Bh; void *
0x18006eeca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006eed0  mov     r9d, eax; char *
0x18006eed3  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006eeda  mov     edx, 10Eh; void *
0x18006eedf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006eee5  mov     r9d, eax; char *
0x18006eee8  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006eeef  mov     edx, 111h; void *
0x18006eef4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006eefa  mov     r9d, eax; char *
0x18006eefd  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006ef04  mov     edx, 119h; void *
0x18006ef09  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006ef0f  mov     r9d, eax; char *
0x18006ef12  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006ef19  mov     edx, 11Dh; void *
0x18006ef1e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006ef24  mov     r9d, eax; char *
0x18006ef27  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006ef2e  mov     edx, 11Fh; void *
0x18006ef33  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006ef39  mov     r9d, eax; char *
0x18006ef3c  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\wpccore\\plugs\\app"...
0x18006ef43  mov     edx, 122h; void *
0x18006ef48  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006ef4e  mov     ecx, eax; this
0x18006ef50  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
