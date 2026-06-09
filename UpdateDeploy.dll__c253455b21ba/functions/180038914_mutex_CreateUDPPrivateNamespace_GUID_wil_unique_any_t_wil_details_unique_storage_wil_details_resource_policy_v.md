# mutex::CreateUDPPrivateNamespace(_GUID &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&mutex::LocalClosePrivateNamespace(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)

- ea: `0x180038914`
- end: `0x180038d18`
- name: `?CreateUDPPrivateNamespace@mutex@@YAJAEAU_GUID@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?LocalClosePrivateNamespace@mutex@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `1028`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180032d44`

## callees

- `0x180002214`
- `0x180003180`
- `0x18000c640`
- `0x18001c3cc`
- `0x18001c75c`
- `0x1800384b4`
- `0x180038580`
- `0x180038750`
- `0x180038914`
- `0x18003916c`
- `0x18003923c`
- `0x180039340`
- `0x180061960`
- `0x180061d54`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038b51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038beb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038b51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038beb`
- `RPCRT4!UuidToStringW` at `0x18003895e`
- `RPCRT4!UuidToStringW` at `0x18003895e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038b08`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038b08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038c5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038c6e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038c5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038c6e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800389c6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800389c6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038c93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038cb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038cd8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038c93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038cb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038cd8`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x180038b4b`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x180038be0`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x180038c35`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x180038b4b`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x180038be0`
- `api-ms-win-core-namespace-l1-1-0!ClosePrivateNamespace` at `0x180038c35`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x180038bb4`
- `api-ms-win-core-namespace-l1-1-0!CreatePrivateNamespaceW` at `0x180038bb4`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x180038b1f`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x180038c09`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x180038b1f`
- `api-ms-win-core-namespace-l1-1-0!OpenPrivateNamespaceW` at `0x180038c09`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180038ce7`
- `api-ms-win-core-namespace-l1-1-0!DeleteBoundaryDescriptor` at `0x180038ce7`

## string_xrefs

