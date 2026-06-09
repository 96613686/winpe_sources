# CLockScreenHistory::s_GetCreativeLockScreenPath(ushort const *,ushort * *,ushort * *,ushort * *,bool *)

- ea: `0x18000b774`
- end: `0x18000bb17`
- name: `?s_GetCreativeLockScreenPath@CLockScreenHistory@@SAJPEBGPEAPEAG11PEA_N@Z`
- size: `931`
- prototype: `__int64 __usercall@<rax>(CreativeFramework::LockScreenCreativeConfigHelpers *this@<rcx>, unsigned __int16 **@<rdx>, unsigned __int16 **@<r8>, unsigned __int16 **@<r9>, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000bf20`

## callees

- `0x180009f0c`
- `0x18000b0d4`
- `0x18000b774`
- `0x18000bb20`
- `0x18000d2b8`
- `0x180034768`
- `0x180034db4`
- `0x180039e34`
- `0x180050ba0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ba98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000ba98`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18000b9bb`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18000b9d8`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18000ba08`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18000ba1f`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18000b9bb`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18000b9d8`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18000ba08`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18000ba1f`
- `SHELL32!__imp_PathComparePaths` at `0x18000b9f0`
- `SHELL32!__imp_PathComparePaths` at `0x18000ba37`
- `SHELL32!__imp_PathComparePaths` at `0x18000b9f0`
- `SHELL32!__imp_PathComparePaths` at `0x18000ba37`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000b880`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18000b880`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000b8f4`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000b8f4`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000b95e`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x18000b95e`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CLockScreenHistory::s_GetCreativeLockScreenPath(
        CreativeFramework::LockScreenCreativeConfigHelpers *this,
        unsigned __int16 **a2,
        const WCHAR **a3,
        unsigned __int16 **a4,
        bool *a5)
{
  int v8; // eax
  unsigned int LastError; // ebx
  __int64 v10; // r9
  __int64 v11; // rdx
  unsigned __int16 *v12; // r14
  const WCHAR *v13; // rdi
  const WCHAR *v14; // rsi
  const char *v15; // r9
  const char *v16; // r9
  int BasicProfileFolderPath; // eax
  __int64 v18; // rdx
  __int64 v19; // r9
  int ReferencedDomainName; // [rsp+20h] [rbp-E0h]
  LPWSTR ReferencedDomainNamea; // [rsp+20h] [rbp-E0h]
  bool *cchReferencedDomainName; // [rsp+28h] [rbp-D8h]
  unsigned __int16 *v24; // [rsp+40h] [rbp-C0h] BYREF
  PSID Sid; // [rsp+48h] [rbp-B8h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR v27; // [rsp+58h] [rbp-A8h] BYREF
  PCWSTR pszPathIn; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v29[4]; // [rsp+68h] [rbp-98h] BYREF
  DWORD v30; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchName; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned __int16 **v32; // [rsp+78h] [rbp-88h]
  bool *v33; // [rsp+80h] [rbp-80h]
  WCHAR v34[20]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR Name[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR v36[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+4D0h] [rbp+3D0h] BYREF
  _BYTE v38[528]; // [rsp+6E0h] [rbp+5E0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+948h] [rbp+848h]

  v32 = a4;
  v33 = a5;
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  LOBYTE(v24) = 0;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl'::`2'::impl);
  v27 = 0;
  pszPathIn = 0;
  *(_QWORD *)v29 = 0;
  v8 = CreativeFramework::LockScreenCreativeConfigHelpers::PeekLockScreenRegistryKeys(
         this,
         v29,
         (unsigned __int16 **)&pszPathIn,
         (unsigned __int16 **)&v27,
         &v24,
         cchReferencedDomainName);
  LastError = v8;
  if ( v8 < 0 )
  {
    v10 = (unsigned int)v8;
    v11 = 397;
LABEL_37:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
      (const char *)v10,
      ReferencedDomainName);
    goto LABEL_38;
  }
  v12 = *(unsigned __int16 **)v29;
  if ( !*(_QWORD *)v29 || !**(_WORD **)v29 )
  {
    v11 = 398;
    goto LABEL_36;
  }
  v13 = pszPathIn;
  if ( !pszPathIn || !*pszPathIn )
  {
    v11 = 399;
    goto LABEL_36;
  }
  v14 = v27;
  if ( !v27 || !*v27 )
  {
    v11 = 400;
LABEL_36:
    LastError = -2147024894;
    v10 = 2147942402LL;
    goto LABEL_37;
  }
  Sid = 0;
  if ( !ConvertStringSidToSidW((LPCWSTR)this, &Sid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x19E,
                  (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
                  v15);
LABEL_11:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&Sid);
LABEL_38:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v27);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszPathIn);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v29);
    return LastError;
  }
  peUse = 0;
  cchName = 257;
  v30 = 16;
  if ( !LookupAccountSidW(0, Sid, Name, &cchName, v34, &v30, &peUse) )
  {
    BasicProfileFolderPath = wil::details::in1diag3::Return_GetLastError(
                               retaddr,
                               (void *)0x16B,
                               (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
                               v16);
    LastError = BasicProfileFolderPath;
    if ( BasicProfileFolderPath < 0 )
    {
      v18 = 416;
LABEL_15:
      v19 = (unsigned int)BasicProfileFolderPath;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v18,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)v19,
        (int)ReferencedDomainNamea);
      goto LABEL_11;
    }
  }
  if ( peUse == SidTypeUser )
  {
    BasicProfileFolderPath = GetBasicProfileFolderPath(6, this, v38, 260);
    LastError = BasicProfileFolderPath;
    if ( BasicProfileFolderPath < 0 )
    {
      v18 = 420;
      goto LABEL_15;
    }
    ReferencedDomainNamea = L"Packages\\Microsoft.Windows.ContentDeliveryManager_cw5n1h2txyewy\\LocalState\\Assets";
    BasicProfileFolderPath = StringCchPrintfW(Name, 0x104u, L"%s\\%s", v38);
    LastError = BasicProfileFolderPath;
    if ( BasicProfileFolderPath < 0 )
    {
      v18 = 422;
      goto LABEL_15;
    }
    if ( PathCchCanonicalize(pszPathOut, 0x104u, Name) < 0
      || PathCchCanonicalize(v36, 0x104u, v13) < 0
      || (PathComparePaths(pszPathOut, v36) & 8) == 0 )
    {
      LastError = -2147024894;
      v19 = 2147942402LL;
      v18 = 426;
      goto LABEL_16;
    }
    if ( PathCchCanonicalize(v36, 0x104u, Name) < 0
      || PathCchCanonicalize(pszPathOut, 0x104u, v14) < 0
      || (PathComparePaths(v36, pszPathOut) & 8) == 0 )
    {
      LastError = -2147024894;
      v19 = 2147942402LL;
      v18 = 431;
      goto LABEL_16;
    }
  }
  *(_QWORD *)v29 = 0;
  *a2 = v12;
  pszPathIn = 0;
  *a3 = v13;
  v27 = 0;
  *v32 = (unsigned __int16 *)v14;
  *v33 = (char)v24;
  if ( Sid )
    LocalFree(Sid);
  return 0;
}

