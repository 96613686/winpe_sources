# CTitleBarPersistence::RuntimeClassInitialize(ushort const *)

- ea: `0x1800243a4`
- end: `0x1800249d2`
- name: `?RuntimeClassInitialize@CTitleBarPersistence@@QEAAJPEBG@Z`
- size: `1582`
- prototype: `__int64 __fastcall(CTitleBarPersistence *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180024200`

## callees

- `0x180004c98`
- `0x1800116c0`
- `0x18001e260`
- `0x180024184`
- `0x1800243a4`
- `0x1800249d8`
- `0x180024a98`
- `0x180024c40`
- `0x180025974`
- `0x180034f28`
- `0x180040270`
- `0x18004092c`
- `0x18004194c`
- `0x180041ec0`
- `0x180043c30`
- `0x18006194c`
- `0x180061a50`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002459a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024664`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800249cb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18002459a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180024664`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800249cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024584`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002464e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180024584`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002464e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800246e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800246f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024938`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024947`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800249a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800249af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800246e1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800246f0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024938`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024947`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800249a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800249af`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800244f1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180024844`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800244f1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180024844`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800247a0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800247a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002486a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800248f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002495d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002486a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800248f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002495d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800245b0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800245b0`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800248cf`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1800248cf`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18002450a`
- `api-ms-win-appmodel-state-l1-2-0!CloseState` at `0x18002450a`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x18002446f`
- `api-ms-win-appmodel-state-l1-2-0!OpenStateExplicit` at `0x18002446f`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CTitleBarPersistence::RuntimeClassInitialize(HKEY *this, unsigned __int16 *a2)
{
  LPCWSTR *v4; // r13
  unsigned __int64 v5; // r14
  int v6; // eax
  unsigned int v7; // ebx
  int PackageFamilyNameFromAumid; // eax
  void *v10; // rbx
  void *v11; // rdx
  CallerIdentity *v12; // rsi
  unsigned __int16 *v13; // r8
  int StateRegKey; // eax
  unsigned int Key; // eax
  void *v16; // rdx
  unsigned int v17; // r8d
  int PackageFullNameFromAppId; // eax
  unsigned int v19; // esi
  HRESULT v20; // eax
  int ActivationFactory; // eax
  HKEY *v22; // rcx
  HKEY *v23; // r12
  WCHAR *v24; // rsi
  unsigned int v25; // eax
  UINT32 v26; // edx
  HRESULT v27; // eax
  int v28; // eax
  unsigned int v29; // r14d
  __int64 v30; // rcx
  HKEY *v31; // rcx
  int v32; // eax
  unsigned int v33; // r14d
  HKEY *v34; // rcx
  LSTATUS ValueW; // eax
  bool v36; // sf
  int v37; // eax
  HKEY *v38; // rcx
  unsigned int v39; // eax
  unsigned int v40; // r8d
  HKEY *v41; // rcx
  unsigned int v42; // eax
  unsigned int v43; // r8d
  unsigned int v44; // edi
  __int64 v45; // rcx
  HKEY *v46; // rcx
  __int64 v47; // rcx
  HKEY *v48; // rcx
  HKEY *dwOptions; // [rsp+20h] [rbp-89h]
  int dwOptionsa; // [rsp+20h] [rbp-89h]
  int dwOptionsb; // [rsp+20h] [rbp-89h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-89h]
  unsigned int dwOptionsd; // [rsp+20h] [rbp-89h]
  HKEY *v54; // [rsp+50h] [rbp-59h] BYREF
  __int64 v55; // [rsp+58h] [rbp-51h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-49h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-41h] BYREF
  DWORD pcbData; // [rsp+70h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-31h] BYREF
  PCWSTR sourceString[3]; // [rsp+80h] [rbp-29h] BYREF
  HKEY pvData; // [rsp+98h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-9h] BYREF
  HSTRING string; // [rsp+B8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v4 = (LPCWSTR *)(this + 8);
  v5 = -1;
  v6 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
         this + 8,
         a2,
         -1);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebarpersistence.cpp",
      (const char *)(unsigned int)v6,
      (int)dwOptions);
    return v7;
  }
  pv = 0;
  PackageFamilyNameFromAumid = GetPackageFamilyNameFromAumid(a2, (unsigned __int16 **)&pv);
  v7 = PackageFamilyNameFromAumid;
  if ( PackageFamilyNameFromAumid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebarpersistence.cpp",
      (const char *)(unsigned int)PackageFamilyNameFromAumid,
      (int)dwOptions);