- `0x180038a60`: `UDPBoundaryDescriptor`
- `0x1800389a5`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\mutex.cpp`
- `0x1800389d4`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\mutex.cpp`
- `0x180038a96`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\mutex.cpp`
- `0x180038adb`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\mutex.cpp`
- `0x180038b89`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\mutex.cpp`
- `0x180038c44`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\mutex.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall mutex::CreateUDPPrivateNamespace(const UUID *a1, _QWORD *a2)
{
  PSID v3; // rbx
  RPC_STATUS v4; // eax
  signed int BuiltinAdminSid; // r14d
  __int64 v6; // rdx
  const char *v7; // r9
  __int64 v8; // r8
  LPWSTR v9; // rdi
  __int64 v10; // rax
  int v11; // eax
  void *v12; // rdi
  int v13; // eax
  void *v14; // rsi
  const WCHAR *v15; // rdx
  signed int LastError; // eax
  const WCHAR *v17; // r8
  const char *v18; // r9
  const WCHAR *v19; // rdx
  LPVOID lpBoundaryDescriptor; // [rsp+20h] [rbp-99h] BYREF
  PSID Sid; // [rsp+28h] [rbp-91h] BYREF
  __int128 v23; // [rsp+30h] [rbp-89h] BYREF
  __int64 v24; // [rsp+40h] [rbp-79h]
  __int64 v25; // [rsp+48h] [rbp-71h]
  _BYTE v26[32]; // [rsp+58h] [rbp-61h] BYREF
  struct _SECURITY_ATTRIBUTES PrivateNamespaceAttributes; // [rsp+78h] [rbp-41h] BYREF
  RPC_WSTR StringUuid; // [rsp+90h] [rbp-29h] BYREF
  LPWSTR StringSid; // [rsp+98h] [rbp-21h] BYREF
  LPCWSTR lpAliasPrefix[3]; // [rsp+A0h] [rbp-19h] BYREF
  unsigned __int64 v31; // [rsp+B8h] [rbp-1h]
  _OWORD Src[2]; // [rsp+C0h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  lpBoundaryDescriptor = 0;
  v3 = 0;
  Sid = 0;
  StringUuid = 0;
  v4 = UuidToStringW(a1, &StringUuid);
  BuiltinAdminSid = v4;
  if ( v4 >= 1 )
    BuiltinAdminSid = (unsigned __int16)v4 | 0x80010000;
  if ( BuiltinAdminSid < 0 )
  {
    v6 = 156;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\mutex.cpp",
      (const char *)(unsigned int)BuiltinAdminSid,
      (int)lpBoundaryDescriptor);
    goto LABEL_47;
  }
  BuiltinAdminSid = mutex::GetBuiltinAdminSid(&Sid);
  if ( BuiltinAdminSid < 0 )
  {
    v6 = 159;
    v3 = Sid;
    goto LABEL_7;
  }
  StringSid = 0;
  v3 = Sid;
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
  {
    BuiltinAdminSid = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0xA2,
                        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\mutex.cpp",
                        v7);
    goto LABEL_45;
  }
  memset(Src, 0, sizeof(Src));
  v8 = -1;
  do
    ++v8;
  while ( StringUuid[v8] );
  std::wstring::_Construct<1,wchar_t const *>(Src, StringUuid);
  v9 = StringSid;
  v10 = std::operator+<wchar_t>(v26, Src, L"_");
  std::operator+<wchar_t>(lpAliasPrefix, v10, v9);
  std::wstring::~wstring(v26);
  v23 = 0;
  v24 = 0;
  v25 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v23, L"UDPBoundaryDescriptor");
  v11 = mutex::CreateUserBoundaryDescriptor(v3, &v23);
  BuiltinAdminSid = v11;
  v12 = lpBoundaryDescriptor;
  if ( v11 >= 0 )
  {
    lpBoundaryDescriptor = 0;
    Sid = 0;
    v13 = mutex::CreateSecurityDescriptor(v3, (PACL *)&Sid, &lpBoundaryDescriptor);
    BuiltinAdminSid = v13;
    v14 = lpBoundaryDescriptor;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAE,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\mutex.cpp",
        (const char *)(unsigned int)v13,
        (int)lpBoundaryDescriptor);
LABEL_40:
      if ( Sid )
        operator delete(Sid, (const struct std::nothrow_t *)8);
      if ( v14 )
        LocalFree(v14);
      goto LABEL_44;
    }
    *(_QWORD *)&PrivateNamespaceAttributes.nLength = 24;
    *(_QWORD *)&PrivateNamespaceAttributes.bInheritHandle = 0;
    PrivateNamespaceAttributes.lpSecurityDescriptor = lpBoundaryDescriptor;
    EnterCriticalSection(&stru_1800A16F8);
    v15 = (const WCHAR *)lpAliasPrefix;
    if ( v31 > 7 )
      v15 = lpAliasPrefix[0];
    lpBoundaryDescriptor = OpenPrivateNamespaceW(v12, v15);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void mutex::LocalClosePrivateNamespace(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator=(
      a2,
      &lpBoundaryDescriptor);
    if ( (char *)lpBoundaryDescriptor - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      ClosePrivateNamespace(lpBoundaryDescriptor, 1u);
    LastError = GetLastError();
    if ( !*a2 )
    {
      if ( (unsigned int)(LastError - 2) > 1 )
      {
        BuiltinAdminSid = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          BuiltinAdminSid = LastError;
        if ( BuiltinAdminSid < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC8,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\mutex.cpp",
            (const char *)(unsigned int)BuiltinAdminSid,
            (int)lpBoundaryDescriptor);
        goto LABEL_38;
      }
      v17 = (const WCHAR *)lpAliasPrefix;
      if ( v31 > 7 )
        v17 = lpAliasPrefix[0];
      lpBoundaryDescriptor = CreatePrivateNamespaceW(&PrivateNamespaceAttributes, v12, v17);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void mutex::LocalClosePrivateNamespace(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator=(
        a2,
        &lpBoundaryDescriptor);
      if ( (char *)lpBoundaryDescriptor - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        ClosePrivateNamespace(lpBoundaryDescriptor, 1u);
      if ( !*a2 )
      {
        if ( GetLastError() == 183 )
        {
          v19 = (const WCHAR *)lpAliasPrefix;
          if ( v31 > 7 )
            v19 = lpAliasPrefix[0];
          lpBoundaryDescriptor = OpenPrivateNamespaceW(v12, v19);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void mutex::LocalClosePrivateNamespace(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator=(
            a2,
            &lpBoundaryDescriptor);
          if ( (char *)lpBoundaryDescriptor - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
            ClosePrivateNamespace(lpBoundaryDescriptor, 1u);
        }
        if ( !*a2 )
        {
          BuiltinAdminSid = wil::details::in1diag3::Return_GetLastError(
                              retaddr,
                              (void *)0xDA,
                              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\mutex.cpp",
                              v18);
LABEL_38:
          LeaveCriticalSection(&stru_1800A16F8);
          goto LABEL_40;
        }
      }
    }
    LeaveCriticalSection(&stru_1800A16F8);
    BuiltinAdminSid = 0;
    goto LABEL_40;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA9,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\mutex.cpp",
    (const char *)(unsigned int)v11,
    (int)lpBoundaryDescriptor);
LABEL_44:
  std::wstring::~wstring(lpAliasPrefix);
  std::wstring::~wstring(Src);
LABEL_45:
  if ( StringSid )
    LocalFree(StringSid);
LABEL_47:
  if ( StringUuid )
  {
    XPtrRpcStringFree(StringUuid);
    StringUuid = 0;
  }
  if ( v3 )
    LocalFree(v3);
  return (unsigned int)BuiltinAdminSid;
}

```

