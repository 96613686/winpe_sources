# SystemSettings::SecureAssessment::GetTemporarySingleAppSid(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)

- ea: `0x14006aebc`
- end: `0x14006b129`
- name: `?GetTemporarySingleAppSid@SecureAssessment@SystemSettings@@YAJAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z`
- size: `621`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14006a198`

## callees

- `0x140005f54`
- `0x140005f84`
- `0x14000ed38`
- `0x14001f3d4`
- `0x14001f3f8`
- `0x14003ff9c`
- `0x1400407b0`
- `0x140069eb0`
- `0x14006aebc`
- `0x14006bcd4`

## import_xrefs

- `KERNEL32!RegOpenKeyExW` at `0x14006af54`
- `KERNEL32!RegOpenKeyExW` at `0x14006af54`
- `KERNEL32!RegQueryValueExW` at `0x14006afa4`
- `KERNEL32!RegQueryValueExW` at `0x14006b057`
- `KERNEL32!RegQueryValueExW` at `0x14006afa4`
- `KERNEL32!RegQueryValueExW` at `0x14006b057`

## string_xrefs

- `0x14006af99`: `TemporaryUserSid`
- `0x14006b04c`: `TemporaryUserSid`
- `0x14006af36`: `Software\Microsoft\Windows\AssignedAccessSettingsPage`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SystemSettings::SecureAssessment::GetTemporarySingleAppSid(__int64 a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  const WCHAR *v5; // rdx
  __int64 v6; // rcx
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 v9; // rdx
  unsigned int v10; // eax
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rbx
  BYTE *v14; // rdi
  unsigned int v15; // eax
  const struct std::nothrow_t *v16; // rdx
  int v17; // eax
  unsigned int v18; // r14d
  const struct std::nothrow_t *v19; // rdx
  const struct std::nothrow_t *v21; // rdx
  int phkResult; // [rsp+20h] [rbp-30h]
  unsigned int phkResulta; // [rsp+20h] [rbp-30h]
  unsigned int phkResultb; // [rsp+20h] [rbp-30h]
  HKEY *p_hKey; // [rsp+30h] [rbp-20h] BYREF
  HKEY v26; // [rsp+38h] [rbp-18h] BYREF
  char v27; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  DWORD cbData; // [rsp+88h] [rbp+38h] BYREF
  DWORD Type; // [rsp+90h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+48h] BYREF

  v2 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(a1, 0);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\SecureAssessmentAdminFlowHandler.h",
      (const char *)(unsigned int)v2,
      phkResult);
    return v3;
  }
  StringCchCopyNW(*(STRSAFE_LPWSTR *)a1, 1u, &Data, 0);
  *(_QWORD *)(a1 + 8) = 0;
  hKey = 0;
  v26 = 0;
  v27 = 1;
  p_hKey = &hKey;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnblockingTestTakingInAdminless>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_UnblockingTestTakingInAdminless>::GetImpl'::`2'::impl,
                          v4) )
  {
    v5 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\SecureAssessment";
    v6 = -2147483646;
  }
  else
  {
    v5 = L"Software\\Microsoft\\Windows\\AssignedAccessSettingsPage";
    v6 = -2147483647;
  }
  v7 = RegOpenKeyExW((HKEY)v6, v5, 0, 0x20019u, &v26);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
  if ( v7 == 2 )
    goto LABEL_23;
  if ( !v7 )
  {
    cbData = 0;
    Type = 0;
    v10 = RegQueryValueExW(hKey, L"TemporaryUserSid", 0, &Type, 0, &cbData);
    if ( v10 != 2 )
    {
      if ( v10 )
      {
        v8 = (const char *)v10;
        v9 = 89;
        goto LABEL_11;
      }
      if ( cbData && Type == 1 )
      {
        v11 = (unsigned __int64)cbData >> 1;
        v12 = 2 * v11;
        v13 = -1;
        if ( !is_mul_ok(v11, 2u) )
          v12 = -1;
        v14 = (BYTE *)operator new[](v12, (const struct std::nothrow_t *)std::nothrow);
        if ( !v14 )
        {
          v3 = -2147024882;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x61,
            (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\SecureAssessmentAdminFlowHandler.h",
            (const char *)0x8007000ELL,
            phkResulta);
          goto LABEL_25;
        }
        v15 = RegQueryValueExW(hKey, L"TemporaryUserSid", 0, 0, v14, &cbData);
        if ( v15 )
        {
          v3 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x67,
                 (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\SecureAssessmentAd"
                               "minFlowHandler.h",
                 (const char *)v15,
                 phkResultb);
          operator delete(v14, v16);
          goto LABEL_25;
        }
        do
          ++v13;
        while ( *(_WORD *)&v14[2 * v13] );
        v17 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCapacity(
                a1,
                v13);
        v18 = v17;
        if ( v17 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x68,
            (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\SecureAssessmentAdminFlowHandler.h",
            (const char *)(unsigned int)v17,
            phkResultb);
          operator delete(v14, v21);
          v3 = v18;
          goto LABEL_25;
        }
        StringCchCopyNW(*(STRSAFE_LPWSTR *)a1, v13 + 1, (STRSAFE_PCNZWCH)v14, v13);
        *(_QWORD *)(a1 + 8) = v13;
        operator delete(v14, v19);
      }
    }
LABEL_23:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return 0;
  }
  v8 = (const char *)v7;
  v9 = 80;