LABEL_57:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pv);
    return v7;
  }
  v10 = pv;
  v12 = (CallerIdentity *)OpenStateExplicit(-6, pv);
  if ( v12 || (int)ResultFromKnownLastError() >= 0 )
  {
    hKey = 0;
    StateRegKey = CallerIdentity::GetStateRegKey(v12, v11, v13, (unsigned int)&hKey, dwOptions);
    if ( StateRegKey >= 0 )
    {
      Key = RegCreateKeyExW(hKey, L"PersistedTitleBarData", 0, 0, 0, 0xF003Fu, 0, this + 7, 0);
      if ( Key )
        wil::details::in1diag3::_Log_Win32(retaddr, v16, v17, (const char *)Key, (unsigned int)dwOptions);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebarpersistence.cpp",
        (const char *)(unsigned int)StateRegKey,
        dwOptionsa);
    }
    CloseState(v12);
    CAutoHandle<HKEY__ *>::~CAutoHandle<HKEY__ *>(&hKey);
  }
  sourceString[0] = 0;
  sourceString[1] = (PCWSTR)-1LL;
  sourceString[2] = (PCWSTR)-1LL;
  PackageFullNameFromAppId = CallerIdentity::GetPackageFullNameFromAppId(
                               (CallerIdentity *)a2,
                               (const unsigned __int16 *)sourceString,
                               (unsigned __int16 **)v13);
  v19 = PackageFullNameFromAppId;
  if ( PackageFullNameFromAppId < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebarpersistence.cpp",
      (const char *)(unsigned int)PackageFullNameFromAppId,
      (int)dwOptions);
LABEL_15:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(sourceString);
    v7 = v19;
    goto LABEL_57;
  }
  v54 = 0;
  v55 = 0;
  string = 0;
  v20 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Package", 0x28u, &hstringHeader, &string);
  if ( v20 < 0 )
  {
    RaiseException(v20, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v54);
  v19 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebarpersistence.cpp",
      (const char *)(unsigned int)ActivationFactory,
      (int)dwOptions);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v55);
    v22 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*((void (__fastcall **)(HKEY *))*v22 + 2))(v22);
    }
    goto LABEL_15;
  }
  v23 = v54;
  hKey = *v54;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v55);
  string = 0;
  v24 = (WCHAR *)sourceString[0];
  do
    ++v5;
  while ( sourceString[0][v5] );
  if ( v5 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    JUMPOUT(0x1800249D1LL);
  }
  v25 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v5);
  v26 = v25 - 1;
  if ( (unsigned int)v5 < v25 )
    v26 = v5;
  v27 = WindowsCreateStringReference(v24, v26, &hstringHeader, &string);
  if ( v27 < 0 )
    RaiseException(v27, 1u, 0, 0);
  v28 = (*((__int64 (__fastcall **)(HKEY *, HSTRING, __int64 *))hKey + 22))(v23, string, &v55);
  v29 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebarpersistence.cpp",
      (const char *)(unsigned int)v28,
      (int)dwOptions);
    v30 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    }
    v31 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*((void (__fastcall **)(HKEY *))*v31 + 2))(v31);
    }
    if ( v24 )
      CoTaskMemFree(v24);
    if ( v10 )
      CoTaskMemFree(v10);
    return v29;
  }
  v32 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v55 + 104LL))(v55, (char *)this + 88);
  v33 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebarpersistence.cpp",
      (const char *)(unsigned int)v32,
      (int)dwOptions);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v55);
    v34 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*((void (__fastcall **)(HKEY *))*v34 + 2))(v34);
    }
