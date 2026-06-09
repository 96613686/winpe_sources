# CtapPluginInternal::GetKcmKeyFromSameApp(void * const,wil::basic_zstring_view<ushort>,unsigned __int64,unsigned __int64 *)

- ea: `0x180121730`
- end: `0x1801219ad`
- name: `?GetKcmKeyFromSameApp@CtapPluginInternal@@YAJQEAXV?$basic_zstring_view@G@wil@@_KPEA_K@Z`
- size: `637`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021bac`

## callees

- `0x180017764`
- `0x180017a88`
- `0x180020584`
- `0x180020614`
- `0x180036da4`
- `0x180036dc8`
- `0x180052df0`
- `0x1800d8900`
- `0x180120e34`
- `0x180121730`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1801217b3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18012184d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1801217b3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18012184d`
- `ncrypt!NCryptOpenKey` at `0x180121920`
- `ncrypt!NCryptOpenKey` at `0x180121920`
- `cryptngc!NgcGetUserIdKeyName` at `0x1801218c2`
- `cryptngc!NgcGetUserIdKeyName` at `0x1801218c2`

## string_xrefs

- `0x18012176c`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x1801217c1`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180121805`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x18012185b`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x1801218d2`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`
- `0x180121930`: `onecore\ds\security\fido\ctap\transports_modern\ctappluginuv.cpp`

## pseudocode

```c
__int64 __fastcall CtapPluginInternal::GetKcmKeyFromSameApp(
        __int64 a1,
        _QWORD *a2,
        NCRYPT_PROV_HANDLE a3,
        NCRYPT_KEY_HANDLE *a4)
{
  int token_information; // eax
  unsigned int LastError; // ebx
  void *v10; // rcx
  void *v12; // rdi
  const char *v13; // r9
  int v14; // eax
  void *v15; // rcx
  PSID *v16; // rsi
  const char *v17; // r9
  LPWSTR v18; // rax
  int UserIdKeyName; // eax
  const WCHAR *v20; // rbx
  SECURITY_STATUS v21; // eax
  DWORD dwFlags; // [rsp+20h] [rbp-50h]
  DWORD dwFlagsa; // [rsp+20h] [rbp-50h]
  LPWSTR StringSid; // [rsp+30h] [rbp-40h] BYREF
  LPWSTR v25; // [rsp+38h] [rbp-38h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+40h] [rbp-30h] BYREF
  LPCWSTR pszKeyName; // [rsp+48h] [rbp-28h] BYREF
  void *Block; // [rsp+50h] [rbp-20h] BYREF
  _QWORD v29[3]; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  Block = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, a1);
  LastError = token_information;
  if ( token_information < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D5,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      (const char *)(unsigned int)token_information,
      dwFlags);
    v10 = Block;
    if ( !Block )
      return LastError;
LABEL_3:
    operator delete(v10);
    return LastError;
  }
  StringSid = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  v12 = Block;
  if ( !ConvertSidToStringSidW(*(PSID *)Block, &StringSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2D7,
                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
                  v13);
LABEL_7:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&StringSid);
    if ( !v12 )
      return LastError;
    v10 = v12;
    goto LABEL_3;
  }
  Block = 0;
  v14 = wil::get_token_information_nothrow<_TOKEN_APPCONTAINER_INFORMATION,0>(&Block, a1);
  LastError = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DB,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      (const char *)(unsigned int)v14,
      dwFlags);
    v15 = Block;
    if ( !Block )
      goto LABEL_7;
LABEL_11:
    operator delete(v15);
    goto LABEL_7;
  }
  v16 = (PSID *)Block;
  v25 = 0;
  if ( !*(_QWORD *)Block )
    goto LABEL_18;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v25,
    0);
  if ( !ConvertSidToStringSidW(*v16, &v25) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2DF,
                  (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
                  v17);
LABEL_15:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v25);
    if ( !v16 )
      goto LABEL_7;
    v15 = v16;
    goto LABEL_11;
  }
  v18 = v25;
  if ( !v25 )
LABEL_18:
    v18 = StringSid;
  v29[0] = v18;
  v29[2] = *a2;
  v29[1] = 0;
  pszKeyName = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pszKeyName,
    0);
  UserIdKeyName = NgcGetUserIdKeyName(v29, 0, &pszKeyName);
  LastError = UserIdKeyName;
  if ( UserIdKeyName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2E9,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      (const char *)(unsigned int)UserIdKeyName,
      dwFlags);
