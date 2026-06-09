# sih::mutex::CreatePrivateMutex(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>)

- ea: `0x140024764`
- end: `0x140024d10`
- name: `?CreatePrivateMutex@mutex@sih@@YAXV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@00@Z`
- size: `1452`
- prototype: `void __fastcall(_QWORD *, void *, void *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140024d18`

## callees

- `0x140003de4`
- `0x140005f98`
- `0x140006fc8`
- `0x1400073f0`
- `0x14000cb54`
- `0x14000e130`
- `0x140017934`
- `0x140018394`
- `0x14001b640`
- `0x14001b7e8`
- `0x14001c230`
- `0x14001e5ac`
- `0x140024300`
- `0x140024520`
- `0x140024764`
- `0x140024e84`
- `0x140045dc0`
- `0x140045de4`
- `0x1400481f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140024abc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140024b1b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140024abc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140024b1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024aa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024b06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024aa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024b06`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x140024a8d`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x140024a8d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x140024aec`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x140024aec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024ab3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024b12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024ab3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024b12`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140024823`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140024823`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140024840`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x140024840`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140024b43`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140024b7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140024b8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140024b43`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140024b7c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140024b8b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400247cb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1400247cb`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x140024a3d`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x140024a3d`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x1400249c6`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x1400249c6`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x1400249ea`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x140024a64`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x1400249ea`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x140024a64`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x1400249af`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x140024b9a`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x1400249af`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x140024b9a`

## string_xrefs

- `0x140024c56`: `CreateWellKnownSid`
- `0x140024c90`: `ConvertSidToStringSid`
- `0x140024cd6`: `CreatePrivateNamespace`
- `0x140024c1c`: `CreateMutex`

## pseudocode

