# GetLocalAccountSidFromName

- ea: `0x1800a6b34`
- end: `0x1800a6d2a`
- name: `GetLocalAccountSidFromName`
- size: `502`
- prototype: `__int64 __fastcall(LPCWSTR lpAccountName)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18004b854`
- `0x180099258`

## callees

- `0x18000782c`
- `0x180007964`
- `0x1800281e0`
- `0x180028200`
- `0x18002db44`
- `0x180048304`
- `0x180097c6c`
- `0x1800a6b34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6bac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a6bac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a6bff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a6d12`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a6bff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a6d12`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a6cb5`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a6cb5`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x1800a6b80`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x1800a6c6f`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x1800a6b80`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountNameLocalW` at `0x1800a6c6f`

## string_xrefs

- `0x1800a6b98`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a6bbf`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a6c35`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a6c7d`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`
- `0x1800a6cce`: `onecore\ds\security\devicecredential\service\util\dcautil.cpp`

## pseudocode

```c
__int64 __fastcall GetLocalAccountSidFromName(LPCWSTR lpAccountName, _QWORD *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  DWORD LastError; // eax
  void **unique_hlocal; // rax
  const char *v9; // r9
  void *v10; // rdi
  HLOCAL v11; // rcx
  const char *v12; // r9
  BOOL v13; // ebx
  const char *v14; // r9
  unsigned int cchReferencedDomainName; // [rsp+20h] [rbp-40h]
  __int64 v16; // [rsp+30h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-28h] BYREF
  __int64 *v18; // [rsp+40h] [rbp-20h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-18h] BYREF
  char v20; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  DWORD v22; // [rsp+88h] [rbp+28h] BYREF
  DWORD cbSid; // [rsp+90h] [rbp+30h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+98h] [rbp+38h] BYREF

  *a2 = 0;
  cbSid = 0;
  v22 = 0;
  peUse = 0;
  if ( LookupAccountNameLocalW(lpAccountName, 0, &cbSid, 0, &v22, &peUse) )
  {
    v4 = -2147418113;
    v5 = 1545;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError != 122 && LastError )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x60D,
               (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
               (const char *)LastError,
               cchReferencedDomainName);
    unique_hlocal = (void **)wil::make_unique_hlocal_nothrow<unsigned char [0]>(&hMem, cbSid);
    v10 = *unique_hlocal;
    *unique_hlocal = 0;
    v11 = hMem;
    hMem = 0;
    if ( v11 )
      LocalFree(v11);
    if ( v10 )
    {
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &hMem,
        0,
        v22,
        v9);
      if ( hMem )
      {
        if ( LookupAccountNameLocalW(lpAccountName, v10, &cbSid, (LPWSTR)hMem, &v22, &peUse) )
        {
          v16 = 0;
          v18 = &v16;
          StringSid = 0;
          v20 = 1;
          v13 = ConvertSidToStringSidW(v10, &StringSid);
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v18);
          if ( v13 )
          {
            *a2 = v16;
            v16 = 0;
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v16);
            v4 = 0;
          }
          else
          {
            v4 = wil::details::in1diag3::Return_GetLastError(
                   retaddr,
                   (void *)0x623,
                   (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
                   v14);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v16);
          }
        }
        else
        {
          v4 = wil::details::in1diag3::Return_GetLastError(
                 retaddr,
                 (void *)0x61E,
                 (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
                 v12);
        }
      }
      else
      {
        v4 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x616,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
          (const char *)0x8007000ELL,
          cchReferencedDomainName);
      }
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&hMem);
      LocalFree(v10);
      return v4;
    }
    v4 = -2147024882;
    v5 = 1555;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\util\\dcautil.cpp",
    (const char *)v4,
    cchReferencedDomainName);
  return v4;
}

