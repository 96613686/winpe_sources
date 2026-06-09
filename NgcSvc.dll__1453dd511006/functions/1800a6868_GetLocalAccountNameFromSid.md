# GetLocalAccountNameFromSid

- ea: `0x1800a6868`
- end: `0x1800a69ea`
- name: `GetLocalAccountNameFromSid`
- size: `386`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a69f0`

## callees

- `0x18000782c`
- `0x180007964`
- `0x1800281e0`
- `0x180028200`
- `0x180048304`
- `0x1800a6868`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a68e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a68e0`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800a68b4`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800a6999`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800a68b4`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800a6999`

## string_xrefs

- `0x1800a68c2`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a68f3`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a6928`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a6962`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a69a7`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`

## pseudocode

```c
__int64 __fastcall GetLocalAccountNameFromSid(PSID Sid, WCHAR **a2)
{
  unsigned int v4; // ebx
  DWORD LastError; // eax
  const char *v6; // r9
  const char *v8; // r9
  WCHAR *v9; // rbx
  const char *v10; // r9
  unsigned int cchReferencedDomainName; // [rsp+20h] [rbp-20h]
  LPWSTR Name; // [rsp+30h] [rbp-10h] BYREF
  LPWSTR ReferencedDomainName; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  DWORD v15; // [rsp+68h] [rbp+28h] BYREF
  DWORD cchName; // [rsp+70h] [rbp+30h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+78h] [rbp+38h] BYREF

  *a2 = 0;
  cchName = 0;
  v15 = 0;
  peUse = 0;
  if ( LookupAccountSidLocalW(Sid, 0, &cchName, 0, &v15, &peUse) )
  {
    v4 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63C,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
      (const char *)0x8000FFFFLL,
      cchReferencedDomainName);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 122 && LastError )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x640,
               (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
               (const char *)LastError,
               cchReferencedDomainName);
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &Name,
      0,
      cchName,
      v6);
    v9 = Name;
    if ( Name )
    {
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &ReferencedDomainName,
        0,
        v15,
        v8);
      if ( ReferencedDomainName )
      {
        if ( LookupAccountSidLocalW(Sid, v9, &cchName, ReferencedDomainName, &v15, &peUse) )
        {
          *a2 = v9;
          v4 = 0;
          Name = 0;
        }
        else
        {
          v4 = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x650,
                 (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
                 v10);
        }
      }
      else
      {
        v4 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x648,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
          (const char *)0x8007000ELL,
          cchReferencedDomainName);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&ReferencedDomainName);
    }
    else
    {
      v4 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x645,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
        (const char *)0x8007000ELL,
        cchReferencedDomainName);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Name);
  }
  return v4;
}