## disassembly

```asm
0x180038914  mov     [rsp-8+arg_10], rbx
0x180038919  mov     [rsp-8+arg_18], rsi
0x18003891e  push    rbp
0x18003891f  push    rdi
0x180038920  push    r12
0x180038922  push    r14
0x180038924  push    r15
0x180038926  lea     rbp, [rsp-37h]
0x18003892b  sub     rsp, 0F0h
0x180038932  mov     rax, cs:__security_cookie
0x180038939  xor     rax, rsp
0x18003893c  mov     [rbp+57h+var_30], rax
0x180038940  mov     r15, rdx
0x180038943  xor     r12d, r12d
0x180038946  mov     edi, r12d
0x180038949  mov     [rsp+110h+lpBoundaryDescriptor], r12; int
0x18003894e  mov     ebx, r12d
0x180038951  mov     [rsp+110h+Sid], rbx
0x180038956  mov     [rbp+57h+StringUuid], r12
0x18003895a  lea     rdx, [rbp+57h+StringUuid]; StringUuid
0x18003895e  call    cs:__imp_UuidToStringW
0x180038964  mov     r14d, eax
0x180038967  cmp     eax, 1
0x18003896a  jl      short loc_180038977
0x18003896c  movzx   r14d, ax
0x180038970  or      r14d, 80010000h
0x180038977  test    r14d, r14d
0x18003897a  jns     short loc_180038983
0x18003897c  mov     edx, 9Ch
0x180038981  jmp     short loc_18003899E
0x180038983  lea     rcx, [rsp+110h+Sid]
0x180038988  call    ?GetBuiltinAdminSid@mutex@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; mutex::GetBuiltinAdminSid(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x18003898d  mov     r14d, eax
0x180038990  test    eax, eax
0x180038992  jns     short loc_1800389B6
0x180038994  mov     edx, 9Fh; void *
0x180038999  mov     rbx, [rsp+110h+Sid]
0x18003899e  mov     rcx, [rbp+5Fh]; this
0x1800389a2  mov     r9d, r14d; char *
0x1800389a5  lea     r8, aCW1SSrcClientU_12; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800389ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800389b1  jmp     loc_180038CBE
0x1800389b6  mov     [rbp+57h+StringSid], r12
0x1800389ba  lea     rdx, [rbp+57h+StringSid]; StringSid
0x1800389be  mov     rbx, [rsp+110h+Sid]
0x1800389c3  mov     rcx, rbx; Sid
0x1800389c6  call    cs:__imp_ConvertSidToStringSidW
0x1800389cc  test    eax, eax
0x1800389ce  jnz     short loc_1800389ED
0x1800389d0  mov     rcx, [rbp+5Fh]; this
0x1800389d4  lea     r8, aCW1SSrcClientU_12; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800389db  mov     edx, 0A2h; void *
0x1800389e0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800389e5  mov     r14d, eax
0x1800389e8  jmp     loc_180038CAE
0x1800389ed  xorps   xmm0, xmm0
0x1800389f0  movups  [rbp+57h+Src], xmm0
0x1800389f4  xorps   xmm1, xmm1
0x1800389f7  movdqu  [rbp+57h+var_40], xmm1
0x1800389fc  mov     rdx, [rbp+57h+StringUuid]
0x180038a00  or      r8, 0FFFFFFFFFFFFFFFFh
0x180038a04  inc     r8
0x180038a07  cmp     [rdx+r8*2], r12w
0x180038a0c  jnz     short loc_180038A04
0x180038a0e  lea     rcx, [rbp+57h+Src]
0x180038a12  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180038a17  nop
0x180038a18  mov     rdi, [rbp+57h+StringSid]
0x180038a1c  lea     r8, asc_18007B970; "_"
0x180038a23  lea     rdx, [rbp+57h+Src]; Src
0x180038a27  lea     rcx, [rbp+57h+var_B8]; void *
0x180038a2b  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring const &,wchar_t const * const)
0x180038a30  nop
0x180038a31  mov     r8, rdi
0x180038a34  mov     rdx, rax
0x180038a37  lea     rcx, [rbp+57h+lpAliasPrefix]
0x180038a3b  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180038a40  nop
0x180038a41  lea     rcx, [rbp+57h+var_B8]
0x180038a45  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038a4a  xorps   xmm0, xmm0
0x180038a4d  movups  [rsp+110h+var_E0], xmm0
0x180038a52  mov     [rbp+57h+var_D0], r12
0x180038a56  mov     [rbp+57h+var_C8], r12
0x180038a5a  mov     r8d, 15h
0x180038a60  lea     rdx, aUdpboundarydes; "UDPBoundaryDescriptor"
0x180038a67  lea     rcx, [rsp+110h+var_E0]
0x180038a6c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180038a71  lea     r8, [rsp+110h+lpBoundaryDescriptor]
0x180038a76  lea     rdx, [rsp+110h+var_E0]; Src
0x180038a7b  mov     rcx, rbx; RequiredSid
0x180038a7e  call    ?CreateUserBoundaryDescriptor@mutex@@YAJPEAXV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?DeleteBoundaryDescriptor@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; mutex::CreateUserBoundaryDescriptor(void *,std::wstring,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&DeleteBoundaryDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x180038a83  mov     r14d, eax
0x180038a86  mov     rdi, [rsp+110h+lpBoundaryDescriptor]
0x180038a8b  test    eax, eax
0x180038a8d  jns     short loc_180038AAC
0x180038a8f  mov     rcx, [rbp+5Fh]; this
0x180038a93  mov     r9d, eax; char *
0x180038a96  lea     r8, aCW1SSrcClientU_12; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180038a9d  mov     edx, 0A9h; void *
0x180038aa2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038aa7  jmp     loc_180038C9A
0x180038aac  mov     [rsp+110h+lpBoundaryDescriptor], r12; int
0x180038ab1  mov     [rsp+110h+Sid], r12
0x180038ab6  lea     r8, [rsp+110h+lpBoundaryDescriptor]
0x180038abb  lea     rdx, [rsp+110h+Sid]
0x180038ac0  mov     rcx, rbx; pSid
0x180038ac3  call    ?CreateSecurityDescriptor@mutex@@YAJPEAXAEAV?$unique_ptr@U_ACL@@U?$default_delete@U_ACL@@@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; mutex::CreateSecurityDescriptor(void *,std::unique_ptr<_ACL> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x180038ac8  mov     r14d, eax
0x180038acb  mov     rsi, [rsp+110h+lpBoundaryDescriptor]
0x180038ad0  test    eax, eax
0x180038ad2  jns     short loc_180038AF1
0x180038ad4  mov     rcx, [rbp+5Fh]; this
0x180038ad8  mov     r9d, eax; char *
0x180038adb  lea     r8, aCW1SSrcClientU_12; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180038ae2  mov     edx, 0AEh; void *
0x180038ae7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038aec  jmp     loc_180038C77
0x180038af1  mov     qword ptr [rbp+57h+PrivateNamespaceAttributes.nLength], 18h
0x180038af9  mov     qword ptr [rbp+57h+PrivateNamespaceAttributes.bInheritHandle], r12
0x180038afd  mov     [rbp+57h+PrivateNamespaceAttributes.lpSecurityDescriptor], rsi
0x180038b01  lea     rcx, stru_1800A16F8; lpCriticalSection
0x180038b08  call    cs:__imp_EnterCriticalSection
0x180038b0e  lea     rdx, [rbp+57h+lpAliasPrefix]
0x180038b12  cmp     [rbp+57h+var_58], 7
0x180038b17  cmova   rdx, [rbp+57h+lpAliasPrefix]; lpAliasPrefix
0x180038b1c  mov     rcx, rdi; lpBoundaryDescriptor
0x180038b1f  call    cs:__imp_OpenPrivateNamespaceW
0x180038b25  mov     [rsp+110h+lpBoundaryDescriptor], rax; int
0x180038b2a  lea     rdx, [rsp+110h+lpBoundaryDescriptor]
0x180038b2f  mov     rcx, r15
0x180038b32  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?LocalClosePrivateNamespace@mutex@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&mutex::LocalClosePrivateNamespace(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&mutex::LocalClosePrivateNamespace(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x180038b37  mov     rcx, [rsp+110h+lpBoundaryDescriptor]; Handle
0x180038b3c  lea     rax, [rcx-1]
0x180038b40  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180038b44  ja      short loc_180038B51
0x180038b46  mov     edx, 1; Flags
0x180038b4b  call    cs:__imp_ClosePrivateNamespace
0x180038b51  call    cs:__imp_GetLastError
0x180038b57  cmp     [r15], r12
0x180038b5a  jnz     loc_180038C67
0x180038b60  lea     ecx, [rax-2]
0x180038b63  cmp     ecx, 1
0x180038b66  jbe     short loc_180038B9F
0x180038b68  movzx   r14d, ax
0x180038b6c  or      r14d, 80070000h
0x180038b73  test    eax, eax
0x180038b75  cmovle  r14d, eax
0x180038b79  test    r14d, r14d
0x180038b7c  jns     loc_180038C58
0x180038b82  mov     rcx, [rbp+5Fh]; this
0x180038b86  mov     r9d, r14d; char *
0x180038b89  lea     r8, aCW1SSrcClientU_12; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180038b90  mov     edx, 0C8h; void *
0x180038b95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038b9a  jmp     loc_180038C58
0x180038b9f  lea     r8, [rbp+57h+lpAliasPrefix]
0x180038ba3  cmp     [rbp+57h+var_58], 7
0x180038ba8  cmova   r8, [rbp+57h+lpAliasPrefix]; lpAliasPrefix
0x180038bad  mov     rdx, rdi; lpBoundaryDescriptor
0x180038bb0  lea     rcx, [rbp+57h+PrivateNamespaceAttributes]; lpPrivateNamespaceAttributes
0x180038bb4  call    cs:__imp_CreatePrivateNamespaceW
0x180038bba  mov     [rsp+110h+lpBoundaryDescriptor], rax
0x180038bbf  lea     rdx, [rsp+110h+lpBoundaryDescriptor]
0x180038bc4  mov     rcx, r15
0x180038bc7  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?LocalClosePrivateNamespace@mutex@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&mutex::LocalClosePrivateNamespace(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&mutex::LocalClosePrivateNamespace(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x180038bcc  mov     rcx, [rsp+110h+lpBoundaryDescriptor]; Handle
0x180038bd1  lea     rax, [rcx-1]
0x180038bd5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180038bd9  ja      short loc_180038BE6
0x180038bdb  mov     edx, 1; Flags
0x180038be0  call    cs:__imp_ClosePrivateNamespace
0x180038be6  cmp     [r15], r12
0x180038be9  jnz     short loc_180038C67
0x180038beb  call    cs:__imp_GetLastError
0x180038bf1  cmp     eax, 0B7h
0x180038bf6  jnz     short loc_180038C3B
0x180038bf8  lea     rdx, [rbp+57h+lpAliasPrefix]
0x180038bfc  cmp     [rbp+57h+var_58], 7
0x180038c01  cmova   rdx, [rbp+57h+lpAliasPrefix]; lpAliasPrefix
0x180038c06  mov     rcx, rdi; lpBoundaryDescriptor
0x180038c09  call    cs:__imp_OpenPrivateNamespaceW
0x180038c0f  mov     [rsp+110h+lpBoundaryDescriptor], rax
0x180038c14  lea     rdx, [rsp+110h+lpBoundaryDescriptor]
0x180038c19  mov     rcx, r15
0x180038c1c  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?LocalClosePrivateNamespace@mutex@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&mutex::LocalClosePrivateNamespace(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&mutex::LocalClosePrivateNamespace(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &&)
0x180038c21  mov     rcx, [rsp+110h+lpBoundaryDescriptor]; Handle
0x180038c26  lea     rax, [rcx-1]
0x180038c2a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180038c2e  ja      short loc_180038C3B
0x180038c30  mov     edx, 1; Flags
0x180038c35  call    cs:__imp_ClosePrivateNamespace
0x180038c3b  cmp     [r15], r12
0x180038c3e  jnz     short loc_180038C67
0x180038c40  mov     rcx, [rbp+5Fh]; this
0x180038c44  lea     r8, aCW1SSrcClientU_12; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180038c4b  mov     edx, 0DAh; void *
0x180038c50  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180038c55  mov     r14d, eax
0x180038c58  lea     rcx, stru_1800A16F8; lpCriticalSection
0x180038c5f  call    cs:__imp_LeaveCriticalSection
0x180038c65  jmp     short loc_180038C77
0x180038c67  lea     rcx, stru_1800A16F8; lpCriticalSection
0x180038c6e  call    cs:__imp_LeaveCriticalSection
0x180038c74  mov     r14d, r12d
0x180038c77  mov     rcx, [rsp+110h+Sid]; void *
0x180038c7c  test    rcx, rcx
0x180038c7f  jz      short loc_180038C8B
0x180038c81  mov     edx, 8; struct std::nothrow_t *
0x180038c86  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180038c8b  test    rsi, rsi
0x180038c8e  jz      short loc_180038C9A
0x180038c90  mov     rcx, rsi; hMem
0x180038c93  call    cs:__imp_LocalFree
0x180038c99  nop
0x180038c9a  lea     rcx, [rbp+57h+lpAliasPrefix]
0x180038c9e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038ca3  nop
0x180038ca4  lea     rcx, [rbp+57h+Src]
0x180038ca8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038cad  nop
0x180038cae  mov     rcx, [rbp+57h+StringSid]; hMem
0x180038cb2  test    rcx, rcx
0x180038cb5  jz      short loc_180038CBE
0x180038cb7  call    cs:__imp_LocalFree
0x180038cbd  nop
0x180038cbe  mov     rcx, [rbp+57h+StringUuid]; void *
0x180038cc2  test    rcx, rcx
0x180038cc5  jz      short loc_180038CD0
0x180038cc7  call    ?XPtrRpcStringFree@@YAXPEAX@Z; XPtrRpcStringFree(void *)
0x180038ccc  mov     [rbp+57h+StringUuid], r12
0x180038cd0  test    rbx, rbx
0x180038cd3  jz      short loc_180038CDF
0x180038cd5  mov     rcx, rbx; hMem
0x180038cd8  call    cs:__imp_LocalFree
0x180038cde  nop
0x180038cdf  test    rdi, rdi
0x180038ce2  jz      short loc_180038CED
0x180038ce4  mov     rcx, rdi; BoundaryDescriptor
0x180038ce7  call    cs:__imp_DeleteBoundaryDescriptor
0x180038ced  mov     eax, r14d
0x180038cf0  mov     rcx, [rbp+57h+var_30]
0x180038cf4  xor     rcx, rsp; StackCookie
0x180038cf7  call    __security_check_cookie
0x180038cfc  lea     r11, [rsp+110h+var_20]
0x180038d04  mov     rbx, [r11+40h]
0x180038d08  mov     rsi, [r11+48h]
0x180038d0c  mov     rsp, r11
0x180038d0f  pop     r15
0x180038d11  pop     r14
0x180038d13  pop     r12
0x180038d15  pop     rdi
0x180038d16  pop     rbp
0x180038d17  retn
```
