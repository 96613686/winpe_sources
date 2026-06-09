# IsTrackedByResourceManager

- ea: `0x180034548`
- end: `0x180034936`
- name: `IsTrackedByResourceManager`
- size: `1006`
- prototype: `__int64 __fastcall(wchar_t *SubStr, LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180031d60`

## callees

- `0x180002a60`
- `0x180002f0c`
- `0x18000421c`
- `0x18000526c`
- `0x1800058fc`
- `0x1800096ec`
- `0x18002ed1c`
- `0x180033d34`
- `0x180034548`
- `0x1800349f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180034812`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180034812`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003465d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034721`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003465d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034721`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800345ef`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800346af`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800345ef`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800346af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034625`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800346e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034625`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800346e5`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003476f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800347fc`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003476f`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800347fc`

## string_xrefs

- `0x180034861`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`
- `0x1800348ba`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`
- `0x1800348d4`: `shellcommon\shell\settingshandlers\workaccess\lib\accountenthusiast.cpp`

## pseudocode

```c
__int64 __fastcall IsTrackedByResourceManager(wchar_t *SubStr, LPCWSTR lpSubKey, _BYTE *a3)
{
  int ResourceManagerTrackedKeyForEnrollment; // eax
  unsigned int v6; // ebx
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  DWORD i; // r15d
  unsigned int v10; // eax
  HKEY v11; // rbx
  LSTATUS v12; // eax
  DWORD v13; // r14d
  HKEY v14; // rdi
  DWORD j; // esi
  unsigned __int64 v16; // rax
  BYTE *v17; // rax
  BYTE *v18; // rdi
  unsigned int v19; // eax
  const struct std::nothrow_t *v20; // rdx
  const struct std::nothrow_t *v21; // rdx
  __int64 v22; // rdx
  int v23; // eax
  unsigned int lpReserved; // [rsp+20h] [rbp-E0h]
  unsigned int lpReserveda; // [rsp+20h] [rbp-E0h]
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v30; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v32[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v33[8]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+280h] [rbp+180h] BYREF
  WCHAR ValueName[264]; // [rsp+490h] [rbp+390h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6E8h] [rbp+5E8h]

  v30 = 0;
  phkResult = 0;
  cbData = 0;
  *a3 = 0;
  cchName = 260;
  hKey = 0;
  ResourceManagerTrackedKeyForEnrollment = GetResourceManagerTrackedKeyForEnrollment(lpSubKey, &hKey);
  v6 = ResourceManagerTrackedKeyForEnrollment;
  if ( ResourceManagerTrackedKeyForEnrollment < 0 )
  {
    v7 = (unsigned int)ResourceManagerTrackedKeyForEnrollment;
    v8 = 220;
    goto LABEL_37;
  }
  v6 = 0;
  for ( i = 0; ; ++i )
  {
    cchName = 260;
    v10 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
    if ( v10 == 259 )
    {
      cchName = 260;
      goto LABEL_42;
    }
    if ( v10 )
    {
      v22 = 230;
      goto LABEL_39;
    }
    v11 = phkResult;
    if ( phkResult )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v32);
      RegCloseKey(v11);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v32);
    }
    phkResult = 0;
    v12 = RegOpenKeyExW(hKey, Name, 0, 0x20119u, &phkResult);
    v6 = v12;
    if ( v12 > 0 )
      v6 = (unsigned __int16)v12 | 0x80070000;
    if ( (v6 & 0x80000000) != 0 )
      break;
    v13 = 0;
LABEL_12:
    cchName = 260;
    v10 = RegEnumKeyExW(phkResult, v13, SubKey, &cchName, 0, 0, 0, 0);
    if ( v10 != 259 )
    {
      if ( v10 )
      {
        v22 = 244;
      }
      else
      {
        v14 = v30;
        if ( v30 )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)v33);
          RegCloseKey(v14);
          wil::last_error_context::~last_error_context((wil::last_error_context *)v33);
        }
        v30 = 0;
        v10 = RegOpenKeyExW(phkResult, SubKey, 0, 0x20119u, &v30);
        if ( v10 )
        {
          v22 = 247;
        }
        else
        {
          for ( j = 0; ; ++j )
          {
            cbData = 0;
            cchName = 260;
            v10 = RegEnumValueW(v30, j, ValueName, &cchName, 0, 0, 0, &cbData);
            if ( v10 == 259 )
            {
              ++v13;
              goto LABEL_12;
            }
            if ( v10 )
              break;
            v16 = 2 * ((unsigned __int64)cbData >> 1);
            if ( !is_mul_ok((unsigned __int64)cbData >> 1, 2u) )
              v16 = -1;
            v17 = (BYTE *)operator new[](v16, (const struct std::nothrow_t *)std::nothrow);
            v18 = v17;
            if ( !v17 )
            {
              v6 = -2147024882;
              v8 = 261;
              goto LABEL_36;
            }
            *(_WORD *)v17 = 0;
            cchName = 260;
            v19 = RegEnumValueW(v30, j, ValueName, &cchName, 0, 0, v17, &cbData);
            if ( v19 )
            {
              v6 = wil::details::in1diag3::Return_Win32(
                     retaddr,
                     (void *)0x10B,
                     (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
                     (const char *)v19,
                     lpReserveda);
              operator delete(v18, v21);
              goto LABEL_42;
            }
            if ( wcsstr((const wchar_t *)v18, SubStr) )
            {
              *a3 = 1;
              operator delete(v18, v20);
              v6 = 0;
              goto LABEL_42;
            }
            operator delete(v18, v20);
          }
          v22 = 258;
        }
      }
LABEL_39:
      v23 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v22,
              (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
              (const char *)v10,
              lpReserved);
LABEL_40:
      v6 = v23;
      goto LABEL_42;
    }
  }
  v23 = -2147024894;
  if ( v6 == -2147024894 )
    goto LABEL_40;
  v8 = 234;
LABEL_36:
  v7 = v6;
LABEL_37:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\accountenthusiast.cpp",
    (const char *)v7,
    lpReserved);
LABEL_42:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v30);
  return v6;
}

```

