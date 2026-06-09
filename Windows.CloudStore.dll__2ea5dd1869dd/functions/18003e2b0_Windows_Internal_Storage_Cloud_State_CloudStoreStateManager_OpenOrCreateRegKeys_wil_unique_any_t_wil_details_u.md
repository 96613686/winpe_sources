# Windows::Internal::Storage::Cloud::State::CloudStoreStateManager::OpenOrCreateRegKeys(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)

- ea: `0x18003e2b0`
- end: `0x18003e668`
- name: `?OpenOrCreateRegKeys@CloudStoreStateManager@State@Cloud@Storage@Internal@Windows@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@0@Z`
- size: `952`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003c7b8`

## callees

- `0x180014aac`
- `0x180016cf4`
- `0x18003e2b0`
- `0x18003e670`
- `0x18003e6b4`
- `0x18003e904`
- `0x18003f11c`
- `0x180065614`
- `0x18009104c`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e51a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e538`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e51a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e538`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e52d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e54b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e52d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e54b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e3ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e46e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e3ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e46e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003e588`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003e60c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003e588`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003e60c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e4f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e525`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e543`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e4f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e525`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003e543`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e5ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e5bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e5ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003e5bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e4e9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003e4e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
LSTATUS __fastcall Windows::Internal::Storage::Cloud::State::CloudStoreStateManager::OpenOrCreateRegKeys(
        __int64 a1,
        HKEY *a2,
        HKEY *a3,
        HKEY *a4)
{
  HKEY v7; // rdi
  HKEY v8; // rdi
  HSTRING v9; // rbx
  __int64 *v10; // rcx
  __int64 v11; // rax
  int v12; // edi
  __int64 v13; // rdx
  const unsigned __int16 *StringRawBuffer; // rdi
  HSTRING v15; // rcx
  CloudStoreUtilities *v16; // rax
  int RegistryRootKey; // eax
  LSTATUS v18; // edi
  char IsSuccessOrNotFoundWin32Error; // al
  unsigned __int64 v20; // r9
  LSTATUS Key; // eax
  char v22; // di
  int v23; // esi
  LSTATUS result; // eax
  unsigned __int64 v25; // r9
  DWORD LastError; // ebx
  DWORD v27; // ebx
  int phkResult; // [rsp+20h] [rbp-60h]
  int phkResulta; // [rsp+20h] [rbp-60h]
  int phkResultb; // [rsp+20h] [rbp-60h]
  HKEY *p_hKey; // [rsp+50h] [rbp-30h]
  struct _SECURITY_ATTRIBUTES v32; // [rsp+58h] [rbp-28h] BYREF
  HKEY v33; // [rsp+70h] [rbp-10h] BYREF
  char v34; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  HKEY hKey; // [rsp+C0h] [rbp+40h] BYREF
  __int64 v37; // [rsp+C8h] [rbp+48h] BYREF
  HSTRING v38; // [rsp+D0h] [rbp+50h] BYREF

  LODWORD(hKey) = 0;
  v7 = *a3;
  if ( *a3 )
  {
    LastError = GetLastError();
    RegCloseKey(v7);
    SetLastError(LastError);
  }
  *a3 = 0;
  v8 = *a2;
  if ( *a2 )
  {
    v27 = GetLastError();
    RegCloseKey(v8);
    SetLastError(v27);
  }
  *a2 = 0;
  hKey = 0;
  v9 = 0;
  v38 = 0;
  v10 = *(__int64 **)(a1 + 40);
  if ( !v10 )
    goto LABEL_9;
  v37 = 0;
  v11 = *v10;
  *(_QWORD *)&v32.bInheritHandle = &v37;
  v33 = 0;
  v34 = 1;
  v12 = (*(__int64 (__fastcall **)(__int64 *, HKEY *))(v11 + 48))(v10, &v33);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(&v32.bInheritHandle);
  if ( v12 >= 0 )
  {
    v13 = v37;
    v37 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(
      &v38,
      v13);
    v9 = v38;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v37);
  if ( v9 )
    StringRawBuffer = WindowsGetStringRawBuffer(v9, 0);
  else
LABEL_9:
    StringRawBuffer = 0;
  v15 = *(HSTRING *)(a1 + 48);
  if ( v15 )
    v16 = (CloudStoreUtilities *)WindowsGetStringRawBuffer(v15, 0);
  else
    v16 = 0;
  p_hKey = &hKey;
  *(_QWORD *)&v32.nLength = 0;
  LOBYTE(v32.lpSecurityDescriptor) = 1;
  RegistryRootKey = CloudStoreUtilities::GetRegistryRootKey(v16, StringRawBuffer, &v32, a4);
  if ( RegistryRootKey < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorestatemanager.cpp",
      (const char *)(unsigned int)RegistryRootKey,
      phkResult);
  if ( LOBYTE(v32.lpSecurityDescriptor) )
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      *(_QWORD *)&v32.nLength);
  if ( *(_BYTE *)(a1 + 56) )
  {
    p_hKey = a2;
    *(_QWORD *)&v32.nLength = 0;
    LOBYTE(v32.lpSecurityDescriptor) = 1;
    v18 = RegOpenKeyExW(hKey, L"StoreInitOnce", 0, 0x20019u, (PHKEY)&v32);
    if ( LOBYTE(v32.lpSecurityDescriptor) )
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        a2,
        *(_QWORD *)&v32.nLength);
  }
  else
  {
    *(_QWORD *)&v32.bInheritHandle = a2;
    v33 = 0;
    v34 = 1;
    v18 = RegCreateKeyExW(hKey, L"StoreInitOnce", 0, 0, 0, 0xF003Fu, 0, &v33, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v32.bInheritHandle);
  }
  IsSuccessOrNotFoundWin32Error = CloudStoreUtilities::IsSuccessOrNotFoundWin32Error((unsigned int)v18);
  if ( v18 <= 0 )
    v20 = (unsigned int)v18;
  else
    v20 = (unsigned __int16)v18 | 0x80070000;
  if ( !IsSuccessOrNotFoundWin32Error )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorestatemanager.cpp",
      (const char *)v20,
      phkResulta);
  if ( v18 )
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      a2,
      0);
  if ( *(_BYTE *)(a1 + 56) )
  {
    *(_QWORD *)&v32.bInheritHandle = a3;
    v33 = 0;
    v34 = 1;
    Key = RegOpenKeyExW(hKey, L"StoreInit", 0, 0x20019u, &v33);
    v22 = 4;
  }
  else
  {
    p_hKey = a3;
    *(_QWORD *)&v32.nLength = 0;
    LOBYTE(v32.lpSecurityDescriptor) = 1;
    Key = RegCreateKeyExW(hKey, L"StoreInit", 0, 0, 1u, 0xF003Fu, 0, (PHKEY)&v32, 0);
    v22 = 8;
  }
  v23 = Key;
  if ( (v22 & 8) != 0 )
  {
    v22 &= ~8u;
    if ( LOBYTE(v32.lpSecurityDescriptor) )
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        p_hKey,
        *(_QWORD *)&v32.nLength);
  }
  if ( (v22 & 4) != 0 && v34 )
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      *(_QWORD *)&v32.bInheritHandle,
      v33);
  result = CloudStoreUtilities::IsSuccessOrNotFoundWin32Error((unsigned int)v23);
  if ( v23 <= 0 )
    v25 = (unsigned int)v23;
  else
    v25 = (unsigned __int16)v23 | 0x80070000;
  if ( !(_BYTE)result )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstorestatemanager.cpp",
      (const char *)v25,
      phkResultb);
  if ( v23 )
    result = wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
               a3,
               0);
  if ( v9 )
    result = WindowsDeleteString(v9);
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x18003e2b0  mov     [rsp-38h+arg_18], rbx
0x18003e2b5  push    rbp
0x18003e2b6  push    rsi
0x18003e2b7  push    rdi
0x18003e2b8  push    r12
0x18003e2ba  push    r13
0x18003e2bc  push    r14
0x18003e2be  push    r15
0x18003e2c0  mov     rbp, rsp
0x18003e2c3  sub     rsp, 80h
0x18003e2ca  mov     r15, r8
0x18003e2cd  mov     rsi, rdx
0x18003e2d0  mov     r14, rcx
0x18003e2d3  xor     r13d, r13d
0x18003e2d6  mov     dword ptr [rbp+hKey], r13d
0x18003e2da  mov     rdi, [r8]
0x18003e2dd  test    rdi, rdi
0x18003e2e0  jnz     loc_18003E51A
0x18003e2e6  mov     [r15], r13
0x18003e2e9  mov     rdi, [rsi]
0x18003e2ec  test    rdi, rdi
0x18003e2ef  jnz     loc_18003E538
0x18003e2f5  mov     [rsi], r13
0x18003e2f8  mov     [rbp+hKey], r13
0x18003e2fc  mov     rbx, r13
0x18003e2ff  mov     [rbp+arg_10], rbx
0x18003e303  mov     rcx, [r14+28h]
0x18003e307  test    rcx, rcx
0x18003e30a  jz      short loc_18003E36B
0x18003e30c  mov     [rbp+arg_8], r13
0x18003e310  mov     rax, [rcx]
0x18003e313  lea     rdx, [rbp+arg_8]
0x18003e317  mov     [rbp+var_18], rdx
0x18003e31b  mov     [rbp+var_10], r13
0x18003e31f  mov     [rbp+var_8], 1
0x18003e323  lea     rdx, [rbp+var_10]
0x18003e327  mov     rax, [rax+30h]
0x18003e32b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e330  mov     edi, eax
0x18003e332  lea     rcx, [rbp+var_18]
0x18003e336  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(void)
0x18003e33b  shr     edi, 1Fh
0x18003e33e  xor     dil, 1
0x18003e342  jz      short loc_18003E359
0x18003e344  mov     rdx, [rbp+arg_8]
0x18003e348  mov     [rbp+arg_8], r13
0x18003e34c  lea     rcx, [rbp+arg_10]
0x18003e350  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHSTRING__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>::reset(HSTRING__ *)
0x18003e355  mov     rbx, [rbp+arg_10]
0x18003e359  lea     rcx, [rbp+arg_8]
0x18003e35d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x18003e362  test    rbx, rbx
0x18003e365  jnz     loc_18003E5A8
0x18003e36b  mov     rdi, r13
0x18003e36e  mov     rcx, [r14+30h]; string
0x18003e372  test    rcx, rcx
0x18003e375  jnz     loc_18003E5BB
0x18003e37b  mov     rax, r13
0x18003e37e  lea     rcx, [rbp+hKey]
0x18003e382  mov     [rbp+var_30], rcx
0x18003e386  mov     [rbp+var_28], r13
0x18003e38a  mov     [rbp+var_20], 1
0x18003e38e  lea     r8, [rbp+var_28]; unsigned __int16 *
0x18003e392  mov     rdx, rdi; unsigned __int16 *
0x18003e395  mov     rcx, rax; this
0x18003e398  call    ?GetRegistryRootKey@CloudStoreUtilities@@YAJPEBG0PEAPEAUHKEY__@@@Z; CloudStoreUtilities::GetRegistryRootKey(ushort const *,ushort const *,HKEY__ * *)
0x18003e39d  mov     rcx, [rbp+38h]; this
0x18003e3a1  test    eax, eax
0x18003e3a3  js      loc_18003E5C8
0x18003e3a9  cmp     [rbp+var_20], r13b
0x18003e3ad  jz      short loc_18003E3BC
0x18003e3af  mov     rdx, [rbp+var_28]
0x18003e3b3  mov     rcx, [rbp+var_30]
0x18003e3b7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003e3bc  xor     r8d, r8d; Reserved
0x18003e3bf  lea     rdx, aStoreinitonce; "StoreInitOnce"
0x18003e3c6  mov     rcx, [rbp+hKey]; hKey
0x18003e3ca  cmp     [r14+38h], r13b
0x18003e3ce  jz      loc_18003E5DD
0x18003e3d4  mov     [rbp+var_30], rsi
0x18003e3d8  mov     [rbp+var_28], r13
0x18003e3dc  mov     [rbp+var_20], 1
0x18003e3e0  lea     rax, [rbp+var_28]
0x18003e3e4  mov     [rsp+80h+phkResult], rax; int
0x18003e3e9  mov     r9d, 20019h; samDesired
0x18003e3ef  call    cs:__imp_RegOpenKeyExW
0x18003e3f5  mov     edi, eax
0x18003e3f7  mov     r12d, r13d
0x18003e3fa  cmp     [rbp+var_20], r13b
0x18003e3fe  jz      short loc_18003E40D
0x18003e400  mov     rdx, [rbp+var_28]
0x18003e404  mov     rcx, [rbp+var_30]
0x18003e408  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003e40d  mov     ecx, edi
0x18003e40f  call    CloudStoreUtilities__IsSuccessOrNotFoundWin32Error
0x18003e414  test    edi, edi
0x18003e416  jle     loc_18003E598
0x18003e41c  movzx   r9d, di
0x18003e420  or      r9d, 80070000h; char *
0x18003e427  mov     rcx, [rbp+38h]; this
0x18003e42b  test    al, al
0x18003e42d  jz      loc_18003E625
0x18003e433  test    edi, edi
0x18003e435  jnz     loc_18003E637
0x18003e43b  xor     r8d, r8d; Reserved
0x18003e43e  lea     rdx, pszMore; "StoreInit"
0x18003e445  mov     rcx, [rbp+hKey]; hKey
0x18003e449  cmp     [r14+38h], r13b
0x18003e44d  jz      loc_18003E556
0x18003e453  mov     [rbp+var_18], r15
0x18003e457  mov     [rbp+var_10], r13
0x18003e45b  mov     [rbp+var_8], 1
0x18003e45f  lea     rax, [rbp+var_10]
0x18003e463  mov     [rsp+80h+phkResult], rax; int
0x18003e468  mov     r9d, 20019h; samDesired
0x18003e46e  call    cs:__imp_RegOpenKeyExW
0x18003e474  mov     edi, 4
0x18003e479  mov     esi, eax
0x18003e47b  or      edi, r12d
0x18003e47e  test    dil, 8
0x18003e482  jz      short loc_18003E49A
0x18003e484  and     edi, 0FFFFFFF7h
0x18003e487  cmp     [rbp+var_20], r13b
0x18003e48b  jz      short loc_18003E49A
0x18003e48d  mov     rdx, [rbp+var_28]
0x18003e491  mov     rcx, [rbp+var_30]
0x18003e495  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003e49a  test    dil, 4
0x18003e49e  jz      short loc_18003E4B3
0x18003e4a0  cmp     [rbp+var_8], r13b
0x18003e4a4  jz      short loc_18003E4B3
0x18003e4a6  mov     rdx, [rbp+var_10]
0x18003e4aa  mov     rcx, [rbp+var_18]
0x18003e4ae  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003e4b3  mov     ecx, esi
0x18003e4b5  call    CloudStoreUtilities__IsSuccessOrNotFoundWin32Error
0x18003e4ba  test    esi, esi
0x18003e4bc  jle     loc_18003E5A0
0x18003e4c2  movzx   r9d, si
0x18003e4c6  or      r9d, 80070000h; char *
0x18003e4cd  mov     rcx, [rbp+38h]; this
0x18003e4d1  test    al, al
0x18003e4d3  jz      loc_18003E646
0x18003e4d9  test    esi, esi
0x18003e4db  jnz     loc_18003E658
0x18003e4e1  test    rbx, rbx
0x18003e4e4  jz      short loc_18003E4F0
0x18003e4e6  mov     rcx, rbx; string
0x18003e4e9  call    cs:__imp_WindowsDeleteString
0x18003e4ef  nop
0x18003e4f0  mov     rcx, [rbp+hKey]; hKey
0x18003e4f4  test    rcx, rcx
0x18003e4f7  jz      short loc_18003E4FF
0x18003e4f9  call    cs:__imp_RegCloseKey
0x18003e4ff  mov     rbx, [rsp+80h+arg_18]
0x18003e507  add     rsp, 80h
0x18003e50e  pop     r15
0x18003e510  pop     r14
0x18003e512  pop     r13
0x18003e514  pop     r12
0x18003e516  pop     rdi
0x18003e517  pop     rsi
0x18003e518  pop     rbp
0x18003e519  retn
0x18003e51a  call    cs:__imp_GetLastError
0x18003e520  mov     ebx, eax
0x18003e522  mov     rcx, rdi; hKey
0x18003e525  call    cs:__imp_RegCloseKey
0x18003e52b  mov     ecx, ebx; dwErrCode
0x18003e52d  call    cs:__imp_SetLastError
0x18003e533  jmp     loc_18003E2E6
0x18003e538  call    cs:__imp_GetLastError
0x18003e53e  mov     ebx, eax
0x18003e540  mov     rcx, rdi; hKey
0x18003e543  call    cs:__imp_RegCloseKey
0x18003e549  mov     ecx, ebx; dwErrCode
0x18003e54b  call    cs:__imp_SetLastError
0x18003e551  jmp     loc_18003E2F5
0x18003e556  mov     [rbp+var_30], r15
0x18003e55a  mov     [rbp+var_28], r13
0x18003e55e  mov     [rbp+var_20], 1
0x18003e562  mov     [rsp+80h+lpdwDisposition], r13; lpdwDisposition
0x18003e567  lea     rax, [rbp+var_28]
0x18003e56b  mov     [rsp+80h+var_48], rax; phkResult
0x18003e570  mov     [rsp+80h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18003e575  mov     [rsp+80h+samDesired], 0F003Fh; samDesired
0x18003e57d  mov     dword ptr [rsp+80h+phkResult], 1; dwOptions
0x18003e585  xor     r9d, r9d; lpClass
0x18003e588  call    cs:__imp_RegCreateKeyExW
0x18003e58e  mov     edi, 8
0x18003e593  jmp     loc_18003E479
0x18003e598  mov     r9d, edi
0x18003e59b  jmp     loc_18003E427
0x18003e5a0  mov     r9d, esi
0x18003e5a3  jmp     loc_18003E4CD
0x18003e5a8  xor     edx, edx; length
0x18003e5aa  mov     rcx, rbx; string
0x18003e5ad  call    cs:__imp_WindowsGetStringRawBuffer
0x18003e5b3  mov     rdi, rax
0x18003e5b6  jmp     loc_18003E36E
0x18003e5bb  xor     edx, edx; length
0x18003e5bd  call    cs:__imp_WindowsGetStringRawBuffer
0x18003e5c3  jmp     loc_18003E37E
0x18003e5c8  mov     r9d, eax; char *
0x18003e5cb  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18003e5d2  mov     edx, 9Eh; void *
0x18003e5d7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003e5dd  mov     [rbp+var_18], rsi
0x18003e5e1  mov     [rbp+var_10], r13
0x18003e5e5  mov     [rbp+var_8], 1
0x18003e5e9  mov     [rsp+80h+lpdwDisposition], r13; lpdwDisposition
0x18003e5ee  lea     rax, [rbp+var_10]
0x18003e5f2  mov     [rsp+80h+var_48], rax; phkResult
0x18003e5f7  mov     [rsp+80h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18003e5fc  mov     [rsp+80h+samDesired], 0F003Fh; samDesired
0x18003e604  mov     dword ptr [rsp+80h+phkResult], r13d; dwOptions
0x18003e609  xor     r9d, r9d; lpClass
0x18003e60c  call    cs:__imp_RegCreateKeyExW
0x18003e612  mov     edi, eax
0x18003e614  lea     rcx, [rbp+var_18]
0x18003e618  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18003e61d  mov     r12d, r13d
0x18003e620  jmp     loc_18003E40D
0x18003e625  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18003e62c  mov     edx, 0ACh; void *
0x18003e631  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003e637  xor     edx, edx
0x18003e639  mov     rcx, rsi
0x18003e63c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003e641  jmp     loc_18003E43B
0x18003e646  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18003e64d  mov     edx, 0BEh; void *
0x18003e652  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003e658  xor     edx, edx
0x18003e65a  mov     rcx, r15
0x18003e65d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003e662  jmp     loc_18003E4E1
```