```

## disassembly

```asm
0x1800a6868  mov     [rsp-18h+arg_0], rbx
0x1800a686d  push    rbp
0x1800a686e  push    rsi
0x1800a686f  push    rdi
0x1800a6870  mov     rbp, rsp
0x1800a6873  sub     rsp, 40h
0x1800a6877  lea     rax, [rbp+arg_18]
0x1800a687b  mov     qword ptr [rdx], 0
0x1800a6882  mov     [rsp+40h+peUse], rax; peUse
0x1800a6887  lea     r8, [rbp+cchName]; cchName
0x1800a688b  lea     rax, [rbp+arg_8]
0x1800a688f  mov     [rbp+cchName], 0
0x1800a6896  mov     rdi, rdx
0x1800a6899  mov     [rsp+40h+cchReferencedDomainName], rax; int
0x1800a689e  xor     r9d, r9d; ReferencedDomainName
0x1800a68a1  mov     [rbp+arg_8], 0
0x1800a68a8  xor     edx, edx; Name
0x1800a68aa  mov     [rbp+arg_18], 0
0x1800a68b1  mov     rsi, rcx
0x1800a68b4  call    cs:__imp_LookupAccountSidLocalW
0x1800a68ba  test    eax, eax
0x1800a68bc  jz      short loc_1800A68E0
0x1800a68be  mov     rcx, [rbp+18h]; this
0x1800a68c2  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a68c9  mov     ebx, 8000FFFFh
0x1800a68ce  mov     edx, 63Ch; void *
0x1800a68d3  mov     r9d, ebx; char *
0x1800a68d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a68db  jmp     loc_1800A69DB
0x1800a68e0  call    cs:__imp_GetLastError
0x1800a68e6  cmp     eax, 7Ah ; 'z'
0x1800a68e9  jz      short loc_1800A690C
0x1800a68eb  test    eax, eax
0x1800a68ed  jz      short loc_1800A690C
0x1800a68ef  mov     rcx, [rbp+18h]; this
0x1800a68f3  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a68fa  mov     r9d, eax; char *
0x1800a68fd  mov     edx, 640h; void *
0x1800a6902  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a6907  jmp     loc_1800A69DD
0x1800a690c  mov     r8d, [rbp+cchName]
0x1800a6910  lea     rcx, [rbp+Name]
0x1800a6914  xor     edx, edx
0x1800a6916  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a691b  mov     rbx, [rbp+Name]
0x1800a691f  test    rbx, rbx
0x1800a6922  jnz     short loc_1800A6946
0x1800a6924  mov     rcx, [rbp+18h]; this
0x1800a6928  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a692f  mov     ebx, 8007000Eh
0x1800a6934  mov     edx, 645h; void *
0x1800a6939  mov     r9d, ebx; char *
0x1800a693c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6941  jmp     loc_1800A69D2
0x1800a6946  mov     r8d, [rbp+arg_8]
0x1800a694a  lea     rcx, [rbp+ReferencedDomainName]
0x1800a694e  xor     edx, edx
0x1800a6950  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a6955  mov     r9, [rbp+ReferencedDomainName]; ReferencedDomainName
0x1800a6959  test    r9, r9
0x1800a695c  jnz     short loc_1800A697D
0x1800a695e  mov     rcx, [rbp+18h]; this
0x1800a6962  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a6969  mov     ebx, 8007000Eh
0x1800a696e  mov     edx, 648h; void *
0x1800a6973  mov     r9d, ebx; char *
0x1800a6976  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a697b  jmp     short loc_1800A69C9
0x1800a697d  lea     rax, [rbp+arg_18]
0x1800a6981  mov     rdx, rbx; Name
0x1800a6984  mov     [rsp+40h+peUse], rax; peUse
0x1800a6989  lea     r8, [rbp+cchName]; cchName
0x1800a698d  lea     rax, [rbp+arg_8]
0x1800a6991  mov     rcx, rsi; Sid
0x1800a6994  mov     [rsp+40h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800a6999  call    cs:__imp_LookupAccountSidLocalW
0x1800a699f  test    eax, eax
0x1800a69a1  jnz     short loc_1800A69BC
0x1800a69a3  mov     rcx, [rbp+18h]; this
0x1800a69a7  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a69ae  mov     edx, 650h; void *
0x1800a69b3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a69b8  mov     ebx, eax
0x1800a69ba  jmp     short loc_1800A69C9
0x1800a69bc  mov     [rdi], rbx
0x1800a69bf  xor     ebx, ebx
0x1800a69c1  mov     [rbp+Name], 0
0x1800a69c9  lea     rcx, [rbp+ReferencedDomainName]; void *
0x1800a69cd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a69d2  lea     rcx, [rbp+Name]; void *
0x1800a69d6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a69db  mov     eax, ebx
0x1800a69dd  mov     rbx, [rsp+40h+arg_0]
0x1800a69e2  add     rsp, 40h
0x1800a69e6  pop     rdi
0x1800a69e7  pop     rsi
0x1800a69e8  pop     rbp
0x1800a69e9  retn
```