## disassembly

```asm
0x180034548  mov     [rsp-8+arg_18], rbx
0x18003454d  push    rbp
0x18003454e  push    rsi
0x18003454f  push    rdi
0x180034550  push    r12
0x180034552  push    r13
0x180034554  push    r14
0x180034556  push    r15
0x180034558  lea     rbp, [rsp-5B0h]
0x180034560  sub     rsp, 6B0h
0x180034567  mov     rax, cs:__security_cookie
0x18003456e  xor     rax, rsp
0x180034571  mov     [rbp+5E0h+var_40], rax
0x180034578  xor     edi, edi
0x18003457a  mov     rax, rdx
0x18003457d  mov     r13, rcx
0x180034580  mov     [rsp+6E0h+var_690], rdi
0x180034585  mov     esi, 104h
0x18003458a  mov     [rsp+6E0h+phkResult], rdi
0x18003458f  mov     rcx, rax; lpSubKey
0x180034592  mov     [rsp+6E0h+cbData], edi
0x180034596  lea     rdx, [rsp+6E0h+hKey]
0x18003459b  mov     [r8], dil
0x18003459e  mov     r12, r8
0x1800345a1  mov     [rsp+6E0h+cchName], esi
0x1800345a5  mov     [rsp+6E0h+hKey], rdi
0x1800345aa  call    GetResourceManagerTrackedKeyForEnrollment
0x1800345af  mov     ebx, eax
0x1800345b1  test    eax, eax
0x1800345b3  jns     short loc_1800345C0
0x1800345b5  mov     r9d, eax
0x1800345b8  lea     edx, [rsi-28h]
0x1800345bb  jmp     loc_1800348B3
0x1800345c0  mov     ebx, edi
0x1800345c2  mov     r15d, edi
0x1800345c5  mov     rcx, [rsp+6E0h+hKey]; hKey
0x1800345ca  lea     r9, [rsp+6E0h+cchName]; lpcchName
0x1800345cf  mov     [rsp+6E0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x1800345d4  lea     r8, [rsp+6E0h+Name]; lpName
0x1800345d9  mov     [rsp+6E0h+lpcchClass], rdi; lpcchClass
0x1800345de  mov     edx, r15d; dwIndex
0x1800345e1  mov     [rsp+6E0h+lpClass], rdi; lpClass
0x1800345e6  mov     [rsp+6E0h+lpReserved], rdi; unsigned int
0x1800345eb  mov     [rsp+6E0h+cchName], esi
0x1800345ef  call    cs:__imp_RegEnumKeyExW
0x1800345f6  nop     dword ptr [rax+rax+00h]
0x1800345fb  cmp     eax, 103h
0x180034600  jz      loc_1800348E7
0x180034606  test    eax, eax
0x180034608  jnz     loc_1800348C8
0x18003460e  mov     rbx, [rsp+6E0h+phkResult]
0x180034613  test    rbx, rbx
0x180034616  jz      short loc_18003463B
0x180034618  lea     rcx, [rsp+6E0h+var_680]; this
0x18003461d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180034622  mov     rcx, rbx; hKey
0x180034625  call    cs:__imp_RegCloseKey
0x18003462c  nop     dword ptr [rax+rax+00h]
0x180034631  lea     rcx, [rsp+6E0h+var_680]; this
0x180034636  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003463b  mov     rcx, [rsp+6E0h+hKey]; hKey
0x180034640  lea     rax, [rsp+6E0h+phkResult]
0x180034645  mov     r9d, 20119h; samDesired
0x18003464b  mov     [rsp+6E0h+lpReserved], rax; int
0x180034650  xor     r8d, r8d; ulOptions
0x180034653  mov     [rsp+6E0h+phkResult], rdi
0x180034658  lea     rdx, [rsp+6E0h+Name]; lpSubKey
0x18003465d  call    cs:__imp_RegOpenKeyExW
0x180034664  nop     dword ptr [rax+rax+00h]
0x180034669  mov     ebx, eax
0x18003466b  test    eax, eax
0x18003466d  jle     short loc_180034678
0x18003466f  movzx   ebx, ax
0x180034672  or      ebx, 80070000h
0x180034678  test    ebx, ebx
0x18003467a  js      loc_1800348A2
0x180034680  mov     r14d, edi
0x180034683  mov     rcx, [rsp+6E0h+phkResult]; hKey
0x180034688  lea     r9, [rsp+6E0h+cchName]; lpcchName
0x18003468d  mov     [rsp+6E0h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180034692  lea     r8, [rbp+5E0h+SubKey]; lpName
0x180034699  mov     [rsp+6E0h+lpcchClass], rdi; lpcchClass
0x18003469e  mov     edx, r14d; dwIndex
0x1800346a1  mov     [rsp+6E0h+lpClass], rdi; lpClass
0x1800346a6  mov     [rsp+6E0h+lpReserved], rdi; lpReserved
0x1800346ab  mov     [rsp+6E0h+cchName], esi
0x1800346af  call    cs:__imp_RegEnumKeyExW
0x1800346b6  nop     dword ptr [rax+rax+00h]
0x1800346bb  cmp     eax, 103h
0x1800346c0  jz      loc_180034841
0x1800346c6  test    eax, eax
0x1800346c8  jnz     loc_18003489B
0x1800346ce  mov     rdi, [rsp+6E0h+var_690]
0x1800346d3  test    rdi, rdi
0x1800346d6  jz      short loc_1800346FB
0x1800346d8  lea     rcx, [rsp+6E0h+var_678]; this
0x1800346dd  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800346e2  mov     rcx, rdi; hKey
0x1800346e5  call    cs:__imp_RegCloseKey
0x1800346ec  nop     dword ptr [rax+rax+00h]
0x1800346f1  lea     rcx, [rsp+6E0h+var_678]; this
0x1800346f6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800346fb  mov     rcx, [rsp+6E0h+phkResult]; hKey
0x180034700  lea     rax, [rsp+6E0h+var_690]
0x180034705  xor     edi, edi
0x180034707  mov     [rsp+6E0h+lpReserved], rax; phkResult
0x18003470c  mov     r9d, 20119h; samDesired
0x180034712  mov     [rsp+6E0h+var_690], rdi
0x180034717  xor     r8d, r8d; ulOptions
0x18003471a  lea     rdx, [rbp+5E0h+SubKey]; lpSubKey
0x180034721  call    cs:__imp_RegOpenKeyExW
0x180034728  nop     dword ptr [rax+rax+00h]
0x18003472d  test    eax, eax
0x18003472f  jnz     loc_180034894
0x180034735  mov     esi, edi
0x180034737  mov     rcx, [rsp+6E0h+var_690]; hKey
0x18003473c  lea     rax, [rsp+6E0h+cbData]
0x180034741  mov     [rsp+6E0h+lpftLastWriteTime], rax; lpcbData
0x180034746  lea     r9, [rsp+6E0h+cchName]; lpcchValueName
0x18003474b  mov     [rsp+6E0h+lpcchClass], rdi; lpData
0x180034750  lea     r8, [rbp+5E0h+ValueName]; lpValueName
0x180034757  mov     [rsp+6E0h+lpClass], rdi; lpType
0x18003475c  mov     edx, esi; dwIndex
0x18003475e  mov     [rsp+6E0h+lpReserved], rdi; lpReserved
0x180034763  mov     [rsp+6E0h+cbData], edi
0x180034767  mov     [rsp+6E0h+cchName], 104h
0x18003476f  call    cs:__imp_RegEnumValueW
0x180034776  nop     dword ptr [rax+rax+00h]
0x18003477b  cmp     eax, 103h
0x180034780  jz      loc_180034834
0x180034786  test    eax, eax
0x180034788  jnz     loc_18003488D
0x18003478e  mov     ecx, [rsp+6E0h+cbData]
0x180034792  mov     eax, 2
0x180034797  shr     rcx, 1
0x18003479a  mul     rcx
0x18003479d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800347a4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800347ab  cmovb   rax, rcx
0x1800347af  mov     rcx, rax; unsigned __int64
0x1800347b2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800347b7  mov     rdi, rax
0x1800347ba  test    rax, rax
0x1800347bd  jz      loc_180034881
0x1800347c3  xor     ecx, ecx
0x1800347c5  lea     r9, [rsp+6E0h+cchName]; lpcchValueName
0x1800347ca  mov     [rax], cx
0x1800347cd  lea     r8, [rbp+5E0h+ValueName]; lpValueName
0x1800347d4  lea     rax, [rsp+6E0h+cbData]
0x1800347d9  mov     [rsp+6E0h+cchName], 104h
0x1800347e1  mov     [rsp+6E0h+lpftLastWriteTime], rax; lpcbData
0x1800347e6  mov     edx, esi; dwIndex
0x1800347e8  mov     [rsp+6E0h+lpcchClass], rdi; lpData
0x1800347ed  mov     [rsp+6E0h+lpClass], rcx; lpType
0x1800347f2  mov     [rsp+6E0h+lpReserved], rcx; unsigned int
0x1800347f7  mov     rcx, [rsp+6E0h+var_690]; hKey
0x1800347fc  call    cs:__imp_RegEnumValueW
0x180034803  nop     dword ptr [rax+rax+00h]
0x180034808  test    eax, eax
0x18003480a  jnz     short loc_18003485A
0x18003480c  mov     rdx, r13; SubStr
0x18003480f  mov     rcx, rdi; Str
0x180034812  call    cs:__imp_wcsstr
0x180034819  nop     dword ptr [rax+rax+00h]
0x18003481e  mov     rcx, rdi; void *
0x180034821  test    rax, rax
0x180034824  jnz     short loc_180034849
0x180034826  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003482b  xor     edi, edi
0x18003482d  inc     esi
0x18003482f  jmp     loc_180034737
0x180034834  mov     esi, 104h
0x180034839  inc     r14d
0x18003483c  jmp     loc_180034683
0x180034841  inc     r15d
0x180034844  jmp     loc_1800345C5
0x180034849  mov     byte ptr [r12], 1
0x18003484e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180034853  xor     ebx, ebx
0x180034855  jmp     loc_1800348EB
0x18003485a  mov     rcx, [rbp+5E8h]; this
0x180034861  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x180034868  mov     r9d, eax; char *
0x18003486b  mov     edx, 10Bh; void *
0x180034870  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180034875  mov     rcx, rdi; void *
0x180034878  mov     ebx, eax
0x18003487a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003487f  jmp     short loc_1800348EB
0x180034881  mov     ebx, 8007000Eh
0x180034886  mov     edx, 105h
0x18003488b  jmp     short loc_1800348B0
0x18003488d  mov     edx, 102h
0x180034892  jmp     short loc_1800348CD
0x180034894  mov     edx, 0F7h
0x180034899  jmp     short loc_1800348CD
0x18003489b  mov     edx, 0F4h
0x1800348a0  jmp     short loc_1800348CD
0x1800348a2  mov     eax, 80070002h
0x1800348a7  cmp     ebx, eax
0x1800348a9  jz      short loc_1800348E3
0x1800348ab  mov     edx, 0EAh; void *
0x1800348b0  mov     r9d, ebx; char *
0x1800348b3  mov     rcx, [rbp+5E8h]; this
0x1800348ba  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x1800348c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800348c6  jmp     short loc_1800348EB
0x1800348c8  mov     edx, 0E6h; void *
0x1800348cd  mov     rcx, [rbp+5E8h]; this
0x1800348d4  lea     r8, aShellcommonShe_10; "shellcommon\\shell\\settingshandlers\\w"...
0x1800348db  mov     r9d, eax; char *
0x1800348de  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800348e3  mov     ebx, eax
0x1800348e5  jmp     short loc_1800348EB
0x1800348e7  mov     [rsp+6E0h+cchName], esi
0x1800348eb  lea     rcx, [rsp+6E0h+hKey]
0x1800348f0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800348f5  lea     rcx, [rsp+6E0h+phkResult]
0x1800348fa  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800348ff  lea     rcx, [rsp+6E0h+var_690]
0x180034904  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180034909  mov     eax, ebx
0x18003490b  mov     rcx, [rbp+5E0h+var_40]
0x180034912  xor     rcx, rsp; StackCookie
0x180034915  call    __security_check_cookie
0x18003491a  mov     rbx, [rsp+6E0h+arg_18]
0x180034922  add     rsp, 6B0h
0x180034929  pop     r15
0x18003492b  pop     r14
0x18003492d  pop     r13
0x18003492f  pop     r12
0x180034931  pop     rdi
0x180034932  pop     rsi
0x180034933  pop     rbp
0x180034934  retn
```