```c
void __fastcall sih::mutex::CreatePrivateMutex(_QWORD *a1, void *a2, void *a3)
{
  void *v5; // rdi
  HLOCAL v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // r8
  wchar_t **v9; // r9
  __int64 RegKeyPath; // rax
  __int64 v11; // rcx
  int v12; // eax
  WELL_KNOWN_SID_TYPE v13; // ecx
  LPWSTR v14; // r13
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  void **v19; // rax
  const WCHAR *v20; // rdx
  __int64 v21; // rcx
  HANDLE v22; // rsi
  const WCHAR *v23; // r8
  __int64 v24; // rcx
  const WCHAR *v25; // r8
  HANDLE v26; // r12
  HANDLE v27; // r13
  DWORD LastError; // r14d
  const WCHAR *v29; // r8
  HANDLE v30; // r12
  HANDLE v31; // r13
  DWORD v32; // r14d
  int v33; // ecx
  unsigned int v34; // eax
  int v35; // ecx
  unsigned int LastErrorHr; // eax
  int v37; // ecx
  unsigned int v38; // eax
  int v39; // ecx
  unsigned int v40; // eax
  HANDLE BoundaryDescriptor; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v44[32]; // [rsp+70h] [rbp-90h] BYREF
  void *v45; // [rsp+90h] [rbp-70h] BYREF
  HLOCAL v46; // [rsp+98h] [rbp-68h]
  void *v47; // [rsp+A0h] [rbp-60h]
  void *v48; // [rsp+A8h] [rbp-58h]
  HLOCAL v49; // [rsp+B0h] [rbp-50h]
  void *v50; // [rsp+B8h] [rbp-48h]
  struct _SECURITY_ATTRIBUTES PrivateNamespaceAttributes; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v52; // [rsp+D8h] [rbp-28h]
  void *v53; // [rsp+E0h] [rbp-20h]
  DWORD cbSid[2]; // [rsp+E8h] [rbp-18h] BYREF
  LPWSTR StringSid; // [rsp+F0h] [rbp-10h] BYREF
  LPCWSTR lpAliasPrefix[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v57[2]; // [rsp+108h] [rbp+8h]
  LPCWSTR lpName[2]; // [rsp+118h] [rbp+18h] BYREF
  __int128 v59; // [rsp+128h] [rbp+28h]

  v48 = a3;
  v47 = a2;
  v52 = a1;
  v53 = a2;
  v50 = a3;
  v5 = 0;
  v45 = 0;
  v46 = 0;
  BoundaryDescriptor = 0;
  v6 = LocalAlloc(0, 0x44u);
  v49 = v6;
  LODWORD(Handle) = 1;
  cbSid[0] = 68;
  if ( !(unsigned int)AreTestKeysAllowed()
    || (RegKeyPath = GetRegKeyPath(29, v7, v8, v9),
        v12 = RegQueryDwordValueWithDefaultAndRangeCheck(v11, RegKeyPath, L"AllowAdmin", 0),
        v13 = WinBuiltinAdministratorsSid,
        !v12) )
  {
    v13 = WinLocalSystemSid;
  }
  if ( !CreateWellKnownSid(v13, 0, v6, cbSid) )
  {
    std::string::string(v44, "CreateWellKnownSid");
    LastErrorHr = GetLastErrorHr(v35);
    sih::hr_exception::hr_exception(pExceptionObject, LastErrorHr, v44);
    throw (sih::hr_exception *)pExceptionObject;
  }
  v46 = v6;
  StringSid = 0;
  if ( !ConvertSidToStringSidW(v6, &StringSid) )
  {
    std::string::string(v44, "ConvertSidToStringSid");
    v38 = GetLastErrorHr(v37);
    sih::hr_exception::hr_exception(pExceptionObject, v38, v44);
    throw (sih::hr_exception *)pExceptionObject;
  }
  v14 = StringSid;
  v15 = a1[2];
  if ( v15 == 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  std::wstring::wstring(pExceptionObject, v15, L"_", 1);
  v16 = std::wstring::append(pExceptionObject, v14);
  *(_OWORD *)lpAliasPrefix = 0;
  *(_OWORD *)v57 = 0;
  *(_OWORD *)lpAliasPrefix = *(_OWORD *)v16;
  *(_OWORD *)v57 = *(_OWORD *)(v16 + 16);
  *(_QWORD *)(v16 + 16) = 0;
  *(_QWORD *)(v16 + 24) = 7;
  *(_WORD *)v16 = 0;
  std::wstring::~wstring(pExceptionObject);
  if ( 0x7FFFFFFFFFFFFFFELL == v57[0] )
    std::_Xlen_string();
  std::wstring::wstring(v44, v57[0], (void *)L"\\", 1);
  v17 = std::wstring::append(v44);
  *(_OWORD *)lpName = 0;
  v59 = 0;
  *(_OWORD *)lpName = *(_OWORD *)v17;
  v59 = *(_OWORD *)(v17 + 16);
  *(_QWORD *)(v17 + 16) = 0;
  *(_QWORD *)(v17 + 24) = 7;
  *(_WORD *)v17 = 0;
  std::wstring::~wstring(v44);
  v18 = std::wstring::wstring(pExceptionObject, a3);
  v19 = (void **)sih::mutex::CreateUserBoundaryDescriptor(&BoundaryDescriptor, v6, v18);
  if ( &v45 != v19 )
  {
    v5 = *v19;
    v45 = *v19;
    *v19 = 0;
  }
  if ( BoundaryDescriptor )
    DeleteBoundaryDescriptor(BoundaryDescriptor);
  v20 = (const WCHAR *)lpAliasPrefix;
  if ( v57[1] > 7uLL )
    v20 = lpAliasPrefix[0];
  *(_QWORD *)cbSid = OpenPrivateNamespaceW(v5, v20);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void sih::mutex::LocalClosePrivateNamespace(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator=(
    v21,
    cbSid);
  if ( (unsigned __int64)(*(_QWORD *)cbSid - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    ClosePrivateNamespace(*(HANDLE *)cbSid, 1u);
  BoundaryDescriptor = 0;
  *(_QWORD *)cbSid = 0;
  sih::mutex::CreateSecurityDescriptor(cbSid, v6, &BoundaryDescriptor);
  *(_QWORD *)&PrivateNamespaceAttributes.nLength = 24;
  *(_QWORD *)&PrivateNamespaceAttributes.bInheritHandle = 0;
  v22 = *(HANDLE *)cbSid;
  PrivateNamespaceAttributes.lpSecurityDescriptor = *(LPVOID *)cbSid;
  if ( !sih::mutex::g_hPrivateNamespace )
  {
    v23 = (const WCHAR *)lpAliasPrefix;
    if ( v57[1] > 7uLL )
      v23 = lpAliasPrefix[0];
    Handle = CreatePrivateNamespaceW(&PrivateNamespaceAttributes, v5, v23);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void sih::mutex::LocalClosePrivateNamespace(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator=(
      v24,
      &Handle);
    if ( (char *)Handle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      ClosePrivateNamespace(Handle, 1u);
    if ( !sih::mutex::g_hPrivateNamespace )
    {
      std::string::string(v44, "CreatePrivateNamespace");
      v40 = GetLastErrorHr(v39);
      sih::hr_exception::hr_exception(pExceptionObject, v40, v44);
      throw (sih::hr_exception *)pExceptionObject;
    }
  }
  v25 = (const WCHAR *)lpName;
  if ( *((_QWORD *)&v59 + 1) > 7u )
    v25 = lpName[0];
  v26 = OpenMutexW(0x10000000u, 1, v25);
  v27 = sih::mutex::g_hMutex;
  if ( (char *)sih::mutex::g_hMutex - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    CloseHandle(v27);
    SetLastError(LastError);
  }
  sih::mutex::g_hMutex = v26;
  if ( v26 && v26 != (HANDLE)-1LL )
  {
    std::string::string(v44, &pszCabPath);
    sih::hr_exception::hr_exception(pExceptionObject, 2149863699LL, v44);
    throw (sih::hr_exception *)pExceptionObject;
  }
  v29 = (const WCHAR *)lpName;
  if ( *((_QWORD *)&v59 + 1) > 7u )
    v29 = lpName[0];
  v30 = CreateMutexW(&PrivateNamespaceAttributes, 0, v29);
  v31 = sih::mutex::g_hMutex;
  if ( (char *)sih::mutex::g_hMutex - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v32 = GetLastError();
    CloseHandle(v31);
    SetLastError(v32);
  }
  sih::mutex::g_hMutex = v30;
  if ( !v30 || v30 == (HANDLE)-1LL )
  {
    std::string::string(v44, "CreateMutex");
    v34 = GetLastErrorHr(v33);
    sih::hr_exception::hr_exception(pExceptionObject, v34, v44);
    throw (sih::hr_exception *)pExceptionObject;
  }
  if ( v22 )
    LocalFree(v22);
  if ( BoundaryDescriptor )
    operator delete(BoundaryDescriptor, (const struct std::nothrow_t *)8);
  std::wstring::~wstring(lpName);
  std::wstring::~wstring(lpAliasPrefix);
  if ( StringSid )
    LocalFree(StringSid);
  if ( v6 )
    LocalFree(v6);
  if ( v5 )
    DeleteBoundaryDescriptor(v5);
  std::wstring::~wstring(a1);
  std::wstring::~wstring(v47);
  std::wstring::~wstring(v48);
}

```