```

## disassembly

```asm
0x1800a6b34  mov     [rsp-18h+arg_0], rbx
0x1800a6b39  push    rbp
0x1800a6b3a  push    rsi
0x1800a6b3b  push    rdi
0x1800a6b3c  mov     rbp, rsp
0x1800a6b3f  sub     rsp, 60h
0x1800a6b43  lea     rax, [rbp+arg_18]
0x1800a6b47  mov     qword ptr [rdx], 0
0x1800a6b4e  mov     [rsp+60h+peUse], rax; peUse
0x1800a6b53  lea     r8, [rbp+cbSid]; cbSid
0x1800a6b57  lea     rax, [rbp+arg_8]
0x1800a6b5b  mov     [rbp+cbSid], 0
0x1800a6b62  mov     rsi, rdx
0x1800a6b65  mov     [rsp+60h+cchReferencedDomainName], rax; int
0x1800a6b6a  xor     r9d, r9d; ReferencedDomainName
0x1800a6b6d  mov     [rbp+arg_8], 0
0x1800a6b74  xor     edx, edx; Sid
0x1800a6b76  mov     [rbp+arg_18], 0
0x1800a6b7d  mov     rbx, rcx
0x1800a6b80  call    cs:__imp_LookupAccountNameLocalW
0x1800a6b86  test    eax, eax
0x1800a6b88  jz      short loc_1800A6BAC
0x1800a6b8a  mov     ebx, 8000FFFFh
0x1800a6b8f  mov     edx, 609h; void *
0x1800a6b94  mov     rcx, [rbp+18h]; this
0x1800a6b98  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a6b9f  mov     r9d, ebx; char *
0x1800a6ba2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6ba7  jmp     loc_1800A6D18
0x1800a6bac  call    cs:__imp_GetLastError
0x1800a6bb2  cmp     eax, 7Ah ; 'z'
0x1800a6bb5  jz      short loc_1800A6BD8
0x1800a6bb7  test    eax, eax
0x1800a6bb9  jz      short loc_1800A6BD8
0x1800a6bbb  mov     rcx, [rbp+18h]; this
0x1800a6bbf  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a6bc6  mov     r9d, eax; char *
0x1800a6bc9  mov     edx, 60Dh; void *
0x1800a6bce  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a6bd3  jmp     loc_1800A6D1A
0x1800a6bd8  mov     edx, [rbp+cbSid]
0x1800a6bdb  lea     rcx, [rbp+hMem]
0x1800a6bdf  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x1800a6be4  mov     rdi, [rax]
0x1800a6be7  mov     qword ptr [rax], 0
0x1800a6bee  mov     rcx, [rbp+hMem]; hMem
0x1800a6bf2  mov     [rbp+hMem], 0
0x1800a6bfa  test    rcx, rcx
0x1800a6bfd  jz      short loc_1800A6C05
0x1800a6bff  call    cs:__imp_LocalFree
0x1800a6c05  test    rdi, rdi
0x1800a6c08  jnz     short loc_1800A6C19
0x1800a6c0a  mov     ebx, 8007000Eh
0x1800a6c0f  mov     edx, 613h
0x1800a6c14  jmp     loc_1800A6B94
0x1800a6c19  mov     r8d, [rbp+arg_8]
0x1800a6c1d  lea     rcx, [rbp+hMem]
0x1800a6c21  xor     edx, edx
0x1800a6c23  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800a6c28  mov     r9, [rbp+hMem]; ReferencedDomainName
0x1800a6c2c  test    r9, r9
0x1800a6c2f  jnz     short loc_1800A6C53
0x1800a6c31  mov     rcx, [rbp+18h]; this
0x1800a6c35  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a6c3c  mov     ebx, 8007000Eh
0x1800a6c41  mov     edx, 616h; void *
0x1800a6c46  mov     r9d, ebx; char *
0x1800a6c49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6c4e  jmp     loc_1800A6D06
0x1800a6c53  lea     rax, [rbp+arg_18]
0x1800a6c57  mov     rdx, rdi; Sid
0x1800a6c5a  mov     [rsp+60h+peUse], rax; peUse
0x1800a6c5f  lea     r8, [rbp+cbSid]; cbSid
0x1800a6c63  lea     rax, [rbp+arg_8]
0x1800a6c67  mov     rcx, rbx; lpAccountName
0x1800a6c6a  mov     [rsp+60h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800a6c6f  call    cs:__imp_LookupAccountNameLocalW
0x1800a6c75  test    eax, eax
0x1800a6c77  jnz     short loc_1800A6C92
0x1800a6c79  mov     rcx, [rbp+18h]; this
0x1800a6c7d  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a6c84  mov     edx, 61Eh; void *
0x1800a6c89  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a6c8e  mov     ebx, eax
0x1800a6c90  jmp     short loc_1800A6D06
0x1800a6c92  lea     rax, [rbp+var_30]
0x1800a6c96  mov     [rbp+var_30], 0
0x1800a6c9e  lea     rdx, [rbp+StringSid]; StringSid
0x1800a6ca2  mov     [rbp+var_20], rax
0x1800a6ca6  mov     rcx, rdi; Sid
0x1800a6ca9  mov     [rbp+StringSid], 0
0x1800a6cb1  mov     [rbp+var_10], 1
0x1800a6cb5  call    cs:__imp_ConvertSidToStringSidW
0x1800a6cbb  lea     rcx, [rbp+var_20]
0x1800a6cbf  mov     ebx, eax
0x1800a6cc1  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800a6cc6  test    ebx, ebx
0x1800a6cc8  jnz     short loc_1800A6CEC
0x1800a6cca  mov     rcx, [rbp+18h]; this
0x1800a6cce  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\devicecredential"...
0x1800a6cd5  mov     edx, 623h; void *
0x1800a6cda  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a6cdf  lea     rcx, [rbp+var_30]; void *
0x1800a6ce3  mov     ebx, eax
0x1800a6ce5  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a6cea  jmp     short loc_1800A6D06
0x1800a6cec  mov     rax, [rbp+var_30]
0x1800a6cf0  lea     rcx, [rbp+var_30]; void *
0x1800a6cf4  mov     [rsi], rax
0x1800a6cf7  mov     [rbp+var_30], 0
0x1800a6cff  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a6d04  xor     ebx, ebx
0x1800a6d06  lea     rcx, [rbp+hMem]; void *
0x1800a6d0a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a6d0f  mov     rcx, rdi; hMem
0x1800a6d12  call    cs:__imp_LocalFree
0x1800a6d18  mov     eax, ebx
0x1800a6d1a  mov     rbx, [rsp+60h+arg_0]
0x1800a6d22  add     rsp, 60h
0x1800a6d26  pop     rdi
0x1800a6d27  pop     rsi
0x1800a6d28  pop     rbp
0x1800a6d29  retn
```
