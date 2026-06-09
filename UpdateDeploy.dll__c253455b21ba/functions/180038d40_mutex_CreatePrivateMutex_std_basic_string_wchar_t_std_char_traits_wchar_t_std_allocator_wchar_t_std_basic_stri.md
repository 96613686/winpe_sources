# mutex::CreatePrivateMutex(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,WuSmartPtr::XHandleBase<void *,WuSmartPtr::Policies::NullHandlePolicy> &)

- ea: `0x180038d40`
- end: `0x180039166`
- name: `?CreatePrivateMutex@mutex@@YAJV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEAV?$XHandleBase@PEAXUNullHandlePolicy@Policies@WuSmartPtr@@@WuSmartPtr@@@Z`
- size: `1062`
- prototype: `__int64 __fastcall(void *Src, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800369a8`

## callees

- `0x180002214`
- `0x180003180`
- `0x18001b2c8`
- `0x18001c75c`
- `0x1800384b4`
- `0x180038580`
- `0x180038d40`
- `0x18003916c`
- `0x18003923c`
- `0x180061960`
- `0x180061d54`
- `0x1800692e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038fbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038fbe`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180038fa2`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x180038fa2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038fb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180038fb4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180038dd6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180038dd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038dbb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038e00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038e0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038f57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003901a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003903d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003904c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039098`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800390bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800390ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800390f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039114`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039123`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038dbb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038e00`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038e0f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180038f57`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003901a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003903d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003904c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039098`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800390bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800390ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800390f1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039114`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180039123`

## string_xrefs

- `0x180038d9b`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\mutex.cpp`
- `0x180038de4`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\mutex.cpp`
- `0x180038f28`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\mutex.cpp`
- `0x180038fed`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\mutex.cpp`
- `0x18003906b`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\mutex.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall mutex::CreatePrivateMutex(void *Src, _QWORD *a2, HANDLE *a3)
{
  int BuiltinAdminSid; // eax
  unsigned int v7; // ebx
  HLOCAL v8; // rbx
  const char *v9; // r9
  unsigned int LastError; // edi
  LPWSTR v11; // rdi
  __int64 v12; // rax
  _QWORD *v13; // rax
  __int64 v14; // rdi
  unsigned __int64 v15; // rdx
  _QWORD *v16; // r9
  __int64 v17; // rcx
  __int64 v18; // r15
  _QWORD *v19; // rsi
  int v20; // eax
  HLOCAL v21; // rdi
  const WCHAR *v22; // r8
  HANDLE v23; // rsi
  signed int v24; // eax
  signed int v25; // esi
  int v27; // [rsp+20h] [rbp-A9h]
  HLOCAL hMem; // [rsp+30h] [rbp-99h] BYREF
  HLOCAL v29; // [rsp+38h] [rbp-91h] BYREF
  _BYTE v30[32]; // [rsp+40h] [rbp-89h] BYREF
  _BYTE v31[32]; // [rsp+60h] [rbp-69h] BYREF
  struct _SECURITY_ATTRIBUTES MutexAttributes; // [rsp+80h] [rbp-49h] BYREF
  _QWORD *v33; // [rsp+98h] [rbp-31h]
  LPWSTR StringSid; // [rsp+A0h] [rbp-29h] BYREF
  LPCWSTR lpName[2]; // [rsp+A8h] [rbp-21h] BYREF
  __int128 v36; // [rsp+B8h] [rbp-11h]
  _BYTE Srca[32]; // [rsp+C8h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v29 = Src;
  v33 = a2;
  hMem = 0;
  BuiltinAdminSid = mutex::GetBuiltinAdminSid(&hMem);
  v7 = BuiltinAdminSid;
  if ( BuiltinAdminSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFB,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\mutex.cpp",
      (const char *)(unsigned int)BuiltinAdminSid,
      v27);
    if ( hMem )
      LocalFree(hMem);
    goto LABEL_61;
  }
  StringSid = 0;
  v8 = hMem;
  if ( !ConvertSidToStringSidW(hMem, &StringSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xFE,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\mutex.cpp",
                  v9);
LABEL_6:
    if ( StringSid )
      LocalFree(StringSid);
    if ( v8 )
      LocalFree(v8);
    v7 = LastError;
    goto LABEL_61;
  }
  v11 = StringSid;
  v12 = std::operator+<wchar_t>(v30, Src, L"_");
  std::operator+<wchar_t>(Srca, v12, v11);
  std::wstring::~wstring(v30);
  v13 = (_QWORD *)std::operator+<wchar_t>(v31, Srca, (void *)L"\\");
  v14 = (__int64)v13;
  v15 = a2[2];
  v16 = a2;
  if ( a2[3] > 7u )
    v16 = (_QWORD *)*a2;
  v17 = v13[2];
  if ( v15 > v13[3] - v17 )
  {
    v14 = std::wstring::_Reallocate_grow_by<_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64>(
            v13,
            a2[2]);
  }
  else
  {
    v18 = v17 + v15;
    v13[2] = v17 + v15;
    v19 = v13;
    if ( v13[3] > 7u )
      v19 = (_QWORD *)*v13;
    memmove((char *)v19 + 2 * v17, v16, 2 * v15);
    *((_WORD *)v19 + v18) = 0;
  }
  *(_OWORD *)lpName = 0;
  v36 = 0;
  *(_OWORD *)lpName = *(_OWORD *)v14;
  v36 = *(_OWORD *)(v14 + 16);
  *(_QWORD *)(v14 + 16) = 0;
  *(_QWORD *)(v14 + 24) = 7;
  *(_WORD *)v14 = 0;
  std::wstring::~wstring(v31);
  v29 = 0;
  hMem = 0;
  v20 = mutex::CreateSecurityDescriptor(v8, (PACL *)&hMem, &v29);
  LastError = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x106,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\mutex.cpp",
      (const char *)(unsigned int)v20,
      v27);
    if ( hMem )
      operator delete(hMem, (const struct std::nothrow_t *)8);
    if ( v29 )
      LocalFree(v29);
    std::wstring::~wstring(lpName);
    std::wstring::~wstring(Srca);
    goto LABEL_6;
  }
  *(_QWORD *)&MutexAttributes.nLength = 24;
  *(_QWORD *)&MutexAttributes.bInheritHandle = 0;
  v21 = v29;
  MutexAttributes.lpSecurityDescriptor = v29;
  v22 = (const WCHAR *)lpName;
  if ( *((_QWORD *)&v36 + 1) > 7u )
    v22 = lpName[0];
  v23 = CreateMutexW(&MutexAttributes, 0, v22);
  if ( *a3 )
    CloseHandle(*a3);
  *a3 = v23;
  v24 = GetLastError();
  v25 = (unsigned __int16)v24 | 0x80070000;
  if ( v24 <= 0 )
    v25 = v24;
  if ( v25 >= 0 )
    v25 = -2147418113;
  if ( *a3 )
  {
    if ( v25 == -2147024713 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x114,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\mutex.cpp",
        (const char *)0x800700B7LL,
        v27);
      if ( hMem )
        operator delete(hMem, (const struct std::nothrow_t *)8);
      if ( v21 )
        LocalFree(v21);
      std::wstring::~wstring(lpName);
      std::wstring::~wstring(Srca);
      if ( StringSid )
        LocalFree(StringSid);
      if ( v8 )
        LocalFree(v8);
      v7 = -2147024713;
    }
    else
    {
      if ( hMem )
        operator delete(hMem, (const struct std::nothrow_t *)8);
      if ( v21 )
        LocalFree(v21);
      std::wstring::~wstring(lpName);
      std::wstring::~wstring(Srca);
      if ( StringSid )
        LocalFree(StringSid);
      if ( v8 )
        LocalFree(v8);
      v7 = 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x111,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\mutex.cpp",
      (const char *)(unsigned int)v25,
      v27);
    if ( hMem )
      operator delete(hMem, (const struct std::nothrow_t *)8);
    if ( v21 )
      LocalFree(v21);
    std::wstring::~wstring(lpName);
    std::wstring::~wstring(Srca);
    if ( StringSid )
      LocalFree(StringSid);
    if ( v8 )
      LocalFree(v8);
    v7 = v25;
  }
LABEL_61:
  std::wstring::~wstring(Src);
  std::wstring::~wstring(a2);
  return v7;
}

```