## disassembly

```asm
0x140024764  mov     [rsp-8+arg_18], rbx
0x140024769  push    rbp
0x14002476a  push    rsi
0x14002476b  push    rdi
0x14002476c  push    r12
0x14002476e  push    r13
0x140024770  push    r14
0x140024772  push    r15
0x140024774  lea     rbp, [rsp-40h]
0x140024779  sub     rsp, 140h
0x140024780  mov     rax, cs:__security_cookie
0x140024787  xor     rax, rsp
0x14002478a  mov     [rbp+70h+var_38], rax
0x14002478e  mov     r12, r8
0x140024791  mov     [rbp+70h+var_C8], r8
0x140024795  mov     r14, rdx
0x140024798  mov     [rbp+70h+var_D0], rdx
0x14002479c  mov     r15, rcx
0x14002479f  mov     [rbp+70h+var_98], rcx
0x1400247a3  mov     [rbp+70h+var_90], rdx
0x1400247a7  mov     [rbp+70h+var_B8], r8
0x1400247ab  xor     r13d, r13d
0x1400247ae  mov     dword ptr [rsp+170h+Handle], r13d
0x1400247b3  mov     edi, r13d
0x1400247b6  mov     [rbp+70h+var_E0], r13
0x1400247ba  mov     [rbp+70h+var_D8], r13
0x1400247be  mov     [rsp+170h+BoundaryDescriptor], r13
0x1400247c3  lea     esi, [r13+44h]
0x1400247c7  mov     edx, esi; uBytes
0x1400247c9  xor     ecx, ecx; uFlags
0x1400247cb  call    cs:__imp_LocalAlloc
0x1400247d1  mov     rbx, rax
0x1400247d4  mov     [rbp+70h+var_C0], rax
0x1400247d8  mov     dword ptr [rsp+170h+Handle], 1
0x1400247e0  mov     [rbp+70h+cbSid], esi
0x1400247e3  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x1400247e8  test    eax, eax
0x1400247ea  jz      short loc_140024815
0x1400247ec  lea     ecx, [rsi-27h]
0x1400247ef  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x1400247f4  mov     dword ptr [rsp+170h+Src], 0FFFFFFFFh
0x1400247fc  xor     r9d, r9d
0x1400247ff  lea     r8, aAllowadmin; "AllowAdmin"
0x140024806  mov     rdx, rax
0x140024809  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x14002480e  test    eax, eax
0x140024810  lea     ecx, [rsi-2Ah]
0x140024813  jnz     short loc_14002481A
0x140024815  mov     ecx, 16h; WellKnownSidType
0x14002481a  lea     r9, [rbp+70h+cbSid]; cbSid
0x14002481e  mov     r8, rbx; pSid
0x140024821  xor     edx, edx; DomainSid
0x140024823  call    cs:__imp_CreateWellKnownSid
0x140024829  test    eax, eax
0x14002482b  jz      loc_140024C56
0x140024831  mov     [rbp+70h+var_D8], rbx
0x140024835  mov     [rbp+70h+StringSid], r13
0x140024839  lea     rdx, [rbp+70h+StringSid]; StringSid
0x14002483d  mov     rcx, rbx; Sid
0x140024840  call    cs:__imp_ConvertSidToStringSidW
0x140024846  test    eax, eax
0x140024848  jz      loc_140024C90
0x14002484e  mov     r13, [rbp+70h+StringSid]
0x140024852  mov     rcx, [r15+10h]
0x140024856  mov     rsi, 7FFFFFFFFFFFFFFEh
0x140024860  mov     rax, rsi
0x140024863  sub     rax, rcx
0x140024866  cmp     rax, 1
0x14002486a  jb      loc_140024CCA
0x140024870  mov     r9, r15
0x140024873  cmp     qword ptr [r15+18h], 7
0x140024878  jbe     short loc_14002487D
0x14002487a  mov     r9, [r15]
0x14002487d  mov     [rsp+170h+var_140], 1; __int64
0x140024886  lea     rax, asc_1400576D8; "_"
0x14002488d  mov     [rsp+170h+Src], rax; Src
0x140024892  mov     [rsp+170h+var_150], rcx; __int64
0x140024897  lea     rcx, [rsp+170h+pExceptionObject]; void *
0x14002489c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1400248a1  nop
0x1400248a2  mov     rdx, r13; void *
0x1400248a5  lea     rcx, [rsp+170h+pExceptionObject]; Src
0x1400248aa  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x1400248af  xorps   xmm0, xmm0
0x1400248b2  movups  xmmword ptr [rbp+70h+lpAliasPrefix], xmm0
0x1400248b6  xorps   xmm1, xmm1
0x1400248b9  movdqu  xmmword ptr [rbp+70h+var_68], xmm1
0x1400248be  movups  xmm0, xmmword ptr [rax]
0x1400248c1  movups  xmmword ptr [rbp+70h+lpAliasPrefix], xmm0
0x1400248c5  movups  xmm1, xmmword ptr [rax+10h]
0x1400248c9  movups  xmmword ptr [rbp+70h+var_68], xmm1
0x1400248cd  xor     ecx, ecx
0x1400248cf  mov     [rax+10h], rcx
0x1400248d3  mov     qword ptr [rax+18h], 7
0x1400248db  mov     [rax], cx
0x1400248de  lea     rcx, [rsp+170h+pExceptionObject]; void *
0x1400248e3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400248e8  mov     rax, [rbp+70h+var_68]
0x1400248ec  sub     rsi, rax
0x1400248ef  mov     r13d, 1
0x1400248f5  cmp     rsi, r13
0x1400248f8  jb      loc_140024CD0
0x1400248fe  lea     r9, [rbp+70h+lpAliasPrefix]
0x140024902  cmp     [rbp+70h+var_68+8], 7
0x140024907  cmova   r9, [rbp+70h+lpAliasPrefix]
0x14002490c  mov     [rsp+170h+var_140], r13; __int64
0x140024911  lea     rcx, SubBlock; "\\"
0x140024918  mov     [rsp+170h+Src], rcx; Src
0x14002491d  mov     [rsp+170h+var_150], rax; __int64
0x140024922  lea     rcx, [rsp+170h+var_100]; void *
0x140024927  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x14002492c  nop
0x14002492d  mov     rdx, r14
0x140024930  lea     rcx, [rsp+170h+var_100]; Src
0x140024935  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x14002493a  xorps   xmm0, xmm0
0x14002493d  movups  xmmword ptr [rbp+70h+lpName], xmm0
0x140024941  xorps   xmm1, xmm1
0x140024944  movdqu  [rbp+70h+var_48], xmm1
0x140024949  movups  xmm0, xmmword ptr [rax]
0x14002494c  movups  xmmword ptr [rbp+70h+lpName], xmm0
0x140024950  movups  xmm1, xmmword ptr [rax+10h]
0x140024954  movups  [rbp+70h+var_48], xmm1
0x140024958  xor     r14d, r14d
0x14002495b  mov     [rax+10h], r14
0x14002495f  mov     qword ptr [rax+18h], 7
0x140024967  mov     [rax], r14w
0x14002496b  lea     rcx, [rsp+170h+var_100]; void *
0x140024970  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140024975  mov     rdx, r12
0x140024978  lea     rcx, [rsp+170h+pExceptionObject]
0x14002497d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140024982  mov     r8, rax
0x140024985  mov     rdx, rbx
0x140024988  lea     rcx, [rsp+170h+BoundaryDescriptor]
0x14002498d  call    ?CreateUserBoundaryDescriptor@mutex@sih@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?DeleteBoundaryDescriptor@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@PEAXV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; sih::mutex::CreateUserBoundaryDescriptor(void *,std::wstring)
0x140024992  lea     rcx, [rbp+70h+var_E0]
0x140024996  cmp     rcx, rax
0x140024999  jz      short loc_1400249A5
0x14002499b  mov     rdi, [rax]
0x14002499e  mov     [rbp+70h+var_E0], rdi
0x1400249a2  mov     [rax], r14
0x1400249a5  mov     rcx, [rsp+170h+BoundaryDescriptor]; BoundaryDescriptor
0x1400249aa  test    rcx, rcx
0x1400249ad  jz      short loc_1400249B5
0x1400249af  call    cs:__imp_DeleteBoundaryDescriptor
0x1400249b5  lea     rdx, [rbp+70h+lpAliasPrefix]
0x1400249b9  cmp     [rbp+70h+var_68+8], 7
0x1400249be  cmova   rdx, [rbp+70h+lpAliasPrefix]; lpAliasPrefix
0x1400249c3  mov     rcx, rdi; lpBoundaryDescriptor
0x1400249c6  call    cs:__imp_OpenPrivateNamespaceW
0x1400249cc  mov     qword ptr [rbp+70h+cbSid], rax
0x1400249d0  lea     rdx, [rbp+70h+cbSid]
0x1400249d4  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?LocalClosePrivateNamespace@mutex@sih@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&sih::mutex::LocalClosePrivateNamespace(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&sih::mutex::LocalClosePrivateNamespace(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x1400249d9  mov     rcx, qword ptr [rbp+70h+cbSid]; Handle
0x1400249dd  lea     rax, [rcx-1]
0x1400249e1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400249e5  ja      short loc_1400249F0
0x1400249e7  mov     edx, r13d; Flags
0x1400249ea  call    cs:__imp_ClosePrivateNamespace
0x1400249f0  mov     [rsp+170h+BoundaryDescriptor], r14
0x1400249f5  mov     qword ptr [rbp+70h+cbSid], r14
0x1400249f9  lea     r8, [rsp+170h+BoundaryDescriptor]
0x1400249fe  mov     rdx, rbx
0x140024a01  lea     rcx, [rbp+70h+cbSid]
0x140024a05  call    ?CreateSecurityDescriptor@mutex@sih@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@PEAXAEAV?$unique_ptr@U_ACL@@U?$default_delete@U_ACL@@@std@@@std@@@Z; sih::mutex::CreateSecurityDescriptor(void *,std::unique_ptr<_ACL> &)
0x140024a0a  nop
0x140024a0b  mov     qword ptr [rbp+70h+PrivateNamespaceAttributes.nLength], 18h
0x140024a13  mov     qword ptr [rbp+70h+PrivateNamespaceAttributes.bInheritHandle], r14
0x140024a17  mov     rsi, qword ptr [rbp+70h+cbSid]
0x140024a1b  mov     [rbp+70h+PrivateNamespaceAttributes.lpSecurityDescriptor], rsi
0x140024a1f  cmp     cs:?g_hPrivateNamespace@mutex@sih@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?LocalClosePrivateNamespace@mutex@sih@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@A, r14; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&sih::mutex::LocalClosePrivateNamespace(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> sih::mutex::g_hPrivateNamespace
0x140024a26  jnz     short loc_140024A77
0x140024a28  lea     r8, [rbp+70h+lpAliasPrefix]
0x140024a2c  cmp     [rbp+70h+var_68+8], 7
0x140024a31  cmova   r8, [rbp+70h+lpAliasPrefix]; lpAliasPrefix
0x140024a36  mov     rdx, rdi; lpBoundaryDescriptor
0x140024a39  lea     rcx, [rbp+70h+PrivateNamespaceAttributes]; lpPrivateNamespaceAttributes
0x140024a3d  call    cs:__imp_CreatePrivateNamespaceW
0x140024a43  mov     [rsp+170h+Handle], rax
0x140024a48  lea     rdx, [rsp+170h+Handle]
0x140024a4d  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?LocalClosePrivateNamespace@mutex@sih@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&sih::mutex::LocalClosePrivateNamespace(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&sih::mutex::LocalClosePrivateNamespace(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x140024a52  mov     rcx, [rsp+170h+Handle]; Handle
0x140024a57  lea     rax, [rcx-1]
0x140024a5b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140024a5f  ja      short loc_140024A6A
0x140024a61  mov     edx, r13d; Flags
0x140024a64  call    cs:__imp_ClosePrivateNamespace
0x140024a6a  cmp     cs:?g_hPrivateNamespace@mutex@sih@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?LocalClosePrivateNamespace@mutex@sih@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@A, r14; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&sih::mutex::LocalClosePrivateNamespace(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> sih::mutex::g_hPrivateNamespace
0x140024a71  jz      loc_140024CD6
0x140024a77  lea     r8, [rbp+70h+lpName]
0x140024a7b  cmp     qword ptr [rbp+70h+var_48+8], 7
0x140024a80  cmova   r8, [rbp+70h+lpName]; lpName
0x140024a85  mov     edx, r13d; bInheritHandle
0x140024a88  mov     ecx, 10000000h; dwDesiredAccess
0x140024a8d  call    cs:__imp_OpenMutexW
0x140024a93  mov     r12, rax
0x140024a96  mov     r13, cs:?g_hMutex@mutex@sih@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> sih::mutex::g_hMutex
0x140024a9d  lea     rdx, [r13-1]
0x140024aa1  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140024aa5  ja      short loc_140024AC2
0x140024aa7  call    cs:__imp_GetLastError
0x140024aad  mov     r14d, eax
0x140024ab0  mov     rcx, r13; hObject
0x140024ab3  call    cs:__imp_CloseHandle
0x140024ab9  mov     ecx, r14d; dwErrCode
0x140024abc  call    cs:__imp_SetLastError
0x140024ac2  mov     cs:?g_hMutex@mutex@sih@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A, r12; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> sih::mutex::g_hMutex
0x140024ac9  test    r12, r12
0x140024acc  jz      short loc_140024AD8
0x140024ace  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x140024ad2  jnz     loc_140024BE4
0x140024ad8  lea     r8, [rbp+70h+lpName]
0x140024adc  cmp     qword ptr [rbp+70h+var_48+8], 7
0x140024ae1  cmova   r8, [rbp+70h+lpName]; lpName
0x140024ae6  xor     edx, edx; bInitialOwner
0x140024ae8  lea     rcx, [rbp+70h+PrivateNamespaceAttributes]; lpMutexAttributes
0x140024aec  call    cs:__imp_CreateMutexW
0x140024af2  mov     r12, rax
0x140024af5  mov     r13, cs:?g_hMutex@mutex@sih@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> sih::mutex::g_hMutex
0x140024afc  lea     rdx, [r13-1]
0x140024b00  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x140024b04  ja      short loc_140024B21
0x140024b06  call    cs:__imp_GetLastError
0x140024b0c  mov     r14d, eax
0x140024b0f  mov     rcx, r13; hObject
0x140024b12  call    cs:__imp_CloseHandle
0x140024b18  mov     ecx, r14d; dwErrCode
0x140024b1b  call    cs:__imp_SetLastError
0x140024b21  mov     cs:?g_hMutex@mutex@sih@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A, r12; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> sih::mutex::g_hMutex
0x140024b28  test    r12, r12
0x140024b2b  jz      loc_140024C1C
0x140024b31  cmp     r12, 0FFFFFFFFFFFFFFFFh
0x140024b35  jz      loc_140024C1C
0x140024b3b  test    rsi, rsi
0x140024b3e  jz      short loc_140024B4A
0x140024b40  mov     rcx, rsi; hMem
0x140024b43  call    cs:__imp_LocalFree
0x140024b49  nop
0x140024b4a  mov     rcx, [rsp+170h+BoundaryDescriptor]; void *
0x140024b4f  test    rcx, rcx
0x140024b52  jz      short loc_140024B5F
0x140024b54  mov     edx, 8; struct std::nothrow_t *
0x140024b59  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140024b5e  nop
0x140024b5f  lea     rcx, [rbp+70h+lpName]; void *
0x140024b63  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140024b68  nop
0x140024b69  lea     rcx, [rbp+70h+lpAliasPrefix]; void *
0x140024b6d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140024b72  nop
0x140024b73  mov     rcx, [rbp+70h+StringSid]; hMem
0x140024b77  test    rcx, rcx
0x140024b7a  jz      short loc_140024B83
0x140024b7c  call    cs:__imp_LocalFree
0x140024b82  nop
0x140024b83  test    rbx, rbx
0x140024b86  jz      short loc_140024B92
0x140024b88  mov     rcx, rbx; hMem
0x140024b8b  call    cs:__imp_LocalFree
0x140024b91  nop
0x140024b92  test    rdi, rdi
0x140024b95  jz      short loc_140024BA1
0x140024b97  mov     rcx, rdi; BoundaryDescriptor
0x140024b9a  call    cs:__imp_DeleteBoundaryDescriptor
0x140024ba0  nop
0x140024ba1  mov     rcx, r15; void *
0x140024ba4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140024ba9  nop
0x140024baa  mov     rcx, [rbp+70h+var_D0]; void *
0x140024bae  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140024bb3  nop
0x140024bb4  mov     rcx, [rbp+70h+var_C8]; void *
0x140024bb8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140024bbd  mov     rcx, [rbp+70h+var_38]
0x140024bc1  xor     rcx, rsp; StackCookie
0x140024bc4  call    __security_check_cookie
0x140024bc9  mov     rbx, [rsp+170h+arg_18]
0x140024bd1  add     rsp, 140h
0x140024bd8  pop     r15
0x140024bda  pop     r14
0x140024bdc  pop     r13
0x140024bde  pop     r12
0x140024be0  pop     rdi
0x140024be1  pop     rsi
0x140024be2  pop     rbp
0x140024be3  retn
0x140024be4  lea     rdx, pszCabPath
0x140024beb  lea     rcx, [rsp+170h+var_100]
0x140024bf0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140024bf5  nop
0x140024bf6  lea     r8, [rsp+170h+var_100]
0x140024bfb  mov     edx, 80245113h
0x140024c00  lea     rcx, [rsp+170h+pExceptionObject]
0x140024c05  call    ??0hr_exception@sih@@QEAA@JAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; sih::hr_exception::hr_exception(long,std::string const &)
0x140024c0a  lea     rdx, _TI3?AVhr_exception@sih@@; pThrowInfo
0x140024c11  lea     rcx, [rsp+170h+pExceptionObject]; pExceptionObject
0x140024c16  call    _CxxThrowException
0x140024c1c  lea     rdx, aCreatemutex; "CreateMutex"
0x140024c23  lea     rcx, [rsp+170h+var_100]
  ... truncated ...
```