```

## disassembly

```asm
0x18000b774  push    rbp
0x18000b776  push    rbx
0x18000b777  push    rsi
0x18000b778  push    rdi
0x18000b779  push    r12
0x18000b77b  push    r13
0x18000b77d  push    r14
0x18000b77f  push    r15
0x18000b781  lea     rbp, [rsp-808h]
0x18000b789  sub     rsp, 908h
0x18000b790  mov     rax, cs:__security_cookie
0x18000b797  xor     rax, rsp
0x18000b79a  mov     [rbp+840h+var_50], rax
0x18000b7a1  mov     [rsp+940h+var_8C8], r9
0x18000b7a6  mov     r13, r8
0x18000b7a9  mov     r12, rdx
0x18000b7ac  mov     r15, rcx
0x18000b7af  mov     rcx, [rbp+840h+arg_20]
0x18000b7b6  mov     [rbp+840h+var_8C0], rcx
0x18000b7ba  xor     esi, esi
0x18000b7bc  mov     [rdx], rsi
0x18000b7bf  mov     [r8], rsi
0x18000b7c2  mov     [r9], rsi
0x18000b7c5  mov     [rcx], sil
0x18000b7c8  mov     qword ptr [rsp+940h+var_8D8], rsi
0x18000b7cd  mov     [rsp+940h+pszPathIn], rsi
0x18000b7d2  mov     [rsp+940h+var_8E8], rsi
0x18000b7d7  mov     byte ptr [rsp+940h+var_900], sil
0x18000b7dc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3> `wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl(void)'::`2'::impl
0x18000b7e3  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x18000b7e8  mov     [rsp+940h+var_8E8], rsi
0x18000b7ed  mov     [rsp+940h+pszPathIn], rsi
0x18000b7f2  mov     qword ptr [rsp+940h+var_8D8], rsi
0x18000b7f7  lea     rax, [rsp+940h+var_900]
0x18000b7fc  mov     [rsp+940h+ReferencedDomainName], rax; int
0x18000b801  lea     r9, [rsp+940h+var_8E8]; unsigned __int16 **
0x18000b806  lea     r8, [rsp+940h+pszPathIn]; unsigned __int16 **
0x18000b80b  lea     rdx, [rsp+940h+var_8D8]; unsigned __int16 *
0x18000b810  mov     rcx, r15; this
0x18000b813  call    ?PeekLockScreenRegistryKeys@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEBGPEAPEAG11PEA_N@Z; CreativeFramework::LockScreenCreativeConfigHelpers::PeekLockScreenRegistryKeys(ushort const *,ushort * *,ushort * *,ushort * *,bool *)
0x18000b818  mov     ebx, eax
0x18000b81a  test    eax, eax
0x18000b81c  jns     short loc_18000B82B
0x18000b81e  mov     r9d, eax
0x18000b821  mov     edx, 18Dh
0x18000b826  jmp     loc_18000BABE
0x18000b82b  mov     r14, qword ptr [rsp+940h+var_8D8]
0x18000b830  test    r14, r14
0x18000b833  jz      loc_18000BAB1
0x18000b839  cmp     [r14], si
0x18000b83d  jz      loc_18000BAB1
0x18000b843  mov     rdi, [rsp+940h+pszPathIn]
0x18000b848  test    rdi, rdi
0x18000b84b  jz      loc_18000BAAA
0x18000b851  cmp     [rdi], si
0x18000b854  jz      loc_18000BAAA
0x18000b85a  mov     rsi, [rsp+940h+var_8E8]
0x18000b85f  xor     ebx, ebx
0x18000b861  test    rsi, rsi
0x18000b864  jz      loc_18000BAA3
0x18000b86a  cmp     [rsi], bx
0x18000b86d  jz      loc_18000BAA3
0x18000b873  mov     [rsp+940h+Sid], rbx
0x18000b878  lea     rdx, [rsp+940h+Sid]; Sid
0x18000b87d  mov     rcx, r15; StringSid
0x18000b880  call    cs:__imp_ConvertStringSidToSidW
0x18000b886  test    eax, eax
0x18000b888  jnz     short loc_18000B8B3
0x18000b88a  mov     rcx, [rbp+848h]; this
0x18000b891  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18000b898  mov     edx, 19Eh; void *
0x18000b89d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b8a2  mov     ebx, eax
0x18000b8a4  lea     rcx, [rsp+940h+Sid]
0x18000b8a9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000b8ae  jmp     loc_18000BAD2
0x18000b8b3  mov     [rsp+940h+var_8F0], ebx
0x18000b8b7  mov     [rsp+940h+cchName], 101h
0x18000b8bf  mov     [rsp+940h+var_8D0], 10h
0x18000b8c7  lea     rax, [rsp+940h+var_8F0]
0x18000b8cc  mov     [rsp+940h+peUse], rax; peUse
0x18000b8d1  lea     rax, [rsp+940h+var_8D0]
0x18000b8d6  mov     [rsp+940h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18000b8db  lea     rax, [rbp+840h+var_8B8]
0x18000b8df  mov     [rsp+940h+ReferencedDomainName], rax; int
0x18000b8e4  lea     r9, [rsp+940h+cchName]; cchName
0x18000b8e9  lea     r8, [rbp+840h+Name]; Name
0x18000b8ed  mov     rdx, [rsp+940h+Sid]; Sid
0x18000b8f2  xor     ecx, ecx; lpSystemName
0x18000b8f4  call    cs:__imp_LookupAccountSidW
0x18000b8fa  test    eax, eax
0x18000b8fc  jnz     short loc_18000B93E
0x18000b8fe  mov     rcx, [rbp+848h]; this
0x18000b905  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18000b90c  mov     edx, 16Bh; void *
0x18000b911  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b916  mov     ebx, eax
0x18000b918  test    eax, eax
0x18000b91a  jns     short loc_18000B93C
0x18000b91c  mov     edx, 1A0h; void *
0x18000b921  mov     r9d, eax; char *
0x18000b924  mov     rcx, [rbp+848h]; this
0x18000b92b  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18000b932  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b937  jmp     loc_18000B8A4
0x18000b93c  xor     ebx, ebx
0x18000b93e  cmp     [rsp+940h+var_8F0], 1
0x18000b943  jnz     loc_18000BA65
0x18000b949  mov     r9d, 104h
0x18000b94f  lea     r8, [rbp+840h+var_260]
0x18000b956  mov     rdx, r15
0x18000b959  mov     ecx, 6
0x18000b95e  call    cs:__imp_GetBasicProfileFolderPath
0x18000b964  mov     ebx, eax
0x18000b966  test    eax, eax
0x18000b968  jns     short loc_18000B971
0x18000b96a  mov     edx, 1A4h
0x18000b96f  jmp     short loc_18000B921
0x18000b971  lea     rax, aPackagesMicros; "Packages\\Microsoft.Windows.ContentDeli"...
0x18000b978  mov     [rsp+940h+ReferencedDomainName], rax
0x18000b97d  lea     r9, [rbp+840h+var_260]
0x18000b984  lea     r8, aSS_1; "%s\\%s"
0x18000b98b  mov     r15d, 104h
0x18000b991  mov     edx, r15d; unsigned __int64
0x18000b994  lea     rcx, [rbp+840h+Name]; unsigned __int16 *
0x18000b998  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b99d  mov     ebx, eax
0x18000b99f  test    eax, eax
0x18000b9a1  jns     short loc_18000B9AD
0x18000b9a3  mov     edx, 1A6h
0x18000b9a8  jmp     loc_18000B921
0x18000b9ad  lea     r8, [rbp+840h+Name]; pszPathIn
0x18000b9b1  mov     rdx, r15; cchPathOut
0x18000b9b4  lea     rcx, [rbp+840h+pszPathOut]; pszPathOut
0x18000b9bb  call    cs:__imp_PathCchCanonicalize
0x18000b9c1  xor     ebx, ebx
0x18000b9c3  test    eax, eax
0x18000b9c5  js      loc_18000BA53
0x18000b9cb  mov     r8, rdi; pszPathIn
0x18000b9ce  mov     rdx, r15; cchPathOut
0x18000b9d1  lea     rcx, [rbp+840h+var_680]; pszPathOut
0x18000b9d8  call    cs:__imp_PathCchCanonicalize
0x18000b9de  test    eax, eax
0x18000b9e0  js      short loc_18000BA53
0x18000b9e2  lea     rdx, [rbp+840h+var_680]
0x18000b9e9  lea     rcx, [rbp+840h+pszPathOut]
0x18000b9f0  call    cs:__imp_PathComparePaths
0x18000b9f6  test    al, 8
0x18000b9f8  jz      short loc_18000BA53
0x18000b9fa  lea     r8, [rbp+840h+Name]; pszPathIn
0x18000b9fe  mov     rdx, r15; cchPathOut
0x18000ba01  lea     rcx, [rbp+840h+var_680]; pszPathOut
0x18000ba08  call    cs:__imp_PathCchCanonicalize
0x18000ba0e  test    eax, eax
0x18000ba10  js      short loc_18000BA41
0x18000ba12  mov     r8, rsi; pszPathIn
0x18000ba15  mov     rdx, r15; cchPathOut
0x18000ba18  lea     rcx, [rbp+840h+pszPathOut]; pszPathOut
0x18000ba1f  call    cs:__imp_PathCchCanonicalize
0x18000ba25  test    eax, eax
0x18000ba27  js      short loc_18000BA41
0x18000ba29  lea     rdx, [rbp+840h+pszPathOut]
0x18000ba30  lea     rcx, [rbp+840h+var_680]
0x18000ba37  call    cs:__imp_PathComparePaths
0x18000ba3d  test    al, 8
0x18000ba3f  jnz     short loc_18000BA65
0x18000ba41  mov     ebx, 80070002h
0x18000ba46  mov     r9d, ebx
0x18000ba49  mov     edx, 1AFh
0x18000ba4e  jmp     loc_18000B924
0x18000ba53  mov     ebx, 80070002h
0x18000ba58  mov     r9d, ebx
0x18000ba5b  mov     edx, 1AAh
0x18000ba60  jmp     loc_18000B924
0x18000ba65  mov     qword ptr [rsp+940h+var_8D8], rbx
0x18000ba6a  mov     [r12], r14
0x18000ba6e  mov     [rsp+940h+pszPathIn], rbx
0x18000ba73  mov     [r13+0], rdi
0x18000ba77  mov     [rsp+940h+var_8E8], rbx
0x18000ba7c  mov     rax, [rsp+940h+var_8C8]
0x18000ba81  mov     [rax], rsi
0x18000ba84  mov     al, byte ptr [rsp+940h+var_900]
0x18000ba88  mov     rcx, [rbp+840h+var_8C0]
0x18000ba8c  mov     [rcx], al
0x18000ba8e  mov     rcx, [rsp+940h+Sid]; hMem
0x18000ba93  test    rcx, rcx
0x18000ba96  jz      short loc_18000BA9F
0x18000ba98  call    cs:__imp_LocalFree
0x18000ba9e  nop
0x18000ba9f  xor     eax, eax
0x18000baa1  jmp     short loc_18000BAF4
0x18000baa3  mov     edx, 190h
0x18000baa8  jmp     short loc_18000BAB6
0x18000baaa  mov     edx, 18Fh
0x18000baaf  jmp     short loc_18000BAB6
0x18000bab1  mov     edx, 18Eh; void *
0x18000bab6  mov     ebx, 80070002h
0x18000babb  mov     r9d, ebx; char *
0x18000babe  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18000bac5  mov     rcx, [rbp+848h]; this
0x18000bacc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bad1  nop
0x18000bad2  lea     rcx, [rsp+940h+var_8E8]
0x18000bad7  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000badc  nop
0x18000badd  lea     rcx, [rsp+940h+pszPathIn]
0x18000bae2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000bae7  nop
0x18000bae8  lea     rcx, [rsp+940h+var_8D8]
0x18000baed  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18000baf2  mov     eax, ebx
0x18000baf4  mov     rcx, [rbp+840h+var_50]
0x18000bafb  xor     rcx, rsp; StackCookie
0x18000bafe  call    __security_check_cookie
0x18000bb03  add     rsp, 908h
0x18000bb0a  pop     r15
0x18000bb0c  pop     r14
0x18000bb0e  pop     r13
0x18000bb10  pop     r12
0x18000bb12  pop     rdi
0x18000bb13  pop     rsi
0x18000bb14  pop     rbx
0x18000bb15  pop     rbp
0x18000bb16  retn
```
