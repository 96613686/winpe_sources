# AppReadiness::User::ImportPackageUserStatusToStateRepository(void)

- ea: `0x18001c238`
- end: `0x18001c70f`
- name: `?ImportPackageUserStatusToStateRepository@User@AppReadiness@@AEAAJXZ`
- size: `1239`
- prototype: `__int64 __fastcall(AppReadiness::User *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010afc`

## callees

- `0x18000e4a0`
- `0x18001c238`
- `0x18001c930`
- `0x1800232cc`
- `0x180027780`
- `0x18002c40c`
- `0x18002edec`
- `0x180030914`
- `0x18003235c`
- `0x18003e210`
- `0x18003f237`
- `0x18003f2ce`
- `0x18003f999`
- `0x180049580`
- `0x18005f25c`
- `0x180074738`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c4fd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c616`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c6af`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c4fd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c616`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001c6af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c4b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c511`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c5fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c4b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c511`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001c5fd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c3f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c3fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c45d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c3f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c3fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c45d`

## string_xrefs

- `0x18001c395`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18001c636`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18001c6c2`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18001c6de`: `onecore\base\appmodel\common\registrykey.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall AppReadiness::User::ImportPackageUserStatusToStateRepository(AppReadiness::User *this)
{
  const WCHAR *v1; // rdi
  WCHAR *v2; // rdx
  const WCHAR *v3; // rdx
  LSTATUS v4; // eax
  signed int v5; // ebx
  const WCHAR *v6; // rbx
  LSTATUS v7; // eax
  __int64 v8; // rdx
  LSTATUS v10; // eax
  HSTRING v11; // r12
  const WCHAR *v12; // r14
  unsigned __int64 v13; // rbx
  int v14; // eax
  int v15; // eax
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // r15
  __int64 (__fastcall *v20)(__int64, HSTRING, HSTRING, int *, int *); // r13
  const WCHAR *v21; // r14
  unsigned __int64 v22; // rcx
  int phkResult; // [rsp+20h] [rbp-89h]
  int phkResulta; // [rsp+20h] [rbp-89h]
  int phkResultb; // [rsp+20h] [rbp-89h]
  DWORD cbData; // [rsp+50h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-51h] BYREF
  BYTE Data[4]; // [rsp+60h] [rbp-49h] BYREF
  int v29; // [rsp+64h] [rbp-45h] BYREF
  int v30; // [rsp+68h] [rbp-41h] BYREF
  __int64 v31; // [rsp+70h] [rbp-39h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+78h] [rbp-31h] BYREF
  __int128 v33; // [rsp+88h] [rbp-21h]
  HSTRING string; // [rsp+98h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+A0h] [rbp-9h] BYREF
  HSTRING v36; // [rsp+B8h] [rbp+Fh] BYREF
  HSTRING_HEADER v37; // [rsp+C0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v1 = (const WCHAR *)((char *)this + 64);
  *(_OWORD *)lpSubKey = 0;
  v33 = 0;
  if ( *((_QWORD *)this + 11) <= 7u )
    v2 = (WCHAR *)((char *)this + 64);
  else
    v2 = *(WCHAR **)v1;
  std::wstring::_Construct<2,unsigned short const *>(lpSubKey, v2, *((_QWORD *)this + 10));
  std::wstring::_Append<unsigned short>(lpSubKey);
  v3 = (const WCHAR *)lpSubKey;
  if ( *((_QWORD *)&v33 + 1) > 7u )
    v3 = lpSubKey[0];
  hKey = 0;
  v4 = RegOpenKeyExW_0(HKEY_USERS, v3, 0, 0x20019u, &hKey);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 <= -2147024895 || (unsigned int)(v5 + 2147024892) <= 0x7FF8FFFB )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A,
      (unsigned int)"onecore\\base\\appmodel\\common\\registrykey.cpp",
      (const char *)(unsigned int)v5,
      phkResult);
    v8 = 3029;
    goto LABEL_18;
  }
  if ( (((unsigned __int64)hKey + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v6 = (const WCHAR *)lpSubKey;
    if ( *((_QWORD *)&v33 + 1) > 7u )
      v6 = lpSubKey[0];
    if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
      RegCloseKey(hKey);
    hKey = 0;
    v7 = RegCreateKeyExW_0(HKEY_USERS, v6, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
    v5 = v7;
    if ( v7 > 0 )
      v5 = (unsigned __int16)v7 | 0x80070000;
    if ( v5 < 0 )
    {
      v8 = 3034;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        (const char *)(unsigned int)v5,
        phkResulta);
      if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
        RegCloseKey(hKey);
      if ( *((_QWORD *)&v33 + 1) > 7u )
        std::_Deallocate<16>((void *)lpSubKey[0], 2LL * *((_QWORD *)&v33 + 1) + 2);
      return (unsigned int)v5;
    }
    cbData = 1;
    v15 = Common::RegistryKey::SetValue((Common::RegistryKey *)&hKey, L"PackageStatusImported", &cbData, 4u, 4u);
    v5 = v15;
    if ( v15 >= 0 )
    {
      v5 = 0;
LABEL_46:
      Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&hKey);
      std::pair<std::wstring,enum AppReadiness::Storage::PackageOperation>::~pair<std::wstring,enum AppReadiness::Storage::PackageOperation>(lpSubKey);
      return (unsigned int)v5;
    }
    v16 = (unsigned int)v15;
    v17 = 3035;
LABEL_62:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
      (const char *)v16,
      phkResultb);
    goto LABEL_46;
  }
  *(_DWORD *)Data = 0;
  cbData = 4;
  v10 = RegQueryValueExW_0(hKey, L"PackageStatusImported", 0, 0, Data, &cbData);
  v5 = v10;
  if ( v10 > 0 )
    v5 = (unsigned __int16)v10 | 0x80070000;
  if ( v5 <= -2147024895 || (unsigned int)(v5 + 2147024892) <= 0x7FF8FFFB )
  {
    v16 = (unsigned int)v5;
    v17 = 3041;
    goto LABEL_62;
  }
  if ( v5 < 0 || !*(_DWORD *)Data )
  {
    v31 = 0;
    if ( WindowsCreateStringReference(
           L"Windows.Internal.StateRepository.Management.RepositoryManager",
           0x3Du,
           &hstringHeader,
           &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v18 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::Management::IRepositoryManager>>(
            (__int64)string,
            &v31);
    v5 = v18;
    if ( v18 >= 0 )
    {
      v30 = 0;
      v29 = 0;
      v19 = v31;
      v20 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, int *, int *))(*(_QWORD *)v31 + 304LL);
      v21 = (const WCHAR *)lpSubKey;
      if ( *((_QWORD *)&v33 + 1) > 7u )
        v21 = lpSubKey[0];
      cbData = 0;
      v13 = -1;
      v22 = -1;
      do
        ++v22;
      while ( v21[v22] );
      if ( (int)ULongLongToULong(v22, &cbData) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      WindowsCreateStringReference(v21, cbData, &hstringHeader, &string);
      v11 = string;
      if ( *((_QWORD *)v1 + 3) <= 7u )
        v12 = v1;
      else
        v12 = *(const WCHAR **)v1;
      cbData = 0;
      do
        ++v13;
      while ( v12[v13] );
      if ( (int)ULongLongToULong(v13, &cbData) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      WindowsCreateStringReference(v12, cbData, &v37, &v36);
      v14 = v20(v19, v36, v11, &v30, &v29);
      if ( (Microsoft_Windows_AppReadinessEnableBits & 0x100000) != 0 )
      {
        if ( *((_QWORD *)v1 + 3) > 7u )
          v1 = *(const WCHAR **)v1;
        McTemplateU0zdqq_EventWriteTransfer(v29, v30, (_DWORD)v1, v14, v30, v29);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
      v5 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBEB,
        (unsigned int)"onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
        (const char *)(unsigned int)v18,
        phkResultb);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    }
    goto LABEL_46;
  }
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  if ( *((_QWORD *)&v33 + 1) > 7u )
    std::_Deallocate<16>((void *)lpSubKey[0], 2LL * *((_QWORD *)&v33 + 1) + 2);
  return 0;
}

```

## disassembly

```asm
0x18001c238  mov     [rsp-8+arg_8], rbx
0x18001c23d  mov     [rsp-8+arg_10], rdi
0x18001c242  push    rbp
0x18001c243  push    r12
0x18001c245  push    r13
0x18001c247  push    r14
0x18001c249  push    r15
0x18001c24b  lea     rbp, [rsp-37h]
0x18001c250  sub     rsp, 0E0h
0x18001c257  mov     rax, cs:__security_cookie
0x18001c25e  xor     rax, rsp
0x18001c261  mov     [rbp+57h+var_28], rax
0x18001c265  lea     rdi, [rcx+40h]
0x18001c269  xorps   xmm0, xmm0
0x18001c26c  movups  xmmword ptr [rbp+57h+lpSubKey], xmm0
0x18001c270  xorps   xmm1, xmm1
0x18001c273  movdqu  [rbp+57h+var_78], xmm1
0x18001c278  cmp     qword ptr [rdi+18h], 7
0x18001c27d  jbe     loc_18001C3ED
0x18001c283  mov     rdx, [rdi]
0x18001c286  mov     r8, [rdi+10h]
0x18001c28a  lea     rcx, [rbp+57h+lpSubKey]
0x18001c28e  call    ??$_Construct@$01PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<2,ushort const *>(ushort const * const,unsigned __int64)
0x18001c293  nop
0x18001c294  mov     r8d, 67h ; 'g'
0x18001c29a  lea     rdx, aSoftwareClasse_0; "\\Software\\Classes\\Local Settings\\So"...
0x18001c2a1  lea     rcx, [rbp+57h+lpSubKey]; Src
0x18001c2a5  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18001c2aa  nop
0x18001c2ab  lea     rdx, [rbp+57h+lpSubKey]
0x18001c2af  cmp     qword ptr [rbp+57h+var_78+8], 7
0x18001c2b4  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18001c2b9  xor     r12d, r12d
0x18001c2bc  mov     [rbp+57h+hKey], r12
0x18001c2c0  lea     rax, [rbp+57h+hKey]
0x18001c2c4  mov     [rsp+100h+phkResult], rax; int
0x18001c2c9  mov     r9d, 20019h; samDesired
0x18001c2cf  xor     r8d, r8d; ulOptions
0x18001c2d2  mov     r13, 0FFFFFFFF80000003h
0x18001c2d9  mov     rcx, r13; hKey
0x18001c2dc  call    RegOpenKeyExW_0
0x18001c2e1  mov     ebx, eax
0x18001c2e3  mov     r15d, 80070000h
0x18001c2e9  test    eax, eax
0x18001c2eb  jle     short loc_18001C2F3
0x18001c2ed  movzx   ebx, ax
0x18001c2f0  or      ebx, r15d
0x18001c2f3  cmp     ebx, 80070001h
0x18001c2f9  jle     loc_18001C6D7
0x18001c2ff  lea     eax, [rbx+7FF8FFFCh]
0x18001c305  mov     r14d, 7FF8FFFBh
0x18001c30b  cmp     eax, r14d
0x18001c30e  jbe     loc_18001C6D7
0x18001c314  mov     rcx, [rbp+57h+hKey]; hKey
0x18001c318  lea     rax, [rcx+1]
0x18001c31c  test    rax, 0FFFFFFFFFFFFFFFEh
0x18001c322  jnz     loc_18001C465
0x18001c328  lea     rbx, [rbp+57h+lpSubKey]
0x18001c32c  cmp     qword ptr [rbp+57h+var_78+8], 7
0x18001c331  cmova   rbx, [rbp+57h+lpSubKey]
0x18001c336  lea     rax, [rcx-1]
0x18001c33a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001c33e  jbe     loc_18001C3FE
0x18001c344  mov     [rbp+57h+hKey], r12
0x18001c348  mov     [rsp+100h+lpdwDisposition], r12; lpdwDisposition
0x18001c34d  lea     rax, [rbp+57h+hKey]
0x18001c351  mov     [rsp+100h+var_C8], rax; phkResult
0x18001c356  mov     [rsp+100h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18001c35b  mov     [rsp+100h+samDesired], 2001Fh; samDesired
0x18001c363  mov     dword ptr [rsp+100h+phkResult], r12d; int
0x18001c368  xor     r9d, r9d; lpClass
0x18001c36b  xor     r8d, r8d; Reserved
0x18001c36e  mov     rdx, rbx; lpSubKey
0x18001c371  mov     rcx, r13; hKey
0x18001c374  call    RegCreateKeyExW_0
0x18001c379  mov     ebx, eax
0x18001c37b  test    eax, eax
0x18001c37d  jle     short loc_18001C385
0x18001c37f  movzx   ebx, ax
0x18001c382  or      ebx, r15d
0x18001c385  test    ebx, ebx
0x18001c387  jns     loc_18001C58E
0x18001c38d  mov     edx, 0BDAh; void *
0x18001c392  mov     r9d, ebx; char *
0x18001c395  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18001c39c  mov     rcx, [rbp+5Fh]; this
0x18001c3a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c3a5  nop
0x18001c3a6  mov     rcx, [rbp+57h+hKey]; hKey
0x18001c3aa  lea     rax, [rcx-1]
0x18001c3ae  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001c3b2  jbe     short loc_18001C3F5
0x18001c3b4  mov     rdx, qword ptr [rbp+57h+var_78+8]
0x18001c3b8  cmp     rdx, 7
0x18001c3bc  ja      loc_18001C6F9
0x18001c3c2  mov     eax, ebx
0x18001c3c4  mov     rcx, [rbp+57h+var_28]
0x18001c3c8  xor     rcx, rsp; StackCookie
0x18001c3cb  call    __security_check_cookie
0x18001c3d0  lea     r11, [rsp+100h+var_20]
0x18001c3d8  mov     rbx, [r11+38h]
0x18001c3dc  mov     rdi, [r11+40h]
0x18001c3e0  mov     rsp, r11
0x18001c3e3  pop     r15
0x18001c3e5  pop     r14
0x18001c3e7  pop     r13
0x18001c3e9  pop     r12
0x18001c3eb  pop     rbp
0x18001c3ec  retn
0x18001c3ed  mov     rdx, rdi
0x18001c3f0  jmp     loc_18001C286
0x18001c3f5  call    cs:__imp_RegCloseKey
0x18001c3fb  nop
0x18001c3fc  jmp     short loc_18001C3B4
0x18001c3fe  call    cs:__imp_RegCloseKey
0x18001c404  jmp     loc_18001C344
0x18001c409  cmp     ebx, 80070001h
0x18001c40f  jle     loc_18001C6BA
0x18001c415  lea     eax, [rbx+7FF8FFFCh]
0x18001c41b  cmp     eax, r14d
0x18001c41e  jbe     loc_18001C6BA
0x18001c424  shr     ebx, 1Fh
0x18001c427  xor     bl, 1
0x18001c42a  jz      loc_18001C5E5
0x18001c430  cmp     dword ptr [rbp+57h+Data], r12d
0x18001c434  jbe     loc_18001C5E5
0x18001c43a  mov     rcx, [rbp+57h+hKey]; hKey
0x18001c43e  lea     rax, [rcx-1]
0x18001c442  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001c446  jbe     short loc_18001C45D
0x18001c448  mov     rdx, qword ptr [rbp+57h+var_78+8]
0x18001c44c  cmp     rdx, 7
0x18001c450  ja      loc_18001C5CF
0x18001c456  xor     eax, eax
0x18001c458  jmp     loc_18001C3C4
0x18001c45d  call    cs:__imp_RegCloseKey
0x18001c463  jmp     short loc_18001C448
0x18001c465  mov     dword ptr [rbp+57h+Data], r12d
0x18001c469  mov     [rbp+57h+cbData], 4
0x18001c470  lea     rax, [rbp+57h+cbData]
0x18001c474  mov     qword ptr [rsp+100h+samDesired], rax; lpcbData
0x18001c479  lea     rax, [rbp+57h+Data]
0x18001c47d  mov     [rsp+100h+phkResult], rax; int
0x18001c482  xor     r9d, r9d; lpType
0x18001c485  xor     r8d, r8d; lpReserved
0x18001c488  lea     rdx, aPackagestatusi; "PackageStatusImported"
0x18001c48f  call    RegQueryValueExW_0
0x18001c494  mov     ebx, eax
0x18001c496  test    eax, eax
0x18001c498  jle     loc_18001C409
0x18001c49e  movzx   ebx, ax
0x18001c4a1  or      ebx, r15d
0x18001c4a4  jmp     loc_18001C409
0x18001c4a9  lea     r9, [rbp+57h+string]; string
0x18001c4ad  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001c4b1  mov     edx, [rbp+57h+cbData]; length
0x18001c4b4  mov     rcx, r14; sourceString
0x18001c4b7  call    cs:__imp_WindowsCreateStringReference
0x18001c4bd  mov     r12, [rbp+57h+string]
0x18001c4c1  cmp     qword ptr [rdi+18h], 7
0x18001c4c6  jbe     loc_18001C586
0x18001c4cc  mov     r14, [rdi]
0x18001c4cf  xor     eax, eax
0x18001c4d1  mov     [rbp+57h+cbData], eax
0x18001c4d4  inc     rbx
0x18001c4d7  cmp     [r14+rbx*2], ax
0x18001c4dc  jnz     short loc_18001C4D4
0x18001c4de  lea     rdx, [rbp+57h+cbData]; unsigned int *
0x18001c4e2  mov     rcx, rbx; unsigned __int64
0x18001c4e5  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18001c4ea  test    eax, eax
0x18001c4ec  jns     short loc_18001C503
0x18001c4ee  xor     r9d, r9d; lpArguments
0x18001c4f1  xor     r8d, r8d; nNumberOfArguments
0x18001c4f4  lea     edx, [r9+1]; dwExceptionFlags
0x18001c4f8  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001c4fd  call    cs:__imp_RaiseException
0x18001c503  lea     r9, [rbp+57h+var_48]; string
0x18001c507  lea     r8, [rbp+57h+var_40]; hstringHeader
0x18001c50b  mov     edx, [rbp+57h+cbData]; length
0x18001c50e  mov     rcx, r14; sourceString
0x18001c511  call    cs:__imp_WindowsCreateStringReference
0x18001c517  lea     rax, [rbp+57h+var_9C]
0x18001c51b  mov     [rsp+100h+phkResult], rax
0x18001c520  lea     r9, [rbp+57h+var_98]
0x18001c524  mov     r8, r12
0x18001c527  mov     rdx, [rbp+57h+var_48]
0x18001c52b  mov     rcx, r15
0x18001c52e  mov     rax, r13
0x18001c531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c536  test    byte ptr cs:Microsoft_Windows_AppReadinessEnableBits+2, 10h
0x18001c53d  jz      short loc_18001C563
0x18001c53f  mov     ecx, [rbp+57h+var_9C]
0x18001c542  mov     edx, [rbp+57h+var_98]
0x18001c545  cmp     qword ptr [rdi+18h], 7
0x18001c54a  jbe     short loc_18001C54F
0x18001c54c  mov     rdi, [rdi]
0x18001c54f  mov     [rsp+100h+samDesired], ecx
0x18001c553  mov     dword ptr [rsp+100h+phkResult], edx
0x18001c557  mov     r9d, eax
0x18001c55a  mov     r8, rdi
0x18001c55d  call    McTemplateU0zdqq_EventWriteTransfer
0x18001c562  nop
0x18001c563  lea     rcx, [rbp+57h+var_90]
0x18001c567  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001c56c  xor     ebx, ebx
0x18001c56e  lea     rcx, [rbp+57h+hKey]; this
0x18001c572  call    ??1RegistryKey@Common@@QEAA@XZ; Common::RegistryKey::~RegistryKey(void)
0x18001c577  nop
0x18001c578  lea     rcx, [rbp+57h+lpSubKey]
0x18001c57c  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4PackageOperation@Storage@AppReadiness@@@std@@QEAA@XZ; std::pair<std::wstring,AppReadiness::Storage::PackageOperation>::~pair<std::wstring,AppReadiness::Storage::PackageOperation>(void)
0x18001c581  jmp     loc_18001C3C2
0x18001c586  mov     r14, rdi
0x18001c589  jmp     loc_18001C4CF
0x18001c58e  mov     [rbp+57h+cbData], 1
0x18001c595  mov     dword ptr [rsp+100h+phkResult], 4; unsigned int
0x18001c59d  mov     r9d, 4; unsigned int
0x18001c5a3  lea     r8, [rbp+57h+cbData]; void *
0x18001c5a7  lea     rdx, aPackagestatusi; "PackageStatusImported"
0x18001c5ae  lea     rcx, [rbp+57h+hKey]; this
0x18001c5b2  call    ?SetValue@RegistryKey@Common@@QEAAJPEBGPEBXKK@Z; Common::RegistryKey::SetValue(ushort const *,void const *,ulong,ulong)
0x18001c5b7  mov     ebx, eax
0x18001c5b9  test    eax, eax
0x18001c5bb  jns     short loc_18001C5CA
0x18001c5bd  mov     r9d, eax
0x18001c5c0  mov     edx, 0BDBh
0x18001c5c5  jmp     loc_18001C6C2
0x18001c5ca  mov     ebx, r12d
0x18001c5cd  jmp     short loc_18001C56E
0x18001c5cf  lea     rdx, ds:2[rdx*2]
0x18001c5d7  mov     rcx, [rbp+57h+lpSubKey]
0x18001c5db  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001c5e0  jmp     loc_18001C456
0x18001c5e5  mov     [rbp+57h+var_90], r12
0x18001c5e9  lea     r9, [rbp+57h+string]; string
0x18001c5ed  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18001c5f1  mov     edx, 3Dh ; '='; length
0x18001c5f6  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Management_RepositoryManager@@3QBGB; "Windows.Internal.StateRepository.Manage"...
0x18001c5fd  call    cs:__imp_WindowsCreateStringReference
0x18001c603  test    eax, eax
0x18001c605  jns     short loc_18001C61C
0x18001c607  xor     r9d, r9d; lpArguments
0x18001c60a  xor     r8d, r8d; nNumberOfArguments
0x18001c60d  lea     edx, [r9+1]; dwExceptionFlags
0x18001c611  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001c616  call    cs:__imp_RaiseException
0x18001c61c  lea     rdx, [rbp+57h+var_90]
0x18001c620  mov     rcx, [rbp+57h+string]
0x18001c624  call    ??$ActivateInstance@V?$ComPtr@UIRepositoryManager@Management@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIRepositoryManager@Management@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::Management::IRepositoryManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::Management::IRepositoryManager>>)
0x18001c629  mov     ebx, eax
0x18001c62b  test    eax, eax
0x18001c62d  jns     short loc_18001C656
0x18001c62f  mov     rcx, [rbp+5Fh]; this
0x18001c633  mov     r9d, eax; char *
0x18001c636  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18001c63d  mov     edx, 0BEBh; void *
0x18001c642  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c647  nop
0x18001c648  lea     rcx, [rbp+57h+var_90]
0x18001c64c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001c651  jmp     loc_18001C56E
0x18001c656  mov     [rbp+57h+var_98], r12d
0x18001c65a  mov     [rbp+57h+var_9C], r12d
0x18001c65e  mov     r15, [rbp+57h+var_90]
0x18001c662  mov     rax, [r15]
0x18001c665  mov     r13, [rax+130h]
0x18001c66c  lea     r14, [rbp+57h+lpSubKey]
0x18001c670  cmp     qword ptr [rbp+57h+var_78+8], 7
0x18001c675  cmova   r14, [rbp+57h+lpSubKey]
0x18001c67a  mov     [rbp+57h+cbData], r12d
0x18001c67e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001c682  mov     rcx, rbx
0x18001c685  inc     rcx; unsigned __int64
0x18001c688  cmp     [r14+rcx*2], r12w
0x18001c68d  jnz     short loc_18001C685
0x18001c68f  lea     rdx, [rbp+57h+cbData]; unsigned int *
0x18001c693  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18001c698  test    eax, eax
0x18001c69a  jns     loc_18001C4A9
0x18001c6a0  xor     r9d, r9d; lpArguments
0x18001c6a3  xor     r8d, r8d; nNumberOfArguments
0x18001c6a6  lea     edx, [r9+1]; dwExceptionFlags
0x18001c6aa  mov     ecx, 0C000000Dh; dwExceptionCode
0x18001c6af  call    cs:__imp_RaiseException
0x18001c6b5  jmp     loc_18001C4A9
0x18001c6ba  mov     r9d, ebx; char *
0x18001c6bd  mov     edx, 0BE1h; void *
0x18001c6c2  lea     r8, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18001c6c9  mov     rcx, [rbp+5Fh]; this
0x18001c6cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c6d2  jmp     loc_18001C56E
0x18001c6d7  mov     rcx, [rbp+5Fh]; this
0x18001c6db  mov     r9d, ebx; char *
0x18001c6de  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\regist"...
0x18001c6e5  mov     edx, 5Ah ; 'Z'; void *
0x18001c6ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c6ef  mov     edx, 0BD5h
0x18001c6f4  jmp     loc_18001C392
0x18001c6f9  lea     rdx, ds:2[rdx*2]
0x18001c701  mov     rcx, [rbp+57h+lpSubKey]
  ... truncated ...
```