LABEL_11:
  v3 = wil::details::in1diag3::Return_Win32(
         retaddr,
         (void *)v9,
         (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\SecureAssessmentAdminFlowHandler.h",
         v8,
         phkResulta);
LABEL_25:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v3;
}

```

## disassembly

```asm
0x14006aebc  mov     [rsp-28h+arg_0], rbx
0x14006aec1  push    rbp
0x14006aec2  push    rsi
0x14006aec3  push    rdi
0x14006aec4  push    r14
0x14006aec6  push    r15
0x14006aec8  mov     rbp, rsp
0x14006aecb  sub     rsp, 50h
0x14006aecf  mov     rsi, rcx
0x14006aed2  xor     edx, edx
0x14006aed4  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x14006aed9  mov     ebx, eax
0x14006aedb  xor     r15d, r15d
0x14006aede  test    eax, eax
0x14006aee0  js      loc_14006B0FB
0x14006aee6  xor     r9d, r9d; cchToCopy
0x14006aee9  lea     r8, Data; pszSrc
0x14006aef0  lea     edx, [r15+1]; cchDest
0x14006aef4  mov     rcx, [rsi]; pszDest
0x14006aef7  call    StringCchCopyNW
0x14006aefc  mov     [rsi+8], r15
0x14006af00  mov     [rbp+hKey], r15
0x14006af04  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UnblockingTestTakingInAdminless@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UnblockingTestTakingInAdminless@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnblockingTestTakingInAdminless> `wil::Feature<__WilFeatureTraits_Feature_UnblockingTestTakingInAdminless>::GetImpl(void)'::`2'::impl
0x14006af0b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UnblockingTestTakingInAdminless@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UnblockingTestTakingInAdminless>::__private_IsEnabled(void)
0x14006af10  mov     [rbp+var_18], r15
0x14006af14  mov     [rbp+var_10], 1
0x14006af18  mov     r9d, 20019h; samDesired
0x14006af1e  xor     r8d, r8d; ulOptions
0x14006af21  test    al, al
0x14006af23  lea     rax, [rbp+hKey]
0x14006af27  mov     [rbp+var_20], rax
0x14006af2b  lea     rax, [rbp+var_18]
0x14006af2f  mov     [rsp+50h+phkResult], rax; phkResult
0x14006af34  jnz     short loc_14006AF46
0x14006af36  lea     rdx, ?c_temporaryStoreKeyPath@@3QBGB; "Software\\Microsoft\\Windows\\AssignedA"...
0x14006af3d  mov     rcx, 0FFFFFFFF80000001h
0x14006af44  jmp     short loc_14006AF54
0x14006af46  lea     rdx, ?c_temporaryStoreKeyPathAdminless@@3QBGB; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14006af4d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14006af54  call    cs:__imp_RegOpenKeyExW
0x14006af5a  mov     ebx, eax
0x14006af5c  lea     rcx, [rbp+var_20]
0x14006af60  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x14006af65  cmp     ebx, 2
0x14006af68  jz      loc_14006B0C0
0x14006af6e  test    ebx, ebx
0x14006af70  jz      short loc_14006AF7C
0x14006af72  mov     r9d, ebx
0x14006af75  mov     edx, 50h ; 'P'
0x14006af7a  jmp     short loc_14006AFBF
0x14006af7c  mov     [rbp+cbData], r15d
0x14006af80  mov     [rbp+Type], r15d
0x14006af84  lea     rax, [rbp+cbData]
0x14006af88  mov     [rsp+50h+lpcbData], rax; lpcbData
0x14006af8d  mov     [rsp+50h+phkResult], r15; int
0x14006af92  lea     r9, [rbp+Type]; lpType
0x14006af96  xor     r8d, r8d; lpReserved
0x14006af99  lea     rdx, ?c_temporaryStoreUserSidValueName@@3QBGB; "TemporaryUserSid"
0x14006afa0  mov     rcx, [rbp+hKey]; hKey
0x14006afa4  call    cs:__imp_RegQueryValueExW
0x14006afaa  cmp     eax, 2
0x14006afad  jz      loc_14006B0C0
0x14006afb3  test    eax, eax
0x14006afb5  jz      short loc_14006AFD6
0x14006afb7  mov     r9d, eax; char *
0x14006afba  mov     edx, 59h ; 'Y'; void *
0x14006afbf  lea     r8, aAdminEduSecure_1; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006afc6  mov     rcx, [rbp+28h]; this
0x14006afca  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14006afcf  mov     ebx, eax
0x14006afd1  jmp     loc_14006B0F0
0x14006afd6  mov     ecx, [rbp+cbData]
0x14006afd9  test    ecx, ecx
0x14006afdb  jz      loc_14006B0C0
0x14006afe1  cmp     [rbp+Type], 1
0x14006afe5  jnz     loc_14006B0C0
0x14006afeb  shr     rcx, 1
0x14006afee  mov     eax, 2
0x14006aff3  mul     rcx
0x14006aff6  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x14006affd  cmovb   rax, rbx
0x14006b001  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14006b008  mov     rcx, rax; unsigned __int64
0x14006b00b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14006b010  mov     rdi, rax
0x14006b013  test    rax, rax
0x14006b016  jnz     short loc_14006B038
0x14006b018  mov     rcx, [rbp+28h]; this
0x14006b01c  mov     ebx, 8007000Eh
0x14006b021  mov     r9d, ebx; char *
0x14006b024  lea     r8, aAdminEduSecure_1; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006b02b  lea     edx, [rax+61h]; void *
0x14006b02e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006b033  jmp     loc_14006B0F0
0x14006b038  lea     rax, [rbp+cbData]
0x14006b03c  mov     [rsp+50h+lpcbData], rax; lpcbData
0x14006b041  mov     [rsp+50h+phkResult], rdi; int
0x14006b046  xor     r9d, r9d; lpType
0x14006b049  xor     r8d, r8d; lpReserved
0x14006b04c  lea     rdx, ?c_temporaryStoreUserSidValueName@@3QBGB; "TemporaryUserSid"
0x14006b053  mov     rcx, [rbp+hKey]; hKey
0x14006b057  call    cs:__imp_RegQueryValueExW
0x14006b05d  test    eax, eax
0x14006b05f  jz      short loc_14006B085
0x14006b061  mov     rcx, [rbp+28h]; this
0x14006b065  mov     r9d, eax; char *
0x14006b068  lea     r8, aAdminEduSecure_1; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006b06f  mov     edx, 67h ; 'g'; void *
0x14006b074  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x14006b079  mov     ebx, eax
0x14006b07b  mov     rcx, rdi; void *
0x14006b07e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14006b083  jmp     short loc_14006B0F0
0x14006b085  inc     rbx
0x14006b088  cmp     [rdi+rbx*2], r15w
0x14006b08d  jnz     short loc_14006B085
0x14006b08f  mov     rdx, rbx
0x14006b092  mov     rcx, rsi
0x14006b095  call    ?_EnsureCapacity@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJ_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCapacity(unsigned __int64)
0x14006b09a  mov     r14d, eax
0x14006b09d  test    eax, eax
0x14006b09f  js      short loc_14006B0CD
0x14006b0a1  lea     rdx, [rbx+1]; cchDest
0x14006b0a5  mov     r9, rbx; cchToCopy
0x14006b0a8  mov     r8, rdi; pszSrc
0x14006b0ab  mov     rcx, [rsi]; pszDest
0x14006b0ae  call    StringCchCopyNW
0x14006b0b3  mov     [rsi+8], rbx
0x14006b0b7  mov     rcx, rdi; void *
0x14006b0ba  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14006b0bf  nop
0x14006b0c0  lea     rcx, [rbp+hKey]
0x14006b0c4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14006b0c9  xor     eax, eax
0x14006b0cb  jmp     short loc_14006B115
0x14006b0cd  mov     rcx, [rbp+28h]; this
0x14006b0d1  mov     r9d, r14d; char *
0x14006b0d4  lea     r8, aAdminEduSecure_1; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006b0db  mov     edx, 68h ; 'h'; void *
0x14006b0e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006b0e5  mov     rcx, rdi; void *
0x14006b0e8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14006b0ed  mov     ebx, r14d
0x14006b0f0  lea     rcx, [rbp+hKey]
0x14006b0f4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14006b0f9  jmp     short loc_14006B113
0x14006b0fb  mov     rcx, [rbp+28h]; this
0x14006b0ff  mov     r9d, ebx; char *
0x14006b102  lea     r8, aAdminEduSecure_1; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006b109  mov     edx, 40h ; '@'; void *
0x14006b10e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14006b113  mov     eax, ebx
0x14006b115  mov     rbx, [rsp+50h+arg_0]
0x14006b11d  add     rsp, 50h
0x14006b121  pop     r15
0x14006b123  pop     r14
0x14006b125  pop     rdi
0x14006b126  pop     rsi
0x14006b127  pop     rbp
0x14006b128  retn
```