## disassembly

```asm
0x180038d40  mov     [rsp-8+arg_18], rbx
0x180038d45  push    rbp
0x180038d46  push    rsi
0x180038d47  push    rdi
0x180038d48  push    r12
0x180038d4a  push    r13
0x180038d4c  push    r14
0x180038d4e  push    r15
0x180038d50  lea     rbp, [rsp-27h]
0x180038d55  sub     rsp, 0F0h
0x180038d5c  mov     rax, cs:__security_cookie
0x180038d63  xor     rax, rsp
0x180038d66  mov     [rbp+57h+var_38], rax
0x180038d6a  mov     r12, r8
0x180038d6d  mov     r14, rdx
0x180038d70  mov     r13, rcx
0x180038d73  mov     [rsp+120h+var_E8], rcx
0x180038d78  mov     [rbp+57h+var_88], rdx
0x180038d7c  xor     r15d, r15d
0x180038d7f  mov     [rsp+120h+hMem], r15
0x180038d84  lea     rcx, [rsp+120h+hMem]
0x180038d89  call    ?GetBuiltinAdminSid@mutex@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; mutex::GetBuiltinAdminSid(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x180038d8e  mov     ebx, eax
0x180038d90  test    eax, eax
0x180038d92  jns     short loc_180038DC6
0x180038d94  mov     rcx, [rbp+5Fh]; this
0x180038d98  mov     r9d, eax; char *
0x180038d9b  lea     r8, aCW1SSrcClientU_12; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180038da2  mov     edx, 0FBh; void *
0x180038da7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038dac  nop
0x180038dad  mov     rcx, [rsp+120h+hMem]; hMem
0x180038db2  test    rcx, rcx
0x180038db5  jz      loc_18003912C
0x180038dbb  call    cs:__imp_LocalFree
0x180038dc1  jmp     loc_18003912C
0x180038dc6  mov     [rbp+57h+StringSid], r15
0x180038dca  lea     rdx, [rbp+57h+StringSid]; StringSid
0x180038dce  mov     rbx, [rsp+120h+hMem]
0x180038dd3  mov     rcx, rbx; Sid
0x180038dd6  call    cs:__imp_ConvertSidToStringSidW
0x180038ddc  test    eax, eax
0x180038dde  jnz     short loc_180038E1C
0x180038de0  mov     rcx, [rbp+5Fh]; this
0x180038de4  lea     r8, aCW1SSrcClientU_12; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180038deb  mov     edx, 0FEh; void *
0x180038df0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180038df5  mov     edi, eax
0x180038df7  mov     rcx, [rbp+57h+StringSid]; hMem
0x180038dfb  test    rcx, rcx
0x180038dfe  jz      short loc_180038E07
0x180038e00  call    cs:__imp_LocalFree
0x180038e06  nop
0x180038e07  test    rbx, rbx
0x180038e0a  jz      short loc_180038E15
0x180038e0c  mov     rcx, rbx; hMem
0x180038e0f  call    cs:__imp_LocalFree
0x180038e15  mov     ebx, edi
0x180038e17  jmp     loc_18003912C
0x180038e1c  mov     rdi, [rbp+57h+StringSid]
0x180038e20  lea     r8, asc_18007B970; "_"
0x180038e27  mov     rdx, r13; Src
0x180038e2a  lea     rcx, [rsp+120h+var_E0]; void *
0x180038e2f  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring const &,wchar_t const * const)
0x180038e34  nop
0x180038e35  mov     r8, rdi
0x180038e38  mov     rdx, rax
0x180038e3b  lea     rcx, [rbp+57h+Src]
0x180038e3f  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x180038e44  nop
0x180038e45  lea     rcx, [rsp+120h+var_E0]
0x180038e4a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038e4f  lea     r8, SubBlock; "\\"
0x180038e56  lea     rdx, [rbp+57h+Src]; Src
0x180038e5a  lea     rcx, [rbp+57h+var_C0]; void *
0x180038e5e  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@AEBV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring const &,wchar_t const * const)
0x180038e63  mov     rdi, rax
0x180038e66  mov     rdx, [r14+10h]
0x180038e6a  mov     r9, r14
0x180038e6d  cmp     qword ptr [r14+18h], 7
0x180038e72  jbe     short loc_180038E77
0x180038e74  mov     r9, [r14]
0x180038e77  mov     rcx, [rax+10h]
0x180038e7b  mov     rax, [rax+18h]
0x180038e7f  sub     rax, rcx
0x180038e82  cmp     rdx, rax
0x180038e85  ja      short loc_180038EB8
0x180038e87  lea     r15, [rcx+rdx]
0x180038e8b  mov     [rdi+10h], r15
0x180038e8f  mov     rsi, rdi
0x180038e92  cmp     qword ptr [rdi+18h], 7
0x180038e97  jbe     short loc_180038E9C
0x180038e99  mov     rsi, [rdi]
0x180038e9c  lea     r8, [rdx+rdx]; Size
0x180038ea0  lea     rcx, [rsi+rcx*2]; void *
0x180038ea4  mov     rdx, r9; Src
0x180038ea7  call    memmove
0x180038eac  xor     eax, eax
0x180038eae  mov     [rsi+r15*2], ax
0x180038eb3  xor     r15d, r15d
0x180038eb6  jmp     short loc_180038EC8
0x180038eb8  mov     qword ptr [rsp+120h+var_100], rdx; int
0x180038ebd  mov     rcx, rdi; Src
0x180038ec0  call    ??$_Reallocate_grow_by@V_lambda_1dfe18491bcca09701d8ccb01d0b0af4_@@PEB_W_K@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_1dfe18491bcca09701d8ccb01d0b0af4_@@PEB_W_K@Z; std::wstring::_Reallocate_grow_by<_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64>(unsigned __int64,_lambda_1dfe18491bcca09701d8ccb01d0b0af4_,wchar_t const *,unsigned __int64)
0x180038ec5  mov     rdi, rax
0x180038ec8  xorps   xmm0, xmm0
0x180038ecb  movups  xmmword ptr [rbp+57h+lpName], xmm0
0x180038ecf  xorps   xmm1, xmm1
0x180038ed2  movdqu  [rbp+57h+var_68], xmm1
0x180038ed7  movups  xmm0, xmmword ptr [rdi]
0x180038eda  movups  xmmword ptr [rbp+57h+lpName], xmm0
0x180038ede  movups  xmm1, xmmword ptr [rdi+10h]
0x180038ee2  movups  [rbp+57h+var_68], xmm1
0x180038ee6  mov     [rdi+10h], r15
0x180038eea  mov     qword ptr [rdi+18h], 7
0x180038ef2  mov     [rdi], r15w
0x180038ef6  lea     rcx, [rbp+57h+var_C0]
0x180038efa  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038eff  mov     [rsp+120h+var_E8], r15
0x180038f04  mov     [rsp+120h+hMem], r15
0x180038f09  lea     r8, [rsp+120h+var_E8]
0x180038f0e  lea     rdx, [rsp+120h+hMem]
0x180038f13  mov     rcx, rbx; pSid
0x180038f16  call    ?CreateSecurityDescriptor@mutex@@YAJPEAXAEAV?$unique_ptr@U_ACL@@U?$default_delete@U_ACL@@@std@@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; mutex::CreateSecurityDescriptor(void *,std::unique_ptr<_ACL> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x180038f1b  mov     edi, eax
0x180038f1d  test    eax, eax
0x180038f1f  jns     short loc_180038F75
0x180038f21  mov     rcx, [rbp+5Fh]; this
0x180038f25  mov     r9d, eax; char *
0x180038f28  lea     r8, aCW1SSrcClientU_12; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180038f2f  mov     edx, 106h; void *
0x180038f34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038f39  mov     rcx, [rsp+120h+hMem]; void *
0x180038f3e  test    rcx, rcx
0x180038f41  jz      short loc_180038F4D
0x180038f43  mov     edx, 8; struct std::nothrow_t *
0x180038f48  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180038f4d  mov     rcx, [rsp+120h+var_E8]; hMem
0x180038f52  test    rcx, rcx
0x180038f55  jz      short loc_180038F5D
0x180038f57  call    cs:__imp_LocalFree
0x180038f5d  lea     rcx, [rbp+57h+lpName]
0x180038f61  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038f66  nop
0x180038f67  lea     rcx, [rbp+57h+Src]
0x180038f6b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038f70  jmp     loc_180038DF7
0x180038f75  mov     qword ptr [rbp+57h+MutexAttributes.nLength], 18h
0x180038f7d  mov     qword ptr [rbp+57h+MutexAttributes.bInheritHandle], 0
0x180038f85  mov     rdi, [rsp+120h+var_E8]
0x180038f8a  mov     [rbp+57h+MutexAttributes.lpSecurityDescriptor], rdi
0x180038f8e  lea     r8, [rbp+57h+lpName]
0x180038f92  cmp     qword ptr [rbp+57h+var_68+8], 7
0x180038f97  cmova   r8, [rbp+57h+lpName]; lpName
0x180038f9c  xor     edx, edx; bInitialOwner
0x180038f9e  lea     rcx, [rbp+57h+MutexAttributes]; lpMutexAttributes
0x180038fa2  call    cs:__imp_CreateMutexW
0x180038fa8  mov     rsi, rax
0x180038fab  mov     rcx, [r12]; hObject
0x180038faf  test    rcx, rcx
0x180038fb2  jz      short loc_180038FBA
0x180038fb4  call    cs:__imp_CloseHandle
0x180038fba  mov     [r12], rsi
0x180038fbe  call    cs:__imp_GetLastError
0x180038fc4  movzx   esi, ax
0x180038fc7  or      esi, 80070000h
0x180038fcd  test    eax, eax
0x180038fcf  cmovle  esi, eax
0x180038fd2  mov     eax, 8000FFFFh
0x180038fd7  test    esi, esi
0x180038fd9  cmovns  esi, eax
0x180038fdc  cmp     [r12], r15
0x180038fe0  jnz     short loc_180039059
0x180038fe2  test    esi, esi
0x180038fe4  jns     short loc_180038FFE
0x180038fe6  mov     rcx, [rbp+5Fh]; this
0x180038fea  mov     r9d, esi; char *
0x180038fed  lea     r8, aCW1SSrcClientU_12; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180038ff4  mov     edx, 111h; void *
0x180038ff9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038ffe  mov     rcx, [rsp+120h+hMem]; void *
0x180039003  test    rcx, rcx
0x180039006  jz      short loc_180039012
0x180039008  mov     edx, 8; struct std::nothrow_t *
0x18003900d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180039012  test    rdi, rdi
0x180039015  jz      short loc_180039020
0x180039017  mov     rcx, rdi; hMem
0x18003901a  call    cs:__imp_LocalFree
0x180039020  lea     rcx, [rbp+57h+lpName]
0x180039024  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039029  nop
0x18003902a  lea     rcx, [rbp+57h+Src]
0x18003902e  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039033  nop
0x180039034  mov     rcx, [rbp+57h+StringSid]; hMem
0x180039038  test    rcx, rcx
0x18003903b  jz      short loc_180039044
0x18003903d  call    cs:__imp_LocalFree
0x180039043  nop
0x180039044  test    rbx, rbx
0x180039047  jz      short loc_180039052
0x180039049  mov     rcx, rbx; hMem
0x18003904c  call    cs:__imp_LocalFree
0x180039052  mov     ebx, esi
0x180039054  jmp     loc_18003912C
0x180039059  mov     r12d, 800700B7h
0x18003905f  cmp     esi, r12d
0x180039062  jnz     short loc_1800390D5
0x180039064  mov     rcx, [rbp+5Fh]; this
0x180039068  mov     r9d, r12d; char *
0x18003906b  lea     r8, aCW1SSrcClientU_12; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180039072  mov     edx, 114h; void *
0x180039077  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003907c  mov     rcx, [rsp+120h+hMem]; void *
0x180039081  test    rcx, rcx
0x180039084  jz      short loc_180039090
0x180039086  mov     edx, 8; struct std::nothrow_t *
0x18003908b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180039090  test    rdi, rdi
0x180039093  jz      short loc_18003909E
0x180039095  mov     rcx, rdi; hMem
0x180039098  call    cs:__imp_LocalFree
0x18003909e  lea     rcx, [rbp+57h+lpName]
0x1800390a2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800390a7  nop
0x1800390a8  lea     rcx, [rbp+57h+Src]
0x1800390ac  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800390b1  nop
0x1800390b2  mov     rcx, [rbp+57h+StringSid]; hMem
0x1800390b6  test    rcx, rcx
0x1800390b9  jz      short loc_1800390C2
0x1800390bb  call    cs:__imp_LocalFree
0x1800390c1  nop
0x1800390c2  test    rbx, rbx
0x1800390c5  jz      short loc_1800390D0
0x1800390c7  mov     rcx, rbx; hMem
0x1800390ca  call    cs:__imp_LocalFree
0x1800390d0  mov     ebx, r12d
0x1800390d3  jmp     short loc_18003912C
0x1800390d5  mov     rcx, [rsp+120h+hMem]; void *
0x1800390da  test    rcx, rcx
0x1800390dd  jz      short loc_1800390E9
0x1800390df  mov     edx, 8; struct std::nothrow_t *
0x1800390e4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800390e9  test    rdi, rdi
0x1800390ec  jz      short loc_1800390F7
0x1800390ee  mov     rcx, rdi; hMem
0x1800390f1  call    cs:__imp_LocalFree
0x1800390f7  lea     rcx, [rbp+57h+lpName]
0x1800390fb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039100  nop
0x180039101  lea     rcx, [rbp+57h+Src]
0x180039105  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003910a  nop
0x18003910b  mov     rcx, [rbp+57h+StringSid]; hMem
0x18003910f  test    rcx, rcx
0x180039112  jz      short loc_18003911B
0x180039114  call    cs:__imp_LocalFree
0x18003911a  nop
0x18003911b  test    rbx, rbx
0x18003911e  jz      short loc_180039129
0x180039120  mov     rcx, rbx; hMem
0x180039123  call    cs:__imp_LocalFree
0x180039129  mov     ebx, r15d
0x18003912c  mov     rcx, r13
0x18003912f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180039134  nop
0x180039135  mov     rcx, r14
0x180039138  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003913d  mov     eax, ebx
0x18003913f  mov     rcx, [rbp+57h+var_38]
0x180039143  xor     rcx, rsp; StackCookie
0x180039146  call    __security_check_cookie
0x18003914b  mov     rbx, [rsp+120h+arg_18]
0x180039153  add     rsp, 0F0h
0x18003915a  pop     r15
0x18003915c  pop     r14
0x18003915e  pop     r13
0x180039160  pop     r12
0x180039162  pop     rdi
0x180039163  pop     rsi
0x180039164  pop     rbp
0x180039165  retn
```