LABEL_21:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszKeyName);
    goto LABEL_15;
  }
  v20 = pszKeyName;
  phKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    &phKey,
    0);
  v21 = NCryptOpenKey(a3, &phKey, v20, 0, 0);
  LastError = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2EC,
      (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctappluginuv.cpp",
      (const char *)(unsigned int)v21,
      dwFlagsa);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
    goto LABEL_21;
  }
  *a4 = phKey;
  phKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&pszKeyName);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&v25);
  if ( v16 )
    operator delete(v16);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&StringSid);
  if ( v12 )
    operator delete(v12);
  return 0;
}

```

## disassembly

```asm
0x180121730  push    rbp
0x180121732  push    rbx
0x180121733  push    rsi
0x180121734  push    rdi
0x180121735  push    r12
0x180121737  push    r14
0x180121739  push    r15
0x18012173b  mov     rbp, rsp
0x18012173e  sub     rsp, 70h
0x180121742  mov     r15, rdx
0x180121745  mov     [rbp+Block], 0
0x18012174d  mov     rdx, rcx
0x180121750  mov     rsi, rcx
0x180121753  lea     rcx, [rbp+Block]
0x180121757  mov     r14, r9
0x18012175a  mov     r12, r8
0x18012175d  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x180121762  mov     ebx, eax
0x180121764  test    eax, eax
0x180121766  jns     short loc_180121795
0x180121768  mov     rcx, [rbp+38h]; this
0x18012176c  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180121773  mov     r9d, eax; char *
0x180121776  mov     edx, 2D5h; void *
0x18012177b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180121780  mov     rcx, [rbp+Block]; Block
0x180121784  test    rcx, rcx
0x180121787  jz      short loc_18012178E
0x180121789  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18012178e  mov     eax, ebx
0x180121790  jmp     loc_18012199E
0x180121795  xor     edx, edx
0x180121797  mov     [rbp+StringSid], 0
0x18012179f  lea     rcx, [rbp+StringSid]
0x1801217a3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1801217a8  mov     rdi, [rbp+Block]
0x1801217ac  lea     rdx, [rbp+StringSid]; StringSid
0x1801217b0  mov     rcx, [rdi]; Sid
0x1801217b3  call    cs:__imp_ConvertSidToStringSidW
0x1801217b9  test    eax, eax
0x1801217bb  jnz     short loc_1801217E7
0x1801217bd  mov     rcx, [rbp+38h]; this
0x1801217c1  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1801217c8  mov     edx, 2D7h; void *
0x1801217cd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801217d2  mov     ebx, eax
0x1801217d4  lea     rcx, [rbp+StringSid]
0x1801217d8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1801217dd  test    rdi, rdi
0x1801217e0  jz      short loc_18012178E
0x1801217e2  mov     rcx, rdi
0x1801217e5  jmp     short loc_180121789
0x1801217e7  mov     rdx, rsi
0x1801217ea  mov     [rbp+Block], 0
0x1801217f2  lea     rcx, [rbp+Block]
0x1801217f6  call    ??$get_token_information_nothrow@U_TOKEN_APPCONTAINER_INFORMATION@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_APPCONTAINER_INFORMATION@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_APPCONTAINER_INFORMATION,0>(wistd::unique_ptr<_TOKEN_APPCONTAINER_INFORMATION,wil::details::token_info_deleter> &,void *)
0x1801217fb  mov     ebx, eax
0x1801217fd  test    eax, eax
0x1801217ff  jns     short loc_180121829
0x180121801  mov     rcx, [rbp+38h]; this
0x180121805  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18012180c  mov     r9d, eax; char *
0x18012180f  mov     edx, 2DBh; void *
0x180121814  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180121819  mov     rcx, [rbp+Block]; Block
0x18012181d  test    rcx, rcx
0x180121820  jz      short loc_1801217D4
0x180121822  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180121827  jmp     short loc_1801217D4
0x180121829  mov     rsi, [rbp+Block]
0x18012182d  mov     [rbp+var_38], 0
0x180121835  cmp     qword ptr [rsi], 0
0x180121839  jz      short loc_18012188E
0x18012183b  xor     edx, edx
0x18012183d  lea     rcx, [rbp+var_38]
0x180121841  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180121846  mov     rcx, [rsi]; Sid
0x180121849  lea     rdx, [rbp+var_38]; StringSid
0x18012184d  call    cs:__imp_ConvertSidToStringSidW
0x180121853  test    eax, eax
0x180121855  jnz     short loc_180121885
0x180121857  mov     rcx, [rbp+38h]; this
0x18012185b  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180121862  mov     edx, 2DFh; void *
0x180121867  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18012186c  mov     ebx, eax
0x18012186e  lea     rcx, [rbp+var_38]
0x180121872  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180121877  test    rsi, rsi
0x18012187a  jz      loc_1801217D4
0x180121880  mov     rcx, rsi
0x180121883  jmp     short loc_180121822
0x180121885  mov     rax, [rbp+var_38]
0x180121889  test    rax, rax
0x18012188c  jnz     short loc_180121892
0x18012188e  mov     rax, [rbp+StringSid]
0x180121892  mov     [rbp+var_18], rax
0x180121896  lea     rcx, [rbp+pszKeyName]
0x18012189a  mov     rax, [r15]
0x18012189d  xor     edx, edx
0x18012189f  mov     [rbp+var_8], rax
0x1801218a3  mov     [rbp+var_10], 0
0x1801218ab  mov     [rbp+pszKeyName], 0
0x1801218b3  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1801218b8  lea     r8, [rbp+pszKeyName]
0x1801218bc  xor     edx, edx
0x1801218be  lea     rcx, [rbp+var_18]
0x1801218c2  call    cs:__imp_NgcGetUserIdKeyName
0x1801218c8  mov     ebx, eax
0x1801218ca  test    eax, eax
0x1801218cc  jns     short loc_1801218F4
0x1801218ce  mov     rcx, [rbp+38h]; this
0x1801218d2  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x1801218d9  mov     r9d, eax; char *
0x1801218dc  mov     edx, 2E9h; void *
0x1801218e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801218e6  lea     rcx, [rbp+pszKeyName]
0x1801218ea  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x1801218ef  jmp     loc_18012186E
0x1801218f4  mov     rbx, [rbp+pszKeyName]
0x1801218f8  lea     rcx, [rbp+phKey]
0x1801218fc  xor     edx, edx
0x1801218fe  mov     [rbp+phKey], 0
0x180121906  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18012190b  xor     r9d, r9d; dwLegacyKeySpec
0x18012190e  mov     [rsp+70h+dwFlags], 0; int
0x180121916  mov     r8, rbx; pszKeyName
0x180121919  lea     rdx, [rbp+phKey]; phKey
0x18012191d  mov     rcx, r12; hProvider
0x180121920  call    cs:__imp_NCryptOpenKey
0x180121926  mov     ebx, eax
0x180121928  test    eax, eax
0x18012192a  jns     short loc_18012194F
0x18012192c  mov     rcx, [rbp+38h]; this
0x180121930  lea     r8, aOnecoreDsSecur_24; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x180121937  mov     r9d, eax; char *
0x18012193a  mov     edx, 2ECh; void *
0x18012193f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180121944  lea     rcx, [rbp+phKey]
0x180121948  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18012194d  jmp     short loc_1801218E6
0x18012194f  mov     rax, [rbp+phKey]
0x180121953  lea     rcx, [rbp+phKey]
0x180121957  mov     [r14], rax
0x18012195a  mov     [rbp+phKey], 0
0x180121962  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180121967  lea     rcx, [rbp+pszKeyName]
0x18012196b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180121970  lea     rcx, [rbp+var_38]
0x180121974  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180121979  test    rsi, rsi
0x18012197c  jz      short loc_180121986
0x18012197e  mov     rcx, rsi; Block
0x180121981  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180121986  lea     rcx, [rbp+StringSid]
0x18012198a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x18012198f  test    rdi, rdi
0x180121992  jz      short loc_18012199C
0x180121994  mov     rcx, rdi; Block
0x180121997  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18012199c  xor     eax, eax
0x18012199e  add     rsp, 70h
0x1801219a2  pop     r15
0x1801219a4  pop     r14
0x1801219a6  pop     r12
0x1801219a8  pop     rdi
0x1801219a9  pop     rsi
0x1801219aa  pop     rbx
0x1801219ab  pop     rbp
0x1801219ac  retn
```