LABEL_42:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(sourceString);
    v7 = v33;
    goto LABEL_57;
  }
  pvData = 0;
  pcbData = 8;
  ValueW = RegGetValueW(this[7], *v4, L"AppVersion", 0x48u, 0, &pvData, &pcbData);
  v36 = ValueW < 0;
  if ( ValueW > 0 )
    v36 = 1;
  if ( v36 || pvData != this[11] )
  {
    v37 = CTitleBarPersistence::PackageVersionMismatchDetected((CTitleBarPersistence *)this);
    v33 = v37;
    if ( v37 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E,
        (unsigned int)"pcshell\\shell\\applicationframe\\frame\\lib\\titlebarpersistence.cpp",
        (const char *)(unsigned int)v37,
        dwOptionsb);
      Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v55);
      v38 = v54;
      if ( v54 )
      {
        v54 = 0;
        (*((void (__fastcall **)(HKEY *))*v38 + 2))(v38);
      }
      goto LABEL_42;
    }
  }
  phkResult = 0;
  v39 = RegCreateKeyExW(this[7], *v4, 0, 0, 0, 2u, 0, &phkResult, 0);
  if ( v39 )
  {
    v7 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x62, v40, (const char *)v39, dwOptionsc);
    if ( phkResult )
      RegCloseKey(phkResult);
    Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(&v55);
    v41 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*((void (__fastcall **)(HKEY *))*v41 + 2))(v41);
    }
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(sourceString);
    goto LABEL_57;
  }
  v42 = RegSetKeyValueW(this[7], *v4, L"AppVersion", 0xBu, this + 11, 8u);
  if ( v42 )
  {
    v44 = wil::details::in1diag3::Return_Win32(retaddr, (void *)0x63, v43, (const char *)v42, dwOptionsd);
    if ( phkResult )
      RegCloseKey(phkResult);
    v45 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    }
    v46 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*((void (__fastcall **)(HKEY *))*v46 + 2))(v46);
    }
    if ( v24 )
      CoTaskMemFree(v24);
    if ( v10 )
      CoTaskMemFree(v10);
    return v44;
  }
  else
  {
    if ( phkResult )
      RegCloseKey(phkResult);
    v47 = v55;
    if ( v55 )
    {
      v55 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    }
    v48 = v54;
    if ( v54 )
    {
      v54 = 0;
      (*((void (__fastcall **)(HKEY *))*v48 + 2))(v48);
    }
    if ( v24 )
      CoTaskMemFree(v24);
    if ( v10 )
      CoTaskMemFree(v10);
    return 0;
  }
}

