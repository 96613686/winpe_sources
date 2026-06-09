# TryGetADRegistrationConfiguration(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,TenantConfiguration &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18009ecec`
- end: `0x18009f2da`
- name: `?TryGetADRegistrationConfiguration@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAVTenantConfiguration@@AEAV12@@Z`
- size: `1518`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task`

## callers

- `0x18009e4ac`

## callees

- `0x180003c20`
- `0x180006061`
- `0x18008aa28`
- `0x18008aa64`
- `0x18008aa9c`
- `0x1800946a4`
- `0x18009480c`
- `0x18009cafc`
- `0x18009cb80`
- `0x18009cde4`
- `0x18009cecc`
- `0x18009d000`
- `0x18009d030`
- `0x18009d0c4`
- `0x18009ecec`
- `0x18009f2e0`
- `0x1800a0c30`
- `0x1800a0e64`
- `0x1800a106c`
- `0x1800a13a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18009f100`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18009f161`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18009f1d1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18009f100`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18009f161`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18009f1d1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18009ed57`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18009ed87`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18009ed57`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18009ed87`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18009f296`
- `WLDAP32!__imp_ldap_value_freeW` at `0x18009f296`

## string_xrefs

- `0x18009ee99`: `configurationNamingContext`
- `0x18009ed23`: `TryGetADRegistrationConfiguration`
- `0x18009ede0`: `TryGetADRegistrationConfiguration`
- `0x18009ee4a`: `TryGetADRegistrationConfiguration`
- `0x18009eed0`: `TryGetADRegistrationConfiguration`
- `0x18009efae`: `TryGetADRegistrationConfiguration`
- `0x18009f005`: `TryGetADRegistrationConfiguration`
- `0x18009f0d0`: `TryGetADRegistrationConfiguration`
- `0x18009f1ab`: `TryGetADRegistrationConfiguration`
- `0x18009f217`: `TryGetADRegistrationConfiguration`
- `0x18009ef1f`: `CN=62a0ff2e-97b9-4513-943f-0d221bd30080,CN=Device Registration Configuration,CN=services,`
- `0x18009f0d7`: `%s: read keywords found value %s`
- `0x18009f15a`: `azureADId:`
- `0x18009f1a4`: `%s: read tenant id %s`
- `0x18009f0f9`: `azureADName:`
- `0x18009f143`: `%s: read tenant name %s`
- `0x18009f21e`: `%s: read enterprise DRS name %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall TryGetADRegistrationConfiguration(_QWORD *a1, __int64 a2, __int64 a3)
{
  _QWORD *v5; // r14
  LdapSearchResult *v6; // rax
  LdapSearchResult *v7; // rdi
  LdapServer *v8; // rax
  LdapServer *v9; // rsi
  const unsigned __int16 *v10; // rax
  int v11; // eax
  unsigned __int16 **v12; // rdx
  unsigned int v13; // ebx
  __int64 v14; // r8
  __int64 v15; // r9
  int RootDSE; // eax
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v19; // rax
  int StringValues; // eax
  __int64 v21; // r8
  __int64 v22; // r9
  unsigned __int64 v23; // rdx
  __int64 v24; // rdi
  __int64 v25; // rbx
  __int64 v26; // rdx
  __int64 v27; // r9
  const void *v28; // r10
  __int64 v29; // rax
  const unsigned __int16 *v30; // rax
  const unsigned __int16 *v31; // r8
  const unsigned __int16 *v32; // r9
  int AttributeValues; // eax
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 i; // rdi
  __int64 v37; // r8
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // r8
  __int64 v48; // r9
  const char *v50; // r8
  signed int LastError; // eax
  unsigned int v52[2]; // [rsp+30h] [rbp-E8h] BYREF
  __int128 v53; // [rsp+38h] [rbp-E0h] BYREF
  __int64 v54; // [rsp+48h] [rbp-D0h]
  LdapSearchResult *v55; // [rsp+50h] [rbp-C8h] BYREF
  PWCHAR *vals; // [rsp+58h] [rbp-C0h] BYREF
  LdapServer *v57; // [rsp+60h] [rbp-B8h] BYREF
  void **v58; // [rsp+68h] [rbp-B0h] BYREF
  const char *v59; // [rsp+70h] [rbp-A8h] BYREF
  _QWORD *v60; // [rsp+80h] [rbp-98h]
  _QWORD v61[4]; // [rsp+88h] [rbp-90h] BYREF
  _QWORD Src[2]; // [rsp+A8h] [rbp-70h] BYREF
  __int64 v63; // [rsp+B8h] [rbp-60h]
  __int64 v64; // [rsp+C0h] [rbp-58h]
  _QWORD v65[4]; // [rsp+C8h] [rbp-50h] BYREF

  v5 = a1;
  v60 = a1;
  Logger::TraceVerbose(L"%s started", L"TryGetADRegistrationConfiguration");
  vals = 0;
  v53 = 0;
  v54 = 0;
  v6 = (LdapSearchResult *)malloc(0x10u);
  v7 = v6;
  v57 = v6;
  if ( v6 )
  {
    *(_QWORD *)v6 = 0;
    *((_QWORD *)v6 + 1) = 0;
  }
  else
  {
    v7 = 0;
  }
  v55 = v7;
  v8 = (LdapServer *)malloc(8u);
  v9 = v8;
  v57 = v8;
  if ( v8 )
    *(_QWORD *)v8 = 0;
  else
    v9 = 0;
  *(_QWORD *)v52 = 0;
  v57 = v9;
  std::unique_ptr<LdapServer>::~unique_ptr<LdapServer>(v52);
  v10 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v5);
  try
  {
    v11 = LdapServer::Connect(v9, v10);
    v13 = v11;
    if ( v11 >= 0 )
    {
      RootDSE = LdapServer::GetRootDSE(v9, v12, v7);
      v13 = RootDSE;
      if ( RootDSE >= 0 )
      {
        v19 = std::wstring::wstring(v61, L"configurationNamingContext");
        StringValues = LdapServer::GetStringValues(v9, v7, v19, &v53);
        v13 = StringValues;
        if ( StringValues >= 0 )
        {
          std::wstring::wstring(
            Src,
            L"CN=62a0ff2e-97b9-4513-943f-0d221bd30080,CN=Device Registration Configuration,CN=services,");
          std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v53);
          if ( v23 > v64 - v63 )
          {
            std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
              Src,
              v23);
          }
          else
          {
            v63 += v23;
            v24 = v63;
            v25 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
            memmove_0((void *)(v25 + 2 * v27), v28, 2 * v26);
            *(_WORD *)(v25 + 2 * v24) = 0;
          }
          v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
          Logger::TraceInformation(L"%s: DRS confg dn %s", L"TryGetADRegistrationConfiguration", v29);
          v52[0] = 0;
          v30 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
          AttributeValues = LdapServer::GetAttributeValues(v9, v30, v31, v32, v52, &vals);
          v13 = AttributeValues;
          if ( AttributeValues >= 0 )
          {
            *(_QWORD *)(a2 + 48) = 0;
            *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 32) = 0;
            *(_QWORD *)(a2 + 16) = 0;
            *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2) = 0;
            *(_QWORD *)(a3 + 16) = 0;
            *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3) = 0;
            for ( i = 0; (unsigned int)i < v52[0]; i = (unsigned int)(i + 1) )
            {
              std::wstring::wstring(v61, vals[i]);
              v37 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v61);
              Logger::TraceInformation(L"%s: read keywords found value %s", L"TryGetADRegistrationConfiguration", v37);
              v38 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v61);
              if ( (unsigned int)_o__wcsnicmp(v38, L"azureADName:", 12) )
              {
                v41 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v61);
                if ( (unsigned int)_o__wcsnicmp(v41, L"azureADId:", 10) )
                {
                  v44 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v61);
                  if ( !(unsigned int)_o__wcsnicmp(v44, L"enterpriseDrsName:", 18) )
                  {
                    v45 = std::wstring::substr(v61, v65, 18);
                    std::wstring::operator=(a3, v45);
                    std::wstring::_Tidy_deallocate(v65);
                    v46 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
                    Logger::TraceInformation(
                      L"%s: read enterprise DRS name %s",
                      L"TryGetADRegistrationConfiguration",
                      v46);
                  }
                }
                else
                {
                  v42 = std::wstring::substr(v61, v65, 10);
                  std::wstring::operator=(a2 + 32, v42);
                  std::wstring::_Tidy_deallocate(v65);
                  v43 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2 + 32);
                  Logger::TraceInformation(L"%s: read tenant id %s", L"TryGetADRegistrationConfiguration", v43);
                }
              }
              else
              {
                v39 = std::wstring::substr(v61, v65, 12);
                std::wstring::operator=(a2, v39);
                std::wstring::_Tidy_deallocate(v65);
                v40 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
                Logger::TraceInformation(L"%s: read tenant name %s", L"TryGetADRegistrationConfiguration", v40);
              }
              std::wstring::_Tidy_deallocate(v61);
            }
            std::wstring::_Tidy_deallocate(Src);
            std::unique_ptr<LdapSearchResult>::~unique_ptr<LdapSearchResult>(&v55);
            if ( (_QWORD)v53 )
            {
              std::_Destroy_range<std::allocator<std::wstring>>(v53, *((_QWORD *)&v53 + 1), v47, v48);
              std::_Deallocate<16>(v53, (v54 - v53) & 0xFFFFFFFFFFFFFFE0uLL);
            }
          }
          else
          {
            Logger::TraceError(
              L"%s: %s failed with error code: 0x%08x.",
              L"TryGetADRegistrationConfiguration",
              L"LdapServer::GetAttributeValues",
              (unsigned int)AttributeValues);
            std::wstring::_Tidy_deallocate(Src);
            std::unique_ptr<LdapSearchResult>::~unique_ptr<LdapSearchResult>(&v55);
            if ( (_QWORD)v53 )
            {
              std::_Destroy_range<std::allocator<std::wstring>>(v53, *((_QWORD *)&v53 + 1), v34, v35);
              std::_Deallocate<16>(v53, (v54 - v53) & 0xFFFFFFFFFFFFFFE0uLL);
            }
          }
        }
        else
        {
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"TryGetADRegistrationConfiguration",
            L"LdapServer::GetStringValues",
            (unsigned int)StringValues);
          std::unique_ptr<LdapSearchResult>::~unique_ptr<LdapSearchResult>(&v55);
          if ( (_QWORD)v53 )
          {
            std::_Destroy_range<std::allocator<std::wstring>>(v53, *((_QWORD *)&v53 + 1), v21, v22);
            std::_Deallocate<16>(v53, (v54 - v53) & 0xFFFFFFFFFFFFFFE0uLL);
          }
        }
      }
      else
      {
        Logger::TraceError(
          L"%s: %s failed with error code: 0x%08x.",
          L"TryGetADRegistrationConfiguration",
          L"LdapServer::GetRootDSE",
          (unsigned int)RootDSE);
        std::unique_ptr<LdapSearchResult>::~unique_ptr<LdapSearchResult>(&v55);
        if ( (_QWORD)v53 )
        {
          std::_Destroy_range<std::allocator<std::wstring>>(v53, *((_QWORD *)&v53 + 1), v17, v18);
          std::_Deallocate<16>(v53, (v54 - v53) & 0xFFFFFFFFFFFFFFE0uLL);
        }
      }
    }
    else
    {
      Logger::TraceError(
        L"%s: %s failed with error code: 0x%08x.",
        L"TryGetADRegistrationConfiguration",
        L"LdapServer::Connect",
        (unsigned int)v11);
      std::unique_ptr<LdapSearchResult>::~unique_ptr<LdapSearchResult>(&v55);
      if ( (_QWORD)v53 )
      {
        std::_Destroy_range<std::allocator<std::wstring>>(v53, *((_QWORD *)&v53 + 1), v14, v15);
        std::_Deallocate<16>(v53, (v54 - v53) & 0xFFFFFFFFFFFFFFE0uLL);
      }
    }
  }
  catch ( std::exception v58 )
  {
    v50 = "Unknown exception";
    if ( v59 )
      v50 = v59;
    Logger::TraceError(L"%s: unhandled exception: %hs", L"TryGetADRegistrationConfiguration", v50);
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2145648611;
    v52[0] = LastError;
    v58 = &std::bad_alloc::`vftable';
    o___std_exception_destroy_0(&v59);
    v13 = v52[0];
    v5 = v60;
  }
  ldap_value_freeW(vals);
  std::unique_ptr<LdapServer>::~unique_ptr<LdapServer>(&v57);
  std::wstring::_Tidy_deallocate(v5);
  return v13;
}

```

## disassembly

```asm
0x18009ecec  mov     [rsp+arg_18], rbx
0x18009ecf1  push    rsi
0x18009ecf2  push    rdi
0x18009ecf3  push    r13
0x18009ecf5  push    r14
0x18009ecf7  push    r15
0x18009ecf9  sub     rsp, 0F0h
0x18009ed00  mov     rax, cs:__security_cookie
0x18009ed07  xor     rax, rsp
0x18009ed0a  mov     [rsp+118h+var_30], rax
0x18009ed12  mov     r13, r8
0x18009ed15  mov     r15, rdx
0x18009ed18  mov     r14, rcx
0x18009ed1b  mov     [rsp+118h+var_98], rcx
0x18009ed23  lea     rdx, aTrygetadregist; "TryGetADRegistrationConfiguration"
0x18009ed2a  lea     rcx, aSStarted; "%s started"
0x18009ed31  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18009ed36  nop
0x18009ed37  mov     [rsp+118h+vals], 0
0x18009ed40  xorps   xmm0, xmm0
0x18009ed43  movdqu  [rsp+118h+var_E0], xmm0
0x18009ed49  mov     [rsp+118h+var_D0], 0
0x18009ed52  mov     ecx, 10h; Size
0x18009ed57  call    cs:__imp_malloc
0x18009ed5d  mov     rdi, rax
0x18009ed60  mov     [rsp+118h+var_B8], rax
0x18009ed65  test    rax, rax
0x18009ed68  jz      short loc_18009ED7B
0x18009ed6a  mov     qword ptr [rax], 0
0x18009ed71  mov     qword ptr [rax+8], 0
0x18009ed79  jmp     short loc_18009ED7D
0x18009ed7b  xor     edi, edi
0x18009ed7d  mov     [rsp+118h+var_C8], rdi
0x18009ed82  mov     ecx, 8; Size
0x18009ed87  call    cs:__imp_malloc
0x18009ed8d  mov     rsi, rax
0x18009ed90  mov     [rsp+118h+var_B8], rax
0x18009ed95  test    rax, rax
0x18009ed98  jz      short loc_18009EDA3
0x18009ed9a  mov     qword ptr [rax], 0
0x18009eda1  jmp     short loc_18009EDA5
0x18009eda3  xor     esi, esi
0x18009eda5  mov     qword ptr [rsp+118h+var_E8], 0
0x18009edae  mov     [rsp+118h+var_B8], rsi
0x18009edb3  lea     rcx, [rsp+118h+var_E8]
0x18009edb8  call    ??1?$unique_ptr@VLdapServer@@U?$default_delete@VLdapServer@@@std@@@std@@QEAA@XZ; std::unique_ptr<LdapServer>::~unique_ptr<LdapServer>(void)
0x18009edbd  mov     rcx, r14
0x18009edc0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009edc5  mov     rdx, rax; unsigned __int16 *
0x18009edc8  mov     rcx, rsi; this
0x18009edcb  call    ?Connect@LdapServer@@QEAAJPEBG@Z; LdapServer::Connect(ushort const *)
0x18009edd0  mov     ebx, eax
0x18009edd2  test    eax, eax
0x18009edd4  jns     short loc_18009EE2F
0x18009edd6  mov     r9d, eax
0x18009edd9  lea     r8, aLdapserverConn; "LdapServer::Connect"
0x18009ede0  lea     rdx, aTrygetadregist; "TryGetADRegistrationConfiguration"
0x18009ede7  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18009edee  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009edf3  nop
0x18009edf4  lea     rcx, [rsp+118h+var_C8]
0x18009edf9  call    ??1?$unique_ptr@VLdapSearchResult@@U?$default_delete@VLdapSearchResult@@@std@@@std@@QEAA@XZ; std::unique_ptr<LdapSearchResult>::~unique_ptr<LdapSearchResult>(void)
0x18009edfe  nop
0x18009edff  mov     rcx, qword ptr [rsp+118h+var_E0]
0x18009ee04  test    rcx, rcx
0x18009ee07  jz      short loc_18009EE2A
0x18009ee09  mov     rdx, qword ptr [rsp+118h+var_E0+8]
0x18009ee0e  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18009ee13  mov     rcx, qword ptr [rsp+118h+var_E0]
0x18009ee18  mov     rdx, [rsp+118h+var_D0]
0x18009ee1d  sub     rdx, rcx
0x18009ee20  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18009ee24  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009ee29  nop
0x18009ee2a  jmp     loc_18009F291
0x18009ee2f  mov     r8, rdi; struct LdapSearchResult *
0x18009ee32  mov     rcx, rsi; this
0x18009ee35  call    ?GetRootDSE@LdapServer@@QEAAJPEAPEAGPEAVLdapSearchResult@@@Z; LdapServer::GetRootDSE(ushort * *,LdapSearchResult *)
0x18009ee3a  mov     ebx, eax
0x18009ee3c  test    eax, eax
0x18009ee3e  jns     short loc_18009EE99
0x18009ee40  mov     r9d, eax
0x18009ee43  lea     r8, aLdapserverGetr; "LdapServer::GetRootDSE"
0x18009ee4a  lea     rdx, aTrygetadregist; "TryGetADRegistrationConfiguration"
0x18009ee51  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18009ee58  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009ee5d  nop
0x18009ee5e  lea     rcx, [rsp+118h+var_C8]
0x18009ee63  call    ??1?$unique_ptr@VLdapSearchResult@@U?$default_delete@VLdapSearchResult@@@std@@@std@@QEAA@XZ; std::unique_ptr<LdapSearchResult>::~unique_ptr<LdapSearchResult>(void)
0x18009ee68  nop
0x18009ee69  mov     rcx, qword ptr [rsp+118h+var_E0]
0x18009ee6e  test    rcx, rcx
0x18009ee71  jz      short loc_18009EE94
0x18009ee73  mov     rdx, qword ptr [rsp+118h+var_E0+8]
0x18009ee78  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18009ee7d  mov     rcx, qword ptr [rsp+118h+var_E0]
0x18009ee82  mov     rdx, [rsp+118h+var_D0]
0x18009ee87  sub     rdx, rcx
0x18009ee8a  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18009ee8e  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009ee93  nop
0x18009ee94  jmp     loc_18009F291
0x18009ee99  lea     rdx, aConfigurationn; "configurationNamingContext"
0x18009eea0  lea     rcx, [rsp+118h+var_90]
0x18009eea8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009eead  lea     r9, [rsp+118h+var_E0]
0x18009eeb2  mov     r8, rax
0x18009eeb5  mov     rdx, rdi
0x18009eeb8  mov     rcx, rsi
0x18009eebb  call    ?GetStringValues@LdapServer@@QEAAJPEAVLdapSearchResult@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@@Z; LdapServer::GetStringValues(LdapSearchResult *,std::wstring,std::vector<std::wstring> &)
0x18009eec0  mov     ebx, eax
0x18009eec2  test    eax, eax
0x18009eec4  jns     short loc_18009EF1F
0x18009eec6  mov     r9d, eax
0x18009eec9  lea     r8, aLdapserverGets_0; "LdapServer::GetStringValues"
0x18009eed0  lea     rdx, aTrygetadregist; "TryGetADRegistrationConfiguration"
0x18009eed7  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18009eede  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009eee3  nop
0x18009eee4  lea     rcx, [rsp+118h+var_C8]
0x18009eee9  call    ??1?$unique_ptr@VLdapSearchResult@@U?$default_delete@VLdapSearchResult@@@std@@@std@@QEAA@XZ; std::unique_ptr<LdapSearchResult>::~unique_ptr<LdapSearchResult>(void)
0x18009eeee  nop
0x18009eeef  mov     rcx, qword ptr [rsp+118h+var_E0]
0x18009eef4  test    rcx, rcx
0x18009eef7  jz      short loc_18009EF1A
0x18009eef9  mov     rdx, qword ptr [rsp+118h+var_E0+8]
0x18009eefe  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18009ef03  mov     rcx, qword ptr [rsp+118h+var_E0]
0x18009ef08  mov     rdx, [rsp+118h+var_D0]
0x18009ef0d  sub     rdx, rcx
0x18009ef10  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18009ef14  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009ef19  nop
0x18009ef1a  jmp     loc_18009F291
0x18009ef1f  lea     rdx, aCn62a0ff2e97b9; "CN=62a0ff2e-97b9-4513-943f-0d221bd30080"...
0x18009ef26  lea     rcx, [rsp+118h+Src]
0x18009ef2e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009ef33  nop
0x18009ef34  mov     rcx, qword ptr [rsp+118h+var_E0]
0x18009ef39  mov     rdx, [rcx+10h]
0x18009ef3d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009ef42  mov     r10, rax
0x18009ef45  mov     r9, [rsp+118h+var_60]
0x18009ef4d  mov     rcx, [rsp+118h+var_58]
0x18009ef55  sub     rcx, r9
0x18009ef58  cmp     rdx, rcx
0x18009ef5b  lea     rcx, [rsp+118h+Src]; Src
0x18009ef63  ja      short loc_18009EF91
0x18009ef65  lea     rdi, [rdx+r9]
0x18009ef69  mov     [rsp+118h+var_60], rdi
0x18009ef71  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009ef76  mov     rbx, rax
0x18009ef79  lea     r8, [rdx+rdx]; Size
0x18009ef7d  lea     rcx, [rax+r9*2]; void *
0x18009ef81  mov     rdx, r10; Src
0x18009ef84  call    memmove_0
0x18009ef89  xor     ecx, ecx
0x18009ef8b  mov     [rbx+rdi*2], cx
0x18009ef8f  jmp     short loc_18009EF9E
0x18009ef91  mov     [rsp+118h+var_F8], rdx; __int64
0x18009ef96  mov     r9, r10
0x18009ef99  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x18009ef9e  lea     rcx, [rsp+118h+Src]
0x18009efa6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009efab  mov     r8, rax
0x18009efae  lea     rdx, aTrygetadregist; "TryGetADRegistrationConfiguration"
0x18009efb5  lea     rcx, aSDrsConfgDnS; "%s: DRS confg dn %s"
0x18009efbc  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18009efc1  mov     [rsp+118h+var_E8], 0
0x18009efc9  lea     rcx, [rsp+118h+Src]
0x18009efd1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009efd6  mov     rdx, rax; unsigned __int16 *
0x18009efd9  lea     rax, [rsp+118h+vals]
0x18009efde  mov     [rsp+118h+var_F0], rax; unsigned __int16 ***
0x18009efe3  lea     rax, [rsp+118h+var_E8]
0x18009efe8  mov     [rsp+118h+var_F8], rax; unsigned int *
0x18009efed  mov     rcx, rsi; this
0x18009eff0  call    ?GetAttributeValues@LdapServer@@QEAAJPEBG00PEAKPEAPEAPEAG@Z; LdapServer::GetAttributeValues(ushort const *,ushort const *,ushort const *,ulong *,ushort * * *)
0x18009eff5  mov     ebx, eax
0x18009eff7  test    eax, eax
0x18009eff9  jns     short loc_18009F062
0x18009effb  mov     r9d, eax
0x18009effe  lea     r8, aLdapserverGeta; "LdapServer::GetAttributeValues"
0x18009f005  lea     rdx, aTrygetadregist; "TryGetADRegistrationConfiguration"
0x18009f00c  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18009f013  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18009f018  nop
0x18009f019  lea     rcx, [rsp+118h+Src]
0x18009f021  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009f026  nop
0x18009f027  lea     rcx, [rsp+118h+var_C8]
0x18009f02c  call    ??1?$unique_ptr@VLdapSearchResult@@U?$default_delete@VLdapSearchResult@@@std@@@std@@QEAA@XZ; std::unique_ptr<LdapSearchResult>::~unique_ptr<LdapSearchResult>(void)
0x18009f031  nop
0x18009f032  mov     rcx, qword ptr [rsp+118h+var_E0]
0x18009f037  test    rcx, rcx
0x18009f03a  jz      short loc_18009F05D
0x18009f03c  mov     rdx, qword ptr [rsp+118h+var_E0+8]
0x18009f041  call    ??$_Destroy_range@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@YAXPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEAV10@AEAV?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::wstring>>(std::wstring *,std::wstring * const,std::allocator<std::wstring> &)
0x18009f046  mov     rcx, qword ptr [rsp+118h+var_E0]
0x18009f04b  mov     rdx, [rsp+118h+var_D0]
0x18009f050  sub     rdx, rcx
0x18009f053  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18009f057  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18009f05c  nop
0x18009f05d  jmp     loc_18009F291
0x18009f062  lea     rsi, [r15+20h]
0x18009f066  mov     qword ptr [rsi+10h], 0
0x18009f06e  mov     rcx, rsi
0x18009f071  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009f076  xor     ecx, ecx
0x18009f078  mov     [rax], cx
0x18009f07b  mov     [r15+10h], rcx
0x18009f07f  mov     rcx, r15
0x18009f082  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009f087  xor     ecx, ecx
0x18009f089  mov     [rax], cx
0x18009f08c  mov     [r13+10h], rcx
0x18009f090  mov     rcx, r13
0x18009f093  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009f098  xor     ecx, ecx
0x18009f09a  mov     [rax], cx
0x18009f09d  xor     edi, edi
0x18009f09f  cmp     edi, [rsp+118h+var_E8]
0x18009f0a3  jnb     loc_18009F23F
0x18009f0a9  mov     rdx, [rsp+118h+vals]
0x18009f0ae  mov     rdx, [rdx+rdi*8]
0x18009f0b2  lea     rcx, [rsp+118h+var_90]
0x18009f0ba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009f0bf  nop
0x18009f0c0  lea     rcx, [rsp+118h+var_90]
0x18009f0c8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009f0cd  mov     r8, rax
0x18009f0d0  lea     rdx, aTrygetadregist; "TryGetADRegistrationConfiguration"
0x18009f0d7  lea     rcx, aSReadKeywordsF; "%s: read keywords found value %s"
0x18009f0de  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18009f0e3  lea     rcx, [rsp+118h+var_90]
0x18009f0eb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009f0f0  mov     rcx, rax
0x18009f0f3  mov     r8d, 0Ch
0x18009f0f9  lea     rdx, aAzureadname; "azureADName:"
0x18009f100  call    cs:__imp__o__wcsnicmp
0x18009f106  lea     rcx, [rsp+118h+var_90]
0x18009f10e  test    eax, eax
0x18009f110  jnz     short loc_18009F14C
0x18009f112  lea     r8d, [rax+0Ch]
0x18009f116  lea     rdx, [rsp+118h+var_50]
0x18009f11e  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18009f123  mov     rdx, rax
0x18009f126  mov     rcx, r15
0x18009f129  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18009f12e  lea     rcx, [rsp+118h+var_50]
0x18009f136  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009f13b  mov     rcx, r15
0x18009f13e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009f143  lea     rcx, aSReadTenantNam; "%s: read tenant name %s"
0x18009f14a  jmp     short loc_18009F1AB
0x18009f14c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009f151  mov     rcx, rax
0x18009f154  mov     r8d, 0Ah
0x18009f15a  lea     rdx, aAzureadid; "azureADId:"
0x18009f161  call    cs:__imp__o__wcsnicmp
0x18009f167  lea     rcx, [rsp+118h+var_90]
0x18009f16f  test    eax, eax
0x18009f171  jnz     short loc_18009F1BC
0x18009f173  lea     r8d, [rax+0Ah]
0x18009f177  lea     rdx, [rsp+118h+var_50]
0x18009f17f  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18009f184  mov     rdx, rax
0x18009f187  mov     rcx, rsi
0x18009f18a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18009f18f  lea     rcx, [rsp+118h+var_50]
0x18009f197  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009f19c  mov     rcx, rsi
0x18009f19f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009f1a4  lea     rcx, aSReadTenantIdS; "%s: read tenant id %s"
0x18009f1ab  lea     rdx, aTrygetadregist; "TryGetADRegistrationConfiguration"
0x18009f1b2  mov     r8, rax
0x18009f1b5  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18009f1ba  jmp     short loc_18009F22B
0x18009f1bc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009f1c1  mov     rcx, rax
0x18009f1c4  mov     r8d, 12h
0x18009f1ca  lea     rdx, aEnterprisedrsn_0; "enterpriseDrsName:"
0x18009f1d1  call    cs:__imp__o__wcsnicmp
0x18009f1d7  test    eax, eax
0x18009f1d9  jnz     short loc_18009F22B
0x18009f1db  lea     r8d, [rax+12h]
0x18009f1df  lea     rdx, [rsp+118h+var_50]
0x18009f1e7  lea     rcx, [rsp+118h+var_90]
0x18009f1ef  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18009f1f4  mov     rdx, rax
0x18009f1f7  mov     rcx, r13
0x18009f1fa  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18009f1ff  lea     rcx, [rsp+118h+var_50]
0x18009f207  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009f20c  mov     rcx, r13
0x18009f20f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009f214  mov     r8, rax
0x18009f217  lea     rdx, aTrygetadregist; "TryGetADRegistrationConfiguration"
0x18009f21e  lea     rcx, aSReadEnterpris; "%s: read enterprise DRS name %s"
  ... truncated ...
```
