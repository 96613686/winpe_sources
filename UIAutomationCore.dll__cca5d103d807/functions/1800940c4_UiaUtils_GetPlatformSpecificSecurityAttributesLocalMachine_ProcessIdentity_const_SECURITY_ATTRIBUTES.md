# UiaUtils::GetPlatformSpecificSecurityAttributesLocalMachine(ProcessIdentity const &,_SECURITY_ATTRIBUTES *)

- ea: `0x1800940c4`
- end: `0x1800946b7`
- name: `?GetPlatformSpecificSecurityAttributesLocalMachine@UiaUtils@@SAJAEBUProcessIdentity@@PEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `1523`
- prototype: `__int64 __fastcall(const struct ProcessIdentity *, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18005d258`
- `0x180093cc8`

## callees

- `0x18002f580`
- `0x180093cfc`
- `0x1800940c4`
- `0x1800946c0`
- `0x1800948b8`
- `0x1800984e0`
- `0x180133418`
- `0x1801334b8`
- `0x1801345f0`
- `0x18014c3ec`
- `0x18015c18c`
- `0x1801632a4`
- `0x180164470`
- `0x1801b62e0`
- `0x1801e8320`
- `0x1801e8344`
- `0x1801e88a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800941f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094329`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094526`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009457b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094599`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800941f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094329`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094526`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009457b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180094599`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094181`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800942d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180094181`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800942d8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009415e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800941e2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180094235`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18009415e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800941e2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180094235`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800942bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180094343`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800943ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800943df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009449e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800944e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180094671`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800942bf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180094343`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800943ab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800943df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009449e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800944e8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180094671`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18009455f`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x18009455f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800942a1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18009445d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18009460e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800942a1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18009445d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18009460e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180094254`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180094254`

## string_xrefs

- `0x18009438f`: `onecore\windows\accessibletech\uiautomationcore\uiautil.cpp`
- `0x1800943c3`: `onecore\windows\accessibletech\uiautomationcore\uiautil.cpp`
- `0x1800944cc`: `onecore\windows\accessibletech\uiautomationcore\uiautil.cpp`
- `0x180094624`: `onecore\windows\accessibletech\uiautomationcore\uiautil.cpp`
- `0x1800943f7`: `onecore\windows\accessibletech\common\basicuiautils.cpp`
- `0x180094696`: `onecore\windows\accessibletech\common\basicuiautils.cpp`
- `0x1800944f8`: `Could not open the process token`
- `0x180094501`: `OpenProcessTokenHelper`
- `0x180094651`: `GetTokenInformation`
- `0x180094472`: `ConvertStringSecurityDescriptorToSecurityDescriptor`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UiaUtils::GetPlatformSpecificSecurityAttributesLocalMachine(
        const struct ProcessIdentity *a1,
        struct _SECURITY_ATTRIBUTES *a2)
{
  int v4; // edi
  void *v5; // rbx
  BOOL v6; // eax
  int v7; // edx
  unsigned int v8; // ecx
  BOOL v9; // r14d
  HLOCAL v10; // rbx
  void *v11; // rsi
  const char *v12; // r9
  signed int v13; // eax
  unsigned int v14; // ebx
  PSID *v15; // rdi
  int v16; // eax
  __int64 result; // rax
  signed int v18; // eax
  PSID *v19; // rcx
  int ObjectPathForProcess; // eax
  unsigned int v21; // ebx
  int v22; // eax
  unsigned int v23; // ebx
  HLOCAL v24; // rbx
  unsigned int v25; // ebx
  int v26; // ebx
  signed int v27; // eax
  signed int v28; // eax
  signed int v29; // eax
  unsigned int LastError; // ebx
  int ReturnLength; // [rsp+20h] [rbp-678h]
  int ReturnLengtha; // [rsp+20h] [rbp-678h]
  DWORD TokenInformation; // [rsp+30h] [rbp-668h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-660h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-658h] BYREF
  DWORD v36[2]; // [rsp+48h] [rbp-650h] BYREF
  WCHAR StringSecurityDescriptor[256]; // [rsp+50h] [rbp-648h] BYREF
  wchar_t pszDest[264]; // [rsp+250h] [rbp-448h] BYREF
  unsigned __int16 v39[264]; // [rsp+460h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+698h] [rbp+0h]

  try
  {
    hMem = 0;
    if ( !BasicUiaUtils::s_isDesktopDetermined )
    {
      BasicUiaUtils::s_isDesktop = GetSystemMetrics(6144) != 0;
      BasicUiaUtils::s_isDesktopDetermined = 1;
    }
    if ( !BasicUiaUtils::s_isDesktop && !BasicUiaUtils::IsWinPE() && byte_1803A1918 )
    {
      wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &hMem,
        0);
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
              L"D:(A;;FRFWGA;;;WD)(A;;FRFWGA;;;S-1-15-2-1)",
              1u,
              &hMem,
              0) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x591,
                      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautil.cpp",
                      v12);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
        return LastError;
      }
LABEL_27:
      a2->nLength = 24;
      a2->lpSecurityDescriptor = hMem;
      a2->bInheritHandle = 0;
      return 0;
    }
    v4 = *(_DWORD *)a1;
    v5 = OpenProcessTokenHelper((unsigned int)a1, (int)a2, *(_DWORD *)a1);
    SecurityDescriptor = v5;
    if ( v5 )
    {
      TokenInformation = 0;
      v36[0] = 0;
      v6 = GetTokenInformation(v5, TokenIsAppContainer, &TokenInformation, 4u, v36);
      v9 = TokenInformation != 0;
      if ( v6 )
      {
        if ( v5 != (void *)-1LL )
          CloseHandle(v5);
LABEL_9:
        if ( !v9 )
          goto LABEL_10;
        ObjectPathForProcess = GetObjectPathForProcess(*(_DWORD *)a1, 0x104u, v39, 0x104u, pszDest);
        v21 = ObjectPathForProcess;
        if ( ObjectPathForProcess >= 0 )
        {
          v22 = StringCchPrintfW(StringSecurityDescriptor, 0x100u, L"D:(A;;FRFWGA;;;WD)(A;;FRFWGA;;;%ws)", pszDest);
          v23 = v22;
          if ( v22 >= 0 )
          {
            v24 = hMem;
            if ( hMem )
            {
              wil::last_error_context::last_error_context((wil::last_error_context *)&SecurityDescriptor);
              LocalFree(v24);
              wil::last_error_context::~last_error_context((wil::last_error_context *)&SecurityDescriptor);
            }
            hMem = 0;
            if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &hMem, 0) )
            {
              v25 = Error::Win32Error(L"ConvertStringSecurityDescriptorToSecurityDescriptor", L"Connecting to server");
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
              return v25;
            }
            goto LABEL_27;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x5A0,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautil.cpp",
            (const char *)(unsigned int)v22,
            ReturnLengtha);
          if ( hMem )
            LocalFree(hMem);
          return v23;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x59A,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautil.cpp",
            (const char *)(unsigned int)ObjectPathForProcess,
            ReturnLengtha);
          if ( hMem )
            LocalFree(hMem);
          return v21;
        }
      }
      v26 = Error::ProcessWin32Error(L"GetTokenInformation", v4, L"Checking if process is low box");
    }
    else
    {
      v9 = 0;
      v26 = Error::ProcessWin32Error(L"OpenProcessTokenHelper", v4, L"Could not open the process token");
    }
    AutoCleanupInfo<void *>::SafeRelease(&SecurityDescriptor);
    if ( v26 < 0 )
    {
LABEL_10:
      v10 = hMem;
      if ( hMem )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&SecurityDescriptor);
        LocalFree(v10);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&SecurityDescriptor);
      }
      hMem = 0;
      v11 = OpenProcessTokenHelper(v8, v7, *(_DWORD *)a1);
      SecurityDescriptor = v11;
      if ( !v11 )
      {
        v27 = GetLastError();
        v14 = v27;
        if ( v27 > 0 )
          v14 = (unsigned __int16)v27 | 0x80070000;
        if ( v14 == -2147024809 )
          v14 = -2147220991;
        AutoCleanupInfo<void *>::SafeRelease(&SecurityDescriptor);
        goto LABEL_26;
      }
      TokenInformation = 0;
      if ( GetTokenInformation(v11, TokenIntegrityLevel, 0, 0, &TokenInformation) )
        goto LABEL_23;
      v13 = GetLastError();
      v14 = v13;
      if ( v13 != 122 )
      {
        if ( v13 > 0 )
          v14 = (unsigned __int16)v13 | 0x80070000;
        goto LABEL_24;
      }
      v15 = (PSID *)operator new[](TokenInformation, (const struct std::nothrow_t *)std::nothrow);
      if ( v15 )
      {
        if ( GetTokenInformation(v11, TokenIntegrityLevel, v15, TokenInformation, &TokenInformation) )
        {
          *(_QWORD *)v36 = 0;
          if ( ConvertSidToStringSidW(*v15, (LPWSTR *)v36) )
          {
            v16 = StringCchPrintfW(
                    StringSecurityDescriptor,
                    0x100u,
                    L"S:(ML;;NW;;;%ws)D:(A;;FRFWGA;;;WD)",
                    *(_QWORD *)v36);
            v14 = v16;
            if ( v16 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x120,
                (unsigned int)"onecore\\windows\\accessibletech\\common\\basicuiautils.cpp",
                (const char *)(unsigned int)v16,
                ReturnLength);
            }
            else
            {
              SecurityDescriptor = 0;
              if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
                     StringSecurityDescriptor,
                     1u,
                     &SecurityDescriptor,
                     0) )
              {
                hMem = SecurityDescriptor;
                if ( *(_QWORD *)v36 )
                  LocalFree(*(HLOCAL *)v36);
                operator delete(v15);
LABEL_23:
                v14 = 0;
                goto LABEL_24;
              }
              v18 = GetLastError();
              v14 = v18;
              if ( v18 > 0 )
                v14 = (unsigned __int16)v18 | 0x80070000;
            }
            if ( *(_QWORD *)v36 )
              LocalFree(*(HLOCAL *)v36);
          }
          else
          {
            v29 = GetLastError();
            v14 = v29;
            if ( v29 > 0 )
              v14 = (unsigned __int16)v29 | 0x80070000;
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v36);
          }
        }
        else
        {
          v28 = GetLastError();
          v14 = v28;
          if ( v28 > 0 )
            v14 = (unsigned __int16)v28 | 0x80070000;
        }
        v19 = v15;
      }
      else
      {
        v14 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x10B,
          (unsigned int)"onecore\\windows\\accessibletech\\common\\basicuiautils.cpp",
          (const char *)0x8007000ELL,
          ReturnLength);
        v19 = 0;
      }
      operator delete(v19);
LABEL_24:
      if ( v11 != (void *)-1LL )
        CloseHandle(v11);
LABEL_26:
      if ( (v14 & 0x80000000) == 0 )
        goto LABEL_27;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5A9,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautil.cpp",
        (const char *)v14,
        ReturnLength);
      if ( hMem )
        LocalFree(hMem);
      return v14;
    }
    goto LABEL_9;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x5B3,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uiautil.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x1800940c4  mov     [rsp+arg_10], rbx
0x1800940c9  mov     [rsp+arg_18], rsi
0x1800940ce  push    rdi
0x1800940cf  push    r14
0x1800940d1  push    r15
0x1800940d3  sub     rsp, 680h
0x1800940da  mov     rax, cs:__security_cookie
0x1800940e1  xor     rax, rsp
0x1800940e4  mov     [rsp+698h+var_28], rax
0x1800940ec  mov     r15, rdx
0x1800940ef  mov     rsi, rcx
0x1800940f2  mov     [rsp+698h+hMem], 0
0x1800940fb  mov     al, cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x180094101  nop
0x180094102  test    al, al
0x180094104  jz      loc_18009455A
0x18009410a  cmp     cs:?s_isDesktop@BasicUiaUtils@@2_NA, 0; bool BasicUiaUtils::s_isDesktop
0x180094111  jz      loc_1800945D3
0x180094117  mov     edi, [rsi]
0x180094119  mov     r8d, edi; unsigned int
0x18009411c  call    ?OpenProcessTokenHelper@@YAPEAXKHK@Z; OpenProcessTokenHelper(ulong,int,ulong)
0x180094121  mov     rbx, rax
0x180094124  mov     [rsp+698h+SecurityDescriptor], rax
0x180094129  test    rax, rax
0x18009412c  jz      loc_1800944F5
0x180094132  mov     [rsp+698h+TokenInformation], 0
0x18009413a  mov     [rsp+698h+var_650], 0
0x180094142  lea     rax, [rsp+698h+var_650]
0x180094147  mov     qword ptr [rsp+698h+ReturnLength], rax; ReturnLength
0x18009414c  mov     r9d, 4; TokenInformationLength
0x180094152  lea     r8, [rsp+698h+TokenInformation]; TokenInformation
0x180094157  lea     edx, [r9+19h]; TokenInformationClass
0x18009415b  mov     rcx, rbx; TokenHandle
0x18009415e  call    cs:__imp_GetTokenInformation
0x180094164  xor     r14d, r14d
0x180094167  cmp     [rsp+698h+TokenInformation], r14d
0x18009416c  setnz   r14b
0x180094170  test    eax, eax
0x180094172  jz      loc_180094648
0x180094178  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18009417c  jz      short loc_180094187
0x18009417e  mov     rcx, rbx; hObject
0x180094181  call    cs:__imp_CloseHandle
0x180094187  test    r14d, r14d
0x18009418a  jnz     loc_180094356
0x180094190  mov     rbx, [rsp+698h+hMem]
0x180094195  test    rbx, rbx
0x180094198  jnz     loc_180094491
0x18009419e  mov     [rsp+698h+hMem], 0
0x1800941a7  mov     r8d, [rsi]; unsigned int
0x1800941aa  call    ?OpenProcessTokenHelper@@YAPEAXKHK@Z; OpenProcessTokenHelper(ulong,int,ulong)
0x1800941af  mov     rsi, rax
0x1800941b2  mov     [rsp+698h+SecurityDescriptor], rax
0x1800941b7  test    rax, rax
0x1800941ba  jz      loc_180094526
0x1800941c0  mov     [rsp+698h+TokenInformation], 0
0x1800941c8  lea     rax, [rsp+698h+TokenInformation]
0x1800941cd  mov     qword ptr [rsp+698h+ReturnLength], rax; int
0x1800941d2  xor     r9d, r9d; TokenInformationLength
0x1800941d5  xor     r8d, r8d; TokenInformation
0x1800941d8  lea     r14d, [r9+19h]
0x1800941dc  mov     edx, r14d; TokenInformationClass
0x1800941df  mov     rcx, rsi; TokenHandle
0x1800941e2  call    cs:__imp_GetTokenInformation
0x1800941e8  test    eax, eax
0x1800941ea  jnz     loc_1800942CD
0x1800941f0  call    cs:__imp_GetLastError
0x1800941f6  mov     ebx, eax
0x1800941f8  cmp     eax, 7Ah ; 'z'
0x1800941fb  jnz     loc_1800945BD
0x180094201  mov     ecx, [rsp+698h+TokenInformation]; unsigned __int64
0x180094205  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009420c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180094211  mov     rdi, rax
0x180094214  test    rax, rax
0x180094217  jz      loc_180094686
0x18009421d  lea     rax, [rsp+698h+TokenInformation]
0x180094222  mov     qword ptr [rsp+698h+ReturnLength], rax; int
0x180094227  mov     r9d, [rsp+698h+TokenInformation]; TokenInformationLength
0x18009422c  mov     r8, rdi; TokenInformation
0x18009422f  mov     edx, r14d; TokenInformationClass
0x180094232  mov     rcx, rsi; TokenHandle
0x180094235  call    cs:__imp_GetTokenInformation
0x18009423b  test    eax, eax
0x18009423d  jz      loc_18009457B
0x180094243  mov     qword ptr [rsp+698h+var_650], 0
0x18009424c  lea     rdx, [rsp+698h+var_650]; StringSid
0x180094251  mov     rcx, [rdi]; Sid
0x180094254  call    cs:__imp_ConvertSidToStringSidW
0x18009425a  test    eax, eax
0x18009425c  jz      loc_180094599
0x180094262  mov     r9, qword ptr [rsp+698h+var_650]
0x180094267  lea     r8, aSMlNwWsDAFrfwg; "S:(ML;;NW;;;%ws)D:(A;;FRFWGA;;;WD)"
0x18009426e  mov     edx, 100h; unsigned __int64
0x180094273  lea     rcx, [rsp+698h+StringSecurityDescriptor]; unsigned __int16 *
0x180094278  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009427d  mov     ebx, eax
0x18009427f  test    eax, eax
0x180094281  js      loc_1800943EC
0x180094287  mov     [rsp+698h+SecurityDescriptor], 0
0x180094290  xor     r9d, r9d; SecurityDescriptorSize
0x180094293  lea     r8, [rsp+698h+SecurityDescriptor]; SecurityDescriptor
0x180094298  lea     edx, [r14-18h]; StringSDRevision
0x18009429c  lea     rcx, [rsp+698h+StringSecurityDescriptor]; StringSecurityDescriptor
0x1800942a1  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800942a7  test    eax, eax
0x1800942a9  jz      short loc_180094329
0x1800942ab  mov     rax, [rsp+698h+SecurityDescriptor]
0x1800942b0  mov     [rsp+698h+hMem], rax
0x1800942b5  mov     rcx, qword ptr [rsp+698h+var_650]; hMem
0x1800942ba  test    rcx, rcx
0x1800942bd  jz      short loc_1800942C5
0x1800942bf  call    cs:__imp_LocalFree
0x1800942c5  mov     rcx, rdi; Block
0x1800942c8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800942cd  xor     ebx, ebx
0x1800942cf  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800942d3  jz      short loc_1800942DE
0x1800942d5  mov     rcx, rsi; hObject
0x1800942d8  call    cs:__imp_CloseHandle
0x1800942de  test    ebx, ebx
0x1800942e0  js      loc_1800943B8
0x1800942e6  mov     dword ptr [r15], 18h
0x1800942ed  mov     rax, [rsp+698h+hMem]
0x1800942f2  mov     [r15+8], rax
0x1800942f6  mov     dword ptr [r15+10h], 0
0x1800942fe  xor     eax, eax
0x180094300  mov     rcx, [rsp+698h+var_28]
0x180094308  xor     rcx, rsp; StackCookie
0x18009430b  call    __security_check_cookie
0x180094310  lea     r11, [rsp+698h+var_18]
0x180094318  mov     rbx, [r11+30h]
0x18009431c  mov     rsi, [r11+38h]
0x180094320  mov     rsp, r11
0x180094323  pop     r15
0x180094325  pop     r14
0x180094327  pop     rdi
0x180094328  retn
0x180094329  call    cs:__imp_GetLastError
0x18009432f  mov     ebx, eax
0x180094331  test    eax, eax
0x180094333  jg      loc_1800944B3
0x180094339  mov     rcx, qword ptr [rsp+698h+var_650]; hMem
0x18009433e  test    rcx, rcx
0x180094341  jz      short loc_180094349
0x180094343  call    cs:__imp_LocalFree
0x180094349  mov     rcx, rdi; Block
0x18009434c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180094351  jmp     loc_1800942CF
0x180094356  lea     rax, [rsp+698h+pszDest]
0x18009435e  mov     qword ptr [rsp+698h+ReturnLength], rax; int
0x180094363  mov     edx, 104h; unsigned int
0x180094368  mov     r9d, edx; cchDest
0x18009436b  lea     r8, [rsp+698h+var_238]; unsigned __int16 *
0x180094373  mov     ecx, [rsi]; unsigned int
0x180094375  call    ?GetObjectPathForProcess@@YAJKKPEAGK0@Z; GetObjectPathForProcess(ulong,ulong,ushort *,ulong,ushort *)
0x18009437a  mov     ebx, eax
0x18009437c  test    eax, eax
0x18009437e  jns     loc_18009440D
0x180094384  mov     rcx, [rsp+698h]; this
0x18009438c  mov     r9d, eax; char *
0x18009438f  lea     r8, aOnecoreWindows_110; "onecore\\windows\\accessibletech\\uiaut"...
0x180094396  mov     edx, 59Ah; void *
0x18009439b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800943a0  nop
0x1800943a1  mov     rcx, [rsp+698h+hMem]; hMem
0x1800943a6  test    rcx, rcx
0x1800943a9  jz      short loc_1800943B1
0x1800943ab  call    cs:__imp_LocalFree
0x1800943b1  mov     eax, ebx
0x1800943b3  jmp     loc_180094300
0x1800943b8  mov     rcx, [rsp+698h]; this
0x1800943c0  mov     r9d, ebx; char *
0x1800943c3  lea     r8, aOnecoreWindows_110; "onecore\\windows\\accessibletech\\uiaut"...
0x1800943ca  mov     edx, 5A9h; void *
0x1800943cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800943d4  nop
0x1800943d5  mov     rcx, [rsp+698h+hMem]; hMem
0x1800943da  test    rcx, rcx
0x1800943dd  jz      short loc_1800943E5
0x1800943df  call    cs:__imp_LocalFree
0x1800943e5  mov     eax, ebx
0x1800943e7  jmp     loc_180094300
0x1800943ec  mov     rcx, [rsp+698h]; this
0x1800943f4  mov     r9d, eax; char *
0x1800943f7  lea     r8, aOnecoreWindows_70; "onecore\\windows\\accessibletech\\commo"...
0x1800943fe  mov     edx, 120h; void *
0x180094403  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094408  jmp     loc_180094339
0x18009440d  lea     r9, [rsp+698h+pszDest]
0x180094415  lea     r8, aDAFrfwgaWdAFrf_0; "D:(A;;FRFWGA;;;WD)(A;;FRFWGA;;;%ws)"
0x18009441c  mov     edx, 100h; unsigned __int64
0x180094421  lea     rcx, [rsp+698h+StringSecurityDescriptor]; unsigned __int16 *
0x180094426  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18009442b  mov     ebx, eax
0x18009442d  test    eax, eax
0x18009442f  js      loc_1800944C1
0x180094435  mov     rbx, [rsp+698h+hMem]
0x18009443a  test    rbx, rbx
0x18009443d  jnz     loc_180094664
0x180094443  mov     [rsp+698h+hMem], 0
0x18009444c  xor     r9d, r9d; SecurityDescriptorSize
0x18009444f  lea     r8, [rsp+698h+hMem]; SecurityDescriptor
0x180094454  lea     edx, [r9+1]; StringSDRevision
0x180094458  lea     rcx, [rsp+698h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18009445d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180094463  test    eax, eax
0x180094465  jnz     loc_1800942E6
0x18009446b  lea     rdx, aConnectingToSe; "Connecting to server"
0x180094472  lea     rcx, aConvertstrings_0; "ConvertStringSecurityDescriptorToSecuri"...
0x180094479  call    ?Win32Error@Error@@SAJPEBG0@Z; Error::Win32Error(ushort const *,ushort const *)
0x18009447e  mov     ebx, eax
0x180094480  lea     rcx, [rsp+698h+hMem]
0x180094485  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009448a  mov     eax, ebx
0x18009448c  jmp     loc_180094300
0x180094491  lea     rcx, [rsp+698h+SecurityDescriptor]; this
0x180094496  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18009449b  mov     rcx, rbx; hMem
0x18009449e  call    cs:__imp_LocalFree
0x1800944a4  lea     rcx, [rsp+698h+SecurityDescriptor]; this
0x1800944a9  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800944ae  jmp     loc_18009419E
0x1800944b3  movzx   ebx, ax
0x1800944b6  or      ebx, 80070000h
0x1800944bc  jmp     loc_180094339
0x1800944c1  mov     rcx, [rsp+698h]; this
0x1800944c9  mov     r9d, ebx; char *
0x1800944cc  lea     r8, aOnecoreWindows_110; "onecore\\windows\\accessibletech\\uiaut"...
0x1800944d3  mov     edx, 5A0h; void *
0x1800944d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800944dd  nop
0x1800944de  mov     rcx, [rsp+698h+hMem]; hMem
0x1800944e3  test    rcx, rcx
0x1800944e6  jz      short loc_1800944EE
0x1800944e8  call    cs:__imp_LocalFree
0x1800944ee  mov     eax, ebx
0x1800944f0  jmp     loc_180094300
0x1800944f5  xor     r14d, r14d
0x1800944f8  lea     r8, aCouldNotOpenTh; "Could not open the process token"
0x1800944ff  mov     edx, edi; int
0x180094501  lea     rcx, aOpenprocesstok; "OpenProcessTokenHelper"
0x180094508  call    ?ProcessWin32Error@Error@@SAJPEBGH0@Z; Error::ProcessWin32Error(ushort const *,int,ushort const *)
0x18009450d  mov     ebx, eax
0x18009450f  lea     rcx, [rsp+698h+SecurityDescriptor]
0x180094514  call    ?SafeRelease@?$AutoCleanupInfo@PEAX@@SAXAEAPEAX@Z; AutoCleanupInfo<void *>::SafeRelease(void * &)
0x180094519  test    ebx, ebx
0x18009451b  jns     loc_180094187
0x180094521  jmp     loc_180094190
0x180094526  call    cs:__imp_GetLastError
0x18009452c  mov     ebx, eax
0x18009452e  test    eax, eax
0x180094530  jg      short loc_18009454F
0x180094532  mov     eax, 80040201h
0x180094537  cmp     ebx, 80070057h
0x18009453d  cmovz   ebx, eax
0x180094540  lea     rcx, [rsp+698h+SecurityDescriptor]
0x180094545  call    ?SafeRelease@?$AutoCleanupInfo@PEAX@@SAXAEAPEAX@Z; AutoCleanupInfo<void *>::SafeRelease(void * &)
0x18009454a  jmp     loc_1800942DE
0x18009454f  movzx   ebx, ax
0x180094552  or      ebx, 80070000h
0x180094558  jmp     short loc_180094532
0x18009455a  mov     ecx, 1800h; nIndex
0x18009455f  call    cs:__imp_GetSystemMetrics
0x180094565  test    eax, eax
0x180094567  setnz   cs:?s_isDesktop@BasicUiaUtils@@2_NA; bool BasicUiaUtils::s_isDesktop
0x18009456e  nop
0x18009456f  mov     cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A, 1; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x180094576  jmp     loc_18009410A
0x18009457b  call    cs:__imp_GetLastError
0x180094581  mov     ebx, eax
0x180094583  test    eax, eax
0x180094585  jle     loc_180094349
0x18009458b  movzx   ebx, ax
0x18009458e  or      ebx, 80070000h
0x180094594  jmp     loc_180094349
0x180094599  call    cs:__imp_GetLastError
0x18009459f  mov     ebx, eax
0x1800945a1  test    eax, eax
0x1800945a3  jle     short loc_1800945AE
0x1800945a5  movzx   ebx, ax
0x1800945a8  or      ebx, 80070000h
0x1800945ae  lea     rcx, [rsp+698h+var_650]
0x1800945b3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800945b8  jmp     loc_180094349
0x1800945bd  test    eax, eax
0x1800945bf  jle     loc_1800942CF
0x1800945c5  movzx   ebx, ax
0x1800945c8  or      ebx, 80070000h
0x1800945ce  jmp     loc_1800942CF
0x1800945d3  call    ?IsWinPE@BasicUiaUtils@@SA_NXZ; BasicUiaUtils::IsWinPE(void)
0x1800945d8  test    al, al
0x1800945da  jnz     loc_180094117
0x1800945e0  mov     al, cs:byte_1803A1918
0x1800945e6  nop
0x1800945e7  test    al, al
0x1800945e9  jz      loc_180094117
0x1800945ef  xor     edx, edx
0x1800945f1  lea     rcx, [rsp+698h+hMem]
0x1800945f6  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
  ... truncated ...
```