```

## disassembly

```asm
0x1800243a4  mov     [rsp-8+arg_10], rbx
0x1800243a9  push    rbp
0x1800243aa  push    rsi
0x1800243ab  push    rdi
0x1800243ac  push    r12
0x1800243ae  push    r13
0x1800243b0  push    r14
0x1800243b2  push    r15
0x1800243b4  lea     rbp, [rsp-27h]
0x1800243b9  sub     rsp, 0D0h
0x1800243c0  mov     rax, cs:__security_cookie
0x1800243c7  xor     rax, rsp
0x1800243ca  mov     [rbp+57h+var_40], rax
0x1800243ce  mov     r12, rdx
0x1800243d1  mov     r15, rcx
0x1800243d4  lea     r13, [rcx+40h]
0x1800243d8  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800243dc  mov     r8, r14
0x1800243df  mov     rcx, r13
0x1800243e2  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800243e7  mov     ebx, eax
0x1800243e9  xor     edi, edi
0x1800243eb  test    eax, eax
0x1800243ed  jns     short loc_18002442E
0x1800243ef  mov     rcx, [rbp+5Fh]; this
0x1800243f3  mov     r9d, eax; char *
0x1800243f6  lea     r8, aPcshellShellAp; "pcshell\\shell\\applicationframe\\frame"...
0x1800243fd  lea     edx, [rdi+3Ah]; void *
0x180024400  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024405  mov     eax, ebx
0x180024407  mov     rcx, [rbp+57h+var_40]
0x18002440b  xor     rcx, rsp; StackCookie
0x18002440e  call    __security_check_cookie
0x180024413  mov     rbx, [rsp+100h+arg_10]
0x18002441b  add     rsp, 0D0h
0x180024422  pop     r15
0x180024424  pop     r14
0x180024426  pop     r13
0x180024428  pop     r12
0x18002442a  pop     rdi
0x18002442b  pop     rsi
0x18002442c  pop     rbp
0x18002442d  retn
0x18002442e  mov     [rbp+57h+pv], rdi
0x180024432  lea     rdx, [rbp+57h+pv]; unsigned __int16 **
0x180024436  mov     rcx, r12; unsigned __int16 *
0x180024439  call    ?GetPackageFamilyNameFromAumid@@YAJPEBGPEAPEAG@Z; GetPackageFamilyNameFromAumid(ushort const *,ushort * *)
0x18002443e  mov     ebx, eax
0x180024440  test    eax, eax
0x180024442  jns     short loc_180024461
0x180024444  mov     rcx, [rbp+5Fh]; this
0x180024448  mov     r9d, eax; char *
0x18002444b  lea     r8, aPcshellShellAp; "pcshell\\shell\\applicationframe\\frame"...
0x180024452  mov     edx, 3Ch ; '<'; void *
0x180024457  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002445c  jmp     loc_18002489F
0x180024461  mov     rbx, [rbp+57h+pv]
0x180024465  mov     rdx, rbx
0x180024468  mov     rcx, 0FFFFFFFFFFFFFFFAh
0x18002446f  call    cs:__imp_OpenStateExplicit
0x180024475  mov     rsi, rax
0x180024478  lea     rdi, aPcshellShellAp; "pcshell\\shell\\applicationframe\\frame"...
0x18002447f  test    rax, rax
0x180024482  jnz     short loc_180024491
0x180024484  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180024489  test    eax, eax
0x18002448b  js      loc_18002451A
0x180024491  mov     [rbp+57h+hKey], 0
0x180024499  lea     r9, [rbp+57h+hKey]; unsigned int
0x18002449d  mov     rcx, rsi; this
0x1800244a0  call    ?GetStateRegKey@CallerIdentity@@YAJPEAXPEBGKPEAPEAUHKEY__@@@Z; CallerIdentity::GetStateRegKey(void *,ushort const *,ulong,HKEY__ * *)
0x1800244a5  mov     rcx, [rbp+5Fh]; this
0x1800244a9  xor     edx, edx
0x1800244ab  test    eax, eax
0x1800244ad  jns     short loc_1800244C1
0x1800244af  mov     r9d, eax; char *
0x1800244b2  mov     r8, rdi; unsigned int
0x1800244b5  mov     edx, 41h ; 'A'; void *
0x1800244ba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800244bf  jmp     short loc_180024507
0x1800244c1  lea     rax, [r15+38h]
0x1800244c5  mov     [rsp+100h+lpdwDisposition], rdx; lpdwDisposition
0x1800244ca  mov     [rsp+100h+phkResult], rax; phkResult
0x1800244cf  mov     [rsp+100h+lpSecurityAttributes], rdx; lpSecurityAttributes
0x1800244d4  mov     [rsp+100h+samDesired], 0F003Fh; samDesired
0x1800244dc  mov     [rsp+100h+dwOptions], edx; int
0x1800244e0  xor     r9d, r9d; lpClass
0x1800244e3  xor     r8d, r8d; Reserved
0x1800244e6  lea     rdx, aPersistedtitle; "PersistedTitleBarData"
0x1800244ed  mov     rcx, [rbp+57h+hKey]; hKey
0x1800244f1  call    cs:__imp_RegCreateKeyExW
0x1800244f7  mov     rcx, [rbp+5Fh]; this
0x1800244fb  test    eax, eax
0x1800244fd  jz      short loc_180024507
0x1800244ff  mov     r9d, eax; char *
0x180024502  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180024507  mov     rcx, rsi
0x18002450a  call    cs:__imp_CloseState
0x180024510  nop
0x180024511  lea     rcx, [rbp+57h+hKey]
0x180024515  call    ??1?$CAutoHandle@PEAUHKEY__@@@@QEAA@XZ; CAutoHandle<HKEY__ *>::~CAutoHandle<HKEY__ *>(void)
0x18002451a  mov     [rbp+57h+sourceString], 0
0x180024522  mov     [rbp+57h+var_78], r14
0x180024526  mov     [rbp+57h+var_70], r14
0x18002452a  lea     rdx, [rbp+57h+sourceString]; unsigned __int16 *
0x18002452e  mov     rcx, r12; this
0x180024531  call    ?GetPackageFullNameFromAppId@CallerIdentity@@YAJPEBGPEAPEAG@Z; CallerIdentity::GetPackageFullNameFromAppId(ushort const *,ushort * *)
0x180024536  mov     esi, eax
0x180024538  xor     r12d, r12d
0x18002453b  test    eax, eax
0x18002453d  jns     short loc_180024564
0x18002453f  mov     rcx, [rbp+5Fh]; this
0x180024543  mov     r9d, eax; char *
0x180024546  mov     r8, rdi; unsigned int
0x180024549  lea     edx, [r12+51h]; void *
0x18002454e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024553  nop
0x180024554  lea     rcx, [rbp+57h+sourceString]
0x180024558  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002455d  mov     ebx, esi
0x18002455f  jmp     loc_18002489F
0x180024564  mov     [rbp+57h+var_B0], r12
0x180024568  mov     [rbp+57h+var_A8], r12
0x18002456c  mov     [rbp+57h+string], r12
0x180024570  lea     r9, [rbp+57h+string]; string
0x180024574  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180024578  mov     edx, 28h ; '('; length
0x18002457d  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180024584  call    cs:__imp_WindowsCreateStringReference
0x18002458a  test    eax, eax
0x18002458c  jns     short loc_1800245A1
0x18002458e  xor     r9d, r9d; lpArguments
0x180024591  xor     r8d, r8d; nNumberOfArguments
0x180024594  lea     edx, [r9+1]; dwExceptionFlags
0x180024598  mov     ecx, eax; dwExceptionCode
0x18002459a  call    cs:__imp_RaiseException
0x1800245a0  int     3; Trap to Debugger
0x1800245a1  lea     r8, [rbp+57h+var_B0]
0x1800245a5  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x1800245ac  mov     rcx, [rbp+57h+string]
0x1800245b0  call    cs:__imp_RoGetActivationFactory
0x1800245b6  mov     esi, eax
0x1800245b8  test    eax, eax
0x1800245ba  jns     short loc_1800245FA
0x1800245bc  mov     rcx, [rbp+5Fh]; this
0x1800245c0  mov     r9d, eax; char *
0x1800245c3  mov     r8, rdi; unsigned int
0x1800245c6  mov     edx, 55h ; 'U'; void *
0x1800245cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800245d0  nop
0x1800245d1  lea     rcx, [rbp+57h+var_A8]
0x1800245d5  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x1800245da  nop
0x1800245db  mov     rcx, [rbp+57h+var_B0]
0x1800245df  test    rcx, rcx
0x1800245e2  jz      short loc_1800245F5
0x1800245e4  mov     [rbp+57h+var_B0], r12
0x1800245e8  mov     rax, [rcx]
0x1800245eb  mov     rax, [rax+10h]
0x1800245ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245f4  nop
0x1800245f5  jmp     loc_180024554
0x1800245fa  mov     r12, [rbp+57h+var_B0]
0x1800245fe  mov     rax, [r12]
0x180024602  mov     [rbp+57h+hKey], rax
0x180024606  lea     rcx, [rbp+57h+var_A8]
0x18002460a  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002460f  xor     eax, eax
0x180024611  mov     [rbp+57h+string], rax
0x180024615  mov     rsi, [rbp+57h+sourceString]
0x180024619  inc     r14
0x18002461c  cmp     [rsi+r14*2], ax
0x180024621  jnz     short loc_180024619
0x180024623  mov     eax, 0FFFFFFFFh
0x180024628  cmp     r14, rax
0x18002462b  ja      loc_1800249BC
0x180024631  mov     ecx, r14d; unsigned int
0x180024634  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180024639  lea     edx, [rax-1]
0x18002463c  cmp     r14d, eax
0x18002463f  cmovb   edx, r14d; length
0x180024643  lea     r9, [rbp+57h+string]; string
0x180024647  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18002464b  mov     rcx, rsi; sourceString
0x18002464e  call    cs:__imp_WindowsCreateStringReference
0x180024654  test    eax, eax
0x180024656  jns     short loc_18002466B
0x180024658  xor     r9d, r9d; lpArguments
0x18002465b  xor     r8d, r8d; nNumberOfArguments
0x18002465e  lea     edx, [r9+1]; dwExceptionFlags
0x180024662  mov     ecx, eax; dwExceptionCode
0x180024664  call    cs:__imp_RaiseException
0x18002466a  nop
0x18002466b  lea     r8, [rbp+57h+var_A8]
0x18002466f  mov     rdx, [rbp+57h+string]
0x180024673  mov     rcx, r12
0x180024676  mov     rax, [rbp+57h+hKey]
0x18002467a  mov     rax, [rax+0B0h]
0x180024681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024686  mov     r14d, eax
0x180024689  xor     r12d, r12d
0x18002468c  test    eax, eax
0x18002468e  jns     short loc_1800246FE
0x180024690  mov     rcx, [rbp+5Fh]; this
0x180024694  mov     r9d, eax; char *
0x180024697  mov     r8, rdi; unsigned int
0x18002469a  lea     edx, [r12+56h]; void *
0x18002469f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800246a4  nop
0x1800246a5  mov     rcx, [rbp+57h+var_A8]
0x1800246a9  test    rcx, rcx
0x1800246ac  jz      short loc_1800246BF
0x1800246ae  mov     [rbp+57h+var_A8], r12
0x1800246b2  mov     rax, [rcx]
0x1800246b5  mov     rax, [rax+10h]
0x1800246b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246be  nop
0x1800246bf  mov     rcx, [rbp+57h+var_B0]
0x1800246c3  test    rcx, rcx
0x1800246c6  jz      short loc_1800246D9
0x1800246c8  mov     [rbp+57h+var_B0], r12
0x1800246cc  mov     rax, [rcx]
0x1800246cf  mov     rax, [rax+10h]
0x1800246d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246d8  nop
0x1800246d9  test    rsi, rsi
0x1800246dc  jz      short loc_1800246E8
0x1800246de  mov     rcx, rsi; pv
0x1800246e1  call    cs:__imp_CoTaskMemFree
0x1800246e7  nop
0x1800246e8  test    rbx, rbx
0x1800246eb  jz      short loc_1800246F6
0x1800246ed  mov     rcx, rbx; pv
0x1800246f0  call    cs:__imp_CoTaskMemFree
0x1800246f6  mov     eax, r14d
0x1800246f9  jmp     loc_180024407
0x1800246fe  mov     rcx, [rbp+57h+var_A8]
0x180024702  lea     r12, [r15+58h]
0x180024706  mov     rax, [rcx]
0x180024709  mov     rdx, r12
0x18002470c  mov     rax, [rax+68h]
0x180024710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024715  mov     r14d, eax
0x180024718  test    eax, eax
0x18002471a  jns     short loc_180024768
0x18002471c  mov     rcx, [rbp+5Fh]; this
0x180024720  mov     r9d, eax; char *
0x180024723  mov     r8, rdi; unsigned int
0x180024726  mov     edx, 57h ; 'W'; void *
0x18002472b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024730  nop
0x180024731  lea     rcx, [rbp+57h+var_A8]
0x180024735  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18002473a  nop
0x18002473b  mov     rcx, [rbp+57h+var_B0]
0x18002473f  xor     eax, eax
0x180024741  test    rcx, rcx
0x180024744  jz      short loc_180024757
0x180024746  mov     [rbp+57h+var_B0], rax
0x18002474a  mov     rax, [rcx]
0x18002474d  mov     rax, [rax+10h]
0x180024751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024756  nop
0x180024757  lea     rcx, [rbp+57h+sourceString]
0x18002475b  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180024760  mov     ebx, r14d
0x180024763  jmp     loc_18002489F
0x180024768  xor     r14d, r14d
0x18002476b  mov     [rbp+57h+pvData], r14
0x18002476f  mov     [rbp+57h+pcbData], 8
0x180024776  lea     rax, [rbp+57h+pcbData]
0x18002477a  mov     [rsp+100h+lpSecurityAttributes], rax; pcbData
0x18002477f  lea     rax, [rbp+57h+pvData]
0x180024783  mov     qword ptr [rsp+100h+samDesired], rax; pvData
0x180024788  mov     qword ptr [rsp+100h+dwOptions], r14; int
0x18002478d  lea     r9d, [r14+48h]; dwFlags
0x180024791  lea     r8, ValueName; "AppVersion"
0x180024798  mov     rdx, [r13+0]; lpSubKey
0x18002479c  mov     rcx, [r15+38h]; hkey
0x1800247a0  call    cs:__imp_RegGetValueW
0x1800247a6  test    eax, eax
0x1800247a8  jle     short loc_1800247B4
0x1800247aa  movzx   eax, ax
0x1800247ad  or      eax, 80070000h
0x1800247b2  test    eax, eax
0x1800247b4  js      short loc_1800247C0
0x1800247b6  mov     rax, [r12]
0x1800247ba  cmp     [rbp+57h+pvData], rax
0x1800247be  jz      short loc_180024812
0x1800247c0  mov     rcx, r15; this
0x1800247c3  call    ?PackageVersionMismatchDetected@CTitleBarPersistence@@AEAAJXZ; CTitleBarPersistence::PackageVersionMismatchDetected(void)
0x1800247c8  mov     r14d, eax
0x1800247cb  test    eax, eax
0x1800247cd  jns     short loc_18002480F
0x1800247cf  mov     rcx, [rbp+5Fh]; this
0x1800247d3  mov     r9d, eax; char *
0x1800247d6  mov     r8, rdi; unsigned int
0x1800247d9  mov     edx, 5Eh ; '^'; void *
0x1800247de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800247e3  nop
  ... truncated ...
```
